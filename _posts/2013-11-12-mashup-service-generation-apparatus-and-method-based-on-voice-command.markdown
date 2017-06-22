---

title: Mash-up service generation apparatus and method based on voice command
abstract: Provided are a mash-up service generation apparatus and method based on a voice command. The mash-up service generation apparatus includes a voice recognizer configured to convert a voice command into a character string, a mash-up natural language processor configured to extract a word corresponding to a mash-up module based on the character string, and convert the word into at least one of metadata of the mash-up module and metadata of a mash-up sequence in which a plurality of mash-up modules are combined, and a mash-up sequence processor configured to search for and select a target mash-up sequence corresponding to the metadata of the mash-up sequence, and newly generate the target mash-up sequence. Accordingly, a customized mash-up service can be provided to a user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09236049&OS=09236049&RS=09236049
owner: ELECTRONICS AND TELECOMMUNICATIONS RESEARCH INSTITUTE
number: 09236049
owner_city: Daejeon
owner_country: KR
publication_date: 20131112
---
This application claims priority to Korean Patent Application No. 10 2012 0127608 filed on Nov 12 2012 in the Korean Intellectual Property Office KIPO the entire contents of which are hereby incorporated by reference.

Example embodiments of the present invention relate in general to a mash up service generation apparatus and method and more specifically to a mash up service generation apparatus and method based on a voice command.

Generally mash up denotes combining and applying various types of contents or services to generate new contents or services. Here the various types of contents or services may be configured with a program module called a block. The mash up denotes a web based data integration application and may be generated using a mash up authoring tool that connects or combines a plurality of the above described blocks. As a detailed example of the mash up there is an application in which a map service of Daum is combined with a photograph service of Naver. When a user clicks a specific position of a map with a mouse the above described mash up allows photographs associated with the clicked position to be displayed on the map.

Here in a general mash up working process a mash up developer designs a kind of mash up to produce and searches for and selects a plurality of open application interfaces APIs to be used to produce the designed mash up. The mash up developer analyzes a map open API of Daum and an open API of Naver and checks characteristics of the respective open API services namely blocks. Here the characteristics of the blocks may be for example a communication protocol a code a data format and a type of input output data.

That is a mash up authoring apparatus places or arranges open APIs namely blocks and connects inputs and outputs of the respective blocks using a data format of the input and output of each of the blocks. Also the mash up authoring apparatus specifies scripts or codes.

Recently demand and supply for lots of smartphones tablet personal computers PCs etc. are increasing and a manipulation scheme of mobile equipment is becoming diversified in proportion to the demand and supply. Also recently due to the spread of smart devices and the generalization of open services open APIs users require various additional services.

However a current service merely provides simple voice recognition and a unilateral response namely a secretary type response and cannot use a multimedia service function that is a characteristic of smart equipment. For this reason the current service cannot be customized and provided to a user. Such a problem occurs because there are no method and apparatus that combine open APIs to automatically generate a new mash up service.

In other words a general mash up service generation apparatus generates a mash up service using a difficult programming that requires the use of a keyboard and a mouse without using the newest function such as voice recognition.

The general mash up service generation apparatus is difficult to be implemented in an environment in which a resource is limited and has a problem that general users lacking programming knowledge cannot conveniently generate a general mash up service.

Accordingly example embodiments of the present invention are provided to substantially obviate one or more problems due to limitations and disadvantages of the related art.

Example embodiments of the present invention provide a mash up service generation apparatus that generates a mash up service using a voice command thus enabling a general user to generate a desired customized mash up service.

Example embodiments of the present invention also provide a mash up service generation method that generates a mash up service using a voice recognition function of smart equipment to generate a mash up service thus enabling a general user to easily generate the mash up service.

In some example embodiments a mash up service generation apparatus includes a voice recognizer configured to convert a voice command into a character string a mash up natural language processor configured to extract a word corresponding to a mash up module based on the character string and convert the word into at least one of metadata of the mash up module and metadata of a mash up sequence in which a plurality of mash up modules are combined and a mash up sequence processor configured to search for and select a target mash up sequence corresponding to the metadata of the mash up sequence and newly generate the target mash up sequence.

When the target mash up sequence already exists the mash up sequence processor may search for and select the target mash up sequence and when there is no target mash up sequence the mash up sequence processor may request a target mash up module corresponding to the metadata of the mash up module and generate the target mash up sequence using the target mash up module.

The mash up service generation apparatus may further include a mash up module manager configured to search for the target mash up module to compare input and output parameters of the target mash up module.

The mash up module manager may search a web to find a new target mash up module corresponding to the metadata of the mash up module and register the new target mash up module.

The mash up service generation apparatus may further include a runtime manager configured to call or generate a runtime code corresponding to the target mash up sequence.

When the target mash up sequence is selected and searched the runtime manager may call the runtime code and when the target mash up sequence is newly generated the runtime manager may automatically generate the runtime code.

The mash up service generation apparatus may further include a mash up display configured to display the mash up service on a web browser.

The mash up service generation apparatus may further include a mash up sequence database DB configured to store the target mash up sequence and a block DB configured to store the target mash up module.

The mash up service generation apparatus may further include a runtime DB configured to store the runtime code.

In other example embodiments a mash up service generation method which generates a mash up service in a mash up service generation apparatus includes converting a voice command into a character string extracting a word corresponding to a mash up module based on the character string converting the word into at least one of metadata of the mash up module and metadata of a mash up sequence in which a plurality of mash up modules are combined to issue a character instruction and requesting a target mash up sequence corresponding to the metadata of the mash up sequence in response to the character instruction.

The requesting of a target mash up sequence may include when the target mash up sequence corresponding to the metadata of the mash up sequence already exists searching for and selecting the target mash up sequence and when there is no target mash up sequence newly generating the target mash up sequence corresponding to the metadata of the mash up sequence.

The newly generating of the target mash up sequence may include requesting a target mash up module corresponding to the metadata of the mash up module and searching for the target mash up module to compare input and output parameters of the target mash up module.

The newly generating of the target mash up sequence may include combining a plurality of the target mash up modules.

The newly generating of the target mash up sequence may include searching a web to find a new target mash up module corresponding to the metadata of the mash up module to newly register the new target mash up module.

The mash up service generation method may further include calling or generating a runtime code corresponding to the target mash up sequence to provide the runtime code.

The providing of the runtime code may include when the target mash up sequence is searched and selected calling the runtime code and when the target mash up sequence is newly generated automatically generating the runtime code.

The providing of the runtime code may include driving the runtime code to generate a mash up service.

The mash up service generation method may further include displaying the mash up service on a web browser.

Since the present invention may have diverse modified embodiments preferred embodiments are illustrated in the drawings and are described in the detailed description of the invention. However it should be understood that the particular embodiments are not intended to limit the present disclosure to specific forms but rather the present disclosure is meant to cover all modification similarities and alternatives which are included in the spirit and scope of the present disclosure. Like numbers refer to like elements throughout the description of the figures 

Relational terms such as first second A B and the like may be used for describing various elements but the elements should not be limited by the terms. These terms are only used to distinguish one element from another. For example a first element could be termed a second element and similarly a second element could be termed a first element without departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled to another element there are no intervening elements present.

In the following description the technical terms are used only for explaining a specific exemplary embodiment while not limiting the present disclosure. The terms of a singular form may include plural forms unless referred to the contrary. The meaning of comprise include or have specifies the presence of stated features integers steps operations elements components and or groups thereof but does not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

Unless terms used in the present disclosure are defined differently the terms may be construed as meaning known to those skilled in the art. Terms such as terms that are generally used and have been in dictionaries should be construed as having meanings matched with contextual meanings in the art. In this description unless defined clearly terms are not ideally or excessively construed as formal meanings.

Hereinafter embodiments of the present invention will be described below in more detail with reference to the accompanying drawings.

Referring to first the mash up service generation apparatus according to an embodiment of the present invention includes a voice recognizer a mash up natural language processor a mash up sequence processor a mash up module manager a runtime manager and a mash up display .

Moreover the mash up service generation apparatus may include a mash up sequence database DB a block DB and a runtime DB .

Here the voice recognizer receives a voice command from a user and converts the voice command into a digital character string recognizable by the mash up service generation apparatus .

Moreover the voice recognizer provides the digital character string to the mash up natural language processor .

Specifically for example when a voice command of Display weather and traffic information around Everland. is input from a user the voice recognizer converts the voice command into a digital character string corresponding to the voice command and supplies the digital character string to the mash up natural language processor .

The mash up natural language processor receives the digital character string corresponding to the voice command analyzes the digital character string as a morpheme and extracts a word corresponding to a mash up module.

Moreover the mash up natural language processor converts the extracted word into at least one of metadata of the mash up module and metadata of a mash up sequence.

Moreover the mash up natural language processor transfers the metadata of the mash up module and the metadata of the mash up sequence which correspond to the extracted word to the mash up sequence processor .

The mash up module for example is called a block and denotes that each of various contents and services provided by a web service provider is configured with a program module in a web . For example a map service of Google a real estate information service of Craigslist that is a real estate information site a photograph service of Flickr a video service of YouTube and a weather service of Yahoo are each configured with a program module and thus may become a mash up module a block . That is the mash up module denotes a module that performs a general function or a unit function provided as an open API.

The metadata denotes secondary information that is obtained by arranging an information type so as to intellectually control and structurally access information. That is an information type of a characteristic expressing the mash up module is metadata and the metadata may be defined as data of data in the sense of data defining a type of data.

The mash up sequence for example denotes a service in which a plurality of mash up modules are combined and provided to a user. Specifically for example the mash up sequence may be a service that when the map service of Google and the weather service of Yahoo are combined and a specific area is clicked informs weather information of the clicked area.

In this case the metadata of the mash up module and the metadata of the mash up sequence are for example information used for various information searches of the mash up module and the mash up sequence and include input output information i.e. a data format of the mash up module and the mash up sequence. As the data format for example there is XML JSON or PHP.

Moreover the metadata of the mash up module and the metadata of the mash up sequence may further include for example information on a communication protocol or hyper text markup language HTML shown in a web page.

Here the communication protocol is for transmitting and receiving data to and from an open API service provider and for example there is JAVA script REST or SOAP. That is the communication protocol denotes a code for performing a unit function.

As described above the mash up natural language processor analyzes the digital character string as a morpheme to extract a word corresponding to a mash up module.

Specifically for example the mash up natural language processor analyzes POS tag information of an input character string to separate words in the form of pseudo morphemes and analyzes a POS tag of each of the words.

Here the pseudo morpheme denotes a new decoding unit of a separation reference suitable for a voice recognition operation while maintaining a characteristic of a morpheme that is a linguistic unit.

The POS tag denotes an operation principle of a morpheme analyzer for a morpheme of a character string. The morpheme analyzer divides each of words composing a sentence into morphemes and each of the divided morphemes is changed to a type in which its own spelling is connected to a tag of a part of speech corresponding thereto. Here each of morphemes in which tag information is combined may be treated as one word.

A more detailed example will be described using a digital character string corresponding to Display weather and traffic information around Everland. that is a voice command.

In this case the mash up natural language processor extracts the digital character string as words for example Everland around corresponding to a mash up module indicating a position weather traffic information and map display corresponding to the mash up module.

Moreover the mash up natural language processor converts the extracted words into metadata of a mash up module and metadata of a mash up sequence and supplies the metadata to the mash up sequence processor .

The mash up sequence processor receives the metadata searches for and selects or newly generates a mash up sequence corresponding to the metadata and supplies the mash up sequence to the runtime manager .

To this end the mash up sequence processor may include a mash up sequence selector a mash up sequence generator and a mash up sequence searcher .

First the mash up sequence searcher searches the mash up sequence DB to find a mash up sequence corresponding to metadata. Here the searched result indicates for example information on whether the mash up sequence corresponding to the metadata is stored in the mash up sequence DB .

Moreover for example the mash up sequence searcher may supply the searched result indicating whether there is the mash up sequence corresponding to the metadata to the mash up sequence selector and the mash up sequence generator .

At this time when the mash up sequence corresponding to the metadata is stored in the mash up sequence DB the mash up sequence selector selects the mash up sequence corresponding to the metadata and supplies the selected mash up sequence to the runtime manager .

On the other hand when the mash up sequence corresponding to the metadata is not stored in the mash up sequence DB the mash up sequence generator receives a mash up module capable of configuring the mash up sequence corresponding to the metadata and generates a new mash up sequence based on the mash up module. At this time the mash up sequence processor may store the newly generated mash up sequence in the mash up sequence DB .

Moreover the mash up sequence generator supplies the newly generated mash up sequence to the runtime manager .

At this time the mash up sequence generator may receive the mash up module configuring the mash up sequence corresponding to the metadata from the mash up module manager .

The mash up module manager searches for a mash up module corresponding to an extracted word and compares input and output parameters of the searched mash up module to supply a connectable mash up module to the mash up sequence processor . In other words the mash up module manager searches for a mesh up module using metadata of the mesh up module.

To this end the mash up module manager may include a mash up module register a mash up module searcher and a mash up module input output comparator .

Specifically for example when a mash up module capable of configuring a mash up sequence is not stored in the block DB the mash up module register may search for a corresponding mash up module in the web and newly store the searched mash up module in the block DB .

The mash up module searcher searches the block DB to find a mash up module capable of configuring the mash up sequence corresponding to the metadata and transfers the found mash up module to the block DB .

The mash up module input output comparator compares input and output parameters of the transferred mash up module to determine whether the mash up module is connectable.

The mash up module input output comparator supplies a connectable mash up module to the mash up sequence processor .

Here the mash up module has its own input and output parameters. Specifically for example the mash up module may have n n 1 number of input parameters and m m 1 number of output parameters. Also each of the n input parameters has a data type. Likewise each of the m output parameters has a data type.

A mash up module A will be described as an example. The mash up module A may have the following four input parameters.

That is the mash up module A has the four input parameters and respective data types of the four input parameters are string float float and dateType.

In this case for example the mash up module input output comparator respectively compares the numbers of input and output parameters of combined mash up modules meanings of titles and data types of blocks and informs a combinability between the mash up modules.

The runtime manager searches the runtime DB to find and execute a runtime code a execution code corresponding to the transferred mash up sequence or newly generates and executes the runtime code corresponding to the mash up sequence.

To this end the runtime manager may include a runtime selector a runtime driver and a runtime generator .

Here the runtime selector searches the runtime DB to find a runtime code corresponding to a mash up sequence.

At this time when there is the runtime code corresponding to the mash up sequence the runtime selector supplies the runtime code to the runtime driver .

On the other hand when there is no runtime code corresponding to the mash up sequence the runtime selector supplies runtime generation information which is information indicating that a runtime code should be newly generated because there is no runtime code to the runtime generator .

The runtime generator receives the runtime generation information automatically generates the runtime code corresponding to the mash up sequence and supplies the runtime code to the runtime driver .

The runtime driver executes the supplied runtime code and supplies the executed result to the mash up display . Here the executed result may be for example a mash up service.

The mash up display displays the executed mash up service on a web browser thereby enabling a user to use the mash up service.

The mash up sequence DB stores various mash up sequences and supplies a mash up sequence requested by the mash up sequence processor to the mash up sequence processor .

The block DB stores various mash up modules and supplies a mash up module requested by the mash up module manager to the mash up module manager .

The runtime DB stores various runtime codes and supplies a runtime code requested by the runtime manager to the runtime manager .

Hereinafter a mash up service generation method according to an embodiment of the present invention will be described with reference to .

First the mash up service generation apparatus generates a digital character string corresponding to a voice command input from a user to recognize a voice in operation S.

The mash up service generation apparatus analyzes the digital character string as morphemes to extract a word corresponding to a mash up module and performs a mash up natural language processing that generates metadata of the mash up module and a mash up sequence which correspond to the digital character string in operation S.

The mash up service generation apparatus determines whether there is a mash up sequence corresponding to the metadata of the mash up sequence in operation S.

At this time when there is no mash up sequence corresponding to the metadata of the mash up sequence the mash up service generation apparatus determines whether there is a mash up module capable of configuring the mash up sequence based on the metadata of the mash up module in operation S. Here when there is no mash up module capable of configuring the mash up sequence the mash up service generation apparatus registers a new mash up module in operation S.

When there is the existing mash up module or there is the mash up module capable of configuring the mash up sequence by newly registering the mash up module the mash up service generation apparatus compares input and output parameters of mash up modules in operation S.

Subsequently when the mash up modules are combinable therebetween as the compared result of the mash up modules the mash up service generation apparatus combines the mash up modules to generate a mash up sequence in operation S.

When there is the mash up sequence corresponding to the metadata of the mash up sequence or the mash up sequence is newly generated the mash up service generation apparatus determines whether there is a runtime code corresponding to the mash up sequence in operation S.

At this time when there is the runtime code corresponding to the mash up sequence the mash up service generation apparatus calls the runtime code in operation S. On the other hand when there is no runtime code corresponding to the mash up sequence the mash up service generation apparatus automatically generates the runtime code corresponding to the mash up sequence in operation S.

The mash up service generation apparatus drives the called or generated runtime code in operation S. The mash up service generation apparatus displays a mash up service generated by driving the runtime code on a screen in operation S and thus the mash up service generation method according to an embodiment of the present invention is completed.

Hereinafter a driving method of the mash up service generation apparatus according to an embodiment of the present invention will be described in more detail with reference to .

First the voice recognizer receives a voice instruction namely a voice command from a user in operation S.

The voice recognizer converts the voice instruction into a digital character string recognizable by the mash up service generation apparatus and supplies a character instruction to the mash up natural language processor in operation S.

The mash up natural language processor analyzes the character instruction extracts a word corresponding to a mash up module converts the extracted word into metadata corresponding to the mash up module and a mash up sequence and requests the mash up sequence from the mash up sequence processor in operation S.

The mash up sequence processor searches for a mash up sequence based on the metadata of the mash up sequence in operation S and requests a driving of a runtime code corresponding to the searched mash up sequence from the runtime manager in operation S. Here it may be assumed that the runtime code corresponding to the mash up sequence is stored in for example the runtime DB in . This is because the existing mash up sequence is used and thus a runtime code corresponding thereto can be generated together and stored in advance. In this case the mash up sequence processor may directly request a driving of the runtime code corresponding to the mash up sequence from the runtime manager . Also the runtime manager may search for the runtime code corresponding to the mash up sequence and thus immediately drive the runtime code.

As an example it is assumed that there is the existing runtime code corresponding to the mash up sequence but when there is no runtime code a runtime code corresponding to the mash up sequence may be newly generated.

The runtime manager drives the runtime code corresponding to the mash up sequence in operation S and requests a display of the driven result value on a screen from the mash up display in operation S.

The mash up display displays a result screen for example on a web browser to supply the driven result to the user in operation S.

Hereinafter a method in which the mash up service generation apparatus generates a mash up service will be described in more detail with reference to .

First the voice recognizer receives a voice instruction namely a voice command from a user in operation S.

The voice recognizer converts the voice instruction into a digital character string recognizable by the mash up service generation apparatus and supplies a character instruction to the mash up natural language processor in operation S.

The mash up natural language processor analyzes the character instruction extracts a word corresponding to a mash up module converts the extracted word into metadata corresponding to the mash up module and a mash up sequence and requests the mash up sequence from the mash up sequence processor in operation S.

The mash up sequence processor searches for a mash up sequence based on the metadata of the mash up sequence in operation S. At this time when there is no mash up sequence corresponding to the metadata of the mash up sequence the mash up sequence processor requests a search of a mash up module corresponding to the metadata of the mash up module from the mash up module manager in operation S. The mash up module manager searches for the mash up module in operation S and supplies a response to the search of the mash up module to the mash up sequence processor in operation S.

The mash up sequence processor requests a comparison of inputs and outputs of mash up modules from the mash up module manager in operation S and the mash up module manager compares the inputs and outputs of the mash up modules in operation S. Also the mash up module manager supplies a response to the comparison of the inputs and outputs of the mash up modules to the mash up sequence processor in operation S.

The mash up sequence processor connects or combines the supplied mash up modules to generate a mash up sequence in operation S. Although not shown when there is the mash up sequence corresponding to the metadata of the mash up sequence the mash up sequence processor may immediately use the searched mash up sequence.

The mash up sequence processor requests generation of a runtime code corresponding to the generated mash up sequence from the runtime manager in operation S and the runtime manager generates the runtime code corresponding to the mash up sequence in operation S. Here since the mash up sequence is generated using a new mash up module for example a runtime code corresponding to a new mash up sequence may not be stored in the runtime DB in . Therefore the runtime manager automatically generates the runtime code corresponding to the new mash up sequence in operation S and supplies a runtime code generation response to the mash up sequence processor in operation S.

As an example it is assumed that the runtime code corresponding to the newly generated mash up sequence is not previously stored but when the runtime code corresponding to the newly generated mash up sequence is previously stored the runtime code may be used.

The mash up sequence processor receiving the runtime code generation response requests a driving of the runtime code from the runtime manager in operation S. Therefore the runtime manager drives the runtime code in operation S and by supplying the driven result value of the runtime code to the mash up display the runtime manager requests a display of the result value on a screen from the mash up display in operation S.

The mash up display displays the result value on the screen such as a web browser or the like in operation S thereby providing the mash up service to the user.

As described above the mash up service generation apparatus and method according the embodiments of the present invention generates the mash up service using a voice recognition function of smart equipment or the like.

Therefore a general user breaks from the existing scheme in which a developer directly programs a mash up service and unilaterally provides the mash up service and can directly generate a customized and personalized mash up service using a voice command. Also the general user can easily generate the mash up service using the voice command.

In of the present invention for the convenience of description the blocks having different configurations have been described above but each of the elements may be configured as one block. For example each of the blocks may be provided in a controller or a processor and may perform the above described series of operations.

The mash up service generation apparatus according to the embodiments of the present invention generates the mash up service using a voice command thus enabling a general user to generate a desired customized mash up service.

The mash up service generation method according to the embodiments of the present invention generates the mash up service using the voice recognition function of smart equipment to generate the mash up service thus enabling a general user to easily generate the mash up service.

While the example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

