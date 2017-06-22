---

title: Entity-relationship model extensions using annotations
abstract: Embodiments extend the relational model and language of standard SQL, to recognize features of higher level entity-relationship models (ERMs). Annotation language is implemented in the data design language (DDL) to incorporate tables and entities Using DDL, annotations are typed structures of metadata. Annotations may be used for types, entities and elements. In the query language (QL), annotations may be added to the standard QL. A reflection program may use the metadata of the annotation language for reflection on the tables or entities.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09430523&OS=09430523&RS=09430523
owner: SAP SE
number: 09430523
owner_city: Walldorf
owner_country: DE
publication_date: 20130906
---
Embodiments relate to databases and in particular to annotating extensions to a database language to accommodate higher level entity relationship models.

Unless otherwise indicated herein the approaches described in this section are not prior art to the claims in this application and are not admitted to be prior art by inclusion in this section.

A database is a powerful tool for the storage organization and analysis of large volumes of data. At a low level a database may employ fundamental data definition and processing that is based upon a relational model. In particular a data definition defines a data type with sufficient metadata being associated therewith. A data definition may also involve a definition of a database structure such as columns and tables. Many database structures rely upon Structured Query Language SQL as the standard database language to define read and manipulate data within a database. In its standard form SQL itself reflects the basic relational model of the database.

Various other types of applications e.g. toolsets are constructed by developers to allow consumers to interact with the database in an efficient and intuitive manner. Such applications are typically provided in an application layer overlying the database.

The overlying applications such as consumer technology and toolsets provided by developers may introduce higher level models e.g. entity relationship models ERMs in order to contribute semantics and ease consumption by the user. In particular a plain data model on the SQL level only contains the requisite information to process data on the SQL level. Adding more information in a declarative fashion provides potential for higher level engines to offload work from developers by contributing more semantics. Adding more information in a declarative fashion can also make data models more comprehensible thereby easing their consumption by users.

One example of a higher level model is an OData Entity Data Model EDM . In particular OData is a web protocol standard providing platform agnostic interoperability for querying and updating data. OData leverages web technologies such as HTTP Atom Publishing Protocol AtomPub and JSON JavaScript Object Notation in order to provide access to information from a variety of applications. The simplicity and extensibility of OData can provide consumers with a predictable interface for querying a variety of data sources.

Other examples of higher level models may include the Semantic Layer in the Business Intelligence BI platform of SAP AG in Walldorf Germany Java Persistence API JPA and enterprise objects in Java or the business objects frameworks in Advanced Business Application Programming ABAP of SAP AG. Also the River programming model and the River Definition Language RDL of the River application development framework for SAP AG in Walldorf Germany are based upon entities linked by relationships.

Even though those higher level models may share many commonalities the individual information cannot be shared across stacks. That is the higher level models mentioned above contribute essentially the same kind of additional information yet that information is provided in different ways that interfere with its being shared across higher level models e.g. between an OData EDM and an ERM created using RDL .

This situation results in a fragmented environment with information unable to be shared between applications. To cope with this fragmentation redundant information is provided with application developers and customers contributing the same essential information in multiple forms thereby undesirably increasing overhead.

Furthermore while the developers of consumer technologies may have some knowledge of SQL they are generally not experts in complex SQL programming. Thus there is a need for an improved language for interacting with relational databases.

Embodiments extend the relational model and language of standard SQL to recognize features of higher level entity relationship models ERMs . Annotation language is implemented in the data design language DDL that defines organization of data and associated metadata in a database to incorporate tables and entities using DDL annotations are typed structures of metadata. Annotations may be used for types entities and elements. In the query language QL annotations may be added to the standard QL. A reflection program may use the metadata of the annotation language for reflection on the tables or entities.

A computer implemented method according to an embodiment comprises providing a database organized according to a relational model providing a database engine in communication with the database utilizing a language describing the relational model providing an application comprising an entity relationship model ERM including a first entity a second entity and a relationship between the first entity and the second entity and elements causing a query engine of the application to communicate a query to the database engine utilizing an annotation language the annotation language comprising a typed structure of metadata related to the first entity the second entity and the elements and causing the database engine to return a query result to the query engine based upon the annotation language.

In various embodiments the method further comprises reflecting at runtime on the annotation language.

A non transitory computer readable storage medium embodies a computer program for performing a method comprising providing a database organized according to a relational model providing a database engine in communication with the database utilizing a language describing the relational model providing an application comprising an entity relationship model ERM including a first entity a second entity and a relationship between the first entity and the second entity and elements causing a query engine of the application to communicate a query to the database engine utilizing an annotation language the annotation language comprising a typed structure of metadata related to the first entity the second entity and the elements and causing the database engine to return a query result to the query engine based upon the annotation language.

An embodiment of a computer system comprises one or more processors and a software program executable on said computer system. The software program is configured to provide a database organized according to a relational model provide a database engine in communication with the database utilizing a language describing the relational model provide an application comprising an entity relationship model ERM including a first entity a second entity and a relationship between the first entity and the second entity and elements and cause a query engine of the application to communicate a query to the database engine utilizing an annotation language the annotation language comprising a typed structure of metadata related to the first entity the second entity and the elements and cause the database engine to return a query result to the query engine based upon the annotation language.

In various embodiments the processor is further configured to reflect at runtime on the annotation language.

In various embodiments the annotation language is a chain of successively included annotation language.

In various embodiments the annotation language includes metadata on types entities and elements in data model definitions of the ERM.

The following detailed description and accompanying drawings provide a better understanding of the nature and advantages of various embodiments.

Described herein are techniques for annotating language extensions of a relational model based database language e.g. Structured Query Language known as SQL to accommodate higher level entity relationship models. In the following description for purposes of explanation numerous examples and specific details are set forth in order to provide a thorough understanding of the present invention. It will be evident however to one skilled in the art that the present invention as defined by the claims may include some or all of the features in these examples alone or in combination with other features described below and may further include modifications and equivalents of the features and concepts described herein.

A lower layer of the database system comprises calculation logic that is designed to interact with the data itself. Such calculation logic may be performed by various engines e.g. SQL engine calculation engine SQL script in order to provide basic data definition and processing based on the relational model. Such basic data definition can include defining of data types making up the database associated metadata and the database structure e.g. columns tables . The lower layer of the database system may include SQL script as well as data structures such as tables views and calculation views .

The embodiment presented in shows HANA the in memory database available from SAP AG of Walldorf Germany implemented as the database. However embodiments are not limited to use with this particular database. Examples of other in memory databases include but are not limited to the SYBASE IQ database also available from SAP AG the Microsoft Embedded SQL for C ESQL C database available from Microsoft Corp. of Redmond Wash. the Exalytics In Memory database available from Oracle Corp. of Redwood Shores Calif. etc.

Further while the embodiment presented in shows the database as comprising an in memory database various embodiments could be employed in conjunction with conventional disk based database systems.

An application layer overlying the calculation logic of the database system comprises control flow logic . The control flow logic may be implemented utilizing River Definition Language RDL and JavaScript JS to reference model concepts such as entities and relationships that are not reflected in basic SQL. This control flow logic may further comprise common languages for defining and consuming data across different containers e.g. native ABAP Java .

As shown in in order to facilitate the sharing of information across such different containers and thereby promote a more unified environment the database system may further comprise a Core Data Services CDS component . CDS component comprises a common set of domain specific languages DSL and services. The CDS component may allow defining and consuming semantically rich data models as an integral part of the database structure thereby permitting data modeling as well as the retrieval and processing of data to be raised to a higher semantic level that is closer to the conceptual thinking of domain experts. The role of the CDS component is discussed in detail further below.

In particular the CDS component implements higher level Domain Specific Languages DSLs and services based on an entity relationship model ERM . The Data Definition Language DDL is used for defining semantically rich data models including the data types associated metadata and database organization e.g. columns and tables . As mentioned throughout according to embodiments the DDL may be extended to further enrich these data models through the use of entities and annotations.

The Query Language QL is used to conveniently and efficiently read data based on data models. It is also used to define views within data models. The role of the QL and its relation to the DDL is further illustrated in connection with .

The Expression Language EL is used to specify calculated fields default values constraints etc. within queries. Calculated fields default values and constraints may be specified as well as for elements in data models.

Other elements of the CDS component can include Data Manipulation Language DML and a Data Control Language DCL both of which may be used to control access to data.

Embodiments as described herein may distinguish between the domain specific languages DDL QL and EL as members of a language family. This approach fosters considerations such as modular design incremental implementation and reuse. is a simplified view illustrating relationships between these language family members. A consistent language experience across the members of the family of can be achieved by ensuring the languages follow a common style. This can extend to the host programming language with expressions in DDL QL and EL code adopting the same syntax. Utilization of application level domain language s as has been described above can offer certain benefits. One possible benefit is that the application domain level language can avoid the use of inefficient and error prone code.

Under some circumstances it may be desired to write a query statement as follows SELECT id name homeAddress.zipCode FROM Employee WHERE . . . .

Within that sample snippet path expressions along relationships are used to fetch data from an associated entity. In the simple data model above the above query statement is equivalent to the following standard SQL statement 

This statement however may already be too complex for many application developers. Thus code patterns similar to that given below may be used in some pseudo languages 

There are several issues with the code presented immediately above. One issue is the use of an imperative coding style with loops in loops resulting in 1 n queries being executed or too much data being fetched with a SELECT statement.

The above code represents only a relatively simple case. A more complex case is found in the following example 

The preceding cases illustrate the importance of increasing expressiveness of the languages used in application development here the query language . This allows the intent of application developers to be captured rather than being buried under substantial volumes of imperative boilerplate coding.

Such expressiveness is in turn is fundamental to having optimizations applied by the query engine in a manner analogous to functional programming vs. imperative programming . This can affect system characteristics such as its overall performance and scalability. Further a language s ability to allow developers to draft concise and comprehensive code can increase developer productivity. It can also reduce the risk of mistakes and also enhance readability and thus increase the maintainability of the code.

In order to write concise and readable query statements it is desirable to enrich the data definitions with sufficient metadata e.g. about associations semantic types etc. . Accordingly embodiments seek to extend the DDL to define data definitions with sufficient metadata and seek to extend the QL to leverage such definitions.

DDL and QL are declarative domain specific languages providing developers with concise ways to express their models and queries. Certain concepts may originate from entity relationship modeling ERM . By adding native support for such concepts in the underlying engine of the database embodiments avoid the impedance mismatch induced by the translation of conceptual models based on ERM into implementations based upon a plain relational model. In particular writing concise and comprehensive code reduces risks of mistakes and increases readability and maintainability.

Moreover as the concepts of entity relationship models may lie at the core of many higher level models embodiments are able to capture the semantics of other data models e.g. RDL based data models and share those semantics with database modelers and or ABAP of SAP AG or Java consumers. This reduces fragmentation and the loss of semantics. In addition since ERM is also the chosen basis for technologies like OData EDM embodiments can facilitate mapping entities and views to OData entity sets.

Embodiments may employ a functional approach that is based on standard SQL. In particular the comprehensive domain specific nature of DDL and QL allows capturing the intent of application developers thus avoiding a lack of clarity regarding that intent which can result from large volumes of imperative boilerplate coding. This follows the principles of functional programming and is important for optimizations.

The functional approach may be inherited from SQL. A SQL SELECT statement declares which sub set of an overall data model is of interest as projections and selections. It may be left to the query engine to determine optimal execution including parallelizing as appropriate.

In contrast with imperative object traversing patterns embodiments can speed up many data retrieval use cases. While many of those retrieval cases are not individually expensive the cumulative impact of this streamlining can have significant impacts on scalability as it affects all requests over long periods of time.

Embodiments address some of the complexity offered by standard SQL to typical application developers by raising the basis of SQL from plain relational models to the level of conceptual models. This is done by providing native support for ERM in the database system. In this manner the use of SQL may be reestablished for most application developers not only for those with the SQL expertise for specific optimization tasks.

Embodiments employ associations in DDL. Specifically the DDL allows definition of data models as entity relationship models on a semantically rich level that is close to actual conceptual thought. To achieve this over the conventional relational model of standard SQL certain concepts are captured by the embodiments described herein.

Another concept underlying entities as described herein involves employing associations on a conceptual level. This approach contrasts with the conventional use of hand managed foreign keys. Associations define relationships between entities and are specified by adding an element with an association type to a source entity that points to a target entity . As shown in the the relationship implemented by the association type between source entity type and the target entity type reflects the actual relationship between entities in the overlying ERM model . Using the type definition associations may capture metadata about relationships present in the ERM in a reflectable way. According to such a reflectable characteristic a consuming portion of code receiving a piece of data from the database can get back to the type information i.e. metadata provided for the respective elements in the data model.

The association may be complemented by optional further information e.g. regarding cardinality which keys to use additional filter conditions etc. up to a complete JOIN condition. According to embodiments the clause based syntax style of standard SQL may be adopted for specifying the various parameters without sacrificing readability.

In addition the extended DDL works with custom defined Types instead of being limited to primitive types only. The extended DDL may also add other enhancements such as annotations to enrich the data models with additional metadata constraints or calculated fields.

In a second step a database engine is provided in communication with a database utilizing a language describing the relational model. In a third step an application is provided comprising an entity relationship model ERM including a first entity a second entity and a relationship between the first entity and the second entity.

In a fourth step a query engine of the application communicates a query to the database engine utilizing a language extension providing the entity and relationship components of the ERM. The language extension may comprise a first structured entity type including a first key and indicating the first entity a second structured entity type including a second key and indicating the second entity and a third structured association type reflecting the relationship. The association type may be complemented with further additional information.

In a fifth step the database engine returns a query result to the query engine based upon the language extension.

Some examples of extension of the SQL database language to provide entities and associations of ERMs are now given below.

For specifying syntax embodiments may use a derivate of the Backus Naur Form BNF family of metasyntax notations used to express a context free grammar and which can be relied upon to make a formal description of a computer language. The basic constructs may be summarized as follows 

Syntax for SQL extended to include entities and associations as described herein may be described as follows 

From DDL perspective association is a new primitive type that is specified with the type name Association followed by several parameter clauses to specify requisite metadata. These parameter clauses are as follows 

Cardinality allows specifying the relationship s cardinality in the form of min . . . max with max denoting infinity and as a shorthand for 0 . . . . As a default if omitted 0 . . . 1 is used as the default cardinality. An example is 

To targetEntity specifies the association s target entity. A qualified name is expected referring to another entity incl. views . Specifying the target is mandatory there is no default.

foreignKeys allows specifying a combination of alternative key elements in the target entity to be used to establish the foreign key relationship. Where a key element is in a substructure on the target side an alias name is to be specified. Further details are provided below regarding associations represented as foreign key relationships.

Another parameter clause is VIA backlink reverseKeys. For 1 m associations it is mandatory to specify target elements which are expected to be a key combination matching the source s primary keys or an association referring to the source entity. An example is 

Another parameter clause is VIA entity entityName. For m m associations it is mandatory to specify a link table s entity name. That name can either refer to a defined entity or a new entity will be created as follows 

If the data model contains an explicit definition of the link table entity that entity must adhere to the template shown above. It can in addition add other elements. An example is given below 

The WHERE filterClause allows specifying additional filter conditions that are to be combined with the JOIN conditions. This can be especially relevant in combination with VIA backlink or entity clauses. Depending on the filterCondition this can reduce a base m relationship to one with a 1 cardinality. An example is given below 

The ON filterClause allows fully specifying an arbitrary join condition which can be any standard SQL filter expression. Using this option results in the respective association being user managed. That is no foreign key elements fields are created automatically. The developer is expected to explicitly manage the foreign key elements including filling them with appropriate foreign key values in write scenarios. An example is given below 

Element names showing up in VIA WHERE and ON clauses are resolved within the scope of the target entity s type structure. Siblings can be referred to by prefixing an element with a . . Elements from the scope above can be referred to by prefixing an element with . . . etc.

In addition the outer entity s top level scope can be referred through the pseudo variable this which is described further below in connection with Pseudo Variables in QL.

According to embodiments associations are represented as foreign key relationships. In the relational model associations are mapped to foreign key relationships. The foreign key elements are usually created automatically as described in the following sections. In particular an element with association type is represented as a nested structure type containing foreign key elements corresponding to the target entity s primary key elements i.e. having the same names and types. The following are examples of definitions which may be given 

In this example the association elements would implicitly be defined with a nested structure type containing foreign key elements in the 1 cases plus additional metadata about the association as follows 

Following the rules for mapping structured types to the relational model as specified above the underlying table would be created 

Rules for representing associations in the persistence model may apply as indicated in the table below 

Consistent with the approach in SQL no plausibility checks are enforced e.g. checking whether target key elements specified in foreignKeys fulfill the uniqueness requirements . Also no implicit referential integrity checks are enforced at runtime.

According to embodiments associations may be in custom defined types. As associations are special types they can principally be defined not only for elements in entity definitions but in type definitions in general. For example the following definition of the association Amount.currency is valid DDL content 

An actual relationship between entities is established when using the type Amount for an element within an entity definition as in 

The code shown above essentially indicates that the entity Employee has two associations one association is to Address and another association is to Currency within its salary element.

Associations in custom defined types may only be supported for a simple to one relationship with a foreign key on the source side. That is associations with via backlink or via entity clauses may not be supported for elements in custom defined types.

Resolving associations or compositions with l m cardinality using path expressions or nested projection clauses with the flattening operator . in place results in flat result sets with duplicate entries for the 1 side which is in line with standard SQL JOINs and the relational model.

As examples in the following queries addresses refers to an association with to many cardinality 0 . . . 

The result sets for the example queries above are shown below each with the same value for name repeated duplicated for each found entry on the m Address side 

Embodiments also allow the return of Deep Result Sets. Specifically in addition to the standard flattening behavior the introduction of nested projection clauses and structured result sets principally allows expression of deep queries along m associations. These deep queries return real deep result sets having the l sides elements on a top level with nested tables sets for the m sides.

Such deep querying may provide certain benefits. One possible benefit is to allow retrieving larger structures through a single query.

Currently in the absence of deep querying such larger structures may frequently be obtained in a brute force approach through 1 n queries with n being the number of records returned by a 1 side query. This is detrimental to performance particularly if such a query spans several levels of to many associations.

While the other extensions can be realized by translating to standard SQL queries this one requires adding special support deep within the query engine. The absence of such support may preclude using to many associations in the non flattened way. This is discussed further below in the associations of FROM clauses regarding how association trees can be traversed.

Associations can arise not only in projection clauses but also in filter conditions in WHERE clauses. Respective comparison operators may be enhanced to support associations as depicted in the following examples 

Several issues arising within the examples immediately above may be worthy of note. In connection with 

ad 1 2 A record literal can be passed to a comparison with an association with elements that match the combination of the foreign keys.

ad 3 Support for Association type in QL includes automatic coercions of typed scalars or string representations thereof to single key associations.

The above provides just a few examples to give the idea. In general every condition that is possible with standard SQL expressions shall be possible to do with associations as well including sub queries with exists and not exists etc.

Embodiments may also allow associations in FROM clauses. Specifically host languages may provide support for representing associations as typed variables or elements. This is described below in connection with association types in host languages.

Accordingly one can traverse along associations as shown in the following examples in some pseudo language 

The expression this can be used. The comparison this can be retrieve an entity by a given association. The pseudo variable this is always an alias for the entity given in the FROM clause. Therefore the statement above actually resolves to 

The comparison this compares a queried entity with a given association the association must be of type Association to . . . . This expands to a WHERE clause corresponding to the ON condition resolved from the association. In this case it would actually resolve to 

Embodiments may also allow the use of SELECT from association. Specifically association traversal code patterns like the one below are frequently seen 

An association in general and a programming language variable with association type support in particular carries all information about a target record essentially providing information as to which entity goes with which key. Thus equivalent to the query above embodiments allow the shorthand below for traversing associations 

Here signifies the metadata associated with the association corresponding to the target entity specified in the association s declaration using the ON targetEntity clause.

Embodiments allow JOINs to declare ad hoc associations. In the case of a missing association the standard JOIN ON clauses as introduced in SQL 92 are still supported which align with the extensions introduced above as they naturally introduce associations in an ad hoc fashion.

For example in the data model given above the entity Employee has an association homeAddress but is lacking a similar association for businessAddress which can be compensated for using a standard JOIN clause as follows 

JOIN clauses fit easily into the extensions in DDL and QL. JOIN clauses can be interpreted as an ad hoc definition of missing associations.

In the example immediately above the association businessAddress is added. This result is recognized if the projection clause of the example above is compared to that of the query applied to the domain model if the association were in place below 

Embodiments also allow the use of simplified JOIN clauses. In particular following the observation that JOINs essentially declare ad hoc associations embodiments JOINs to be declared using the same clauses that are used to declare associations in DDL. Given this the above example can be written more easily as follows 

The DDL supports annotations to enrich the data models with additional metadata. Annotations are declared as typed structures of metadata. Instances of the annotations can be assigned to entities and elements of a data model. In various embodiments annotations are used to enrich types entities and elements in data model definitions.

Users and clients such as user interface UI frameworks open data OData consumption layers and analytics tools can define their own extension metadata and store them in place with an application s data model. At runtime a user can reflect on the metadata including the annotations using a reflection program reflection engine or reflection application programming interface API . In some embodiments AL includes a set of predefined annotations.

In some embodiments the enrichment of annotations may allow OData resources to be fully defined by view building plus OData specific annotations solely with the combination of DDL and annotations.

Annotations are also very beneficial in the convergence of online transaction processing OLTP and online analytic processing OLAP . By annotating data models with information specific to analytical engines or clients redundant remodeling of the same things to add the requisite delta information may be avoided. Moreover a single view may be supported by expressing analytical views with annotated DDL plus QL syntax. Stated differently annotations give frameworks or consumers a technique to enrich data models with additional metadata without introducing new models and thereby redundantly repeat type structures just for adding a few additional metadata or more as desired. In particular this allows convergence of data models from transactional and analytical systems.

Annotations are typed records of metadata. According to embodiments new annotations may be introduced by defining a new structured type that is introduced with the keyword annotation instead of the keyword entity.

From the perspective of the DDL U Annotation is a primitive type that is specified with the type name Annotation followed by several parameter clauses to specify requisite metadata.

Cardinality allows adding cardinalities to type specifications in the form of min . . . max with max denoting infinity and as a shorthand for 0 . . . . In some embodiments cardinalities distinguish scalars from arrayed types with additional metadata to be used for constraint checks. As a default if omitted 0 . . . 1 is used as the default cardinality. In some embodiments a cardinality greater than 1 implies that the type is an arrayed type with the base type used for its entries.

In some embodiments the expression specified for default or a constant element in annotation is restricted to an expression that can be resolved at compilation time such as reference to literals and identifiers resolving data that can be computed during compilation.

In general any user may introduce new annotations. In some embodiments usage of annotation is limited to only selected cases controlled by a system administrator.

According to embodiments a defined annotation type can be used to annotate types entities and views and individual elements therein. Annotating an object or element is viewed as creating a literal instance of the annotation type and assigning this instance to the annotated object or element.

An example syntax for DDL enhancements for pre annotations and post annotations within the DDL is as follows 

An example syntax for DDL enhancements for annotating types entities and elements within the DDL is as follows 

An example syntax for DDL enhancements for annotating parameters in view definitions in the DDL is as follows 

An example syntax for DDL QL enhancements for annotating elements in view definitions not for queries in general may be as follows 

According to embodiments annotations can generally put in before the annotated definition e.g. a type entity view or element therein. In addition annotation for elements in a structured type or an entity definition may also appear within the element definition immediately before the delimiter e.g. in case of type and entity definitions and in case of a query elements in view definitions except the last one . Suffixed annotations start with a followed by a 

The elements in the syntax include typeName and assignedValue. The element typeName specifies the name of a defined annotation type. The element element specifies a defined element of the annotation type.

The element assignedValue specifies a value to assign to the element. The value is an expression with the same restriction as described above for cardinality default values and derived elements for annotation.

The elements element specifies values for element assignments. Annotation records can be filled by specifying values for all elements or only for selected ones. If only one element is to be specified an element Record.element value can be used which also may be used for element paths through nested record types.

The element literal are specified based on their parameter values. In some embodiments the options for automatic coercion pass single records or scalar values to elements with array type i.e. with cardinality 1 .

As described above annotations can be defined to annotate certain constructs within a data model e.g. types entities views or elements thereof. In some embodiments if annotations are used in a way that violates this restriction parsing fails.

According to embodiments the restriction is defined by the annotation Scope as shown in the following example 

If an annotation is not annotated with Scope or if the scope is defined as ANY the annotation is not restricted to any specific construct. The annotation Scope may be a predefined annotation.

Annotations are structured types with metadata . Annotating an object or element is viewed as creating a literal instance of the annotation type and assigning this instance shown as assignment to the annotated object or element . Object and element correspond to an object and element respectively in the relational model.

Annotations may capture metadata about relationships present in the ERM model in a reflectable way. At runtime a user can reflect on the metadata including the annotations using a reflection program reflection engine or reflection application programming interface API .

In a second step a database engine is provided in communication with a database utilizing a language describing the data model. For example the language may be a domain specific language such as SQL. In a third step an annotation of the data model is provided. The annotation may comprise metadata. Instances of the annotations can be assigned to entities and elements of a data model. In various embodiments annotations are used to enrich types entities and elements in data model definitions.

In a fourth step a reflection engine is provided to examine the data model at runtime. In a fifth step the reflection engine reflects on the data model and the annotations. The reflection engine may examine the metadata of the data model and the annotations.

In a second step a database engine is provided in communication with a database utilizing a language describing the relational model. For example the language may be a domain specific language such as SQL. In a third step an application is provided comprising an entity relationship model ERM including a first entity a second entity and a relationship between the first entity and the second entity.

In a fourth step a query engine of the application communicates a query to the database engine utilizing annotation language. The query may include a standard query based on the relational model and the annotation language.

In a fifth step the database engine returns a query result to the query engine based upon the annotation language.

An example system is illustrated in . Computer system includes a bus or other communication mechanism for communicating information and a processor coupled with bus for processing information. Computer system also includes a memory coupled to bus for storing information and instructions to be executed by processor including information and instructions for performing the techniques described above for example. This memory may also be used for storing variables or other intermediate information during execution of instructions to be executed by processor . Possible implementations of this memory may be but are not limited to random access memory RAM read only memory ROM or both. A storage device is also provided for storing information and instructions. Common forms of storage devices include for example a hard drive a magnetic disk an optical disk a CD ROM a DVD a flash memory a USB memory card or any other medium from which a computer can read. Storage device may include source code binary code or software files for performing the techniques above for example. Storage device and memory are both examples of computer readable mediums.

Computer system may be coupled via bus to a display such as a cathode ray tube CRT or liquid crystal display LCD for displaying information to a computer user. An input device such as a keyboard and or mouse is coupled to bus for communicating information and command selections from the user to processor . The combination of these components allows the user to communicate with the system. In some systems bus may be divided into multiple specialized buses.

Computer system also includes a network interface coupled with bus . Network interface may provide two way data communication between computer system and the local network . The network interface may be a digital subscriber line DSL or a modem to provide data communication connection over a telephone line for example. Another example of the network interface is a local area network LAN card to provide a data communication connection to a compatible LAN. Wireless links are another example. In any such implementation network interface sends and receives electrical electromagnetic or optical signals that carry digital data streams representing various types of information.

Computer system can send and receive information including messages or other interface actions through the network interface across a local network an Intranet or the Internet . For a local network computer system may communicate with a plurality of other computer machines such as server . Accordingly computer system and server computer systems represented by server may form a cloud computing network which may be programmed with processes described herein. In the Internet example software components or services may reside on multiple different computer systems or servers across the network. The processes described above may be implemented on one or more servers for example. A server may transmit actions or messages from one component through Internet local network and network interface to a component on computer system . The software components and processes described above may be implemented on any computer system and send and or receive information across a network for example.

The above description illustrates various embodiments of the present invention along with examples of how aspects of the present invention may be implemented. The above examples and embodiments should not be deemed to be the only embodiments and are presented to illustrate the flexibility and advantages of the present invention as defined by the following claims. Based on the above disclosure and the following claims other arrangements embodiments implementations and equivalents will be evident to those skilled in the art and may be employed without departing from the spirit and scope of the invention as defined by the claims.

