---

title: Dynamic hyperlinking approach
abstract: A method of returning target scenes from a user link request is disclosed. The method comprises the steps of: receiving a user link request on a user interface; comparing the received user link request to a plurality of entries in a lookup table; for each entry in the plurality of entries in the lookup table that matches the received user link request, identifying a target scene that corresponds to the matched entry in the lookup table; determining a closest one of the target scenes if multiple entries in the lookup table match the user link request; and transitioning to the closest target scene.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09344763&OS=09344763&RS=09344763
owner: HILLCREST LABORATORIES, INC.
number: 09344763
owner_city: Rockville
owner_country: US
publication_date: 20130917
---
This application claims the benefit of U.S. Provisional Patent Application No. 60 683 099 filed on May 20 2005 and entitled Dynamic Hyperlinking Approach which is herein incorporated by reference in its entirety.

This application is a continuation of and claims priority from U.S. patent application Ser. No. 11 438 520 filed on May 22 2006 entitled Dynamic Hyperlinking Approach . This application is also related to and claims priority from U.S. patent application Ser. No. 11 119 663 filed on May 2 2005 entitled Freespace Pointing Devices and Methods now U.S. Pat. No. 7 239 301 issued Jul. 3 2007 referred to herein as the 663 application and Ser. No. 10 768 432 filed on Jan. 30 2004 entitled A Control Framework with a Zoomable Graphical User Interface for Organizing Selecting and Launching Media Items referred to herein as the 432 application . The subject matter of each of these applications is incorporated in its entirety herein by reference.

The present invention relates generally to user interfaces and methods associated therewith and more specifically to navigation between user interface icons organized in a hierarchical manner.

User interfaces are ubiquitous in today s society. Computers cell phones fax machines and televisions to name a few products all employ user interfaces. User interfaces are intended to provide a mechanism for users to easily access and manipulate the sometimes complex functionality of the devices that they support. An example of a user interface is found in U.S. patent application Ser. No. 10 768 432 filed on Jan. 30 2004 entitled A Control Framework with a Zoomable Graphical User Interface for Organizing Selecting and Launching Media Items the disclosure of which is incorporated here by reference. Typically such user interfaces employ remote handheld devices to provide inputs to their respective applications.

User interfaces facilitate navigation within an increasingly complex array of choices in a home entertainment system for example. Objects or icons within a user interface may be organized logically in a hierarchical manner. A user may select an icon on a home entertainment system user interface to indicate his or her desire to watch TV play computer games access the internet etc. via a monitor display for example. Once the choice for watching TV is indicated the user may be presented with icons for selection that represent broadcast channels premium channels sports channels etc. Each of these icons may be actuated to provide additional levels of choices. For example under broadcast channels the network channels may be presented.

As the choices and levels of organization of the interface objects icons increase it would be desirable to transition between user choices in a rapid manner.

In one embodiment a method of returning target scenes from a user link request is disclosed. The method comprises the steps of receiving a user link request on a user interface comparing the received user link request to a plurality of entries in a lookup table for each entry in the plurality of entries in the lookup table that matches the received user link request identifying a target scene that corresponds to the matched entry in the lookup table determining a closest one of the target scenes if multiple entries in the lookup table match the user link request and transitioning to the closest target scene.

The following detailed description of the invention refers to the accompanying drawings. The same reference numbers in different drawings identify the same or similar elements. Also the following detailed description does not limit the invention. Instead the scope of the invention is defined by the appended claims.

Exemplary embodiments of the present invention provide a method for navigating between and returning targets for user selections on a user interface. More specifically a closest target from potentially multiple targets is returned as described in more detail herein below. User interfaces as they pertain to exemplary embodiments are described first and specific exemplary methods for returning targets are then described.

An exemplary user interface UI is illustrated in . UI may include a plurality of icons each representing a choice for user selection. The user may highlight and depress or click one of these icons such as icon to indicate his or her preference for watching TV. A user input device may be utilized to perform this function. UI may function as the home or root user interface.

An exemplary input device or free space pointing device may resemble a mouse such as a wireless mouse depicted in . Button presses on mouse correspond to actuation of buttons and and scroll wheel for example.

Another exemplary free space pointing device may resemble a loop shaped device such as that illustrated in and designed by HillCrest Labs of Rockville Md. Free space pointing device includes buttons and and scroll wheel corresponding to buttons and and scroll wheel of .

Referring back to actuation of icon may result in displaying UI of . UI may present choices under the watch TV category of . The choices may include icons representing premium channels broadcast channels and sports channels for example. UI may also include navigational icons . Clicking on home icon may result in return to UI or home of for example.

If a user chooses to watch premium channels then actuation of icon may result in displaying UI of which may include icons corresponding to exemplary premium channels and navigational icons .

Actuation of icon on UI may result in displaying UI of which may include icons corresponding to exemplary genres and navigational icons . Actuation of icons and may result in displaying UI of respectively which may include icons and corresponding to exemplary movie titles and navigational icons . The movie titles are also exemplary and in some cases such as The Matrix Reloaded Preview and The Matrix Behind Scenes may be fictitious but may be based on actual movie titles and have been included for purely illustrative purposes.

While each of the icons are depicted as having an oval shape they are not restricted to this shape. The icons may be rectangular square circle or any other shapes. The icons may also be arranged in multiple rows as illustrated in user interface of in a rectangular shape which also includes navigational icons and .

For each movie title the user may wish to view the movie the user may also be presented with a description of the movie and or a list of related titles as illustrated on user interface in that also includes navigational icons and .

The user interface illustrated may be referred to as a zoomable user interface ZUI since highlighting one of a plurality of icons magnifies the highlighted icon in exemplary embodiments as illustrated in user interface of for example which also includes navigational icons and . The 432 application describes the zoomable aspect.

An overall exemplary hierarchical structure for the icons of is illustrated as nodes in a tree in . For the purposes of this invention each node may be referred to as a scene. The illustration of is purely illustrative and not exhaustive. In implementation several additional networks may be available i.e. besides HBO and SHOWTIME for each network additional genres may be available for each genre additional movie titles besides the two that are illustrated may be available.

The language definition for each scene is represented as a scalable vector graphic SVG . SVGs are used as they describe shapes on a display page movements on a display page and location of graphics as they appear on a display page within a graphical display.

Programming information for a particular channel network may be received by the server from the respective network on a periodic basis. Such programming may be dynamic in nature. That is a movie title under the action genre for HBO for one period a week or a month may differ from a movie title under the action genre for HBO for a second period.

Each of the nodes scenes may have a unique description or definition that may be stored in a server. The scene definition therefore may rely on information received from the networks. The scene representing The Terminator in may have the exemplary definition home SHOWTIME movies sci fi The Terminator.

The scene representing The Matrix may have the following two exemplary definitions since The Matrix occurs twice home SHOWTIME movies sci fi The Matrix and home HBO movies action The Matrix.

The definition in this exemplary embodiment may be in a folder subfolder type of hierarchy. Other formats may also be used to define the scenes. The definition for a scene may be viewed as the path from the home location to the scene location. The server may store a description or definition for all scenes that are currently available.

In the example described above a plurality of generic identifiers may be assigned under the genre. The generic identifiers may be termed as movie movie . . . movie n. The generic identifiers may have different movies associated with them based on programming for a particular time period. For the month of November 2005 for example movie may correspond to The Matrix and movie may correspond to Mission Impossible In April 2006 movie may correspond to Spiderman and movie may correspond to Mission Impossible II .

Each of the program titles such as Mission Impossible and The Matrix may have unique identification associated therewith such as a numeric or an alphanumeric code for example. Such identification may be included in metadata corresponding to the movie and may be received or known by the server.

A user highlighting The Matrix under HBO Movies Action for example may also be presented with related titles. The related titles movies may be those having similar story lines genre or those having common actors etc. The related titles movies may also be included in the metadata received by the server.

A user wishing to obtain information such as a preview clip or description or to view play a related movie may click on an icon representing the related movie movie movie etc. of . This may serve as a user link request. The request for information on and for viewing of the related movie movie for example may be represented on the movie icon for example.

For each movie title or program available on the server an entry may be created in a lookup table based on an identification generated by the server representing a user link request. Separate entries may be created for each aspect of a particular title. The separate aspects may be movie information such as preview and movie play for example. For each of these entries a location i.e. path of a scene described above where the desired information such as movie information or movie play a target scene may be found may be listed in the corresponding column.

Because a particular user link request may have multiple resulting scenes the link request may be listed multiple times in the table each having a different corresponding resulting scene or path.

During runtime i.e. while the user is navigating the user interface a link request received from a user may be searched for in the table. If the received link request matches an entry in the table the corresponding location information is obtained. If multiple entries match the received link request then the information for multiple corresponding locations each corresponding to one of the multiple entries is obtained and the closest one of these corresponding locations is selected using an algorithm described below.

During runtime using the exemplary setup illustrated in if a user seeks information on related movies from The Matrix under Home HBO Movies Action for example the server may provide the two choices in the example illustrated in The Matrix Reloaded Preview and The Matrix Behind Scenes .

For The Matrix Reloaded Preview there are two potential resulting scenes. The scenes in this example have the paths Home The Matrix Reloaded Preview and Home SHOWTIME The Matrix Reloaded Preview. A scene representing The Matrix Behind Scenes may be Home HBO Documentaries The Matrix Behind Scenes or Home SHOWTIME Movies The Matrix Behind Scenes.

If the user chooses The Matrix Reloaded Preview for example the server computes the shortest distance to The Matrix Reloaded Preview from the current scene.

In determining the shortest distance the server attempts to minimize the number of steps or levels that have to be traversed up i.e. go up as little as possible . This may be accomplished by picking the target having the longest common prefix as it relates to the scene definition or path with the current scene.

Then it attempts to minimize the number of steps or levels that have to be traversed down i.e. go down as little as possible . For the going down part the server examines paths to each possible target and selects the path having the fewest in exemplary embodiments.

In the example above if the chosen scene is The Matrix Reloaded Preview the current location scene is Home HBO Movies Action The Matrix. The two possible destination scenes may be Home SHOWTIME The Matrix Reloaded Preview and Home The Matrix Reloaded Preview. The common prefix for the current scene and the first destination scene is Home. The common prefix for the current scene and the second destination scene is also Home.

Both destination scenes in this example have the same length common prefixes with respect to the current scene. This implies that the same number of levels have to be traversed up regardless of either destination scenes. However the number of levels to traverse down from Home varies between the destination scenes. For the first destination scene two levels have to be traversed. For the second destination scene only one level has to be traversed down. In this case the server chooses the second destination i.e. Home The Matrix Reloaded Preview .

If the user chooses The Matrix Behind Scenes then the two destination scenes may be Home HBO Documentaries The Matrix Behind Scenes or Home SHOWTIME Movies The Matrix Behind Scenes. In this scenario the current scene i.e. Home HBO Movies Action The Matrix has a longer common prefix with Home HBO Documentaries The Matrix Behind Scenes than with Home SHOWTIME Movies The Matrix Behind Scenes. The server then chooses the first destination scene.

If only one destination scene is available then the shortest distance need not be determined and the one destination scene may be selected. As illustrated in from The Matrix a user s desire for background information results in only one scene corresponding to The Matrix Behind Scenes . This destination may then be selected.

If the distance to multiple destinations is identical then any one of the destinations may be selected. As illustrated in from The Matrix a user s desire for background information results in two scenes corresponding to The Matrix Behind Scenes HBO Documentaries The Matrix Behind Scenes and HBO Events The Matrix Behind Scenes . In this scenario either of the destination scenes may be selected.

The transition from the source scene to the destination scene may be visually presented on the user interface utilizing the zoomable aspect of the user interface. That is for example the transition from Home HBO Movies Action The Matrix to Home HBO Documentaries The Matrix Behind Scenes in may be displayed as a series of transitioning sequence interfaces illustrated in .

At each stage of the transitioning sequence the scene of interest and or relevance may be displayed more prominently on the user interface than other scenes and at that hierarchical level illustrated in . The navigational icons and appears in the user interface as well.

Navigational icons illustrated in each of facilitate navigation to home icon for example up one level icon or to previous scene icon .

The methods described herein may be implemented using known Java techniques. The server may be remotely located and user interaction via a handheld device may be facilitated over a network connecting a receiver receiving user actuation from the handheld device to the server. An exemplary system is illustrated in . System includes a server a network a receiver and a handheld device . Communication between the handheld device and the receiver may be over wireless medium such as Bluetooth for example.

Exemplary methods described above may be illustrated with reference to . A user link request may be received at . The received request is compared to a plurality of entries in a lookup table at . For each entry in the plurality of entries in the lookup table that matches the received user link request a target scene that corresponds to the matched entry in the lookup table is identified at . A closest one of the target scenes is determined if multiple entries in the lookup table match the user link request at . The closest target scene is transitioned to at .

The above described exemplary embodiments are intended to be illustrative in all respects rather than restrictive of the present invention. Thus the present invention is capable of many variations in detailed implementation that can be derived from the description contained herein by a person skilled in the art. For example while the description focused on navigating between programs in multiple locations in a home entertainment system exemplary embodiments may be equally applicable for determining a closest branch of a retail chain having multiple locations that is within a same jurisdiction for ensuring a particular sales tax rate.

All such variations and modifications are considered to be within the scope and spirit of the present invention as defined by the following claims. No element act or instruction used in the description of the present application should be construed as critical or essential to the invention unless explicitly described as such.

