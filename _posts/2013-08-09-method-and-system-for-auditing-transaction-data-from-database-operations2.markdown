---

title: Method and system for auditing transaction data from database operations
abstract: A method for validating SRS registry transaction data includes receiving OLTP transaction data from a first database, parsing the OLTP transaction data, and comparing the parsed OLTP transaction data to one or more of a set of profiles. Each of the one or more of the set of profiles includes metadata in XML files. The method also includes caching the parsed OLTP transaction data in a first data cache, receiving log data associated with the OLTP transaction data; and caching the log data in a second data cache. The method further includes correlating the parsed transaction data cached in the first data cache with the log data cached in the second data cache.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09535971&OS=09535971&RS=09535971
owner: VERISIGN, INC.
number: 09535971
owner_city: Reston
owner_country: US
publication_date: 20130809
---
The internet is an increasingly international network of computers that supports various forms and levels of communication. For instance on the world wide web WWW information can be presented on universally available pages commonly known as websites. The internet also supports one on one communication between end users via electronic email and or internet bulletin board services. The common denominator in every form of communication over the internet however is the use of domain names to identify the computer to be contacted. The domain name which is referred to as an internet protocol IP number is actually a unique combination of numbers separated by decimal points.

Because IP numbers can be cumbersome and difficult for internet users to remember or use the IP numbering system has been overlaid with the more user friendly domain name system. This system allows internet addresses to be assigned an alphanumeric designation or domain name which directly correlates to the assigned IP number. Special computers known as domain name servers maintain tables linking domain names to their respective IP numbers.

The anatomy of a domain name consists of more than two parts called domain levels separated by a period referred to as a dot . The Top Level Domain level TLD which is referred to by its internet zone designation .com or .gov. .uk etc. is found to the right of the dot. TLDs which represent a specific country are referred to as Country Code TLDs or cTLDs. The Second Level Domain SLD or Third Level Domain which is commonly referred to as the domain name consists of characters including letters numbers and hyphens located immediately to the left of the dot.

For the domain name address system to operate properly each domain name within a particular TLD must be unique even if it differs from another domain name by only one character. In order to prevent duplicate domain names from being assigned a single entity commonly referred to as a registry is ultimately responsible for maintaining a complete database of all of the domain names in each particular TLD. This database is referred to as a registry database. In the majority of generic e.g. .com .net .org domain name registrations there is little or no human intervention in the registration process. The registry database maintained by the registry electronically records the assigned relationship between the more easily remembered domain name and its corresponding IP number received from an international entity tasked with assigning all IP numbers and reports this information to the TD registry for recordation in the master database of all domain names. The registrar also enters into a registration agreement contract with each registrant and records and maintains vital registrant contact and billing information.

Due to the vital role domain names play in internet communication the easy immediate secure and dependable registration and maintenance of domain names is necessary to the continued rapid growth of the internet. Thus there is a need in the art for improved methods and systems related to auditing and validation of transactions associated with registry databases.

The present invention relates generally to database systems. More specifically the present invention relates to methods and systems for auditing transactions performed in a registry database. Merely by way of example the invention has been applied to a system that validates transaction data using profiles describing registry operations and compares the validated transaction data to transaction log files. The methods and techniques can be applied to other high value database systems to verify data integrity.

According to an embodiment of the present invention a method for validating SRS registry transaction data is provided. The method includes receiving OLTP transaction data from a first database parsing the OLTP transaction data and comparing the parsed OLTP transaction data to one or more of a set of profiles. Each of the one or more of the set of profiles comprises metadata in XML files. The method also includes caching the parsed OLTP transaction data in a first data cache and receiving log data associated with the OLTP transaction data. The method further includes caching the log data in a second data cache and correlating the parsed transaction data cached in the first data cache with the log data cached in the second data cache.

According to another embodiment of the present invention a method for validating transaction data is provided. The method includes receiving the transaction data from a first database and parsing the transaction data. The method also includes comparing the parsed transaction data to one or more of a set of profiles and receiving log data associated with the transaction data. The method further includes correlating the parsed transaction data with the log data.

According to a specific embodiment of the present invention a system for validating transaction data associated with an SRS registry database with transaction log files stored in a transaction log database is provided. The system includes a database reader operable to receive OLTP transaction data from the SRS registry database and parse the OLTP transaction data and a database data validator coupled to the database reader and operable to compare the parsed OLTP transaction data with one or more of a set of profiles. The system also includes a transaction log file reader operable to receive transaction log files from the transaction log database and a data correlator coupled to the database data validator and the transaction log file reader and operable to correlate the parsed transaction data with the transaction log files.

According to another specific embodiment of the present invention a computer readable medium storing a plurality of instructions for controlling a data processor to validate transaction data is provided. The plurality of instructions includes instructions that cause the data processor to receive the transaction data from a first database and instructions that cause the data processor to parse the transaction data. The plurality of instructions also includes instructions that cause the data processor to compare the parsed transaction data to one or more of a set of profiles and instructions that cause the data processor to receive log data associated with the transaction data. The plurality of instructions further includes instructions that cause the data processor to correlate the parsed transaction data with the log data.

Many benefits are achieved by way of the present invention over conventional techniques. For example embodiments of the present invention provide operations staff with alerts when any changes to the SRS registry database are performed outside of known applications. Thus information related to malicious activity associated with the registry database is provided by the embodiments described herein. Moreover embodiments of the present invention provide registry database operators with a competitive advantage over business competitors since validation of registry data enhances the integrity of the data. By utilizing the methods and systems described herein system operators are able to detect intruders and malicious activity more easily and quickly thereby limiting potential damage to the registry database. Furthermore utilizing embodiments of the present invention operations staff are able to identify the origin of every transaction that manipulates data within the database thus the security auditor establishes a chain of trust between the application and database. Additionally embodiments of the present invention ensure that every transaction committed to the database comes from a know source. These and other embodiments of the invention along with many of its advantages and features are described in more detail in conjunction with the text below and attached figures.

The system includes the registry database which includes online transaction processing OLTP data. Embodiments of the present invention are applicable to other databases but OLTP data is discussed herein as a representative data source. A database reader is utilized to pull data from the database and send the data to the database validator . The database reader will typically parse the data for example the OLTP data. The database validator receives profile data from profile database and validates the data from the database reader against one or more matching profiles from the profile database. As an example if data related to an Add Domain operation is present in the OLTP data then the database validator can compare this OLTP data against an Add Domain profile to determine if the correct database operations were performed as part of the Add Domain operation. Additional discussion related to validating data using profiles is provided throughout the present specification and more particularly below. After validation data can be cached in data cache .

The system also includes a transaction log file reader that receives data from transaction log files . The transaction log data can be cached in a transaction log data cache or passed directly to the data correlator . As shown in the data correlator receives inputs from the database validator the transaction log file reader and or the data cache and the transaction log data cache . The data correlator compares the validated data from the database validator and the transaction log data to determine if there is consistency between these two data sources. Additional discussion related to correlation of these data sources is provided throughout the present specification and more particularly below. An optional report generator receives the results of the data correlation process and is adapted to provide reports to system operators and the like.

It is understood that the various functional blocks otherwise referred to herein as systems processor engine and the like including database reader database validator transaction log file reader data correlator and optional report generator illustrated in may be included in one or more general purpose processors configured to execute instructions and data. Thus the various processes illustrated in can be performed by processors adapted to the various tasks and coupled to one or more memories that store instructions adapted to be executed by the processor. The processor can be a general purpose microprocessor configured to execute instructions and data such as a Pentium processor manufactured by the Intel Corporation of Santa Clara Calif. It can also be an Application Specific Integrated Circuit ASIC that embodies at least part of the instructions for performing the method in accordance with the present invention in software firmware and or hardware. As an example such processors include dedicated circuitry ASICs combinatorial logic other programmable processors combinations thereof and the like. The memory can be any device capable of storing digital information such as RAM flash memory a hard disk a CD etc. The processor can be coupled to the various databases for example the source of the OLTP data the profile data the transaction log file data the data cache the transaction log data cache or other databases that can store other pertinent information. Thus processors as provided herein are defined broadly and include but are not limited to processors performing data validation correlation and the like. These processes can thus be implemented using computer readable medium storing a plurality of instructions for performing at least a portion of the methods included within the scope of the present invention.

As described more fully throughout the present specification embodiments of the present invention compare database transaction to known transaction profiles. Since the applications have finite code paths they can be compared against the database transaction to determine if the transaction was authorized. Additionally by correlating database transactions to application server logs a chain of trust is created between systems thereby improving system confidence.

After the transaction data is parsed the parsed transaction data is validated by comparison with existing profiles stored in the profile list . In the SRS registry database each application has a finite code path based on the code itself. Thus every transaction that occurs throughout an application should fit a known profile. A profile is metadata expressed in XML files describing an auditable registry operation. As discussed more fully below the system will provide one profile per registry operation. By auditing all successful writable operations to the SRS registry database using the profiles the transactions in the database can be validated as authorized. Merely by way of example a profile may contain metadata related to operations performed during a registry operation e.g. an INSERT into a particular table business logic rules that are applied during a registry operation and the like.

Embodiments of the present invention provide methods and systems in which the database is mined and the transactions are compared against all known profiles to determine if each transactions match a profile. If a transaction doesn t match one of the known profiles this provides an indication that an anomaly has occurred. By validating the data the security auditor ensures that the customer s intent was correctly persisted in the database and that all the business rules have been properly enforced. After validation the validated transaction data can be stored in a cache referred to as the database data cache.

In addition to validation of the transaction data the security auditor utilizes transaction logs created on the application side and correlates these transaction logs with the validated data. The transaction log files reader pulls transaction logs from the transaction log file database . The transaction log files are created by the application servers. The transaction log files are parsed and in an optional step are cached in a transaction data log data cache. The data correlator is used to correlate the validated transaction data with the corresponding transaction log data to ensure that the changes made to the SRS registry database have come from a known source. As an example of an anomaly if the transaction data after validation does not match the corresponding transaction log then it provides an indication that the change to the database did not come from a known source. Accordingly an alarm could be raised.

The report generator is used to receive information from the database data validator as well as the data correlator . Accordingly reports can be generated based on data validation errors i.e. transaction data not matching a known profile or correlation errors. The reports can include information such as a list of transactions that failed validation a count of the distinct validation errors the total number of transactions audited the amount of time taken to validate the transactions and the like. An identifier in the transaction log on the application server is compared to the transaction in the database ensuring that these elements match up as designed. Thus the customer s intent in the transaction log is persisted properly in the database which is represented by the OLTP data stream .

Utilizing embodiments of the present invention all transactions that manipulate data within the registry database are verified to come from a known source and match a known profile associated with an existing application code path. The transactions are verified by mining transaction data from the database and comparing the transactions to a profile associated with the transaction to determine if known application logic flows were utilized in performing the transactions. Once the data is validated using the process flow profiles it is then compared to application transaction logs. These comparisons provide a level of data integrity not available using conventional systems. Based on the validation process the methods and systems described herein provide the added benefit of alerting operations staff if data is updated outside of the application which could indicate malicious intent.

An exemplary use case for the methods and systems described herein is a hacker gaining access to the registry database and slowly deleting a certain number of domains per day outside of the authorized applications. The security auditor described herein would detect the unauthorized deletions since the changes would not comply with the profile established for deleting domains and does not come from a known source. Upon identification of the unauthorized character of the changes an alert could be raised thereby enabling the system operator to take corrective action.

The parsed OLTP transaction data is compared to one or more of a set of profiles . Each of the one or more of the set of profiles comprises metadata in XML files. In accordance with the type of transaction data received the profiles can include profiles related to operations such as adding a domain name deleting a domain name renewing a domain name or the like. In other embodiments the profiles can relate to adding a domain name server deleting a domain name server or modifying a domain name server.

In one embodiment the method optionally includes caching the parsed OLTP transaction data in a first data cache although this is not required by the present invention. The method further includes receiving log data associated with the OLTP transaction data and correlating the parsed OLTP transaction data with the log data . In one embodiment the log data can be cached in a second data cache although this is not required by the present invention. In embodiments utilizing caches the correlation process can utilize parsed data that is cached and log data that is cached.

The method can also optionally include determining a validation error and generating an alert related to the validation error . As an example of the alert one or more reports e.g. a detail report and a summary report can be generated for use by system operators or other.

It should be appreciated that the specific steps illustrated in provide a particular method of validating transaction data according to an embodiment of the present invention. Other sequences of steps may also be performed according to alternative embodiments. For example alternative embodiments of the present invention may perform the steps outlined above in a different order. Moreover the individual steps illustrated in may include multiple sub steps that may be performed in various sequences as appropriate to the individual step. Furthermore additional steps may be added or removed depending on the particular applications. One of ordinary skill in the art would recognize many variations modifications and alternatives.

According to an embodiment of the present invention the Security Auditor is instantiated by the APE Asynchronous Processing Engine framework. The APE framework is responsible for reading OLTP transactions from transaction log files e.g. Golden Gate trail files and making them available in a memory queue for consumption by downstream applications. The Security Auditor is one such downstream application. The Security Auditor is instantiated with a configuration file and the start date time at which the transactions are to be audited. In the implementation described herein the Security Auditor on startup will instantiate and start the following components.

It should be appreciated that the specific steps illustrated in provide a particular method of operating the Security Manager according to an embodiment of the present invention. Other sequences of steps may also be performed according to alternative embodiments. For example alternative embodiments of the present invention may perform the steps outlined above in a different order. Moreover the individual steps illustrated in may include multiple sub steps that may be performed in various sequences as appropriate to the individual step. Furthermore additional steps may be added or removed depending on the particular applications. One of ordinary skill in the art would recognize many variations modifications and alternatives.

According to embodiments of the present invention the Security Auditor utilizes the Service Provider Interface SPI model to ensure that different components can be plugged in and out. For example if the decision is made to move from one database services application e.g. from LogMiner audit tool available from Oracle Corporation of Redwood Shores Calif. to GoldenGate transaction data integration software available from GoldenGate Software of San Francisco Calif. then the code to parse GoldenGate will be written to provide the same information as that provided using LogMiner .

According to a specific embodiment all programming will be done using the interfaces as exposed by the SPI. Depending on the embodiment a number of different high level interfaces can be utilized to provide the following functionality 

As discussed above one implementation integrates the Security Auditor with the APE Framework. The APE Framework has two main responsibilities 

Security Auditor will host a management server. There are a number MBeans registered with the management server which may include the following list of MBeans. This list of MBeans is provided merely by way of example and additional MBeans can be added as appropriate to the particular application. One of ordinary skill in the art would recognize many variations modifications and alternatives.

Profile Manager is a singleton class which reads the profiles that are in XML format and caches them in memory. On startup the Security Auditor will initialize the Profile Manager with the location of the profiles. In one implementation profiles are cached in a java.util.TreeMap. Each profile may be cached in two tree maps in memory with the following keys 

The SQL Summary Cache Manager SQLSummaryCacheManager is a singleton class which is a cache of the SQL summaries. SQL summaries are cached in a java.util.LinkedBlockingQueue. DBProcessor threads will add valid SQL summaries to this queue. The transaction Id associated with a database transaction which has not passed all the database validation rules will be cached in a HashSet. This way when the corresponding transaction log entry expires it is known that it was associated with an invalid SQLSummary to begin with.

If the SCN of the SQL summary is less than the maximum SCN read in the transaction log file minus the SCN threshold the entry is removed from the cache and a SQLSummaryExpired exception is thrown. The maximum size of the SQL summary cache is controlled by a parameter in the sa.config configuration file. This value is passed to the SQLSummaryCacheManager by the Security Auditor during the initialization phase.

The Trans Log Summary Cache Manager TransLogSummaryCacheManager is a singleton class which is a cache of the transaction log summaries. Transaction log summaries are cached in an inner class ExpiringTransSummaryCache which extends java.util.LinkedHashMap. TransLogProcessorThread classes will add valid transaction log summaries to this map.

For every transaction log summary added to the ExpiringTransSummaryCache the removeEldestEntry method is invoked with the least recently used LRU entry in the map. If the SCN of the transaction log entry is less than the maximum SCN read in the database transaction minus the SCN threshold the entry is removed from the cache and a TransLogSummaryExpired exception is thrown. The SCN threshold is set by a parameter in the sa.config configuration file. The maximum size of the transaction log summary cache is controlled by a parameter in the sa.config configuration file. This value is passed to the TransLogSummaryCacheManager by the Security Auditor during the initialization phase.

The Exception Manager is illustrated in . Whenever an exception is thrown in the Security Auditor the constructor in the base SAException class performs two functions 

A singleton class com.verisign.sa.spi.exception.ExceptionManager is provided and a cache HashMap is used to keep track of the number of validation errors based on the error type. The SecurityAuditorReport class uses this information when generating a report.

Embodiments of the present invention provide a log copy script which is a perl script e.g. logcopy.pl that is used to copy all the relevant transaction log files to the input transaction log folder being monitored by the TransLogFilesPoller. The script will then scp all the transaction log files to an input transaction log folder. The file build.properties will be modified as needed to include the IP addresses of all the servers which have transaction log files.

A parameter logcopy.date.interval specifies how far back to go in number of days to copy the transaction log files. A value of 1 specifies that transaction log files from yesterday need to be copied. Similarly a value of 2 will copy day before yesterday s and yesterday s transaction log files. After all the log files have been copied Log Copy will then create a file named trigger in the input transaction log folder. This is to ensure that Security Auditor will only start processing after all the transaction log files have been copied. Log Copy will be scheduled as a cron job to run at 2 a.m. every day.

The Transaction Log Files Poller TransLogFilesPoller illustrated in is used to poll the directory specified in a configuration file for the specific file named trigger . The transaction log files parameters are specified in a configuration file.

Referring once again to the transaction log files are copied to the input transaction log files folder via a cron job using the log copy logcopy.pl perl script that is provided and the following sequence of events occur 

Database processor threads are initially in a waiting state to be notified by the Resumeable component manager to start retrieving database transactions from the APE Framework. As OLTP transactions are read from the APE Framework via the SecurityAuditorFacade the following steps will occur 

As described throughout the present specification there are three sets of thread that are executed concurrently in the Security Auditor. The SummaryCorrelator also referred to as a SummaryCorrelatorManager is responsible for the creation and management of the correlator threads thread pool. The three sets of threads executing concurrently in the Security Auditor are 

The SecurityAuditorReportManager is initialized by the Security Auditor on startup. Reports generated by the Report Manager will be written to a folder specified by a parameter in the configuration file.

In a specific embodiment the report file name will have the following format MMddyyyyHHmmss to MMddyyyyHHmmss .txt. As an example a report could be named 11012009000000 to 11022009000000 Summary.txt for a report generated for transactions beginning at midnight on Nov. 1 2009 and ending at Nov. 2 2009 midnight.

As illustrated in two types of reports are provided either Summary or Detail . Additional description related to the summary and detail reports is provided throughout the present specification and more particularly below. Prior to generating the report SecurityAuditorReportManager will perform the following actions 

Two reports detail and summary will be generated for transactions audited beginning at the startDateTime and ending at the endDateTime specified in the Security Auditor. The parameter which controls the report time duration is specified in a configuration file. After the report is generated ResettableComponentManager is invoked to reset the statistics in all the resettable components. Resettable components will be discussed in more detail below.

As discussed above the Security Auditor will generate at least two reports a summary report which is a high level report that just mentions the types and counts of validation errors encountered and a detail report which contains details about each error that has occurred and the number of times it has occurred. When SecurityAuditorReportManager is initialized on startup it instantiates and starts the DetailReport thread . As validation errors occur a detail version of the error message is placed in a queue. The DetailReport thread will read the error messages off this queue. It will then check a cache to see if an identical error message was encountered before. If an identical error message is already present in the cache then the count is incremented. If an identical error message is not found in the cache then the message is added to the cache with a count of 1.

By providing the DetailReport thread as a thread in and of itself embodiments of the present invention ensure that the validation threads continue to do their work of validating without having to wait for the detail error message to be checked in the cache.

Embodiments of the present invention provide for notification of certain components in the Security Auditor when certain events happen that would trigger the resumption of their activity. The ResumableComponentManager is provided for this purpose. The components that will wait for such events to resume processing are resumeable components in the Security Auditor. All resumeable components register themselves with ResumeableComponentManager to be notified of such events by implementing the following interface.

The TransLogFilesDispatcher will invoke ResumeableSAComponentManager.resumeAuditing when one day s worth of transaction log files are received. ResumeableSAComponentManager will in turn invoke the resume method on all the registered ResumeableSAComponents.

The following components in the Security Auditor implement the ResumeableSAComponent interface and register themselves with the singleton ResumeableSAComponentManager class 

Embodiments of the present invention provide for notification of certain components in the Security Auditor when certain events happen that would trigger the reset of the variables that hold statistics about the transactions currently being audited. The resettable components register themselves with ResettableComponentManager to be notified of such events by implementing the following interface.

The SecurityAuditorReportManager will invoke ResettableSAComponentManager.resetComponents to reset the state in the resettable components after a report has been generated. ResettableSAComponentManager will in turn invoke the reset method on all the registered ResettableSAComponents.

The following components in the Security Auditor implement the ResettableSAComponent interface and register themselves with the singleton ResettableSAComponentManager class 

Components in the Security Auditor which need to perform some cleanup action in the event of a shutdown by implementing the following interface 

When Security Auditor s shutDown method is invoked via JMX it invokes ShutDownManager.shutDown method. Prior to invoking this method Security Auditor will write the timestamp of the last processed SQLSummary to startdate.txt file. Thus when Security Auditor is started again it knows where it left off. ShutDownManager will then invoke the shutdown method on all the registered ShutDownListener classes.

The following components in the Security Auditor implement the ShutDownListener interface and register themselves with the singleton ShutDownManager class 

Embodiments of the present invention provide a specific profile for each registry operation. The profiles include but are not limited to 

For example a login EPP command will insert into the REGISTRYSESSION and TRANSACTION tables. Profiles for each registry operation are provided in a separate XML file that captures metadata regarding a registry operation. By having validation information in an XML file the implementations described herein separate the code to perform validation from the actual metadata present in the profile. Preferably the validation rules will be expressed in the profiles. For certain corner case validations which may be cumbersome to express in XML a Java hook could be provided to perform the complex one off validation.

An XML schema has been created to represent the profile for all registry operations. XMLBeans are used to parse and navigate the data within a profile. Once a profile has been parsed it is further converted into a framework of classes to represent the metadata information. This would then free the application of relying on the format in which the original profile information is stored or for that matter where it is stored.

A profile for a registry operation contains the following three 3 pieces of metadata Operation Info Database Info and Validation Criterion. is a simplified diagram illustrating metadata for a registry operation according to an embodiment of the present invention. A registry operation profile is represented by the following interface 

OperationInfo captures information regarding a registry operation. A profile can be retrieved from cache based on the operationID. When SQL statements are parsed the relevant profile is retrieved based on the operationID i.e. insert into Transaction table has the operationID of the registry operation . is a simplified diagram illustrating metadata for OperationInfo according to an embodiment of the present invention.

The dbOperation specifies whether it was insert update or delete operation on the table. The min max attributes specifies the minimum and maximum number of the specified operations on the table. The column elements specify the columns of interest to parse and cache from the associated SQL statement. As an example there could be 10 columns in a SQL statement but there may be only two columns whose values are cached.

According to embodiments of the present invention constraints can be specified on columns. The following attributes of the column element specify the constraints 

The mutually exclusive tables element specifies the operations on tables that are mutually exclusive as part of this operation.

As an example of a logic flow for an add domain profile the following snippet is an example of an ADD DOMAIN profile which is associated with transactions in which a domain name is added 

The XML from this snippet specifies that the minimum value for REGISTRATIONPERIOD is 1 and the maximum value is 10 . Similarly the minimum length of the DOMAINNAME column is 1 and the maximum length is 67 . The allowable values for ENCODINGTYPEID are 3 or 14 . Other values are utilized in other particular implementations and these values are merely provided by way of example.

In order to illustrate a profile for deleting a domain name the following snippet is provided for a DEL DOMAIN profile 

When a delete domain operation occurs on a domain within the grace period a DELETE on the DOMAIN table SQL statement is issued by the application. On the other hand when a delete domain operation occurs on a domain after the grace period a UPDATE on the DOMAIN table SQL statement is issued by the application. Since a domain can either be in the grace period or not both these SQL statements cannot be part of the same transaction. Thus these operations are mutually exclusive and use of both operations will be flagged as an unauthorized transaction.

This element captures metadata related to transaction log entry validation. is a simplified diagram illustrating Transaction Log Validation according to an embodiment of the present invention. A value in the transaction log entry is matched with a value in the SQL summary. In embodiments the value of a transaction log entry identified by a name must be equal to the value of the column value in a table with the specified database operation. The ignoreCase attribute specifies whether the comparison of the values is case sensitive or not.

In the event a combination of transaction log entries must be concatenated to match a single value in a database column then the transaction log entry parameters specified by the transLogEntryParams element will be concatenated using the specified delimiter. The resulting value is then compared with a value in a database column.

The knownIssue attribute illustrated in and other figures specifies whether or not an alert is raised if the validation rule were to fail. The attribute knownIssue can be turned on or off for a number of the different validation rules. If the attribute knownIssue true and a validation error were to occur while applying the specified validation rule to the data then an alert will not be raised. This attribute thus gives the operator the ability to turn off alerts for issues identified in the system but for which a fix has not yet been implemented. Once the system has been updated to adhere to the validation rule the attribute knownIssue false can be set. Thus utilizing the knownIssue attribute noise can be reduced in the system with respect to the errors reported.

As an example of transaction log validation the following example is applicable to an ADD DOMAIN operation 

In this example the value specified by the transaction log entry with name dm will be compared with case insensitivity against the value in the DOMAIN.DOMAINNAME column in the database.

As the SQL statements retrieved from the database reader are parsed into in memory data structures database validation rules as specified in the associated profile are applied. Thus any SQL statements that do not match a profile are flagged early in the process.

An operation can have any number of referential validation rules. Optionally a regular expression may be applied on the master column prior to it being compared with values in a child column.

As an example of referential validation the following example from an ADD DOMAIN profile is provided.

The above validation rule specifies that the regular expression specified is applied to the value in the DOMAIN.DOMAINNAME column in the database. The resulting value must then be equal to the DOMAIN.PARENTDOMAIN column in the database. Thus this rule specifies that all domains inserted into the DOMAIN table must end in COM NET EDU ARPA and the corresponding TLD must match the value in the PARENTDOMAIN column.

A lookup validation is performed to ensure that the value inserted into a column is the right value based on the value in a lookup table. is a simplified diagram illustrating lookup validation according to an embodiment of the present invention. As illustrated in the value in the tableName.columName must be equal to the value returned by executing the specified SQL statement in the profile. This validation rule is optional in some embodiments of the present invention.

As an example of conditional validation the following example from an ADD DOMAIN profile is provided.

The above example specifies that all the column values specified such as DomainName RegistrationPeriod and the like must have been inserted into the TRANSACTIONATTRIBUTES.ATTRIBUTE column.

Referring to if either the regexValidation or the conditionalValidation specified for the rule is satisfied then operations on the tables specified must also be part of the operation.

As an example of exists in tables using regular expression validation the following example from an ADD DOMAIN profile is provided.

The above example states that if the value DOMAIN.DOMAINNAME column matches the regular expression XN then an insert into the INTERNATIONALDOMAIN table operation must also exist.

The above condition states that if the value inserted into the TRANSACTIONATTRIBUTES.ATTRIBUTE column is equal to Directive AND the value inserted into the ATTRIBUTEVALUE column is 1 then the following SQL operations must also occur.

In the above example we are ensuring that the REGISTRATIONEXPIRATIONDATE value is not more than 10 years from the CREATEDDATE of the domain. Here is the sequence of operations that occur for this validation.

Certain complex validation rules that are too cumbersome to express in XML are done via custom validation in code. is a simplified diagram illustrating custom validation according to an embodiment of the present invention. An example of a custom validation rule for the SYNC DOMAIN operation is shown below 

All the validation regarding the registration expiration date is performed in the SyncDomainExpirationDatejava class. Some of the validations are 

All the custom validation classes are pre instantiated using Java Reflection API and cached in the CustomValidationCacheManager. All classes that support custom validation must implement the following interface.

If the domain name is not an international domain name then a determination is made if name servers are linked . If the name servers are linked then the domain name server link and the domain name server link audit are inserted and . After the domain name server link and the domain name server link audit are inserted the transaction is updated . If the name servers are not linked then the transaction is updated .

It should be appreciated that the specific steps illustrated in provide a particular method of performing an add domain operation according to an embodiment of the present invention. Other sequences of steps may also be performed according to alternative embodiments. For example alternative embodiments of the present invention may perform the steps outlined above in a different order. Moreover the individual steps illustrated in may include multiple sub steps that may be performed in various sequences as appropriate to the individual step. Furthermore additional steps may be added or removed depending on the particular applications. One of ordinary skill in the art would recognize many variations modifications and alternatives.

There are valid database transactions that occur in the database without a corresponding transaction log entry in a transaction log file. The inventors have identified valid database transactions without a corresponding transaction log entry. Profiles have been created for these 43 database transactions.

The profile above states the following When a SQL statement such as UPDATE TRANSACTION SET FILEID occurs in a transaction by itself it is a KNOWN ISSUE as specified by the operationiD and conceptClassName tags. Only when the columns specified in the profile are updated will the SQL statement be designated as a known issue. For example if another column other than the FILEID is updated in the TRANSACTION table then this is deemed to be a malicious database transaction.

When ProfileManager loads the no transaction log entry profiles a key is generated in the following form 

For example the key generated for the SQL statement for the above profile would be TRANSACTION.UPDATE FILEID . This key is then used to cache the associated profile in memory. For every database transaction the value of the associated OPERATIONID column is retrieved from the SQL statement INSERT INTO TRANSACTION table. When a database transaction is retrieved that does not contain an INSERT INTO TRANSACTION table SQL statement then a key is generated in the above format. Using this key the associated profile is then retrieved from the ProfileManager. If the value of the tag in the profile is KNOWN ISSUE then this is considered a valid database transaction. If no profile is retrieved with the generated key or if the value of the tag is not equal to KNOWN ISSUE then this is deemed to be a malicious database transaction.

Embodiments of the present invention provide a summary has all the information necessary to perform all the specified validations in a profile. All the information received either from the database reader or the application transaction logs is saved as summaries in memory. There are two types of summaries 

Embodiments of the present invention provide an auditable summary. Both the SQL and transaction log summaries extend AuditableSummary. AuditableSummary specifies operations that are common across both the summaries. The hasExpired method is invoked to find out if a summary cache entry has expired or not when compared with the maximum SCN retrieved from either the transaction log files or the database.

The hasExpired method ensures that summaries that could not be validated within a specified period of time are deemed to be an error. Since all summaries are persisted in memory this safeguard ensures that there is an upper limit on the number of summaries in memory.

Embodiments of the present invention provide an SQL Summary which is the end product of successfully parsing and validating SQL statements contained within a transaction boundary. The central tenet of SQLSummary is to expose an interface that will be useful for validating transactions in the SRS registry regardless of whether the database reader utilized in the embodiment.

Each SQLSummary instance is associated with a registry profile and contains a collection of SQL statements. SQLStatement is the parent interface of a whole hierarchy of interfaces for capturing relevant information from the parsed SQL statement. Specifically the sub classes of SQLStatement are used to represent information in an INSERT UPDATE DELETE SQL statement. SQL summaries are cached in a java.util.LinkedBlockingQueue.

The TransLogSummary is the end result of successfully parsing a transaction log entry. TransLogSummary is cached keyed by the transaction ID. For each SQLSummary retrieved by the correlator from the SQLSummary cache the corresponding TransLogSummary is retrieved from the TransLogSummary cache using the transaction ID. The registry profile associated with the SQLSummary is then used to apply transaction log validation rules to the SQL and transaction log summaries.

Correlator threads perform the crucial act of correlating the data in the SQL summary with the data in the transaction log summary. SQL summaries are cached in a java.util.BlockingLinkedQueue. Transaction log summaries are cached in a java.util.HashMap.

On startup SummaryCorrelator instantiates a specified number of correlator threads. The following sequence of actions takes place in the correlator threads.

As discussed previously the Security Auditor is integrated with the APE Framework. The APE Framework hides the details of the source of the OLTP transaction data. Thus as far as the Security Auditor is concerned it is just retrieving OLTP transaction data from an in memory queue in the APE Framework. The APE Framework instantiates the SecurityAuditorFacade via a Spring context. The Spring configuration file HostedComponent config.xml is included in the SecurityAuditor.

The APE Framework s AsyncProcessingEngine will invoke the SecurityAuditorDateRange class to determine the start date time from which point the OLTP transaction data needs to be retrieved from the database reader. The SecurityAuditorDateRange class writes this information to the startdate.txt file. The database reader process is started by passing this start date time. In the configuration file for the database reader process the java user exit class is set to be the AsyncProcessingEngine class. The AsyncProcessingEngine class will in turn instantiate the SecurityAuditorFacade via the Spring context. SecurityAuditorFacade in turn instantiates SecurityAuditor. Thus embodiments of the present invention provide for integration between the APE Framework and the SecurityAuditor which is a hosted component.

As part of the reporting function provided by embodiments of the present invention all validation errors will be written to log files. Two reports summary and detail are generated on a daily basis by the Security Auditor.

All error logging is done in one place in the SAException class. The format of the error logging is as follows in a particular embodiment 

Depending on how far down the processing the validation exception has occurred the Operation Name and Transaction ID may not always be present. Sequence number specifies the number of times this exception has occurred in the Security Auditor.

A summary report is generated on a daily basis by the Security Auditor. The summary report contains the types and count of errors that have occurred while auditing the transactions. Statistical information such as the number of records processed how long it has taken to process them and the like are also present. The following is an exemplary report that is prepared according to an embodiment of the present invention.

The detail report is generated on a daily basis by the Security Auditor. The number of times a unique error has occurred and details about the error are present in this report. The detail report contains actionable information that can be used by system operators to determine the exact cause of the validation errors. The following is an exemplary detail report prepared according to an embodiment of the present invention.

The following unique validation errors have occurred. Please refer to the error log file for details.

Embodiments of the present invention provide a detail error log that shares some similarities with the detail report. As each detailed validation error is sent to the DetailReport thread the thread first logs the message in the detail error log. It then caches the message to be written to the detail report with the count of the number of times the message has been encountered.

The detail error log is written to the logs folder as specified in the Security Auditor configuration file. The name of detail error log is in the following format sa.err.detail.log.

The verbose error log contains all the details of a validation error. This includes the actual values of the columns in the offending transaction. A system operator could first look into the detail report and if necessary can then look into the verbose error log for more information as required. The verbose error log is written to the logs folder as specified in the Security Auditor configuration file. The name of verbose error log is in the following format sa.err.

The Security Auditor will host a management server in some embodiments. As mentioned above there will be a number of mbeans registered with the management server to provide statistics regarding the status of the Security Auditor and its constituent components.

There are multiple mbeans defined in the Security Auditor for monitoring and reporting purposes. There are mbeans that are defined as components in the Security Auditor. Additionally there are mbeans defined for the configuration information and the Security Auditor itself.

This mbean has attributes and operations of the Security Auditor. The following attributes are exposed 

Start Date Time String The start date time for the Security Auditor. The creation timestamp of the transactions being audited is used to determine if the transactions are in the current time frame of the auditing cycle. Typically this is midnight of the day before yesterday.

End Date Time String The end date time for the Security Auditor. Similar to the start date time the end date time is used to determine when the auditing cycle needs to be stopped and a report generated. Typically this is midnight of previous day.

Started This attribute is a boolean variable. A value of true indicates that the Security Auditor is up and running. This can be used by external monitoring components to determine if the Security Auditor is up.

Currently Processing This attribute is a boolean variable. A value of true indicates that the Security Auditor is currently auditing transactions. This can be used by external monitoring components to determine if the Security Auditor is up.

The configuration information specified in the configuration file for the Security Auditor is exposed as read only attributes. is a screen shot illustrating configuration information according to an embodiment of the present invention.

The rest of the Mbeans are defined as components of the Security Auditor. Hence them is a sub type associated with the key for the following mbeans.

This mbean defines two operations Log Error Counts and Display Error Counts. Log Error Counts is an operation that logs the error counts of the validation errors encountered to the error log file. Display Error Counts is an operation that returns a java.lang.String with the same information that was written to the error log file by the logErrorCounts operation. This information could then be displayed in external components such as the Admin Console.

Number of Profiles Loaded in Memory This attribute specifies the number of profiles that have been parsed and loaded into memory by the Profile Manager.

List Profile Operation Names This operation will return a java.lang.String of the operation names of the profiles in memory. Examples of operation names are ADD DOMAIN RESTORE DOMAIN and the like.

Reload Profiles This operation will forcibly reload the profiles on disk into memory. This operation can be used to reload profiles on demand if there were changes to the profiles. Thus modified profiles can be loaded into memory without shutting down the Security Auditor.

Latest Summary Report This attribute contains the latest available report of the audited transactions in the Security Auditor. The last summary report generated by the Security Auditor is available via this attribute. This way the latest summary report can be viewed in external components such as the Admin Console.

Total Valid SQL Summaries This attribute specifies the total number of valid SQL summaries that were added to the valid SQL summary cache in the current auditing cycle.

Total Invalid SQL Summaries This attribute specifies the total number of invalid SQL summaries that were added to the invalid SQL summary cache in the current auditing cycle.

This mbean has attributes that have information regarding the correlation of transaction and SQL summary caches.

Number of Correlated Transactions This attribute specifies the number of transactions that have been correlated across the SQL and transaction log summary caches.

Num Summaries in Cache This attribute specifies the current size of the transaction log summary cache.

Total Trans Summaries This attribute specifies the total number of transaction log summaries that were added to the transaction log summary cache in the current auditing cycle.

The base class for all exceptions thrown in the Security Auditor is com.verisign.sa.spi.exception.SAException. All other exception classes extend SAException class and are defined in the com.verisign.sa.spi.exception package. The following exception classes which are provided merely by way of example and are not intended to limit the present invention will be used for various validation errors according to an embodiment of the present invention 

The base abstract class SAException does all the error logging. According to a particular embodiment no other logging of validation errors is provided anywhere else in the application.

The Security Auditor writes the start date time from which transactions need to be audited to a file named startdate.txt . In the event of a shut down Security Auditor will write the timestamp of the last SQLSummary processed to this file. Thus embodiments provide for restarting the Security Auditor to perform auditing of transactions from where it had left off.

Since embodiments of the present invention provide a Security Auditor that is an in memory validator of registry operations concurrent execution of operations will typically be utilized. Accordingly the following concurrent executions take place 

Components that utilize a pool of threads will typically use the Executor interface. In addition the size of the thread pools for each of these components is specified in a configuration file.

It should be noted that all the thread pools in the Security Auditor will be instantiated with the same ThreadFactory ThreadGroup and RejectionHandler in an embodiment. Additionally locks in the Security Auditor will be created using a common LockFactory in order to ensure the same global lock fairness policy for uniformity across the application.

Embodiments of the present invention utilize a number of external libraries including the Directory Poller. The Directory Poller library provides the ability to monitor specific directories and generate events when files are copied to the directory. On startup Security Auditor will register TransLogFileDispatcher as a listener with the Directory Poller. When a transaction log file is copied to the directory Directory Poller picks it up generates an event and sends the java.io.File object to the TransLogFileDispatcher. This capability of Directory Poller will ensure that when Security Auditor is operating in a real time auditing mode the transaction log files can be processed as available.

According to some embodiments all the interfaces exposed in the SPI model are serializable. This enables the different data components such as caches summaries profiles and the like to be persisted as appropriate based on reasons related to performance recoverability or the like.

Based on the profiles discussed above the steps of the various operations are validated for the appropriate transactions stored in the OLTP database in one embodiment. Since the profile demonstrates how the operations for writing data to the database should proceed if the data is not written in this exact format the security auditor will flag the transaction for further investigation and or reporting. A similar syntax is used for mapping application transaction logs to database transaction logs to establish a chain of custody from the application servers to the database.

The 24 7 monitoring team generates trouble tickets which may be stored in trouble ticket database . The trouble ticket database can be co located with the 24 7 monitoring team of may be remotely located depending on system implementation. Information related to the reporting from the security auditor is passed to the Operations Engineering team by the 24 7 monitoring team. The information can be passed automatically or after review by the 24 7 monitoring team. In some embodiments the trouble tickets generated by the 24 7 monitoring team are utilized to provide inputs and notifications to the Operations Engineering team . As illustrated the Operations Engineering team has access to the trouble ticket database . Depending on the nature of the issue detected by the security auditor appropriate action is taken which can include updates to the security auditor updates to the registration system for example by communicating with a registrar or the like.

It is also understood that the examples and embodiments described herein are for illustrative purposes only and that various modifications or changes in light thereof will be suggested to persons skilled in the art and are to be included within the spirit and purview of this application and scope of the appended claims.

