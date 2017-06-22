---

title: Information processing device, information processing method, and program
abstract: In the event that there is a call-up for an API (Application Programming Interface) ensuring the drawing integrity of drawing graphics images as to a graphics plane, which is a storage region in which storage regions for two images of an L region that is a storage region for one image to store an image for the left eye, and a R region that is a storage region for one image to store an image for the right eye, are collaterally arranged, images drawn on the graphics plane are output for display. The present invention may be applied to a BD player for playing BDs, and the like.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09225956&OS=09225956&RS=09225956
owner: Sony Corporation
number: 09225956
owner_city: Tokyo
owner_country: JP
publication_date: 20130927
---
This document is a Divisional application of and is based upon and claims the benefit of priority under 35 U.S.C. 120 from U.S. Ser. No. 12 993 386 filed Nov. 18 2010 herein incorporated by reference which is a National Stage application of International Application No. PCT JP2010 055135 filed Mar. 24 2010. This application is based upon and claims the benefit of priority from prior Japanese Patent Applications No. 2009 091163 filed Apr. 3 2009 and 2010 046028 filed Mar. 3 2010.

The present invention related to an information processing device an information processing method and a program and specifically relates to for example an information processing device an information processing method and a program whereby the content of a 3D Dimension image can suitably be played from a recording medium.

For example 2 dimensional 2D image contents are the mainstream for contents such as movies but lately the 3 dimensional 3D image graphics contents realizing stereoscopic viewing have attracted attention.

There are various types of methods for 3D image hereafter also referred to as stereo image display methods but regardless of the method employed the data amount of a 3D image is greater than the data amount of a 2D image.

Also the contents of high resolution images such as movies may have a great size and in order to record such a large volume image content as a 3D image having great data amount a large capacity recording medium is necessary.

Examples of such a large capacity recording medium include Blu Ray R Discs hereafter also referred to as BD such as BD Blu Ray R ROM Read Only Memory and so forth.

With BD BD J BD Java registered trademark can be handled and according to BD J a high interactive function can be provided PTL 1 .

Incidentally with the current BD standard how to record and how to play a 3D image content has not yet been stipulated.

However relegating how to record or play a 3D image content to an author who performs authoring of 3D image contents may result in 3D image contents not being suitably played.

The present invention has been made in light of the above described situation and is to enable a 3D image content to be suitably played from a recording medium such as BD or the like.

An information processing device or program according to a first aspect of the present invention is an information processing device or a program causing a computer to function as an information processing device wherein a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and wherein by taking a drawing command sequence for drawing the image for the left eye and the image for the right eye of the graphics as to the graphics plane in a matched manner as an argument in the event that there is a call up for an API Application Programming Interface ensuring the drawing integrity of drawing the image for the left eye and the image for the right eye of the graphics in a matched manner the drawing command sequence is executed thereby performing drawing of the graphics images to the graphics plane and after completion of the drawing the images drawn on the graphics plane are output for display.

An information processing method according to the first aspect of the present invention is an information processing method wherein a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and wherein by taking a drawing command sequence for drawing the image for the left eye and the image for the right eye of the graphics as to the graphics plane in a matched manner as an argument in the event that there is a call up for an API Application Programming Interface ensuring the drawing integrity of drawing the image for the left eye and the image for the right eye of the graphics in a matched manner the drawing command sequence is executed thereby performing drawing of the graphics images to the graphics plane and after completion of the drawing the images drawn on the graphics plane are output for display.

According to the first aspect of the present invention a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and by taking a drawing command sequence for drawing the image for the left eye and the image for the right eye of the graphics as to the graphics plane in a matched manner as an argument in the event that there is a call up for an API Application Programming Interface ensuring the drawing integrity of drawing the image for the left eye and the image for the right eye of the graphics in a matched manner the drawing command sequence is executed thereby performing drawing of the graphics images to the graphics plane and after completion of the drawing the images drawn on the graphics plane are output for display.

An information processing device or program according to a second aspect of the present invention is an information processing device or a program causing a computer to function as an information processing device wherein a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and wherein in the event that there is a call up for a drawing completion notification API Application Programming Interface notifying that drawing of images to the graphics plane has ended the images drawn on the graphics plane are output for display.

An information processing method according to the second aspect of the present invention is an information processing method wherein a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and wherein in the event that there is a call up for a drawing completion notification API Application Programming Interface notifying that drawing of images to the graphics plane has ended the images drawn on the graphics plane are output for display.

According to the second aspect of the present invention a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and in the event that there is a call up for a drawing completion notification API Application Programming Interface notifying that drawing of images to the graphics plane has ended the images drawn on the graphics plane are output for display.

An information processing device or program according to a third aspect of the present invention is an information processing device or a program causing a computer to function as an information processing device wherein a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and wherein in the event that there is a call up for a drawing start notification API Application Programming Interface notifying that drawing of images to the graphics plane will start following which there is a call up for a drawing completion notification API notifying that drawing of images to the graphics plane has ended all images drawn on the graphics plane after the call up for the drawing start notification API up to the call up for the drawing completion notification API are output for display.

An information processing method according to the third aspect of the present invention is an information processing method wherein a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and wherein in the event that there is a call up for a drawing start notification API Application Programming Interface notifying that drawing of images to the graphics plane will start following which there is a call up for a drawing completion notification API notifying that drawing of images to the graphics plane has ended all images drawn on the graphics plane after the call up for the drawing start notification API up to the call up for the drawing completion notification API are output for display.

Accordion to the third aspect of the present invention a graphics plane to store a graphics image is a storage region where storage regions for two images of an L region that is a storage region for one image to store an image for the left eye and a R region that is a storage region for one image to store an image for the right eye are collaterally arranged and in the event that there is a call up for a drawing start notification API Application Programming Interface notifying that drawing of images to the graphics plane will start following which there is a call up for a drawing completion notification API notifying that drawing of images to the graphics plane has ended all images drawn on the graphics plane after the call up for the drawing start notification API up to the call up for the drawing completion notification API are output for display.

The information processing device may be a stand alone device or may be an internal block making up a device.

Also the program may be provided by being transmitted via a transmission medium or by being recorded in a recording medium.

Description will be made below regarding a case where an embodiment of the present invention has been applied to BD.

First with regard to the current BD description will be made regarding a management structure hereafter also referred to as BDMV format content such as a content recorded in BD ROM which is read only BD i.e. AV Audio Video data or the like stipulated in Blu ray Disc Read Only Format Ver1.0 part3 Audio Visual Specifications .

For example bit streams encoded by an encoding method such as an MPEG Moving Picture Experts Group video MPEG audio or the like and multiplexed in accordance with MPEG2 are referred to as clip AV streams or AV streams . Clip AV streams are recorded in BD as a file by a file system defined with Blu ray Disc Read Only Format part2 that is one of standards regarding BD. The file of clip AV streams is referred to as a clip AV stream file or AV stream file .

Clip AV stream files are managing units on a file system and information necessary for playback of clip AV streams of a clip AV stream file and the like are recorded in BD as a database. This database is stipulated in Blu ray Disc Read Only Format part3 that is one of the BD standards.

The lowermost layer is a layer to which clip AV streams belong and hereafter will also be referred to as a clip layer as appropriate.

The layer one above layer of the clip layer is a layer to which playlists Movie PlayLists for specifying playback positions as to clip AV streams belong and hereafter will also be referred to as a playlist layer.

The layer one above the playlist layer is a layer to which movie objects Movie Objects made up of a command for specifying playback order as to a playlist and the like belong and hereafter will also be referred to as an object layer.

The layer uppermost layer one above the object layer is a layer to which an index table for managing titles and the like to be stored in BD belongs and hereafter will also be referred to as an index layer.

Description will be further made regarding the clip layer playlist layer object layer and index layer.

Clip AV streams are streams wherein video data audio data which serve as the data of a content or the like is converted into a TS MPEG TS Transport Stream format.

Clip information Clip Information is information relating to clip AV streams and is recorded in BD as a file.

The stream of graphics of a caption is referred to as a presentation graphics PG Presentation Graphics stream and the stream of graphics of a menu is referred to as an interactive graphics IG Interactive Graphics stream.

Also a set of a clip AV stream file and the file clip information file of corresponding clip information clip information relating to the clip AV streams of the clip AV stream file thereof is referred to as a clip Clip .

Multiple positions including the first and last positions point in time when laying out a content corresponding to clip AV streams making up a clip on a temporal axis are set as access points. Access points are specified principally with a timestamp by a playlist PlayList on the upper layer.

Clip information making up a clip includes the address logical address of the position of a clip AV stream represented with the access point that a playlist specified using a timestamp.

Playlists are configured of an AV stream file to be played and a play item PlayItem including a playback start point IN point and a playback end point OUT point for specifying a playback position of the AV stream file thereof.

Now playback of a play item means playback of a section of a clip AV stream specified with the IN point and the OUT point included in the play item thereof.

Movie objects Movie Objects and BD J objects Blu ray Disc Java registered trademark objects belong to the object layer.

A movie object includes terminal information that correlates a HDMV High Definition Movie navigation command program navigation command with the movie object thereof.

Navigation commands are commands for controlling playback of playlists. Terminal information includes information for allowing a user s interactive operation as to a BD player for playing BD. With the BD player user operation such as call up for a menu title search or the like is controlled based on terminal information.

BD J objects are Java registered trademark programs and can provide a more advanced sophisticated interactive function than navigation commands.

Entries fields of the index table correspond to titles and a link is provided from each entry to the object movie object or BD J object of the title HDMV title or BD J title corresponding to the entry.

Now in files including directories under a directory mean files immediately under the directory thereof and files included in a directory mean files immediately under the directory thereof and also files under a so called subdirectory of the directory thereof.

Two files index.bdmv and MovieObject.bdmv are stored immediately under the directory BDMV . Note that files other than index.bdmv and MovieObject.bdmv excluding directories cannot be stored immediately under the directory BDMV .

The file index.bdmv includes the index table described in serving as information relating to a menu for playing BD.

For example the BD player plays all of the contents of BD plays a particular chapter alone repeatedly performs playback or plays the screen of an initial menu including content items such as displaying a predetermined menu or the like based on the file index.bdmv .

Also a movie object Movie Object to be executed at the time of each item being selected can be set to the file index.bdmv and in the case that one item is selected from the initial menu screen by the user the BD player executes a Movie Object command set to the file index.bdmv .

The file MovieObject.bdmv is a file including the information of a Movie Object. Movie Objects include a command for controlling playback of a PlayList recorded in BD and for example the BD player plays a content title recorded in the BD by selecting one of the Movie Objects recorded in the BD and executing this.

Directories PLAYLIST CLIPINF STREAM AUXDATA META BDJO JAR and BACKUP are provided immediately under the directory BDMV .

A database of playlists is stored in the directory PLAYLIST . Specifically playlist files xxxxx.mpls are stored in the directory PLAYLIST . A file name made up of a 5 digit numeral xxxxx and an extension mpls is used as the file names of playlist files xxxxx.mpls .

A database of clips is stored in the directory CLIPINF . Specifically a clip information file xxxxx.clpi as to each of the clip AV stream files is stored in the directory CLIPINF . A file name made up of a 5 digit numeral xxxxx and an extension clpi is used as the file names of clip information files xxxxx.clpi .

Clip AV stream files xxxxx.m2ts are stored in the directory STREAM . TSs Transport Streams are stored in clip AV stream files xxxxx.m2ts . A file name made up of a 5 digit numeral xxxxx and an extension m2ts is used as the file names of clip AV stream files xxxxx.m2ts .

Note that a matched file name excluding its extension is used as the file names of a clip information file xxxxx.clpi and a clip AV stream file xxxxx.m2ts making up a given clip. Thus a clip information file xxxxx.clpi and a clip AV stream file xxxxx.m2ts making up a given clip can be readily specified.

A sound file a font file a font index file a bitmap file and the like are stored in the directory AUXDATA .

Predetermined sound data audio data is stored in the file sound.bdmv . This sound.bdmv is fixedly used as the file name of the file sound.bdmv .

Font data used for display of a caption a BD J object application or the like is stored in the files having the extension otf . A 5 digit numeral is used as the portion other than the extension of the file names of the files having the extension otf .

Metadata files are stored in the directory META . BD J object files are stored in the directories BDJO and JAR . The backup of a file recorded in BD is stored in the directory BACKUP .

The BD player in is configured so as to perform playback of BD in which a 3D image content is recorded.

A processor computer such as a CPU Central Processing Unit or the like is embedded in the BD player. An input output interface is connected to the CPU via a bus .

Upon a command being input by an input unit being operated or the like by the user via the input output interface the CPU executes a program stored in ROM Read Only Memory in accordance therewith. Alternatively the CPU loads a program recorded in a hard disk or disc mounted on a drive to RAM Random Access Memory and executes this.

Thus the CPU performs later described various types of processing. Subsequently for example the CPU outputs the processing results thereof from an output unit via the input output interface or transmits from a communication unit or further records in a hard disk or the like as necessary.

Note that the input unit is configured of a keyboard mouse microphone or the like. Also the output unit is configured of an LCD Liquid Crystal Display speaker or the like. The communication unit is configured of a network card or the like.

Now a program that the CPU executes may be recorded beforehand in the hard disk or ROM serving as a recording medium embedded in the BD player.

Alternatively the program may be stored recorded in a removable recording medium such as disc or the like. Such a removable recording medium may be provided as so called packaged software. Here examples of a removable recording medium include a flexible disk CD ROM Compact Disc Read Only Memory MO Magneto Optical disk DVD Digital Versatile Disc magnetic disk and semiconductor memory.

Note that in addition to installing the program from such a removable recording medium into the BD player the program may be downloaded to the BD player via a communication network or broadcast network so as to be installed into the built in hard disk . Specifically for example the program may be transferred wirelessly from a download site to the BD player via an artificial satellite for digital satellite broadcasting or may be transferred by cable to the BD player via a network such as a LAN Local Area Network the Internet or the like.

In the disc is for example BD where a 3D image content is recorded in a manner maintaining compatibility with BD to be played at a legacy player.

Accordingly the disc may be played at the legacy player and also may be played at the BD player in which is a BD player capable of playing a 3D image content hereafter also referred to as 3D compatible player .

Now the legacy player is a BD player which can play BD in which a 2D image content is recorded but is incapable of playing a 3D image content.

With the legacy player a 2D image content can be played from the disc but a 3D image content cannot be played.

On the other hand with the BD player in which is a 3D compatible player not only a 2D image content but also a 3D image content can be played from the disc .

With the BD player in upon the disc which is a BD disc being mounted on the drive the CPU performs playback of the disc by controlling the drive .

With the BD player in which is a 3D compatible player the CPU executes a Java registered trademark virtual machine and on the Java registered trademark virtual machine a BD J application is executed.

The 3D compatible player draws 3D images on a logical plane a PG plane or a video plane . Note that the entities of the logical plane PG plane and video plane are for example a partial storage region in the RAM in .

3D images that the 3D compatible player draws include BD J graphics stipulated with the BD standard PG Presentation Graphics TextST Text subtitle video and background.

Now in a graphics 3D image stereo graphics source is configured of an image for the left eye L Left view which is an image to be observed by the left eye and an image for the right eye R Right view which is an image to be observed by the right eye.

A PG 3D image stereo PG source a video 3D image stereo video source and a background 3D image stereo background source are also configured of the image for the left eye and the image for the right eye.

Note that the image for the left eye and the image for the right eye making up a video 3D image and the like may be encoded with H.264 AVC Advanced Video Coding MVC Multi view Video coding or the like for example.

Now with H.264 AVC MVC image streams called base view Base View and image streams called dependent view Dependent View are defined.

Predictive coding with another stream as a reference image is not allowed for base view but predictive coding with base view as a reference image is allowed for dependent view. Of the image for the left eye and the image for the right eye for example the image for the left eye may be taken as base view and the image for the right eye may be taken as dependent view.

The 3D compatible player draws a 3D image drawn on the logical plane on the graphics plane or background plane .

The graphics plane is configured of an L graphics plane L Left graphics plane L for storing the image for the left eye and an R graphics plane R Right graphics plane R for storing the image for the right eye.

The image for the left eye making up the graphics 3D image drawn on the logical plane is drawn on the L graphics plane L and the image for the right eye is drawn on the R graphics plane R.

Here the L graphics plane L is one image worth of image storage region L region for storing an image for L Left image for the left eye to be observed by the left eye. Also the R graphics plane R is one image worth of image storage region R region for storing an image for R Right image for the right eye to be observed by the right eye.

The entities of the L graphics plane L and the R graphics plane R i.e. the entity of the graphics plane is a partial storage region in the RAM in separate from the logical plane .

The PG plane is configured of an L PG plane L Left PG plane L for storing the image for the left eye and a R PG plane R Right PG plane R for storing the image for the right eye.

The 3D compatible player draws the image for the left eye making up a PG 3D image on the L PG plane L and draws the image for the right eye on the R PG plane R.

The video plane is configured of an L video plane L Left video plane L for storing the image for the left eye and an R video plane R Right video plane R for storing the image for the right eye.

The 3D compatible player draws the image for the left eye making up a video 3D image on the L video plane L and draws the image for the right eye on the R video plane R.

The background plane is configured of an L background plane L Left background plane L for storing the image for the left eye and an R background plane R Right background plane R for storing the image for the right eye.

The image for the left eye making up the background 3D image drawn on the logical plane is drawn on the L background plane L and the image for the right eye is drawn on the R background plane R.

The image for the left eye and the image for the right eye drawn recorded on the graphics plane PG plane video plane and background plane are supplied to a mixer .

The mixer blends synthesizes the graphics image for the left eye from the graphics plane the PG image for the left eye from the PG plane the video image for the left eye from the video plane and the background image for the left eye from the background plane to output the image for the left eye that are the synthesized result thereof.

Also the mixer blends synthesizes the graphics image for the right eye from the graphics plane the PG image for the right eye from the PG plane the video image for the right eye from the video plane and the background image for the right eye from the background plane to output the image for the right eye that are the synthesized result thereof.

The image for the left eye that the mixer outputs is supplied to a display not illustrated in the drawing as display output for left L Left display output . Also the image for the right eye that the mixer outputs is supplied to the display not illustrated in the drawing as display output for right R Right display output .

With the display not illustrated in the drawing a 3D image is displayed by the image for the left eye and the image for the right eye from the mixer being alternately or simultaneously displayed.

BD J applications can perform drawing of images on the graphics plane and the background plane of the graphics plane PG plane video plane and background plane .

Now with the present embodiment let us say that BD J applications can only access the logical plane alone and cannot directly access the graphics plane and the background plane .

Accordingly BD J applications can perform drawing of images as to the logical plane alone but cannot directly do so as to the graphics plane and the background plane . Therefore BD J applications indirectly draw images on the graphics plane or background plane by drawing an image on the logical plane .

However hereafter for convenience of description drawing of images as to the graphics plane or background plane via the logical plane by a BD J application will simply be described as drawing of an image as to the graphics plane or background plane .

Note that the 3D compatible player may be configured so as not to include the logical plane . In this case BD J applications directly draw images on the graphics plane or background plane .

In addition to drawing of images on the graphic plane and the background plane BD J applications can perform playback control of video and PG such as control of scaling or positions display positions of video and PG and the like.

Note that BD J applications handle video and PG as a set collectively . In other words BD J applications cannot distinguish cannot distinguish between video and PG.

With the first drawing method the author of a BD J application performs drawing as to a stereo plane.

Specifically with the first drawing method the data of a graphics 3D image is configured of the data of an image for the left eye and the data of an image for the right eye and the BD J application draws the image for the left eye and the image for the right eye on the logical plane .

Subsequently the image for the left eye and the image for the right eye drawn on the logical plane are drawn on the graphics plane without change. Specifically the image for the left eye drawn on the logical plane is drawn on the L graphics plane L without change and the image for the right eye drawn on the logical plane is drawn on the R graphics plane R without change.

With the second drawing method the author of a BD J application performs drawing as to a mono plane. Also the author supplies an offset value graphics plane offset value simultaneously. The 3D compatible player generates a stereo plane from the mono plane.

That is to say with the second drawing method the data of a 3D image is configured of the data of the original image serving as a so called source for generating a 3D image and the data of disparity for generating an image for the left eye and an image for the right eye from the original image by applying disparity to the original image.

The BD J application draws the original image on the logical plane . The 3D compatible player draws the image for the left eye and the image for the right eye generated by applying disparity to the original image drawn on the logical plane on the L graphics plane L and the R graphics plane R respectively.

Now if we say that the data of disparity is an offset value offset the number of pixels to be shifted in the horizontal direction x direction from the position of the original image may be employed as this offset value.

With the L graphics plane L the original image drawn on the logical plane is drawn on a position shifted in the horizontal direction by the offset value with the right direction from the left as a positive direction. That is to say an image obtained as a result of shifting the position in the horizontal direction of the original image drawn on the logical plane by the offset value is drawn on the L graphics plane L as an image for the left eye.

With the R graphics plane R the original image drawn on the logical plane is drawn on a position shifted in the horizontal direction by the offset value with the left direction from the right as a positive direction. That is to say an image obtained as a result of shifting the position in the horizontal direction of the original image drawn on the logical plane by the offset value is drawn on the R graphics plane R as an image for the right eye.

Note that the original image drawn on the logical plane is horizontally shifted and drawn on the L graphics plane L and accordingly a region pixels where drawing is not performed occurs within a region to be drawn a region where drawing is performed in the case of the position in the horizontal direction being not shifted . The region where drawing of the original image is not performed of the L graphics plane L is drawn with a transparent color. This is also the same regarding the R graphics plane R.

Now in the case that the offset value is positive a 3D image displayed with the image for the left eye and the image for the right eye appears to float up toward the near side in the depth direction perpendicular to the display screen not illustrated . On the other hand in the case that the offset value is negative a 3D image displayed with the image for the left eye and the image for the right eye appears to be concaved toward the depth side in the depth direction.

Let us specify that with a Reference Decoder Model the 3D compatible player constantly includes two planes L graphics plane L and R graphics plane R and BD J applications perform drawing as to the logical plane .

Ultimately the image for the left eye of a graphics drawn on the L graphics plane L L graphics plane is blended with the image for the left eye of a video and PG drawn on the L video plane L L video plane . Also the image for the right eye of a graphics drawn on the R graphics plane R R graphics plane is blended with the image for the right eye of a video and PG drawn on the R video plane R R video plane .

A in illustrates a mono logical plane offset value mode that is one mode Mode 1 of the graphics mode hereafter also referred to as offset graphics mode .

With the offset graphics mode BD J applications draw a mono image that is a graphics 2D image on the logical plane . Also BD J applications give the 3D compatible player an offset value.

The 3D compatible player generates a stereo image that is a graphics 3D image from a mono image drawn on the logical plane and the offset value given from a BD J application. Further the BD player draws stores an image for the left eye making up the stereo image on the L graphics plane L L region and also draws stores an image for the right eye making up the stereo image thereof on the R graphics plane R R region .

Subsequently the mixer blends the graphics image for the left eye drawn stored on the L graphics plane L with the video and PG image for the left eye drawn on the L video plane L and outputs the blended result. Further the mixer blends the graphics image for the right eye drawn stored on the R graphics plane R with the video image for the right eye drawn on the R video plane R and outputs the blended result.

B in illustrates a stereo logical plane mode that is one mode Mode 2 of the graphics mode hereafter also referred to as stereo graphics mode .

With the stereo graphics mode BD J applications draw an image for the left eye and an image for the right eye which make up a stereo image that is a graphics 3D image on the logical plane .

The 3D compatible player draws the image for the left eye drawn on the logical plane on the L graphics plane L and also draws the image for the right eye drawn on the logical plane on the R graphics plane R.

Subsequently the mixer blends the graphics image for the left eye drawn on the L graphics plane L with the video image for the left eye drawn on the L video plane L and outputs the blended result. Further the mixer blends the graphics image for the right eye drawn on the R graphics plane R with the video image for the right eye drawn on the R video plane R and outputs the blended result.

C in illustrates a forced mono logical plane mode that is one mode Mode 3 of the graphics mode hereafter also referred to as forced mono graphics mode .

With the forced mono graphics mode BD J applications draw a stereo image that is a graphics 3D image on the logical plane .

The 3D compatible player draws of the stereo image drawn on the logical plane one of the L graphics image and R graphics image for example the L graphics image alone on the one of the L graphics plane L and the R graphics plane R for example the L graphics plane L alone.

Subsequently the mixer blends the graphics mono image drawn on the L graphics plane L with the video image drawn on the L video plane L and outputs.

D in illustrates a flattened stereo logical plane mode that is one mode Mode 4 of the graphics mode hereafter also referred to as flattened stereo graphics mode . With the flattened stereo graphics mode BD J applications draw an image for the left eye and an image for the right eye which make up a stereo image that is a graphics 3D image on the logical plane .

The 3D compatible player draws one of the left eye image and the right eye image drawn on the logical plane for example the left eye image alone on both of the L graphics plane L and the R graphics plane R and discards the other right eye image.

The left eye image of the graphics drawn on the L graphics plane L is supplied to the mixer and the left eye image of the graphics drawn on the R graphics plane R is supplied as a right eye image to the mixer as well.

E in illustrates a mono logical plane mode that is one mode Mode 5 of the graphics mode hereafter also referred to as mono graphics mode .

With the mono graphics mode BD J applications draw a mono image that is a graphics 2D image on the logical plane .

The 3D compatible player draws the mono image drawn on the logical plane on one of the L graphics plane L and the R graphics plane R e.g. the L graphics plane L alone.

Subsequently the mixer blends the graphics mono image drawn on the L graphics plane L with the video image drawn on the L video plane L and outputs.

With the 3D compatible player the offset value may be applied to the graphics plane and the PG plane .

Here an offset value data to provide disparity to a graphics image to be applied to the graphics plane will also be referred to as a graphics plane offset Graphics plane offset value. Also an offset value data to provide disparity to a PG image to be applied to the PG plane will also be referred to as a PG plane offset PG plane offset value.

With regard to setting obtaining of the graphics plane offset value offset value read write dedicated API such as the following is defined and accordingly setting obtaining of the graphics plane offset value can be performed by the dedicated API thereof.

Note that the setOffset method is a method for storing setting the graphics plane offset value in an internal storage region which is a storage region proceeded within the BD player and getOffset is a method for obtaining the graphics plane offset value stored in the internal storage region of the BD player.

Also the BD player has a PSR Player Setting Register for storing information relating to playback of BD and the graphics plane offset value and the PG plane offset value are reserved for legacy player of the PSR e.g. may be stored in PSR 21.

Here the entity of the internal storage region and the PSR is a partial storage region of the RAM or hard disk in .

Incidentally with the current BD standard BD ROM standard writing in the PSR of the BD player from BD J applications is prohibited.

Allowing the BD player in which is a 3D compatible player to perform writing in the PSR from BD J applications would necessitate the current BD standard to be revised on a large scale.

Accordingly with the 3D compatible player writing in the PSR is indirectly enabled by defining the offset value as General Preference.

Specifically the 3D compatible player includes General Preference API Application Programming Interface for reading writing of the offset value as to PSR 21 for storing information relating to playback of BD which is data for providing disparity to a graphics or PG image conforming to the BD standard as one of General Preference conforming to the BD standard.

Here PSR 21 is mapped to General Preference of BD standard part3 2 Annex L of which the value may be set or obtained by org.dvb.user.GeneralPreference API.

The General Preference name for accessing the PSR by the General Preference API can be defined as follows.

Specifically the General Preference name of the graphics plane offset value can be defined for example as graphics offset . Also the General Preference name of the PG plane offset value can be defined for example as subtitle offset .

Now let us say that the default values of the graphics offset General Preference and the subtitle offset General Preference are both 0 for example.

Also with regard to setting obtaining of the graphics plane offset value dedicated API such as the following is defined and accordingly setting obtaining of the graphics plane offset value may be performed by the dedicated API thereof.

Note that the setOffset method is a method for storing a graphics plane offset value in an internal storage region within the BD player in this case PSR for example and getOffset is a method for obtaining the graphics plane offset value stored in the internal storage region within the BD player.

That is to say A in is a block diagram illustrating a functional configuration example of the BD player in as a 3D compatible player having a dedicated API for reading writing offset values whereby reading writing of offset values of graphics and PG conforming to the BD standard is performed as to the internal storage region of the 3D compatible player.

With the 3D compatible player in A in a BD J application requests the offset value read write dedicated API General Preference API for reading writing setting or obtaining of the offset value.

In response to the request from the BD J application the offset value read write dedicated API either sets an offset value graphics plane offset value PG plane offset value in the internal storage region of the 3D compatible player or obtains an offset value from the internal storage region of the 3D compatible player and returns it to the BD J application.

Note that in A in playback control engine Playback Control Engine performs control for generating playing an image for the left eye and an image for the right eye from an image original image that the BD J application has drawn on the logical plane in accordance with the offset value set within the internal storage region of the 3D compatible player.

As described above an offset value read write dedicated API is defined and the offset value read write dedicated API performs reading writing of BD standard graphics and offset values providing PG images with disparity to the internal storage region of the 3D compatible player in accordance with requests from the BD J application thereby enabling offset values providing images with disparity to be indirectly set and obtained from the BD J application.

B in is a block diagram illustrating a functional configuration example of the BD player in serving as a 3D compatible player including the General Preference API for performing reading writing of an offset value as to PSR 21 with the offset value of graphics and PG conforming to the BD standard as one of General Preferences conforming to the BD standard.

With the 3D compatible player in B in a BD J application requests the General Preference API of reading writing setting or obtaining of the offset value.

Specifically in the case that the offset value to be read written is the graphics plane offset value the BD J application calls up the General Preference API with the General Preference name as graphics offset .

Also in the case that the offset value to be read written is the PG plane offset value the BD J application calls up the General Preference API with the General Preference name as subtitle offset .

In response to the request from the BD J application the General Preference API sets the offset value to PSR 21 of the PSR Player Setting Register or obtains the offset value from PSR 21 to return this to the BD J application.

Note that in B in playback control engine Playback Control Engine performs control for generating playing an image for the left eye and an image for the right eye from an image original image that the BD J application drew on the logical plane .

As described above the General Preference API performs reading writing of the offset value as to PSR 21 storing information relating to playback of BD with the offset value that is data giving disparity to graphics and PG images conforming to the BD standard as one of General References conforming to the BD standard according to a request from the BD J application whereby the offset value giving disparity to an image can indirectly be set or obtained from the BD J application.

A in illustrates a mono video mode hereafter also referred to as mono video mode that is one mode Mode 1 of the video mode.

With the mono video mode the 3D compatible player draws stores a mono image that is a video 2D image on for example only the L video plane L which is one of the L video plane L L region and R video plane R R region .

Subsequently the video mono image drawn stored on the L video plane L alone is supplied to the mixer .

B in illustrates a dual mono video mode hereafter also referred to as dual mono video mode that is one mode Mode 2 of the video mode.

With the dual mono video mode the 3D compatible player draws stores a mono image that is a video 2D image on the L video plane L L region as an image for the left eye and also draws stores the mono image thereof on the R video plane R R region as an image for the right eye .

Subsequently both of the video mono image drawn stored on the L video plane L and the video mono image drawn stored on the R video plane R are supplied to the mixer .

C in illustrates a stereo video mode hereafter also referred to as stereo video mode that is one mode Mode 3 of the video mode.

With the stereo video mode the 3D compatible player draws an image for the left eye making up a stereo image that is a video 3D image on the L video plane L and also draws an image for the right eye making up the stereo image thereof on the R video plane R.

Subsequently the video image for the left eye drawn stored on the L video plane L and the video image for the right eye drawn on the R video plane R are both supplied to the mixer .

D in illustrates a flattened stereo video mode hereafter also referred to as flattened stereo video mode that is one mode Mode 4 of the video mode.

With the flattened stereo video mode the 3D compatible player draws one of an image for the left eye and an image for the right eye making up a stereo image that is a video 3D image e.g. the image for the left eye alone on both of the L video plane L and the R video plane R and discards the other image for the right eye.

Subsequently the video image for the left eye drawn stored on the L video plane L is supplied to the mixer and also the video image for the left eye drawn on the R video plane R is supplied to the mixer as the image for the right eye .

E in illustrates a forced mono video mode hereafter also referred to as forced mono video mode that is one mode Mode 5 of the video mode.

With the forced mono video mode the 3D compatible player draws one of an image for the left eye and an image for the right eye making up a stereo image that is a video 3D image e.g. the image for the left eye alone on for example only the L video plane L which is one of the L video plane L L region and R video plane R R region and discards the other image for the right eye.

Subsequently just the video image for the left eye drawn stored on the L video plane L is supplied to the mixer .

A in illustrates a dual mono background mode hereafter also referred to as dual mono background mode that is one mode Mode 1 of the background mode.

With the dual mono background mode the BD J application draws a mono image that is a background 2D image on the logical plane as an image for the left eye and an image for the right eye.

Subsequently the 3D compatible player draws stores the image for the left eye drawn on the logical plane on the L background plane L L region and also draws stores the image for the right eye drawn on the logical plane on the R background plane R R region .

Both of the background image for the left eye drawn stored on the L background plane L and the background image for the right eye drawn stored on the R background plane R are supplied to the mixer .

B in illustrates a stereo background mode hereafter also referred to as stereo background mode that is one mode Mode 2 of the background mode.

With the stereo background mode the BD J application draws an image for the left eye and an image for the right eye which make up a stereo image that is a background 3D image on the logical plane .

Subsequently the 3D compatible player draws the image for the left eye drawn on the logical plane on the L background plane L and also draws the image for the right eye drawn on the logical plane on the R background plane R.

Both of the background image for the left eye drawn on the L background plane L and the background image for the right eye drawn on the R background plane R are supplied to the mixer .

C in illustrates a flattened stereo background mode hereafter also referred to as flattened stereo background mode that is one mode Mode 3 of the background mode.

With the flattened stereo background mode the BD J application draws an image for the left eye and an image for the right eye which make up a stereo image that is a background 3D image on the logical plane .

Subsequently the 3D compatible player draws one of the image for the left eye and the image for the right eye drawn on the logical plane e.g. the image for the left eye alone on both of the L background plane L and the R background plane R and discards the other image for the right eye.

The background image for the left eye drawn on the L background plane L is supplied to the mixer and also the background image for the left eye drawn on the R background plane R is supplied to the mixer as the image for the right eye .

D in illustrates a mono background mode hereafter also referred to as mono background mode that is one mode Mode 4 of the video mode.

With the mono background mode the BD J application draws stores a mono image that is a background 2D image on the logical plane .

Subsequently the 3D compatible player draws the mono image drawn on the logical plane on one of the L background plane L and the R background plane R for example the L background plane L alone.

E in illustrates a forced stereo background mode hereafter also referred to as forced stereo background mode that is one mode Mode 5 of the background mode.

With the forced stereo background mode the BD J application draws an image for the left eye and an image for the right eye which make up a stereo image that is a background 3D image on the logical plane .

Subsequently the 3D compatible player draws one of the image for the left eye and the image for the right eye drawn on the logical plane e.g. the image for the left eye alone on one of the L background plane L and the R background plane R for example the L background plane L alone and discards the other image for the right eye.

Now let us say that the graphics plane which stores graphics the video plane which stores video and also the PG plane which stores PG and the background plane which stores background shown in will be collectively referred to as device planes.

With the BD player in which is a 3D compatible player the configurations of the device planes are defined so as to be represented with four attributes of 1 Image frame resolution and color depth 2 Video mode 3 Graphics mode BD J Graphics mode and 4 Background mode.

The graphics plane is configured of the L graphics plane L serving as an L region that is a storage region for storing an image for the left eye and the R graphics plane R serving as an R region that is a storage region for storing an image for the right eye. With the graphics plane the L graphics plane L and the R graphics plane R are disposed in an array.

Specifically in the L graphics plane L and the R graphics plane R are vertically arrayed in a form wherein the L graphics plane L that is an L region is disposed on the upper side and also the R graphics plane R that is an R region is disposed on the lower side thereby configuring the graphics plane .

The other device planes i.e. the PG plane video plane and background plane are also configured in the same way as the graphics plane .

The images drawn on the graphics plane PG plane video plane and background plane are overlaid blended in the order of the graphics plane PG plane video plane and background plane from the near side and the images of the L region and the images of the R region obtained as a result thereof are alternately drawn stored on a logical screen wherein the display screen of a display is abstracted.

Also the device planes are all made up of a storage region where an L region and an R region which are each one image worth of image storage region are vertically arrayed and accordingly are two images worth of image storage region but the logical screen is one image worth of image storage region.

With regard to 3D images the configurations of the device planes are defined as to the entirety of device planes which are two images worth of image storage regions.

In the image frames the number of horizontal x vertical pixels of a device plane resolution and color depths of five rows from the top indicate the image frames and color depths of 3D images and the image frames and color depths of the remaining five rows five rows from the bottom indicate the image frames and color depths of 2D images.

With one image worth of 2D image as one image worth of image a 3D image is made up of an image for the left eye and an image for the right eye and accordingly is two images worth of image. Also all of the device planes are storage regions where an L region and an R region which are one image worth of image storage regions are vertically arrayed and accordingly the image frame of a 3D image to be stored in such a device plane has a size obtained by doubling the number of pixels in the vertical direction of the image frame of the corresponding 2D image 2D image having the same size as the image for the left eye or image for the right eye .

Note that with the current BD standard with regard to 2D images both of the image frame of graphics image stored in the graphics plane and the image frame of background image stored in the background plane are essentially matched with the image frame of video image stored in the video plane .

However with regard to 2D images in the case that the image frame of video to be stored in the video plane is 1920 1080 pixels the image frame of background to be stored in the background plane is 1920 1080 pixels in the same way as the image frame of video to be stored in the video plane but the image frame of graphics to be stored in the graphics plane may be 960 540 pixels obtained by dividing each of the width and length of the image frame of video to be stored in the video plane into halves the fourth row from the bottom in hereafter also referred to as mismatched case of 2D images .

In this case the graphics of 960 540 pixels to be stored in the graphics plane is displayed after the size thereof is matched with 1920 1080 pixels that is the image frame of video to be stored in the video plane by doubling each of the width and length thereof.

With regard to 3D images as well there may be a case corresponding to a mismatched case of 2D images hereafter also referred to as mismatched case of 3D images .

With a mismatched case of 3D images in the event that the image frame of video to be stored in the video plane is 1920 2160 pixels the image frame of background to be stored in the background plane is 1920 2160 pixels in the same way as the image frame of video to be stored in the video plane but the image frame of graphics to be stored in the graphics plane may be 960 1080 pixels obtained by dividing each of the width and length of the image frame of video to be stored in the video plane into halves the third row from the top in .

Even in a case of mismatched 3D images the graphics of 960 1080 pixels is displayed after the size thereof is matched with 1920 2160 pixels that is the image frame of video to be stored in the video plane by doubling each of the width and length thereof.

With the second drawing method such as described in B in the original image serving as a source for generating a 3D image is drawn on the logical plane and then an image for the left eye and an image for the right eye to be generated by the shifting of the original image in the horizontal direction by the offset value are drawn on the graphics plane .

Now the second drawing method may also be described as a method wherein two images obtained by horizontally shifting the upper side half and the lower side half of a vertically long image where two images of the original image and a copy of the original image are vertically arrayed in accordance with the offset value are drawn on the graphics plane as an image for the left eye and an image for the right eye.

Now with the second drawing method in a case of mismatched 3D images an image for the left eye and an image for the right eye of 960 540 pixels obtained by shifting each of the upper side half and the lower side half of graphics of 960 1080 pixels in the horizontal direction in accordance with the offset value are drawn on the graphics plane and then upon doubling each of the width and length of the image for the left eye and the image for the right eye of the graphics plane an image for the left eye and an image for the right eye obtained as a result thereof are images of which the shift amount in the horizontal direction is double of the offset value.

Accordingly in this case the position in the depth direction of a 3D image displayed with the image for the left eye and the image for the right eye is a position different from the position intended by the author.

Therefore in a case of mismatched 3D images in the event of drawing a 3D image using the second drawing method an image obtained by doubling each of the width and length of the original image serving as a source for generating a 3D image needs to be drawn on the logical plane with an image for the left eye and an image for the right eye to be generated by shifting the image drawn on the logical plane in the horizontal direction by the offset value then being drawn on the graphics plane .

Thus the position in the depth direction of a 3D image displayed with the image for the left eye and the image for the right eye is the position intended by the author.

With the current BD standard one image worth of image storage region is assumed as the logical screen and it is not assumed that an image for the left eye Left Left eye and an image for the right eye Right Right eye are alternately drawn on the logical screen which is one image worth of image storage region thereof.

Further with the current BD standard it is assumed that there is one on one relationship between the configuration of a device plane and the logical screen . Under such an assumption two separate logical screens of a logical screen for drawing the image for the left eye and a logical screen for drawing the image for the right eye need to be provided as the logical screen regarding 3D image processing.

Therefore with the BD player in which is a 3D compatible player the device configurations for L R are defined with one image by doubling the definition of resolution in the vertical direction. A drawing model is defined wherein the logical screen itself is taken as one image as conventionally done and outputs for L R are drawn thereon simultaneously.

That is to say the BD player in includes the device planes graphics plane video plane PG plane and background plane storing graphics video or background image conforming to BD.

The device planes are storage regions where two images worth of image storage regions of an L region which is one image worth of image storage region storing an image for the left eye and an R region which is one image worth of image storage region storing an image for the right eye are disposed in an array and the configurations of the device planes are defined as to the entirety of device planes which are image storage for two images.

The image for the left eye and the image for the right eye stored in the device planes are for example alternately drawn on the logical screen .

Thus a logical screen storing an image for the left eye image for L and a logical screen storing an image for the right eye image for R do not have to be provided separately.

Configurations can be specified set with a bit field for specifying a configuration by providing this within a BD J object file.

Four fields of initial configuration id initial graphics mode initial video mode and initial background mode can be provided within a BD J object file to specify a configuration.

The initial configuration id is a field for specifying 1 image frame and color depth. If we say that the value that initial configuration id takes is configuration id the following values can be defined as configuration ids.

Note that HD19201080 represents the image frame and color depth at the sixth row from the top of HD1280720 represents the image frame and color depth at the eighth row from the top of SD720576 represents the image frame and color depth at the tenth row from the top of SD720480 represents the image frame and color depth at the ninth row from the top of QHD960540 represents the image frame and color depth at the seventh row from the top of HD19202160 represents the image frame and color depth at the first row from the top of HD12801440 represents the image frame and color depth at the second row from the top of FIG. SD7201152 represents the image frame and color depth at the fifth row from the top of SD720960 represents the image frame and color depth at the fourth row from the top of and QHD9601080 represents the image frame and color depth at the third row from the top of respectively.

Now there are a total of five modes of the offset graphics mode offset stereo graphics mode stereo mono graphics mode mono Legacy playback mode forced mono graphics mode forced mono Legacy playback mode and a flattened stereo graphics mode flattened stereo described with as the graphics mode BD J Graphics mode .

Let us say that the following values are defined as initial graphics mode for specifying the graphics mode.

Note that GRAPHICS MONO VIEW represents the mono graphics mode GRAPHICS STEREO VIEW the stereo graphics mode GRAPHICS PLANE OFFSET the offset graphics mode GRAPHICS DUAL MONO VIEW the flattened stereo graphics mode and GRAPHICS FORCED MONO VIEW the forced mono graphics mode.

Also in the case that initial configuration id is set to any one of 1 2 3 4 and 5 initial graphics mode is ignored.

Now there are a total of five modes of the dual mono video mode dual mono stereo video mode stereo flattened stereo video mode flattened stereo mono video mode mono Legacy playback mode and forced mono video mode forced mono described in as the video mode.

Let us say that the following values are defined as initial video mode for specifying the video mode.

Note that VIDEO MONO VIEW represents the mono video mode VIDEO STEREO VIEW represents the stereo video mode VIDEO FLATTENED STEREO VIEW represents the flattened stereo video mode VIDEO DUAL MONO VIEW represents the dual mono video mode and VIDEO FORCED MONO VIEW represents the forced mono video mode respectively.

Also in the case that initial configuration id is set to one of 1 2 3 4 and 5 initial video mode is ignored.

Now there are a total of four five of the dual mono background mode dual mono stereo background mode stereo flattened stereo background mode flattened stereo mono background mode mono Legacy playback mode and forced mono background mode forced mono described in as the background mode.

Let us say that the following values are defined as initial background mode for specifying the background mode.

Note that BACKGROUND MONO VIEW represents the mono background mode BACKGROUND STEREO VIEW represents the stereo background mode BACKGROUND FLATTENED STEREO VIEW represents the flattened stereo background mode BACKGROUND DUAL MONO VIEW represents the dual mono background mode and BACKGROUND FORCED MONO VIEW represents the forced mono background mode respectively.

Also in the case that initial configuration id is set to one of 1 2 3 4 and 5 initial background mode is ignored.

Now with the BD J Object file specifications may be employed wherein of initial configuration id initial graphis mode initial video mode and initial background mode initial configuration id alone is specified.

With the BD J Object file in the case of specifying initial configuration id alone the default stipulated values of initial video mode initial graphis mode and initial background mode need to be provided.

Note that STEREO VIEW of the video mode initial video mode represents the above VIDEO STEREO VIEW or VIDEO FLATTENED STEREO VIEW and MONO VIEW represents the above VIDEO MONO VIEW or VIDEO DUAL MONO VIEW.

Also STEREO VIEW of the graphics mode initial graphics mode represents the above GRAPHICS STEREO VIEW or GRAPHICS PLANE OFFSET and MONO VIEW represents the above GRAPHICS MONO VIEW or GRAPHICS DUAL MONO VIEW.

Further STEREO VIEW of the background mode initial background mode represents the above BACKGROUND STEREO VIEW or BACKGROUND FLATTENED STEREO VIEW and MONO VIEW represents the above BACKGROUND MONO VIEW or BACKGROUND DUAL MONO VIEW.

The configurations can be changed at timing of when auto reset at the time of starting a BD J title or at the time of playing a PlayList is performed dynamic change and when API call up by a BD J application is performed dynamic change .

Unlike at the time of playback of mono video mono graphics with conventional arrangements change in a plane configuration can be made even during playback of AV.

That is to say with the 3D compatible player the configuration may be changed when playing AV streams video .

Similar to Mono view with playback other than KEEP RESOLUTION playback the 3D compatible player performs configuration change processing so that image frames are aligned so that video background is aligned with the image frame of graphics at the time of starting a BD J title so that graphics background is aligned with the image frame of video and at the time of playback of a PlayList or so that the image frame of a plane set by API is aligned with the image frame of an unset plane other than that plane at the time of API call up by a BD J application . Also error processing at the time of change in the configuration depends on the 3D compatible player.

Now KEEP RESOLUTION playback is a playback mode for synthesizing SD Standard Definition video and HD High Definition graphics and HD background and there is a case where Graphics of 1920 1080 pixels Video PG of 720 480 pixels and Background of 1920 1080 pixels are synthesized and a case where Graphics of 1920 1080 pixels Video PG of 720 576 pixels and Background of 1920 1080 pixels are synthesized. Note that regardless of an HD image reproduction of an image of 1280 720 pixels is not included in KEEP RESOLUTION playback.

A in illustrates an example of processing of the 3D compatible player in the case that the configuration video mode of graphics graphics plane is changed from STEREO VIEW to MONO VIEW.

For example with the 3D compatible player in the case that the video mode is STEREO VIEW graphics is drawn on the L graphics plane L and the R graphics plane R making up the graphics plane of 1920 2160 pixels let us say that the video mode is changed from STEREO VIEW to MONO VIEW without resetting the storage region serving as the graphics plane .

In this case with the 3D compatible player only the image stored drawn on one of the L graphics plane L and the R graphics plane R making up the graphics plane e.g. the L graphics plane L is supplied to the logical screen and displayed and the image stored in the R graphics plane R which is the other is discarded.

B in illustrates an example of the processing of the 3D compatible player in the case that the video mode is changed from MONO VIEW to STEREO VIEW.

For example with the 3D compatible player in the case that the video mode is MONO VIEW graphics is drawn on the L graphics plane L alone making up the graphics plane of 1920 1080 pixels let us say that the video mode is changed from MONO VIEW to STEREO VIEW without resetting the graphics plane .

In this case with the 3D compatible player the graphics drawn on the L graphics plane L is copied to the R graphics plane R the graphics drawn on the L graphics plane L is supplied to the logical screen as the image for the left eye and also the graphics copied to the R graphics plane R is supplied to the logical screen as the image for the right eye.

The following three rules 1 1 1 2 and 1 3 are applied to change in a configuration at the time of starting a BD J title in principle.

Specifically the rule 1 1 is a rule wherein with the configuration of a device plane the resolutions image frames of three images of Graphics Video and Background must be the same resolutions all the time.

The rule 1 2 is a rule wherein in the case that playback of a PlayList other than KEEP RESOLUTION playback is performed the resolutions image frames of three images of Graphics Video and Background must be aligned with the resolution of video.

The rule 1 3 is a rule wherein with the configuration in the case that graphics is QHD graphics resolution after scaling double in the vertical direction and in the horizontal direction is taken as the resolution of the configuration.

Note that the value of each of the video mode graphics mode and background mode is determined in accordance with the default value stipulation by the initial configuration id of a BD J object file video mode graphics mode and background mode are determined .

Also in the case that autostart first PlayList flag of the BD J object file is set to change in the configuration of the video plane follows not the default value but an auto reset dynamic change rule at the time of playback of a PlayList.

The following three rules 2 1 2 2 and 2 3 are applied to change in a configuration when auto reset at the time of playing a PlayList is performed in principle.

Specifically the rule 2 1 is a rule wherein with the configuration of a device plane the resolutions image frames of three images of Graphics Video and Background must be the same resolutions all the time.

The rule 2 2 is a rule wherein in the case that playback of a PlayList other than KEEP RESOLUTION playback is performed the resolutions image frames of three images of Graphics Video and Background must be aligned with the resolution of video.

The rule 2 3 is a rule wherein with the configuration in the case that graphics is QHD graphics resolution after scaling double in the vertical direction and in the horizontal direction is taken as the resolution of the configuration.

At the time of start of playback of a PlayList the video plane configuration is automatically aligned with the video attribute of the PlayList.

In the case that the configuration is automatically aligned with the video attribute of the PlayList with the current BD standard it is stipulated to automatically align the graphics plane and background plane with the attribute of the video plane as an indispensable function on the BD player side. However with the 3D compatible player at the time of switching from a stereo PlayList playlist for playing a 3D image to a mono PlayList playlist for playing a 2D image or at the time of switching from a mono PlayList to a stereo PlayList the graphics and background modes graphics mode and background mode are set to predetermined initial values.

A 3D image of 1920 2160 pixels is played as graphics and a 3D image of 1920 2160 pixels is played as background.

The following three rules 3 1 3 2 and 3 3 are applied to change in a configuration when API call up by a BD J application is performed in principle.

Specifically the rule 3 1 is a rule wherein with the configuration of a device plane the resolutions image frames of three images of Graphics Video and Background must be the same resolutions all the time.

The rule 3 2 is a rule wherein in the case that playback of a PlayList other than KEEP RESOLUTION playback is performed the resolutions image frames of three images of Graphics Video and Background must be aligned with the resolution of video.

The rule 3 3 is a rule wherein with the configuration in the case that graphics is QHD graphics resolution after scaling double in the vertical direction and in the horizontal direction is taken as the resolution of the configuration.

During playback of a graphics 3D image stereo G video 3D image stereo V and background 3D image stereo B in the case that the resolution of the graphics 3D image has been changed according to API call up the 3D compatible BD player automatically change the resolutions of the video 3D image and background 3D image in accordance with the above rules 3 1 3 2 and 3 3.

Also during playback of a graphics 3D image stereo G video 3D image stereo V and background 3D image stereo B in the case that the resolution of the background 3D image has been changed according to API call up the 3D compatible BD player automatically change the resolutions of the graphics 3D image and video 3D image in accordance with the above rules 3 1 3 2 and 3 3.

Further during playback of a graphics 3D image stereo G video 3D image stereo V and background 3D image stereo B in the case that the resolution of the video 3D image has been changed according to API call up the 3D compatible BD player automatically change the resolutions of the graphics 3D image and background 3D image in accordance with the above rules 3 1 3 2 and 3 3.

The 3D compatible player can seamlessly perform change in the graphics mode between the stereo graphics mode stereo graphics and the offset graphics mode offset graphics .

A in illustrates a case where during playback of a graphics 3D image plane offset gfx graphics in the offset graphics mode video and PG 3D image stereo video PG and background 3D image stereo background the graphics mode is changed from the offset graphics mode to the stereo graphics mode.

In this case switching from playback of the graphics 3D image plane offset gfx in the offset graphics mode video and PG 3D image stereo video PG and background 3D image stereo background to playback of the graphics 3D image stereo gfx graphics in the stereo graphics mode video and PG 3D image stereo video PG and background 3D image stereo background is performed and this switching can be performed seamlessly.

Inverse switching i.e. from playback of the graphics 3D image stereo gfx in the stereo graphics mode video and PG 3D image stereo video PG and background 3D image stereo background to playback of the graphics 3D image plane offset gfx in the offset graphics mode video and PG 3D image stereo video PG and background 3D image stereo background can also be performed seamlessly.

B in illustrates a case where during playback of a graphics 3D image stereo gfx in the stereo graphics mode video and PG 3D image stereo video PG and background 2D image mono background the graphics mode is changed from the stereo graphics mode to the offset graphics mode.

In this case switching from playback of the graphics 3D image stereo gfx in the stereo graphics mode video and PG 3D image stereo video PG and background 2D image mono background to playback of the graphics 3D image plane offset gfx in the offset graphics mode video and PG 3D image stereo video PG and background 2D image mono background is performed and this switching can be performed seamlessly.

Inverse switching i.e. from playback of the graphics 3D image plane offset gfx in the offset graphics mode video and PG 3D image stereo video PG and background 2D image mono background to playback of the graphics 3D image stereo gfx in the stereo graphics mode video and PG 3D image stereo video PG and background 2D image mono background can also be performed seamlessly.

In the case that the graphics mode has been changed from the stereo graphics mode stereo gfx to the offset graphics mode plane offset gfx playback of video L R Left Right video and background L R Left Right background are still continued.

On the other hand with regard to graphics a playback object is switched from a graphics 3D image stereo gfx in the stereo graphics mode to a graphics 3D image plane offset gfx in the offset graphics mode.

Implementation of a switching method of this playback object depends on an individual 3D compatible player. However at the time of switching of a playback object so called black out and interruption of playback of AV video have to be prevented from occurrence.

Note that in the case that resolution is also changed at the time of change in the graphics mode black out may occur.

Next the 3D compatible player can seamlessly perform change in the background mode between the stereo background mode stereo background and the mono background mode mono background .

A in illustrates a case where during playback of a graphics 3D image stereo gfx a video and PG 3D image stereo video PG and a background 3D image stereo background in the stereo background mode the background mode is changed from the stereo background mode to the mono background mode.

In this case switching from playback of the graphics 3D image stereo gfx video and PG 3D image stereo video PG and background 3D image stereo background in the stereo background mode to playback of the graphics 3D image stereo gfx video and PG 3D image stereo video PG and background 2D image mono background in the mono background mode is performed and this switching can be performed seamlessly.

B in illustrates a case where during playback of a graphics 3D image plane offset gfx a video and PG 3D image stereo video PG and a background 2D image mono background in the mono background mode the background mode is changed from the mono background mode to the stereo background mode.

In this case switching from playback of the graphics 3D image plane offset gfx video and PG 3D image stereo video PG and background 2D image mono background in the mono background mode to playback of the graphics 3D image plane offset gfx video and PG 3D image stereo video PG and background 3D image stereo background in the stereo background mode is performed and this switching can be performed seamlessly.

Next the 3D compatible player can seamlessly perform change in the video mode between the stereo video mode stereo video the flattened stereo video mode flattened stereo video and the dual mono video mode dual mono video .

A in is a diagram for describing change in the video mode in the case that a graphics 3D image stereo gfx a background 3D image stereo background and also a video image are being played.

In the case that the video mode is the stereo video mode and a video and PG 3D image stereo video PG in the stereo video mode is being played when the video mode is changed from the stereo video mode to the flattened stereo video mode the video image is switched from the video and PG 3D image stereo video PG in the stereo video mode to a video and PG 3D image flattened video PG in the flattened stereo video mode and this switching can be performed seamlessly.

Also in the case that the video mode is the flattened stereo video mode and a video and PG 3D image flattened video PG in the flattened stereo video mode is being played when the video mode is changed from the flattened stereo video mode to the dual mono video mode the video image is switched from the video and PG 3D image flattened video PG in the flattened stereo video mode to a video and PG 3D image dual mono video PG in the dual mono video mode and this switching can be performed seamlessly.

B in is a diagram for describing change in the video mode in the case that a graphics 3D image plane offset gfx a background 2D image mono background and also a video image are being played.

In the case that the video mode is the dual mono video mode and a video and PG 3D image dual mono video PG in the dual mono video mode is being played when the video mode is changed from the dual mono video mode to the flattened stereo video mode the video image is switched from the video and PG 3D image dual mono video PG in the dual video mode to a video and PG 3D image flattened video PG in the flattened stereo video mode and this switching can be performed seamlessly.

Also in the case that the video mode is the flattened stereo video mode and a video and PG 3D image flattened video PG in the flattened stereo video mode is being played when the video mode is changed from the flattened stereo video mode to the stereo video mode the video image is switched from the video and PG 3D image flattened video PG in the flattened stereo video mode to a video and PG 3D image stereo video PG in the stereo video mode and this switching can be performed seamlessly.

With the current BD standard a configuration is stipulated with resolution image frame and color depth. Therefore change in a configuration means change in resolution. However at the time of change in resolution playback is temporarily stopped and the display screen is a blacked out state.

On the other hand for example the mono logical plane offset value playback mode of the graphics plane or the like can be stipulated as a configuration of 1920 1080 32 bpp but this case may induce black out for example by switching from mono logical plane offset value to stereo logical plane or the like.

Therefore with the 3D compatible player plane configurations are unified into a two face definition configuration of 1920 2160 pixels 1280 1440 pixels 960 1080 pixels 720 960 pixels or 720 1152 pixels and an attribute other than resolution color depth is defined as a mode value. Thus in the case that only the mode is changed without changing resolution a configuration can be changed without causing the display screen to go into a blacked out state. Further similar to a legacy player change in a configuration can be performed by calling up the Configuration Preference setting API.

With the 3D compatible player in the configuration of a device plane which is a storage region where two images worth of image storage regions of an L region which is one image worth of image storage region storing an image for the left eye and an R region which is one image worth of image storage region storing an image for the right eye are disposed in an array is defined as to the entirety of the device plane thereof.

Also five modes of the mono graphics mode stereo graphics mode offset graphics mode forced mono graphics mode and flattened stereo graphics mode are defined as the graphics mode. Further five modes of the mono video mode dual mono video mode stereo video mode forced mono video mode and flattened stereo video mode are defined as the video mode. Also five modes of the mono background mode dual mono background mode stereo background mode forced mono background mode and flattened stereo background mode are defined as the background mode.

Also the configuration of a device plane includes 1 image frame resolution and color depth 2 video mode 3 graphics mode and 4 background mode and the setting change of 2 video mode 3 graphics mode and 4 background mode can be performed by the configuration mode setting API.

With the 3D compatible player in in the case of changing the video mode graphics mode or background mode a BD J application calls up the configuration mode setting API and requests change setting of the video mode graphics mode or background mode.

The configuration mode setting API directly or indirectly controls a necessary one of the presentation engine Presentation Engine video decoder and display processor according to the request from the BD J application thereby changing setting the video mode graphics mode or background in accordance with the request from the BD J application.

On the other hand in the case of changing the image frame resolution and color depth the BD J application calls up the resolution setting API to request change setting of resolution and the like.

The resolution setting API directly or indirectly controls a necessary one of the presentation engine video decoder and display processor according to the request from the BD J application thereby changing setting the image frame resolution and color depth in accordance with the request from the BD J application.

Note that in the presentation engine provides the decoding function and presentation function of audio video and HDMV graphics to a playback control engine not illustrated for controlling playback of BD.

Also in the video encoder performs decoding of images. Further the display processor is hardware for overlaying each plane of the graphics plane video video PG plane and background plane and then outputting an image obtained with overlaying thereof to the display connected to the BD player.

As described above the configuration of a device plane is defined as to the entirety of the device plane which is two images worth of image storage regions and the graphics mode and the like are included in the configuration of the device plane separately from the resolution image frame and color depth. Subsequently the 3D compatible player sets the graphics mode and the like according to calling up of the configuration mode setting API. Thus the graphics mode and the like can be changed without changing the resolution.

Video PG TextST Text subtitle is handled collectively without distinction from BD J applications. Also BD J applications cannot individually control the PG plane but can control of the position or scaling size of video. Note that with the current BD standard in the case that control of the position or scaling of video is performed from a BD J application PG TextST is to be aligned with the video.

Accordingly in the case that control of the scaling of video is to be performed the PG plane offset value is scaled with a scaling ratio percentage of enlargement or percentage of reduction for scaling the video.

On the other hand it is desirable to allow the 3D compatible player to set a mode for playing mono PG images that are 2D images 1 plane legacy playback a mode for playing stereo PG images that are 3D images 2 planes and a mode for playing 3D PG images using an image for the left eye and an image for the right eye with disparity generated from a 2D image and the offset value 1 plane offset .

Therefore with the 3D compatible player PG plane control 1 plane legacy playback and switching of configurations between 1 plane offset and 2 planes are indirectly performed by selecting a PG stream.

Therefore with regard to HDMV PG mono PG streams that are the PG streams of a PG image that is a mono image serving as a 2D image stereo PG streams that are the PG streams of a PG image that is a stereo image serving as a 3D image and PG streams for offset that are the PG streams of a mono PG image used for generating a stereo image e.g. streams including a mono PG image and an offset value are defined as the PG streams of a PG image conforming to the BD standard along with an offset value giving disparity to a mono image.

Further with regard to HDMV PG mono 1 stream legacy content mode L R 2 stream mode and 1 stream plane offset mode are defined as a PG playback mode for playing a PG image.

Now in the case that the PG playback mode is the mono 1 stream mode a 2D PG image is played using mono PG streams.

In the case that the PG playback mode is the L R 2 stream mode a 3D PG image is played by playing an image for the left eye and an image for the right eye using stereo PG streams.

In the case that the PG playback mode is the 1 stream plane offset mode a 3D PG image is played by generating an image for the left eye and an image for the right eye using PG streams for offset based on the offset value and playing the image for the left eye and the image for the right eye.

Also with regard to HDMV TextST mono TextST streams that are the TextST streams of a TextST image that is a mono image serving as a 2D image stereo TextST streams that are the TextST streams of a TextST image that is a stereo image serving as a 3D image and TextST streams for offset that are the TextST streams of a TextST image that is a mono image used for generating a stereo image e.g. streams including a TextST image that is a mono image and an offset value are defined as the TextST streams of a TextST image conforming to the BD standard along with an offset value giving disparity to a mono image.

Further with regard to HDMV TextST mono 1 stream legacy content mode L R 2 stream mode and 1 stream plane offset mode are defined as a TextST playback mode for playing a TextST image.

Now in the case that the TextST playback mode is the mono 1 stream mode a 2D TextST image is played using mono TextST streams.

In the case that the TextST playback mode is the L R 2 stream mode a 3D TextST image is played by generating an image for the left eye and an image for the right eye using streams using a stereo TextST stream.

In the case that the TextST playback mode is the 1 stream plane offset mode a 3D TextST image is played by generating an image for the left eye and an image for the right eye using TextST streams for offset based on the offset value and playing the image for the left eye and the image for the right eye.

With the 3D compatible player the configuration of the PG Text ST can be switched set through API for selecting streams.

With regard to HDMV PG even in the case that the video mode configuration is any of the mono video mode mono flattened stereo video mode flattened stereo dual mono video mode dual mono forced mono video mode forced mono and stereo video mode stereo the 1 stream plane offset mode mono offset PG stream for offset can be selected.

Accordingly the PG streams for offset can be selected even in the case that the video mode is any of the mono video mode flattened stereo video mode dual mono video mode forced mono video mode and stereo video mode.

Also with regard to HDMV PG the L R 2 stream mode stereo stereo PG stream can be selected regardless of which one of the flattened stereo video mode flattened stereo dual mono video mode dual mono forced mono video mode forced mono and stereo video mode stereo the video mode is.

Accordingly the stereo PG streams can be selected regardless of which one of the flattened stereo video mode dual mono video mode forced mono video mode and stereo video mode the video mode is.

However in the case that the video mode is the mono video mode mono flattened stereo video mode flattened stereo forced mono video mode forced mono or dual mono video mode dual mono when the PG streams for offset mono offset are selected the mono image of the PG streams for offset is played ignoring the offset value setting the offset value to 0 .

Also in the case that the video mode is the mono video mode mono or forced mono video mode forced mono when the stereo PG streams stereo are selected one of an image for the left eye and an image for the right eye making up a stereo image corresponding to the stereo PG streams e.g. the image for the left eye L PG streams alone is played.

Also in the case that the video mode is the flattened stereo video mode flattened stereo or dual mono video mode dual mono when the stereo video streams stereo are selected in the event that the a PG stream for offset of which the stream No. which is a No. to be assigned to the stream which matches the selected stereo PG stream exists is recorded in the BD mono images of the PG stream for offset having the same stream No. as the stereo PG stream is played instead of the selected stereo PG stream ignoring the offset value.

On the other hand with regard to HDMV TextST even in the case that the video mode configuration is one of the mono video mode mono flattened stereo video mode flattened stereo forced mono video mode forced mono and dual mono video mode dual mono the 1 stream plane offset mode mono offset Text subtitle stream for offset can be selected.

Accordingly the TextST streams for offset Text subtitle streams for offset can be selected in the case that the video mode is one of the mono video mode flattened stereo video mode forced mono vide mode and dual mono video mode.

Also with regard to HDMV TextST the L R 2 stream mode stereo stereo Text subtitle stream can be selected regardless of which one of the flattened stereo video mode flattened stereo dual mono video mode dual mono forced mono video mode forced mono and stereo video mode stereo the video mode is.

Accordingly the stereo TextST streams stereo Text subtitle streams can be selected regardless of which one of the flattened stereo video mode dual mono video mode forced mono video mode and stereo video mode the video mode is.

However in the case that the video mode is the mono video mode mono flattened stereo video mode flattened stereo forced mono video mode forced mono or dual mono video mode dual mono when the TextST streams for offset mono offset are selected the mono image of the TextST streams for offset is played ignoring the offset value.

Also in the case that the video mode is the mono video mode mono or forced mono video mode forced mono when a stereo TextST stream stereo is selected just the left eye image L TextST stream for example of the left eye stream and right eye stream making up the stereo image corresponding to the stereo TextST stream is played.

Also in the case that the video mode is the flattened stereo video mode or dual mono video mode when a stereo TextST stream is selected in the event that the a TextST stream for offset of which the stream No. which is a No. to be assigned to the stream which matches the selected stereo TextST stream exists mono images of the TextST stream for offset having the same stream No. as the stereo TextST stream is played instead of the selected stereo TextST stream ignoring the offset value.

In a 3D compatible player is configured of a BD J application PG TextST stream selecting API video control API PG selecting engine Playback Control Function TextST selecting engine Playback Control Function video control engine Playback Control Function playback control engine Playback Control Engine presentation engine Presentation Engine and the like.

Processing of the 3D compatible player in will be described with reference to with processing regarding PG as an example.

The BD J application calls up the PG TextST stream selecting API to request selection of PG streams. The PG TextST stream selecting API selects the PG streams requested from the BD J application.

That is to say such as described in in the event that the PG streams requested from the BD J application can be selected as to the current video mode the PG TextST stream selecting API controls the PG selecting engine so as to select the PG streams thereof.

The PG selecting engine selects the PG streams in accordance with the control of the PG TextST stream selecting API from the PG streams recorded in the disc which is BD and supplies these to a stereo PG decoder or mono PG decoder not illustrated in .

Now in the case that the PG streams selected by the PG selecting engine are stereo PG streams the stereo PG streams thereof are supplied to the stereo PG decoder.

Also in the case that the PG streams selected by the PG selecting engine are PG streams for offset the PG streams thereof are supplied to the mono PG decoder.

The stereo PG decoder decodes the PG streams supplied from the PG selecting engine to an image for the left eye and an image for the right eye making up a stereo image and draws these on each of the L PG plane L and R PG plane R of the PG plane .

On the other hand the mono PG decoder decodes the PG streams for offset supplied from the PG selecting engine to a mono image and draws this on the logical plane .

The PG generating API generates an image for the left eye and an image for the right eye from the mono image drawn on the logical plane using the offset value e.g. an offset value included in the PG streams for offset an internal storage region of the 3D compatible player or the offset value stored in PSR 21 . Subsequently the PG generating API draws the image for the left eye and the image for the right eye on the L PG plane L and the R PG plane R of the PG plane respectively.

Note that with the 3D compatible player such as described in depending on a combination between the current video mode and the PG streams PG playback mode selected by the PG selecting engine one of the image for the left eye and the image for the right eye making up the stereo image corresponding to the stereo PG streams e.g. only the image for the left eye may be played or only the mono image corresponding to the PG streams for offset may be played ignoring the offset value.

As described above with the 3D compatible player mono PG streams that are the PG streams of a PG image that is a mono image serving as a 2D image stereo PG streams that are the PG streams of a PG image that is a stereo image serving as a 3D image and PG streams for offset that are the PG streams of a mono PG image used for generating a stereo image are defined as the PG streams of a PG image conforming to the BD standard along with an offset value that is data giving disparity to a mono image. Subsequently the PG TextST stream selecting API selects mono PG streams stereo PG streams or PG streams for offset in accordance with the request from the BD J application.

Accordingly playback of a PG image configuration of PG can indirectly be controlled from the BD J application.

Subsequently the graphics mode is the stereo graphics mode stereo gfx graphics the video mode is the stereo video mode stereo video and the background mode is the mono background mode respectively.

Subsequently the graphics mode is changed to the offset graphics mode plane offset gfx and the video mode is changed to the dual mono video mode dual mono video respectively.

Further subsequently in the operation mode is changed from the 3D playback mode to the 2D playback mode Legacy playback mode for playing 2D images in the same way as with the legacy player.

In accordance with change in the operation mode the graphics mode is changed from the offset graphics mode plane offset gfx to the mono graphics mode mono gfx . Further the video mode is changed from the dual mono video mode dual mono video to the mono video mode mono video . Note that the background mode is still in the mono background mode mono background .

Subsequently in the operation mode is changed from the 2D playback mode to the 3D playback mode again.

In accordance with change in the operation mode the graphics mode is changed from the mono graphics mode mono gfx to the stereo graphics mode stereo gfx . Further the video mode is changed from the mono video mode mono video to the flattened stereo video mode flattened stereo video . Note that the background mode is still in the mono background mode mono background .

In subsequently the background mode is changed from the mono background mode mono background to the stereo background mode stereo background .

In for example in the case that the operation mode is changed from the 3D playback mode to the 2D playback mode when change in resolution image frame is accompanied the display screen may black out.

JMF Java registered trademark Media Framework control such as javax.tv.media.AwTVideoSizeControl org.dvb.media.BackgroundVideoPRsentationControl or the like can be used for the control of the position and size of video from a BD J application.

Note that the author of a BD J application sets the position and size of video using not the coordinates on the plane video plane but display coordinates.

Also the 3D compatible player must perform correction of the position and size of each of the image for the left eye L video source and the image for the right eye R video source .

For example the display coordinate system is a coordinate system of the size of 1920 1080 pixels as to the video plane of 1920 2160 pixels vertically a half thereof. In this case the author must set the position and size of video such as the following for example.

The author sets the position and size of the video image for the left eye. In the position and size of the image for the left eye of video are set to the display coordinate system of the size of 1920 1080 pixels.

The 3D compatible player sets the settings of the position and size of the image for the left eye of video as to the display coordinate system to the L video plane L of the video plane without change.

Further the 3D compatible player applies the settings of the position and size of video of the L video plane L to the R video plane R without change.

Accordingly as viewed from the author in the event that the position and size of video are set to the L video plane L the same position and same size as those of video thereof are also set to the R video plane R.

Now with regard to video depth information is not provided externally. Accordingly an arrangement for providing an offset is not only wasteful but also can lead to output unintended by the video producer.

That is to say while video producers should produce video images so as to display intended 3D images with the 3D compatible player for example upon processing being performed such as shifting of the positions of the images image for the left eye and image for the right eye of video drawn on the video plane or the like according to information to be provided externally such as the offset value or the like stored in PSR 21 an image that the video producer does not intend may be displayed.

Therefore with the 3D compatible player L R video plane is defined on the configuration but restraints are provided so as to allow the author of a BD J application to handle only L video plane. That is to say the 3D compatible player also must apply the API call up of L video scaling L video positioning by a BD J application to R video scaling R video positioning.

Note that in the event that setting the size of the video causes the video to be scaled to that size the PG plane offset value is scaled by the scaling percentage percentage of enlargement or percentage of reduction for scaling the video as described in Switching of PG Text Subtitle Configuration and the graphics plane offset value also is scaled by the scaling percentage of the video in the same way.

The 3D compatible player in includes API for L for setting the size and position of an image to be stored in the L video plane L L region and API for R for setting the size and position of an image to be stored in the R video plane R R region . One of the API for L and the API for R sets the same size and same position as the size and position set by the other API.

That is to say with the 3D compatible player in a video decoder decodes video and supplies the image for the left eye and the image for the right eye obtained as a result thereof to the API for L and the API for R.

The API for L is made up of L video scaling L Left video scaling API and L video positioning L Left positioning API and sets the position and size of the image for the left eye from the video decoder according to call up of the setting requests for the position and size of video from a BD J application.

That is to say the L video scaling API performs scaling to control the size of the image for the left eye from the video decoder so as to obtain the size according to the request from the BD J application and supplies this to the L video positioning API.

The L video positioning API controls the position of the image for the left eye from the L video scaling API so as to obtain the position according to the request from the BD J application and draws an image for the left eye obtained as a result thereof on the L video plane L draws the image for the left eye from the L video scaling API on the position on the L video plane L according to the request from the BD J application .

Also the L video scaling API calls up a later described R video scaling API to perform the same request as the request from the BD J application. Further the L video positioning API calls up a later described R video positioning API to perform the same request as the request from the BD J application.

Also in response to the video size setting request the L video scaling API supplies the scaling percentage percentage of enlargement or percentage of reduction S at the time of scaling the video image image for left eye to the PG generating API and graphics generating API.

The API for R is made up of R video scaling R Right video scaling API and R video positioning R Right positioning API and sets the position and size of the image for the right eye from the video decoder according to the setting requests of the position and size of video from the API for L.

That is to say the R video scaling API controls the size of the image for the right eye from the video decoder so as to obtain the size according to the request from the L video scaling API and supplies this to the R video positioning API.

The R video positioning API controls the position of the image for the right eye from the R video scaling API so as to obtain the position according to the request from the L video positioning API and draws an image for the right eye obtained as a result thereof on the R video R.

As described above of API for L for setting the size and position of an image to be stored in the L video plane L L region and API for R for setting the size and position of an image to be stored in the R video plane R R region one API thereof e.g. the API for R sets the same size and same position as the size and position set by the API for L that is the other API according to the request from the BD J application.

Accordingly with regard to the video plane where a video image conforming to the BD standard is stored the author is allowed to handle only the L video plane L which is one of the L video plane L L region and the R video plane R R region and accordingly a video image unintended by the video producer can be prevented from being displayed.

It should be noted however that at the PG generating API PG plane offset values e.g. offset values included in the offset PG stream offset values stored in the internal storage region of the 3D compatible player or in the PSR 21 are scaled at the scaling percentage S from the L video scaling API the PG plane offset values are multiplied by the scaling percentage S .

Then at the PG generating IP a left eye image and right eye image are generated from the mono image supplied to the logical plane using the PG plane offset value following scaling.

Also with the 3D compatible player the configuration mode setting API selects images of the graphics mode corresponding to the request from the BD J application from the graphics images recorded in the disc which is a BD and draws these on the graphics plane .

That is to say in the event that the video mode is for example the stereo graphics mode a left eye image and right eye image which are stereo image graphics are drawn on the L graphics plane L and R graphics plane R of the graphics plane respectively.

Also in the event that the video mode is for example the offset graphics mode an image of the mono image graphics is drawn on the logical plane and further the graphics generating API performs scaling of the graphics plane offset value e.g. offset value offset value stored in the internal storage region of the 3D compatible player or in the PSR 21 at the scaling percentage S from the L video scaling API.

The graphics generating API generates a left eye image and right eye image from the mono image drawn on the logical plane using the graphics plane offset value following scaling which are drawn on the L graphics plane L and R graphics plane R respectively.

The pixel coordinate system effective for the stereo graphics configuration configuration for displaying graphics 3D images is one of the following.

An image drawn on the L graphics plane L which is a storage region on the upper side of the graphics plane top half is an image for the left eye observed by the left eye L Left graphics view and an image drawn on the R graphics plane R which is a storage region on the lower side of the graphics plane bottom half is an image for the right eye observed by the right eye R Right graphics view .

In one container Root container and two components that are children of the container thereof are drawn.

The coordinates of a component are represented with relative coordinates with the container serving as the parent of the component thereof as a reference.

Note that with the 3D compatible player a buffer region for the purpose of guarding must not be provided to the edge of the graphics plane .

Also the 3D compatible player must implement an arrangement for suppressing mismatching between L view and R view.

Now the BD player which is a legacy player has no mechanism for detecting completion of drawing by a BD J application and transferring this to a monitor after completion. In the case of L and R video outputs output mismatching may occur between L graphics and R graphics.

Therefore with the 3D compatible player some sort of API call up is defined as a signal indicating completion of drawing by the BD J application. Conversely if the BD J application calls up no drawing completion notification API nothing is output on the screen. The author always has to resort to using this technique.

That is to say after the image image for the left eye is drawn on the L graphics plane L before drawing of an image as to the R graphics plane R is completed upon the drawing content of the graphics plane being displayed on the display screen as an image for the left eye and an image for the right eye the image for the left eye and the image for the right eye thereof are mismatched images not viewable as a 3D image in this case drawing of the image for the right eye is imperfect and accordingly this causes an uncomfortable feeling to the user who looks at the image on the display screen.

Thus in order to prevent the user from having uncomfortable feeling the 3D compatible player has a function for suppressing mismatching between the image for the left eye and the image for the right eye i.e. a function for preventing the image for the left eye and the image for the right eye which are in a mismatched state so as to be viewable as a 3D image from being displayed on the display screen.

Specifically after completing drawing of both of the image for the left eye and the image for the right eye as to the graphics plane the 3D compatible player outputs the image for the left eye and the image for the right eye to display these.

Accordingly the 3D compatible player needs to recognize that drawing of both of the image for the left eye and the image for the right eye as to the graphics plane has been completed.

With Direct drawing the 3D compatible player has no way for telling whether or not issuance of drawing commands for drawing a graphics image from the BD J application has been completed.

Specifically in the case that the BD J application has issued drawing commands 1 2 and so on through N and drawing of an image to the graphics plane has been performed in accordance with the drawing commands 1 through N thereafter the 3D compatible player cannot recognize whether or not a drawing command will be further issued i.e. whether or not issuance of drawing commands by the BD J application has been completed.

Therefore in the case of performing drawing of images as to the graphics plane by drawing commands the author of the BD J application is obligated to perform call up of a drawing integrity guarantee API which ensures the integrity of the drawing of graphics so that the processing is not returned to the BD J application until drawing to the graphics plane is completed as signaling as to the 3D compatible player.

Alternatively in the case of performing drawing of images as to the graphics plane by drawing commands the author of the BD J application is obligated to perform call up of the drawing completion notification API for notifying that drawing of images as to the graphics plane has been completed as signaling as to the 3D compatible player.

Alternatively in the case of performing drawing of images as to the graphics plane by drawing commands the author of the BD J application is obligated to perform call up of a drawing start notification API for notifying that drawing of images as to the graphics plane has been started and subsequently call up of the drawing completion notification API for notifying that drawing of images as to the graphics plane has been completed as signaling as to the 3D compatible player.

In this case the 3D compatible player can recognize that drawing of images to the graphics plane has ended i.e. that issuance of the drawing command has been completed by call up of the drawing integrity guarantee API call up of the drawing completion notification API or call up of the drawing start notification API and the subsequent call up of the drawing completion notification API. Subsequently as a result thereof the image for the left eye and the image for the right eye can be displayed in a matched state so as to be viewable as a 3D image .

Now a dedicated API having a drawing command sequence as an argument can be defined as the drawing completion notification API.

Also for example the java.awt.Toolkit sync method can be employed as the drawing completion notification API. In this case with the 3D compatible player as long as call up of the java.awt.Toolkit sync method is not performed images drawn on the graphics plane are not output and accordingly the images drawn on the graphics plane are not displayed on the display screen.

Further for example a predetermined method of java registered trademark or a dedicated API can be defined as the drawing start notification API.

Note that upon call up of the java.awt.Toolkit sync method being performed multiple times during one frame during 1 video frame graphics frames may include dropped frames. Accordingly it is not allowed for call up of the java.awt.Toolkit sync method to be consecutively performed multiple times or to be consecutively performed with little drawing therebetween.

With an AWT Abstract Windowing toolkit paint model the repaint method of the root container serving as a part making up a graphics image calls up the update method of each component serving a part making up a graphics image.

Subsequently with the AWT paint model the drawing process of a graphics image can completely be controlled at the 3D compatible player and accordingly the 3D compatible player can recognize that drawing of images as to the graphics plane has been completed.

Accordingly implementation of the 3D compatible player can be performed so that the image for the left eye and the image for the right eye in a matched state are displayed even in the event that call up of the above drawing completion notification API is not performed.

Note that here the BD J application calls up the drawing completion notification API in the event that drawing of the images to the graphics plane has been completed.

The 3D compatible player includes buffers L and R and buffers L and R serving as the graphics plane .

Note that in the buffers L and L are equivalent to the L graphics plane L and the buffers R and R are equivalent to the R graphics plane R.

Also a set of the buffers L and R and a set of the buffers L and R alternately serve as a back buffer hidden buffer and a front buffer.

Here the back buffer is a buffer where drawing of graphics images is performed by the BD J application and the front buffer is a buffer where images to be displayed on the display screen logical screen are stored while drawing of images is performed in the back buffer.

A in illustrates the 3D compatible player in a state in which the set of the buffers L and R are the back buffer and the set of the buffers L and R are the front buffer.

In A in drawing of graphics images image for the left eye and image for the right eye by the BD J application is performed as to the buffers L and R serving as the back buffer and images image for the left eye and image for the right eye stored in the buffers L and R serving as the front buffer are output as output to the display screen.

Upon drawing of the graphics images being completed as to the buffers L and R serving as the back buffer the BD J application calls up the drawing completion notification API.

Upon call up of the drawing completion notification API being performed the 3D compatible player starts output of the images stored in the back buffer to the display screen as substitute for the front buffer.

That is to say B in illustrates the 3D compatible player immediately after call up of the drawing completion notification API is performed.

Upon call up of the drawing completion notification API being performed the 3D compatible player starts output of the images stored in the buffers L and R serving as the back buffer to the display screen as substitute for the images stored in the buffers L and R serving as the front buffer.

Further the 3D compatible player copies the images stored in the buffers L and R serving as the back buffer to the buffers L and R serving as the front butter.

Specifically the 3D compatible player sets the buffers L and R serving as the back buffer to the front buffer and sets buffers L and R serving as the front buffer to the back buffer.

That is to say C in illustrates the 3D compatible player in a state in which the set of the buffers L and R are the front buffer and the set of the buffers L and R are the back buffer.

The BD J application starts drawing of graphics images as to the buffers L and R serving as the back buffer and thereafter the same processing is repeated.

In step S the 3D compatible player determines whether or not there has been a call up of the drawing integrity assurance API from the BD J application and in the event that determination is made that there is not the flow returns to step S.

Also in step S in the event that determination is made that there has been a call up of the drawing integrity assurance API the flow proceeds to step S where the 3D compatible player sequentially executes the drawing command sequence serving as the argument of the drawing integrity assurance API draws the graphics image obtained as a result thereof to the back buffer and also outputs the graphics image stored in the front buffer to the display screen outputs for display .

Subsequently after completion of drawing to the back buffer in step S the 3D compatible player outputs the graphics images stored in the back buffer to the display screen as substitute for the front buffer output for display .

Subsequently in step S the 3D compatible player copies the graphics images stored in the back buffer to the front buffer.

Subsequently in step S the 3D compatible player switches the back buffer and the front buffer and returns to step S and thereafter the same processing is repeated.

As described above with the 3D compatible player in the event of call up of the drawing integrity assurance API for ensuring the integrity of the drawing of graphics images as to the graphics plane serving as the back buffer from the BD J application the images drawn on the graphics plane are output for display.

Accordingly after awaiting for notification that drawing of graphics images by the 3D compatible player has been completed being performed the images drawn on the graphics plane can be displayed and accordingly the image for the left eye and the image for the right eye can be prevented from being displayed on the display screen in a mismatched state.

The 3D compatible player awaits issuance of a drawing command from the BD J application and in step S executes the drawing command thereof.

Subsequently in step S the 3D compatible player draws graphics images obtained as a result of execution of the drawing command in the back buffer and also outputs the graphics images stored in the front buffer to the display screen output for display .

Subsequently in step S the 3D compatible player determines whether or not call up of the drawing completion notification API has been performed from the BD J application.

In the case that determination is made in step S that call up of the drawing completion notification API has not been performed the 3D compatible player awaits issuance of a drawing command from the BD J application and returns to step S and thereafter the same processing is repeated.

Also in the case that determination is made in step S that call up of the drawing completion notification API has been performed the 3D compatible player proceeds to step S and outputs the graphics images stored in the back buffer to the display screen as substitute for the front buffer output for display .

Subsequently in step S the 3D compatible player copies the graphics images stored in the back buffer to the front buffer.

Subsequently in step S the 3D compatible player switches the back buffer and the front buffer awaits issuance of a drawing command from the BD J application and returns to step S and thereafter the same processing is repeated.

As described above with the 3D compatible player in the event of call up of the drawing completion notification API for notifying that drawing of graphics images as to the graphics plane serving as the back buffer has been completed being performed from the BD J application the images drawn on the graphics plane are output for display.

Accordingly after notification that drawing of graphics images by the BD J application has been completed being performed the images drawn on the graphics plane can be displayed and accordingly the image for the left eye and the image for the right eye in a mismatched state can be prevented from being displayed on the display screen.

In step S the 3D compatible player determines whether or not there has been call up of the drawing start notification API from the BD J application and in the event of determination that there is not the flow returns to step S.

Also in step S in the event that determination is made that there has been call up of the drawing start notification API the 3D compatible player awaits for issuance of a drawing command from the BD J application advances to step S and executes that drawing command.

Subsequently in step S the 3D compatible player determines whether or not call up of the drawing completion notification API has been performed from the BD J application.

In the case that determination is made in step S that call up of the drawing completion notification API has not been performed the 3D compatible player awaits issuance of a drawing command from the BD J application and returns to step S and thereafter the same processing is repeated.

Also in the case that determination is made in step S that call up of the drawing completion notification API has been performed the 3D compatible player proceeds to step S draws graphics images obtained as the result of executing the drawing command to the back buffer and also outputs the graphics images stored in the front buffer to the display screen output for display .

Subsequently in step S the 3D compatible player outputs the graphics images stored in the back buffer to the display screen as substitute for the front buffer output for display .

Subsequently in step S the 3D compatible player copies the graphics images stored in the back buffer to the front buffer.

Subsequently in step S the 3D compatible player switches the back buffer and the front buffer returns to step S and thereafter the same processing is repeated.

As described above with the 3D compatible player in the event of call up of the drawing start notification API notifying starting of drawing graphics images and the subsequent call up of the drawing completion notification API for notifying that drawing of graphics images as to the graphics plane serving as the back buffer has been completed being performed from the BD J application the images drawn on the graphics plane are output for display.

Accordingly after notification that drawing of graphics images by the BD J application has been completed being performed the images drawn on the graphics plane can be displayed and accordingly the image for the left eye and the image for the right eye in a mismatched state can be prevented from being displayed on the display screen.

The pixel coordinate system effective for the stereo background configuration configuration for displaying background 3D images is one of the following.

Note that the format of background images Contents format is one of single color Single color JPEG JFIF and MPEG2 drip feed and in the case that the format is the MPEG2 drip feed background images must be SD images SD video only .

Also JPEG JFIF images of 1920 2160 pixels 1280 1440 pixels 720 960 pixels or 720 1152 pixels may be used as background images.

For example in the case that widget based GUI Graphical User Interface or the like is employed as a graphics image with the legacy player multiple components which are children of a certain single container making up the GUI cannot have focus all at once.

Also with the legacy player multiple root containers making up GUI cannot be made active all at once in a focused state .

Here containers are components parts of a graphics image and are capable of having parents upper layers and children lower layers . A container having no parent but children alone is referred to as a root container.

In the case that GUI serving as a graphics image is a 3D image with each of an image for the left eye and an image for the right eye making up the 3D image thereof the corresponding container has to be focused and transition of the focus thereof needs to be performed in the same way equally .

Specifically in the case that of the image for the left eye and the image for the right eye a certain container making up one of the images is focused but a container making up the other image corresponding to that container is not focused a user who views a 3D image displayed with such an image for the left eye and an image for the right eye is caused to have uncomfortable feeling.

Thus in order to prevent the user from having uncomfortable feeling the 3D compatible player performs focus management so as to have the same focus transition at the container of the image for the left eye and the container of the image for the right eye.

The GUI in is made up of every two corresponding components 1 2 and 3 which make up one root container and a child of the root container thereof.

Note that in the components 1 2 and 3 drawn on the L graphics plane L make up an image for the left eye and the components 1 2 and 3 drawn on the R graphics plane R make up an image for the right eye.

For example in the event that the component i of the image for the left eye is focused the component i which is the corresponding component of the image for the right eye also must be focused.

In order to make widget state transition management symmetric between L and R the 3D compatible player handles this by causing the two containers or components to be focused simultaneously. Therefore an instance of the containers or components needs to have a flag indicating whether or not focus is held so as to be manageable. Also the third focus request must be made to fail. That is to say the number of containers or components holding focus is restricted to 0 or 2.

A focus method for causing two corresponding containers components of the image for the left eye and the image for the right eye to be focused includes a first focus method and a second focus method.

The first focus method causes two corresponding containers of a container component on the L graphics plane L and a container component on the R graphics plane R serving as children of a container Root Container straddling the L graphics plane L and the R graphics plane R to be focused simultaneously.

B in illustrates the second focus method 2 root containers one for L graphics plane another for R graphics plane .

With the second focus method a root container is drawn on each of the L graphics plane L and the R graphics plane R and both of the root containers are activated caused to be focused simultaneously.

Now let us say that containers components making up GUI to be drawn on the graphics plane have a focus flag representing whether or not the corresponding container component is focused.

Upon focus being requested in step S the 3D compatible player sets a variable i for counting the number of containers to 0 serving as an initial value.

Subsequently in step S the 3D compatible player determines whether or not there have already been two components in a focused state hereafter also referred to as focus holding components of components containers which are the children of a container c i on the graphics plane based on the focus flag of each component.

In the case that determination is made in step S that there are not two focus holding components of the components serving as the children of the container c i the 3D compatible player proceeds to step S and causes the two corresponding components to have the requested focus. Further in step S the 3D compatible player sets a value to the effect that focus is held to the focus flag of each of the two components caused to be focused and proceeds to step S.

On the other hand in the case that determination is made in step S that there are two focus holding components of the components serving as the children of the container c i the 3D compatible player skips step S proceeds to step S increments the variable i by one and proceeds to step S.

In step S the 3D compatible player determines whether or not the variable i is less than the number of containers N on the graphics plane . In the case that determination is made in step S that the variable i is less than the number of containers N on the graphics plane the 3D compatible player returns to step S and the same processing is repeated.

Also in the case that determination is made in step S that the variable i is not less than the number of containers N on the graphics plane the processing ends.

As described above in the case that two containers are not focused as to a focus request the 3D compatible player changes a container on the L graphics plane L L region storing the image for the left eye and a container on the R graphics plane R R region storing the image for the right eye into a focused state.

Accordingly for example of containers making up a 3D image widget the transition of focus can be set in the same way between a container of an image for the left eye and a container of an image for the right eye.

In the case of Stereo graphics the two dimensional coordinates on the screen of a mouse cursor may be different coordinates on the L and R graphics planes. Accordingly the BD J application needs to perform coordinate conversion when describing processing depended on mouse events but an offset value for coordinate conversion differs for each implementation of a BD player and accordingly is unknown.

A cursor is displayed by a BD player but with the 3D compatible player it is desirable to display the 3D image of a cursor so as to be viewable in a position nearer than a graphics 3D image 3D image to be played from the disc .

On the other hand in the case of displaying the cursor using a 3D image the cursor of an image for the left eye on the logical screen is in a position x x y shifted by a certain offset value x from a position x y on the display screen where the 3D image of the cursor can be seen and the cursor of an image for the right eye on the logical screen is also in a position x x y shifted by a certain offset value x from the position x y on the display screen where the 3D image of the cursor can be seen.

Here a position in the depth direction of the 3D image of the cursor is changed according to the certain offset value x.

With the 3D compatible player in the case of displaying the 3D image of the cursor in a position nearer than a graphics 3D image a value max depth representing the nearest position in the depth direction Z direction of the graphics 3D image needs to be used. However with the 3D compatible player it is difficult to compute the value max depth from the graphics 3D image.

Therefore for example the value max depth is recorded beforehand in the disc which is BD and the 3D compatible player can set store the value max depth thereof to the PSR e.g. PSR 21 .

In this case the 3D compatible player or display which displays the 3D image output by the 3D compatible player can obtain the offset value x for displaying the cursor on nearer side than the position represented with the value max depth with reference to the value max depth stored in the PSR. Subsequently the 3D image of the cursor can be displayed in a position nearer than the graphics 3D image.

Note that OSD On Screen display that the 3D compatible player displays can also be displayed in a position nearer than the graphics 3D image in the same way as with the cursor.

Also a value min depth representing the deepest side position in the depth direction of a 3D image to be played from the disc which is BD is recorded beforehand in the disc which is BD along with the value max depth whereby the value max depth and the value min depth can be set to the PSR .

As described above with the 3D compatible player the value max depth representing the nearest side position in the depth direction of the 3D image recorded in the disc which is BD and the like are set to the PSR whereby the cursor and OSD can be displayed on nearer side than the 3D image to be played from the BD.

Incidentally the 3D compatible player can arbitrarily set the offset value x for displaying the 3D image of the cursor. Also there is no need for the offset value x to be constant and for example may be set changed for each frame.

Accordingly upon employing the position x y of the display screen as the position of the cursor when issuing an event with the cursor position as an argument as to the BD J application the BD J application must perform coordinate conversion of the position x y of the display screen thereof to obtain a cursor position x x y or x x y on the graphics plane .

However in order to perform coordinate conversion of the position x y of the display screen the BD J application needs to recognize the offset value x and it is difficult for the BD J application to recognize the offset value x that the 3D compatible player can arbitrarily set.

Therefore the coordinate system of mouse events is restricted to only the L graphics plane. The BD player is obligated to employ coordinates on the L graphics plane as the two dimensional position information at the time of issuing a mouse event as to the BD player.

Specifically with the 3D compatible player for example the 3D image of the cursor of a pointing device such as a mouse is configured of an image for the left eye and an image for the right eye but as the cursor position at the time of issuing an event with the cursor position as an argument one of the L graphics plane L L region and the R graphics plane R R region of the graphics plane of the 3D image of the cursor e.g. a position on the L graphics plane L L region is used.

Thus the BD J application can know recognize a position on the L graphics plane L as the cursor position of a 3D image and accordingly the author of the BD J application can describe processing as to an event mouse event with the cursor position as an argument using the position on the graphics plane L as the cursor position.

The 3D compatible player must ensure matching between L view and R view. Specifically the 3D compatible player must ensure that the image for the left eye and the image for the right eye of graphics are drawn in a matched state as to the graphics plane so as to be viewable as a 3D image and are then displayed on the display screen.

Initialization reset of the graphics plane is similarly performed. Specifically in the case of initializing one of the L graphics plane L and the R graphics plane R of the graphics plane the other also must be initialized.

However the author of the BD J application has a responsibility authoring responsibility for meaningful matching between L view and R view i.e. matching of image contents between the image for the left eye and the image for the right eye of graphics.

A in illustrates the image for the left eye and the image for the right eye of graphics drawn in a matched state.

In A in drawing of the image for the left eye as to the L graphics plane L and drawing of the image for the right eye as to the R graphics plane R have been completed and thus after completion of drawing the 3D compatible player must display the image for the left eye and the image for the right eye on the display screen.

Note that with the drawing integrity guarantee API described with a drawing command sequence is taken as an argument but the command sequence which is the argument for the drawing integrity guarantee API has to be a drawing command sequence for drawing a left eye image and a right eye image in a matching manner so as to appear as a 3D image and according to this drawing integrity guarantee API drawing of the left eye image and right eye image of the graphics in a matching manner is ensured.

B in illustrates the image for the left eye and the image for the right eye of graphics drawn in a mismatched state.

In B in drawing of the image for the left eye as to the L graphics plane L has been completed but drawing of the image for the right eye as to the R graphics plane R has not been completed.

The 3D compatible player must not display the image for the left eye and the image for the right eye in the state in B in on the display screen.

Matching between the image for the left eye and the image for the right eye of graphics can be ensured for example by employing triple buffering at the 3D compatible player.

The 3D compatible player includes a back buffer hidden buffer serving as the graphics plane front buffers and .

The back buffer is configured of buffers L and R. The front buffer is configured of buffers L and R and the front buffer is configured of buffers L and R.

Note that in the buffers L L and L are equivalent to the L graphics plane L and store an image for the left eye. The buffer R R and R are equivalent to the R graphics plane R and store an image for the right eye.

The BD J application issues a drawing command and the 3D image of graphics serving as a result of execution of the drawing command thereof image for the left eye and image for the right eye is drawn on the back buffer .

On the other hand the front buffers and are alternately selected and the image for the left eye and the image for the right eye stored in the buffer which is the selected one hereafter also referred to as selected buffer are displayed on the display screen supplied to Display processor .

After completion of drawing of the image for the left eye and the image for the right eye as to the back buffer the image for the left eye and the image for the right eye stored drawn in the back buffer thereof are copied to the unselected one of the front buffers and .

Switching of selection for alternately selecting the front buffers and as a selected buffer is executed at timing of VIBE Vertical Blanking Interval after readout copy of the image for the left eye and the image for the right eye from the back buffer is completed up to the last horizontal line to prevent occurrence of tearing artifacts.

FAA Frame Accurate Animation includes two of Image Frame Accurate Animation and Sync Frame Accurate Animation but in order to operate an image for the left eye and an image for the right eye used for animation synchronously for the sake of L R synchronization with the 3D compatible player it is desirable to individually perform drawing of the image for the left eye for animation and drawing of the image for the right eye for animation even with any of Image Frame Accurate Animation and Sync Frame Accurate Animation to operate animation at two places simultaneously .

That is to say with the legacy player animation is operated only at one place. In the event of using an image or buffer so as to straddle L and R animation operation can be performed at two places in a pseudo manner but a sufficient animation frame rate is not output due to performance demands on the BD player side.

In a single image of w h 1080 pixels is drawn straddling the L graphics plane L and the R graphics plane R of the graphics plane of 1920 2160 pixels.

In of the image of w h 1080 pixels a portion excluding the upper portion of a w h pixel image and the lower portion of a w h pixel image central portion is filled with transparent pixels transparent color whereby the upper portion of a w h pixel image can be taken as the image for the left eye for animation and the lower portion of a w h pixel image can be taken as the image for the right eye for animation.

That is to say the central portion of the single image in is filled with transparent color whereby appearance when viewing the single image can be set to a state in which the w h pixel image is drawn on the same position of the L graphics plane L and the R graphics plane R. Accordingly 3D image animation can be realized wherein the w h pixel image on the L graphics plane L and the w h pixel image on the R graphics plane R are operated synchronously.

However in regardless of the image for the left eye and the image for the right eye used for animation being the w h pixel images drawing of a huge single image of w h 1080 pixels needs to be performed.

As a result it may take time to draw the image depending on the performance of the BD player and it is difficult to display 3D image animation with a sufficient frame rate.

Therefore with the 3D compatible player drawing of the image for the left eye for animation and drawing of the image for the right eye for animation are individually performed.

With the 3D compatible player the image for the left eye for animation is drawn on the L graphics plane L L region . Further with the 3D compatible player the image for the right eye for animation is drawn on the R graphics plane R R region separately from drawing of the image for the left eye for animation as to the L graphics plane L L region .

Thus drawing of the image for the left eye and the image for the right eye used for animation can rapidly be performed and as a result thereof 3D image animation can be displayed with a sufficient frame rate.

A in illustrates a configuration example of a 3D compatible player for drawing animation as Image Frame Accurate Animation.

An image buffer is a buffer serving as cache memory for a BD J application loading and saving a resource from the disc which is BD and stores a list of images for the left eye for animation list of images for L and a list of images for the right eye for animation list of images for R .

A pixel transfer device L sequentially reads out images for the left eye for animation from the image buffer in increments of pixels to draw these on the L graphics plane L.

A pixel transfer device R sequentially reads out images for the right eye for animation from the image buffer in increments of pixels to draw these on the R graphics plane R.

B in illustrates a configuration example of a 3D compatible player for drawing animation as Sync Frame Accurate Animation.

Graphics memory is work memory of the 3D compatible player and is configured of a buffer storing images for the left eye for animation buffer for images for L and a buffer storing images for the right eye for animation buffer for images for R .

A pixel transfer device L sequentially reads out images for the left eye for animation from the graphics memory in increments of pixels to draw these on the L graphics plane L.

A pixel transfer device R sequentially reads out images for the right eye for animation from the graphics memory in increments of pixels to draw these on the R graphics plane R.

Further sample code of Image Frame Accurate Animation is illustrated in and . Note that is a diagram continuing from .

Also sample code of Sync Frame Accurate Animation is illustrated in and . Note that is a diagram continuing from .

Now the embodiments of the present invention are not restricted to the above mentioned embodiment and various modifications can be performed without departing from the essence of the present invention.

That is to say according to the present embodiment an arrangement has been made wherein with the BD player in which is a 3D compatible player processing is performed as to 3D image contents and Java registered trademark applications recorded in the disk but an arrangement may be made wherein the 3D image contents and Java registered trademark applications to be processed at the 3D compatible player are supplied from data supplying means other than a recording medium such as the disc or the like specifically supplied from for example an object carousel or data carousel which is a digital broadcasting application to the 3D compatible player and at the 3D compatible player the 3D image contents and Java registered trademark applications supplied from the object carousel or data carousel are processed.

