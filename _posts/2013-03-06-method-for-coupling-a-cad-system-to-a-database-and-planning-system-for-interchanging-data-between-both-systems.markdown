---

title: Method for coupling a CAD system to a database and planning system for interchanging data between both systems
abstract: The invention which relates to a method for coupling a CAD system to a database and planning system for interchanging data between both systems is based on the problem of specifying a method for coupling CAD systems to different database and planning systems, which method reduces the outlay in the event of changes and adaptations to different systems. According to the present invention, the problem is solved by virtue of the fact that the conversion between the communication protocols takes place in two substeps in such a manner that the data are converted from the first communication protocol into a third communication protocol in a CAD abstraction layer and are then converted from this third communication protocol into the second communication protocol in a useful layer or vice versa.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09354946&OS=09354946&RS=09354946
owner: CIDEON Software GmbH & Co. KG
number: 09354946
owner_city: Görlitz
owner_country: DE
publication_date: 20130306
---
The invention relates to a method for coupling a CAD system to a database and planning system for interchanging data between both systems in which case a first CAD side interface operating with a first communication protocol and a second database side interface operating with a second communication protocol are provided and in which case the data to be transmitted are converted from the first communication protocol to the second communication protocol or vice versa between the first and second interfaces.

Methods for coupling CAD applications to database and or planning systems such as SAP SAP GmbH data processing systems applications and products according to the prior art are implemented for example using a CAD side first interface a database side second interface and a software or interface module arranged between both interfaces. In this case the module is specifically geared to coupling two specific systems. So called programming interfaces API application programming interface provided by the manufacturer are usually used as interfaces for example.

If on the one hand the CAD system or on the other hand the database and or planning system changes the interposed module must be reprogrammed in order to provide the desired functionality again after a change. This reprogramming may affect parts or the entire module.

Such CAD integrations have already existed at least since the 1990s. CIDEON Software also already has many years of experience with CAD interface modules to SAP and other systems. The application AutoORG STL existed on the one hand as an interface module from AutoCAD to a separate dBase based or Oracle based database and on the other hand as an interface module to SAP. AutoORG STL was certified by SAP in 1996. CIDEON Software subsequently developed further interface modules to systems such as Baan PDM AMS and ProALPHA.

The modules were implemented as AutoCAD ARX modules. The integrations thus established a permanent connection between a CAD system and a database and or planning system also called a back end system . For a new CAD version sometimes even for a new service pack of the CAD system the interface modules had to be at least recompiled or possibly adapted in terms of programming. Connecting a new CAD system always required redevelopment of the integration.

Such interface modules have disadvantages such as a large amount of programming and testing effort for each change or each new coupling variant.

An object of the invention is to provide a method for coupling CAD systems to different database and planning systems which method reduces the amount of effort in the event of changes and adaptations to different systems.

In a method for coupling CAD systems of the type mentioned at the outset the object is achieved according to the invention by virtue of the fact that the conversion between the communication protocols is carried out in two substeps in such a manner that the data are converted from the first communication protocol in a CAD abstraction layer to a third communication protocol and are then converted from this third communication protocol to the second communication protocol in a useful layer or vice versa.

In the present description a communication protocol is understood as meaning for example a COM NET ObjectARX MDL WebService or Lisp API.

According to the invention the conversion of the data is subdivided into two or more substeps or areas. It is therefore possible for example when replacing the database and or planning system coupled according to the method that only the substep which converts the data between the second communication protocol of the second database side interface and the third communication protocol has to be adapted to the communication protocol of the new database and or planning system. The substep to be implemented in the useful layer therefore needs to be adapted. The substep of converting the data from the third communication protocol to the first communication protocol which takes place in the CAD abstraction layer can therefore be retained without change. If this substep has been subdivided for example into further sub substeps all of these sub substeps can be retained without change.

One refinement of the invention provides for further intermediate steps for adapting the communication by means of communication libraries to be inserted when converting the data from the third communication protocol to the second communication protocol or vice versa.

According to the invention a conversion substep can also be subdivided into further substeps. A further conversion substep may be provided for example in a module optionally arranged between the database and or planning system and the useful layer.

Another refinement of the invention provides for the conversions between the communication protocols to be carried out taking into account further CAD specific or customer specific specifications.

In addition to the general specifications for converting the data between the communication protocols in the useful layer and or in the CAD abstraction layer there may be further additional specifications which enable adaptation to customer specific or CAD specific specifications or additional options.

The basic idea is to provide an interface module according to the invention in the form of a so called virtual CAD API. The latter is abstracted from an underlying CAD system for example SolidWorks MicroStation Autodesk Inventor Solid Edge AutoCAD or CATIA.

The useful layer based on this then provides its functionality on the basis of the virtual CAD API. It therefore establishes a connection between the virtual CAD and the back end system.

An integration in a further superordinate back end system substantially involves according to the invention creating or adapting a further useful layer.

An integration in a further underlying CAD system substantially involves creating or adapting a further CAD abstraction layer.

In arranged below the interface module according to the invention is the CAD system which is coupled to the database and or planning system arranged above the module.

The interface module is connected to the CAD system via the first interface and is connected to the database and or planning system via the second interface .

In this case communication libraries may optionally comprise separate modules or else so called third party modules such as a programming interface back end API .

The useful layer may comprise one or more modules and implements the connection between the CAD system and the back end system .

This basic subdivision of the interface module into the subcomponents of the CAD abstraction layer and useful layer makes it possible to reduce the effort when adapting the range of functions and during adaptation to a new CAD system and or a new database and or planning system since a change usually needs to be made only in one of the layers or .

This variation is provided for example for functionalities which are extremely close to CAD or if a specific CAD functionality is not covered in the CAD abstraction layer .

This additional option provides the advantage that functionalities which are currently not enabled by the CAD abstraction layer can be incorporated within the scope of customer projects.

A first example of the interaction between the different layers of the architecture is illustrated in and is explained below.

During starting of the CAD system or subsequently on the request of the user or a program the CAD system loads a CAD module using its loading methods. For example Inventor loads a registered COM DLL AutoCAD loads an ARX file using AutoLisp or MicroStation loads an ma file.

The CAD module which contains program parts for expanding the capabilities of the CAD system now in turn loads connected modules. The CAD module need not know these files but rather these files can be determined dynamically by registration in COM using an ini file using a user selection . These modules have a defined interface for this purpose.

The modules create abstracted commands which are then divulged by the CAD abstraction layer in the CAD system for example by means of an entry in the CAD menu by means of insertion into a toolbar or by means of provision as a command which can be called from scripts.

After the preparation by loading the modules has been concluded the interface module is ready for operation.

At a subsequent time a command is used in the CAD system . This can be effected by selecting in the menu clicking in the toolbar typing in the command line keying in or calling from a script language such as VBA VSTA or AutoLisp.

The CAD abstraction layer converts the request into a command as was registered by the connected module and transmits it to the connected modules. This operation is illustrated in the right hand part of .

A CAD system emits events in particular situations as is illustrated in the left hand part of . These events are converted into CAD neutral events by the CAD abstraction layer. The connected modules can process them 

The third example shows the creation changing display use of the material or article of a parts list item.

In this sequence illustrated in functions which resort to material and or article information from the back end system are carried out with a parts list item in CAD.

The CAD abstraction layer then converts the request into a CAD specific request. Parts list functions of the CAD API are used in CAD systems having their own parts list management such as AutoCAD Mechanical or Inventor. The CAD abstraction layer itself provides simple parts list management in CAD systems without their own parts list management such as AutoCAD without add ons or MicroStation. For this purpose CAD objects with particular properties for example AutoCAD blocks with particular block names are considered and treated as parts list items.

A parts list item in the CAD system has property fields which can be read and written to by the interface.

These fields are now read and processed by the useful layer and the desired functions are called in the back end system .

After the function has ended information is also written from the back end object back into the CAD parts list item again if necessary 

In order to make it possible to manage a 3D structure and generally a CAD file with dependent files this structure of dependencies must be read and stored in the back end system. shows an example of how a structure in the CAD system can be mapped.

This structure in the CAD system is converted into a structure illustrated in in the CAD abstraction layer .

The CAD abstraction layer provides a separate structure. Even with the relationships between abstracted objects the CAD specialties for example the different types of dependencies are hidden from the business logic layer.

This abstracted structure from can now be used to transmit the structures to the back end system for example in order to create them as document parts lists in SAP to display them on SAP s CAD desktop or to process them in another manner. The integration may likewise use the structures to display parts of the structure or the entire structure on its own user interface side panel external program to carry out or process structure comparisons with the structures stored in the back end system.

The different CAD systems and add ons for these CAD systems contain a multiplicity of graphical and non graphical elements which constitute a representation of objects which can also be managed in the back end system . These may be for example

These elements contain data in the CAD system sometimes additionally data in an application specific database and sometimes graphical information for example an exact border. Some elements are identical to the displayed element pipe architectural area and others are only a representative block in AutoCAD with meta data .

The CAD abstraction layer now provides neutral access to an object and its properties. This makes it possible to access all properties in the same manner irrespective of whether these properties come from an attribute a database field or a graphical calculation area .

These neutral objects can now be linked to objects in the back end system for example technical spaces items of equipment architectural objects or materials in SAP. The useful layer can hard code this assignment or make it freely configurable as a result of which it is easily possible to incorporate further target objects. A computer in the back end system of SAP which is modeled in the CAD system can thus be depicted as an item of equipment which can now be assigned further data for example type build year installed software and other information.

The linking can be carried out by searching for or newly creating objects in the back end system with subsequent allocation of key fields. However it can also be carried out by manually changing a key field. A search can also use the values which have already been set on the abstracted CAD object in order to achieve a semiautomatic or fully automatic assignment.

For the CAD abstraction layer it is likewise possible to handle an area or a polygon which actually represents a separate element together with a block which likewise represents a separate element. From the point of view of the useful layer it therefore seems as if the element block which is hidden behind the neutral object has an area. illustrates an example of this.

An element can be assigned to an area by means of automatic detection. Conditions such as a block name a drawing layer name contents of fields or detection that there is an element inside an area can be taken into account in this case.

An element can also be assigned by means of a user assignment as a result of which an element can also lie outside an area if the area is too small.

An item of information relating to whether other elements are inside the area are just inserted into the area are moved from the area or are deleted is likewise provided. This makes it possible for the useful layer to update relationships between objects in the back end system synchronously or on request without knowledge of graphical information.

For example an item of equipment can be created when inserting an accordingly configured block the status can be set to invalid when deleting a block and the equipment can be removed from a technical space when shifting the block from the area of another block.

In some CAD systems it is not sufficient to consider CAD documents and their referenced files in this case a plurality of CAD documents must be considered as a set of documents.

This is the case for example in Plant 3D where a plurality of CAD documents are assigned to a Plant 3D project. The project in turn has further files such as configuration files or databases.

In AutoCAD Electrical there are electrical projects which manage CAD files together with other additional files.

In standard AutoCAD there are so called sheet sets which can be used to output files together or to enable faster access to associated files.

The solution involves providing a function for the useful layer on the abstracted CAD document which function answers the question of whether the CAD document belongs to a superordinate bracket object and if so making it possible to access an abstracted project object which then in turn again allows access to all referenced documents.

The useful layer can therefore move upward for example in the structure in irrespective of the specific type of bracket project sheet set of a given document and can resolve the complete structure from the superordinate project instead of from the loaded document.

This makes it possible to handle the documents combined by the project together in the back end system such as the storage of the structure common checking in or checking out etc.

Some CAD files have additional referenced files which belong only to this CAD file and cannot be sensibly used alone or referenced by other CAD files. Examples are the so called IDV files in older Inventor versions referenced old drawings in MicroStation and simulation files in Inventor. Since these are not intended to receive a separate document info record in the back end system as far as possible but rather are intended to be assigned as an additional original in the document info record of the CAD file the CAD abstraction layer does not display these files as referenced files but rather as an additional file for the CAD file.

Additional files for projects such as project databases project configuration files and others are also processed in this manner.

