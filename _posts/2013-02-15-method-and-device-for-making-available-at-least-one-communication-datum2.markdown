---

title: Method and device for making available at least one communication datum
abstract: A method and a device are provided for making available at least one communication datum retrieved during consultation of a multimedia stream on a first terminal. The method includes a step of reception of a request for obtaining the at least one communication datum, a step of extraction of the at least one communication datum from the multimedia stream, a step of transmission to at least one second terminal of the at least one communication datum extracted. The communication datum transmitted thus makes it possible to implement on the second terminal an application making it possible to establish a multimedia communication between the second terminal and a remote device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09549002&OS=09549002&RS=09549002
owner: ORANGE
number: 09549002
owner_city: Paris
owner_country: FR
publication_date: 20130215
---
This Application is a Section 371 National Stage Application of International Application No. PCT FR2013 050313 filed Feb. 15 2013 the content of which is incorporated herein by reference in its entirety and published as WO 2013 128094 on Sep. 6 2013 not in English.

The invention lies in the field of telecommunication networks. It relates to a device and a method for making available by a first terminal at least one communication datum intended for at least one second terminal and allowing the setting up of a multimedia communication between the second terminal and a remote terminal.

A service of Click to Call type also called immediate call is a very widespread application in the field of Internet applications. From the consultation of a web page displaying phone numbers a user can by clicking on the displayed phone numbers trigger the setting up of a phone call to the user who can be contacted by the phone numbers displayed from for example a VoIP Voice over Internet Protocol phone terminal connected to his or her consultation terminal. The call can also be sent from a mobile terminal for example the number of which has been entered into the Click to Call application beforehand.

In order to set up the call from any terminal the technology of the prior art requires the prior registration by a user of the numbers of the terminal from which the user wishes to make the call. The use of the Click to Call application on a computer of PC Personal Computer type shared between several users for example in a cybercafe or a family home becomes complicated. Indeed each user generally possesses his or her own terminal and wishes to make the call from it. Each user must then systematically enter his or her phone numbers into the application of the shared terminal. This results in a waste of time for the user and a mechanism for disclosing his or her personal numbers that has poor security.

Other similar problems appear when retrieving a television program in which a user is prompted to make a call or send an SMS Short Message Service to play order products or obtain more information on the retrieved program. No simple and automatic technique exists allowing the user to set up a communication from any phone terminal that he or she has access to. The user must memorize the numbers retrieved from the television program dial them on his or her terminal and trigger the call. The user can thus lose time by memorizing and dialing the number to contact. Moreover this mechanism can lead to setting up unwanted communications in the event of a user error concerning the memorized numbers.

An exemplary embodiment of the present disclosure proposes a method for making available at least one communication datum retrieved during the consultation of a multimedia stream on a first terminal. The method comprises a step of receiving a request to obtain the at least one communication datum a step of extracting the at least one communication datum from the multimedia stream a step of transmitting the at least one extracted communication datum to at least one second terminal the at least one transmitted communication datum making it possible to implement on the second terminal an application making it possible to set up a multimedia communication between the second terminal and a remote device.

Correlatively the invention relates to a terminal for making available at least one communication datum retrieved during the consultation of a multimedia stream on the terminal comprising means for receiving a request to obtain the at least one communication datum means for extracting the at least one communication datum from the multimedia stream means for transmitting the at least one extracted communication datum to at least one second terminal the at least one transmitted communication datum making it possible to implement on the second terminal an application making it possible to set up a multimedia communication between the at least one second terminal and a remote device.

The method for making available a communication datum allows a user to obtain the communication datum for example on his or her mobile terminal without having to manually enter the communication datum on his or her terminal. A simple interaction with the first terminal allows him or her to obtain the communication datum on the second terminal. The first terminal can be a terminal of personal computer type or a television or a terminal for retrieving any multimedia stream.

The method according to the invention makes it possible to simplify the access and the use of communication data retrieved on different terminals.

The various modes or characteristics of embodiment mentioned below can be added independently or in combination with each other to the steps of the method for making available defined above.

The various modes or characteristics of embodiment mentioned below can be added independently or in combination with each other to the characteristics of the device for making available defined above.

According to a particular embodiment of the invention the method for making available furthermore comprises a step of converting the at least one received communication datum into the form of a link that can be interpreted by the application of the second terminal.

The communication datum can be thus be interpreted by an application of the second terminal of the user without requiring the intervention of the user or complicated manipulation.

According to another particular embodiment of the invention the identifier of the at least one second terminal is extracted from the request to obtain the at least one communication datum. The user does not need to enter the identifier of the second terminal into the terminal retrieving the communication datum. It obtains the communication datum in a secure manner.

According to another particular embodiment of the invention the step of extracting the at least one communication datum comprises a sub step of analyzing the audio and or video data of the consulted multimedia stream. This particular embodiment of the invention makes it possible to extract a communication datum even when this datum has not been previously associated with the multimedia stream consulted on the first terminal. It makes it possible to apply the invention to any type of multimedia stream received by the first terminal.

The invention also relates to a method implemented by a second terminal for receiving at least one communication datum retrieved during the consultation of a multimedia stream on a first terminal. The method comprises a step of receiving the at least one communication datum a step of receiving a user validation command following the retrieving by the second terminal of the at least one received communication datum a step of implementing an application making it possible to set up a multimedia communication between the second terminal and a remote device from the at least one communication datum in the form of a link that can be interpreted by the application of the second terminal.

Correlatively the invention also relates to a terminal for receiving at least one communication datum retrieved during the consultation of a multimedia stream on a retrieving terminal comprising means for receiving the at least one communication datum means for receiving a user validation command following the retrieval by the receiving terminal of the at least one received communication datum means for implementing an application making it possible to set up a multimedia communication between the receiving terminal and a remote device from the at least one communication datum in the form of a link that can be interpreted by the application of the receiving terminal.

The user of the receiving terminal can thus with a simple click on the receiving terminal trigger a multimedia communication on the basis of a communication datum that has been retrieved for it on another terminal. Unlike the techniques of the prior art it is the receiving terminal that triggers the communication desired by the user. The user thus has the option of triggering the communication immediately or triggering it later.

The various modes or characteristics of embodiment mentioned below can be added independently or in combination with each other to the steps of the receiving method defined above.

The various modes or characteristics of embodiment mentioned below can be added independently or in combination with each other to the characteristics of the receiving device defined above.

According to a particular embodiment of the invention the receiving method comprises prior to the step of implementing the application a step of converting the at least one received communication datum into the form of a link that can be interpreted by the application of the second terminal. Thus when the first terminal cannot carry out the conversion the second terminal carries out the conversion of the communication datum itself so that the triggering of the communication remains simple for the user.

According to another particular embodiment of the invention the at least one communication datum is associated with additional information allowing the user to identify the at least one communication datum.

This particular embodiment of the invention is particularly advantageous in the case where the second terminal receives several communication data or if the user wishes to store the communication datum and be able to identify it later.

According to another particular embodiment of the invention the receiving method comprises a prior step of sending a request to obtain the at least one communication datum to the first terminal. Correlatively the receiving terminal comprises means for sending a request to obtain the at least one communication datum to the retrieving terminal.

For example the receiving terminal is thus capable of interacting with the first terminal and obtaining information without the need to associate the receiving terminal with the first terminal beforehand.

The invention also relates to a computer program including instructions for executing the method for making available according to any of the particular embodiments of the invention mentioned earlier when the program is executed by a processor.

The invention also relates to a computer program including instructions for executing the receiving method according to any of the particular embodiments of the invention mentioned earlier when the program is executed by a processor.

The invention also relates to a storage medium readable by a processor on which is stored a program including instructions for executing the method for making available according to any of the particular embodiments of the invention mentioned earlier.

The invention also relates to a storage medium readable by a processor on which is stored a program including instructions for executing the receiving method according to any of the particular embodiments of the invention mentioned earlier.

According to a particular embodiment of the invention a user possessing a mobile terminal T for example consults on the terminal T a web page notably displaying the phone numbers of a third party to be contacted. When the user clicks on the phone numbers displayed on the terminal T the method for making available at least one communication datum is implemented by the terminal T and the displayed phone numbers are broadcast by the terminal T for example into the form of a link that can be interpreted by an application of the terminal T. The terminal T then implements the method for receiving at least one communication datum. The received communication datum is interpreted for example on the terminal T by an application of the Click to call type previously installed on the terminal. By clicking on the number that is displayed on the terminal T the user can thus make a call for example to the terminal T if the phone numbers match those of the terminal T.

According to another particular embodiment of the invention the user consults on the terminal T a television stream in which the numbers are displayed or announced by a presenter of the television program being watched. Using his or her terminal T the user sends to the terminal T a request to obtain the numbers retrieved on the terminal T. The terminal T implements the method for making available at least one communication datum and sends to the terminal T the numbers retrieved on the terminal T. The terminal T then implements the method for receiving at least one communication datum. The user can choose for example to make a call or to send a message of SMS type using the received numbers interpreted for example by an application of the Click to call type.

In a variant of this particular embodiment of the invention instead of the numbers retrieved by the terminal T the user can request using his or her terminal T to obtain additional information on the television program that he or she is viewing. The terminal T implements the method for making available at least one communication datum and sends the communication datum to the terminal T in the form of a communication link to a web page containing the additional information requested. The terminal T then implements the method for receiving at least one communication datum. A web browsing application of the terminal T can for example interpret the communication link received and set up a communication with a server T of multimedia data. The additional information is then displayed on the terminal T.

A step REST FLX of retrieving a multimedia stream is implemented for example by the terminal T in . The multimedia stream corresponds for example to a web page that can contain text images videos sounds etc. The multimedia stream can for example also be an electronic message displayed using an electronic messaging application for example. At least one communication datum for example a phone number is displayed on the web page or in the window displaying the electronic message.

The rest of the method is described using an example of an application displaying the phone number on a web page.

The terminal T receives REC DDE a request to obtain the displayed communication datum while detecting in a step that a user has clicked on the site of the communication datum on the web page.

In order to detect the phone number selected by the user the displayed number can be displayed in a form capable of being recognized by the web browser as a communication datum for example using dedicated tags in the HTML code of the web page.

In a variant when the phone number is not in a form directly recognizable by the web browser an application incorporated into the web browser can detect the number by analyzing the source code of the web page and the contents of the source code tags. The application incorporated into the web browser can then render the displayed numbers capable of being selected by the user for example by displaying a possible action when the user passes his or her selection pointer over the number. The selection of the number thus detected can be made by a simple click of the user on the number or a right click allowing the rest of the method to be triggered.

The terminal T extracts EXTRACT in a step the corresponding phone number for example by analyzing the source code of the web page as described above.

According to a particular embodiment of the invention in a step the terminal T then generates GEN FIC a file comprising the extracted communication datum. The generated file is for example a file in the HTML HyperText Markup Language or XML eXtensible Markup Language format that can be interpreted by a web browsing application.

In a step the terminal T broadcasts TRANS DAT the extracted communication datum or the generated file containing the communication datum to the nearby terminals. For example the terminal T uses a connection of Bluetooth type or a local network of WIFI type for broadcasting.

The terminals near the terminal T can then receive the communication datum thus broadcast and notably the terminal T of the user.

According to a particular embodiment of the invention the user of the terminal T can have clicked on several phone numbers and wish to receive on his or her terminal T all the phone numbers on which he or she has clicked.

The terminal T then extracts all the communication data corresponding to the successive phone numbers on which the user has clicked. In the step of generating the file the terminal T also implements a step of aggregating the extracted communication data. Thus a single file containing several communication data will be broadcast.

According to another particular embodiment of the invention the terminal T can also add to the generated file information relating to at least one communication datum allowing the user to identify the communication datum such as the information resulting from the metadata of the web page notably corresponding to the data of page title or paragraph type for example.

In a step the terminal T receives REC DAT a communication datum for example in the form of an HTML or XML file that can be interpreted by a web browsing application of the terminal T.

According to another particular embodiment of the invention the communication datum can also be received in another data format for example a file in the text format or in the CSV type for Comma Separated Values format or another format. For example for a file in the text format each line will correspond to a number and separators for example a double separate a phone number data element from the various additional information items which can for example be the name and first name of the person in the title of the HTML page in question a title of an advertisement for example. Each line of the file ends in the ASCII for American Standard Code for Information Interchange code corresponding to a carriage return.

According to this embodiment the terminal T carries out a conversion of the transmitted communication datum so that it can be interpreted by an application of the terminal T for example a web browsing application and the communication datum is then converted for example into the form of an HTML or XML file. Thus for example the text file described above is converted into an HTML file by adding the HTML code tags making it possible to define an HTML page such as to enclose the content. Inside the page a table can be created by the tags and to present the content with a formulation of the following type 

Each line is enclosed by the tags and and at the level of a line each data element is enclosed by the tags and .

In this example the conversion of the text file into an HTML file consists in adding the tags indicating that it is an HTML file then in positioning each line of the text file determined from the carriage return of the text file between 2 tags and of the table while removing the ASCII code of this carriage return. Then inside a line each data element determined in the text file by the aforementioned separator is positioned between 2 tags and and to remove the characters separating the data elements. The file thus created is stored in a file with the extension .html .

In a variant the application of the terminal T can also be a mobile telephony or IP telephony application. In this case the communication datum is converted into the form of a contact datum or of phone number data that can be directly used by the telephony application.

According to another particular embodiment of the invention the terminal T can receive a group of communication data originating from one and the same terminal or from different terminals. The terminal T then implements a step AGG DAT of aggregating communication data and displays to the user all the received communication data. The communication data can be received in a file that can be interpreted by a web browsing application of the terminal T.

In a variant they can be received in another format and require a step CONV DAT of data conversion. The conversion step makes it possible to obtain a data file that can be interpreted for example by a web browsing application. According to this variant the received communication data are converted for example into the form of links inserted into an HTML or XML file displayed by the web browsing application.

In a step the communication datum or data are visually or vocally retrieved for the user on the terminal T.

According to a particular embodiment of the invention the terminal T can carry out a security analysis of the communication data received in order to identify if the communication data received contain any data harmful to the operation of the terminal T for example data of the computer virus type.

According to another particular embodiment of the invention the receiving of communication data by the terminal T can be associated with a ringtone or a vibration implemented by the terminal T in order to inform the user that the datum has been received.

The user can then send a validation command REC CMD to the terminal T making it possible to validate at least one communication datum received and to allow its storage at least temporarily in the memory of the terminal T. The validated communication datum can then be used in order to set up ETBL COM a multimedia communication for example a phone call or a sending of a message to the terminal corresponding to the number associated with the communication datum.

If the user wishes for an immediate call from the correspondent the set up of the call can be implemented in the step for example by an application of Click to call type installed on the terminal T.

The user can also preserve the communication datum in the memory of his or her terminal T in order to set up a communication later on using a mobile or IP telephony application or a messaging application.

A step REST FLX of retrieving a multimedia stream is implemented for example by the terminal T in . The multimedia stream for example corresponds to a television program in which a communication datum is retrieved on the terminal T. This communication datum can for example correspond to a phone number optionally associated with one or more SMS for Short Message Service codes which appears in the image or which is announced by a program presenter. The phone number for example allows a user to take part in a game to obtain additional information relating to the retrieved program or to order products presented in the program. The communication datum can also correspond to a communication link for example an Internet link making it possible to obtain additional information relating to the retrieved program.

In a step the terminal T receives REC DDE a request to obtain the retrieved communication datum for example originating from the terminal T of the user.

According to a particular embodiment of the invention the type of the communication datum requested for example a communication link or phone numbers can be associated with the request for the communication datum and extracted from the request.

According to a particular embodiment of the invention in a step the terminal T extracts from the request to obtain the communication datum an identifier of the terminal T and temporarily stores REG ID this identifier in the memory.

According to another particular embodiment of the invention the terminal T receives the request to obtain a communication datum originating from a remote control that makes it possible to interact with the terminal T. The remote control allows a user to indicate to the terminal T a wish to make a communication or to receive more information on a terminal. For example different keys or combinations of different keys can be used on the remote control to indicate the wish of the user.

The terminal T not having received any terminal identifier associated with the request the request to obtain the datum and the communication datum that will be extracted in the rest of the method can be temporarily stored while awaiting a validation request from the terminal.

In a variant of this particular embodiment the request to obtain a communication datum can originate from a vocal command made by the user intended for the terminal T or via the remote control of the terminal T.

According to a particular embodiment of the invention the terminal T can receive several requests to obtain communication data originating from one and the same terminal or from different terminals. The received requests are then temporarily stored in the memory of the terminal T and processed in succession. According to another particular embodiment of the invention the search for the communication datum can be shared for example if the requests to obtain the datum are received in a short time interval in the order of a few seconds for example. If the requests originate from one and the same terminal the terminal T can reply to it by the subsequent simultaneous or successive sending of communication data.

According to another particular embodiment of the invention the terminal T then implements a step of analyzing the retrieved multimedia stream ANL FLX in order to extract the communication datum from the multimedia stream. For example the analysis can consist in an analysis of OCR Optical Character Recognition type. This analysis is implemented on the images of the multimedia stream in order to identify a displayed communication datum. The OCR analysis is conventionally known in the prior art for example in Videotext OCR using hidden Markov models by Natarajan P Elm ieh B Schwartz B and Makhoul J. published in 62001. Other known OCR techniques can be used to implement this analysis.

The analysis can also consist in an analysis of the audio data of the multimedia stream for example by vocal recognition in order to identify a read communication datum. The analysis can also consist in a combination of these two types of analysis on the audio and video data.

In a variant of this particular embodiment of the invention several communication data can be extracted for example to take account of the reaction time of a user following the broadcasting of a number during a broadcast program.

According to another particular embodiment of the invention the step of analyzing the multimedia stream can be implemented continuously on the multimedia stream in order to constantly extract communication data retrieved by any program. The communication data are then stored and time stamped temporarily in the memory on the terminal T in order to be used where applicable upon the receiving of a request to obtain a communication datum.

According to another particular embodiment of the invention the analysis step can be implemented by a remote server on the multimedia stream. According to the choice of implementation of this particular embodiment of the invention the analysis can be implemented continuously or on demand. This embodiment makes it possible to share the analysis of the multimedia stream between several users. In this particular embodiment of the invention the terminal T sends to the remote server a command to analyze the multimedia stream as well as an item of information on the time interval over which the analysis must be implemented. The remote server sends it in return at least one communication datum identified in the multimedia stream.

According to another particular embodiment of the invention the communication datum can be sent simultaneously with the multimedia stream as an additional datum associated with the stream.

The terminal T extracts EXTRACT in a step the communication datum of the analyzed data from the multimedia stream or following the receiving of the communication datum originating from a remote server or the multimedia stream when the datum is sent simultaneously to the stream.

According to a particular embodiment of the invention the terminal T can generate a file similar to the step GEN FIC described in relation to .

In a step the terminal T transmits TRANS DAT the extracted communication datum to the terminal T using the previously stored terminal identifier. For example the terminal T uses a connection of Bluetooth type or a local network of WIFI type for transmission.

According to a particular embodiment of the invention before carrying out the transmission of the extracted communication datum the terminal T can wait until a request is received to validate a terminal for example the terminal T. The terminal T temporarily stores the extracted communication datum in the memory. Upon receiving the validation request by the terminal T for example the terminal T extracts from the validation request the identifier of the terminal T and transmits the stored communication datum to it. This embodiment is particularly advantageous when the user wishes to interact on a multimedia stream retrieved by the terminal T but does not have any terminal T nearby. Often a remote control is close to the retrieving terminal T and it is therefore quicker for the user to interact with an instant of the multimedia stream using the remote.

When the user is available to trigger a communication he or she can use the terminal T in order to validate the request for a communication datum on the terminal T and receive it on his or her terminal T.

According to a particular embodiment of the invention the terminal T can have extracted several communication data from the multimedia stream. In this case the terminal T sends the extracted communication data to the terminal T. According to a particular embodiment of the invention the terminal T aggregates the communication data in a file before the transmission to the terminal T.

In a variant the terminal T can also add to the generated file items of information relating to at least one communication datum allowing the user to identify the communication datum.

According to another particular embodiment the method described in can also be applied to the case where the communication datum is displayed REST FLX on the terminal of personal computer type T. The terminal T receives REC DDE a request to obtain a communication datum from terminal T. In this embodiment a software application that may have been previously installed on the terminal T makes it possible to search for and detect an active window of the terminal T. An active window of the terminal T can for example be a web browser window or a window of a messaging application open on the terminal T or else a word processing document. The software application also makes it possible to detect in the active window at least one displayed communication datum.

In this embodiment it is possible to detect phone numbers or links of hypertext type as well as additional information associated with these communication data and allowing them to be identified.

After receiving the request to obtain a communication datum the terminal T extracts from the request to obtain a datum an identifier of the terminal T and temporarily stores REG ID this identifier in the memory.

The terminal T analyzes the multimedia stream retrieved on the terminal T in order to extract at least one communication datum. The multimedia stream can for example be an active window of the terminal T ANL FLX . The extraction of the communication data can for example be carried out by analyzing the source code of a web page or of the electronic message if the active window is a window of a web browsing application or a window of an electronic messaging application. If the active window is of a word processing application the terminal T can analyze the contents of the document displayed in the active window.

The terminal T extracts EXTRACT at least one communication datum of the analyzed data from the multimedia stream and generates a file in a similar manner to the step GEN FIC described in relation to . In this embodiment the user not having previously selected a particular communication datum on the screen of the terminal T it is probable that the terminal T will extract more than one communication datum retrieved by the multimedia stream. In this variant the terminal T can aggregate the extracted communication data into one and the same file.

The terminal T transmits TRANS DAT the extracted communication datum to the terminal T using the previously stored terminal identifier. For example the terminal T uses a connection of Bluetooth type or a local network of WIFI type for transmission. illustrates steps of the method for receiving at least one communication datum according to another particular embodiment of the invention. The receiving method is for example implemented by the terminal T which is situated near the terminal T implementing the method for making available a communication datum for example as described in relation to .

During the consultation of a multimedia stream on the terminal T the terminal T then makes in a step a request to obtain ENV DDE a communication datum retrieved on the terminal T.

According to a particular embodiment of the invention a dedicated application is installed on the terminal T allowing the terminal to interact with the terminal T.

In a step the terminal T receives in return REC DAT the communication datum for example in the form of an HTML or XML file that can be interpreted by a web browsing application of the terminal T or in any other format that can be interpreted by a telephony application for example.

According to a particular embodiment of the invention the terminal T can receive several communication data either in succession or aggregated into one and the same datum file.

In a step the communication datum or data are visually or vocally retrieved for the user on the terminal T.

The user can then send a validation command REC CMD to the terminal T making it possible to validate at least one communication datum received and to allow it to be at least temporarily stored in the memory of the terminal T. The validated communication datum can then be used in order to set up ETBL COM a multimedia communication for example a phone call or a sending of a message toward the terminal corresponding to the number associated with the communication datum.

If the user wishes for an immediate call from the correspondent the set up of the call can be implemented in the step for example by an application of Click to call type installed on the terminal T.

The user can also preserve the communication datum in the memory of his or her terminal T in order to set up a communication later on using a mobile or IP telephony application or a messaging application.

According to another particular embodiment of the invention when the communication datum is a communication link making it possible to obtain additional information related to the retrieved program the terminal T sets up ETBL COM a communication with a remote server of multimedia data using the communication link. The communication link contains an addressing datum making it possible to address the remote server. The remote server then sends to the terminal T items of information related to the retrieved program.

The device comprises a storage space for example a memory MEM a processing unit equipped for example with a microprocessor FROG and controlled by the computer program PG implementing the method for making available at least one communication datum as described in the invention with reference to .

At set up the code instructions of the computer program are for example loaded into a RAM memory before being executed by the processor of the processing unit . The microprocessor of the processing unit implements the steps of the method for making available at least one communication datum retrieved during the consultation of a multimedia stream on the device and notably the steps of receiving a request to obtain the at least one communication datum of extracting the at least one communication datum from the multimedia stream of transmitting to at least one terminal the at least one extracted communication datum the transmitted at least one communication datum making it possible to implement on the terminal an application making it possible to set up a multimedia communication between the terminal and a remote server according to the instructions of the computer program .

To do this the device comprises means for retrieving REST a multimedia stream for example a screen and loudspeakers.

The device also comprises means for receiving and transmitting data I O such as a network connection interface for example of Bluetooth WIFI infrared or IP type.

A module for extracting the at least one communication datum from the multimedia stream is controlled by a computer program PG implemented by a processor PROC using a memory MEM.

According to a particular embodiment of the invention the device comprises means MEM for storing at least temporarily an identifier of a terminal sending a request to obtain a communication datum. The storing means also make it possible according to another particular embodiment of the invention to store communication data received simultaneously in the multimedia stream.

The device comprises a storage space for example a memory MEM a processing unit equipped for example with a microprocessor FROG and controlled by the computer program PG implementing the method for receiving at least one communication datum as described in the invention with reference to .

At set up the instructions of computer program code are for example loaded into a RAM memory before being executed by the processor of the processing unit . The microprocessor of the processing unit implements the steps of the method for receiving at least one communication datum retrieved during the consultation of a multimedia stream on a terminal and notably the steps of receiving the at least one communication datum of receiving a user validation command following the retrieval by the device of the at least one received communication datum of implementing an application making it possible to set up a multimedia communication between the device and a remote device from the at least one communication datum in the form of a link that can be interpreted by the application of the device according to the instructions of the computer program .

To do this the device comprises means for receiving and transmitting I O data such as a network connection interface for example of Bluetooth WIFI infrared or IP type.

According to a particular embodiment of the invention the receiving and transmitting means allow the device to make a request to obtain a communication datum.

The receiving and transmitting means also allow the device to receive a transmitted communication datum.

The device also comprises means for retrieving REST communication data for example a screen and loud speakers. An application of the device capable of interpreting the communication datum received by the device is controlled by a computer program PG implemented by a processor PROC using a memory MEM.

According to a particular embodiment of the invention this application can be a web browsing application.

According to another particular embodiment of the invention this application can be a telephony or messaging application.

According to a particular embodiment of the invention the device comprises means MEM for at least temporarily storing a communication datum received.

The device also comprises communicating means COM making it possible to set up a multimedia communication between the device and a remote device for example a phone terminal or a server. The communicating means can for example be a network interface making it possible to set up a communication on a mobile or a circuit switched network or an IP network.

Although the present disclosure has been described with reference to one or more examples workers skilled in the art will recognize that changes may be made in form and detail without departing from the scope of the disclosure and or the appended claims.

