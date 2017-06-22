---

title: Terminal and method for hiding and restoring message
abstract: A terminal to hide a message includes an input unit to receive a signal to hide a message and a signal to restore a hidden message; a display unit to display the message and the hidden message; and a control unit to control display of the message. The terminal hides messages or applications on a separate screen. The separate screen may be a virtual screen or a different display screen. A hidden message may be displayed on the separate screen according to a conversation partner. A hidden message may be restored to a location in which the message would have originally been displayed. A portion of the stored message may be extracted and provided to an application of the terminal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09256747&OS=09256747&RS=09256747
owner: Pantech Co., Ltd.
number: 09256747
owner_city: Seoul
owner_country: KR
publication_date: 20130204
---
This application claims priority from and the benefit under 35 U.S.C. 119 a of Korean Patent Application No. 10 2012 0019288 filed on Feb. 24 2012 the entire disclosure of which is incorporated herein by reference for all purposes.

The following description relates to data protection technology and more particularly to message hiding and message restoring technology.

Developments in the information and communications industry have increased the number of methods of acquiring information available to users. Devices like mobile terminals have become essential communication devices and are used particularly for transmitting messages and receiving messages.

Increasing device usability is accompanied by increasing interest in data protection which requires a user environment that is highly usable and more intuitive. That is increasing usability is accompanied by an increasing need for a user environment that is highly convenient and intuitive when displaying messages or managing message lists or messages.

As an example of a message display and management method if a user wishes to perform an archiving process on a specific message from an outgoing incoming message list a first message list for consolidated management of messages transmitted to and received from a large number of partners the specific message may be moved from the first message list to a message archiving list a second message list to be stored and eliminated from the first message list.

For example if the specific message to be archived is selected by the user from the first message list through a hardware button or a software button a menu screen may pop up and then the message is eliminated from the first message list if an archiving instruction is input by the user.

Accordingly it may be difficult for the user to intuitively discern which message is eliminated from the first message list or where the message is located in the second message list.

In addition since the archived messages are all stored in a storage box in a list form without distinction between conversation partners a series of processes of selecting individual messages from the list of the storage box verifying detailed contents of a message to be retrieved by the user transmission reception targets or the date and time of transmission reception and returning to the list have to be repeatedly performed in order to view the detailed contents the transmission reception targets or the date and time of transmission reception. This repetition may be the result of messages being stored in the message storage box which is integrally managed without distinction between transmission reception targets the data and time of transmission reception and the like if the messages are separately archived.

In addition when a user wishes to view previously received messages a considerable amount of time may be required for searching if there is a large history of messages.

Exemplary embodiments of the present invention provide a terminal having a data protection operation and a message hiding operation.

Additional features of the invention will be set forth in the description which follows and in part will be apparent from the description or may be learned by practice of the invention

An exemplary embodiment of the present invention discloses a terminal to hide a message including an input unit to receive a first input signal and a second input signal a control unit to hide a message in response to the first input signal and to restore the message in response to the second input signal and a display unit to display messages according to control of the control unit.

An exemplary embodiment of the present invention also discloses a method for hiding a message including receiving a first input to select a message on a main screen moving the message to a hidden screen in response to the first input and restoring the message to the main screen if a second input is received.

An exemplary embodiment of the present invention also discloses a method for hiding an application including receiving a first input to select an application on a main screen moving the application to a hidden screen in response to the first input and restoring the application to the main screen if a second input is received.

An exemplary embodiment of the present invention also discloses a method of hiding and restoring an object including receiving an input selecting an object and hiding or restoring the selected object in response to the input.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed. Other features and aspects will be apparent from the following detailed description the drawings and the claims.

Exemplary embodiments are described more fully hereinafter with reference to the accompanying drawings in which embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure is thorough and will fully convey the scope of the invention to those skilled in the art. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like reference numerals in the drawings denote like elements.

It will be understood that when an element or layer is referred to as being on another element or layer it can be directly on the other element or layer or intervening elements or layers may be present. In contrast when an element is referred to as being directly on another element or layer there are no intervening elements or layers present. It will be understood that for the purposes of this disclosure at least one of X Y and Z can be construed as X only Y only Z only or any combination of two or more items X Y and Z e.g. XYZ XYY YZ ZZ .

A terminal includes an input unit a control unit and a display unit . The terminal may further include a message database .

The terminal may be any device which can transmit messages to and receive messages from another party in a wired or wireless manner such as cellular phones personal digital assistants PDAs wireless communication devices portable devices laptop computers tablet computers desktop computer cordless phones and the like. The terminal may be a portable multi functional device such as a smart phone a smart pad and the like. The terminal may include a user interface to recognize a touch operation input from a user.

Privacy of a terminal user may be protected by enabling a message to be hidden if the user opens a message window to read or edit the message. The message refers to a message which the user does not want to reveal or wants to archive separately. The message may be a reference message a predetermined message a selected message and the like.

Ease of use may be increased in addition to protecting privacy. A hiding operation may be performed on a message and the message may be hidden within the message window through a user s simple operation. If hiding the message an original position may be hidden to be identified. Accordingly a user may verify in which position the message is hidden within the message window.

Messages may be hidden or archived for each conversation partner and therefore the user may immediately verify which conversation partners messages are hidden within the message window.

A hide target is not limited to messages and the hide target may be replaced with or expanded to all types of data which the user can hide in the terminal for information protection. For example the hide target may be phonebook data call list data schedule data or memo data. The messages may include character messages multimedia messages or multimedia contents. The multimedia messages may be character messages including photos moving images music and the like. The multimedia message may be for example image data or moving image data.

The message hiding operation may be applied to message related applications such as Kakao Talk and the like in addition to general message programs.

The display unit may display a message on a screen. The message may be displayed in the form of a speech bubble for each conversation partner. The speech bubble may be a graphic user interface object in which contents of the message transmitted to and received from a corresponding conversation partner within a small box may be recorded. For example on the screen of the terminal messages transmitted and received between a user and a conversation partner A may be displayed in chronological order. Messages transmitted to the conversation partner A from the user may be displayed on the right side of the screen and on the left side of the screen messages received by the user from the conversation partner A may be displayed.

The message displayed in the form of a speech bubble for each conversation partner will be described in detail with reference to the appended drawings.

The display unit may display on the screen of the terminal at least a part of a main screen where an outgoing message and an incoming message may be displayed an outgoing hide screen where an outgoing message is hidden an incoming hide screen where an incoming message is hidden and an outgoing incoming hide screen where the hidden outgoing message and the hidden incoming message are all displayed.

The input unit may be a user interface for executing user commands such as message reading deletion editing hiding archiving and the like with respect to the message displayed on the screen through the display unit .

The input unit may receive a user input signal to hide the message displayed on the screen or to restore a hidden message. The input unit may recognize a touch operation of the user. The input unit and the display unit may be formed in the same physical space for example in a touch screen so that the user may perform the touch operation on the screen. The user input signal for hiding the message may be received according to a drag method a double tap method a rubbing method etc. with respect to the message. A drag method a double tap method and a rubbing method will be described below with reference to and .

The input unit may receive the user input signal in a direction perpendicular to a direction aligned with scroll direction of a message.

The user input signal may be received via a touch and drag method a flicking method or the like. The user input signal may be received in a position of a hide target message in the message list if hiding the message and in an empty space where the message is absent from the message list or in a message position where a hiding indicator is present if restoring the message.

The control unit may control the display unit in accordance with the user input signal received from the input unit to hide the message in a screen space or restore the message hidden in the screen space. The control unit may hide the message in the screen space corresponding to an original position of the hidden message to identify an origin of the hidden message.

If the message is provided in the form of a speech bubble for each conversation partner the control unit may perform a message hiding and restoring operation for each conversation partner.

For example message hiding may refer to the control unit displaying an outgoing hide screen and displaying an incoming hide screen on the other side. The outgoing hide screen may be disposed on a side perpendicular to a direction in which the messages are aligned in a row on the main screen. In other words the outgoing hide screen may be disposed to be perpendicular to a direction in which the messages are parallel with each other. The messages may be hidden in the screen space horizontally corresponding to the original position of the hidden message. The outgoing hidden screen and incoming hidden screen will be described below with reference to and .

For example message hiding may refer to the control unit displaying the outgoing hide screen and the incoming hide screen through a virtual view separately from a view of the main screen by controlling the display unit . The messages are hidden in the screen space horizontally and vertically corresponding to the original position of the hidden message. A virtual outgoing hide screen and incoming hide screen will be described below with reference to .

The message database DB may manage the hidden messages. The message DB may be utilized as a space for storing and managing the hidden messages. Messages restored by the user after being hidden may be eliminated from the message DB .

The control unit may provide an addition operation in conjunction with another application with respect to the hidden message. The applications may be schedules notes or bookmarks. An example of the additional operation in conjunction with the other application will be described below with reference to and .

The components of the terminal shown in may be logically separated however two or more of these components may be physically integrated or they may all be separately implemented. Although will be described with reference to the features of exemplary embodiments are not limited thereto.

The control unit includes a message hiding and restoring control unit hereinafter referred to as a message control unit of an application terminal and a call processing unit of a framework terminal. The message DB includes a local DB of the application terminal and a message service DB of the framework terminal.

A DB that stores messages such as multimedia message service MMS message service SMS and the like may not be the local DB depending on the application but rather the message service DB managed by the call processing unit of the framework terminal.

The application may perform an arithmetic operation with respect to the message service DB through the call processing unit . There may be a risk if directly changing a structure of the call processing unit of the framework terminal and the message service DB to perform the message hiding and restoring operation. For example a third application may access an application programming interface API of the changed framework and therefore problems may be caused at the time of use.

If transmitting and receiving messages the messages stored in the message service DB of the framework terminal are archived as is and the message control unit stores a hiding message or attribute information identifying the hiding message in a separate local DB provided within the application. The message control unit may store both the hiding message and the attribute information concerning the hiding message.

If receiving a message hiding input signal from a user the message control unit may call a call processing API operation and requests a message list from the call processing unit . The call processing unit may search for the message list from the message service DB and return the searched message list to the message control unit .

The message control unit may access the local DB which is generated asynchronously from the above described process to obtain a hiding message list. The hiding message list obtained from the local DB and the message list returned from the message service DB may be compared and if a message coinciding with the hiding message of the local DB is present in the message service DB the corresponding message may be hidden on the screen.

If receiving the message hiding input signal with respect to a message from the user the message control unit may store at least one of the hiding message and the attribute information concerning the hiding message in the local DB . If data of the local DB is updated the local DB transmits a hiding request message to the message control unit . The message control unit may receive the hiding request message to hide the message on the screen.

If receiving a message restoring input signal with respect to a message from a user the message control unit may search for the corresponding hiding message from the local DB and restore the searched hiding message on the screen. The local DB may transmit a restoring request message to the message control unit and the message control unit receives the restoring request message to restore the corresponding message on the screen. A message list may be searched from the message service DB through the call processing unit . The hiding message of the local DB and messages from the message list of the message service DB may be compared and the corresponding hiding message may be restored if the compared messages are the same based on the comparison result.

If the message restoring input signal with respect to a hiding message is received from a user the message control unit searches for the attribute information of the corresponding hiding message from the local DB . A message corresponding to the attribute information may be searched from the message list of the message service DB through the call processing unit using the attribute information of the hiding message and when the corresponding message is searched the searched message is restored on the screen. For example the message may be tagged and stored and later searched according to the tag. Further the tag the tagged message and or the message may be extracted and used for another application.

The terminal may display a main screen where an outgoing message and an incoming message are displayed an outgoing hide screen where an outgoing message may be hidden and an incoming hide screen where an incoming message may be hidden. The terminal may display the outgoing hide screen on one side perpendicular to a direction in which messages are aligned in a row on the main screen and the incoming hide screen on the other side.

The terminal may select a display screen based on specifications of a display of the terminal. The specifications of the display may include a screen size and a screen direction of the terminal .

For example referring to if a terminal screen is longer in a transverse direction the number of pages displayed on a single screen may be 2. In other words the main screen and the incoming hide screen may be displayed on a single screen as shown in a screen or the main screen and the outgoing hide screen may be displayed in a single screen as shown in a screen . In other words the single screen may be divided into two pages because a size of the screen is reduced if the terminal screen is longer in the transverse direction.

Referring to an incoming message may be hidden on the left side of the screen on a hide screen corresponding to a main screen as shown in a screen and an outgoing message may be hidden on the right side as shown in a screen . The hidden outgoing and incoming messages may be displayed outside the main screen as shown in a screen .

Referring to the terminal may display a main screen an incoming hide screen and an outgoing hide screen on a single screen. This screen may corresponds to a terminal screen is longer in a transverse direction or to a terminal with a larger screen size such as a tablet PC a notebook PC a laptop etc.

If the terminal is longer in a transverse direction and the main screen and the hide screen are displayed together on the same screen the ratio of a width of a message of the main screen may be applied in a longitudinal direction. This may compensate for a phenomenon in which a message is laterally elongated and becomes visually awkward if the terminal is converted into a transverse screen.

If performing a pinch in operation on the main screen by a user the incoming hide screen and the outgoing hide screen may be displayed and if performing pinch out operation the screen returns to display the main screen .

Referring to the terminal may display an outgoing hide screen and an incoming hide screen through a virtual view separated from a view of a main screen.

Multi view refers a concept in which a user may be aware of messages displayed in different three dimensional 3D spaces. On a screen space horizontally and vertically corresponding to an original position of a hidden message messages may be hidden. Displaying the hidden message using the multi view may provide relative freedom from limitations on the size of the terminal screen.

Referring to in a screen a drag input may be performed with respect to a message positioned on a main screen by a user. The terminal may hide the message in a corresponding dragging direction as shown in a screen . A drag input signal may be a long press and drag operation but is not limited thereto. If a drag input is performed with respect to the hidden message in the opposite direction by the user as shown in the screen the terminal may display the hidden message on the main screen as shown in the screen .

Referring to in a screen a multi touch drag input may be performed by a user on the screen where a message is hidden. The terminal may display all hidden messages together with an output message and an incoming message on a main screen as shown in a screen . A drag input signal may be a double finger drag operation but is not limited thereto.

Referring to in a screen a multi touch drag input may be performed by a user in the same direction as the user input direction of on a screen where an output message and an incoming message are displayed. The terminal may provide a screen in which histories of hidden outgoing and incoming messages are displayed as shown in a screen . A drag input signal may be a double finger drag operation but is not limited thereto.

Referring to in a screen a drag input may be performed with respect to a background of a main screen by a user. The terminal may provide a screen in which histories of hidden outgoing and incoming messages are displayed as shown in the screen . A drag input signal may be a long press and drag operation but is not limited thereto.

Referring to in the screen a multi touch drag input may be performed by a user on a screen in which a message is hidden. The terminal restores the hidden message on a main screen as shown in a screen . A drag input signal may be a double finger drag operation.

The screens described with reference to and are exemplary and a variety of screen configurations according to a variety of user input signals may be implemented by those skilled in the related art.

Referring to in a screen a reference input for example a press operation may be performed with respect to a message by a user. A link may be formed with another application as a result of the reference input. The application may be schedule a memo or a bookmark as shown in a screen .

An operation of recording specific schedule contents may be automatically performed by the terminal or directly input by the user.

Although and illustrate message hiding linked with the schedule application aspects of the present invention are not limited to the screens depicted in and .

Although illustrates message hiding linked with the memo application aspects of the present invention are not limited to the screens depicted in .

If setting at least one bookmark a bookmark shape may be formed on an upper portion of the screen . A set bookmark may be verified as shown in a screen if selecting the bookmark shape by the user.

Although illustrates message hiding linked with the bookmark application aspects of the present invention are not limited to the screens depicted in .

If the message hiding operation of the terminal is linked with the other application a variety of input signals may be used to operate the application. For example a user input such as a long press a double tap or the like may be used. A pop up method in which a selection window pops up on a screen of the terminal may be used.

In a screen illustrates a tap operation on a message which is linked with an application. The message hiding operation may be linked with an application using a specific user operation and a pop up method. A pop up screen may appear as shown in screen if selecting a message from the screen through a tap operation. The pop up window may include menu items such as hiding bookmark storing in schedule storing in memo using corresponding operation as default and the like. A default menu item may be provided in a checkbox format and a corresponding operation instruction may be matched with a selected operation to be provided if a user checks the checkbox one time to perform the selected operation.

For example if a user checks the checkbox of the default menu item to perform a hiding operation a tap operation may be selected as a hiding operation. The default menu item may be changed for example in an environment setting.

Hereinafter a message hiding operation being linked with a schedule application using the specific user operation and pop up method will be described.

Referring to and if selecting a message through a tap operation on a screen by a user a pop up window appears as shown in a screen . If selecting the schedule application operation by the user a calendar is displayed on a screen. Keywords related to the schedule are extracted from the message as shown in a screen and schedule contents are recorded on the calendar as shown in a screen .

Referring to and if selecting a message through a tap operation on a screen a pop up window appears as shown in a screen . A memo window is displayed in a screen if selecting a memo application operation in the screen . Memo contents are recorded if the user enters them as shown in a screen .

Referring to a message is selected through a tap operation on a screen . If selecting a bookmark application operation on a screen a bookmark mode is entered and a bookmark with respect to the message may be set as shown in a screen .

A user may hide a message or restore a hidden message through an operation such as a drag method a double tap method a rubbing method or the like.

Referring to a user input signal for hiding a message or restoring a hidden message may be received via the drag method. For example as shown in a screen if performing a drag operation with respect to a message on a main screen in a direction a corresponding message may be hidden as shown in a screen .

In contrast if performing the drag operation in the opposite direction on the screen where the message is hidden the hidden message may be restored as shown in the screen . The drag operation may be a long tap and flick operation.

Referring to a user input signal for hiding a message or restoring a hidden message may be received via the double tap method. For example as shown in a screen if performing the double tap operation with respect to a message on a main screen a corresponding message may be hidden as shown in a screen . In contrast if the double tap operation is performed on the screen where the message is hidden the hidden message may be restored as shown in the screen .

Referring to a user input signal for hiding a message or restoring a hidden message may be received via the rubbing method. For example if performing the rubbing operation with respect to a message on a main screen as shown in a screen a corresponding message may be hidden as shown in a screen . In contrast if performing the rubbing operation on the screen where the message is hidden the hidden message may be restored as shown in the screen .

Referring to if a user performs a reference operation for example a flick operation with respect to a message to be hidden as shown in a screen the terminal displays a bookmark for identifying an origin of the hidden message while hiding a corresponding message as shown in a screen .

Referring to if a user performs a reference operation for example a rubbing operation with respect to a message to be hidden as shown in a screen the terminal hides a corresponding message in a semi transparent manner as shown in a screen .

Although and illustrate message hiding aspects of the present invention are not limited to the screens depicted in and .

Referring to histories of two hidden outgoing message and a hidden incoming message may be displayed in a single window. In contrast referring to the history of the two hidden outgoing message may be displayed on a single screen.

In operation the terminal hides a message on a reference screen space in accordance with the user input signal. The terminal may set the message as in a hidden state and hide the message in a screen space corresponding to an original position of the hidden message to identify an origin of the hidden message.

In operation the terminal may hide the message for each conversation partner with respect to messages provided in the form of speech bubbles.

According to aspects of the exemplary embodiments in operation the terminal may display an outgoing hide screen on one side of a main screen perpendicular to a direction in which messages are aligned in a row on the main screen and an incoming hide screen on the other side. The message may be hidden in a screen space horizontally corresponding to the original position of the hidden message.

According to aspects of the exemplary embodiments in operation the terminal may display the outgoing hide screen and the incoming hide screen through a virtual view separately from the main screen. The message may be hidden in a screen space horizontally and vertically corresponding to the original position of the hidden message.

According to aspects of the exemplary embodiments the terminal may provide an additional operation in conjunction with another application with respect to the hidden message. The application may be a schedule application a memo application a bookmark application etc.

According to exemplary embodiments if a user protects messages in a terminal user convenience and user data protection may be increased.

If a user of the terminal opens a message window to view conversation contents the privacy of the user may be protected by hiding a message.

According to aspects of the exemplary embodiments a user may verify in which position a message is hidden within a message window which may increase ease of use.

According to aspects of the exemplary embodiments a message may be hidden for each conversation partner such that a user may verify which conversation partners messages are hidden within the message window.

According to aspects of the exemplary embodiments a hide target may be messages or may be replaced with or expanded to all types of data which the user can hide in the terminal for information protection.

For example the hide target may be phonebook data call list data schedule management data or memo data.

According to aspects of the exemplary embodiments the messages may include character messages multimedia messages or multimedia contents.

It will be apparent to those skilled in the art that various modifications and variation can be made in the present invention without departing from the spirit or scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

