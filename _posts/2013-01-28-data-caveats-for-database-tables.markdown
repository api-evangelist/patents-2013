---

title: Data caveats for database tables
abstract: A method for storing data caveats for databases is described. The method includes storing at least one record in at least one content table in a database. The method includes storing at least one data caveat having a relationship to the content table in at least one record in a caveat table. A data caveat has a relationship to the content table when the data caveat applies to: a record in the content table or the content table in entirety. The method also includes storing, in a memory device, an indication of the relationship. Articles of manufacture are also described.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08990205&OS=08990205&RS=08990205
owner: International Business Machines Corporation
number: 08990205
owner_city: Armonk
owner_country: US
publication_date: 20130128
---
The exemplary embodiments relate generally to data storage and more specifically relate to storing data caveats for databases.

This section is intended to provide a background or context. The description herein may include concepts that could be pursued but are not necessarily ones that have been previously conceived or pursued. Therefore unless otherwise indicated herein what is described in this section is not prior art to the description and claims in this application and is not admitted to be prior art by inclusion in this section.

Databases may be used to store data. Some metadata such as data about the structure of the data may also be stored. However this type of structural metadata does not provide a full understanding of the data in the database. Metacontent is a type of metadata which provides information about the data content itself. Such metacontent enables future users to appreciate additional aspects of the data such as the process used to collect the data.

In an exemplary aspect a method for storing data caveats that is warnings or qualifications about the data or use of the data for database tables is provided. The method includes storing at least one data field in at least one table in a database. The method includes storing at least one data caveat having a relationship to one or more database tables in at least one record in a caveat table. A data caveat has a relationship to one or more database tables when the data caveat applies to one or more records in one or more database tables in the database. The method also includes storing in a memory device an indication of the relationship.

In another exemplary aspect an article of manufacture for storing data caveats for database tables is provided. The article of manufacture is tangibly embodying computer readable non transitory instructions which when implemented cause a computer to carry out the steps of a method. The method includes storing at least one data field in at least one table one or more database tables. The method includes storing at least one data caveat having a relationship to one or more database tables in at least one record in a caveat table. A data caveat has a relationship to one or more database tables when the data caveat applies to one or more records in one or more database tables in the database. The method also includes storing in a memory device an indication of the relationship.

As a non limiting example the data access manager also communicates with a JDBC API in order to access caveat tables and content tables . The caveat tables and the content tables may be stored on separate memory devices or on the same memory device.

The data access manager represents an API dealing with data persistence. The data access manager can be a simple wrapper of a JDBC Connection or a more complex interface that implements Java bean persistence.

Databases such as may be used to store data and metadata about the structure of the data. In accordance with an exemplary embodiment information about the instances of the data such as data about data content or content about content for example may also be maintained. Such information about content or metacontent may include for example what was the procedure for collecting the data did this procedure change over the collection period were there any constraints imposed during the collection of the data etc. This sort of metacontent for a set of data will depend on the data itself and will likely change over time. The metacontent captures whatever information is important to ensure that data will be well understood by future users. It can also be used to identify which data was included or excluded for a particular type of analysis.

Various exemplary embodiments enable the data access manager to identify relevant information for an entire table or to explicitly flag records with a multi bit mask which would indicate which of any number of caveats apply to the entry. Each bit of the mask may be associated with a particular caveat which could be detailed in another table in the database such as caveat table . Such a flag would make it easy for a potential user such as client to have a clear understanding about the data and reduce the probability of that user misinterpreting the data due to a lack of understanding of the data itself.

At point the client sends data and a caveat to the data access manager for storing. As a non limiting example the data and caveat are sent in a single message however the data may be sent in one message and the caveat may be sent in separate message. The data access manager provides at point the data to the DB for storage in the content table at point and provides at point the data such as a caveat to the DB for storage in the caveat table at point . The data access manager may also add fields to the data and or caveat in order to indicate a relationship between the data and caveat. As a non limiting example the data access manager may add a field to the content record indicating which caveats in the caveat table apply to that entry and or a field to the caveat record indicating which content tables the caveat either applies to or have data entries to which the caveat applies.

At some later time at point the client sends a query to the data access manager . The data access manager processes the query such as by reference to a SQL converter for example . Based on the processed query the data access manager accesses the DB at point . Next the DB accesses the content table at point and caveat table at point in order to retrieve information sufficient to create the query result which is returned to the data access manager at point . At point the data manger provides a query response to the client .

As a non limiting example Tables 1 3 show two content tables Table 1 and Table 2 and a related caveat table Table 3 . Table 1 shows a table named Timing 

As shown each record in the table has a number of fields for various data elements such as a Unique ID an Entry ID an Activity Type an Activity etc. Additionally each entry includes a Timing Caveats field holding an eight bit byte. Each bit corresponds to a caveat in a caveat table.

Similar to Table 1 each record in the table has a number of fields including an eight bit field corresponding to caveats in a caveat table.

Similar to the records in Table 1 and Table 2 the records in Table 3 include a number of fields for various data elements. However in contrast to the data in Table 1 or Table 2 various fields in Table 3 provide information regarding caveats that apply to the content of the data in the other tables Table 1 and Table 2 .

The field Table provides an indication of which database table the record is related to. A record relates to a database table when the caveat of the record applies to the table as a whole table wide or to at least one entry in the table. The Field Name field provides an indication of a named field in the related database table for example a value of Timing Caveats indicates the Timing Caveats field in the Timing table Table 1 . The Bit field indicates which bit in the indicated field corresponds to the record. The Data and Description fields provide information regarding the caveat record such as changes in teams which enter data and when such changes occurred for example. The Description field may be used to provide specific information regarding the caveat or bit in the caveat.

A value of in the Table field indicates the caveat applies to all the tables in the database. A value of in the Field Name field indicates the caveat applies to all the fields in the database table or database in the case that the value of Table is also . When the Field Name has a value of there is no need to specify a value for the Bit field.

Data caveats can be used to capture information in order that data can be well understood by future users of that data. Caveats may be used to provide users with information regarding how data was captured which is important when performing analysis of the data and data collection processes. Caveats can also be used to identify which data was included or excluded for a particular type of analysis. This enables subsequent analysis to ensure use of the same data.

Using a caveat table such as Table 3 for example various exemplary embodiments provide a method for tagging structured data with unstructured information such as data caveats . The metacontent may be created for data using a structured technique such as a metacontent to SQL syntax for a direct SQL implementation as a non limiting example or the metacontent may be added in a more free form.

In a non limiting example each entry in a database table is flagged with a multi bit mask indicating which caveats apply to the data. Each bit of the mask is associated with a particular caveat detailed in another database table. These caveats may be created at data collection time or added prior to publication of the data. Various caveats may apply table wide such that the caveat applies to all entries in the table. Such table wide caveats may be indicated without being part of the multi bit mask in order to avoid excess repetition as a non limiting example a table wide caveat may be indicated by being omitted from the multi bit mask .

By providing accessible fields in the content tables and caveat tables the data may be seamlessly queried in regards to the caveats and likewise the data entries may be queried with a certain set of caveats. For example a user may request a list of all caveats that apply to a given entry. Such a search may or may not omit table wide caveats based on the user s preferences. In another non limiting example a user may wish to see to which records a specific caveat applies.

A final field is present that indicates which if any caveats in the caveat table apply to that entry. As a non limiting example field may include a multi bit field such as an 8 bit byte where each bit corresponds to a specific caveat. In one embodiment a bit value of 1 indicates that the caveat corresponding to that bit applies to the data entry and a value of 0 indicates that the caveat corresponding to that bit does not apply to the data entry.

The caveat table stores data regarding various caveats that apply to various records in the content table or to the content table in whole table wide . Each record in the caveat table has a field for a Caveat Id to identify the record and a field for Table indicating to which content table s the record relates.

Records in the caveat table also include a field named Field which may be used to distinguish caveats that relate to individual records in the indicated table. The example has a value Caveats for this field. A value of for Field indicates that the caveat relates to the content table in whole. For those records which relate to individual records of the content table s a field named Bit indicates which bit in field pointed to by value of Field of the content table indicate whether or not the caveat applies to that record. In a non limiting example the value represents the number of bits to the left of the right most bit is used. Such that a value of 0 indicates the right most bit and a value of 2 indicates the third bit to the left shown with an X in the following byte 00000 00 .

The field named Date contains the date at which the caveat took effect. The Field named Description contains a description of the caveat that is the information which future consumers of the data should know to properly use the data.

As shown the content table entry with a Timing Id value of 4 corresponds to a Team meeting activity for the Green team on Oct. 12 2011 which lasted 60 minutes. The caveat field has a value of 7 which corresponds to the byte 0000 0111. Each bit in the byte can relate to a caveat record in the caveat table . In this example since bits and have values of 1 Caveat Id records and apply to the entry.

A user may request from the data access manager information regarding the stored data. Using SQL language as a non limiting example the user via the client may request a list of caveats for the whole table using the following command 

In order to request records that match certain caveats such as by having the caveat apply to that record the user may use the command 

In accordance with SQL language as a non limiting example the commands may be written using alternative commands for example the following commands would also be acceptable to request records that match certain caveats 

In accordance with SQL language commands as a non limiting examples may also be used to update entries 

As a non limiting example data access manager may receive an SQL command SELECT FROM Timing WITH CAVEATS 2 3 . This command requests all data entries from the Timing content table which have caveats 2 and 3 as identified in the Caveat ID field applied to the entries.

Referring to circle highlights the Caveat ID fields for caveats 2 and 3 . These records arc indicated by bit for caveat 2 and bit for caveat 3 shown by circle .

The JDBC API may consult the Caveat table to identify which bits identify an entry as having caveats 2 and 3 applied to it as seen above this would be bits and . Next the JDBC API accesses Timing table as specified by value of Timing in field in order to find all entries which have bits and flagged that is showing a value of 1 in the field named Caveats as specified in the field . Circle highlights the 0 and 1 bits in the Caveats field byte for Timing ID entry 4. This indicates that Timing ID entry 4 has at least caveats 2 and 3 applied to it and thus satisfies the query. As the other entries do not satisfy the query JDBC API may return a reference to Timing ID entry 4 as a response to the query.

The above example is but one non limiting embodiment. In an alternative embodiment caveats for each table are stored in a caveat table having primary key columns and caveat columns and or the caveat column is combined with primary key PK column such that 8 bits of the PK represent the caveats as non limiting examples . There can be one cavear table per content table or a single caveat table for multiple content tables with an extra column to reference the content table . The caveat column may use a data type that can contain more bits such as a LONG VARCHAR FOR BIT DATA for example .

In another alternative embodiment caveat definitions can be applied to more than one table. For example the Caveat table may be replaced by two tables a caveat definition table such as a table having fields for ID Date and Definition for example and a relationship table such as a table having fields for Caveat Id Table Field and Bit for example .

Reference is made to for illustrating a simplified block diagram of various electronic devices and apparatus that are suitable for use in practicing exemplary embodiments. For example computer may be used to control a lithography process in accordance with an exemplary embodiment.

The computer includes a controller such as a computer or a data processor DP and a computer readable memory medium embodied as a memory MEM that stores a program of computer instructions PROG .

The PROGs is assumed to include program instructions that when executed by the associated DP enable the device to operate in accordance with exemplary embodiments as will be discussed below in greater detail.

That is various exemplary embodiments may be implemented at least in part by computer software executable by the DP of the computer or by hardware or by a combination of software and hardware and firmware .

The computer readable MEM may be of any type suitable to the local technical environment and may be implemented using any suitable data storage technology such as semiconductor based memory devices flash memory magnetic memory devices and systems optical memory devices and systems fixed memory and removable memory. The DP may be of any type suitable to the local technical environment and may include one or more of general purpose computers special purpose computers microprocessors digital signal processors DSPs and processors based on a multicore processor architecture as non limiting examples.

The exemplary embodiments as discussed herein and as particularly described with respect to exemplary methods may be implemented in conjunction with a program storage device such as at least one memory for example readable by a machine tangibly embodying a program of instructions such as a program or computer program for example executable by the machine for performing operations. The operations comprise steps of utilizing the exemplary embodiments or steps of the method.

The exemplary embodiments may be carried out by computer software implemented by the DP or by hardware or by a combination of hardware and software. As a non limiting example the exemplary embodiments may be implemented by one or more integrated circuits. The MEM may be of any type appropriate to the technical environment and may be implemented using any appropriate data storage technology such as optical memory devices magnetic memory devices semiconductor based memory devices fixed memory and removable memory as non limiting examples. The DP may be of any type appropriate to the technical environment and may encompass one or more of microprocessors general purpose computers special purpose computes and processors based on a multi core architecture as non limiting examples.

The various blocks shown in may be viewed as method steps and or as actions that result from operation of computer program code and or as a plurality of coupled logic circuit elements constructed to carry out the associated function s .

The blocks shown in further may be considered to correspond to one or more functions and or operations that are performed by one or more components circuits chips apparatus processors computer programs and or function blocks. Any and or all of the above may be implemented in any practicable solution or arrangement that enables operation in accordance with the exemplary embodiments as described herein.

In addition the arrangement of the blocks depicted in should be considered merely exemplary and non limiting. It should be appreciated that the blocks shown in may correspond to one or more functions and or operations that may be performed in any order such as any suitable practicable and or feasible order for example and or concurrently such as suitable practicable and or feasible for example so as to implement one or more of the exemplary embodiments. In addition one or more additional functions operations and or steps may be utilized in conjunction with those shown in so as to implement one or more further exemplary embodiments.

That is the exemplary embodiments shown in may be utilized implemented or practiced in conjunction with one or more further aspects in any combination such as any combination that is suitable practicable and or feasible for example and are not limited only to the steps blocks operations and or functions shown in .

Below are further descriptions of various non limiting exemplary embodiments. The below described exemplary embodiments are numbered separately for clarity purposes. This numbering should not be construed as entirely separating the various exemplary embodiments since aspects of one or more exemplary embodiments may be practiced in conjunction with one or more other aspects or exemplary embodiments.

The exemplary embodiments as discussed herein and as particularly described with respect to exemplary methods may be implemented in conjunction with a program storage device such as at least one memory for example readable by a machine tangibly embodying a program of instructions such as a program or computer program for example executable by the machine for performing operations. The operations comprise steps of utilizing the exemplary embodiments or steps of the method.

Any use of the terms connected coupled or variants thereof should be interpreted to indicate any such connection or coupling direct or indirect between the identified elements. As a non limiting example one or more intermediate elements may be present between the coupled elements. The connection or coupling between the identified elements may be as non limiting examples physical electrical magnetic logical or any suitable combination thereof in accordance with the described exemplary embodiments. As non limiting examples the connection or coupling may comprise one or more printed electrical connections wires cables mediums or any suitable combination thereof.

An exemplary embodiment provides a method for storing data caveats for databases. The method includes storing such as in a memory for example at least one record in at least one content table. The method includes storing such as in a memory for example at least one data caveat having a relationship to a content table in at least one record in a caveat table. A data caveat has a relationship to a content table when the data caveat applies to a record in the content table or to the content table in entirety. The method also includes storing such as in a memory for example in a memory device an indication of the relationship.

In a further exemplary embodiment of the method above the at least one data caveat applies to a content table. The indication of the relationship is embodied in the fields in the caveat table.

In another exemplary embodiment of any one of the methods above the at least one data caveat applies to the at least one record in a content table or at least one table. The indication of the relationship is embodied in a field in the record in the data caveat table and if the relationship is to specific records in the content table in the at least one field in records of the content table s . The field may include at least one bit and each of the at least one bit corresponds to a record in the caveat table.

In a further exemplary embodiment of any one of the methods above storing the at least one data caveat includes adding a record to the caveat table. Storing the indication of the relationship to specific records in a content table includes changing at least one bit in a field in a record in the content table.

In another exemplary embodiment of any one of the methods above each record in the caveat table includes a field indicating a content table associated with the data caveat in the record. A content table is associated with a data caveat when the data caveat has a relationship to the content table.

In a further exemplary embodiment of any one of the methods above the method also includes receiving the at least one data caveat with the at least one data record.

In another exemplary embodiment of any one of the methods above the method also includes receiving the at least one data record at a first time and receiving the at least one data caveat at a second subsequent time.

In a further exemplary embodiment of any one of the methods above the method also includes receiving a query and responding to the query based at least in part on the caveat table s and the content table s . The query may be a structured query language SQL query.

Another exemplary embodiment provides an article of manufacture for storing data caveats for databases. The article of manufacture is tangibly embodying computer readable non transitory instructions which when implemented cause a computer to carry out the steps of a method. The method includes storing at least one data element in at least one entry in a database. The method includes storing at least one data caveat having a relationship to the database in at least one record in a caveat table. A data caveat has a relationship to the database when the data caveat applies to a record in the content table or the content table itself. The method also includes storing in a memory device an indication of the relationship.

In a further exemplary embodiment of the article of manufacture above the at least one data caveat applies to at least one content table. The indication of the relationship is embodied in a field in the caveat table.

In another exemplary embodiment of any one of the articles of manufacture above the at least one data caveat applies to the at least one content table. The indication of the relationship to one or more specific records in a content table is embodied in a field in the at least one entry in the content table. The field may include at least one bit and each of the at least one bit corresponds to a record in the caveat table.

In a further exemplary embodiment of any one of the articles of manufacture above storing the at least one data caveat includes adding a record to the caveat table. Storing the indication of the relationship to specific records in a content table includes changing at least one bit in a field in an entry in the content table.

In another exemplary embodiment of any one of the articles of manufacture above each record in the caveat table includes a field indicating a database associated with the data caveat in the record. A content table is associated with a data caveat when the data caveat has a relationship to the content table.

In a further exemplary embodiment of any one of the articles of manufacture above the method also includes receiving the at least one data caveat with the at least one data record.

In another exemplary embodiment of any one of the articles of manufacture above the method also includes receiving the at least one data record at a first time and receiving the at least one data caveat at a second subsequent time.

In a further exemplary embodiment of any one of the articles of manufacture above the method also includes receiving a query and responding to the query based at least in part on the caveat table s and the content table s . The query may be a structured query language query.

Generally various exemplary embodiments can be implemented in different mediums such as software hardware logic special purpose circuits or any combination thereof. As a non limiting example some aspects may be implemented in software which may be run on a computing device while other aspects may be implemented in hardware.

The foregoing description has provided by way of exemplary and non limiting examples a full and informative description of the best method and apparatus presently contemplated for carrying out various exemplary embodiments. However various modifications and adaptations may become apparent to those skilled in the relevant arts in view of the foregoing description when read in conjunction with the accompanying drawings and the appended claims. However all such and similar modifications will still fall within the scope of the teachings of the exemplary embodiments.

Furthermore some of the features of the preferred embodiments could be used to advantage without the corresponding use of other features. As such the foregoing description should be considered as merely illustrative of the principles and not in limitation thereof.

The following abbreviations that may be found in the specification and or the drawing figures are defined as follows 

