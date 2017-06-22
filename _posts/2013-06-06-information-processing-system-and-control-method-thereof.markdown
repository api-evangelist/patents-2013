---

title: Information processing system and control method thereof
abstract: A disclosed information processing system includes plural information processing apparatuses connected with a network. One of the plural information processing apparatuses includes: a first allocation unit to identify, for each subnetwork of plural subnetworks included in the network, one information processing apparatus from among information processing apparatuses included in the subnetwork, and assign to the identified one information processing apparatus, a first Reduce processing that is a processing to summarize results of a Map processing executed for data held in the information processing apparatuses included in the subnetwork; and a second allocation unit to allocate to any one of the plural information processing apparatuses, a second Reduce processing that is a processing to summarize results of the first Reduce processing executed for each subnetwork of the plural subnetworks.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09124587&OS=09124587&RS=09124587
owner: FUJITSU LIMITED
number: 09124587
owner_city: Kawasaki
owner_country: JP
publication_date: 20130606
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2012 152261 filed on Jul. 6 2012 the entire contents of which are incorporated herein by reference.

In order to improve throughput when executing a large scale MapReduce job over a wide area it is extremely important that no delays in communication occur. Conventionally the following technique was developed in order to suppress a drop in throughput due to delays in communication.

For example in an Open Science Data Cloud OSDC it becomes possible to execute Hadoop over a wide area by connecting data centers using dedicated lines.

Moreover in a wide area network a processing for Transmission Control Protocol TCP is sometimes the cause of delays. Therefore the use of a protocol called UDP based Data Transfer Protocol UDT that is based on User Datagram Protocol UDP is proposed. Furthermore in a technique that is called Sector Sphere UDT is employed as the core technique in order to achieve a distributed file system and parallel data processing.

In the technique that is called CloudBLAST the throughput is improved by using a Wide Area Network WAN technique in the transport layer which is called ViNe Virtual Network .

However there are cases in which the utilization of the techniques such as described above is not always suitable for a MapReduce job. For example not only is the cost of techniques such as described above high but flexibly analyzing data that is generated daily at data centers located around the world is difficult. Furthermore when the transport layer protocol other than TCP is used there is a possibility that the existing firewall framework may not be usable so there is a security problem.

Moreover there is no conventional art that can improve the throughput in the MapReduce processing that is executed over a wide area.

An information processing system relating to this invention includes plural information processing apparatuses connected with a network. One of the plural information processing apparatuses includes a first allocation unit to identify for each subnetwork of plural subnetworks included in the network one information processing apparatus from among information processing apparatuses included in the subnetwork and assign to the identified one information processing apparatus a first Reduce processing that is a processing to summarize results of a Map processing executed for data held in the information processing apparatuses included in the subnetwork and a second allocation unit to allocate to any one of the plural information processing apparatuses a second Reduce processing that is a processing to summarize results of the first Reduce processing executed for each subnetwork of the plural subnetworks.

The object and advantages of the embodiment will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the embodiment as claimed.

The data that is the object of the MapReduce job is document data that is stored in an input data storage unit an input data storage unit an input data storage unit and an input data storage unit . There is one or plural Map tasks and Reduce tasks included in one MapReduce job. In a Map task the number of appearances of each word that is included in a document is counted and in a Reduce task the results of the Map tasks are summarized or aggregated.

The node includes a job client a job tracker that includes a first allocation unit and a second allocation unit and a task tracker . An execution result storage unit and an input data storage unit are connected to the node .

The node includes an execution controller a job client and a task tracker . An execution result storage unit and an input data storage unit are connected to the node .

The node includes a job client and a task tracker . An execution result storage unit and an input data storage unit are connected to the node .

The node includes a job client and a task tracker . An execution result storage unit and an input data storage unit are connected to the node .

When the execution controller receives an execution instruction of a MapReduce job from a user the execution controller divides the MapReduce job relating to the execution instruction and generates a MapReduce job for each data center in other words each network . The execution controller outputs information on the MapReduce job after the division to the job client .

The job client starts execution of the MapReduce job. More specifically the job client transmits the received information on the MapReduce job to the job tracker .

The job tracker executes scheduling of the Map task and Reduce task. That is when the job tracker receives a task allocation request that requests allocation of a task from a task tracker the job tracker allocates a task that can be executed by the node that includes that task tracker. The task allocation request includes for example the number of empty slots among the slots for a Map task and the number of empty slots among the slots for a Reduce task.

However in this embodiment a Reduce task is executed in each data center. Therefore the first allocation unit in the job tracker allocates a Reduce task that summarizes the results of the Map tasks that were executed in the data center to a node in the data center . Similarly the first allocation unit causes a node in the data center to execute a Reduce task that summarizes the results of the Map tasks that were executed in the data center . The second allocation unit in the job tracker then allocates a Reduce task that summarizes the results of the Reduce tasks that were executed in each data center to a node that is designated by the user.

The job tracker saves a management structure such as illustrated in and manages allocation by using such a management structure. For example tasks for data data and data are not allocated to the node that is subordinate to rack c2 in however a task for data is allocated.

The task trackers to manage the number of Map tasks being executed and the number of Reduce tasks being executed. When there are an empty slot for a Map task and an empty slot for a Reduce task the task trackers to transmit a task allocation request that requests allocation of the tasks for the empty slots to the job tracker . Then when the task trackers to receive allocation data that includes information concerning the types of tasks and positions or locations of the input data from the job tracker the task trackers to activate a process for executing the tasks. The execution results of the task are stored in the execution result storage units to .

As for a further explanation of the job client job tracker and task tracker refer to the supplementary material that will be mentioned later.

Next the operation of the system illustrated in will be explained by using . A method for executing a MapReduce job in this embodiment is called Cluster Wide Combiner CWC .

First the user who operates the node inputs a job execution instruction that includes output destination information for the execution results of the MapReduce job and a Uniform Resource Identifier URI for the input data. The execution controller of the node accepts an input of the job execution instruction from the user step S .

The user inputs a command such as illustrated in for example as a job execution instruction. The user designates CWC by adding data cwc.py to the start of the command. The input data is designated by what follows input and the output destination is designated by what follows output . On the other hand when a normal MapReduce job is designated instead of CWC a command is inputted to which the data cwc.py is not added such as illustrated in .

The command illustrated in is an example of a command in the case of the implementation using Python. As illustrated in when implementing using Python the user creates a command having the same argument as the Hadoop streaming interface here this is cwc.py and then executes cwc.py . As for an explanation of the Hadoop streaming interface refer to the supplementary material that will be mentioned later.

When the MapReduce job is described in Java registered trademark the argument is set by a Java Application Programming Interface API and after that JobClient.runjob is called. Therefore as illustrated in when implementing using Java for example a child class for example JobClient cwc that inherits the job client is prepared and that child class is called from the Java program of the MapReduce job. As a result JobClient cwc can intercept the argument.

Returning to the explanation of the execution controller extracts the URIs of the input data from the job execution instruction step S . Then the execution controller groups the URIs of the input data according to identification information of the data center which is included in the URI step S . At the step S the grouping is performed so that the URIs of the input data that exist in the same data center are included in the same group. For example when a user inputs an execution instruction such as in the number immediately after data in the URI is identification information of the data center.

The execution controller sets 1 to a variable x which is a variable for identifying the data center that is the object of processing step S .

The execution controller determines whether x is greater than N step S . N is the number of data centers and in this embodiment N is 2. When x is greater than N step S YES route the execution controller executes the MapReduce job at the second stage so the processing moves to step S in by way of terminal A. However when x is N or less step S NO route the execution controller executes the MapReduce job at the first stage for the data center x step S . The processing of the step S will be explained using to .

First a processing in the case of executing a MapReduce job for the data center will be explained using . The execution controller outputs information on a MapReduce job for the data center to the job client . The information on the MapReduce job includes the URI for the input data. The job client transmits the information on the MapReduce job for the data center to the job tracker step S .

The job tracker in the node receives the information on the MapReduce job for the data center step S . Here it is presumed that the URI of the input data represents the input data storage unit in the node and the input data storage unit in the node . Therefore the first allocation unit allocates tasks only when a task allocation request is received from the task tracker and task tracker .

The task tracker in the node transmits a task allocation request to the job tracker in the node step S . The task allocation request includes for example identification information of the node the number of empty slots among the slots for Map tasks and the number of empty slots among the slots for Reduce tasks.

The job tracker in the node receives the task allocation request from the node step S . The first allocation unit in the job tracker then transmits allocation data for Map tasks and Reduce tasks to the task tracker in the node step S . The allocation data includes for example the type of tasks and information concerning the location or position of the input data in the case of Map tasks the offset and the size of the input data. It is not illustrated in the figure however it is presumed that the task tracker in the node also outputs a task allocation request to the job tracker and receives allocation data for Map tasks from the job tracker .

The task tracker in the node receives allocation data for Map tasks and Reduce tasks from the node step S . The task tracker then activates a process for executing a Map task and cause the process to execute the Map task step S .

On the other hand the task tracker in the node activates a process for executing a Map task and causes the process to execute the Map task step S . The task tracker transmits the execution result of the Map task to the node step S . Actually when the node that executes a Reduce task requests the node to send the execution result of the Map task the node transmits the execution result of the Map task to the node .

The task tracker in the node receives the execution result of the Map task from the node step S . The task tracker activates a process for executing a Reduce task and causes the process to execute the Reduce task at the first stage step S . In the Reduce task at the step S the execution result of the Map task in the node and the execution result of the Map task in the node are summarized and the result of the Reduce task is stored in the execution result storage unit . After the Reduce task completes the task tracker outputs a completion notification to the execution controller .

Next the processing when executing a MapReduce job for the data center will be explained using . The execution controller outputs information on the MapReduce job for the data center to the job client . The information on the MapReduce job includes the URI of the input data. The job client then transmits the information on the MapReduce job for the data center to the job tracker step S .

The job tracker in the node receives the information on the MapReduce job for the data center step S . Here it is presumed that the URI of the input data represents the input data storage unit in the node and the input data storage unit in the node . Therefore the first allocation unit allocates tasks only when a task allocation request is received from the task tracker and the task tracker .

The task tracker in the node transmits a task allocation request to the job tracker in the node step S . The task tracker in the node transmits a task allocation request to the job tracker in the node step S .

The job tracker in the node receives a task allocation request from the node and the node step S . In order to simplify the explanation the task allocation requests are received simultaneously from the node and node however the timing of receipt of the task allocation requests is not always the same.

The first allocation unit transmits allocation data for a Map task to the task tracker in the node step S . The first allocation unit also transmits allocation data for a Map task and Reduce task to the task tracker in the node step S .

The task tracker in the node receives the allocation data for the Map task from the node step S . The task tracker then activates a process for executing the Map task and causes the process to execute the Map task step S .

The task tracker in the node receives the allocation data for the Map task and Reduce task from the node step S . The task tracker then activates a process for executing the Map task and cause the process to execute the Map task step S .

The task tracker in the node transmits the execution result of the Map task to the node step S . Actually when the node that executes the Reduce task requests the node to send back the execution result of the Map task the node transmits the execution result of the Map task to the node .

The task tracker in the node receives the execution result of the Map task from the node step S . The task tracker then activates a process for executing a Reduce task and causes the process to execute the Reduce task at the first stage step S . In the Reduce task at the step S the execution result of the Map task in the node and the execution result of the Map task in the node are summarized and the result of the Reduce job is stored in the execution result storage unit . After the Reduce task completes the task tracker transmits a completion notification to the execution controller in the node .

When the job tracker receives a task allocation request from a task tracker the job tracker transmits allocation data to that task tracker 3 in . The task tracker activates a process and cause the process to execute the Map task and Reduce task 4 in . The execution result of the Reduce task is stored in the execution result storage unit.

For example it is presumed that the Map task is a task that counts the number of times the word example appears the result of Map task 1 represents example 1 or in other words the word example has appeared one time. Moreover it is presumed that the result of Map task 2 represents example 2 the result of Map task 3 represents example 2 and the result of Map task 4 represents example 3 .

In this case the result of the Reduce task in the node becomes example 3 and the result of the Reduce task in the node becomes example 5 .

Returning to the explanation of the execution controller increments x by 1 step S and the progressing returns to the processing of the step S.

Moving to an explanation of the execution controller determines whether or not completion notifications for the MapReduce job at the first stage have been received from all of the data centers step S . When any completion notification has not been received from any data center step S NO route the execution controller executes the processing of the step S again.

On the other hand when the completion notifications for the MapReduce job at the first stage have been received from all of the data centers step S YES route the execution controller executes a job at the second stage step S . The processing of the step S will be explained using and .

First the execution controller outputs information concerning the MapReduce job at the second stage to the job client . The information concerning the MapReduce job at the second stage includes information regarding the output destination. The job client transmits the information concerning the MapReduce job at the second stage to the job tracker step S .

The job tracker in the node receives the information concerning the MapReduce job at the second stage step S . Here it is presumed that the information regarding the output destination represents the execution result storage unit in the node . Therefore the second allocation unit allocates a Reduce task only when a task allocation request for a Reduce task is received from the task tracker .

The task tracker then outputs a task allocation request for a Reduce task to the job tracker . After that the second allocation unit in the job tracker outputs allocation data to the task tracker step S . The received allocation data includes identification information of the nodes that holds the execution results of the Reduce tasks. Therefore the task tracker requests the node and node which are the nodes that holds the execution results of the Reduce tasks to send the execution results of the Reduce tasks at the first stage.

In response to this the task tracker in the node reads the execution result of the Reduce task at the first stage from the execution result storage unit and transmits the result to the node step S . Moreover the task tracker in the node reads the execution result of the Reduce task at the first stage from the execution result storage unit and transmits the result to the node step S .

The task tracker in the node receives the execution results of the Reduce tasks at the first stage from the node and node step S . The task tracker then activates a process for executing a Reduce task and causes the process execute the Reduce task at the second stage step S . In the Reduce task at the step S the execution result of the Reduce task in the node and the execution result of the Reduce task in the node are summarized and the execution results of the Reduce tasks are stored in the execution result storage unit . After the Reduce task completes the task tracker transmits a completion notification of the MapReduce job at the second stage to the execution controller in the node .

When the second allocation unit in the job tracker receives a task allocation request from a task tracker the second allocation unit transmits allocation data to that task tracker 3 in . Here when a task allocation request for a Reduce task is received from the task tracker in the node the second allocation unit outputs allocation data for a Reduce task at the second stage to the task tracker . The task tracker then requests the node and node to send execution results of the Reduce tasks at the first stage. The task tracker in the node reads the result of the Reduce task at the first stage from the execution result storage unit and transmits the execution result to the node . Moreover the task tracker in the node reads the result of the Reduce task at the first stage from the execution result storage unit and transmits the execution result to the node . In Map tasks are illustrated as being executed however actually data is only read from the execution result storage units. The task tracker then activates a process for the Reduce task at the second stage and causes the process to execute the Reduce task 4 in . The execution result of the Reduce task at the second stage is stored in the execution result storage unit .

For example it is presumed that a Map task is a task that counts the number of times that the word example appears the result of the Reduce task at the first stage which is stored in the execution result storage unit represents example 3 and the result of the Reduce task at the first stage which is stored in the execution result storage unit represents example 5 . In this case the result of the Reduce task at the second stage in the node becomes example 8 . In a shuffle phase at the second stage the result of the Reduce task at the first stage is transmitted between data centers. However the results of the Reduce tasks are summarized for each data center and then the result is transferred so the amount of data that is transferred is less than in the normal wide area Hadoop.

Returning to the explanation of the execution controller determines whether a completion notification of a MapReduce job at the second stage has been received step S . When the completion notification of the MapReduce job at the second stage has not been received step S NO route the execution controller executes the step S again. On the other hand when the completion notification of the MapReduce job at the second stage has been received step S YES route the processing ends.

As illustrated in in the normal wide area Hadoop the Map task results are collected in one of the nodes. Therefore the result of Map task that was executed in the node and the result of Map task that was executed in the node flow over the WAN. On the other hand in the case of CWC after the Map task results are summarized at each data center the results are further summarized at one of the nodes. Consequently in the example in the result that flows over the WAN is only the result of the Reduce task that was executed in the node . Therefore according to CWC it is possible to reduce the amount of data that flows over the WAN so it becomes more difficult for communication delays to occur in the WAN and thus it is possible to improve the throughput.

The effect of CWC changes greatly depending on the number of unique words that are included in document data that is the object of processing. When the number of unique words is too little the amount of data is greatly reduced by a combiner that is originally prepared for Hadoop so the effect of CWC becomes difficult to notice. On the other hand when the number of unique words is too great the records having a common key among plural Map tasks that are executed at the first stage decrease so even though CWC is executed records are not summarized much in the data center. Conversely due to the overhead for dividing a MapReduce job into two stages the throughput of the MapReduce job may decrease. Therefore in this embodiment a following processing is executed.

First a user that operates the node inputs a job execution instruction that includes information concerning the output destination of the execution results of the MapReduce job and the URI of the input data. The execution controller in the node accepts the input of the job execution instruction from the user step S .

The execution controller calculates the number of unique words in the input data step S . At the step S the execution controller collects at least part of the input data and calculates the number of unique words.

The execution controller determines whether the number of unique words is within a predetermined range in other words equal to or greater than a first preset threshold value and less than or equal to a second preset threshold value step S . When the number of unique words is not within the predetermined range step S NO route the execution controller executes a MapReduce job by the normal Hadoop step S . The processing then ends by way of terminal B. When a MapReduce job is executed by the normal Hadoop the execution controller notifies the job client of that.

On the other hand when the number of unique words is within the predetermined range step S YES route the execution controller extracts the URIs of the input data from the job execution instruction and groups the extracted URIs according to the identification information of the data center which is included in the URI step S . At the step S the grouping is performed so that URIs of input data that exists in the same data center are included in the same group.

The execution controller sets 1 to a variable x which is a variable for identifying the data center that is the object of processing step S .

The execution controller determines whether x is greater than N step S . N is the number of data centers and 2 in this embodiment. When x is greater than N step S YES route the processing moves to step S in through the terminal A so that the execution controller executes a MapReduce job at the second stage. On the other hand when x is equal to or less than N step S NO route the execution controller executes a MapReduce job at the first stage for data center x step S . The processing of the step S is as explained using to .

The execution controller increments x by 1 step S and the processing returns to the processing of the step S.

Moving to an explanation of the execution controller determines whether or not completion notifications for the MapReduce job at the first stage have been received from all of the data centers step S . When a completion notification has not been received from either data center step S NO route the execution controller executes the processing of the step S again.

On the other hand when the completion notifications for the MapReduce job at the first stage have been received from all data centers step S YES route the execution controller executes the MapReduce job at the second stage step S . The processing of the step S is as explained using and .

The execution controller determines whether a completion notification for the MapReduce job at the second stage has been received step S . When the completion notification for the MapReduce job at the second stage has not been received step S NO route the execution controller executes the processing of the step S again. However when the completion notification for the MapReduce job at the second stage has been received step S YES route the processing ends.

When the aforementioned processing is carried out CWC is executed as long as CWC is effective. Therefore it is possible to avoid a state where the throughput is decreased by CWC.

Although the embodiments of this invention were explained above this invention is not limited to those. For example the aforementioned functional block diagram of the nodes to does not always correspond to a program module configuration.

Moreover the aforementioned table structures are mere examples and may be changed. Furthermore as for the processing flow as long as the processing results do not change an order of steps may be changed. Furthermore plural steps may be executed in parallel.

In addition the aforementioned nodes to are computer devices as illustrated in . That is a memory storage device a CPU processor a hard disk drive HDD a display controller connected to a display device a drive device for a removable disk an input device and a communication controller for connection with a network are connected through a bus as illustrated in . An operating system OS and an application program for carrying out the foregoing processing in the embodiment are stored in the HDD and when executed by the CPU they are read out from the HDD to the memory . As the need arises the CPU controls the display controller the communication controller and the drive device and causes them to perform predetermined operations. Moreover intermediate processing data is stored in the memory and if necessary it is stored in the HDD . In this embodiment of this technique the application program to realize the aforementioned functions is stored in the computer readable non transitory removable disk and distributed and then it is installed into the HDD from the drive device . It may be installed into the HDD via the network such as the Internet and the communication controller . In the computer as stated above the hardware such as the CPU and the memory the OS and the application programs systematically cooperate with each other so that various functions as described above in details are realized.

Hadoop is a framework in which cluster nodes read a huge amount of data in parallel and execute a batch processing also called Hadoop job or job simply at high speed.

The Map task is a processing to read input data and generate a record in a key value pair format. The transmission destination of the generated record is determined according to a hash function or the like for example. Typically plural Map tasks can be executed in parallel.

The Reduce task is a processing to summarize the records and output results of the batch processing. Typically plural Reduce tasks can be executed in parallel.

The combiner is a processing executed as a post processing of the Map task. The combiner reduces an amount of transferred data by summarizing plural records when plural records including the same key among results of the Map tasks exist.

A phase in which the Map task is executed is called Map phase a phase in which the Reduce task is executed is called Reduce phase and a phase in which the result of the Map task is transferred to the Reduce task is called shuffle phase.

The contents of the Map task and Reduce task can be described in a format of a function by the user. The functions are called Map function and Reduce function.

Components of Hadoop will be explained by using . Hadoop includes a job client job tracker and task tracker.

The job client operates on each node in a cluster. The job client has a role to start a Hadoop job designated by a user. The job client transmits information on the Hadoop job designated by the user to the job tracker. Such processing relates to 1 and 2 in .

The job tracker starts the Hadoop job and manages a progress status of the Hadoop job. Moreover in response to a request from the task tracker the job tracker allocates a Map task and Reduce task i.e. performs scheduling. This processing relates to 3 in .

The task tracker manages the number of Map tasks to be executed and the number of Reduce tasks to be executed. When a slot for the Map task or a slot for the Reduce task becomes empty the task tracker requests the job tracker to allocate the task for the empty slots. When the task is allocated by the job tracker the task tracker activates a process to execute a task. Such processing relates to 4 in .

When the Hadoop job is executed over plural data centers connected through WAN a cluster is constructed over the plural data centers as illustrated in for example. When constructing the wide area cluster the logical configuration does not change from the configuration explained above. Normally the job tracker is provided in either data center. Because the job client operates on each node in the cluster it is possible for the user to instruct the execution of the Hadoop job on an arbitrary node.

Moreover as illustrated in any one node in an example of node collects results of the Map task and summarizes the results of the Map task in the Reduce task.

The Hadoop streaming interface is a mechanism for enabling to describe a Map function and Reduce function in programming languages other than Java by enabling to utilize a standard input and output as the input and output of the Map function and Reduce function. When activating the Hadoop job the Map function Reduce function input file output file and the like are designated by arguments of the command.

Typically the interface to start the Hadoop job is an API in Java. Therefore in order to execute the Hadoop job an appropriate Java class is implemented. Moreover each of the Map function and Reduce function is implemented as a Java class.

An information processing system relating to a first mode of the embodiments includes plural information processing apparatuses connected with a network. One of the plural information processing apparatuses includes A a first allocation unit to identify for each subnetwork of plural subnetworks included in the network one information processing apparatus from among information processing apparatuses included in the subnetwork and assign to the identified one information processing apparatus a first Reduce processing that is a processing to summarize results of a Map processing executed for data held in the information processing apparatuses included in the subnetwork and B a second allocation unit to allocate to any one of the plural information processing apparatuses a second Reduce processing that is a processing to summarize results of the first Reduce processing executed for each subnetwork of the plural subnetworks.

When executing a MapReduce processing over a wide area it is important to avoid the communication delay in the network connecting the subnetworks in order to improve the throughput. Then according to the aforementioned configuration it is possible to reduce an amount of data that flows on the network connecting the subnetworks. Therefore it becomes possible to improve the throughput of the MapReduce processing executed in the wide area.

Moreover the information processing apparatus to which the first Reduce processing is allocated C may collect the results of the Map processing from the information processing apparatuses belonging to a same subnetwork and summarize the collected results of the Map processing. Moreover the information processing apparatus to which the second Reduce processing is allocated D may collect the results of the first Reduce processing from information processing apparatuses that executed the first Reduce processing and summarize the collected results of the first Reduce processing.

Thus the amount of data that flows on the network connecting the subnetworks can be reduced compared with a case where the Reduce processing is simply executed once.

Moreover the aforementioned Map processing may be a processing to count an appearance frequency of a word in a document. In such a case the one of the plural information processing apparatuses may further include E an execution controller to execute a processing to count a number of unique words for data held in the plurality of information processing apparatuses and causes the first allocation unit and the second allocation unit to execute a processing in case where the counted number of unique words is within a predetermined value.

In case where the number of unique words is extremely little or great the throughput may not be improved so much even when the aforementioned first and second Reduce processing. Then by employing the aforementioned configuration it becomes possible to execute a processing only when the improvement of the throughput is expected.

Moreover the plural subnetworks may be local area networks and the network including the plural subnetworks may be a wide area network.

According to this feature it becomes possible to treat a case where the MapReduce processing is executed in WAN such as the Internet for example.

Moreover the aforementioned second allocation unit b1 may allocate the second Reduce processing to an information processing apparatus designated by a user among the plurality of information processing apparatuses.

Thus it is possible for the user to designate the information processing apparatus of the output destination of the MapReduce processing.

A control method relating to a second mode of the embodiments includes F identifying by using one of plural information processing apparatuses connected with a network for each subnetwork of plural subnetworks included in the network one information processing apparatus from among information processing apparatuses included in the subnetwork assigning by using the one of the plural information processing apparatuses for each subnetwork of the plural subnetworks to the identified one information processing apparatus a first Reduce processing that is a processing to summarize results of a Map processing executed for data held in the information processing apparatuses included in the subnetwork G and allocating by using the one of the plural information processing apparatuses for each subnetwork of the plural subnetworks to any one of the plural information processing apparatuses a second Reduce processing that is a processing to summarize results of the first Reduce processing executed for each subnetwork of the plural subnetworks.

Incidentally it is possible to create a program causing a computer to execute the aforementioned processing and such a program is stored in a computer readable storage medium or storage device such as a flexible disk CD ROM DVD ROM magneto optic disk a semiconductor memory and hard disk. In addition the intermediate processing result is temporarily stored in a storage device such as a main memory or the like.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present inventions have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

