---

title: Managing job execution
abstract: A method for managing jobs scheduled for execution on a target system in which some jobs may spawn additional jobs scheduled for execution on the target system including intercepting jobs scheduled for execution in the target system, determining whether there is resource sufficiency in the target system for executing jobs, responsive to an affirmative determination of resource sufficiency, releasing previously intercepted jobs for execution in the target system, computing a limit of a number of jobs which can be concurrently scheduled by an external system to the target system, and transmitting the computed limit to the external system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08875140&OS=08875140&RS=08875140
owner: International Business Machines Corporation
number: 08875140
owner_city: Armonk
owner_country: US
publication_date: 20130228
---
The present application is continuation of U.S. patent application Ser. No. 13 500 345 filed Apr. 5 2012 entitled MANAGING JOB EXECUTION which application is a United States national phase application filed pursuant to 35 USC 371 of International Patent Application Serial No. PCT EP2010 062325 entitled A METHOD SYSTEM AND PROGRAM TO OPTIMIZE JOB EXECUTION SCHEDULED FROM AND EXECUTED ON EXTERNAL APPLICATION CONTAINERS filed Aug. 24 2010 which application claims priority to European Patent Application Serial No. 09172741.2 filed Oct. 12 2009 which foregoing applications are incorporated herein by reference in their entireties.

The present invention generally relates to job execution and more particularly to management of job execution when the jobs are scheduled from a source external system and executed on a target external system.

Application containers such as Enterprise Solution Resource Planning ERP systems based on SAP JBoss ORACLE E Business suite or IBM Websphere Application Server are able to schedule execution of batch jobs on one other application container SAP is a trademark or registered trademark of SAP AG in Germany and in several other countries all over the world JBoss is a trademark of JBoss Inc. Oracle is a registered trademark of Oracle Corporation IBM and Websphere are trademarks of International Business Machines Corporation in certain countries .

When submitting batch workload from an originating external system to be executed on a target external system it is easy to overload the target system and reduce the job execution throughput scheduled from the originating system. The most usual cause is when jobs spawn several children jobs in the target external system but the maximum number of processes able to run together is fixed in that target system. Moreover in the target execution system the management of the job execution queue decreases the overall efficiency and throughput. Some external systems can provide a simple load balancing but cannot manage a big amount of batch submissions.

There is thus a need to control in external systems execution of jobs scheduled from one other external system.

The U.S. Pat. No. 7 231 455 applies to controlling data packets by an external system. It uses a throttling mechanism to limit and control data packets. It is based on a cascaded pipeline architecture between the monitored relays. Data goes through this pipeline of relays . The pipeline acts as a multilevel proxy between the source and destination. Both end points do not change their behaviors. Finally it is time period based. It calculates the amount of data flow in each time period and decides to limit data fan out.

The U.S. Pat. No. 7 137 019 is an IBM patent describing an adaptive throttling system for reducing the impact of non production work less and less important on productive work more important in data processing systems by selecting a performance impact limit to satisfy. It balances non production and production work in a data processing system.

One other U.S. Pat. No. 7 243 121 describes a load balancing scheduling system to control execution of jobs and descendent jobs children on a multi node distributed environment. The method described in U.S. Pat. No. 7 243 121 assumes that is known in advance a given number of children jobs created by a job in execution. In the general case the source scheduling system is not supposed to know that a job running on the target execution system for example SAP will or will not spawn children jobs and in any case the number of children jobs is not determined in advance. U.S. Pat. No. 7 243 121 splits the workload into several pieces and distribute it to different nodes that are under the control of the system. A new component provided in IBM Tivoli Workload Scheduler for Application 8.5 allows controlled release of jobs into a SAP system the target external system according to the current workload of the SAP system. This component is a program interfacing with the external system SAP controlling the scheduling of jobs inside SAP. It is a limiter that ensures that the number of concurrent jobs on SAP does not exceed the maximum resource capacity. This new component uses an API provided by the SAP external system to control job scheduling in the external system.

A method for managing jobs scheduled for execution on a target system in which some jobs may spawn additional jobs scheduled for execution on the target system including intercepting jobs scheduled for execution in the target system determining whether there is resource sufficiency in the target system for executing jobs responsive to an affirmative determination of resource sufficiency releasing previously intercepted jobs for execution in the target system computing a limit of a number of jobs which can be concurrently scheduled by an external system to the target system and transmitting the computed limit to the external system.

It is possible to extend and customize these policies to adapt the control program to the needs of the workload systems.

It is noted that the computed limit at a given t time is based on the number of resources available for batch job execution at this given time. For example the number free batch processes b t in SAP Target systems at this given time as explained in more detail in reference to .

A first part of the flowchart corresponds to the control existing in prior art on jobs scheduled in the target system performed by an external control program. With this first control jobs scheduled in the target system are enqueued in a queue local to the control program and released when the program determines that the resources in the target system are available. Three new steps of the preferred embodiment are added. They bring a second control by the control program which applies to the jobs scheduled by the Source scheduling system.

Periodically with a time period the program checks if new jobs have been submitted in the Target system. This is done by reading the queue of submitted jobs in the Target system. For example while using the SAP XBP2.0 API the interface macros BAPI XBP JOB SELECT and BAPI XBP CONFIRM JOB are used to look into the SAP Job Queue and find new submitted jobs. By getting SAP job details it is possible to find out whether the job has been spawned by one other job or not.

New jobs answer Yes to test are candidate to be controlled by the program if they can be suspended . In SAP this checking is done using the macro BAPI XBP GET INTERCEPTED JOBS. However some jobs cannot be suspended. Those jobs are submitted from external schedulers or those jobs not are matching the interception criteria stated in SAP Table TBCICPT1. If jobs in the scheduling queue of the target system can be suspended answer yes to test the program dequeues the jobs from the scheduling queue of the target external system and enqueues them in a queue local to the Control program.

If no job can be suspended among the new jobs scheduled in the target external system answer No to test then the program cannot delay the scheduling for execution of this job but performs a second level of control at the level of the Source scheduling system. The control program changes in the target system the system parameter limiting the number of jobs scheduled in the Target system. This step comprises a computation of the best limit to put in place according to the number of jobs currently executing and the resources available in the Target system number of free processes in the example of SAP . The computation is described in .

The program tests if the local queue has jobs to release . This step is also performed if there is no new jobs answer No to test which have been submitted in the Target system.

If there are jobs to be released from the Local queue of the Control program answer Yes to test the program checks if there are resources available in the Target system . This is done for example by using customizable policies such as provided with the SAP XBP2.0 API. Spawned jobs can be suspended until an external program like the Control program described here resumes them. As described in relation with description of different policies to resume suspended jobs can be used.

If there is enough resource answer yes to test then the jobs are released or otherwise transmitted from the local queue and re included in the waiting queue of the Target system. In SAP this is possible using the macro BAPI XBP JOB START ASAP.

When there are no more jobs to control in the Target external system end of step answer No to test and answer no to test the program changes in the target system the system parameter adapting the number of jobs to be scheduled in the target system. As in step this step comprises a computation of the best limit representing the maximum of jobs to be submitted by the Source system in the Target system. This computation is done knowing the resources available for batch job execution in the Target system. In SAP the maximum number of concurrent jobs is equal to the number of SAP Background Processes . In this second execution of computation of limit in the flowchart of the method of the preferred embodiment as there are resources available the limit will be increased compared to the result of step which reduces the limit. The computation is described in detail in relation with .

If the program is not stopped answer Yes to test the process goes on by checking if new jobs have been scheduled by the originating external system in the target system. If not answer No to test the program ends.

In SAP only jobs that have been internally submitted or any spawned jobs can be intercepted by an external control program. Externally submitted jobs cannot be intercepted. So when SAP is the target system the Control program intercepts internally submitted jobs and spawned jobs and enqueues them in the local queue. But this is not the general case and the solution of the preferred embodiment considers the case where any job waiting for execution in the target system can be intercepted and enqueued in the local queue of the control program.

The first step is performed by the control program to check how many free batch processes b t are available in the Target system at this t time. Then the Control program reads in a Configuration file parameters for preparing computation of a formula to provide or otherwise transmit the maximum number of jobs to be scheduled prior to returning processing to steps or knowing the value of these parameters at this t time and the number of free batch processes b t which are available in the Target system.

The number of concurrent jobs that can be submitted into the SAP system at time t is given by Limit t . This function is calculated as follows Limit 

 is a positive or negative constant representing the minimum limit level if positive or a fixed negative bias if negative 

 is the multiplying factor that translates the number of concurrent SAP jobs into concurrent external jobs 

 is a positive or negative constant representing a reserved number of batch processes that must be left always free if negative or an additional bias to overload batch if positive and

Given configuration parameters and using the Simple Moving Average of length the computed limit value at time t will be 

If there are many jobs starting and finishing very quickly then a slow update of the limit could be better to follow the actual average of the running jobs by ignoring unuseful fluctuations. On the opposite if there are few slow jobs then it could be better to change the limit with the same rate as the background processes. Regardless the adopted tuning parameters the solution of the preferred embodiment is able to synchronize the scheduling among Source and Target systems and is also able to avoid that the Target system could get overloaded. If the configuration parameter values are the best ones then the solution is used at its best capability.

For 1 1 0 1 the limit will be equal to the number of free batch processes plus one so even if the number of free batch process is zero the limit is Limit 1 

For 0 1 1 1 a batch process is always left free and the limit will be equal to the number of free batch processes less one Limit 1

Even if the solution of the preferred embodiment has been described has been described when one source system schedules batch jobs for execution in one target system the person skilled in the art can easily adapt the control program to control in the same way one source system scheduling batch jobs for execution in more than one target system. For example one adaptation could be managing one local queue per each couple source system target system .

The preferred embodiment implements a double level of synchronization because the external system is updated for any change in the target execution system and will not submit an overloading number jobs and the target execution system will have an execution queue that does not exceed the maximum number of executable jobs.

The preferred embodiment allows optimizing resource utilization and throughput of job execution in external systems such as application container systems. The preferred embodiment is based on a double level mechanism that allows a fine grained optimization by manual customization or automatic adaptive tuning. The double level job throttling mechanism of the preferred embodiment includes a first level to control children jobs spawned by other running jobs and a second level.

The preferred embodiment is resource based. It measures the number of background processes available at a given time instant. The principle is one independent entity polling schedulers of the external systems without staying in between mediating data. This entity acts tuning the two schedulers behaviors by limiting job scheduling on the target execution system and controlling release of jobs sent for execution on the target execution system.

The preferred embodiment provides the following advantages. First it does not require changes in the two schedulers only the standard APIs provided by the external systems are used. Second it does not require any change of the connection between the originating external system and the target execution system. Third it is stateless as it does not need historical data or statistics but it can benefit from statistics data for an automatic tuning.

The preferred embodiment starts from an existing control program which can define an interception rule that can suspend batch jobs scheduled by a source system before their actual execution in a target system at fixed time intervals. The preferred embodiment retrieves the list of suspended jobs and accordingly to user defined policies resumes them. The preferred embodiment is enhanced by adding a second level throttling system to optimize use of resources for batch execution in the target system. At a fixed time interval the preferred embodiment checks the number of free batch processes in the target system. This value is used to calculate the maximum number limit of jobs that can be concurrently submitted into the target system. Since batch jobs can spawn children jobs during their execution the combination of the above three actions to limit concurrent job submission to define suspension rules to resume suspended jobs can be tuned to optimize job execution throughput.

All the configuration parameters used in this preferred embodiment can be manually defined or can be automatically evaluated by a statistical analysis system which monitors job execution throughput and adjusts the configuration to get the best performance.

