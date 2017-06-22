---

title: Apparatus, control method, and storage medium to instruct a framework to stop a target application based on a usage amount of a resource and a type of the target application
abstract: At a timing after a target application is installed, in a case where a usage amount of a resource used at a predetermined timing by the target application exceeds a declaration of a maximum value of the usage amount of the resource described in an application file corresponding to the target application, a framework is instructed to stop the target application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09274775&OS=09274775&RS=09274775
owner: Canon Kabushiki Kaisha
number: 09274775
owner_city: Tokyo
owner_country: JP
publication_date: 20130110
---
The present invention relates to an apparatus that can install and execute an application a control method and a storage medium.

Conventionally an image forming apparatus as typified by Multifunctional Embedded Application Platform MEAP trademark of Canon Inc. has been provided in which an application execution environment is installed and an application can be installed and executed. Applications that can be installed into the MEAP include an authentication application for performing authentication of the image forming apparatus in addition to normal applications.

In such an image forming apparatus a size of a persistent storage area non volatile storage area such as a hard disk drive HDD and a flash read only memory ROM that can be used by the application is previously determined and each application uses the persistent storage area within a predetermined range.

In the MEAP as described in Japanese Patent Application Laid Open No. 2006 338268 a predetermined management file in each application declares a usage amount of the persistent storage area used by each application. In addition a mechanism is also discussed in which the application can be installed only when a total sum of sizes declared by each application does not exceed a range of a maximum usable size predetermined by the image forming apparatus.

On the other hand as a solution when resources are depleted Japanese Patent Application Laid Open No. 2010 134871 discusses an information processing apparatus that notifies a user of resource depletion information.

However under a specific condition due to an operation difficulty of the application a case may occur where the application uses the storage area more than the declared amount. For example when an operation log of the application is accumulated and stored recording is performed over the upper limit of the log size.

If such a situation is left unsolved the resource of the image processing apparatus is depleted and thus the image processing apparatus may not continue the operation normally. As another issue if a function of performing notification after the resource has been depleted is provided the image forming apparatus may be already in an unusable state when it is notified and thus a user s work may be stopped for long hours.

In addition the following issue is also conceivable. As a type of the application that can be installed into the image forming apparatus in addition to the normal applications an authentication application for performing user authentication for allowing a user to use the image forming apparatus is provided.

Since the authentication application is used to protect the entire image forming apparatus the authentication application needs to be more appropriately operated compared with the normal applications. To prevent the image forming apparatus from being wrongly used the authentication application needs to be differently operated from the normal applications.

The present invention is directed to provide an image forming apparatus that can solve at least one the issues described above.

According to an aspect of the present invention an apparatus including an application framework for managing a life cycle of an application. The apparatus includes an instruction unit configured to in response to receiving an installation instruction instruct the framework to install a target application an acquisition unit configured to acquire from the framework a declaration of a maximum value of a usage amount of a resource described in an application file corresponding to the target application and a determination unit configured to determine a usage amount of a resource that is uniquely allocated to an application on installation of the application and used by the target application at predetermined timing wherein at a timing after the target application is installed in a case where the determined usage amount of the resource used at the predetermined timing by the target application exceeds the declaration of the maximum value of the usage amount of the of the target application the instruction means is configured to instruct the framework to stop the target application.

Further features and aspects of the present invention will become apparent from the subsequent detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

According to a first exemplary embodiment as illustrated in an image forming apparatus and personal computers PC and are communicably connected to a network

The control unit is connected with a function unit and controls operations of an operation unit a scanner unit and a printer unit . The operation unit includes a liquid crystal display unit having a touch panel function and a keyboard. The control unit controls each unit to provide a user with a service for issuing a job for the image forming processing and according to a user s instruction issues the job for the image forming apparatus and processes the issued job.

The scanner unit reads an image on a document to generate image data and inputs the image data into the control unit . The printer unit prints the image data to be printed that is input from the control unit on a recording medium. An interface unit connects the control unit with a local area network LAN to receive image data to be printed from the PCs and on the network or to transmit screen data read by the scanner unit .

A print image received from the PCs and is temporarily stored in an image memory and then printed by the printer unit via the control unit .

For an operating system OS a real time OS is generally used however these days a general purpose OS such as Linux registered trademark may be used. JavaVM is a virtual machine which is represented by Java registered trademark provides an execution environment of the application.

An application framework on the JavaVM includes a function of managing a life cycle of a management target application which is operated on the JavaVM and an interface I F for controlling the function.

The life cycle indicates states of the application including installation activation stop and uninstallation of the application. The application framework according to the first exemplary embodiment is an Open Service Gateway Initiative OSGi registered trademark framework specified by the OSGi Alliance.

Management of the life cycle refers to performing on the application the appropriate processing corresponding to a changed state in a case where a state of the application is changed to anyone of the above described states. For example if the state of the application is changed to an activation state the application framework controls the application to activate and when the state of the application is changed to an uninstallation state the application framework uninstalls the application. As described above the application framework included in the JavaVM includes the function of managing the life cycle of the application.

The application framework manages the application based on a declaration value described in the application file described below. For example the application framework performs management of association of an application name uniquely allocated to the application with a substance of the installed application and management of version information about the installed application.

A device control library running on the JavaVM includes an I F for enabling a user to use the image forming processing such as printing and scanning provided by a native function from applications A and B described below. The I F abstracts various functions provided by the image forming apparatus and is configured to enable another different image forming apparatus to realize the same function by the same procedure.

More specifically the function provided by the image forming apparatus is converted to an object. A parameter is set for the object or an application programming interface API for acquiring the parameter from the object is called so that various types of information can be set and acquired. In addition the functions such as printing and scanning can be performed by calling the API according to a predetermined procedure.

With this arrangement if the application is executed in an environment different from that of the OS the native function of controlling the image forming apparatus can be used.

An operation unit control library running on the JavaVM includes a function of displaying an operation screen on the liquid crystal display unit of the operation unit according to an instruction from the applications A and B described below or transmitting key input to each application and an I F for using the function.

A communication control library running on the JavaVM includes a function of communicating with other communication devices on the LAN via the interface unit and an I F for using the function. A native function is a collective term of software providing original functions of the image forming apparatus such as scanning copying and printing of the document and transmitting the image to the PC using the operation unit .

The native function is a software group built in at a stage of manufacturing the image forming apparatus and not installed according to a user s instruction. On the other hand the application on the JavaVM can be installed according to a user s instruction and can be managed and operated in a client environment.

As illustrated in the native function is the software running on the OS and on the other hand the applications such as an installer service and the application A is the software running on the JavaVM . A native unit corresponds to the native function .

The application or applications running on the JavaVM also use the device control library to perform the same device control in different image forming apparatus and thus the image forming apparatus can be customized after the stage of manufacturing.

The application or applications running on the JavaVM transmit various commands such as an image processing command to the native function via the device control library to cause the native function to execute predetermined processing. Accordingly even after the image forming apparatus is sold and installed in the client environment a user who is a client can add an application so that the user can use an image processing application providing further effective solutions.

Applications can be installed to improve the image forming apparatus and thus various solutions can be provided for the user.

An installer service performs installation processing by registering a plurality of applications such as the applications A and B described below into the application framework . An instruction to change the state of the application is transmitted from the installer service.

The installer service displays to the user a management screen on which the user can input an instruction to change the state of the application and thus the user input an instruction to change the state of the application via the management screen. A system service group provides various functions other than the installer service to the application however the system service group is not specifically described in detail in the present exemplary embodiment.

The installer service and the system service group are built into the image forming apparatus at the stage of manufacturing thereof similarly to the native function . Applications and are installed by the installer service and provide various functions on the image forming apparatus . The applications and can use the operation unit control library and communicate with the user via the operation unit .

In addition the applications and can receive data from the PC via the interface unit using the communication control library and perform printing using the printer unit via the device control library .

The installer service can be accessed from a browser of the PCs and via the interface unit and receives a predetermined application file using the communication control library . A screen for managing the application will be described with reference to below.

Management information in the management information portion includes an attribute of the application or a declaration of specification. An identification ID is used for uniquely identifying the application. According to the present exemplary embodiment an individual universally unique identifier UUID is defined for each application. The application file has an application name .

A maximum usage size of the HDD can be used by the application file on the image forming apparatus . The management information portion in the application file is referred to as a manifest.

Based on the declaration described in the application file the application framework manages the application. More specifically the application framework manages the application such that the attribute of the application or the declaration of the specification are stored and then information about the declaration is provided for an inquiry.

Identification information is used for identifying a type of the application file . According to the present exemplary embodiment the application A installed by the installer service includes information of Normal Service .

The Normal Service indicates the application that is installed and executed in the client environment and used by customizing the function provided by the image forming apparatus from the operation unit or the PC via the browser. In other words the Normal Service application can be installed when a user for example a manager in the client environment performs an operation to install the application. Accordingly the image forming apparatus can provide various solutions.

Services other than the Normal Service application include a Login Service indicating an authentication application and a System Service indicating the installer service and the system service group previously built into the image forming apparatus.

Such applications can be installed not by a user s operation but by a different predetermined method. The predetermined method includes for example installation by a manufacturer at the stage of manufacturing or installation by a salesperson who sells the image forming apparatus.

As described above such an application is typically installed not by a client user who has purchased the image forming apparatus but by a user other than the client user. A parameter stored in the management information portion is not limited to items described in the present exemplary embodiment.

The installer service performs various types of control processing including determination of whether to install the application using the application file when installing the application however when the specified processing is finished the application file is discarded. Thus if the installer service confirms the declaration described in the application file the application list needs to be acquired from the application framework.

The application list stores application objects in an array. In a first application object information about the application A is acquired according to the present exemplary embodiment.

Application identification information corresponds to the ID . Application name information corresponds to the application name . A maximum storage area size corresponds to the maximum size . Application type information corresponds to the identification information .

Path information indicates a storage location in which the application is stored. The installer service can acquire the above described information pieces from the application object using a predetermined acquisition API.

According to the present exemplary embodiment a work folder in the HDD is allocated to the application framework and the application framework can use a folder beneath the work folder . The folder allocated to the application framework may be determined by the user or previously determined.

The application framework installs the application according to an instruction of the installer service . At this point in the work folder of the HDD folders and independent for each application are generated using the I F of the OS .

In other words the application is installed and then the resource is uniquely allocated to the application. The application file and the like are stored in the above described folders.

According to the present exemplary embodiment each application can freely generate folders and files only in the folders and in which the application is installed. According to the present exemplary embodiment the maximum size of the HDD that can be used by the application is an allowable size of the work folder .

When the application is installed in the image forming apparatus the installer service controls the installation instruction such that a total of the maximum usage sizes declared by the individual applications does not exceed the size allowed by the work folder .

For example it is supposed that a persistent storage area where the application can be installed is 1 giga byte GB and the persistent storage area currently used by a plurality of applications is 800 megabyte MB . In such a case when a target application to be installed exceeds 200 MB the installer service does not issue the installation instruction and when the application does not exceed 200 MB the installer service issues the installation instruction.

Each application to be installed is installed supposing that the resource is used within a declaration value declared in the application file corresponding to each application. For example when the declaration value of the maximum usage amount of the HDD of the application A is 100 MB the application A is allowed to use 100 MB and installed.

In other words when the total of the declared maximum value and the resource amount currently used by the application is less than the maximum value previously allocated to all applications running on the application executing environment the installation is allowed.

However a case is conceived where the HDD amount used by the specific application exceeds the maximum usage amount declared by the application file. This is a state where the declaration value relating to the usage of the resource in the application file is used when the application is installed however the declaration value is not strictly adhered to when the application framework manages the application.

The application framework performs the management to associate the application name and version information in the application file and the substance of the installed application with one another. However the application framework manages the declaration value related to the usage of the resource in the application file but does not include a function of controlling the operation of the application according to the declaration value.

Thus if a capacity of the work folder used by the application exceeds the declaration value allowed by the installer service the operation of the image forming apparatus may become unstable. Further a situation that the image forming apparatus stops the operation may occur.

The lists in are displayed when the user accesses the installer service from the browser on the PC . A screen is a screen in a normal state and the installer service forms the screen according to the application list acquired via the application framework .

A state indicates a current state of the application in the life cycle of the application acquired via the I F of the application framework . A disk usage amount for each application indicates the usage amount of the folder storing the application by the path information and the function of the OS at a predetermined timing.

A Maximum disk usage is information indicating an upper limit of disk usage which is displayed by acquiring information in the application information via the application framework . A screen is a screen of the installer service displayed when overuse of the resource is detected according to the present exemplary embodiment.

A state indicates the state of the application which indicates that the application A is stopped due to the resource over according to the present exemplary embodiment. A disk usage amount for each application indicates the current usage amount similarly to the disk usage amount . As items to be displayed on the application list screen other items than those illustrated in of the present exemplary embodiment may be displayed. In addition to get the user to recognize that the application is stopped because the usage resource exceeds the declaration a symbol for recognizing the state of the application may be displayed.

A job list stores job objects set in an array. According to the present exemplary embodiment it is assumed that the application A performs a printing job. A first job object includes various parameters for characterizing the job.

A parameter indicates a job name. A job reception number is given by the native function . The native function gives different numbers to the jobs each time it receives various jobs. Application identification information is used for identifying the application that performs the printing job .

A state of the print job indicates that the print job is in operation according to the present exemplary embodiment. The parameter of the job is not limited to the example illustrated in of the present exemplary embodiment and may include other parameters such as a sheet size and an output method.

An item indicates processing to be performed when the overuse of the resource resource over occurs in the application A and the processing is set to immediately stop the operation of the application when the resource over is detected. An item indicates processing to be performed when the resource over occurs in the application B and the processing is set to immediately stop the operation of the application similarly to the application A. An item is used to set a monitoring period. According to the present exemplary embodiment the setting indicates that monitoring is performed once day namely once a day.

The resource monitoring condition is not limited to the contents in of the present exemplary embodiment. For example a specific amount may be specified or the monitoring period may be input with numeral values. In addition the set information is stored in a predetermined area in the HDD . As described above a method for setting the monitoring date and time and the monitoring conditions is not limited.

The setting screen in is displayed when the user accesses the installer service from the browser on the PC . An item is used to set how to control a copy job when the resource over of the application is detected and whether to cancel or continue the copy job can be set. An item is used to set how to control a printing job when the resource over of the application is detected and whether to cancel or continue the print job can be set.

An item is used to set how to control a scanning job when the resource over of the application is detected and according to the present exemplary embodiment the cancel is selected. According to the present exemplary embodiment a reason why only copy job and printing job include an option of continue is that in a copy function and a printing function the application is less likely to store data involved in printing in the work folder .

On the other hand in a scanning function a scanned image is likely to be subjected to processing such as transmission or image conversion and thus the scanned image may be stored in the work folder . In order to prevent the application that has been already stopped from using the resource any more specifications of the resource are controlled according to a type of the issued job. The set information is stored in a predetermined area in the HDD .

Further the timing is set by the monitoring period . As described above it is apparent that the present invention is directed to the image forming apparatus configured to restrict a wrong operation of the installed application and avoid being in an inappropriate state.

In step S the installer service acquires all application lists existing on the JavaVM via the application framework . In step S a parameter N for checking all objects in the application list acquired in step S and a parameter K for checking the number of times of executions of the flowchart illustrated in are initialized.

In step S the installer service acquires the maximum storage area size of an N th application via the application framework . According to the present exemplary embodiment as the N 0 th application information about the application A is used.

In step S the installer service acquires the path information about the N th application which is the application A via the application framework .

According to the present exemplary embodiment information specifying the application folder is acquired. As illustrated in according to the present exemplary embodiment since each application is stored in the different folder the different path information can be acquired for each application.

In step S the installer service acquires a current usage amount of the folder indicated by the path information acquired in step S via the OS to acquire a current HDD consumption amount of the application A . The installer service acquires the usage amount of the folder indicated by the path information acquired in step S and confirms the usage amount of the resource currently used by the installed target application.

The timing for acquisition is a predetermined timing and may be the same timing as that set by the monitoring period or may be different therefrom. Thus the amount of the resource used by the application can be acquired at an earlier timing than the timing set by the monitoring period . As described above the timing for acquiring the resource usage amount is not limited.

In step S the installer service compares a size acquired in step S with that in step S. However the data to be compared is adjusted according to the resource monitoring condition of the application or the setting in the item .

In step S a result of the comparison performed in step S is evaluated. When it is determined that the resource is over YES in step S the processing proceeds to step S. When it is determined that the resource is not over NO in step S the processing proceeds to step S.

In step S the installer service performs processing of when the resource over is detected. With reference to the processing performed on the application in step S will be described in detail. In step S the parameter N is added for checking a subsequent application in the application list acquired by the installer service in step S.

In step S it is determined whether the check is completed on all items in the application list acquired in step S. When it is determined that the check is completed YES in step S the processing in the flowchart is ended. When it is determined that the check is been completed NO in step S the processing returns to step S and the resource monitoring is performed on the subsequent application.

In step S the parameter K is added. In step S the installer service outputs a message to be indicated on a message illustrated in onto a liquid crystal panel of the operation unit via the operation unit control library .

In step S the installer service determines the type information of the application. More specifically the installer service determines whether the content acquired via the application framework coincides with the Normal Service . As a result of determination if the content coincides with the Normal Service YES in step S the processing proceeds to step S. If the content does not coincide with the Normal Service NO in step S the processing proceeds to step S.

In step S the installer service determines whether the application has already been started or is in operation. When it is determined that the application has been started YES in step S the processing proceeds to step S. When it is determined that the application has not been started NO in step S the processing proceeds to step S.

In step S the installer service displays an error screen illustrated in on the liquid crystal display unit of the operation unit via the operation unit control library . A number displayed in an error code illustrated in is changed according to the content of the application type information .

The error screen displays an error code to be notified to a repair company repair vendor that repairs the image forming apparatus. A repair worker of the repair company who is notified the error code can understand the state of the image forming apparatus owned by the client user and appropriately repairs the image forming apparatus.

In S the installer service stops the application via the application framework . More specifically the installer service instructs the application framework to stop and the application framework performs processing dealing with the stop state in response to the application shifting to the stop state.

In step S the installer service acquires the job list in operation from the native function via the device control library . In step S the parameter for confirming the job list acquired in step S is initialized.

In step S the installer service determines whether the application identification information coincides with the application from an M th job in the job list acquired in step S. More specifically similarly to step S the application identification information of the application A is compared with the application identification information of the job object . When it is determined that the application identification information coincides with the application YES in step S the processing proceeds to step S. When it is determined that the application identification information does not coincide with the application NO in step S the processing proceeds to step S.

In other words it is determined whether the job issued by the target application that is instructed to stop in step S is included.

In step S the installer service determines whether to cancel the job and determines setting content of the set item stored in a predetermined region in the HDD . As a result when it is determined to cancel the job YES in step S the processing proceeds to step S. When it is determined not to cancel the job NO in step S the processing proceeds to step S.

In step S the installer service cancels the job via the device control library . More specifically when it is determined that the application identification information coincides with the application in step S the installer service issues an instruction to stop the processing on the job issued by the target application instructed to stop.

In step S to perform processing on a subsequent job in the job list acquired in step S a parameter M is added.

In step S the installer service determines whether confirmation of all the jobs acquired in step S is completed. When it is determined that confirmation of all the jobs is completed YES in step S the processing proceeds to step S. When it is determined that confirmation of all the jobs is not completed NO in step S the processing returns to step S and performs the processing on a subsequent job.

In step S the installer service sets a message indicating stoppage of the job due to the resource over in a column for the state of the application in an application list .

A reason why if the application type information indicates a Long Service in step S the same processing as that of the System Service is performed is that the authentication application is directed to protection of the image forming apparatus.

More specifically it is because if the Long Service and the Normal Service are treated as the same and the application is stopped the user cannot be authenticated which may cause a problem in security. According to this processing if the problem occurs in the authentication application the security of the image forming apparatus can be maintained.

According to the first exemplary embodiment when the usage amount of the resource of the application exceeds the declaration the image forming apparatus is immediately stopped. However stoppage of the application may stagnate office operations. Thus according to a second exemplary embodiment the image forming apparatus can be used without stopping the application as possible as it can.

According to the second exemplary embodiment as illustrated in when the installer service installs an application temporary folders and having predetermined names are generated. Then the application stores a file to be temporarily used in the temporary folders and .

In step S the installer service deletes file data in the temporary folder or of the application. In step S the installer service performs the same processing as in step S to compare a newly acquired usage amount with the declaration value.

In step S a result of the comparison performed in step S is evaluated. When it is determined that the resource is over YES in step S the processing proceeds to step S. When it is determined that the resource is not over NO instep S the processing proceeds to step S.

According to the second exemplary embodiment if the application accidentally causes the resource over and if it happens in the file in the temporary folder the application can be automatically restored.

According to the first exemplary embodiment the function is provided by the installer service previously built into the image forming apparatus. However a configuration for solving the problem of the present invention without updating the installer service will be described in a third exemplary embodiment.

According to the third exemplary embodiment the function realized in the installer service according to the first exemplary embodiment is provided as a normal application. More specifically an application described in the third exemplary embodiment includes the application list function illustrated in the resource monitoring condition setting function and the monitoring period setting function illustrated in and the job control setting illustrated in . Further in place of the installer service the application performs the processing in the flowcharts illustrated in .

According to the third exemplary embodiment in place of the processing in step S illustrated in the processing in step S is adopted. In step S the application K displays an error message indicated in a status line in via the operation unit control library .

According to the third exemplary embodiment without changing the installer service previously built into the image forming apparatus the resource monitoring function equivalent to that of the first and second exemplary embodiments can be realized. Therefore in the image forming apparatus that has been already sold when the installer service is installed and executed as a normal application the effect equivalent to that of the first exemplary embodiment can be acquired.

Each exemplary embodiment of the present invention is described by targeting on the usage amount of the persistent storage area used by the application. As another exemplary embodiment the present invention can be applied to a usage amount other than the usage amount of the persistent storage area used by the application.

In the management information of the application file the usage amount of the resource in the image forming apparatus such as the usage amounts of the CPU and the memory can be declared. Further the installer service can acquire information about the target application installed according to an installation instruction from the application framework in addition to the usage amount of the persistent storage area used by the application.

For example the usage amounts of the CPU and the memory used by the application can be acquired. Based on the acquired information the flow of processing for the resource over illustrated in is performed to deal with the usage amounts of entire resources of the image forming apparatus such as the usage amounts of the persistent storage area the CPU and the memory.

Accordingly more accurate application control can be performed. Further such information pieces can be combined with each other. More specifically both the usage amounts of the persistent storage area and the memory can be confirmed by the processing. In such a case advanced control for stopping the operation of the application when any one of the usage amounts exceeds the declared amount can be performed and thus advanced application control can be performed.

In each exemplary embodiment of the present invention the image forming apparatus is described as the apparatus to which the present invention is applied. The image forming apparatus as illustrated in includes both the scanner unit and the printer unit and processes a job related to the image forming processing using one of or both of these image forming units.

However the image forming apparatus includes the apparatus provided with either one of the image forming units or the apparatus provided with the image forming unit of other type. Such an apparatus processes a job related to the image forming processing with use of the image forming unit provided therein. Further the present invention can be applied to an apparatus other than the image forming apparatus.

For example the present invention can be applied to smart phones personal computers and other apparatuses. In a case of such apparatuses a job is not always related to the image forming processing. Therefore the present invention can be applied to any type of jobs processed by the apparatus.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or an MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium . In such a case the system or apparatus and the recording medium where the program is stored are included as being within the scope of the present invention.

It will be understood that the present invention has been described above purely by way of example and modification of detail can be made within the scope of the invention. Each feature disclosed in the description and where appropriate the claims and drawings may be provided independently or in any appropriate combination.

This application claims priority from Japanese Patent Application No. 2012 006202 filed Jan. 16 2012 which is hereby incorporated by reference herein in its entirety.

