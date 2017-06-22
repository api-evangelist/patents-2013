---

title: Systems and methods providing recommendation data
abstract: Computer applications may generate event data based on a large volume of different types of record data. Described herein are systems, methods and devices for providing website recommendations using the event data. In one example, using the event data, a computing node generates the website recommendations within a designated amount of time after the generation of the record data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09361379&OS=09361379&RS=09361379
owner: Amazon Technologies, Inc.
number: 09361379
owner_city: Reno
owner_country: US
publication_date: 20130927
---
Computer systems may generate a large volume of different types of log data representing millions of different processes occurring every second. Because of the differences in the types of data variability in expressing that data the volume of the log data and so forth it is difficult for applications to consume the data in near real time.

Certain implementations and embodiments will now be described more fully below with reference to the accompanying figures in which various aspects are shown. However various aspects may be implemented in many different forms and should not be construed as limited to the implementations set forth herein. Like numbers refer to like elements throughout.

U.S. patent application Ser. No. 09 157 198 now U.S. Pat. No. 6 266 649 filed on Sep. 18 1998 titled Collaborative Recommendations Using Item to Item Similarity Mappings to Gregory D. Linden et al. is incorporated by reference in its entirety into this disclosure.

U.S. patent application Ser. No. 11 841 926 now U.S. Pat. No. 7 921 042 filed on Aug. 20 2007 titled Computer Processes for Identifying Related Items and Generating Personalized Item Recommendations to Jennifer A. Jacobi et al. is incorporated by reference in its entirety into this disclosure.

U.S. patent application Ser. No. 11 863 108 now U.S. Pat. No. 7 779 040 filed on Sep. 27 2007 titled System for Detecting Associations Between Items to Cory Hicks is incorporated by reference in its entirety into this disclosure.

U.S. patent application Ser. No. 13 174 601 now U.S. Pat. No. 8 706 860 filed on Jun. 30 2011 titled Remote Browsing Session Management to Mathew L. Trahan et al. is incorporated by reference in its entirety into this disclosure.

Computer systems may generate a large volume of different types of record data such as log data representing millions of different processes occurring every second. The record data may have many different types and may be expressed in many different ways. Due to the differences in the types of record data variability in expressing that record data the volume of the record data and so forth it is difficult for applications to perform computational tasks using the data in near real time. Also as the volume of record data continues to grow in size determining the resource usage associated with the performance of the computational tasks has become challenging. In addition as the volume of record data continues to grow in size users e.g. internal business users may desire to customize the record data for more efficient processing.

This disclosure relates to systems and methods for transforming the record data into parsed data. A processing system node is configured to transform the record data into the parsed data. The processing system node is made up of one or more computing nodes which can perform functions described in this disclosure. These functions may be executed as one or more services. The processing system node generates parsed data from the record data in real time or near real time. Users such as internal business users may configure the processing system node to transform the parsed data into event data. The processing system node provides the event data to sink nodes. The sink nodes may use the event data for computational tasks. For example a particular sink node may analyze the event data to determine whether a user has incorrectly been granted access to a particular piece of content such as a document or movie.

The processing system node may have an application programming interface configured to provide a common set of service calls which may be used by one or more services executing on one or more nodes. The application programming interface may be implemented as one or more libraries including routines data structures object classes variables and so forth associated with operation of the system described herein.

The record data represents various information about activities associated with producer nodes. The record data may comprise at least one of data indicating that a computing device has been accessed data indicating that information was transferred to the computing device data indicating an occurrence of an error and so forth. The producer nodes may comprise computing nodes having computing devices configured to implement certain functions described in this disclosure as one or more services.

Record data from different sources may have different types. For example the record data may be different in layout composition encoding and so forth. A first producer node may generate record data having a first type or expression and a second producer node may generate record data having a second different type or expression. For example the first producer node may generate record data comprising the text LOGIN indicating that a particular computing device has been accessed and the second producer node may generate record data comprising the text USER HAS SIGNED IN indicating that another particular computing device has been accessed. In this example the record data generated by the first and second producer nodes indicate a same or similar activity has occurred namely the activity of logging onto a computing device. However the generated text of the record data is expressed differently. That is the text LOGIN has a different expression than the text USER HAS SIGNED IN but this text indicates a same or similar activity has occurred.

In some implementations the record data includes record entries. A particular record entry may comprise data about an activity associated with a producer node. For example generated record data may include a first record entry indicating that a particular computing device has been accessed and a second record entry indicating the user that accessed the particular computing device. As discussed in more detail below to generate parsed data the record entries may be mapped to parsed entries.

The parsed data may be described as transformed or otherwise processed record data. In some implementations the parsed data includes parsed entries. A parsed entry may be described as a transformed or otherwise processed record entry. As discussed in more detail below the parsed data may be further processed into event data which may be used by other computing nodes to perform computational tasks.

The record data may be transformed into parsed data in real time or near real time using one or more transformation functions. As used in this disclosure near real time may be a period of time less than or equal to 20 seconds. By transforming the record data into parsed data in near real time computing systems may consume large volumes of different types of record data in near real time. Transforming the record data into parsed data in real time or near real time may include allocating the record data to certain data processing modules when the record data is received by the processing system node. Transforming the record data into parsed data in real time or near real time may include generating parsed data as the record data is received by the processing system node.

The record data may be transformed into parsed data as instantaneously as possible. The amount of time to transform the parsed data may be limited by various factors. The factors may include the ability to receive the record data the ability of the hardware or software to receive or access the record data and perform the transformation and so forth.

In some implementations the record data is transformed into parsed data in real time or near real time because the processing system node performs the transformation as the processing system receives the record data. Once the processing system node receives the record data the processing system node may perform its functions by maintaining the record data in the primary system memory as compared to the secondary system memory. Due to faster read write times reduced contention or other factors data transfer with the primary system memory is greater than the secondary system memory. As a result the time for processing the record data is reduced compared to systems which rely on storage in the secondary system memory. This may reduce overall processing time allowing the record data to be transformed into parsed data in real time or near real time as the processing system node receives the record data.

Transforming the record data into parsed data in near real time may be described as transforming the record data substantially immediately once the processing system node receives the record data. In some examples substantially immediately may be described as within a designated period of time such as five seconds.

In one example the processing system node may transform the record data into parsed data by converting the record entries into the parsed entries. For example a first record entry of LOGIN may be converted to a first parsed entry of L and a second record entry of User has signed in may be converted to a second parsed entry of L .

The processing system node may transform the record data into parsed data in real time or near real time by mapping record entries to parsed entries. For example the record data may include a first record entry comprising text data indicating a date and a second record entry comprising text data indicating a unique identifier of a computing device. The text data indicating the date may be mapped to a first parsed entry which may comprise a different expression of the date. For example a date of Aug. 4 2013 may be mapped to 2013 08 04 . The text data indicating the unique identifier may be mapped to a second parsed entry. For example a unique identifier of 94 1234 56 may be mapped to 9412356 .

The processing system node may generate parsed data which reorders the order of record entries. For example the first record entry may include text data comprising LOGIN and the second record entry may include text data comprising 2013 07 08 indicating a particular date that a user logged onto a computing device. In this example the order of the record entries may be changed such that the resulting parsed data comprises a first parsed entry comprising text data 2013 07 08 and a second parsed entry including text data comprising LOGIN .

In addition to reordering the order of the record entries the processing system node may transform the record data by converting the record data such that the record entries conform to a designated standard. For example a first record entry may include text data comprising Jul. 17 2013 and a second record entry which includes text data comprising 28MAY2013 . The designated standard may include dates having the following format four digit year two digit month and two digit day. In this example the first record entry may be converted from Jul. 17 2013 to 2013 07 17 and the second record entry may be converted from 28MAY2013 to 2013 05 28 .

The processing system node may perform more than one process with regard to the record data to generate the parsed data. For example the processing system node may reorder the record entries and convert the record entries.

In some implementations the processing system node may add resources to process data. For example the processing system node may add computing devices to transform the record data into parsed data. The processing system node may determine that the record data is not being transformed into the parsed data within a certain amount of time or within real time or near real time. Based on this determination the processing system node may add resources such that the record data is transformed within the certain amount of time. Because the processing system node may add resources to process the record data the processing system node provides scalability for the overall system. That is additional processing system nodes may be added to handle in parallel an increasing amount of data.

The processing system node may include different parse modules configured to handle different types of record data. The different parse modules may be optimized to handle certain types of record data. In one example the processing system node includes a first parse module and a second parse module. A first producer node may generate first record data having a first type and a second producer node may generate second record data having a second type. The first parse module may be configured to process the first record data and not process the second record data. The second parse module may be configured to process the second record data and not process the first record data.

The processing system node may be configured to allocate the different record data to the different parse modules based on information included in the record data. The information may include data which identifies the computing node that generated the record data. For example a first record data may include data indicating that the first record data was generated from a first producer node. Based on the information indicating that the first record data was generated from the first producer node the processing system node may provide the first record data to a parse module that is optimized to process record data from the first producer node.

In some implementations the processing system node is configured to generate event data by transforming the parsed data. The processing system node may generate the event data by transforming the parsed data in real time or near real time. As discussed in more detail below the event data may be used by other computing nodes such as sink nodes to perform various computational tasks. For example the sink node may use the event data to determine whether a particular user has incorrectly accessed a piece of content.

The processing system node may transform the parsed data into event data using one or more processes. For example the processing system node may transform the parsed data into event data by applying format data to the parsed data. The format data may comprise information about configuring the processing system node to format the parsed data. In one example the format data comprises an expression language. The processing system node may store different format data for different sink nodes. Different sink nodes may cause the processing system node to perform different functions on the parsed data based on the different format data. For example a first sink node may only be interested in user data and therefore may cause the processing system node to filter out all data from the parsed data except the user data. Continuing the example a second sink node may only be interested in data about a computing device being accessed and therefore may cause the processing system node to filter out all data from the parsed data except the data about the computing device being accessed.

The processing system node may apply the format data to the parsed data using one or more various functions. Applying the format data to the parsed data may include filtering one or more parsed entries from the parsed data. For example a first parsed entry may include text data comprising 2012 08 28 and a second parsed entry may include text data comprising a unique identifier of 8765 4321 . The processing system node may filter the parsed data by removing the date 2012 08 28 such that the resulting event data comprises only the unique identifier.

In another example applying the format data to parsed data may include decorating the parsed data. Decorating may be described as adding information to the parsed data. For example the parsed data may comprise a parsed entry including text data comprising an Internet Protocol IP address. The IP address may be decorated by adding additional information such as location data associated with that IP address.

In another example applying the format data to parsed data may include changing the order of parsed entries. For example the first parsed entry may include text data comprising a time value of 12 34 06 and the second parsed entry may include text data comprising 2012 03 31 indicating a particular date. In this example the order of the parsed entries may be changed such that the resulting event data comprises a first event entry comprising the text data 2012 03 31 and a second event entry including text data comprising 12 34 06 .

The sink node may comprise one or more computing nodes. The one or more computing nodes may comprise computing devices which may include hardware processors and memory devices. The computing devices may be configured to implement certain functions described in this disclosure as one or more services. The sink node may use the event data to perform various computing tasks. For example the sink node may be configured to analyze the parsed data to determine whether a designated computing device has been accessed by an unauthorized user. In another example the sink node may be configured to analyze the parsed data to determine whether a particular document has been accessed by an unauthorized user.

In some implementations the event data comprises configuration data. For example the event data may comprise data which causes the sink node to provide one of a plurality of treatments to a media device. The treatments may comprise web pages. For example based on a first treatment the media device may display a web page which includes an advertisement at the upper right side portion of the display screen of the media device. Based on a second treatment the media device may display the web page with the advertisement at a lower centered position of the display screen.

In some implementations the sink node is configured to generate sink configuration data. The sink configuration data may comprise various information. For example the sink configuration comprises the format data. The sink node may enable an administrative user to operate with the sink node to generate the format data based on user input.

In another example the sink configuration data comprises percentage data which is configured to cause the processing system node to provide a portion of the generated event data to the sink node. For example an administrative user may operate with the sink node and enter in a value of 50 percent . Based on the entered value of 50 percent the sink node may generate sink configuration data which includes the value of 50 percent and provide the sink configuration data to the processing system node. Using the value of 50 percent the processing system node may provide every other generated event data to the sink node. In some implementations the sink node may only need a representative set of the event data rather than a complete set of the event data. By providing a representative set of the event data the processing system node may increase the speed of providing data to the sink node because less data is needed. In some implementations the processing system node may provide both the complete set of event data and a subset of the complete set of event data that may be used for faster processing. The subset of event data may be processed at a cheaper cost when compared to processing the complete set of event data.

By generating parsed data within a designated amount of time after a generation of a large amount of record data sink nodes may perform computational tasks in real time or near real time. Performing tasks in real time or near real time using the record data may provide many advantages. For example unauthorized access to computing devices or content may be detected quickly. Further by enabling administrative users to configure the processing system node to apply customized processes to the parsed data sink nodes may receive specific structured data for executing computational tasks rather than receiving a large amount of unstructured data.

The processing system node may include a producer configuration generation module configured to generate producer configuration data . The producer configuration data may comprise information about configuring the producer node . For example the producer configuration data may comprise identification data that identifies the processing system node . The identification data may cause the producer node to provide data to the identified processing system node . In the producer configuration generation module provides the producer configuration data to the producer node .

The producer node includes a record generation module configured to generate record data . The record data may include various data about one or more activities associated with the producer node . For example the record data may comprise data indicating that the producer node has been accessed data indicating that certain information was transferred to the producer node data indicating an error occurred at the producer node and so forth. The record data may be a different type of data from the record data . For example the record data may be different in layout composition or encoding from the record data . For example the record data may comprise the text LOGIN and the record data may comprise the text USER HAS SIGNED IN . The record data may include record entries not shown . A particular record entry may comprise data about an activity associated with a producer node P . For example the record data may include a first record entry indicating that a particular computing device has been accessed and a second record entry indicating the user which accessed the particular computing device.

In the record generation module provides the record data to an input module of the processing system node . The input module may be configured to receive different record data from different producer nodes P . For example in the input module receives the record data from the producer node and the record data from the producer node P . As discussed in more detail below for optimization purposes the input module may allocate different record data to different parse modules of the processing system node .

Once the input module receives the record data the record data may be by maintained in a primary system memory as compared to a secondary system memory. Due to faster read write times reduced contention or other factors data transfer with the primary system memory is greater than the secondary system memory. As a result the time for processing the record data is reduced compared to systems which rely on storage in the secondary system memory.

The configuration node may include a mapping datastore configured to store mapping data a format datastore configured to store format data and a configuration generation module configured to generate configuration data . The mapping datastore and the format datastore may comprise data structures stored on one or more memory devices.

The configuration data may comprise information about configuring the processing system node to generate parsed data and event data which are discussed in more detail below. The configuration data may also include information about configuring the producer nodes . Once the processing system node receives the configuration data the processing system node may apply the configuration data to generate at least one of the parsed data and the event data . This application may occur within a designated period of time after the generation of the configuration data . For example the application may occur within fifteen seconds after the generation of the configuration data . Because the configuration data may be applied by the processing system node within the designated period of time sink nodes may acquire more relevant data resulting in a more efficient process.

The configuration data may be generated based on machine learning. For example a first sink node may generate the configuration data in response to a determination by a second sink node that a need exists to start including new information. The second sink node may provide data to the first sink node which causes the first sink node to automatically generate the configuration data .

In some implementations the configuration node includes an interface for enabling users to operate with the interface to generate the configuration data based on user input. The interface may include for example a web interface or an application programming interface.

The mapping data may comprise data about associating or mapping the record data with other data. Mapping the record data is discussed in more detail below. The configuration node may provide the mapping data to the processing system node . In one example the configuration node provides the mapping data to the processing system node in response to a request from the processing system node . The configuration node may enable the mapping data to be configurable. In one example the configuration node may provide a user interface not shown which enables an administrative user to modify the mapping data . The configuration node may provide the mapping data as configuration data .

The format data may comprise information about configuring the processing system node . The application of the format data is discussed in more detail below. The configuration node may provide the format data to the processing system node . In one example the configuration node provides the format data to the processing system node in response to a request from the processing system node . The configuration node may enable the format data to be configurable. In one example the configuration node includes a user interface not shown which enables an administrative user to modify the format data . The configuration node may provide the format data as the configuration data . By storing the format data at the format datastore more than one sink node may use the format data stored at the format datastore . The format data may be constructed in a hierarchical fashion. For example the processing system node may generate formatted data by applying a first format data to a relatively large amount of parsed data and then a second format data may be applied to the formatted data. By constructing the format data in a hierarchical fashion the processing system node may generate data more efficiently.

The processing system node may include a parse module . In the parse module generates the parsed data . The parse module may generate the parsed data by transforming the record data based on the mapping data . For example the record data may include a first record entry comprising text data indicating a date and a second record entry comprising text data indicating a unique identifier of a computing device. The text data indicating the date may be mapped to a first parsed entry which may comprise a different expression of the date. For example a date of Aug. 4 2013 may be mapped to 2013 08 04 . The text data indicating the unique identifier may be mapped to a second parsed entry. For example a unique identifier of 94 1234 56 may be mapped to 9412356 .

The parse module may generate the parsed data at a rate which is greater than or equal to a rate at which the record data is received. Such a configuration may cause the processing system node to operate as a real time or near real time system.

In some implementations the same or similar record data may be transformed into different parsed data based on modifications to the mapping data . For example at a first point in time a first record entry of Aug. 4 2013 may be changed to a first parsed entry of 2013 08 04 . Thereafter the mapping data may be modified such that a second record entry of Aug. 4 2013 may be changed to a second parsed entry of AUG 2013 .

The record data may be transformed into the parsed data in real time or near real time by converting the record entries of the record data into parsed entries which comprise the parsed data . For example a first record entry of LOGIN may be converted to a first parsed entry of L and second record entry of User has signed in may be converted to a second parsed entry of L .

In addition to converting the record entries the parse module may generate the parsed data by reordering the record entries of the record data . For example the first record entry may include text data comprising LOGIN and the second record entry may include text data comprising 2013 07 08 indicating a particular date that a user logged onto a computing device. The order of the record entries may be changed such that the resulting parsed data comprises a first parsed entry comprising text data 2013 07 08 and a second parsed entry including text data comprising LOGIN .

Although the example illustrated in shows the processing system node having one parse module the processing system node may have more than one parse module configured to generate parsed data . In some implementations the different parse modules are configured to handle different record data . These different parse modules may be optimized to handle different record data .

In some implementations the processing system node adds one or more parse modules to generate the parsed data . The processing system node may add the one or more parse modules if the record data is not being transformed into the parsed data within a certain amount of time. In this example the processing system node may add the one or more parse modules such that that record data is transformed within the certain amount of time. Because the processing system node may add resources such as parse modules to process the record data the processing system node provides scalability for the overall system .

The processing system node may include one or more processing modules comprising various modules used to generate event data . The event data may be described as transformed or otherwise processed parsed data . For example in the processing module includes a filter module a decorate module and other modules . The filter module may be configured to filter one or more parsed entries from the parsed data . For example the parsed data may comprise a first parsed entry including text data comprising 2012 08 28 and a second parsed entry including text data comprising a unique identifier of 8765 4321 . The filter module may filter the parsed data by removing the 2012 08 28 such that the resulting event data comprises only the unique identifier. The decorate module may be configured to decorate the parsed data . For example the parsed data may comprise a parsed entry including text data comprising an IP address. The IP address may be decorated by adding additional information such as location data associated with the IP address. The other module may be configured to perform various other functions to generate the event data . For example the other module may reorder the parsed entries to generate the event data . In another example the other module may convert the parsed data into event data comprising markup language such as extensible markup language XML .

In the processing module provides the event data to the sink node . The sink node is configured to perform computational tasks using the event data . The sink node may include an event processor module configured to perform the computational tasks. In one example the computational task includes generating alarm data which indicates that a user has been granted access to a particular document.

The sink node may include a sink configuration generation module configured to generate sink configuration data . The sink configuration data may comprise information about configuring the processing system node . For example the sink configuration data may include the format data discussed above with regard to the format datastore . In some implementations the sink node provides the sink configuration data to the configuration node . In other implementations the sink node provides the sink configuration data to the processing system node .

The sink node may include an interface module that enables administrative users to operate with the processing system node to generate the format data based on user input. In some implementations another computing device not shown includes the interface module which enables the administrative user to generate the format data based on user input.

By enabling administrative users to operate with computing devices to generate the sink configuration data sink nodes may receive specific structured data for executing computational tasks rather than receiving a large amount of unstructured data.

In the record data includes five record entries illustrated as different shapes. That is the record data includes a first record entry illustrated as a first triangle a second record entry illustrated as a circle a third record entry illustrated as a second triangle a fourth record entry illustrated as a square and a fifth record entry illustrated as a third triangle. The record entries may represent different information associated with the producer node . The record data includes five record entries illustrated as different shapes. That is the record data includes a first record entry illustrated as a square a second record entry illustrated as a first circle a third record entry illustrated as a second circle a fourth record entry illustrated as a third circle and a fifth record entry illustrated as a triangle.

In one example the triangles may represent data about users accessing particular devices circles may represent data indicating that an item was purchased and squares may represent an indication that an error occurred. illustrates that event data comprises two square record entries. An administrative user associated with the sink node may have configured the processing system node to generate the event data to include only data about indications of errors. The event data may comprise three triangle record entries because an administrative user associated with the sink node may have configured the processing system node to generate the event data such that only data about accessing particular devices is included. The event data may comprise three circle record entries and two square record entries because an administrative user associated with the sink node may desire for the event data to include only data about items being purchased and data about the occurrence of errors.

The user data may comprise information about a user. In one example the user data includes data representing a unique identifier associated with a user of a computing device. The unique identifier may represent a user that caused a computing device to perform an action such as accessing a particular computing device purchasing an item and so forth.

The device data may comprise information about a computing device. For example the device data may comprise at least one of data representing a unique identifier associated with the computing device data identifying a computing device that performed a particular action or data representing an IP address of the computing device.

The action data may comprise information about a particular action that was performed. For example the action data may include at least one of data indicating a user has accessed a particular computing device data indicating information was transferred to an unauthorized computing device data indicating an item was purchased or data indicating an occurrence of an error.

The location data may comprise information about location. For example the location data may comprise information about the location of a computing device. The location data may include geolocation data which is indicative of a latitude and longitude of the computing device. The location data may include geolocation data which is indicative of a latitude and longitude of the location in which a particular action was performed. For example the location data may indicate that a user accessed a particular computing device in a particular conference room.

The privilege data may comprise information about events related to a modification of privileges. For example the privilege data may indicate that a user was granted access to a particular document. The time data may comprise information about time. The time data may represent when an event occurred when a particular record data was generated and so forth. The object data may comprise information about an object that a computing device is performing an action on. For example the object data may identify a particular document that is being modified. The date data may comprise information about the date that an event occurred. The protocol data may comprise data about a transmission protocol which was used to send the record data .

The parsed data may be described as transformed or otherwise processed record data . The parsed data may include a plurality of parsed entries. For example the parsed data may include parsed entries . . . Y . As illustrated in the parsed entry may comprise one or more of the following data user data device data action data location data privilege data time data object data date data and protocol data .

The event data may be described as transformed or otherwise processed parsed data . The event data may include a plurality of event entries. For example the event data may include event entries . . . Z . As illustrated in the event entry may comprise one or more of the following data user data device data action data location data privilege data time data object data date data and protocol data .

The event entry may include configuration data comprising information about configuring a computing device. For example the event entry may comprise data which causes the sink node to provide one of a plurality of web pages to a media device.

The event entry may include filtered data . The filtered data may be described as data which has been processed by the filter module . The event entry may include decorated data . The decorated data may be described as data which has been processed by the decorate module .

The endpoint data may comprise data which causes the producer node to provide the record data to the processing system node . The percentage data may comprise data which causes the producer node to provide a portion of the record data to the processing system node . The portion of the record data may be a designated percentage of a random sample of the record data . For example the portion may be the first twenty percent or the last twenty percent of a random sample of the record data . In another example the portion of the record data may be determined based on intervals. For example the producer node may provide every other generated record data or every third generated record data .

The protocol data may comprise data which causes the producer node to provide the record data to the processing system node using a designated communications protocol. The designated protocol may include Transmission Control Protocol User Datagram Protocol and so forth.

The sink configuration data may be described as data used to configure the processing system node . The sink configuration data may include information which indicates which producer nodes to receive information from. In one example at a first point in time the sink configuration data includes information which causes the processing system node to provide data from a first producer node and a second producer node . Thereafter the sink configuration data may include information which causes the processing system node to no longer provide event data using information from the first producer node . The sink configuration data may include format data . The format data may comprise data about configuring the processing system node to format the parsed data . The format data may include at least one of filter format data decorate format data decorate data or other format data .

The filter format data may comprise data which causes the processing system node to filter or remove at least a portion of the parsed data . The decorate format data may comprise data which causes the processing system node to decorate the parsed data . The decorate data may comprise data which is used by the decorate module to decorate the record data . The other format data may comprise various data. For example the other format data may comprise data which causes the processing system node to reorder the parsed data .

The sink configuration data may include percentage data . The percentage data may be configured to cause the processing system node to provide a portion of the generated parsed data . For example an administrative user may operate with the sink node and enter in a value of 50 percent . Based on the entered value of 50 percent the sink node may generate the percentage data which includes the value of 50 percent and provide the percentage data to the processing system node . Using the value of 50 percent the processing system node may provide every other generated parsed data to the sink node resulting in fifty percent of the parsed data being provided.

As described above the format data may be generated based on user input. In some implementations the format data may not be generated based on user input. For example a particular sink node may determine that an amount of event data being received is too large for the sink node to process. Based on this determination the sink node may automatically generate format data which causes the processing system node to provide less event data . In another example the format data may be generated based on machine learning. For example a first sink node may generate the format data in response to a determination by a second sink node that a need exits to start including new information. The second sink node may provide data to the first sink node which causes the first sink node to automatically generate the format data .

The records include the record entries . The record associated with record ID 1 comprises the following six record entries 1 LOGIN 2 2009 07 05 3 02 30 21 4 user 1 5 DATA PROCESSOR and 6 1921685 . The record associated with record ID 2 comprises the following six record entries 1 COMPUTER ACCESSED 2 2009 07 05 3 02 38 56 4 user 2 5 COMPUTING MACHINE and 6 1527885 . The record associated with record ID 3 comprises the following six record entries 1 USER HAS SIGNED IN 2 2009 07 05 3 02 39 12 4 user 3 5 ELECTRONIC COMPUTER and 6 9874852 .

The mapping data includes a mapping table which includes data characterized as being organized in columns and rows. The columns of the mapping table include the following fields record entry and parsed entry . The parsed entries in the mapping table include the following values L and COMPUTER .

In the parse module generates the parsed data by mapping the record entries to the parsed entries . For example the parse module maps the record entry Login to the parsed entry L . The parse module also maps the record entry Computer accessed to the parsed entry L and the record entry User has signed in to the parsed entry L . Using field data the parse module assigns the record entries to designated fields as shown in a parsed data table . The field data may comprise information about assigning the record entries to designated fields.

The parsed data may include the parsed data table which includes data characterized as being organized in columns and rows. The parsed data table includes the following six fields parsed ID user data device data action data time data and date data . In the parse module reorganizes the input data. For example as shown in when viewed from left to right the data of the parsed data table has a different order than the data of the record data table .

Once the filtered data is generated the decorate module generates the decorated data using the filtered data and the decorate format data . The decorate format data comprises information which adds other information to the filtered data . The other information is illustrated in the decorated data as star shapes. The other information may comprise any suitable data. For example the other information may comprise text data representative of a location. The added text data may be determined based on an IP address included in the filtered data .

In the processing system node provides the event data to the sink node . The event data may comprise the decorated data . The sink node may use the event data to perform one or more computational tasks.

In some implementations the parse module is configured to provide the parsed data to more than one of the processing modules which are configured to generate different formatted data by applying different format data to the parsed data after applying the format data . These different generated formatted data may then be provided to other processing modules for further processing. Such a configuration may be visualized as a hierarchical construction which may increase the efficiency of the processing system node . Efficiency may be increased because different sink nodes that would perform most of the same or similar processing of record data to generate the event data may not need to perform the same processing multiple times. That is the root of the hierarchy is processed once for all leaf nodes and each level below the root is processed once as needed for the leaf node. In complex cases such a configuration may reduce a large amount of processing time.

As illustrated in the decorate format data comprises expression language data which causes the decorate module to decorate the parsed data based on the expression language. The decorate format data may be generated based on user input from for example an administrative user associated with the sink node . As discussed above the decorate data may comprise information which is added to the parsed data . In the information added to the parsed data is illustrated as having star shapes. That is as shown in the decorated data information has been added and is illustrated as stars. These star shapes may be described as parsed entries .

Once the decorated data is generated the filter module generates the event data using the decorated data and the filter format data . As illustrated in the filter format data comprises expression language data that causes the filter module to filter the decorated data based on the expression language. The filter format data may be generated based on user input from for example an administrative user associated with the sink node . As shown in the filter module removes the square parsed entries and the triangle parsed entries resulting in event data that comprises event entries illustrated as three circles and two stars.

The producer node may include a primary data generation module configured to generate primary data . The primary data may comprise information about one or more activities associated with the producer node .

The record data may be described as transformed or otherwise processed primary data . As illustrated in the primary data may comprise one or more of the following data user data device data action data location data privilege data time data object data date data and protocol data .

In the record generation module generates the record data using the primary data and the producer configuration data . In this example the primary data generation module causes the record generation module to remove information. The information removed from the primary data is illustrated as a square shape. This information may comprise various information. For example the information removed may include information about a user information about a device information about an action and so forth. The primary data generation module may be configured to perform similar or the same functions as the parse module or the processing module . For example the primary data generation module may apply format data to the primary data . Additionally the primary data generation module generates the record data by converting the primary data based on mapping data . In another example the record generation module may reorder the primary data based on the producer configuration data .

The primary data generation module may provide various benefits. For example efficiency of the processing system node may improve because the processes performed by the primary data generation module may reduce the amount of data transferred from the producer node to the processing system node . In addition the processes performed by the primary data generation module may reduce the amount of resources e.g. servers computing nodes and so forth needed at the processing system node to process data received from the producer node because the producer node has already processed the data.

The processing system node includes at least one input output I O interface that enables portions of the processing system node e.g. the hardware processor to communicate with other devices. The I O interface may include Inter Integrated Circuit I2C Serial Peripheral Interface bus SPI Universal Serial Bus USB RS 232 HDMI TOSLINK Bluetooth and so forth. The at least one I O interface may be coupled to at least one I O device . In some implementations certain I O devices are physically incorporated with the processing system node or externally placed.

The processing system node may include at least one communication interface . The communication interface may be configured to provide communications between the processing system node and other devices such as servers routers access points and so forth. The communication interface may connect to a network.

The processing system node may include at least one bus or other internal communications hardware or software that enables for the transfer of data between the various modules and components of the processing system node .

As illustrated in the processing system node may include at least one memory or memory device . The memory may comprise one or more non transitory computer readable storage media CRSM . The CRSM may include at least one of an electronic storage medium a magnetic storage medium an optical storage medium a quantum storage medium a mechanical computer storage medium and so forth. The CRSM may comprise primary system memory or secondary system memory. Primary system memory is online readily accessible storage that may be accessed with little or no latency. For example primary system memory may include random access memory RAM flash memory and so forth. In comparison secondary system memory may be accessed with latency greater than the primary system memory. For example the secondary system memory may include spinning magnetic media magnetic tape and so forth. The memory may store computer readable instructions data structures program modules and other data for the operation of the processing system node .

The memory may include at least one operating system OS module . The OS module may be configured to manage hardware resources such as the I O interface the I O devices the communication interfaces and provide various services to applications or modules executing on the hardware processor . The memory may also store at least one of the following modules which may be executed as foreground applications background tasks daemons and so forth.

The memory may include a user interface module . The user interface module may be configured to provide a user interface to a user using the I O devices and to accept inputs received from the I O devices . The user interface may include one or more visual audible or haptic elements. For example the user interface may be configured to provide a graphic user interface an audible user interface and so forth.

As discussed above the producer configuration generation module may generate the producer configuration data . In some implementations the producer configuration generation module generates the producer configuration data based on user input. The producer configuration generation module may enable a user to operate with the processing system node to enter the producer configuration data .

The input module may be configured to receive different record data from different producer nodes P . For example the input module may receive the record data from the producer node and the record data from the producer node P .

As discussed above the parse module may generate the parsed data . The parse module may generate the parsed data by transforming the record data based on various processes. For example the parse module may convert the record entries into parsed entries based on the mapping data . In another example the parse module may generate the parsed data by reordering the record entries .

As discussed above although the example illustrated in illustrates the processing system node having one parse module the processing system node may have more than one parse module configured to generate parsed data . In some implementations the different parse modules are configured to handle different record data . These different parse modules may be optimized to handle different record data .

The processing module may include various modules used to generate the event data . In the processing module includes the filter module the decorate module and the other module .

In some implementations the memory includes a datastore for storing information. The datastore may use a flat file database linked list code tree or other data structure to store the information. The datastore may comprise the primary system memory which may include random access memory flash memory and so forth. In other implementations the datastore may comprise the secondary system memory. In some implementations the datastore or a portion thereof may be distributed across at least one other device such as another server a network storage device and so forth. As illustrated in the datastore may include the producer configuration data the mapping data the format data the configuration data the parsed data the event data the sink configuration data the filtered data and the decorated data .

At block the producer node generates first record data including information about first activities. For example the producer node may generate the record data . The record data may include information indicating that a computing device has been accessed data indicating that information was transferred to a computing device data indicating an occurrence of an error and so forth.

In some implementations the producer node generates the first record data based on the producer configuration data . The producer configuration data may comprise information about configuring the producer node . In some implementations the processing system node enables a user e.g. an administrative user to operate an input device of the processing system node to generate the producer configuration data . The producer configuration data may cause the producer node to provide the record data to the processing system node using a specified transmission protocol. The producer node may generate the record data using the primary data . The primary data may comprise information about one or more activities performed by the producer node .

At block the producer node generates second record data including information about second activities. For example the producer node P may generate the record data . The record data may be different in layout composition or encoding from the record data .

At block the processing system node allocates the first record data to a first parse node based on information included in the first record data . The information included in the first record data may comprise header data indicating a type of data of the first record data . The first parse node may comprise one of a plurality of parse modules .

At block the first parsed node generates first parsed data by transforming the first record data . The first parsed data is generated within a designated amount of time after the generation of the first record data . The designated amount of time may be equal to or less than 20 seconds.

At block the processing system node allocates the second record data to the second parse node based on information included in the second record data . The information included in the second record data may comprise header data indicating a type of data of the second record data .

At block the second parse node generates second parsed data by transforming the second record data . The second parsed data may be generated within a designated amount of time after the generation of the second record data . In some implementations the first parse node and the second parse node are configured to generate parsed data contemporaneously.

At block the processing system node generates event data by transforming the first record data and the second record data . For example the processing system node may generate event data by transforming the record data and the record data .

In some implementations the processing system node generates the event data based on sink configuration data . The sink configuration data may comprise various data. For example the sink configuration data may comprise the endpoint data representing a request for the processing system node to provide the event data to the sink node . The sink configuration data may comprise the percentage data representing a request for the processing system node to provide a percentage of the event data to the sink node . The sink configuration data may comprise the format data comprising information about configuring the processing system node to format the event data . The sink configuration data may be generated by the sink node or a separate computing device communicatively coupled to the processing system node .

At block the processing system node provides the event data to the sink node . The processing system node may provide the event data to a plurality of sink nodes .

At block the sink node performs a computational task using the event data . In one example the performance of the computational task includes determining that a user has been granted access to a particular document and generating alarm data indicating that the user has been granted access to the particular document. In another example the performance of the computational task includes determining that information was transferred to an unauthorized computing device and generating alarm data indicating that the information was transferred to the unauthorized computing device.

At block the processing system node accesses record data which includes record entries . The record entries may comprise various data and may be expressed differently. For example the record entries may comprise text based log data or a human readable log file. The human readable log file may comprise information that can be naturally read by humans. The record entries may indicate that a computing device has been accessed may indicate that information was transferred to an unauthorized computing device may indicate an item was purchased may indicate an occurrence of an error and so forth. The processing system node may comprise one or more computing devices that have one or more hardware processors and one or more memory devices communicatively coupled to the one or more hardware processors. At block the processing system node accesses mapping data which includes data about mapping the record entries .

At block the processing system node generates parsed data by transforming the record data using the mapping data . The parsed data may include parsed entries associated with the record entries . In some implementations the parsed data is generated within a designated amount of time after the generation of the record data . The designated amount of time may comprise fifteen seconds. In some implementations the transformation of the record data using the mapping data includes converting the record data to a markup language. In some implementations the transformation of the record data using the mapping data includes converting the first record entry to a first parsed entry and converting the second record entry to a second parsed entry . The parsed data may indicate that a computing device has been accessed may indicate that information was transferred to an unauthorized computing device may indicate an item was purchased may indicate an occurrence of an error and so forth. In some implementations the transformation of the record data using the mapping data includes changing an order of the first record entry and the second record entry . The transformation of the record data using the mapping data may further include converting the record data such that the first record entry and the second record entry conform to a designated standard. In some implementations the parsed data is generated by filtering the first record entry from the record data such that the first record entry is removed from the record data . The parsed data may further be generated by decorating the second record entry by supplementing the second record entry with other information such as the decorate data .

At block the processing system node generates event data by transforming the parsed data . The event data may be used by a computing node to perform a computational task. For example the event data may be used by the sink node to determine whether a user has incorrectly accessed a piece of content. The event data may be described as record data that has been parsed filtered and mapped. Computing nodes may process the event data more efficiently when compared to processing the record data . In some implementations the event data may be described as being more machine readable when compared to the record data .

In some implementations the processing system node determines whether the parsed data is generated within a designated amount of time e.g. fifteen seconds after a generation of the record data . If the processing system node determines that the parsed data is not generated within the designated amount of time the processing system node may cause additional resources e.g. additional computing devices to operate in cooperation with the processing system node such that subsequently generated parsed data is generated within the designated amount of time. In some implementations once the determination is made the processing system node provides producer configuration data comprising information that causes the producer node to provide generated record data to the computing node operating in cooperation with the processing system node . The computing node operating in cooperation with the processing system node may be located within the processing system node . The designated amount of time may be determined based on a percentage. For example for a system which requires the parsed data or the event data to be generated within twenty seconds if the processing system determines that the parsed data or the event data will be generated in at least sixteen seconds i.e. eighty percent of twenty seconds the processing system node may be configured to cause the computing node to operate in cooperation with the processing system node .

At block the producer node generates record data which includes a first record entry and a second record entry . At block the processing system node accesses the record data . At block the processing system node accesses the mapping data . At block the processing system node generates parsed data by transforming the record data using the mapping data . The parsed data may be generated within a designated amount of time after the generation of the record data .

In some implementations transforming the record data using the mapping data includes converting the first record entry to a first parsed entry and converting the second record entry to a second parsed entry .

At block the sink node generates the format data . At block the processing system node generates the event data by applying the format data to the parsed data . Applying the format data to the parsed data may include filtering the first parsed entry from the parsed data such that the first parsed entry is removed from the parsed data . In some implementations applying the format data to the parsed data includes decorating the second parsed entry by supplementing the second parsed entry with additional information.

At block the processing system node provides the event data to the sink node . At block the sink node performs a computational task using the event data .

At block the processing system node accesses record data which includes record entries . The producer nodes P may provide the record data to the processing system node .

At block the processing system node generates parsed data by transforming the record data within a designated amount of time after the generation of the record data . In some implementations transforming the record data using the mapping data includes changing an order of the record entries . In some implementations generating the parsed data by transforming the record data includes associating the first record entry with a first parsed entry and associating the second record entry with a second parsed entry .

At block the processing system node accesses format data which includes data about configuring a computing node to format the parsed data . For example the format data may comprise information configured to cause the processing system node to format the parsed data .

At block the processing system node generates event data by applying the format data to the parsed data . For example the sink node may use the event data to determine whether particular items have been purchased. In some implementations applying the format data to the parsed data includes filtering the first parsed entry from the parsed data such that the first parsed entry is removed from the parsed data . Applying the format data to the parsed data may include decorating the second parsed entry by supplementing the second parsed entry with additional information. In some implementations applying the format data to the parsed data includes changing an order of the first record entry and the second record entry . Applying the format data to the parsed data may include converting the parsed data to a markup language.

At block the sink node performs a computational task using the event data . For example the sink node may use the event data to determine whether particular items have been purchased.

The sink node may include the sink configuration generation module configured to generate the sink configuration data . The sink configuration data may comprise information about configuring the processing system node . In the sink node provides the sink configuration data to the processing system node .

The processing system node includes the processing module configured to generate the event data . In the processing module provides the event data to the sink node . In this example the event data comprises information about success metrics which includes one or more quantitative measurements of the operation or performance of the computing devices . The success metrics may be generated as the record data described above. The success metrics may include various information. For example the success metrics may include data about user interactions with web pages. In another example the success metrics include data about whether a particular item has sold.

The sink node includes a treatment datastore configured to store treatment data . . . T . The treatment data may comprise various information which is configured to be processed by one or more computing devices . The treatment data may comprise a service response which is provided in response to a particular computing device requesting a service. In one example different treatment data comprise different web pages that are provided in response to a request for web page. The web pages may have differences such as differences in layouts color schemes content functionality and so forth. In another example as illustrated in the treatment data may comprise at least one of marketing data or code data .

The marketing data may comprise information which causes the computing device to present data in a particular configuration. For example the marketing data may comprise data causing the computing device to display a web page with an advertisement positioned at a bottom centered position of the display screen of the computing device . The code data may comprise information about a set of code or software configured to be processed by the computing device .

The record data may comprise data indicating a user selection of a displayed advertisement data indicating information was transferred to a particular computing device data indicating that an item was purchased or data indicating an occurrence of an error.

The computing devices may be implemented as the producer nodes described above. In one example the computing device is implemented as the producer node which is configured to provide the record data to the processing system node illustrated in .

In the sink node includes a treatment distribution module . The treatment distribution module may be configured to present one or more of the treatment data to the computing devices based on the event data . The event data may comprise information about configuring the sink node to change the treatment data provided to the computing device . For example at a first point in time the treatment distribution module provides a first web page to a first computing device . The first web page is configured to cause the first computing device to display an advertisement at a lower centered position. Thereafter the processing module analyzes user interactions with the first web page. The processing module may generate event data comprising information about changing the first web page to a second web page configured to display the advertisement at an upper right position of the display screen of the computing device . In one example the processing module may be configured to generate the event data that causes the change of the web page when a click through rate is equal to or less than a threshold value when the first web page is displayed.

In some implementations the system includes a web server not shown configured to provide the treatment data to the computing devices . In these implementations the web server includes the treatment datastore . In response to receiving request data from the web server the sink node may provide identification data to the web server. The identification data may be used to identify which treatment data to send to which computing device .

The first web page has various locations including a first location and a second location . In the computing device presents a first treatment at the first location of the first web page . The first treatment comprises an advertisement positioned at a lower centered location of the display screen of the computing device . In this example the advertisement states CLICK HERE FOR SPECIAL OFFERS. 

Referring to the second web page the computing device presents a second treatment at the second location of the second web page . The second treatment comprises an advertisement positioned at an upper right location of the display screen of the computing device . In this example the advertisement states CLICK HERE FOR SPECIAL OFFERS. 

The sink node may cause the computing device to change the display of the first treatment at the first location to the display of the second treatment at the second location based on an analysis of the event data . For example a historical analysis of the event data may indicate that a greater number of user clicks occur when an advertisement is displayed at the second location when compared to the advertisement being displayed at the first location . In another example a historical analysis of the event data may indicate that a greater number of errors are generated when an advertisement is displayed at the second location when compared to the advertisement being displayed at the first location .

In some implementations a first group of users is served web pages that remain unchanged over time and a second group of users is served web pages that undergo various changes over time. In this manner users in different groups view different web pages e.g. different layouts color schemes content functionality etc. and engage in different experiences with the web pages. The users interactions with the different web pages are tracked and analyzed in an effort to determine whether adjustments made to the web pages had an effect on user behavior.

The sink node includes at least one I O interface which enables portions of the sink node e.g. the hardware processor to communicate with other devices. The I O interface may include I2C SPI USB RS 232 HDMI TOSLINK Bluetooth and so forth. The at least one I O interface may be coupled to at least one I O device . In some implementations certain I O devices are physically incorporated within the sink node or externally placed.

The sink node may include at least one communication interface . The communication interface may be configured to provide communications between the sink node and other devices such as servers routers access points and so forth. The communication interface may connect to a network.

The sink node may include at least one bus or other internal communications hardware or software that enables the transfer of data between the various modules and components of the sink node .

As illustrated in the sink node may include at least one memory or memory device . The memory may include one or more non transitory CRSM. The CRSM may include at least one of an electronic storage medium a magnetic storage medium an optical storage medium a quantum storage medium a mechanical computer storage medium and so forth. The memory may include computer readable instructions data structures program modules and other data for the operation of the sink node .

The memory may include at least one OS module . The OS module may be configured to manage hardware resources such as the I O interfaces the I O devices the communication interfaces and provide various services to applications or modules executing on the hardware processor . The memory may also store at least one of the following modules which may be executed as foreground applications background tasks daemons and so forth.

The memory may include the sink configuration generation module configured to generate the sink configuration data . The sink configuration data may comprise information about configuring the processing system node .

The memory may include the event processor module configured to perform one or more computational tasks using the event data . In one example the computational task includes generating alarm data which indicates that a particular item has been sold at a predetermined rate. For example a particular database may indicate that an item has been selling at a rate of over fifty per day for the last week. In some implementations the event processor module comprises the treatment distribution module .

The memory may include the interface module that enables administrative users to operate with the sink node to generate the format data based on user input. In some implementations another computing device not shown includes the interface module that enables the administrative user to generate the format data based on user input.

The memory may include the treatment distribution module . As discussed above the treatment distribution module may be configured to present one or more of the treatment data to the computing devices based on the event data .

In some implementations the memory includes a datastore for storing information. The datastore may use a flat file database linked list code tree or other data structure to store the information. In some implementations the datastore or a portion thereof may be distributed across at least one other device such as another server a network storage device and so forth. As illustrated in the datastore may include the event data the treatment datastore the sink configuration data the filtered data the decorated data and the format data .

At block the sink node accesses first treatment data comprising a first web page . The first treatment data may comprise marketing data configured to cause a first computing device to display an advertisement at a first location of a display screen of the first computing device . In another example the first treatment data may include code data comprising a first set of code instructions or software. The sink node may be configured to compare different code data to determine which code data causes less errors.

At block the sink node provides the first treatment data to a first computing device configured to present the first web page . The sink node may provide the first treatment data to the first computing device based on an analysis of the event data . For example the analysis of the event data may indicate that when the first treatment data is presented by the first computing device a particular item sells at a predetermined threshold rate.

At block the processing system node accesses record data comprising first recorded information about user interactions with the first web page . In one example the user interactions may comprise information about whether a particular advertisement was clicked. In another example the user interactions may comprise information about whether a particular item was purchased.

At block the processing system node generates parsed data by transforming the record data . The parsed data is generated within a designated amount of time from a generation of the record data . The record data may comprise a first record entry comprising information about a first user interaction with the first web page and a second record entry comprising information about a second user interaction with the first web page . The processing system node may generate the parsed data by associating the first record entry with a first parsed entry and the second record entry with a second parsed entry .

At block the sink node generates format data comprising information about configuring the processing system node to format the parsed data . At block the sink node provides the format data to the processing system node . In other implementations the sink node provides the format data to the configuration node rather than the processing system node . As described above the processing system node may access the format data from the configuration node .

At block the processing system node generates event data by applying the format data to the parsed data . The event data includes information about configuring the sink node to provide second treatment data to the first computing device . In one example the parsed data comprises a first parsed entry and a second parsed entry . Applying the format data to the parsed data may include filtering the first parsed entry from the parsed data such that the first parsed entry is removed from the parsed data . Applying the format data to the parsed data may also include decorating the second parsed entry by supplementing the second parsed entry with additional information.

The second treatment data may comprise second marketing data that is configured to cause the first computing device to display an advertisement at a second location of the display screen of the first computing device .

At block the processing system node provides the event data to the sink node . At block the sink node terminates providing the first treatment data to the first computing device . At block the sink node accesses the second treatment data . At block the sink node provides the second treatment data to the first computing device .

At block the sink node accesses first treatment data comprising a service response. The service response may comprise data which is provided in response to a particular computing device requesting a service. For example the computing device may provide data to the sink node indicative of a request for a web page. The sink node may provide the service response which may include the first web page . The service response may include markup language data such as XML data.

At block the sink node provides the first treatment data to a first computing device configured to perform a computational task using the service response. In one example the sink node provides the treatment data to the computing device which is configured to present the first web page .

At block the processing system node accesses record data comprising recorded information about success metrics associated with the service response. In one example the success metrics include user interactions with the first web page . In another example the success metrics include data about the price at which an item has sold. The record data may comprise at least one of data about a user selection of a displayed advertisement data which indicates that information was transferred to a particular computing device data indicating an item was purchased or data indicating an occurrence of an error.

At block the processing system node generates parsed data by transforming the record data . The parsed data may be generated within a designated amount of time after the generation of the record data . In some implementations in response to a determination that the parsed data is not generated within a designated amount of time from the generation of the record data the processing system node causes another computing node to operate in cooperation with the processing system node . This additional computing node operates such that subsequently generated parsed data is generated within the designated amount of time. In some implementations once the determination is made the processing system node provides producer configuration data comprising information that causes the producer node to provide generated record data to the computing node operating in cooperation with the processing system node . The computing node operating in cooperation with the processing system node may be located within the processing system node . The designated amount of time may be determined based on a percentage. For example for a system which requires the parsed data or the event data to be generated within twenty seconds if the processing system determines that the parsed data or the event data will be generated in at least sixteen seconds i.e. eighty percent of twenty seconds then the processing system node may be configured to cause the computing node to operate in cooperation with the processing system node . In one example transforming the record data includes changing an order of the first record entry and the second record entry .

At block the processing system node generates event data by transforming the parsed data . The processing system node may transform the parsed data by applying format data to the parsed data . The format data may comprise information about configuring the processing system node to format the parsed data and may be generated based on user input. Applying the format data may include filtering one or more parsed entries from the parsed data such that the one or more parsed entries are removed from the parsed data . In another example applying the format data includes decorating the one or more parsed entries by supplementing the one or more parsed entries with additional information. In another example applying the format data includes converting the parsed data to a markup language. In some implementations the event data comprises the configuration data . The configuration data may comprise information about selecting one or a plurality of different treatment data .

At block the processing system node provides the event data to the sink node . At block the sink node analyzes the event data . At block the sink node automatically changes the first treatment data that is being provided to the first computing device to second treatment data based on the analysis of the event data . Automatically changing the treatment data may include changing the treatment data without any human interaction. In one example the sink node changes the first treatment data to the second treatment data in response to a determination that a click rate is equal to a less than a threshold value when the advertisement is displayed at the first location . By causing the sink node to analyze the click rates costs may be reduced. Costs may be reduced because the sink node may determine at a faster rate which treatments have higher click rates when compared to the amount of time in which users analyze the click rates and then cause the sink node to change to a relatively better treatment.

The analysis of the event data may include analyzing click through rates associated with the treatment data . For example the sink node may change from the treatment data to the treatment data because the click through rate for the treatment data is higher than the click through rate for the treatment data .

The analysis of the event data may include analyzing sales data associated with the treatment data . For example the sink node may change from the treatment data to the treatment data because the sales data for the treatment data indicates that items are sold at a higher rate when compared the rate for the treatment data .

In another example the analysis of the event data may include analyzing error data associated with the treatment data . For example the sink node may increase the percentage associated with the treatment data when compared to the percentage associated with the treatment data because less errors occur when the computing devices execute the treatment data than when the computing devices execute the treatment data .

In some implementations the analysis of the event data may include analyzing latencies associated with the treatment data . In one example the sink node increases the percentage associated with the treatment data when compared to the percentage associated with the treatment data because computing devices executing the treatment data load web pages faster than computing devices executing the treatment data .

In some implementations the treatment distribution module determines particular treatment data to provide to the computing devices based on percentages. For example the sink node may assign the treatment data with a first percentage of ninety percent and may assign the treatment data with a second percentage of ten percent. In this example the sink node provides the treatment data ninety percent of the time to the computing devices and provides the treatment data ten percent of the time to the computing devices . Over time if the treatment data becomes more successful when compared to the treatment data the sink node may be configured to automatically change the percentages assigned to the treatment data and . For example the sink node may increase the percentage assigned to the treatment data because the treatment data has a better success rate.

The processing system node may determine the percentages associated with the treatment data based on the analysis of the record data . The processing system node may provide the percentages to the sink node . Once the sink node receives the percentages the sink node may assign the percentages to the treatment data .

The producer node includes the record generation module configured to generate the record data . In this example the record data may comprise recorded information including unique identifier data comprising unique identifiers associated with a plurality of users. The record data may also include web browsing data comprising information about web browsing history associated with the unique identifiers. In the record generation module provides the record data to the processing system node . The producer node also includes a content generation module configured to generate content data . The content data may include audio data video data electronic book data application data game data and so forth.

The producer node may use a web browser having a plurality of different subsystems. The subsystems may include a networking subsystem a hypertext markup language subsystem a page rendering subsystem and so forth. In some implementations the producer node may execute one or more of the subsystems and the computing device may execute one or more of the subsystems.

The processing system node includes the processing module which is configured to generate the event data as described above. In one example the processing module generates the event data by applying the format data to the parsed data .

The crawling system node includes a crawler module configured to generate crawled data . The crawled data may comprise information about web pages. In the crawler module provides the crawled data to the classifying system node .

The classifying system node includes a recommendation module configured to generate recommendation data . The recommendation data may comprise information about at least one unique identifier associated with at least one recommended web address. In some implementations the recommendation module generates the recommendation data based on the event data the crawled data and association data . The association data may comprise data about thresholds and recommended web addresses. The classifying system node is communicatively coupled to the producer node . The classifying system node may be implemented as the sink node . In the recommendation module provides the recommendation data to the producer node in response to receiving recommendation request data comprising information that causes the recommendation module to provide the recommendation data .

In the computing device provides content request data to the producer node . The content request data comprises information configured to cause the producer node to provide the content data . In this example once the producer node receives the content request data the producer node provides the content data and the recommendation data to the computing device .

Once the content data and the recommendation data are received a content presentation module presents the content data and the recommendation data to a user of the computing device .

In some implementations the classifying system node may include an indexing module not shown . The indexing module may be configured to generate data that is used by the crawler module to generate the crawled data . In one example the indexing module generates an index to optimize speed and performance in finding relevant event data .

The classifying system node includes at least one I O interface which enables portions of the classifying system node e.g. the hardware processor to communicate with other devices. The I O interface may include I2C SPI USB RS 232 HDMI TOSLINK Bluetooth and so forth. The at least one I O interface may be coupled to at least one I O device . In some implementations certain I O devices are physically incorporated with the classifying system node or externally placed.

The classifying system node may include at least one communication interface . The communication interface may be configured to provide communications between the classifying system node and other devices such as servers routers access points and so forth. The communication interface may connect to a network.

The classifying system node may include at least one bus or other internal communications hardware or software that enables for the transfer of data between the various modules and components of the classifying system node .

As illustrated in the classifying system node may include at least one memory or memory device . The memory may include one or more non transitory CRSM. The CRSM may include at least one of an electronic storage medium a magnetic storage medium an optical storage medium a quantum storage medium a mechanical computer storage medium and so forth. The memory may include computer readable instructions data structures program modules and other data for the operation of the classifying system node .

The memory may include at least one OS module . The OS module may be configured to manage hardware resources such as the I O interfaces the I O devices the communication interfaces and provide various services to applications or modules executing on the hardware processor . The memory may also store at least one of the following modules which may be executed as foreground applications background tasks daemons and so forth.

The memory may include the sink configuration generation module configured to generate the sink configuration data . The sink configuration data may comprise information about configuring the processing system node .

The memory may include the event processor module configured to perform one or more computational tasks using the event data . The event processor module may comprise the recommendation module .

The memory may include the interface module that enables administrative users to operate with the classifying system node to generate the format data based on user input. In some implementations another computing device not shown includes the interface module that enables the administrative user to generate the format data based on user input.

The memory may include the recommendation module configured to generate the recommendation data . The recommendation module may generate the recommendation data based on the event data crawled data and association data .

In some implementations the memory includes a datastore for storing information. The datastore may use a flat file database linked list code tree or other data structure to store the information. In some implementations the datastore or a portion thereof may be distributed across at least one other device such as another server a network storage device and so forth. As illustrated in the datastore may include the event data the sink configuration data the filtered data the decorated data the format data the recommendation data and the association data . The event data may comprise information about data indicating a user selection of a displayed advertisement or data indicating a user selection of a displayed web address.

The events include the event entries . The event associated with event ID 1 comprises the following five event entries 1 Computer 1 2 User XYZ 3 2013 08 25 4 07 30 21 and 5 Accessed www.example.com . The event associated with event ID 2 comprises the following five event entries 1 Computer 1 2 User XYZ 3 2013 08 25 4 07 35 51 and 5 Accessed www.example.com first article . The event associated with event ID 3 comprises the following five event entries 1 Computer 1 2 User XYZ 3 2013 08 25 4 07 45 21 and 5 Accessed www.example.com second article . The event associated with event ID 4 comprises the following five event entries 1 Computer 2 2 User ABC 3 2013 08 27 4 10 57 24 and 5 Accessed www.example.com second article . The event entries may further comprise information about data indicating a user selection of a displayed advertisement or data indicating a user selection of a displayed web address.

The crawled data may comprise information about web pages. In the crawled data includes web addresses . The web addresses include illustration.com representative.com news.com and math.com .

The association data includes an association table . The columns of the association table include the following fields threshold and web addresses . The thresholds in the association table include the following values EXAMPLE.COM ACCESSED 2 and EXAMPLE.COM ACCESSED 10 . The thresholds are used by the recommendation module to determine whether to recommend any associated web addresses . For example based on the association table if the event data indicates that a user associated with a unique identifier has accessed example.com more than ten times the web addresses news.com and math.com would be recommended to a computing device associated with the unique identifier.

In the recommendation module generates the recommendation data by associating unique identifiers to the web addresses . For example the recommendation module associates the unique identifier USER XYZ to the web addresses ILLUSTRATION.COM and REPRESENTATIVE.COM because an analysis of the event data indicates that the threshold has been triggered. That is as illustrated by the event entries the USER XYZ has accessed the website example.com more than twice. As illustrated in the recommendation data comprises the user identifier User XYZ associated with web addresses illustration.com and representative.com . Once the recommendation data is generated the recommendation data may be provided to a computing device associated with the unique identifier.

In some implementations the classifying system node generates the association data based on the crawled data . For example the classifying system node may include a datastore configured to store previously collected crawled data which may include a collection of text data from a plurality of web pages. When the crawler module generates new crawled data based on a new web page having new text data the classifying system node may determine that the new web page includes a threshold amount of the same text data as some of the previously generated crawled data . Because the new web page is similar to one or more of the previously crawled web pages the classifying system node may generate new or updated association data that includes information associating the new web page with one or more previously crawled web pages.

The classifying system node may generate the association data based on behavior data which comprises information about user interactions with one or more web pages. In one example the classifying system node accesses behavior data that indicates a particular user associated with a first unique identifier spends a designated amount of time on a first web page and a second web page. In this example the classifying system node determines that a new user associated with a second unique identifier spends the designated amount of time on the first web page. Because the first user and the second user spend the designated amount of time on the first web page the classifying system node may generate association data which causes the second user to receive a recommendation that includes the second web page.

At block the producer node generates the record data including data about unique identifiers associated with a plurality of users and data about web browsing history associated with the unique identifiers .

At block the processing system node generates the parsed data by transforming the record data . The parsed data may be generated within a designated time period after the generation of the record data . In some implementations in response to a determination that the parsed data is not generated within a designated amount of time from the generation of the record data the processing system node causes another computing node to operate in cooperation with the processing system node such that subsequently generated parsed data is generated within the designated amount of time.

At block the processing system node generates the event data by transforming the parsed data . The processing system node may transform the parsed data by applying the format data to the parsed data . The format data may comprise information about configuring the processing system node to format the parsed data and may be generated based on user input. At block the processing system node provides the event data to the classifying system node .

At block the classifying system node accesses the crawled data comprising information about web pages. In some implementations the crawler system node provides the crawled data to the classifying system node .

At block the classifying system node accesses the association data comprising information about recommended web addresses and thresholds . The thresholds may comprise logic which is processed by the classifying system node to determine whether to associate a particular unique identifier to a particular web address . In some implementations the classifying system node generates the association data using the event data . For example based on a historical analysis of user interactions with a plurality of web pages the classifying system node may generate association data which includes information about grouping certain users together. The classifying system node may analyze behavior data that indicates a particular user associated with a first unique identifier spends a designated amount of time on a first web page and a second web page . In this example the classifying system node determines that a new user associated with a second unique identifier spends the designated amount of time of the first web page . Because the first user and the second user spend the designated amount of time on the first web page the classifying system node may generate association data that causes the second user to receive a recommendation that includes the second web page .

The classifying system node may generate the association data within a designated amount of time after the generation of the event data . For example the designated amount of time may be less than or equal to fifteen seconds.

At block the classifying system node generates the recommendation data using the event data the crawled data and the association data . At block the classifying system node provides the recommendation data to the producer node . At block the producer node provides the recommendation data to the computing device that is configured to access the web page using the recommendation data .

Those having ordinary skill in the art will readily recognize that certain steps or operations illustrated in the figures above can be eliminated or taken in an alternate order. Moreover the methods described above may be implemented as one or more software programs for a computer system and are encoded in a computer readable storage medium as instructions executable on one or more hardware processors.

Embodiments may be provided as a computer program product including a non transitory computer readable storage medium having stored thereon instructions in compressed or uncompressed form that may be used to program a computer or other electronic device to perform processes or methods described herein. The computer readable storage medium can be any one of an electronic storage medium a magnetic storage medium an optical storage medium a quantum storage medium and so forth. For example the computer readable storage media may include but is not limited to hard drives floppy diskettes optical disks read only memories ROMs RAMs EPROMs EEPROMs flash memory magnetic or optical cards solid state memory devices or other types of physical media suitable for storing electronic instructions. Further embodiments may also be provided as a computer program product including a transitory machine readable signal in compressed or uncompressed form . Examples of machine readable signals whether modulated using a carrier or not include but are not limited to signals that a computer system or machine hosting or running a computer program can be configured to access including signals transferred by one or more networks. For example the transitory machine readable signal may comprise transmission of software by the Internet.

Additionally those having ordinary skill in the art readily recognize that the techniques described above can be utilized in a variety of devices environments and situations.

at least one computing device configured to implement at least a first producer node a second producer node a processing system node and a sink node the processing system node including a first parse node and a second parse node wherein 

the first producer node is configured to generate first record data comprising first recorded information about one or more first activities 

the first producer node is configured to provide the first record data to the processing system node 

the second producer node is configured to generate second record data comprising second recorded information about one or more second activities the second record data being different in type from the first record data 

the second producer node is configured to provide the second record data to the processing system node 

the first parse node is configured to generate first parsed data by transforming according to one or more transformation functions the first record data wherein the first parsed data is generated in real time 

the processing system node is configured to allocate the second record data to the second parse node based on information included in the second record data 

the second parse node is configured to generate second parsed data by transforming according to one or more transformation functions the second record data the second parsed data being generated in real time 

the processing system node is configured to generate event data by transforming the first parsed data and the second parsed data 

in response to a determination that one or more of the first parsed data or the second parsed data is generated greater than real time the processing system node causes one or more computing devices to operate in cooperation with the processing system node such that subsequently generated parsed data is generated within real time.

Clause 2. The system of clause 1 wherein the processing system node is configured to generate first producer configuration data the processing system node is configured to provide the first producer configuration data to the first producer node the processing system node is configured to generate second producer configuration data the processing system node is configured to provide the second producer configuration data to the second producer node the first record data is generated based on the first producer configuration data and the second record data is generated based on the second producer configuration data.

Clause 3. The system of clauses 1 to 2 wherein the sink node is configured to generate sink configuration data comprising data about configuring the processing system node the sink node is configured to provide the sink configuration data to the processing system node the event data is generated based on the sink configuration data and the sink configuration data comprises at least one of 

endpoint data representing a request for the processing system node to provide the event data to the sink node 

percentage data representing a request for the processing system node to provide a percentage of the event data to the sink node or format data comprising data about configuring the processing system node to format the event data.

a first record entry comprising information about a first activity and a second record entry comprising information about a second activity wherein the first computing node comprises one or more first computing devices the one or more first computing devices comprising one or more first hardware processors and one or more first memory devices communicatively coupled to the one or more first hardware processors 

accessing by the first computing node first mapping data comprising data about mapping the first record entry and the second record entry 

accessing by the first computing node second mapping data comprising data about mapping the third record entry and the fourth record entry the second mapping data being configurable and different from the first mapping data 

generating by the first computing node first parsed data by transforming the first record data using the first mapping data the first parsed data comprising 

generating by the first computing node second parsed data by transforming the second record data using the second mapping data the second parsed data comprising 

generating by the first computing node event data by transforming the first parsed data and the second parsed data wherein a second computing node uses the event data to perform a computational task wherein the second computing node comprises one or more second computing devices the one or more second computing devices comprising one or more second hardware processors and one or more second memory devices communicatively coupled to the one or more second hardware processors.

Clause 5. The method of clause 4 wherein the first parsed data and the second parsed data are generated contemporaneously.

the first parsed data is generated within a designated amount of time after generation of the first record data and

the second parsed data is generated within the designated amount of time after generation of the second record data.

Clause 7. The method of clause 6 wherein the designated amount of time is less than or equal to fifteen seconds.

Clause 8. The method of clauses 4 to 7 further comprising in response to a determination that the first parsed data is generated in an amount of time exceeding a designated amount of time after a generation of the record data causing a third computing node to operate in cooperation with the first computing node such that subsequently generated parsed data is generated within the designated amount of time wherein the third computing node comprises one or more third computing devices the one or more third computing devices comprising one or more third hardware processors and one or more third memory devices communicatively coupled to the one or more third hardware processors.

Clause 9. The method of clauses 4 to 8 wherein the transforming the first record data using the first mapping data includes at least one of 

Clause 10. The method of clauses 4 to 9 wherein the first parsed data is generated by at least one of 

filtering the first record entry from the record data such that the first record entry is removed from the first record data or

providing by the first computing node the producer configuration data to the second computing node the second computing node being configured to generate the first record data using the producer configuration data the producer configuration data comprising at least one of 

endpoint data representing a request for the second computing node to provide the first record data to the first computing node 

percentage data representing a request for the second computing node to provide a percentage of the first record data to the first computing node or

protocol data representing a request for the second computing node to transmit the first record data to the first computing node using a designated transmission protocol.

generating by the second computing device primary data comprising a first primary data item and a second primary data item 

generating by the second computing node the first record data by removing one of the first primary data entry and the second primary data entry based on the producer configuration data and

accessing by a processing system node first record data comprising first recorded information about one or more first activities the processing system node comprising one or more first computing devices the processing system node including a first parse node and a second parse node 

allocating by the processing system node the first record data to the first parse node based on information included in the first record data 

accessing by the processing system node second record data comprising second recorded information about one or more second activities 

allocating by the processing system node the second record data to the second parse node based on information in the second record data 

generating by the first parse node first parsed data by transforming the first record data according to one or more transformation functions the first parsed data being generated within a first designated amount of time from a generation of the first record data and

generating by the second parse node second parsed data by transforming the second record data the second parsed data being generated within a second designated amount of time from a generation of the second record data.

providing by the processing system node the first parsed data and the second parsed data to a first sink node and a second sink node the second sink node being separate from the first sink node 

performing by the first sink node a first computational task using the first parsed data and the second parsed data and

performing by the second sink node a second computational task using the first parsed data and the second parsed data.

providing by a first producer node the first record data to the processing system node using a first transmission protocol the first producer node comprising one or more second computing devices and

providing by a second producer node the second record data to the processing system node using a second transmission protocol the second transmission protocol being different from the first transmission protocol the second producer node comprising one or more third computing devices.

the information in the first record data comprises first header data indicating a first type of the first record data and

the information in the second record data comprises second header data indicating a second type of the second record data the second type being different from the first type.

at least one computing device configured to implement at least a producer node a processing system node and a sink node wherein 

the processing system node is configured to access the record data the processing system node being communicatively coupled to the producer node 

the processing system node is configured to access mapping data comprising data about mapping the first record entry and the second record entry 

the processing system node is configured to generate parsed data by transforming the record data using the mapping data the parsed data being generated within a designated amount of time from the generation of the record data 

the sink node is configured to generate format data comprising data about configuring the processing system node to format the parsed data the sink node being communicatively coupled to the processing system node 

the processing system node is configured to generate event data by applying the format data to the parsed data 

Clause 22. The system of clause 21 wherein transforming the record data using the mapping data includes at least one of 

converting the first record entry to a first parsed entry the first parsed entry included in the parsed data or

converting the second record entry to a second parsed entry the second parsed entry included in the parsed data.

Clause 23. The system of clauses 21 to 22 wherein applying the format data to the parsed data includes at least one of 

filtering the first parsed entry from the parsed data such that the first parsed entry is removed from the parsed data or

decorating the second parsed entry by supplementing the second parsed entry with additional information.

a second record entry comprising information about a second activity wherein the first computing node comprises one or more first computing devices the one or more first computing devices comprising one or more first hardware processors and one or more first memory devices communicatively coupled to the one or more first hardware processors 

generating within a designated amount of time from the generation of the record data by the first computing node parsed data by transforming the record data 

accessing by the first computing node format data comprising data about configuring the first computing node to format the parsed data the format data being configurable and

generating by the first computing node event data by applying the format data to the parsed data wherein a second computing node is configured to perform a computational task based on the event data the second computing node comprising one or more second computing devices the one or more second computing devices comprising one or more second hardware processors and one or more second memory devices communicatively coupled to the one or more second hardware processors.

Clause 25. The method of clause 24 wherein the parsed data is generated at a rate which is greater than or equal to a rate at which record data is received.

Clause 26. The method of clauses 24 to 25 wherein transforming the record data using the mapping data includes changing an order of the first record entry and the second record entry.

Clause 27. The method of clauses 24 to 26 wherein generating the parsed data by transforming the record data includes associating 

the first record entry with a first parsed entry the first parsed entry included in the parsed data and

the second record entry with a second parsed entry the second parsed entry included in the parsed data.

Clause 28. The method of clauses 24 to 27 wherein applying the format data to the parsed data includes at least one of 

filtering the first parsed entry from the parsed data such that the first parsed entry is removed from the parsed data or

decorating the second parsed entry by supplementing the second parsed entry with additional information.

Clause 29. The method of clauses 24 to 28 wherein applying the format data to the parsed data includes changing an order of the first record entry and the second record entry.

Clause 30. The method of clauses 24 to 29 wherein applying the format data to the parsed data includes converting the parsed data to a markup language.

generating by the second computing node the format data wherein the format data is generated based on user input and

Clause 35. The method of clauses 24 to 34 wherein the parsed data is stored at a primary system memory.

generating by a sink node format data comprising data about configuring a processing system node to format event data the processing system node communicatively coupled to the sink node wherein the sink node comprises one or more first computing devices and the processing system node comprises one or more second computing devices 

generating by the processing system node the event data by applying the format data to record data comprising recorded information about one or more activities the event data being generated within a designated period of time from a generation of the record data 

Clause 38. The method of clauses 36 to 37 wherein the performance of the computational task includes 

generating alarm data indicating that the information was transferred to an unauthorized computing device.

Clause 39. The method of clauses 36 to 38 wherein the performance of the computational task includes determining that one or more items have been purchased.

Clause 40. The method of clauses 36 to 39 wherein the performance of the computational task includes 

generating alarm data indicating that the information was transferred to the unauthorized computing device.

one or more computing devices the one or more computing devices configured to implement one or more of a sink node and a processing system node wherein 

the sink node is configured to provide the first treatment data to at least one second computing device configured to present the first web page 

the processing system node is configured to access record data comprising first recorded information about user interactions with the first web page the processing system node being communicatively coupled to the sink node 

the processing system node is configured to generate parsed data by transforming the record data the parsed data being generated within a designated amount of time from a generation of the record data 

the sink node is configured to generate format data comprising data about configuring the processing system node to format the parsed data 

the processing system node is configured to generate event data by applying the format data to the parsed data the event data comprising data about configuring the sink node to provide second treatment data to the first computing device the second treatment data comprising a second web page the second web page being different from the first web page and

a first record entry comprising information about a first user interaction with the first web page and

a second record entry comprising information about a second user interaction with the first web page 

filtering the first parsed entry from the parsed data such that the first parsed entry is removed from the parsed data and

decorating the second parsed entry by supplementing the second parsed entry with additional information.

accessing by a first computing node first treatment data comprising a first service response the first computing node comprising one or more computing devices 

providing by the first computing node the first treatment data to one or more second computing devices configured to perform a computational task using the service response 

accessing by a second computing node record data comprising recorded information about success metrics associated with the service response the second computing node being communicatively coupled to the first computing node the second computing node comprising one or more third computing devices 

automatically changing by the first computing node the first treatment data that is being provided to the first computing device to second treatment data based on the analysis of the event data the second treatment data comprising a second service response.

Clause 45. The method of clause 44 wherein the parsed data is generated within a designated amount of time after a generation of the record data.

Clause 46. The method of clauses 44 to 45 wherein the success metrics comprise one or more quantitative measurements of an operation or performance of the one or more second computing devices.

Clause 47. The method of clauses 44 to 46 further comprising in response to a determination that a time to generate the parsed data relative to generation of the record data exceeds a threshold value causing a third computing node to operate in cooperation with the second computing node such that subsequently generated parsed data is generated within the designated amount of time.

transforming the record data includes changing an order of the first record entry and the second record entry.

generating by the first computing node format data comprising data about configuring the second computing node to format the parsed data and

providing by the first computing node the format data to the second computing node wherein generating the event data includes applying the format data to the parsed data.

the first treatment data comprises first marketing data configured to cause the first computing device to display an advertisement at a first location of a display screen of the computing device and

the second treatment data comprises second marketing data configured to cause the first computing device to display the advertisement at a second location of the display screen.

Clause 54. The method of clauses 44 to 53 wherein the first computing node changes the first treatment data to the second treatment data in response to a determination that a click rate is equal to or less than a threshold value when the advertisement is displayed at the first position.

accessing by a first computing node record data comprising recorded information about one or more first activities the first computing node comprising one or more first computing devices the one or more first computing devices comprising one or more first hardware processors and one or more first memory devices communicatively coupled to the one or more first hardware processors 

generating by the first computing node parsed data by transforming the record data the parsed data being generated within a designated amount of time after a generation of the record data 

accessing by the first computing node format data comprising data about configuring the first computing node to format the parsed data 

generating by the first computing node configuration data by applying the format data to the parsed data the configuration data comprising data about selecting one of a plurality of different treatment data the plurality of different treatment data comprising a plurality of different web pages 

providing by the first computing node the configuration data to a second computing node communicatively coupled to the first computing node the second computing node comprising one or more second computing devices the one or more second computing devices comprising one or more second hardware processors and one or more second memory devices communicatively coupled to the one or more second hardware processors 

automatically selecting by the second computing node one of the plurality of different treatments based on the configuration data and

Clause 59. The method of clause 58 wherein the parsed data is generated within a designated amount of time after a generation of the record data based on the first computing node not storing the record data at a datastore a buffer or a cache.

Clause 60. The method of clauses 58 to 59 wherein the parsed data is generated within a designated amount of time after a generation of the record data based on processing the record data when the processing system node receives the record data.

generating by a producer node record data comprising recorded information the recorded information including 

web browsing data comprising information about web browsing history associated with the unique identifiers wherein the producer node comprises one or more first computing devices the one or more first computing devices comprising one or more first hardware processors and one or more first memory devices communicatively coupled to the one or more first hardware processors 

accessing by a processing system node the record data wherein the processing system node is communicatively coupled to the producer node the processing system node comprising one or more second computing devices the one or more second computing devices comprising one or more second hardware processors and one or more second memory devices communicatively coupled to the one or more second hardware processors 

generating by the processing system node parsed data by transforming the record data the parsed data being generated within a designated time period after the generation of the record data 

providing by the processing system node the event data to a classifying system node wherein the classifying system is communicatively coupled to the processing system node and the producer node the classifying system node comprising one or more third computing devices the one or more third computing devices comprising one or more third hardware processors and one or more third memory devices communicatively coupled to the one or more third hardware processors 

generating by a crawling system node crawled data comprising information about web pages wherein the crawling system node is communicatively coupled to the classifying system node the crawling system node comprising one or more fourth computing devices the one or more fourth computing devices comprising one or more fourth hardware processors and one or more fourth memory devices communicatively coupled to the one or more fourth hardware processors 

accessing by the classifying system node association data comprising data about thresholds and recommended web addresses 

generating by the classifying system node recommendation data using the event data the crawled data and the associated data the recommendation data comprising at least one unique identifier associated with at least one recommended web address 

providing by the producer node the recommendation data to a computing device configured to access the at least one recommended web address using the recommendation data.

a second record entry comprising information about web browsing history associated with the first unique identifier 

generating by the classifying system node format data comprising data about configuring the processing system node to format the parsed data and

providing by the classifying system node the format data to the processing system node wherein generating the event data includes applying the format data to the parsed data.

generating by a first computing node parsed data using record data comprising recorded information the first computing node comprising one or more first computing devices 

generating by the first computing node event data by applying format data to the parsed data the format data being configurable the event data comprising data about unique identifiers associated with a plurality of users and data about web browsing history associated with the unique identifiers 

accessing by a second computing node the event data the second computing node comprising one or more second computing devices 

accessing by the second computing node association data comprising data about thresholds and recommended web addresses 

generating by the second computing node recommendation data using the event data the crawled data and the association data the recommendation data including 

data representative of at least one recommended web addresses which is associated with the at least one of the unique identifiers and

causing one or more third computing devices to receive the recommendation data the one or more third computing devices being configured to access the recommended web address.

Clause 65. The method of clause 64 wherein the parsed data is generated within a designated amount of time after a generation of the record data.

Clause 66. The method of clauses 64 to 65 further comprising in response to a determination that the parsed data is not generated within a designated amount of time from a generation of the record data causing a third computing node to operate in cooperation with the first computing node such that subsequently generated parsed data is generated within the designated amount of time the third computing node comprising one or more fourth computing devices.

a second record entry comprising information about web browsing history associated with the first unique identifier and

transforming the record data includes changing an order of the first record entry and the second record entry.

generating by the second computing node the format data wherein the format data comprises information about configuring the first computing node to format the parsed data and

providing by the second computing node the format data to the first computing node wherein the event data is generated by applying the format data to the parsed data.

Clause 69. The method of clauses 64 to 68 wherein the parsed data comprises a first parsed entry and a second parsed entry and

filtering the first parsed entry from the parsed data such that the first parsed entry is removed from the parsed data and

decorating the second parsed entry by supplementing the second parsed entry with additional information.

Clause 70. The method of clauses 64 to 69 wherein applying the format data to the parsed data includes converting the parsed data to a markup language.

Clause 75. The method of clauses 64 to 74 wherein the computing device receives the recommendation data in response to providing a request for content to a web server.

Clause 76. The method of clauses 64 to 75 further comprising generating by the second computing node the association data using the event data wherein 

the association data is generated within a designated amount of time after a generation of the event data and

Clause 77. The method of clauses 64 to 76 further comprising generating by a third computing node the record data the third computing node using a web browser which includes a first subsystem and a second subsystem wherein 

the record data comprises information indicating user selections of a plurality of different web pages.

accessing by a processing system node record data comprising recorded information the processing system node comprising one or more computing devices 

generating by the processing system node parsed data using the record data the parsed data being generated within a designated time period after a generation of the record data 

accessing by the processing system node format data comprising data about configuring the processing system node to format the parsed data 

generating by the processing system node event data using the parsed data and the format data the event data comprising data about unique identifiers associated with a plurality of users and data about web browsing history associated with the unique identifiers and

providing by the processing system node the event data to a sink node communicatively coupled to the processing system node the sink node configured to generate recommendation data using the event data the recommendation data comprising data representative of at least one of the unique identifiers and data representative of at least one recommended web address which is associated with the at least one of the unique identifiers wherein the sink node comprises one or more second computing devices.

Clause 79. The method of clause 78 wherein the one or more first computing devices comprise one or more hardware processors and one or more memory devices communicatively coupled to the one or more hardware processors.

Clause 80. The method of clauses 78 to 79 the recommendation data being generated within a designated amount of time after a generation of the record data.

Although the present disclosure is written with respect to specific embodiments and implementations various changes and modifications may be suggested to one skilled in the art and it is intended that the present disclosure encompasses such changes and modifications that fall within the scope of the appended claims.

