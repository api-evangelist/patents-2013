---

title: Computing device for state transitions of recursive state machines and a computer-implemented method for the definition, design and deployment of domain recursive state machines for computing devices of that type
abstract: A computing device for state transitions of recursive state machines and a computer-implemented method for the definition, design and deployment of domain recursive state machines for computing devices of that type; such devices are intended for the simulation of large systems involving human and automated components, particularly the type generally called “Enterprise Applications”; such devices are also applicable to a much wider range of fields, such as cognitive modelling or robotics. The commonality between the computing device and the computer-implemented method is the Subject Predicate Object Protocol (SPOP) which is used to capture instructions by the computer-implemented method for the definition, design and deployment of recursive state machines and also is the protocol used by the computing device for state transitions of recursive state machines to communicate inbound and outbound events based on the captured instructions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09378071&OS=09378071&RS=09378071
owner: PMDA SERVICES PTY LTD
number: 09378071
owner_city: 
owner_country: AU
publication_date: 20130604
---
The present invention relates to the construction of an appliance that implements executable models of complex systems involving several disparate types of activity dynamics.

It has been developed primarily for the simulation of large systems involving human and automated components particularly the type generally called Enterprise Applications . However it is applicable to a much wider range of fields such as cognitive modelling or robotics.

The description that follows will make use of examples drawn from a Human Resources Application and an Enterprise Framework Application however it can be used for any application.

Any reference to publications or acts cited in this specification is not an admission that the disclosures constitute common general knowledge in Australia or elsewhere.

In the early days of computing software was not thought of as an independent category of activity or product. In fact the word software itself only acquired widespread usage in the 1960 s. Up to the middle of the 1960s there were programs delivered to the buyer with the computing machinery hardware by the manufacturer. The more adventurous users slowly undertook to write their own programs in FORTRAN Algol or later COBOL. The first companies dedicated to developing software were founded in 1955 Computer Usage Company and 1959 Computer Services Corporation and the plan was to offer programming services.

Typically the early applications of computers were military or scientific mainly in fields of interest to the military or government e.g. census weather forecasting or mechanical translation . The first business oriented languages were introduced in the late 1950 s FLOW MATIC COMTRAN FACT then COBOL 

The introduction of symbolic compilable languages was the first step of abstraction in the separation of software yet to be openly so named from the underlying machinery. This step gave rise to two development trends leading to an independent software industry.

The first trend was motivated by the commercial imperatives of fledgling software companies. Bespoke program writing in large contracts for public or private organisations represented a narrow constricted market by comparison with the large field of business. There was strong incentive to develop pre written products which would be usable on any machine of a certain type or more ambitious still on a variety of hardware platforms compilable high level languages made this conceivable .

Given IBM s domination of the hardware market it is not surprising that many of the more successful software companies were founded by ex IBM engineers.

The initial strategy was to identify a part of business activity which was similar if not identical across the range of businesses and to reduce it to automation. Not surprisingly the first successes were in the domain of business accounting.

The approach was extended to all repeatable aspects of business. By the early 1970s the concept of Enterprise Resource Planning ERP was taking root promoted in particular by SAP. ERP software is typically made up of modules for each business function adopting modules from the same vendor almost guarantees perfect integration. However not all of one company s modules are necessarily the best of breed some vendors may specialise in particular areas e.g. supply chain or customer relationship and produce superior products in their particular specialty. This in turn raises the issue of integrating offerings from different vendors.

At this point the attractiveness of packaged software brought to the fore a new issue in business automation strategy the make or buy decision. Wholly integrated solutions were typically expensive while combining individual best of breed modules or developing in house raised architecture design and cost issues.

Software vendors responded to this new challenge in two ways. On the one hand some vendors kept the concept of a unified business solution but specialised to particular industry verticals such as banking or telecommunications. This approach enabled them to address the idiosyncratic needs of a given industry in a more precise way. Other vendors developed middleware products targeting the integration problem transaction monitors messaging platforms business hubs . Middleware is positioned between system software which addresses issues of machinery hardware drivers and operating systems and application software which addresses issues of business needs.

The whole domain of Enterprise Application Integration EAI has proved to be a major step in the evolution of business software. Initially EAI approaches were individual and ad hoc. Progressively a body of wisdom and best practices emerged and vendors followed by offering tools and products to implement those. As a result there is a new balance in the enterprise software industry while adopting integrated solutions from a single vendor still offers some advantages the availability of integration resources makes best of breed approaches less risky.

The term software engineering appeared almost simultaneously with the word software itself. Programmers inspired by existing branches of engineering were investigating how the engineering stance might apply to their work.

This concern with engineering was exacerbated by the software crisis in the 1960s. The lack of an established discipline for software construction has disastrous effects on software project costs and on the quality of results. The profession of software engineer was acknowledged as a result of two NATO conferences in the late 1960s.

The objective of software engineering is to apply a systematic disciplined quantifiable approach to the design development operation and maintenance of software. This trend is independent of subject matter. The notion of reuse had flourished much earlier. As early software was free it was shared without restraint. Some groups e.g. IBMSHARE offered catalogues of reusable components. But there were no principles to guide reuse.

The first successful systematic form of reuse was based on the concept of libraries. A library offers a collection of implementation of common functions or algorithms which can be invoked from any client program. The programmer remained responsible for designing and implementing the overarching logic flow of the program. Libraries were very successful in boosting the efficiency of programming beginning with FORTRAN mathematic and scientific libraries.

Another approach inverted the problem how to address a family of software tasks which share an overall logic flow but in which small individual parts need to be customised. This gave rise to frameworks. In a typical framework the core software can run out of the box and provide a useful function. This is made possible by the fact that all possible variable options have been given a default value. However for each such point on the software a mechanism is available to override the default and introduce newly defined behaviour. An interesting form of framework architecture is the plug in introduced in Apache and systematised in Eclipse.

The concept of framework has been generalised to more complex arrangements while maintaining the original characteristic of customisation points. In each case the effect is to facilitate software development by allowing designers and programmers to devote their time to meeting requirements rather than dealing with the details of providing a working system. Software frameworks include support programs application programming interface API and tool sets that bring together all the different components to enable development of a solution. This approach is particularly suited to business software development once the fundamental features of a given business problem are understood.

Another development in software engineering relates to the relationship between algorithms and data. According to Niklaus Wirth s formula Algorithms Data Structures Programs . There is therefore a necessary coupling between some algorithms and some data structures. Identifying and investigating the nature of such couplings led to the formulation of Abstract Data Types ADT . An ADT is a packaging of a Data type typically complex with the functions algorithms which can operate on it. Expressing a software design in terms of ADT eliminates the need to manage the coupling separately supports the factoring of the software into self contained units which are more amenable to reuse and supports the principle of information hiding in that data structures are only accessible to functions which must operate on them which protects against integrity violations and increases the potential for software quality.

The natural progression from ADT led to Objects. While ADTs are defined individually it quickly appears that they in fact form families of similar types in which one is derived from another by specialisation or conversely several can be grouped together by abstraction. Several forms of inheritance have been defined and codified in various languages. Object oriented programming has known an overwhelming success among other reasons because it is appealing to ordinary human cognition. In particular objects defined in software engineering have often been interpreted as reflections of objects in the real world partly because much of object orientation arose from simulation.

On the other hand objects tend to partition a domain of interest and fail to capture features common to different domains. Thus arose another perspective around the concept of Aspects. Tooling has been developed to incorporate Aspect oriented elements of code in Object oriented software thus taking advantage of both kinds of factoring.

All the above inventions amounted to various ways of raising the level of abstraction in the representation of what the software is meant to accomplish. In effect the larger more complex units identified in these efforts library routines framework structures ADTs Objects Aspects consisted in clustering the low level commands to the hardware instructions into aggregates associated with a concept more amenable to human cognition.

The next step in this progression was the concept of a software engine that is a construct which had a defined parameterised behaviour such that the parameters could be declared in an appropriate notation high level language 4GL etc. . In this group of innovations can be found interpreters virtual machines rules engines process engines reasoning engines etc.

Of special importance to Enterprise applications are process engines which mechanise the execution of a business process. The desired behaviour of the process is declared using an appropriate language e.g. BPMN Business Process modeling notation . Changes in the process can now be implemented without having to write new code explicitly with some process engines the high level notation must be translated by a tool similar to a compiler others are interpretive and execute the notation directly 

Similarly rules engine can execute rules declared in a rule notation e.g. Rule Speak either interpretively or after compilation. This approach to software blurs the distinction between modelling and execution and leads to the concept of an executable model.

If the granularity of the units identified and enacted by engines is such that they map to well understood business concepts the resulting software architecture is that known as Service oriented.

Many commercial packages are architected as combinations of engine and framework like frameworks they provide for specific locations where the user can insert code additions to override defaults software extensions . Like engines they offer a rich set of parameters which can be declared by the user configuration . However this flexibility has strict limits if the user introduces customisations i.e. modifications which do not fit the prescribed extensions or configurations the vendor offers no guarantee as to compatibility with future versions. Also because extensions and customisations are specific to a given package the associated concepts are not portable across packages and cannot support an enterprise wide approach.

Service Oriented Architecture SOA is an approach to address the resulting challenge. While an Enterprise s IT resources must serve the changing needs of the business they must also be free to evolve in the best and most efficient way possible with technology trends. The concept of service supports the decoupling of Business dynamics associated with the first trend from Technology dynamics associated with the second trend .

The dynamics of the business and of the information systems that support it are quite different. Business is driven internally by the enterprise mission and its strategy and externally by the nature of the markets and by statutory obligations. Information systems are driven internally by the automation strategy if any and externally by technology trends and available vendors.

SOA is the first architectural approach which gives first class status to the business view of services. While ITIL and other accepted norms of Information Technology refer to services and may provide guidance on their management there was no accurate definition of a service as such. SOA declares a service to be a unit of technology deployment which provides a definite business function. In simple terms like a word in a language a service within SOA has a form its technical implementation and deployment and a meaning the function it provides to the business endeavour.

The analogy with language goes further. If services are like words in a language there must be a way to combine them into meaningful sentences read service invocations must be combinable to form business valuable scenarios . The syntax of a service language is called orchestration and draws on the concepts of process engine and process notation.

The SOA approach has a major implication for IT professionals a service s meaning is defined in the context of business operations. This means that any SOA effort presupposes a precise definition of the structure and behaviour of the business endeavour. IT Architects have long realised that they cannot devise sensible solutions without first having defined the business problem. However in the past this definition was done piecemeal addressed a limited scope and took the form of a collection of requirements often lacking any sort of internal structure. SOA requires that services should be defined in a properly articulated business context and brings to the fore the need for a Business Architecture as an essential part of the architecture of the enterprise.

With SOA the level of abstraction has finally been raised all the way to business value . In principle services defined by their business value can be reused as long as the business meanings remain stable. Introduction of a new line of business might reuse some services and specify a few new ones. Innovations in technology might warrant the design of a new implementation new deployment techniques e.g. cloud deployment may warrant changes in physical detail. All this can be accomplished economically and flexibly provided that the Business architecture exists to provide the base context.

The present invention is positioned at the convergence of the two trends discussed above. It supports defining a Business Architecture in terms of the activity types targeted in the first commercial trend thereby leveraging the experience acquired in domain specification. It supports a fine recursive decomposition of these domains into granular services a necessity of structure as will be shown in the following section on complex systems . Finally it supports the articulation of the business meaning of the services with a variety of implementation and deployment forms leveraging the engineering resources discussed in the second trend which make it possible to anchor the conceptual business model in practical realisation.

The challenge of IT Architecture arises from the fact that Business Information Systems are complex systems which embody several kinds of regularities at once. Any notation designed to document one kind of regularity e.g. process may be incompatible with notations for other kinds. A major contribution of the present invention is the devising of a meta grammar which makes it possible to define grammars suitable for each regularity and yet to connect them as compatible formal devices. The detail of this development is the topic of the next section.

The present invention arises as a response to the challenge of engineering or simply modelling complex systems and addresses four characteristic issues of such systems.

A clear illustration of these issues is offered by the discipline of Enterprise Architecture which was one of the starting points for the research which resulted in the present invention.

The usefulness of IT systems depends crucially on how well IT investments are aligned with business strategies. As suppliers of information systems the IT team of an enterprise are tasked with delivering technology support to make the business more efficient and are measured by the quality of the systems that they provide to the business. To get an overall perspective of how the systems link and flow together they create detailed charts maps and diagrams which together comprise an Enterprise Architecture. The Enterprise Architecture is used to describe govern and manage the automated systems. The discipline of Enterprise Architecture while not yet fully mature has seen major progress over the past two decades. Theories have been elaborated and methods developed to guide and support the work of practitioners. At the cost of some considerable effort it is now possible to prepare and maintain effective models of the automated parts of an enterprise. Yet Enterprise Architecture still remains headless inasmuch as the essential motivation for its existence is not established with adequate clarity and precision. The consumers of enterprise information systems are the business stakeholders who are tasked with managing and executing initiatives that realise business goals and are measured by their achievement of business outcomes. Business systems are simply tools to make them more efficient in the execution of their activities. To fully realise its benefits Enterprise Architecture must include a constituent Business Architecture defined governed and managed with a precision and clarity similar to those now available for the technical constituents. This is not currently the case. While several theories of business organisation are extant there is no systematic approach to the discovery analysis and definition of the architecture of a whole business endeavour.

ArchiMate TOGAF and Enterprise Architect are examples respectively of a modelling language a framework and a tool for Enterprise Architecture in which some consideration is given to Business Architecture. In each the elements associated with the definition of a business are little more than conceptual placeholders lacking the clarity and precision of the more technical terms. The practitioner is left with little beyond a recourse to experience and intuition.

The major challenge to the construction of an adequate Business Architecture arises from the language practices within business. While business people mostly understand each other in everyday practice difficulties arise when attempting to apply formal methods. This requires means of describing a business in a way which can be processed using other tools into IT specifications and to be sufficiently ambitious into executable artefacts software appliances hardware devices etc. This objective of expressiveness and rigour has an obvious prerequisite the notation must be adequate and precise. Since the notation adopted here is natural language we are doomed to failure unless we introduce usage conventions in the form of a Controlled Vocabulary i.e. a set of chosen words associated with an agreement to use the words of the set according to specific semantic rules controlling their denotation. For example the term domain occurs quite frequently in the discussion of business activities. In spite of this common usage there appears to be no formal definition of this term nor even a precise understanding of its import.

At present the practice of business modelling is primarily based on UML and BPMN. Of these UML Unified Modelling Language is a general purpose modelling language originally designed to model software. It is suitable for business modelling only by reason of its generality. In fact practitioners must resort to the stereotype device to specialise the application of UML concepts. But there are no directing principles for this specialisation with the consequence of incompatibility among the work of different individual practitioners.

As to BPMN Business Process Modelling Notation its name itself indicates that it is specialised for a narrow aspect of a business endeavour. Processes modelled using BPMN treat other aspects e.g. the objects of the business and their lifecycles or the groupings of such objects and functions by affinity as peripheral or incidental.

Enterprises are typically made up of very diverse components. This is due to the fact that most have grown by accretion and that the interactions between the parts have been set up on an ad hoc basis. This situation raises a serious challenge to the modeller in order to be applicable to this diversity of fact the modelling artefacts must exhibit three kinds of invariance.

The modelling artefacts must not depend on the content of the components since the subject matter of each is indefinitely variable. For example an enterprise manufacturing widgets will also have a finance department dealing in budgets. While it makes sense to have a model for budgets and another for widgets the means used in modelling must be uniform.

As mentioned above UML provides the stereotype device which is a mechanism for extending or altering the meaning display and syntax of a model element. In other words a stereotype allows the modeller to assign special features to a model element while at the same time assigning it to one of a few fundamental categories. As a result the commonalities are carried by static categories while the stereotypes allow indefinite variation in the syntax of dynamic interaction. By contrast the present invention provides a uniform syntax for interactions thereby making them invariant with respect to content.

Typically the analysis leading to a model will proceed by progressive decomposition. To return to the term domain discussed earlier its applications range from narrow scopes e.g. the domain of stationery purchasing to the full extent of an industry e.g. the utilities domain also some domains can be contained within other domains . Accordingly any definition of the term is likely to be scale invariant and as a consequence have a recursive structure.

Among the existing notations BPMN supports recursion in the specific mechanism of subprocess. On the other hand given that its application is restricted to processes it has nothing to offer for scale invariance in other aspects e.g. objects or capabilities . As to UML it allows recursion and scale invariance by default inasmuch as the syntax of model elements is at the discretion of stereotype builders. The language itself has nothing specific to offer to guarantee scale invariance. In contrast the present invention identifies three types of models the Object models relate to atomic structural elements and the Universe models define maximum extents. In between component models provide the syntactic support for recursive decomposition.

For the same reason the way in which components of a modelling unit e.g. a domain interact with each other how they are coupled must be describable using the same concepts and artefacts regardless of the identity of the components. This kind of invariance applies to issues of governance and management mechanisms composition mechanisms scope and boundary specifications etc.

In BMPN coupling of objects or functions is an incidental consequence of the defined processes. The only explicitly defined interactions are among processes themselves either by virtue of shared objects of by intermediary events. In UML any number of modelling constructs can induce some coupling.

By contrast the present invention offers a single coupling mechanism linking the lifecycles of two objects by rules which declare the states in which their interaction is possible and or required.

System failures have often been traced to a failure of communication between the business agencies expressing their need for functionality and the Information technologists who were charged with supplying that need.

Necessarily the structure and dynamics of automation and those of business systems evolve independently. It is not possible to find isomorphisms between those two worlds. In other words when mapping business function to automation there will appear discrepancies which must be reconciled by means of appropriate artefacts recipes or to be more ambitious algorithms for the translation of expressed business needs to IT requirements. The formulation of such discrepancy bridging recipes requires a suitable language.

While UML notation can be adapted by means of stereotypes there is no provision for expressing complex mappings between models. This requires the introduction of a new notation. Proponents of Model driven Architecture have introduced Mappings with the QVT formalism and Marks to parameterise the mappings. However these ideas are still at the conceptual stage and much R D is required to bring them to a point where their effectiveness can be assessed.

By contrast the present invention offers the bridge mechanism. A bridge is an ontology dedicated to expressing the mapping between two sets of propositions in a semantic notation.

In the late 1980 s David Harel introduced statecharts a very powerful means of describing reactive systems that is systems whose behaviour is sensitive to external events as distinct from transformational systems whose behaviour can be fully characterised by a fixed transfer function from input to output . He characterised statecharts as being an extension of state diagrams in the following formula statecharts state diagrams depth orthogonality broadcast communication

In this formula state diagrams introduces the event driven nature of such systems depth provides for a hierarchical decomposition orthogonality allows the coexistence of several parts which evolve independently of each other while broadcast communication provides for some degree of mutual influence between the parts.

These properties of statecharts go a long way towards addressing the challenges outlined above. Specifically depth provides for recognising that systems are made up of parts organised at several scales orthogonality deals with the diversity and quasi independence of such parts and broadcast communication addresses the fact that parts typically do not know which other parts will be affected by their behaviour and therefore cannot direct their messages .

The intuitive notion of domain is used generally in discussion of enterprise systems. Its degree of definition as observed above is generally vague. For the sake of a precise descriptive theory we must either do without it or specify it adequately. Two considerations bear on a possible specification. First the use of this term ranges from quite narrow cases e.g. the domain of stationery purchasing to the full extent of an industry e.g. the utilities domain therefore there cannot be any limitation of subject matter content invariance .

Second some domains can be contained within other domains this implies a hierarchical structure. Harel s statecharts provide the mechanism for hierarchical decomposition but further refinement is needed. If distinct layers of the hierarchy are to be structured differently it becomes necessary to identify levels and to assign a particular structural description to each of these levels. This fallacy has trapped many attempts at defining domains . For example many process decomposition models claim to distinguish say three levels of process definition . The alternative is to accept that a given domain and its constituent subdomains are amenable to the same structural description. In other words domain structure is self similar or scale invariant and the descriptive framework must be recursive.

The present invention embodies the second approach. Domains are taken to be properly embedded and this hierarchy is modelled by the recursion of Component models between the lower limit of atomic Object models and the upper limit of Universe models. The composition of models is uniformly ruled by a single mechanism SPOP .

Strict self similarity entails infinite detail at small scales this clearly is not compatible with what we know of the components of the real world water molecules grains of sand cells etc. . So a fractal description of a natural object cannot be the whole picture. Regularities stated in a descriptive theory must be associated with a scope that is their applicability is limited to a range of scale or resolution in the phenomena under study.

For instance a model of a cloud may invoke self similarity but this will cease to be applicable below the scale of water droplets. From the point of view of the cloud water droplets are atomic or to put it another way they are black boxes their internal structure is not accessible to the regularity that defines the cloud. This is not to say that such internal structure is not susceptible of description. Therefore a water droplet participates in two kinds of regularity one internal in terms say of water molecules the other external in terms of its relation to the cloud. The constraint of fitting this dual structure is what we call a bridge.

From the above two observations we can construct a precise and stable concept of domain. A domain is any aggregation of subject matter which is amenable to a uniform descriptive rule. This rule may be flat applying only to objects of a single scale or recursive applying self similarly to a range of scales in which case its scope will be contained between two bridges.

The stricture of recursion has implications for the mechanism of communication. Harel s broadcast communication is too general in that it would allow some event in a deeply embedded subdomain to affect any part of the system directly. This is a well known conundrum in information systems or computer science manifested in spaghetti code and highlighted in such publications as Dijkstra s letter Go To Statement Considered Harmful . More formally this kind of undifferentiated messaging has been hemmed in by the principle of information hiding. Communication of events can be structured by such mechanisms as hierarchical exception handling to climb the domain hierarchy peer to peer messaging for management of interfaces among siblings and delegation whereby a construct passes an event down for handling by one of its children .

In the present invention objects are black boxes which only expose their current state any communication or coupling is restricted to that information. The SPOP mechanism is activated by an event and applies to whichever constructs are selected by rules.

Typically the approach to the modelling is threefold. One may focus on the conceptual in which a system is view in terms of intents motivations and capabilities. Or one may consider the logical organisation addressing the sequencing dependencies and collaborations. Finally one may address the issues of implementation whether through manual processes or automation.

The relationship between these folds is called manifestation. Thus logical structure manifests conceptual intent and implementation manifests logical structure. Clearly there would not be a need for three folds if the structures were isomorphic. But the fact is that each of these folds has its own dynamics is organised differently at any one time and evolves at different rates and in different directions. There is therefore a need to spell out the manifestation mappings. It goes without saying that only the non isomorphic parts need to be specified. There are two aspects to those. On the one hand there are many to many mappings between elements in each fold.

On the other and more intricate there are atomic elements in one fold manifesting or manifested by non atomic structures in another. Such cases are called discrepancies and are the source of much of the systems complexity.

In the present invention as discussed above such discrepancies are handled by bridges. There are currently two bridge types. One manages the concept to design discrepancies by declaring semantic interconnections between the business systems definition business CIM and a defined structure and dynamics of automation technical CIM which is intended as the basis of design. The other manages the design to implementation discrepancies by declaring semantic interconnections between the business systems design business PIM and a defined structure and dynamics of machinery platform CIM which is intended as the platform for deployment.

Thus one embodiment of each of the methods described herein is in the form of a computer readable carrier medium carrying a set of instructions e.g. a computer program that are for execution on one or more processors. Thus as will be appreciated by those skilled in the art embodiments of the present invention may be embodied as a method an apparatus such as a special purpose apparatus an apparatus such as a data processing system or a computer readable carrier medium.

The computer readable carrier medium carries computer readable code including a set of instructions that when executed on one or more processors cause a processor or processors to implement a method. Accordingly aspects of the present invention may take the form of a method an entirely hardware embodiment an entirely software embodiment or an embodiment combining software and hardware aspects. Furthermore the present invention may take the form of carrier medium e.g. a computer program product on a computer readable storage medium carrying computer readable program code embodied in the medium.

The software may further be transmitted or received over a network via a network interface device. While the carrier medium is shown in an example embodiment to be a single medium the term carrier medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term carrier medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by one or more of the processors and that cause the one or more processors to perform any one or more of the methodologies of the present invention. A carrier medium may take many forms including but not limited to non volatile media volatile media and transmission media.

It will be understood that the steps of methods discussed are performed in one embodiment by an appropriate processor or processors of a processing i.e. computer system executing instructions computer readable code stored in storage. It will also be understood that the invention is not limited to any particular implementation or programming technique and that the invention may be implemented using any appropriate techniques for implementing the functionality described herein. The invention is not limited to any particular programming language or operating system.

Furthermore some of the embodiments are described herein as a computer implemented method or combination of elements of a method that must necessarily be implemented by a processor of a processor device computer system or by other computational device. Thus a processor with the necessary instructions for carrying out such a method or element of a method forms a means for carrying out the method or element of a method.

Generally the invention comprises a computing device for state transitions of recursive state machines and a computer implemented method for the definition design and deployment of domain recursive state machines for computing devices of that type such devices are intended for the simulation of large systems involving human and automated components particularly the type generally called Enterprise Applications such devices are also applicable to a much wider range of fields such as cognitive modelling or robotics. The commonality between the computing device and the computer implemented method is the Subject Predicate Object Protocol SPOP which is used to capture instructions using the computer implemented method for the definition design and deployment of recursive state machines and also used as the protocol used by the computing device for state transitions of recursive state machines to communicate inbound and outbound events based on the captured instructions. When executing the computer implemented method for the Definition Design and Deployment of domain recursive state machines the Subject Predicate Object Protocol SPOP is captured during the domain definition using the PCIML construct Filter pciml Filter to capture and relate the objects finite state machines recursively to form components and universes behaviour which is then implemented by the PPIML Construct SPOP ppiml SPOP which is then deployed using the PPSML Construct Rules Engine ppsml RulesEngine which accesses the schema data rules model data data instances data and platform Specific Template Instances of objects configured using the PPSML Construct Repository Schema ppsml RepositorySchema and the PPSML Construct Rules Repository ppsml RulesRepository and the PPSML Construct Data Repository ppsml DataRepository and the PPSML Construct Interface ppsml Interface respectively. The Subject Predicate Object Protocol SPOP becomes then the protocol of communication via events received and sent by the computing device for state transition of recursive state machines ESTCA .

In a preferred embodiment of the invention a computing device for state transitions of recursive state machines the computing device comprising 

Preferably if the condition is untrue it is not a valid state transition and the device further comprises sending condition constraint data representing the untrue condition.

Preferably in storing the first object data in the memory store the device further comprises calculating a valid action for the valid state transition.

Preferably in calculating the valid action the device further comprises sending valid event data representing the valid action.

Preferably the valid event data further comprises the first object data second object data and the data representing a relationship between the second object data and the first object data.

Preferably in selecting a first object schema data and a first object rules model data in accordance with the first object data and selecting a second object schema data and a second object rules model data in accordance with the second object data comprises defining designing and deploying domain recursive state machines comprising the steps of 

In another preferred embodiment of the invention a computer implemented method for definition design and deployment of domain recursive state machines comprising the steps of 

Preferably the step of capturing in a computation independent manner the structure of the first object definition foundation ontology data and the second object definition foundation ontology data comprises 

Preferably the step of capturing in a computation independent manner the behaviour of the first object definition foundation ontology data and the second object definition foundation ontology data comprises 

Preferably the step of capturing in a computation independent manner a component definition foundation ontology data creating a relationship between the second object definition foundation ontology data and the first object definition foundation ontology data comprises 

Advantageously the method includes a frame based definition view for receiving the definition foundation ontology data.

Advantageously in generating the logically equivalent ontology includes generating models that meets W3C Web Ontology Language OWL specification.

Advantageously in generating the physical database schema includes generating schema that meets the formal language supported by a database management system DBMS .

Advantageously in generating the inference notation data includes generating data that meets W3C SPARQL Inference Notation SPIN specification.

Advantageously it further comprising the step of providing a frame based view for data entry type applications to capture first object second object and component data in accordance with the first object schema data and first object rules model data second object schema data and second object rules model data and component schema data and component rules model data.

Advantageously the computer implemented method for definition design and deployment of domain recursive state machines further comprising validating the first object definition foundation ontology data in accordance with definition foundation ontology.

Advantageously the computer implemented method for definition design and deployment of domain recursive state machines the method includes the additional step of simulating the first object finite state machine data in accordance with the first object definition foundation ontology data.

Advantageously in simulating the first object finite state machine data in accordance with the first object definition foundation ontology data involves the use of a series of frame based views.

Advantageously the computer implemented method for definition design and deployment of domain recursive state machines the method includes the additional step of generating a definition type report in accordance with the first object definition foundation ontology data or the second object definition foundation ontology data or the component definition foundation ontology data.

Advantageously the computer implemented method for definition design and deployment of domain recursive state machines the method includes the ability to maintain a library of business object models the library comprising 

Advantageously the computer implemented method for definition design and deployment of domain recursive state machines the method includes the ability to maintain a library of domain specific language the library comprising 

Preferably in capturing in a platform independent manner the design foundation ontology data comprises 

Preferably in capturing in a platform independent manner the first object design foundation ontology data and the second object design foundation ontology data and the component design foundation ontology data comprises 

Advantageously the computer implemented method for design of domain recursive state machines the method includes providing a frame based view for receiving the design foundation ontology data.

Advantageously the computer implemented method for design of domain recursive state machines the method includes one or more of the following additional steps 

Advantageously the computer implemented method for design of domain recursive state machines the method comprises the additional step of calculating a Data and Application Architecture type report.

Preferably in capturing in a platform specific manner the deployment foundation ontology data is comprised of the following steps 

Preferably in capturing in a platform specific manner the first object deployment foundation ontology data and the second object deployment foundation ontology data and the component deployment foundation ontology data is comprised of the following steps 

Advantageously the computer implemented method for deployment of domain recursive state machines the method includes providing a frame based view for receiving the deployment foundation ontology data.

Advantageously the computer implemented method for design of domain recursive state machines the method comprises one or more of the following additional steps 

Advantageously the computer implemented method for deployment of domain recursive state machines the method comprises the additional step of calculating a Technology Architecture type report.

Advantageously the computer implemented method for design of domain recursive state machines the method comprises the additional step of calculating the equivalent to UDDI Universal Description Discovery and Integration information type configuration file.

Advantageously with a plurality of computing devices the devices are further adapted to perform process orchestration of the different events processed by the plurality of computing devices.

Advantageously with a plurality of computing devices at least one of the devices is further adapted to perform framework type events used to manage 

It should be noted in the following description that like or the same reference numerals in different embodiments denote the same or similar features.

The device comprises semiconductor memory comprising volatile memory such as random access memory RAM or read only memory ROM . The memory may comprise either RAM or ROM or a combination of RAM and ROM.

The device comprises a computer program code storage medium reader for reading the computer program code instructions from computer program code storage media . The storage media may be optical media such as CD ROM disks magnetic media such as floppy disks and tape cassettes or flash media such as USB memory sticks.

The device further comprises I O interface for communicating with one or more peripheral devices. The I O interface may offer both serial and parallel interface connectivity. For example the I O interface may comprise a Small Computer System Interface SCSI Universal Serial Bus USB or similar I O interface for interfacing with the storage medium reader . The I O interface may also communicate with one or more human input devices HID such as keyboards pointing devices joysticks and the like. The I O interface may also comprise a computer to computer interface such as a Recommended Standard 232 RS 232 interface for interfacing the device with one or more personal computer PC devices . The I O interface may also comprise an audio interface for communicate audio signals to one or more audio devices such as a speaker or a buzzer.

The device also comprises a network interface for communicating with one or more computer networks . The network may be a wired network such as a wired Ethernet devices . The I O interface may also comprise an audio interface for communicate audio signals to one or more audio devices such as a speaker or a buzzer.

The device comprises an arithmetic logic unit or processor for performing the computer program code instructions. The processor may be a reduced instruction set computer RISC or complex instruction set computer CISC processor or the like. The device further comprises a storage device such as a magnetic disk hard drive or a solid state disk drive.

Computer program code instructions may be loaded into the storage device from the storage media using the storage medium reader or from the network using network interface . During the bootstrap phase an operating system and one or more software applications are loaded from the storage device into the memory . During the fetch decode execute cycle the processor fetches computer program code instructions from memory decodes the instructions into machine code executes the instructions and stores one or more intermediate results in memory .

In this manner the instructions stored in the memory when retrieved and executed by the processor may configure the computing device as a special purpose machine that may perform the functions described herein.

The device also comprises a video interface for conveying video signals to a display device such as a liquid crystal display LCD cathode ray tube CRT or similar display device.

The device also comprises a communication bus subsystem for interconnecting the various devices described above. The bus subsystem may offer parallel connectivity such as Industry Standard Architecture ISA conventional Peripheral Component Interconnect PCI and the like or serial connectivity such as PCI Express PCIe Serial Advanced Technology Attachment Serial ATA and the like.

In one particular example the web server is provided with a web server application for receiving requests such as Hypertext Transfer Protocol HTTP and File Transfer Protocol FTP requests and serving hypertext web pages and files and SOAP and REST messages in response. The web server application may be for example the Apache or the Microsoft IIS HTTP server or any other portal technology.

The web server is also provided with a hypertext preprocessor for processing one or more web page templates capable to access data from one or more databases and triple stores graphs which store Domain Data Instance Graphs and Domain Platform Specific Template instances . This data is used to generate hypertext web pages. The hypertext preprocessor may for example be the PHP Hypertext Preprocessor PHP or Microsoft Asp hypertext preprocessor or Top Braid Live SPARQL Web Pages SWP . The web server is also provided with web page templates such as one or more SWP PHP or ASP files.

The web server host applications that can provide templates of pages menus buttons and any other portal type component store as Web page templates .

Upon receiving a request from the web server application the hypertext preprocessor is operable to retrieve a web page template and its components from the web page templates execute any dynamic content therein including loading information from the one or more databases or triple stores graphs storing Domain Data Instance Graphs and Domain Platform Specific Template instances that are domain specific models to compose a hypertext web page. The composed hypertext web page may comprise client side code such as Javascript for Document Object Model DOM manipulating asynchronous HTTP requests and the like.

Upon receiving a request from the web server application the Application Server is operable to execute a calculation using the appropriated Domain Data Instance Graphs loading information from the one or more databases or triple stores graphs storing Domain Data Instance Graphs and Domain Platform Specific Template instances holding data for a specific domain which are part of the domain specific models . The Application Server then responds with a calculation that can be used by the hypertext processor or by any other device ATM Liquid display etc .

The Domain Platform Specific Templates instances provide domain specific meta data that is used to compose a domain specific hypertext web pages. This pages also contain domain specific information stored in the Domain Data Instances Graphs .

Upon loading information from the one or more databases or triple stores graphs storing Domain Data Instance Graphs holding data for a specific domain using domain specific models the Application Server is going to send an inbound event SPOP to the ESTCA Web Server . The event is received by the web server that will trigger the computing device for state transitions of recursive state machines . The application server is going then to listen for outbound event SPOP sent by the web server by the steps trigger outbound event sending condition constraint data representing the untrue condition generated by inference engine or will send valid event data representing the valid action which comprises the first object data second object data and the data representing a relationship between the second object data and the first object data and routing it to the appropriated agent .

In this example the client computing device is provided with a browser application such as the Mozilla Firefox or Microsoft Internet Explorer or Google Chrome or Opera browser applications. The browser application requests hypertext web pages from the web server and renders the hypertext web pages on a display device .

Other examples using any other client computing devices connected via client server architecture can also be used.

As is evident from the technical description below the embodiments described herein offer several distinct advantages including the use of the network of computing devices such as displaying output pages with enabled events using the web server that is not bound to any particular domain. Furthermore this invention is able to implement different domains only by defining designing and deploying domain foundation ontology data which are going to be explained later.

Referring now to there is shown three exemplary graphical user interface GUI and . The GUI and are displayed by the display device of the client computing device coupled to the web server across the internet that is going to communicate via events with the ESTCA web server that implements the computing device appliance for state transitions of recursive state machines. Herein the embodiments will be described with reference to the human resources domain but it should be appreciated that application may be found in other related domains or industries too.

In GUI a user has registered himself and also provided information required to submit a job application for a job position for the purposes of getting a job in company ABC. In GUI a user that is an internal Human Resources employee of company ABC has open a job application for review and processing. There are various ways by which the web server receives job application data from the user representing the candidate. For example the user may browse using browser application to a particular resource using a URL such that the web server is able to present the correct page with the correct content based on the user role and the candidate and its job application states. In alternative embodiments the user may apply for a job via a Mobile application.

As shown in the GUI self service portal www.ABCjobapplication.com displays a screen that is rendered based on the information contained in the response event coming from an outbound event SPOP from the computing device for state transitions of recursive state machines that was triggered when the user that has the self service candidate role Joe Blog has selected the job application Nr. 001234 that triggered the event open job application. Upon the event is triggered the Application Server is going to send an inbound event SPOP to the Web Server passing the event open job application from user Joe Blog with the objects Joe Blog B Object related via the predicate hasJobApplication to job application Nr. 001234 A Object .

A different scenario is shown in where the GUI self service portal www.ABCjobapplication.com displays a screen that is rendered based on the information contained in the response event coming from an outbound event SPOP from the computing device for state transitions of recursive state machines that was triggered when the user that has the self service candidate role Joe Blog has submitted the job application Nr. 001234 by pressing the submit button that triggered the event submit job application. Upon the event is triggered the Application Server is going to send an inbound event SPOP to the Web Server passing the event submit job application from user Joe Blog with the objects Joe Blog B Object related via the predicate hasJobApplication to job application Nr. 001234 A Object with the information required to change the status of the job application Nr. 001234 to Submitted .

A different scenario is shown in the GUI portal www.HumanResourcesManagement.com displays a screen that is rendered based on the information contained in the response event coming from an outbound event SPOP from the computing device for state transitions of recursive state machines that was triggered when the user and employee that has the recruiter manager role Mary Ann has open the job application Nr. 001234 that triggered the event open job application. Upon the event is triggered the Application Server is going to send an inbound event SPOP to the Web Server passing the event open job application from user Mary Ann with the object Joe Blog B Object related via the predicate hasJobApplication to job application Nr. 001234 A Object with the information required to open the job application Nr. 001234 that in this stage is submitted .

With the example defined in Its is important to define that the A Object is the same as the First Object in the Claims Section. The B Object is the same as the Second Object in the Claims Section.

It is also important to highlight that in the example both portals described on the example such as www.ABCjobapplication.com and www.HumanResourcesManagement.com are described as implemented in the web server however they could be implemented in different web servers and also use different ESTCA Web Server described on the example as a single one.

The ESTCA web server is provided with a web server application for receiving requests such as Hypertext Transfer Protocol HTTP requests and serving REST and SOAP messages in response to the domain application servers in this example. The web server application may be for example the Apache or the Microsoft IIS HTTP server.

The ESTCA web server is also provided with a SPARQL Motion Script for processing one or more state transitions by having access to data from the Application PPSML Deployment Models the A schema graphs and rules and the B schema graphs and rules and the A and B Data Instance Graphs and an Inference Engine to calculate valid transition responses in the form of outbound event SPOP messages. The response messages may for example be SOAP or REST messages.

Part of the computing device for state transitions of recursive state machines is displayed in . The computing device is implemented by one or more computing devices and in particular one or more computing devices connected across the Internet as substantially shown in .

In this particular example the steps of the computing device described below are implemented by the ESTCA web server for state transitions of recursive state machines. Herein the web server comprises a processor for processing digital data a memory device for storing digital data including computer program code and being coupled to the processor via a bus a network interface for sending and receiving digital data and being coupled to the processor via the bus and many data sources used for storing digital data that are domain specific models including A Schema Graphs A Rules Models B Schema Graphs B Rules Models A and B Data Instance Graphs and Application PPSML Deployment Models being coupled to the processor via the bus .

The ESTCA engine could also be implemented using different architectures that could simulate the inference power by been capable to identify states via rules like the subclass restrictions.

The computing device starts at step receive via the data interface event data representing an event in relation to a first object wherein the processor controlled by the computer program code to receive via the network interface an event related to a first object A .

At step receive via the data interface event data representing an event in relation to a first object of computing device the web server is adapted to receive from the Application Server the inbound event SPOP using the SPO Protocol. The computing device also executes the steps receive via the data interface appropriate event management meta data receive via the data interface first object data representing the first object receive via the data interface second object data representing a second object and receive via the data interface data representing a relationship between the second object and the first object .

Both Inbound and outbound events communicate using the same protocol which is the Subject Predicate Object Protocol SPOP . This protocol communicates the following information 

The predicate Property data representing a relationship between the second object and the first object Predicate Property that has the second object Subject as domain and the first object Object as range.

The First Object represents the Object A and the Second Object represents the Subject B in the Subject Predicate Object Relationship.

Upon success in Validate User Permissions the SPARQL Motion Script is adapted to selecting a first object schema data and a first object rules model data in accordance with the first object data . It is also adapted to selecting a second object schema data and a second object rules model data in accordance with the second object data . It is also adapted store received data and selected schema data and rules model data in memory . It is also adapted to operate inference engine on memory in order to calculate a first state in relation to the first object and in order to calculate a second state in relation to the second object and calculate a valid state transition in accordance with the relationship between the second state and the first state .

Advantageously when the SPARQL Motion Script making use of the Inference Engine to calculate a first state in relation to the first object and calculate a second state in relation to the second object and calculate a valid state transition in accordance with the relationship between the second state and the first state .

The TopSPIN Inference Engine provided by Top Quadrant is the most efficient inference engine by executing SPIN natively.

When calculating a valid state transition conditions will be applied and in the case where no conditions return untrue the result is a valid state transition the SPARQL Motion Script will storing the first object data in the memory store and storing optionally the second object data in the memory store inside the first object A and second object B Data Instance Graphs . The update is based on the data provided via the steps receive via the data interface first object data representing the first object and receive via the data interface second object data representing a second object .

When in calculating a valid transition if a condition is untrue returning constraints the SPARQL Motion Script will trigger outbound event sending condition constraint data representing the untrue condition generated by inference engine to the Web Server .

Upon the Web Server receiving an outbound event from the SPARQL Motion Script it will communicate the event to the Application Server via the outbound event SPOP using the SPO Protocol.

Upon storing the session memory the SPARQL Motion Script is going to calculate a valid action for the valid state transition based on the content of the Application PPSML Deployment Models . The SPARQL Motion Script is then going to send valid event data representing the valid action which comprises the first object data second object data and the data representing a relationship between the second object data and the first object data and routing it to the appropriated agent that in this example is implemented on the Web Server .

Upon the Web Server receiving an outbound event from the SPARQL Motion Script it will communicate the event to the Application Server via the outbound event SPOP using the SPO Protocol.

ESTCA is an event based computing device that is triggered by inbound events inbound event Subject Predicate Object Protocol SPOP and respond using outbound events outbound event Subject Predicate Object Protocol SPOP based on the state of the Subject Predicate Object SPO or Object B Relationship Object A or Second Object Relationship First Object of the domain to the appropriated agent. The Agents do not have any intelligence the intelligence is in ESTCA. In this example ESTCA it is implemented using the ESTCA Web server that communicates with Agents implemented using the Web server .

In order for ESTCA computing device be capable to perform state transitions of recursive state machines responding to Agent events which interact with a particular domain it requires instructions Structure Behaviour and Rules which are stored in separated specific domain models . This models are the models Domain Data Instance Graphs the A First Object and B Second Object Schema and Rules Models the A First Object and B Second Object Data Instance Graphs for a specific domain. Since this Domain interacts using events with agents via some technology the models Domain Platform Specific Template Instances and the Application PPSML Deployment Model will describe the domain implementation and deployment configuration using a particular technology.

The A First Object and B Second Object Schema models define the schema that defines the two Objects used by each state transition. It defines the object classes properties and states as subclass cardinality restrictions used to store the objects and also infer the object states.

The A First Object and B Second Object Rules models defines the constraint rules related to the respective object states and also the construct rules related to the respective object classes

The A First Object and B Second Object Data Instance Graphs and the Domain Data Instance Graphs models contain the data instances or objects of the A First Object and B Second Object classes and the entire domain respectively.

The Domain Platform Specific Template Instances contain the meta data that relates a business domain that in this example is the Recruitment Management to a Technical Specification design pattern used to describe applications like in the example of the www.ABCjobapplication.com and www.ABCHumanResourcesManagement.com .

The Application PPSML Deployment Model connects the Physical Platform Components and the technical designs that support a Particular Domain.

In this example the domain is accessed by applications hosted in that is composed of many models for all objects constituents of the domain the Application PPSML Deployment Model is used to map models and characteristics of the object A First Object and subject B Second Object used in each state transition such as 

The first 4 steps and are responsible for the definition of Domain Recursive State Machines. The first step then is about defining the business Object PCIML Definition Models.

The steps capturing in a computation independent manner the structure of a first object definition foundation ontology data and a second object definition foundation ontology data capturing in a computation independent manner the behaviour of the first object definition foundation ontology data and the second object definition foundation ontology data and capturing in a computation independent manner the rules of the first object definition foundation ontology data and the second object definition foundation ontology data are about defining the Business Object PCIML Definition Models Business Object Definition Foundation Ontology Data for each object that are constituent of a particular business domain.

Each Business Object PCIML Definition model contain one of the domain constituent business objects definition foundation ontology data captured using the Parametric Computation Independent Model Language PCIML . In the example the Business Object PCIML Definition models are built for Job Application and Person Management Object PCIML Models that have their definition captured using the Parametric Computation Independent Model Language PCIML .

PCIML is a modelling language that is developed as an alternative to General purpose modelling GPM languages such as UML Unified Model Language that can be also used to build DSL Domain Specific Language . PCIML follows an Object Oriented Design implementing a Logical Domain Finite State machine where an object is said to have an internal state and is capable of receiving messages responding to them sending messages to other objects and changing the internal state during message handling. In more practical terminology to call an object s method is considered the same as to send a message to the object.

The main advantage PCIML provides over any other General purpose modelling GPM Language is the method of building the structure relationship via the definition of its behaviour keeping the structure aligned with the behaviour without constraining it.

The delivery of a filter that is the reification of a proposition using two object states enables the definition of the entire domain logic connecting object state machines recursively in a form of Subject Predicate and Object prepositions which define the domain state transitions logic.

The Filter is also the PCIML mechanism to connect Classes and Domains via a Predicate in a way in which components of a modelling unit e.g. a domain interact with each other how they are coupled are describable using the same concepts and artefacts regardless of the identity of the components. This kind of invariance applies to issues of governance and management mechanisms composition mechanisms scope and boundary specifications etc.

The PCIML meta model is an example of a layer 2 MOF Meta Object Facility model the model that describes PCIML ontology itself. These M2 models describe elements of the M1 layer and thus M1 models. These would be for example the object and component models written using the PCIML ontology to capture the definition foundation ontology data. The last layer is the M0 layer or data layer. It is used to describe real world objects and in this case is composed of the particular Schema Graph and models generated from the M1 layer and the data instances and used to hold domain instances.

In Executable UML terms a system is composed of multiple subject matters known as domains. Executable UML is used to model a domain at the level of abstraction of its subject matter independent of implementation concerns. The resulting domain model is represented by the following elements 1 The domain chart provides a view of the domain being modelled and the dependencies it has on other domains. 2 The class diagram defines the classes and class associations for the domain. 3 The statechart diagram defines the states events and state transitions for a class or class instance. 4 The action language defines the actions or operations that perform processing on model elements.

The shows the capturing in a computation independent manner the structure of a first object definition foundation ontology data and a second object definition foundation ontology data capturing in a computation independent manner the behaviour of the first object definition foundation ontology data and the second object definition foundation ontology data and capturing in a computation independent manner the rules of the first object definition foundation ontology data and the second object definition foundation ontology data which form the steps that are subdivided in sub steps used to capture the Object PCIML Definition foundation ontology data of interest. The sub steps are used define the Object Composition Structure Behaviour and Control Rules .

By performing the sub steps on The PCIML Definition ontology for any object and specific to the example the Person and Job Application are going to enable the inference of the object chart 1 class diagram 2 statechart 3 and the action language 4 . PCIML also have many other classes and properties that are responsible for configuration simulation constraints validation etc upon execution of an inference engine on the model ontology described.

The Object PCIML Model is used to describe Objects that can be person company location party invoice sales order product job application schedule accounts service purchase order manufacture order page form application host menu buttons actions transactions data repositories etc.

In order to illustrate the method some examples provided are from the Job Application Business Object PCIML Model and others the Person Business Object PCIML Model . In the Object PCIML Description Domain is equivalent to Object.

The definition of PCIML starts by defining the object structure using the step capturing in a computation independent manner the structure of a first object definition foundation ontology data and a second object definition foundation ontology data where the first two sub steps are about receiving structure data the structure data including at least one of class data representing a class for the first and second object and receiving property data representing at least one property for the first and second object using the PCIML construct Resource that describes the Object. In other words it defines the classes pciml Thing and attributes pciml Property that define the scope of the Object model.

The PCIML construct Thing pciml Thing describes the classes the model is formed of following a Sub Class hierarchy defined by the property pciml subclassOf . This hierarchy creates the object model taxonomy. Refer to for the person resources taxonomy including the states defined later.

Everything we call a Thing can be a pciml Thing . Some examples are person companies organisational units sites products services materials assets accounts job application orders invoices contracts warranties pages forms fields menus host application data sources.

For the Person PCIML Model pciml Thing example refer to . The displays the Person thing definition the person model also contain Candidate and Worker things that are subclasses of Person extracted using a report provided by the invention.

After defining the construct Thing the PCIML construct Property pciml Property that describes the properties of the classes defined as pciml Thing which are important to describe the Domain via the property pciml isPropertyOf .

Everything we call a Property can be a pciml Property. Some examples are first name last name age data of birth has manager has address has product ID has price weight value of assets field name page name host name property.

For the Person PCIML Model pciml Property examples refer to which displays the Person properties definition extracted using a report provided by the embodiment.

The next step is about receiving state data representing at least one state of the first and second object using the PCIML construct State pciml State which defines the states of a class defined as a pciml Thing within the scope of the Object. These States are the possible results of object or component services.

The States are represented by subclasses of a class based on the presence of as value for some property in a form of parametric restrictions. These States are used to define the Object s Finite State Machine.

For the Job Application PCIML Model pciml State definition examples refer to where in the example the Approved Job Application State extracted using a report provided by the embodiment. Based on the definition if we use an example where the Job Application Nr for the Candidate John Smith has approved Date of Jul. 7 2012 we can infer that the State Approved Job Application is true for the Job Application Nr so the Job Application Nr is of type Approved Job Application .

The property pciml deploy defines the pciml Thing which the state of affairs pciml State is about. E.g The state employed is a sub class of the pciml Thing worker with some descriptive restriction as characteristics.

The property pciml achievedBy is inferred by PCIML and is an inverse of the pciml Operation property pciml achieves which is going to be described later. It defines the pciml Operation that is responsible for achieving such pciml State .

The property pciml hasPrerequisiteObject and pciml hasPrerequisiteSubject are properties inferred by PCIML that describes the pciml State an object has to have acting as subject or object before having this pciml State. This property enables the simulation of the Object Finite State Machine behaviour.

The states restrictions should only use properties contained in the object model when defining the property pciml isDefinedBy which describes the parametric descriptive restriction definition used to create owl restrictions. In this implementation the state restrictions are based on subclass cardinality restrictions Min Cardinality 1 or Cardinality 0 . Other methods of definition of the states of an object using any kind of form that defines a criteria that can be calculated using other platforms can also be used. For the State definition data structure refer to

The next step is about receiving data relating to agents that can manipulate the first and second object using the PCIML construct Agent pciml Agent . The Agent defines who access creates and evolves the instance of classes through its states within the scope of the Object.

These Agents are authorized to perform pciml Events grouped by pciml Authorizations in order to change and evolve the instances through its states pciml State when executing pciml Operation .

For the Person PCIML Model pciml Agent definition examples refer to where there is a table with the Agents definition extracted using a report provided by the embodiment.

The property pciml isAuthorisedTo is inferred by PCIML and is an inverse of the Authorization Property pciml grantedTo that is going to be described later. It defines the pciml Authorization that granted access to this agent.

After defining the Object structure constructs the next step is defining the Behaviour of the Object using the step capturing in a computation independent manner the behaviour of the first object definition foundation ontology data and the second object definition foundation ontology data .

The next step is about receiving behaviour data for the first and second object the behaviour data including the first and second object finite state machine data comprising data relating to at least one operation that changes the state of the first and second object using the PCIML construct Operation pciml Operation which defines functions that are executed in order to change the state of an instance within the scope of the Object.

This is done by defining the property pciml achieves that relates the pciml State that is achieved when the operation is executed.

Operations are subdivided into Transactions that are triggered internally in the domain and Actions which involve an external event to the Domain. Inbound and Outbound events embody communication with the external world.

The property pciml hasParentOperation is used to define the Operation hierarchy. The Operation taxonomy can be inferred by this relationship. An example of the Job Application Operation taxonomy displayed on extracted using a report provided by the embodiment.

The property pciml hasPrerequisiteOperation is a property inferred by PCIML and describes the pciml Operation that are prerequisite of this particular operation. In another words it is the operation that achieves a state that makes a Filter pattern true enabling this Operation. This property enables the simulation of the Domain Finite State Machine behaviour.

The Property pciml isPrerequisiteOperation is a property inferred by PCIML and is a inverse property of pciml hasPrerequisiteOperation in another words it is the operation that can happen only after the execution of this operation. This property enables the simulation of the Domain Finite State Machine behaviour. The Property pciml enabledBy is a property inferred by PCIML and is a inverse property of pciml enable defined with the Filter that is going to be described later.

The Property pciml considerEvents is a property inferred by PCIML and is a inverse property of pciml consideredBy defined with the Event that is going to be described later.

For the Job Application PCIML Model pciml Operation definition example refer to which are extracted using a report provided by the embodiment where the Job Application Management Operation is an example of the Main type of operation that does not achieve any State and for consequence is not prerequisite of any other operation. The Job Application Instantiation Operation is an example of Action and achieves New Job Application State. On the same the Job Application Operation Taxonomy tree is displayed.

After defining the Operations the next step is receiving event considered by the operation to communicate with agents defining valid events that are going to be received and sent by ESTCA which is capable of invoking and be invoked by operations to evolve objects between states or to manipulate objects to perform domain specific functionality.

The PCIML construct Event pciml Event defines events that are required by the scope of the Domain in order to communicate with the external world in association with a particular pciml Operation. It also defines the valid events which ESTCA computing device can receive and send based on the Domain State.

The events are related to pciml Operation via the property pciml consideredBy which defines the operation that would consider both outbound and inbound Events.

The Outbound Events outbound event SPOP are going to be triggered by ESTCA when the Operation is enabled getting to rest Apart from Synchronous Request and the Inbound Events inbound event SPOP received by ESTCA would trigger the execution of the Operation from the external World when the Operation is enabled.

The property pciml eventDirection describes the direction of communication of the Event in relation to the Domain. The pciml Outbound events communicates from the Domain to the external World via ESTCA outbound event SPOP e.g a message or a widget can be displayed in Page . The pciml Inbound events communicates from the external World to the Domain via ESTCA inbound event SPOP e.g. the event triggers an update or opening of an object. 

The property pciml triggerinboundEvent is used by the events of type Menu Create New Menu Open Button Hyperlink and Menu. It enables outbound events to be linked to an inbound action. This five events are example of the content of the interface between the domain and the external world via a Dashboard.

The Property pciml eventSequence is mainly used for events considered by transaction type of operations and it defines the sequence the Events should follow in a particular transaction.

The pciml affectThing is a property inferred by PCIML that defines the pciml Thing that is affected by the event.

For the Job Application PCIML Model pciml Event example refer to extracted using a report provided by the embodiment where a table with Job Application Events is displayed.

After defining the Events that can be communicated via ESTCA the next step is receiving filter qualifying the applicability of the at least one operation on the first and second object s finite state machine .

The filters that enable the Operations can be formed of a simple State or formed by the two States a Subject and an Object related via a predicate that is used by ESTCA during the step calculate a valid state transition in accordance with the relationship between the second state and the first state .

The PCIML construct Filter pciml Filter defines then filter patterns using a State defined as a Subject related via a Predicate to another State defined as Object.

By the word enable one mean it is available but is not guaranteed it will be executed. This mean branches can exist on the path of the Finite State Machine.

Within the scope of a Component the Filter pciml Filter is focused in defining the proposition using the Subject Predicate Object pattern linking different states. This propositions defines one subject pciml State related via a predicate pciml Property to object pciml State .

Inside Object Models most of the times the full Subject Predicate Object pattern is not filled since in most cases there is only one object inside an Object Model. So the Filter defines that in case any instance which has the state defined as Object is true an Operation is going to be enabled.

Inside Component Models when the properties has subject has Predicate and has Object are filled the Filter defines that in case any instance which has the state defined as Object is true and that is related by a predicate to any other instance which has the state defined as Subject is also true an Operation will be enabled. This will also create a relationship between the pciml Thing deployed as Subject pciml State via the predicate pciml Property to the pciml Thing deployed by the Object pciml State.

An important Behaviour of the Filter is that if the Subject Predicate Object Pattern is true a pciml Operation is enabled to be executed if appropriate.

This evolution is represented in a Finite State Machine that is triggered when filters are matched enabling actions or transactions which trigger events communicated to the external world responsible for moving object instances to the next State achieved by the next Operation. This is also called Filter Operation State Transition.

The combination of these state transitions represents the Component or Object Logic. This defines the core behaviour in form of state transitions used by the ESTCA Web Server as instruction in performing state transitions.

For the Person PCIML Model pciml Filter examples refer to extracted using a report provided by the embodiment where the Filter Instantiated Candidate Selected that has the Object pattern defined as 

Another example refer to extracted using a report provided by the embodiment where another Filter the Created Candidate has Job Application Selected has Subject and Predicate pattern defined as 

Refer also to extracted using a report provided by the embodiment for the Operation Sequence Diagrams representing the Candidate and Job Application and Recruitment Management Finite State Machines.

After defining the Filter which is the last behaviour construct the next step in defining the domain foundation ontology is defining the Rules of the domain using the step capturing in a computation independent manner the rules of the first object definition foundation ontology data and the second object definition foundation ontology data .

The next step is receiving object specific derivation rules to be applied for a particular authorization using the PCIML construct Derivation pciml Derivation which defines the parameters which define how the information should be set when a particular Agent is receiving or sending an Event.

PCIML supports any Derivation types required to describe a Domain. Some example of derivation types are 1 Object property parameters that are configured by the user admin that manages the Domain Configuration. 2 Parameters that define the values that are included in the value set Properties. 3 Formulas used to define Property values that are calculated based in a formula or by a function. 4 Domains business unit and sales regions data sets within domains. 5 External objects that are required by the business object behaviour or by specific functions.

For the Person and Job Application PCIML Model pciml Derivation example refer to extracted using a report provided by the embodiment where there are formulas examples and extracted using a report provided by the embodiment where there are Value set examples.

After the Derivation construct is defined the next step is receiving object state specific condition rules which validate the first and second object s state transitions used by ESTCA on the step calculate a valid state transition in accordance with the relationship between the second state and the first state . The PCIML construct Condition pciml Condition defines the condition rules to validate the instance against the State to be achieved by an operation within the scope of the Domain. The condition will normally enforce a criterion over the Subject or Object properties returning true for a valid state transition and untrue for an invalid state transition.

Refer to for the pciml Condition and pciml ConditionState structure displaying all its domain properties with its ranges.

For the Person and Job Application PCIML Model pciml Condition example refer to extracted using a report provided by the embodiment where the Condition Validate First Name defines that the property first Name is required for achieving the Created Candidate State . If condition is untrue it will return an error type constraint with the Message First Name is a required property of Candidate .

After defining the Condition construct the next step is receiving rules data for the first and second object the rules data including at least one object specific rule constrained authorization connecting agents to events via the PCIML construct Authorization pciml Authorization which describes the Authorization to Operations Data Sets etc which are granted to Agents within the scope of a Domain.

Each pciml Authorization groups pciml Event using the pciml authorises property. This group of events are then related to Agents that are granted permission to the particular pciml Authorization via the property pciml grantedTo property

For the Person and Job Application PCIML Model pciml Authorization example refer to extracted using a report provided by the embodiment where the Create Candidate Authorization authorizes the events Button Save Candidate Instantiate New Candidate Menu Create New Candidate and Save Candidate and is granted to the agents Recruiter and Self Service Candidate .

Referring to we can see an example of the graphical notation view of the Second Object Thing B and the First Object Thing A definition using PCIML. The view displays the Second and First Objects which are interfaced to the external World via the ACCESS Layer .

Inside the ACCESS Layer there are then two smaller sets which represent the pciml Thing Second Object Thing B and pciml Thing First Object Thing A which defines two classes. Inside each Things there are smaller sets which represent the pciml State that deploy each particular Thing. The properties are not displayed in the diagram but they are defined for each thing as domain properties and are used in the criterion that restricts the States sets.

At the boundary of the domain represented by the access layer are the agents that will have access to the Domain.

There are also lines with arrows that represent the pciml Operation achieving one state each. As demonstrated on the diagram each pciml Operation achieves only one pciml State .

Interfacing the Operations to the ACCESS Layer to be communicated via ESTCA represented as black broken arrows are the pciml Event .

The pciml Filter is represented by the round rectangles with a dot style pattern which defines the object state patterns around the object states which enables an operation that will achieve another State creating two separated Object s Finite State Machines FST . In the example we have one FST for the Second Object Thing B and another for the First Object Thing A.

The Derivations are represented by ellipses with a brick style that are located on top of the Events that interface the External World to the Domain. The Conditions which are represented by rectangles are used like gates between the Operations and the States to be achieved. The idea is to gate an operation based on its state conditions been true.

And the last of the PCIML constructs which is responsible for Authorizing Agents to have access to Events available at the ACCESS Layer that is represented as an external grey belt or wall that connects Agents to Events via different Authorizations .

At the end of the PCIML definition the Objects Job Application and Person have their structure the finite state machine and the rules that control the objects defined the same way as the Object A and B have on the example. PCIML is then responsible for formulating the findings in a formal language defining the objects logic that can be used by ESTCA as instructions to process state transitions.

PCIML is deployed in one ontology file that is pciml.owl Base URl and also one spin file that is pciml.spin.ttl Base URl .

Both the Person and Job Application Object PCIML Models import the pciml.owl model. After defining the Business Object PCIML models the next step is defining the Business Component PCIML Models.

By performing the sub steps described on the Recruitment Management Component PCIML definition ontology is going to enable the inference of the Recruitment Management domain chart 1 class diagram 2 statechart 3 and the action language 4 . PCIML also have many other classes and properties that are responsible for configuration simulation constraints validation etc upon execution of an inference engine on the model ontology described.

In order to illustrate the steps some examples are defined using the Recruitment Management Business Component PCIML Model that is going to include the Person and Job Application Object PCIML Models.

This embodiment defines steps that will enable the capture of the definition of a component composed of objects to be integrated with ESTCA.

In order to perform the sub steps described on starting from receiving a reference of the definition foundation ontology defining the first object and the second object and optionally extra objects this embodiment proposes to subdivide the domain in small building blocks that can be plugged when necessary in order to provide a solution which is scale invariant where some domains can be contained within other domains and also be object oriented.

By doing this the building blocks will be kept decoupled from the broader domain being available to be developed tested and used separately from other broader domains. This embodiment enables the scale invariance.

This embodiment approaches design starting from dividing the Domain in hierarchical smaller Building Blocks BB Domains. The smallest BB are called Object PCIML Model used to define the Person and Job Application examples above. As described an Object PCIML Model defines the objects structure its Finite State Machines and the rules that are captured using the PCIML.

Object PCIML Models are then imported by Component PCIML Models filtering the scope to the specific area of endeavour addressed by that Domain that are then imported by Universes PCIML Models that define a broader area of endeavour.

In applying it to real world situations Industry Domains Business Universe PCIML Models would establish a common language for a particular industry model. A particular enterprise within an Industry Domain might define Functional Domains Business Component PCIML Models along functional business areas within the organization. For example a typical business might have separate Domains for Human Resources Management Customer Management Supplier Management Manufacturing Financial Management Recruitment Management etc.

Refer to for visual hierarchy diagram where from a hierarchy perspective PCIML models can be of three different types that build the domain hierarchy a Universe PCIML Models b Component PCIML Models and c Object PCIML Models .

The embodiment assures the object model controls the object definition only. It is independent of any other object that also forms the domain. From a Service Oriented Architecture SOA perspective this subdivision enables the creation of unassociated loosely coupled units of behaviour and functionality that have no calls to each other embedded in them.

The core of the component definition including the Object Finite State Machines is defined in the Object PCIML Model captured during capturing in a computation independent manner the structure of a first object definition foundation ontology data and a second object definition foundation ontology data capturing in a computation independent manner the behaviour of the first object definition foundation ontology data and the second object definition foundation ontology data and capturing in a computation independent manner the rules of the first object definition foundation ontology data and the second object definition foundation ontology data .

Another embodiment delivers two types of relationships between models that are used to relate Object PCIML Models that are part of the same Logic Component PCIML Model .

The relationships are recorded at the broader level this mean that two Object PCIML Models can be related via a Component PCIML Model and two Component PCIML Models can be connected via a Universe PCIML Model without changing the child in this Parent Child relationship.

The Imports owl imports relationship defines the Parent Child relationship between PCIML models that are part of the same Domain. This relationship type is responsible for defining the Domain Architecture boundaries Domain Dependencies and Domain Structure.

The embodiment allows the import and remove of a model from a component or universe model. So a Universe PCIML Model will import many Component PCIML Models which then will import many Business Object PCIML Models .

When one Object PCIML Model is imported inside a Component PCIML Model the Main Thing of the Imported Object Model becomes a subclass of the Main thing of the broader domain model and the Main Operation of the Imported Object Model will have the Main Operation of the broader domain model as parent.

Refer to where the Recruitment Management Business Component PCIML Model as an example imports the Person and Job Application Business Object PCIML Models when performing the sub step receiving a reference of the definition foundation ontology defining the first object and the second object and optionally extra objects described on

Using the same example the class Recruitment Thing is created in order to be the superclass of Person and Job Application during the step receiving the class used to be the superclass of the constituents object classes used in calculating the domain vocabulary taxonomy . Refer to for the Recruitment Management vocabulary taxonomy .

Using the same example the Recruitment manager Agent is created in order to be able to change the Person and Job Application objects by defining this agent as parent agent of the Person and Job Application agents when receiving agent which interact with the component as distinct from a particular object .

Using the same example the operation Recruitment Management is created in order to group the Person and Job Application operations when receiving the component operation used to group the constituent object operations used in calculating the taxonomy of component operations . Refer to for the Recruitment Management operation taxonomy .

The Second type of relationship is about the Behavioural Functional Relationship between PCIML Models which are imported by the same Component or Universe. It is about building the Component or Universe Finite State Machine by relating all required Object or Component Finite State Machines recursively.

This embodiment proposes to use the PCIML construct Filter pciml Filter in order to relate the behaviour of two PCIML models.

As described in receiving filter qualifying the applicability of the at least one operation on the first and second object s finite state machine within the scope of an Object PCIML Model the pciml Filter is used for defining the single States which are possible to happen within the scope of the Object PCIML Model . It is also the main driver for the definition of the object model finite state machine by the definition of the Object Filter Operation State transition.

However when receiving behaviour data comprising the creation of a relationship between the second object s finite state machine data and the first object s finite state machine data by at least one filter qualifying the recursive aggregation of quasi orthogonal object state machines into components of wider scope using a Component PCIML Model or a Universe PCIML Model the Filter pciml Filter qualifying the recursive aggregation of quasi orthogonal object state machines into domains of wider scope is defined by the full proposition using the Subject Predicate Object pattern linking Object PCIML Models imported by the respective Component PCIML Model . In this way one State from one Object PCIML Model acting as Subject is going to be related via a Predicate that is also defined in the same Object PCIML Model to another State in another Object PCIML Model acting as Object in the broader Component PCIML Model .

The above embodiment embodies the approach where Domains are taken to be properly embedded and this hierarchy is modelled by the recursion of Component models between the lower limit of atomic Object models and the upper limit of Universe models. The composition of models is uniformly ruled by a single mechanism SPOP provided by the Filter.

The shows an example of the Recruitment Management Business Component PCIML Model . The Person Management Object PCIML Model defines the Person lifecycle from New Candidate to Employed state without taking in consideration the other functions that are required to evolve a candidate to an Employee. The Job Application Management Object PCIML Model defines the lifecycle of a Job Application from New Job Application to an approved or Rejected Job Application state.

When two Object PCIML Models are included inside a Component PCIML Model the Object PCIML Models lifecycle can be recursively connected using the pciml Filter so the Recruitment Management Component PCIML Model will describe the lifecycle of a candidate going through the process of creating an Job Application then preparing it before submitting to a prospect employer.

It is important from a dependency perspective to mention that the Filter with has Subject Created Candidate has Predicate hasJobApplication and has Object New Job Application relationship which couples two Object PCIML Models without changing the Object PCIML Models . The coupling happens inside the Recruitment Management PCIML Component Model leaving the Person Management PCIML Object Model and Job Application Management PCIML Object Model untouchable. This embodiment enables coupling invariance and also the ability to have a library of business objects which can be used as it is needed.

Refer to for an example the Filter Has Instantiated Job Application selected defined in the Job Application PCIML Model will be keep like below 

The coupling will happen in the Recruitment Management Component PCIML Model where for the same Filter Has Instantiated Job Application selected will be connected to the Subject and predicate like below 

By defining the full proposition on the example in the the new Job Application cannot exist by itself within the Recruitment Component. It needs a Created Candidate as Subject related by the predicate has Job Application .

From an Ontology Structure Perspective it creates the Job Application as a Range for the Property has Job Application .

This guarantees that each Object PCIML Model which contains one object lifecycle represented in a Object Finite State Machine will be connected via the pciml Filter in a Component PCIML Model where the two Objects will be connected forming the Component Finite State Machine which is composed of many Object Finite State Machines connected recursively.

Referring to now the graphical notation view defined in and is displayed with the inclusion of the of the Component X definition foundation ontology data relating the second object B definition foundation ontology data and the first object A definition foundation ontology data using PCIML defined in capturing in a computation independent manner a component definition foundation ontology data creating a relationship between the second object definition foundation ontology data and the first object definition foundation ontology data . The view displays the Component X that is interfaced to the external World via the ACCESS Layer .

Referring back to the second object B and the first object A were not connected inside the Component X . The shows the pciml Filter represented by the round rectangles with dot style patterns which define the object state patterns around only object states that enables operations that will achieve another State defining two separated Objects Finite State Machine FSM . The shows a different example of pciml Filter use case where it shows the connection of two individual objects FSM the Second and First objects which are related via the pciml Filter forming the Component X FSM. In this case the pciml Filter connects instances in a particular Subject from Second Object B State via a predicate to instances that are in a particular Object from First Object A State and in case this pattern is true the Operation is enabled achieving a new State.

The difference from the Filter and Filter from the is that in the example the Filter enforces that in order for the Operation to be enabled an instance of the object A1 is required to have an instance of B2 as Subject related via the predicate instead of only an instance of A1 from the example. In the other example of the Filter enforces that in order for the Operation to be enabled an instance of B3 subject requires to have an instance of A5 as object related via the predicate instead of only an instance of B3 from the example.

These two Filter definitions from also define that the instances of the First Object A acting as Object requires an instance the Second Object B acting as subject related via the property Predicate to exist. This connects the two Finite State Machines where the instance of the Second Object B needs to relate to an instance of the First Object A that will evolve in its own until it drives the evolution of the Second Object B instance. The Filter also defines the relationships between classes of the Domain.

The Derivations and all other constructs are just the same as they follow the object definitions however with a broader coverage.

Refer also to for the Operation Sequence Diagrams displaying the Recruitment Management Component Finite State Machine and also the two separated object Finite State Machine for Candidate and Job Application .

Refer to for a diagram that displays the Recruitment Person and Job Application PCIML Models Hierarchical and Behavioural Relationships.

Refer to for the PCIML graphical notation of the example the Recruitment Management Component PCIML Model Component definition foundation ontology data that is composed by two PCIML Object Models Second Object definition foundation ontology data and First Object definition foundation ontology data which are Person Management and Job Application Management respectively related hierarchically and behaviourally.

After defining the filters qualifying the recursive aggregation of object using the Recruitment Management example the next step would be for receiving the component specific as distinct from a particular object rule constrained authorizations connecting agents to events . In this example no new Authorization is created and the Person and Job Application objects authorizations are responsible to define the component authorizations.

PCIML is then responsible for formulating the findings in a formal language . This defines the entire Component logic that can be used by ESTCA as instructions in order to perform state transitions.

The embodiment also offers a frame based definition view where the Business Modeller or Business Domain is capable of editing of the Domain PCIML Models definition definition foundation ontology data .

Refer for the example of the frame based Definition View for the BOPersonManagement Object PCIML Model. The frame based Definition view is currently developed using Top Braid Ensemble delivered by Top Quadrant. Using the Person Domain example the header of the view displays the name of the model been edited. e.g. BOPersonManagement with PCIML in front to highlight that the edited model is a PCIML Model

The header also displays the hyperlink to navigate to the other frame based views provided by the PMDA Framework to support the Definition. The different frame based views are used for Simulation Hierarchy and Relationship Visualization and Process Debugging provided in the same environment as different Tabs. These frame based views are provided in order for the Business Modeller or Business Domain Expert to be capable to analyse the definitions from different perspectives.

At the Header there is also the Icon displaying a little disk which is used to save the changes on the PCIML model.

Below the header on the left side of the frame based Definition View there is the PCIML menu formed by a tree with nodes representing the PCIML Columns Structure Behaviour and Rules with their respective constructs provide by PCIML.

In order to navigate between the different instances of each construct the user only need to select the constructs desired.

By selecting a construct in the centre side of the view there is a grid which will display the instances of the construct selected on the left side. In the example the Grid has Focus on the Construct Thing .

On the Right corner of the Grid is also available a button used to insert instances of classes focused on the Grid in form of a Diamond with a Plus sign and a button used to delete the instance selected on the Grid in form of a Diamond with a Minus sign .

In case the user wishes to change or just review one of the instances displayed on the Grid it needs only to select the desired instance.

On the right side of the grid there is a Review and an Edit Form that is going to display the instance selected on the grid or also another instance selected using a hyperlink connected via a property. In the example the Person Thing is highlighted in the Grid and Displayed on the form.

This view also provides a template loader that could use any other model as a template and insert most of the PCIML Constructs that can then be adjusted saving lots of time and effort by reusing models which have similar state lifecycles.

The definition view also displays constraint violations generated by any data inconsistency identified and will be displayed by a particular icon with the message of the violation when hovering the mouse over each icon.

Another embodiment also provides many different methods of PCIML data import from xml csv files excel files and database connection that can be used to upload domains into the PCIML Definition Foundation Ontology.

Currently the navigation is coordinated by selecting a construct on the menu then an instance of the construct and then reviewing or editing the instance without a proper sequence due to technical restrictions of Ensemble. The ideal GUI for PCIML would be a wizard like type of application that takes the Business Modeller or Business Domain Expert to a sequence of screens that would capture the PCIML Domain in the same sequence described on the PCIML Example definition using the steps and . This is the end goal for the Definition PCIML View.

The entire Component logic is also used for consistency and validation checking and also for activity simulations driven by State Operation and Transition. This is a powerful feature which allows domain partitioners to validate simulate and print their domain modelling work.

The second frame based view deployed with the embodiment is called Operations View. This frame based view will provide the ability to simulate within the Finite State machine of the particular domain by running the inference button taking the Operations perspective.

The embodiment also allows the domain Business Modeller or Business Domain Expert to not only see the business processes sequencing with focus on the operations but also all the operation taxonomy of the particular Domain the condition rules that are linked to the state achieved by the operation etc.

Refer for the example of the frame based Operation view for the BDRecruitmentManagement Domain PCIML Model that imports the BOPersonManagement and the BOJobApplicationManagement

On the top left side of the frame based Operations View there is the Operation Taxonomy that shows the Recruitment Management hierarchy that is composed by Job Application Management and the Person Management operations. When an Operation is selected in the Taxonomy tree it will be displayed on the centre of the screen in the selected operation grid driving the display of the content of all other grid views. In the example the Job Application Creation is displayed in the centre of the page.

Since all other grids are updated based on the Operation selection on the Grid has Prerequisite Operation there are two operations that are required to happen before the Job Application Creation which are Candidate Creation and Job Application Instantiation.

On the Grid is Prerequisite Operation there is one operation that requires the Job Application Creation as prerequisite that is Job Application Preparation.

On the Grid Achieves State there is the state achieved by the Job Application Creation Operation In Draft Job Application.

On the Grid Conditions there are conditions related to achieving the in Draft Job Application State Validate Candidate Validate Job Position.

On the Grid Considered Events there are Events that are considered by the Job Application Creation Operation Save Job Application Button Save Job Application.

On the Grid Enabled By Filter there is the SPO Protocol which enabled the Job Application Creation Operation Has Instantiated Job Application Selected.

On the Grids has Subject has Predicate and has Object represent the Filter Parameters that enable the Job Application Creation Operation. They are respectively Created Candidate has Job Application New Job Application.

By selecting the Operations in one of the Grids is Prerequisite Operation or has Prerequisite Operation the selected Operation would become the focus and it will be displayed at the centre of the screen changing all the other grids that are refreshed based on the new selected operation.

This view is very useful to navigate through the State machine in order to validate if the sequence is correct from an Operation perspective.

The embodiment also provides a third frame based view which is called States View. This view will provide the ability to simulate within the Finite State machine of the particular domain by running the inference button with focus on the states.

It also allows the domain Business Modeller or Business Domain Expert to not only see the business processes sequencing with focus on the states but also all the vocabulary taxonomy of the particular Domain.

This view is very useful to navigate through the State machine in order to validate if the sequence is correct from a state perspective.

The fourth frame based view is called Relationship View. This view will provide the ability to visualise the relationships between classes which is defined using the Subject Predicate and Object Pattern during the pciml Filter definition within the particular domain.

It also allows the domain Business Modeller or Business Domain Expert to not only see the Classes or Entities relationship via properties but also make changes on the sequencing triggered by the Filters in the particular Domain and dynamically navigate through the relationships from the Main Subject of the Domain jumping from each relationship to the far related entity.

This view is very useful to navigate through the Domain Relationship in order to validate if all required relationships are already created.

The fifth frame based view is called Transition View. This view will provide the ability to visualise the full path of evolution with a focus on the States.

It also allows the domain Business Modeller or Business Domain Expert to not only see the evolution rules but also make changes on the sequencing triggered by the Filter Operation State Transition in the particular Domain.

This view allows the domain Business Modeller or Business Domain Expert to see each transition of the domain in detail enabling him to do the final adjustments.

With all these views the domain Business Modeller or Business Domain Expert will be capable to not only define the domain but also to think logically on how these domains could be changed in order to implement changes required by the Business.

The embodiment also provides a script for validating the models against the PCIML Rules in case all required properties of all instances of the nine constructs are filled the model is going to be validated. The script cannot identify if there are missing instances of constructs because this is a matter of the scope to be defined by the Business Modeller or Business Domain Expert.

The embodiment also provides a HTML Report that is dynamically created based on the Domain model inferred via TOP Spin. This report was used as examples of the PCIML constructs. These examples can be found and

This report provides a view of the domain that can be shared with Operation people of the particular domain for knowledge sharing and validation.

It is important to know that anytime a PCIML domain model is changed to describe a change on the business the next report will be representing the situation of the Model at the time of the report.

This mean that when the entire Domain is considered completed it become the source of truth of the Business to be used as requirement for software upgrades or to provide to auditors or also to be used by the strategic business people for simulation of new ways of performing business activities or procedures.

After defining the Object PCIML Models by capturing in a computation independent manner the structure of a first object definition foundation ontology data and a second object definition foundation ontology data capturing in a computation independent manner the behaviour of the first object definition foundation ontology data and the second object definition foundation ontology data and capturing in a computation independent manner the rules of the first object definition foundation ontology data and the second object definition foundation ontology data and the Component and Universe PCIML Models by capturing in a computation independent manner a component definition foundation ontology data creating a relationship between the second object definition foundation ontology data and the first object definition foundation ontology data .

The next step calculating the first and second object and component schema data and the rules model data creates the object schema rules and data models based on the definition foundation ontology model for the objects of interest where the first object A and second object B Object schema and the Domain Component or Universe Schema Graph models which are the schema models that formalise the data structure and the possible states of the domain. Each Schema Graph model is created based on a PCIML Model.

In order for the Web Server to display the GUI self service portal www.ABCjobapplication.com and the GUI portal www.ABCHumanResources Management.com displayed in using the ESTCA Web server the B Schema Graph and A Schema Graph and a component or universe Schema Graph where the relationships of B and A classes is stored for Person Job Application and Recruitment Management respectively are required to be created.

As explained before each PCIML meta model is a little database that holds instances of PCML Classes that describe part of the Domain so each Component or Object Schema Graph model is then the model that implements that part of the Domain.

Using as example the Object PCMIL Definition Model for Job Application that is stored in the following model file displayed in the . Fwk DomainModels BOJobApplicationManagement.ttl .

The PCIML Model BOJobApplicationManagement have the prefix BOJobApplication that is equivalent to the base URl .

Inside the PCIML Model the BOJobApplication JobApplication which is an instance of the pciml Thing Class is the same of .

This instance is then instantiated into an Object Schema Graph model BOJobApplicationManagement ex with Prefix JobApplication and Base URl . The Schema contains the class JobApplication JobApplication that is the same of .

The full transformation from PCIML to Schema Graph model is detailed in where the BOJobApplicationManagement is detailed with more instances examples defined inside each PCIML class constructs represented by the round rectangles.

The class constructs such as pciml Thing pciml Properties pciml State and pciml Filter will be used to create a new little Data Base where the classes are going to be the ones that were defined as pciml Thing and pciml State and not the PCIML Classes that used to calculate the instantiated Schema Graph model.

On the diagram on there are 4 lines with arrows connecting the PCIML instances of the Job Application PCIML Object Model BOJobApplicationManagement to the instantiated classes or properties on the new Job Application Schema Graph Model BOJobApplicationManagement ex .

ii. Each instance of pciml Propety becomes a rdf Property or other owl type properties depending on their type and are related to the respective Class as a domain property

iii. Each instance of pciml State becomes a SubClass restriction using min cardinality 1 and or cardinality 0 of the Class that is deployed in PCIML

iv. The Full Filter become the rdfs range relationship between the pciml hasPredicate property and the pciml hasSubject Class

The Instantiated Schema Graph model also respect the hierarchy defined for PCIML keeping the Component models separated from the Object models etc.

By keeping the Schema Graphs also separated the entire Schema is kept in small specialised schemas that are connected via the rdfs range linking subject properties to Object things which are kept in federated component or universe models. ESTCA is then capable of using only the modes required for the objects involved in each state transition. This embodiment enables enormous performance gains since ESTCA uses in most cases only the schemas of the First Object A and Second Object B when reasoning via an inference engine in calculating a valid state transition.

Comparing to a Relational DB World each Object model contain the schema of one table and its properties and the Component model contain the Relationship between the tables imported as Object Models representing a Domain Relational Schema.

The example on also displays the Job Application Schema Graph model. In the Diagram the Main Classes of the Object Schema Graph Model is displayed e.g. JobApplication JobApplication .

In the diagram the States are also created as subclasses of the JobApplication JobApplication that are JobApplication NewJobApplication JobApplication CreatedJobApplication JobApplication ReadyToSubmitJobApplication JobApplication SubmittedJobApplication .

The Properties are created related to the JobApplication JobApplication via the property rdfs domain.

The Schema Model for Job Application is then stored in the Fwk ExecutableModels BOJobApplicationManagement ex.ttl file.

After the Schema Graph is created in this example the Rules models which use SPIN Rules to formalise the Domain Rules is also created. The same as the schema each Rules model is created based on a PCIML Model.

In order for the Web Server to display the GUI self service portal www.ABCjobapplication.com and the GUI portal www.ABCHumanResources Management.com displayed in using the ESTCA Web server the A Rules models B Rules models and the component Rules models for Job Application Person and Recruitment Management respectively are also required to be created.

As explained before each PCIML meta model is a little database that holds instances of PCML Classes which describes a part of a Domain. Each Rules model is then the model that implements rules of part of a Domain.

The PCIML Model BOJobApplicationManagement have the prefix BOJobApplication which is equivalent to the base URl .

The condition BOJobApplication ValidateResume which is the same of is an instance of the pciml Condition Class Construct that is instantiated into a Rules Model BOJobApplicationManagement.spin with Prefix JobApplication.spin and Base URl 

During the instantiation the JobApplication.spin ValidateResume SPIN Constraint Rule which is the same of is created.

The transformation from PCIML Model to Rule models is also detailed in where the BOJobApplicationManagement is detailed with instances examples defined inside each PCIML class constructs represented by the round rectangles.

The instances of class constructs such as pciml Condition and pciml Derivation will be used to create a new Rules Model that holds Construct and Constraint SPIN Rules connected to the adequate classes defined in the Schema Graph.

On the diagram there are 2 lines with arrows connecting the PCIML instances of the Job Application PCIML Object Model BOJobApplicationManagement to the instantiated Construct and Constraint SPIN Rules on the new Job Application Rules Model BOJobApplicationManagement.spin .

i. Each instance of pciml Derivation is going to become an instance of a Construct SPIN Rule Template related to the appropriated Class.

ii. Each instance of pciml Condition is going to become an instance of a Constraint SPIN Rule Template related to the appropriated Class.

The diagram also shows that the Rules models imports the BOJobApplicationManagement ex Schema Graph model

The generated Rules Model also respect the hierarchy defined for PCIML keeping the Component and Universe models separated from the Object models etc.

By keeping the Rules also separated the entire Domain Rules is kept in small specialised rules repository that can be federated when appropriated. This embodiment enables enormous performance gains since ESTCA uses in most cases only the rules of the Objects A and B when reasoning via an inference engine in calculating a valid state transition.

If we compare to a Rules Engine World each Object Rules model contain rules that can be used separately by object or federated via a Component or Universe.

The Rules Model for Job Application is then stored in the Fwk RulesModels BOJobApplicationManagement.spin.ttl file.

After the Schema Graph is created the Data Instance models that are used to store instances of Domain classes is also created.

In order for the Web Server to display the GUI self service portal www.ABCjobapplication.com and the GUI portal www.ABCHumanResources Management.com displayed in using the ESTCA Web server the A and B Data Instance Graphs and the Domain Component or Universe Data Instance Graphs models containing the data instances or objects of the A and B classes or the domain respectively for Job Application Person and Recruitment Management respectively are also required to be created.

The Data Instance models are created as a new OWL model with the new Base URl with the prefix JobApplication data and the base URl that imports the respective Schema Graph model BOJobApplicationManagement ex which imports the respective Rules Model BOJobApplicationManagement.spin .

The Data Instance models also respect the hierarchy defined for PCIML keeping the Component and Universe Data Instance models separated from the Object Data Instance models etc.

By keeping the Data Instance Models also separated the entire Domain Data is kept in small data sources that are based on small specialised schemas that can be connected anytime for Model data Federation.

This embodiment enables the deployment of cloud applications where data can spread across many different servers.

The diagram also displays the JobApplication JobApplication Classes. Each Class has three different instances in italic representing 3 different Job Applications that are stored in the Job Application model.

From a component perspective BDRecruitmentManagement data Recruitment data model has some triples linking the Persons Candidate Worker as Subject to the Job Applications as Object via the predicate Person hasJobApplication using RDF Triples.

Since the BOJobApplicationManagement data JobApplication data model has a property called JobApplication hasCandidate that is pciml inversePropertyOf the Predicate Person hasJobApplication the inferred triples linking the Job Applications as Subject to the Candidate as Object via the predicate JobApplication hasCandidate are also stored in the BDRecruitmentManagement data Recruitment data Model using RDF Triples. JobApplication data 001233 JobApplication hasCandidate Person data Paul JobApplication data 001234 JobApplication hasCandidate Person data John JobApplication data 001235 JobApplication hasCandidate Person data Guil

By keeping the relationship triples at the Federated Component Model allows to be able to keep data separated and federated as it is suited in different situations.

The Data Instances Model for Job Application is then stored in the Fwk DataModels BOJobApplicationManagement data.ttl file.

After the PCIML data instances model creation it is possible to validate the data structure and the rules defined in the PCIML models. This model also enables the work of data migration since the data repository will be created.

The embodiment provides a SPARQL Motion web service that creates the data instance model that is an OWL model with suffix  data that import the Schema Domain Ontology  ex 

The embodiment also provides a frame based view for editing the data instance models which provides a tree with the resources taxonomy Classes with all its properties. The data instance frame based view offers the ability to insert real data into the model with the ability to infer the results that will apply the rules defined in the rules model .spin returning constraints on the data inserted.

At this stage all structure behaviour and rules of PCIML can be tested. The frame based view cannot control the Agents Events and Authorization definitions of PCIML because the access is external to the Domain and so the Agents the Events and the authorization are not described on the Ontology. They are going to be defined by the method for design and deployment of domain recursive state machines defined next.

After the Business PCIML models are defined and the Schema Rules and Data models are created the next step is capturing in a platform independent manner the first and second object and component design foundation ontology data for use in calculating a first and second object and component platform specific model data in accordance with the first and second object and component design foundation ontology data that is about defining the Business PPIML Design Models or Business design foundation ontology data for each object component and universe that is constituent of a particular business domain.

Each Business PPIML Design model contains one of the business domains constituent design captured using the Parametric Platform Independent Model Language PPIML . In the example the Business Component PPIML Design Model for the Recruitment Management and the Business Object PPIML Design models for Job Application and Person Management are created in order to have their technical design captured using the Parametric Platform Independent Model Language PPIML which in this example is specialised for the SPARQL Web Pages SWP Technical Platform running on the web server .

This embodiment proposes the construction of a mechanism to manage the concept to design discrepancies by declaring semantic interconnections between the business systems definition Business PCIML Domain Definition Models and a defined structure and dynamics of automation Technical PCIML Domain Definition Models which is intended as the basis of design. The Technical PCIML Domain Definition Models are grouped in a Technical Specification that is most suited for each particular Domain Design enabling the Business and Technical Interoperability . The PPIML Design model is the bridge between Business Domain Decomposition and the Technical Domain Decomposition responsible for managing the discrepancies.

The Business PPIML design models connect then business meta models M1 models Business PCIML Models to technical schema models M0 models Instantiated from Technical PCIML Models .

Each domain has a form for example we can have a domain that defines a TV. This domain will have the TV that can have the States On Off display menu display channel etc. The TV will also have the events that are represented by every button on its remote control and some conditions on what functionality required a different state to be available etc.

This same TV has not only a definition but a design which is what we see. It has a screen that is x inches large that has y kg that is z cm deep and that has w number of HDMI connectors etc.

The PPIML Design model is about the design of the Business Domain using a Web Portal that is the best method for interacting with Business Domains which are hosted as Web page templates within the web service . In this example we need to define the Job Application page that is x pixels large that is divided in z sessions each sessions has y components that have w buttons etc.

The design is about defining the way the Business Domain wants to present itself when communicating to different Agents on the external world. Another example the domain can communicate with Agents via messages and with other agents via a Portal and with others via Rest Web services.

The main extension provided by this embodiment is the addition of the Parametric Platform Independent Model Language PPIML used to capture the design of the domain based on different Technical Specifications that in the example is the Technical domain called Web Design Specification that is instantiated into the Technical Specification for Web Technical Design Schema Graph Models that are responsible for providing the Specific Technical Design Patterns classes that are used to capture the Business Domain Design with intent to provide web portals.

The technical specification is designed using the semantic web by providing a SWP Platform portal which can natively integrate to the schema rules and data graph models by querying using SPARQL to read from all triple store models. However a technical specification could be designed to simulate application frameworks like Sales Force or PeopleSoft or SAP. In case the behaviour of the designed application framework are changed to be pure service oriented by using only one state transition engine this applications could have their process orchestrated by ESTCA.

This is only possible because the Technical Specification is composed of Technical Design Schema Graph Models instantiated from Technical Component PCIML Model that in this example represents the Web Design Specification implemented using SWP.

As part of the Recruitment Management development in the example was decided that the application must be provided via the Web so the design patterns required to implement a Web Application were defined in many Technical Object PCIML Models grouped in a Technical Component PCIML Model called TCTechnicalServices.

The Technical Models are the models which describe the technical abstractions of the applications that can be implemented by a Technical Specification.

The ability to define different types of domains such as Business Framework Aspect Technical and Platform enables the content invariance.

Taking the Web Design Specification as an example that is described using the Technical Component TCTechnicalServices and the fact that PCIML is build using approaches to software modularization and composition the technical components used in this example will be defined in many Technical Object PCIML Models that are then grouped by the TCTechnicalServices Component via the property owl imports exactly the same way the Business models Recruitment Person and Job Applications are connected which was described previously.

The ability to create schemas and rules models from Technical Domain PCIML Models plus the structure provided by the Parametric Platform Independent Model Language PPIML with constructs that link the high level design and its subclasses to the definition of a business domain defined using PCIML is the key for building bridges between business and technical domains which is required for componentization of any Framework Architecture.

This is achieved by using the property subclass of PPIML construct that links each Technical Object PCIML Model to a PPIML Construct what allow the embodiment to integrate the classes of the schema models generated from a Technical Object PCIML Model as a subclass of a PPIML construct that are then linked with the PPIML Ontology that is going to be used to capture the design abstractions and specifications in the PPIML Models.

This is achieved by the creation of the PPIML link to a Technical Specification WebTechnicalSpec ontology model which has the base URl http estca.org PPIML WebTechnicalSpec .

The Technical Specification schema model imports then the two following models that form the Web Specification PPIML link 

ii. The TCTechnicalServices ex Schema Graph Model composed of all Technical Schema Graph for its Technical Object PCIML elements.

The Job Application PPIML Design Model is used as an example for the description of the step capturing in a platform independent manner the first and second object and component design foundation ontology data for use in calculating a first and second object and component platform specific model data in accordance with the first and second object and component design foundation ontology data . The Model imports the Web Technical Specification as the selected Technical Specification so the PPIML Design Model will import the model defined above connecting the PPIML Constructs described below to the instantiated technical schema model classes like in the example below using RDF Triples.

Another embodiment of the invention delivers the Parametric Platform Independent Model Language PPIML ontology which the class relationship diagram is represented graphically in which defines the view of a system from the platform independent viewpoint which is captured in the design foundation ontology data. The PPIML has constructs that exhibit a specified degree of platform independence so as to be suitable for use with a number of different platforms of similar type OMG 2003 .

The PPIML describes the construction of a system on an ontological level meaning that the construction of the system is specified without implementation details. It is important to say that a PPIML depends on a PCIML Definition Model to exist in order to enable the design.

PPIML is then a domain design language that captures domain design from a PIM view point connecting business PCIML models to technical schemas generated from technical PCIML models building a bridge between definition and design creating the Business and Technical Interoperability.

PPIML is an incomplete meta model that defines 9 main constructs mainly used as bridge between Business PCIML models and the technical domain components that are specific for a technical requirement defined as Technical PCIML models that could be specific to Web Client Server Mobile etc.

As explained before the final PPIML will be configured for each need based on the specific design required to deliver a business domain. The configuration is done by creating a Technical Component PCIML that would describe a particular technical specification. In this example is the SWP web application running on web server . After the technical domain schema is generated it will provide the technical abstractions required by defining the technical design that is attached to PPIML in order to extend the Business PCIML Domain Definition.

The final PPIML is then responsible in defining the design that will enable the business domain to interact with the external World. At the same time PCIML defines the domain logic the PPIML designs the way the external world can picture the same Domain in order to communicate with it.

As an example a Business Domain Logic Definition that require data input and output which enable a Human Resources Domain can be designed to be used in a Web Browser or a client server application or also a mobile device etc so the look and feel will be specific to a design type chosen. The same Business Domain can communicate also with other agents via messages and the information contained on these messages will have to comply with some specific standards.

There is also a PCIML PPIML link ontology that is composed only by the Property rdfs range definitions linking the properties of PPIML ontology to classes of PCIML ontology. This link ontology creates a neural connection between PCIML and PPIML. The Graphical representation of the PPIML and PCIML Link is represented graphically in

The meta model is an example of a layer 2 MOF Meta Object Facility model the model that describes PPIML ontology itself. These M2 models describe elements of the M1 layer and thus M1 models. These would be for example models written using the PPIML ontology. The last layer is the M0 layer or data layer. It is used to describe real world objects and in this case is composed of the particular technical component schema models generated from the M1 layer and Technical Domain instances.

On the step capturing in a platform independent manner the first and second object and component design foundation ontology data for use in calculating a first and second object and component platform specific model data in accordance with the first and second object and component design foundation ontology data is subdivided in sub steps used to capture the Object or Component or Universe PPIML Design foundation ontology data models of interest. The sub steps are used to define the Design of a Business PCIML Model defined before.

By performing the sub steps on The PPIML Design foundation ontology data is going to enable the design of any Business PCIML Object that can be person company location party invoice sales order product job application schedule accounts service purchase order manufacture order using Technical PCIML Objects like page form menu buttons actions transactions events users etc.

In order to illustrate the steps some examples are defined using the Job Application Business Object PPIML Design foundation ontology data Model that is used in the GUI and on implemented using the Web Design Specification Technical specification that describes the components stored as Web page templates used by a portal application that is hosted in the web service .

All Job Application Business Object PPIML Model together represent the Job Application canonical model by connecting the enterprise definition of Job Application with each Technical Application used to deploy Job Application type services. This enables the integration between capabilities to be defined at the Computation Independent viewpoint and not in the Platform Independent viewpoint as it is the case with the current technologies.

The first three PPIML constructs are responsible for describing what is required to design technically a Domain defined in PCIML. It defines the elements the possible output forms and the communication methods to deliver the design.

The first step is about receiving communication means required to connect the objects with appropriate agents using the PPIML Construct Communication ppiml Communication which groups the Technical PCIML instantiated schema models that deploy Communication type objects for the technical specification such as TOUserRoleCommunication TOGatewayManagement TOPortalManagement.

For the Job Application PPIML Design Model definition of PPIML Construct Communication refer to for some examples using RDF Triples like PPIMLBOJobApplication ABCJobApplicationDotCom a Portal Portal PPIMLBOJobApplication ABCJobApplicationDotCom ppiml implementsAgent PPIMLBOJobApplication Self serviceCandidate

Communication has implements agent ppiml implementsAgent property. Each instantiated technical PCIML model class that is subclass of ppiml Communication is going to have the above properties as part of their domains.

The implements agent ppiml implementsAgent defines a relationship with the PCIML construct Agent pciml Agent and defines the agent that is implemented using the communication creating the link between Design and Definition.

The next step is about receiving output means for state specific representations of objects using the PPIML Construct Output ppiml Output which groups the Technical PCIML instantiated schema models that deploy Output type domains for the technical specification such as TOMessageManagement TOPageManagement TOPageSectionManagement.

For the Job Application PPIML Design Model definition of PPIML Construct Output refer to for some examples using RDF Triples like PPIMLBOJobApplication ObjectJobApplicationPage a Page Page PPIMLBOJobApplication ObjectJobApplicationPage PPIML implementsResource JobApplication JobApplication

The Output defined is used for the Web Server to display the GUI self service portal www.ABCjobapplication.com and the GUI portal www.ABCHumanResourcesManagement.com displayed in using the ESTCA Web server .

Output has communicated via ppiml communicatedVia composed by ppiml composedBy and depict ppiml depict properties. Each instantiated technical PCIML model class that is subclass of ppiml Output is going to have the output properties as part of their domains.

The property communicated via ppiml communicatedVia defines a Communication ppiml Communication method that delivers the output.

The property depict ppiml depict defines a relationship with the PCIML construct Thing pciml Thing in order to define what thing is depicted by the particular output creating the link between Design and Definition.

The next step is about receiving elements required to build the outputs based on object requirements using the PPIML Construct Element ppiml Element which groups the Technical PCIML instantiated schema models that deploy Element type domains for the technical specification such as TOFormManagement TOFieldManagement TOButtonManagement TOMenuManagement and TOStyleSheetComponent.

For the Job Application PPIML Design Model definition of PPIML Construct Element refer to for some examples using RDF Triples like PPIMLBOJobApplication CreateNewJobApplicationMenu a Menu Menu PPIMLBOJobApplication OpenJobApplicationMenu a Menu Menu PPIMLBOJobApplication SaveJobApplicationMenu a Button Button PPIMLBOJobApplication SubmittJobApplicationMenu a Button Button PPIMLBOJobApplication ObjectJobApplicationForm a Form Form PPIMLBOJobApplication HasCandidateField a Field Field PPIMLBOJobApplication HasResumeField a Field Field PPIMLBOJobApplication HasCoverLetterField a Field Field

Element has implements resource ppiml implementsResource property. Each instantiated technical PCIML model class that is subclass of ppiml Element is going to have the Element properties as part of their domains.

The property implements resource ppiml implementsResource defines a relationship with the PCIML construct Resource pciml Resource in order to define what resource is implemented by this particular element creating the link between Design and Definition.

The next three constructs are responsible for describing the behaviour of outputs and elements. This evolution is represented in a finite state machine that is triggered when SPOP is matched enabling actions or transactions services that trigger actions responsible for delivering outputs. It defines the way the elements are executed or demonstrated as part of the domain behaviour it also drives the communication to the external world.

The next step is about receiving actions required to implement the events that can be emitted with the output using the PPIML Construct Action ppiml Action that groups the Technical PCIML instantiated schema models that deploy Action type technical domains for the technical specification such as TOActionEventComponent.

Below are some examples of the Job Application PPIML Design Model definition of PPIML Construct Action using RDF Triples PPIMLBOJobApplication SubmitJobApplicationActionEvent a ActionEvent ActionEvent PPIMLBOJobApplication SubmitJobApplicationActionEvent ppiml implementsEvent BOJobApplication SubmitJobApplicationButton PPIMLBOJobApplication SubmitJobApplicationActionEvent ppiml implementsElement PPIMLBOJobApplication SubmitButton

Action has implements element ppiml implementsElement and implements event ppiml implementsEvent Properties. Each instantiated technical PCIML model class that is subclass of ppiml Action is going to have the action properties as part of their domains.

The property implements element ppiml implementsElement defines an element ppiml Element that is implemented by this Action.

The property implements event ppiml implementsEvent defines a relationship with the PCIML construct Event pciml Event in order to link the Event that is computation independent to the action that is the technical implementation creating the link between Design and Definition.

The next step is about receiving services required to implement the operations used to move objects through their states using the PPIML Construct Service ppiml Service which groups the Technical PCIML instantiated schema models that deploy Service type technical domains for the technical specification such as TOActionServiceComponent TOTransactionServiceComponent

Below are some examples of the Job Application PPIML Design Model definition of PPIML Construct Service using RDF Triples PPIMLBOJobApplication JobApplicationSubmitingService a ActionService ActionService PPIMLBOJobApplication JobApplicationSubmittingService ppiml deployOperation BOJobApplication JobApplicationSubmitting

Service has deploy operation ppiml deployOperation property. Each instantiated technical PCIML model class that is subclass of ppiml Service is going to have the service properties as part of their domains.

The property deploy operation ppiml deployOperation defines a relationship with the PCIML construct Operation pciml Operation in order to link the Operation that is computation independent to the Service that is the technical implementation creating the link between Design and Definition.

The next step is about receiving subject predicate object protocol means that implement filters responsible for enabling services when receiving events using the PPIML Construct SPOP ppiml SPOP which groups the Technical PCIML instantiated schema models that deploy SPOP type technical domains for the technical specification such as TOStatePatternService.

Below are some examples of the Job Application PPIML Design Model definition of PPIML Construct SPOP using RDF Triples PPIMLBOJobApplication SubmittedJobApplicationPattern a StatePattern StatePattern PPIMLBOJobApplication SubmittedJobApplicationPattern ppiml implementsFilter BOJobApplication HasSubmittedJobApplication

SPOP has implements Filter ppiml implementsFilter and trigger ppiml trigger properties. Each instantiated technical PCIML model class that is subclass of ppiml SPOP is going to have the status properties as part of their domains.

The property trigger ppiml trigger defines a Service ppiml Service that is triggered by the ppiml SPOP.

The property implements Filter ppiml implementsFilter defines a relationship with the PCIML construct Filter pciml Filter in order to link the Filter that is computation independent to the SPOP that is the technical implementation creating the link between Design and Definition.

The next three PPIML constructs are responsible for describing how the technical configuration is going to control the Permissions and also the definition of Rules and Templates used to deliver domain specific rules functionality.

The next step is about receiving permissions used to connect agents to a communication means or to authorise elements and outputs via actions using the PPIML Construct Permission ppiml Permission which groups the Technical PCIML instantiated schema models that deploy Permission type of technical domains for the technical specification such as TOPermissionListManagement

Below are some examples of the Job Application PPIML Design Model definition of PPIML Construct Permission using RDF Triples PPIMLBOJobApplication SubmitJobApplicationPL a PermissionList PermissionList PPIMLBOJobApplication SubmitJobApplicationPL ppiml implementsAuthorization BOJobApplication SubmitJobApplicationAuthorization

Permission has implements authorization ppiml implementsAuthorization property. Each instantiated technical PCIML model class that is subclass of ppiml Permission is going to have the permission properties as part of their domains.

The property implements authorization ppiml implementsAuthorization defines a relationship with the PCIML construct Authorization pciml Authorization in order to link the Authorization that is computation independent to the Permission that is the technical implementation creating the link between Design and Definition.

The next step is about receiving rule defined constructs from the objects rule models used to validate conditions using the PPIML Construct Rule ppiml Rule which groups the Technical PCIML instantiated schema models that deploy Rules type technical domains for the technical specification such as TOSPINConstraintManagement.

Below are some examples of the Job Application PPIML Design Model definition of PPIML Construct Rule using RDF Triples PPIMLBOJobApplication ValidateResumeConstraint a SPINConstraint SPINConstraint PPIMLBOJobApplication ValidateResumeConstraint ppiml implementsCodition BOJobApplication ValidateResume

Rule has implements condition ppiml implementsCondition property. Each instantiated technical PCIML model class that is subclass of ppiml Rule is going to have the rule properties as part of their domains.

The property implements condition ppiml implementsCondition defines a relationship with the PCIML construct Condition pciml Condition in order to link the Condition that is computation independent to the Rule that is the technical implementation creating the link between Design and Definition.

The next step is about receiving templates declaring the formulas implemented inside functionality specific models used to calculate derivation rules using the PPIML Construct Template ppiml Template which groups the Technical PCIML instantiated schema models that deploy Template type of technical domains for the technical specification such as TOSPINConstructManagement

Below are some examples of the Job Application PPIML Design Model definition of PPIML Construct Template using RDF Triples PPIMLBOJobApplication dateSubmittedDefaultValueFormulaTemplate a SPINConstruct SPINConstruct PPIMLBOJobApplication dateSubmittedDefaultValueFormulaTemplate ppiml implementsDerivation BOJobApplication dateSubmittedDefaultValue

Template has implements derivation ppiml implementsDerivation property. Each instantiated technical PCIML model class that is subclass of ppiml Template is going to have the template properties as part of their domains.

The property implements derivation ppiml implementsDerivation defines a relationship with the PCIML construct Derivation pciml Derivation in order to link the Derivation that is computation independent to the Template that is the technical implementation creating the link between Design and Definition.

At the end of the PPIML design the Objects Job Application and Person and the Component Recruitment Management have their design patterns defined. PPIML is then responsible for formulating the findings in a formal language defining the domain design foundation ontology data used to communicate with ESTCA.

PPIML is deployed in 1 ontology file that is ppiml.owl Base URl and also one spin file that is ppiml.spin.ttl Base URl .

PPIML also delivers a model that is built to link the Design PPIML and Definition PCIML that is ppiml2pciml.owl Base URl 

The embodiment also provides the Technical Designer and Technical Domain Expert the Design frame based view currently developed using Top Braid Ensemble delivered by Top Quadrant like the frame based definition view shown in . Like the frame based definition view the header of the Application displays name of the model been edited is displayed. e.g. PPIMLBOPersonManagement with PPIML in front to highlight that the edited model is a PPIML Model.

The header also displays the hyperlink to navigate to the other views provided by the embodiment in order to support the Design. The different views are used for Hierarchy and Relationship Visualization provided in the same environment as different Tabs. These views are provided in order for the Technical Designer and Technical Domain Expert to be capable to analyse the definitions from a design perspective.

Below the header like in the definition view on the left side of the frame based Design View there is the PCIML menu tree formed by the PCIML respective constructs provide by PCIML in order to access the Domain Logic Definitions for reference.

And below the PCIML Menu tree there is the PPIML menu tree formed by the PPIML respective constructs provide by PPIML.

In order to navigate between the different instances of each construct the user only need to select one of the constructs desired like in the frame based Definition view.

By selecting any PCIML and PPIML construct in the centre side of the view there is a grid that will display the instances of the construct selected on the left side.

Another embodiment is responsible for Interpreting the PPIML Design Model in the form of Domain Platform Specific Template Instances .

This embodiment is highly coupled with the Platform that is going to support the Design. The current deployed Interpreter is focus in generating interpreted instances of SWP Elements that is deployed by the SWP Platform.

When defining the Technical Domain PCIML Model there are extra parameters captured in order to enable the automatic mapping between definition and design used for automatically loading most of the design 

In case the Definition is deployed using a different Platform such as SAP or PeopleSoft the above properties must be configured to generate the mappings. In case it is desired that the meta data that drives the Events in PeopleSoft and SAP to be automatically generated then this embodiment can be used as a start point. The entire logic in converting the design to a deliverable format that could then be uploaded in one of the Platforms need to be build from the scratch.

These elements implement HTML Pages Action Events AJAX Menus and Trees etc. This step is responsible in generating the Domain Platform Specific Template Instances containing the meta data which relates a business domain that in this example is the Recruitment Management to a Technical Specification design pattern used to describe applications like in the example of the www.ABCjobapplication.com and www.ABCHumanResourcesManagement.com implemented as web applications using the SWP Platform.

After the Business PPIML Design models are defined and after the Business PCIML Definition models are defined and the Schema and Rules and and Data models and and Domain Platform Specific Template Instances Models are created. The next step is capturing in a platform specific manner the first and second object and component deployment foundation ontology data for use in selecting a first and second object schema data and a first and second object rules model data in accordance with the first and second object data for use in selecting a first object schema data and a first object rules model data in accordance with the first object data . It is about defining the Application PPSML Deployment Models for each model that is constituent of a particular business domain.

Each Business PPSML Deployment model contain one of the domain business deployment captured using the Parametric Platform Specific Model Language PPSML . In the example the Business Component PPSML Deployment Model for the Recruitment Management and the Business Object PPSML Deployment model for Job Application and Person Management are created in order to have their deployment configuration captured using the Parametric Platform Specific Model Language PPSML . This example is specialised for the Semantic Web Platform. Some configurations are used to define the web server where the Portal application is running and the ESTCA web server where the ESTCA Computing device is running.

This embodiment proposes the construction of a mechanism to manage the design to implementation discrepancies by declaring semantic interconnections between the business systems design PPIML Business Domain Design and a defined structure and dynamics of machinery PCIML Platform Domain which is intended as the platform for deployment. The PCIML Platform Domain are instantiated in a Platform Specification that is most suited for each particular Domain Deployment enabling the Business Design and Platform Interoperability . The PPSML Deployment model is the bridge between Business Domain Design Decomposition and the Platform Domain Decomposition responsible for managing the discrepancies.

The Business PPSML deployment models connect then business design meta models M1 models Business PPIML Models to platform schema models M0 models Instantiated from Platform PCIML Models .

The PPSML Deployment model is about the deployment of the Business Domain using a Web Portal that is the best method for interacting with Business Domains . The Portal is hosted somewhere that is configured. In this example it uses the Web page templates within the web service .

The deployment is about defining which platform components support the Business Domain Design in order to execute and communicate with different Agents on the external world. Another example the domain can communicate with Agents via messages and with other agents via a Portal and with others via Rest Web services and this components need also to be defined.

The main extension provided by this embodiment is the addition of the Parametric Platform Specific Model Language PPSML used to capture the deployment of the domains based on different Platform Specifications . In the example a Platform domain called Semantic Web Specification that is instantiated into the Specific Semantic Web Platform Schema Graph Models is used to provide the Specific Platform Component classes that are used to capture the Business Domain Deployment with intent to deploy semantic web applications.

This platform specification example is designed using the semantic web as platform by defining the semantic web components. However a platform specification could be defined to be implemented using application frameworks like Sales Force cloud or PeopleSoft or SAP.

This is only possible because the Platform Specification is composed of Platform Schema Graph Models instantiated from Platform Domain PCIML Models . In this example they represents the Semantic Web Specification implemented using Top Braid Live.

The Platform Domain Models are the models that describe the platform abstractions of the component used to deploy a particular Platform Specification.

As part of the Recruitment Management deployment example was decided that the application must be deployed using Semantic Web and the fact that PPSML is build using approaches to software modularization and composition the platform components required by this example in order to deploy a full application will be defined as many Platform Object PCIML Models that are then grouped by the PCPlatformServices Component PCIML model via the property owl imports.

The ability to create schema models from Platform Domain PCIML Models plus the structure provided by the Parametric Platform Specific Model Language PPSML with constructs that link the high level design and its subclasses to the definition of a business domain defined in PCIML and the design of business domain designed in PPIML is the key for componentization of any Architecture Deployment.

This is achieved by using the property subclass of PPSML construct that links each Platform Object PCIML Model to a PPSML Construct what allow the embodiment to integrate the instantiated schema model classes from a Platform Object PCIML Model as a subclass of a PPSML construct that are then linked with the PPSML Ontology. This is going to capture the abstractions and specifications in the PPSML Models.

This is achieve by the Creation of the PPSML link to a Platform Specification SemanticWebPlatform ontology model which has the base URl http estca.org PPSML SemanticWebPlatform .

The Platform Specification ontology model imports then two models that form the SemanticWebPlatform PPIML link 

ii. The PCPlatformServices ex Schema Graph Model composed of all Platform Schema Graph for its Platform Object PCIML Components PO . . . 

So when defining the Job Application PPSML Deployment Model used below for the description of the step capturing in a platform specific manner the first and second object and component deployment foundation ontology data for use in selecting a first and second object schema data and a first and second object rules model data in accordance with the first and second object data it will import the Semantic Web Specification as Platform Specification so the PPSML Deployment Model will import the Ontology defined above connecting the PPSML Constructs described below to the instantiated platform schema model classes like in the RDF triples example below.

Another embodiment delivers the Parametric Platform Specific Model Language PPSML class relationship diagram represented graphically in which defines the view of a system from the platform specific viewpoint.

The PPSML extends the specifications defined in the PPIML with the details required to specify how that system uses a particular type of platform OMG 2003 . In other words the PPSML is a more detailed version of the PPIML .

PPSML is a domain deployment language that captures domain deployment foundation ontology data from a PSM view point connecting business PPIML models to platform schema models generated from platform PCIML models building a bridge between definition design and deployment creating the Business and Platform Interoperability.

PPSML is an incomplete meta model that defines 9 main constructs mainly used as bridge between Business PCIML models designed using Business PPIML models and the platform domain components that are specific for a platform requirement defined as Platform PCIML models that could be specific to Data Base Host Servers Applications Middleware RDF Stores Data Schemas etc.

The final PPSML will be customised for each need based on the specific platform required to deliver a domain. The customization is done by creating a Platform PCIML domain that would describe a particular platform specification domain that in this example is the Semantic Web Platform. After the platform specification is instantiated providing the platform abstractions required by deploying such platform that is attached to PPSML in order to deploy the PPIML Design defined.

The final PPSML is then responsible in defining the chosen platform to deploy such a design provide by PPIML and defined by PCIML to the external World. At the same time PCIML defines the domain the PPIML designs the way the external world can picture the same Domain the PPSML define the physical components that enable the design.

As an example a design that enable Web Components can be implemented using Java or JSP or PHP or SWP. The same design enable the Data to be stored in Relational DB that can be implemented using Oracle SQL Server or Sybase or triple stores like Oracle Jena or only RDF models.

There are also two link ontologies one PCIML PPSML link ontology that is composed only by the Property Range definitions linking the properties of PPSML ontology to classes of PCIML ontology and other PPIML PPSML link ontology that is composed only by the Property Range definitions linking the properties of PPSML ontology to classes of PPIML ontology. These link ontologies create a neural connection between PCIML PPIML and PPSML . The Graphical representation of the PPSML and PCIML Link is represented graphically in

An example is by linking a pciml Thing to a Data Repository or linking a pciml Thing to a Rules Repository or a pciml Operation to an Application Server item.

The meta model is an example of a layer 2 MOF Meta Object Facility model the model that describes PPSML ontology itself. These M2 models describe elements of the M1 layer and thus M1 models. These would be for example models written using the PPSML ontology. The last layer is the M0 layer or data layer. It is used to describe real world objects and in this case is composed of the particular platform domain schema model generated from the M1 layer and Platform data instances models.

On the capturing in a platform specific manner the first and second object and component deployment foundation ontology data for use in selecting a first and second object schema data and a first and second object rules model data in accordance with the first and second object data step is subdivided in sub steps used to capture the Object or Component or Universe PPSML Definition models of interest. The sub steps are used to define the Deployment of a Business PCIML Model defined before.

By performing the sub steps on The PPSML Deployment ontology for any domain it is going to enable the deployment of any Business Object that can be person company location party invoice sales order product job application schedule accounts service purchase order manufacture using Platform Objects like RDF Stores Application Server Host SPARQL Rules Engine etc grouped in a Platform Specification used to describe the Semantic Web Platform components used to implement the portal application that in this example is hosted in the web service and ESTCA Web Service .

In order to illustrate the steps some examples are defined using the Job Application Business Object PPSML Model that is used in the GUI and on implemented using the Semantic Web Specification Platform specification that describes the platform components used to store Web page templates .

In the example the server that runs the portal application that in this example is hosted in the web service the ESTCA computing device for state transitions of recursive state machines server is hosted in the ESTCA web server and all the other required domain models such as the domain specific source models including A Schema Graphs A Rules Models B Schema Graphs B Rules Models A and B Data Instance Graphs are going to be defined inside the Application PPSML Deployment Models .

The first step is about receiving addresses of all platform items required for implementing the objects and their agents using the PPSML Construct Address ppsml Address which groups the Platform PCIML instantiated schema models that deploy Address type of platform domains for the platform specification such as POHostManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Address refer to for some examples using RDF triples 

Address has instantiate ppsml instantiate specify address for communication with agent ppsml specifyAddressForCommunicationWithAgent and specify address for communication ppsml specifyAddressForCommunication properties. Each instantiated platform PCIML model class that is subclass of address is going to have the address properties as part of their domains.

The property instantiate ppsml instantiate defines an environment ppsml Environment that is instantiated on that respective address.

The property specify address for communication with agent ppsml specifyAddressForCommunicationWithAgent defines a relationship with the PCIML construct Agent pciml Agent and specify address for communication ppsml specifyAddressForCommunication defines a relationship with the PPIML construct Communication ppiml Communication in order to create the link between Deployment Design and Definition.

The next step is responsible for receiving environments specification that provide agents the object specific operations and user interface functionality using the PPSML Construct Environment ppsml Environment which groups the Platform PCIML instantiated schema models that deploy Environment type of platform domains for the platform specification such as POApplicationManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Environment refer to for some examples using RDF triples 

PPSMLBOJobApplication ABCHumanResourcesManagementdotcom Application portalName www.ABCHumanResourcesManagement.com

Environment has deploy capacity of main operation ppsml deployCapacityOfMainOperation and deploy capacity of service ppsml deployCapacityOfService properties. Each instantiated platform PCIML model class that is subclass of ppsml Environment is going to have the Environment properties as part of their domains.

The property deploy capacity of main operation ppsml deployCapacityOfMainOperation defines a relationship with the PCIML construct Operation pciml Operation and deploy capacity of service ppsml deployCapacityOfService defines a relationship with the PPIML construct Service ppiml Service in order to create the link between Deployment Design and Definition.

The next step is about receiving repository schemas that implement the object and component schemas using the PPSML Construct Repository Schema ppsml RepositorySchema which groups the Platform PCIML instantiated schema models that deploy Repository Schema type of platform domains for the platform specification such as PORDFSchemaRepositoryManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Repository Schema refer to for some examples using RDF triples 

Repository Schema has deploy schema of main thing ppsml deploySchemaOfMainThing and deploy schema of element ppsml deploySchemaOfElement properties. Each instantiated platform PCIML model class that is subclass of ppsml RepositorySchema is going to have the repository schema property as part of their domains.

The property deploy schema of main thing ppsml deploySchemaOfMainThing defines a relationship with the PCIML construct Thing pciml Thing and deploy schema of element ppsml deploySchemaOfElement defines a relationship with the PCIML construct Thing ppiml Element in order to create the link between Deployment Design and Definition.

The next three constructs of PPSML are responsible for describing the location of Platform behaviour components.

The next step is about receiving interfaces that embodies the PSM Platform Specific Model used by the each object or component to communicate using the PPSML Construct Interface ppsml Interface which groups the Platform PCIML instantiated schema models that deploy Interface type of platform domains for the platform specification such as PODomainSpecificInterfaceManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Interface refer to for some examples using RDF triples 

Interface has deploy interface of main operation ppsml deployInterfaceOfMainOperation and deploy interface of service ppsml deployInterfaceOfService properties. Each instantiated platform PCIML model class that is subclass of ppsml Interface is going to have the Interface properties as part of their domains.

The property deploy interface of main operation ppsml deployInterfaceOfMainOperation defines a relationship with the PCIML construct Operation pciml Operation and deploy interface of service ppsml deployInterfaceOfService defines a relationship with the PPIML construct Service ppiml Service in order to create the link between Deployment Design and Definition.

The next step is about receiving application servers specifications that are used to implement the interface for a particular object using the PPSML Construct Application Server ppsml ApplicationServer which groups the Platform PCIML instantiated schema models that deploy Server type of platform domains for the platform specification such as POSWPApplicationServerManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Application Server refer to for some examples using RDF triples 

Application Server has deploy Application Service Supporting the capacity of main operation ppsml deployASSupportingTheCapacityOfMainOperation and deploy Application Service Supporting the capacity of Service ppsml deployASSupportingTheCapacityOfService properties. Each instantiated platform PCIML model class that is subclass of ppsml ApplicationServer is going to have the Application Server properties as part of their domains.

The property deploy Application Service Supporting the capacity of main operation ppsml deployASSupportingTheCapacityOfMainOperation defines a relationship with the PCIML construct Operation pciml Operation and deploy Application Service Supporting the capacity of Service ppsml deployASSupportingTheCapacityOfService defines a relationship with the PPIML construct Service ppiml Service in order to create the link between Deployment Design and Definition.

The next step is about receiving data repository items used to store the objects using the PPSML Construct Data Repository ppsml DataRepository which groups the Platform PCIML instantiated schema models that deploy Data Repository type of platform domains for the platform specification such as PORDFDataRepositoryManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Data Repository refer to for some examples using RDF triples 

Data Repository has deploy instances of main thing ppsml deployInstancesOfMainThing and deploy instances of element ppsml deployInstancesOfElement properties. Each instantiated platform PCIML model class that is subclass of ppsml DataRepository is going to have the Data Repository properties as part of their domains.

The property deploy instances of main thing ppsml deployInstancesOfMainThing defines a relationship with the PCIML construct Thing pciml Thing and deploy instances of element ppsml deployInstancesOfElement defines a relationship with the PCIML construct Thing ppiml Element in order to create the link between Deployment Design and Definition.

The last three constructs of PPSML are responsible for describing the location of Platform rules components.

The next step is about receiving security means used to protect the object using the PPSML Construct Security ppsml Security which groups the Platform PCIML instantiated schema models that deploy Security type of platform domains for the platform specification such as POLDAPServerManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Security refer to for some examples using RDF triples 

Security has deploy security around the main thing instances ppsml deploySecurityAroundTheMainThingInstances and deploy security supporting the main operation ppsml deploySecuritySupportingTheMainOperation and deploy security around the element instances ppsml deploySecurityAroundTheElementInstances and deploy security supporting the Service ppsml deploySecuritySupportingTheService Properties. Each instantiated platform PCIML model class that is subclass of ppsml Security is going to have the Security properties as part of their domains.

The property deploy security around the main thing instances ppsml deploySecurityAroundTheMainThingInstances defines a relationship with the PCIML construct Thing ppiml Element and deploy security supporting the main operation ppsml deploySecuritySupportingTheMainOperation defines a relationship with the PPIML construct Service ppiml Service and deploy security around the element instances ppsml deploySecurityAroundTheElementInstances defines a relationship with the PCIML construct Thing ppiml Element and deploy security supporting the Service ppsml deploySecuritySupportingTheService defines a relationship with the PPIML construct Service ppiml Service in order to create the link between Deployment Design and Definition.

The next step is about receiving rules engines that are used for each domain object using the PPSML Construct Rules Engine ppsml RulesEngine which groups the Platform PCIML instantiated schema models that deploy Rules Engine type of platform domains for the platform specification such as POSPARQLMotionTransitionEngineManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Rules Engine refer to for some examples using RDF triples 

Rules Engine has deploy Rules Engine Supporting the main operation ppsml deployRESupportingTheMainOperation and deploy Rules Engine Supporting the service ppsml deployRESupportingTheService properties. Each instantiated platform PCIML model class that is subclass of ppsml RulesEngine is going to have the Rules Engine properties as part of their domains.

The deploy Rules Engine Supporting the main operation ppsml deployRESupportingTheMainOperation defines a relationship with the PCIML construct Operation pciml Operation and deploy Rules Engine Supporting the service ppsml deployRESupportingTheService defines a relationship with the PPIML construct Service ppiml Service in order to create the link between Deployment Design and Definition.

The next step is about receiving rules repository items used to store the object rules using the PPSML Construct Rules Repository ppsml RulesRepository which groups the Platform PCIML instantiated schema models that deploy Rules Repository type of platform domains for the platform specification such as POSPINRulesRepositoryManagement.

For the Job Application PPSML Deployment Model definition of PPSML Construct Rules Repository refer to for some examples using RDF triples 

Rules Repository has deploy rules of main thing ppsml deployRulesOfMainThing and deploy rules of element ppsml deployRulesOfElement properties. Each instantiated platform PCIML model class that is subclass of ppsml RulesRepository is going to have the Rules Repository properties as part of their domains.

The property deploy rules of main thing ppsml deployRulesOfMainThing defines a relationship with the PCIML construct Thing pciml Thing and deploy rules of element ppsml deployRulesOfElement defines a relationship with the PCIML construct Thing ppiml Element in order to create the link between Deployment Design and Definition.

At the end of the PPSML deployment the Objects Job Application and Person and the Component Recruitment Management have their deployment components defined. PPSML is then responsible for formulating the findings in a formal language defining the objects deployment platform components that can implement ESTCA.

PPSML is deployed in 1 ontology file that is ppsml.owl Base URl and also one spin file that is ppsml.spin.ttl Base URl .

PPSML also delivers a model that is built to link the Deployment PPSML and Design PPIML and Definition PCIML that are ppsml2pciml.owl Base URl and ppsml2ppiml.owl Base URl 

The embodiment also provides the Platform Specialists or Infrastructure Specialist with the frame based Deployment View. This view enables the editing of the Domain Deployment PPSML Models.

The frame based Deployment view is currently developed using Top Braid Ensemble delivered by Top Quadrant the same way the frame based definition FIG. and frame based design views are built. Like the definition view the header of the Application displays name of the model been edited is displayed. e.g. PPSMLBOJobApplicationManagement with PPSML in front to highlight that the edited model is a PPSML Model

The header also display the hyperlink to navigate to the other views provided by the embodiment in order to support the Deployment. The different views are used for Hierarchy and Relationship Visualization provided in the same environment as different Tabs. These views are provided in order for the Platform Specialists or Infrastructure Specialist be capable to analyse the definitions from a deployment perspective.

Below the header on the left side of the frame based Deployment View there is the PCIML menu tree formed by three nodes representing the PCIML Columns constructs provide by PCIML in order to access the Domain Logic Definitions for reference.

Right below the PCIML Menu tree there is the PPIML menu tree formed by nodes representing the PPIML Columns constructs provide by PPIML also for reference.

And for the end there is the PPSML menu tree formed by nodes representing the PPSML respective constructs provide by PPSML.

In order to navigate between the different instances of each construct the user only need to select one of the constructs desired like in the frame based Definition and Design view.

By selecting any PCIML PPIML and PPSML construct the right side of the view the grid will display the instances of the construct selected on the left side.

Another embodiment is responsible for generating the Application PPSML Deployment Model using the Business PPSML deployment models .

After defining the Business PPSML deployment models the Application PPSML Deployment Model connecting the Physical Platform Components and the technical designs that support a Particular Domain is created.

In this example the domain is accessed by applications hosted in that is composed of many models for all objects constituents of the domain the Application PPSML Deployment Model is used to map the object A First Object and subject B Second Object involved in a transition with 

When the definition design and deployment of the Recruitment Management Domain recursive state machine is completed. The executable models in the form of Domain Specific Models are calculated via transformations and its behaviour can be automated by the ESTCA Engine which is used to implement the GUI and that is the Recruitment Management domain where the object A is the Job Application and Object B the Person class. The models are also defining the Recruitment Management domain s integration with applications such as the two examples provided based in a particular technology www.ABCjobapplication.com and www.ABCHumanResourcesManagement.com running in the web server .

The Parametric Model Driven Framework PMDA Framework Deployed Using the Computer Implemented Method for the Definition Design and Deployment of Domain Recursive State Machines Orchestrated Using the Computing Device for State Transition of Recursive State Machines ESTCA .

In order to prove the efficiency of the computer implemented method for the Definition Design and Deployment of domain recursive state machines and the orchestration capability of the computing device for state transition of recursive state machines ESTCA and also extending the embodiment with Enterprise Architecture requirements the PMDA Framework is defined designed developed deployed and orchestrated using recursive state machines defined using the Subject Predicate Object Protocol SPOP.

When executing the computer implemented method for the Definition Design and Deployment of domain recursive state machines the Subject Predicate Object Protocol SPOP is captured during the domain definition using the PCIML construct Filter pciml Filter to capture and relate the objects finite state machines recursively to form components and universes behaviour which is then implemented by the PPIML Construct SPOP ppiml SPOP which is then deployed using the PPSML Construct Rules Engine ppsml RulesEngine which accesses the schema data rules model data data instances data and platform Specific Template Instances of objects configured using the PPSML Construct Repository Schema ppsml RepositorySchema and the PPSML Construct Rules Repository ppsml RulesRepository and the PPSML Construct Data Repository ppsml DataRepository and the PPSML Construct Interface ppsml Interface respectively. The Subject Predicate Object Protocol SPOP becomes then the protocol of communication via events received and sent by the computing device for state transition of recursive state machines ESTCA .

Since the Framework proposes an Architecture formed by a finite number of Models based on MDA CIM PIM and PSM abstraction views the Framework is called Parametric Model Driven Architecture PMDA Framework and the models are called PMDA Models.

Didactically the embodiment was described using the example of a Business Domain which defines designs and deploys the Recruitment Management Models which is composed by the Person and Job Application Management. In reality the Framework Domain Models were captured earlier in order to provide the proper Enterprise Architecture tool for capturing the Definition Design and Deployment of business type domain recursive state machines.

Based on the fact that the PMDA framework is build using the meta model foundation ontologies and the fact that the Framework is designed to deliver a model architecture the following domains Component and Object are defined using PCIML designed using PPIML and deployed using PPSML to enable the PMDA framework. All these models are the PMDA Framework Models and they are 

The PMDA Framework Models have a particular prefix FU which stands for Framework Universe PCIML Model Universe definition foundation ontology data FC for Framework Component PCIML Model Component definition foundation ontology data and FO for Framework Object PCIML Model Object definition foundation ontology data .

The FOModelManagement Framework Object PCIML Model defines the structure behaviour and rules around Models in order to enable a Parametric Model Driven Architecture Framework to manage the definition design and deployment of Models.

The same as the Recruitment Management Domain needs a Person and Job Application the PMDA Framework domain needs an infrastructure to manage Models and their lifecycle to deliver Enterprise Applications. These models are the model types required to deliver an Executable Enterprise Architecture. This Framework PCIML Definition Model describes then the Models types that are required in order to provide the required Model Architecture Framework. This 9 Framework models types are called PMDA Models and are 

These 9 Framework models types are then subdivided in hierarchical model types which define the model scope Universe Component and Object and also in domain types Business Aspect Framework Technical and Platform which are defined in the FOModelManagement Framework Object PCIML Model as things pciml Thing which are connected using the property pciml subClassOf to form the proper model structure. There are a total of 75 models types defined as things that represent all model types that support the Framework.

Using the PCIML Model as an example for each different Domain type there are different model types like 

The PCIML domain models are then subdivided based on different scopes like in the example for Framework models below 

It is important to remember that any instance of these model types are about defining designing or deploying Business Aspects and Framework models using technical specifications defined by Technical Domain models and platform specifications defined by platform Domain models forming the Enterprise domain formed by a hierarchy of Universe Component and Object Models.

As an example there is a Person Management Object PCIML Model that defines the Person Management Object captured using the PCIML or in a computation independent manner the definition foundation ontology data and a Job Application Management Object PPIML Model which defines the Job Application Management Object captured using the PPIML or in a platform independent manner the design foundation ontology data.

The FOModelManagement Object PCIML Model defines the entire definition of the Model Object using PCIML . As an example the properties the models have are defined using the PCIML Construct pciml Property the relationships that connect the model types to other model types by defining the pciml Filter Subject predicate Object patterns and also the rules that manage these relationships based on their state which are defined as conditions pciml Condition etc.

Since the Framework models define the evolution from Definition to Design and Deployment this means that the relationship between a PCIML Definition Model to a PPIML Design Model already define the stage of the evolution of the Domain from Definition to Design.

For example if the Recruitment Management Component PCIML Model has the relationship has PPIML Design Model with the Recruitment Management PPIML Design Model one can infer the Recruitment Management has its design already started.

The Models Types are related to other Model Types and or to any other object class defined in any of the PCIML Framework Universe constituent models such as Capability Technical Specification Platform Specification Implemented Services or Deployed Services via the pciml Filter predicate inside the PMDA Framework Component or any other new object class that is included as part for the PCPMDAFrameworkManagement. This means that the relationships between models provided by PMDA can be extended by the addition of new PCIML Framework object models like the Recruitment Management Component could be extended with other functionality such as Job Offer Interview Forms etc.

The relationships currently delivered by PMDA Framework are defined below as Subject Predicate Object Relationships using pciml Filter

Based on the fact that all functionality provided by the PMDA Framework is enabled by the defined PMDA Framework models all models from Definition PMDA Framework PCIML models to Design PMDA Framework PPIML models and Deployment PMDA Framework PPSML models are defined for all Object and Component models that are part of the PMDA Framework Models .

By making the PMDA Framework Models available PMDA allows the customisation of the framework also enabling the deployment of new functionality required. The potential of configuration and extension of the framework is unlimited and the ability to create the extensions is also enabled by the embodiment.

The PMDA Framework also requires Aspect models for Security management Authentication Management etc which form the Security Aspects Models which are also part of the PMDA Framework Models 

The Aspect Models have a particular prefix AU which stands for Aspect Universe PCIML Model Universe definition foundation ontology data AC for Aspect Component PCIML Model Component definition foundation ontology data and AO for Aspect Object PCIML Model Object definition foundation ontology data .

Based on the fact that all framework is authenticated and enabled by the defined Aspect Domains all models from Definition PCIML to Design PPIML and Deployment PPSML are defined for all Object and Component models that are part of the Security Aspects Models .

By making the Security Aspect Models available PMDA allows the customisation of the aspects also enabling the deployment of new functionality required.

PMDA is also supported by a series of Services implemented using SPARQL Motion Scripts Agent Computing Devices which execute specific functionality required by a model driven architecture that are used for Instantiation Simulation Transformation loading of identified patterns of data Interpretation and file management. These Services are provided as REST Web services by the PMDA Model Management Services which is implemented using devices such as the Web Services and are defined as external agents which provides model development architecture specific functionality. This services are not smart and they depend on ESTCA for orchestrations. The Framework Services are 

Supported by the scripts PMDA would use the Synergy between Service Oriented Architecture decoupling Framework dynamics PMDA Framework Models from Technology dynamics Web Specification PCIML Models and Semantic Web PCIML Models and MDA to transform the definitions captured for the PMDA Framework Definition Design and Deployment .

The same the Synergy enable the creation of an Architecture Framework such Parametric Model Driven Architecture PMDA Framework delivered in the form of meta meta model . The reason PMDA Framework is meta meta model is because it manages an architecture of models that are themselves meta models.

Using the Script number 4 with the PMDA Framework PCIML Definition Models as parameter the Framework will calculate the PMDA Framework Schema Data Ontology and also calculate the PMDA Framework Rules Model Data

Using the Script number 5 using the PMDA Framework PCIML Models the Framework will create a PMDA Framework Data instance models that imports the PMDA Framework Schema Data models

Using the Script number 12 using the PMDA Framework PPIML Design Models the Framework will interpret in PMDA Framework Platform Specific Models

Using the Script number 16 using the PMDA Framework PPSML Model the Framework will calculate a PMDA Framework Deployed model

The PMDA Framework Domain Specific Models can be deployed as an Appliance which can be implemented using Web server .

With the PMDA Framework Models the Security Aspects Models and the PMDA Model Management Services functionality implemented the PMDA Framework still needs a mechanism that allows the communication of the Services available in the External World to and from the Internal Domain Services.

Taking the PMDA Framework as an example the Framework Domain Models needs to communicate to some agents in order to perform specific Framework Model Services.

The PMDA Framework Design Models are designed using the Technical Specifications called WebTechnicalSpec defined by Web Specification PCIML Technical Models used for Web which is also used to design the Recruitment Management Domain. The PMDA Framework Deployment Models are deployed using the Platform Specification called SemanticWebPlatform used for Semantic Web which is also used to deploy the Recruitment Management Domain. The WebTechnicalSpec Technical Specification and the SemanticWebPlatform Platform Specification defined by the Semanctic Web PCIML Platform Models describe the SWP Platform which is a Web Application implemented and deployed using the Semantic Web. The SWP Platform sits between the PMDA Framework and the Agents that interact with the Framework.

The Web Specification PCIML Models are models which describe the web technical Specification Domain from PCIML perspective used to represents the Web Interface design pattern.

The Semantic Web Platform PCIML Models are models which describe the Semantic web Platform Specification Domain from PCIML perspective used to define the platform component types required by the Semantic Web Platform.

With the functionality required by the Framework and looking for a platform that could provide native connections to SPARQL Motion Scripts SPARQL Queries SPIN Templates function and Magic Properties that could be easily connected using Rest Web Services.

The SWP Platform is the application that implements a method of communication with the external world via Pages Menus Messages Buttons Action Events web services xml exports etc stored as Web Pages Templates . This templates are required by the PMDA Framework functionality and also to be able to enforce Aspects of Security like login pages authentication etc.

SPARQL Web Pages SWP is an RDF based framework to describe user interfaces for rendering Semantic Web data. Dedicated properties such as ui view are used to link RDFS OWL resources with user interface descriptions. User interface components are described with the help of a declarative object model that may contain SPARQL queries to dynamically insert data driven content. These object models can be defined either in terms of RDF structures or with XML files similar to JSP and Flex documents. The resulting UI object model can then be rendered into various target platforms in particular HTML and SVG.

Since SWP is provided by the Top Braid Live Platform it has also access to Rest Web Services that is the PMDA method used to communicate with agents via messages.

The SWP Platform follows the SWP recommendations and deploys SWP elements that would implement each one of the TDTechnicalServices Domain that are the basis for the Web Technical Specification WebTechnicalSpec defined by Web Specification PCIML Technical Models .

In other words the SWP Platform implements the Communication methods that can be used to communicate Events between the Domain Services and the external World. The SWP Platform provides Web page Templates which can be filled with Domain Platform Specific Templates

With the platform decided and with the focus in provide a portal to communicate with Users the following Components were build 

Create Session Web Service Script that creates a Model as a session and imports all domain models that represents the user session 

For example a component for creating AJAX Pages another that implements and AJAX Tree another implements an Update Action Service that will make calls to the ESTCA Web Server and other implements Specific Domain Functions that will make calls to the Platform Agents via web services. This connects the following agent roles to the Technology agents define next 

The PMDA Framework is deployed using 9 main logically separated Technology Agents which need access to the Domain and also are accesses by the Domain. These Agents are 

Now with the PMDA Framework Models the Security Aspects Models the Framework Services functionality implemented and a mechanism that allows the communication of the Services available in the External World to and from the Internal Domain Services the PMDA Framework needs a platform to orchestrate the Appropriate Events that should be enabled in order to access Domain Services based on the State of Models Managed by the Domain.

The PMDA Framework uses then ESTCA State Transition Engine implemented as ESTCA Web Server for the Events orchestration based on the State of the Instance of the Framework domain such as PCIML Models PPIML Models PPSML Models Schema Data Models Rules Data Models Capabilities Technical Specifications etc that are changed by an event or internal action that is going to interact with the PMDA Framework Agents driven by the PMDA Framework Web Portal for Users agent implemented using SWP Platform as an event Maestro.

The ESTCA Web Server computing Device is deployed as a SPARQL Motion Script that uses Top Spin Inference Engine that is enabled by the Top Braid Live Server technology that enable the delivery of Services via a Rest web services that delivers the engine responsible to coordinate the sequence of events to be communicated from and to the external world based on the state of the models defined as PCIML designed as PPIML and deployed as PPSML by PMDA Framework.

The ESTCA Web Server computing Device uses the PMDA Framework Domain Specific Models to know where to locate the PMDA Framework Schema Data Models PMDA Framework Rules Models Data and PMDA Framework Data Instance Models models required to provide the instructions structure behaviour and rules required by the ESTCA Web Server computing Device to process state transitions based in an inbound event.

By selecting only the right instances schemas and rules models that are appropriate to each transition based on the state to be achieved using the pcimlFilter via the SPO pattern the pciml Condition and the pciml Derivation definitions before executing the Inference Engine in order to infer only on the right data from the subject and object involved in the transition is a key element in order to deliver a good performance during each transition.

Many techniques can be used in order to connect this infrastructure to any other platform available on the market by only describing a different Technical Specification also using the PMDA Framework.

The ESTCA is also used to Orchestrate Applications like the Agent services which are integrated to PMDA only by describing their Technical Specification.

The engine could be used as an orchestration engine that could update any system at any time anywhere. It is just necessary an input of data from the master of data and then update the target system with enough information to move to the next event and then communicate again and so on.

The Components defined in the architecture could be deployed in the cloud as separated or federated appliances.

The shows the way PMDA Framework is implemented using the embodiment. The PMDA Framework brings together several recent technical developments and trends to create a practical tool that will drastically simplify the design development and deployment of Enterprise Information Systems which are 

The embodiment and consequently the PMDA Framework are built using the infrastructure currently provided by the Semantic Web Technology applying a Model Driven Architecture MDA perspective. In this way the 3 model layers representing distinct stakeholder views CIM PIM and PSM from MDA are implemented using the following features provided by the Semantic Web Technology 

This combination enables the creation of the following 3 separated MOF M2 Meta model Ontologies used for definition design and deployment which can be easily interconnected when required 

The Parametric Platform Independent Model Language PPIML Ontology Design Foundation Ontology in this example uses the Web Specification Schema models These many models are the schema data ontologies calculated by the Web Specification PCIML Models used to capture the Web Design Specifications.

The Parametric Platform Specific Model Language PPSML Ontology Deployment Foundation Ontology in this example uses the Semantic Web Platform Schema Ontology models These many models are the schema ontologies calculated by the Semantic Web Platform PCIML Models used to capture the Semantic Web Platform Specifications.

Using the MOF M2 Meta model Ontologies as the foundation the PMDA Framework drive the Ecology of the Enterprise Architecture that is composed of a finite number of models that will be transformed into an application. In this way the PMDA Framework captures the three different model types PCIML PPIML and PPSML used to capture Business Domain Definition Design and Deployment data using the respective PMDA Framework views provided by the PMDA Framework Web Portal for Users .

Each Model will import the respective foundation ontology that will define the schema structure of the data captured in each model. In this way the MOF M2 meta model ontologies underlies the Framework Views and model instantiations which are used to capture the Requirement Management and its constituents Definition Design and Deployment foundation ontology data defined below 

These Model Instantiations are going to hold the Definition Design and Deployment foundation ontology data of a particular domain using the structure dictated by one of the three foundation ontologies.

With the infrastructure provided by the PCIML PPIML and PPSML Models the next step in designing the Framework is creating an architecture which is modular and ecologic when connecting models by applying the concept of Enterprise Architecture that is to pursue optimisation not at the traditional fragmented level of individual business processes but in the context of the whole enterprise and to seek to best balance of automation and human work to make the enterprise agile and strategically flexible.

By ecology one mean the best way to connect remove transform and merge different model types that compose the Enterprise. It is about been able to separate models that should be separated and link models that should be linked. It is about defining each models responsibility for contributing to the Enterprise ecosystem without waist and lack of resources. It is about been able to remove easily a model that is not more required. Models are used to store objects first and second and component definition foundation ontology data.

The PMDA Framework provides a frame and method for driving the Enterprise Architecture semantically integrating its Domains Access Services and Information layers using the definition design and deployment foundation ontology data models. In this way the Enterprise will be modular enough for providing the flexibility required to keep evolving with the business changes required by growth.

This will also drive the Ecology of the Enterprise Architecture that is composed of a finite number of models that will be transformed into an application.

As demonstrated the PMDA Framework also introduces the concept of executable models which are composed of Schema data and Rules Model data that have their own behaviour defined.

The Recruitment Management PCIML Model contains the definition of the Recruitment Management Component and its constituent objects such as Person and Job Application Management from a Computation Independent viewpoint perspective becoming then the definition foundation ontology data for Recruitment Management.

The Recruitment Management PPIML Model contains the design of the Recruitment Management Component and its constituent objects such as Person and Job Application Management from a Platform Independent viewpoint perspective becoming then the design foundation ontology data used to implement the Recruitment Management Domain.

The Recruitment Management PPSML Model contains the deployment of the Recruitment Management Component and its constituent objects such as Person and Job Application Management from a Platform Specific viewpoint perspective becoming then the deployment foundation ontology data required for deploying the definition and design which enable Recruitment Management.

Supported by the Framework model types and scripts like in the example using the Framework Models the Recruitment Management Models are transformed.

Using the Script number 4 with the Recruitment Management PCIML Definition Model as parameter the Framework will calculate the Recruitment Management Schema Data Ontology and also calculate the Recruitment Management Rules Model

Using the Script number 5 using the Recruitment Management PCIML Model the Framework creates a Recruitment Management Data instance model that have the Recruitment Management Schema Data Ontology under it .

Using the Script number 12 using the Recruitment Management PPIML Design Model the Framework will interpret a Recruitment Mgt Platform Specific Model

Using the Script number 16 using the Recruitment Management PPSML Model the Framework will deploy a Recruitment Mgt Deployed model .

The deployed Domain Specific Models represented in the diagram as Recruitment Mgt Domain Specific Models can be deployed as an Appliance which can be implemented using the Web server in or in the cloud like in the example. The PMDA Framework claims to a be a platform independent Framework however as an example and proof of concept PMDA deliver a SWP Platform using SPARQL Web Pages SWP TopBraid Ensemble which can be implemented using a web server connected to the ESTCA Web Server that combined with the Domain Specific Models that in the example are the Recruitment Mgt Domain Specific Models deployed as an Appliance on the Cloud . Any other platform such as Java JSP ASP and PHP would be also valid platforms that would access Inference and SPIN via a Java API.

After the Recruitment Mgt Deployed models are deployed the Recruitment Management Domain is already available to be orchestrated using a different implementation of ESTCA and deployed as an end user application like the www.ABCHumanResourcesManagement.com examples in that is enabled by another instance of the SWP Platform Implementation and orchestrated by the ESTCA Web Server computing Device.

The Parametric Model Driven Architecture Framework is an enterprise modelling framework developed to provide IT and business stakeholders with a tool which enables the propagation of business definition changes into design development and deployment of services in a simplified way. It enables the management of the executable enterprise blueprint defined from a Computation Independent viewpoint and enables the technical structure and dynamics of automation and those of business systems to evolve independently.

The PMDA Framework brings together several recent technical developments and trends such as Enterprise Architecture Service Oriented Architecture Model Driven Architecture Cloud Computing Appliances Business Orchestration and Semantic Technology to create a practical tool that drastically simplifies the design development and deployment of Enterprise Information Systems.

While the technical means are well understood individually their synergy has not been generally perceived.

PMDA leverages this synergy by enabling a systems development life cycle SDLC that is founded on modelling the Executable Enterprise Business Architecture definition which is captured by the steps capturing in a computation independent manner the structure of a first object definition foundation ontology data and a second object definition foundation ontology data capturing in a computation independent manner the behaviour of the first object definition foundation ontology data and the second object definition foundation ontology data and capturing in a computation independent manner the rules of the first object definition foundation ontology data and the second object definition foundation ontology data and capturing in a computation independent manner a component definition foundation ontology data creating a relationship between the second object definition foundation ontology data and the first object definition foundation ontology data . The Executable Enterprise Business Architecture definition is delivered and governed using Capabilities.

The PMDA Framework functionality enables a flexible management of different model types which are used to define design develop and deploy Enterprise capability services. Each model is classified based on domain related information from different viewpoints business aspects framework technical and platform scope universe component and object levels of abstraction CIM definition foundation ontology PIM design foundation ontology and PSM deployment foundation ontology .

To enable the technical structure and dynamics of automation and those of business systems to evolve independently the framework classifies and separates models of different viewpoints into five different domain types which are 

Business Models used to describe the Business Architecture. Examples of Business Models are models which define Banking Pharmaceutical Customer Relationship Management Billing Management Human Resources Management Person Sales Order Job Application Party Organisational Structure etc.

Aspect Models used to describe Aspect Architecture that is those concerns which cut across business domains and are generally applicable to business systems. Examples of Aspect concerns are Security Reliability Scalability Resilience etc.

Technical Models used to describe the technical design patterns used to implement Capabilities Services. Technical Models define technical concerns. Examples are SAP PeopleSoft Mainframe Pages Menus Buttons Actions Services Records Objects Components etc.

Platform Models used to describe the platform specific components used to deploy Capability Services that have been implemented using Technical Models. Platform Models define platform domain components. Examples are NetWeaver PeopleTools Oracle Relational DB Oracle Triple Store Application Server ILOG Rules Engine Hosting Server etc.

Framework Models used to describe the PMDA Framework Architecture Domain. Examples of Framework Domain Models are models such as Model Capability Technical Specification platform specification and others proposed by Enterprise Architecture Frameworks like TOGAF Archimate and Zachman. These models implement the PMDA Framework.

The PMDA framework addresses the progressive decomposition required when defining a domain enabling domain models to be contained within other domain models of the same type. The framework recognises three different types corresponding to three different scopes namely 

Universe Models representing the maximum scope of a domain for instance the whole extended Enterprise. The universe models establish a common language for a particular industry model. A universe defines the enterprise behaviour in terms of constituent components and required interfaces.

Object Models representing objects i.e. atomic units of structure and behaviour such as Person Company Location Party Invoice Product Job Application Schedule Accounts Page Form Host Menu Buttons Data Repositories etc.

Component Models representing intermediate scopes with recursive embedding composition Functional Domains . The component models define domain structure by the way in which they are composed of other component or object models and their relationships. Examples of Component models are for Business Human Resources Management Customer Relationship Management Billing Management Financial Management for Aspect Security Services for Technology PeopleSoft for Platform Oracle Platform Components etc.

Using the classification and segmentation described above the PMDA Framework enables the Systems development life cycle SDLC delivered as Enterprise Capability Services.

Core Capability represents the actions which an endeavour could not thrive without. Core Capabilities are defined by definition models or definition foundation ontology data CIMs . Core Capabilities are implemented using Implemented Services defined by Design Models or design foundation ontology data PIMs and deployed using Deployed Services defined by Deployment Models or deployment foundation ontology data PSMs .

Implemented Service represents the mapping between a Core Capability and an Implementation Capability which is the same thing of a Technical Specification using Technical CIM captured using Design Models PIMs .

Deployed Service represents the mapping between an Implemented Service and a Deployment Capability which is the same thing of a platform Specification using Platform CIM captured using Deployment Models PSMs .

Based on the Core Capability the PMDA Definition phase delivers the definition of Business Objects and Components that are used to deliver the equivalent of TOGAF s Business Architecture using the Business Definition Models CIM Design Patterns required to create the TOGAF Information Systems Architecture during the design phase using the Technical Definition Models CIM and Platform Devices required to create the TOGAF Technology Architecture during the deployment phase using the Platform Definition Models CIM .

Definition Models CIMs definition foundation ontology data specify the logic of a system without showing constructional details using the Parametric Computation Independent Modelling Language PCIML . A CIM captures a domain s structure its behaviour in terms of Finite state machines FSM representing the lifecycles of objects and components and rules. The Definition Model plays an important role in bridging the gap between subject matter experts i.e. business experts and experts in the design and construction of the system i.e. IT experts . For example the Business CIMs define the business structure business lifecycles statecharts and business rules captured using PCIML .

Each CIM is defined using PCIML . The definition follows a bottom up approach where the first CIMs to be defined are the Business Object CIMs which capture the object s structure behaviour and rules. Building on this first step Business Component CIMs capturing the structure behaviour and rules of components can be defined. Component Finite State Machines FSM are constructed recursively by connecting the previously defined Object FSMs. Finally the Business Universe CIM represents the maximal component model.

Using the Definition Models CIM definition foundation ontology data the Framework provides views and functionality around 

The Business Component CIMs for example can be defined incrementally over time by different projects implementing different Business Components delivered by different Core Capabilities.

From a Core Capability perspective the Business CIMs capture the agents that are responsible for delivering the capability and also the taxonomy of services and resources provided by each capability as well as the associated business value business goals and business requirements. The Implemented and deployed services related to the Core Capability are captured in the Business PIM design foundation ontology data and Business PSM deployment foundation ontology data built in the next PMDA phases described below.

The PMDA Design phase delivers Implemented Services the equivalent of TOGAF s Information Systems Architecture. It starts by mapping a Core Capability with a particular Implementation Capability the Implementation Capability is defined by a technical component CIM also delivered in the PMDA Definition phase.

Continuing the example of the PMDA Design phase extends each Recruitment Management Business Component constituent CIM with a design specification captured using the respective Business Design Model PIM .

Design Models PIMs design foundation ontology data capture the design using the Parametric Platform Independent Modelling Language PPIML . A Platform Independent Model PIM captures the construction of a system on an ontological level meaning that the construction of the system is specified without implementation details. A PIM serves to extend the definition of Core Capabilities captured in a CIM which is mapped to an Implementation Capability with the design that best implements the Core Capability using PPIML . Each CIM can have multiple PIMs enabling a Core Capability to have many Implemented Services.

When creating a Business PIM an Implementation Capability or technical specification must be selected in order to define the design pattern to be used.

Implementation Capability Technical Specification are used during the creation of a new PIM which maps Core Capabilities using a CIM with design patterns defined by a Technical Component CIM. Each Implementation Capability is based on one Technical Component CIM which is composed of several Technical Object CIMs used to define individual elements provided by a particular type of design pattern. In the example of the same method used to create the Recruitment Management Business CIM is applied to create a Technical Component CIM called PeopleTools Services with its constituent Technical Object CIMs which define the Peopletools specific Pages Records Permissions Lists Reports Forms Messages etc.

When the Implementation Capability is created the schema and rules are instantiated from the PeopleTools Services Technical Component CIM and its constituent Object CIMs. The PeopleTools Services Component Schema and rules models are then imported by the PPIML meta model ontology connecting each model to the appropriate PPIML Construct. For example the Page is to be connected to the Output PPIML construct while the Record is going to be connected to the Element PPIML construct.

The PMDA Deployment phase delivers a Deployed Service the equivalent of TOGAF s Technology Architecture. It starts by mapping an Implemented Service PIM with a particular Deployment Capability Platform Specification used for deployment this Deployment Capability is defined by a platform definition CIM also delivered in the PMDA Definition phase.

Continuing the example of the PMDA Deployment phase extends each Recruitment Management Business Component constituent PIM with a Deployment Capability captured using the respective Business Deployment Models PSM .

Deployment Models PSMs deployment foundation ontology data capture the deployment configuration using the Parametric Platform Specific Modelling Language PPSML . A Platform Specific Model PSM extends the Implemented Services captured in a PIM which is mapped to a Deployment Capability that best deploys the Implemented Service using PPSML . Each PIM can have multiple PSMs enabling a Implemented Service to have many Deployed Services. When creating a Business PSM a Deployment Capability Platform Specification must be selected in order to define the deployment components to be used.

Deployment Capability Platform Specification are used during the creation of a new PSM which maps an Implemented Service using a PIM with deployment components defined by Platform Component CIMs. Each Deployment Capability is based on a Platform Component CIM which is composed of several Platform Object CIMs used to define individual services provided by a particular type of platform. When the Deployment Capability is created the schema and rules are instantiated from the Oracle Platform Component CIM and its constituent Object CIMs. The Oracle Platform Component Schema and rules models are then imported by the PPSML meta model ontology connecting each device to the appropriate PPSML Construct.

Each CIM PIM and PSM also has properties used for Project Management such as Allocated Resource Estimated Effort Percentage Completed Target Date etc used to measure the effort of Deployment.

The invention may be embodied using devices conforming to other network standards and for other applications including for example other WLAN standards and other wireless standards. Applications that can be accommodated include IEEE 802.11 wireless LANs and links and wireless Ethernet.

In the context of this document the term wireless and its derivatives may be used to describe circuits devices systems methods techniques communications channels etc. that may communicate data through the use of modulated electromagnetic radiation through a non solid medium. The term does not imply that the associated devices do not contain any wires although in some embodiments they might not. In the context of this document the term wired and its derivatives may be used to describe circuits devices systems methods techniques communications channels etc. that may communicate data through the use of modulated electromagnetic radiation through a solid medium. The term does not imply that the associated devices are coupled by electrically conductive wires.

Unless specifically stated otherwise as apparent from the following discussions it is appreciated that throughout the specification discussions utilizing terms such as processing computing calculating determining analysing or the like refer to the action and or processes of a computer or computing system or similar electronic computing device that manipulate and or transform data represented as physical such as electronic quantities into other data similarly represented as physical quantities.

In a similar manner the term processor may refer to any device or portion of a device that processes electronic data e.g. from registers and or memory to transform that electronic data into other electronic data that e.g. may be stored in registers and or memory. A computer or a computing device or a computing machine or a computing platform may include one or more processors.

The methodologies described herein are in one embodiment performable by one or more processors that accept computer readable also called machine readable code containing a set of instructions that when executed by one or more of the processors carry out at least one of the methods described herein. Any processor capable of executing a set of instructions sequential or otherwise that specify actions to be taken are included. Thus one example is a typical processing system that includes one or more processors. The processing system further may include a memory subsystem including main RAM and or a static RAM and or ROM.

Furthermore a computer readable carrier medium may form or be included in a computer program product. A computer program product can be stored on a computer usable carrier medium the computer program product comprising a computer readable program means for causing a processor to perform a method as described herein.

In alternative embodiments the one or more processors operate as a standalone device or may be connected e.g. networked to other processor s in a networked deployment the one or more processors may operate in the capacity of a server or a client machine in server client network environment or as a peer machine in a peer to peer or distributed network environment. The one or more processors may form a web appliance a network router switch or bridge or any machine capable of executing a set of instructions sequential or otherwise that specify actions to be taken by that machine.

Note that while some diagram s only show s a single processor and a single memory that carries the computer readable code those in the art will understand that many of the components described above are included but not explicitly shown or described in order not to obscure the inventive aspect. For example while only a single machine is illustrated the term machine shall also be taken to include any collection of machines that individually or jointly execute a set or multiple sets of instructions to perform any one or more of the methodologies discussed herein.

Thus one embodiment of each of the methods described herein is in the form of a computer readable carrier medium carrying a set of instructions e.g. a computer program that are for execution on one or more processors. Thus as will be appreciated by those skilled in the art embodiments of the present invention may be embodied as a method an apparatus such as a special purpose apparatus an apparatus such as a data processing system or a computer readable carrier medium.

The computer readable carrier medium carries computer readable code including a set of instructions that when executed on one or more processors cause a processor or processors to implement a method. Accordingly aspects of the present invention may take the form of a method an entirely hardware embodiment an entirely software embodiment or an embodiment combining software and hardware aspects. Furthermore the present invention may take the form of carrier medium e.g. a computer program product on a computer readable storage medium carrying computer readable program code embodied in the medium.

The software may further be transmitted or received over a network via a network interface device. While the carrier medium is shown in an example embodiment to be a single medium the term carrier medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term carrier medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by one or more of the processors and that cause the one or more processors to perform any one or more of the methodologies of the present invention. A carrier medium may take many forms including but not limited to non volatile media volatile media and transmission media.

It will be understood that the steps of methods discussed are performed in one embodiment by an appropriate processor or processors of a processing i.e. computer system executing instructions computer readable code stored in storage. It will also be understood that the invention is not limited to any particular implementation or programming technique and that the invention may be implemented using any appropriate techniques for implementing the functionality described herein. The invention is not limited to any particular programming language or operating system.

Furthermore some of the embodiments are described herein as a computer implemented method or combination of elements of a method that must necessarily be implemented by a processor of a processor device computer system or by other computational device. Thus a processor with the necessary instructions for carrying out such a method or element of a method forms a means for carrying out the method or element of a method.

Generally the invention comprises a computing device for state transitions of recursive state machines and a computer implemented method for the definition design and deployment of domain recursive state machines for computing devices of that type such devices are intended for the simulation of large systems involving human and automated components particularly the type generally called Enterprise Applications such devices are also applicable to a much wider range of fields such as cognitive modelling or robotics. The commonality between the computing device and the computer implemented method is the Subject Predicate Object Protocol SPOP which is used to capture instructions using the computer implemented method for the definition design and deployment of recursive state machines and also is the protocol used by the computing device for state transitions of recursive state machines to communicate inbound and outbound events based on the captured instructions. When executing the computer implemented method for the Definition Design and Deployment of domain recursive state machines the Subject Predicate Object Protocol SPOP is captured during the domain definition using the PCIML construct Filter pciml Filter to capture and relate the objects finite state machines recursively to form components and universes behaviour which is then implemented by the PPIML Construct SPOP ppiml SPOP which is then deployed using the PPSML Construct Rules Engine ppsml RulesEngine which accesses the schema data rules model data data instances data and platform Specific Template Instances of objects configured using the PPSML Construct Repository Schema ppsml RepositorySchema and the PPSML Construct Rules Repository ppsml RulesRepository and the PPSML Construct Data Repository ppsml DataRepository and the PPSML Construct Interface ppsml Interface respectively. The Subject Predicate Object Protocol SPOP becomes then the protocol of communication via events received and sent by the computing device for state transition of recursive state machines ESTCA .

Similarly it is to be noticed that the term coupled when used in the claims should not be interpreted as being limitative to direct connections only. The terms coupled and connected along with their derivatives may be used. It should be understood that these terms are not intended as synonyms for each other. Thus the scope of the expression a device A coupled to a device B should not be limited to devices or systems wherein an output of device A is directly connected to an input of device B. It means that there exists a path between an output of A and an input of B which may be a path including other devices or means. Coupled may mean that two or more elements are either in direct physical or electrical contact or that two or more elements are not in direct contact with each other but yet still co operate or interact with each other.

Reference throughout this specification to one embodiment or an embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention. Thus appearances of the phrases in one embodiment or in an embodiment in various places throughout this specification are not necessarily all referring to the same embodiment but may. Furthermore the particular features structures or characteristics may be combined in any suitable manner as would be apparent to one of ordinary skill in the art from this disclosure in one or more embodiments.

Similarly it should be appreciated that in the above description of example embodiments of the invention various features of the invention are sometimes grouped together in a single embodiment figure or description thereof for the purpose of streamlining the disclosure and aiding in the understanding of one or more of the various inventive aspects. This method of disclosure however is not to be interpreted as reflecting an intention that the claimed invention requires more features than are expressly recited in each claim. Rather as the following claims reflect inventive aspects lie in less than all features of a single foregoing disclosed embodiment. Thus the claims following the Detailed Description of Specific Embodiments are hereby expressly incorporated into this Detailed Description of Specific Embodiments with each claim standing on its own as a separate embodiment of this invention.

Furthermore while some embodiments described herein include some but not other features included in other embodiments combinations of features of different embodiments are meant to be within the scope of the invention and form different embodiments as would be understood by those in the art. For example in the following claims any of the claimed embodiments can be used in any combination.

In the description provided herein numerous specific details are set forth. However it is understood that embodiments of the invention may be practiced without these specific details. In other instances well known methods structures and techniques have not been shown in detail in order not to obscure an understanding of this description.

In describing the preferred embodiment of the invention illustrated in the drawings specific terminology will be resorted to for the sake of clarity. However the invention is not intended to be limited to the specific terms so selected and it is to be understood that each specific term includes all technical equivalents which operate in a similar manner to accomplish a similar technical purpose. Terms such as forward rearward radially peripherally upwardly downwardly and the like are used as words of convenience to provide reference points and are not to be construed as limiting terms.

In the claims which follow and in the preceding description of the invention except where the context requires otherwise due to express language or necessary implication the word comprise or variations such as comprises or comprising are used in an inclusive sense i.e. to specify the presence of the stated features but not to preclude the presence or addition of further features in various embodiments of the invention.

Any one of the terms including or which includes or that includes as used herein is also an open term that also means including at least the elements features that follow the term but not excluding others. Thus including is synonymous with and means comprising.

Thus while there has been described what are believed to be the preferred embodiments of the invention those skilled in the art will recognize that other and further modifications may be made thereto without departing from the spirit of the invention and it is intended to claim all such changes and modifications as fall within the scope of the invention. For example any example definition given above are merely representative of procedures that may be use representative of procedures that may be used. Functionality may be added or deleted from the block diagrams and operations may be interchanged among functional blocks. Steps may be added or deleted to methods described within the scope of the present invention.

Although the invention has been described with reference to specific examples it will be appreciated by those skilled in the art that the invention may be embodied in many other forms.

The present invention is applicable to the definition design and deployment of recursive state machines in support of any state defined process. Consequently it is applicable to the delivery and orchestration of event driven applications in any industry such as telecommunications banking utilities retail manufacturing etc. The applicable domains may also be subdomains common to many industries such as Human Resources Management Customer Relationship Management Billing Management Procurement Management etc.

The example of Recruitment Management which is a sub domain of Human Resources Management is used to describe the invention.

The present invention is also applicable to the definition design and deployment and orchestrations of framework type applications. The Framework constructed to maintain the domain models in accordance with the invention is also defined designed and deployed using the present invention.

