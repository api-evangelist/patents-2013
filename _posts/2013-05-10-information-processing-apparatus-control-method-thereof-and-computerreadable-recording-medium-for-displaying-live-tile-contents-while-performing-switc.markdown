---

title: Information processing apparatus, control method thereof, and computer-readable recording medium for displaying live tile contents while performing switching thereof
abstract: An information processing apparatus includes a control unit configured to add a first live tile content including printer information about a first print queue and a second live tile content including printer information about a second print queue different from the first print queue to a tile list that is gathering for specifying a live tile content displayed by an operating system, wherein the first print queue and the second print queue are each associated with a same application. The operating system is configured to display the first live tile content in a tile display region according to the tile list and to display the second live tile content in the tile display region in place of the first live tile content after the first live tile content is displayed, and the application is launched when a user specifies the tile display region.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09025184&OS=09025184&RS=09025184
owner: Canon Kabushiki Kaisha
number: 09025184
owner_city: Tokyo
owner_country: JP
publication_date: 20130510
---
The present disclosure relates to a technique for displaying a plurality of live tile contents while performing switching thereof.

Japanese Patent Application Laid Open No. 2010 123103 discusses a method for associating a device management system with a device driver by describing a plurality of driver names in an extensible markup language XML .

According to an aspect of the present disclosure an information processing apparatus includes a control unit configured to add a first live tile content including printer information about a first print queue and a second live tile content including printer information about a second print queue different from the first print queue to a tile list that is gathering for specifying a live tile content displayed by an operating system wherein the first print queue and the second print queue are each associated with a same application wherein the operating system is configured to display the first live tile content in a tile display region according to the tile list and to display the second live tile content in the tile display region in place of the first live tile content after the first live tile content is displayed and wherein the application is launched when a user specifies the tile display region.

Further features and aspects of the present disclosure will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the disclosure will be described in detail below with reference to the drawings.

It is assumed that by applying a technique discussed in Japanese Patent application Laid Open No. 2010 123103 device drivers or print queues associated with applications are displayed in one display region. When such a configuration is adopted for example if a display region is small information about all peripheral devices associated with the applications may not be able to be displayed. Even if the information about the all peripheral devices can be displayed in the one display region as long as the display region is limited when the peripheral devices associated with the applications are increased information about an added peripheral device may not be displayed in the display region.

A central processing unit CPU controls an entire apparatuses according to a program stored in a read only memory ROM or random access memory RAM in a main storage apparatus or an auxiliary storage device . The RAM is used as a work area when the CPU executes various types of processing. The auxiliary storage device records an OS and an application .

Input devices such as a keyboard and a pointing device including a mouse and a touch panel are used to give various types of instructions from a user to the computer connected via an input interface I F .

An output I F is used to output data to outside the client computer in other words the output I F outputs the data to an output device such as a monitor and a printer . The printer may not be directly connected with a local input output I O . In other words the printer may be connected to a network via a communication I F .

Further a common data system bus is used to transmit receive the data between the I Fs and the modules

Additionally the CPU executes the processing based on the program stored in the auxiliary storage device to realize a software configuration of the client computer illustrated in and each step of the flowcharts described below.

As illustrated in a printer driver and a print queue retain a device identification ID corresponding to a connected printer. Further a device management control file describes how the device ID is associated with a device management system and a device management application . With reference to the device management control file the OS can determine how the printer driver the print queue the device management system and the device management application are associated with one another.

Further when a print queue associated with the device management application is generated the OS installs the device management application .

However the device management system cannot manage the print queue corresponding to each function of a plurality of peripheral devices to which internet protocol IP addresses which are different among the peripheral devices are allocated. The device management system manages either a single print queue corresponding to the peripheral device or a plurality of print queues each corresponding to a plurality of peripheral devices to which a same IP address is allocated.

On the other hand the device management application can manage the print queue corresponding to the each function of the plurality of peripheral devices to which the IP addresses which are different among the peripheral devices are allocated.

Furthermore when the OS retains a media access control MAC address of the peripheral device the device management system cannot manage the print queue corresponding to each function of the plurality of peripheral devices to which the MAC addresses which are different among the peripheral devices are allocated. On the other hand the device management application can manage the print queue corresponding to the each function of the plurality of peripheral devices to which the MAC addresses which are different among the peripheral devices are allocated.

According to the specification the printer will be described as an example of the peripheral device corresponding to the print queue however the peripheral device may also be a facsimile FAX . Similarly printer information described below may be information about the FAX.

The device management control file may be generated for each device or one device management control file may be generated for all types of devices.

As illustrated in the OS displays functions and aligned in a tile like arrangement. The OS displays a tile for the device management application as one of the tiles in a tile like shape. According to the specification for convenience a screen illustrated in is referred to as a home screen. The home screen displays information provided by various applications installed in the OS . Also the home screen is provided by the OS to launch the application in response to a user s click operation.

Further when the tile is clicked a screen indicating a state of the plurality of peripheral devices managed by the device management application associated with the device management application is displayed as illustrated in . In the device management application via the screen for indicating the information about the plurality of peripheral devices the user can confirm a current state of the displayed device and consumable goods.

The specification describes examples in which the live tile content is generated in steps of the flowcharts described below. However the device management application may hold an image including predetermined printer information as the live tile content.

According to the example illustrated in after the contents to are sequentially displayed the loop display is performed by returning to the content again. Further according to the example illustrated in the live tile contents and display the printer information about the print queues of Printer AAA Printer BBB and Printer CCC respectively.

The printer information refers to an icon a queue name and status information such as errors of the peripheral device including the printer and the FAX. More specifically with reference to the live tile contents and display the icon and the queue name of the peripheral device corresponding to each print queue. Additionally the live tile content indicates that the Printer AAA is out of toner as the status information included in the printer information. Further the live tile content indicates that the Printer CCC is out of toner and out of paper as the status information included in the printer information. Furthermore since the Printer BBB keeps a normal status the live tile content indicates nothing at a position corresponding to a position where the status is displayed in the live tile content and the live tile content .

All of the icon the queue name and the status information do not need to be displayed in the live tile content as the printer information. One kind of the printer information described above may be displayed.

In the specification a list gathering of the live tile contents is referred to a tile list. The tile list is managed by the OS . By performing loop display according to the tile list the user can recognize that the device management application is associated with each of the Printer AAA the Printer BBB and the Printer CCC. At the same time the printer information about each printer is displayed and thus the information about the printer having a problem can be displayed so that the user can easily recognize the printer state.

With reference to processing in which the device management application generates the live tile content will be briefly described.

On the other hand illustrates processing performed when the status of the Printer BBB is changed from normal to out of toner . At this point the device management application generates a new live tile content indicating that the Printer BBB is out of toner. Subsequently as illustrated in the live tile content indicating that the Printer BBB is in a normal status is replaced with the live tile content . Since the live tile content is replaced with the live tile content the OS instead of performing the loop display of the live tile contents and performs the loop display of the live tile contents and . With this display the user can find the printer having a problematic status of the printers associated with the device management application only by browsing the home screen.

In step S the device management application receives a notification from the OS . When a printer is connected to the client computer and a print queue is generated the OS performs the notification to the device management application associated with the printer. Association is performed with reference to the device management control file . Similarly the OS performs the notification to the device management application also when receiving information about a status change from the connected printer.

In step S the device management application confirms whether the notification indicates generation of the print queue. When the notification indicates the generation of the print queue YES in step S then in step S the queue name which is the name of the generated print queue is acquired from the OS . In step S a new live tile content is generated with the acquired queue name set as a tag name. More specifically an empty live tile content is generated and then the icon the queue name and the status information about the corresponding printer are arranged on the tile. The icon of the printer retained by the device management application is used. Further the status information is acquired from the peripheral device corresponding to the print queue.

In step S the generated live tile content is added to the tile list and then the processing ends. The device management application uses an application programming interface API prepared by the OS to add the live tile content to the tile list.

On the other hand in step S when the notification from the OS does not indicate the generation of the print queue NO in step S then in step S the device management application confirms whether the notification indicates the status change of the print queue. When the notification indicates the status change of the print queue YES in step S then in step S the queue name of the print queue whose status has been changed is acquired from the OS . In step S the live tile content is generated to which the status change is reflected with the acquired queue name set as a tag name. In step S the device management application replaces the live tile content having the same tag name in the tile list with the generated live tile content . With such arrangement when the new printer is connected to the client computer and thus the print queue is added or when the status of the printer that has been already connected to the client computer is changed the live tile content can be correctly updated.

The live tile contents retain their own tag names . The OS performs processing described below when the live tile content having the same tag name as that of the live tile content included in the tile list is added to the tile list. The processing is performed for replacing the live tile content having the same tag name that has been already included in the tile list with the new live tile content. Thus in step S the device management application may only request the OS to add the live tile content to the tile list. Further according to the present exemplary embodiment both the processing for generating the print queue and the processing for changing the status are performed in one flowchart. However only one of the two processing operations may be performed.

The device management application and the OS perform the above operations so that the user can confirm the status of the printer associated with the device management application on the home screen without clicking the device management application .

By specifying the number of seconds of display to the tile list the device management application indirectly notifies the OS of the number of seconds of display.

The device management application may use the API to notify the OS of the specified number of seconds of display.

In other words to the tile list the device management application specifies movement to the next live tile content when a predetermined time elapses after each live tile content is displayed. The device management application specifies the number of seconds of display at timing for adding the live tile content to the tile list in step S or timing for the replacement in step S. The predetermined time herein is three seconds for the live tile contents and and ten seconds for the live tile content and . The processing proceeds to step S when the specified number of seconds elapses in step S and thus the OS can perform an operation illustrated in .

Further as illustrated in the live tile contents of the Printer AAA in a status of being out of toner and the Printer CCC in a status of being out of toner and paper are highlighted. The device management application generates the highlighted live tile contents in step S or in step S to realize the highlighted display. More specifically the emphatic display is realized by differentiating background of the live tile contents of the Printer AAA and the Printer CCC black background according to the present exemplary embodiment from the background of the Printer BBB. In other words the highlighted display is realized by using the image including the background of the live tile content of the print queue having the problematic status the errors which is different from the background of the live tile content of another print queue having the normal status.

As described above the live tile content of the problematic print queue is generated to be more noticeable than the live tile content of the normal print queue so that the user can easily recognize the problems.

Other configurations are not repeatedly described since they are similar to the first exemplary embodiment.

With this arrangement of the print queues associated with the device management application only the problematic print queues are displayed as the tiles on the home screen and thus the user can easily recognize the problematic print queues even when a great number of print queues are associated with the device management application . Processing performed by the OS according to the present exemplary embodiment may be similar to that according to the first exemplary embodiment. Other configurations are not repeatedly described since they are similar to the first exemplary embodiment.

To easily grasp the peripheral device that can be used by the user of the print queues associated with the device management application only the live tile contents having the normal status may be displayed.

There will be described effects of sequentially displaying the live tile contents with print queues having high important statuses in order. When the live tile contents in the tile list are sequentially displayed according to a display order the live tile content with print queues having high important statuses are displayed earlier than other live tile contents. If the display order of the live tile content in the tile list is determined with the importance of the status of the print queue ignored and when the live tile contents are sequentially displayed on the home screen according to a descending order of the tile list the problems described below will arise. If the live tile content listed upper in the tile list is displayed prior to the print queue having the more important status the print queue having the more important status takes time to be displayed on the home screen. If the live tile contents with print queues having high important statuses are displayed in order this problem can be avoided.

More specifically the Printer CCC indicates the status of being out of toner and paper which is the most important status and the Printer AAA indicates is the status of being out of toner which is secondary important and thus the Printer AAA is displayed next to the Printer CCC . The Printer BBB indicating a less important status and the Printer DDD indicating a normal status are not displayed.

The importance for each status is specified by a status point table managed by the device management application . illustrates an example of the status point table . The status point is previously determined for each status . The higher status point indicates the more important status.

On the other hand when the notification does not indicate the generation of the print queue NO in step S then in step S the device management application confirms whether the notification indicates the status change of the print queue. When the notification indicates the status change of the print queue YES in step S then in step S the queue name of the print queue whose status has been changed is acquired from the OS . In step S the print queue management table is updated with the information about the changed print queue.

In step S the device management application calculates the total status point based on the status point table for the print queue that is added in step S or updated in step S. The all print queues are ranked from the first up to the Nth and the print queue management table is updated with the order number set as the tag name .

In step S the device management application generates the live tile contents to which the status information is reflected with the tag names from the first to the Nth.

Finally in step S the generated live tile content is added to the tile list. At this point as described above the live tile content in the tile list having the same name as that of the new live tile content is replaced with the new live tile content.

Thus as illustrated in the information only about the N print queues of high importance can be displayed as the tiles on the home screen. The processing performed by the OS according to the present exemplary embodiment is similar to that of the first exemplary embodiment.

An example of including information about a plurality of printers into one live tile content according to a fifth exemplary embodiment of the present disclosure will be described. For example the information about two printers may be included in one live tile content. With such a configuration when the live tile contents are displayed while performing switching thereof by a method described in the first to fourth exemplary embodiments the information about the two printers in the one tile content may be switched or only the information about one of the two printers may be switched.

Embodiments of the present disclosure can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions recorded on a storage medium e.g. a non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s of the present disclosure and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more of a CPU micro processing unit MPU or other circuitry and may include a network of separate computers or separate computer processors. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a RAM a ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

According to the exemplary embodiments of the present disclosure the printer information about the plurality of print queues can be displayed in the same display region.

While the present disclosure has been described with reference to exemplary embodiments it is to be understood that the disclosure is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2012 110750 filed May 14 2012 which is hereby incorporated by reference herein in its entirety.

