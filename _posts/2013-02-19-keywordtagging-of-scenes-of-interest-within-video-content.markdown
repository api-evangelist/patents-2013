---

title: Keyword-tagging of scenes of interest within video content
abstract: Extraction of scenes of interest from video content is disclosed, which includes: collecting comments from a comment server, which contain keywords associated with the video content; segmenting the video content into scenes; measuring the number of ones of the comments which were posted for each scene, as a post count; detecting ones of the scenes, each of which has the post count equal to or larger than a predetermined number, as a plurality of scenes of interest; extracting, per each scene-of-interest, at least one of the keywords which is contained in the comments with a number equal to or larger than a pre-selected number, as a comment keyword; and tagging each scene of interest with the comment keyword, per each scene-of-interest.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09008489&OS=09008489&RS=09008489
owner: KDDI Corporation
number: 09008489
owner_city: Tokyo
owner_country: JP
publication_date: 20130219
---
This application claims priority to U.S. Provisional Application No. 61 600 214 filed 17 Feb. 2012 entitled KEYWORD TAGGING OF SCENES OF INTEREST WITHIN VIDEO CONTENT which is hereby incorporated herein by reference in its entirety.

This application is related to Japanese Patent Application Nos. 2011 002513 filed 7 Jan. 2011 and 2011 086785 filed 5 Apr. 2011 each of which is hereby incorporated herein by reference in its entirety.

The invention relates to techniques of performing extraction of scenes of interest from video or motion picture content such as TV broadcast content or content from a video sharing website from a user s viewpoint.

In recent years a variety of pieces of video content have been delivered to a large audience via TV broadcasting or the Internet. Such video content is any type of media content such as TV broadcast content or content from a video sharing website.

For example in the case of TV broadcast content the TV broadcast content contains not only audio video information representative of a broadcast program but also caption or subtitle teletext information appearing in synchronization with the audio video information. The caption teletext information is typically a short text message of a summary of the broadcast program and the message contains keywords that represent the audio video information appropriately. The caption teletext information is provided by a content provider.

In addition a large audience is actively posting their comments to a website such as a blog web log or a mini blog mini web log e.g. Twitter Registered Trademark via the Internet. These comments are characterized in that they share the same topic for discussion. The shared topic includes video content delivered to the large audience as described above.

While many users are viewing video content for example they can discuss the video content that is being broadcast via a mini blog or the like. In recent years such a viewing habit has become more popular that while viewing TV broadcast content e.g. a drama for example users post their comments on the TV broadcast content via a mini blog. This makes many users to feel that they are viewing one piece of video content as a shared content.

In addition it is possible to extract keywords that interest many viewers of the same piece of TV broadcast content from comments that those viewers have posted to a blog site resulting in collection of comments. Those keywords are for example hash tags in the case of Twitter for example.

It is noted that there is a conventional technique of detecting scenes of interest peaks based on the number of comments posted i.e. the number of tweets in the case of Twitter and partitioning video content see Non patent Literature No. 1 David A. Shamma Lyndon Kennedy and Elizabeth F. Churchill Tweet the Debates Proc WSM 09 Oct. 23 2009 for example into segments. This technique allows estimation of the content of each one of scene segments from its number of tweets.

This technique of Non patent Literature No. 1 applies to a discussion event such as a debate. For example a hypothetical event is considered in which in video content opinion of a first leader is followed by opinion of a second leader. In this event the audience continues posting their first comments on the first leader s opinion even when the second leader is presenting her or his opinion. Non patent Literature No. 1 is for correcting a temporal deviation temporal difference between when each scene of the video content appears and when the associated posts are counted.

From a different standpoint there are also many cases where some viewers cannot view TV broadcast content for example in realtime but they need to view only scenes of interest by scene extraction. Video content is content that is to be viewed in a time sequential manner and abbreviated content provided by extracting only scenes of interest from the video content is delivered by a content provider. In contrast there is also a technique of extracting highlights using an image feature based approach see Non patent Literature No. 2 Alan Hanjalic Adaptive Extraction of Highlights From a Sport Video Based on Excitement Modeling IEEE Transactions on Multimedia Vol. 7 No. 6 December 2005 for example . This technique allows highlights extraction by analysis of features of motion pictures themselves of a TV program.

However it is desirable that scenes of interest be selected based on a user s viewpoint in every possible case. In addition tagging scenes of interest with comment keywords based on a user s viewpoint promotes the user s understanding while viewing. Additionally the use of such comment keywords enables the user to search for scenes of interest to thereby allow the user to view various scenes of interest. It is added that the technique of Non patent Literature No. 2 allows analytical processing for image feature extraction with a vast number of computational operations which cannot extend to calculation for estimating the content of the motion pictures themselves.

Therefore it is desirable to tag scenes of interest that are selected from video content broadcast sequentially from a user s viewpoint to indicate the content of the video content.

According to the present invention the following modes are provided. These modes will be stated below such that these modes are divided into sections and are numbered and such that these modes depend upon other mode s where appropriate. This facilitates a better understanding of some of the plurality of technical features and the plurality of combinations thereof disclosed in this specification and does not mean that the scope of these features and combinations should be interpreted to limit the scope of the following modes of the invention. That is to say it should be interpreted that it is allowable to select the technical features which are stated in this specification but which are not stated in the following modes as technical features of the invention.

Furthermore reciting herein each one of the selected modes of the invention in a dependent form so as to depend from the other mode s does not exclude the possibility of the technical features in the dependent form mode from becoming independent of those in the corresponding dependent mode s and to be removed therefrom. It should be interpreted that the technical features in the dependent form mode s may become independent according to the nature of the corresponding technical features where appropriate.

 1 A method for use in a device of receiving video content to be published of extracting scenes of interest from the video content the method comprising 

a comment collection step of collecting a plurality of comments with posting timestamps indicating times at which the comments were posted from a comment server the comments containing keywords associated with the video content 

a post counting step of segmenting the video content into a plurality of scenes each having a predetermined time duration and of measuring a number of ones of the plurality of comments which were posted during a time zone of each scene as a post count 

a scene of interest detection step of detecting ones of the plurality of scenes each of which has the post count equal to or larger than a predetermined number as a plurality of scenes of interest 

a comment keyword extraction step of extracting per each scene of interest at least one of the keywords which is contained in the plurality of comments with a number equal to or larger than a pre selected number as a comment keyword and

a comment tagging step of tagging each scene of interest with the comment keyword per each scene of interest.

 2 The method according to mode 1 wherein the comment keyword extraction step comprises a sub step of extracting per each scene of interest words from the plurality of comments by morphological analysis and of extracting distinctive words per each scene of interest using TF TDF Term Frequency Inverse Document Frequency as the comment keyword.

a sub step of extracting per each scene of interest a part of speech of a person s name among the distinctive words by the morphological analysis and

a sub step of extracting per each scene of interest an important word having the largest score of the TF IDF among the distinctive words by the morphological analysis and

the comment tagging step comprises a sub step of tagging each scene of interest with the comment keyword in the form of the part of speech of the person s name and the important word per each scene of interest.

a sub step of extracting each scene as the scene of interest if the each scene has the post count equal to or larger than a sum of the average and the standard deviation .

 5 The method according to any one of modes 1 4 further comprising an abbreviated content generation step of generating abbreviated content representative of an abbreviated version of the video content by combining at least some of the scenes of interest.

a post count graph generation step of generating a post count graph representative of a time varying number of the posts such that the post count graph is tagged with the comment keywords at selected points in time by referencing a scene of interest storage storing the scenes of interest and

a post count graph transmission step of transmitting the post count graph to a viewer s terminal equipment allowing the viewer to view the video content.

 7 The method according to mode 6 further comprising a requested keyword reception step of receiving a requested keyword from the terminal equipment wherein the post count graph generation step comprises a sub step of tagging the post count graph with ones of the comment keywords which contain the requested keyword.

 8 The method according to mode 7 wherein the post count graph generation step comprises a sub step of generating a post count graph representative of only numbers of ones of the plurality of comments which contain the requested keyword.

 9 The method according to any one of modes 6 8 further comprising a scene of interest transmission step of transmitting to the terminal equipment only ones of the scenes of interest which are tagged with the requested keyword.

 10 The method according to any one of modes 6 9 further comprising a comment transmission step of transmitting to the terminal equipment ones of the plurality of comments which correspond to ones of the scenes of interest which are tagged with the requested keyword received from the terminal equipment.

 11 The method according to any one of modes 6 10 wherein the post count graph generation step comprises 

a sub step of calculating a ratio number of users posted total post count of a number of users who posted the plurality of comments to a total number of the plurality of comments for ones of the scenes of interest which are tagged with the comment keywords on the post count graph and

a sub step of displaying the comment keywords with which the scenes of interest are tagged such that each comment keyword is visually emphasized at an increasing emphasis level as the ratio of the associated one of the tagged scenes of interest increases.

 12 The method according to any one of modes 6 10 wherein the post count graph generation step comprises 

a sub step of calculating a ratio number of quotations total post count of a number of ones of the plurality comments which have quotation to a total number of the plurality of comments for ones of the scenes of interest which are tagged with the comment keywords on the post count graph and

a sub step of displaying the comment keywords with which the scenes of interest are tagged such that each comment keyword is visually emphasized at an increasing emphasis level as the ratio of the associated one of the tagged scenes of interest increases.

 13 The method according to any one of modes 6 12 wherein the video content includes at least one of TV broadcast content and content from a video sharing website and the comment server includes a mini blog mini Web log server.

 14 The method according to mode 13 wherein the mini blog server is a Twitter Registered Trademark server and the comment collection step comprises a sub step of collecting the plurality of comments containing hash tags based on the video content from the Twitter server.

 15 A server for receiving video content to be published and extracting scenes of interest from the video content comprising 

a collector that collects a plurality of comments with posting timestamps indicating times at which the comments were posted from a comment server the comments containing keywords associated with the video content 

a post counter that segments the video content into a plurality of scenes each having a predetermined time duration and measures a number of ones of the plurality of comments which were posted during a time zone of each scene as a post count 

a scene of interest detector that detects ones of the plurality of scenes each of which has the post count equal to or larger than a predetermined number as a plurality of scenes of interest 

a comment keyword extractor that extracts per each scene of interest at least one of the keywords which is contained in the plurality of comments with a number equal to or larger than a pre selected number as a comment keyword 

a comment tagger that tags each scene of interest with the comment keyword per each scene of interest and

a scene of interest delivery unit that delivers the tagged scenes of interest upon reception of a request from a viewer s terminal equipment allowing the viewer to view the video content.

a collector collects a plurality of comments with posting timestamps indicating times at which the comments were posted from a comment server the comments containing keywords associated with the video content 

a post counter that segments the video content into a plurality of scenes each having a predetermined time duration and measures a number of ones of the plurality of comments which were posted during a time zone of each scene as a post count 

a scene of interest detector that detects ones of the plurality of scenes each of which has the post count equal to or larger than a predetermined number as a plurality of scenes of interest 

a comment keyword extractor that extracts per each scene of interest at least one of the keywords which is contained in the plurality of comments with a number equal to or larger than a pre selected number as a comment keyword and

a comment tagger that tags each scene of interest with the comment keyword per each scene of interest.

 17 A non transitory storage medium having stored a program executed by a computer for implementing a method for use in a device of receiving video content to be published of extracting scenes of interest from the video content 

a comment collection step of collecting a plurality of comments with posting timestamps indicating times at which the comments were posted from a comment server the comments containing keywords associated with the video content 

a post counting step of segmenting the video content into a plurality of scenes each having a predetermined time duration and of measuring a number of ones of the plurality of comments which were posted during a time zone of each scene as a post count 

a scene of interest detection step of detecting ones of the plurality of scenes each of which has the post count equal to or larger than a predetermined number as a plurality of scenes of interest 

a comment keyword extraction step of extracting per each scene of interest at least one of the keywords which is contained in the plurality of comments with a number equal to or larger than a pre selected number as a comment keyword and

a comment tagging step of tagging each scene of interest with the comment keyword per each scene of interest.

It is noted here that as used in this specification the singular form a an and the include plural reference unless the context clearly dictates otherwise. It is also noted that the terms comprising including and having can be used interchangeably.

Some of the more specific embodiments of the invention will be described in the following in more detail with reference to the drawings in which like numerals are used to indicate like elements throughout.

As illustrated in a content publishing server delivers video content to a large number of viewers over the air or the Internet. The video content may be for example TV broadcast content or content from a video sharing website. TV broadcast content which is broadcast over the air is delivered by terrestrial digital broadcasting one segment broadcasting BS Broadcast Satellite etc. In addition content from a video sharing website which is broadcast over the Internet is delivered by live video streaming based on for example Upstream Registered Trademark .

Terminal equipment receives video content delivered from the content publishing server over the air or the Internet and plays it back. A user can view video content played back by the terminal equipment . The terminal equipment may be a TV set a mobile phone a smart phone etc. The terminal equipment may receive video content through a set top box that receives broadcasting waves or through a router that is connected with an access network. It is added that the terminal equipment will be described below as a mobile terminal such as a smart phone.

As illustrated in a mini blog server serving as a comment server is connected with the Internet. The mini blog server is for example a Twitter website server. A large number of viewers can each post comments to the mini blog server while viewing video content through the terminal equipment . In addition each user can view comments that other posted to the mini blog server without permission.

In an example these comments are written in Japanese language in which word boundaries are not indicated by blank spaces.

In addition as illustrated in a scene of interest extraction server which is a part of the present embodiment is also connected with the Internet. The scene of interest extraction server receives video content from the content publishing server and collects comments associated with the video content from the mini blog server . The scene of interest extraction server extracts scenes of interest in the video content based on the comments posted in association with the video content. And the scenes of interest can be tagged to indicate the content of the associated comment. The scene of interest extraction server delivers scenes of interest in the video content in response to reception of a request from the terminal equipment .

The content publishing server delivers video content toward a large number of viewers. Sets of the terminal equipment which are held by the large number of viewers play back the video content on a display see which has been received by the terminal equipment over the air or the Internet.

 S A user who is viewing the video content can post a plurality of comments associated with the video content via the terminal equipment to the mini blog server . The mini blog server stores the plurality of comments received by the mini blog server and publishes the plurality of comments to a large number of viewers.

 S The scene of interest extraction server collects a plurality of comments associated with the video content from the mini blog server . A plurality of comments containing keywords associated with the video content are collected from a comment server in combination with their posting timestamps indicating times at which the plurality of comments were posted. In an example of a Twitter website server a plurality of comments i.e. tweets containing a designated keyword can be retrieved. For example to search for tweets containing a keyword tigers the following URL Uniform Resource Locator is designated 

In addition when Twitter is used for collection of a plurality of comments associated with video content only comments with an added hash tag the symbol and a string of alphabetical characters associated with the video content can be collected. When Twitter is used the use of a hash tag allows topics to be shared which can cluster comments with the addition of the same hash tag. For example to search for tweets with an added hash tag tigers the following URL is designated 

In addition the designation of a date allows search for up to one week s worth of tweets. Documentation of the Twitter API Application Programming Interface is known.

 S The video content is segmented into a plurality of scenes each having a predetermined time duration and the number of ones of the plurality of comments which were posted during a time zone of each scene is measured as a post count. In an example post counts are measured at time intervals of 2 minutes.

 S Next ones of the plurality of comments each of which has the post count equal to or larger than a predetermined number are extracted as a plurality of scenes of interest. Not only scenes exceeding the predetermined number increasingly exciting scenes with a rapid increase in the post count can be also detected. For detection of such scenes of interest the Newton method known as a gradient method can be desirably used. The Newton Raphson method is used to solve an approximated value of the point of intersection of a function f x with an x axis x intercept by iterative calculation.

In a more specific implementation an average and a standard deviation a of a post count are desirably used for each of the scenes e.g. occurring at time intervals of 2 minutes .

The average is a mean value calculated for each of the scenes e.g. occurring at time intervals of 2 minutes in an example within a predetermined time window e.g. with a 10 muniute long duration in the example smoothing . For example the average is calculated by dividing the number of posts collected for one time window by the number of scenes belonging to the one time window e.g. five in the above example and the calculated average is kept constant between the scenes belonging to the one time window.

The standard deviation is referred to the square root of the dispersion of posts for each scene. The dispersion is referred to the square of differences between the actual post counts and the average of the post counts which represents how spread out a distribution of the actual post counts. The standard deviation can vary between the scenes belonging to the one time window. And if per each of the scenes the post count is equal to or larger than the sum of the average p and the standard deviation the each scene is extracted as a scene of interest that is determined by reference to post counts as an exciting scene.

As illustrated in on the graph a dotted line represents the sum of average and standard deviation . Fractions of the post counts which are above the dotted line are illustrated with each of which indicates a scene of interest or an exciting scene.

 S Next comment keywords are extracted which are contained in a plurality of comments with a number equal to or larger than a predetermined number per each scene of interest. In this implementation a plurality of words are extracted from the plurality of comments by morphological analysis. The morphological analysis is referred to a method of segmenting a text into words each having semantic meaning and determining the part of speech and the content of each word using a dictionary. The morpheme is referred to the smallest linguistic unit that has semantic meaning among a plurality of units forming a text.

In this regard the morphological analysis may be performed using for example open source morphological analyzer engine MeCab. This engine which uses a hierarchy of parts of speech also allows analysis of parts of speech of morphemes. This has the function called word segmentation by software that can generate any possible morpheme stings of an inputted sentence with marginal probabilities. As a result this determines parts of speech such as noun unique noun organization district general . . . etc. per each morpheme.

In this regard in the present embodiment it is also desirable to perform extraction for the part of speech of person s name which is one of distinctive words by the morphological analysis. Within a scene a person s name is the most exemplary among distinctive words.

Then distinctive words are extracted as comment keywords by TF IDF Term Frequency Inverse Document Frequency . The TF IDF is referred to a method of representing a document with a query by giving a weight to each word and ranking the document by a similarity score between the document and the query. It is recognized that the larger the score by the ranking the more likely the word is to be important. In other words what video content is like is appropriately represented by frequencies of keywords appearing in a document.

Per each scene of interest an important word having the largest score of the TF IDF among the distinctive words is extracted by the morphological analysis. In this regard it is desirable to extract at least 1 distinctive words featured by a part of speech of person s name by the morphological analysis and 2 other distinctive words.

 S Then each scene of interest is tagged with words featured by a part of speech of person s name and other distinctive words each serving as a comment keyword per each scene of interest. This allows each scene of interest to be tagged with key character and important words per each scene of interest which makes it easier to understand scenes that excite a user.

 S A plurality of scenes of interest which have been tagged with comment keywords are stored in a scene of interest storage. The comment keywords that the plurality of scenes of interest have been tagged with are used not only for the user s understanding but also as search keys used for searching the scene of interest storage.

 S Optionally abbreviated content representative of an abbreviated version of the video content is generated by combining a sub plurality of scenes of interest. Video content featured by the graph of is 260 minutes 4 hours and 20 minutes long while 36 minute long abbreviated content is generated by combining only 18 scenes of interest.

The scene of interest extraction server transmits scenes of interest in particular video content in response to reception of a request from the terminal equipment by the user s operation. This allows the user to view only desired scenes of interest using the terminal equipment . The scene of interest extraction server searches the scene of interest storage in response to reception of a requested keyword from the terminal equipment and transmits associated ones of the scenes of interest to the terminal equipment .

As illustrated in the scene of interest extraction server includes a communications interface connected with the Internet a comment collector a post counter a scene of interest detector a comment keyword extractor a comment tagger a scene of interest storage and an abbreviated content generator . These functional constituents are implemented by executing a predetermined program with a computer a processor and a memory built in the scene of interest extraction server . It is of course that these functional constituents may be implemented by executing the program with a computer not shown built in the terminal equipment as illustrated in in parentheses.

The comment collector collects a plurality of comments with posting timestamps indicating times at which the comments were posted from a comment server e.g. a Twitter website server wherein the comments contain keywords associated with the video content in the similar manner with the above described S of . As illustrated in comments are collected such as for example NAKAZAWA always starts good . . . The first inning s strikeouts are followed by a mountain of mishits . . . NAKA Get a strikeout . . . . . . NAKAZAWA . . . good from the first inning . . . . Collected comments are delivered to the post counter .

The post counter segments the video content into a plurality of scenes each having a predetermined time duration and measures the number of ones of the plurality of comments which were posted during a time zone of each scene as a post count in the similar manner with the above described S of . As illustrated in the graph of for example posts are counted per each scene e.g. at time intervals of 2 minutes as post counts. The post counts are delivered to the scene of interest detector per each scene.

The scene of interest detector detects ones of the plurality of scenes each of which has the post count equal to or larger than a predetermined number as a plurality of scenes of interest in the similar manner with the above described S of . As illustrated in the graph of for example if each scene has the post count equal to or larger than a sum of the average and the standard deviation the each scene is detected as a scene of interest. The detected scenes of interest are delivered to the comment keyword extractor .

The comment keyword extractor extracts per each scene of interest at least one of the keywords which is contained in the plurality of comments with a number equal to or larger than a pre selected number as a comment keyword in the similar manner with the above described S of . As illustrated in for one of the scenes of interest per word count values which may be replaced with TF IDF scores obtained by the morphological analysis are specially depicted.

In an example depicted in each of the per word count values includes per each word a scene specific frequency i.e. how often each word appears in each scene a total frequency and a TF IDF score of each word.

In this implementation the comment keyword extractor extracts a word that is featured by a part of speech of a person s name and has the higher TF IDF score than a threshold and a word that is not featured by a person s name and has the higher TF IDF score than a threshold. Then as illustrated in the number of times that a word featured by the part of speech of the person s name and a word not featured by a person s name concurrently occur i.e. co occurrence frequency is specially depicted. The comment keyword extractor delivers a set of words co occurring the most frequently to the comment tagger .

In this example depicted in a pair of NAKAZAWA and START is selected as the most frequent co occurring pair and is delivered to the comment tagger .

Further in this example first step word extraction is performed for identifying one or more key characters or important persons and then second step word extraction is performed for one or more key events or important events in association with the previously identified one or more key characters with improved extraction efficiency.

The comment tagger tags each scene of interest with a comment keyword in the similar manner with the above described S of . The comment tagger tags each scene of interest with a comment keyword in the form of a part of speech of a person s name and an important word per each scene of interest.

The scene of interest storage stores scenes of interest which have been tagged with comment keywords. The comment keywords are also used as search keys for searching for scenes of interest.

The abbreviated content generator generates abbreviated content of the video content by combining a sub plurality of scenes of interest. The generated abbreviated content is stored in the scene of interest storage .

 S The scene of interest extraction server generates a post count graph representative of a time varying number of the posts. The post count graph is tagged with the comment keywords at selected points in time by referencing the scene of interest storage .

On the graph of post counts are taken along the vertical axis while points in time during a time lapse are taken along the horizontal axis. Further per each of selected points in time comment keywords that have been used for tagging are depicted. This post count graph is generated to serve as information represented by an image helping the user understand this graph directly through the image. Glancing at this post count graph helps the user understand temporal changes in the post count even when the video content is relatively long. Further it allows the user to learn major comment keywords in scenes of interest.

 S The scene of interest extraction server transmits the generated post count graph to the terminal equipment . On the display of the terminal equipment the post count graph is displayed.

As illustrated in on the display of the terminal equipment in the form of a smart phone a video display region a post count graph display region key character select buttons and key event select buttons are displayed. On the video display region video content that has been received from the content publishing server is played back. On the post count graph display region a post count graph that has been received from the scene of interest extraction server is displayed.

The key character select buttons and the key event select buttons are assigned keywords that appear relatively frequently in comment keywords attached to a post count graph for tagging and the user can select one of those eight buttons and .

In an example depicted in the terminal equipment is configured to automatically select three key character keywords and three key event keywords from a group of comment keywords attached to a post count graph for tagging which appear more frequently than other keywords in the same group and automatically assign the selected three key character keywords and the selected three key event keywords to the first three ones of the four key character select buttons and the first three ones of the four key event select buttons respectively.

In this example depicted in the remaining one of the four key character select buttons is selected by the user to display on the display screen all the key characters contained in the group of comment keywords and the remaining one of the four key event select buttons is selected by the user to display on the display screen all the event characters contained in the group of comment keywords.

The user s touch onto a desired one of the eight buttons and which has been assigned a desired keyword allows a scene of interest containing the keyword to be played back and also allows the user to visually conceive the number of comments associated with only the keyword.

 S It is presumed that the user touches one of the key character select buttons and the key event select buttons which are being displayed on the display of the terminal equipment . The terminal equipment transmits a keyword corresponding to the user selected button or as a requested keyword to the scene of interest extraction server . The scene of interest extraction server retrieves scenes of interest associated with the requested keyword from the scene of interest storage .

It is added that alternatively as illustrated in in dotted line the user may view a post count graph displayed on the terminal equipment and enter a selected point in time. In this mode the terminal equipment transmits the selected point in time to the scene of interest extraction server . The scene of interest extraction server retrieves one of the scenes of interest which is associated with the selected point in time from the scene of interest storage .

In this stage as illustrated in in dotted line S and S may be executed again. The scene of interest extraction server may tag a post count graph with only comment keywords containing the requested keyword. And the scene of interest extraction server may generate a post count graph representative of only the number of comments containing the requested keyword.

 S The scene of interest extraction server transmits scenes of interest tagged with the requested keyword to the terminal equipment .

 S Further the scene of interest extraction server transmits to the terminal equipment comments posted in association with the scenes of interest tagged with the requested keyword which have been received from the terminal equipment .

The post count graph of is displayed on the display of the terminal equipment when the user operates the terminal equipment in the following manner 

As a result the user can understand at first sight which one of scenes of interest many comments appear in wherein each comment contains a keyword representative of a key character to who the user pays attention.

In addition a seek bar is also displayed on the display screen which moves as a time elapses while video content is being played back.

The post count graph of is displayed on the display of the terminal equipment when the user operates the terminal equipment in the following manner 

As a result the user can understand at first sight which one of scenes of interest many comments appear in wherein each comment contains a keyword representative of a key event to who the user pays attention.

The post count graph of is displayed on the display of the terminal equipment when the user operates the terminal equipment in the following manner 

Also for the post counts the numbers of comments containing NAKAZAWA as a keyword are displayed on the display screen at discrete points in time.

As a result the user can understand at first sight which one of scenes of interest many comments appear in wherein each comment contains a keyword representative of a NAKAZAWA to who the user pays attention.

As illustrated in the graph of comment keywords that scenes of interest on the graph have been tagged with are displayed on the display screen such that the comment keywords are visually emphasized at different emphasis levels between the comment keywords. In this stage for each scene of interest that has been tagged with a comment keyword on the graph a ratio i.e. posted user number total post number of the number of users who posted their comments to the total number of the posted comments in association with the each scene of interest is calculated. Then each comment keyword is displayed on the display screen such that the each comment keyword is visually emphasized at an increasing emphasis level as the ratio of a scene of interest tagged with the each comment keyword increases. For example the displaying is performed so that a label is collared conspicuously. As the ratio of the number of people who posted comments in association with a scene of interest increases a comment keyword that the scene of interest is tagged with is displayed on the display screen with greater visual emphasis.

In an example fifty comments e.g. fifty tweets in the case of Twitter were posted in association with a first scene of interest while fifty users posted the comments each user posted only one comment and the ratio is 50 50 1. Further fifty comments were posted in association with a second scene of interest while twenty users posted the comments each user posted 2.5 comments on the average and the ratio is 20 50 0.4. In this example a comment keyword for the first scene of interest is displayed on the display screen with greater visual emphasis than a comment keyword for the second scene of interest.

As illustrated on the graph of comment keywords that scenes of interest on the graph have been tagged with are displayed on the display screen such that the comment keywords are visually emphasized at different emphasis levels between the comment keywords. In this stage for each scene of interest having been tagged with comment keywords on the graph a ratio i.e. quotation number total post number of the number of ones of the posts which have been made by post quotation to the total number of the posted comments in association with the each scene of interest is calculated. Then each comment keyword is displayed such that the each comment keyword is visually emphasized at an increasing emphasis level as the ratio of a scene of interest tagged with the each comment keyword increases. For example the displaying is performed so that a label is collared conspicuously.

The post quotation is referred to for example ReTweet in the case of Twitter. ReTweet is referred to incorporation of others posted comments i.e. Tweets into my comment by quotation or reference. A comment keyword is displayed on the display screen with visual emphasis when a scene of interest has a comment made by many quotations and when the scene of interest has been tagged with the comment keyword.

In an example fifty comments e.g. fifty tweets in the case of Twitter were posted in association with a first scene of interest while twenty ones of the associated comments are made by quotation and the ratio is 20 50 0.4. Further fifty comments were posted in association with a second scene of interest while ten ones of the associated comments are made by quotation and the ratio is 10 50 0.2. In this example a comment keyword for the first scene of interest is displayed on the display screen with greater visual emphasis than a comment keyword for the second scene of interest.

The post count graph of is displayed on the display of the terminal equipment when the user operates the terminal equipment in the following manner 

Then it is presumed that the user designates one of the displayed keywords. The designation may be a click event via a pointing device or a long press event. This allows the seek bar to jump to a scene of interest having the designated keyword.

As illustrated in comments are displayed on the video display region of the display of the terminal equipment . For example tweets are displayed in the case of Twitter. This allows the user to view the posted comments.

As illustrated in the scene of interest extraction server includes in addition to the functional constituents depicted in a post count graph generator a post count graph transmitter a requested keyword receiver a scene of interest transmitter and a comments transmitter . These functional constituents are implemented by executing a predetermined program with the computer built in the scene of interest extraction server .

The post count graph generator generates a post count graph that is representative of a time varying post count and that is tagged with comment keywords at selected points in time by referencing the scene of interest storage see the above described S of . In this regard the post count graph generator may tag the post count graph with only comment keywords containing a requested keyword. And the post count graph generator may generate a post count graph representative of only the number of comments containing a requested keyword. The generated post count graph is transmitted to the post count graph transmitter .

The post count graph transmitter transmits the post count graph to the terminal equipment see the above described S of .

The requested keyword receiver receives a requested keyword from the terminal equipment see the above described S of . The requested keyword is delivered to the post count graph generator and the scene of interest transmitter . It is noted that the requested keyword receiver may receive a selected point in time from the terminal equipment . This is a time at which a scene of interest is played back according to a request from the user through the terminal equipment . The selected point in time at which a scene of interest is played back according to a request is delivered to the scene of interest transmitter .

The scene of interest transmitter transmits to the terminal equipment only scenes of interest tagged with a requested keyword by referencing the scene of interest storage see the above described S of . The scene of interest transmitter also transmits a scene of interest associated with a selected point in time to the terminal equipment .

The comments transmitter transmits to the terminal equipment comments associated with scenes of interest tagged with a requested keyword received from the terminal equipment by referencing the scene of interest storage see the above described S of .

As described above in detail the present embodiment allows extraction of scenes of interest exciting scenes from video content being broadcast sequentially by referencing the number of comments e.g. twitters that have been posted e.g. the number of tweets attached with a hash tag from a user s viewpoint and allows tagging of the scenes of interest with their comment keywords. Each comment keyword is comprised of a person s name and an important word. The user can view a scene of interest together with a keyword that briefly indicates the content of the scene of interest promoting the user s understanding of the scene of interest. The use of a comment keyword that scenes of interest are tagged with to serve as a keyword tag enables the user to search for scenes of interest to thereby allow the user to view various scenes of interest.

Additionally the user can learn through the post count graph when each scene of interest appears within the full time length of video content and the user can view only scenes of interest associated with the user designated desired keyword.

Although the embodiments have been described above with comments written in Japanese language the invention may be practiced when comments are written in English language or other languages e.g. Chinese language Korean language or German language .

However for analyzing comments written in language such as English language in which word boundaries are indicated by blank spaces without any need for word segmentation the invention may be practiced by completely or partially abbreviating the whole process of the above described Morphological Analysis.

Reference throughout the specification to one embodiment or an embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention.

Thus the appearance of the phrases in one embodiment or in an embodiment in various places throughout the specification are not necessarily all referring to the same embodiment. Furthermore the particular features structures or characteristics may be combined in any suitable manner in one or more embodiments.

Moreover inventive aspects lie in less than all features of a single disclosed embodiment. Thus the claims following the Detailed Description are hereby expressly incorporated into this Detailed Description with each claim standing on its own as a separate embodiment of this invention.

The present specification provides a complete description of the methodologies systems and or structures and uses in exemplary implementations of the presently described technology. Although various implementations of this technology have been described above with a certain degree of particularity or with reference to one or more individual implementations those skilled in the art could make numerous alterations to the disclosed implementations without departing from the spirit or scope of the technology thereof. Furthermore it should be understood that any operations may be performed in any order unless explicitly claimed otherwise or a specific order is inherently necessitated by the claim language. It is intended that all matter contained in the above description and shown in the accompanying drawings shall be interpreted as illustrative only of particular implementations and are not limiting to the embodiments shown. Changes in detail or structure may be made without departing from the basic elements of the present technology as defined in the following claims.

