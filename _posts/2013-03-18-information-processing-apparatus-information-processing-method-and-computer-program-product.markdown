---

title: Information processing apparatus, information processing method, and computer program product
abstract: An information processing apparatus is connectable to a plurality of devices of different types via a network. The information processing apparatus includes a receiving unit that receives, from the devices, management information of each of the devices in a data format corresponding to the respective devices; a first storage unit that stores therein a first conversion rule for converting the management information into manage information in a first common data format common to the devices; and a conversion unit that converts the management information thus received into management information in the first common data format based on the first conversion rule.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09306799&OS=09306799&RS=09306799
owner: RICOH COMPANY, LIMITED
number: 09306799
owner_city: Tokyo
owner_country: JP
publication_date: 20130318
---
The present application claims priority to and incorporates by reference the entire contents of Japanese Patent Application No. 2012 062845 filed in Japan on Mar. 19 2012 and Japanese Patent Application No. 2012 250680 filed in Japan on Nov. 14 2012.

The present invention relates to an information processing apparatus an information processing method and a computer program product.

Conventionally widely known are systems that remotely control various devices and systems that remotely manage various devices. Japanese Patent No. 4185661 for example discloses a method for readily setting and managing identification information of each device by using a home gateway to control various types of devices. Japanese Patent Application Laid open No. 2004 171277 discloses a method for managing a personal computer together with various devices by using a device monitoring managing server.

In the conventional technology however if a new type of device is added as a device to be managed it may possibly be difficult to support the device because of difference in a data format to be dealt with for example.

Therefore there is a need for an information processing apparatus and an information processing method that even if a new type of device is added as a device to be managed can readily support the device.

According to an embodiment there is provided an information processing apparatus connectable to a plurality of devices of different types via a network. The information processing apparatus includes a receiving unit that receives from the devices management information of each of the devices in a data format corresponding to the respective devices a first storage unit that stores therein a first conversion rule for converting the management information into manage information in a first common data format common to the devices and a conversion unit that converts the management information thus received into management information in the first common data format based on the first conversion rule.

According to another embodiment there is provided an information processing method performed in an information processing apparatus connectable to a plurality of devices of different types via a network. The information processing method includes receiving from the devices management information of each of the devices in a data format corresponding to the respective devices and converting based on a first conversion rule for converting the management information into manage information in a first common data format common to the devices the management information thus received into management information in the first common data format.

According to still another embodiment there is provided a computer program product including a non transitory computer readable medium having a computer readable program. The program causes a computer which is connectable to a plurality of devices of different types via a network to execute receiving from the devices management information of each of the devices in a data format corresponding to the respective devices and converting based on a first conversion rule for converting the management information into manage information in a first common data format common to the devices the management information thus received into management information in the first common data format.

The above and other objects features advantages and technical and industrial significance of this invention will be better understood by reading the following detailed description of presently preferred embodiments of the invention when considered in connection with the accompanying drawings.

The different types of devices are devices equipped with different functions. A function is a type of processing that can be performed by each device. Examples of the function include a function to transmit information of an image to be output and a function to input various types of information such as printing projection and display. The function is not limited to an input and output function of data. A function to change various types of setting information such as setting of a network is also included in the function for example.

As illustrated in the devices such as the projector and the MFP are present in a local network. The information processing apparatus is present in a public network . The operation terminal is present in a public network .

The multiple types of devices such as the projector and the MFP and the information processing apparatus can be connected via a network. The multiple types of devices such as the projector and the MFP and the operation terminal can be connected via a communication line such as a network. The information processing apparatus the operation terminal and the multiple types of devices such as the projector and the MFP can be connected via a network. Examples of the network include the Internet and a local area network LAN .

The MFP is an image forming apparatus equipped with at least two functions of a copying function a printing function a scanning function and a facsimile function. The projector is an apparatus having an image display function to project a still image and a moving image onto a projection plane such as a screen and a wall as video.

While the MFP and the projector are explained as examples of the multiple types of devices in the present embodiment the multiple types of devices are not limited thereto. The multiple types of devices may include an image forming apparatus other than an MFP such as a copier a scanner a printer and a facsimile and other information output devices e.g. a personal computer a mobile terminal such as a smartphone and a video conferencing system for example.

The operation terminal receives a device ID identification information for uniquely identifying a device to be a target of a processing request made by a user as well as an acquisition request for management information of the device identified by the device ID and transmits the device ID and the acquisition request for management information to the information processing apparatus . While a personal computer PC or a mobile terminal are used as the operation terminal for example the operation terminal is not limited thereto. The operation terminal transmits various types of information such as the device ID and the acquisition request for management information in a data format unique to the operation terminal .

The user interface hereinafter referred to as the UI displays various screens to the user and receives various operations from the user. In the present embodiment the UI displays an input screen that receives a device ID identification information of a device to be a target of a processing request made by the user and an acquisition request for management information of the device identified by the device ID to the user and receives the device ID and the acquisition request for management information with an operation performed by the user.

The device search unit searches for a device such as the projector and the MFP in the network and establishes an ad hoc network connection with the device thus searched for. Furthermore the device search unit requests the device with which the ad hoc network connection is established to transmit a device ID which is identification information for identifying a device and receives the device ID.

The performance requesting unit transmits an acquisition request in which a device ID is specified that is a device ID and an acquisition request for management information to the information processing apparatus .

When the devices such as the projector and the MFP receive a request for a device ID from the operation terminal the devices transmit their own device IDs to the operation terminal .

The information processing apparatus manages various devices connectable to the network of the information processing system. In the present embodiment the information processing apparatus receives a device ID and an acquisition request for management information from the operation terminal in the data format of the operation terminal . The information processing apparatus then transmits management information of the device identified by the device ID to the operation terminal in a first common data format common to the devices. Detailed description will be given later.

While examples of the information processing apparatus include a computer such as a server a work station and a PC an image forming apparatus such as an MFP and a copier an information projection apparatus such as a projector and a mobile terminal such as a mobile phone a personal data assistance PDA and a tablet terminal the information processing apparatus is not limited thereto.

The projector and the MFP serving as the different types of devices each perform functions such as an input function and an output function. Furthermore the projector and the MFP receive a request from the information processing apparatus and transmit management information to the information processing apparatus .

The management information includes identification information of each device and an actual value corresponding to a processing item that changes depending on usage of each device for example and varies depending on the type and the usage of each device. The management information will be described later in detail.

In the present embodiment both the projector and the MFP can be an input device and an output device.

As illustrated in the information processing apparatus includes a device management application a request receiving unit a device management unit a device search management unit a device operating unit a storage unit a first storage unit a receiving unit and a queue .

The information processing apparatus is divided into an upper layer and a lower layer by a boundary of an application programming interface hereinafter referred to as an API . The information processing apparatus has the device management application in the upper layer. Furthermore the information processing apparatus has the device management unit the device search management unit the device operating unit the storage unit the receiving unit and the queue in the lower layer below the boundary of API.

The device management application receives from the operation terminal an acquisition request in which a device ID is specified. In the present embodiment as described above the acquisition request includes a device ID identification information for uniquely identifying a device to be a target of a processing request made by the user and an acquisition request for management information of the device identified by the device ID.

The device management application uses the API to transmit the acquisition request in which the device ID is specified and which is received from the operation terminal to the device management unit as a processing request corresponding to the acquisition request. Furthermore the device management application receives management information which corresponds to the device identified by the device ID specified in the processing request and which is converted into the first common data format common to a plurality of devices as well as receives the device ID specified in the processing request from the device management unit . The device management application then transmits the management information in the first common data format thus received to the device identified by the device ID thus received.

The API can receive various requests such as an acquisition request from the device management application using a predefined function such as parameter specification. If the API receives an acquisition request by using the function the API issues a processing request for acquisition of management information of the device identified by the device ID specified in the acquisition request to the device management unit . Thus the device management application issues the processing request corresponding to the acquisition request received from the operation terminal to the device management unit via the API.

In other words the API and the layer lower than the API have a function to serve as a platform of processing for the device management application .

The API will now be described in detail. In the present embodiment an acquisition request function is provided as the API.

Therefore by calling the acquisition request function that specifies the input parameter the device management application issues a processing request corresponding to the acquisition request to the device management unit .

As described above the information processing apparatus includes the device management unit the device search management unit the device operating unit the storage unit the receiving unit and the queue in the lower layer below the boundary of API.

The receiving unit receives management information of each device from the various devices such as the projector and the MFP in a data format corresponding to each of the devices and stores the management information in the queue . The receiving unit functions as an interface which transmits and receives data between the information processing apparatus and each device and also functions as an API. Therefore if each device is compatible with the API of the receiving unit each device can transfer various data such as management information to the information processing apparatus . In other words each device can be managed by the information processing apparatus .

The receiving unit may receive the management information by acquiring management information of each device from the various devices such as the projector and the MFP in the data format corresponding to the respective devices a pull method or may receive the management information by means of transmission of the management information from the various devices such as the projector and the MFP a push method .

The management information in the data format of each device stored in the queue is read by the device management unit at predetermined time intervals and is stored in the storage unit .

The storage unit is a storage medium such as a hard disk drive HDD and a flash memory that stores therein various data.

In the present embodiment the storage unit stores therein the management information in the data format of each device acquired from each device a first conversion rule a model code database hereinafter referred to as a model code DB and a master database of management information of each device hereinafter referred to as a management information MDB for example.

The management information MDB is registered in the storage unit for each device when each device is connected to the information processing apparatus for the first time via the network. is a view for explaining an example of the management information MDB.

As illustrated in the management information MDB stores therein an information ID an item name a data type a unit the maximum value and the minimum value in a manner associated with one another. As illustrated in the information ID is information for uniquely identifying each item name. The item name is a name of a management item. Specifically the item name is an item name of each management item of a processing item unique to each device such as a device ID a product name a model code and a firmware version and of a processing item that changes depending on usage of each device such as time of use power consumption and a COreduction. In other word the management information MDB stores therein an information ID a data type a unit the maximum value and the minimum value for each processing item unique to each device and each processing item that changes depending on usage of each device.

The data type and the unit correspond to the data format of each device in the present embodiment. The data format is a data format unique to each device and a unit of each piece of data for example and is not limited to the data type and the unit.

The data type is a data format of data corresponding to each processing item received from a corresponding device. The unit is a unit of data corresponding to each processing item. The maximum value and the minimum value are the maximum value of a value corresponding to each processing item and the minimum value of the value respectively and are updated appropriately by processing performed by the device management unit which will be described later.

The management information MDB is registered in the storage unit every time a new device is connected to the information processing apparatus via the network.

The management information MDB may be registered in the storage unit for each device. In the present embodiment however an explanation will be made of the case where the management information MDB is registered in the storage unit for each model to which each device belongs.

The information ID corresponds to the information ID in the management information MDB illustrated in . In other words the management information in the data format of each device acquired from each device indicates an information ID of a processing item unique to each device and an actual value corresponding to the information ID and an information ID of a processing item that changes depending on usage of each device and an actual value corresponding to the information ID in the data format of each device.

As described above the management information in the data format of each device is stored in the queue in response to an acquisition request for management information issued from the information processing apparatus for example. Subsequently the management information is read by the device management unit at predetermined time intervals and is stored in the storage unit .

The first conversion rule is a conversion rule for converting management information in each data format of a plurality of different types of devices into management information in the data format common to these devices. is a view for explaining an example of the first conversion rule. As illustrated in the first conversion rule defines for each information ID of each processing item information indicating a first common data format that is a common data format corresponding to the processing item and information indicating a common unit that is a common unit corresponding to the processing item. The first conversion rule simply needs to be a conversion rule for converting management information in each data format of a plurality of different types of devices into management information in the first common data format common to these devices and is not limited to the aspect illustrated in .

Referring back to the device management unit manages each device connected to the network. The device management unit includes a management control unit a conversion unit and an information control unit .

The management control unit receives from the device management application via the API a processing request corresponding to an acquisition request in which a device ID is specified and which is received from the operation terminal . The management control unit then transmits the processing request thus received to the information control unit .

The information control unit reads management information in the data format of each device stored in the queue and stores the management information in the storage unit . At this time the information control unit issues a first conversion request to the conversion unit . The first conversion request is a signal for instructing to convert the management information in the data format of each device stored in the storage unit into management information in the first common data format based on the first conversion rule stored in the storage unit .

If no management information MDB corresponding to the device ID included in the processing request is stored in the storage unit the management control unit transmits a device search request for the device ID to a device search unit which will be described later of the device search management unit . The device search unit which will be described later transmits an acquisition request for the management information MDB to each of the devices connected to the network to acquire the management information MDB from each of the devices described later in detail . The device search unit then stores the management information MDB thus acquired in the storage unit .

If a first conversion request described later in detail is issued at predetermined time intervals or from the information control unit the conversion unit converts the management information in the data format of each device stored in the storage unit into management information in the first common data format based on the first conversion rule stored in the storage unit . The conversion unit then stores the management information in the first common data format thus converted in the storage unit in a manner associated with the device ID of each device.

In detail the conversion unit reads for each piece of management information of the same device ID the management information in the data format of each device stored in the storage unit . The conversion unit then reads the item name of the processing item identified by the information ID in each piece of the management information from the management information MDB corresponding to the model code or the device ID included in the management information. Subsequently the conversion unit calculates as an actual value corresponding to each processing item the sum of the values of the processing items that change depending on usage of the device that are time of use power consumption and a COreduction in the present embodiment among the values of the processing items included in the management information.

Furthermore the conversion unit reads the data format of the value corresponding to each processing item included in the management information in the data format of each device stored in the storage unit from the management information MDB. The conversion unit then converts the data format of the actual value corresponding to each processing item into the first common data format e.g. a common data format and a common unit of the corresponding processing item defined by the first conversion rule. In the same manner as described above the conversion unit converts the data format of the value corresponding to the information ID of the processing item unique to each device such as a device ID corresponding to the information ID included in the management information in the data format of each device into the first common data format of the corresponding processing item defined by the first conversion rule.

The conversion unit then registers the management information including an item name of a processing item unique to each device such as a device ID and the value corresponding to the processing item converted into the first common data format and an item name of a processing item that changes depending on usage of the device that is time of use power consumption or a COreduction in the present embodiment and the value corresponding to the processing item converted into the first common data format in the storage unit as the management information in the first common data format corresponding to the device ID in a manner associated with the device ID.

The conversion into the first common data format performed by the conversion unit may be performed at predetermined time intervals performed when the information control unit issues the first conversion request or performed every time management information is newly registered in the storage unit via the queue . In the present embodiment every time management information in the data format of each device is newly stored in the queue from each device via the receiving unit the information control unit registers the management information in the storage unit and issues the first conversion request to the conversion unit . Therefore in the present embodiment the latest management information in the first common data format is stored in the storage unit for each device ID.

The information control unit receives a processing request from the management control unit . The information control unit then reads management information in the first common data format corresponding to the device identified by the device ID specified in the processing request thus received from the storage unit and transmits the management information to the device management application via the management control unit . The management information in the first common data format is obtained by converting management information in the data format of each device into management information in the first common data format common to a plurality of devices by the conversion unit as described above.

The device management application transmits the management information in the first common data format received from the device management unit to the operation terminal that transmits the acquisition request corresponding thereto as described above.

Furthermore the information control unit reads the management information in the data format of each device stored in the queue and stores the management information in the storage unit . At this time the information control unit issues the first conversion request to the conversion unit .

The device search management unit searches for and manages devices connectable to the network in the information processing system. The device search management unit includes the device search unit and a capability management unit .

The device search unit transmits an acquisition request for management information to each device connected to the network at predetermined time intervals. The device search unit acquires from a device newly connected to the network a device ID of the device and stores the device ID in the storage unit . If a device search request of a device ID is received from the management control unit the device search unit transmits an acquisition request of the device ID and the management information MDB to each device connected to the network and acquires the device ID and the management information MDB from each device. The device search unit then registers the device ID and the management information MDB thus acquired in the storage unit .

The capability management unit is a storage medium such as an HDD and a flash memory that stores therein the management information in the data format of each device received from each device. The device operating unit performs control on each device.

An explanation will be made of management performed in the information processing system and the information processing apparatus with the configuration described above according to the present embodiment using a specific example.

While the explanation will be made using the projector as an example of the device connected to the network in the information processing system in the same applies to the case where another device is connected.

When the user operates a power switch of the projector which is not illustrated and power is supplied to the respective units included in the projector the projector comes into a state connected to the information processing apparatus via the network. The projector then transmits the device ID of the projector to the information processing apparatus Step S .

When the device search unit of the information processing apparatus receives the device ID the device search unit stores the device ID in the storage unit as an ID of a device being in a state connected to the network Step S .

Subsequently at the point of time where a value corresponding to each processing item in management information is changed or alternatively at predetermined time intervals the projector transmits management information of the projector in the data format of the projector to the information processing apparatus Step S . The management information is registered in the queue of the information processing apparatus .

The information control unit of the information processing apparatus acquires the management information in the data format of each device registered in the queue at predetermined time intervals Step S and Step S and stores the management information in the storage unit Step S .

If the information control unit stores new management information in the storage unit the information control unit transmits a first conversion request to the conversion unit Step S . The conversion unit that receives the first conversion request converts the management information in the data format of each device stored in the storage unit into management information in the first common data format based on the first conversion rule stored in the storage unit Step S Step S and Step S . The conversion unit then stores the management information in the first common data format thus converted in the storage unit in a manner associated with the device ID of the device Step S .

A new device may possibly be connected to the network in the information processing system. In this case no information on the device e.g. the management information MDB is registered in the information processing apparatus . Therefore the information processing system performs registration operation illustrated in Step S in .

In other words the device search unit of the information processing apparatus receives the device ID from the projector connected to the network at Step S and performs the operation at Step S. Subsequently the device search unit performs the operation at Step S.

The device search unit of the information processing apparatus performs registration confirmation for determining whether the device ID received at Step S has already been registered Step S . In the present embodiment the device search unit performs the registration confirmation by determining whether the device ID received at Step S is registered in the capability management unit Step SA and Step SB . The device search unit may perform the registration confirmation by determining whether the management information MDB corresponding to the device ID received at Step S is registered in the storage unit .

In the registration confirmation if the device search unit determines that the device ID received at Step S has already been registered the registration at Step S is terminated and the system control goes to Step S.

By contrast if the device search unit determines that the device ID received at Step S is not registered the system control goes to Step S. At Step S the device search unit transmits an acquisition request for management information MDB to the projector that is a device identified by the device ID received at Step S Step S .

The projector that receives the acquisition request for management information MDB transmits the management information MDB to the information processing apparatus Step S . The device search unit of the information processing apparatus that receives the management information MDB stores the management information MDB thus received in the capability management unit Step S . The capability management unit stores the management information MDB in the storage unit Step S .

By performing the registration operation Step S from Step S to Step S the device ID and the management information MDB of the device newly connected to the network are registered in the information processing apparatus .

Information notification in the management performed by the information processing apparatus will now be described specifically. is a sequence diagram of the information notification performed in the information processing system and the information processing apparatus according to the first embodiment.

An assumption is made that the user who carries the operation terminal is present near the projector serving as the device to be a target of a processing request for example and that the operation terminal desires to acquire the management information of the projector .

In this case the user acquires the device ID of the device to be a target of a processing request. In the present embodiment the user issues an operation instruction from the operation terminal to request the device ID of the projector from the projector serving as a device to be a target of the processing request Step S and Step S .

The user who carries the operation terminal does not necessarily acquire the device ID of a device to be a target of processing by the method described above. The user may acquire the device ID by visually checking the device ID on a display screen that displays the device ID of the projector or by visually checking the device ID written in a management sticker put on the housing of the projector for example.

Subsequently the operation terminal transmits the device ID thus received and an acquisition request for management information of the device identified by the device ID the projector in this example to the information processing apparatus Step S .

The device management application of the information processing apparatus that receives the acquisition request in which the device ID is specified uses the API to transmit a processing request corresponding to the acquisition request to the management control unit Step S .

The management control unit receives from the device management application via the API the processing request corresponding to the acquisition request in which the device ID is specified and which is received from the operation terminal . The management control unit then transmits the processing request thus received to the information control unit Step S .

The information control unit receives the processing request from the management control unit . The information control unit then reads management information in the first common data format corresponding to the device identified by the device ID specified in the processing request thus received from the storage unit Step S and Step S . The information control unit then transmits the management information in the first common data format thus read to the device management application via the management control unit Step S and Step S . The management information in the first common data format is information obtained by converting management information in the data format of each device into management information in the first common data format common to a plurality of devices by the conversion unit as described above.

The device management application transmits the management information in the first common data format received from the device management unit to the operation terminal that transmits the acquisition request corresponding thereto Step S .

As described above in the information processing apparatus according to the present embodiment the conversion unit converts the management information of each device received in the data format of each device from each device into management information in the first common data format based on the first conversion rule stored in the storage unit .

Thus if the information processing apparatus receives an acquisition request of the management information of each device from the operation terminal for example the information processing apparatus can transmit the management information in the first common data format to the operation terminal . Therefore even if a new type of device is added as a device to be managed the information processing apparatus according to the present embodiment can provide the management information of each device in a format common to a plurality of devices the first common data format .

Accordingly even if a new type of device is added as a device to be managed the information processing apparatus according to the present embodiment can readily support the device.

The device management application of the information processing apparatus according to the present embodiment uses the API to transmit an acquisition request in which the device ID is specified and which is received from the operation terminal to the device management unit as a processing request corresponding to the acquisition request. Furthermore the device management application receives management information that corresponds to the device identified by the device ID specified in the processing request and that is converted into the first common data format common to a plurality of devices and the device ID specified in the processing request from the device management unit . The device management application then transmits the management information in the first common data format thus received to the device identified by the device ID thus received.

Thus even if a device in a new data format is connected to the network the device management application can transmit the management information of the device to the operation terminal regardless of the data format of the device.

The device ID included in an acquisition request is not limited to one device ID and may be a plurality of device IDs. If an acquisition request includes a plurality of device IDs the information processing apparatus can provide management information corresponding to each of the device IDs included in the acquisition request in the first common data format to the operation terminal 

In the first embodiment the operation terminal transmits a device ID identification information for uniquely identifying a device to be a target of a processing request made by the user and an acquisition request for management information of the device identified by the device ID to the information processing apparatus information processing apparatus in the first embodiment . In a second embodiment the operation terminal transmits a device ID and a performance request to cause the device identified by the device ID to perform specific processing to an information processing apparatus.

As illustrated in the information processing apparatus includes a device management application a performing unit a device management unit a device operating unit a storage unit a first storage unit a receiving unit a queue a second storage unit and an API.

The information processing apparatus has the device management application in the upper layer above the boundary of API. Furthermore the information processing apparatus has the device management unit the device operating unit the storage unit the receiving unit and the queue in the lower layer below the boundary of API.

In addition to the functions in the first embodiment the device management application receives from the operation terminal a performance request in which a device ID is specified.

In other words the device management application receives from the operation terminal an acquisition request in which a device ID is specified or a performance request in which a device ID is specified. The operation performed when the device management application receives an acquisition request in which a device ID is specified is the same as that in the first embodiment.

The performance request in which a device ID is specified includes a device ID identification information of a device to be a target of a processing request made by the user and a performance request to cause the device identified by the device ID to perform specific processing.

The device management application uses the API to transmit the performance request in which the device ID is specified and which is received from the operation terminal to the device management unit as a processing request corresponding to the performance request.

Here the API in the information processing apparatus according to the second embodiment can receive various requests such as an acquisition request and a performance request issued from the device management application using a predefined function such as parameter specification in the same manner as in the first embodiment. If the API receives an acquisition request by using the function the API issues a processing request for acquisition of management information of the device ID specified in the acquisition request to the device management unit . Thus the device management application issues the processing request corresponding to the acquisition request received from the operation terminal to the device management unit via the API. This operation is the same as that in the first embodiment.

In addition if the API in the information processing apparatus according to the present embodiment receives a performance request by using the function the API issues a processing request for creation of processing performance information for causing the device identified by the device ID specified in the performance request to perform the processing specified in the performance request to the device management unit . Thus the device management application issues the processing request corresponding to the performance request received from the operation terminal to the device management unit via the API. The processing performance information will be described later in detail.

In addition to the acquisition request function described in the first embodiment a performance request function is provided as the API in the second embodiment. Because the acquisition request function is the same as that in the first embodiment the explanation thereof will be omitted.

Therefore by calling the performance request function that specifies the input parameter the device management application issues a processing request corresponding to the performance request to the device management unit .

The queue is a FIFO queue and is generated on a storage medium such as a memory. In the same manner as in the first embodiment the queue stores therein management information in the data format of each device. The management information in the data format of each device is read by the device management unit at predetermined time intervals and is stored in the storage unit in the same manner as in the first embodiment.

In the present embodiment the queue further stores therein processing performance information described later in detail created by the device management unit based on the performance request specified by the processing request in a manner associated with a device ID of a device to be caused to perform the processing based on the processing performance information.

Each device such as the projector and the MFP connected to the network checks the queue at predetermined time intervals. If processing performance information corresponding to its own device ID is stored in the queue each device reads the processing performance information corresponding to its own device ID and performs processing specified in the processing performance information.

The storage unit is a storage medium such as an HDD and a flash memory that stores therein various data.

In the same manner as in the first embodiment the storage unit stores therein management information in the data format of each device acquired from each device a first conversion rule a model code database hereinafter referred to as a model code DB and a master database of management information of each device hereinafter referred to as a management information MDB for example.

The storage unit further stores therein a command management master database of each device hereinafter referred to as a command management MDB and a command database of each device hereinafter referred to as a command DB .

The command management MDB is registered in the storage unit for each device when each device is connected to the information processing apparatus for the first time via the network. By including the registration contents of the command management MDB in the management information MDB the command management MDB may be registered in the storage unit in a manner included in the management information MDB.

The command for performing processing in each device include a change of various settings such as a network setting new registration of various data printing projection and reading of an image however the command is not limited thereto.

The command DB is registered in the storage unit for each device when each device is connected to the information processing apparatus for the first time via the network. By including the registration contents of the command DB in the management information MDB the command DB may be registered in the storage unit in a manner included in the management information MDB.

Referring back to the device management unit manages each device connected to the network. The device management unit includes a management control unit a conversion unit and an information control unit . The conversion unit is the same as that in the first embodiment.

The management control unit receives from the device management application via the API a processing request corresponding to an acquisition request in which a device ID is specified and which is received from the operation terminal . The management control unit then transmits the processing request thus received to the information control unit . This operation is the same as that in the first embodiment.

In the present embodiment the management control unit further receives from the device management application via the API a processing request corresponding to a performance request in which a device ID is specified and which is received from the operation terminal . The management control unit then transmits the processing request thus received to the information control unit .

The information control unit receives a processing request from the management control unit . If the processing request thus received is a processing request corresponding to an acquisition request the information control unit reads management information in the first common data format corresponding to the device identified by the device ID specified in the processing request from the storage unit and transmits the management information to the device management application via the management control unit in the same manner as in the first embodiment. By reading a parameter included in the processing request thus received the information control unit determines that the processing request thus received is a processing request corresponding to an acquisition request.

In this case the device management application transmits the management information in the first common data format received from the device management unit to the operation terminal that transmits the acquisition request corresponding thereto.

Furthermore in the same manner as in the first embodiment the information control unit reads the management information in the data format of each device stored in the queue and stores the management information in the storage unit . At this time the information control unit issues the first conversion request to the conversion unit as described above.

By contrast if the processing request received from the management control unit is a processing request corresponding to a performance request the information control unit creates processing performance information based on the performance request specified by the processing request and stores the processing performance information in the queue .

If the processing request received from the management control unit is a processing request corresponding to a performance request the creating unit creates processing performance information based on the performance request specified by the processing request. By reading a parameter included in the processing request thus received the creating unit determines that the processing request thus received is a processing request corresponding to a performance request.

The processing performance information is information including a command for causing each device of the device ID specified in the processing request to perform specific processing to be performed that is specified in the processing request and including a parameter.

The creating unit reads the command management MDB and the command DB corresponding to the device ID specified in the processing request from the storage unit . At this time if a plurality of device IDs are specified in the processing request the creating unit reads the command management MDB and the command DB corresponding to each of the device IDs from the storage unit .

The creating unit then reads a command corresponding to the processing to be performed that is specified in the processing request and a data type corresponding to the command ID of the command for each device ID thus specified. Subsequently the creating unit creates processing performance information including the command corresponding to the processing to be performed that is specified in the processing request and a parameter obtained by converting the parameter corresponding to the processing specified in the processing request into the data type thus read for each device ID.

The creating unit creates the processing performance information for each device ID specified in the processing request and stores the processing performance information in the queue in a manner associated with the device ID corresponding thereto. Instead of the command included in the processing performance information a command ID may be used. In this case each device stores therein information indicating a command corresponding to the command ID in advance.

Each device such as the projector and the MFP connected to the network checks the queue at predetermined time intervals. If processing performance information corresponding to its own device ID is stored in the queue each device reads the processing performance information corresponding to its own device ID and performs the processing specified in the processing performance information.

An explanation will be made of management performed by the information processing apparatus with the configuration described above according to the present embodiment using a specific example.

Memory conversion in the management is the same as that in the first embodiment refer to . The memory conversion in the second embodiment is different from that in the first embodiment in that when the management information MDB is registered the command management MDB and the command DB are also received from the device and registered in the storage unit .

Furthermore information notification in the management is the same as that in the first embodiment refer to .

Device control in the management performed by the information processing apparatus will be described below. is a sequence diagram of the device control performed in the information processing system and the information processing apparatus according to the present embodiment.

An assumption is made that the user who carries the operation terminal desires to issue a performance request for specific processing to one or each of a plurality of devices for example.

In this case the user acquires the device ID of the device to be a target of the processing request. In the present embodiment the user issues an operation instruction using the operation terminal to request the device ID of the projector to the projector to be the target of the processing request and receives the device ID Step S and Step S .

Similarly to the first embodiment the user who carries the operation terminal does not necessarily acquire the device ID of the device to be the target of the processing by the method described above.

Subsequently the operation terminal transmits the device ID of the device to be the target of the processing and a performance request for causing the device identified by the device ID the projector in this example to perform the specific processing to the information processing apparatus Step S .

The device management application of the information processing apparatus that receives the performance request in which the device ID is specified uses the API to transmit a processing request corresponding to the performance request to the management control unit Step S .

The management control unit receives from the device management application via the API the processing request corresponding to the performance request in which the device ID is specified and which is received from the operation terminal . The management control unit then transmits the processing request thus received to the information control unit Step S .

The creating unit of the information control unit receives the processing request from the management control unit . The information control unit then reads for each device ID specified in the processing request thus received a command corresponding to a function specified in the processing request and a data type corresponding to the command ID of the command corresponding to the device ID from the storage unit Step S and Step S .

The creating unit then creates processing performance information including the command or the command ID corresponding to the function to be performed that is specified in the processing request and a parameter that corresponds to the function specified in the processing request and is converted into the data type corresponding to the command ID for each device ID thus specified Step S .

Subsequently the creating unit stores the processing performance information thus created in the queue in a manner associated with the device ID corresponding thereto Step S .

Each device connected to the network performs read processing for reading the processing performance information from the queue at predetermined time intervals Step S .

In more detail the projector which is an example of each device reads the processing performance information corresponding to the device ID of the projector Step S and Step S . If no processing performance information corresponding to the device ID is stored in the queue the read processing at Step S is terminated.

In accordance with the command included in the processing performance information thus read the projector performs the corresponding processing Step S .

An assumption is made that the operation terminal transmits a plurality of device IDs of devices connected to the information processing system and a performance request for causing the devices of the device IDs to change the network setting to a certain parameter to the information processing apparatus as a performance request for example.

In this case the information processing apparatus creates processing performance information including a command or a command ID for causing the device identified by each device ID specified in the performance request to change the network setting to the parameter specified in the performance request and including a parameter and stores the processing performance information in the queue . Each device connected to the network performs the processing in accordance with the command included in the processing performance information corresponding to its own device ID stored in the queue thereby changing the network setting to the parameter specified in the performance request.

As described above in the information processing apparatus according to the present embodiment if a processing request received from the operation terminal is a performance request the creating unit creates processing performance information based on the performance request specified by the processing request. The processing performance information is information including a command or a command ID for causing each device of the device ID specified in the processing request to perform a function to be performed that is specified in the processing request and including a parameter. Each command and each parameter are commands that can be performed by each device identified by each device ID and are in the data format of each device.

Therefore by accessing the queue of the information processing apparatus and performing the processing specified in the processing performance information corresponding to each device stored in the queue each device connected to the network can perform the processing specified by the user.

Accordingly even if a new type of device is added as a device to be managed the information processing apparatus according to the present embodiment can readily support the device.

In the first embodiment the operation terminal transmits a device ID identification information for uniquely identifying a device to be a target of a processing request made by the user and an acquisition request for management information of the device identified by the device ID to the information processing apparatus information processing apparatus in the first embodiment . In a third embodiment the operation terminal transmits a history acquisition request to an information processing apparatus.

As illustrated in the information processing apparatus A includes a device management application A a performing unit a device management unit A a device operating unit a storage unit A a first storage unit a receiving unit A a queue A and an API.

The information processing apparatus A has the device management application A in the upper layer above the boundary of API. Furthermore the information processing apparatus A has the device management unit A the device operating unit the storage unit A the receiving unit A and the queue A in the lower layer below the boundary of API. The device operating unit and a device search management unit are the same as those in the first embodiment.

In addition to the functions in the first embodiment the device management application receives a history acquisition request from the operation terminal . In other words the device management application A receives an acquisition request in which a device ID is specified or a history acquisition request.

The device management application A may further receive a performance request in which a device ID is specified from the operation terminal in the same manner as in the second embodiment. The processing performed when the device management application A receives an acquisition request in which a device ID is specified is the same as that in the first embodiment. Furthermore the processing performed when the device management application A receives a performance request in which a device ID is specified is the same as that in the second embodiment.

Each device connectable to the information processing apparatus A creates processing history information. The processing history information created by each device includes histories of a plurality of types of processing. While examples of the processing include acquisition of a specific file and processing that can be performed by each device e.g. printing display and error restoration the processing is not limited thereto.

The history acquisition request is an acquisition request for processing history information of each device. In the present embodiment an explanation will be made of the case where the history acquisition request is an acquisition request for a processing result of a specific item included in a history of specific processing among pieces of processing history information in each device.

Specifically the history acquisition information includes specification information for specifying processing to be acquired identification information of an item to be acquired hereinafter also referred to as an item name and an acquisition request of a record content corresponding to the item identified by the item name. The specification information simply needs to be information that can specify the processing to be acquired.

The device management application A uses the API to transmit a history acquisition request to the device management unit A as a processing request corresponding to the history acquisition request.

The API in the information processing apparatus A according to the third embodiment can receive various requests such as a history acquisition request an acquisition request and a performance request issued from the device management application A using a predefined function such as parameter specification in the same manner as in the first embodiment.

If the API receives an acquisition request by using the function the API issues a processing request for acquisition of management information for the device ID specified in the acquisition request to the device management unit A. Thus the device management application A issues the processing request corresponding to the acquisition request received from the operation terminal to the device management unit A via the API. This operation is the same as that in the first embodiment.

If the API receives a performance request by using the function the API issues a processing request for creation of processing performance information for causing the device of the device ID specified in the performance request to perform the processing specified in the performance request to the device management unit A. Thus the device management application A issues the processing request corresponding to the performance request received from the operation terminal to the device management unit A via the API. This operation is the same as that in the second embodiment.

If the API receives a history acquisition request by using the function the API issues a history processing request corresponding to the history acquisition request in the processing history information acquired from each device to the device management unit A. Thus the device management application A issues the history processing request corresponding to the history acquisition request received from the operation terminal to the device management unit A via the API.

In addition to the acquisition request function described in the first embodiment and the performance request function described in the second embodiment a history acquisition request function is provided as the API in the third embodiment. Because the acquisition request function is the same as that in the first embodiment and the performance request function is the same as that in the second embodiment the explanations thereof will be omitted.

Parameter including an acquisition request for a record content corresponding to the item identified by the item name included in the history of the processing specified by the specification information in the processing history information acquired from each device 

Therefore by calling the history acquisition request function that specifies the input parameter the device management application A issues a history processing request corresponding to the history acquisition request to the device management unit A.

The queue A is a FIFO queue and is generated on a storage medium such as a memory. In the same manner as in the first embodiment the queue A stores therein management information in the data format of each device. The management information in the data format of each device is read by the device management unit A at predetermined time intervals and is stored in the storage unit A in the same manner as in the first embodiment.

The queue A further stores therein processing performance information created by the device management unit A based on the performance request specified by the processing request in a manner associated with a device ID of a device to be caused to perform processing based on the processing performance information. Because the processing performance information is the same as that in the second embodiment the detailed explanation thereof will be omitted.

In the present embodiment the queue A further stores therein processing history information in the data format of each device. The processing history information in the data format of each device is read by the device management unit A at predetermined time intervals and is stored in the storage unit A.

The management information in the data format of each device and the processing history information in the data format of each device stored in the queue A may be read and stored in the storage unit A when the device management unit A uses each piece of the information to perform the corresponding processing.

Every time the processing history information is updated in each device each device such as the projector and the MFP connected to the network transmits the processing history information in the data format of each device thus updated to the information processing apparatus A. The information processing apparatus A that receives the processing history information in the data format of each device from each device stores the processing history information thus received in the queue A.

When the processing history information is updated in each device each device may transmit the history of processing thus updated alone to the information processing apparatus A.

In the same manner as in the second embodiment each device checks the queue A at predetermined time intervals. If processing performance information corresponding to its own device ID is stored in the queue A each device reads the processing performance information corresponding to its own device ID and performs the processing specified in the processing performance information.

The storage unit A is a storage medium such as an HDD and a flash memory that stores therein various data.

In the same manner as in the first embodiment the storage unit A stores therein management information in the data format of each device acquired from each device a first conversion rule a model code DB and a management information MDB of each device for example. Furthermore in the same manner as in the second embodiment the storage unit A stores therein a command management MDB of each device and a command DB of each device.

In the present embodiment the storage unit A further stores therein processing history information in the data format of each device acquired from each device a log definition database hereinafter referred to as a log definition DB a converted database hereinafter referred to as a converted DB and a second conversion rule for example.

Each piece of device history information is stored in the storage unit A in a manner associated with a device ID. The processing history information illustrated in is stored in a manner associated with a device ID MFP indicating an MFP for example. The processing history information illustrated in is stored in a manner associated with a device ID projector indicating a projector . Similarly the processing history information illustrated in is stored in a manner associated with a device ID TV conference terminal indicating a TV conference terminal .

As described above the processing history information is information indicating a history of processing performed by each device. The processing history information is information indicating a record content corresponding to an item in accordance with a definition schema predetermined for each device or for each model in a description form e.g. a data format and a unit predetermined by the definition for the corresponding processing thus performed. Specifically the data format of each device in the processing history information indicates an item name determined for each device and a description form of a record content corresponding to the item identified by the item name. In other words the processing history information is a data format corresponding to each device or each model and may be different from one another.

While examples of the item recorded in the processing history information include a processing date and time a processing state status a processing method a processing content data stored area a processing result and processing time the item is not limited thereto. Furthermore an arbitrary format is determined for the format and the unit of the record content corresponding to each item for each device. In the present embodiment an explanation will be made of the case where the processing content which is an example of the item is used as specification information for specifying processing to be acquired.

As illustrated in when each device acquires the data sample data stored in the information processing apparatus A data formats of the processing history information recorded by each device are different from one another.

Specifically as illustrated in the record contents e.g. formats and units corresponding to the definitions of the item name or the item identified by the item name are different from one another. The processing history information illustrated in for example indicates the processing time required for acquiring the data sample data on the information processing apparatus A by microseconds. In the example of the processing time is 3098.832 microseconds. In the example of no item name of the processing time is provided and the processing time is indicated at the end of the processing history.

By contrast the processing history information illustrated in indicates the processing time required for acquiring the data sample data on the information processing apparatus A by milliseconds. In the example of the processing time is 4.075 milliseconds. In the present embodiment the item name of the item indicating the processing time is represented as total runtime in the projector. Similarly the processing history information illustrated in indicates the processing time required for acquiring the data sample data on the information processing apparatus A by milliseconds. In the example of the processing time is 3.999 milliseconds. In the present embodiment the item name of the item indicating the processing time is represented as total in the TV conference terminal.

The log definition is a log definition schema of a device ID corresponding thereto. In the present embodiment the log definition is a data structure of the processing history information of the device identified by the device ID corresponding thereto. Specifically the log definition defines the item name of an item recorded as the processing history information of the device identified by the device ID corresponding thereto and the data format and the unit for example of the record content corresponding to the item specified by each item name in order of being recorded in the processing history information.

The second conversion rule is a conversion rule for converting the data formats of the processing history information of a plurality of different types of devices into a second common data format serving as a data format common to these devices.

As illustrated in the second conversion rule is a table that stores therein a common item name a device ID and an item name corresponding to the processing history information in the data format of each device in a manner associated with one another.

In the present embodiment for example the second conversion rule defines totalTime as a common item name indicating the processing time as illustrated in . Furthermore in the second conversion rule ResponseTime is associated with the device ID MFP total runtime is associated with the device ID projector and total is associated with the device ID TV conference terminal as a corresponding item name in the processing history information of each device corresponding to the common item name totalTime . Similarly in the second conversion rule the common item name the device ID and the corresponding item name in the processing history information in the data format of each device are associated with one another for the other items included in the processing history information.

The second conversion rule simply needs to be a conversion rule for converting the data formats of the processing history information of a plurality of different types of devices into the second common data format and is not limited to the aspect illustrated in . The second conversion rule is created in the information processing apparatus A and is stored in the storage unit A in advance.

Referring back to the device management unit A manages each device connected to the network. The device management unit A includes a management control unit A a conversion unit A and an information control unit A.

The management control unit A receives from the device management application A via the API a processing request corresponding to an acquisition request in which a device ID is specified and which is received from the operation terminal . The management control unit A then transmits the processing request thus received to the information control unit A. This processing is the same as that performed by the management control unit in the first embodiment. Similarly to the management control unit in the first embodiment if no management information MDB corresponding to the device ID included in the processing request is stored in the storage unit A the management control unit A transmits a device search request for the device ID to a device search unit of the device search management unit .

In the present embodiment the management control unit A further receives from the device management application A via the API a processing request corresponding to a history acquisition request received from the operation terminal . The management control unit A then transmits the processing request thus received to the information control unit A.

The information control unit A reads processing history information in the data format of each device stored in the queue A and stores the processing history information in the storage unit A. If new processing history information is stored in the storage unit A the information control unit A transmits a converted DB creation request described later in detail to the conversion unit A. Furthermore if a history processing request is received from the management control unit A the information control unit A issues a second conversion request to the conversion unit A.

The second conversion request is information for instructing to convert the processing history information in the data format of each device into processing history information in the second common data format based on the second conversion rule.

In the present embodiment the second conversion request includes specification information for specifying processing to be acquired in the history processing request corresponding to the history acquisition request received from the operation terminal identification information of an item to be acquired item name and an acquisition request for a record content corresponding to the item identified by the item name.

The conversion unit A receives the converted DB creation request and the second conversion request from the information control unit A.

The changed DB creation will now be described. If the converted DB creation request is received at predetermined time intervals or from the information control unit A the conversion unit A performs the converted DB creation. The converted DB creation is processing for creating a converted DB for each device. The converted DB is a table that stores therein a record content corresponding to each item included in the processing history information in the data format of each device in a manner associated with the item name defined in the data format of the processing history information of each device.

In more detail the conversion unit A reads the log definition DB corresponding to each device ID and the processing history information in the data format of each device corresponding to each device ID stored in the storage unit A.

The conversion unit A then creates the converted DB for each device ID. In more detail the conversion unit A reads the item name specified in the log definition DB for each device ID. Subsequently by associating the item name thus read with the record content corresponding to the item identified by the item name in the processing history information in the data format of each device the conversion unit A creates the converted DB corresponding to each device ID.

Similarly by associating the record content corresponding to each item indicated in the processing history information corresponding to the device ID MFP illustrated in with the item name corresponding to the record content in the log definition corresponding to the device ID MFP illustrated in for example the conversion unit A creates the converted DB illustrated in .

By associating the record content corresponding to each item indicated in the processing history information corresponding to the device ID projector illustrated in with the corresponding item name indicated in the log definition corresponding to the device ID projector illustrated in for example the conversion unit A creates the converted DB illustrated in .

Similarly by associating the record content corresponding to each item indicated in the processing history information corresponding to the device ID TV conference terminal illustrated in with the corresponding item name indicated in the log definition corresponding to the device ID TV conference terminal illustrated in for example the conversion unit A creates the converted DB illustrated in .

If the second conversion request is received the conversion unit A performs the conversion. The conversion is processing for converting the processing history information in the data format of each device into processing history information in the second common data format common to each device based on the second conversion request and the second conversion rule.

In the present embodiment the conversion unit A reads a history of processing specified by the specification information designated in the second conversion request in the processing history information in the data format of each device. The conversion unit A then reads a record content corresponding to the item identified by the item name specified in the second conversion request included in the history of processing of each device thus read. With this processing the conversion unit A reads the record content of specific processing specified by the second conversion request from the processing history information of each device in different data formats. The conversion unit A then transmits the processing history information including the record content thus read to the information control unit A as the processing history information in the second common data format common to a plurality of devices.

In more detail the conversion unit A extracts a history of processing specified by the specification information designated in the second conversion request.

An assumption is made that the specification information designated in the second conversion request is URI sample data for example. In this case the conversion unit A reads the common item name corresponding to the item name URI included in the specification information from the second conversion rule refer to . If the item name included in the specification information is defined as the common item name in the second conversion rule the conversion unit A reads the common item name. In the present embodiment the conversion unit A reads URI as the common item name for example.

The conversion unit A then reads the item name for each device corresponding to the common item name thus read from the second conversion rule.

Specifically the conversion unit A reads Location for the device ID MFP path for the device ID projector and URI for the device ID TV conference terminal as the item name of each device ID corresponding to the common item name URI .

Subsequently the conversion unit A reads a converted DB including the item name of each device ID corresponding to the common item name URI specified by the specification information designated in the second conversion request and the record content sample data included in the specification information among the converted DBs corresponding to each device ID. Thus the conversion unit A extracts the history of processing specified by the specification information designated in the second conversion request.

In the present embodiment the conversion unit A reads a converted DB including the item name Location corresponding to the common item name URI and the record content sample data for the device ID MFP refer to .

The conversion unit A reads a converted DB including the item name path corresponding to the common item name URI and the record content sample data for the device ID projector refer to .

The conversion unit A reads a converted DB including the item name URI corresponding to the common item name URI and the record content sample data for the device ID TV conference terminal refer to .

Subsequently the conversion unit A reads the record content corresponding to the item name of the item to be acquired that is designated in the second conversion request from the history of processing specified by the specification information designated in the second conversion request.

In more detail the conversion unit A reads the common item name corresponding to the item name totalTime of the item to be acquired that is designated in the second conversion request from the second conversion rule Refer to . If the item name designated in the second conversion request is defined as the common item name in the second conversion rule the conversion unit A reads the common item name. In the present embodiment the conversion unit A reads totalTime as the common item name corresponding to the item name totalTime of the item to be acquired that is designated in the second conversion request.

The conversion unit A then reads the item name in each device corresponding to the common item name thus read from the second conversion rule Refer to .

Specifically the conversion unit A reads the item name ResponseTime for the device ID MFP the item name total runtime for the device ID projector and the item name total for the device ID TV conference terminal as the item name of each device ID corresponding to the common item name totalTime .

The conversion unit A then reads the record content corresponding to the item name of each device thus read from the converted DB.

Specifically the conversion unit A reads 3098.832 which is the record content corresponding to the item name ResponseTime from the converted DB corresponding to the device ID MFP illustrated in . The conversion unit A reads 4.075 which is the record content corresponding to the item name total runtime from the converted DB corresponding to the device ID projector illustrated in . The conversion unit A reads 3.999 which is the record content corresponding to the item name total from the converted DB corresponding to the device ID TV conference terminal illustrated in .

If the units of the record contents to be acquired are different the conversion unit A makes the units consistent. Whether the units are different may be determined by reading the log definition refer to corresponding to each device ID and determining the units corresponding to the item names of the record contents thus acquired.

The conversion unit A then transmits information including the specification information designated in the second conversion request the identification information of the item to be acquired the record content thus read and the device ID of the device corresponding to the record content to the information control unit A as the processing history information in the second common data format.

As described above the conversion unit A extracts the record content corresponding to the item name of the item to be acquired that is designated in the second conversion request from the processing history information in the data format of each device based on the second conversion rule. Thus the conversion unit A creates processing history information in the second common data format common to a plurality of devices and transmits the processing history information to the information control unit A.

After issuing the second conversion request to the conversion unit A if the information control unit A receives processing history information in the second common data format from the conversion unit A the information control unit A transmits the processing history information in the second common data format thus received to the management control unit A.

The management control unit A transmits the processing history information in the second common data format to the device management application A. The device management application A transmits the processing history information in the second common data format received from the device management unit A to the operation terminal that transmits the history acquisition request corresponding thereto.

An explanation will be made of management performed in the information processing system and the information processing apparatus A with the configuration described above according to the present embodiment using a specific example.

While the explanation will be made using the projector as an example of the device connected to the network in the information processing system in the same applies to the case where another device is connected.

If the user operates a power switch of the projector which is not illustrated and power is supplied to each unit of the projector the projector comes into a state connected to the information processing apparatus A via the network. The projector then transmits the device ID of the projector to the information processing apparatus A Step S .

If the device search unit of the information processing apparatus A receives the device ID the device search unit stores the device ID in the storage unit A as an ID of a device in a state connected to the network Step S . This operation is the same as that in the first embodiment.

Subsequently at predetermined time intervals or every time processing history information is updated the projector transmits the processing history information in the data format of the projector to the information processing apparatus A Step S . The processing history information is registered in the queue A of the information processing apparatus A.

The information control unit A of the information processing apparatus A acquires the processing history information in the data format of each device registered in the queue A at predetermined time intervals Step S and Step S and stores the processing history information in the storage unit A Step S .

If the information control unit A stores new processing history information in the storage unit A the information control unit A transmits a converted DB creation request to the conversion unit A Step S .

The conversion unit A that receives the converted DB creation request reads the log definition DB corresponding to each device ID and the processing history information in the data format of each device corresponding to each device ID stored in the storage unit A Step S and Step S .

The conversion unit A then creates the converted DB for each device ID Step S . Subsequently the conversion unit A stores the converted DB thus created in the storage unit A in a manner associated with each device ID Step S .

History information notification processing performed by the information processing apparatus A will now be described specifically. is a sequence diagram of history acquisition performed in the information processing system and the information processing apparatus A according to the present embodiment.

An assumption is made that the user issues an operation instruction to transmit a history acquisition request from the operation terminal to the information processing apparatus A Step S . The device management application A of the information processing apparatus A uses the API to transmit a history processing request corresponding to the history acquisition request to the management control unit A Step S .

The management control unit A receives from the device management application A via the API the history processing request corresponding to the history acquisition request received from the operation terminal . The management control unit A then transmits the history processing request thus received to the information control unit A Step S .

The information control unit A receives the history processing request from the management control unit A. The information control unit A then transmits a second conversion request corresponding to the history processing request thus received to the conversion unit A Step S .

The conversion unit A that receives the second conversion request reads the second conversion rule the converted DB corresponding to each device ID and the log definition corresponding to each device ID stored in the storage unit A Step S and Step S and performs the conversion Step S .

The conversion unit A then transmits the processing history information in the second common data format common to a plurality of devices created by the conversion to the information control unit A Step S .

If the information control unit A receives the processing history information in the second common data format from the conversion unit A the information control unit A transmits the processing history information to the management control unit A Step S . The management control unit A transmits the processing history information in the second common data format to the device management application A Step S . The device management application A transmits the processing history information in the second common data format received from the device management unit A to the operation terminal that transmits the history acquisition request corresponding thereto Step S .

Subsequently the conversion unit A reads the item name in the history information in the data format of each device corresponding to the specification information designated in the second conversion request Step S . In more detail the conversion unit A reads the common item name corresponding to the item name included in the specification information designated in the second conversion request from the second conversion rule. The conversion unit A then reads the item name for each device corresponding to the common item name thus read from the second conversion rule.

Subsequently the conversion unit A extracts a history of processing specified by the specification information designated in the second conversion request from the processing history information in the data format of each device corresponding to each device ID Step S .

The conversion unit A then reads the record content corresponding to the item name of the item to be acquired that is designated in the second conversion request from the history of processing specified by the specification information designated in the second conversion request Step S .

If the units of the record contents read at Step S are different the conversion unit A makes the units consistent Step S .

By performing the process from Step S to Step S the conversion unit A extracts the record content corresponding to the item name of the item to be acquired that is designated in the second conversion request from the processing history information in the data format of each device based on the second conversion rule. Thus the conversion unit A creates the processing history information in the second common data format common to a plurality of devices.

As described above in the information processing apparatus A according to the present embodiment the conversion unit A extracts the record content corresponding to the item name of the item to be acquired that is designated in the second conversion request from the processing history information in the data format of each device based on the second conversion rule. Thus the conversion unit A creates the processing history information in the second common data format common to a plurality of devices. The second conversion rule is a conversion rule for converting the data formats of the processing history information of a plurality of different types of devices into the second common data format serving as the data format common to these devices.

Therefore in addition to the advantageous effects in the first embodiment the information processing apparatus A according to the third embodiment can process the processing history information in the data format of each device while absorbing the difference among the data formats.

The second conversion rule is a table that stores therein a common item name a device ID and a corresponding item name in the processing history information in the data format of each device in a manner associated with one another. Therefore the information processing apparatus A can manage the item name of the item included in the processing history information in the data format of each device in a manner associated with the common item name having the same meaning based on the second conversion rule. As a result the information processing apparatus A can collectively manage a plurality of types of processing history information in different data formats.

The information processing apparatuses according to the first to the third embodiments have a hardware configuration including a control device such as a central processing unit CPU a storage device such as a read only memory ROM and a random access memory RAM an external storage device such as an HDD and a compact disk CD drive a display device such as a display and an input device such as a keyboard and a mouse.

The computer program executed in the information processing apparatuses and the information processing systems according to the first to the third embodiments is provided in a manner recorded in a computer readable recording medium such as a compact disk read only memory CD ROM a flexible disk FD a compact disk recordable CD R and a digital versatile disk DVD as a file in an installable or executable format.

The computer program executed in the information processing apparatuses and the information processing systems according to the first to the third embodiments may be provided in a manner stored in a computer connected to a network such as the Internet to be made available for downloads via the network. Furthermore the computer program executed in the information processing apparatuses and the information processing systems according to the first to the third embodiments may be provided or distributed over a network such as the Internet.

The computer program executed in the information processing apparatuses and the information processing systems according to the first to the third embodiments may be provided in a manner incorporated in a ROM and the like in advance.

The computer program executed in the information processing apparatuses and the information processing systems according to the first to the third embodiments have a module configuration including each unit described above. In actual hardware the CPU processor reads and executes each computer program from the storage medium described above to load each unit on the main memory. Thus each unit is generated on the main memory.

Even if a new type of device is added as a device to be managed the information processing apparatus according to the present invention can readily support the device.

Although the invention has been described with respect to specific embodiments for a complete and clear disclosure the appended claims are not to be thus limited but are to be construed as embodying all modifications and alternative constructions that may occur to one skilled in the art that fairly fall within the basic teaching herein set forth.

