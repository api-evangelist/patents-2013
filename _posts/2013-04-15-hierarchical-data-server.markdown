---

title: Hierarchical data server
abstract: A hierarchical data server provides a query and storage system for hierarchical data with three interfaces that are, data interface for accepting hierarchical data, query interface for accepting a query, and result interface for returning output of the query. The system models hierarchical data with one data object called data vine and one data structure type called data vine list. A data vine includes a name, a property list, and a child list. A data vine list is an ordered list of data vines. A data vine is recursively defined with its child list as a data vine list. The system introduces five basic operators, cast, restrict, unique, sort, and traverse. Each operator acts on one data vine list and returns another data vine list. A property list in a data vine is unordered with set operations implemented, which include default operation, update operation, elimination operation, replacement operation, and intersection operation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09218393&OS=09218393&RS=09218393
owner: 
number: 09218393
owner_city: Elmhurst
owner_country: US
publication_date: 20130415
---
This invention relates to a query system for searching database based upon SGML. The invention is a query system designed for working on hierarchical structures. It provides queries with operators and operations to retrieve and modify any element in a hierarchical structure. To construct a result the query language in the invention binds on one hierarchical data source or multiple hierarchical data sources for adopting some child structures getting prototype of a desired part and cascading with property data inside.

Many hierarchical data formats became the standards of technologies including SGML Standard Generalized Markup Language HTML Hyper Text Markup Language and XML Extensible Markup Language . Among them SGML is the most basic one. The rest are its derivatives. The HTML 4 is considered to be an application of SGML and XML is considered to be a subset of SGML. Many query languages have been disclosed for the purpose of extracting and modifying SGML data. These published data query systems or prior arts adopt SQL like languages. Some of them use FLWOR expressions FOR LET WHERE ORDERED BY RETURN and others use constructs like SELECT WHERE similar to SQL. However SQL is dealing with relational databases that are not hierarchically structured and actually are of one single level structured. This innate scope makes SQL Like query languages less constructible than a query language that is directly defined on hierarchal structures of multiple levels. The invention is directly defined on and designed on hierarchical structures. It is a complement to the approach in all of the related arts. The major techniques in the query language of the invention are the use of CRUST operators that are cast operator restrict operator unique operator sort operator and traverse operator.

U.S. Patent Application Publication No. 2007 0219959 A1 by Kanemasa and published on Sep. 20 2007 describes a query language for XML named XML QL which has a SELECT WHERE construct similar to SQL and borrows features of various query languages for semi constructed data. Kanemasa does not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data according to the claimed invention.

U.S. Pat. No. 6 665 677 B1 issued to Wotring on Dec. 13 2003 allows data to be transformed from a relational database to a hierarchical database. Wotring does not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data according to the claimed invention.

J. Jaakkola and P. Kilpel inen Using sgrep for querying structured text files 1996 Espoo Finland Oct. 4 5 1996 implement an algebra of unrestricted text fragments called regions. The algebra allows the retrieval of document components represented as regions based on conditions on their relative containment and ordering. J. Jaakkola and P. Kilpel inen do not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data.

J. Le Maitre E. Murisasco M. Rolbert SgmIQL a language for querying SGML documents 4th Lisbon Portugal Jul. 2 4 1996 present a complete SGML query language based on SQL like expressions. The language uses pattern matching primitives which are integrated into common operators such as SELECT FROM WHERE. J. Le Maitre E. Murisasco and M. Rolbert do not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data.

S. Abiteboul D. Quass J. McHugh J. Widom J. L. Wiener The Lorel query language for semistructured data International Journal on Digital Libraries Volume 1 Number 1 68 88 1997 present a query language called the Lorel language for querying semi structured data. Lorel language is written in the SQL OQL style for querying data. For wide applicability the simple object model underlying Lorel can be viewed as an extension of the ODMG data model and the Lorel language as an extension of OQL. Abiteboul et al. do not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data.

K. Lee Y. K. Lee P. B. Berra Management of Multi structured HypermediaDocuments A Data Model Query Language and Indexing Scheme Volume 4 Number 2 199 223 1997 propose an object oriented model for multi structured hypermedia documents by using unique element identifiers and an indexing schema. K. Lee Y. K. Lee P. B. Berra do not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data.

A. Duetsch M. Fernandez D. Florescu A. Levy D. Suciu XML QL A Query Language for XML 19 Aug. 1998 introduce the XML which is SQL like and adopts FLWOR expressions FOR LET WHERE ORDERED BY RETURN . A. Duetsch M. Fernandez D. Florescu A. Levy D. Suciu do not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data.

N. Fuhr and K. Grobjohann XIRQL a query language for information retrieval in XML documents SIGIR 01 Proceedings of the 24th annual international ACM SIGIR conference on Research and development in information retrieval add the features of weighting and ranking to XML and provide related query optimization. N. Fuhr and K. Grobjohann do not suggest use of the CRUST operators on hierarchical structures or set operations on property lists to retrieve and construct SGML data.

According to an aspect of the present disclosure a dedicated storage system is provided with a query language. The storage system stores hierarchical databases particularly for data based upon SGML. The query language is for searching and modifying persistent data in the storage. The query language of the invention suggests a logic view on hierarchical data with a data object called data vine together with a data structure type called data vine list that is an ordered list of data vines. Data vine and data vine list are recursively defined in an alternating way that the child list in a data vine is a data vine list and each member of a data vine list is a data vine. This mechanism helps to reach any element on hierarchical data up to certain high order and volume that a system can accommodate. The invention facilitates drilling on hierarchical data sources to extract and or construct hierarchical data by working on data vine lists with the CRUST operators Cast operator Restrict operator Unique operator Sort operator Travers operator .

A data vine is stored in the server in Prolog codes specifically defined in the format of a predicate name with four parameters. The first parameter is a reference to the parent element the second parameter is a tag name or text in SGML the third parameter is a list of properties and the fourth parameter is a reference to the child list.

A query can be used to build knowledge leads for quick accesses to hierarchical data. A knowledge lead is a hierarchical structure building on the original hierarchical data. Queries can be based upon the original data source as well as the build up knowledge leads. Well designed knowledge leads by users could form a part of intelligence on the original hierarchical data source and make an application more useful.

The invention supports the current standards and technologies based upon SGML. By its hierarchical nature it could be adjusted with very few modifications and fully complied with new releases of the standards in the future. The invention provides an easy access and persistent storage for hierarchical data. The user interface of the invention is a simple query language. By submitting a query the stored data can be retrieved updated and modified in anyway. With a password or a few lines of verification in queries the data security can be improved. Although the query language does not have the same power as a subscripting language however it could enhance the management and utilization of subscripting languages by applying modularization on the subscripting source codes and processing the modularized as hierarchical data. All these features are available because the invention adopts a different way to the process holding the whole data in hierarchical structures and casting out what are needed. It is a complement to the current approach of document subscripting model.

The invention is a stand alone software program which stores retrieves modifies and updates hierarchical data in SGML format. The usage of the invention covers all SGML derivatives.

part 1 a data server which resides in a computer holds hierarchical data and facilitates query services 

part 2 a data input interface which provides a channel to an authorized user to store data in the server 

The invention works in a query model. Its administrator stores a computer readable data package in the server that resides in a computer. The data package gets into the server through the data input interface. The data package could be an SGML document or a part of such document in well formed format or multiple SGML documents or a combination of these mentioned.

To utilize the data in the package a user or a computer program submits a query in the query language in part 5. The submitting can be done through LAN WAN or Internet to the server via part 3. Once the server receives the query a corresponding result is returned to the submitter via part 4. A query is a hierarchical structure written in the query language which is actually the prototype of the query result. Depending on what a query is asking for the result of the query could be an SGML document or a part of SGML document. The server in part 1 may return an empty string if no suitable result is found or an error is contained in the query.

The query language of part 5 is used to process stored data in SGML format. It is a declarative language.

qualified name which is a string starting with a lower case letter from a to z followed by letters of a to z A to Z the underscore   digits from 0 to 9 

The query language defines a property as a pair of property name which is a qualified name and property value which is a double quote. The query language defines a property list as a group of properties.

For writing a query in a logic way the query language suggests a data object called data vine that includes a name of qualified name a property list and a data structure called data vine list. Both data vine and data vine list are logic views to use with CRUST operators in order to formulate a query.

Angle tags in SGML are allowed in the query language to form hierarchical structures. An angle element in SGML represents a data vine in the query language. A tag name in SGML represents a data vine list in the query language. The traditional child operator of one slash sign descendent operator of two slash signs and property value operator of one commercial at sign are accepted by the query language of the invention. A child operator returns a data vine list of one level down on the path in which each member has the same parent name that is the one before the operator sign and the same child name that is the one after the operator sign . A descendent operator returns a data vine list of multiple levels down on the path in which each member has the same parent name that is the one before the operator sign and the same child name that is the one after the operator sign . A property value operator returns the property value belonging to the property name that is the one after the operator sign .

The query language in the invention provides five right unary operators that are the cast operator the restrict operator the unique operator the sort operator and the traverse operator. An operator acts on a data vine list and return another data vine list. In a query each operator is prefix with one exclamation point and postfix with parameters in parentheses.

The cast operator has two modes. The first mode is castall and the second mode is castnone. Both modes of cast operator open the navigating data vine and act with iterations on the members inside. The operator castAll extracts all members inside and includes all of them in the result list. The castNone operator only iterates all members inside without including anyone of them in the result list instead providing a change for alteration. A cast operator has parameters that can add more members into the result or remove any existing member from the result.

A restrict operator acts on a data vine list and only extracts those restricted members inside. A parameter could be one of the following where N X and Y are positive integers 

between X and Y which allows all members of index numbers greater than X and less than Y in the result 

A unique operator acts on a data vine list and extracts one for each satisfaction with the given condition of uniqueness. In case that duplicated ones are found only the first one is selected. A unique operator has only one parameter that is a descendent name and no path operator is needed in the parameter.

A sort operator sorts the data vine list according to the given sorting conditions. Parameters of a sort operator could be one the following. The first parameter sortFlag is a sorting flag. Its value can be 1 for sensitive ascending 2 for sensitive descending 3 for insensitive ascending and 4 for insensitive descending. The flag could be omitted and the default value is 1 of sensitive ascending. The second parameter can be one of tagName tagName tagName tagName attributeName tagName attributeName MagName attributeName and attributeName.

A traverse operator acts on a data vine list yields a spanning tree. The result collects those on the backward traverse path on the tree according to the given condition in parameters. A traverse operator and its parameter could be one of the following. In the notation here tagName1 and tagName2 represent tag names value1 and aValue2 represent values.

The query language in the invention provides five property operations default and among property lists. If S is the property list of the current data vine P is a property list as propert1 propert2 . . . propertyN where each property is a pair of property name and property value and N is a positive integer the following operations are between S and P. S is not showing in the expression because S represents the current existing property list of the action.

P is the default operation on S. P completely replaces S and becomes the property list of the current data vine.

 P is the update operation on S. A property in P will replace a property in S if these two properties share the same name otherwise this property will join S and become a new property of S.

 P is the elimination operation on S. A property in S will be removed if it has the same name and the same value with a property in P.

 P is the replacement operation on S. A property in P will replace a property in S if these two properties share the same name otherwise no action is taken.

 P is the intersection operation on S. Any property in S must be exactly the same as some property in P otherwise it will be dropped from the result.

If  DVL is a data vine list and each member in  DVL has a number as value the aggregation functions on  DVL are defined below.

Average function is defined as avg  DVL which is the average number of all data vine values from  DVL.

Minimum function is defined as min  DVL which is the minimum number of all data vine values from  DVL.

Maximum function is defined as max  DVL which is the maximum number of all data vine values from  DVL.

The query language in the invention provides criterion functions. In the following criterion functions AA is a data vine list and BB is either a number or a double quote. A criterion function returns a value of logic true or false. In case BB is a data vine list the first member of BB is used.

The equal function is expressed as the equal sign . The expression AA BB will be evaluated to true if each member in AA has the same value as BB.

The greater than function is expressed as the word isGT . The expression AA isGT BB will be evaluated to true if each member in AA has the value greater than BB.

The greater than or equal to function is expressed as the word isGTE . The expression AA isGTE BB will be evaluated to true if each member in AA has the value greater than or equal to BB.

The less than function is expressed as the word isLT . The expression AA isLT BB will be evaluated to true if each member in AA has the value less than BB.

The less than or equal to function is expressed as the word isLTE . The expression AA isLTE BB will be evaluated to true if each member in AA has the value less than or equal to BB.

The query language in the invention provides conditional statements if then and if then else that accommodate data vine lists.

All delimiters of SGML including starting tags ending tags single tags tag names and attribute names are legal terms in the query language and can be used in a query directly as native terms without any other signs. A tag element in SGML is assigned to a logic view of a data vine. A tag name in SGML is assigned to a logic view of a data vine list. The attribute name and value are assigned to logic views of property name and value respectively.

Further features and aspects of the present disclosure will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the disclosure will be described in detail below with reference to the drawings.

The invention provides a dedicated server program that facilitates persistent storage. A database administrator loads hierarchical data into server. A user submits a query based on the loaded hierarchical data. A query accepts SGML angle notations. Any data in a SGML angle are used directly without quote symbol. Any text between a pair of angle tags of SGML is used in the query language within a pair of double quote symbols. A query result returns a document in SGML or a section of well formed SGML data. A frequently submitted query may be reused to build a knowledge lead that is a new hierarchical structure on the original hierarchical data. Subsequent queries can take this advantage and navigate on the knowledge lead to get a short cut to the desired data.

The invention works in a query model. In this model databases are input via computer readable medium to a server that is a program running in computer a query is submitted to the server via computer readable medium for data request and an answer is returned to the query maker via computer readable medium. The advantage of this model is that data files and file locations are not exposed to query makers. The invention follows this model and extends it in the way that a query is returned either in whole if it succeeds everywhere or nothing if it fails somewhere. The invention provides a self contained query language in which logic programming principles bind on statements of a query. If a query succeeds on each statement then the appropriated result is returned. No incomplete answer is returned and no rollback is needed.

part 1 a data server which resides in a computer holds hierarchical data and facilitates query services 

part 2 a data input interface which provides a channel to a server administrator or an authorized user to store data in the server 

The following contents are SGML data of three books under catalog in SGML. The contents are input to the server via part 2 of the data input interface. The contents are processed and stored in the data server for subsequent queries.

A data vine is stored in the server in Prolog codes specifically defined in the format of a predicate name with four parameters. The first parameter is a reference to the parent data vine the second parameter is a double quote corresponding to a tag name in SGML data the third parameter is a list of properties and the fourth parameter is a reference to the child list. A terminal data vine is a data vine with none as child reference. A tag value in SGML is expressed as a terminal data vine with the value in the second parameter. The above data of three books under catalog are stored with the following Prolog codes in server.

Among the codes for example t39513293834 j48310636322 book cover papercover h24636326765 is a data vine stored in the server. The first parameter j48310636322 is the reference to the parent data vine the second parameter book is the tag name in the SGML data source the third parameter cover papercover is a property list and the fourth parameter h24636326765 is the reference to child vine list.

Among the codes for example h79547784277 h24636326765 2nd edition none is a terminal data vine. The first parameter h24636326765 is the reference to the parent data vine the second parameter 2nd edition is the tag value in the SGML data source the third parameter is an empty list for properties and the fourth parameter is none that indicates being a terminal vine and no more child reference.

Generally a frequently submitted query may be reused to build a knowledge lead that is a new hierarchical structure on the original data. Subsequent queries may take this advantage and navigate on the knowledge lead to get a short cut to the desired data. This feature helps a large scale application.

The following contents are showing a query written with part 5. A query may contain SGML angle notations such as and in below. The query is submitted to server via part 3 of the query interface. In the query the expression of title and edition in SGML angle notation are directly used without any quote symbol to extract corresponding data.

The result of this query is returned via part 4 of the query interface. Because the use of castnone operator the tags of are not included in the result. Only title and edition are included because they are explicitly expressed in the query for extraction. The tags of in the query are used to enclose title and edition in the result.

The query language in the invention suggests a data object called data vine and a data structure type called data vine list. Data vine list is an ordered list of data vines. Data vine and data vine list are logic views to write a query. A data vine is a piece of data with a name that is a string of letters a property list that is a set of pairs and a vine list as its children. Constant data of a number a string a single quote and a double quote are classified as terminal data vine. A terminal data vine has a constant as its name an empty proper list and a null child list. The following content corresponds to a data vine with a name of book a property list of cover papercover and a child list that has 3 data vines as members title edition and author . Among the child list the first member is the data vine with the name title an empty property list and a child list of the only member FOL and PROLOG . In turn the constant FOL and PROLOG is a terminal data vine with the name of itself an empty proper list and a null child list. The same logic views can apply on the second member of data vine edition and the third member of data vine author .

The child operator and the descendent operator are extended to accept a data vine list and return a data vine list. For example catalog is data vine list. The expression catalog book represent another data vine list that all of its members are immediate children of catalog . The expression catalog last is a data vine list that all of its members are descendent of catalog and each with the vine name last . A variable in the query language is used to represent a data vine list. A variable is prefixed with an underscore symbol. The query language uses symbol of to assign a data vine list to a variable. For example  book is a variable and book is a data vine list the assignment is  book book.

The operator castnone is designed to provide a chance for prototyping a data element. The data in are input to the server. In a query similar to the following query is submitted. The variable  Book is assigned to a data vine list to hold the elements of book . Then the castNone operator acts on this list. There are four statements as the parameters of castNone title edition and . The two statements title and edition are the original tag names in the given data set. The castnone operator iterates on the act on data vine list but does not extract anything. These two statements explicitly extract elements of and from the act on data vine list and cast them out in the result.

As in there are nine book elements in the result. The first book and the second book have the same title with different editions. The angle tags of are not from extracting but from the query declaration.

The operator castall is designed to extract a piece of data with hierarchical infrastructure intact. The data in are input to the server. In the castAll operator casts all out including tag with its attributes. There are three statements as the parameters. The statement noshow is used to block casting out anyone under the element but it does not block the casting of the tag . After blocking all elements under the element the statements title and edition are used to explicitly extract elements of and from the act on data vine list and cast them out in the result.

As in there are nine book elements in the result. The castall operator extracts the angle tags of with the attribute in tags. The contents in the angle tags of are also extracted but suppressed by the noshow statement.

The operator restrict is designed to screen out members from the act on data vine list. The data in are input to the server. In book is a data vine list with 9 book elements. The query book restrict 1 3 4 7 only keeps the elements of index 1 3 4 and 7 that includes the result data vine list. Other legal expressions in a restrict operator could be following 

The unique operator is designed to make a given data vine list to be unique up to the given condition in parameters. It acts on the given data vine list and only selects the first item if multiple items satisfy the condition. A single data vine name or a tag name in the parameter is used for operation. No path operator is needed in the parameter. In the query book author is the operant of the unique operator and is a data vine list of 13 members including all elements in . The query is book author unique last which means make it unique up to the last name of the element in . After operation of unique operator on the data vine list of 13 members 9 members with different last names are extracted and remained on the result list.

The sort operator is designed to sort a given data vine list up to conditions in parameters. The operant of sort operator in is the result vine list from which is book author unique last . The query is book author unique last sort last . It sorts the data vine list up to the last names of elements. In case a sorting flag is omitted and the default value of 1 is used for the sorting order of sensitive ascending. The sort operator has more options. The first parameter sortFlag is a sorting flag. Its value can be 1 for sensitive ascending 2 for sensitive descending 3 for insensitive ascending and 4 for insensitive descending. The flag could be omitted and the default value 1 for sensitive ascending is used. The second parameter with a notation of tagName as a data vine name or as a tag name and attributeName as a property or as an attribute name can be written as expressions of tagName tagName tagName tagName attributeName tagName attributeName tagName attributeName and attributeName. The following are legal use of the sort operator although some of them may not cause significant sorting change 

The operator traverse is designed to help a user for data mining on a specific part in databases with one or two values under a tag name or a data vine name. A traverse operator acts on a data vine list that is a hierarchical structure as a tree. The traverse operator picks items in the tree on a backward traverse path according to the given condition in the parameter extracts and collects any member from the operant list if the member has a descendent in the picked up list. In a traverse operator acts on a data vine list of nine elements. The parameter is expressed as from price 12.99 to edition 4th edition . All descendent elements of these nine elements are put into the middle result list in the order of their appearances in . The traverse operator picks elements Price2a Price2b Price2c Book3 Title3 and Edition3 due to the value 12.99 is in Price2a and the value 4th edition is in Edition3 and locates the ancestors of these picked elements in the operant list which are Book2 and Book3 in the result list. A traverse operator and its parameter could be one of the following. In the notation here tagName1 and tagName2 represent tag names and aValue1 and aValue2 represent values.

A property list is a logic view of attributes. In the elements have one or two attributes. In the first starting tag as of the corresponding property list is cover papercover . In the third starting tag as of the corresponding property list is year cover papercover .

The default operation provides a replacement for the entire property list. The query book castall tagTitle title searchDate datenow provides replacements for attributes of all tags in with tagTitle title searchdate datenow by which the first tag becomes and the third tag becomes .

The update operation updates the existing property list. The query book castall year publishingdate searchDate datenow updates the attribute values of the attribute name year and adds the new attribute of name searchDate. The first tag becomes and the third tag becomes .

The elimination operation removes the designated members from the existing property list. The query book castall year removes the attribute of the name year . The first tag becomes and the third tag becomes .

The replacement operation renews the property value only for a property that has the same property name in both property lists of the operation. The query book castall year publishingdate searchDate datenow renews the proper values of the property name year only. The first tag becomes and the third tag becomes .

The intersection operation verifies the existing property list so that a property is kept if it has the same property name in both property lists of the operation. The query book castall year intersects each of property lists of elements with year . The first tag becomes since it does not have attribute of the name year and the third tag becomes .

The query language in the invention provides criterion functions that return a value of true if the criterion is satisfied otherwise it returns false.

The equal function is expressed as the equal sign the left side of is a data vine list A and the right side of is evaluated to a number or a double quote B. The function returns true if all data vines in A evaluate to the value of B.

The greater than function is expressed as the word isGT the left side of isGT is a data vine list A and the right side of isGT is evaluated to a number or a double quote B. The function returns true if one data vine in A has the value greater than B.

The greater than or equal function is expressed as the word isGTE the left side of isGTE is a data vine list A and the right side of isGTE is evaluated to a number or a double quote B. The function returns true if one data vine in A has the value greater than or equal to B.

The less than function is expressed as the word isLT the left side of isLT is a data vine list A and the right side of isLT is evaluated to a number or a double quote B. The function returns true if one data vine in A has the value less than B.

The less than or equal function is expressed as the word isLTE the left side of isLTE is a data vine list A and the right side of isLTE is evaluated to a number or a double quote B. The function returns true if one data vine in A has the value less than or equal to B.

The query language in the invention provides conditional statements if then and if then else that accommodate data vine lists.

the statement if count auth isGT 2 then casts out a single tag for a book with three or more authors.

A path operation of the child operator of one slash and the descendent operator of two slashes is a legal statement

A beginning angle tag and its closing angle tag conforming well formed rules is a legal statement. The angle tags appear pair and must obey the well formed rules. The comma following an angle tag can be omitted.

SGML tags tag names and attribute names in hierarchical databases are embedded in the query language for direct use as legal terms in a query. A tag element is assigned to a logic view of a data vine. A tag name is assigned to a logic view of a data vine list. The attribute name is assigned to a logic view of a property name. In the query of the starting tag and the ending tag with contents in between consolidate an hierarchical element that is assigned to a logic view of data vine price is a tag name in and is assigned to represent a data vine list in which every member has the tag name of price currency is an attribute name in and is assigned to be used as a property name.

the statement avg  X is a aggregation function that returns the average price in US dollars of all books in .

While the present disclosure has been described with reference to exemplary embodiments it is to be understood that the disclosure is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

