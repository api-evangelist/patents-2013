---

title: Gamification provider abstraction layer
abstract: A system that manages a gamification provider abstraction layer can select a gamification provider. The system receives a common gamification request message from a client and creates a provider-specific request message based on the received common gamification request message and the selected gamification provider. The system then transmits the provider-specific request message to the selected gamification provider.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09526984&OS=09526984&RS=09526984
owner: ORACLE INTERNATIONAL CORPORATION
number: 09526984
owner_city: Redwood Shores
owner_country: US
publication_date: 20131121
---
One embodiment is directed generally to a computer system and in particular to a computer system that manages a gamification provider abstraction layer.

Gamification is the use of game thinking game mechanics reputation mechanics and or social mechanics in a non game context to engage users and or solve problems. Gamification can be used in applications and processes to improve user engagement return on investment data quality timeliness and learning. Gamification techniques strive to leverage people s natural desires for competition achievement status self expression altruism and closure.

One gamification strategy is rewards for players who accomplish desired tasks. Types of rewards include points achievement badges or levels the filling of a progress bar and providing the user with virtual currency. Competition is another element of games that can be used in gamification. Making the rewards for accomplishing tasks visible to other players or providing leader boards are ways of encouraging players to compete.

Another approach to gamification is to make existing tasks feel more like games. Some techniques used in this approach include adding meaningful choice onboarding with a tutorial increasing challenge and adding narrative.

One embodiment is a system that manages a gamification provider abstraction layer. The system selects a gamification provider. The system receives a common gamification request message from a client and creates a provider specific request message based on the received common gamification request message and the selected gamification provider. The system then transmits the provider specific request message to the selected gamification provider.

One embodiment is a system that manages gamification services by providing a gamification provider abstraction layer that enables client applications such as enterprise applications to interact indirectly with a selected gamification or behavior service provider such as The Behavior Platform by Badgeville Inc. Badgeville and Nitro by Bunchball Inc. Bunchball . The abstraction layer provides gamification services to the enterprise applications without requiring direct interaction between the applications and any particular gamification provider. The applications communicate with the system according to a common application programming interface API provided by the abstraction layer which allows the system to change the selected gamification provider without requiring changes to the enterprise applications. The system transforms sensitive data before transmitting data to the selected gamification provider such as obfuscating sensitive data and or de identifying personal identification medical data. The system provides unique gaming namespaces gamespaces in which applications can capture user behaviors and collect rewards. Gamespaces can be limited to a single application or shared across applications and applications can access multiple gamespaces.

In one embodiment the system receives requests from applications according to a common API and transforms the common requests into provider specific requests. The system transmits the provider specific requests to the selected gamification provider and receives provider specific responses. The provider specific responses are transformed into common responses and sent to the requesting application.

Computer readable media may be any available media that can be accessed by processor and includes both volatile and nonvolatile media removable and non removable media and communication media. Communication media may include computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media.

Processor is further coupled via bus to a display such as a Liquid Crystal Display LCD for displaying information to a user. A keyboard and a cursor control device such as a computer mouse is further coupled to bus to enable a user to interface with system .

In one embodiment memory stores software modules that provide functionality when executed by processor . The modules include an operating system that provides operating system functionality for system . The modules further include a gamification provider abstraction layer that provides a common gamification API as disclosed in more detail below. The modules further include a Client SDK API that can be used by client applications such as gamified client application to interact with gamification provider abstraction layer . Client application can be executed locally on system or remotely on a second system such as a mobile device and connect to gamification provider abstraction layer through a network or any other method. Gamified client application that interacts with gamification provider abstraction layer to provide behavior collection services for the end users of application . Examples of gamified client application include web applications desktop applications and mobile applications or apps etc. Examples of gamified client application further include enterprise applications such as the following applications from Oracle Corp. the Argus product family the Health Management Platform Solution the InForm product family the Mobile Clinical Research Associate application Mobile CRA or a Customer Relationship Management CRM application. System can be part of a larger system such as an enterprise resource planning ERP system. Therefore system will typically include one or more additional functional modules to include the additional functionality. A database is coupled to bus to provide centralized storage for modules and and store behavior information gamespace definitions etc.

In one embodiment system receives a common gamification request at gamification provider abstraction layer such as a request to register a user behavior from client application and creates a provider specific request based on the common request. Gamification provider abstraction layer transmits the provider specific request to gamification provider e.g. Badgeville Bunchball etc. and receives a provider specific response. Gamification provider abstraction layer creates a common response based on the provider specific response and transmits the common response to client application . In some embodiments client application can be running on a separate system and communicate with gamification provider abstraction layer via a network such as a local area network LAN wide area network WAN the Internet etc. For example client application can be a mobile app running on a personal digital assistant PDA or smartphone.

In some embodiments when creating the provider specific request system de identifies any personal identification data and or medical data before adding such data to the provider specific request. In some embodiments when creating the provider specific request system de identifies any personal identification data for users who have not opted in before adding such data to the provider specific request. Therefore system can be compliant under the Health Insurance Portability and Accountability Act of 1996 HIPAA .

In some embodiments system comprises a common representational state transfer REST interface between client applications and gamification providers that provide implementations for tracking and gamifying user behaviors such as Badgeville Bunchball etc. For example system can include modules for accessing Badgeville and Bunchball as gamification providers.

Some embodiments provide security and authentication models such as token based authentication and credentials based username and password authentication.

In some embodiments gamification provider abstraction layer can be an abstraction on top of features provided by various gamification or behavior service providers. Features provided by behavior gamification providers can be abstracted using the concept of a gamespace as described herein.

In some embodiments gamespaces can have different access types. For example a public gamespace can be accessible without registration while a private gamespace can be accessible only by users registered in that gamespace. In another example a gamespace with inherited access can be accessible by users who have access to that gamespace s parent.

In some embodiments gamespaces with private access type require explicit player registration i.e. existing users hosted and on premises should register with the gamespace first before using it .

In some embodiments users can be categorized as hosted or on premises. For example on premises users can include users who access gamification provider abstraction layer via a product installed on a third party system whereas hosted users include users who access gamification provider abstraction layer via a product hosted off site such as a cloud based product a SaaS product etc.

In embodiments before a gamespace can be used the gamespace is created using a create gamespace request such as the create new gamespace API described in below. In some embodiments API can be invoked by a REST client using client credentials. In some embodiments among other parameters the API can allow for gamespace template name to be provided. For example gamespace templates defining a set of allowed behaviors activities can be used during gamespace creation to facilitate the creation of similarly structured gamespaces.

Referring again to in one embodiment public root gamespace is a predefined gamespace and is at the top of the hierarchy. Community gamespace community gamespace and community gamespace are top level private gamespaces. Gamespaces are gamespaces for community s gamified products consumer application instances .

In embodiments clients can create their respective top level private gamespaces directly under public root gamespace such as top level private gamespaces and . Privacy restrictions can be enforced such that users of private gamespace and its descendants cannot access private gamespace and its descendants and vice versa. In some embodiments gamespaces and can be a container gamespace or a mixed gamespace.

For example in some embodiments container gamespaces do not define their own behaviors e.g. clients cannot invoke behavior related APIs within a container gamespaces and cannot engage in a game using the container gamespace . In such embodiments container gamespaces can be used as a parent to for example provide common access permission for its sub gamespaces. In some embodiments the container gamespaces do not need to be mapped to any artifact on the gamification provider s side unless the provider supports a similar container type gamespace concept.

In some embodiments mixed gamespaces can be used as a parent to for example provide common access permission for its sub gamespaces like container gamespaces and also support behavior activities at the same time. For example in some embodiments mixed gamespaces can have properties of both container gamespaces and product gamespaces.

In embodiments product gamespaces can be created with the inherited access type under a top level private gamespace for gamified products e.g. products with gamification support and examples of such product gamespaces are provided as gamespaces and . The inherited access type allows users of the parent gamespace to access the child gamespace with inherited access type.

In some embodiments gamespaces can include product features and the same hierarchical inherited access rules can apply to product features having dedicated behavior support. For example product features may define their own sub features in a hierarchical manner similar to the manner in which gamespaces can be hierarchically defined. In such examples inheritance rules can apply to the featute sub feature hierarchy of a product feature heirarchy. For example product feature XYZ can have sub features X Y and Z for which gamification is enabled and it is possible to configure respective gamespaces as follows clients of feature XYZ will have access to all sub features X Y and Z or clients of sub feature X do not have access to sub features Y and Z and vice versa. In some embodiments gamespaces need not be restricted to single clients products and can be shared across products and or clients.

In some embodiments APIs can be implemented as Representational State Transfer REST APIs made available over the Hypertext Transfer Protocol HTTP at the indicated Uniform Resource Identifier URI using HTTP POST and GET method requests that include data formatted according to the JavaScript Object Notation JSON format as described below.

In some embodiments authentication can be provided using client credentials e.g. username and password and or token based authentication. For example admin APIs can be accessed by supplying client credentials such as a username and password according to the HTTP basic access authentication method. Non admin APIs can be accessed using token based authentication using for example tokens generated via generate new token API .

Create new gamespace API can be invoked to create a new gamespace. Requests to can be supplied via HTTP POST with the following data 

The following is an example request response under create new gamespace API to create a new gamespace 

Get namespace information API can be invoked to get information describing an existing gamespace. Requests to can be supplied via HTTP GET with the following data 

Create new user API can be invoked to create or modify a user. Requests to can be supplied via HTTP POST with the following data 

Responses to create new user API requests can include an HTTP response code to indicate whether the request was successful.

The following is an example request response under create new user API to get information about a gamespace 

The HTTP status code in the example response shown above can indicate that the request was successful and the requested user was added successfully. Other HTTP status codes can be used to indicate failure of the request due to an error. For example HTTP status code can be used to indicate an invalid request can indicate an unauthorized request can indicate an internal server error or can indicate that the headers sent in the request are not acceptable. In some embodiments HTTP status codes can also be used for responses in one or more of other APIs .

Get player info API can be invoked to get player information. Requests to can be supplied via HTTP GET with a user identifier included in the HTTP request header.

In some embodiments non admin APIs and utilize token based authentication by populating custom HTTP header fields CBS user and CBS token with the target user and token value respectively as shown above. Although not shown the remaining non admin APIs can also utilize similar token based authentication. Tokens can be generated using generate new token API as described below and further described in .

Create activity API can be invoked to create an activity for a user for example register a behavior . Requests to can be supplied via HTTP POST with the following data 

Responses to requests can include an HTTP response code to indicate whether the request was successful.

Get rewards obtained by user API can be invoked to get a list of rewards earned by a given user. Requests to can be supplied via HTTP GET with the given user being supplied in the custom HTTP header field CBS user .

Get levels API can be invoked to get a list of all levels that can be achieved in a given gamespace. Requests to API can be supplied via HTTP GET with the gamespace identifier being included in the URI path.

Get all rewards API can be invoked to get a list of all rewards that a user can achieve. Requests to can be supplied via HTTP GET with the CBS user custom HTTP header field indicating the user for which the list of achievable rewards is requested.

Get all leaderboards API can be invoked to get all the leaderboards for a given gamespace. Requests to can be supplied via HTTP GET with the target gamespace being identified in the URI path.

Get leaderboard information API can be invoked to get leaderboard information for a particular leaderboard. Requests to can be supplied via HTTP GET with the leaderboard indicator being included in the URI path.

Responses to requests can include data for one leaderboard similar to the data returned in response to requests.

Generate token API can be invoked to generate a token that can be used to access non admin APIs . Requests to can be supplied via HTTP POST with the following data 

The token returned by can then be used by clients to access the non admin APIs which can utilize token based authentication.

In embodiments when Badgeville is selected as the gamification provider top level gamespaces directly under the root gamespace can be mapped to Badgeville s network. Other gamespaces below the top level gamespaces can be mapped to Badgeville sites and the sites can be created from templates. Top level registered users can be mapped to Badgeville users and individual activity properties can be mapped to similar behavior properties as is without any property name value translations.

Gamification provider abstraction layer can be configured to receive from Client a common request e.g. one of the admin APIs such as create gamespace API request . Gamification provider abstraction layer can be configured to create and transmit a provider specific request based on common request to gamification provider . For example if the selected gamification provider is Badgeville gamification provider abstraction layer can create a Badgeville specific request to create a Badgeville network or site and transmit it to Badgeville.

Gamification provider abstraction layer can be configured to receive a provider specific response from gamification provider . Gamification provider abstraction layer can create a common response based on the received provider specific response and transmit common response to client .

It will be appreciated that the actual gamification provider can be swapped without impacting client . For example Bunchball can replace Badgeville as the selected gamification provider without requiring changes to client because client and gamification provider abstraction layer can be configured such that client does not directly interact with the selected gamification provider .

Gamification provider abstraction layer can transmit data to and receive data from client in accordance with a common gamification API such as common gamification API shown in . Gamification provider abstraction layer can transmit data to and receive data from gamification provider to fulfill client requests.

Gamification provider abstraction layer can be configured to receive a generate token request such as generate token API request as shown in above. Gamification provider abstraction layer can be configured to generate a token and transmit a generate token response including the generated token to client .

Gamification provider abstraction layer can be configured to receive a common request from client and apply token based authentication such as the token based authentication described above for non admin API requests shown in . For example client can transmit a common request e.g. any non admin API request that includes the token received at for token based authentication. Gamification provider abstraction layer can receive common request authenticate the token create a provider specific request based on the common request and transmit provider specific request to gamification provider .

In some embodiments gamification provider abstraction layer can be configured to transform data prior to transmitting provider specific request and or to gamification provider . For example gamification provider abstraction layer can be configured to de identify any identification data that may be a part of provider specific request and or modifying medical related data as described in below. In another example gamification provider abstraction layer can be configured to de identify data sent to selected gamification provider for those users who have not opted in to the service as described in below.

Gamified applications and include modules and respectively to facilitate communications with gamification provider abstraction layer . Gamification provider abstraction layer can include an authentication layer a REST API module implementing common gamification API as shown in above a Personal Health Information PHI cleaner module a Personally Identifiable Information PII obfuscation and privacy labor compliance module a gamification service provider interface module a persistence service provider module and a gamification provider implementation module .

In some embodiments mobile application SDK and JavaScript API can be configured to provide a client SDK and API to mobile application and browser application respectively for connecting to gamification provider abstraction layer via REST API module which implements common gamification API . For example JavaScript module can include JavaScript client APIs that are AJAX based and invoke the respective server APIs of common gamification API accordingly.

In operation requests from gamified applications and can be authenticated by authentication module using HTTP basic authorization and or a custom token authentication schema as provided by common gamification API . The authenticated requests can be handled to REST API module which can delegate further processing to PHI cleaner module PII obfuscation and privacy labor compliance module gamification provider interface module and or gamification provider implementation module to create a provider specific request.

PHI cleaner module can ensure that behaviors and data pass screening before being sent to gamification provider . For example in some embodiments PHI cleaner module can provide for the de identification of personal health information before it is sent to gamification provider . In embodiments de identification can be performed by convention and or registration.

For example de identification performed by convention can be defined by an Augmented Backus Naur Form ABNF . In one embodiment de identification by convention can be defined by the following ABNF 

In another example de identification performed by registration can be performed by configuration. In such an example PHI cleaner module can load a JSON document to be used to perform de identification.

For example the JSON document can contain a list of valid gamification activity property names for a given gamespace. The valid property names can be obfuscated property names. Subsequently PHI cleaner module can validate the properties of gamification activities posted by clients against the list of valid gamification activity property names contained in the JSON document. If at least one activity property is not found in the pre defined list contained in the JSON document e.g. the client attempts to use an unobfuscated property not contained in the JSON document the posted activity is rejected by the gamification abstraction layer and not submitted to a gamification provider. In such examples the gamification abstraction layer does not maintain a mapping of the obfuscated property names to their respective unobfuscated counterparts and therefore even if both the gamification abstraction layer and the gamification provider are compromised the attacker will not be able to de identify the data. In such examples the de identification mapping is maintained solely on the client side.

PII obfuscation and privacy labor compliance module can ensure legal and regulatory compliance by verifying a player s eligibility for behavior collection and to obfuscate usernames before sending them to gamification provider . Some countries do not allow behavior collection for certain employees or other classes of users while some countries allow behavior collection of users who expressly opt in to the collection. PII obfuscation and privacy labor module can be aware of the applicable rules and ensure compliance with privacy and labor laws. For example an opt in field can be associated with each user and set if the user has expressly opted in to behavior collection. In another example PII obfuscation and privacy labor compliance module can be aware of the privacy and labor rules applicable to a user based on e.g. the user s Internet Protocol IP address mailing address work address company place of business server location etc. and ensure that behavior collection is not performed if not permitted under the applicable country s privacy and or labor rules.

Gamification provider interface module can provide one or more service provider implementations such as gamification provider implementation for integrating with one or more specific gamification provider such as Badgeville. The service provider implementations delegate the provider specific requests to the actual external gamification provider e.g. Badgeville.

In some embodiments modules and can use persistent storage and interface with database using persistence service provider .

At module receives a create token request from a client. In some embodiments the create token request can be a generate new token API request as shown in above. For example in embodiments the create token request includes at least a key signature and a nonce value.

At module creates a new token based on the create token request including at least the key and nonce value.

At module receives a request such as a non admin API request including the token generated at and authenticates the user. Under the token based authentication scheme each token can be used only one time.

At module selects a gamification provider such as Badgeville Bunchball etc. In some embodiments the gamification provider is selected once and only one gamification provider can be selected at a time for all clients. In other embodiments the gamification provider can be selected on a per client per user player or per gamespace basis.

At module receives a common gamification API request from a client such as a create activity request. In some embodiments the common request is authenticated using token based authentication.

At module transforms the common request into a provider specific request. In some embodiments transforming the common request into a provider specific request includes de identify personal health information obfuscate sensitive data such as personally identifying information and or ensure compliance with privacy labor rules before sending provider specific requests to a selected gamification provider as described above in .

At module transforms the provider specific response into a common response in accordance with the common API.

In some embodiments module can receive requests in accordance with common gamification API as shown in above.

Start quest screen can include a list of available quests such as a water quest an alcohol quest a sleep quest and or a coffee quest .

If a user selects to begin a water quest begin quest screen can be displayed and the user can select one or more desired water quest parameters to be applied such as length of quest show targets and enable reminders . The user can begin the water quest using the desired parameters by selecting begin .

In some embodiments when the user begins a water quest the user s behavior can be recorded using the common gamification API provided by the gamification provider abstraction layer of to track the user s progress i.e. adherence to the quest parameters and provide progress rewards. For example in some embodiments the gamified mobile application illustrated in interfaces with the common gamification API which interacts with a gamification provider e.g. Badgeville so that the gamified mobile application does not interact directly with the gamification provider. Examples of the gamified mobile application include applications utilizing the Medical Adherence Tracker Framework disclosed in U.S. patent application Ser. No. 14 085 987 filed on Nov. 21 2013 the contents of which is hereby incorporated by reference in its entirety.

Complete quest screen can be shown when the user completes a water quest. The user can view rewards earned for completing the quest by selecting button . Rewards can be based on user behavior recorded by the application as discussed hereinabove.

For example custom authentication grants such as those found in section 4.5 of the OAuth 2.0 specification can allow a client of gamification provider abstraction layer to provide its the client s users with access to gamification provider abstraction layer which can be owned and managed by a second entity separate from the client. The functionality shown in avoids the need to provision each end user of the client within gamification provider abstraction layer .

At module provisions a gamification service client. As part of the provisioning process the client is issued client credentials. The credentials are used to access module at below. In some embodiments this is a one time activity per client.

At the client transmits a request to module to create a private gamespace. As part of the gamespace creation module issues the client a gamespace secret key. Both the client and module store the key securely. In some embodiments this is a one time activity per gamespace.

At an end user requests the client to provide a token to access module . The client can define its own protocol and or requirements for the end user request because the end user s request is not required to be received nor is it required to be processed by module .

At the client sends a token request to module on behalf of the user. In some embodiments token request includes gamespace identifier user identifier timestamp certain unique identifier nonce and a digital signature of these parameters. Digital signature is created using the gamespace key from above and can be based for example on a keyed hash message authentication code HMAC algorithm such as an HMAC 512 algorithm e.g. HMAC MD5 or HMAC SHA1 .

At if the request is valid e.g. digital signature verified successfully module issues a token to the client. In some embodiments the token itself includes a timestamp and the digital signature of the timestamp user id and gamespace id. This digital signature is based on the same gamespace key and can be based on for example an HMAC 512 algorithm.

At the end user uses the token to access module APIs directly such as for example common gamification API of .

As disclosed embodiments comprise a gamification provider abstraction layer to provide a common interface for client applications to engage in behavior collection in configurable gamespaces without directly interacting with a specific gamification provider. The abstraction layer can provide de identification of health information for HIPAA compliancy personal information obscuration privacy labor compliance assurance and enhanced token based authentication.

Several embodiments are specifically illustrated and or described herein. However it will be appreciated that modifications and variations of the disclosed embodiments are covered by the above teachings and within the purview of the appended claims without departing from the spirit and intended scope of the invention.

