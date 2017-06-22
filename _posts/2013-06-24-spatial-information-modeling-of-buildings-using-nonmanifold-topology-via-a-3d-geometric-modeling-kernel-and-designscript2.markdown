---

title: Spatial information modeling of buildings using non-manifold topology via a 3D geometric modeling kernel and designscript
abstract: A method, apparatus, system, and computer program product provide the ability to utilize a spatial model. A first input body and a second input body are obtained. A non-regular Boolean operation is performed that combines the first input body and the second input body to create and output an output body. The output body is a spatial model represented by a non-manifold solid body. A topological property of the non-manifold solid body is exposed to select and control an attribute of a building component represented by the non-manifold solid body.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09607111&OS=09607111&RS=09607111
owner: Autodesk, Inc.
number: 09607111
owner_city: San Rafael
owner_country: US
publication_date: 20130624
---
This application claims the benefit under 35 U.S.C. Section 119 e of the following and commonly assigned U.S. provisional patent application s which is are incorporated by reference herein 

Provisional Application Ser. No. 61 665 156 filed on Jun. 27 2012 by Roslyn Robert Aish and Aparajit Pratap entitled SPATIAL INFORMATION MODELING OF BUILDINGS USING NON MANIFOLD TOPOLOGY VIA ASM AND DESIGNSCRIPT.

This application is related to the following and commonly assigned patent application which application is incorporated by reference herein 

U.S. patent application Ser. No. 13 306 730 filed on Nov. 29 2011 now U.S. Pat. No. 8 825 459 entitled MULTI MODAL MANIPULATION OF A GEOMETRIC MODEL by Roslyn Robert Aish et. al. which application claims the benefit under 35 U.S.C. 119 e to U.S. Provisional Patent Application Ser. No. 61 417 808 filed on Nov. 29 2010 entitled DESIGN SCRIPT A MULTI PROGRAMMING PARADIGM LANGUAGE SYSTEM by Roslyn Robert Aish et. al.

The present invention relates generally to architectural geometry and in particular to a method apparatus system computer program product and article of manufacture for supporting a design of spatial architecture and the use of a spatial analysis of building models in related engineering design processes.

Much of the discourse in architectural geometry has focused on the geometric design and physical optimization of the material Building Model specifically the building structure envelope and the digital fabrication of facades.

Embodiments of the invention go behind the facade and consider architecture not so much as a physical building model but rather as the enclosure of space . The intent is to explore related geometric and topological concepts which can be the foundation of appropriate computational design tools. The objective of these tools is to support the design of a spatial architecture and the use of the spatial analysis of building models in related engineering design processes. To achieve this the concept of non manifold topology implemented in a three dimensional 3D geometric modeling kernel e.g. the ASM Autodesk Shape Manager 3D geometric modeling kernel is used but in a novel way in which the interior of what would normally be referred to as a solid body is not thought of being made of solid material but rather as an enclosed void that can be used in an architectural sense as the enclosure of space .

Much of the discourse in architectural geometry has focused on the geometric design and physical optimization of the material Building Model specifically the building structure envelope and the digital fabrication of facades. Embodiments of the invention go behind the facade and consider architecture not so much as a physical building model but rather as the enclosure of space . The intent is to explore related geometric and topological concepts which can be the foundation of appropriate computational design tools. The objective of these tools is to support the design of a spatial architecture and the use of the spatial analysis of building models in related engineering design processes.

To achieve this the concept of non manifold topology implemented in a 3D modeling kernel is utilized but in a novel way in which the interior of what would normally be referred to as a solid body is not thought of being made of solid material but rather as an enclosed void that can be used in an architectural sense as the enclosure of space .

To realize this concept a set of special non regular Boolean operations are used to create non manifold bodies and a series of topological classes that allow the user to access the resulting spatial models. Topological query functions are provided to allow the user to make a traversal of the spatial model of the building.

In view of the above one may distinguish between a spatial model of the building as the partitioning of the building envelope into discrete cells representing the interior spaces or rooms and the material model of the building which might use the topology of the spatial model for example the cells faces edges and vertices as supporting geometry. This topological and geometric modeling functionality is combined with the DesignScript associative modeling language described in the cross referenced application that is incorporated by reference herein . Spatial Information Modeling and parametric associative modeling work well together and allow the designer to experiment with what if scenarios. Changes to the spatial model can associatively update any downstream engineering analysis such as a web based energy analysis software e.g. Green Building Studio available from the assignee of the present application and the dependent material model.

In the following description reference is made to the accompanying drawings which form a part hereof and which is shown by way of illustration several embodiments of the present invention. It is understood that other embodiments may be utilized and structural changes may be made without departing from the scope of the present invention.

In one embodiment the computer operates by the general purpose processor A performing instructions defined by the computer program under control of an operating system . The computer program and or the operating system may be stored in the memory and may interface with the user and or other devices to accept input and commands and based on such input and commands and the instructions defined by the computer program and operating system to provide output and results.

Output results may be presented on the display or provided to another device for presentation or further processing or action. In one embodiment the display comprises a liquid crystal display LCD having a plurality of separately addressable liquid crystals. Alternatively the display may comprise a light emitting diode LED display having clusters of red green and blue diodes driven together to form full color pixels. Each liquid crystal or pixel of the display changes to an opaque or translucent state to form a part of the image on the display in response to the data or information generated by the processor from the application of the instructions of the computer program and or operating system to the input and commands. The image may be provided through a graphical user interface GUI module A. Although the GUI module A is depicted as a separate module the instructions performing the GUI functions can be resident or distributed in the operating system the computer program or implemented with special purpose memory and processors.

In one or more embodiments the display is integrated with into the computer and comprises a multi touch device having a touch sensing surface e.g. track pod or touch screen with the ability to recognize the presence of two or more points of contact with the surface. Examples of multi touch devices include mobile devices e.g. iPhone Nexus S Droid devices etc. tablet computers e.g. iPad HP Touchpad portable handheld game music video player console devices e.g. iPod Touch MP3 players Nintendo 3DS PlayStation Portable etc. touch tables and walls e.g. where an image is projected through acrylic and or glass and the image is then backlit with LEDs .

Some or all of the operations performed by the computer according to the computer program instructions may be implemented in a special purpose processor B. In this embodiment the some or all of the computer program instructions may be implemented via firmware instructions stored in a read only memory ROM a programmable read only memory PROM or flash memory within the special purpose processor B or in memory . The special purpose processor B may also be hardwired through circuit design to perform some or all of the operations to implement the present invention. Further the special purpose processor B may be a hybrid processor which includes dedicated circuitry for performing a subset of functions and other circuits for performing more general functions such as responding to computer program instructions. In one embodiment the special purpose processor is an application specific integrated circuit ASIC .

The computer may also implement a compiler that allows an application program written in a programming language such as COBOL Pascal C FORTRAN or other language to be translated into processor readable code. Alternatively the compiler may be an interpreter that executes instructions source code directly translates source code into an intermediate representation that is executed or that executes stored precompiled code. Such source code may be written in a variety of programming languages such as Java Perl Basic etc. After completion the application or computer program accesses and manipulates data accepted from I O devices and stored in the memory of the computer using the relationships and logic that were generated using the compiler .

The computer also optionally comprises an external communication device such as a modem satellite link Ethernet card or other device for accepting input from and providing output to other computers .

In one embodiment instructions implementing the operating system the computer program and the compiler are tangibly embodied in a non transient computer readable medium e.g. data storage device which could include one or more fixed or removable data storage devices such as a zip drive floppy disc drive hard drive CD ROM drive DVD drive tape drive etc. Further the operating system and the computer program are comprised of computer program instructions which when accessed read and executed by the computer cause the computer to perform the steps necessary to implement and or use the present invention or to load the program of instructions into a memory thus creating a special purpose data structure causing the computer to operate as a specially programmed computer executing the method steps described herein. Computer program and or operating instructions may also be tangibly embodied in memory and or data communications devices thereby making a computer program product or article of manufacture according to the invention. As such the terms article of manufacture program storage device and computer program product as used herein are intended to encompass a computer program accessible from any computer readable device or media.

Of course those skilled in the art will recognize that any combination of the above components or any number of different components peripherals and other devices may be used with the computer .

A network such as the Internet connects clients to server computers . Network may utilize ethernet coaxial cable wireless communications radio frequency RF etc. to connect and provide the communication between clients and servers . Clients may execute a client application or web browser and communicate with server computers executing web servers . Such a web browser is typically a program such as MICROSOFT INTERNET EXPLORER MOZILLA FIREFOX OPERA APPLE SAFARI GOOGLE CHROME etc. Further the software executing on clients may be downloaded from server computer to client computers and installed as a plug in or ACTIVEX control of a web browser. Accordingly clients may utilize ACTIVEX components component object model COM or distributed COM DCOM components to provide a user interface on a display of client . The web server is typically a program such as MICROSOFT S INTERNET INFORMATION SERVER .

Web server may host an Active Server Page ASP or Internet Server Application Programming Interface ISAPI application which may be executing scripts. The scripts invoke objects that execute business logic referred to as business objects . The business objects then manipulate data in database through a database management system DBMS . Alternatively database may be part of or connected directly to client instead of communicating obtaining the information from database across network . When a developer encapsulates the business functionality into objects the system may be referred to as a component object model COM system. Accordingly the scripts executing on web server and or application invoke COM objects that implement the business logic. Further server may utilize MICROSOFT S Transaction Server MTS to access required data stored in database via an interface such as ADO Active Data Objects OLE DB Object Linking and Embedding DataBase or ODBC Open DataBase Connectivity .

Generally these components all comprise logic and or data that is embodied in or retrievable from device medium signal or carrier e.g. a data storage device a data communications device a remote computer or device coupled to the computer via a network or via another data communications device etc. Moreover this logic and or data when read executed and or interpreted results in the steps necessary to implement and or use the present invention being performed.

Although the terms user computer client computer and or server computer are referred to herein it is understood that such computers and may be interchangeable and may further include thin client devices with limited or full processing capabilities portable devices such as cell phones notebook computers pocket computers multi touch devices and or any other devices with suitable processing communication and input output capability.

Of course those skilled in the art will recognize that any combination of the above components or any number of different components peripherals and other devices may be used with computers and .

Embodiments of the invention are implemented as a software application on a client or server computer . Further as described above the client or server computer may comprise a thin client device or a portable device that has a multi touch based display.

Architecture has been described as the enclosure of space . Indeed most buildings are conceived in two ways 

One might call such a conception a spatial or idealized model of the building. Most conventional Building Information Modeling applications adopt a different approach by providing design tools that support the placement and editing of components such as walls floors etc. that represent the material aspects of the building. This may be referred to as a material or physical model of the building.

It is of course recognized that at the end of an architectural design process the design engineering and construction teams should have produced a complete unambiguous building information model . However during an exploratory design process it is important that the architect can build the lightest possible model using the least effort that gives him the most accurate feedback about his design ideas. A modeling process that combines spatial modeling via non manifold topology and associative parametric modeling via scripting can facilitate this light weight least effort maximum feedback design methodology. The resulting spatial information model and associated topological queries can be used for 

To realize this concept a set of special non regular Boolean operations may be used to create non manifold bodies and a series of topological classes to allow the designer to access the resulting spatial models. Topological query functions are provided to allow the designer to make a traversal of the spatial model of the building.

This topological and geometric modeling functionality is combined with the DesignScript associative modeling language. Spatial Information Modeling and parametric associative modeling work well together and allow the designer to experiment with what if scenarios. Changes to the spatial model can automatically update any downstream engineering analysis such as Green Building Studio green energy analysis and the dependent material model.

A 3D manifold body has a boundary that separates the enclosed solid from the external void. The boundary is made of faces that have interior solid material on one side and the exterior void on the other. In a 3D manifold body each edge represents the meeting of exactly two faces so that even where faces join there is still solid material on one side of the boundary and a void on the other.

The boundary of a body does not have to be connected a body can have several disjoint pieces of boundary as long as each connected piece of the boundary is closed. This means a single body can contain disjoint volumes of material and a single volume can have one or more interior voids where each is defined by a closed boundary with material on one side and the interior void on the other.

In practical terms a manifold body without internal voids can be machined out of a single block of material.

A non manifold solid also has a boundary made of faces that separates the enclosed solid from the external void. However faces can also be internal separating one region of interior from another . Thus faces are either external separating the interior enclosed space from the exterior void or internal separating one enclosed space or cell from another .

Furthermore a non manifold solid can have edges where more than two faces meet so space around the edge can be divided into more than two regions each of which can be interior or exterior depending on the sidedness of the faces thus dividing a solid into multiple distinct internal regions.

One way to construct non manifold bodies is by using non regular Boolean operations. When Boolean operations are used to create a new body from input bodies these inputs are often configured so that all or part of one input body intersects with the other input body see .

Generally with regular operations external faces of the input bodies that are within the resulting body are removed.

Generally with non regular operations external faces of the input bodies that are within the resulting body are retained thus becoming double sided interior faces.

In a practical example of applying multiple non regular Boolean operations is illustrated. In this example there were multiple slice operations using planes in different X Y and Z direction followed by an Impose operation. This illustrates that even if the modeling process starts with manifold bodies the results after the first non regular operation will be a non manifold body. Therefore subsequent non regular operations will use non manifold bodies as input as illustrated in .

One may compare the results of the impose operation with the results of a regular and non regular union. There is no regular impose operation. However in a non regular impose operation internal face regions of the blank A within the tool B are removed.

One may also compare the results of regular and non regular imprint operations. In a regular imprint operation the result is only imprinted edges of the tool b on the external faces of the blank A with no new cells created. However in a non regular imprint operation the external faces of B within A are imprinted inside blank A thereby creating cells. A regular slice operation results in multiple bodies each with cells derived from splitting those in the original input non manifold body. In contrast a non regular slice operation on non manifold inputs results in a single non manifold body with new split cells.

In view of the above generally with non regular operations on non regular input bodies external faces of the input bodies and internal faces of the input bodies that are within the resulting body are retained except in the impose operation where internal faces of the blank A within the tool B are removed.

Shell The shell topology class defines a connected set of Faces in a manifold solid. A solid with a hollow void inside has two Shells one external Shell and another internal Shell.

Cell The cell topology class defines a closed continuous volume enclosing a spatial partition in a non manifold solid.

Face The face topology class may define an interior exterior face with material on one side and a void on the other or it can be a double sided interior face.

CellFace The Faces in a non manifold model have either one or two CellFaces attached to them two in the case of a double sided inside face . A Cell can be queried for its constituent CellFaces .

The geometry class may be implemented as solids e.g. a non manifold solid a B spline surface a B spline curve and or a point .

With the range of manifold and non manifold classes and the range of regular and non regular Boolean operations the designer is able to create manifold and non manifold solid models. By exposing the properties of geometry classes and topology classes to the designer the designer is able to make his her own e.g. independent topological queries. These queries can be used to build a number of different spatial information models.

The idealized spatial model of a building and the physical or material model of the building are interrelated.

The spatial model is the basis for the derived material model If the architect starts with the idealized spatial model then the resulting interior faces and edges can be used as the support geometry for the material components. However there may be conceptual boundaries between spaces that are not actually defined with material components for example air conditioning zones in an auditorium . With the spatial model as the basis for deriving the material model methodology only those partitions of the internal space that need to be materialized are populated with components.

The material model is the basis for the derived spatial model Conversely it may be possible to extract or derive a spatial model of the building from the physical model but this is exceedingly complex and error prone for example if the walls surrounding what is thought of as enclosed space are not water tight . In addition there is the question of how to represent spatial partitioning for which there is no equivalent material component.

The modeling starts with a non manifold solid body shown in 2D representing the idealized spatial form and partitioning of a building. Such a non manifold model may contain cells used for initial volumetric analysis e.g. for Green Building Studio analysis software while faces and edges may be used as support for geometry for the material building model.

The outer shell of the non manifold solid is extracted and converted to a manifold outer solid. The thin shell of the manifold outer solid may also be obtained by a regular shelling operation. Similarly the double inside faces of the non manifold solid are extracted and used to create offset solids .

The union of the thin shell of the manifold outer solid with the offset solids from the double inside faces of the original non manifold solid may also be obtained. Such a union represents the thin shell model of the original non manifold solid and may be used to represent the space take of the material model.

The exterior shell and interior shells may also be extracted. Potentially depending on the thin shell wall thickness for each cell in the original non manifold body there will now be a resulting interior shell . The uses of the shell model and are varied. The exterior shell building envelope that represents the space take of the whole building model may be used in city zoning rights to light. The interior shells could be used to more accurately represent the resulting interior volumes.

To create a material building model from a spatial information model the user first develops a spatial non manifold model of the building.

The collection of columns beams slabs roof panels facade panels and interior partitions form the material model of the building.

Alternatively the material model could be used to 3D print the complete material model of the building including the fabrication of the proposed moon base being designed by the European Space Agency. In this regard illustrates the artistic view of a lunar habitat covered by a 3D printed regolith shelter from 3D Printing Technology for a moon outpost exploiting lunar soil Ceccanti F. et al. 61Int. Astronautical Congress Prague 2010. http www.spacerenaissance.org projects LHD Praga Conference Luna.pdf 

The spatial model of a building and the analytical or material models of the building are interrelated. The spatial model consists of cells faces and edges.

The exemplary modeling sequence starts with a solid primitive at a . A trimming surface is defined at b and then used at c to trim the solid thereby creating a manifold building envelope.

The edges of the manifold building envelope are used as geometric supports for curvilinear structural members at d . Horizontal vertical and lateral slicing planes are then created at e . The slicing planes are used to slice the manifold building envelope to create a non manifold spatial building model at f . The edges of the non manifold spatial building model are used as the geometric supports for the curvilinear structural members at g .

At i a cone primitive is created to represent an atrium and an impose operation is used on the spatial building model. The atrium is then moved so that it intersects with the spatial building model while creating new cells and edges at j . As the atrium moves through the spatial model k new edges create corresponding structural members. Finally the atrium is moved out of the spatial building model at l and edges and structural members adjust accordingly.

Using the number of faces associated with each edge it is possible to determine the position of each edge within the spatial model and to populate different types of edges identified based on position with an appropriate type of structural component.

In view of the above it may be noted that non manifold topology and non regular Boolean operations e.g. non regular union may exist in the prior art in one or more forms. In contrast unavailable in the prior art embodiments of the invention provide for 

 1 the use of impose operations e.g. a sort of asymmetrical union as well as a non regular slice operation 

 2 the use of the count of the number of faces at a single edge to determine the position of that edge in the topology 

 4 the use of the faces whether outside face or inside face combined with the geometric orientation of these faces for example horizontal or not to populate the building model with exterior or interior wall floor or roof components 

 5 the use of non manifold topology with the internal spaces representing the cells of the non manifold model and topological queries used to find the adjacent cells and faces of a given cell as input to energy analysis and other building performance analysis and simulation software tools and

 6 the ability to vary the overall modeling configuration for example presence and position of an atrium within the overall building envelope and the consequential associative re computation of the manifold topology and hence structural configuration and spatial decomposition .

The Use of the Spatial Information Model for Energy Analysis e.g. via Green Building Studio Energy Analysis Software 

The exemplary modeling sequence begins at step a with the non manifold spatial building and the atrium . At step b the atrium is imposed onto the spatial building model . At step c the spatial building model is exploded so that the individual cells are distinct. Steps d h illustrate the movement of the atrium through the spatial building model .

The key topological elements illustrated in are the cell and the faces that bound each cell . In embodiments of the invention each topological elements may be given the following additional attributes to provide a complete data model for an energy analysis 

The topological analysis defines which faces are external or between cells therefore which cells are adjacent and therefore may affect the loads on the other cells. The notional thickness of the faces multiplied by the face area can be used to factor the cell volume to arrive at a reasonably accurate volumetric data without the need for a precise building model. Certainly this volumetric data will be within an acceptable tolerance when considered against the accuracy of the other data involved.

The DesignScript spatial information model may utilize functions in an analytical information model toolkit by using a foreign function interface FFI e.g. utilizing a C FFI of the AIM toolkit . In this regard the DesignScript spatial information model may provide cellular and face data to the AIM toolkit . The AIM toolkit may then export the cellular and face data to an energy analysis application such as Green Building Studio . The export of the cellular and face data may be in an extensible markup language XML based on a specific schema such as GBXML Green Building extensible markup language . The resulting energy analysis may be returned for display within DesignScript or via other energy analysis dashboards . As illustrated the energy analysis may also be displayed using an energy analysis and thermal load simulation program e.g. the EnergyPlus simulation application .

Parametric associative modeling and spatial information modeling applications work well together for a variety of reasons. Designers and architects are often interested in several what if scenarios where they can experiment with alternative values for key design parameters and generate alternative design solutions. Parametric associative modeling is a powerful tool that enables users to achieve this. In the context of Spatial Information Modeling for example designers can harness associative modeling to easily conceptualize different building configurations. Making simple tweaks to any of the spatial material or analysis models can associatively update the entire dependency graph and re execute the analysis to quickly generate several design alternatives and enable users to choose the most optimal or economical structural or energy saving solution.

At step a first input body and a second input body which may be manifold or non manifold bodies are obtained.

At step a non regular Boolean operation is performed that combines the first input body and the second input body to create and output an output body. The output body is a spatial model represented by a non manifold solid body.

The non regular Boolean operation may be an impose operation that imposes the first input body on the second input body. In such an impose operation internal faces within the output non manifold solid body that are derived from the first input body remain and internal faces within the output non manifold solid body that are derived from the second input body are removed.

The non regular Boolean operation may also be a slice operation that slices the first input body by the second input body e.g. which is a plane . The output body defines a single body with two cells based on the second input body. Further the output body retains the plane from the second input body.

At step a topological property of the non manifold solid body is exposed to select and control an attribute e.g. a type size and or geometry of a building component represented by the non manifold solid body. The topological property may be exposed via a set of topological classes that include query functions used to traverse the spatial model.

The topological property and a geometry of edges of the non manifold solid body may be used to control an edge linear or curvilinear based structural or non structural building component e.g. columns and beams . Such a topological property of the edges may be a property of constituent faces that forms the edges and defines each constituent face as an outside face or an inside face.

Alternatively or in addition the topological property and a geometry of faces of the non manifold solid body may be used to control a face planar or non planar based structural or non structural building component e.g. slabs . The topological property of the faces defines each face as an outside face or an inside face.

The topological property and the geometry of cells of the non manifold model may further be used to represent a partitioning of a building into its constituent spaces e.g. rooms . In such an embodiment the attribute may define occupancy data e.g. absolute per unit volume per unit area etc. of the constituent spaces. Further both the partitioning and the occupancy data may be used as input for energy analysis and other related simulation applications .

Embodiments of the invention present a novel application of non manifold topologies together with parametric and associative scripting to idealize design and model the spatial organization of buildings to use this information to create different analytical and material models of a building e.g. as the support geometry for a material model of a building and to perform useful environmental analyses of these enclosures . The core of the DesignScript system is a set of unified geometry and topology classes that can be driven through a number of different programming paradigms. Without the ability to manipulate such spatial models parametrically and programmatically it is doubtful whether a user could handcraft such complex geometry using interactive direct manipulations or whether a user could systematically explore alternative configurations and options. Accordingly a modeling process that combines spatial modeling via non manifold topology and associative parametric modeling via end user scripting can facilitate a light weight least effort maximum feedback design methodology.

This concludes the description of the preferred embodiment of the invention. The following describes some alternative embodiments for accomplishing the present invention. For example any type of computer such as a mainframe minicomputer or personal computer or computer configuration such as a timesharing mainframe local area network or standalone personal computer could be used with the present invention.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

