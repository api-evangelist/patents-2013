---

title: Method for implementing a computer game
abstract: A method, implemented as computer code being executed by one or more processors, in which computer game graphics for a casual, social game are shown on a display of a computing device, where the casual, social game is downloaded as an app to a smartphone and/or tablet computer and can be accessed or played using a social network application or environment; and in which one or more of the processors are programmed such that: a notification is automatically generated if a player is stuck at a level for more than a defined time or after more than a defined number of attempts to pass that level, the notification alerting friends of the player so that they can assist him or her.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09592444&OS=09592444&RS=09592444
owner: KING.COM LTD.
number: 09592444
owner_city: St. Julians
owner_country: MT
publication_date: 20130917
---
This application is based on and claims priority to U.S. Provisional Application No. 61 701 907 filed Sep. 17 2012 UK Application No. 1302121.7 filed Feb. 6 2013 UK Application No. 1302910.3 filed Feb. 19 2013 UK Application No. 1304442.5 filed Mar. 12 2013 UK Application No. 1304444.1 filed Mar. 12 2013 UK Application No. 1304545.5 filed Mar. 13 2013 UK Application No. 1306117.1 filed Apr. 4 2013 UK Application No. 1306118.9 filed Apr. 4 2013 U.S. Provisional Application No. 61 811 019 filed Apr. 11 2013 U.S. Provisional Application No. 61 818 702 filed May 2 2013 U.S. Provisional Application No. 61 827 298 filed May 24 2013 U.S. Provisional Application No. 61 832 348 filed Jun. 7 2013 U.S. Provisional Application No. 61 832 355 filed Jun. 7 2013 U.S. Provisional Application No. 61 832 359 filed Jun. 7 2013 U.S. Provisional Application No. 61 832 362 filed Jun. 7 2013 U.S. Provisional Application No. 61 832 364 filed Jun. 7 2013 U.S. Provisional Application No. 61 832 369 filed Jun. 7 2013 UK Application No. 1310589.5 filed Jun. 13 2013 UK Application No. 1310592.9 filed Jun. 13 2013 UK Application No. 1311119.0 filed Jun. 21 2013 UK Application No. 1314147.8 filed Aug. 7 2013 and UK Application No. 1316045.2 filed Sep. 10 2013 the entire contents of each of which being fully incorporated herein by reference.

Computer implemented games is a well known category of games that allow a player to interact with a computing device to cause the processor to perform certain calculations and typically display a result on a screen or other display device.

Different types of games have evolved from classical arcade games in to games that can be played on a handheld device such as a smartphone or personal computer. Some games are also connected to the Internet and the player can play against or compare score with other users in multiplayer mode.

There are multiple technical challenges facing the designer of computer implemented games to create a fun and compelling game. Three of these challenges can be broadly categorized into the following areas engagement viralisation and monetisation .

We will look first at engagement which involves designing gameplay to be engaging and rewarding to players. This typically requires games to be easily understood at their simplest or introductory levels providing rewarding gameplay with quite simple game mechanics but becoming progressively more challenging so that players are not bored but remain engaged and develop rewarding skills. Effective engagement requires various forms of feedback to reinforce players sense of success and accomplishment. Effective engagement can be greatly magnified if the game has as social aspect for example if it is linked to a social network so that game players can interact with their friends in the social network. The game can then transform into something that goes far beyond a solo game experience and become more like a shared journey.

 Viralisation requires a game to include various techniques that encourage players to share the game with others encouraging them to play the game. It is a key technique in enabling mass scale distribution or penetration of games. Viralisation can be especially effective when the game is integrated into a social network environment in some manner so that the game can then propagate through the network of player s friends and their friends and so on.

 Monetisation covers those techniques that enable revenue to be generated from a game this involves many challenges because the monetisation techniques need to be acceptable to players and in no way undermine engagement.

A successful and original game will require a team of game designers to solve complex problems of engagement viralisation and monetisation this can take many months of skilled work and not infrequently a great deal of trial and error testing of new ideas functions and game mechanics before a game successfully combines all these elements into a new experience.

A match 3 game is a type of casual puzzle game where the player is required to find patterns on a seemingly chaotic board. The player then has to match three or more of the same type of game element on the game board and those matched elements will then disappear.

One variant of casual games are the so called clicker games where the player can click on a group of adjacent game elements of a certain type and those will then be removed. Some clicker games only require two adjacent objects to remove those elements if clicked by the user.

Another type of match 3 games are the so called switcher games where the player switches place on two adjacent game elements on the game board so that one or both of them create a chain of at least three adjacent game elements of the same type. Those matched game elements will then disappear. In a typical switcher game the game board will be repopulated with game objects from the top of the board with the physics of the game board being that the game pieces are falling downwards on the board.

Another type of match 3 game are the so called shooter games where the player launches for instance a ball or bubble on to the game board tying to aim at groups of similar game elements already on the game board. If the launched ball hits or forms a group of more than 3 similar game elements then that group of game elements are removed fro the game board. In a typical shooter game the physics of the game board being that the game pieces are falling downwards on the board.

This patent specification describes not only various ideas and functions but also their creative expression. A portion of the disclosure of this patent document therefore contains material to which a claim for copyright is made and notice is hereby given Copyright King.com Limited 2012 and 2013 pursuant to 17 U.S.C. 401 . A claim to copyright protection is made to all screen shots icons look and feel and all other protectable expression associated with the games illustrated and described in this patent specification.

The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but reserves all other copyright rights whatsoever. No express or implied license under any copyright whatsoever is therefore granted.

Casual social games have been implemented before and are known. However previous inventions have not successfully devised effective solutions to one or more of engagement viralisation and monetisation in the same way as the present invention does.

A method implemented as computer code being executed by one or more processors in which computer game graphics for a casual social game are shown on a display of a computing device where the casual social game is downloaded as an app to a smartphone and or tablet computer and can be accessed or played using a social network application or environment and in which one or more of the processors are programmed such that 

A computing device adapted to play a computer game the device including a processor a memory a display a touch screen or a cursor based input device and computer code stored in device memory or on a remote server and executable by the device processor or a remote processor and in which the computer code generates computer game graphics for the display on the device and in which one or more processors are programmed such that 

A non transitory computer readable medium encoded with instructions for controlling a computer system to display a game on a display and in which the instructions running on the processor s are such that 

The terms user and player are used interchangeably throughout this document and no specific meaning is intended using one or the other unless the context suggests otherwise.

In the following description of various implementations of the invention reference is made to the accompanying drawings which form a part thereof and in which is shown by way of illustration various implementations in which the invention may be utilized. It is to be understood that other implementations may be utilized and structural and functional modifications may be made without departing from the scope of the present invention.

People skilled in the art will understand that other devices than the exemplary ones listed can be also be used without departing from the spirit and scope of the invention.

The techniques described in this patent can be deployed in many different gameplay architectures. For example a computer game can be implemented as a computer program that is stored and runs entirely locally on the processor of a PC games console tablet or mobile telephone or other computing device. The game can be implemented solely as a computer program that is stored and runs entirely on one of many processors in a remote server and data streams or updates are supplied to the client device e.g. tablet smartphone etc. to enable the client to render and display graphics and sounds this web services approach is increasingly common.

Another approach is a hybrid one in which back end servers handle some elements of the gameplay and for instance a Java game applet is provided to client devices and it is the locally running Java applet that generates the graphics sounds user interaction for gameplay on the player s client device. Some data may be fed back to the back end servers to enable scoring interaction with other players and cross platform synchronisation. Generally the techniques described in this specification are not specific to any one game architecture but can be deployed on any suitable game architecture.

The game can be implemented allowing a user to interact with it in different ways depending on the capabilities of the device which the user is accessing the game with. A user can interact with the game through using a touch screen where the user can select and or move elements on the game board with a finger or for instance with a stylus. The game can also be played with a pointing device such as a mouse or other interaction devices such as a keyboard.

Mobile devices may have a touch screen interface where the player can interact with the game using a finger or a pointing device such as a stylus. Some mobile devices have hard keys that complement the touch screen interface. Such hard keys may be in the form of a button or in the form of a joystick type of interaction.

Over the course of players playing the game data will be produced. This data can for instance be related to a player s game performance or to game information related to a social network to which the game is connected. It is possible to gather this data store it and make use of it for instance to improve the game. One example is by using a database to store the amount of times players try and fail a level on average. This data can then be reviewed and if the players seem to fail a substantial amount of times before completing a level the difficulty can be adjusted accordingly. The difficulty can be adjusted through changing a score target for the level increasing the available time or moves or giving the player for instance a booster to enhance the gameplay.

There can be certain performance indicators used to measure the success of the game. These indicators can for instance relate to player retention the virality of the game and the revenue of the game.

A person skilled in the art will realise that the different approaches to implementing the game is not exhaustive what is described herein are certain preferred embodiments. It is possible to implement the way in a number of variations without departing from the spirit or scope of the invention.

The terms user and player are used interchangeably throughout this document and no specific meaning is intended using one or the other unless the context suggests otherwise.

The following description will describe some implementations of the inventions described in the document. The examples will be from the game Candy Crush Saga by King . The person skilled in the art will understand that there are many other ways the present ideas can be implemented and the description is not limited to only one implementation.

Standard game elements These are the six basic candies used for making switches and colour matches on the game board. Compared to special game elements the standard game elements have no extra properties or behaviour they are only used to make colour combinations or to create new special game elements.

Ingredients Game elements that are included in levels where one of the goals to complete the level is to bring down ingredient elements to the bottom of the game board.

Jelly block A game element that is placed underneath other game elements and need one or two matches on top of them to disappear.

Special game elements All elements that appear on the game board and which have specific behaviours and properties.

Moves Score Level In this game mode you have a limited number of switches before running out of moves. If you have not reached the score required to earn at least 1 Star then you will fail the level.

Jelly Level In this game mode the game board behind the candy is covered in jelly. Remove the jelly by matching candy on top of the jelly. If you fail to remove all jelly before running out of moves then you will fail the level.

Ingredients Level In this game mode ingredients will appear on the game board. Collect these ingredients by bringing them to their delivery point. On the side of the board you will see a recipe of how many ingredients you need to collect. If you do not bring down all the ingredients before running out of moves then you will fail the level.

Time Limited Level In this game mode there is a time limit. If you have not reached the score required to earn at least 1 Star when the time runs out then you will fail the level.

Candy Order level In this game mode you are tasked with collecting a number of candies. This is done by removing the wanted candies. If you have not collected all the wanted candies before running out of moves then you will fail the level.

Booster Something that enhances the gameplay and that supports assists or increases power or effectiveness.

Blocker Special game elements that are unswappable need 1 or more matches next to them to disappear and are in the way for falling candies.

Candy Crush Saga by the games developer King is a game belonging to the match 3 category of games. This means that the core basic of the game is to match three or more game elements sharing the same colour with each other. In Candy Crush Saga these game elements are implemented as candies. and shows one implementation of the first level in Candy Crush Saga where candies have to be matched to complete the level.

The game has more than 350 different levels and not all of those levels have the same requirements to be completed. Simply matching three or more game elements is not enough to complete all levels in the game but the player has to meet certain goals as well. These goals could be to reach a certain amount of points before running out of moves or time to bring down certain game elements to the bottom of the screen to remove a certain amount of game elements before running out of moves or to collect certain game elements through specific matches before running out of moves.

If the game becomes difficult there are boosters to help the player pass a level. These can be obtained from in game purchases or received as gifts from Facebook friends.

The game also has a candy land themed map view illustrates one implementation of this where the map can be scrolled up and down. The map view shows what levels have been completed as well as how many levels are left to play. Throughout the game and for each level completed the player journeys across the map and follows the story of a girl who is journeying through the candy land. The map is also divided into different areas where each area has its own candy theme as well as a small story connected to that area.

If the player has connected to a social network by entering login details through a prompt in the game then friends progress from the same network can be viewed on the map by the means of their portrait next to the highest level they have currently reached.

If the player connects to the social network Facebook when playing the game then the game will automatically synchronize and either download or upload the latest changes in the progression of the game. For example the player could have played the game on another computer via Facebook s own platform and if the player then later decides to play on for example their iPhone the latest updates would be sent to this device. As long as the player is connected to the internet and has logged in to Facebook via the game then the game will automatically synchronize and send data to Facebook making it possible for the player to play on any computer iOS device or Android device without having to start the game over. This makes the place to play very flexible.

To play Candy Crush Saga game elements in the shape of candies are swapped with each other to make moves on a game board. To gain points the player has to make moves that create matches of at least three of the same candy. If doing so the player gains points and the matched candies are removed see . As a result new candies fall into place from the top of the game board in order to fill any empty spaces created. For all candies that are removed on the game board points are always shown in the same colour as the candy that was removed for example three red candies will show red points green candies green points and so on. If a blocker element would be removed then the points shown would be in the same colour as the candies from the match that removed it.

Only swapping moves that will create at least one combination of at least three game elements of the same type are allowed.

A typical game mode of Candy Crush Saga provides the player with a limited number of moves to reach the level target.

The Candy Crush Saga game board comes in various shapes and sizes. The maximum size is a grid of 9 9 squares but within those limits the shape and size varies between the levels played see and . This gives more variety to the game compared to many other games in the match 3 genre where the game board always looks the same.

To add more diversity and make Candy Crush Saga a more dynamic game players have to fulfil different criteria in order to complete different levels these are referred to as goals. Each level always has one or more goals that have to be fulfilled in order to complete that level.

One of Candy Crush Saga s most common goals is to collect a certain amount of points before running out of moves illustrates this. The points are collected through making matching combinations on the game board. The smarter combinations made the more points.

Candy Crush Saga also has timed levels. The goal that needs to be fulfilled on these levels is to collect a certain amount of points before time runs out see . The smarter combinations made the more points.

Some levels are referred to as Ingredients levels. The Ingredients levels have two goals which need to be fulfilled in order to complete the level 

One of the most frequent set of goals in Candy Crush Saga is the one used for levels that contain Jelly blocks. Jelly blocks are game elements that are found underneath other game elements and need one or two matches on top of them to disappear See description elsewhere . The goals that need to be fulfilled on levels with Jelly blocks are 

Another type of level Candy Crush Saga has introduced to their variety of game modes is a so called Order level. Order levels have two goals 

In this game mode players are required to collect an even amount of two colours of candies to complete the level. The level goal can be indicated with a scale where the two different types of candies to be collected are placed on either side. When the count is unbalanced one side of a scale starts tipping the bigger the difference the faster it tips. If one end touches bottom level has failed. Score is given to the player based on the number of moves it takes to collect the required amount of the two colours.

The goal of this game mode is to light up all squares cells on the game board. In some implementations the requirement to light up a cell is to combine a candy that is in that cell. In other implementations the player has to combine multiple candies in the same cell before it lights up.

In this game mode players are required to combine candies in cells adjacent to blockers in order to dig down in the level. When digging the player can uncover objects that are covered initially.

All of the game modes described herein can also be used in any combination with one another. For instance the requirement to complete one level could be to remove all jelly as well as bringing down ingredients.

If the player tries to make a move with two candies in such a way that no candy will be matched with at least two more of its own colour then the move will not be allowed and the player will have to try to find another move.

If no moves are possible on the game board then all the candies are reshuffled so that there will always be at least one possible move available. If the player can t see or find a move to make then the game helps the player by giving a hint. The hint is displayed after a few seconds of inactivity and is shown by brightening and magnifying the candies of a possible move in a flashing animation see .

Not only the match of 3 candies is allowed but matches of more candies can also be done see for the different possible match patterns. Matches with more than 3 candies give more points and is something the player should try and aim for. Different acceptable matches are 

As can be noticed from the list of possible matches no diagonal matches are accepted. Diagonal matches and or swaps can be allowed in some implementations of the game.

Matches made of four or more candies not only give more points but also reward the player with special game elements. The special game elements received from combos have various positive properties and can be used to gain more points and to easier pass a level. The elements received from different matches are 

If a match is made with more than 6 candies then it is likely that the combo is a shape merged from 4 in a row 5 in a row L shape and T shape. If so there is a hierarchy of what kind of special element is received 

Special game elements received from matches can be combined with each other for various positive effects affecting the game board. Striped candies Wrapped candies and Colour bombs can all be matched with each other. To trigger these combos they do not need to be matched by game elements of the same colour but can simply be swapped with each other for an instant trigger.

Special game elements can either be received from special combos or from an automatic placement on the game board.

A Striped candy is given by matching four candies of the same colour in a horizontal or vertical line.

The Striped candies have the same shape and colour as the standard game elements except for that they have white vertical or horizontal lines on them see . The colour and the shape of the striped candy will be the same as the candies which were being matched to create it.

If the match of four candies is done in a horizontal line then a candy with vertical lines will be given. If a match of four candies is done in a vertical line then a candy with horizontal lines will be given.

Striped candies removes a whole row or column depending on if it was made from a vertical or horizontal combo. The white lines on the candy indicates whether it will remove a row or a column. To trigger a Striped candy it needs to be matched with two more candies of the same colour.

Striped candies removes all candies in a row or column also if the game board is divided up in two or more areas that are not connected. The player can this way remove candies from areas that otherwise would be hard or impossible to find combinations in. The impact of different game board designs are described elsewhere in this document.

When a Striped candy is being triggered an animation shoots out of the Striped candy following the row or column which it is removing. The animation looks something like the candy being stretched out and turned into lines that shoot out together with a sparkle effect. For all candies that are being removed the points given for each candy will be shown in the same colour as the candy being removed. See for an example of triggered horizontal and vertical striped candies and the animation they come with.

The Wrapped candies have the same shape and colour as standard game elements but with a wrapping around them see . The colour and the shape of the Wrapped candy will be the same as the candies which were being matched to create it.

The Wrapped candy is triggered by matching it with two more candies of the same colour. The result of the trigger are two explosions removing candies in a 3 3 square around the Wrapped candy. The first explosion occurs instantly when the Wrapped candy is being triggered the second explosion occurs after all candies from the first explosion have been removed and replaced with new candies. If the Wrapped candy is at the edge of the game board an explosion will happen but there is no effect from the part of the explosion area that is outside of the game board.

When a Wrapped candy detonates an animation with sparkling effect and light circles is shown with the Wrapped candy in the centre of the animation see .

When the Colour bomb is triggered it removes all candies of the same colour as the candy that was used to trigger it.

When the Colour bomb is being used. Blue coloured lightning bolts shoots out from the colour bomb to all candies that are going to be removed see .

Mystery Candies are placed randomly on the game board and do not need a special combination to appear.

The Mystery candies have an oval flattened shape which is slightly tilted and with a question mark painted onto it see . The Mystery candy comes in the 6 standard candy colours.

To use the mystery candy it needs to be included in a standard match 3 with candies of the same colour as the Mystery candy. The Mystery candy will then turn into a random game element which could have either positive or negative impact for the player. It could for example turn into a Striped candy or a Colour bomb or it could turn into something less fortunate for example a spreading chocolate block see description elsewhere or a bomb that counts down and explodes to make the player game over.

Lucky candies are inserted on the game board automatically when having selected a pre game booster which specifically adds Lucky candies to the candy mix on the game board.

The Lucky candy looks like a flattened sphere with a white tick mark painted on top of it see . The candy comes in all the 6 standard candy colours.

To use the Lucky candy it need to be matched with two more candies of the same colour. The Lucky candy will then turn into a random positive game element.

When the Lucky candy is being matched it looks like it is unwrapped and behind the wrap it reveals the new game element see .

Fishes are placed on the game board by selecting a pre game booster that specifically does so. Further ahead in the game the Fish can also appear randomly on the game board.

The fish is used by matching it with two more candies of the same colour. Doing so will trigger 3 fishes to swim into the screen and remove a total of three random pieces on the game board. If there are Jelly blocks or other blockers then the game will prioritize to remove those before removing a candy that stands on an empty square.

When the Fish is used it swims away out of the screen and then three Fishes swim into the screen remove one block or candy each and then disappears. The Fishes appearing are in the same colour as the fish that was in the combo.

A Wrapped fish is obtained if switching a Wrapped candy with a Fish. The Wrapped candy and the Fish do not need to be of the same colour. Furthermore the Wrapped fish will be triggered instantly and can not be saved for later use.

The Wrapped fish looks like the standard candy Fish but with a wrapper around it. The Wrapped fish comes in all the 6 standard candy colours.

When the Fish is switched with the Wrapped candy the effect of the Wrapped fish is triggered immediately. Three random game elements will be turned into Wrapped candies which trigger instantly and explodes two times like the standard Wrapped candy.

The Wrapped fish created from the switch with the Wrapped candy swims out of view and comes back with two more Wrapped fishes that swim onto the game board and to the position where the Wrapped candies will be created. Having reached the position the Wrapped fishes disappear.

This fish is given when combining a Fish with a Striped candy. The Striped candy and the Fish do not need to be of the same colour. Furthermore the Polka fish will be triggered instantly and can not be saved for later use.

The Polka fish looks like a standard candy Fish but with the same kind of stripes as the Striped candy.

The Polka fish turns three random candies into 3 randomly vertical or horizontal Striped candies which in turn are instantly triggered and creates 3 line blast effects.

In one implementation as with the standard candy Fish and the Wrapped Fish the created Polka fish swims out of view and returns with two more Polka fishes of the same colour which then swims to the position of the candies that are to be turned into triggered line blast elements. Having reached their destination the Polka fishes disappear.

This fish is acquired by combining a colour bomb with a fish. The Polka dotted fish is instantly triggered from this combination and swims out of the screen to bring three new Polka dotted fishes. The new Polka dotted fishes swim to three random locations on the game board and turn 1 game element each into a new Fish. The three new fishes will in turn swim out of the screen and then bring three new fishes each so that a total of nine new fishes swim onto the game board to nine random positions on the game board where they remove one game element each. After this the fishes disappear. The total effect of the initial trigger of the Polka dotted fish is that 12 game elements have been removed from the game board. Furthermore if there are squares with Jelly blocks on the fishes will always go to these first.

These candies are placed automatically on the game board. They could also be a resulting candy when having used a mystery candy.

Like a standard candy but with a soft glow around it and an animation of a rainbow passing by over the surface of the candy.

This is a game element that is automatically placed on a fixed position on an edge of one of the cells in the game board. The teleporter will typically be placed on the game board in pairs where one of the teleporters act as an entry point for candies falling on the game board across the cell edge where the teleporter sits. The candy will then be introduced on the game board where the exit point teleporter sits. So if a candy is normally falling one way from the top of the game board to the bottom of the game board the teleporter can move a candy up the game board again or to another area of the game board.

The teleporter does not fall down or take space on the area where switching is done and it is never included in any colour combinations.

Jelly blocks are introduced early in the game and a typical goal to complete a level is to remove all Jelly blocks on the game board.

The Jelly blocks are placed behind candies and are stuck into place. They can not be swapped and they do not fall down if candies below them are being removed.

To remove a Jelly block a match has to be made on top of it. Sometimes Jelly blocks consist of two layers and then they need two matches on top of them to be removed.

This is a visible game mechanic. In one implementation it can indicate where liquorice bombs and ingredients are set to appear.

Special game elements can be combined with each other through a simple switch. Doing so creates powerful effects that help the player earn more points and to easier pass a level.

Combining two Striped candies will trigger two simultaneous line blasts where one row and one column is removed in a cross shaped way see . It does not matter if the Striped candies combined are horizontal or vertical. The column and row blasts will be initiated from the position which the moved striped candy has been moved to.

Swapping any two Wrapped candies with each other will create a double explosion as with a standard Wrapped candy the difference being that the area of effect will be much larger see and remove everything in a 6 5 square area or a 5 6 square area depending on if the Wrapped candies are placed next to each other horizontally or vertically.

Combining any Striped candy with any Wrapped candy will trigger 3 horizontal and 3 vertical line blast effects. The result is three adjacent rows being removed see and thereafter three adjacent columns being removed see .

Combining these two will first remove all candies of the same colour as the Wrapped candy. After that the Colour bomb will be triggered a second time and remove all candies of a random colour.

The combination of these two special candies will turn all candies of the same colour as the Striped candy into randomly vertical or horizontal Striped candies which are then instantly triggered and fills the game board with line blasts. In a Colour bomb has been matched with an orange Striped candy turning all orange candies into Striped candies which are then automatically triggered.

Combining two Colour bombs will remove all game elements on the game board except if a game element is a multi layered blocker see description elsewhere . If a game element has more than one layer then one of those layers will be removed. displays one implementation of the animation when two colour bombs have been combined.

First all candies which the game board has the most of will be removed. After those candies have been removed the Coconut wheel will roll over the board and every candy it rolls over will turn into stripes.

With this combination the Coconut wheel will roll over the board and turn all candies it rolls over into Striped candies that instantly triggers.

With this combination the Coconut wheel turns all candies that it rolls over into Wrapped candies which are then instantly triggered and explodes.

The game implements several different kinds of so called Blockers. Blockers are negative game elements that are in the way for the player when wanting to make matches on different areas of the game board.

The blockers can have different properties some allow candies to sit on top of them while other allow candies to be included in them. Some fully cover a cell on the game board and are for instance only removed when there is an adjacent match of candies.

The frosting blocker see appears early in the game and functions as an obstacle that is in the way for surrounding candies. Frosting blockers can not be swapped they are stuck where they are. To remove the Frosting blocker the player has to create a colour match next to the blocker.

This is another blocker that comes in five different versions see . It can have 1 to 5 layers which means it needs 1 to 5 colour matches next to it to disappear. A 1 Layer frosting needs one colour match a 2 Layer frosting needs two colour matches and so on. Layered frostings are stuck where they are and can not be swapped.

Another type of blocker found in the game is the Chocolate blocker see . It not only blocks a space on the game board but also multiplies to block even larger areas of the game board. If a colour combination is made next to a Chocolate blocker then no Chocolate block will multiply and that Chocolate block will be removed. However if a colour match is made and is not next to a chocolate block then one of the Chocolate blocks on the gameboard will multiply and another space on the game board will be filled with a Chocolate blocker. The space that receives a new Chocolate block will always be adjacent to an existing Chocolate block however which Chocolate block on the game board it will come from is seemingly random. If all Chocolate blocks on the game board have been removed then no new Chocolate blocks will appear. Chocolate blockers can not be swapped and change places but are stuck where they are. Chocolate blockers can only multiply to a cell on the game board that is occupied with a candy.

Liquorice blockers see need one colour match next to them to disappear. What makes them different is that they are not fixed on the game board but falls down as regular candies. They can be swapped if the candy they are swapping with is part of a colour match. Liquorice blockers can not be matched with each other.

This blocker is stuck in place and can not be swapped with other elements see . The blocker contains a standard candy and can be removed if it s a part of a colour match with candies of the same colour as the one it is holding. It can not be removed by making colour matches next to it.

The Chocolate fountain see is a blocker connected to Chocolate blockers. It creates new Chocolate blockers even if the player as removed all on the game board. The Chocolate fountain can not be switched but is stuck in place. The Chocolate fountain can not be removed.

This is a blocker that holds candies into place so that they can t be swapped see . The candies may however be part of a colour combination and if so the Marmalade will disappear. The Marmalade will also disappear if a colour match is made next to it.

The Bomb see is an element that exists in all the standard 6 candy colours. It falls onto the game board at the same time as new candies fall into place when colour matches have been made. The bomb is switchable and falls downwards on the game board like standard candies. The bomb has a timer which counts down for each move that is made by the player. If the timer hits zero then the Bomb will explode and the level will be failed. The player has to stop the bomb from exploding and this is done by matching the bomb with two more candies of the same colour or removing it with the help of a special candy.

Candy Crush Saga has a wide selection of boosters available to the player. Boosters are items or features that help the player by enhancing gameplay and support assist or increase power or effectiveness. In the game boosters unlock as the player progress through the game. To be able to use a booster the player must pay to top it up with a certain amount of charges or receive a booster as a gift from a friend. Using a booster once will remove one charge and when there are no charges left the booster will need to be topped up again. In the implementation of this game the player can choose to use boosters either before starting a level when playing a level or when ending a level.

There is an option to choose what boosters to use before starting a level. This is referred to as a pre level choice of boosters. Boosters available for a pre level choice are 

The player can choose to use booster in action and at the exact moment when they need them. This is an In level choice. Boosters available for an in level choice are 

If being very close to completing a level but knowing you are not quite there and the level is about to fail then there is a choice of boosters at the end level. Boosters available for an end level choice are 

Some boosters are permanent and will only have to be purchased one time these are called Charms. After a first initial payment the Charm will be available to the player forever and will never have to be topped up.

Charm of Life increases the maximum number of lives from 5 to 8. It is a passive permanent booster which means it is always in use and the player does not need to do anything to take advantage of its effect. To buy the charm the player has to pay 169 Facebook Credits which is equivalent to 11.20 GBP. When buying this charm the player receives a free life top up.

This charm is booster that is available when playing a level. It lets the user create a Striped candy once per game. To use the charm the player clicks on the icon for the charm and then on the candy they wish to transform. To buy the charm the player has to pay 399 Facebook Credits which is equivalent to 26.45 GBP.

This charm freezes time on levels with time limits. It s included in the group of pre level choice boosters and if the player wants to use the charm it will then have to be chosen before starting a level. To gain use of the Charm of Frozen Time the player has to pay 249 Facebook Credits which is equivalent to 16.51 GBP.

Jelly Fish is a booster that adds Jelly Fishes as game elements on the game board together with all the standard candies. As described elsewhere the Jelly fishes on the game board need to be match with 2 more candies of the same colour and if doing so 3 random game elements will be removed from the game board. To gain access to this booster the player has to pay 19 Facebook credits which is equivalent to 1.26 GBP. Paying this will let the player use the booster three times before it has to be topped up again.

In some implementations this booster can only be used in ingredients levels. When using the booster it appears as an extra candy piece on the game board that looks like a pink round candy with some black candy filling in the middle see . To trigger the Coconut wheel it can be switched with any game element and does not need a colour match.

When triggered it rolls over the game board in the same direction as it was switched in. In its path the Coconut wheel transforms 3 standard candies into Striped candies which in turn are instantly triggered. When the wheel starts spinning it also removes the candy it was swapped with. illustrates one implementation of the Coconut wheel before it has be switched with a candy and after is has been activated. When activated the wheel rolls over the game board and creates three striped candies which then automatically triggers.

If the player wants to use this booster they can pay 39 Facebook Credits which is equivalent to 2.59 GBP. The booster will then top up and let the player use it three times before it needs to be topped up again.

The Colour bomb booster can be used on all levels. It lets the player start a level with one Colour bomb on the game board. To buy it the player has to pay 9 Facebook credits which will let the player use the booster three times before it has to be topped up again.

This booster gives the player 15 extra seconds either in the beginning of a level or when time is up on a level. If buying it when time is up it costs 9 Facebook credits which is approximately 0.53.

This booster lets the player start a level with one Striped and one Wrapped candy on the game board. To use it the player can top up the booster for 19 Facebook credits which will then let the player use the booster 3 times.

The Lucky Candy booster adds Lucky candies on the game board which will turn into useful candy when removed. The Lucky candy booster costs 29 Facebook credits 1.92 to top up and will then let the player use it three times before it needs to be topped up again.

This booster is available to buy at any point when playing a level. It has a booster icon that can be pressed but there is also a reminder message that appears when starting to run out of moves. In some implementations the booster becomes available when the player has five moves left. The booster may also appear when already being out of moves giving the player the option to continue the level. If using the booster it instantly gives the player five extra moves which can help the player to complete the level. To use the booster the player needs to pay 9 Facebook credits.

The Lollipop hammer lets the player remove any candy from the game board. The booster can be used at any time when playing a level. The player simply clicks the booster icon which in one implementation will turn the cursor into a big lollipop see .

The player then clicks on the candy they wish to remove and the cursor lollipop will break and remove that candy.

This booster lets the player switch two candies on the game board even if no match will be made. If clicking the booster icon then in one implementation the cursor turns into a hand or a glove see . To use the glove the player switch two candies like normal. To use the booster the player must have topped it up using Facebook credits. Topping it up lets the player use the booster three times.

The Bomb cooler helps the user with bombs that are counting down. The booster adds 5 more to the timer of the bomb and rescues the player from failing a level. If the bomb does reach zero then there is an option to add 5 more on the bombs timer in order to continue playing. If choosing to use the Bomb cooler when all bombs have reached zero it will cost 19 Facebook credits 1.26 GBP to use it even if the player has uses left from the last top up.

The Sweet Teeth booster destroys different kinds of blockers. To gain access to it the player has to pay 99 Facebook credits 6.56 GBP and will then be able to use it three times before having to top up again. When the booster is being used it flies over the game board and removes blockers by eating them up. The Sweet Teeth is very fond of chocolate liquorice and marmalade. 

The Bubble gum Troll booster helps the player out on levels that contain Chocolate fountains. When clicking on the booster s icon a Bubble gum troll appears see FIG. which then shoots bubble gum on top of the fountains see . This prevents the Chocolate fountains from spreading chocolate blocks. The bubble gum stays on the fountains during four switches see . On the fifth switch the bubble gum disappears. On the 6th switch a new chocolate block appears. To gain access to the Bubble gum troll booster the player needs to top up the booster by paying 39 Facebook credits 2.59 GBP which then lets the player use the booster three times before having to top up again.

All boosters are created through a crafting model that let s the player choose what to create based on items he has collected. Items are collected by playing gifting or buying them for credits. A booster is only available to craft once you have unlocked it which will be based on progress.

If the player has run out of lives instead of waiting 30 minutes to gain a new one lives can be purchased. Paying 12 Facebook credits will refill the lives counter and give the player 5 or 8 lives depending on if the player has previously acquired the Charm of Life. To find where to buy lives the player can click on the white plus sign next to the counter in the map view interface. If the player does not want to pay for new lives then messages can be sent to friends see where the player asks them to send a life. Sending a life to a friend does not cost anything but is free for both the player asking for lives and the person sending a life.

In the Yeti shop the player can either buy charms see or gifts see . The charms are personal whereas the gifts are for Facebook friends.

When starting Candy Crush Saga for the first time the player is given tutorials in order to facilitate learning the game. Tutorials are not exclusive to the first few levels of the game certain game features are given an introduction at the time they are introduced which can be far into the overall game progress. Such game features can for instance include new boosters and new game modes.

When playing Candy Crush Saga for the first time level one automatically starts. The player is presented with instructions of how to make the most basic of combinations three of the same kind of candy see . This is shown both vertically and horizontally. The game specifies which three candies are to be combined and the player must then combine those. It is not possible to perform other moves than the ones prompted by the game when playing the level for the first time. The player is prompted to do three specific combinations first and then three of their own choice.

Level two starts off with prompting the player to combine four candies which results in a striped candy. The player is then further prompted to combine the striped candy with two other candies which results in the striped candy triggering a line blast. It is not possible to perform other moves than the ones prompted by the game. After performing these two moves the player is told to achieve a certain score within a certain amount of moves. When getting enough points to qualify for the first star of the level at 1900 points the concept of stars and score levels is described to the player.

After completing level 2 the player is taken to the map view where level 3 becomes unlocked. Before being able to play level 3 the player is briefly introduced to the Yeti Shop with a message saying that it can be used to send gifts to friends.

Level three starts off with prompting the player to combine five candies in a T shape or L shape which results in a wrapped candy. The player is then further prompted to combine the wrapped candy with two other candies resulting in two consecutive blasts of three times three candies. Once again the player is unable to perform any other moves than the ones prompted by the game. Once these two moves are performed the player can freely choose how to perform moves.

Level four starts off with prompting the player to combine a wrapped candy and a striped candy that are already placed on the game board at the start. After this single move the player is allowed to perform moves freely.

Level five starts off with prompting the player to combine five candies in a single line which results in a colour bomb. After this the player is prompted to combine it with another candy but the player must use the combination prompted by the game. After this move has been performed an instruction is displayed telling the player the different possible combinations of special candies. However it does not specify which effects that are generated by these combinations.

Level six is the first level introducing a new goal for the game. The goal is to remove all the jelly blocks. It is explained that candies have to be matched in the areas containing jelly for it to be removed. The player is then prompted to make a specific move to remove three candies and also three tiles of jelly. After this single forced move the player is allowed to perform moves freely.

After completing level six the player is taken to the map view and is informed that a new booster has been unlocked the Lollipop Hammer.

When starting level seven for the first time the player is shown how to use the recently unlocked Lollipop Hammer booster. It is described as a hammer that can smash candy .

After completing level seven the player is taken to the map view and is informed that a new booster has been unlocked Five extra moves.

The game board is part of the view that is presented to the player while playing levels in Candy Crush Saga. The term game board signifies the area that contains candies and other elements such as ingredients jelly and frosting not the surrounding landscape such as the score meter and the heart showing the amount of lives left.

Typically the game board consists of a number of connected areas cells arranged in a grid that can be occupied by either candies or special game elements. However there can be more complex layouts as well. For instance the areas containing game elements do not have to be interconnected. There may be multiple sections of interconnected areas that are not connected to each other see . This means that candies can only travel between these areas through falling or using teleporters . Also sometimes the only way to interact with these areas will be through special game elements for instance striped candies which trigger line blasts which make for very challenging levels.

In the most basic version this feature serves the purpose of letting players know their performance while playing the game by showing which level of score they have accomplished. The level of score is determined by the amount of points gathered and compared against predefined levels that will earn the player one two or three stars. Stars are a representation of how well a player is performing on a level. Achieving at least one star is required to pass a level. Achieving more than one stars indicates that a player is performing better than the minimum required and is a factor that helps drive engagement by making players feel more skilled. The amount of points required to achieve one two or three stars is pre defined and typically does not change for any level. However in some implementations it is possible to have a variable score required for different amounts of stars for instance one that is correlated with the average scores of all players playing the game.

In some implementations there are indications of the performance of other players displayed during the play of a level. This information is often based on data from previously completed levels but it can also be related to levels that have been attempted and failed by other players. Performance information can for instance be derived from a social network connected to the game or from databases more directly related to the game. In some implementations players can see the score of other players in real time thus increasing the competitive element of the game. The other players whose performance will be displayed is sometimes chosen by the player sometimes automatically derived from a social network of the player and other times it can be based on other elements such as the performance of all players of the game.

In some implementations the player can see indications of the previous high score achieved on a level while playing it shown by in . It is also possible that no indication of the player s own previous score is shown.

In some implementations the indications of the performance of other players are shown in relation to the score meter. It can be both absolute and relative indications. The indications can be in the form of pictures associated with the players as shown by and in . When the player passes the score of another player or the previous best score the player has achieved a message can be shown to encourage the player and denote the accomplishment. One example of such a message is illustrated by in .

It should be understood that the invention is not limited to using stored scores to show the performance of other players. In one implementation players can see the scores of other players currently playing the same level while they are playing it making it so that the indications of other players scores can be moving in real time during the play of a game.

The score comparisons presented to the player can be given in percentages points and when applicable other indicators for instance time played or number of attempts on a level.

The look of a level as well as the overall look of the virtual landscape can change as the player performs better. For instance after achieving one star during the play of a level the digits shown when scoring points can turn into a different colour. The lookout of the virtual landscape can be come warmer and more colourful as more stars are gained. The look of the game can change according to other variables as well such as the in game view changing depending on how many moves are left in order to convey a sense of urgency.

In Candy Crush Saga the Star Meter also has other important functions. One is that the score of friends from a social network is shown on the meter if there is data available. This increases competition and incentivises players to replay levels in order to beat the score of friends.

Another function is that the amount of stars achieved on each level is shown next to the levels on the map view. This gives players an overview of their overall performance in the game. Also in order to complete a level the player needs to reach the amount of points needed to achieve at least one star.

Upon finishing a level Candy Crush Saga displays Sugar Crush accompanied by audio saying the words. The first thing that happens after this display is that all special candies trigger one after another removing other game elements and gaining points. After all remaining special candies have been triggered the player is awarded for remaining moves if there are any. Being awarded for the remaining moves when finishing a level is important for making players feel successful and skilled at the game and is an important driver for increasing replayability. There are two different end game bonuses that trigger depending on the type of level.

In some game modes players are awarded for their remaining moves by a number of candy fish spawning. The fish are proportional to the amount of remaining moves left. The fish come from outside the game board and randomly seek out candies which are removed upon impact. Players receive bonus score for when each fish hits a candy.

In other game modes players are awarded for their remaining moves by a number of candies turning into striped candies and subsequently triggering. The number of candies transforming from regular into a striped version is proportional to the amount of moves left. Upon a candy transforming from a regular version into a striped one the player is awarded with bonus points.

In levels where the player has a limited amount of time there are certain candies that are marked with a 5 symbol meaning that they give an additional 5 seconds if popped. If any of these candies remain when the time runs out they transform into wrapped candies that subsequently trigger.

Before starting a level players have to select which level to play from the map view. The exception to this is the very first time Candy Crush Saga is played when level one starts immediately. When selecting a level the player is shown information about the level such as the amount of points needed the available boosters that can be used the goal of the level and also the highscores of friends who have previously played that level see .

A difference between playing a level for the first time and playing a previously completed level is that the previous best score of the player is displayed together with the amount of stars achieved see . Also the text that is telling the player what the target goal is in terms of points is changed depending on how many stars the players has achieved before. As can be seen in and the target goal in is 40 000 points which correlates to one star on the level. When the player replays the same level after already achieving two stars as seen in the target goal is displayed as 100 000 points which correlates to three stars. Having the game set up in this way increases replayability by making players focus on always improving but not necessarily too much at a time. If the first goal presented was the one correlating to three stars players could feel inadequate if they get less points than that even if the level was completed.

The player can choose boosters that will in some way affect the game play before starting a level. Boosters are unlocked and gained as the player progresses throughout the game but it is also possible to purchase more boosters. As can be seen in and players can only select boosters that are applicable for the type of level to be played and boosters which they have at least one of. If they player does not have enough boosters a top up can be purchased.

It is also possible to help friends by sending them lives. illustrated one implementation where this can be done by clicking on the icon with a heart and letter on it located next to friends names in the highscore list.

In some implementations the pre level screen shown on a mobile device is slightly different from the one shown on a computer. It has the same core components but the layout can differ. It does not have the information about the level goal in the standard view but this can be shown by clicking on a symbol indicating what the goal is see .

When completing a level the player is presented with a screen that shows the amount of points gained the amount of stars achieved and the previous highscores of friends. This is shown in where the player has earned three stars and is therefore placed on 4th place in the highscore list.

After the post level screen has been closed the player may be presented with yet another screen related to the performance of the just completed level. shows one implementation of this screen which displays how well the player scored in relation to friends highscores together with a message about which friend s that has been beaten.

Both the Post level screen and the screen that shows when a friend has been beaten present the player with an option to share this information. The sharing part is done on a social network to which the game is connected. By sharing information such as which friends the player has beaten competition is encouraged and the viralisation of the game is increased due to people not playing the game also being able to see such messages.

It is possible to help friends by sending lives from this screen as well. As depicted in this can be done with a click on the icon with a heart and letter on it next to the friends names. The tick marks indicate that the player has already sent lives to those friends. The player may only send lives to any one friend once within a certain period of time for instance once per day.

In some implementations the mobile version of the game has a slightly different post level screen. When completing a level the player is given the options of retrying the level or going to the next one. If choosing to play the next level it starts immediately without going over to the map view. A version of the mobile post level screen is shown in .

When failing to complete a level a screen similar to the one shown when completing a level is displayed. The difference is that the screen when failing a level has a broken heart on it together with information stating why the level was failed see . Failing a level can happen due to a number of reasons such as not reaching the minimum score for one star failing to accomplish the goal or by a bomb exploding. The player is informed of the reason for why he has failed the level. Understanding why you have failed a level increases the likelihood that the player will try to play the level again to reach that target for the level. If wanting to play the same level again there is an option to do so. In one implementation the option to replay the failed level is presented with a large and visually significant button.

Games created using the techniques described herein can be played locally on a player s computer or handheld device. The game can also be played over the Internet where the whole game or portions are downloaded and executed on the local machine or run on a remote computer or server. The user s progress in the game and results can be stored locally and compared to the user and other players on the local computer. The progress and results can in an alternative embodiment be synchronised with other players either directly or through a server or social network or gaming platform.

Three platforms in particular are changing the way people expect games to be played. These three platforms are growing at the same time and provide new input possibilities. To date games have not absorbed all the new input possibilities.

The first platform is Facebook. The skilled person will understand that where Facebook is referred to in this document other social network platforms may be used. A Facebook game may be a social game a game you play with your friends. It is rare or unthinkable to launch a game i.e. to play for the first time on Facebook that is a paid game because people playing games on Facebook expect not to pay to access a game. A Facebook game may be played on the internet after logging in to Facebook whether automatically or manually such as from a personal computer.

The second platform is smartphones. Use of smartphones is not always continuous. You may use a smartphone for 5 minutes on a bus and then for 20 minutes on a connecting train for example. The use can have many starts and stops. Not like someone working at an office desk or at a home desk in a conventional way. A smartphone can be on an iOS platform or on an Android platform for example.

The third platform is tablets. What is a tablet It can function as a mobile device and as a non mobile device. The tablet can be a substitute for a personal computer. A user may want a seamless experience between using the game on a personal computer and on a tablet and on another mobile device. A tablet can be on an iOS platform or on an Android platform for example.

A game which works on a plurality of such as all three of the above platforms or more may provide a connected fully synchronized seamless experience. Hence multi platform games are important. Key criteria for multi platform games are they are free they are social stop start use is possible and seamless experience is provided. Such games may be played anywhere e.g. in a mobile environment or in a non mobile environment. Such games may also be played online or offline.

The game must be fun when used in a stop start way and when used for even just short intervals. In an example a game consists of parts or levels each of which runs for about 3 minutes eg. between 1 and 5 minutes. In an example a game is structured in levels so that if successful in a game level such as by scoring a minimum score a user can progress from that level to the next level. In an example a game has about 200 levels.

A game can be optimized post launch. For example if it is clear that too many users are failing to progress past a particular level the minimum score to pass the level can be lowered. An optimized game may be provided as an application update from an application store. In an alternative a game may be optimized by a server sending a revised data file of scores required to pass each game level to a mobile device when a game state of a user is being synchronized with the server wherein the application running on the device replaces the previous file of scores stored on the device required to pass each level with the revised file of scores required to pass each level.

The progress of a player is also synchronised across devices for instance between a handheld device and a computer. This is described in further detail in Appendix A. The player can play on one platform have the progress saved and then continue playing seamlessly on another platform. It is also possible for the player to play on offline devices and having the game synchronise when a connection is available.

In some implementations players can be rewarded for playing the game on multiple platforms. For instance players active on a computer based platform could get a bonus for also installing the game on a handheld device.

Players can also be rewarded for playing multiple games that are related for instance games from the same developer. When choosing to play a new game the player can receive bonuses in another game. This can be triggered by using a link from one game to the other or by games sharing information between one another so that it automatically detects a player that is playing more than one game and subsequently rewards them.

It is also possible that games can have elements in common that enables certain objects for instance boosters to be usable in multiple games. These games can be located on the same or on different servers. In some implementations a booster bought in Candy Crush Saga can be used in another game that shares certain features with it.

One example of an implementation with synchronisation across platforms is as follows A first server for instance one hosting a social network with a first data store storing data relating to the state of a game. The first server is configured to communicate with a first plurality of devices such as mobile phones or personal computers through a first application programming interface where the first plurality of devices is related to a first computing platform.

A second server for instance one hosting a game platform with a second data store storing data relating to the state of the game. The second server is configured to communicate with a second plurality of devices such as mobile phones or personal computers through a second application programming interface where the second plurality of devices is related to a second computing platform.

A third server with a third data store configured to communicate with the first and the second server. The three servers are configured to synchronise the three data stores in such a way that when synchronized the first second and third data store all relate to a synchronised game state.

It is possible for implementations of the game to vary depending on the location of the player. For instance the language can be adapted and translated into different languages. It can also be so that updates of the game are incorporated at different times in different locations in order to avoid interference with the times of the day that players are as most active.

If trying to access the game online as opposed to starting a local version that is saved on the device while updates are being made the player can be met by a message saying that the game cannot be accessed right at that moment see .

The screen in could be displayed instead of the game as a placeholder for when the game is taken offline for instance so that the game can be updated with new features and software.

The game can be implemented so that a player progresses through multiple levels of changing and typically increasing difficulty. shows an implementation of the game with a virtual map layout of a game environment displayed on the computing device used by the game player. As the player travels through the levels in the game his progress is represented as a journey along a path in the virtual map. Representing progress in this manner provides an additional layer of engagement for players and also opportunities for viralisation and monetisation.

The virtual map consists of stages 1 2 with varying number of levels 3 4. The user travels between levels and completes the levels one by one along a path by playing the associated game. When the player reaches the goal of a level the next level is unlocked and the player can play that level in the game. The number of stages and levels can vary depending on the implementation. The levels can be numbered consecutively throughout the game or they can be numbered within a stage it is also understood that other ways of identifying the stages and levels can be implemented. New stages to the virtual map can be added by the game designers at any time so a game may be launched with say 20 levels and after a number of weeks there may be fifty or sixty levels present.

One way of unlocking new stages is to complete the last level on the latest stage. The user is sometimes faced with challenges to unlock the next stage in the virtual map.

In one implementation traveling from one stage to another once all the levels have been completed on that stage requires the help of for instance three friends. The player can ask friends for help by sending an in game message within the game environment or for instance through a social network that the game is connected to. The friends can already be playing the game and do not have to be new players but they can be friends not already on the same social network.

The player can also pay to get instant access to the locked stage. The player can use a combination of help from friend and payment to unlock the new stage. The cost for unlocking can in some implementations be lowered as a fraction of the total number of friends needed when help from some but not all needed friends have been received.

The request for help is sent to the friend who then has the option to accept to help. The request for help can in some implementations be sent using the social network to which the game is connected an alternative implementation is to send the request to someone external to the game via email text message instant message for instance who has to join the game to respond to the help request. This is one of the viralisation techniques implemented in this game.

In addition to the virtual map layout in there can also be other levels or stages that are not part of the progress along the path in the virtual map. Such stages or levels can be present in the game associated with the virtual map at all times or can be unlocked when the user reaches a certain in game achievement. This in game achievement can for instance be completing a specific level reaching a predetermined high score for instance collecting a specific number of stars when completing a level highly skilled gameplay can win the user three stars or paying virtual currency to unlock the stage or level.

The map layout in can be used in games connected to or linked with a social network. It is common that the users on such networks have avatars with for instance a photo of the user and or the user s name. Such avatars can for instance also be a sign or a figure. The user s avatar is displayed on the map layout alongside the level where the user is 6. It is understood that there are different implementations of showing where the user currently is on the map. This can for instance be the latest level the user completed the level with the highest score or the last completed level along the traversed path.

The user can in some embodiments be given the option to select which users should be shown on the virtual map. The users to choose from can be friends on a social network or the user can get suggestions to show friends which meet a certain criteria for instance friends which the player has interacted with the most in the past or friends living in the same geographic area as the player. The user can get the option to choose from other people not being friends on the social network but that meet other certain criteria.

The user can play any of the unlocked levels on the map so the user can go back and replay already completed levels to get a better score or beat friends high scores.

The player is in some implementations of the game rewarded for good gameplay of a level for instance reaching a target score. In some implementations the user has to reach a certain number of points to complete a level reaching this target score can be represented with a symbol such as a star. In one implementation a star is lit when the user reaches a certain number of points in a level. The user can earn more than one star on each level and the levels are re playable to get a higher score.

The player s total number of stars collected in the game can in some embodiments unlock features. The unlocked features can for instance be power ups in game currency or bonus levels.

The symbol representing how well the user has played on each level can be displayed alongside the level on the map .

If the game is connected to a social network or the user has connected with other players in the game the levels will present a leaderboard showing who among the user s connections has the highest score. There can in some embodiments be a notification shown on the map if the user that has the highest score among the friends connected to the game.

The landscape of the virtual map will typically have animated sequences which give a feeling of the map being alive and dynamic. For example trees on the map can sway in the wind animals can move around and the player progressing from one level to another can be accompanied by an animation of a player associated character moving on the map.

In some implementations it is possible for the player to interact with objects on the map in such a way that animations are triggered. For instance clicking on a bird can make it fly into the air and hovering over water can make waves appear.

It is also possible to have any combination of a map that is static but reacts to player input a static map that does not react to player input a dynamic map that reacts to player input and a dynamic map that does not react to player input.

One example of how the virtual map can be dynamic and moving is shown in where as an example a coconut character moves slightly from side to side. A collection of subtle as well as less subtle animations throughout the map will together make the map appear moving and alive.

The game can also be implemented to be played with a limited time or limited number of moves or both over a consecutive set of levels. The score can be collected over the several levels to give the player a score for all the levels completed.

The player can in some implementations play the game in head to head tournaments against one or several other players. The player with the highest collective score over the number of levels will be the winner in the tournament. In some implementations the tournaments are played with real time comparisons of players scores in other implementations the scores of players are compared after finishing a level.

The game can also be played in tournaments with jackpots where the player plays the same level where the same types of game elements are used.

The game can have schemes for giving rewards and bonuses to players. One reason for giving out rewards is to increase player engagement and to some extent to help with monetisation. Players can for instance be rewarded for playing multiple days in a row something that awards persistence and dedication. In other implementations there is a daily bonus available that is gained by every player playing the game online during that day or to players passing a certain secret location during that day. By giving players samples of existing boosters they are given a free preview of purchasable items that potentially can lead to sales in the long run which helps monetise the game.

The virtual landscape of Candy Crush Saga is presented to the player in between levels. This is also referred to as the map view and the virtual map within this document. The player travels along a virtual path as more levels are completed in the game which gives the feel of moving forward.

The looks of the map view is in the style of a physical foldable game board see such as one commonly used for board games. However since Candy Crush Saga is not a physical board game but a virtual one the board is much larger than what can be displayed in a single screen. The player can at any time while in the map view look at all available levels and also scroll through the entirety of the game board. Having such a style gives a strong feeling of actually progressing forward in the game as more levels become unlocked.

When navigating on a map in a game it is sometimes difficult to find desired spot or area of the map if the map is for example too large. One way to solve this problem is to have mini map in an expandable tab connected to the edge of the screen where the player can fast jump to desired location. In this document we refer to the expandable tab and the mini map as the navigator.

If the player does not need to use the navigator then it is unnecessary for it to take up precious screen space. Therefore in one implementation the navigator is only in full view when the player needs it the rest of the time it is hidden with only a small part of it showing see . Clicking on this small part will expand the navigator see and let the player use it. Clicking on the same part again will once more hide the navigator. In one implementation when the navigator is hidden a small tab is placed at the bottom right edge of the screen which will in turn expand the navigator when clicked on see .

When the navigator is expanded the player is provided with a mini map showing an area of the map. The player can press anywhere on the mini map and when doing so the main view will jump to the same location. The player may also press and drag the mouse up or down over the mini map which will then simultaneously scroll the map in the main view.

A map may sometimes be too large to fit on a mini map at least if the player is to make any sense of what it is displaying. One way to solve this problem is to divide the map into areas and on the mini map only show one area at a time.

In one implementation there are clouds on the bottom and or on the top of the mini map to indicate that there is more to be seen. Pressing one of the arrows which are placed on the clouds will take the player to either the next or previous area of the map. The arrow can be pressed both on the mini map and in the main view see and . If changing area on the mini map the main view will also jump to the next area. If the player reaches the end of the map unused areas of the mini map will be clearly marked and therefore indicate to the player that the map is ending. The player can not scroll past this point see .

Even when being able to scroll and click to desired locations on the mini map it may still be difficult to find a specific spot on the map. There are several implementations to make it easier for the player on this point.

In one implementation if the player for example wants to jump to the furthest reached location on the map then there is a home button which will take the player there directly. Pressing the home button will not only take the player to the current location but will also hide the navigator giving the player a full view. With the home button the player can always find their active location in the blink of an eye.

In an alternative implementation the map will also be zoomed in when the player presses the home button and jumps to the furthest reached location this is illustrated in .

Another implementation may be to offer the player filtering and multiple choices of where to jump on the map. There could for example be an icon which when pressed lets the player choose exactly which level to jump to. There could also be an alternative to receive a list of levels the player can jump to which satisfy certain criteria for example all levels with limited moves and ingredients in them. The filter could offer many kinds of choices. shows an alternative implementation of the navigator offering multiple choices and filters.

The player may not only navigate to different locations on the map but can also be presented with the possibility to zoom in and out. If playing a game on a touch screen device pinching ones fingers on the screen would make the map zoom out see . Zooming in on the map would require the fingers to spread out from each other the opposite of doing a pinch gesture see .

Having a zoom in out function can help the player get an overview of a map while at the same time being able to see details and other various interesting parts of it which are connected to a specific area or position. Furthermore zoom in functions on a touch screen device can be helpful if there are interactive parts that may feel to small to press properly. Zooming in makes it easier to target and interact with desired object.

The overall theme of Candy Crush Saga lends a special atmosphere to the game. Everything is candy themed with bright and warm colours used in all animations and pictures. The words used for encouragement throughout the game such as sweet and delicious serve as an example of the candy theme.

As the player progresses in the game new areas episodes are unlocked. Each episode has a related story and often a mini theme that is present in at least some levels in the area. Also the same background picture is used in all levels in the same area. When reaching a new are the background image will change. Each episode also has a specific colour which is used in the virtual landscape view to show the different episodes.

The episodes all have different names each with a candy theme to it for example Candy Town Candy Factory Lemonade Lake Chocolate Mountains Lollipop Forrest and so on.

Within each episode there is a set of levels. The division of levels between the episodes is not entirely linear. The first two episodes consist of ten levels each while episodes three and onward each consists of 15 levels each. This makes it easier for the player to advance in the beginning something that can be important for player retention and engagement.

In the virtual landscape the player follows a virtual path as the game progresses. After completing a level the next one becomes unlocked and the player travels there on the virtual map. There is an indicator showing which level the player is currently on in one implementation the indicator is in the form of an orange arrow bouncing up and down.

The virtual landscape is divided into areas each area representing a different episode of the game. The episodes are also coloured differently with one colour being used consistently throughout one episode area. The end of an episode is marked by a special kind of obstacle that can only be passed with the help of three friends or through a purchase. In this obstacle is depicted with three question marks inside a rectangle with inverted corners. When passing these kinds of obstacles there is a celebratory animation accompanying the passage to signal that the player has progressed into a new episode of the game.

In the virtual landscape see levels that have not yet been reached by the player are shown in a different way than levels already accessible. There is also a difference between unreached levels in an unlocked area and unreached levels in areas not yet unlocked. As can be seen in areas that have not yet been reached are greyed out. This furthers the experience of giving players a sense of accomplishment when reaching a new area since it is reflected by the virtual landscape actually changing slightly.

As already mentioned there are special obstacles that hinder the player from reaching new areas in the game. These obstacles are collaboration blocks which means that the player needs to receive help from friends in order to pass. One such implementation can be seen in . Help from friends can be requested through a social network and the new area will not be unlocked until three friends accept to help. This is a way to increase viralisation as well as player engagement. By helping each other players get a sense of collaboration as well as it being a competitive element to remind the player how far friends have come.

It is possible to circumvent the need of having friends to help pass into the next area by instead paying for it. The amount that has to be paid can be reduced by having some friends help even if the required amount of help for passing without paying is not reached. For example if one friends help the player has to pay more than if no friends help if two friends help a lesser amount has to be paid than if one friends help and if three friends help the player does not need to pay at all.

When reaching a collaboration block which is at the end of each episode in the game except for the first two the player is prompted to select which friends to send requests to. The friends need to have Candy Crush Saga installed in order to be able to provide help but it is possible to send requests to friends who do not yet

To travel from one stage to another once all the levels have been completed on that stage requires the help of three friends. These friends can already be playing the game and do not have to be new players. However instant access can also be bought using a virtual currency. Friends can be asked for help either by clicking the Ask friends for help button or by the sign to the right of the buttons. Once the stage has been unlocked with the help of the three friends all the levels within that stage are unlocked too.

The user can choose to request help from only selected friends or to send a request to multiple friends. There can be a limit to how many friends the player can send the request to and also a limit in time before the user can send a reminder or similar request.

The request for help is sent to the friend who then has the option to accept to help or to decline to help. The request can in one implementation be sent using the social network to which the game is connected an alternative implementation is to send the request to someone external to the game via email text message instant message for instance who has to join the game to respond to the help request. This is one of the viralisation techniques implemented in this game.

The inventions may be implemented with ways of getting past a collaboration block other than asking friends for help and paying for it which are the most common ways of passing a collaboration block. This can be done through to use of Mystery Quests which gives the player the option of completing one or several challenges to unlock the block. Such challenge can for instance be to play one or several past levels with modified goals in order to pass the collaboration block for instance three levels one for each of the locks.

These challenges are typically in the form of replaying a previously completed level but with a new goal to reach for instance a target high score. In a typical implementation the score requirement is higher than it is for playing the level regularly and also no other goals need to be fulfilled. For example if the player gets to replay a level with jelly with a new target high score the player would not need to remove the amount of jellies specified as long as the target score was reached.

In a typical implementation this option to pass a collaboration block in the game is available in three cases if the player is not connected to the Internet if the player has not connected the game to a social network or if the player is not connected to either a social network or to the Internet. If the player is not connected to either a social network or the Internet then the other options available for passing the block such as sending requests to friends cannot be used. However it is possible to have this option available to users connected to both a social network and to the Internet as well. shows the three options typically available for passing a collaboration block.

It is possible to combine the ways of passing a collaboration block. For instance completing one Mystery Quest could make it so that the player only has to request help from two friends once a connection to a social network has been established or that the player does not need to pay as much for purchasing a way through the collaboration block.

In some implementations Mystery Quests are not tied to specific collaboration blocks. For example if the player reaches a collaboration block and completes a Mystery Quest then connects to a social network and receives help from three friends the player will only have to complete two Mystery Quests the next time that option is chosen to pass a collaboration block. If the player then only completes one more mission and then goes on to receive help from friends or purchase a way through the third time a Mystery Quest is chosen as a way to pass a collaboration block the player only needs to complete one level.

If the player chooses to play the mystery quest to pass the collaboration block the player will be taken to a screen showing three symbols representing challenges to be completed as well as specifications regarding which level is to be played and what score is required to pass the first challenge. This can be seen in . In a typical implementation the game randomly chooses a previously completed level and increases the score required to pass it. In other implementations the Mystery Quest levels can be new levels that the player has not completed before.

If the player chooses to continue with the quest another screen is presented allowing the player to choose boosters. This screen is very similar to a regular pre level screen with the difference that instead of the level number it says Mystery Quest instead of three stars it shows a special padlock indicating that it is a Mystery Quest and a special symbol in front of the target score to further indicate that it is a Mystery Quest and not a regular level. One implementation of the pre level screen for a Mystery Quest can be seen in .

If the player chooses to play the Mystery Quest level the game proceeds to the game board screen and the player can start playing. If the player fails to achieve the target score a pop up shows why the player failed. In some implementations using levels previously completed as Mystery Quests the regular goals for completing the level are listed as a reason for failure as well as failing the target score as can be seen in . However even though this is shown as a reason for failing the level the player will in a typical implementation complete the Mystery Quest as long as the target score is achieved even if the other goals of the level are not. In other implementations the player can be required to achieve both the target score and other goals for the Mystery Quest to be completed.

However if the player manages to achieve the target score on a Mystery Quest the level will be completed. Completing a Mystery Quest level will take the player to a post level screen similar to a regular post level screen but with the same differences as the pre level screen. One example of such a post level screen is shown in . After this there will typically be an animation to signal that the player has completed the level such as the padlock going from being locked to being unlocked. There can be other ways to show a post level screen after the animation of unlocking the padlock has been shown.

After completing a Mystery Quest and pressing Done on the post level screen the player is typically taken back to the main Mystery Quest screen. This screen will then show the player the overall progress with the Mystery Quest which in a typical implementation consists of three levels. In it can be seen that the player has completed the first quest and that the next one will become available after a certain period of time 23 hours 59 minutes and 46 seconds in the figure.

In some implementations the player needs to wait 24 hours between completing each of the three levels of the Mystery Quest. In other implementations the wait time could be less or none at all. It is also possible to use other criteria for accessing the next Mystery Quest such as getting more stars on previously completed levels.

Typically the player will use a life for each failed attempt of clearing a Mystery Quest level just as is the case with regular level. It is also possible that the Mystery Quest levels do not affect the player s life total or that it uses up another kind of resource as such as boosters.

It is possible for Mystery Quests to be used for other reasons than to pass a collaboration block. For instance there can be bonus levels within the game that can only be accessed through completing Mystery Quests. In some implementations Mystery Quests can be a way for players to earn boosters in the game without having to purchase them. It is also possible that Mystery Quests are only available at certain times such as between 9 PM and 10 PM each day or on specific days.

For players who are not connected to friends through a social network or players who are connected but only have very small social networks an alternative way is to connect them to other players if they want and find proxies for the social experiences that existing networks provide.

It is important to allow players who otherwise would be stuck at a collaboration block or other social interaction tools to also be able to progress in the game. This is important to minimize the churn and to allow the game to be a fun experience for a larger portion of the players.

One such implementation is to drive installs of the game using new channels SMS E Mail Twitter etc. This will boost DAU create engagement by creating social connections and communication channels with those connections. It may also increase revenue by keeping players in the game.

This alternative approach may be used for interaction for instance when a player reaches a collaboration block or runs out of lives. The game prompts player to ask for help from other players based on some user derived player characteristics such as location player game experience. The player gets a prompt to get help with a generated but editable alias and they send the message. If the player s Push Notification PN settings are set to off include the requirement to turn PN on. The client registers the player request user ID with the server. Server generates a response granting the user request on a random basis from 5 to 55 minutes from request. And sends a PN to player. After the player has completed a single loop request PN request grant. They become capable of receiving help requests when they launch the game.

When a standalone player a player with no or only a few friends connected to the game or to a social network reaches a blocker in the game this alternative approach gives them a way to extend their game play by asking for help. Players will be able to select where they ask for help from through SMS Email Twitter etc.

Upon Completion of the loop they will receive the requested help allowing them to continue in the game.

This approach can be used for collaboration blocks that the player can request lives request other help in the game. It can also be implemented so that the player can send invitations to the game and if the recipient will join the game then the inviting player may get a reward.

The player that receives the request for help can click on the link on for instance his mobile device or computer.

The recipient will be taken to the link destination where the client device is detected and it is identified whether the player has already installed the game on the device. An exemplary overview is seen in . This can for instance be done using a so called URI scheme as described below. If the recipient does not have the game already installed he is taken to the appropriate webpage or application store to download or activate the game. This can for instance be the Apple or android app stores or to the Facebook app page. There are different options available to implement this functionality and the identification of the device can be done on the specific device or on the server. The player that has sent a help request will be notified when he has received the requested help. The help request experience can be seen in .

When a player has run out of lives or is stuck at a collaboration block he or she can send a request for help via SMS. The SMS consists of a short message describing what help is wanted and a link. The message and link can be sent to one or more receivers. The link contains info on who sent the request what the request was for and a timestamp. When the receiver clicks the link the required help is sent. Link usage is kept track of in the database so a link cannot be reused by the same user. If the player does not get help within a certain time span he or she gets help from themselves looks like someone helped them . This is only to reward the behavior of asking for things and its use is limited.

The data is then encoded in Base64 is replaced by  and is replaced by empty string. The link is a normal http link. Nothing is stored server side until the receiver clicks the link.

Push notifications are used to close the loop and are also limited per 24 h period. In some implementations they are not needed for the help to get sent.

Players can choose to be notified of certain events in a game. The notifications may be both pushed as well as only available once a player logs into the game. Notifications can be sent on both stationary computers and mobile devices depending on the players platform of choice. It is also possible to have notifications that stretch across multiple platforms for instance they can pop up on both Facebook and on a mobile device at the same time.

 Push technology and subsequently push notifications describes communications in which transaction requests are initiated by a publisher or central server as opposed to pull technology in which the receiver or client initiates a transaction requests. Typically the player can configure in which way push notifications should be received from a range of available options such as 

Banners Notifications are shown at the top of the screen and automatically disappear after a set period of time typically a few seconds unless the player interacts with them. A typical implementation of a banner notification can be seen in . Banner notifications can state information regarding the notification or it can simply state which game the notification is coming from. It is in a typical implementation possible to interact with banner notifications for instance by clicking on them. Typically clicking on a banner notification will bring the player into the game.

Alerts Notifications require interaction from a player before disappearing typically they appear in the middle of the screen. A typical implementation of an alert notification can be seen in .

In a typical implementation the player can choose which events to be notified about. shows the settings where a player can choose to be notified about certain events. In some implementations the player can be choose to be notified when a new Mystery Quest is available or when the player has full lives. In other implementations the player can choose to be notified regarding a variety of different events such as the following 

In a typical implementation the player can choose to interact with notifications in various ways some of these are shown in for example 

In some implementations where notifications are pushed the player will only get the first notifications pushed subsequent ones will not be seen until the player chooses to acknowledge the first one. This is because players should not feel irritated or overwhelmed by notifications.

Notifications can also be implemented so that they synchronise across platforms. For instance if a player has been notified about an occurrence it can be sent to both a mobile device and the Facebook platform but after acknowledging the notification on one platform it also disappears from other platforms. Notifications can be sent in various ways for instance 

In the virtual landscape levels are not simply represented by numbers signifying which level it is. There are also symbols that correlate to each game mode depending on what the goal is in that mode. There are five different symbols 

In the map view the player can hover over an unlocked level to display a thumbnail of it see . This makes it easier to find specific already completed levels and can also give the player an idea of what to expect before actually starting a level. Thumbnails cannot be displayed for levels that have not yet been reached. If trying to view one of these a symbol of a padlock will be in the place the miniature version of the level is supposed to be.

The thumbnail can also display how well the player has done on the level if he has played it previously. This can for instance be represented with the number of stars the player has received on that level the actual score or some other indication.

The thumbnail can also display the player s position on the high score table in relation to the player s friends or showing what friends are on the high score table. This can be a driver for the player to replay the level to beat one of the friends.

In order to give players a better overview of their progress and overall performance in the game Candy Crush Saga shows the amount of stars achieved on a level adjacent to the level node. When hovering over a level node the stars are instead displayed adjacent to the thumbnail.

Games created using the invention described herein can be connected to or linked with a social network such as Facebook or Google or a games platform with different players who can interact and see each other s progress. It is common that the users on such networks have avatars with for instance a photo of the user and or the user s name. Such avatars can for instance also be a sign or a figure.

The social network can be located on a server that is different from the server on which the game is located the game and the social network can also be located on the same server. In some implementations there is a direct live connection between the social network and the game platform that continuously synchronise them in other implementations the two platforms synchronise at certain intervals such as when the player logs into the game. The players progress when having played in offline mode for instance completed levels and score for instance if the player is travelling in a tunnel can be synchronized when the player is connected to the internet.

The user and his friends avatars can be displayed in the game or in relation to different levels in the game to show the player s progress. The avatars can also be shown in relation to indicators of the player s skill level or high score. In some implementations the avatars can be derived from a social network to which the game is connected in other implementations they can be derived from a database related to the game. It is possible for the avatars related to users to change depending on the overall progress or performance in the game. For instance an avatar can become larger or more visually advanced as the player plays the game for a longer time.

The user can connect with other users of the social network either as friends on the social network or as friends within the game environment. The player can interact with other players he is connected to on the social network or who are playing the same game.

The game can be implemented to synchronize game state information and or retrieve and connect to the social graph information and user profile of the player on a social network. It can also be connected to a proprietary network related to the game or the game developer.

The game can also be implemented so that it is connected to a plurality of social networks. The user can be given the option to select what information that can be derived and shared with which social network.

One example of how the game can be connected to a social network is the Facebook s Open Graph API allows websites and applications to draw and share information about more objects than simply people including photos events and pages and their relationships between each other. This expands the social graph concept to more than just relationships between individuals and instead applies it to virtual non human objects between individuals as well. A game can typically share in game events such as that a level has been completed that a player has passed a friend in the game or beaten a friend s high score on a level. The game can also post events such as that a player has purchased objects in the game or received objects from other players of the game.

When showing the pre level screen players are presented with the highscores of friends. This gives an opportunity to know beforehand what to aim for and is something that increases the competitive element in the game. The information about friends scores is derived from a social network connected to which the game is connected. It is important for further increasing the engagement and of players and to some extent viralisation since players are constantly being reminded about the performance of others which can incentivise players to try harder.

In some implementations each area in the game can have a Candy King meaning the player within a network of players that has the best performance on the levels in that area.

Another feature in the game that increases the competitive element is that friends progress on the virtual map is shown. Even if the player has not unlocked or reached the areas in which friends are playing their progress can still be shown by means of a picture associated with the player being displayed next to the level they are currently at see .

It is also possible to invite new players to play the game. These can be invited through the game platform or through a social network to which the game is connected. In some implementations the game suggests which players to invite. This suggestion can for instance be based on if the players have played other games from the same developer if they are active on a social network or if they seem to like other games in the same genre. It is also possible for the suggestions to be based from data related to a social network such as how often they interact with other players or how often they log in to the social network.

One aspect that increases the competitive element of the game is that messages can be sent to friends for instance related to beating their scores or passing them in terms of overall level progression. In some implementations the game prompts the player to send a message to signal that a friend has been beaten. This message can be edited by the player or it can be a pre defined version suggested by the game.

The messages can be generated on a server hosting the game or on a server hosting a social network to which the game is connected. Information used in the message can for instance be derived from one of the databases to which the game is connected or from databases related to networks to which the game is connected.

One aspect of Candy Crush Saga that increases the viralisation and engagement of players is the ability to send gifts to other players which help them in the game. It is possible to give certain gifts for free such as one extra life. The option to send free lives is available for instance through the pre level screen and the post level screen. When starting the game the player is presented with a list of friends to send lives to as .

After this screen the player is presented with new messages. Gifts sent from other players are displayed under messages and certain free gifts such as lives can easily be reciprocated. In clicking Accept would automatically send a life back to the friend who sent one.

In some implementations the game prompts players to send lives to other players that have run out of lives. When a player completes a level after receiving help from a friend a thank you message can be sent to that friend either automatically or manually. This message can contain an item of value. In some implementations the player helping another player can get other benefits such as special symbols or marks being displayed next to their names. Recognition is another benefit that can be awarded to players who help others.

In the mobile version of the game the player is presented with messages when logging in. Messages that are presented can be related to the player receiving lives and friends requesting lives. This is shown in . After receiving a life from a friend the player is asked to send a life back. If choosing to send a life back in response the friend who originally sent it will not get a request to send back yet another life. So this chain of events has two steps if a player starts out by sending a life without request step 1 is sending a life and step 2 is the recipient sending a life back in response. If a player starts with requesting a life the chain of events has three steps step 1 is requesting a life step 2 is receiving a life step 3 is sending a life back in response.

It is also possible to buy gifts in the Yeti shop and send these to friends. Such gifts are in the form of boosters that can be used either during a level or before a level.

Sending Extra Moves to a Player that is Stuck on a Level for a Certain Number of Days Failed Attempts

Another way of helping friends is to send extra moves. This is not something that is possible to do to all players at all times but instead certain criteria must be fulfilled. The criteria are related to how long a player has been stuck on the same level. When selecting the icon Play with Friends a list of friends is presented see . Some of these friends will have been stuck on a level for an extended period of time and the player then has an option to help these players by sending three extra moves free of charge. These moves are different from the booster giving five extra moves not only because the amount of extra moves is lower but also because the booster is only usable and available on a specific level. This is a way of facilitating the harder levels of the game by receiving help from friends.

The game can also prompt the player to send extra moves to friends that have been stuck on the same level for an extended period of time. In some implementations this period of time is two days. In other implementations the criteria for a player being stuck is related to the amount of times they have tried and failed a level. The prompting is for instance done when a player logs onto the game as shown in . This increases engagement by helping players when the game is particularly difficult and also adds a sense of collaboration and community among players. When a player has received extra moves this is indicated by a ribbon enveloping the node of the level in which the moves can be used see .

In some implementations the player can receive help from multiple friends. Help from multiple friends can be used at the same time or subsequently. When a player completes a level after receiving help from a friend a thank you message can be sent to that friend. This message can have different implementations such as the ones described in the passage above about a thank you message related to sending lives.

Candy Crush Saga has a storyline that runs through the game. The main character is a little girl that goes around helping and defeating various creatures. At the start of the game as well as at the start of every new episode there are animated sequences. These sequences tell the story of how the girl goes around the world of Candy Crush Saga and how she overcomes obstacles that are presented to her. shows an example of an animation that is displayed at the start of a new episode.

In some implementations an area will start off as being slightly dirty with a sad atmosphere to become colourful and full of love and warmth as the player progresses through the levels. Areas become even more happy and colourful as the player earns more stars even on previously completed levels.

The player may in some implementations select subgroups of all available friends or filter the friends to only show the friends that also are playing the game. An exemplary implementation is shown in and .

The friend selection may appear when the player is to send requests to other player or ask for help. Exemplary implementations may include 

By way of example one implementation where the player can select to filter the friends may be based on a certain criteria such as the level of interaction the friends have had in the past or the skill level or progress in the games. These different criteria are illustrated with a pre filtering in three tabs in a pop up window in the game. This popup window can be automatically initiated by the game or requested by the player through for instance pressing a button in the game.

The list of friends may be populated from friends of the player that are also active in the game or only from friends on a social network. shows the first tab open where friends from a social network who have installed the game are listed. In one implementation the default mode is that no friends have been selected. Clicking on a friend s picture or name will select that friend and a tick mar may appear to indicate that it has been selected.

Listed friends may be prioritised in the way they are shown in the list to the player. One such criteria in which the order of the listed friends show may be if they have paid for something in the game. Within that group players may be higher ranked if they have spent more money or if they have spent more money within a specific time period. Another criteria may be that the listed friends have been active in the game within a certain time period or with a certain activity level. Another criteria may be that the listed friends are ranked base don how many total game invites they have received to date highest first.

If the user has no friends playing the game this tab may be renamed Friends playing other games and the same prioritization may be applied to these game network players.

If the user has no friends at all playing games according to the filtering criteria then the tab may not appear.

The third tab shown in shows friends on the social network that the player previously have sent a request to. Only the friends that have not yet responded to the request are listed here. In an alternative implementation only the friends that have not yet installed the game may be presented in this tab. The player may tick some of the friends to indicate which to send a reminder to.

The friends listed in the different tabs may be prioritised further. The following refers to the tabs all friends and remind friends but the person skilled in the art will understand that this may in some implementations also be applied to other filtered groups.

Ideally this list should be easy to reorganise. E.g. in month 1 the focus might be on virality so we would prioritise the game network s players known to be viral but in month 2 we might want to focus on monetisation so we would want to prioritise the game network s players who spend a lot.

Prompting invitees may be stopped at some point so that they are not being spammed. For instance invitees who have received 10 invites should no longer appear in the list.

Friend selector pop ups may be customized according to two factors 1 the user who sees them and 2 the current priorities of the game environment where it has been implemented.

For example the game team wants to push monetisation so in the Send moves pop up the user s friends are arranged according to their spend and so only friends with the highest spend appear in the pop up.

The standard implementation for showing popups is to show all friends. Reasons for customizing the popups can be several 

These may also be combined e.g. if the game team wants to reactive lapsed spenders they might want the send moves pop up to display each user s friends in order of spend but to display only users who have been inactive for 10 days.

There are many possible approaches. Customisation could be approached on a game specific basis using only information relating to a single game e.g. the game could customise pop ups using only the game s data This information is stored in the game s own database. But customization may be much more powerful if it used data from across the games company network using data from all games. That information is typically stored in a database.

Customisation on a game specific basis the server creates the user rankings based their past behaviour in the game and that determines which users the server sends to the client. The client would simply display the users selected.

Customisation on a game company network basis we create user rankings based on information taken from a database covering all their activity within the game company network. The rankings would be stored in a system would be updated at least on a daily basis and would be available to all games using that framework. An individual game s servers would pull the rankings out of the system and determine which users to send to the client. The client would simply display the users selected.

Candy Crush Saga has both music and other audio effects that are important for the overall feel of the game. All sounds and music have the same warm feeling to them as the colours and animations.

Audio effects are always played as soon as something is happening in the game whether it is due to an input from the player or if it s some kind of automated event. For example an automated event could be when the user starts the game and a pop up appear suggesting that the player should send gifts to friends. When this pop up appear there is a discrete swishing sound to make the player aware that something happened. Another automated event could be before starting a level and a message screen shows up saying what needs to be done to pass the level before it automatically disappears again.

For all objects that can be interacted with in the game there is always either a visual notification a sound or both to let the player know that something in the interface can be interacted with. For example in one implementation there is a shop icon that highlights starts swinging and lets off a short sound when the mouse is hovered over it.

The sounds played to give indication of interactable objects are always non disturbing sounds that the player does not even think about are there unless someone points it out to him.

Sounds and effects are not only there to indicate when an interaction is possible. They are also present when something is being or has been interacted with for example a click on a button would make a certain sound and sometimes change the appearance on some of the buttons available. shows one implementation where a play button looks like a wrapped candy and when pressed the wrapper on the button becomes wrinkled.

Clicking on a candy when playing a level would also give a visual notification. In one implementation the candy would be highlighted and so the player will know what candy has been chosen. In another implementation a frame would appear around the chosen candy see .

When making different kinds of switches there are also different kinds of sounds and animations connected to these. There is one sound if the player tries to make an invalid move another sound for a match of three yet another sound for a match of four and so on. When candies are removed there is a small animation of stars in the emptied space. This adds to the visual feeling of the game.

The game encourages players to make good moves and the sounds made when generating special candies are triumphant sounding and can give players a feeling of satisfaction.

Triggering special candies also have their unique sounds and visual effects. Animations with lines and stars are shown to emphasize how good it is to use these in the game and how much it helps the player. shows a collection of several implementations of animations that are shown when various game elements are being triggered or removed.

If getting a cascade of matches falling one after the other then there is yet another sound together with a message shown on the screen saying either Delicious Divine Sweet and Tasty depending on how many matches were made with only one move. Together with these visual messages there is a voice saying them out loud in order to compliment and motivate the player and as a result adding more feeling to the game. The same thing happens when completing a level there is a voice and a message saying Sugar crush in order to make the player feel like a good player.

Music is constantly played while displaying the virtual landscape as well as when showing the game board. There can in some implementations be different music playing in a level compared to when viewing the virtual landscape.

Candy Crush Saga has implemented a background music that creates a state of mind of the player that is desirable to optimize engagement virality and monetisation.

Weird and jarring descending passages in an unusual mode creates a slightly unpleasant and jittery feeling after the contrasting happy swinging jolly music of the game play subconsciously makes the player speed up and get onto the next gameplay screen where normal tonality and harmony resume 

Three platforms in particular are changing the way people expect games to be played. These three platforms are growing at the same time and provide new input possibilities. To date games have not absorbed all the new input possibilities.

The first platform is Facebook. The skilled person will understand that where Facebook is referred to in this document other social network platforms may be used. A Facebook game may be a social game a game you play with your friends. It is rare or unthinkable to launch a game i.e. to play for the first time on Facebook that is a paid game because people playing games on Facebook expect not to pay to access a game. A Facebook game may be played on the internet after logging in to Facebook whether automatically or manually such as from a personal computer.

The second platform is smartphones. Use of smartphones is not always continuous. You may use a smartphone for 5 minutes on a bus and then for 20 minutes on a connecting train for example. The use can have many starts and stops. Not like someone working at an office desk or at a home desk in a conventional way. A smartphone can be on an iOS platform or on an Android platform for example.

The third platform is tablets. What is a tablet It can function as a mobile device and as a non mobile device. The tablet can be a substitute for a personal computer. A user may want a seamless experience between using the game on a personal computer and on a tablet and on another mobile device. A tablet can be on an iOS platform or on an Android platform for example.

A game which works on a plurality of such as all three of the above platforms or more may provide a connected fully synchronized seamless experience. Hence multi platform games are important. Key criteria for multi platform games are they are free they are social stop start use is possible and seamless experience is provided. Such games may be played anywhere e.g. in a mobile environment or in a non mobile environment. Such games may also be played online or offline.

The game must be fun when used in a stop start way and when used for even just short intervals. In an example a game consists of parts or levels each of which runs for about 3 minutes eg. between 1 and 5 minutes. In an example a game is structured in levels so that if successful in a game level such as by scoring a minimum score a user can progress from that level to the next level. In an example a game has about 200 levels.

A game can be optimized post launch. For example if it is clear that too many users are failing to progress past a particular level the minimum score to pass the level can be lowered. An optimized game may be provided as an application update from an application store. In an alternative a game may be optimized by a server sending a revised data file of scores required to pass each game level to a mobile device when a game state of a user is being synchronized with the server wherein the application running on the device replaces the previous file of scores stored on the device required to pass each level with the revised file of scores required to pass each level.

See for instance the method and system described in U.S. application Ser. No. 13 479 107 filed on 23 May 2012 and incorporated in this document.

The system and method described herein can be implemented together with a game in which players can see their own and also their social network friends game level position on a virtual path or other virtual world and in which game state information is fully synchronised across different platforms such as iOS desktop and Android via Facebook or other online social network so that a player can seamlessly stop and re start playing the game on any of those different platforms.

Some implementations of the game allows for the game to be synchronised between different devices or platforms.

The game can for instance be played in an offline mode on a handheld device using locally stored information on the handheld device. The device can store all or some of the levels that are available for the player to play in the game. Some of the features in the game can be locally run on the device and dependent on the local machine. This can for instance be that if the game is implemented to regenerate lives after a certain period of time then the time can be locally decided based on the clock on the device. In some implementations the central game server clock can override the local clock when the local device has been synchronised with the server.

A game can be implemented so that the player knows if it has synchronised the available data with the central server or servers. This can for instance be through a coloured symbol or a check mark that indicates that the information is up to date. shows one implementation of this where a symbol on the bottom right corner of the screen has a spinning animation while synchronizing and when synchronization has completed the symbol turns into a check mark symbol.

The game can also indicate if it has been able to establish a connection with the central server for synchronisation or if for instance the network connection is down. That the device is offline can for instance be illustrated with a greyed out icon.

The game can be implemented to synchronize game state information and or retrieve and connect to the social graph information and user profile of the player on a social network such as Facebook or Google .

The game can also be implemented so that it is connected to a plurality of social networks. The user can be given the option to select what information that can be derived and shared with which social network.

One example of how the game can be connected to a social network is the Facebook s Open Graph API allows websites and applications to draw and share information about more objects than simply people including photos events and pages and their relationships between each other. This expands the social graph concept to more than just relationships between individuals and instead applies it to virtual non human objects between individuals as well. A game can typically share in game events such as that a level has been completed that a player has passed a friend in the game or beaten a friend s high score on a level. The game can also post event such as that a player has purchased objects in the game or received objects from other players of the game.

There are six different game elements candies . They can be combined in series of 3 4 or 5 in a line either row or a column or in combinations in the shape of a T or L form.

The game elements have certain sizes all similar but not identical making it possible to have a specific maximum number of rows and columns with candies.

The game board is dark semi transparent and placed on top of a background picture which is tied to the story of the game.

In the game board each element has a square space that is delimited by light horizontal lines and darker vertical lines. The lines do not cover the full square but leave a gap in all the corners.

New special game elements are introduced throughout the game to increase the difficulty. For example a layer which has to be removed by matching a candy covered by the layer jelly or an impassable block that has to be removed by matching candies next to it a number of times Frosting .

Most levels have two separate goals one involving certain actions remove jelly get fruits to the bottom and another related to score. This makes for a more challenging game.

The player is awarded points for each combination of at least 3 candies enabling high score comparisons with other players as well as a challenge to beat oneself.

The amount of points gained by a combination is shown upon completing a combination in the same colour as the candies used in the combination.

The score given for different combinations is not linear but formed in a way to encourage longer combinations and a more thought out approach of playing the game.

Give Bonus Points in the Form of Certain Schemes to Player when Finishing a Level Sooner than Necessary

When a player finishes with moves left bonus points are awarded. However it is not simply a point bonus there are at least two different bonus schemes that can trigger. One transforms a number of candies into striped candies the other summons jellyfish that remove candies on the game board.

There is a booster that removes three columns by turning three candies into striped candies. This booster is in the form of a coconut wheel.

By making certain combinations of candies special game elements will be produced. These are formed by making combinations of 4 candies striped candy 5 candies in a row or column colour bomb L or T shapes of 5 candies bomb candy .

A colour bomb candy will be produced by combining 5 candies in a row or column. This item will either remove all candies of a certain colour if combined with a regular candy or it will remove all elements of two colours if combined with a bomb candy or it will transform all candies of the same colour into striped candies that subsequently trigger if combined with a striped candy .

By combining 5 or 6 candies into a L shape or a T shape a bomb candy will be produced. This removes elements in a rectangle shape with a three candy diameter.

It is possible to combine striped candies when doing so one column and one row of candies will be removed.

It is possible to combine a striped candy with a bomb candy when doing so three columns and three rows of candies will be removed originating from the spot where the combination was made.

It is possible to combine two bomb candies with each other. When doing so a rectangle shape with a diameter of 5 candies will be removed by each combined bomb candy.

When combining a striped candy with a bomb candy a special visual animation is triggered in the form of a giant candy moving first horizontally in both directions from the point of origin then vertically.

When combining a colour bomb with a striped candy all other candies of that colour will also be transformed into striped game elements that automatically trigger.

The first and the second area in the game each has 10 levels. Area three and all subsequent areas each has 15 levels. This is not an obvious division but might make it feel easier in the beginning.

The player progresses through the levels of the game which is visually represented on a map. This gives the player a more tangible way of seeing progress than if levels were just represented by a number.

Having a tool for helping players to easily navigate and jump between areas on a map with as little effort as possible. One implementation is to have an expandable mini map which the player can scroll or click on to jump to desired location or press a button which instantly takes the player to the furthest reached location on the map.

Having a tool that helps players getting an overview of a map either by the help of a special designed mini map or with a zoom in out function.

A small thumbnail version of each level can be shown by hovering the cursor over the level icon on the map. This gives the player a feel for what the level looks like before playing it and makes it easier to find a level when wanting to replay it.

The highest level reached by a player is indicated by an orange arrow pointing at it. This makes it easy for the player to find the current level and also facilitates the visualization of how far he has progressed.

All available levels in Candy Crush can be viewed in the map even though they haven t been unlocked. However a padlock symbol is shown to represent that a level is yet to be unlocked and that it currently cannot be played.

At the start of Candy Crush the player is greeted by an encouraging message Your adventure starts today Click here to play level 2 

Candy Crush offers a tutorial in the beginning of the game to introduce the player to new concepts. Basic concepts possible combinations and the different game modes are explained among other things.

Different game modes makes for a more diverse game. Candy Crush offers at least five different game modes Score Jelly Ingredients Orders Time

There are game elements in Candy Crush that have to be removed before objects can pass through the space they occupy. These are in the form of frosting blocks and require candies to be matched next to them a certain amount of times before they disappear.

When selecting a level from the map view information about the level is displayed together with an array of boosters that can be purchased and or activated for that level. Information include previous scores of friends and specific instructions for the current level.

The previous high score of friends can be seen before playing a level while playing a level and after a level has been played provided that friends have played the level before . This increases competition and gives a sense of community at the same time.

The player can select boosters before playing a level as well as during the play of a level. The boosters which can be used in the two situations differ. This facilitates and adds more depth to the game.

After finishing a level the player will get feedback to how his score relates to that of friends playing the game. An option is given to share results with friends possibly accompanied by a message saying something along the lines of I beat your score .

The player is provided real time feedback in relation to the score during play of a level. This is done by a meter being filled the meter having three different levels represented by one two and three stars respectively.

In the map view the player can see results of previously completed levels in the form of how many stars were attained in those levels. This makes for a easy overview of the overall performance in the game.

The player starts with 5 lives that are used up when failing to complete a level. These lives are then replenished with one life every 30 minutes.

When hovering over a level with the cursor the player is presented with a thumbnail version of the level showing the layout of it. Also displayed on this thumbnail is the performance of the player if applicable and also the performance of friends if applicable.

Candy Crush very quickly recognizes when there are no possible moves left. When that occurs the candies on the game board are re shuffled. When re shuffling there will be no combinations automatically triggering i.e. 3 or more candies are not placed adjacent to each other.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path in which the game is fully sync d across different platforms such as iOS desktop and Android via Facebook and in which the gameplay for each level can be enhanced through the use of an acquired item.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path and in which the game board contains switchable elements that can be matched with other switchable elements and switchable elements that cannot be matched with other switchable elements on the game board where one of the goals for completing a level is to interact with the game board in such a way that a predefined number of non matchable switchable elements are placed in any of a plurality of predefined areas on the game board.

A match 3 game in which the player has to satisfy a plurality of criteria within a limited number of moves to complete the level the criteria include at least one of the following 

There are multiple technical challenges facing the designer of computer implemented games. These challenges can be broadly categorized into the following areas engagement viralisation and monetisation .

We will look first at engagement which involves designing game play to be engaging and rewarding to players. This typically requires games to be easily understood at their simplest or introductory levels providing rewarding game play with even quite simple game mechanics but becoming progressively more challenging so that players are not bored but remain engaged and develop rewarding skills Effective engagement requires various forms of feedback to reinforce players sense of success and accomplishment. Effective engagement can be greatly magnified if the game has a social aspect for example it is linked into a social network so that game players can interact with their friends in the social network. The game can then transform into something that goes far beyond a simple solo game experience into a shared journey.

 Viralisation requires a game to be include various techniques that encourage players to share the game with others encouraging them to play the game. It is a key technique in enabling mass scale distribution or penetration of games. Viralisation can be especially effective when the game is integrated into a social network environment in some manner so that the game can then propagate through the network of player s friends and their friends and so on.

 Monetisation covers those techniques that enable revenue to be generated from a game this involves many challenges because the monetisation techniques need to be acceptable to players and in no way undermine engagement.

A successful and original game will requires a team of game designers to solve complex problems of engagement viralisation and monetisation this can take many months of skilled work and not infrequently a great deal of trial and error testing of new ideas functions and game mechanics before a game successfully combines all these elements into a new experience. The skilled game designer will appreciate that there is an almost infinite number of possible combinations of game features and mechanics available to him although in isolation these features may be known it takes inventive insight to create a combination where there is some synergistic effect or where the whole is more compelling than the mere sum of its parts.

In this section we will summarise some of the combinations of features that have made Candy Crush Saga one of the most popular casual social games in the world.

A gaming system in which functions and features relating to sharing players game state information including levels and achievements on a virtual path or other virtual world with that player s social network friends is continuously or regularly optimized for engagement and monetisation by continuously or regularly monitoring analysing player behaviour and interaction such as monetisation.

A gaming system in which a single user database which may be distributed or centralised tracks all metrics for all players including all game state information irrespective of the platform used by each of those players and that single user database is accessible by several different games such as a match 3 switcher and a match 3 clicker a bubble shooter etc.

A casual social game connected to a player s friends through a social network in which every change in the game state such as every move of a game piece by the user and every consequential change in every game piece on the game board is accompanied by sound and or visual feedback to provide immediate positive gratification to the player.

A match 3 switcher game in which players can see their own and also their social network friends game level position on a virtual path or other virtual world and in which game state information is fully sync d across different platforms such as iOS desktop and Android via Facebook so that a player can seamlessly stop and re start playing the game on any of those different platforms.

A match 3 switcher game in which a player s score and game level position and also the scores and game level positions of all their social network friends also playing the game is fully sync d across different platforms such as iOS desktop and Android via Facebook.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path or other virtual world and in which each level of the game can be failed and if a level is failed the game automatically offers the player extra moves to purchase to carry on playing the game.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which in app purchases are bought for real or virtual currency by touching an icon of the booster shown next to the gameplay board and then touching a buy button that is subsequently displayed.

A match 3 switcher game in which a player s score and game level position and also the scores and game level positions of all their social network friends also playing the game is fully sync d across different platforms such as iOS desktop and Android via Facebook and there are sections of the game that must be unlocked through either help from those friends or through a purchase.

A match 3 switcher game connected to a player s friends through a social network in which friends can send gifts boosters extra moves or extra lives to one another.

A match 3 switcher game in which players can see their own and social network friends game level position on a virtual path or other virtual world and where a visual prompt is displayed by the game if a friend s high score has been beaten by that player the prompt enabling the player to send a message to that friend.

A match 3 switcher game in which players can see their own and also their social network friends game level position on a virtual path or other virtual world and where the player can play the game in offline mode on one platform device and the progress in the game and other game state information is synchronised with a remote server when the device is online again and the player can continue playing the game on another platform.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path or other virtual world and the game enables the player to buy a permanent booster which can be used without limit in time.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which successive levels have different difficulty rankings to introduce variety even without a new game mechanic being introduced e.g. after a difficult level there is an easier level.

A match 3 switcher game connected to a player s friends through a social network where some or all of those friends are sent a message prompting the friend s to assist the player once that player has played but not completed a level for more than a predefined time or predefined number of attempts.

A match 3 switcher game or other kind of social casual game in which players can see their own and their social network friends level position on a virtual path or other virtual world and where the player is prompted to notify a social network friend when the friend s high score on a specific level has been beaten by that player.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which the game state information is fully sync d across different platforms such as iOS desktop and Android via Facebook and in which the gameplay for each level can be enhanced through the use of an acquired item such as a booster.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which the game state information is fully sync d across different platforms such as iOS desktop and Android via Facebook and in which the gameplay for each level can be enhanced through the use of an acquired item such as a booster and where the game state information relating to the acquisition or use of an acquired item is synchronized across several different platforms.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path or other virtual world and in which the game board contains switchable elements that can be matched with other switchable elements and switchable elements that cannot be matched with other switchable elements on the game board where one of the goals for completing a level is to interact with the game board in such a way that a predefined number of non matchable switchable elements are placed in any of a plurality of predefined areas on the game board such as being brought down from the top of the gameboard to the bottom.

A match 3 game in which the player has to satisfy multiple criteria within a limited number of moves to complete the level in which the criteria include at least two of the following 

A match 3 switcher game in which a player can purchase on line a booster to aid gameplay and that booster once available for use on the player s current platform can be used immediately and alternatively on any other platform used by the player and in which game state information for that player including information relating to use of the booster is synchronised using a remote server across each of several different devices used by that player.

A casual online game connected to a social network in which players can see their own and their social network friends game level position on a virtual path or other virtual world with nodes representing levels in the game and each node can reveal in response to user input a graphical preview representation of the gameboard for that level and if the player has played that level before a visual indication of how well the player succeeded on that level.

A match 3 switcher game in which after a player has failed to meet the level completion criteria a message is shown articulating why the level completion criteria was not met and offering as the only visually significant option to replay the level.

A match 3 switcher game in which after a player has achieved the level completion criteria a message is shown articulating that the level was successfully completed and offering as the only visually significant option to share information to a social network.

A match 3 switcher game in which when matching 3 or more of the same type of game element the matched game elements are removed from the game board and replaced with a game element from the same type of game elements that has a higher stage and when including the newly introduced game element in a new combination replacing it with another game element of a further higher stage when the introduced game element reach a certain stage it is removed and all game elements of the same type on the game board are upgraded one level.

NB Each of the above concepts can be combine with any and all of the other high level concepts. Also although the high level concepts are generally defined in relation to a match 3 switcher game the concepts can be deployed in other game variants e.g. clicker games .

A gaming system in which a single user database which may be distributed or centralised tracks all metrics for all players including all game state information irrespective of the platform used by each of those players and that single user database is accessible by several different games such as a match 3 switcher or clicker a bubble shooter etc.

A clicker game in which players can see their own and also their social network friends game level position on a virtual path or other virtual world and in which game state information is fully sync d across different platforms such as iOS desktop and Android via Facebook so that a player can seamlessly stop and re start playing the game on any of those different platforms.

A clicker game in which a player s score and game level position and also the scores and game level positions of all their social network friends also playing the game is fully sync d across different platforms such as iOS desktop and Android via Facebook.

A clicker game in which players can see their own and their social network friends game level position on a virtual path or other virtual world and in which each level of the game can be failed and if a level is failed the game automatically offers the player extra moves to purchase to carry on playing the game.

A clicker game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which in app purchases are bought for real or virtual currency by touching an icon of the booster shown next to the gameplay board and then touching a buy button that is subsequently displayed.

A clicker game in which a player s score and game level position and also the scores and game level positions of all their social network friends also playing the game is fully sync d across different platforms such as iOS desktop and Android via Facebook and there are sections of the game that must be unlocked through either help from those friends or through a purchase.

A clicker game connected to a player s friends through a social network in which friends can send gifts boosters extra moves or extra lives to one another.

A clicker game in which players can see their own and social network friends game level position on a virtual path or other virtual world and where a visual prompt is displayed by the game if a friend s high score has been beaten by that player the prompt enabling the player to send a message to that friend.

A clicker game in which players can see their own and also their social network friends game level position on a virtual path or other virtual world and where the player can play the game in offline mode on one platform device and the progress in the game and other game state information is synchronised with a remote server when the device is online again and the player can continue playing the game on another platform.

A clicker game in which players can see their own and their social network friends game level position on a virtual path or other virtual world and the game enables the player to buy a permanent booster which can be used without limit in time.

A clicker game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which successive levels have different difficulty rankings to introduce variety even without a new game mechanic being introduced e.g. after a difficult level there is an easier level.

A clicker game connected to a player s friends through a social network where some or all of those friends are sent a message prompting the friend s to assist the player once that player has played but not completed a level for more than a predefined time or predefined number of attempts.

A clicker game or other kind of social casual game in which players can see their own and their social network friends level position on a virtual path or other virtual world and where the player is prompted to notify a social network friend when the friend s high score on a specific level has been beaten by that player.

A clicker game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which the game state information is fully sync d across different platforms such as iOS desktop and Android via Facebook and in which the gameplay for each level can be enhanced through the use of an acquired item such as a booster.

A clicker game in which players can see their own and their social network friends game level position on a virtual path or other virtual world in which the game state information is fully sync d across different platforms such as iOS desktop and Android via Facebook and in which the gameplay for each level can be enhanced through the use of an acquired item such as a booster and where the game state information relating to the acquisition or use of an acquired item is synchronized across several different platforms.

A clicker game in which players can see their own and their social network friends game level position on a virtual path or other virtual world and in which the game board contains switchable elements that can be matched with other switchable elements and switchable elements that cannot be matched with other switchable elements on the game board where one of the goals for completing a level is to interact with the game board in such a way that a predefined number of non matchable switchable elements are placed in any of a plurality of predefined areas on the game board such as being brought down from the top of the gameboard to the bottom.

A clicker game in which the player has to satisfy multiple criteria within a limited number of moves to complete the level in which the criteria include at least two of the following 

A clicker game in which a player can purchase on line a booster to aid gameplay and that booster once available for use on the player s current platform can be used immediately and alternatively on any other platform used by the player and in which game state information for that player including information relating to use of the booster is synchronised using a remote server across each of several different devices used by that player.

A clicker game in which after a player has failed to meet the level completion criteria a message is shown articulating why the level completion criteria was not met and offering as the only visually significant option to replay the level.

A clicker game in which after a player has achieved the level completion criteria a message is shown articulating that the level was successfully completed and offering as the only visually significant option to share information to a social network.

A clicker game in which when removing a group of game elements of the same type of game element the matched game elements are removed from the game board and replaced with a game element from the same type of game elements that has a higher stage and when including the newly introduced game element in a new combination of removed game elements replacing it with another game element of a further higher stage when the introduced game element reach a certain stage it is removed from the game board and all other game elements of the same type on the game board are upgraded one level.

NB Each of the above concepts can be combine with any and all of the other high level concepts. Also although the high level concepts are generally defined in relation to a specific type of game match 3 switcher game the concepts can be deployed in other game variants e.g. clicker games match 3 switcher games bubble shooter games puzzle games .

Candies are shiny reflective brightly coloured candies but the background gameplay region is dark and matt so the candies readily stand out reducing cognitive load.

Some or all game levels are untimed eliminating any time pressure e.g. because a player can seamlessly stop and re start playing the game at any time since game state information is stored e.g. remotely and or on the playing device 

Some or all levels have a true fail which enables monetisation through purchasing extra moves true fails in casual games are rare because the assumption to the designer is that it will put people off playing the game allowing players to continue playing manipulates the fail condition to make it feel agreeable .

Game generates and displays congratulatory messages when the player scores more than a predefined amount or matches more than a predefined number of game elements in a single move

There is always an available match 3 switcher move readily seen by the average player that will score some points whilst higher scoring moves are randomly available.

Games are played using software downloaded to an end user device such as a smartphone tablet PC or laptop or running remotely on a server or a combination of the two the software running on one or more processors and the processor controls or is involved with all gameplay game interaction graphics displays communication interaction with social networks synchronization across platforms data storage game state information.

Games are played using a hardware gaming system comprising processors and data memories the system including multiple end user devices such as smartphones tablets and PCs as well as remotely connected servers the gaming system enabling the games defined above to be played on the multiple end user devices.

The game is defined using non transitory computer readable medium encoded with instructions for controlling a hardware gaming system to display and enable users to play the games defined above.

A match 3 game fully sync d across platforms having an algorithm for automatically detecting when there are no possible moves left.

A match 3 game fully sync d across platforms having an algorithm for re shuffling the elements on the game board.

A switcher based match 3 game fully sync d a cross platforms having sections which must be unlocked with the help of friends or through a purchase.

A switcher based match 3 game fully sync d across platforms with at least 3 5 different goals for completing different levels.

A switcher based match 3 game fully sync d across platforms having a limited amount of lives that can be replenished either by waiting or by purchasing new lives.

A match 3 switcher game that offers users to buy permanent boosters which can be accessed one or more times for each time playing a level or once a day.

A match 3 switcher game which is connected to the player s friends through a social network and where friends can send gifts to each other.

A match 3 switcher game which is connected to the player s friends through a social network and where friends can help each other by sending extra moves or extra lives.

A match 3 switcher game which is connected to the player s friends through a social network and where friends can help each other by sending various boosters and where the help sent can only be used on the level the player is stuck on.

A match 3 game that has a sign in the shape of a bow tie or ribbon next to those level nodes on the visual path where help from the player s friends.

A match 3 switcher game where the player s Facebook portrait moves along a virtual path when progressing through the game.

A match 3 game where there is a map showing the progress of the player and where the map looks like a foldable physical game board which has been place on top of a table.

A match 3 game where the player moves along a virtual path and where the path moves through different candy themed areas and where each area has its own sub story with an intro and an end when entering and exiting each area respectively.

The switch based match 3 game comprising a special game element which variable in its character can be automatically moved and combined with other game elements into a match combo or is locked in the blocker that is required to be unlocked first.

The switch based match 3 game comprising a special game element which variable in its character can remain as the same special game element after combinable moves are taken.

The switch based match 3 game comprising a special game element which variable in its character can transform into a random game element that can either yield a combo to remove the game elements or yield an obstacle to block the combo depending on the game elements it combined with.

The switch based match 3 game comprising a special game element which can transform into another special game element that when combined with other game elements yields a special combo effect to remove all the game elements in a row and or column or a bigger area more than a layer.

The switch based match 3 game comprising a special game element which can transform into another special game element that when combined with other game elements yields a special combo effect to remove game elements of the same colour.

The switch based match 3 game comprising a special game element which can transform into another special game element that is not playable or movable unless it is unlocked first.

The switch based match 3 game comprising a special game element which can transform into another special game element that consume other game elements so that they are not playable or movable.

The switch based match 3 game comprising special boosters which are purchasable before or during the game level.

The switch based match 3 game comprising special boosters which can smash and remove any game element.

The switch based match 3 game comprising special boosters which allow the game element to switch if no any combinable move on the game board is available.

The switch based match 3 game comprising special boosters which allow different special game elements to exist at the start of the game level.

The switch based match 3 game comprising special boosters which add five to the count of the time counting in game elements on the game board.

The switch based match 3 game comprising special boosters which rolls over an area on the game board by transforming into striped game element and creates three line blasts.

The switch based match 3 game comprising special boosters which following its path can chomp away any game elements and have them removed at several squares.

The switch based match 3 game comprising special boosters which more than one can be mixed or combined from a certain game level.

A match 3 switcher game in which players can see their social network friends level position on a virtual path and where the player can play the game in offline mode on one platform device and the progress in the game is synchronised with a central server when the device is online again and the player can continue playing the game on another platform.

A casual online game connected to a social network where social network friends are prompted to assist another player if that other player has played but not completed a level meeting a certain criteria the criteria can be any of the following

A casual online game connected to a social network where social network friends are prompted to assist another player if that other player has played but not completed a level meeting a certain criteria the help received can only be used by the player on that specific level.

Although these ideas are generally defined in relation to a match 3 switcher game the ideas can be deployed in other game variants e.g. clicker games etc .

If the player doesn t make a move for a pre set time then a possible match 3 combination of candies is shown with each candy briefly illuminated or otherwise highlighted.

If 4 candies are combined then a striped candy results combining that striped candy into a match 3 combination removes all candies in the stripe direction for the row or column of the striped candy

The direction of the stripes of a striped candy is perpendicular to the combination that created the striped candy

The column and line that are removed are determined by the crossing point the cell in which the combination is made

If 5 candies are combined in a line then a special candy results subsequently switching that special candy with an adjacent candy of a given colour then removes all candies on the board in that colour.

If the special game element that removes all game elements of one colour is combined with a striped candy then all candies of the striped candy s colour becomes triggered striped candies

If the special game element that removes all game elements of one colour is combined with another identical special game element then all game element son the game board are removed in a sweeping motion from left to right.

Some special game elements can be swapped normally which later transforms into a random game element that can be either a positive element or an obstacle.

Positive e.g. a striped game element a wrapped game element a colour bomb a fish a lucky candy which can transform into useful element when removed etc.

Negative e.g. a piece of chocolate which if left unchecked will spread a chocolate factory a piece of liquorice a piece of cream of random thickness etc.

Levels contain non combinable game elements that shall be moved to the last row on the screen where they disappear in order to complete the game.

All non combinable game elements to be moved are not on the game board at the start and will be introduced during the gameplay when other game elements are removed

Remove a certain number of some or all of the available types of matchable game elements on the game board to complete the level.

The sequence of game elements is re arranged instead of level failed with the current elements on the board when no combinable moves are available during the level.

A part of the game board that moves a game element that passes through it to a different part on the game board

The virtual path is set on a candy themed fantasy map which has the appearance of a physical game board that is foldable and placed on top of a table.

Moving along the virtual path transports the player through different themed landscapes areas and when entering a new landscape a sub story begins which then ends when that landscape has been progressed through.

On the virtual path there are level nodes representing each level. The level nodes have a specific look depending on what type of goal the level they represent has.

3. Seek friends help is possible through social network Facebook. Players may send requests for more lives by clicking the icon on the screen which will launch a Facebook pop up that allows the player to select friends individually.

4. A special method of adding game life is to purchase the Charm of Life from which the player may increase number of maximum lives from five to eight. The change of default life time can be permanent through a full refill Charm of life.

Players can see their social network friends scores for the same level they are currently playing on the star meter together with their friends portrait

The player is prompted to post a message on the wall of a friend that is passed in the high score list

The player is presented with the option o texted the play on the level more moves or time to beat one of the friends in that level.

There is a booster that gives additional time for the player to complete a timed level Coconut Wheel a booster that rolls over an area on the game board by transforming into striped game element and creates 3 line blasts

A booster that inserts special elements jelly fishes on the game board which clears three pieces of jelly when matched

Stripe wrap booster A booster that gives a striped game element and a wrapped game element at the beginning of the game.

Shuffle Candy A booster that allows to shuffle the game element on the board if no any good move is available.

Boosters can be permanent and available to the player for all levels or they can be non permanent and need to be topped up through purchases or help from friends

In app purchases are bought by touching an icon of the booster shown next to the gameplay board and then touching a buy button that is subsequently displayed

Social network friends are prompted to help out if the player has been stuck on a level for a specified time without completing the level.

Social network friends are prompted to help out if the player has played a level a certain number of times without completing the level.

Social network friends are prompted to help if the player has run out of game life and wish to continue the game.

The help that can be sent to a stuck friend can be extra moves to be used for free in that specific level

That the player has received from a friend is indicated on the overview map in relation to the level where the help can be used

In one implementations if the player has completed the level using the help from a specific friend a thank you message is sent to the helping friend.

A player that is stuck can buy himself past that level with help from friends receiving help unlocking from a plurality of friends gets the player past the level.

Successive levels can have different difficulty rankings e.g. after a tough level there is an easy level.

Goal for successive levels may change e.g. one level may require the player to clear all the jellies and the next may require the player to bring down all the special non candy foods. Or successive levels may require jellies to be cleared but have very different shapes of the gameboard and blockers.

A goal may be to collect by making combos a certain amount of candies special candies or specific combos in order to complete a level.

