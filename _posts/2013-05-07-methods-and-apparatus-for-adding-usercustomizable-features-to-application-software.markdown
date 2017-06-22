---

title: Methods and apparatus for adding user-customizable features to application software
abstract: An application's users are divided into two groups: administrative users and end-users. Each type of region, produced on an application's screen, is assigned a class. Each actual occurrence, of a region type, is called an instance. An end-user invokes a user-added feature by indicating a screen location and inputting a unique signal. The classes, of the screen-region instances present at the indicated location, determine whether one or more rules are activated. The rules are written by an administrative user. If activated, a rule produces a URL in accordance with an administrative-user-defined template. A value stored in the instances present, at the location indicated when the unique signal occurred, are accessed in a template by including the name of the value as a parameter. Each parameter is substituted by the text-equivalent of its current value. The URL produced can be used to provide the information desired by the end-user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09170703&OS=09170703&RS=09170703
owner: Ascent Technology, Inc.
number: 09170703
owner_city: Cambridge
owner_country: US
publication_date: 20130507
---
As provided for under 35 U.S.C. 119 e this patent claims benefit of the filing date of the following U.S. Provisional application herein incorporated by reference in its entirety 

 Methods and Apparatus for User Customizable Application Software Application No. 61 676 119 filed 2012 Jul. 26 y m d .

The present invention relates generally to the user customization of application software and more particularly to customization that includes customizable production of a Universal Resource Identifier or URI .

Communication between application software and a resource by the production of a Uniform Resource Locator or URL is known. In the singular application software can be referred to with increasing levels of brevity as an application program application or App . For example an App for reading emails such as OUTLOOK from MICROSOFT CORPORATION Redmond Wash. can detect the presence of a URL or link in an email message and activate that link. Once activated a user can go to the URL i.e. open the page at the URL in a web browser embedded in an email simply by selecting the link e.g. clicking the URL with a mouse .

A limitation of this type of activation is that it is static i.e. the particular URL embedded in an email is fixed .

A REST or a REpresentational State Transfer approach to web services can allow customizable App to App communication via URIs. Web services however merely provide a more uniform basis for interchange between Apps typically business oriented Apps . The behavior of the App itself is still determined by the coding of the App producer e.g. MICROSOFT CORPORATION and is thus fixed from the perspective of an end user.

It would be desirable to introduce techniques and methods by which to enable user customization that includes user customizable production of URLs and more generally Uniform Resource Identifiers URIs . Uniform Resource Identifier is a term that covers both URLs and Uniform Resource Names . Such capability would provide a greater range of options by which each user can adapt an App s behavior to the user s particular operating environment and needs.

Reference will now be made in detail to various embodiments of the invention examples of which are illustrated in the accompanying drawings. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts.

Please refer to Section 5 Glossary of Selected Terms included as the last section of the Detailed Description for the definition of selected terms used below.

Large metropolitan area airports e.g. Logan International Airport Boston Mass. U.S.A IATA code BOS frequently use some kind of App for assigning airplanes to gates.

An example main display for an unspecified airport AP1 using an example gate assignment App GAA1 is shown in . The display of is loosely based upon the ARIS Gate Manager product of Ascent Technology Inc. Cambridge Mass. U.S.A. . However the display of is merely for purposes of example and the techniques of the present invention can be applied to any gate assignment App with a Graphical User Interface GUI . More generally the techniques of the present invention can be applied to any App with a Graphical User Interface GUI . The two main axes of such pair of axes labeled serve the following functions 

The gate assignment chart of presents a timeline of how a particular gate is utilized by different airplanes during the day. Vertical line also called the now line indicates the current time at which the chart is being viewed. As can be seen the current time is approximately 3 05 pm. A period of time during which an airplane remains at a gate is represented by a lozenge shape. The points at the left and right ends of a lozenge provide respectively an airplane s arrival and departure times at a gate. For example includes a lozenge that indicates the following data 

The gate assignment chart of also includes lozenge shapes and . Some of the data indicated by each of these shapes is as follows. Lozenge 

Using a gate assignment system like GAA1 a ground control manager can assign airplanes to gates by creating and moving such lozenge shapes. The graphical nature of the display assists the manager in avoiding conflicts i.e. two or more planes utilizing a same gate at a same time since it is immediately obvious whether lozenges within a row overlap. Of course in addition to avoiding overlap many other types of rules may need programming into a gate assignment system. For example the lozenges can be required to provide sufficient transition time between one plane s departure and another s arrival. In addition to the types of information discussed above a lozenge shape typically also includes information about the type e.g. manufacturer and model number of an airplane since certain types of planes can only be accommodated at certain types of gates.

Assume gate assignment App GAA1 that can be as discussed above any suitable gate assignment software has been supplied to airport AP1 by a software company SC1 that can be any suitable software supplier . Assume AP1 would like to add a collection of features let s call the feature collection FC1 to GAA1 and that FC1 is unique to the particular needs of this airport. For purposes of example we will assume an FC1 that includes the following features 

For each of the above listed features it can be appreciated that a convenient user interface would follow a similar pattern 

While it can be expected that GAA1 will already use mouse clicks for such operations as selecting and dragging lozenge shapes we will assume that such mouse clicks are never used in combination with the Control Shift or C S key combination. In this case each feature of FC1 could be activated by a mouse click when combined with the C S key combination. This type of mouse click can also be referred to herein as C S mouse click. Example types of locations or regions of a user s screen for a C S mouse click on the gate assignment chart of along with the kind of data that might be desired in response are as follows 

To further explain the feature disambiguating pop up menu consider the following example. Suppose a C S mouse click occurs at left end of lozenge shape . This mouse click could be meant to invoke any of the three above listed features of FC1. In this situation a pop up menu can appear giving the ground control manager the option of obtaining one of the following three windows live camera data current flight status or local weather.

Without the techniques of the present invention it can be expected that AP1 would need to obtain from SC1 customized changes to the source code of GAA1. In many situations such customer customized changes are not available or even if available can be too costly for AP1.

Source code changes to GAA1 are not needed if in accordance with the teachings of the present invention GAA1 is provided with a facility for extensibility.

The main interface by which administrative users provide the new features can be a database where certain kinds of rules can be stored also referred to herein as a Rules Database . Administrative users are provided with access to this Rules Database. By simply writing new rules that follow a specified format the administrative users are able to add new features.

In addition to access to a Rules Database the administrative users need the following types of documentation from SC1 

For each feature of collection FC1 an example screen region class is depicted in one of . depicts a screen region class called WHOLE CHART an example instance of which is indicated by outline . shows a screen region class called GATE ROW example instances of which for Gates C1 and C5 are indicated by respectively outlines and . shows a screen region class called FLIGHT LEG example instances of which for lozenge shape are indicated by respectively outlines and to better emphasize the flight leg regions lozenge shape is shown in lighter outline . For purposes of example it is assumed that each of these screen region classes corresponds as follows to a feature of FC1 

For each instance of an above listed screen region class of Table 2.1 the following Table 2.2 lists at least some of the parameters available to a rule of the Rules Database 

Regarding documentation on the Rules Database it can be described as having the following basic structure 

If more than one rule is triggered the end user can be provided with a rule disambiguating pop up menu by which to select the rule to execute.

First there can be a table shown below as Trigger Table 2.3 specifying the trigger condition for each rule 

For each row of Table 2.3 its left and right columns can specify respectively the following information 

For example the rule Display Local Weather is shown as triggered simply by a UPL within WHOLE CHART. The above table shows only a single screen region class per rule trigger. However rule triggering can be made dependent upon a UPL that indicates multiple classes of screen regions. This can be accomplished by having multiple rows entered with a same rule name but each row specifying a different screen region class. In this case a logical AND operation is performed where all the rows for the single rule name must be satisfied before the rule is triggered.

For example it might be desirable to further limit the Live Gate Camera feature such that it is only activated if in addition to selecting a gate row the UPL is on or near the now line e.g. now line of . depicts a screen region class called NOW LINE an example instance of which is indicated by outline . Trigger Table 2.3 as shown above can be augmented to become the following Trigger Table 2.3.1 

As can be seen Trigger Table 2.3.1 is the same as Trigger Table 2.3 except that the rule Display Live Gate Camera now has two rows one that requires the GATE ROW class and another that requires the NOW LINE class. In the following discussion however it will be assumed that Display Live Gate Camera needs only the class GATE ROW for triggering. 

A second major aspect to structure of the Rules Database is that it can contain a table shown below as Action Table 2.4 specifying the action for each rule 

Each row of Table 2.4 specifies in its left and right columns respectively the following information 

To show how a template can work consider the example discussed above of an end user gesture with a UPL anywhere over gate C7 as depicted in the gate assignment chart of 

As discussed above however a gesture and UPL anywhere over a gate s row not only means that an instance of screen region class GATE ROW is indicated but that at least the screen region class WHOLE CHART is also indicated. In this case as discussed above a feature disambiguating pop up menu can be displayed. The production of useful descriptions for the user in such pop up menu can in a way similar to the production of URL s also be accomplished by templates. Following is a table of such description producing templates 

Assume a user enters a gesture and UPL over the left side i.e. side of lozenge shape as shown in . In accordance with the screen region classes of it can be appreciated that the following instances and classes are indicated 

Assuming a disambiguating pop menu is desired each template of Table 2.5 can respectively operate as follows 

Whenever a template s parameter is being resolved regardless of whether the parameter is appearing in an Action or Description Template each indicated screen region instance is checked for whether it has a value for the parameter. For the example given above where a user has entered a gesture and UPL over side of lozenge shape the three above listed instances are checked i.e. instance for each of AP1 C7 and LAX 1400 . Each instance can be checked by use of a resolver function mentioned above where each screen region class has its own resolver.

If the choice to View data for flight 1400 is selected then the Action Template of Action Table 2.4 can produce the following URL 

Any suitable relative positioning can be used between screen of and screen of . For example if the display screen is large enough screen can be displayed without any overlap of screen . Alternatively screen could overlap any or all of screen . Once the end user has obtained sufficient information from screen it can be closed as can be accomplished with any windowed display system.

While this section has focused upon gate assignment software it should be readily appreciated that the technique described herein for producing user extensible software can be applied to any kind of application software. It is only required that the application use a graphical user interface GUI where the screen can be meaningfully divided into different classes of screen region.

While this section has focused on the generation of a URL more generally any URI could be produced. In addition to generating a URI templates could instead or also be used to produce any other type of command or request. For example a template could be used to generate a database query such as an SQL query.

While this section has focused on the generation of a URI encoded as a character string any kind of encoding suitable for the particular area of use of the application can be produced.

Further any kind of URI can be produced including URI s that include one or more embedded database queries or one or more embedded commands.

To continue with the example of above GAA1 can either be designed by SC1 with the extensibility capability of a user accessible Rules Database or if it is already a commercially available App it can be retrofitted to provide this capability. Either way this section outlines some example coding strategies for efficient implementation of such extensibility. To emphasize the general applicability of the invention to any

We shall refer to the portion of App1 s code responsible for responding to an end user s input of a UPL the UPL Processor. The UPL Processor needs to incorporate a test to determine whether the UPL is accompanied by a gesture and is therefore an invocation of a user added command. If the input of a UPL does include a gesture the UPL Processor needs to invoke that portion of App1 s code responsible for execution of user defined commands. We can refer to such portion of App1 s code as the Gesture Processor. 

While any suitable programming language can be used to implement App1 and its Gesture Processor there can be advantages to utilizing an object oriented programming language 

Pseudo code for CollectAccess4Instances is shown in . CollectAccess4Instances operates in three main stages 

Pseudo code for FindMatchingRules second major stage of GestureProcessor is shown in lines . FindMatchingRules operates in three main stages 

RuleMatchesToken is also shown in lines . It operates as follows. It uses RequiredTypes types to retrieve the classes required by a rule s Trigger Table line . As long as each of these classes is listed in the HandledTypes of the current token determined by the SUBSET function of line a value of TRUE is returned.

Pseudo code for InvokeRule third major stage of GestureProcessor is shown in lines . It operates as follows all of the following is performed by the nested function calls of line 

As shown in the computing delivered is typically at any or all of the following levels from lowest level to highest 

A more hardware oriented version of is shown in . As with the clients are labeled Cloud Client to Cloud Client N. The clients are shown as communicating with the cloud service provider through an Internet cloud . The front end hardware of the cloud service provider is shown as being a computer that can provide among other functions load balancing and a firewall. Front end computer is shown as connected to the servers of a Server Farm . The load balancing function of computer can balance the loading of these server farm servers. As can be seen the server farm servers are labeled Server to Server K. With regard to the present invention the server farm servers can all share a Rules Database . As discussed above Rules Database is written by the administrative users to implement additional features for the end users.

The present invention can be incorporated into an application offered under a SaaS model. In this case the invention can be viewed from at least the following perspectives 

Of course any suitable information technology infrastructure can be utilized. For example it is still common for application programs to operate on a single user personal computer. In this case the functions of client computer and server computer are realized in the same physical computer at which a user is seated.

Whether the physical computer being used by a user is the entirety of the information technology infrastructure utilized or whether such physical computer is simply a client to a server where the server can be provided in a cloud fashion or in any other suitable way depicts an example general purpose computer for such purpose.

In some embodiments computer programs embodying the present invention are stored in a computer readable medium e.g. CD ROM or DVD. In other embodiments the data and or computer programs are embodied in an electromagnetic carrier wave. For example the electromagnetic carrier wave may include the data or programs being accessed over a network.

If display monitor mouse pointing device and keyboard are omitted can also be representative of an embedded computer system.

While the invention has been described in conjunction with specific embodiments it is evident that many alternatives modifications and variations will be apparent in light of the foregoing description. Accordingly the invention is intended to embrace all such alternatives modifications and variations as fall within the spirit and scope of the appended claims and equivalents.

