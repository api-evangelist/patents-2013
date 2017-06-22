---

title: System, method, and article of manufacture for a merger and acquisition knowledgebase
abstract: A system, method and article of manufacture are provided for managing a merger or an acquisition. A plurality of statistics are tracked relating to a merger or an acquisition for reporting purposes. Further, a plurality of decisions are stored relating to the merger or acquisition. Such decisions may be accessed by a plurality of users involved in the merger or acquisition. In addition, a plurality of items associated with the merger or acquisition are inputted into a database. Each item is associated with at least one of the users. The users may be search for the items in the database.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09123011&OS=09123011&RS=09123011
owner: Accenture Global Services Limited
number: 09123011
owner_city: Dublin
owner_country: IE
publication_date: 20130919
---
This is a continuation of application Ser. No. 09 447 680 filed Nov. 23 1999 now allowed which is incorporated herein by reference in its entirety.

The present invention relates to managing a process and more particularly to managing a process such as a merger or acquisition through a networked database system.

In the past instructional databases have been commonly used to provide users with a plethora of information. Such information may be used to execute various tasks or enable the users to accomplish a goal. Often such instructional databases may be stored on a centralized server and provide access to a plurality of client computers via a network. In some instances such network is the Internet in which case the database is accessed via a web site.

Such prior art instructional databases however often utilize a conventional hypertext system which makes it particularly difficult to navigate the information in a progression that the original designers intended without sacrificing the ability of the user to freely navigate the information. Further none of such prior art instructional databases allow an effective exchange of ideas in order to achieve a goal at hand.

Still yet another feature that the prior art instructional databases lack is the ability to track a progression of an effort to achieve an intended goal. Finally the prior art instructional databases have never been used to facilitate a merger and acquisition situation.

A system method and article of manufacture are provided for managing a merger or an acquisition. A plurality of statistics are tracked relating to a merger or an acquisition for reporting purposes. Further a plurality of decisions are stored relating to the merger or acquisition. Such decisions may be accessed by a plurality of users involved in the merger or acquisition. In addition a plurality of items associated with the merger or acquisition are inputted into a database. Each item is associated with at least one of the users. The users may be search for the items in the database.

In accordance with at least one embodiment of the present invention a single entry point is provided for merger acquisition participants to access related information and deliverables utilizing Intranet technology. Entry may be accomplished using a hardware implementation such as is illustrated in . Further various functional and user interface features of the present invention may be enabled using software programming i.e. object oriented programming OOP .

A representative hardware environment of a preferred embodiment of the present invention is depicted in which illustrates a typical hardware configuration of a workstation having a central processing unit such as a microprocessor and a number of other units interconnected via a system bus . The workstation shown in includes Random Access Memory RAM Read Only Memory ROM an I O adapter for connecting peripheral devices such as disk storage units to the bus a user interface adapter for connecting a keyboard a mouse a speaker a microphone and or other user interface devices such as a touch screen not shown to the bus communication adapter for connecting the workstation to a communication network e.g. a data processing network and a display adapter for connecting the bus to a display device . The workstation typically has resident thereon an operating system such as the Microsoft Windows NT or Windows 95 Operating System OS the IBM OS 2 operating system the MAC OS or UNIX operating system.

Object oriented programming OOP has become increasingly used to develop complex applications. As OOP moves toward the mainstream of software design and development various software solutions require adaptation to make use of the benefits of OOP. A need exists for the principles of OOP to be applied to a messaging interface of an electronic messaging system such that a set of OOP classes and objects for the messaging interface can be provided.

OOP is a process of developing computer software using objects including the steps of analyzing the problem designing the system and constructing the program. An object is a software package that contains both data and a collection of related structures and procedures. Since it contains both data and a collection of structures and procedures it can be visualized as a self sufficient component that does not require other additional structures procedures or data to perform its specific task. OOP therefore views a computer program as a collection of largely autonomous components called objects each of which is responsible for a specific task. This concept of packaging data structures and procedures together in one component or module is called encapsulation.

In general OOP components are reusable software modules which present an interface that conforms to an object model and which are accessed at run time through a component integration architecture. A component integration architecture is a set of architecture mechanisms which allow software modules in different process spaces to utilize each other s capabilities or functions. This is generally done by assuming a common component object model on which to build the architecture. It is worthwhile to differentiate between an object and a class of objects at this point. An object is a single instance of the class of objects which is often just called a class. A class of objects can be viewed as a blueprint from which many objects can be formed.

OOP allows the programmer to create an object that is a part of another object. For example the object representing a piston engine is said to have a composition relationship with the object representing a piston. In reality a piston engine comprises a piston valves and many other components the fact that a piston is an element of a piston engine can be logically and semantically represented in OOP by two objects.

OOP also allows creation of an object that depends from another object. If there are two objects one representing a piston engine and the other representing a piston engine wherein the piston is made of ceramic then the relationship between the two objects is not that of composition. A ceramic piston engine does not make up a piston engine. Rather it is merely one kind of piston engine that has one more limitation than the piston engine its piston is made of ceramic. In this case the object representing the ceramic piston engine is called a derived object and it inherits all of the aspects of the object representing the piston engine and adds further limitation or detail to it. The object representing the ceramic piston engine depends from the object representing the piston engine. The relationship between these objects is called inheritance.

When the object or class representing the ceramic piston engine inherits all of the aspects of the objects representing the piston engine it inherits the thermal characteristics of a standard piston defined in the piston engine class. However the ceramic piston engine object overrides these ceramic specific thermal characteristics which are typically different from those associated with a metal piston. It skips over the original and uses new functions related to ceramic pistons. Different kinds of piston engines have different characteristics but may have the same underlying functions associated with them e.g. how many pistons in the engine ignition sequences lubrication etc. . To access each of these functions in any piston engine object a programmer would call the same functions with the same names but each type of piston engine may have different overriding implementations of functions behind the same name. This ability to hide different implementations of a function behind the same name is called polymorphism and it greatly simplifies communication among objects.

With the concepts of composition relationship encapsulation inheritance and polymorphism an object can represent just about anything in the real world. In fact the logical perception of the reality is the only limit on determining the kinds of things that can become objects in object oriented software. Some typical categories are as follows 

With this enormous capability of an object to represent just about any logically separable matters OOP allows the software developer to design and implement a computer program that is a model of some aspects of reality whether that reality is a physical entity a process a system or a composition of matter. Since the object can represent anything the software developer can create an object which can be used as a component in a larger software project in the future.

If 90 of a new OOP software program consists of proven existing components made from preexisting reusable objects then only the remaining 10 of the new software project has to be written and tested from scratch. Since 90 already came from an inventory of extensively tested reusable objects the potential domain from which an error could originate is 10 of the program. As a result OOP enables software developers to build objects out of other previously built objects.

This process closely resembles complex machinery being built out of assemblies and sub assemblies. OOP technology therefore makes software engineering more like hardware engineering in that software is built from existing components which are available to the developer as objects. All this adds up to an improved quality of the software as well as an increase in the speed of its development.

Programming languages are beginning to fully support the OOP principles such as encapsulation inheritance polymorphism and composition relationship. With the advent of the C language many commercial software developers have embraced OOP. C is an OOP language that offers a fast machine executable code. Furthermore C is suitable for both commercial application and systems programming projects. For now C appears to be the most popular choice among many OOP programmers but there is a host of other OOP languages such as Smalltalk Common Lisp Object System CLOS and Eiffel. Additionally OOP capabilities are being added to more traditional popular computer programming languages such as Pascal.

Class libraries are very flexible. As programs grow more complex more programmers are forced to reinvent basic solutions to basic problems over and over again. A relatively new extension of the class library concept is to have a framework of class libraries. This framework is more complex and consists of significant collections of collaborating classes that capture both the small scale patterns and major mechanisms that implement the common requirements and design in a specific application domain. They were first developed to free application programmers from the chores involved in displaying menus windows dialog boxes and other standard user interface elements for personal computers.

Frameworks also represent a change in the way programmers think about the interaction between the code they write and code written by others. In the early days of procedural programming the programmer called libraries provided by the operating system to perform certain tasks but basically the program executed down the page from start to finish and the programmer was solely responsible for the flow of control. This was appropriate for printing out paychecks calculating a mathematical table or solving other problems with a program that executed in just one way.

The development of graphical user interfaces began to turn this procedural programming arrangement inside out. These interfaces allow the user rather than program logic to drive the program and decide when certain actions should be performed. Today most personal computer software accomplishes this by means of an event loop which monitors the mouse keyboard and other sources of external events and calls the appropriate parts of the programmer s code according to actions that the user performs. The programmer no longer determines the order in which events occur. Instead a program is divided into separate pieces that are called at unpredictable times and in an unpredictable order. By relinquishing control in this way to users the developer creates a program that is much easier to use. Nevertheless individual pieces of the program written by the developer still call libraries provided by the operating system to accomplish certain tasks and the programmer must still determine the flow of control within each piece after it s called by the event loop. Application code still sits on top of the system.

Even event loop programs require programmers to write a lot of code that should not need to be written separately for every application. The concept of an application framework carries the event loop concept further. Instead of dealing with all the nuts and bolts of constructing basic menus windows and dialog boxes and then making all these things work together programmers using application frameworks start with working application code and basic user interface elements in place.

Subsequently they build from there by replacing some of the generic capabilities of the framework with the specific capabilities of the intended application.

Application frameworks reduce the total amount of code that a programmer has to write from scratch. However because the framework is really a generic application that displays windows supports copy and paste and so on the programmer can also relinquish control to a greater degree than event loop programs permit. The framework code takes care of almost all event handling and flow of control and the programmer s code is called only when the framework needs it e.g. to create or manipulate a proprietary data structure .

A programmer writing a framework program not only relinquishes control to the user as is also true for event loop programs but also relinquishes the detailed flow of control within the program to the framework. This approach allows the creation of more complex systems that work together in interesting ways as opposed to isolated programs having custom code being created over and over again for similar problems.

Thus as is explained above a framework basically is a collection of cooperating classes that make up a reusable design solution for a given problem domain. It typically includes objects that provide default behavior e.g. for menus and windows and programmers use it by inheriting some of that default behavior and overriding other behavior so that the framework calls application code at the appropriate times.

Thus through the development of frameworks for solutions to various problems and programming tasks significant reductions in the design and development effort for software can be achieved. A preferred embodiment of the invention utilizes HyperText Markup Language HTML to implement documents on the Internet together with a general purpose secure communication protocol for a transport medium between the client and a company. HTTP or other protocols could be readily substituted for HTML without undue experimentation. Information on these products is available in T. Berners Lee D. Connoly RFC 1866 Hypertext Markup Language 2.0 November 1995 and R. Fielding H Frystyk T. Bemers Lee J. Gettys and J. C. Mogul Hypertext Transfer Protocol HTTP 1.1 HTTP Working Group Internet Draft May 2 1996 . HTML is a simple data format used to create hypertext documents that are portable from one platform to another. HTML documents are SGML documents with generic semantics that are appropriate for representing information from a wide range of domains. HTML has been in use by the World Wide Web global information initiative since 1990. HTML is an application of ISO Standard 8879 1986 Information Processing Text and Office Systems Standard Generalized Markup Language SGML .

To date Web development tools have been limited in their ability to create dynamic Web applications which span from client to server and interoperate with existing computing resources. Until recently HTML has been the dominant technology used in development of Web based solutions. However HTML has proven to be inadequate in the following areas 

With Java developers can create robust User Interface UI components. Custom widgets e.g. real time stock tickers animated icons etc. can be created and client side performance is improved. Unlike HTML Java supports the notion of client side validation offloading appropriate processing onto the client for improved performance. Dynamic real time Web pages can be created. Using the above mentioned custom UI components dynamic Web pages can also be created.

Sun s Java language has emerged as an industry recognized language for programming the Internet. Sun defines Java as a simple object oriented distributed interpreted robust secure architecture neutral portable high performance multithreaded dynamic buzzword compliant general purpose programming language. Java supports programming for the Internet in the form of platform independent Java applets. Java applets are small specialized applications that comply with Sun s Java Application Programming Interface API allowing developers to add interactive content to Web documents e.g. simple animations page adornments basic games etc. . Applets execute within a Java compatible browser e.g. Netscape Navigator by copying code from the server to client. From a language standpoint Java s core feature set is based on C . Sun s Java literature states that Java is basically C with extensions from Objective C for more dynamic method resolution. 

Another technology that provides similar function to JAVA is provided by Microsoft and ActiveX Technologies to give developers and Web designers wherewithal to build dynamic content for the Internet and personal computers. ActiveX includes tools for developing animation 3 D virtual reality video and other multimedia content. The tools use Internet standards work on multiple platforms and are being supported by over 100 companies. The group s building blocks are called ActiveX Controls which are fast components that enable developers to embed parts of software in hypertext markup language HTML pages. ActiveX Controls work with a variety of programming languages including Microsoft Visual C Borland Delphi Microsoft Visual Basic programming system and in the future Microsoft s development tool for Java code named Jakarta. ActiveX Technologies also includes ActiveX Server Framework allowing developers to create server applications. One of ordinary skill in the art readily recognizes that ActiveX could be substituted for JAVA without undue experimentation to practice the invention.

The Merger and Acquisition M A Engine provides knowledge management and delivery capabilities to facilitate the learning and execution of merger related work. In one embodiment this is accomplished by storing the M A Engine on a centralized server which may be accessed over a network i.e. the Internet via a web site using a hardware implementation set forth hereinabove and shown in .

During operation the M A Engine facilitates user work manages and delivers reusable knowledge improves the ability to manage change resulting from mergers and acquisitions and expedites the learning process for new merger resources. The M A Engine streamlines communication between merger participants and assists in the consolidation of projects. The M A Engine can also be used as a marketing tool. In addition the M A Engine promotes standardization of processes that are applicable to individual areas such as status reporting business case development and budget and benefits monitoring.

Using the M A Engine productivity is improved during the transition by increased communication. Merger acquisition participants are given a common entry point to effectively access information and deliverables leverage existing knowledge contribute knowledge conduct informal conversations document meeting outcomes and issues etc.

The M A Engine improves documentation and outcomes by providing users access to the entire history of an on line discussion. This functionality improves the understanding of issues and or topics e.g. conversion schedule DARTs etc. as well as what decisions or progress has been made towards a resolution. The M A Engine improves issue resolution during the transition by utilizing discussion databases to submit and or answer issues questions topics etc. This gives key stakeholders an improved understanding of the most current status of key deliverables.

The M A Engine supports standardization of consolidation activities and deliverables. Users are consistently guided through the steps to complete merger acquisition activities and are provided samples and templates to facilitate the completion of deliverables associated with those activities. The M A Engine also develops and retains institutional knowledge related to consolidation thus reducing costs related to training and use of outside consultants.

The M A Engine also supports the evolution of process driven methods for the transition by utilizing the Intranet as its delivery vehicle. Through the M A Engine users are able to drill down from a merger activity to specific task packages and deliverables. This capability improves the understanding throughout the organization of the complete range of activities that are involved with the consolidation of two or more organizations.

One embodiment of the M A Engine includes a plurality of features for accomplishing the foregoing goals. For example the present invention includes Navigation Chevron a Discussion Database a Discussion Database Interface Page a 30 60 90 Plan and a Merger Site Map. A workbench homepage is used to navigate the user through the M A Engine environment. The Discussion Database is used to discuss concepts and serve as an audit trial of topics. The Discussion Database Interface Page describes the various discussion groups available to the user and subscribes the user to individual discussion groups when selected. The 30 60 90 Plan is used to account for all actions taken during the first 90 days of consolidation. Finally the Merger Site Map tracks activities and duration of these activities throughout the consolidation.

The Navigation Chevron of the present invention is a form of hypertext that facilitates the navigation of data during use of the M A Engine. Hypertext systems are a class of complex information management systems. These systems allow people to create annotate link together and share information from a variety of media such as text graphics audio video animation and programs. They also provide flexible access to information by incorporating the notions of navigation annotation and tailored presentation.

Hypertext is defined as an approach to information management in which data is stored in a network of nodes connected by links. Nodes can contain text graphics audio video as well as source code or other forms of data. Hypertext with multimedia is called hypermedia . The utility of hypermedia lies in its ability to produce large complex richly connected and cross referenced bodies of information.

Outside the academic world due to the implementation of hypertext like features in products such as MS Windows Help information systems professionals are of the opinion that hypertext is just another user interface approach. However hypertext is a hybrid that spans across traditional boundaries. It is a database method providing a novel way of directly accessing and managing data. It is also a representation scheme a kind of semantic network which mixes informal textual material with more formal and mechanized processes. It is an interface modality that features link icons or markers that can be arbitrarily embedded with the contents and can be used for navigational purposes. In short a hypertext system is a database system which provides a totally different and unique method of accessing information. Whereas traditional databases have some structure around them a hypertext database has no regular structure. The user is free to explore and assimilate information in different ways.

A hypertext system is made of nodes or concepts and links or relationships. A node usually represents a single concept or idea. It can contain text graphics animation audio video images or programs. It can be typed and can include detail proposition collection summary observation and issue thereby carrying semantic information. Nodes are connected to other nodes by links. The node from which a link originates is called the reference and the node at which a link ends is called the referent. They are also referred to as anchors. The contents of a node are displayed by activating links.

Links connect related concepts or nodes. They can be bidirectional thus facilitating backward traversals. Links can also be typed i.e. specification link elaboration link membership link opposition link and others specifying the nature of relationship. Links can be either referential for cross referencing purposes or hierarchical for showing parent child relationships. Activation of a link marker displays a node.

Hypertext parallels human cognition and facilitates exploration. People think in nonlinear chunks which they try to associate with each other thus building a network of concepts. When a person reads a book they go back and forth a number of times to refer to previously read material to make notes and to jump to topics using the table of contents or the index. When they set out to write a document they first develop an outline of ideas. Then a person brainstorms writes down on paper organizes revises reorganizes and repeats the cycle until they are satisfied with the outcome a coherent document. In fact people have been forced to adapt to traditional linear text because of representation on paper.

In order to understand hypertext it is very essential to understand how people read and write documents. Reading and writing models have been developed by cognitive psychologists that can be used to understand non linear thinking by human beings.

The theory of semiotics or the study of symbols shows that the understanding of knowledge takes place at four levels lexical syntactic semantic and pragmatic. At the lexical level the user determines the definition for each word encountered. At the syntactic level the subject action and object of a sentence are determined. The meaning of a sentence is determined at the semantic level. The pragmatic interpretation of text depends on the integration of semantic meaning of text with the reader s knowledge of self and of the world.

While reading text people proceed from a lexical level to the syntactic level to the semantic and to the pragmatic levels in that order. All these levels interact continuously and they cannot be truly separated. The reader might have to have knowledge of the world in order to understand the meaning of a word. The correct syntactic and semantic interpretation of text may depend on the reader s knowledge of the world. Hence though readers may proceed from words to sentences to paragraphs and to the overall document the progress is more forward and backward.

A mental representation of the meaning of text is then constructed which is in the form of propositions or relationships. While reading text readers establish local coherence in short term memory small scale inferences from few small units of information i.e. relationships between words sentences and so on. The reader makes preliminary hypotheses based on titles words propositions and knowledge about the real world. A reading control system retrieves knowledge from the real world present in long term memory in order to filter out information present in short term memory. These hypotheses are refined as the reading of the text proceeds with the reading control system being invoked continuously. These propositions are combined into larger structures also called global. This hypothesized macroproposition or superstructure is used to understand the overall content of the text. The construction of a coherent mental representation has important consequences for navigation. In addition to generating forward references we accumulate cues for backward navigation.

The reading control system uses the spreading activation model to access propositions or concepts. In semantic memory each concept is connected to a number of other concepts. Activating one concept activates its adjacent concepts which in turn activate their adjacent concepts. Thus activation spreads through the memory structure determining what is to be added and what is to be removed from the interpretation of text. This process continues until further activation of adjacent propositions does not change the propositions used to interpret the text. That is spreading activation decreases over time and semantic distance.

Writing is constrained by goal and audience. The author is guided by a goal but constrained by what the audience is prepared to accept. Different people approach writing in different ways. Some are good at making an outline first and then brainstorming. Some do the opposite. An expert author would always keep the reading model in mind so that the writing clearly reaches the target audience.

Writing involves the following three phases exploring organizing and encoding. In the Cognitive Framework for Written Communication Smith et al. call these three phases prewriting organizing and writing.

Exploring or pre writing is the process of brainstorming and taking unstructured notes. The writer retrieves potential content from long term memory or external sources considers possible relations among ideas groups related ideas and constructs small hierarchical structures. Thus the product of exploration is a network or directed graph of ideas.

Organizing is the process of putting these notes or ideas in order in the form of an outline or a hierarchy. This process involves abstract construction that involves perceiving subordinate superordinate relations comparing abstractions sequencing proportion and balance. Thus the product of organization is a hierarchy of related concepts.

Encoding or writing is the final phase of completing the document. The primary task is translating the abstractions of content and the relations of a hierarchical structure into a sequence of words sentences paragraphs sections chapters and illustrations. The structure of the encoded text is linear and represents a path through the hierarchy. Reading employs processes in the reverse order. That is a linear sequence of words is transformed into a hierarchy which is later integrated into a network in long term memory.

The writing model can be extended by considering unstructured and structured representation at each phase. Whereas an unstructured item is isolated a structured item shows coherence. Exploring can be split into unstructured brainstorming followed by structured note taking.

Organizing can be classified as unstructured argumentation where relationships are established between ideas and structured organization of notes where notes are grouped together to make coherent sense. Encoding has an unstructured phase of linear planning which involves viewing groups of notes as sequences and a structured phase of drafting and revising in order to produce a final document which is a linear sequence of notes.

Just as the reader of a linear document constructs a local and global mental representation of the document the author of a linear document uses cues both at the local and at the global levels dividing the document into chapters sections paragraphs sentences words etc. This facilitates comprehension and navigation.

Thus both reading and writing processes emphasize a lot on the non linear nature of thinking a natural process in human beings. Human cognition is essentially organized as a semantic network in which concepts are linked together by associations. Hypertext systems try to exploit this basic nature of cognition.

One aspect of the present invention utilizes a unique hypertext feature a Navigation Chevron to navigate the user through the data in the M A engine environment. is an illustration of the Navigation Chevron . The Navigation Chevron is generally shaped as an indicia similar to a pointer and may be arranged in any orientation such as horizontally diagonally or vertically.

The Navigation Chevron is made up of components or discrete phase chevrons which may be generally shaped similar to the Navigation Chevron . Displayed on each discrete phase chevron is an indication of the topic relating to that particular discrete phase chevron . The indication may be a color or some other identifying mark. A preferred indication is the title or general description of the topic area related to the particular discrete phase chevron . The description allows the user to easily determine which discrete phase chevron relates to the particular topic needed to complete a particular task.

The Navigation Chevron is used to navigate a database of knowledge utilizing a progression of ideas or phases. Each idea or phase of the knowledge database is represented by a discrete phase chevron in the Navigation Chevron . The discrete phase chevrons are organized in a logical progression of the topics covered by the Navigation Chevron s related knowledge database.

The topic pages in the related knowledge database generally include a Navigation Chevron as part of their display. The Navigation Chevron may be located anywhere on the display preferably away from the data provided by the knowledge database such as at the top or to the side of the display. In addition the Navigation Chevron may be of any size. A preferred embodiment uses an initially large Navigation Chevron . However with each subsequent progression the Navigation Chevron becomes smaller in size.

As the user decides on an area of knowledge to explore the user picks a discrete phase chevron utilizing a computer input device such as the mouse . Once a discrete phase chevron is chosen the related knowledge database topic page is displayed along with a Navigation Chevron including a highlighted discrete phase chevron related to the current knowledge database topic page . The Navigation Chevron thus allows the user to navigate an extensive knowledge database in an easy and intuitive manner.

The user is able to explore the knowledge database in the order presented on the Navigation Chevron or in an order more pertinent to the task at hand. By selecting the topic to explore in the Navigation Chevron the user can go directly to the topic needed for a particular task. In addition the Navigation Chevron allows the user to visualize the knowledge database as a whole and determine how the current knowledge database topic page relates to other topics in the knowledge database. As such the Navigation Chevron indicates a relationship i.e. progression or sequence that is inherently not present in conventional hypertext systems.

Navigation Chevrons may be nested allowing a more detailed navigation through a knowledge database. is an illustration showing the use of the Navigation Chevrons in an exemplary graphical user interface .

In another embodiment a large Navigation Chevron may be used to allow access to broad topic areas covered by discrete phase chevrons . Each topic covered by a discrete phase chevron may also have a further Navigation Chevron related to the particular broad topic covered by the discrete phase chevron . Such Navigation Chevron may further include additional discrete phase chevrons which relate to more detailed information associated with the broad topic of the discrete phase chevron . The nesting of Navigation Chevrons may continue including further nested Navigation Chevrons as much as needed to allow easier navigation of a large knowledge databases. As discussed above the nested Navigation Chevrons allow the user to visualize the knowledge database as a whole and determine how a knowledge database topic page relates to the knowledge database as a whole.

It should be noted that Navigation Chevrons may be employed to navigate data within any type of database including but not limited to the M A Engine. Below is an html code segment for displaying and using a Navigation Chevron 

Bulletin board systems or BBS s refer to computer systems equipped with one or more modems or other means of network access that serves as an information and message passing center for remote users. Often BBS s are focused on special interests such as science fiction movies Windows software or Macintosh systems and can have free or fee based access or a combination. Users dial into a BBS with their modems and post messages to other BBS users in special areas devoted to a particular topic in a manner reminiscent to posting notes on a cork bulletin board. Many BBS s also allow users to chat online with other users send e mail download and upload files that include freeware and shareware software and access the Internet. Many software and hardware companies run proprietary BBS s for customers that includes sales information technical support and software upgrades and patches.

In other words a BBS acts as a storage facility where people calling from their computers can post or receive messages and send or receive program files. A BBS is usually subdivided by topics so that users with similar interests can send information to other users of similar interests. These related groups of messages are referred to as topics message areas forum s or conferences i.e. a particular BBS may contain numerous related groups of messages such as on the subjects of travel sports stamp collecting etc.

BBS s are distinguishable from electronic mail in that BBS s are used for posting messages of a particular group of computer users who have similar interests but these posted messages are not ordinarily addressed to any particular user. BBS s are also used by some computer users who wish just to read posted messages and other information without having to post a reply message. For example a person in Columbus Ohio who is preparing for a vacation may access a BBS on travel through his home computer and post a message asking for the best places to go skiing in the United States. Other network users with an interest in travel may read the message from the person from Columbus and then reply with their opinion about where the best place is for skiing. There are thousands of BBS s available to computer network users on a wide variety of subject areas.

Another component of the M A Engine of the present invention is the Discussion Database. The Discussion Database in some limited respects is similar to a BBS in that it is a repository of knowledge on various topics compiled from the input of various users of the Discussion Database. is a block diagram of a Discussion Database in accordance with one embodiment of the present invention.

A Discussion Database includes a broad topic field having Discussion Groups relating to specific subject areas of the broad topic . The Discussion Groups include User Posts which are documents contributed by users of the Discussion Database . Preferably the User Posts are contributed by users of the particular broad topic field and most preferably the User Posts are contributed by users of the particular discussion group in which the User Post is located. Generally many broad topic fields are used to create the Discussion Database to increase ease of navigation. Typically the more broad topic fields that are used to create the Discussion Database the easier it is for a user to find the particular Discussion Group related to the information they need. However a broad topic field may itself be a Discussion Group and thus contain User Posts .

Utilizing the broad topic fields users locate an area of knowledge they need. As discussed above within each broad topic field are related Discussion Groups . The Discussion Groups are further refinements of the broad topic field to which they relate. Users search through a list of Discussion Groups within the broad topic field to determine which Discussion Group most closely relates to the information they need. Once a Discussion Group is found relating to the information needed the user searches through a list of User Posts located in the chosen Discussion Group .

In addition to obtaining information from the User Posts previously located in the Discussion Group users may contribute their own documents to the Discussion Group thereby increasing the knowledge base available in the Discussion Database . To contribute documents users select the document they want to contribute and inform the system utilizing the Discussion Database Interface Page discussed below. The system then adds the document to the list of available documents contained in the Discussion Group and makes the corresponding document available to other users of the Discussion Database .

The Discussion Database is a dynamic continuously growing entity. The more the Discussion Database is used the more it grows. The Discussion Database as a whole increases as users continue to contribute documents relating to the various Discussion Groups . For example in Joe decides he needs information about transition management projects on mergers of Nuclear Reactor companies. Joe first searches a list of broad topic fields and determines that the Transition Management topic is the best topic to search in more detail. He then searches through a list of Discussion Groups associated with the Transition Management topic field and determines that TMGT Special Projects Discussion Group is the most closely related to the information he needs. Joe then reads through the User Post contained in the TMGT Special Projects Discussion Group and finds the information he needs. Joe then decides to contribute a document he wrote concerning other TMGT Special Projects and proceeds to post it to the system. In the end a user acquired the knowledge he needed and as a result the Discussion Database increased its available knowledge base. Thus it can be seen that the use of a continuously growing knowledge database dramatically increases productivity and organizational knowledge without having to continuously rely on outside sources.

The Discussion Database Interface Page describes the various Discussion Groups which are available to the user of the M A Engine of the present invention. The Discussion Database Interface Page also subscribes the user to the individual Discussion Groups used most often by the user. is an illustration of a Discussion Database Interface Page .

In one embodiment the Discussion Database Interface Page may include a Discussion Group List having a list of broad topic fields and Discussion Groups . As discussed above a broad topic field may itself be a Discussion Group .

Each Discussion Group may have a Description associated with it. Each Description includes a string of descriptive data or summary of what type of information is contained in the related Discussion Group . The Description is preferably kept short to decrease the overall size of the Discussion Group List. However the Description may be as long as needed to adequately inform users as to the contents of a particular Discussion Group .

By describing the categories of information within the Discussion Groups a user may effectively select the categories on the Discussion Database Interface Page which are most relevant. As an option the aforementioned string of descriptive data may constitute a link to the data. Also a user may subscribe and access the categories of data by executing only one user action namely clicking on the appropriate Discussion Groups on the Discussion Database Interface Page .

As such the Discussion Database Interface Page is utilized by the user to subscribe to and access individual Discussion Groups . When a user wishes to join a Discussion Group the user selects the appropriate Discussion Group from the Discussion Group List. The corresponding Discussion Group is then added to the Discussion Groups the user can utilize. By subscribing only to Discussion Groups pertinent to the particular user s interest and needs the user can more quickly obtain needed information. Since the number of Discussion Groups subscribed to by a particular user is generally much less than the total number of Discussion Groups available the user does not need to search through a large list of Discussion Groups every time he or she needs information. Instead the user selects only those Discussion Groups that he or she will need most often. Thereafter when the user desires information he or she will generally only need to search through the Discussion Groups the user has subscribed to. Thus the search time is drastically reduced after the first use of the system.

The use of the Discussion Database in combination with the Discussion Database Interface Page creates a wealth of information useful for the entire organization utilizing the system. The Discussion Database contains not only information provided by the organization that sets up the Discussion Database but also information provided by users of the system. The Discussion Database coupled with the Discussion Database Interface Page creates a living library which grows with each use and grows with the knowledge of its users. As users acquire more knowledge from experience and other outside sources they transfer that knowledge to the Discussion Database utilizing the Discussion Database Interface Page . The transfer of knowledge to the Discussion Database increases the knowledge contained in the Discussion Database and helps keep the information contained in the Discussion Database updated as new developments arise in various fields.

It should be noted that the Discussion Database Interface Page may be employed to provide effective access to any type of database including but not limited to the database associated with the M A Engine.

One embodiment of the present invention is thus a web based tool for use by clients to provide a central source for executing project management tasks understanding industry specific solutions and accessing a planning guide. is a home page of one embodiment of the web based tool of the present invention. As shown various categories of project management tools a planning guide and industry solution packs relating to a merger and acquisition may be retrieved from a single interface . Such management tools include a reporting and tracking tool decision management tool value realization information execution tool and reference tool . is a site map of one embodiment of the web based tool of the present invention.

The Project Management Tools allow users to access templates create store and retrieve documents and generate reports. These tools are separated into five categories.

The reporting and tracking tool ensures that the M A effort is being planned properly and that progress is being effectively monitored. There are multiple Reporting and Tracking functions namely an executive dashboard status reporting key milestones and project planning.

Optionally a preview of the item may be displayed after its creation and prior to it being stored. As another option the accomplished milestones may be graphically outputted. The milestones may also be outputted in terms of time. In a further aspect of the present invention the status reports may relate to projects such as customers customer service employees financials and technology.

Executive Dashboard Provides interested parties a single checkpoint area to understand the current state of the merger.

Executives must be able to identify and track realized benefits as well as issues securely and quickly. The Executive Dashboard is a consolidated tool that provides a means for executives to access key information in a quick and illustrated manner. For Release I the Executive Dashboard may include two or more categories including a Merger Integration Balanced Scorecard and a Progress Status Report.

As an option the milestones may be differentiated in terms of being planned and made. As a further option the issues may be differentiated in terms of being open late and resolved.

In another aspect of the present invention the projects may include customers customer service employees financials and technology. In a further aspect of the present invention the criteria may include not started on schedule behind schedule at risk not applicable and complete.

The first topic the Merger Integration Balanced Scorecard can include is an Issue Resolution section. This will provide executives with an opportunity to review information on open resolved and executive attention issues. Secondly the Scorecard will include an update of Key Milestones including the total number of Planned Milestones as well as the number of Made Milestones.

The Progress Status section looks at 5 projects including Customer Customer Service Employee Financials and Technology. Each Line of Business is scored in 6 different areas Define Requirements Design Development System Test Integrated Test and Mock Conversion . Scores include Not Started black On Schedule green Behind Schedule yellow At Risk red Not Applicable black and Complete a grayed out field .

The Executive Dashboard program will exhibit basic functionality. Since the user is not required to input any data there are no required fields. However listed below are the field names that will appear on the page. Most of the fields on the Executive Dashboard page are static. Those fields that are marked with an asterisk. These fields are integer fields. They will display a number generated by the program.

The Executive Dashboard program does not require data input by the user. A Perl script will be executed performing a series of queries by accessing the database. Aggregate function will be built into the Issue Resolution query in order to obtain  Open High Open and  Resolved and  Late. A returned Search Result will display all requested information as seen in the screen shot below.

The Executive Dashboard is a report in and of itself. It provides executives with detailed information regarding Issue Resolution and Key Milestones going on in the merger acquisition as well as information regarding the company its financials customers employees and technology.

The Status Reporting function allows users to create and track status reports on the progress of a process for themselves others and teams within the Workbench.

The main screen serves as an entry point to the Status Reporting function. The Main Screen will list the records of the current Status Reports within the Workbench sorted by Period Ending. The Main Screen should be populated with high level data regarding the Status Reporting entries. The data is stored in an Access database and retrieved using CGI scripts.

The results will be broken into groups of 10 results at a time. If more than 10 results exist a link to the Next 10 records will be displayed on the bottom right hand corner of the results set. If the user proceeds to the next 10 results a link to move back to the Previous will activate on the bottom left hand corner of the display.

From the Main Screen each Status Report displayed is linked to the details of the respective Status Report through the Owner column. By clicking on an entry the Display Screen is shown. This screen will display the entire Status Report.

The Status Report will display each field used within a Status Report and the values for the particular Status Report. None of the fields are editable in this screen. The following lists all the fields their formats and a description 

From the display screen the user is given three new navigational options. First the user can click Back to return to the Main Screen display. This should take them back to the exact set of 10 results the came from. Meaning if there are more than 10 Status Reports listed and they clicked Next to move to the next set and selected a Status Report from that list when they click Back from the Display Screen they are returned to the second set of 10 and not the beginning of the list.

Secondly the user can click Print which will bring up the browser s print dialog box in order to print the Status Report.

And finally the use can click Edit By doing this the user is sent to a new page that contains all of the fields seen in the Display Screen but with many of them editable. The following fields are editable 

Another area of functionality allows the user to create a Status Report using the Workbench which stores the data in the Workbench database and is retrievable from the Status Reporting function and the Deliverables Library.

The user must provide data into the required fields and is given optional fields for certain information. If one of the required fields is not completed the user will be prompted to include the data in to the missing required fields. The error message will list the field s missed and provide a link for the user to return and complete those fields. The only field that is not required on the first create screen shown below is the Submitted By field. This field should be used if a third party is submitting a Status Report on behalf of somebody else.

After a user has successfully completed a status report they will see a preview of the status report. From the preview screen the user can 1. Go back and edit the report or 2. Save the Status Report in the database. Note that a user can always return at a future date time to edit the status report as described above.

The create function is separated into 2 main screens. The first screen requires the following fields 

Once all fields have been validated one of four screens will be displayed based on the user s inputs 

When the user completes all the fields the user can click Preview. By doing this the user is shown exactly what his her Status Report looks like and will look like when displayed in the Display Screen.

From the Preview screen the user will see all the inputs entered in non editable text. The Accomplishments Goals and Issues Risks Concerns will be displayed in a Bullet format

If the user finds a mistake or wants to make any changes whether it is an edit or adding deleting an Accomplishment Goal or Issue Risk Concern they can in this way and when satisfied click Preview again.

Once satisfied with the Preview the user would click Save Report. By saving the report the new Status Report is inserted into the appropriate tables in the Workbench Database and the user is returned a confirmation dialog box thanking them for their submission and is redirected to the Main Screen.

Another area of functionality allows the user to search for one or more Status Reports in the Workbench database using a specified search criteria. depicts an embodiment of the present invention which provides a method for querying a database which is storing a plurality of items generated by multiple users. In operation users are allowed to create an item with a plurality of fields. The item is stored in a database in operation . The item should be stored with an identifier corresponding to the user. Upon receipt of a search query in operation the database is searched in operation using the search query. In operation the identifiers of a plurality of items found during the search are displayed. Upon selection of the associated identifier of one of the items the fields of that item are depicted in operation .

In an aspect of the present invention the item may include a report a milestone an issue and or a project plan. Optionally the item may also include information on a merger or acquisition. In another aspect of the present invention the identifier corresponding to the user may include a name of the user a team on which the user works and or a time a period is to end.

In an embodiment of the present invention a user may be allowed to edit a predetermined set of the fields upon depicting the same in response to the selection of the associated identifier. In a further embodiment of the present invention a preview of the item may be displayed after the creation thereof and prior to the storing thereof. In an additional embodiment of the present invention a report may be generated that includes a predetermined number of the fields of the items corresponding to the depicted identifiers in response to a user action.

If the user conducts a search with no search criteria all of the Status Reports in the database will be listed displaying at a time for example. If no Status Reports are found that match the search criteria a screen will appear stating that no results were found and a link returning them to the Search Screen will be present.

A successful search will display the results in a table format. These results will be displayed in descending order by using the Period Ending Date. The search results screen will display a set of 10 results. If more than 10 results are found each result screen will link to the next set of 10 results.

The edit search criteria option returns the user to the search criteria to edit the fields or values being searched.

The generate detail report is yet another area of functionality allows the user to generate a Detail Report of all status reports obtained from the search. Detail Reports will display the complete Status Report of every result found in the search separating each one with a Horizontal Rule. The user will have a choice to Print the detailed report or go Back to the search results. The fields within the Detail Report are listed below.

Summary Reports are created by clicking on the Generate Summary Report on the Search Results screen. The user will be able to print the report by clicking Print or return to the Search Results by clicking Back . The Summary report will resemble the initial Search Results screen and the Main Screen but will not limit the number of records shown to 10 and will contain one extra field. The fields within the Summary Report are listed below 

The Help screen is meant to provide basic help on the Status Reporting function. The Help Screen contains three areas 

Status Reporting is composed of three modules. These modules are named Create Search and Help. All of the Status Reports are stored in the Workbench database within 3 tables. The fields that allow only one entry StatusID Owner Team Period Beginning. Period Ending Comments are within the tblStatus Report table with the StatusID being automatically generated . The Goals Accomplishments are stored within the tblStatus Tasks table Each one is assigned a TaskID and is given a 1 or 4 to differentiate between Accomplishments and Goals respectively .

All tables are stored within an ODBC compliant database. The five modules and their relationship to the issues and comments table is shown below 

It should also be noted that the input forms for the CREATE SEARCH and UPDATE modules are generated by a module that will extract data from the tblMembers table and the tblMergerTeam tables from within the database

The Status Reporting application will create Status Reports. It will also have the capability to generate reports of Status Reports.

The Key Milestones function allows users to create and track key milestones related to the M A Effort.

The first area of functionality allows the user to create Key Milestones using the Workbench which stores the data in the Workbench database. The user must provide data into the required fields. If one of the required fields is not completed the user will be prompted to include the data in to the missing required fields. After a user has successfully completed an Key Milestone they will see a preview of the Key Milestone. From the preview screen the user can 1. Go back and edit the Key Milestone or 2. Save the Key Milestones in the database. Note that a user can always return at a future date time to edit the Key Milestones.

The user must input a value into each of the required fields. Also certain validations occur specifically for the date fields. The following rules are validated 

If one or more fields that are required are left blank an error message will appear displaying the list of fields that are incorrect. Once all fields have been validated a Preview screen will be displayed which will allow the user the opportunity to view what his her Key Milestone will look like when displayed and based on that either Submit the Key Milestone or go back and Edit the Key Milestone. When the user clicks Submit the new Key Milestone will be entered into the database the user will receive a confirmation dialog box and will be returned to the Display Screen listing the most recent Key Milestones.

Another area of functionality allows the user to search for Key Milestones in the Workbench database using a search criteria. If the user conducts a search with no search criteria all of the Key Milestones in the database will be listed displaying 10 at a time. If no Key Milestones are found that match the search criteria a screen will appear stating that no results were found and a link will be provided to return and edit the search criteria.

A successful search will display the results in a table format. These results will be displayed in descending order by using End date to sort them. The search results screen will display a set of 10 results. If more than 10 results are found each result screen will link to the next set of 10 results.

If a user clicks on a link made from the search or main screen the user will see the specific Key Milestone. The fields that will be shown include 

If a user wants to add fields or make changes to their status report they have editing ability on most fields. The following fields can not be edited 

The remainder of fields can be edited. In addition to the fields shown when a milestone was created when a Key Milestone is being edited the user will have a few new fields to work with. Each time a person wants to edit the Key Milestone they will have the ability to add a comment and create a revised start end date. The following fields will be added when a Key Milestone is added 

If the user enters any text or makes a change to the Comments Revised Start or Revised End field they must enter a value for Name. If they do not they will receive a validation error returning them back to the form. When the user completes the edits s he can as they did when they created a key milestone first preview their key milestone and than save it into the database. The new changes and additions can be seen when the Key Milestone details are displayed.

Yet another area of functionality will allow the user to generate a Detail or Summary report of key milestones. This report can be created based on the same criteria that are provided through the SEARCH functionality. Detail Reports are created by clicking on a button labeled Generate Detail Report on the Search Results screen. The user will have a choice to print the report. The fields within the detail report are identical to those described in the Display Results Screen .

Summary Reports are created by click on a button labeled Generate Summary Report on the Search Results screen. The user will be able to print the report or simply view it on the screen. The summary report will resemble the initial search results screen but will not limit the number of records shown to 10. The fields within the list report are the same as the fields in the Search Key Milestones Results screen.

The Help section of Key Milestones will include three areas and will be accessible from any Key Milestone screen. The three areas include 

Key Milestones is composed of five modules. These modules are named Create Search Display Searched Results Generate Reports and Edit Key Milestones.

All tables are stored within an ODBC compliant database. The five modules and their relationship to the issues and comments table is shown below 

It should also be noted that the input forms for the CREATE SEARCH and UPDATE modules are generated by a module that will extract data from the tblMembers table and the tblMergerTeam tables from within the database

The Project Planning function allows users to upload and track project planning files for themselves others and teams within the M A effort. The Project Planning function is to be used by both Andersen Consulting and client personnel.

The main screen serves as an entry point to the Project Planning function. The Main Screen will list the records of the current Project Planning files uploaded within the Workbench. The Main Screen should be populated with high level data regarding the Project Planning entries. The data is stored in an Access database and retrieved using CGI scripts.

The results will be broken into groups of 10 results at a time. If more than 10 results exist a link to the Next 10 records will be displayed on the bottom right hand corner of the results set. If the user proceeds to the next 10 results a link to move back to the Previous will activate on the bottom left hand corner of the display.

This area of functionality allows the user to create a Project Planning file using the Workbench and a template. A Project Planning template is provided. This template will give the users a generic template of how Project Planning files should look.

By click on the template the file should open in its respective application. Once the user using the template creates his her Project Planning file the file should be saved on their local disk drive.

This functionality is dependent on the assumption that once the file was created the user would upload the file into the Workbench repository. The user is required to complete a short form including the following fields 

The user must select a value for each of the fields. If one or more of the fields are left blank and the user clicks Attach an error message should appear displaying the list of fields that the user neglected to complete followed by a link to return to the Create Screen. If this occurs all the fields that were completed appropriately by the user should remain selected except for the File To Attach field. This field will reset automatically and must be entered again.

When all appropriate fields are entered and the Attach button is click the user will receive a confirmation pop up window stating Thank You for attaching your Project Planning File. Once the user clicks OK the user is returned to the Main Screen.

If the file that the user is attempting to upload already exists in the Project Planning repository the user will receive an error message stating the file already exists. The user will be given two links from this error page. One will allow the user to return to the Create Screen and select a different file or change the file name. The second will link to a for identical to the Create Screen but will allow the user to submit a file that already exists. By selecting the Overwrite link the user will have to re enter the file name and click Overwrite on the Overwrite form. A warning message will be displayed on the form notifying the user that if they proceed to copy a file with the same name as one that already exists the old file will be lost and replaced with the new one. This is a irreversible function.

Once a file is uploaded the CGI script creates a new entry into the Access Database and this new entry should appear as the top item on the Main Screen Display.

This area of functionality allows the user to search for all Project planning files in the Workbench database using a specified search criteria. If the user conducts a search with no search criteria all of the Project Planning files in the database will be listed displaying at a time as they were displayed in the Main screen. If no Project Planning are found that match the search criteria a screen will appear stating that no results were found and provide a link back to change the search criteria.

The user can use any of the below fields or any combination of them into the Search Screen input form 

Using the search criteria if no search criteria is chosen all the results are shown the program will search the Access Database for any records meet the specified criteria.

A successful search will display the results in a table format. These results will be displayed in descending order by using the Date Created. The search results screen will display a set of 10 results. If more than 10 results are found each result screen will link to the next set of 10 results.

The Help screen is accessible from any screen within the Project Planning function. The Help screen is divided into 3 sections About Project Planning About The Template Navigation.

The About Project Planning section will provide a brief explanation of what is meant by Project Planning and how it can be used within the M A effort.

The About The Template section will provide a list and description of all the fields the user must complete to upload a Project Planning File.

The Navigation section will list and describe each navigational option the user has. Each button or link within the Project Planning function will be listed and described.

The Help screen has three links representing each of the three sections. The user can click on one of these links to move to a particular section or the user can simply scroll up or down with the right hand side scroll bar.

Project planning is composed of two modules. These modules are named Create and Search. All of the Project Planning files are stored in the Deliverables Repository and the owner data is stored in the Workbench database within I table.

The Decision Management tools provide a forum to review and update important decisions being made that impact the merger. There are five Decision Management functions namely key decisions issue management change control readiness assessment and a discussion database.

In an aspect of the present invention the process may be a merger or acquisition. In another aspect of the present invention the network may includes a wide area network. More specifically in an embodiment of the present invention the network may include the Internet.

In another embodiment of the present invention requests for increasing a scope of the process may also be received and stored. In a further embodiment of the present invention the items may include status reports milestones issues and or workplans.

The key decision functionality lists the major merger wide executive decisions that have been determined. This provides a simplistic yet critical service of keeping all interested parties abreast of various happenings.

The Issue Management application allows users of the M A Workbench to track issues relating to the Merger or Acquisition. A user can create an issue that can be serviced by the appropriate personnel on the M A project.

A first area of functionality allows the user to create an issue in the ISSUES database. The user must provide data into the required fields. If one of the required fields is not completed the user will be prompted to include the data in to the missing required fields. After a user has successfully created an issue a confirmation screen will appear. This screen will contain the entire set of fields that are associated with the issue.

Another area of functionality allows the user to search for an issue in the ISSUES database using a search criteria. If the user conducts a search with no search criteria all of the issues in the issues database will be listed. If no issues are found that match the search criteria a screen will appear stating that no results were found. The user must input the fields listed below into the SEARCH ISSUE input form 

A successful search will display the results in a table format. These results will be displayed in descending order by using the DATE ENTERED. The search results screen will display a set of 10 results. If more than 10 results are found each result screen will link to the next set of 10 results. The top of the results screen will display the search criteria and at the bottom the number of matching records and the total number of records will display.

Still yet another area of functionality allows a user to update an issue whose STATUS field is either Open or Deferred . A user cannot update a Closed Issue . In addition to providing updates to an issue the EDIT ISSUE screen allows the user to add recommendation to an ISSUE.

The present area of functionality will allow the user to generate a report of issues. This report can be created based on the same criteria that are provided through the SEARCH functionality. Issue Reports are created by clicking on a button labeled Generate Report on the Search Results screen. The user will have a choice whether to print the report to the screen or directly to the printer. The fields within the report are listed below.

Issue Management is composed of five modules. These modules are named Create Search Edit Update Summary Report and Detail Report. All of the issues are stored in the ISSUES table. This table is stored within an ODBC compliant database.

It should also be noted that the input fields for the CREATE SEARCH and UPDATE modules are generated by extracting data from Member table and Team table.

The first screen in the Issue Management application is the list of ISSUES. This screen presents the user with a list of all issues order by date created. The user is able to go to CREATE SEARCH and HELP from any of the pages within the application.

The Issue Management application will create Issue. It will also have the capability to generate detail summary reports of issues.

The Readiness Assessment function allows users to upload and track Readiness Assessment files for themselves others and teams within the M A effort. The Readiness Assessment function is to be used by both Andersen Consulting and client personnel.

The main screen serves as an entry point to the Readiness Assessment function. The Main Screen will list the records of the current Readiness Assessment files uploaded within the Workbench. The Main Screen should be populated with high level data regarding the Readiness Assessment entries. The data is stored in an Access database and retrieved using CGI scripts.

The results will be broken into groups of 10 results at a time. If more than 10 results exist a link to the Next 10 records will be displayed on the bottom right hand corner of the results set. If the user proceeds to the next 10 results a link to move back to the Previous will activate on the bottom left hand corner of the display.

This area of functionality allows the user to create a Readiness Assessment file using the Workbench and a template. A Readiness Assessment template is provided. This template will give the users a generic template of how Readiness Assessment files should look.

By click on the template the file should open in its respective application. Once the user using the template creates his her Readiness Assessment file the file should be saved on their local disk drive.

This functionality is dependent on the assumption that once the file was created the user would upload the file into the Workbench repository. The user is required to complete a short form including the following fields 

The user must select a value for each of the fields. If one or more of the fields are left blank and the user clicks Attach an error message should appear displaying the list of fields that the user neglected to complete followed by a link to return to the Create Screen. If this occurs all the fields that were completed appropriately by the user should remain selected except for the File To Attach field. This field will reset automatically and must be entered again.

When all appropriate fields are entered and the Attach button is click the user will receive a confirmation pop up window stating Thank You for attaching your Readiness Assessment File. Once the user clicks OK the user is returned to the Main Screen.

If the file that the user is attempting to upload already exists in the Readiness Assessment repository the user will receive an error message stating the file already exists. The user will be given two links from this error page. One will allow the user to return to the Create Screen and select a different file or change the file name. The second will link to a for identical to the Create Screen but will allow the user to submit a file that already exists. By selecting the Overwrite link the user will have to re enter the file name and click Overwrite on the Overwrite form. A warning message will be displayed on the form notifying the user that if they proceed to copy a file with the same name as one that already exists the old file will be lost and replaced with the new one. This is a irreversible function.

Once a file is uploaded the CGI script creates a new entry into the Access Database and this new entry should appear as the top item on the Main Screen Display.

This area of functionality allows the user to search for all Readiness Assessment files in the Workbench database using a specified search criteria. If the user conducts a search with no search criteria all of the Readiness Assessment files in the database will be listed displaying at a time as they were displayed in the Main screen. If no Readiness Assessment are found that match the search criteria a screen will appear stating that no results were found and provide a link back to change the search criteria.

The user can use any of the below fields or any combination of them into the Search Screen input form 

Using the search criteria if no search criteria is chosen all the results are shown the program will search the Access Database for any records meet the specified criteria.

A successful search will display the results in a table format. These results will be displayed in descending order by using the Date Created. The search results screen will display a set of 10 results. If more than 10 results are found each result screen will link to the next set of 10 results.

The Help screen is accessible from any screen within the Readiness Assessment function. The Help screen is divided into 3 sections About Readiness Assessment About The Template Navigation.

The About Readiness Assessment section will provide a brief explanation of what is meant by Readiness Assessment and how it can be used within the M A effort.

The About The Template section will provide a list and description of all the fields the user must complete to upload a Readiness Assessment File.

The Navigation section will list and describe each navigational option the user has. Each button or link within the Readiness Assessment function will be listed and described.

The Help screen has three links representing each of the three sections. The user can click on one of these links to move to a particular section or the user can simply scroll up or down with the right hand side scroll bar.

Readiness Assessment is composed of two modules. These modules are named Create and Search. All of the Readiness Assessment files are stored in the Deliverables Repository and the owner data is stored in the Workbench database within 1 table.

The Readiness Assessment application will upload files associated with Readiness Assessment into the Deliverables Repository while recording the new deliverable within the Access database.

The discussion database gives users a medium for asking and answering merger questions in a discussion thread. Such database was discussed hereinabove during reference to .

Value realization of provide context to understand actual financial costs benefits and potential value related to the merger. There are four value realization functions namely benefits realization budget management business cases and value analysis.

Benefits realization determines the benefits to performing certain activities or making certain integration decisions. Budget management allows users to create and retrieve budgets and financials for all projects. Business cases allows users to create and retrieve business case information for all merger projects and initiatives. Value analysis provides a framework for determining value to the client throughout the entire merger lifecycle.

The Execution tools of include many of the integration specific activities that need to be completed. There are five Execution functions namely communications quality management risk management testing and conversion events.

Communications allows users to access all customer and employee communications. Quality management provides area to address quality planning and reviews and to calculate project metrics. Risk management addresses all risks impacts to the integration such as customer support and contingencies. Testing provides a centralized tool to perform all scripting execution and SIR resolution. Conversion events contains all the tools and components required for running the conversion command center

The Reference section contains additional tools that are necessary during the M A effort. There are four Reference functions namely deliverables library contacts calendars and organization charts.

The Deliverable Repository function allows users to create modify and track all Deliverable types available in the Workbench for themselves others and teams within a merger acquisition.

For any given deliverable type more detailed logic may be obtained in the design documentation of the specific function you are interested in.

The introductory screen serves as an entry point to the Deliverables Repository function. The Introductory Screen will list all deliverables accessible within the Workbench. Each Deliverable type listed on Introductory screen will be hyperlinked to the appropriate function s Main screen. On the Introductory screen the user has the ability to Create Search or obtain Help.

When the user clicks a deliverable type on the Introductory Screen the Main Screen of that function results. The Main Screen serves as an entry point to a respective function. The Main Screen defaults the last 5 records of the that function within the Workbench. It is at the Main Screen that a user may begin navigating the respective function. The design documentation for a specific function may be viewed in order to access more detailed information.

From the Introductory screen the user may opt to create a deliverable by pushing the Create button. In doing so the Create Deliverable display screen is viewed. The user must obtain a deliverable template for the document they wish to create as well as upload a deliverable type that it is not provided in the Workbench. Data must be provided into the required and optional fields. If one of the required fields is not completed the user will be prompted to include the data in to the missing required fields. The error message will list the field s missed and provide a link for the user to return and complete those fields. A list of all fields on the Create Deliverable screen are listed below. Those fields that are required fields are marked with an asterisk.

Once the user fills out the form they can push the Upload Files button in order to save it in the database.

From the Introductory screen the user may opt to search a deliverable by pushing the Search button. In doing so the Search Deliverables display screen is viewed. Here the user is presented with five input fields without any required fields including 

The user has the ability to generate a search that is extremely broad or very specific. For example if Search is clicked without pro filling any fields a search result will be displayed with every deliverable stored in the entire Workbench. If Document Type and Owner are pre filled then all the specified documents belonging to a specific owner will display. Finally the user may specify a date range that a specific deliverable was generated. A successful search will display the results in a table format. These Search results will be displayed in groups of five. If more than five results exist a link will appear that reads Next 10. Once those documents appear a link will appear that reads Prev 10 indicating to the user that they may return to the previous search results.

For each document that is displayed in a search result the user has the ability to view the document by clicking on it. The document will display in read only format.

The Deliverables Repository is comprised of 4 modules including Create Search Display Search Results Edit Status Reports. All Deliverables are stored in the Workbench database within tables. All tables are stored within an ODBC compliant database.

It should also be noted that the input forms for the CREATE SEARCH and UPDATE modules are generated by a module that will extract data from the tblMembers table and the tblMergerTeam tables from within the database

The first screen in the Deliverables Repository application is the Introductory Screen. This screen presents the user with a list of all Deliverable types stored in the Workbench. The user has two options at the Introductory screen. They can access a specific function Status Reports Issue etc by clicking on the hyperlinked deliverables listed. Or the user may click on CREATE SEARCH and HELP on this Introductory Screen. When Create is clicked the Create Deliverable screen is displayed. When the Search button is clicked the Search Deliverable screen is displayed and finally when Search is clicked the Search Deliverables screen is displayed.

The Deliverables Repository generates and accesses a variety of reports and documents necessary for a successful M A effort. Every document used through an M A engagement will be linked to the Deliverables Repository.

The Contacts function will be used as a listing of all members from both the client organization and Andersen Consulting working on the M A effort.

The create area within Contacts is a bit misleading. That is because every person within the M A effort is originally created within the Workbench by an Administrator within the Administrator Functions of the Workbench. In this function individuals can log on and edit and their existing profiles. The Administration function will create Contacts assigning them a password. With that a user can select his her name enter the password that was assigned to them and assuming they entered the same password edit their profile. The following fields are available to the user 

No fields are required by themselves but some are dependent on others and therefore can become required. For example if a user wants to change their password they must enter their Old Password and their new password twice. The Password field will also be validated to four characters digits.

Once the user is complete entering his her information they can click Submit to save their changes into the database. They will receive a confirmation dialog box and will be returned to the main screen.

This function allows users to use a wildcard keyword search of all contacts using either the name team email office team. This requires the user to select from a drop down box which field to search by and type in any text or parts of text that should be used as search criteria.

All tables are stored within an ODBC compliant database. The five modules and their relationship to the issues and comments table is shown below 

It should also be noted that the input forms for the CREATE SEARCH and UPDATE modules are generated by a module that will extract data from the tblMembers table and the tblMergerTeam tables from within the database

The first screen in the Contacts application is the Main screen. This screen presents the user with a list of all the Contacts sorted by Name. The user is able to go to CREATE SEARCH and HELP from any of the pages within the application.

The Organization Charts function allows users to upload and track Organization Charts files for themselves others and teams within the M A effort. The Organization Charts function is to be used by both Andersen Consulting and client personnel.

The main screen serves as an entry point to the Organization Charts function. The Main Screen will list the records of the current Organization Charts files uploaded within the Workbench. The Main Screen should be populated with high level data regarding the Organization Charts entries. The data is stored in an Access database and retrieved using CGI scripts.

The results will be broken into groups of 10 results at a time. If more than 10 results exist a link to the Next 10 records will be displayed on the bottom right hand corner of the results set. If the user proceeds to the next 10 results a link to move back to the Previous will activate on the bottom left hand corner of the display.

This area of functionality allows the user to create a Organization Charts file using the Workbench and a template. A Organization Charts template is provided. This template will give the users a generic template of how Organization Charts files should look.

By click on the template the file should open in its respective application. Once the user using the template creates his her Organization Charts file the file should be saved on their local disk drive.

This functionality is dependent on the assumption that once the file was created the user would upload the file into the Workbench repository. The user is required to complete a short form including the following fields 

The user must select a value for each of the fields. If one or more of the fields are left blank and the user clicks Attach an error message should appear displaying the list of fields that the user neglected to complete followed by a link to return to the Create Screen. If this occurs all the fields that were completed appropriately by the user should remain selected except for the File To Attach field. This field will reset automatically and must be entered again.

When all appropriate fields are entered and the Attach button is click the user will receive a confirmation pop up window stating Thank You for attaching your Organization Charts File. Once the user clicks OK the user is returned to the Main Screen.

If the file that the user is attempting to upload already exists in the Organization Charts repository the user will receive an error message stating the file already exists. The user will be given two links from this error page. One will allow the user to return to the Create Screen and select a different file or change the file name. The second will link to a for identical to the Create Screen but will allow the user to submit a file that already exists. By selecting the Overwrite link the user will have to re enter the file name and click Overwrite on the Overwrite form. A warning message will be displayed on the form notifying the user that if they proceed to copy a file with the same name as one that already exists the old file will be lost and replaced with the new one. This is a irreversible function.

Once a file is uploaded the CGI script creates a new entry into the Access Database and this new entry should appear as the top item on the Main Screen Display.

This area of functionality allows the user to search for all Organization Charts files in the Workbench database using a specified search criteria. If the user conducts a search with no search criteria all of the Organization Charts files in the database will be listed displaying at a time as they were displayed in the Main screen. If no Organization Charts are found that match the search criteria a screen will appear stating that no results were found and provide a link back to change the search criteria.

The user can use any of the below fields or any combination of them into the Search Screen input form 

Using the search criteria if no search criteria is chosen all the results are shown the program will search the Access Database for any records meet the specified criteria.

A successful search will display the results in a table format. These results will be displayed in descending order by using the Date Created. The search results screen will display a set of 10 results. If more than 10 results are found each result screen will link to the next set of 10 results.

The Help screen is accessible from any screen within the Organization Charts function. The Help screen is divided into 3 sections About Organization Charts About The Template Navigation.

The About Organization Charts section will provide a brief explanation of what is meant by Organization Charts and how it can be used within the M A effort.

The About The Template section will provide a list and description of all the fields the user must complete to upload a Organization Charts File.

The Navigation section will list and describe each navigational option the user has. Each button or link within the Organization Charts function will be listed and described.

The Help screen has three links representing each of the three sections. The user can click on one of these links to move to a particular section or the user can simply scroll up or down with the right hand side scroll bar.

Organization Charts is composed of two modules. These modules are named Create and Search. All of the Organization Charts files are stored in the Deliverables Repository and the owner data is stored in the Workbench database within 1 table.

The Organization Charts application will upload files associated with Organization Charts into the Deliverables Repository while recording the new deliverable within the Access database.

The M A Planning Guide is an interactive web based tool. This application allows its users both client and Andersen Consulting personnel to pick and choose the desired Activities and Questions that need to be considered when undertaking an M A effort. In addition the M A Planning Guide offers non client specific knowledge capital points of view best practices that have been attained through Andersen s depth of experience in the M A arena.

The Planning Guide application uses a www based client server architecture where the database driving the client side is Microsoft Access. When users click on a given Phase Activity or Task input is passed to the www server which executes a particular Planning Guide module as a CGI program. The Planning Guide application is written in Html and the Perl scripting language.

The Planning Guide application is divided into 2 distinct screens. Each screen will display more specific information depending on where the user has navigated within the application. Such details include best practices selected from the group consisting of establishing an integration leadership team making and documenting initial decisions developing guiding principles and success factors reviewing a current operating model identifying integration planning projects confirming a quick view target operating model formalizing a stakeholder analysis confirming a value of the merger or acquisition establishing governance protocols developing an initial customer retention approach developing an initial employee redeployment and retention approach developing an operations stability approach identifying stakeholder communication requirements creating initial announcements creating a short term communication plan confirming model selection criteria performing mapping defining a target environment determining gaps defining impacts defining and estimating work iterating prioritizing defined work defining an integration sequence determining delivery phases and dates developing a human resources approach developing an operations approach and developing a technology approach.

This frame will display an item of information. This frame is not displayed when the user first enters the Planning Guide Application. This screen is displayed when a user has selected a Menu Item from the Menu Frame which is described below .

The left side of the Content View frame will contain a back and next navigation button. In situations where a user must return to the full Introduction Screen a home navigation button will be displayed. The back button will return the user to a previous screen. The next button will cause the next item in the menu list to be displayed.

The right side of the Content View frame will display the text for a given area that the user has selected. If the amount text is larger than the right side a scroll bar will appear to allow the user to view all of the text.

This frame will contain the name of the application. The name of the application is The Financial Services Mergers and Acquisitions Planning Guide for example.

This frame will always be located at the top of the Introduction Screen. No hyperlinks or navigation features are contained in this frame.

This frame will provide navigation to the introductory sections of the Planning Guide application. It will contain three navigation buttons. When one of these buttons is clicked a drop down menu will appear. The table below describes exemplary navigation buttons and their respective menu items 

The Picture Frame will display a picture of a bridge for example. The entire frame will be populated by the picture. The picture frame will not provide navigation features.

This frame will display a chevron shape. The chevron shape will provide navigation to the phase areas of the application. When a user clicks on a specific area inside of the chevron shape the application will display the Display View this is described in the next section . A user click on a chevron navigation area will cause the Display View to display a specific set of frames. The areas within the Chevron shape are classified as either Phase navigation areas inner or Manage Transition navigation areas outer .

This frame will display a chevron shape. This frame will always be located at the top of the Display Screen. The chevron shape will provide navigation to the phase areas of the application and also provide information on the entry exit criteria for a given phase.

Unlike the Chevron frame in the Introduction Screen this frame will not provide navigation to the Manage transition areas of the application. The Phase Frames that are described later on will provide this functionality.

When a given phase navigation area is clicked a yellow box will appear over the top of the area. The Phase frame will also be displayed below the Chevron frame. The Phase frame will always contain the content for the phase that was clicked on. The yellow box will always appear on top of the Phase Navigation area when it is displayed.

The Chevron frame will contain an Entry Criteria button and an Exit Criteria button. When either button is clicked a dialogue box will appear that contains some text that describes the entry or exit criteria for a given phase. The entry criteria button will be positioned at the far left of the Chevron Frame. The exit criteria button will be positioned at the far right of the Chevron Frame.

The Chevron Frame will contain a Home button. The location of this button is not yet decided. Clicking this button will cause the Introduction Screen to be displayed.

This frame will display an interactive diagram for a given phase. Each phase will have a unique diagram. However every diagram will always contain a Manage Transition button . Clicking this button will cause the Manage Transition frame to be displayed. When this happens the Phase Frame is no longer visible.

Within Phase Frame each interactive diagram will contain groups of Activity boxes . A user click on an Activity Box will cause a drop down menu to be displayed. See which illustrates a drop down menu. The menu items will vary depending upon the Activity Box. When the user selects a menu item the Content View Frame is displayed. When this happens the Phase Frame is no longer visible. The Chevron Frame will still have a yellow box around the Phase Navigation area that was previously displayed. The user can return to the Phase View by clicking on the Content View Frame s back button.

An Activity Box within a Phase Frame will also contain a Help Question Mark icon. Clicking on this icon will display a dialogue box that contains a text overview of the Activity.

This frame will display the specific Manage Transition Frame that corresponds to a given Phase. This frame can be displayed by two different ways A user can click on a Manage Transition navigation area from the Introduction Screen s Chevron Frame. OR A user can click on the Phase Frame s interactive Phase Diagram.

The top portion is a shadow representation of the Phase that corresponds to the Manage Transition Frame. Clicking on this area will return the user to the respective Phase Frame.

The bottom portion of the Manage Transition Frame will contain Activity Boxes that will display drop down menus when clicked. When user select a menu item the Content View Frame is displayed and the Manage Transition Frame is no longer visible. Within the Content View Frame the user can return to the Manage Transition Frame by clicking on the back button.

An Activity Box within a Phase Frame will also contain a Help Question Mark icon. Clicking on this icon will display a dialogue box that contains a text overview of the Activity.

From the introduction screen home page the user may choose to navigate from the Menu Frame or the Chevron Frame. In both cases a Display screen results. The menu Frame items navigate to introductory sections of the Planning Guide as described hereinabove. If the user selects a Phase on the chevron bar the appropriate Phase detail page will show.

Referring again to the screen shot shown illustrates the Mobilize Effort Phase and its associated Stages and Activities. The chevron bar remains displayed in the Chevron Frame with the chosen Phase highlighted. The user can select Manage Transition as well. In the Phase Frames each Activity has the capability to display a drop down menu once it is clicked.

The Planning Guide has many associated documents Power Point Excel Word that pertain to M A specific content. These documents exist at the Activity Task and Question level of the Planning Guide. The user may obtain such documentation while navigating throughout the application.

The Industry Solution Packs explain key activities key risks and proven practices that can be applied to specific industries. There are four Industry Solution Packs within Financial Services 

There are several Health Services specific processes that are impacted during an M A event Ancillary Services e.g. pharmacy materials management 

There are several Insurance specific processes that are impacted during an M A event Agency Management e.g. agency automation communications selection retention training 

During the Pre Deal period a strategy is developed in the Develop Strategy phase. Maore particularly the Develop Strategy phase positions an organization evaluating mergers or acquisitions as growth options. Key activities of this phase include 

During the Analyze Target phase the organization begins a detailed assessment of a specific target. Key activities of this phase include 

During the Structure Deal phase the two organizations agree on the specifics of the transaction and begin to execute the arrangement. Key activities of this phase include 

During the Mobilize Effort phase the organization establishes the methods and resources required to communicate the deal and conduct the integration. As shown in key activities of this phase include 

In a second phase the Quick View Target Operating Model is confirmed in operation . In operation stakeholder analysis is formalized. Finally in operation the value of the merger or acquisition is confirmed.

The Define Migration phase establishes what the integrated environment will be and how the organization will migrate to it illustrates many of the key activities and subactivites that may be performed during the define migration phase.

The Integrate Operations phase the organization conducts the migration to the integrated environment. Key activities for the phase include 

The Manage Transition phase occurs throughout the entire lifecycle of the merger or acquisition. Key activities include 

Although only a few embodiments of the present invention have been described in detail herein it should be understood that the present invention may be embodied in many other specific forms without departing from the spirit or scope of the invention. Therefore the present examples and embodiments are to be considered as illustrative and not restrictive and the invention is not to be limited to the details given herein but may be modified within the scope of the appended claims.

