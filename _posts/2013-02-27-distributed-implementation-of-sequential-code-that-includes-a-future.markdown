---

title: Distributed implementation of sequential code that includes a future
abstract: A distributed code including a plurality of programs is created based on a sequential code that includes at least one call of a first function associated with a future, where at least a first of the plurality of programs is to execute the first function associated with the future, and at least a second of the plurality of programs is to execute a second function in a present section of the sequential code. A normalization function is included in each of the plurality of programs to normalize virtual addresses accessed by the first and second functions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09465594&OS=09465594&RS=09465594
owner: Hewlett Packard Enterprise Development LP
number: 09465594
owner_city: Houston
owner_country: US
publication_date: 20130227
---
For improved performance code can be executed in a distributed fashion in a parallel computing system that has multiple processing nodes. Distributed processing can include dividing processing tasks into multiple partitions that can be concurrently executed by the multiple processing nodes.

In some cases a specialized framework library or programming language can be used to implement a distributed processing system. Examples include the MapReduce framework the MPI Message Passing Interface Library and the Erlang programming language. However using such specialized frameworks libraries and languages involves understanding parallel programming concepts that can be relatively complex.

A simpler way of producing distributed code for running in a distributed computing environment involves generating the distributed code from sequential code. Sequential code refers to code which includes a collection of executable instructions that is arranged to execute sequentially. A future construct also referred to simply as a future can be included in the sequential code to allow for generation of the distributed code. A future can refer to a placeholder for a value that will eventually exist. This value can come into existence at any time so long as the value is available before its implicit or explicit use.

An example original sequential code P is depicted in . The example original sequential code P has three lines of code. In line a variable tf is set equal to the output of a function ff. In line a variable tp is set equal to the output of a function fp. In line the value of the variable tf is used. A function can refer to a routine or any other code that can perform a specified task.

The program P depicted in is a futurized instance of the original sequential code P. In the futurized instance P lines correspond to lines of the sequential code P. However at line of the futurized instance P a call of ff is prefixed with the future keyword to convert the call to a future call. The normal call is referred to as the future call s synchronous counterpart. The future call immediately returns with a future. This future is assignable to a variable such as to tf at line in . The future is said to be claimed at the point at which its value is used such as at line in .

The code stretch from just after the future s assignment to just before its claim point is referred to as the present section for example the code from just after line to just before line is the present section in the example of . The present section of a code includes one or more functions that are invoked after the future call and prior to claiming the future. As discussed further below the function that is the subject of the future call and the function s in the present section can be executed concurrently the ability to separately identify the future call and the present section forms the basis for generating distributed code based on sequential code in accordance with some implementations.

The future call is said to complete when its synchronous counterpart has fully executed. At run time the code is free to complete the future call anywhere between the point the future call is initiated invocation point and the claim point. In accordance with some implementations a parallel programming model PPM is provided in which a future call s synchronous counterpart starts executing concurrently with the present section. If a potential breach of sequential semantics called a violation is detected then all effects due to the parallel execution are discarded and the lines of the sequential code are executed again this time sequentially in accordance with P. In this manner the distributed implementation of the sequential code achieves a safe future since the semantics of the original sequential program are preserved.

The sequential program can be written in an unmanaged language such as C or C . An unmanaged language does not employ entities such as virtual machines or the like to ensure address consistency or to perform sequential semantics checks. Examples of managed languages include Java and C .

Generating distributed code from sequential code can be associated with various challenges. In accordance with some implementations relatively efficient techniques or mechanisms are provided to produce distributed code from sequential code. In accordance with some implementations the distributed code generated from sequential code can include multiple programs that can be executed on respective different processing machines. A processing machine can refer to a computer system a processor a core of a processor or any other processing circuit that is able to execute program code.

The multiple programs of the distributed code include a first program that is to execute a first function associated with a future call and a second program that is to execute a second function in a present section of the sequential code. The ability to execute the first and second programs on different processing machines allows for parallel execution of the first and second functions that can result in improved performance as compared to execution of the sequential code in a sequential manner.

Techniques or mechanisms according to some implementations allow for non disruptive use of sequential code in producing the respective distributed code. The sequential code can be written in standard programming languages such as C C or other languages. Non disruptive use of sequential code refers to use in which no data structure changes have to be made to the source code of the sequential code. Instead relatively minor syntactic changes can be made to a control structure of the sequential code.

A future according to some implementations can decouple a logical behavior of the future from a performance behavior of the future. Sequential semantics i.e. semantics of the sequential code are used to determine the logical behavior and a PPM is used to determine the performance behavior. From a programmer s point of view all reasoning is as if all mentions of a future in the code were elided removed and the code were executed sequentially. The only impact of a future is on the program s performance during execution.

In the ensuing discussion any function symbol in P s source code the original sequential source code is referred to with the subscript s. Any function symbol in P s source code a futurized instance of the sequential source code is referred to as is. Thus ffand fpin Pare the sequential instances of ff and fp in P. In contrast ff and fp are the futurized instances of ffand fp.

The system also includes a compiler which can receive as input the futurized code to produce as output a distributed code . The compiler can be executable on one or multiple processors .

In accordance with some implementations the distributed code includes multiple programs including a first program referred to as P and a second program referred to as P . The distributed code in can thus be considered to include two programs that execute concurrently.

The following assumes that the futurized code is a futurized instance of the sequential program Pof . In such an example the states of Pand Pjust prior to line in are the same as that of Pjust prior to line . After reaching line Ponly performs the future e.g. future call of the function ff in and Ponly performs the present e.g. computes the function fp in the present section of the code of . Pand Pcan then exchange their results which brings their states to that of Pafter line . Execution can be faster as compared to the sequential execution of P. since Pand Peach perform a partial portion of P.

The system further includes a network interface to allow the system to communicate over a network with processing machines and . The processing machines and can each be configured similar to the system which is another processing machine . Although three processing machines are depicted in it is noted that in alternative examples different numbers less than three or greater than three can be used in other examples.

The programs Pand Pcan be executed concurrently in different processing machines. For example the program Pcan be executed on one of the machines and while the program Pcan be executed on another one of the machines and .

In some examples the processing machine on which Pexecutes can be referred to as the root node. The root node and a collection of server nodes other processing machines can form a distributed execution platform. In some examples all processing machines on which programs of the distributed code can execute can have the same ISA Instruction Set Architecture operating system and libraries although the processing machines can differ in aspects such as their microarchitecture or file system layout. For simplified explanation it can be assumed that a common file system is provided across all processing machines so that a file can be accessed from each processing machine using the same file name. However in other examples different file systems can be employed in the different processing machines.

At least one processing machine e.g. can include a daemon referred to as a sentinel . The sentinel can continually listen for requests to create a distributed code from sequential code.

The future keyword manifests as a pragma. A compiler that does not support futures can still handle futurized code. Turning on support for the future pragma can be as simple as flipping a switch e.g. by providing the following command cc futures foo.c.

The parallelism is transparent to a programmer or user of the sequential code. In other words the programmer or user does not have to be concerned that the sequential code would actually be converted to a distributed code prior to execution. The fact that Pand Pof the distributed code may execute on different processing machines is hidden from the programmer or user.

When an execution of P the futurized code is invoked on a root node what is actually invoked is an execution of P. Initialization code in Pcontacts the sentinel to initiate an execution of a matching Pon another processing machine. After that there is no more process creation. Hence the present and future processes Pand P are initiated together and executed in tandem. In particular the dynamic fork based creation of processes is avoided.

In accordance with some implementations each of the programs and Pand P respectively can include a normalization function to normalize virtual addresses accessed by functions in the respective programs and . The programs and can use virtual addresses. However virtual addresses may be different on different processing machines on which the programs and execute respectively. Thus a virtual address that is sent from one program executing on a first processing machine to another program executing on a second processing machine may not be recognizable by the second processing machine since the two processing machines may use different virtual addresses. Instead the virtual addresses are normalized by each normalization function into normalized addresses which are then exchanged between the programs and executing on separate processing machines. The normalized addresses can be understood on the respective separate processing machines.

In some examples a program may have different virtual addresses on different processing machines because of ASLR Address Space Layout Randomization . Operating systems can utilize ASLR for security reasons. Hence the placements of the process image parts of the same program across distinct but similar machines e.g. same ISA operating system and libraries are not guaranteed to be the same.

Examples of the programs Pand Pare depicted in where the programs of correspond to the futurized code P of . In the program Pincludes lines f. to f. of code whereas the program Pincludes lines p. to p. of code. The code in lines f. to f. is referred to as the future harness and the code in lines p. to p. is referred to as the present harness.

Although reference is made to two different programs Pand Pin the present discussion it is noted that the distributed code generated by the compiler of can actually be a single distributed code referred to as P that can be instantiated multiple times to run as multiple instances of P. The multiple instances of Pcan include a first instance that makes up the program Pand a second instance that makes up the program P where the first instance of Pexecutes the code in the present section of the futurized code P and the second instance of Pexecutes the code in the future call of the futurized code P.

Pcan include a runtime defined function called i am the future that can return one of two values e.g. Boolean values in each instantiation of P. The value returned is dependent on the environment at the start of the run of P.

If i am the future returns a first value then Pbehaves as Pin a run whereas if i am the future returns a second value Pbehaves as Pin a run. An example of Pis provided below where lines f. to f. include the code of Pwhile lines p. to p. include the code of P.

Lines f. to f. are the code for Pcorresponding to lines to of P in . Lines p. to p. are the code for Pcorresponding to lines to of P in . It is assumed that there are no future calls before line and after line in P. Then the code prior to line and subsequent to line in Pis for the most part replicated prior to lines f. and p. and subsequent to lines f. and p. respectively.

If another future call exists before line in P or after line in P then the code depicted at lines f. to f. and at lines p. to p. in can be replicated prior to lines f. and p. or subsequent to lines f. and p. respectively except with the names of the functions changed to correspond to the different functions that may be invoked in the other future call.

Lines f. and p. in contain calls to the functions ff and fp . These functions ff and fp are derived from the sequential instances ffand fp corresponding to functions ff and fp respectively in the sequential code P by adding instrumentation to intercept at run time the virtual addresses in nonlocal accesses of data in ffand fp. Ignoring this instrumentation ff and ff and fp and fp have identical semantics.

Adding instrumentation to a function refers to adding instruction s to the function to perform specified task s . In the case of ff and fp the instrumentation involves adding instructions to intercept virtual addresses in nonlocal accesses of data.

A memory access is nonlocal to a function if the access is a read or a write of an object a named piece of storage in the execution environment that resides outside that function s active stack frame. Examples of nonlocal accesses include the following a read of a global scalar variable a write of a global array element and so forth. The instrumentation added at every nonlocal access is akin to a memory management barrier the task of the instrumentation is to store the virtual address of the access in a read set R or a write set W .

The barriers track nonlocal accesses by Pand Pat the granularity of a card which is a division of memory intended to be finer than a page of the memory. A page of the memory can refer to a predefined segment of the memory. The runtime code of Pand P divides a v bit virtual address space into 2cards where the card size is specified when the runtime code is built.

In some examples a card is a contiguous sequence of 2bytes aligned on a 2 byte boundary. The parameter c c 0 is a non negative integer constant that is specified when the runtime code is built. To track an access is to include the virtual address of the read or written location in a set. A set including expressions of such locations is referred to as the tracked set . The tracking ignores the content of the location in question the tracking is thus address based and not value based. In addition the card size which is the granularity of tracking is transparent to the programmer or user. The card size can be chosen when the runtime code is built the choice of the card size does not alter program semantics but can affect runtime performance.

At the end of line f. of the program P elements in the read set R and write set W are the virtual addresses of the nonlocal objects read or written in ff. Similarly at the end of line p. of the program P elements in the corresponding read set R and write set W are the virtual addresses of the nonlocal objects read or written in fp.

Lines f. and p. add to the read and write sets associated with the programs Pand P line f. adds tf the virtual address of the variable tf to P s write set W and line p. adds tp the virtual address of the variable tp to P s write set W. After execution of lines f. and p. the read and write sets of virtual addresses are considered built.

Lines f. p. and p. each includes a call of a normalization function norm to normalize virtual addresses into a normal form. The normalization function converts elements of a write set W or read set R to respective normalized addresses. Unlike a virtual address a normalized address for a nonlocal object is the same at both physical machines executing corresponding Pand P if Pand Pare run with the same inputs. Line f. invokes norm W to normalize the virtual addresses in P s write set W into normalized addresses using a segment map . Similarly line p. invokes norm W to normalize the virtual addresses in P s write set W into normalized addresses using another segment map and line p. invokes norm R to normalize the virtual addresses in P s read set R into normalized addresses using a segment map .

In some implementations the normal form of a virtual address v is a duple sn so where sn and so are the s number and s offset of v. An s number is an identifier that uniquely identifies a contiguous region in virtual memory called the segment. An s offset is a displacement from a segment s base. Hence sn is the s number of the segment that contains v and so is the displacement of v from the base of sn. In Linux for example a segment corresponds to a VMA Virtual Memory Area .

For every segment except the stack the base is its lowest virtual address. For the stack the base is its highest virtual address. This is because stacks grow downward meaning from high to low virtual address.

A segment map e.g. or is an injective function that associates an s number with the virtual address of the corresponding segment s base. The segment map is used to go between a virtual address s absolute and normal forms. The segment map can be set up by locating a program s text data stack and other segments when a process of the program starts up. These segments can be located by using services of a dynamic linker loader e.g. ld.so in Linux such as services provided by the dl iterate phdr interface. Although reference is made to Linux routines and commands in this discussion it is noted that in other examples routines and commands of other operating systems can be used.

In some examples a stack segment s s number can be 0. The s numbers of special segments such as vDSO can be pre specified positive integers. The segments that come from ELF Executable and Linkable Format files can be assigned s numbers that are constructed from their file names. A goal is to ensure that segments are uniquely numbered and that a segment in P P has the same s number as its counterpart in P P .

The creation of new segments can be detected by intercepting the mmap system call which is a Linux routine to obtain memory from the system. In both Pand P s numbers are assigned to the created segments in the same order from the same sequence of positive integers. As long as a segment in one program P P has a counterpart in the other program P P and as long as segments in one program are created in the same order as the counterparts in the other program then the segments in Pand Pcan be matched and the matching segments will have the same s numbers.

At lines f. to f. of Pand lines p. to p. of Pin the programs Pand Pexchange the normalized sets w rand w containing normalized addresses produced using the respective norm functions at lines f. p. and p. respectively . A send s function can be used to send the elements of a set s of one program to the other program. For example send w at line f. sends the elements of the set wof the program Pto the other program P. Psends its normalized read and write sets rand wto P by invoking send r and send w at lines p. and p. respectively.

The matching r in the other program fills the set r with the received elements first allocating r if appropriate. For example w at line p. of Preceives the elements of wfrom P.

The send call can be nonblocking which allows Pand Pto immediately advance to the next step which is to receive the sent sets Pinvokes r and w and Pinvokes r .

The call is blocking as denoted by the horizontal bar. The call does not return until all of the content of the matching send call is received.

Once all the calls return on both sides i.e. Pand P the exchange of the normalized read and write sets is complete. Both Pand Pwill then each have the sets w wand r. After lines f. and p. Phas in rand wthe sets of normalized addresses read and written by P and Phas in wthe set of normalized addresses written by P.

Instead of sending individual normalized addresses between the programs ranges of normal addresses can be exchanged. In such implementations a set of normalized addresses can be represented as a set of normalized ranges. A normalized range is the duple sn so so that denotes all of the virtual addresses within the segment sn whose s offsets run from sothrough so. By using normalized ranges contiguous sequences of addresses can be collapsed into a compact interval. Thus if the normalized ranges are exchanged between the programs rather than individual normalized addresses savings can be achieved in communications bandwidth and storage space.

Note that the tracking of nonlocal accesses by the programs Pand Pis asymmetrical. In P read and write accesses of nonlocal or potentially nonlocal data are tracked by separate read and write sets. In P only write accesses of nonlocal or potentially nonlocal data are tracked by a write set.

As further depicted in lines f. and p. of the programs Pand Pcheck for violations of sequential semantics. Each of Pand Pevaluates the violation check predicate 0 .

If VC is true sequential semantics is guaranteed. If VC is false sequential semantics has been potentially violated.

The violation check predicate at lines f. and p. includes a conjunction of two sub predicates. The first sub predicate w r is false if there is a flow dependence from the future call s synchronous counterpart to the present section. In other words there is a flow dependence if a write is performed by ffto a memory location that is read by fp.

The second sub predicate c 0vw w is false if c 0 and there is an output dependence between the synchronous counterpart and the present section in other words both ffand fpwrite to the same memory location. When c 0 and there is no flow dependence as checked by the first sub predicate the presence of an output dependence does not matter because the size of a card when c 0 is a byte which is the smallest piece of readable or writable memory in some examples.

Note that anti dependences do not matter. An anti dependence exists if what is read by ffis also written by fp. Anti dependences do not affect sequential semantics because the address spaces of Pand Pare separate. Therefore unlike in a shared memory setting anti dependences alone do not hinder concurrent execution.

The violation check predicate at lines f. and p. evaluates to true if no sequential semantics violation is detected. In that situation Pand Pexchange the cards written by the respective programs lines f. and p. . Psends the cards for all of the locations written by P. However Psends just the cards at the addresses in w wbecause locations in w wshould not be overwritten in P.

Pinvokes sendc w w which sends the cards located at w wto P and Pinvokes sendc w which sends the cards located at wto P. The reason Psends only the cards located at w wis because locations in w wshould not be overwritten in Pin order to ensure sequential semantics.

A sendc s function invoked at each of lines f. and p. sends the cards addressed by the elements of s to the other program. A matching r function invoked at each of lines f. and p. in the other program receives the cards at locations addressed by the elements of r. The sendc and functions take sets of normalized addresses as arguments.

The functions sendc s and r marshal and unmarshal the cards by scanning the normalized addresses in s and r in the same order and by using and to convert the normalized addresses when reading and writing the cards. Marshaling a card can refer to converting data in the card to a format for communication over a network while unmarshaling a card can refer to a receiver converting received data into the format understood at the receiving processing machine.

The bar above the recvc function denotes its blocking nature. The sendc function on the other hand is a nonblocking function. The nonblocking nature of sendc allows Pand Pto immediately advance to the next step which is to receive the sent cards at lines f. and p..

Once the function returns on both sides the exchange of the cards performed to ensure sequential semantics is complete. Both Pand Pwill then have the same user program state.

If a violation is detected cards are only sent from Pto Pbecause P s memory content remains valid. This is because Plogically executes only ffby the time it reaches its violation check. The sent cards are for the locations in w w as specified in line f. . Upon receiving the cards at line p. P s user program state is set to the user program state at line f. in P. This is the state between lines and in P. Both Pand Pthen normally invoke fp which is in the present section of P. Thus if a violation is detected the results of the parallel execution are discarded and the lines of the sequential code are executed again this time sequentially in accordance with the sequential program P.

There is no special consideration for the stack because activation records in Pfor and below the future call would have returned and activation records in Pbelow the call containing the present section would have returned. Writes into activation records that are above would be automatically handled by the aforementioned card exchange.

The process next includes at a normalization function e.g. norm in in each of the programs where the normalization function is for normalizing virtual addresses accessed by the first and second functions.

A function invoked in P is either defined or undefined. The function is defined if its definition is in P. Suppose that the ff function called at line in is a defined function and that all of the future or normal calls in the body of the ff function are to a single defined or undefined function ffa. This means that ffis a defined function in P and that all of the calls in the body of ffare to the single defined or undefined function ffa. Then the ff provided in the translation of P in particular for the code in line f. in can be obtained from ffby replacing the calls to ffain ffwith calls to ffa in addition to instrumenting the nonlocal accesses in ff.

In the transformation of ffinto ff depicted in nonlocal accesses including accesses of X Y and Z i for example are instrumented. When a global variable X is read in ff a call rb X is inserted just before the read of the global variable X in ff where rb is a read barrier. The call rb X includes X in the read set R. Similarly when a global variable Y and a global array element Z i are written in ff a call wb Y and a call wb Z i are inserted just before writes to Y and Z i respectively in ff . The call wb is a write barrier.

In general the primed version of every function call reachable from either ffor fp i.e. reachable from either f for fpin the static call graph for P may be generated by the compiler by inserting the read barrier and or write barrier as illustrated in .

For the undefined call reachable functions however the primed versions are to be provided in a library. The library writer can produce the primed versions in the same way the compiler produces ff from a defined ff.

A translation scheme according to some implementations for generating distributed code from sequential code does not result in nesting of futures. In other words inner future calls execute as normal calls. The elision of the inner future calls provides flattened futures. For example if lines to of form the body of the first function executed by P then line is the first future call and all future calls in functions transitively called from lines and will execute as normal calls.

The execution of inner future calls as normal calls is valid because futures according to some implementations have sequential semantics. In any complete call chain all future calls except the outermost future call execute as normal calls. The outermost future call also executes as a normal call if the outermost future call occurs below a present section in the complete call chain.

The elision of inner future calls i.e. to treat inner future calls as normal calls affords another advantage to the translation scheme it allows nonlocal accesses to be tracked using a single read set and a single write set. For instance if the invocation at line in is the outermost future call then because inner future calls are treated as normal calls the primed functions transitively called from ffcan add their nonlocal access addresses to the same R and W sets used by ff . Hence the R and W sets can be set up before the outermost future call and present section initiate i.e. before lines f. and p. in and can be torn down after the outermost future call and present section finish i.e. after lines f. and p. in .

In some implementations a translation scheme to turn P into a distributed code may involve the compiler having to generate up to three versions of a defined function called in the sequential code P. The compiler may also have to obtain from a library up to two versions of an undefined function.

For example suppose that lines to in form the body of an example defined function foo. The first generated version of foo corresponds to the code in . If foo is invoked in the present section of another defined function bar then foo i.e. the sequential instance of foo has to be generated because foowill then be called at lines f. and p. in bar s translation. Finally if foo is call reachable from a future call then foo would also have to be generated for use at line f. of for example.

If the ff function called at line in is undefined then shows that only ff has to be provided in the translation for the code at line f. . And if the fp function called at line is undefined then shows that only fp and fphave to be provided in the translation for the code at lines p. f. and p. in .

As noted above one of the versions of a defined function in the translation scheme discussed above is foo . This is obtained by replacing all calls to a function ffain the body of foo i.e. the sequential instance of foo in addition to instrumenting the nonlocal accesses in foo.

The function foois useable at lines f. and p. in . However at line f. a more specialized version can be used one in which none of the reads are tracked. Such a specialized version is referred to as foo . The function foo can be generated from foo by replacing all calls to faain the body of fooby ffa and by only instrumenting the nonlocal writes in foo. In other words nonlocal reads do not have to be instrumented which can reduce processing time of the distributed code. Thus up to four versions of a defined function may have to be used in an optimized translation scheme.

If foo were undefined then up to three versions may have to be provided in the optimized translation scheme foo foo and foo.

Irrevocable functions are handled differently than revocable functions in the process of translating a sequential code to distributed code. A function is irrevocable if its effects may not be undoable. Some examples of irrevocable functions are those that perform input output operations such as a function to perform printing raise signals and perform a nonlocal transfer of control.

If either of the functions invoked at lines and in is irrevocable the compiler falls back to generating normal code for the code section from line to line . Once again this is valid because futures have sequential semantics.

An undefined function e.g. baz should be marked irrevocable unless there is information to the contrary. Information to the contrary can come in the form of a summary that states that bazis revocable. Such a summary may accompany baz s library definition. Whether the undefined function bazis revocable may also be determinable from a specification if bazis part of a standardized API Application Programming Interface for instance if bazis a system call specified by POSIX or belongs to the standard C library.

A defined function should be conservatively marked irrevocable if any statement in its body is irrevocable. A statement is either a call or a noncall. A call statement is irrevocable only if the called function is irrevocable. A noncall statement is usually revocable except in certain language specific cases. Examples of language specific cases in C are inscrutable asm assembler statements and statements that access volatile objects. Hence a defined function s revocability can be automatically established by the compiler by examining its noncall statements considering the summaries of its undefined callees and recursively establishing the revocability of its defined callees.

More aggressive solutions may be possible in particular cases. For instance if the files output by the future call and present section can be sandboxed and if the violation check is extended to reflect flow and output dependences on file content then concurrency may be achievable even in the presence of file output operations.

The following provides an explanation of virtual and normalized addresses according to some examples. It is assumed that the compiler writes code into files that conform to ELF Executable and Linking Format . An ELF file is generally one of three types a relocatable object an executable object and a shared object. A relocatable file is intended for further linking with other ELF files and eventually leads to a shared object or executable file. The following discussion refers to executable and shared object files.

A program s process image is a collection of virtual memory segments that are constructed from the so called sections that comprise its executable and shared object files. Segments can hold specialized information. For example a text segment holds the program s code and read only data a data segment holds the program s statically allocated writable data and heap and a stack segment holds the program s run time stack.

Segments occupy disjoint intervals in the process s virtual address space. Those constructed from the sections of an executable file are located at fixed virtual addresses. This means that a static data item in a program s executable file will have the same virtual address in every run of the program. The foregoing point is demonstrated using an example C program shown in . The value of X will be the same in every run of the program. If the example C program of were compiled into an ELF executable file e.g. a.out then readelf s a.out awk X print 2 gives the value that X will have on every run. Consequently X can be determined without running the program.

Segments constructed from the sections of a shared object however can be located at different virtual addresses in every run. But the relative positions of the static data within the segments stay fixed.

The logical base of every segment except the stack is at the segment s lowest virtual address. Thus on every run all static data will have the same displacements from the logical bases of their containing segments irrespective of whether the segments come from an executable or a shared object file.

The logical base of the stack segment is at its highest virtual address because stacks grow downward. Therefore if the complete call chain is the same whenever a function is invoked for the nth time then a stack variable allocated in the nth invocation of that function will have the same displacement from the stack segment s logical base.

In implementations discussed above it is assumed that the programs of the distributed code produced from the sequential code includes instructions pertaining to performing a check for violation of sequential semantics e.g. at lines f. and p. in . In some cases the violation check can be omitted in the runtime code e.g. Pand P . Instead in such cases the violation check can be performed statically at compile time rather than at run time.

Compilers statically model the possible definitions and uses at a call site cs of a function by MOD REF sets. MOD cs is a set of lvalue expressions of locations that may be defined on executing cs. REF cs is a set of lvalue expressions of locations that may be used on executing cs.

Two lvalues alias if they name overlapping objects. Let the predicate X Y be true if there exists an x X and a y Y where X and Y are lvalue sets such that x and y may alias. The static violation check performed at compile time would be as follows MOD 0 MOD MOD 

The static violation check SVC is evaluated at compile time for Pin for example. If SVC evaluates to true the compiler replaces the code at lines f. to f. with the code at lines f. to f. in and replaces the code at lines p. to p. with the code at lines p. to p..

The following describes how a violation check can be enhanced over the violation check depicted in . It can be shown that the violation check predicate can be rewritten as where r r w is equivalent to the violation check used in when c 0. Hence when c 0 rather than tracking all of the read locations in the read set R as performed in the tracking of read locations that are also written either before or after can be avoided. Read locations that are also written can include much fewer elements than the full read set.

A read barrier call e.g. rb in on a virtual address is covered if its execution implies that a write barrier call e.g. wb in on the same virtual address was or will be executed. According to the optimized violation check predicate VC discussed above the compiler can eliminate covered read barrier calls when c 0.

The following describes a procedure for determining a subset of covered read barrier calls. The input to the procedure is C a CFG control flow graph that is in the SSA Static Single Assignment form. Suppose that the statement rbcs in a basic block bb is the read barrier call rb a where the lvalue a is the virtual address of a location that is read. If the basic block bb also contains wb a then rbcs is a covered read barrier call.

It is assumed that there is no wb a in the basic block bb. Then all basic blocks in C that contain wb a are deleted to obtain the CFG C . If the basic block bb is either unreachable from the entry basic block or does not reach the exit basic block in C then rbcs is a covered read barrier call. The compiler can safely remove statements that are covered read barrier calls.

In some examples the foregoing technique of eliminating read barriers is able to detect read barrier elimination opportunities that may not be detectable by dominance or post dominance alone.

Suppose that a statement bcs is a read barrier call rb a or a write barrier call wb a . If the variable a is invariant with respect to its innermost containing loop L then bcs can be hoisted out of the loop L.

On detecting a barrier hoisting opportunity in the loop L the compiler peels out the first iteration of the loop L by using a loop peeling transformation. Let L be the resulting loop. All barrier calls whose innermost loop is L and whose arguments are invariant with respect to L can be safely removed by the compiler .

Since sendc is a nonblocking call it can be moved to points earlier than those shown in . This allows the runtime to overlap the execution of the sendc call with the execution of the violation check and other send and receive operations. shows a result of applying hoisting of sendc calls to the code in .

The w call at line f. blocks until n cards have been received from P where n is the number of elements in w. These cards are simply discarded on receipt they therefore do not affect the user program state.

In the and calls for receiving normalized addresses and corresponding cards respectively are blocking calls.

Let recv and recvc be the nonblocking versions of and . The recv and recvc calls can be moved earlier in each of the programs Pand Pas compared to points where the blocking calls and would have been placed as can be easily determined based on comparing . By using recv and recvc the executions of ff . . . and fp . . . in the programs Pand Pcan be overlapped with the receive operations specified by the recv and recvc calls.

As shown at lines f. f. p. and p. in the recv and recvc calls return handles. A wait call on a handle blocks until the corresponding receive operation completes. Thus after lines f. f. p. p. and p. in the receive operations at lines f. f. p. p. and p. would have respectively completed.

Machine readable instructions described above including the compiler futurized code and the distributed code can be loaded for execution on a processor or processors. A processor can include a microprocessor microcontroller processor module or subsystem programmable integrated circuit programmable gate array or another control or computing device.

Data and instructions are stored in respective storage devices which are implemented as one or more computer readable or machine readable storage media. The storage media include different forms of memory including semiconductor memory devices such as dynamic or static random access memories DRAMs or SRAMs erasable and programmable read only memories EPROMs electrically erasable and programmable read only memories EEPROMs and flash memories magnetic disks such as fixed floppy and removable disks other magnetic media including tape optical media such as compact disks CDs or digital video disks DVDs or other types of storage devices. Note that the instructions discussed above can be provided on one computer readable or machine readable storage medium or alternatively can be provided on multiple computer readable or machine readable storage media distributed in a large system having possibly plural nodes. Such computer readable or machine readable storage medium or media is are considered to be part of an article or article of manufacture . An article or article of manufacture can refer to any manufactured single component or multiple components. The storage medium or media can be located either in the machine running the machine readable instructions or located at a remote site from which machine readable instructions can be downloaded over a network for execution.

In the foregoing description numerous details are set forth to provide an understanding of the subject disclosed herein. However implementations may be practiced without some or all of these details. Other implementations may include modifications and variations from the details discussed above. It is intended that the appended claims cover such modifications and variations.

