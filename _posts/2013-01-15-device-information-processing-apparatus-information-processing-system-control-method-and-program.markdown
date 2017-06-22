---

title: Device, information processing apparatus, information processing system, control method, and program
abstract: When the information processing apparatus receives an instruction from the device, the information processing apparatus transmits user input information to the device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08988699&OS=08988699&RS=08988699
owner: Canon Kabushiki Kaisha
number: 08988699
owner_city: Tokyo
owner_country: JP
publication_date: 20130115
---
To request a user to enter a password for printing a printer driver often displays a dialog at the time of printing and waits for input from the user. The printer driver then executes printing using a value entered by the user see Patent Literature PTL 1 .

In confidential printing unlike in the case of PTL 1 there are cases where an OS running on an information processing apparatus cannot automatically prompt the user to enter user input information at the time of print execution. In such cases where the user cannot enter user input information at the time of print execution a device cannot acquire user input information necessary to output print data.

In departmental management and FAX transmission as well as in confidential printing there are cases where the OS cannot automatically prompt the user to enter user input information necessary.

A device of the present invention for solving the problem described above includes control means for notifying an information processing apparatus of an execution instruction to cause an application on the information processing apparatus to execute predetermined processing when the information processing apparatus requires entry of user input information after reception of print data receiving user input information corresponding to the print data from the information processing apparatus following the notification of the execution instruction and controlling an output operation on the basis of the user input information and the print data.

Another device of the present invention for solving the problem described above includes control means for notifying an information processing apparatus of an execution instruction when the information processing apparatus requests confidential printing receiving user input information corresponding to print data from the information processing apparatus after the notification of the execution instruction and controlling an output operation on the basis of the user input information and the print data.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

It is to be understood that unless otherwise stated and as long as the functions of the present invention are executed the present invention is applicable to any system regardless of whether it is a single functional unit a system composed of a plurality of devices or a system where connection is established and processing is performed through a network.

A CPU controls the overall operation of the apparatus in accordance with a program stored in a ROM or RAM of a main memory or in an auxiliary memory . The RAM also serves as a work area for various processing performed by the CPU . The auxiliary memory stores an operating system OS and application software . Input devices such as a keyboard a pointing device e.g. mouse and a touch panel are for the user to give various instructions through an input I F to the computer. An output I F is an interface for outputting data to the outside. The output I F outputs data to output devices such as a monitor and a printer . The client may be directly connected through a local I O line to the printer or may be connected through a communication I F and a network to the printer . Reference numeral denotes a common data system bus through which data is transmitted and received between interfaces and modules.

When the CPU executes processing in accordance with a program stored in the auxiliary memory a software configuration of the computer see and an operation in each step of a flowchart described below are realized.

The print processing is executed by performing the following three operations in sequence selecting a printer creating print settings and converting rendering data. First selecting a printer involves selecting a print queue corresponding to the printer that executes printing. Next creation of print settings is performed. A configuration module of the printer driver creates initial values of the print settings for a document. The created print settings are changed using the user interface of the application or printer driver to obtain a final print result intended by the user. For example an output paper size is changed and print options such as duplex printing and black and white printing are selected.

The configuration module provides a user interface of the printer driver . The print settings are stored on the RAM in a binary data structure or in a markup language such as XML. This format varies depending on the specification of the printer driver or operating system . The print settings are created for each document printing. For saving optional device configuration settings of the printer or preference settings of each user the printer driver stores the settings in a registry database of the operating system . Default values of the print settings for each user are stored in the registry database by the print manager of the operating system .

After creation of the print settings the user instructs the application to perform print processing. The application notifies the operating system of the print processing instruction. Through the graphics engine the operating system performs rendering for the printer driver specified. If layout processing is specified in the print settings a temporary spool file is created before the processing proceeds to a rendering module of the printer driver and the print manager starts a layout module .

The layout processing involves changing the order of pages and assigning a plurality of logical pages to one physical page. After changing the layout the layout module performs rendering for the printer driver again.

Upon receipt of the rendering data the printer driver causes the rendering module to convert the rendering data into a printer control language that is a data language that can be understood by printers.

At the same time the printer driver may also convert the print settings into the printer control language. For convenience in explanation the rendering data and the print settings converted to the printer control language will hereinafter be described as being different from each other.

Both the rendering module and the configuration module are often common to a plurality of types of printers . Device to device differences are described in a device dependent data file . The rendering module and the configuration module refer to the device dependent data file as necessary.

The printer control language obtained through conversion by the printer driver is sequentially stored as the spool file .

The print manager acquires the spool file and manages the schedule of data print processing. When the printer becomes ready to print the print manager sequentially transmits data through an I O module to the printer .

Thus the rendering data from the application is converted into the printer control language and printed. Hereinafter the printer control language will be referred to as print data.

To create the print settings for the document the application directly rewrites the print settings or the user rewrites the print settings using a user interface see provided by the configuration module of the printer driver .

The print settings have a structure called DEVMODE structure see in the Microsoft registered trademark Windows registered trademark operating system.

The DEVMODE structure is divided into a standard setting area publicly defined by the operating system and a setting area extended by the printer driver.

The standard setting area contains basic print setting values for changing the paper size and the paper feed stage switching between color and black and white modes etc.

The extended setting area contains values for a paper eject function and a fine color adjustment function corresponding to printer options.

The application is unable to recognize the extended settings of each printer driver . That is the only print settings that can be directly rewritten by the application are those in the standard setting area defined by the system.

Therefore the application typically displays a user interface of the printer driver to allow the user to make print settings in the extended setting area .

The configuration module provides not only the user interface but also an application programming interface API . Therefore it is possible to make print settings in the extended setting area from the outside without displaying the user interface.

However when the API of the configuration module is used the application needs to support each printer driver . Therefore a typical application makes changes only to the standard setting area .

Reference numeral denotes a CPU in the controller unit . The CPU is a processor that controls the overall operation of the system.

The CPU executes processing in accordance with a program stored in a hard disk drive . Thus an operation in each step of the flowchart described below is realized.

Reference numeral denotes a RAM. The RAM serves not only as a system work memory for operation of the CPU but also as a program memory for storing programs and as an image memory for temporarily storing image data.

Reference numeral denotes a ROM in which a system boot program and various control programs are stored.

Reference numeral denotes a hard disk drive HDD in which image data and various programs for system control are stored. Reference numeral denotes an operation unit interface I F serving as an interface with an operation unit UI . Image data to be displayed on the operation unit is output from the operation unit I F to the operation unit . Also the operation unit I F serves to notify the CPU of information e.g. user information entered by the user of the present system from the operation unit . The operation unit includes a display with a touch panel. The user can give various instructions by pressing buttons displayed on the display i.e. by touching the buttons with a finger .

Reference numeral denotes a network interface I F which is connected to the network and performs data input and output.

Reference numeral denotes a modem which is connected to the public line and performs data input and output such as FAX transmission and reception.

Reference numeral denotes an external interface I F which accepts an external input from a USB an IEEE1394 bus a printer port etc.

For use in user authentication a card reader for reading an IC card may be optionally connected to the external I F . When the card reader is connected the CPU can control through the external I F the reading operation of the card reader for reading information from an IC card and acquire the information read from the IC card.

Reference numeral denotes an image bus interface I F . The image bus I F serves as a bus bridge that connects a system bus to an image bus for high speed transfer of image data and converts a data structure. The image bus is a PCI bus or an IEEE1394 bus.

Reference numeral denotes a raster image processor RIP which expands for example vector data e.g. PDL code into a bitmap image. Reference numeral denotes a printer interface I F which connects the printer unit to the controller unit and performs synchronous asynchronous conversion of image data. Reference numeral denotes a scanner interface I F which connects the scanner to the controller unit and performs synchronous asynchronous conversion of image data.

Reference numeral denotes an image processing unit that corrects processes and edits input image data and performs printer correction and resolution conversion on print output image data. Additionally the image processing unit rotates image data performs JPEG compression decompression on multivalued image data and performs JBIG MMR or MH compression decompression on binary image data.

The scanner illuminates an image on a document sheet scans the image with a CCD line sensor and converts the scanned image into an electrical signal which is raster image data. Document sheets are placed on a tray of a document feeder. A printer user gives a reading start instruction from the operation unit . In response to this the CPU instructs the scanner to read document images on document sheets which are fed one by one by the feeder.

The printer unit is configured to convert raster image data into an image on a sheet. For example the printer unit uses an electrophotographic method or an inkjet method to create a printed matter. The electrophotographic method involves using a photosensitive drum and a photosensitive belt and the inkjet method involves ejecting ink from a micro nozzle array to directly print an image on a sheet. The print operation is started by an instruction from the CPU . The printer unit has a plurality of paper feed stages and the corresponding paper cassettes to allow selection of different paper sizes and different paper orientations.

The operation unit includes an LCD unit having an LCD with a touch panel sheet attached thereon. The operation unit displays a system operation screen. When a displayed key is pressed the operation unit notifies the CPU through the operation unit I F of the corresponding positional information. The operation unit includes various operation keys such as a start key a stop key an ID key and a reset key. The start key of the operation unit is used for example to start an operation of reading a document image. The start key has a two color green and red LED in the center thereof to indicate whether the start key is ready for use. The stop key of the operation unit is used to stop an operation in progress. The ID key of the operation unit is used to enter a user ID of the user. The reset key is used to initialize settings from the operation unit.

The card reader reads information stored in an IC card under the control of the CPU and notifies the CPU of the read information through the external I F .

The client executes a print application for touch panels hereinafter referred to as a touch panel print application related to printing operations.

A touch panel print application refers to an application that has a function of responding to print related settings associated with the printer driver and to a notification from the printer. Main functions of the touch panel print application include providing a UI that allows print settings to be made and receiving a PrinterEvent execution instruction from the device. These functions will be described later on.

A PrinterEvent refers to a file that the printer transmits to the touch panel print application on the client. Upon receipt of the PrinterEvent the touch panel print application executes processing of an event corresponding to the PrinterEvent.

The description of the present specification is based on the assumption that the touch panel print application is always running on the client and is ready to receive a PrinterEvent.

The touch panel print application may be configured to start upon receipt of a PrinterEvent on the client . In this case the operating system may be configured to start the touch panel print application upon receipt of a PrinterEvent.

The touch panel print application and a general purpose application for touch panels hereinafter referred to as a touch panel general purpose application described below are designed to be operated with the touch panel and the pointing device . However they may be designed to be operated only with the pointing device .

The touch panel print application is preferably installed simultaneously with the installation of the printer driver. This is because in the present specification the touch panel print application and the printer driver operate in a synchronized manner. Thus the description of the present embodiment is based on the assumption that the printer driver and the touch panel print application are already installed on the client and are associated with each other.

Web Services on Devices WSD used in transmitting and receiving a PrinterEvent will now be briefly described. WSD is a technique used to discover a device i.e. a printer in the present embodiment on the network use functions of the device and acquire information about the device.

The present specification describes a system that uses WSD as a communication means of a port monitor. As another communication means of the port monitor TCP IP communication or USB may be used to connect the client to the printer. With WSD the device can automatically transmit a PrinterEvent. With WSD for example if a finisher configuration of the printer is physically changed it is possible to broadcast the finisher change notification to all clients.

However if the communication means of the port monitor is TCP IP communication the PrinterEvent cannot be transmitted on the initiative of the device. Instead the client needs to check the state of the device using a polling function. Specifically if the communication means of the port monitor is TCP IP communication the client uses a polling function or the like to check and acquire a PrinterEvent notification from the device to the client so that the same function as that of the present embodiment can be realized.

As described below the printer has a user authentication function and a job saving function and associates user input information with print data. Thus it is possible to use a confidential printing function which does not allow printing without user authentication.

In the present embodiment a user name and password in confidential printing will be described as an example of user input information for printing.

User input information provided by the printer driver can include departmental management information and FAX information. A user name and password is not entered when confidential printing is not performed.

Specifically if the printer uses departmental management information instead of a user name and saves a log that associates the departmental management information with a job of print data the user can calculate the printing cost for each department. The FAX information includes a phone number. When FAX information is entered the printer performs FAX transmission on the basis of print data and a phone number. In FAX transmission the device does not necessarily perform printing on the basis of print data. However data transmitted by the client will be referred to as print data as in the case of confidential printing and departmental management. The printer unit may be optional if the device performs FAX transmission only.

Hereinafter in the present specification entering user input information will be referred to as entering a password.

Examples of methods for authentication other than entering a user name and password include using a personal identification number a contact noncontact type key or card biometrics or some combinations of them. The present specification will hereinafter be described on the assumption that a user name and password is used for authentication.

Processing performed by the printer according to the present embodiment will now be described with reference to the flowchart of .

In step SB the printer determines from the print settings whether the print data is for confidential printing. If the printer determines that the print data is not for confidential printing the processing proceeds to step SB. Then the print data starts to be output and the print processing ends. If the printer determines that the print data is for confidential printing the processing proceeds to step SB.

To realize confidential printing the user may set a password on the client before transmitting data so that the user does not have to enter the password on the client after the printer receives the data. In this case since user input information accompanies the data transmitted from the client to the printer the client does not have to prompt the user to enter a password after the client transmits the data. Therefore if the printer determines in step SB that there is no need to enter information on the client the processing proceeds to step SB where the received data is registered as a confidential print job in the printer . If the printer determines in step SB that information needs to be entered on the client the processing proceeds to step SB.

In step SB the printer transmits a PrinterEvent to the client . The PrinterEvent is written in a format e.g. XML format that can be read by the touch panel print application. The PrinterEvent contains for example an instruction to prompt the user for input a job identifier for identifying the confidential print job an IP address of the printer a print data name and a user name.

For example a universally unique identifier UUID may be used as the job identifier. By associating a UUID with each job and writing the UUID in the PrinterEvent the job can be easily associated with the PrinterEvent.

The IP address is used by the printer to communicate with the client . The IP address may not be necessary if the printer can communicate with the client .

In step SB the printer waits for a cancellation instruction or user input information from the client . Executing the step of waiting for a cancellation instruction or user input information in step SB does not interrupt the other functions of the printer . Therefore multiple users can simultaneously execute confidential printing in accordance with the flowchart of .

The printer may be configured to delete print data if no user input information is received for a certain length of time. However when the printer is configured to receive a cancellation instruction the printer can determine whether the user actually intends to cancel the confidential printing or still wants to continue the confidential printing even though the connection between the client and the printer has been lost.

In step SB if the information received is a cancellation instruction the processing proceeds to step SB where the print processing ends. If the information received is not a cancellation instruction the processing proceeds to step SB.

In step SB if the information received is user input information the processing proceeds to step SB. If the information received is not user input information the processing returns to step SB where the printer enters the waiting state again.

In step SB the printer associates the received user input information with the print data by using a job identifier and registers them as a confidential print job in the printer .

In step SB the user logs in to the printer and selects from registered confidential print jobs a job the user wants to print. A confidential print job has a function of asking the user for a password after selection of the job. Therefore the printer accepts the input of a password here.

In step SB the printer compares the password the user has entered on the printer with the password for the registration of the confidential print job.

If these passwords match the processing proceeds to step SB. If the password entered on the printer is incorrect the processing returns to the job selection screen in step SB where the user is prompted for input again.

The printer may be configured such that the user can select without logging in to the printer a confidential print job the user wants to print from a list of registered jobs and is asked to enter a password after the selection of the confidential print job.

In step SB the printer starts to output the print data. In step SB the print processing ends. If the user input information contains departmental management information the printer associates the departmental management information with the job of the print data and saves them. If the user input information contains a phone number the printer transmits the print data on the basis of the phone number.

In step SA printing is executed from the touch panel general purpose application by the user on the client . This means that a printing instruction is executed by selecting any print queue from the touch panel general purpose application. In response to a print execution instruction from the user the printer driver transmits print data and print settings to a predetermined printer. The print settings contain data indicating that the print data is for confidential printing.

In step SB of the confidential printing described above data transmitted from the client to the printer contains a password. For the client side however a description will be given only of processing in which the client asks the user to enter a password after transmitting the data.

In step SA the touch panel print application running on the client starts processing corresponding to the PrinterEvent received in step SA.

In step SA the touch panel print application running on the client displays a password entry screen. The displayed screen preferably has a user friendly UI suitable for a touch panel. To realize a user friendly UI the client can provide larger buttons or display the touch panel print application over the entire screen.

Instead of directly displaying the password entry screen for the touch panel print application the client may display a dialog that prompts the user to start the touch panel print application.

Reference numeral denotes a screen for the touch panel print application. Upon receipt of a PrinterEvent from the printer the touch panel print application can prompt the user for input with a user friendly UI suitable for a touch panel.

Reference numeral denotes a field where a print data name can be displayed and edited. The input I F is used for input. Reference numeral denotes a field where a user name is displayed. Reference numeral denotes a field where a password can be entered. The functions of buttons denoted by reference numerals and will be described later on.

The touch panel print application may call another application which displays the UI illustrated in .

Although the user is prompted for input for one job in the present embodiment there are cases where user input is required for a plurality of jobs. For example assume that the user suspends the execution of the touch panel print application without entering user input information on the touch panel print application. Here the suspension means that the user switches from the currently active application to another application. Then after the suspension if the user executes printing on the touch panel print application the user is required to enter user input information twice for the first execution of printing on the touch panel print application and the second execution of printing after the suspension.

In this case it is possible that the user input information corresponding to the first execution of printing cannot be entered. If the touch panel print application is configured to save a list of jobs waiting for user input and allow the user to enter user input information for a job selected by the user user input information can be entered twice for the two printing operations described above.

If the Cancel button is pressed in step SA the client determines that the printing has been cancelled. In this case the client transmits a cancellation instruction to the printer so as to cancel the registration of the corresponding print data in the printer . The printing can be regarded as being cancelled if no input has been received for a certain length of time in step SA. Then the processing proceeds to step SA.

When the user enters a password in the field and presses the OK button in step SA the processing proceeds to step SA.

In step SA the client transmits user input information to the printer . Then the processing proceeds to step SA.

In step SA the client terminates the processing in the touch panel print application and resumes the processing in the touch panel general purpose application.

As described above even when the OS cannot automatically prompt the user to enter user input information at the time of print execution the client can prompt the user to enter user input information by acquiring a notification from the device. Thus the client can instruct the device to perform an output operation based on user input information and print data.

Although the device makes various determinations in the first embodiment such determinations can be made by the touch panel print application installed on the client. In the present embodiment after executing printing the client transmits to the device an instruction to transmit a PrinterEvent. In response to this the device transmits to the client the PrinterEvent corresponding to the instruction. The client performs processing corresponding to the PrinterEvent in the touch panel print application. Thus even if the size of print data is very large the client can immediately receive the PrinterEvent. Therefore it is possible to solve the problem of taking much time to display a user input screen.

Note that the same operations as those of the above described steps will be given the same step numbers and their description will be omitted unless otherwise stated.

In step SB if the printer determines that information received is a PrinterEvent transmission instruction the processing proceeds to step SB.

In step SB the printer transmits a PrinterEvent in response to the PrinterEvent transmission instruction received from the client . A PrinterEvent transmission instruction refers to an instruction command that serves as a trigger for the printer to transmit a PrinterEvent to the client . In the present embodiment the printer receives an instruction command to transmit a PrinterEvent that prompts the user to enter a password. Upon receipt of the instruction command the printer transmits the PrinterEvent that prompts the user to enter a password. Then the processing returns to step SB.

If the printer determines in step SB that the information received is not a PrinterEvent transmission instruction the printer assumes that data has been received. The processing then proceeds to step SB.

If the printer determines in step SB that the received data is for executing confidential printing the processing proceeds to step SB.

In step SA printing is executed from the touch panel general purpose application by the user on the client . This means that a printing instruction is executed by selecting any print queue from the touch panel general purpose application. In step SA unlike step SA in the first embodiment the touch panel general purpose application does not transmit print data to the printer . Instead the client saves created print data and print settings.

In step SA the client determines from the print settings whether information needs to be entered at the time of printing. If no information needs to be entered at the time of printing that is if a password to be entered is already set or the printing does not involve entering user input information the processing proceeds to step SA. After the client transmits the print data and user input information to the printer in step SA the processing ends in step SA.

If the client determines in step SA that information needs to be entered at the time of printing the processing proceeds to step SA where the client transmits a PrinterEvent transmission instruction command to the printer . This means that the client requests the printer to perform confidential printing departmental management or FAX transmission.

The PrinterEvent transmission instruction command may be configured by transmitting to the printer empty data which produces no printed output by being processed by the printer .

Unlike the first embodiment even if the client determines in step SA that the printing has been cancelled the client does not transmit a cancellation instruction to the printer . This is because since the printer has not yet saved the print data at the point of step SA there is no need for the client to instruct the printer to delete the print data.

A method for associating user input information with print data is to describe either in the user input information or the print data information indicating that the user input information and the print data are associated with each other. Another method is to combine the print data and the user input information into one data.

When the client does not simultaneously perform a plurality of confidential printing operations there is only one piece of print data in step SA. Therefore it is easy to associate the PrinterEvent received from the printer with the print data.

The client can simultaneously perform a plurality of confidential printing operations by using a UUID as in the first embodiment described above. That is when print data is issued a job identifier such as a UUID is associated with the print data and a PrinterEvent transmission instruction command including the job identifier is transmitted to the printer . The printer writes in the PrinterEvent the job identifier included in the transmission instruction command and transmits the PrinterEvent to the client . The client may associate the PrinterEvent with the print data by matching the job identifier acquired from the PrinterEvent with the job identifier associated with the print data.

The processing performed in and after step SB on the printer side according to the present embodiment is the same as the processing that involves executing confidential printing in the related art. Thus even in the cases where the OS cannot automatically prompt the user to enter user input information at the time of printing the client can prompt the user to enter user input information without causing significant changes to the printer as compared to the first embodiment.

After receiving a PrinterEvent the touch panel print application may not display an input screen for password entry. Specifically if user input information is entered in the touch panel print application by default the touch panel print application does not display an input screen for password entry after receiving a PrinterEvent. Before execution of printing the user enters user input information in the touch panel print application in advance.

With this configuration steps SA SA SA and SA in the flowchart of are not performed. In step SA the client transmits user input information set in advance by the user to the printer . The same method is applicable to departmental management and FAX transmission.

Thus the user can perform confidential printing departmental management and FAX transmission without entering user input information every time printing is executed.

In this processing software program that realizes the functions of the embodiments described above is supplied through a network or various storage media to a system or apparatus so that a computer or CPU or MPU of the system or apparatus reads and executes the program.

Even when the OS cannot automatically prompt the user to enter user input information at the time of print execution the information processing apparatus can prompt the user to enter user input information by acquiring a notification from the device. Thus the information processing apparatus can instruct the device to perform an output operation based on the user input information and print data.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of International Patent Application No. PCT JP2012 050920 filed Jan. 18 2012 which is hereby incorporated by reference herein in its entirety.

