---

title: Information processing apparatus, information processing method, reproducing apparatus, reproducing method, program, and recording medium
abstract: An information processing apparatus includes a controller that sets type information, which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3-D image, in a clip information file which describes information on a transport stream including the dependent view video stream out of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to the a predetermined video coding format.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09036983&OS=09036983&RS=09036983
owner: SONY CORPORATION
number: 09036983
owner_city: Tokyo
owner_country: JP
publication_date: 20130401
---
This application is a continuation of and is based upon and claims the benefit of priority under U.S.C. 120 for U.S. application Ser. No. 12 729 739 filed Mar. 23 2010 and which claims the benefit of priority under 35 U.S.C. 119 from Japanese Patent Application No. 2009 093624 filed Apr. 8 2009 the entire contents of each of which are incorporated herein by reference.

The present invention relates to an information processing apparatus an information processing method a reproducing apparatus a reproducing method a program and a recording medium. Particularly the present invention relates to an information processing apparatus an information processing method a reproducing apparatus a reproducing method a program and a recording medium capable of setting information used to manage reproduction of a base view video stream and a dependent view video stream that is recorded on a recording medium such as a BD blu ray disk and encoded according to the H.264 AVC MVC.

2 dimensional image contents such as movie contents are most widely used in the film industry or the like. Recently stereoscopic image contents capable of providing a solid vision are being focused.

A dedicated device is demanded to display the solid image. As an example of the solid vision device an integral photography IP solid image system has been developed by the Japan Broadcasting Corporation NHK .

Since the image data of the solid vision includes image data at a plurality of viewpoints image data on images captured at a plurality of viewpoints the number of viewpoints is large. Since the viewpoints are distributed in a wide range an object can be seen from many directions. In other words it is possible to implement a peeping television .

A stereoscopic image so called 3 Dimensional image has two viewpoints which is the smallest number of viewpoints out of the solid vision images. The image data of the stereoscopic image contains data on a left image observed by a left eye and data on a right image observed by a right eye.

Meanwhile since high resolution image contents such as a movie have a large data amount a large capacity recording medium is demanded in order to record the contents of a large data amount.

A Blu Ray R disc hereinafter also referred to as a BD such as a Blue Ray R ROM Read Only Memory is usually used as the high capacity recording medium.

However the BD standard does not specify how to record or reproduce the solid vision image data including stereoscopic image to from the BD.

Even when management information of the image data used in the BD standard of the related art is employed without change it may fail to reproduce the stereoscopic image data.

It is desirable to set the information used in management of reproducing base view video streams and dependent view video streams obtained by encoding the H.264 AVC MVC video recorded on the recording medium such as a BD.

According to a first embodiment of the invention an information processing apparatus includes a controller which sets type information which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3 D image in a clip information file which describes information on a transport stream including the dependent view video stream out of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format.

The controller may set the type information when the base view video stream and the dependent view video stream are included in different transport streams.

According to a first embodiment of the invention an information processing method includes a step of setting type information which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3 D image in a clip information file which describes information on a transport stream including the dependent view video stream out of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format.

According to a first embodiment of the invention a program executes in a computer a process including a step of setting type information which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3 D image in a clip information file which describes information on a transport stream including the dependent view video stream out of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format.

According to a first embodiment of the invention there is provided a recording medium where type information which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3 D image is set in a clip information file which describes information on a transport stream including the dependent view video stream out of a base view video stream and a dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format.

According to a second embodiment of the invention a reproducing apparatus reproduces a base view video stream and a dependent view video stream by reading type information recorded in the recording medium where the type information which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3 D image is set in a clip information file which describes information on a transport stream including the dependent view video stream out of the base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format.

According to a second embodiment of the invention a reproducing method includes a step of reproducing a base view video stream and a dependent view video stream by reading type information recorded in a recording medium where the type information which represents that an application for executing a process using a dependent view video stream is set in a clip information file which describes information on a transport stream including the dependent view video stream out of the base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format is an application for reproducing a 3 D image.

According to a second embodiment of the invention a program executes in a computer a process including a step of reproducing a base view video stream and a dependent view video stream by reading type information recorded in a recording medium where the type information which represents that an application for executing a process using a dependent view video stream is set in a clip information file which describes information on a transport stream including the dependent view video stream out of the base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format is an application for reproducing a 3 D image.

According to a third embodiment of the invention an information processing apparatus includes a controller that sets a different value as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a third embodiment of the invention an information processing method includes a step of setting a different value as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a third embodiment of the invention a program executes in a computer a process including a step of setting a different value as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a third embodiment of the invention there is provided a recording medium where a different value is set as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a fourth embodiment of the invention a reproducing apparatus reproduces a base view video stream and a dependent view video stream by reading type information recorded in the recording medium where a different value is set as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a fourth embodiment of the invention a reproducing method includes a step of reproducing a base view video stream and a dependent view video stream by reading type information recorded in a recording medium where a different value is set as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a fourth embodiment of the invention a program executes in a computer a process including a step of reproducing a base view video stream and a dependent view video stream by reading type information recorded in a recording medium where a different value is set as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a first embodiment of the invention type information which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3 D image is set in a clip information file which describes information on a transport stream including the dependent view video stream out of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format.

According to a second embodiment of the invention a base view video stream and a dependent view video stream are reproduced by reading type information recorded in the recording medium where the type information which represents that an application for executing a process using a dependent view video stream is an application for reproducing a 3 D image is set in a clip information file which describes information on a transport stream including the dependent view video stream out of the base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format.

According to a third embodiment of the invention a different value is set as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to a fourth embodiment of the invention a base view video stream and a dependent view video stream are reproduced by reading type information recorded in a recording medium where a different value is set as a value of type information which represents a type of a path which uses a dependent view video stream as a reproducing interval included in reproduction management information used to manage reproduction of a base view video stream and the dependent view video stream obtained by encoding a plurality of video data according to a predetermined video coding format based on whether the dependent view video stream is multiplexed in the same transport stream as that of the base view video stream and a recording location of the dependent view video stream.

According to the present invention it is possible to set the information used in management of reproducing base view video streams and dependent view video streams obtained by encoding the H.264 AVC MVC video recorded on the recording medium such as a BD.

Referring to the reproducing system includes a reproducer and a display device connected with a HDMI High Definition Multimedia Interface cable or the like. The reproducer is installed with an optical disc such as a BD.

Streams are recorded on the optical disc as much as necessary to display a stereoscopic image a so called 3 D image having two viewpoints.

The reproducer is a player corresponding to the 3 D reproducing of the streams recorded on the optical disc . The reproducer reproduces the streams recorded on the optical disc and displays 3 D images obtained by reproducing it on a display device such as a television set. Similarly the reproducer reproduces an audio and outputs it to a loudspeaker installed in the display device .

Various schemes have been proposed as the 3 D image display scheme. Herein type 1 and 2 display schemes are employed as the 3 D image display scheme.

In the type 1 display scheme a 3 D image is displayed by constructing the 3 D image data of data on an image observed by a left eye referred to as an L image and data on an image observed by a right eye referred to as an R image and alternately displaying the L and R images.

In the type 2 display scheme a 3 D image is displayed by displaying the L and R images generated by using original image data of the images functioning as a basis for generating the 3 D image and depth data. The data on the 3 D image used in the type 2 display scheme includes original image data and depth data capable of generating L and R images provided by the original image.

The type 1 display scheme demands a user to wear spectacles to watch the 3 D image. The type 2 display scheme allows a user to watch the 3 D image without spectacles.

On the optical disc streams made to display the 3 D image using either of the type 1 or 2 display scheme are recorded.

As an encoding scheme for recording such streams on the optical disc for example a H.264 AVC Advanced Video Coding MVC Multi view Video coding is employed.

According to the H.264 AVC MVC base view video streams and dependent view video streams are defined. Hereinafter the H.264 AVC MVC will be referred to as an MVC.

Referring to the image capturing is performed using a camera for the L view and a camera for the R view with respect to the same target object. Elementary steams of the videos captured using the camera for the L view and camera for the R view are input to the MVC encoder.

Referring to the MVC encoder includes an H.264 AVC encoder an H.264 AVC decoder a depth calculation unit a dependent view video encoder and a multiplexer .

The streams of a video captured using the camera for the L view are input to the H.264 AVC encoder and the depth calculation unit . The streams of a video captured using the camera for the R view are input to the depth calculation unit and the dependent view video encoder . Alternatively the streams of the video may be input to the H.264 AVC encoder and the depth calculation unit and the streams of the video may be input to the depth calculation unit and the dependent view video encoder .

The H.264 AVC encoder encodes the stream of the video for example as a H.264 AVC high profile video stream. The H.264 AVC encoder outputs the AVC video stream obtained through the encoding to the H.264 AVC decoder and the multiplexer as the base view video stream.

The H.264 AVC decoder decodes the AVC video stream supplied from the H.264 AVC encoder and outputs the stream of the video obtained through the decoding to the dependent view video encoder .

The depth calculation unit calculates a depth based on the streams of the video and and outputs the data on the calculated depth to the multiplexer .

The dependent view video encoder encodes the stream of the video supplied from the H.264 AVC decoder and the stream of the video input from the outside and outputs a dependent view video stream.

A prediction encoding in which one of other streams is used as a reference image is not permitted in the base view video. However as shown in a prediction encoding in which the base view video is used as a reference image is permitted in the dependent view video. For example a data amount of the dependent view video stream obtained by encoding the L view as the base view video and the R view as the dependent view video is smaller than the data amount of the base view video stream.

In addition since the H.264 AVC encoding is employed prediction in a temporal direction is performed for the base view video. Also for the dependent view video the prediction in a temporal direction is performed together with prediction between views. In order to decode the dependent view video it is necessary to previously complete the decoding of the base view video which has been referenced during the encoding.

The dependent view video encoder outputs the dependent view video stream obtained by performing the encoding using the prediction between views to the multiplexer .

The multiplexer multiplexes the base view video stream supplied from the H.264 AVC encoder the dependent view video stream i.e. depth data supplied from the depth calculation unit the dependent view video stream supplied from the dependent view video encoder for example into a MPEG2 TS. The base view video stream and the dependent view video stream may be multiplexed into a single MPEG2 TS or may be included in separate MPEG2 TSs.

The multiplexer outputs the generated TS MPEG2 TS . The TS output from the multiplexer is recorded on the optical disc in the recording device together with other management data and provided to the reproducer as recorded in the optical disc .

If it is necessary to distinguish between the dependent view video used with the base view video in the type 1 display scheme and the dependent view video depth used with the base view video in the type 2 display scheme the former is denoted by a D1 view video and the latter is denoted by a D2 view video.

In addition a 3 D reproduction based on the type 1 display scheme using the base view video and the D1 view video is referred to as a B D1 reproducing. A 3 D reproduction based on the type 2 display scheme using the base view video and the D2 view video is referred to as a B D2 reproducing.

When the B D1 reproducing is to be performed in response to a user s instruction or the like the reproducer reads the base view video stream and the D1 view video stream from the optical disc and reproduces them.

When the B D2 reproducing is to be performed the reproducer reads the base view video stream and the D2 view video stream from the optical disc and reproduces them.

Furthermore when a normal 2 D image is to be reproduced the reproducer reads only the base view video stream from the optical disc and reproduces it.

Since the base view video stream is an AVC video stream encoded based on the H.264 AVC if a player corresponding to a BD format is used it is possible to display the 2 D image by reproducing that base view video stream.

Hereinafter a case where the dependent view video is the D1 view video will be described. If the dependent view video is simply called it means the D1 view video. The D2 view video is recorded on the optical disc and reproduced in a similar way to the D1 view video.

As shown in the AV stream management is performed using two layers i.e. PlayList and Clip . The AV stream may be recorded in the local storage of the reproducer as well as the optical disc .

Herein a pair of a single AV stream and clip information accompanied thereby is considered as a single object and called as a clip. Hereinafter a file storing the AV stream is referred to as an AV stream file. In addition a file storing the clip information is referred to as a clip information file.

The AV stream is deployed on a time axis and access points of each clip are usually specified in the PlayList using a timestamp. The clip information file is used to search for an address starting to be decoded within the AV stream.

The PlayList is a set of reproducing intervals of the AV stream. One of the reproducing intervals within the AV stream is referred to as a PlayItem. The PlayItem is represented by a pair of IN and OUT points of the reproducing interval on the time axis. As shown in the PlayList includes a single of a plurality of PlayItems.

The PlayList located in the first from the left in includes two PlayItems. Using the two PlayItems a first half and a second half of the AV stream included in the left clip are referenced respectively.

The PlayList located in the second from the left includes a single PlayItem and thus the entire AV stream included in the right clip is referenced.

The PlayList located in the third from the left includes two PlayItems. A portion where the AV stream included in the left clip exists and a portion where the AV stream included in the right clip are referenced by the two PlayItems respectively.

For example when the left side PlayItem included in the first PlayList from the left is specified by the disc navigation program as a reproducing location a first half of the AV stream included in the left side clip referenced by that PlayItem is reproduced. In this manner the PlayList is used as the reproduction management information for managing the AV stream reproduction.

Within the PlayList a reproduction path including a sequence of one or more PlayItems is referred to as a main path.

Within the PlayList a reproduction path including a sequence of one or more SubPlayItems in addition to the main path is referred to as a subsidiary path SubPath .

The aforementioned base view video stream is managed as the stream referenced by the PlayItem included in the main path. In addition the dependent view video stream is managed as the stream reference by the SubPlayItem included in the subsidiary path.

The PlayList of includes a single main path made by a sequence of three PlayItems and three subsidiary paths.

IDs are sequentially set in the PlayItems of the main path starting from the leading end. Similarly IDs are sequentially set in SubPlayItems of the subsidiary path starting from the leading end e.g. Subpath id 0 Subpath id 1 and Subpath id 2 .

In the example shown in the subsidiary path set to Subpath id 0 includes a single SubPlayItem. The subsidiary path set to Subpath id 1 includes two SubPlayItems. The subsidiary path set to Subpath id 2 includes a single SubPlayItem.

The clip AV stream referenced by a single PlayItem includes at least a video stream i.e. main image data .

The clip AV stream may include one or more audio streams reproduced at the timing of in synchronization with the video stream of the clip AV stream or may not include the audio stream.

The clip AV stream may include one or more subtitle data streams or presentation graphics PG of bitmaps reproduced in synchronization with the video stream of the clip AV stream or may not include the subtitle data.

The clip AV stream may include one or more interactive graphics IG streams reproduced in synchronization with the video stream of the clip AV stream file or may not include the IG stream. The IG stream is used to display graphics such as a button manipulated by a user.

The clip AV stream referenced by a single PlayItem is obtained by multiplexing the video stream with 0 or more audio streams 0 or more PG streams and 0 or more IG streams reproduced in synchronization with the video stream.

A single SubPlayItem references the video stream the audio stream or the PG stream different separately provided from the clip AV stream referenced by the PlayItem.

The AV stream management using the PlayList the PlayItem and the SubPlayItem is disclosed in for example Japanese Unexamined Patent Application Publication Nos. 2008 252740 and 2005 348314.

Referring to files are hierarchically managed based on a directory structure. A single root directory is created on the optical disc . Files under the root directory are managed by a single recording reproducing system.

Immediately under the BDMV directory an index file Index.bdmv and a MovieObject file MovieObject.bdmv are stored.

Under the BDMV directory a BACKUP directory a PLAYLIST directory a CLIPINF directory and a STREAM directory are provided.

The PLAYLIST directory stores PlayList files that describe the PlayLists. The name of each PlayList file is set by a combination of five numerals and an extension .mpls . The single PlayList file shown in has a file name 00000.mpls .

The CLIPINF directory stores a clip information file. The name of each clip information file is set by a combination of five numerals and an extension .clpi .

Three clip information files shown in have file names 00001.clpi 00002.clpi and 00003.clpi . Hereinafter the clip information file will be referred to simply as a clpi file.

For example the clpi file of 00001.clpi is a file describing information on the clip of the base view video.

The STREAM directory stores stream files. The name of each stream file is set by a combination of five numerals and an extension .m2ts or a combination of five numerals and an extension .ilvt . Hereinafter a file having an extension .m2ts will be referred to simply as an m2ts file a file having an extension .ilvt will be referred to as a ilvt file.

The m2ts file of 00001.m2ts is a 2 D reproducing file and the base view video stream is read by specifying this file.

The m2ts file of 00002.m2ts is a file of a D2 view video stream and the m2ts file of 00003.m2ts is a file of a D1 view video stream.

The ilvt file of 10000.ilvt is a B D1 reproducing file and the base view video stream and the D1 view video stream are read by specifying this file.

The ilvt file of 20000.ilvt is a B D2 reproducing file and the base view video stream and the D2 view video stream are read by specifying this file.

Although shown in under the BDMV directory a directory for storing a file of an audio stream is also provided.

The field length is a 32 bit unsigned integer representing the number of bytes from the bit immediately after this length field to the end of the PlayList In other words the field length represents the number of bytes from the field reserved for future use to the end of the PlayList.

The field number of PlayItems is a 16 bit field representing the number of PlayItems included in the PlayList. In the case of the example of the number of PlayItems is set to 3. To the value of PlayItem id numbers are allocated in the order the PlayItem is provided within the PlayList starting from 0. For example 0 1 and 2 are allocated to the value of PlayItem id of .

The field number of SubPaths is a 16 bit field representing the number of subsidiary paths within the PlayList. In the case of the number of subsidiary paths is 3. To the value of SubPath id numbers are allocated in the order the SubPath is provided within the PlayList starting from 0. For example 0 1 and 2 are allocated to the Subpath id of . In the subsequent for sentence the PlayItem is referenced as many as the number of PlayItems and the SubPath is referenced as many as the number of subsidiary paths.

The field length is a 32 bit unsigned integer representing the number of bytes from the bit immediately after this length field to the end of the SubPath . In other words the field length represents the number of bytes from the field reserved for future use to the end of the PlayList.

The field SubPath type is an 8 bit field representing a type of the application executing a process using the subsidiary path. The field SubPath type is used to represent the type of the subsidiary path for example whether the subsidiary path is related to an audio a bitmap subtitle or a text subtitle. The SubPath type will be described later with reference to .

The field is repeat SubPath is a one bit field for specifying a method of reproducing the subsidiary path and represents whether the subsidiary path is repetitively reproduced while the main path is reproduced or whether the subsidiary path is reproduced only a single time. For example the field is repeat SubPath is used when the reproducing timing of the clip referenced by the main path is different from the reproducing timing of the clip referenced by the subsidiary path such as a case where the main path is used as a path of a slideshow of still images and the subsidiary path is used as a path of an audio such as BGM .

The field number of SubPlayItems is an 8 bit field representing the number entry number of SubPlayItems within a single subsidiary path. For example the field number of SubPlayItems of the SubPlayItem in case of SubPath id 0 as shown in is set to 1 and the field number of SubPlayItems of the SubPlayItem in case of SubPath id 1 is set to 2. In the subsequent for sentence the SubPlayItem is referenced as much as the number of SubPlayItems.

In Out of mux means that the streams referenced by the subsidiary path i.e. the streams referenced by the SubPlayItem included in the subsidiary path and the streams referenced by the main path i.e. the streams referenced by the PlayItem included in the main path are multiplexed in different TSs.

On the contrary In of mux means the streams referenced by the subsidiary path and the streams referenced by the main path are multiplexed in the same TS.

 SubPath type 5 is set to 2nd Audio Presentation path a path for referencing the second audio stream . The second audio stream referenced by the subsidiary path where SubPath type 5 is set includes for example a commentary of a film director.

 SubPath type 6 is set to 2nd Video Presentation path a path for referencing the second video stream . The second video stream referenced by the subsidiary path where SubPath type 6 is set includes for example a comment e.g. a moving picture of a film director .

 SubPath type 7 is set to a path for one or more ESs primary audio PG IG secondary audio or a picture in picture presentation path.

 SubPath type 8 to 11 is used to define a subsidiary path for an application that executes a 3 D reproduction. Herein difference values are set depending on the pattern of the multiplexing of the dependent view video stream referenced by the subsidiary path.

 SubPath type 8 is set to Out of mux 3D SubPath from Disc . This represents that the dependent view video stream referenced by the subsidiary path is recorded in the optical disc and multiplexed in a different TS from the base view video stream referenced by the main path.

 SubPath type 9 is set to In mux 3D SubPath from Disc . This means the dependent view video stream referenced by the subsidiary path is recorded on the optical disc and multiplexed in the same TS as the base view video stream referenced by the main path.

 SubPath type 10 is set to Out of mux 3D SubPath from Local Storage . This means that the dependent view video stream referenced by the subsidiary path is recorded in the local storage and multiplexed in a different TS from the base view video stream referenced by the main path.

As will be described later the reproducer is enabled to execute a 3 D reproduction by downloading dependent view video stream from a server and using it together with the base view video stream recorded in the optical disc .

 SubPath type 11 is set to In mux 3D SubPath from Local Storage . This means the dependent view video stream referenced by the subsidiary path is recorded in the local storage and multiplexed in the same TS as that of the base view video stream referenced by the main path. In this case the base view video stream is also recorded in the local storage.

In this manner in the subsidiary path which references the dependent view video stream a location where the referenced dependent view video stream is recorded and a value representing a multiplexing pattern for the TS are set.

As a result the reproducer can identify whether the dependent view video stream referenced by the subsidiary path is recorded in the optical disc or the local storage.

The reproducer can identify whether the dependent view video stream referenced by the subsidiary path is multiplexed in the same TS as that of the base view video stream or a different TS.

The field length is a 16 bit unsigned integer representing the number of bytes from the bit immediately after the length field to the end of the SubplayItem .

The SubPlayItem i of is described by dividing into a case where the parameter SubPlayItem references a single clip and a case where the parameter SubPlayItem references a plurality of clips.

The field Clip codec identifier 0 represents a codec scheme of the clip. The field Clip codec identifier 0 is followed by the reserved for future use field.

The field is multi Clip entries is a flag representing whether or not the multi clip is registered. When the is multi Clip entries flag is turned on the syntax where the parameter SubPlayItem references a plurality of clips is referenced.

The field ref to STC id 0 represents information on an STC discontinuous point discontinuous points in the system time base .

The field SubPlayItem IN time represents a starting position of the reproducing interval of the subsidiary path and the SubPlayItem OUT time field represents an end position.

The field sync PlayItem id and sync start PTS of PlayItem represent timings for initiating to reproduce the subsidiary path on a time axis of the main path.

The fields SubPlayItem IN time SubPlayItem OUT time sync PlayItem id and sync start PTS of PlayItem are commonly used in the clip referenced by the parameter SubPlayItem. 

Now a case where if is multi Clip entries 1b and the parameter SubPlayItem references a plurality of clips will be described.

The field num of Clip entries represents the number of clips that are referenced. The field Clip Information file name SubClip entry id designates the number of clips except for Clip Information file name 0 . 

The field ref to STC id SubClip entry id represents information on the STC discontinuous point discontinuous points in the system time base . The field ref to STC id SubClip entry id is followed by the field reserved for future use. 

The field length is a 16 bit unsigned integer representing the number of bytes from the bit immediately after the length field to the end of the PlayItem 

The field Clip Information file name 0 represents the name of the clip information file of a clip referenced by the PlayItem . In addition the same five numerals are included in the file name of the m2ts file containing the clips and the file name of the corresponding clip information file.

The field Clip codec identifier 0 represents a codec scheme of the clip. The field Clip codec identifier 0 is followed by the field reserved for future use. The field reserved for future use is followed by the fields is multi angle and connection condition. 

The field ref to STC id 0 represents information on the STC discontinuous point discontinuous points in the system time base .

The field IN time represents the initiation position of the reproducing interval of the PlayItem and the field OUT time represents the end position.

The field OUT time is followed by the fields UO mask table PlayItem random access mode and still mode. 

 STN table includes information on the AV stream referenced by a target PlayItem. If a subsidiary path reproduced in relation to the target PlayItem exists the information on the AV stream referenced by the SubPlayItem included in that subsidiary path is also included.

The field length is a 16 bit unsigned integer representing the number of bytes from the bit immediately after the length field to the end of the STN table The field length is followed by the 16 bit field reserved for future use. 

The field number of video stream entries represents the number of streams where the video stream id is provided entered registered within the STN table 

The field video stream id describes information for identifying the video stream. For example the ID of the base view video stream is specified by this description. The ID of the dependent view video stream may be defined within STN table or may be obtained by calculation as will be described later.

The field video stream number represents the video stream number observed by a user and used in the video conversion.

The field number of audio stream entries represents the number of streams of first audio stream corresponding to the audio stream id entered within the STN table . The field audio stream id represents information for identifying the audio stream and the field audio stream number represents the audio stream number observed from a user and used in the audio conversion.

The field number of audio stream2 entries represents the number of streams of the second audio stream corresponding to the audio stream id2 entered within the STN table . The field audio stream id2 represents information for identifying the audio stream and the field audio stream number represents the audio stream number observed by a user and used in the audio conversion. In this example the audio to be reproduced can be switched.

The field number of PG txtST stream entries represents the number of streams corresponding to the PG txtST stream id entered within the STN table . In this case the PG stream obtained by performing the run length encoding for the bitmap subtitles such as a sub picture of the DVD and the text subtitle file txtST are entered. The field PG txtST stream id represents information for identifying the subtitle stream and the field PG txtST stream number represents the subtitle stream number observed by a user and used in the subtitle conversion.

The field number of IG stream entries represents the number of streams corresponding to the IG stream id entered within the STN table In this case the IG streams are entered. The field IG stream id represents the information for identifying the interactive graphics stream and the field IG stream number represents the graphics stream number observed by a user and used in the graphics conversion.

The IDs of the main TS and subsidiary TS which will be described later are also registered in the STN table A fact that that ID is not the ID of the elementary stream but the ID of the TS is described in the field stream attribute 

The application type is described in the clip information file ClipInfo A single clip information file is provided for each clip.

The application type 1 represents that the TS clip corresponding to the clip information file including the description thereof is a TS for the movie application.

The application type 2 represents that the TS corresponding to the clip information file including the description thereof is a TS for the time based slideshow.

The application type 3 represents that the TS corresponding to the clip information file including the description thereof is a TS for the browsable slideshow.

The application type 4 represents that the TS corresponding to the clip information file including the description thereof is a TS for the subsidiary path of the browsable slideshow.

The application type 5 represents that the TS corresponding to the clip information file including the description thereof is a TS for the subsidiary path of the interactive graphics.

The application type 6 represents that the TS corresponding to the clip information file including the description thereof is a TS for the text subtitle text subtitle data of the subsidiary path.

The application type 7 represents that the TS corresponding to the clip information file including the description thereof is a TS for the subsidiary path including one or more ESs.

The application type 8 represents that the TS corresponding to the clip information file including the description thereof is a TS for the application which performs the 3 D reproduction.

In this manner values for the application for executing the 3 D reproduction are defined using the application type . As a result the application for executing the 3 D reproduction is enabled to identify the TS to be managed by itself based on the value of application type .

In the main TS of the base view video stream the dependent view video stream the primary audio stream the base PG stream the dependent PG stream the base IG stream and the dependent IG stream are multiplexed. In this manner the dependent view video stream may be included in the main TS together with the base view video stream.

The main TS and the subsidiary TS are recorded in the optical disc . The main TS includes at least a base view video stream. The subsidiary TS is a TS including the streams except for the base view video stream and used together with the main TS.

Similar to the video each of base and dependent streams is also provided for the PG and IG in order to allow the 3 D image to be displayed.

Planes of the base views of the PG and IG obtained by decoding each stream are synthesized and displayed with a plane of the base view video obtained by decoding the base view video stream. Similarly the plane of the dependent view of the PG and IG is synthesized and displayed with the plane of the dependent view video obtained by appropriately decoding the dependent view video stream.

For example when the base view video stream is an L view stream and the dependent view video stream is an R view stream the stream of that base view becomes a stream of the L view graphics also for the PG and IG. In addition the PG stream and the IG stream of the dependent view become the stream of the R view graphics.

Meanwhile when the base view video stream is an R view stream and the dependent view video stream is an L view stream the stream of that base view becomes a stream of the R view graphics also for the PG and IG. In addition the PG stream and the IG stream of the dependent view become the stream of the L view graphics.

A value of the application type of the main TS the application type described in the clip information file corresponding to the main TS is set to 1.

The base view video stream included in the main TS is also a stream managed by the movie application which is an application for a typical 2 D reproduction as described above as well as an application for the 3 D reproduction. In the TS managed by both the movie application and the 3 D reproduction application 1 is set as the value of the application type .

In addition since it is included in the same TS as that of the base view video stream a value of the SubPath type of the subsidiary path which references the dependent view video stream is set to 9. In this example the dependent view video stream is recorded in the optical disc .

Since it is included in the same TS as that of the base view video stream the value of the SubPath type of the subsidiary path which references the dependent view video stream is set to 9. Also in this example the dependent view video stream is recorded in the optical disc .

The subsidiary TS of includes the primary audio stream the base PG stream the dependent PG stream the base IG stream and the dependent IG stream.

Since it is the TS managed by the application for executing the 3 D reproduction a value of the application type of the subsidiary TS is set to 8.

In the main TS of the base view video stream the primary audio stream the base PG stream the dependent PG stream the base IG stream and the dependent IG stream are multiplexed.

Since a different TS from that of the base view video stream is included a value of the SubPath type of the subsidiary path which references the dependent view video stream is set to 8. Also in this example the dependent view video stream is recorded in the optical disc .

In this manner in the clip information file corresponding to the subsidiary TS managed by an application executing the 3 D reproduction a value for representing that the TS is managed by the application executing the 3 D reproduction is set by using the value of application type. 

In the subsidiary path which references the dependent view video stream a value corresponding to the pattern of the multiplexing and a location where that dependent view video stream is recorded is set by using the SubPath type .

Furthermore according to the BD standard the number of TSs that can be simultaneously read from the optical disc is limited to 2.

In the browsable slideshow as described above it is envisaged that the audio stream used as the BGM is referenced by the subsidiary path SubPath type 2 in addition to the video stream the stream of the slideshow of a still image referenced by the main path. During the reproduction of the slideshow the video stream referenced by the main path and the audio stream referenced by the subsidiary path are simultaneously read.

Here a 3 D display of the slideshow of the still images will be considered. When the base view video stream and the dependent view video stream as a video stream are included in different TSs two TSs can be read. However it may be difficult to read the audio stream used as the BGM.

In this regard it is operated such that only SubPath type 9 or 11 can be set for the browsable slideshow Application type 3 . As a value of the SubPath type of the subsidiary path which references the dependent view video stream included in the TS managed by the browsable slideshow application a value of 8 or 10 is not set which means that it is included in the TS different from that of the base view video stream.

As a result by limiting the value that can be set by using the value of SubPath type based on the Application type it may avoid a difficulty in reading the TS.

As described with reference to the IDs of each stream stream id referenced by the PlayItem and the SubPlayItem are managed in the STN table .

The video stream id managed in the STN table represents the ID of the base view video stream and the PG txtST stream id represents the ID of the base PG stream. In addition the IG stream id represents the ID of the base IG stream.

Here for the stream of the dependent view each stream id is not registered in the STN table but is derived from calculation using the stream id of the stream of the base view.

For example the stream id of the dependent view video stream is defined in the following equation 1 . video stream id dependent view video stream id 1 

The stream id of the dependent PG stream is defined in the following equation 2 . PG textST stream id Dependent PG textST stream id 2 

The stream id of the dependent IG stream is defined in the following equation 3 . IG stream id Dependent IG stream id 3 

The value of x in the equations 1 to 3 is arbitrarily set. Different values may be input as the value of x in the equations 1 to 3 .

As a result the recording device which records the data in the optical disc is terminated without setting in the STN table the stream id of the dependent view stream in addition to the stream id of the base view stream.

In addition if the stream id of the base view stream is specified from the STN table the reproducer can specify the stream id of the corresponding dependent view stream from calculation.

According to the BD standard various processes using the stream are implemented by a JAVA registered trademark application.

For example when any process using a stream is executed as shown in the JAVA registered trademark application instructs the driver to read the stream by specifying the stream id using an API Application Programming Interface .

The driver sets the stream id specified from the JAVA registered trademark application using the API as the stream id of the base view stream and specifies the stream id of the dependent view stream by calculation based on that. In addition based on the specified stream id the base view stream and the dependent view stream are read.

As a result even when the 3 D display is executed only one stream id is specified by the JAVA registered trademark application using the API. In addition it is necessary to extend the API so that two stream ids can be specified for the base view and the dependent view.

Since the ID of the dependent view stream is automatically calculated from the ID of the base view stream the following advantages can be obtained.

In the BD an algorithm for allowing a player to automatically select a reproduced stream is provided. For example this algorithm is used to automatically determine which subtitle is to be reproduced when any English video is reproduced.

If the stream ID is also allocated to the dependent view stream the stream reproduction selection algorithm provided in the existing player is similarly to be executed for the dependent view and thus the processing load in the player increases. In other words after the player executes the processing of the stream reproduction selection algorithm by focusing on the base view stream it is necessary to execute the stream reproduction selection algorithm by focusing on the dependent view stream.

As described above it is possible to avoid the processing executed by focusing on the dependent view stream by automatically calculating the ID of the dependent view stream from the ID of the base view stream.

The version number represents a version number of the xxxx.mpls . The version number contains four numerals. For example 0240 representing a 3D Spec version is set in the PlayList file for a 3 D reproduction.

The PlayList start address represents the leading end address of the PlayList in the unit of a relative byte number starting from the leading end byte of the PlayList file.

The PlayListMark start address represents the leading end address of the PlayListMark in the unit of a relative byte number starting from the leading end byte of the PlayList file.

The ExtensionData start address represents the leading end address of the ExtensionData in the unit of a relative byte number starting from the leading end byte of the PlayList file.

In the AppInfoPlayList parameters for controlling reproduction of the PlayList such as a reproduction limitation are stored.

In the PlayList parameters relating to the main path or the subsidiary path as described with reference to are stored.

In the PlayListMark mark information of the PlayList i.e. information on a jump destination or jump point in a user operation or command for instructing a chapter jump or the like is stored.

The field view type represents whether the base view video stream of which reproduction is managed by the PlayList is an L view stream or an R view stream. The field view type may represent whether the dependent view video stream is an L view stream or an R view stream.

A value of the 3D PL type of 01 represents a PlayList for the B D1 reproduction out of the 3 D reproduction types.

A value of the 3D PL type of 10 represents a PlayList for B D2 reproduction out of the 3 D reproduction types.

For example a value of the 3D PL type is 01 or 10 3 D PlayList information is registered in the ExtensionData of the PlayList file. For example a file name of a clpi file corresponding to the clip of the dependent view video stream is registered in the example of 00002.clpi as the 3 D PlayList information.

A value of the view type of 0 represents that the base view video stream is the L view stream when the 3 D reproduction is executed. When the 2 D reproduction is executed it represents that the base view video stream is the AVC video stream.

By describing the view type in the PlayList file the reproducer is allowed to identify whether the base view video stream is the L view stream or the R view stream.

For example when the video signal is output to the display device using the HDMI cable the reproducer is demanded to output by distinguishing between the L view signal and the R view signal.

By identifying whether the base view video stream is the L view stream or the R view stream the reproducer is allowed to output the L view and R view signals by distinguishing therebetween.

The controller executes a control program that has been previously prepared and controls all operations of the reproducer .

For example the controller controls the disc driver to read the PlayList file for the 3 D reproduction. The controller reads the main TS and the subsidiary TS based on the ID registered in the STN table and supplies them to the decoder unit .

The disc driver reads data from the optical disc according to the control of the controller and outputs the read data to the controller the memory or the decoder unit .

The memory appropriately stores data or the like demanded by the controller to execute various processes.

The local storage includes for example an HDD Hard Disk Drive . The dependent view video streams or the like downloaded from the server are recorded in the local storage . The streams recorded in the local storage are also appropriately supplied to the decoder unit .

The Internet interface performs communication to the server via a network under the control of the controller and supplies the data downloaded from the server to the local storage .

From the server data for updating the data recorded in the optical disc are downloaded. It is possible to implement the 3 D reproduction of different contents from those of the optical disc by allowing the downloaded dependent view video stream to be used together with the base view video stream recorded in the optical disc . When the dependent view video stream is downloaded the contents of the PlayList are also appropriately updated.

The decoder unit decodes the streams supplied from the disc driver or the local storage and outputs the video signal obtained through the decoding to the display device . The audio signal is also output to the display device via a predetermined path.

The manipulation input unit includes an input device such as a button a key a touch panel a jog dial and a mouse or a receiver unit which receives a signal of infrared or the like transmitted from a predetermined remote commander. The manipulation input unit detects a user s manipulation and supplies a signal indicating the content of the detected manipulation to the controller .

The PID filter identifies whether the TS supplied from the disc driver or the local storage is a main TS or a subsidiary TS based on the ID of the stream or the PID of the packet included in the TS. The PID filter outputs the main TS to the buffer and also outputs the subsidiary TS to the buffer .

The PID filter sequentially reads the packets of the main TS stored in the buffer and distributes them based on their PIDs.

For example the PID filter outputs the packets of the base view video stream included in the main TS to the B video buffer and also outputs the packets of the dependent view video stream to the switch .

In addition the PID filter outputs the packets of the base IG stream included in the main TS to the switch and also outputs the packets of the dependent IG stream to the switch .

The PID filter outputs the packets of the base PG stream included in the main TS to the switch and also outputs the packets of the dependent PG stream to the switch .

As described with reference to the base view video stream the dependent view video stream the base PG stream the dependent PG stream the base IG stream and the dependent IG stream may be multiplexed in the main TS.

The PID filter sequentially reads the packets of the subsidiary TS stored in the buffer and distributes them based on their PIDs.

For example the PID filter outputs the packets of the dependent view video stream included in the subsidiary TS to the switch .

In addition the PID filter outputs the packets of the base IG stream included in the subsidiary TS to the switch and also outputs the packets of the dependent IG stream to the switch .

The PID filter outputs the packets of the base PG stream included in the subsidiary TS to the switch and also outputs the packets of the dependent PG stream to the switch .

As described with reference to the dependent view video stream may be included in the subsidiary TS. In addition as described with reference to the base PG the dependent PG stream the base IG stream and the dependent IG stream may be multiplexed in the subsidiary TS.

The switch outputs the packets of the dependent view video stream supplied from the PID filter or the PID filter to the D video buffer .

The switch sequentially reads the packets of the base view video stored in the B video buffer and the packets of the dependent view video stored in the D video buffer according to the timing information which defines the decoding timing. For example the same timing information is set in the packet which stores data on the picture where the base view video exists and the packet which stores data on the picture of the corresponding dependent view video.

The switch outputs the packets read from the B video buffer or the D video buffer to the video decoder .

The video decoder decodes the packets supplied from the switch and outputs data of the dependent view video or the base view video obtained by decoding the packets to the switch .

The switch outputs the data obtained by decoding the packets of the base view video to the B video plane generator unit and also outputs the data obtained by decoding the packet of the dependent view video to the D video plane generator unit .

The B video plane generator unit generates a plane of the base view video based on the data supplied from the switch and outputs the plane to the synthesizing unit .

The D video plane generator unit generates a plane of the dependent view video based on the data supplied from the switch and outputs the plane to the synthesizing unit .

The switch outputs the packets of the base IG stream supplied from the PID filter or to the B IG buffer .

The B IG decoder decodes the packets of the base IG stream stored in the B IG buffer and outputs the data obtained by decoding the packets to the B IG plane generator unit .

The B IG plane generator unit generates a plane of the Base IG based on the data supplied from the B IG decoder and outputs the plane to the synthesizing unit .

The switch outputs the packets of the dependent IG stream supplied from the PID filter or to the D IG buffer .

The D IG decoder decodes the packets of the dependent IG stream stored in the D IG buffer and outputs the data obtained by decoding the packets to the D IG plane generator unit .

The D IG plane generator unit generates a plane of the dependent IG based on the data supplied from the D IG decoder and outputs the plane to the synthesizing unit .

The switch outputs the packets of the base PG stream supplied from the PID filter or to the B PG buffer .

The B PG decoder decodes the packets of the base PG stream stored in the B PG buffer and outputs the data obtained by decoding the packets to the B PG plane generator unit .

The B PG plane generator unit generates a plane of the base PG based on the data supplied from the B PG decoder and outputs the plane to the synthesizing unit .

The switch outputs the packets of the dependent PG stream supplied from the PID filter or to the D PG buffer .

The D PG decoder decodes the packets of the dependent PG stream stored in the D PG buffer and outputs the data obtained by decoding the packets to the D PG plane generator unit .

The D PG plane generator unit generates a plane of the dependent PG based on the data supplied from the D PG decoder and outputs the plane to the synthesizing unit .

The synthesizing unit synthesizes the plane of the base view video supplied from the B video plane generator unit the plane of the Base IG supplied from the B IG plane generator unit and the plane of the base PG supplied from the B PG plane generator unit by sequentially overlapping them to generate a plane of the base view.

The synthesizing unit synthesizes the plane of the dependent view video supplied from the D video plane generator unit the plane of the dependent IG supplied from the D IG plane generator unit and the plane of the dependent PG supplied from the D PG plane generator unit by sequentially overlapping them to generate a plane of the dependent view.

The synthesizing unit outputs the data of the plane of the base view and the data of the plane of the dependent view. The video data output from the synthesizing unit is output to the display device to perform the 30D display by alternately displaying the plane of the base view and the plane of the dependent view.

The video encoder includes the same configuration as that of the MVC encoder of . The video encoder generates the base view video streams and the dependent view video streams by encoding a plurality of video data according to the H.264 AVC MVC and outputs them to the buffer .

The audio encoder outputs the data obtained by encoding the input audio streams to the buffer . To the audio encoder the audio streams recorded in the disc together with the base view video streams and the dependent view video streams are input.

The data encoder encodes various data such as the PlayList file described above in addition to the video and audio data and outputs the data obtained by the encoding to the buffer .

For example the data encoder sets 8 as a value of the application type of the clip information file corresponding to the subsidiary TS including the dependent view video stream. The application type 8 means that the application executing the process using the dependent view video stream is an application which executes the 3 D reproduction.

In addition the data encoder sets in the PlayList whether the dependent view video stream is multiplexed in the same TS as that of the base view video stream and the SubPath type corresponding to the recording location. The recording location of the dependent view video stream is the optical disc or the local storage .

Furthermore when in the side of the reproducer the dependent view stream is calculated based on the ID of the base view stream the data encoder sets a value of x used in that calculation in a predetermined location such as STN table 

The data encoder sets in the PlayList file the view type representing whether the base view video stream is L view stream or the R view stream according to the encoding of the video encoder .

The multiplexer unit multiplexes the video data the audio data and the data stored in each buffer except for the stream together with the synchronization signal and outputs them to the error correction coding ECC unit .

The error correction coding ECC unit adds the error correction code to the data multiplexed by the multiplexer unit .

The modulator unit modulates the data supplied from the error correction coding ECC unit and outputs the modulation result. The output of the modulator unit is software recorded in the optical disc that can be reproduced by the reproducer .

The software manufacturing processing unit having such a configuration is installed in the recording device.

A mastering process is performed by the pre mastering processing unit for the recording signal generated by the software manufacturing processing unit to generate a signal having a format to be recorded in the optical disc . The generated signal is supplied to the disc recording unit .

In the recording disc fabrication unit a disc made of glass or the like is prepared and a recording material made of a photoresist or the like is coated thereon. As a result a recording disc can be manufactured.

In the disc recording unit a laser beam is modulated according to the recording signal supplied from the pre mastering processing unit and then illuminated onto the photoresist. As a result the photoresist on the disc is exposed according to the recording signal. Then pits on the disc are formed by developing this disc.

In the metal disc fabrication unit a process such as an electrocasting is performed to manufacture a metal disc to which the pits on the glass disc are transferred. Furthermore a metal stamper is formed on the metal disc which is used as a molding die.

In the mold processing unit a material such as PMMA acryl or PC polycarbonate is injected to the molding die through injection and then stabilized. Otherwise a material such as 2P ultraviolet cured resin is coated on the metal stamper and then cured by illuminating an ultraviolet ray. As a result pits of the metal stamper can be transferred to the replica made of resin.

In the film forming processing unit a reflection film is formed on the replica through deposition or sputtering. Otherwise the reflection film is formed on the replica through a spin coat.

In the post processing unit inner and outer diameters are processed for this disc and necessary processes such as attaching two discs are performed. The disc is inserted into a cartridge after forming a label or hub. As a result it is possible to manufacture an optical disc where the data that can be reproduced by the reproducer are recorded.

A series of the processes described above may be executed by hardware or software. When a series of the processes are executed by software a program functioning as the software is installed from a program recording medium in a computer or a general purpose personal computer or the like integrated into dedicated hardware.

The CPU Central Processing Unit the ROM Read Only Memory and the RAM Random Access Memory are connected to each other via a bus .

Furthermore the input output interface is connected to the bus . An input unit such as a keyboard or a mouse and an output unit such as a display or a loudspeaker are connected to the input output interface . Moreover a storage unit such as a hard disc or a non volatile memory a communication unit such as a network interface and a drive for driving the remote medium are connected to the bus .

In the computer constructed as described above the CPU performs a series of the aforementioned processes for example by loading the program stored in the storage unit to the RAM via the input output interface and the bus and executing the program.

The program executed by the CPU is installed in the storage unit by recording it for example in a remote medium or providing it via a wired or wireless transmission medium such as a local area network LAN the Internet or a digital broadcasting.

In addition the program executed by the computer may be processed in a time series according to the sequence described herein or may be processed at a necessary timing in parallel or when it is called.

The embodiments of the invention are not limited to the aforementioned examples but may be variously changed without departing from the scope and spirit of the present invention.

