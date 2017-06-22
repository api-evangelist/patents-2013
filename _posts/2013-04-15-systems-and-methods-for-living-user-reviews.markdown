---

title: Systems and methods for living user reviews
abstract: Systems and methods for creating an opinion timeline. Users are able to submit ongoing reviews for products and services based on extended use, new revelations, additional features, upgrades and the like. Users can be notified of upgrades or improvements and are requested to provide another review of the product or service which is tied to the original review. Users can also update their review of the product or service based on a change in mind. The opinion timeline can be applied to reviews of products, television shows, music, etc.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09400989&OS=09400989&RS=09400989
owner: CBS Interactive Inc.
number: 09400989
owner_city: San Francisco
owner_country: US
publication_date: 20130415
---
This application is a continuation of application Ser. No. 12 579 383 filed on Oct. 14 2009 the contents of which are incorporated herein by reference.

The subject invention relates to systems and methods for updating user reviews and in particular to systems and methods for creating an opinion timeline.

The Internet is used for retailers to offer products and services that they are selling and for consumers to purchase those products and services. Many of these sites allow users to review the products they have purchased and or services that they have used. Independent sites sites that do not retail the products and services being reviewed e.g. yelp.com are also available for users to submit reviews of products and services.

User reviews are representative of a fixed moment in time that is they are static in nature. Users typically review products soon after they purchase the product and review services soon after they receive the service. User opinions however typically continue to evolve throughout the lifecycle of the product and over the course of the relationship with the service provider. In addition some products are upgraded to enhance features or otherwise improve the product e.g. electronics receive upgrades to their internal operating systems firmware or software .

Some sites allow users to edit their reviews if their opinion changes. These sites however do not offer the ability for users to add information to their original review based on ongoing use while maintaining the original review.

The following summary of the invention is included in order to provide a basic understanding of some aspects and features of the invention. This summary is not an extensive overview of the invention and as such it is not intended to particularly identify key or critical elements of the invention or to delineate the scope of the invention. Its sole purpose is to present some concepts of the invention in a simplified form as a prelude to the more detailed description that is presented below.

According to an aspect of the invention a computer system is provided that includes memory and a processor in communication with the memory the processor configured to allow a user to submit a first review of an asset on a website store the first review of the asset on the website with a user identifier allow the user to submit a second review of the asset on the website store the second review with the first review and the user identifier and generate an opinion timeline for the asset for the user associated with the user identifier.

The second review is based on a change of mind of the user. The second review may be based on an update of the asset.

The processor may be further configured to notify the user of an update to the asset and request the user provide the second review of the asset based on the update.

The processor may be further configured to analyze the first review and the second review and recommend another asset to the user based on the first review and the second review.

The processor may be further configured to generate and transmit a request to the user to submit the second review.

According to another aspect of the invention a computer implemented method is provided that includes allowing a user to submit a first review of an asset on a website storing the first review of the asset on the website with a user identifier allowing the user to submit a second review of the asset on the website storing the second review with the first review and the user identifier and generating an opinion timeline for the asset for the user associated with the user identifier.

The second review may be based on a change of mind of the user. The second review may be based on an update of the asset.

The method may also include notifying the user of an update to the asset and requesting the user provide the second review of the asset based on the update.

The method may also include analyzing the first review and the second review and recommending another asset to the user based on the first review and the second review.

The method may also include generating and transmitting a request to the user to submit the second review.

According to a further aspect of the invention a computer readable storage media is provided having computer executable instructions stored thereon which cause a computer system to carry out the above method when executed.

Embodiments of the invention are directed to systems and methods that allow users to submit ongoing updates to reviews for various products and services assets based on for example extended use new revelations additional features and the like. The systems and methods preserve previous reviews and allow the user to make changes as well as add new information to their review. The full review including both the old review and this edited review is used to generate an opinion timeline . This opinion timeline allows users to continue adding information to their review based on these changes providing a way for users to express their changing opinions over time.

These systems and methods may also notify users of updates to assets they have reviewed and ask them to provide additional information based on those updates. Similarly the systems and methods may also notify users of assets that are similar to assets the user has previously reviewed to generate an opinion timeline that is a comparison review . In effect these systems and methods allow users to change their mind after they have reviewed an asset based on new information changes to the asset or competitive assets.

It will be appreciated that these systems and methods may be used in a variety of contexts in which users submit a review. For example reviews of products services and or media content may be collected at various stages of a user s interaction with each asset to gain valuable insight into the change of user opinions over time and the factors that most impact this change. That analysis can then be applied to product enhancement media creation content recommendations as well as to improve targeted advertising delivery. When combined with other statistical information such as user demo psychographics the opinion timelines can be associated with purchasing and content consumption analyses.

An embodiment of the invention will now be described in detail with reference to . illustrates a server that is connected over a network to a plurality of user systems . The server includes a processor and memory which are in communication with one another.

The server is configured to deliver online content to users at the user systems . The server is typically a computer system and may be an HTTP Hypertext Transfer Protocol server such as an Apache server. The memory may be any type of storage media that may be volatile or non volatile memory that includes for example read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices and zip drives.

The network is a local area network LAN wide area network WAN a telephone network such as the Public Switched Telephone Network PSTN an intranet the Internet or combinations thereof. The plurality of user systems may be mainframes minicomputers personal computers laptops personal digital assistants PDA cell phones and the like. The plurality of user systems are characterized in that they are capable of being connected to the network . The plurality of user systems typically include web browsers.

In use when a user of one of the plurality of user systems is browsing a web page a request to access content is communicated to the server over the network . For example a signal is transmitted from one of the user systems the signal having a destination address e.g. address representing the server a request e.g. content request and a return address e.g. address representing user system that initiated the request . The processor accesses the memory to provide the requested content which is communicated to the user over the network . For example another signal may be transmitted that includes a destination address corresponding to the return address of the client system and the content responsive to the request.

The web layer is configured to receive user requests to access content through a web browser and return content that is responsive to the user request. The web layer communicates the user requests to the cache . The cache is configured to temporarily store content that is accessed frequently by the web layer and can be rapidly accessed by the web layer . In one embodiment the cache may be a caching proxy server. The cache communicates the user requests to the site application .

The site application is configured to update the cache and to process user requests received from the web layer . The site application may identify that the user request is for a page that includes data from multiple sources. The site application can then convert the page request into a request for content from multiple sources and transmits these requests to the content API.

The content API is configured to simultaneously access data from the plurality of data stores to collect the data responsive to the plurality of requests from the site application . The plurality of data stores include catalogue data about different product types e.g. product specifications pricing images upgrades etc. and other asset types e.g. television shows seasons cast music artists albums songs release date etc. . It will be appreciated that in alternative embodiments only one data store may be provided to store the data.

The data in the data stores is provided to the content API which provides the content to the site application . The site application updates the cache and delivers the cached content in combination with the accessed content to the web layer which delivers browsable content to the user.

The opinion timeline engine is configured to generate an opinion timeline and allow users to interact with the opinion timeline. In one embodiment the logic layer is configured to generate the opinion timeline using data in the data stores and the delivery mechanism is configured to receive the user reviews from the website and or deliver the opinion timeline to the users at the website .

The product data store is configured to store data about products e.g. model name manufacturer retailers upgrades images etc. . The show data store is configured to store data about television shows e.g. show name network season cast episode name etc. . The music data store is configured to store data about music available online e.g. artist name album name song title release date producer etc. The user opinion data store is configured to store user reviews. These user reviews may be stored with a user identifier to identify the user that submitted the review and or an asset identifier to identify the asset e.g product show music in data stores that was reviewed. It will be appreciated that alternatively the reviews may be stored in data stores with the asset being reviewed.

In use a user reviews a first asset and transmits the review to the delivery mechanism . The logic layer stores that user review in the user opinion data sore . The logic layer may optionally generate a request for an update using information in the data stores . The user submits another review of the asset e.g. editing or updating their previous review and this new review is also stored in the user opinion data store as described above. The logic layer then associates these two user reviews together using the user identification information and or asset identification information associated with both reviews. The opinion timeline can then be generated by the logic layer and transmitted to the website using the delivery mechanism .

As described above the opinion timeline provides a multi dimensional view into consumer relationships with products and companies. Each review of an asset offered by a provider affects the overall rating of the provider both by the individual user and in aggregate.

For example a user may purchase an Apple IPHONE 3G immediately after is released experiencing problems with dropped calls and accessing the Internet. After much frustration the user may submit a poor review of the product on CNET Reviews. A few weeks later a software update may be released for the Apple IPHONE 3G which may resolve those problems. The user may receive a notification from CNET about the software update along with a request to update their review which the user does. As additional updates are released the user may continue to add information to the review creating a feedback loop that can be used for a variety of content and product recommendations. In addition the individual product review influences the overall user rating for the product manufacturer e.g. Apple .

In another example a TV.com viewer may start watching the series Heroes and enjoys the entire first season. The user may enthusiastically submit a review of the series on TV.com. The user continues viewing the second and third seasons of the series but decides eventually that the show is no longer as enjoyable as it was in that first season. The user may submit this information as an update to the previous review that was submitted. Other viewers can read the review and subsequent updates to decide is they want to start viewing Heroes. In addition the decline in the quality of the series can be mapped against changes in the content division at NBC or other relevant data.

In yet another example a Last.fm listener may discover the band The Smashing Pumpkins listening to several of the early albums and submit glowing reviews of the music. The listener may discover that they do not enjoy the more recent albums and post a review to that effect. The individual review is applied to the album as well as to the overall band rating for the listener and in aggregate for users who have reviewed The Smashing Pumpkins. In addition the combination of reviews from different points in time provides a better method for delivering insightful content recommendations to the user.

The process begins by allowing a user to submit a first review of an asset on a website block and storing the first review of the asset on the website with a user identifier block . For example the opinion timeline engine may receive a user review of an asset stored in one of data stores and stores that user review in the user opinion data store .

The process continues by allowing the user to submit a second review of the asset on the website block and storing the second review with the first review and the user identifier block . For example the opinion timeline engine may receive a user review related to the first review and stores that user review in the user opinion data store . This second review may be an edit of the first review or an addition to the first review. The second review may be based on for example a change in opinion over time a change in opinion based on an update a comparison of a similar asset and the like.

The process continues by generating an opinion timeline for the asset for the user associated with the user identifier block . For example the opinion timeline engine may generate an opinion timeline using the first review and the second review e.g. by matching the user identifier of the first review with the user identifier of the second review .

It will be appreciated that many additional iterations of the above process may be performed i.e. each time a user submits a new review or update to the existing review . It will also be appreciated that the process may include additional steps. For example the process may also generate a request for the user to submit the second review and transmit that request to the user. In another example the process may aggregate the user reviews and analyze the aggregated user reviews.

The exemplary computer system includes a processor e.g. a central processing unit CPU a graphics processing unit GPU or both a main memory e.g. read only memory ROM flash memory dynamic random access memory DRAM such as synchronous DRAM SDRAM or Rambus DRAM RDRAM etc. and a static memory e.g. flash memory static random access memory SRAM etc. which communicate with each other via a bus .

The computer system may further include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alphanumeric input device e.g. a keyboard a cursor control device e.g. a mouse a disk drive unit a signal generation device e.g. a speaker and a network interface device .

The disk drive unit includes a computer readable medium on which is stored one or more sets of instructions e.g. software embodying any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processor during execution thereof by the computer system the main memory and the processor also constituting computer readable media.

The software may further be transmitted or received over a network via the network interface device .

While the computer readable medium is shown in an exemplary embodiment to be a single medium the term computer readable medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term computer readable medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of the present invention. The term computer readable medium shall accordingly be taken to include but not be limited to solid state memories and optical and magnetic media.

It should be noted that the review system is illustrated and discussed herein as having various modules which perform particular functions and interact with one another. It should be understood that these modules are merely segregated based on their function for the sake of description and represent computer hardware and or executable software code which is stored on a computer readable medium for execution on appropriate computing hardware. The various functions of the different modules and units can be combined or segregated as hardware and or software stored on a computer readable medium as above as modules in any manner and can be used separately or in combination.

It should be understood that processes and techniques described herein are not inherently related to any particular apparatus and may be implemented by any suitable combination of components. Further various types of general purpose devices may be used in accordance with the teachings described herein. It may also prove advantageous to construct specialized apparatus to perform the method steps described herein. The present invention has been described in relation to particular examples which are intended in all respects to be illustrative rather than restrictive. Those skilled in the art will appreciate that many different combinations of hardware software and firmware will be suitable for practicing the present invention.

Moreover other implementations of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. Various aspects and or components of the described embodiments may be used singly or in any combination. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

