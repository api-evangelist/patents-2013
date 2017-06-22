---

title: Computer-implemented method, computer software and apparatus for use in a translation system
abstract: A computer-implemented method for use in natural language translation comprises performing in software processes, the steps of: comparing source material with stored material in a first natural language, said stored material having previously been translated from said first natural language to at least a second natural language, identifying at least a part of said source material which has a relationship with at least a part of said stored material, outputting said identified part of source material and said identified part of stored material in a form suitable for review by a user, and replacing said identified part of source material with said identified part of stored material to assist full translation of said source material from said first natural language to at least said second natural language.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09400786&OS=09400786&RS=09400786
owner: SDL PLC
number: 09400786
owner_city: Maidenhead
owner_country: GB
publication_date: 20130725
---
This nonprovisional utility patent application is a continuation of and claims the priority benefit of U.S. patent application Ser. No. 11 525 231 filed on Sep. 21 2006 entitled Computer Implemented Method Computer Software and Apparatus for Use in a Translation System issued as U.S. Pat. No. 8 521 506 on Aug. 27 2013 which is hereby incorporated by reference in its entirety including all references cited therein.

This invention relates to a computer implemented method computer software and apparatus for use in natural language translation. In particular the invention relates to a computer implemented method computer software and apparatus for improving the consistency of source content creation for use in natural language translation.

Many organisations whose trade extends abroad desire documentation in numerous languages in order to provide the greatest possible coverage in the international marketplace. Modem communication systems such as the Internet and satellite networks span almost every corner of the globe and require ever increasing amounts of high quality natural translation work in order to achieve full understanding between a myriad of different cultures.

As a rule of thumb an expert human translator can translate approximately 300 words per hour although this figure may vary according to the difficulties encountered with a particular language pair. It would take a huge amount of manpower alone to cope with all the global translation needs of modem day life. Clearly some assistance for human translators is needed in order for them to keep up with constantly evolving requirements and updates for countless web pages company brochures government documents and press articles to name but a few areas of application.

With the ability to process vast amounts of information computers naturally lend themselves to tackling the problem by way of machine translation. Various pure machine translators exist which can translate many thousands of words in a matter of seconds but the success rates cannot be guaranteed. A human influence can be used somewhere in the machine translation process to provide the desired level of translation. Bridging the gap between purely human and purely machine translation are machine assisted translation methods where the burden can be shared between a human translator and a computer the human translator in such cases sometimes being referred to as a computational linguist.

It is estimated that currently only a third of current internet users are native English speakers. By 2010 it is expected that this fraction will fall to a quarter so the need to write with international audiences in mind is growing increasingly important. Global organisations should provide communications which are consistent regardless of which market they address or which language they communicate in whether these communications are in the form of technical documentation web pages or marketing collateral. Variations in such communications around the globe could cause confusion or mislead the public which could lead to devaluation of brands or markets.

U.S. Pat. No. 6 047 299 describes a document composition supporting method and system for the support of document editing or translation using an electronic terminology dictionary which is composed such that terms in standard expression and terms in alternative spelling expression corresponding thereto are registered in association with each other. The terminology dictionary is used to search an inputted document for terms in the document matching with terms in standard expression and terms in alternative spelling expression registered in the terminology dictionary. For terminological standardisation of the document the terms in the document matching with the terms in alternative spelling expression inputted in the terminology dictionary are replaced by the corresponding terms in standard expression.

International patent application no. WO 02 29622 A1 describes a dynamic machine editing system incorporating a dynamic rules database. The dynamic database of editing rules helps to automate the editing of already translated documents to better reflect the nuances of language content and meaning and especially the use of nomenclature that is culture and or industry specific. An initial set of editing rules is deployed in the database and used to edit machine translated documents. Manual changes which are subsequently made to the machine edited documents by a human editor are recorded and that data is used to form updates or additions to the initial editing rules.

Japanese patent application no. JP 2005 107597 describes a translation support system that uses an example database to search for examples of matching or similar sentences to an input sentence. A translation server which stores a number of bilingual sentence examples determines the similarity between pre stored and input sentences based on the ratio of words in the stored sentences which match words in the input sentence. The results are then displayed to a translator for selection of a suitable pre stored sentence whereby to assist with translation of the input sentence.

Machine assisted translation methods for example such as described in International patent application WO 2006 016171 A2 filed by the present applicants still require considerable time on the part of the computational linguists involved. Any assistance that can be given to the computational linguists in their work is therefore desirable as this will lead to reductions in associated overall translation costs.

There is thus a need for a quick efficient easy to use and consistent machine assisted natural language translation system which reduces the burden on computational linguists.

In accordance with a first aspect of the present invention there is provided a computer implemented method for use in natural language translation said method comprising performing in software processes the steps of 

comparing source material with stored material in a first natural language said stored material having previously been translated from said first natural language to at least a second natural language 

identifying at least a part of said source material which has a relationship with at least a part of said stored material 

outputting said identified part of source material and said identified part of stored material in a form suitable for review by a user and

replacing said identified part of source material with said identified part of stored material to assist full translation of said source material from said first natural language to at least said second natural language.

Hence by use of the present invention a user i.e. the person currently authoring the source material can be made aware that source material they are currently authoring has some form of relationship with stored material that may have already be translated. The source material that is currently being authored can then be amended according to the stored material. Parts of the source material can be replaced with parts of the stored material which have the same or a similar meaning. Such content re use means that when a full translation of the source material is required the process is simpler and cheaper as some of the source material need not be translated again. The consistency of translation may also be increased in this manner as an author can adapt their authoring to source material that has previously been translated.

If such methods are adopted globally then the cost and consistency benefits may increase accordingly. Adopting such methods early in the content creation process i.e. during authoring of the source material as opposed to later in the process once individual authors have pooled their source materials can increase overall efficiency as the amount of editing can be reduced and content re use reduces the volume of translation required. Such methods also help to maintain consistency of style and terminology across global markets.

Preferably the replacing is carried out in response to input from a user. The user may thus choose to amend the source material they are currently authoring according to the identified stored material. The author may also choose to replace parts of the source material with parts of the stored material which have the same or a similar meaning.

Preferably full translation of said source material from said first natural language to at least said second natural language is conducted with reference to said stored material which has previously been translated into at least said second natural language. Hence full translation of the source material is facilitated as parts of the source material which have previously been translated need not be translated again during full translation of the source material.

The step of conducting full translation of said source material from said first natural language to at least said second natural language may comprise a human translator translating parts of said source material which were not replaced after having been identified as having a relationship with parts of said stored material. Hence parts of source material which have not been previously translated can be translated by a human translator.

Alternatively or in addition the step of conducting full translation of said source material from said first natural language to at least said second natural language may comprise a machine translation process translating parts of said source material which were not replaced after having been identified as having a relationship with parts of said stored material. Hence parts of source material which have not been previously translated can be translated by a machine translation process.

Alternatively or in addition the step of conducting full translation of said source material from said first natural language to at least said second natural language may comprise a machine assisted translation process in which a human translator and a machine translation process are used to translate parts of said source material which were not replaced after having been identified as having a relationship with parts of said stored material. Hence parts of source material which have not been previously translated can be translated by a human translator and a machine translation process.

Preferably a full translation of said source material is output in a form suitable for review by a user. The full translation can thus undergo a review by a user. The user conducting the review of the full translation may be the same person as the human translator or alternatively may be a different person in which case it may undergo transmission over a data communications link.

Preferably the parts of said full translation which were translated with reference to said stored material which had previously been translated into at least said second natural language parts of said full translation which were translated by a human translator and or parts of said full translation which were translated by a machine translation process and or parts of said full translation which were translated by a machine assisted translation process are outputted in different forms for example if different colours can be used for each form. A reviewer is thus able distinguish between parts of the translation which have been translated in different ways and the review process can be made more efficient.

Preferably the at least one translation memory contains a plurality of stored segment pairs each of said stored segment pairs comprising source material in said first natural language and corresponding translation in at least said second natural language. A translation memory is used to store segment pairs which have previously been translated from a first natural language into at least a second natural language. The content of a translation memory can then be re used to facilitate later translations.

Preferably each of the stored segments pairs corresponds to at least one of a paragraph a sentence or a phrase. Hence if a matching or similar paragraph cannot be found in the stored material then a matching or similar sentence may be found. Similarly if a matching or similar sentence cannot be found in the stored material then a matching or similar phrase may be found.

Preferably the source material is divided into a plurality of source segments prior to said comparison of said source material with said stored material. Hence source segments rather than the whole material can be compared with the stored material.

Preferably said plurality of source segments are compared with said stored material in said first natural language from said plurality of stored segments.

Preferably said identified part of source material comprises one or more of said plurality of source segments.

Preferably said source material is processed by dividing it into said source segments where at least one of a full stop an exclamation mark a question mark a colon a semicolon a tab character or a paragraph mark appears in said source material. Hence boundaries between successive segments can be made in the source material where such characters marks appear. Alternatively a user may define characters marks or such like for boundaries between successive segments or may choose the location of the boundaries themselves in the source material.

Preferably said replacement comprises replacing a part of said source material with a part of said preferred terminology material.

The preferred terminology material could for example include terminology that accords to company standards or accepted regional norms or such like. The author can be alerted if parts of the source material they are currently authoring have some form of relationship with preferred terminology material. The source material currently being authored may then be amended according to the preferred terminology material thus helping to increase the consistency of content and or style of the source material with previously approved content. The adoption at the authoring stage of preferred terminology that has previously been translated also has the benefit of reducing the amount of translation required when a full translation of the source material is carried out.

Preferably said replacement comprises replacing a part of said source material with a part of said preferred terminology material.

The list of forbidden terminology could for example include terminology used by competitors or which may cause offence or confusion or damage a company s reputation or brand. The author can be alerted if parts of the source material they are currently authoring have some form of relationship with forbidden terminology material. The forbidden terminology material may thus be replaced with material from the list of preferred terminology at the authoring stage thus helping to increase the consistency of the source material. This also avoids the inefficiency of the forbidden terminology material being unnecessarily translated and then having to be corrected in translated form.

Preferably said method comprises comparing said source material with a set of options. These options may include grammatical options. Alternatively or in addition the options may include stylistic options.

Preferably said replacement comprises replacing a part of said source material according to at least one option from said set of options.

Preferably said set of options comprises at least one of a spelling variant an abbreviation a contraction a compound word punctuation the length of a sentence a commonly misused word unnecessary wording or a combination of specific characters.

Preferably at least one of said options is user configurable. This may involve a user choosing which options are used with the content they are currently creating or a user choosing settings for one or more of the options differently to default settings. This may also involve a user defining their own options.

The options provide a user with the ability to select and configure a number of checks or rules that can be applied to the source material. The checks can help a user to author the source material such that it is consistent with corporate authoring standards or preferences at the authoring stage.

The options may involve the way in which words and punctuation appear in the source material. One example of option may relate to spelling variants so that a user may choose either British or American English spelling. Other such options may relate to the use of abbreviations contractions or compound words.

The options may involve the clarity and conciseness of the source material. An example of such an option may relate to the length of sentences commonly misused words or unnecessary wording that can be removed. An option may also relate to a regular expression which could be used for example to check for a specific combination of characters in the source material.

Preferably the relationship comprises a correlation between said identified part of source material and said identified part of stored material. The correlation could be an exact match or less strictly could indicate similarities between the source material and stored material.

Preferably the predetermined level is user definable. A user may thus adjust the predetermined level according to how closely the user requires the match between the stored material and the source material to be. Typical values may for example range from a relatively low 75 level to a relatively high 95 level depending on the amount and preciseness of matched or similar stored material the user wishes to review. If a user finds that a relatively low level for example 70 is producing too many similar results then the user may adjust the level for example to 90 such that the results are more manageable.

Preferably said correlation comprises a fuzzy logic match. Fuzzy logic techniques can thus be employed to produce a measure of how closely the compared source and stored material matches.

Preferably said outputting further comprises outputting data associated with said relationship. Data associated with the relationship can be output in order to give some indication to a user of the nature of the relationship identified between parts of the source and stored material. This could involve for example highlighting the common or different words and or displaying a correlation coefficient or a fuzzy logic match percentage.

Preferably said source material is input into a first software process by a user. The first software process may have some form of text editing functionality such as provided by word processing software.

Preferably said outputting and replacing steps are carried out by said first software process. Hence a user is presented with identified source and stored material by the word processing software they are currently authoring the content in. This will allow the user to see the effect that replacement of any source material with stored material will have on the content they are currently authoring.

Preferably said comparing and identifying steps are carried out by a second software process. The second software process can be a separate process to the first software process such that the invention can be used with many of the commercially available word processing software packages without the need for customisation.

Preferably said first software process interfaces with said second software process via an Application Program Interface API . The second software process is thus able to communicate with the first software process via an API provided for such purposes with the first software process.

Preferably said stored material is accessed by said second software process. Hence stored material can be searched and retrieved by the second software process and passed to the first software process where necessary.

In accordance with a second aspect of the present invention there is provided a computer program product comprising a computer readable medium having computer readable instructions recorded thereon for natural language translation the computer readable instructions being operative when performed by a computerized device to cause the computerized device to perform a method comprising 

comparing source material with stored material in a first natural language said stored material having previously been translated from said first natural language to at least a second natural language 

identifying at least a part of said source material which has a relationship with at least a part of said stored material 

outputting said identified part of source material and said identified part of stored material in a form suitable for review by a user and

replacing said identified part of source material with said identified part of stored material to assist full translation of said source material from said first natural language to at least said second natural language.

In accordance with a third aspect of the present invention there is provided apparatus for use in natural language translation the apparatus including one or more computing platforms being collectively programmed with a plurality of components the components being co operative to perform a method comprising 

comparing source material with stored material in a first natural language said stored material having previously been translated from said first natural language to at least a second natural language 

identifying at least a part of said source material which has a relationship with at least a part of said stored material 

outputting said identified part of source material and said identified part of stored material in a form suitable for review by a user and

replacing said identified part of source material with said identified part of stored material to assist full translation of said source material from said first natural language to at least said second natural language.

Further features and advantages of the invention will become apparent from the following description of preferred embodiments of the invention given by way of example only which is made with reference to the accompanying drawings.

A schematic system diagram according to an embodiment of the invention is shown in . Each of the components may be implemented and run on a common computing platform or may be distributed amongst different computing platforms. By computing platform here we mean a personal computer server or other type of computerized device which typically includes memory a processor and input output interface circuitry. As shown in the system includes a core component which includes a translation memory sub component a terminology sub component and a grammatical and stylistic sub component . The core component has access to a number of stored material databases which include one or more translation memory databases one or more terminology databases and one or more grammatical and stylistic databases . The core component interfaces with an authoring environment via a bridging component .

The authoring environment may be word processing software or such like which allows a user to author and edit source material such as text. The user creates the content hereinafter referred to as source material in one natural language with a view that the content may well be subsequently translated into one or more other natural languages. The authoring environment may comprise a first software process. The authoring environment may for example be software such as Microsoft Word Adobe Framemaker Blast Radius XMetal Author or Arbortext Editor .

The bridging component allows communication between the authoring environment and the core component . The core component may comprise a second software process.

When a user initiates an authoring check source material currently being created is passed from the authoring environment via the bridging component to the core component for processing. The results of the check are then passed back from the core component to the authoring environment O via the bridging component for review by the user. The operation of the bridging component will be described in more detail with reference to below.

The core component is responsible for the main data processing function of the invention. It may be in the form of a desktop software application running on a user s personal computer or similar computing device. Alternatively the core component may consist of an application hosted on a server with the user using a dumb terminal with all or the majority of processing being carried out by the server.

When the core component receives source material it compares it to material which has previously been stored in one or more databases hereinafter referred to as stored material. The core component identifies parts of the source material which have a relationship with parts of the stored material. The identified stored material is then passed back to the authoring environment which is then output for review by the user in the form of a proposed edit of the source material.

Data associated with the identified relationship may also be passed back to the authoring environment and used to indicate to the user the nature of the identified relationship. This data may for example relate to which words or phrases in the source material match or are similar to words or phrases in the identified stored material. Alternatively or additionally the data associated with the relationship may include a metric indicating how close the relationship is for example a correlation coefficient or percentage.

The user may now review the identified source material the identified stored material and optionally data relating to the identified relationship between the source and stored material and decide whether to edit the source material accordingly. If the user decides to edit the source material according to the proposal then the identified part of the source material is replaced with the stored material.

The core component includes three different sub components and which each are responsible for performing different authoring checks with different data processing functions. A user can choose to perform an authoring check using one or more of the subcomponents each of which is described below in turn.

The authoring checks may be carried out on source material in succession or concurrently. Preferably the translation memory check is carried out before the terminology or grammatical and stylistic checks.

The translation memory sub component has access to one or more translation memory databases TM DB which may be local network based or server based. The translation memory databases contain stored material which has previously been translated from a first natural language to at least one other natural language. The stored source material may be general translation memory data for all users or more commonly may be specific to one user or one technical field for example.

The translation memory sub component check involves comparing source material with stored source material and identifying any parts of the source material which have a relationship with parts of the stored material. When presented with the results i.e. the stored material identified as having a relationship with the source material from the translation memory subcomponent the user can decide whether to replace parts of the source material with parts of the stored material. When a full translation of the source material is subsequently carried out no translation of the replaced parts of the source material is required. This means that the workload associated with and time required to complete the full translation can be reduced and overall translation costs lowered due to the re use of previously translated material.

The terminology sub component has access to one or more terminology databases Terminology DB which may be local network based or server based. The terminology databases contain stored material which relates to terminology which has previously been used by a user or is of a form suitable for inclusion by a user hereinafter referred to as preferred terminology material. Preferred terminology material may be terminology which accords to company authoring guidelines or to accepted regional language customs or such like. The terminology databases also contain stored material which is not suitable for inclusion by the user hereinafter referred to as forbidden terminology material. Forbidden terminology material is terminology which for one or more reasons should not be used by the user for example because it is used by competitors or because it may be offensive to some readers.

The terminology sub component check involves comparing the source material to the stored material and identifying parts of the source material which have a relationship with parts of the stored material. When presented with the results from the terminology sub component a user can decide whether to replace parts of the source material with parts of the stored material. By such replacement of the source material the author can produce content which is more consistent with previously authored content for example using the same term for a feature which has previously been used by a user or a company as a whole. This can help to prevent confusion caused by differing wordings being used to refer to the same features for example. A further advantage here is that the terminology may have already been translated previously which reduces associated translation workload and costs and further increases the consistency of the full translation.

The terminology sub component is able to identify forbidden terminology to a user who may then edit the source material to remove it. The editing may be according to preferred terminology identified by the terminology sub component which is proposed to the user as a potential way in which the source material could be edited.

The grammatical and stylistic sub component has access to one or more grammatical and stylistic databases Grammatical and stylistic DB which may be local network based or server based. The grammatical and stylistic databases contain stored material which relates to a set of grammatical and stylistic options which the user may wish to have the source material checked for. The user can configure the grammatical and stylistic sub component to include any number of options from the set during a check of the source material. Each option may have a default setting and may be further configured by the user.

The grammatical and stylistic options may involve features that directly concern the way in which words and punctuation appear in the source material. This allows consistent application of writing conventions or rules whether accepted universally or specifically in a certain technical field or in a certain language or country for example.

One example of a grammatical option may relate to spelling variants so that a user may choose to check for either British or American English spelling. If the user wishes to author in British English then the grammatical and stylistic sub component can be configured such that the grammatical and stylistic sub component identifies parts of the source material which use American English spelling with reference to rules stored in the grammatical and stylistic database s . The grammatical and stylistic sub component can then propose British English versions from the stored material to replace the American English spelling in the source material.

Another example of a grammatical option may relate to the use of abbreviations as the user may wish to allow or not allow abbreviations in the source material. In a similar manner to the spelling variants option the grammatical and stylistic sub component can then propose replacement versions with or without abbreviations from the stored material for example using F AQ instead of Frequently asked questions. 

Another example of a grammatical option may relate to the use of contractions for example allowing use of isn t instead of is not. 

Another example of a grammatical option may relate to the use of compound words for example using world wide or worldwide .

Stylistic options may involve the clarity and conciseness of the source material currently being authored.

An example of such a stylistic option may relate to the length of sentences for example allowing a minimum sentence length of two words and a maximum sentence length of 25 words.

Another such stylistic option may relate to contextually commonly misused words for example the use of accept instead of except in certain contexts.

Another such stylistic option may relate to unnecessarily long wording or padding in the source material which could be replaced without changing the semantics of the source material to any great extent. This may for example allow for the words at the present time to be replaced by the word now. 

Another stylistic option may relate to a regular expression which could be used for example to check for a specific combination of characters in the current source material.

Configuration settings for a user or groups of users can be stored in configuration profile files for subsequent use. Such configuration profile files can be distributed or made available centrally to a number of users leading to easier management and increased consistency in the use of options between different users in natural language translation projects.

On the desktop side the core data processing part interfaces with a general configuration part . This allows the user to configure general settings such as listing the databases that the core data processing part may access and user authentication information. The core data processing part also interfaces with a grammatical and stylistic options configuration part . This allows configuration of settings relating to the grammatical and stylistic options sub component for example abbreviations contractions etc.

The core data processing part has further interfaces with one or more authoring environments including for example first Authoring environment second Authoring environment third Authoring environment fourth Authoring environment each of which has an associated current source material document . These could for example be Word Arbortext XMetal and Framemaker or any other such software package. The user may be currently authoring source material in one or more of the authoring environments and there may be more than one document not shown currently being authored in each authoring environment.

The core data processing part also interfaces with a translation memory subcomponent a grammatical and stylistic sub component and a terminology sub component as described above with reference to .

The translation memory sub component has a services interface which interfaces with stored material available in the form of one or more translation memory databases. The stored material in the translation memory databases may be accessed either concurrently or in turn during the comparing identifying and outputting steps of the invention as described above with relation to .

The translation memory databases may include a desktop translation memory database which is located on a storage device local to the user connected either directly to the user s personal computer or via a local area network LAN . The user may also have access to other remote translation memory databases for example a server based translation memory database accessed via a network such as the internet or m intranet through a server . There may be further translation memory databases accessible via the network not shown .

Similarly to the translation memory sub component the terminology sub component has a services interface which interfaces with stored material available to the user in the form of one or more terminology databases denoted Terminology DB in . The stored material in the terminology databases can be accessed either concurrently or in turn during the comparing identifying and outputting steps of the invention as described above with relation to . The terminology databases may include a desktop terminology database which is located on a storage device local to the user connected either directly to the user s personal computer or via a local area network LAN . The user may also have access to other remote terminology databases for example a server based terminology database accessed via network through a server . There may be further translation memory databases accessible via network not shown .

In alternative embodiments servers and may be the same server translation memory database and terminology database may be combined into the same database and or translation memory database and terminology database may be combined. In further alternative embodiments any of the components on the desktop may be hosted at a remote server with the desktop including a terminal capable of interfacing with the remote server.

The grammatical and stylistic sub component has access to one or more local and or remote grammatical and stylistic options databases in a similar manner to that described for the translation memory and terminology sub components the operation of which will be clear in view of the foregoing similar descriptions.

The bridging component starts processing in step when it receives a notification from the authoring environment that an authoring check should be carried out. The bridging component then finds the next part of the source material i.e. the next piece of text to be checked in step . This may be a highlighted paragraph or sentence for example.

The bridging component checks in step whether there is another part of the current source material to be checked. If there is another part of the source material to be checked the bridging component passes in step the next part of the source material to be checked to the core component . When the core component has finished processing i.e. checked that part of the source material the core component passes the results of the authoring check back to the bridging component . The results may include any stored material that has been identified as having a relationship with the part of the source material that has been checked and may also include data relating to the identified relationship between the stored material and the source material. The results are then processed in step by the bridging component . The processing will determine whether any stored material and relationship data needs to be passed to the authoring environment for review by the user.

If there is stored source material and relationship data to be displayed this is displayed to the user for review in step and the user may accept or reject any proposed changes to the source material and the process returns to step where the bridging component finds the next part of the current source material to be checked.

If there is no stored source material and relationship data to be displayed the process returns to step where the bridging component finds the next part of the source material to be checked.

The above process continues until during step the bridging component determines there are no more parts of the source material to be checked and processing stops in step .

The bridging component may be implemented using an Application Programming Interface API . An API can be defined as an interface that enables one or more computer programs to use facilities provided by one or more other computer programs whether by calling those programs or by being called by them. Thus in the present invention an API can be used to allow communication of a first software process i.e. an authoring environment with a second software process i.e. a core component .

In an alternative embodiment the bridging component may be a separate software process to the first and second software processes authoring environment and core component respectively . Further alternatively the bridging component may form part of the second software process.

The core component starts processing in step when it receives a part of source material from the bridging component upon which an authoring check should be carried out. Using appropriate segmentation rules the core component divides up the part of source material into segments in step ready for checking. The segments may for example be paragraphs sentences phrases or words. The nature of the segmentation will depend on the nature of the stored source material that the current source material is to be checked against.

In an alternative embodiment segmentation may be carried out by the bridging component so that the core component receives source material that has already been segmented.

Segmentation involves analysing the source material and dividing it up into segments according to one or more segmentation rules. The segmentation rules may be predetermined and may be user configurable. The division between segments may be determined according to punctuation present in the source material. For example it could be based on punctuation such as a full stop a semicolon a colon a question mark an exclamation mark a tab character or a paragraph mark. A user may specify segmentation rules which take a segment s context into consideration and may affirm or reject divisions between segments. Such rules may operate on spaces abbreviations the number and nature of leading and trailing characters and words and also take user specified lists into account such as abbreviation lists or lists of words which may follow ordinal numbers .

In step the core component determines whether the requested check is for a translation memory authoring check. If a translation memory authoring check has been requested the translation memory sub component carries out the translation memory check authoring in step to identify stored material which has a relationship with the source material being checked.

In step the core component determines whether the requested check is for a terminology authoring check. If a terminology authoring check has been requested the terminology sub component carries out the terminology authoring check in step to identify any stored material which has a relationship with the source material being checked.

In step the core component determines whether the requested check is for a grammatical and stylistic authoring check. If a grammatical and stylistic authoring check has been requested the grammatical and stylistic sub component carries out the grammatical and stylistic authoring check in step to identify any stored source material which has a relationship with the source material being checked.

In step the results of any of the translation memory terminology or grammatical and stylistic checks are arranged in a suitable form and passed back to the bridging component for processing. The core component then finishes processing of the authoring check for the source material in step .

In step of the translation memory sub component receives the first segment of source material to be checked from the bridging component via the core component . The first translation memory database from a list of translation memory databases that the translation memory sub component is configured for is selected in step . This could for example be the desktop translation memory database shown in . The translation memory sub component then accesses the selected translation memory database in step to identify any matches i.e. stored material which has a relationship with the segment of source material being checked. The translation memory sub component can be configured to identify as shown in step the closest match which may be an exact match or a number of the closest matches which are similar to the part being checked.

If there is an exact match then the exactly matching stored material may be retrieved from the translation memory database or alternatively the fact that an exact match has been found may be noted as shown in step .

If an exact match has not been identified the translation memory sub component may have identified stored material which is similar to the part being checked for example a fuzzy match. In this case the similar stored material is retrieved in step along with the data associated with the identified relationship for example the level of the fuzzy match. This data could be in the form of a percentage calculated using the number of matching and non matching words for example.

The translation memory sub component then checks to see if there are any more configured translation memory databases to be checked in step .

If there are more translation memories to be checked the next one in the list of configured translation memories is selected in step . This may for example be the server based translation memory database shown in . Steps and are then repeated accordingly for this and any further configured translation memories.

The translation memory sub component then determines whether there are any more segments of the source material to be checked in step in which case the next segment is obtained from the bridging component via the core component in step and the process repeats as above. If there are no more segments to be checked then any identified results and data relating to any identified relationships are returned to the core component which in turn passes these on to the bridging component in a suitable format.

In step of the terminology sub component receives the first segment of source material to be checked from the bridging component via the core component . The first terminology database from a list of terminology databases that the terminology subcomponent is configured for is selected in step . This could for example be the desktop terminology database database shown in . The terminology sub component then accesses the selected terminology database in step to identify any matches i.e. stored material which has a relationship with the segment of source material being checked. The terminology sub component can be configured to identify as shown in step the closest match which may be an exact match or one or more of the closest matches which are similar to the segment being checked. Any matches are retrieved in step in a similar manner to that described above for the translation memory sub component.

The terminology sub component then checks if there are more terminology databases to be checked in step .

If there are more terminology databases to be checked the next one in the list of configured terminology databases is selected in step . This may for example be the server based terminology database shown in . Steps and are then repeated accordingly for any further configured terminology databases.

The terminology sub component then determines whether there are any more segments of the source material to be checked in step in which case the next segment is obtained from the bridging component via the core component in step and the process repeats as above. If there are no more segments to be checked then any identified results and data relating to any identified relationships are returned to the core component which passes these on to the bridging component in a suitable format.

In step of the grammatical and stylistic sub component receives the first segment of source material to be checked from the bridging component via the core component . The first grammatical and stylistic database from a list of grammatical and stylistic databases that the grammatical and stylistic sub component is configured for is selected in step . This could for example be a desktop network or server based grammatical and stylistic database. The grammatical and stylistic sub component then accesses the selected grammatical and stylistic database in step to identify any matches i.e. stored material which has a relationship with the segment of source material being checked. The grammatical and stylistic sub component can be configured to identify as shown in step the closest match which may be an exact match or a number of the closest matches which are similar to the segment being checked. Any matches are retrieved in step in a similar manner to that described above for the translation memory sub component.

The grammatical and stylistic sub component then checks if there are more grammatical and stylistic databases to be checked in step .

If there are more grammatical and stylistic databases to be checked the next one in the list of configured grammatical and stylistic databases is selected in step . Steps and are then repeated accordingly for any further configured grammatical and stylistic databases.

The grammatical and stylistic sub component then determines whether there are any more segments of the source material currently being authored to be checked in step in which case the next segment is obtained from the bridging component via the core component in step and the process repeats as above. If there are no more segments to be checked then any identified results and data relating to any identified relationships are returned to the core component which passes these on to the bridging component in a suitable format.

In alternative embodiments all segments that are to undergo translation memory terminology and or grammatical and stylistic checks may be passed en masse to the respective sub components and checked against the relevant databases in groups of segments or a block of all the segments.

The invention includes functionality which can provide data reports on source material and any authoring checks carried out.

A report may be produced for one or more documents that a user is currently working on or one or more document that a user has previously worked on. The reports can provide various types of information for example configuration settings the number of segments and words the number of identified translation memory terminology and or grammatical and stylistic matches or similarities the number of forbidden terms identified etc. Such reports can give a useful measure of how the invention has improved consistency in the source material and how translation workloads have been reduced. A report may be presented in a word processing document or a spreadsheet or such like and may include various presentation aids such as graphs pie charts etc. and may include estimated translation cost savings.

The functionality disclosed herein may be embodied in a computer program product comprising a computer readable medium having computer readable instructions recorded thereon for natural language translation wherein the computer readable instructions are operative when performed by a computerized device to cause the computerized device to perform the corresponding method. Examples of such computer readable media include without limitation semiconductor memory media magnetic storage media and optical storage media.

The above embodiments are to be understood as illustrative examples of the invention. Further embodiments of the invention are envisaged. It is to be understood that any feature described in relation to anyone embodiment may be used alone or in combination with other features described and may also be used in combination with one or more features of any other of the embodiments or any combination of any other of the embodiments. Furthermore equivalents and modifications not described above may also be employed without departing from the scope of the invention which is defined in the accompanying claims.

