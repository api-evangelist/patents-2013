---

title: Image forming device, information processing method, and information processing program
abstract: In an image forming device which is capable of executing an application program, a plurality of interface providing units are arranged each providing the application program with an interface which enables the application program to use a function of the image forming device. A selecting unit selects at least one of the plurality of interface providing units as an object of use for the application program based on a result of comparison of information stored in a storage device and indicating an execution environment of each of the plurality of interface providing units with information stored in the storage device and indicating an execution environment of the image forming device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09645863&OS=09645863&RS=09645863
owner: RICOH COMPANY, LTD.
number: 09645863
owner_city: Tokyo
owner_country: JP
publication_date: 20130503
---
This application is a Continuation of U.S. application Ser. No. 12 108 804 filed Apr. 24 2008 which is based on and claims the benefit of priority of Japanese patent application No. 2007 120216 filed on Apr. 27 2007 and Japanese patent application No. 2008 078312 filed on Mar. 25 2008 the contents of which are incorporated herein by reference in their entirety.

This invention relates to an image forming device an information processing method and an information processing program which are capable of executing an application program.

In recent years there is an image forming device called a multi function peripheral which is provided with an API application programming interface for making use of functions of the image forming device. The image forming device is capable of executing an application program which was developed using the API. For example see Japanese Laid Open Patent Application No. 2005 269619.

Generally the functions of image forming device vary depending on the model of the image forming device. If the function difference is reflected in the API as it is the software developers have to develop application programs for every model. To avoid this abstract concepts of the functions of image forming device are expressed in the API in order to reduce the model dependency of the API and facilitate the deployment of application programs developed using the API to two or more models of image forming device.

However even if the function difference is absorbed in the API the difference in the execution environment exists apart from the function difference. For example the memory resources and CPU performance may vary depending on the model. And even if two image forming devices are of the same model they may differ in the number of application programs installed or the presence of add on memory.

Therefore in order to realize the maximum performance using the limited resources of the application incorporated system implementation of the logics in conformity with the actual execution environment is demanded for the module which is called through the API which module is called service module . A conceivable method of increasing the performance is to implement the logics in conformity with various execution environments in the same service module. However this method has the following problems.

First the program size of the service module is enlarged and the amount of the memory consumed at a time of loading the programs on the memory RAM is increased. Second the work area the heap area etc. that is not used actually is secured on the memory which may increase the amount of the memory consumed excessively.

These problems are very important for the image forming device in which several application programs are incorporated and the available memory space is more limited than a general purpose computer. For this reason it is desired to provide a plurality of service modules which provide the same function with the same API in accordance with the execution environment. However it is not desirable that the operator is caused to make a decision on which service module is suitable for the execution environment of the image forming device which will lower the ease of operation of the image forming device.

In one aspect of the invention the present disclosure provides an improved image forming device in which the above described problems are eliminated.

In one aspect of the invention the present disclosure provides an image forming device and an information processing method which enable an application program to use a suitable software module among a plurality of software modules which provide the functions used by the application program.

In an embodiment of the invention which solves or reduces one or more of the above mentioned problems the present disclosure provides an image forming device which is capable of executing an application program the image forming device comprising a plurality of interface providing units each providing the application program with an interface which enables the application program to use a function of the image forming device and a selecting unit selecting at least one of the plurality of interface providing units as an object of use for the application program based on a result of comparison of information stored in a storage device and indicating an execution environment of each of the plurality of interface providing units with information stored in the storage device and indicating an execution environment of the image forming device.

In an embodiment of the invention which solves or reduces one or more of the above mentioned problems the present disclosure provides an information processing method for use in an image forming device capable of executing an application program the information processing method comprising the steps of arranging a plurality of interface providing units each providing the application program with an interface which enables the application program to use a function of the image forming device and selecting at least one of the plurality of interface providing units as an object of use for the application program based on a result of comparison of information stored in a storage device and indicating an execution environment of each of the plurality of interface providing units with information stored in the storage device and indicating an execution environment of the image forming device.

According to the embodiments of the invention it is possible to provide an image forming device and an information processing method which enable an application program to use a suitable software module among a plurality of software modules which provide the functions used by the application program.

A description will be given of embodiments of the invention with reference to the accompanying drawings.

The controller includes a CPU a RAM a ROM and a HDD . In the ROM read only memory various kinds of programs and data used by the programs are stored. The RAM random access memory is used as a memory region for loading a program or a work area of the loaded program etc. The CPU central processing unit processes the program loaded on the RAM to realize the function which will be described later. The HDD hard disk drive is used as a storage region for storing the data such as image data which is generated by the execution of the program. In the HDD programs which may be installed or uninstalled and data used by the programs are also stored.

The scanner is the hardware for reading image data from a document. The printer is the hardware for printing image data on a copy sheet. The modem is the hardware for connecting the image forming device with a telephone line and this modem is used in order to perform the facsimile transmission and reception of image data via the telephone line.

The network interface is the hardware for connecting the image forming device with a network such as LAN local area network . The network may be a wireless communication network or a wired communication network.

The operation panel is the hardware which is provided with a set of buttons a liquid crystal panel etc. which is adapted for receiving the inputs from the user and for providing operational information to the user.

The OSGi open services gateway initiative platform is the standardized technology offered by the OSGi Alliance. The OSGi platform is a software platform which provides an execution environment for Java based software components software modules created based on the open software component technology. The Java based software is mounted in the form of software components called bundles on the OSGi platform . Each bundle is constituted by a single JAR Java archiver file and the respective bundles can be installed independently of each other.

The service module provides an interface API to which the function of the image forming device is abstracted. The service module is a bundle which provides the service of performing the function in response to a call of the interface. Two or more instances of the service module may exist in the image forming device depending on the content of the service to be provided the version of the service and an appropriate execution environment for example performance of the image forming device for the service. For example two or more service modules may exist in which the interfaces and the content of the services are shared or overlapped. As shown in a provision function information file and an execution condition file are provided in each of the service modules . In other words a provision function information file and an execution condition file are associated with each service module .

The provision function information file is a file in which the information provision function information for identifying the function provided by a corresponding service module is stored. is a diagram showing the composition of the provision function information.

As shown in the provision function information is classified in a hierarchical structure including major class middle class and minor class. As for the major class an identifier identification information of the function among the image forming device functions classified as major classes such as scan print fax etc which is provided by the corresponding service module is specified as the major class. As for the middle class the identifiers identification information of the functions considered the attributes of the major class function such as color monochrome applicable paper size etc. which are provided by the corresponding service module are specified as the middle class. The items functions which can be specified as the middle class may vary depending on the value which is specified as the major class. As for the minor class the identifiers identification information of the functions considered as more detailed attributes of the major class function such as resolution double sided printing etc. which are provided by the corresponding service module are specified as the minor class. The items functions which can be specified as the minor class may vary depending on the value which is specified as the major class or the middle class.

The execution condition file is a file in which the information execution condition information which describes the execution conditions of the service module is stored. is a diagram showing the composition of the execution condition information.

As shown in the execution condition information contains available memory space service modules to be executed concurrently CPU performance speed priority memory saving priority service module to be replaced etc.

The value of the available memory space which is required or recommended for performing the corresponding service module is specified as the available memory space. The identifiers or IDs of service modules which are to be executed concurrently with or in parallel with the corresponding service module are specified as the service modules to be executed concurrently. As for the CPU performance the recommended or minimum CPU performance clock speed etc. required to execute the corresponding service module is specified. As for the speed priority memory saving priority the information indicating whether the service module is created according to the speed priority scheme or according to the memory saving priority scheme is specified. For example when a service module which performs decompression editing and recompression of a compressed image as a scanning result is created according to the speed priority scheme a large amount of work memory is secured and a block processing of the image data of one page is performed collectively. On the other hand when a service module of the same type is created according to the memory saving priority scheme the image data of one page is divided into a set of image data portions and processing of each image data portion is performed individually. Thus depending on whether the speed priority scheme or the memory saving priority scheme is used the content substance of the service module which provides the same function varies in the logic. Taking into consideration the above mentioned situation the item of speed priority memory saving priority is provided in the execution condition information. As for the service module to be replaced the identifier or ID of the existing service module which is compulsorily replaced by the corresponding service module when the corresponding service module is installed is specified.

The provision function information file and the execution condition file are stored in the HDD when the service module is installed. Namely the provision function information file and the execution condition file are created concurrently with the time of creating the service module and these files are provided in the service module . Suppose that the file identifiers of the provision function information file and the execution condition file in this embodiment are arranged to include a specific ID in the following called assigned to the corresponding service module . In the following the specific ID assigned to the corresponding service module is called service ID . Accordingly in this embodiment the corresponding service module can be identified based on the file identifier namely based on the service ID contained in the file identifier .

The association between service module and service ID is stored in the HDD separately. The form of description of the provision function information and the execution condition information is not limited to a predetermined form. For example the provision function information and the execution condition information may be described in XML extensible markup language .

Referring back to the software composition of the image forming device will be described again. The application module is a bundle which constitutes an application program directly used by a user. In the following an application program may be also called an application. The application module uses the function of the image forming device through the interface provided by the service module in order to respond to the demand from the user. Two or more instances of the application module may exist in the image forming device depending on the kind of the application.

A use function information file is provided in each of the application modules . In other words a use function information file is associated with each application module .

The use function information file is a file in which the information use function information for identifying the function to be used by the corresponding application module is stored. The use function information is defined in the composition that is the same as that of the provision function information mentioned above. The items of the use function information correspond to those of the provision function information. Therefore the composition of the use function information in this embodiment is the same as shown in .

In the major class of the provision function information usually one function is specified. Namely one service module usually provides a single function considered as the major class. On the other hand in the major class of the use function information usually two or more functions may be specified. Namely one application module may use two or more functions considered as the major classes. When two or more major classes are specified the middle class is specified for every major class and the minor class is specified for every major class or middle class.

In order to allow the application module to use a pertinent service module the connection manager selects a service module which is suitable for the execution environment relevant to the application module and the image forming device based on the provision function information file the execution condition file and the use function information file . Then the connection manager performs the processing for allowing the application module to use the selected service module .

Specifically when two or more service modules which are relevant to the function being used by the application module exist a suitable service module is chosen from among the two or more service modules by the connection manager .

In the example shown in the connection manager chooses a scan service A or a scan service B in response to the scan function use request r and chooses a print service C or a print service D in response to the print function use request r. The scan service A and the scan service B are service modules which provide a scan function by using the same interface. The print service C and the print service D are service modules which provide a print function by using the same interface.

Next the process performed by the image forming device will be explained. is a diagram for explaining the process performed by an image forming device in an embodiment of the invention. In the elements which are the same as corresponding elements in are designated by the same reference numerals and a description thereof will be omitted.

As shown in registration of the provision function information stored in the provision function information file and the execution condition information stored in the execution condition file for each of the service modules into the connection manager is carried out beforehand for example at the time of installation steps S S . The registration in this case means that the connection manager is set in a state in which the connection manager is able to use the provision function information and the execution condition information.

For example the registration may be carried out by notifying the respective file identifiers of the provision function information file and the execution condition file in each of the service modules to the connection manager . This is because the connection manager is able to acquire and use the provision function information and the execution condition information based on the corresponding file identifiers.

Alternatively if a location for example a folder where the provision function information file and the execution condition file of each service module should be stored is recognized by the connection manager beforehand the step of storing the provision function information file and the execution condition file of each service module into the location may be performed instead of the above mentioned steps S S. This is because the connection manager is able to actively acquire and use the provision function information file and the execution condition file from the storage location.

When execution of the application module is requested by the input of the user through for example the operation panel S the application module notifies to the connection manager the storage location or file identifier of the use function information file provided therein or the use function information stored in the use function information file steps S and S .

In this case it is assumed that the scan function and the print function are included in the use function information of the application module as the major class functions. Therefore transmitting the above mentioned notification from the application module to the connection manager is equivalent to sending both the scan function use request S and the print function use request S to the connection manager .

The connection manager chooses one of the scan service A and the scan service B as the scan function being used and one of the print service C and the print service D as the print function being used based on the use function information of the application module the provision function information and the execution condition information of each service module . The selected service modules are loaded on the RAM and subsequently the processing is performed in accordance with various kinds of method calls from the application module

Next a description will be given of a service module selection process performed by the connection manager. is a flowchart for explaining a service module selection process performed by the connection manager .

In the service module selection process of when the use function information from the application module is received at the connection manager S the connection manager selects one major class in the use function information as an object of processing S .

Subsequently the connection manager compares the use function information concerning the major class including the functions indicated by the major class the functions indicated by the middle class belonging to the major class and the functions indicated by the minor class belonging to the major class with the provision function information of the respective service modules matching and searches any service modules which include the provision function information meeting the use function information concerning the major class namely the service modules can provide all the functions belonging to the major class S .

In this regard the provision function information meeting the use function information means that it includes all the functions specified as the use function information for all the hierarchical structure including the major class the middle class and the minor class. Exact matching between the provision function information and the use function information is also included.

Subsequently the connection manager determines whether the number of the searched service modules is one S . When the number of the searched results is one the connection manager selects the searched service module as an object of use and loads it on the RAM S .

On the other hand when there are a plurality of searched results at the determination of step S the connection manager compares the current execution environment the available memory space the information indicating the CPU performance with the execution condition information of each of the searched service modules the available memory space the information indicating the CPU performance and selects a service module which is most suitable for the current execution environment among the searched service modules S .

As for the service module in which the service ID is registered in the item of the service module to be replaced by other service modules it is omitted from the object of selection. Even if it is selected such a service module will be replaced by other service modules . Therefore even if the previous service module is not uninstalled the new service module is automatically selected as the object of use.

As for the item of the speed priority or memory saving priority in the execution condition information when the available memory space is smaller than a predetermined value a service module of memory saving priority is selected preferentially and when the available memory space exceeds the predetermined value a service module of speed priority is selected preferentially.

However if speed priority or memory saving priority is clearly specified to the connection manager by the application module the comparison of the item is performed based on the specification by the application module .

Subsequently the connection manager loads the selected service module on the RAM as an object of use S .

The processing of the steps S S is repeated until all the major classes included in the use function information are processed S . After all the major classes included in the use function information are processed the service module selection process of is terminated.

Alternatively another service module selection process as shown in may be performed instead of the process of . is a flowchart for explaining a service module selection process performed by the connection manager . In the steps which are the same as corresponding steps in are designated by the same reference numerals and a description thereof will be omitted.

In the service module selection process of the step S shown in is replaced by step S. In step S the connection manager selects preferentially a service module which execution condition information is indicated as being of memory saving priority.

Alternatively the step Smay be performed by comparing the available memory space in the execution condition information of each searched service module and selecting a service module which has the smallest value of the available memory space among the searched service modules or which has a small available memory space required or recommended to perform the service as an object of use.

In the service module selection process of the processing of additional steps S S indicated by the dotted line in is added after step S. In the step S shown in is omitted and therefore none of the service modules selected at the step is yet loaded on the RAM at the start point of step S.

In step S the connection manager computes a total value of the available memory spaces of the execution condition information for all the service modules selected as objects of use after the step S.

Subsequently the connection manager computes a difference between the available memory space in the current execution environment and the total value computed in the step S the available memory space of the current execution environment the computed total value of the available memory spaces S .

Subsequently the connection manager determines whether the difference is larger than a predetermined threshold S .

When the difference is larger than the threshold the connection manager determines whether the service module is specified as being of speed priority by the application module S .

When the service module is specified as being of speed priority the already selected service module is replaced by the service module of speed priority for the function in which the service module of speed priority exists such that the resulting memory space falls within the acceptable limits of the available memory space S . Namely the already selected service module is omitted from the object of use and the service module of speed priority is selected as an object of use.

Determination as to whether the resulting memory space is within the acceptable limits of the available memory space may be made before the replacement by comparing the available memory space in the execution condition information of the service module of speed priority and the available memory space in the current execution environment in the process of replacing the already selected service module by the service module of speed priority sequentially.

After the replacement is completed all the service modules selected as objects of use at this time are loaded on the RAM S .

On the other hand when it is determined at the step S that the difference is not larger than the threshold the connection manager performs processing in case of insufficient memory space S .

As shown in in step S the connection manager checks the service modules to be executed concurrently in the execution condition information of each service module selected as an object of use S . The connection manager classifies the service modules to be executed concurrently into groups S . The term concurrently means that the service modules are to be executed almost at the same timing or in parallel with each other. The application module may notify to the connection manager the service modules to be executed concurrently. For example the information indicating the service modules to be executed concurrently may be contained as a part of the use function information. In this case the service modules to be executed concurrently may not be contained in the execution condition information.

Subsequently the connection manager computes a total value of the available memory space in the execution condition information of the service modules for every group S .

Subsequently the connection manager determines a maximum of the total value of the available memory space among the groups by comparing the respective total values computed for the groups S .

Subsequently the connection manager computes a difference between the available memory space in the current execution environment and the maximum computed at the step S the available memory space the maximum S .

Then the connection manager determines whether the difference is larger than a predetermined threshold S .

When it is determined at the step S that the difference is larger than the threshold the connection manager performs the loading and unloading of service modules to the RAM for every group in accordance with the progress of the processing of the application module S .

Specifically when a function use request from the application module is received the connection manager loads a service module corresponding to the function concerning the use request and other service modules belonging to the group that is the same as that of the service module on the RAM . Each of the thus loaded service modules performs its processing. When the processing is completed and a timing at which the service module can be unloaded is reached the service module notifies the connection manager of the end of the processing. When the processing end notices from all the service modules belonging to the same group are received the connection manager unloads all the service modules belonging to the same group.

Repeating such processing enables the connection manager to validate execution of the application module while reducing the amount of the memory consumed at a time. The unloaded service module may be loaded again if needed when a function use request from the application module is received again.

On the other hand when it is determined at the step that the difference is not larger than the threshold the connection manager determines that execution of the application module is impossible S.

The threshold used at the step S of and the step S of means a margin or allowable value with respect to the amount of the memory used by the service module . It is not necessary that the threshold is always constant. Namely when the application module is performed actually not only the application module but also the service module uses the memory. Therefore it is preferred that the amount of the memory used by the application module be taken into consideration when performing the selection process of service module .

However the amount of the memory used by the application module varies depending not only on the specification of the application module but also on the actual operating condition. For example even when the same application module is executed the amount of the memory used in a case of scanning an A3 document at 600 dpi is different from the amount of the memory used in a case of scanning an A4 document at 200 dpi. Therefore the use of a fixed threshold in the service module selection process may cause a problem that the performance of the application module cannot be fully demonstrated.

In order to eliminate the problem the image forming device of the invention may be arranged so that the connection manager always measures the available memory space during execution of the application module and updates dynamically the threshold based on the result of the measurement.

The updating of the threshold may be performed at a timing that the threshold is used actually. In such a case it is not necessary to always measure the available memory space and the threshold may be updated based on the available memory space at the timing that the threshold is used.

Even when the connection manager determines that execution of the application module is possible an error of insufficient memory space may occur if a fixed threshold is used. However updating dynamically the threshold enables the value of the threshold to be increased in such a case. The margin of the memory amount for operation of the application module can be enlarged and occurrence of an error of insufficient memory space can be prevented.

When initiation of an application module is requested in the state where one or more application modules are already performed the process of may be performed again for the in progress application modules in order to change dynamically the service modules selected as objects of use by taking into consideration the amount of the memory resources used by the newly started application module .

Specifically when the connection manager determines during search of service modules corresponding to the newly started application that the available memory space is insufficient with any service module the connection manager selects a service module having a smaller memory consumption that is the value of the available memory space in the execution condition information is relatively small or a service module which is specified as of memory saving priority in the execution condition information and includes all the use functions of the in progress application modules as an object of use for the newly started application module. Accordingly it is possible for the thus modified image forming device to perform a plurality of application modules efficiently.

Meanwhile the provision function information the execution condition information and the use function information are not limited to the composition in the above described embodiment etc. . For example the provision function information and the execution condition information may be stored collectively as one information item which information will be called service module information in a single file having the following composition.

The provision function information contains a class and an attribute. The class denotes the class of function and is equivalent to the major class in the example of . The attribute corresponds to the middle class or the minor class in the example of but the composition of the attribute varies depending on the class.

The service module information of corresponds to a scan function and the scan is specified as the class. The attribute is constituted in accordance with the setup information of the scan function.

On the other hand the execution condition information in the service module information of contains a use memory and a performance.

The use memory corresponds to the available memory space in the example of . The performance is an index indicating the performance of a corresponding function scan function and the unit of the performance varies depending on a corresponding function. In a case of the scan function the number of scanned sheets per second is selected as the unit of the performance.

In correspondence to the above mentioned service module information the use function information associated with the application module may be arranged in the following composition. is a diagram showing an example of use function information.

In the example of the use function information includes a list of use functions a list of attribute items for every use function and a list of use attribute values for every attribute item. The class of functions used by a corresponding application module is indicated by the list of use functions. The attribute values used by a corresponding application module are indicated by the list of use attribute values.

Even in the case where the provision function information the execution condition information and the use function information are changed to the composition as shown in the process performed by the connection manager may be substantially the same as described above.

Namely what is necessary for the above mentioned case is just to change the loop process for all the major classes in the steps S S of or to the loop process for all the use functions in the use function information of . What is necessary is just to change the step S of or to the step which searches a service module which can respond to the use function and use attribute value specified in the use function information of based on the class and the attribute of the provision function information in the service module information of . What is necessary is just to change the step which uses the available memory space in to the step which uses the use memory in . Moreover what is necessary is just to change the step which uses the speed priority in to the step which uses the performance in .

For example when the process of is performed by using the service modules which meets the scan function requested by the application module are the service module with service ID 0x00010001 and the service module with service ID 0x00010002 S . In the step S in this case the service module of ID 0x00010002 which has a smaller memory usage is also selected. However if the available memory space has a margin and the step S is performed the service module of ID 0x00010001 with sufficient performance is finally selected as an object of use.

As mentioned above according to the image forming device in this embodiment the interface which is provided to the application module is the same but two or more service modules which are specialized for the execution environment are provided. The request from the application module the functions provided by the service modules and the situation of the execution environment are judged. And a suitable service module can be associated with the application module and therefore the application module is enabled to use the functions provided by the suitable service module .

In this case the service modules which are not used are not loaded on the RAM and the amount of the memory consumed at a time can be reduced.

If the need of acquiring a log of the application module arises from a viewpoint of security the outputting of the log is attained by replacing the service module by the service module which outputs a log without changing the application module .

The actual use state of the function provided by the service module may be used as a criterion of judgment for selecting the service module . Specifically the log use state log which is indicative of the use frequency of the function method actually used by the application module among the functions provided by the service module is stored in the HDD . The information recorded in the use state log may be a total value of the use frequency or an average of the number of uses over a fixed period of time.

When a multi function service module is installed but there are very few possibilities of using all the functions provided by the service module in a specific model or application module it shows that the memory resources are vainly used. In such a case the service module equivalent to the subset version of service module of a standard version in which only the specific function is mounted is installed and the provision function information is registered to the connection manager . If the connection manager determines the use state of the function method of the service module based on the use state log and determines that it is enough with the subset version or if the function concerning the provision function information in the subset version meets the use functions derived from the use state log the replacement of multi function service module by the subset version may be performed. In such a case the standard service module the full set version being replaced is not loaded on the RAM . However it exists in the ROM or the HDD . If using the function not included in the subset version is requested by the application module the subset version may be replaced again by the full set version at that time.

The selection process of service module may be performed by an external computer or external server which is connected to the image forming device via a network. is a sequence diagram for explaining the process performed by the connection manager when a service module selection process is performed by an external server.

With reference to suppose that the external server has a program which when executed by a CPU of the external server causes the CPU to perform the process of or and this program is stored in a HDD of the external server . Moreover suppose that the external server has the provision function information the execution condition information and the substance programs of various service modules which are stored in the HDD.

As shown in when the use function information from the application module is received at the connection manager S the connection manager transmits to the external server the device information relevant to the hardware resources CPU memory etc. of the image forming device required for the service module selection process and the information relevant to the current execution environment of the image forming device including the available memory space the service IDs of the already loaded service modules etc. S .

Then the external server performs the service module selection process the process of or based on the received information S .

Subsequently the external server returns the service IDs of the service modules which are selected as objects of use in the image forming device to the connection manager S .

If there are some service modules among the already loaded service modules which are no longer necessary after the new service modules selected as the objects of use are loaded onto the RAM the external server returns the service IDs of such service modules also to the connection manager .

Subsequently the external server transmits to the connection manager the substance of the new service modules selected as the objects of use S . Then the connection manager installs the received new service modules into the image forming device and stores them in the HDD .

Subsequently the connection manager unloads the service modules the service IDs of which were notified as being unnecessary S . Then the connection manager loads the new service modules which were selected as the objects of use and received in the step S on the RAM S .

According to such composition the necessary service modules from the external server are received at the connection manager at any time and it is not necessary that all the service modules are installed beforehand in the image forming device . Therefore it is possible to prevent the HDD or the ROM of the image forming device from running short of the available storage amount. Selection and loading of the service modules performed in cooperation with the external server is effective and allows the newest update of the service modules for the purpose of fault correction etc. to be received at the connection manager at any time.

The connection manager may be arranged so that after the function using process of the application module is completed the connection manager deletes from the HDD the service modules which were received in accordance with the function use request from the application module .

The present invention is not limited to the above described embodiments and variations and modifications may be made without departing from the scope of the present invention.

