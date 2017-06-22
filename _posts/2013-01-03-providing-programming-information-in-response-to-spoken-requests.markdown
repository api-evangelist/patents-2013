---

title: Providing programming information in response to spoken requests
abstract: A system allows a user to obtain information about television programming and to make selections of programming using conversational speech. The system includes a speech recognizer that recognizes spoken requests for television programming information. A speech synthesizer generates spoken responses to the spoken requests for television programming information. A user may use a voice user interface as well as a graphical user interface to interact with the system to facilitate the selection of programming choices.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08805691&OS=08805691&RS=08805691
owner: Intel Corporation
number: 08805691
owner_city: Santa Clara
owner_country: US
publication_date: 20130103
---
This application is a continuation of U.S. patent application Ser. No. 11 729 213 filed on Mar. 28 2007 which is a continuation of U.S. patent application Ser. No. 09 494 714 filed on Jan. 31 2000 now abandoned .

This invention relates generally to providing programming information in response to spoken requests.

Electronic programming guides provide a graphical user interface on a television display for obtaining information about television programming. Generally an electronic programming guide provides a grid like display which lists television channels in rows and programming times corresponding to those channels in columns. Thus each program on a given channel at a given time is provided with a block in the electronic programming guide. The user may select particular programs for viewing by mouse clicking using a remote control on a highlighted program in the electronic programming guide.

While electronic programming guides have a number of advantages they also suffer from a number of disadvantages. For one as the number of television programs increases the electronic programming guides become somewhat unmanageable. There are so many channels and so many programs that providing a screen sized display of the programming options becomes unworkable.

In addition the ability to interact remotely with the television screen through a remote control is somewhat limited. Basically the selection technique involves using a remote control to move a highlighted bar to select the desired program. This is time consuming when the number of programs is large.

Thus there is a continuing need for a better way to provide programming information in response to spoken requests.

An electronic programming guide may respond to conversational speech with spoken or visual responses including graphical user interfaces in accordance with one embodiment of the present invention. In some embodiments of the present invention a limited domain may be utilized to increase the accuracy of speech recognition. A limited or small domain allows focused applications such as an electronic programming guide application to be implemented wherein the recognition of speech is improved because the vocabulary is limited.

A variety of techniques may be utilized for speech recognition. However in some embodiments of the present invention the process may be simplified by using surface parsing. In surface parsing questions or statements are handled separately and there is no movement to convert questions into the same subject verb object order as a statement. As a result conventional commercially available software may be utilized for some aspects of speech recognition with surface parsing. However in some embodiments of the present invention deep parsing with movement may be more desirable.

As used herein the term conversational as applied to a speech responsive system involves the ability of the system to respond to broadly or variously phrased requests to use conversational history to develop the meaning of pronouns to track topics as topics change and to use reciprocity. Reciprocity is the use of some terms that were used in the questions as part of the answer.

In some embodiments of the present invention a graphical user interface may be utilized which may be similar to conventional electronic programming guides. This graphical user interface may include a grid like display of television channels and times. In other embodiments either no graphical user interface at all may be utilized or a more simplified graphical user interface may be utilized which is narrowed by the spoken requests that are received by the system.

In any case the system uses a voice user interface VUI which interfaces between the spoken request for information from the user and the system. The voice user interface and a graphical user interface advantageously communicate with one another so that each knows any inputs that the other has received. That is if information is received from the graphical user interface to provide focus to a particular topic such as a television program this information may be provided to the voice user interface to synchronize with the graphical user interface. This may improve the ability of the voice user interface to respond to requests for information since the system then is fully cognizant of the context in which the user is speaking.

The voice user interface may include a number of different states including the show selected the audio volume pause and resume and listen mode. The listen mode may include three listening modes never once and always. The never mode means that the system is not listening and the speech recognizer is not running. The once mode means that the system only listens for one query. After successfully recognizing a request it returns to the never mode. The always mode means that the system will always listen for queries. After answering one query the system starts listening again.

A listen state machine utilized in one embodiment of the present invention may reflect whether the system is listening to the user working on what the user has said or has rejected what the user has said. A graphical user interface may add itself as a listener to the listen state machine so that it may reflect the state to the user. There are four states in the listen state machine. In the idle state the system is not listening. In the listening state the system is listening to the user. In the working state the system has accepted what the user has said and is starting to act on it. In the rejected state what the user said has been rejected by the speech recognition engine.

The state machine may be set up to allow barge in. Barge in occurs when the user speaks while the system is operating. In such case when the user attempts to barge in because the user knows what the system is going to say or is no longer interested in the answer the system yields to the user.

Referring to the system software may include an application that may be an electronic programming guide application in one embodiment of the present invention. In the illustrated embodiment the application includes a voice user interface and a graphical user interface . The application may also include a database which provides information such as the times programs genre and subject matter of various programs stored in the database . The database may receive inquiries from the voice user interface and the graphical user interface . The graphical and voice user interfaces may be synchronized by synchronization events.

The voice user interface may also include a speech synthesizer a speech recognizer and a natural language understanding NLU unit . In other embodiments of the present invention output responses from the system may be provided on a display as text from a synthesizer other than as voice output responses The voice user interface may include a grammar which may utilized by the recognizer .

A state vector is a representation of the meaning of an utterance by a user. A state vector may be composed of a set of state variables. Each state variable has a name a value and two flags. An in context state vector may be developed by merging an utterance vector which relates to what the user said and a history vector. A history vector contains information about what the user said in the past together with information added by the system in the process of servicing a query. Thus the in context state vector may account for ambiguity arising for example from the use of pronouns. The ambiguity in the utterance vector may be resolved by resorting to a review of the history vector and particularly the information about what the user said in the past.

In any state vector including utterance history or in context state vectors the state variables may be classified as one of two types of variables. One type may indicate what information the user is asking for and the other type indicates the information the user is supplying. Borrowing from the SQL database language the terms SELECT and WHERE may be used for the two types. SELECT variables represent information a user is requesting. In other words the SELECT variable defines what the user wants the system to tell the user. This could be a show time length or show description as examples.

WHERE variables represent information that the user has supplied. A WHERE variable may define what the user has said. The WHERE variable provides restrictions on the scope of what the user has asked for. Examples of WHERE variables include show time channel title rating and genre.

Part of day range afternoon The request when is the SELECT variable. The WHERE variables include the other attributes including the title X Files and the time of day afternoon .

The information to formulate responses to user queries may be stored in a relational database in one embodiment of the present invention. A variety of software languages may be used. By breaking a query down into SELECT variables and WHERE variables the system is amenable to programming in well known database software such as Structured Query Language SQL . SQL is standard language for relational database management systems. In SQL the SELECT variable selects information from a table. Thus the SELECT command provides the list of column names from a table in a relational database. The use of a WHERE command further limits the selected information to particular rows of the table. Thus a bare SELECT command may provide all the rows in a table and the combination of a SELECT and a WHERE command may provide less than all the rows of a table including only those items that are responsive to both the SELECT and the WHERE variables. Thus by resolving spoken queries into SELECT and WHERE aspects the programming may be facilitated in some embodiments of the present invention.

Referring to a user request or query may result in a state vector with a user flag and a grounding flag . The user flag indicates whether the state variable originated from the user s utterance. The grounding flag indicates if the state variable has been grounded. A state variable is grounded when it has been spoken by the synthesizer to the user to assure mutual understanding. The VUI may repeat portions of the user s query back to the user in its answer.

Grounding is important because it gives feedback to the user about whether the system s speech recognition was correct. For example consider the following spoken interchange 

At utterance number all state variables are flagged as from the user and not yet grounded. Notice that the speech recognizer confused fifty and fifty eight. At utterance number the system has attempted to repeat the title and the channel spoken by the user and they are marked as grounded. The act of speaking parts of the request back to user lets the user know whether the speech recognizer has made a mistake. Grounding enables correction of recognition errors without requiring re speaking the entire utterance. At utterance number the user repeats and the channel is again ungrounded. At utterance number the system speaks the correct channel and therefore grounds it.

Turning next to software for speech recognition involves the use of an application program interface API in one embodiment of the present invention. For example the JAVA speech API may be utilized in one embodiment of the present invention. Thus as indicated in block initially the API recognizes an utterance as spoken by the user. The API then produces tags as indicated in block . These tags are then processed to produce the state vector as indicated in block .

In one embodiment of the present invention the JAVA speech API may be the ViaVoice software available from IBM Corporation. Upon recognizing an utterance the JAVA speech API recognizer produces an array of tags. Each tag is a string. These strings do not represent the words the user spoke but instead they are the strings attached to each production rule in the grammar. These tags are language independent strings representing the meaning of each production rule. For example in a time grammar the tags representing the low order minute digit may include text which has no meaning to the recognizer. For example if the user speaks five then the recognizer may include the tag minute in the tag array.

The natural language understanding NLU unit develops what is called an in context meaning vector indicated in . This is a combination of the utterance vector developed by the recognizer together with the history vector . The history vector includes information about what the user said in the past together with information added by the system in the process of servicing a query. The utterance vector may be a class file in an embodiment using JAVA. The history vector and a utterance vector may be merged by structural history management software to create the in context meaning vector . The history utterance and in context meaning vectors are state vectors.

The in context meaning vector is created by decoding and replacing pronouns which are commonly used in conversational speech. The in context meaning vector is then used as the new history vector Thus the system decodes the pronouns by using the speech history vector to gain an understanding of what the pronouns mean in context.

The in context meaning vector is then provided to dialog control software . The dialog control software uses a dialog control file to control the flow of the conversation and to take certain actions in response to the in context meaning vector .

These actions may be initiated by an object that communicates with the database and a language generation module . Prior to the language generation module the code is human language independent. The module converts the code from a computer format to a string tied to a particular human understood language like English. The actions object may call the synthesizer to generate speech. The actions object may have a number of methods See Table I infra .

Thus referring to the dialog control software initially executes a state control file by getting a first state pattern as indicated in block in one embodiment of the invention. Dialog control gives the system the ability to track topic changes.

The dialog control software uses a state pattern table see Table I below . Each row in the state pattern table is a state pattern and a function. The in context meaning vector is compared to the state pattern table one row at a time going from top to bottom block . If the pattern in the table row matches the state vector diamond then the function of that row is called block . The function is also called a semantic action.

Each semantic action can return one of three values CONTINUE STOP and RESTART as indicated at diamond . If the CONTINUE value is returned the next state pattern is obtained as indicated at block and the flow iterates. If the RESTART value is returned the system returns to the first state pattern block . If the STOP value is returned the system s dialog is over and the flow ends.

The action may do things such as speak to the user and perform database queries. Once a database query is performed an attribute may be added to the state vector which has the records returned from the query as a value. Thus the patterns consist of attribute value pairs where the attributes in the state pattern table correspond to the attributes in the state vector. The values in the pattern are conditions applied to the corresponding values in the state vector.

Thus in the table above the state patterns at lines are basic functions such as help turn the television on or off and tune the television and all return a STOP value.

In row six the state pattern checks to see if the time attribute is defined. If not it calls a function called defaultTime to examine the request determine what the appropriate time should be set the time attribute and return a CONTINUE value.

In row seven the pattern is empty so the function checkDBLlimits is called. A time range in the user s request is checked against the time range spanned by the database. If the user s request extends beyond the end of the database the user is notified and the time is trimmed to fit within the database range. A CONTINUE value is returned.

Row eight calls the function queryDB QueryDB transforms the state vector into an SQL query makes the query and then sets the NFOUND variable to the number of records retrieved from the database. The records returned from the query are also inserted into the state vector.

At row nine a check determines if the query done in row eight found anything. For example the user may ask When is the X Files on Saturday when in fact the X Files is really on Sunday. Rather than telling the user that the X Files is not on it is preferable that the system say that the X Files is not on Sunday but is on Sunday at 5 00 p.m . To do this the constraints of the user s inquiry must be relaxed by calling the function relaxConstraints . This action drops the time attribute from the state vector. If there were a constraint to relax relaxConstraints sets NFOUND to 1. Otherwise it leaves it at zero and returns a CONTINUE value.

Row causes a query to be repeated once the constraints are relaxed and returns a CONTINUE value. If there were no records returned from the query the system gives up tells the user of its failure in row and returns a STOP value. In row an answer is composed for the user if one record or show was found and a STOP value is returned.

In row a check determines whether more than one response record exists. Suppose X Files is on both channels and . GiveChoice tells the user of the multiple channels and asks the user which channel the user is interested in. GiveChoice returns a STOP value diamond indicating that the system s dialog turn is over. If the user tells the system a channel number then the channel number is merged into the previous inquiry stored in history.

The system tracks topic changes. If the user says something that clears the history the state pattern table simply responds to the query according to what the user said. The state pattern table responds to the state stored in the in context vector.

Turning next to the software implements structural history management SHM . Initially the flow determines at diamond whether an immediate command is involved. Immediate commands are utterances that do not query the database but instead demand immediate action. They do not involve pronouns and therefore do not require the use of structural history. An example would be Turn on the TV . In some cases an immediate command may be placed between other types of commands. The immediate command does not effect the speech history. This permits the following sequence of user commands to work properly 

The first sentence puts the X Files show into the history. The second sentence turns on the television. Since it is an immediate command the second sentence does not erase the history. Thus the pronoun it in the record command third sentence can be resolved properly.

Thus referring back to if an immediate command is involved the history is not changed as indicated in block . Next a check at diamond determines whether a list selection is involved. In some cases a query may be responded to with a list of potential shows and a request that the user verbally select one of the listed shows. The system asks the user which title the user is interested in. The user may respond that it is the Nth title. If the user utterance selects a number from a list then the system merges with history as indicated in block . Merging with history refers to an operation in which the meaning derived from the speech recognizer is combined with history in order to decode implicit references such as the use of pronouns.

Next a check at diamond determines whether the query includes both SELECT and WHERE variables. If so history is not needed to derive the in context meaning as indicated in block .

Otherwise a check determines whether the utterance includes only SELECT diamond or only WHERE diamond variables. If only a SELECT variable is involved the utterance vector is merged with the history vector block .

Similarly if the utterance includes only a WHERE variable the utterance is merged with history as indicated in block . If none of the criteria set forth in diamonds or apply then the history is not changed as indicated in block .

Thus the history vector records a previous query When is X Files on this afternoon . Thereafter the user may ask What channel is it on which has the following attributes 

Thus there is a SELECT attribute but no WHERE attribute in the user s query. As a result the history vector is needed to create an in context or merged meaning as follows 

As another example assume the history vector includes the question What is X Files about which has the following attributes 

Title Xena from How about Xena The query results in an in context meaning as follows when merged with the history vector 

Since there was no SELECT variable obtainable from the user s question the SELECT variable was obtained from the historical context i.e. from the history vector . Thus in the first example the WHERE variable was missing and in the second variable the SELECT variable was missing. In each case the missing variable was obtained from history to form an understandable in context meaning.

If an utterance has only a WHERE variable then the in context meaning vector is the same as the history vector with the utterance s WHERE variable inserted into the history vector. If the utterance has only a SELECT variable then the in context meaning is the same as the history vector with the utterance s SELECT variable inserted into the history vector. If the utterance has neither a SELECT or a WHERE variable then the in context meaning vector is the same as the history vector. If the utterance has both parts then the in context meaning is the same as that of the utterance and the in context meaning vector becomes the history vector.

The software shown in coordinates actions between the graphical user interface and the voice user interface in one embodiment of the invention. A show is a television show represented by a database record. A show is basically a database record with attributes for title start time end time channel description rating and genre.

More than one show is often under discussion. A collection of shows is represented by a ShowSet. The SHOW SET attribute is stored in the meaning vector under the SHOW SET attribute. If only one show is under discussion then that show is the SHOW SET.

If the user is discussing a particular show in the SHOW SET that show is indicated as the SELECTED SHOW attribute. If the attribute is 1 or missing from the meaning vector then no show in the SHOW SET has been selected. When the voice user interface produces a ShowSet to answer a user s question SHOW SET and SELECTED SHOW are set appropriately. When a set of shows is selected by the graphical user interface it fires an event containing an array of shows. Optionally only one of these shows may be selected. Thus referring to diamond if the user selects a set of shows an event is fired as indicated in block . In block one of those shows may be selected. When the voice user interface receives the fired event block it simply replaces the values of SHOW SET and SELECTED SHOW block in the history vector with those of a synchronization event.

When the voice user interface translates a meaning vector into the appropriate software language the statement is cached in the history vector under the attributes. This allows unnecessary database requests to be avoided. The next time the history vector is translated it is compared against the cached value in the history vector. If they match there is no need to do the time consuming database query again.

The conversational model implemented by the system accounts for two important variables in obtaining information about television programming time and shows. A point in time may be represented by the a JAVA class calendar. A time range may be represented by a time range variable. The time range variable may include a start and end calendar. The calendar is used to represent time because it provides methods to do arithmetic such as adding hours days etc.

The time range may include a start time and end time either of which may be null indicating an open time range. In a state vector time may be represented using attributes such as a WEEK RANGE which includes last this and next DAY RANGE which includes now today tomorrow Sunday Monday . . . Saturday next Sunday . . . last Sunday . . . this Sunday . . . PART OF DAY RANGE which includes this morning tonight afternoon and evening HOUR which may include the numbers one to twelve MINUTE which may include the numbers zero to fifty nine and AM PM which includes AM and PM.

Thus the time attributes may be composed to reflect a time phase in the user s utterance. For example in the question Is Star Trek on next Monday at three in the afternoon may be resolved as follows 

Since the state vector is a flat data structure in one embodiment of the invention it is much simpler and uses simpler programming. The flat data structure is made up of attribute value pairs. For example in the query When is X Files on this afternoon the request is the when part of the query. The request is an attribute whose value is when . Similarly the query has a title attribute whose value is the X Files . Thus each attribute value pair includes a name and a value. The data structure is simplified by ensuring that the values are simple structures such as integers strings lists or other database records as opposed to another state vector.

In this way the state vector contains that information needed to compute an answer for the user. The linguistic structure of the query such as whether it is a phrase a clause or a quantified set is deliberately omitted in one embodiment of the invention. This information is not necessary to compute a response. Thus the flat data structure provides that information and only that information needed to formulate a response. The result is a simpler and more useful programming structure.

The software for creating the state vector shown in in accordance with one embodiment of the present invention receives the utterance as indicated in block . An attribute of the utterance is determined as indicated in block . A non state vector value is then attached to the attribute value pair as indicated in block .

Thus referring again to the conversation model may include time attributes which may include time ranges in a time state vector. Show attributes may include a show set and selected show. The time attributes and show attributes are components of an utterance. Other components of the utterance may be who said what as indicated at and immediate commands as indicated at . The conversation model may also include rules and methods discussed herein as well as a history vector dialog control and a grammar

The methods and rules in may include a number of methods used by the unit . For example a method SetSelected may be used by the unit to tell the voice user interface what shows have been selected by the graphical user interface . The method Speak may be used to give other parts of the system such as the graphical user interface the ability to speak. If the synthesizer is already speaking then a Speak request is queued to the synthesizer and the method returns immediately.

The method SpeaklfQuiet may be used by the unit to generate speech only if the synthesizer is not already speaking. If the synthesizer is not speaking the text provided with the SpeaklfQuiet method may be given to the synthesizer . If the synthesizer is speaking then the text may be saved and spoken when the synthesizer is done speaking the current text.

One embodiment of a processor based system for implementing the capabilities described herein shown in may include a processor that communicates across a host bus to a bridge an L cache and system memory . The bridge may communicate with a bus which could for example be a Peripheral Component Interconnect PCI bus in accordance with Revision 2.1 of the PCI Electrical Specification available from the PCI Special Interest Group Portland Oreg. 97214. The bus in turn may be coupled to a display controller which drives a display in one embodiment of the invention.

The display may be a conventional television. In such case the hardware system shown in may be implemented as a set top box as shown in . The set top box sits on and controls a conventional television display .

A microphone input may lead to the audio codec AC 97 where it may be digitized and sent to memory through an audio accelerator . The AC 97 specification is available from Intel Corporation www.developer.intel.com pc supp webform ac97 . Sound data generated by the processor may be sent to the audio accelerator and the AC 97 codec and on to the speaker .

In some embodiments of the present invention there may be a problem distinguishing user commands from the audio that is part of the television program. In some cases a mute button may be provided for example in connection with a remote control in order to mute the audio when voice requests are being provided.

In accordance with another embodiment of the present invention a differential amplifier differences the audio output from the television signal and the input received at the microphone . This reduces the feedback which may occur when audio from the television is received by the microphone together with user spoken commands.

In some embodiments of the present invention a microphone may be provided in a remote control unit which is used to operate the system as shown in . For example the microphone inputs may be transmitted through a wireless interface to the processor based system and its wireless interface in one embodiment of the present invention. Alternatively the remote control unit may interface with the television receiver through its wireless interface .

The bus may be coupled to a bus bridge that may have an extended integrated drive electronics EIDE coupling in and Universal Serial Bus USB coupling i.e. a device compliant with the Universal Serial Bus Implementers Form Specification Version 1.0 www.usb.org . Finally the USB connection may couple to a series of USB hubs .

The EIDE connection may couple to a hard disk drive and a CD ROM player . In some embodiments other equipment may be coupled including a video cassette recorder VCR and a digital versatile disk DVD player not shown.

The bridge may in turn be coupled to an additional bus which may couple to a serial interface which drives a infrared interface and a modem . The interface may communicate with the remote control unit . A basic input output system BIOS memory may also be coupled to the bus .

Referring to graphical user interfaces may be displayed on a television receiver . One interface may include an electronic programming guide grid which includes a set of rows representing each channel and a set of columns representing a plurality of times of day. The grid sets forth programs on a given channel at a given time. For example the receiver may be currently tuned to the highlighted show X Files on channel two at one p.m. The display of the current program is indicated at . At two o clock a movie called The Movie comes on. A series of programs at different times and different channels are listed in association with corresponding channels.

On the right side of the display a caption gives the name of the currently viewed show in block . In addition its time a description of the show is provided at and its genre science fiction is indicated at .

With the interface shown in the user may ask a question When is Star Trek on In response the portion of the interface comprising the electronic programming guide maybe replaced by a list of programs all of which include the name Star Trek in their titles. Thus the user may then be asked to indicate which of the Star Trek programs on channels and indicated at is the one which is the subject of the user s request. The user may select one of the programs by highlighting it on the channel or description to select the desired program. In one embodiment of the present invention this may be done by operating a cursor using a remote control to move the highlighting to the desired response. The response may then be selected by pressing an enter button on the remote control to select that response.

While the present invention has been described with respect to a limited number of embodiments those skilled in the art will appreciate numerous modifications and variations therefrom. It is intended that the appended claims cover all such modifications and variations as fall within the true spirit and scope of this present invention.

