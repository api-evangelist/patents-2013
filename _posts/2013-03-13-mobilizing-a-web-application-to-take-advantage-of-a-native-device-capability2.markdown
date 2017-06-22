---

title: Mobilizing a web application to take advantage of a native device capability
abstract: Mechanisms are provided to mobilize a web application (e.g., a webpage) to take advantage of a native device capability (e.g., a native device capability of a mobile device). In one example, existing program code in a webpage that performs a first action that uses functionality of desktop software is identified and replaced with replacement program code that performs a second action that uses native device capability of a mobile device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09563448&OS=09563448&RS=09563448
owner: International Business Machines Corporation
number: 09563448
owner_city: Armonk
owner_country: US
publication_date: 20130313
---
The present application is related to commonly owned co pending U.S. patent application Ser. No. 13 801 924 entitled TRANSFORMING APPLICATION CACHED TEMPLATE USING PERSONALIZED CONTENT filed on Mar. 13 2013 U.S. patent application Ser. No. 13 801 820 entitled MOBILE ENABLEMENT OF WEB PAGES filed on Mar. 13 2013 U.S. patent application Ser. No. 13 801 830 entitled MOBILE ENABLEMENT OF EXISTING WEB SITES filed on Mar. 13 2013 and U.S. patent application Ser. No. 13 801 892 entitled ENHANCED MOBILIZATION OF EXISTING WEB SITES filed on Mar. 13 2013 the entire contents and disclosures of which are expressly incorporated by reference herein as if fully set forth herein.

The present disclosure relates generally to the field of mobilizing a web application e.g. a webpage to take advantage of a native device capability e.g. a native device capability of a mobile device . In one example the mobilizing may be implemented by modifying an existing web application e.g. an existing webpage .

In one example the present disclosure relates to the field of mobilizing a web application e.g. a webpage to take advantage of a native device capability.

In one specific example the mobilizing may be implemented by modifying the web application e.g. the webpage .

In another specific example the web application e.g. webpage may be an existing web application e.g. webpage .

In another specific example the native device capability may be a native device capability of a mobile device.

In one embodiment a method for modifying at least one webpage is provided the method comprising receiving the webpage identifying by a processor existing program code in the webpage that performs a first action that uses functionality of desktop software and replacing by the processor the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device.

In another embodiment a computer readable storage medium tangibly embodying a program of instructions executable by the computer for modifying at least one webpage is provided the program of instructions when executing performing the following steps receiving by the computer the webpage identifying by the computer existing program code in the webpage that performs a first action that uses functionality of desktop software and replacing by the computer the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device.

In another embodiment a computer implemented system for modifying at least one webpage is provided the system comprising an input element configured to receive the webpage an identifying element in operative communication with the input element configured to identify existing program code in the webpage that performs a first action that uses functionality of desktop software and a replacing element in operative communication with the input element and the identifying element configured to replace the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device.

In one example one or more systems may provide for automatically mobilizing a web application e.g. a webpage to take advantage of a native device capability e.g. a native device capability of a mobile device . In another example one or more methods may provide for automatically mobilizing a web application e.g. a webpage to take advantage of a native device capability e.g. a native device capability of a mobile device . In another example one or more algorithms may provide for automatically mobilizing a web application e.g. a webpage to take advantage of a native device capability e.g. a native device capability of a mobile device .

For the purposes of describing and claiming the present invention the term mobile device is intended to refer to a device that can communicate data e.g. receive transmit over a network and can be carried by a user. Examples include but are not limited to a mobile phone a cellular phone a smart phone and or a tablet.

For the purposes of describing and claiming the present invention the term hybrid application is intended to refer to an application that can be installed natively on a mobile device but that can also have web content such as HTML CSS and or JavaScript.

For the purposes of describing and claiming the present invention the term installed natively on a mobile device is intended to refer to using the standard native deployment model to distribute the application to end users. The APPLE APP STORE and GOOGLE PLAY are two examples . Another example is an enterprise app store where corporations can distribute applications to their employees. The key part is having an application physically installed on the device and running locally versus remotely loading an app via a mobile device web browser.

For the purposes of describing and claiming the present invention the term uses native device capability is intended to refer to direct or indirect access to the native operating system APIs.

For the purposes of describing and claiming the present invention the term program code is intended to refer to computer code instructions.

For the purposes of describing and claiming the present invention the term widget is intended to refer to stand alone piece of program code that is readily insertable into a larger application.

For the purposes of describing and claiming the present invention the term desktop software is intended to refer to a software application configured to run on a non mobile device.

For the purposes of describing and claiming the present invention the term web application is intended to refer to a computer application run over the world wide web using a browser as an interface.

For the purposes of describing and claiming the present invention the term webpage is intended to refer to the content shown in a user interface screen displayed by a web browser.

Referring now to an example implementation according to one embodiment is shown. For the purposes of this example form of represents a product rating form or widget that is part of a webpage of a conventional e commerce website other examples may be applied to social networking e.g. social networking websites and or websites such as CRAIGSLIST where images are very often uploaded .

Still referring to in the original desktop browser based application clicking on the button marked Add images or videos would result in the user being presented with a modal dialog containing a set of form fields with one of the form fields being a file upload form field.

In this example implementation instead of having the link direct the user to the modal dialog the mobilized web application interacts with a mobile device camera application. By leveraging the camera directly the user can skip the monotonous task of having to first get the image or video file via a separate application store the file and then in turn upload the file to the website server. That is by providing this simplified user experience the user can now have the camera support enabled as part of the mobilized web application.

In one example selection step and or determination step may be made automatically by the computer tool. In one specific example such automation may utilize context awareness. For example if text is found that suggests to upload an image and such text can be associated with something like a feedback ratings type of widget it can be assumed this could be converted to a widget that invokes the native camera API.

Referring now to a method implemented in a computer system for modifying at least one webpage is shown. As seen in this the method of this embodiment comprises at receiving the webpage at identifying by a processor existing program code in the webpage that performs a first action that uses functionality of desktop software at replacing by the processor the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device and at saving the webpage after replacing the existing program code with the replacement program code.

In another example any steps may be carried out in the order recited or the steps may be carried out in another order.

Referring now to in another embodiment a system for modifying at least one webpage is provided. This system may include the following elements an input element configured to receive the webpage an identifying element in operative communication with the input element configured to identify existing program code in the webpage that performs a first action that uses functionality of desktop software a replacing element in operative communication with the input element and the identifying element configured to replace the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device and a saving generating element in operative communication with the input element the identifying element and the replacing element configured to a save the webpage as a modified webpage after the existing program code is replaced with the replacement program code wherein the modified webpage performs the second action that uses native device capability of a mobile device and or b generate and save a hybrid application after the existing program code is replaced with the replacement program code wherein the generated hybrid application performs the second action that uses native device capability of a mobile device .

Further the saved modified webpage and or the saved generated hybrid application may then be installed on a mobile device using any appropriate mechanism e.g. downloading via a network .

In one example communication between and among the various components of may be bi directional. In another example the communication may be carried out via the Internet an intranet a local area network a wide area network and or any other desired communication channel s . In another example each of the components may be operatively connected to each of the other components. In another example some or all of these components may be implemented in a computer system of the type shown in .

In another example a method for converting an existing web application to a mobile application taking advantage of native device capabilities comprises converting a web application to a mobile web application by parsing and separating the web application into static content and a dynamic content with data sources rendering the static content as hypertext markup language HTML pages with the links between the HTML pages converted to local links and references to dynamic content changed to Representational State Transfer REST requests utilizing a mobile gateway on a remote server for accessing the dynamic content with the data sources converting a section of a webpage for the mobile web application into a set of separate webpages views packaging the views into the mobile web application installing the mobile web application on a mobile device and converting the views to utilize one or more natively installed applications e.g. via application programming interface s or API s .

Referring now to this figure shows a hardware configuration of computing system according to an embodiment of the present invention. As seen this hardware configuration has at least one processor or central processing unit CPU . The CPUs are interconnected via a system bus to a random access memory RAM read only memory ROM input output I O adapter for connecting peripheral devices such as disk units and tape drives to the bus user interface adapter for connecting a keyboard mouse speaker microphone and or other user interface device to the bus a communications adapter for connecting the system to a data processing network the Internet an Intranet a local area network LAN etc. and a display adapter for connecting the bus to a display device and or printer e.g. a digital printer or the like .

As described herein a mechanism is provided for converting an existing browser based application into a mobile application. Such conversion may be performed by denoting a section of an existing webpage that can be pulled into a separate webpage called a view . One or more of such views may then be packaged as part of what is referred to as a hybrid application. Further one or more of such views may be configured to utilize certain native device capabilities that do not exist in a browser application mobile or desktop .

As described herein a model is provided for generating mobile views from existing desktop based browser program code. In one example the model may include determining that certain existing functionality could be replaced by other functionality that is only capable of being performed on mobile devices.

As described herein various embodiments provide for leveraging device capabilities that are available only to natively installed applications. Such leveraging of device capabilities can be used to enhance the views that are created which in essence can yield entirely new views that were not possible with the original application .

As described herein enhanced mobile views may be run as part of a native container wherein the enhanced mobile views can leverage device APIs that are native to a device and can provide a unique browsing experience. Examples of such device APIs include but are not limited to camera vibration accelerometer contact lists notifications geolocation sound playback device information click to call.

As described herein web applications e.g. existing web applications may be converted to native applications for mobile devices to leverage various native mobile device capabilities e.g. camera vibration accelerometer contact lists notifications geolocation sound playback device information click to call that are otherwise not available to a web application.

In various embodiments a mechanism such as PhoneGap may be used to implement having a mobile webpage being capable of calling device APIs.

As described herein the APIs capable of being called may include but not be limited to Accelerometer Camera Capture Compass Connection Contacts Device Events File Geolocation Globalization InAppBrowser Media Notification Splashscreen and or Storage.

As described herein various embodiments may be provided in the context of next generation web application enablement including WEB 2.0 and or Rich Internet Application RIA .

As described herein various embodiments may be provided in the context of a Cloud Delivery model Platform as a Service PaaS b Cloud Delivery model Software as a Service SaaS and or c Software Application development software. As described herein various embodiments may provide for refactoring a user interface UI to take advantage of native device APIs.

In another example the replacement program code may comprise code e.g. JavaScript that interacts with an API of the mobile device.

In another example the replacement program code may comprise code e.g. JavaScript that interacts with an API of the mobile device via software.

In another example a plurality of web applications e.g. comprising a website may be mobilized to take advantage of a native device capability.

In another example a web application may be mobilized to take advantage of a plurality of native device capabilities.

In one embodiment a method for modifying at least one webpage is provided the method comprising receiving the webpage identifying by a processor existing program code in the webpage that performs a first action that uses functionality of desktop software and replacing by the processor the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device.

In another example the replacing comprises removing the existing program code from the webpage and inserting the replacement program code into the webpage.

In another example the replacing comprises inserting the replacement program code into the webpage and rendering the existing program code inoperative on the mobile device.

In another example the file upload process comprises uploading at least one of a at least one image file b at least one video file and c at least one audio file.

In another example the mobile device comprises a camera and a microphone and wherein the second action comprises at least one of a obtaining a photo with the camera b obtaining a video with the camera and the microphone and c obtaining audio with the microphone.

In another example the method further comprises saving the webpage after replacing the existing program code with the replacement program code.

In another example the first action and the second action are related actions such that the performance of the second action eliminates a need to perform the first action.

In another embodiment a computer readable storage medium tangibly embodying a program of instructions executable by the computer for modifying at least one webpage is provided the program of instructions when executing performing the following steps receiving by the computer the webpage identifying by the computer existing program code in the webpage that performs a first action that uses functionality of desktop software and replacing by the computer the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device.

In another example the replacing comprises removing the existing program code from the webpage and inserting the replacement program code into the webpage.

In another example the replacing comprises inserting the replacement program code into the webpage and rendering the existing program code inoperative on the mobile device.

In another example the file upload process comprises uploading at least one of a at least one image file b at least one video file and c at least one audio file.

In another example the mobile device comprises a camera and a microphone and wherein the second action comprises at least one of a obtaining a photo with the camera b obtaining a video with the camera and the microphone and c obtaining audio with the microphone.

In another example the program of instructions when executing further performs the following step saving the webpage after replacing the existing program code with the replacement program code.

In another example the first action and the second action are related actions such that the performance of the second action eliminates a need to perform the first action.

In another embodiment a computer implemented system for modifying at least one webpage is provided the system comprising an input element configured to receive the webpage an identifying element in operative communication with the input element configured to identify existing program code in the webpage that performs a first action that uses functionality of desktop software and a replacing element in operative communication with the input element and the identifying element configured to replace the identified existing program code with replacement program code that performs a second action that uses native device capability of a mobile device.

In another example the replacing comprises removing the existing program code from the webpage and inserting the replacement program code into the webpage.

In another example the replacing comprises inserting the replacement program code into the webpage and rendering the existing program code inoperative on the mobile device.

In another example the file upload process comprises uploading at least one of a at least one image file b at least one video file and c at least one audio file.

In another example the mobile device comprises a camera and a microphone and wherein the second action comprises at least one of a obtaining a photo with the camera b obtaining a video with the camera and the microphone and c obtaining audio with the microphone.

In another example the system further comprises a saving element in operative communication with the input element the identifying element and the replacing element configured to save the webpage after the existing program code is replaced with the replacement program code.

In another example the first action and the second action are related actions such that the performance of the second action eliminates a need to perform the first action.

As will be appreciated by one skilled in the art aspects of the present invention may be embodied as a system method or computer program product. Accordingly aspects of the present invention may take the form of an entirely hardware embodiment an entirely software embodiment including firmware resident software micro code etc. or an embodiment combining software and hardware aspects that may all generally be referred to herein as a circuit module or system. Furthermore aspects of the present invention may take the form of a computer program product embodied in one or more computer readable medium s having computer readable program code embodied thereon.

Any combination of one or more computer readable medium s may be utilized. The computer readable medium may be a computer readable signal medium or a computer readable storage medium. A computer readable storage medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus or device or any suitable combination of the foregoing. More specific examples a non exhaustive list of the computer readable storage medium would include the following an electrical connection having one or more wires a portable computer diskette a hard disk a random access memory RAM a read only memory ROM an erasable programmable read only memory EPROM or Flash memory an optical fiber a portable compact disc read only memory CD ROM an optical storage device a magnetic storage device or any suitable combination of the foregoing. In the context of this document a computer readable storage medium may be any tangible medium that can contain or store a program for use by or in connection with an instruction execution system apparatus or device.

A computer readable signal medium may include a propagated data signal with computer readable program code embodied therein for example in baseband or as part of a carrier wave. Such a propagated signal may take any of a variety of forms including but not limited to electro magnetic optical or any suitable combination thereof. A computer readable signal medium may be any computer readable medium that is not a computer readable storage medium and that can communicate propagate or transport a program for use by or in connection with an instruction execution system apparatus or device.

Program code embodied on a computer readable medium may be transmitted using any appropriate medium including but not limited to wireless wireline optical fiber cable RF etc. or any suitable combination of the foregoing.

Computer program code for carrying out operations for aspects of the present invention may be written in any programming language or any combination of one or more programming languages including an object oriented programming language such as Java Smalltalk C or the like or a procedural programming language such as the C programming language or similar programming languages. The program code may execute entirely on the user s computer partly on the user s computer as a stand alone software package partly on the user s computer and partly on a remote computer or entirely on the remote computer or server. In the latter scenario the remote computer may be connected to the user s computer through any type of network including a local area network LAN or a wide area network WAN or the connection may be made to an external computer for example through the Internet using an Internet Service Provider .

Aspects of the present invention may be described herein with reference to flowchart illustrations and or block diagrams of methods systems and or computer program products according to embodiments of the invention. It will be understood that each block of the flowchart illustrations and or block diagrams and combinations of blocks in the flowchart illustrations and or block diagrams can be implemented by computer program instructions. These computer program instructions may be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

These computer program instructions may also be stored in a computer readable medium that can direct a computer other programmable data processing apparatus or other devices to function in a particular manner such that the instructions stored in the computer readable medium produce an article of manufacture including instructions which implement the function act specified in the flowchart and or block diagram block or blocks.

The computer program instructions may also be loaded onto a computer other programmable data processing apparatus or other devices to cause a series of operational steps to be performed on the computer other programmable apparatus or other devices to produce a computer implemented process such that the instructions which execute on the computer or other programmable apparatus or other devices provide processes for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

The flowcharts and block diagrams in the figures illustrate the architecture functionality and operation of possible implementations of systems methods and computer program products according to various embodiments of the present invention. In this regard each block in the flowcharts or block diagrams may represent a module segment or portion of code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some implementations the functions noted in the block may occur out of the order noted in the figures. For example two blocks shown in succession may in fact be executed substantially concurrently or the blocks may sometimes be executed in the reverse order depending upon the functionality involved. It will also be noted that each block of the block diagrams and or flowchart illustrations and combinations of blocks in the block diagrams and or flowchart illustrations can be implemented by special purpose hardware based systems that perform the specified functions or acts or combinations of special purpose hardware and computer instructions.

It is noted that the foregoing has outlined some of the objects and embodiments of the present invention. This invention may be used for many applications. Thus although the description is made for particular arrangements and methods the intent and concept of the invention is suitable and applicable to other arrangements and applications. It will be clear to those skilled in the art that modifications to the disclosed embodiments can be effected without departing from the spirit and scope of the invention. The described embodiments ought to be construed to be merely illustrative of some of the features and applications of the invention. Other beneficial results can be realized by applying the disclosed invention in a different manner or modifying the invention in ways known to those familiar with the art. In addition all of the examples disclosed herein are intended to be illustrative and not restrictive.

