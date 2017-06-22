---

title: Information storing device, information storing system and method
abstract: An information storing device includes a storage device in which one or more storage areas are generated for storing electronic data therein, wherein in the storage device at least one of first and second processes is set on a storage area basis; a storing part configured to, when the information storing device has received electronic data and a designation of the storage area from one of a plurality of electronic apparatuses, store the received electronic data in the storage area designated by the received designation; and an executing part configured to, when the received electronic data is stored by the storing part, perform the first process on the stored electronic data if the first process is set in the storage area in which said electronic data is stored, and perform the second process using the stored electronic data if the second process is set in the storage area in which said electronic data is stored.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09563639&OS=09563639&RS=09563639
owner: Ricoh Company, Ltd.
number: 09563639
owner_city: Tokyo
owner_country: JP
publication_date: 20130703
---
This disclosure is related to an information storing device an information storing system and a method.

For example Japanese laid open patent publication No. 2008 191711 discloses a printing system utilizing a personal computer wherein when data is input into a particular folder as a hot folder a print process set in advance for the folder is performed for the input data.

In recent years users are utilizing various electronic apparatuses for outputting electronic data such as a printer a Multi Function Peripheral and a projector and various information processing devices such as a mobile phone a smart phone and a tablet terminal. In a system where the electronic apparatus and the information processing device are utilized in cooperation value is expected to be improved by utilizing these electronic apparatus and information processing devices in cooperation.

However according to a prior art system utilizing the electronic apparatuses and the information processing devices the respective information processing devices that utilize a folder a process defined folder with which a predefined processing is performed for the input data need to have functions of storing the data in the folder. Further functions of displaying the folder and storing the data in the folder need to be adapted to the apparatus that has the process defined folder.

In this way according to the prior art system utilizing the electronic apparatuses and the information processing devices it is difficult to coordinate the electronic apparatuses and the information processing devices with the apparatus that has the process defined folder in utilizing the process defined folder.

An object of this disclosure is to provide an information storing device an information storing system and a method that can execute processing utilizing a process defined folder in conjunction with each other.

According to one aspect of this disclosure an information storing device is provided which includes a storage device in which one or more storage areas are generated for storing electronic data therein wherein in the storage device at least one of first and second processes can be set on a storage area basis the first process is to be performed on the electronic data stored in the storage area and the second process is to be performed using the electronic data stored in the storage area a storing part configured to when the information storing device has received electronic data and a designation of the storage area among the storage areas of the storage device from one of a plurality of electronic apparatuses store the received electronic data in the storage area designated by the received designation and an executing part configured to when the received electronic data is stored by the storing part perform the first process on the stored electronic data if the first process is set in the storage area in which said electronic data is stored and perform the second process using the stored electronic data if the second process is set in the storage area in which said electronic data is stored.

The network N is an intranet internet or the like that utilizes wired LAN Local Area Network wireless LAN or the like and enables communications between different devices. The smart phone and the tablet terminal are examples of an information processing device that is carried and operated by a user. The information processing device may be a device that the user can operate.

The smart phone and the tablet terminal each have a wireless communication function for example and functions of displaying storing transmitting and receiving various files. Further the smart phone and the tablet terminal each have a camera device incorporated therein and is capable of taking a picture etc.

The PC is a desktop PC or a portable PC for example. The PC is capable of performing various types of file manipulation such as generating new files updating files deleting files and renaming files for a folder of the information storing device by utilizing SMB Server Message Block protocol of the network N. It is noted that the folder is often referred to as a directory and is an example of a storage location in which data or files are stored. The PC is an example of a information processing device.

The digital camera has a wireless communication function for example and is capable of storing a captured image file in the folder of the information storing device . Further the digital camera is capable of displaying the image file stored in the folder of the information storing device .

The MFP the network printer and the network projector are examples of an electronic apparatus for outputting electronic data. The MFP is an example of an image forming device. The MFP is an image forming device that has multi functions including a copy function a facsimile FAX function a print function a scanner function a function of distributing input images etc. The input image includes a document image read by the scanner function and images input by the print function and the facsimile functions. The MFP is capable of designating and printing the file stored in the information storing device . Further the MFP is capable of storing the document image read by the scanner function in the information storing device . The MFP has a browser installed therein and the scanner function or the print function can be utilized from a Web application operated on the browser.

The network printer is an example of an image forming device that has the print function. The network printer has functions including a function of printing the file stored in the information storing device via the network N etc.

The network projector is an example of an image projecting device that has a projector function. The network projector is capable of accessing the information storing device via the network N. The network projector has functions including a function of projecting and displaying the file stored in the information storing device etc.

It is noted that devices other than the smart phone the tablet terminal the PC the digital camera the MFP the network printer and the network projector may be used in the present embodiment as long as the devices are capable of connecting to the network N and handling a general purpose image file format.

The information storing device is an example of a cooperative processing device. The information storing device has a function as a server that is capable of acquiring and storing files from other devices such as the smart phone and the MFP . Further the information storing device has a function of performing processing such as a predefined format conversion of the file transmission of an e mail etc. when the file is stored in a process defined folder. It is noted that the process defined folder is referred to as a workflow folder hereinafter.

Further the information storing device is capable of communicating the respective devices via the network N. The information storing device is capable of causing the electronic devices such as MFP to output electronic data in cooperation with the information processing device such as the smart phone . It is noted that the information storing device may be formed by a plurality of computers in a decentralized manner.

The information storing device is formed by a computer system having a hardware configuration illustrated in for example. It is noted that the information processing devices such as the smart phone the tablet terminal and the PC each include such a hardware configuration as illustrated in . is a diagram for illustrating an example of a hardware configuration of a computer system according to the embodiment.

In the example illustrated in the computer system includes an input device a display device an external I F a RAM a ROM a CPU a communication I F a HDD etc. that are interconnected via a bus B. The input device includes a keyboard a mouse or the like and is used to input operation signals to the computer system .

The display device includes a display etc. and displays a processing result of the computer system . The communication I F connects the computer system to the network N. With this the computer system can perform data communication with other devices and apparatuses via the communication I F .

The HDD is a nonvolatile storage that stores programs and data. The stored programs and data include an OS Operating System that is a basic software item for controlling the computer system as a whole and application software items for providing various functions on the OS. Further the HDD manages the stored programs and data with a predetermined file system and or DB Data Base .

The external I F is an interface with external devices. The external devices include a recording medium or the like. Thus the computer system can perform writing and or reading of the recording medium via the external I F . It is noted that the recording medium includes a flexible disk a CD a DVD Digital Versatile Disk a SD memory card a USB memory Universal Serial Bus memory etc.

The ROM is a nonvolatile semiconductor memory storage that can hold programs and data even if power is turned off. The ROM stores programs and data such as a BIOS Basic Input Output System that is executed at the time of starting up the computer system an OS setting and a network setting. The RAM is a volatile semiconductor memory storage that can temporarily hold the programs and data.

The CPU is a calculating device that reads the programs and data from the storage such as the ROM and the HDD and writes them in the RAM to implement total control or a function of the computer system .

The computer system according to the embodiment can implement the respective functions described hereinafter with the hardware configuration described above.

The information storing device according to the embodiment is implemented by a process block illustrated in for example. is a diagram for illustrating an example of a process block of the information storing device according to the embodiment. The information storing device executes programs to implement a WebAPI a SMB connecting part a WebUI a Web controlling part a folder monitoring part a job managing part a file converting part an e mail transmitting part a file transmitting part a setting managing part a folder and a DB .

The information storing device is connected to devices such as the smart phone the tablet terminal the PC the digital camera the MFP the network printer and the network projector via the network N as illustrated in . In the smart phone the PC and the MFP are illustrated as an example.

The WebAPI Application Programming Interface enables reception of folder list acquiring demands from the smart phone and the MFP as well as file transmission file uploading . The WebAPI is available via the network N. The WebAPI accepts an HTTP request and performs an HTTP response.

The WebAPI is a predefined interface provided for receiving the request demand from the smart phone and the MFP and includes functions classes or the like for example.

Further the WebAPI of the information storing device can be provided as a SDK Software Development Kit to developers of applications that are installed in the smart phone etc. The developers of applications can develop the applications using the SDK. The SDK can be provided to a third party vender other than a provider of the information storing device . The third vender can develop the applications using the provided SDK. The applications developed using the SDK can be installed in the information processing device such as the smart phone .

By providing the WebAPI of the information storing device as a SDK not only the applications developed by the provider of the information storing device but also the applications developed by the third vender can be installed in the information processing device such as the smart phone .

The SMB connecting part enables folder browsing from the PC via the network N. The SMB connecting part places the folder in the public domain on the network N with a SMB protocol. The user can use the PC to access the folder that is placed in the public domain on the network N.

The WebUI displays a setting screen for changing a workflow setting a file conversion format an e mail transmission destination etc. and an apparatus setting. The user can display WebUI from the Web browser of the PC for example. The user can change the workflow setting and the apparatus setting via the setting screen using the Web browser. The Web controlling part performs processing in response to the request HTTP request accepted via the WebAPI .

The folder monitoring part monitors various types of file manipulation such as generating new files to be stored in the folder updating the files deleting the files and renaming the files. The job managing part manages execution order of works tasks or jobs set in the workflow. The file converting part the e mail transmitting part and the file transmitting part are examples of a module that executes respective works.

For example the file converting part performs a format conversion of a file. The e mail transmitting part performs an e mail transmission to a designated destination. The file transmitting part stores a file in a designated folder. In three works are illustrated as an example however any function can be set as a work as long as it provides users with any merit.

The setting managing part connects to the DB to update and retrieve values of the DB . The DB stores values of the workflow setting and the apparatus setting set by the user. The folder stores a file. The file stored in the folder includes an image file an application file a document file etc. It is noted that the file stored in the folder is an embodiment of data.

The information storing device illustrated in includes the WebAPI and the SMB connecting part as interfaces with respect to the folder . Thus even the information processing device such as the smart phone which cannot utilize the SMB protocol can access the folder by utilizing the WebAPI .

Because the information processing device such as the smart phone can perform the folder list acquiring demand and the file transmission file uploading with respect to the folder by utilizing the WebAPI the information processing device can utilize a workflow folder .

In the following processing of the cooperative processing system according to the embodiment is described in detail.

The contents of the workflow setting include a workflow name a file conversion format necessary at the time of the format conversion of the file stored in the workflow folder a file destination to which the file is to be transmitted an e mail transmission destination etc. It is noted that the file conversion format includes a PDF a text attached PDF JPEG etc.

In step S the setting managing part stores in the DB the values of the workflow setting that has been set by the user using the WebUI . If the values of the workflow setting are stored successfully in the DB the setting managing part generates a folder workflow folder with a workflow name set by the user and places the generated workflow folder in the public domain as a shared folder.

In step S the folder monitoring part starts to monitor the workflow folder . At that time the file manipulation with respect to the workflow folder to be monitored is the generation of a new file. When the processes in steps S through S are completed setting the workflow is completed. After the completion of the workflow setting the user can actually perform the workflow.

In step S the folder monitoring part determines whether the file is stored in the workflow folder . If the file is not stored in the workflow folder the folder monitoring part returns to step S and thus the folder monitoring part continues monitoring.

If the folder monitoring part detects that the file is stored in the workflow folder the folder monitoring part goes to step S and waits for a predetermined time. The folder monitoring part executes the workflow described hereinafter after a lapse of the predetermined time.

It is noted that the reason why the folder monitoring part waits for the predetermined time is because if the execution of the workflow is started immediately after the user stores the file in the workflow folder the user cannot make a cancellation in the case where the user erroneously stores the file in the workflow folder . By waiting the predetermined time the user can make a cancellation within the predetermined time by deleting the file in the workflow folder in the case where the user has erroneously stored the file in the workflow folder .

In step S such a workflow list screen as illustrated in is displayed in the Web browser on the PC etc. is an image diagram for illustrating an example of a workflow listing screen. The workflow list screen illustrated in includes generate new workflow button .

The user can display such a workflow setting screen illustrated in in the Web browser by pressing the generate new workflow button or edition buttons . is an image diagram for illustrating an example of a workflow setting screen.

According to the workflow setting screen illustrated in a workflow name a file conversion format necessary at the time of the format conversion of the file stored in the workflow folder an original document keeping intention whether to keep the original document a file destination to which the file is to be transmitted an e mail transmission destination etc. can be set.

In step S the setting managing part stores the values of the workflow setting set in the workflow setting screen illustrated in in the DB as illustrated in for example. is a diagram for illustrating an example of a configuration of values of the workflow setting stored in the DB .

According to the DB illustrated in the values of the workflow setting set in the workflow setting screen are stored in a workflow setting table a file destination table and an e mail transmission destination table for example. The workflow setting table includes workflow IDs users workflow names file conversion formats original document keeping intentions etc. as data items. The file destination table includes workflow IDs users destination names and file transmission destination as data items. The e mail transmission destination table includes workflow IDs users destination names and e mail transmission destination as data items.

It is noted that the workflow setting table the file destination table and the e mail transmission destination table are associated with workflow IDs respectively. For example with respect to the workflow of the workflow ID 7tge983fsv in one file destination and two e mail transmission destinations are set.

When the folder list displaying process is selected by the user the smart phone transmits the folder list acquiring demand to the information storing device with the HTTP request GET . The Web controlling part of the information storing device accepts the folder list acquiring demand via the WebAPI . The Web controlling part generates a folder list. is a diagram for explaining an example of an HTTP request that the information storing device accepts. illustrates an example of a GET that is placed in the public domain by the information storing device .

In step S the Web controlling part transmits the generated folder list to the smart phone with such a HTTP response as illustrated in . is a diagram for illustrating an example of a configuration of a response for the folder list acquiring demand. The response illustrated in has a JSON JavaScript Object Notation format however other formats may be used as long as the folder list can be displayed on the smart phone .

In step the application installed in the smart phone displays based on the response for the folder list acquiring demand illustrated in the folder and file that are placed in the public domain by the information storing device . As a result of repeating the processes of steps S through S such screens as illustrated in are displayed on the smart phone .

In step S if Upload button is pressed in the folder displaying screen illustrated in the smart phone displays a folder selecting screen illustrated in . is an image diagram for illustrating an example of a folder selecting screen.

When the user selects workflow in the folder selecting screen illustrated in the application installed in the smart phone displays such a workflow selecting screen as illustrated in .

The user makes a file uploading demand to the workflow folder selected as the upload destination folder in order to store the files stored in the smart phone in the workflow folder selected as the upload destination folder.

When the file uploading demand is made by the user in step S the smart phone transmits the file uploading demand to the information storing device with the HTTP request POST . The Web controlling part of the information storing device accepts the file uploading demand via the WebAPI . The Web controlling part stores the file in the upload destination workflow folder . is a diagram for explaining an example of an HTTP request that the information storing device accepts. illustrates an example of a POST that is placed in the public domain by the information storing device .

It is noted that the storage of the file in the workflow folder can be performed from the PC via the SMB connecting part as well as from the smart phone via the WebAPI . is a flowchart for illustrating another example of a process for storing a file in a workflow folder.

In step S the user operates the PC to select a folder list displaying process of the information storing device . The PC utilizes the SMB protocol of the network N to display the workflow folder of the information storing device .

In step S the user operates the PC to select the workflow folder which the user wants to perform. The PC utilizes the SMB protocol of the network N to store the file in the workflow folder selected by the user.

In step S the folder monitoring part obtained the values of the workflow setting from the setting managing part . The folder monitoring part determines the work to be actually performed among the obtained values of the workflow setting. Then the folder monitoring part selects a scenario definition what is to be executed and execution order suited for the work to generate a job and registers the job in the job managing part . Further in step S the job managing part starts the execution of the job according to the scenario definition of the registered job.

In step S the job managing part determines whether an image conversion is necessary in executing the job. If the job managing part determines that the image conversion is necessary the job managing part causes the file converting part to convert the file format in step S. If the job managing part determines that the image conversion is not necessary the job managing part skips the process of step S.

In step S the job managing part determines whether a file transmission is necessary in executing the job. If the file transmission is necessary the job managing part causes the file transmitting part to store the file in the designated folder in step S. If the file transmission is not necessary the job managing part skips the process of step S.

In step S the job managing part determines whether an e mail transmission is necessary in executing the job. If the e mail transmission is necessary the job managing part causes the e mail transmitting part to transmit an e mail to the designated destination in step S. If the e mail transmission is not necessary the job managing part skips the process of step S.

After the job managing part completes all the works the job managing part goes to step S in which the job managing part reports the execution result of the workflow to the folder monitoring part . It is noted that processing of the folder monitoring part when the execution result of the workflow is reported to the folder monitoring part described hereinafter.

After the meeting the user uses the tablet terminal to display the workflow. The user launches the camera application of the tablet terminal to capture the picture of the white board. The user selects as the storage destination of the picture data the workflow folder of the information storing device in which the workflow converting to PDF and transmitting e mail is set to store the picture data file in the workflow folder .

The folder monitoring part detects that the file is stored in the workflow folder and executes the workflow converting to PDF and transmitting e mail . Then the job managing part causes the file converting part to convert the file image file stored in the workflow folder into the PDF file. Further the job managing part causes the e mail transmitting part to perform the e mail transmit of the PDF file to the predefined e mail transmission destinations of the attendants of the meeting.

In this way the user can share a picture captured by the tablet terminal between the attendants of the meeting by utilizing the workflow folder of the information storing device in which the workflow converting to PDF and transmitting e mail is set. The user can share the contents of the white board between the attendants of the meeting without taking such a procedure that includes user s taking the picture with the digital camera reading the captured picture data into the PC and then creating the e mail to transmit the picture data from the PC .

Further another usage example of the workflow is such that the user uses the PC the digital camera or the MFP to execute the workflow. The user performs the processing based on the workflow setting by storing in the workflow folder the scan data obtained by using the scan function of the MFP the picture data obtained by using the picture function of the digital camera or the data stored in the PC . Further another usage example of the workflow may be such that the network projector is caused to project the result of the processing based on the workflow setting.

When the folder monitoring part is reported the execution result of the workflow the folder monitoring part performs a process illustrated in for example. is a flowchart for illustrating an example of a process of a folder monitoring part which is informed of the execution result of the work flow. is a diagram for illustrating an example of a configuration of a folder.

In step S the job managing part reports the execution result of the job to the folder monitoring part after completing the job of the workflow. Then in step S the folder monitoring part receives the execution result of the job from the job managing part .

In step S the folder monitoring part determines based on the execution result of the job whether an error occurred at the time of the execution of the workflow. If an error didn t occur at the time of the execution of the workflow the folder monitoring part goes to step S in which the folder monitoring part deletes a workflow execution file and ends the process routine.

If an error occurred at the time of the execution of the workflow the folder monitoring part goes to step S in which the folder monitoring part generates a folder which has a name combined by year month date and time of the error occurrence a name of the file with which the error occurred and a workflow name which was executed under an error folder illustrated in .

In step S the folder monitoring part generates according to the execution result of the job a file in which the content of the error is described and in step S the folder monitoring part stores the generated folder. The content of the error that is described in the file error content description file includes for example there is no transmission destination folder and it is not a convertible file format etc. Then in step S the folder monitoring part transfers the workflow execution file to the folder which is generated in step S and ends the process.

In this way the information storing device generates the error content description file and stores it in the folder . Thus it is possible to provide the information processing device such as the smart phone with the error content description file utilizing the WebAPI . The user can check the error content description file without launching the browser installed in the PC to access the WebUI or launching the mailer to receive the e mail.

Next a workflow for transmitting and receiving with the facsimile the data in the information storing device using the MFP is described. First a workflow for transmitting the data in the information storing device from the MFP with the facsimile is described.

Further the smart phone may read a QR code registered trademark or the like displayed in the MFP to obtain the information for identifying the MFP and the input may be implemented by using the obtained information. Instead of the QR code short distance wireless communication such as Bluetooth registered trademark or infrared communication may be used for obtaining the information for identifying the MFP .

Information of the destination to which the facsimile is to be transmitted is input for the item destination . A facsimile number of the destination is directly input in a box in . Further information in an address book in the smart phone for example may be referenced by pressing a selection button so that the destination may be set based on the information in the address book. Further the address book may be stored in the information storing device . In this case the smart phone may obtain the address book so that the user can select the destination.

Information on whether a cover sheet is attached at the time of the facsimile transmission is set for the item presence or absence of cover sheet . Selecting OK after setting all the items causes to generate a facsimile transmission workflow folder.

The information storing device monitors the folder as described in a flowchart in after the facsimile transmission workflow folder is generated.

The folder monitoring part monitors whether the file is stored in the facsimile transmission workflow folder step S . The folder monitoring part repeats the process of step S until the folder monitoring part detects that the file is stored in the facsimile transmission workflow folder. When the folder monitoring part detects the storage of the file the file converting part converts the stored file into image data for the facsimile transmission image data in a TIF format for example step S .

It is noted that the file to be stored in the facsimile transmission workflow folder is not limited to the file in the information storing device and may be a file that is stored from the external device such as the tablet terminal as is the case with .

The file converting part determines whether the cover sheet is necessary step S . If cover sheet attached is selected in the workflow setting screen the file converting part determines that the cover sheet is necessary and thus newly generates data in which the cover sheet is merged at the leading page of the converted file.

It is noted that the process of step S for merging the cover sheet is performed after converting the file in step S however this order is not indispensable. For example whether the cover sheet is necessary may be determined before converting the file in step S and the file may be converted after generating the image data including the cover sheet.

The file generated in step S is transmitted to the MFP which is set as FAX transmission MFP in together with a facsimile execution demand step S . The facsimile execution demand includes destination set in the workflow setting screen.

The MFP which is the FAX transmission MFP transmits the received image data to the MFP at the destination in response to the received facsimile execution demand.

It is noted that in the embodiment described above the facsimile execution demand is transmitted from the information storing device to the MFP which is the FAX transmission MFP however this is not indispensable. For example a facsimile execution demand storage folder for storing the facsimile execution demand may be generated in the information storing device and the MFP which is the FAX transmission MFP may perform polling monitoring of the facsimile execution demand storage folder. The information storing device does not transmit the facsimile execution demand to the MFP which is the FAX transmission MFP in step S and stores the facsimile execution demand in the facsimile execution demand storage folder. When the facsimile execution demand is stored in the facsimile execution demand storage folder the MFP which is the FAX transmission MFP may obtain the facsimile execution demand to transmit the received image data to the MFP at the destination in response to the facsimile execution demand.

Next a workflow for causing the smart phone to display the image received by the MFP at the destination is described with reference to . is a conceptual diagram for illustrating an example of a facsimile transmission in the embodiment. is a sequence diagram for illustrating an example of details of a process of the facsimile transmission.

The user sets a file conversion format necessary at the time of the format conversion of the file stored in the workflow folder a file destination to which the file is to be transmitted and an e mail transmission destination as is the case with the workflow setting screen illustrated in . The information storing device generates a facsimile reception workflow folder based on the setting by the user step S . As an example it is assumed that the file conversion format is set to PDF the file destination is set to a Hoge folder and the e mail transmission destination is set to abcd xxxx.co.jp . When the facsimile reception workflow folder is generated the information storing device starts to monitor the facsimile reception workflow folder .

Next the MFP at the destination selects as a transfer destination to which the received facsimile is to be transferred the facsimile reception workflow folder generated in step S. It is noted that in the embodiment the user sets the transfer destination as an example.

The MFP at the destination receives the folder list acquiring demand from the user step S . The MFP at the destination transmits the folder list acquiring demand to the information storing device step S . It is noted that the folder list acquiring demand may be transmitted with the HTTP request or the SMB protocol as described with reference to .

When the information storing device receives the folder list acquiring demand transmitted from the MFP at the destination in step S the information storing device transmits a response to the MFP at the destination step S .

In step S the MFP at the destination displays the folder list in the information storing device based on the response transmitted from the information storing device in step S.

The MFP at the destination receives the selection of the facsimile reception workflow folder from the user step S . The MFP at the destination sets the facsimile reception workflow folder as a transfer folder of the facsimile step S .

After the transfer folder of the facsimile is set in step S the MFP at the destination receives the facsimile step S . The MFP at the destination transmits based on the transfer folder set in step S facsimile image data in a TIF format for example received in step S to the information storing device to store the facsimile image data in the facsimile reception workflow folder step S . The transmission of the facsimile image data may be implemented by the HTTP request or the SMB protocol.

When the information storing device detects that the facsimile image data is stored in the facsimile reception workflow folder the information storing device performs the process in based on the setting of the workflow set in step S step S . In this case since the image conversion is necessary in step S in the file format of the facsimile image data is converted from the TIF format to the PDF format in step S. Further since the file transmission is necessary in step S the facsimile image data which is converted to the PDF format is stored in the Hoge folder in step S. It is noted that trimming scaling down scaling up of the image etc. may be performed when the image is converted to the PDF format. Further since the e mail transmission is necessary in step S such an e mail as illustrated in is transmitted to abcd xxxx.co.jp . It is noted that the e mail to be transmitted has a body in which the storage address of the facsimile image data faxdata.pdf that is converted to the PDF format is described as a file storage link as illustrated in .

The smart phone receives the e mail transmitted from the information storing device step S . It is noted that the reception of the e mail transmitted from the information storing device may be implemented by the application that is used for the connection to the information storing device or other applications.

The user selects the address file storage link described in the body of the e mail transmitted from the information storing device as illustrated in . The smart phone transmits to information storing device a demand facsimile image data acquiring demand for acquiring the facsimile image data which is converted to the PDF format and stored in the Hoge folder in the information storing device step S . If the e mail is received by an application other than the application used for the access to the information storing device the smart phone launches the application used for access to the information storing device when the file storage link is selected. The smart phone may transmit the facsimile image data acquiring demand to the information storing device using the application used for access to the information storing device .

The information storing device transmits the facsimile image data which is converted to the PDF format and stored in the Hoge folder to the smart phone in response to the facsimile image data acquiring demand transmitted from the smart phone . In step S the smart phone displays the facsimile image data which is converted to the PDF format and transmitted in step S.

In this way when the facsimile is transmitted to the MFP at the destination the user who uses the smart phone can check the content of the facsimile with the smart phone .

It is noted that if the MFP at the destination is capable of receiving a plurality of facsimile numbers and the transfer destination can be set for the respective facsimile numbers a plurality of the facsimile reception workflow folders may be generated and the respective facsimile reception workflow folders may be the transfer destinations. Storing the facsimile image data in different facsimile reception workflow folders enables the information storing device to transmit the e mail to the different e mail addresses.

For example when the MFP at the destination is capable of receiving the facsimile to the facsimile number 000 0001 as well as the facsimile to the facsimile number 000 0002 the facsimile reception workflow folders of the respective facsimile numbers are set as different transfer destinations. In this way the information storing device copies the facsimile image data transmitted to the facsimile number 000 0001 in the Hoge folder enabling the notification to the e mail address of the user A. Further the information storing device copies the facsimile image data transmitted to the facsimile number 000 0002 in the Hoge2 folder enabling the notification to the e mail address of the user B. With this arrangement the information storing device can perform the notification to different users on a facsimile number basis.

It is noted that the functions of the information storing device according to the embodiment may be implemented by information processing devices such as a plurality of PCs.

According to the cooperative processing system of the embodiment since the information storing device is provided with the WebAPI and the SMB connecting part as an interface to the workflow folder it becomes possible for such a information processing device and an electronic apparatus which cannot utilize the SMB protocol to execute the workflow.

Further when an error occurs at the execution of the workflow the information storing device generates the error content description file and stores the generated error content description file in the workflow folder which enables providing the error content description file utilizing the WebAPI .

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiment s of the present inventions have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

The present application is based on Japanese Priority Application No. 2012 154921 filed on Jul. 10 2012 Japanese Priority Application No. 2013 100636 filed on May 10 2013 and Japanese Priority Application No. 2013 127511 filed on Jun. 18 2013 the entire contents of which are hereby incorporated by reference.

