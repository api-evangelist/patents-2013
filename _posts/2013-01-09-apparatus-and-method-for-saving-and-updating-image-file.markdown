---

title: Apparatus and method for saving and updating image file
abstract: An image saving apparatus may extract an object from a photographed picture, and may store position information. The image saving apparatus may selectively perform image processing of each object using the position information and may provide a user with a dynamic image in which a change in the photograph range is considered.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09324176&OS=09324176&RS=09324176
owner: Samsung Display Co., Ltd.
number: 09324176
owner_city: Yongin-si
owner_country: KR
publication_date: 20130109
---
This application claims priority from and the benefit of Korean Patent Application No. 10 2012 0030546 filed on Mar. 26 2012 which is hereby incorporated by reference for all purposes as if fully set forth herein.

Exemplary embodiments of the present invention relate to storing an image file and more particularly to updating a photographed picture using information about a current time.

A related image saving scheme may store in a buffer image data that is acquired using a camera mounted in or on a mobile phone and may store the stored image data as an image file.

A related image synthesizing scheme may generate a static image by synthesizing the stored image data with a different image. The related image synthesizing scheme may perform synthesis by classifying separate images into multiple layers and by arranging each layer at a selected position.

In addition according to the related art global positioning system GPS position information and additional data such as a time when a picture is photographed a text and the like may be added to a static image and thereby may be stored as an image file. Additional information about individual objects may not be stored. Accordingly there are some constraints on applying an individual image synthesis scheme with respect to each object.

Exemplary embodiments of the present invention provide an apparatus to save and update an image file.

Exemplary embodiments of present invention also provide a method for saving and updating an image file.

Additional features of the invention will be set forth in the description which follows and in part will be apparent from the description or may be learned by practice of the invention.

An exemplary embodiment of the present invention discloses a method for storing and updating an image file including extracting a first object from the image file determining first position information of the first object according to a location of the image of the image file grouping the first object into a first layer according to the first position information determining an updated condition of the first position information of the first object generating a second image according to the updated condition of the first position information in a second layer storing the first layer and the second layer.

An exemplary embodiment of the present invention also discloses an apparatus to store an updated image file including an object extractor to determine a first object in the image file a position information adder to determine a first location of the first object and to receive updated condition information about the first location of the first object a grouping unit to group the first object into a first layer according to the location of the first object and an image processing unit to generate a second layer including a second image according to the updated condition of the location of the first object.

An exemplary embodiment of the present invention also discloses a method for storing a dynamic image file including receiving an image file extracting a first object from the image file determining a first position of the first object grouping the first object into a first layer according to the first position determining if the first object is a dynamic object if the first object is a dynamic object receiving updated condition information of the first object processing the image of the first object according to the updated condition storing the first layer according to the processing of the image of the first object.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed. Other features and aspects will be apparent from the following detailed description the drawings and the claims.

Exemplary embodiments are described more fully hereinafter with reference to the accompanying drawings in which embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure is thorough and will fully convey the scope of the invention to those skilled in the art. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like reference numerals in the drawings denote like elements.

It will be understood that when an element is referred to as being on or connected to another element or layer it can be directly on or directly connected to the other element or layer or intervening elements or layers may be present. In contrast when an element is referred to as being directly on or directly connected to another element or layer there are no intervening elements or layers present. It will be understood that for the purposes of this disclosure at least one of X Y and Z can be construed as X only Y only Z only or any combination of two or more items X Y and Z e.g. XYZ XYY YZ ZZ .

The object extractor may be configured to extract an object from the generated image file. The object extractor may extract an outline of the image from the image file and may extract an object using the extracted outline. For example if the camera unit generates an image file by photographing a landscape including a tree a mountain a cloud a building a person and the like each of the tree the mountain the cloud the building the person and the like may be extracted as a different object.

The position information adder may be configured to add position information to the extracted object. The position information may include information about a distance from the camera unit to a photographing target for example a tree a mountain a cloud a building a person and the like corresponding to each object.

The position information may be generated using a focal distance of the camera unit . The camera unit may divide a screen into a plurality of zones and may calculate a focal distance of each of the zones.

For example the camera unit may calculate a first focal distance with respect to a first zone and may calculate a second focal distance with respect to a second zone. The position information adder may calculate a distance from a photographing target that is positioned in the first zone using the first focal distance with respect to the first zone and may add the calculated distance as position information of an object corresponding to the photographing target.

The position information may include information about a geographical position of a photographing target corresponding to each object and may be generated using a GPS signal. The GPS module may receive a GPS signal and calculate coordinates of the image saving apparatus according to the GPS signal.

Position information about each object may be stored for all the objects that are included in a screen.

The image saving apparatus may recognize a direction of the image saving apparatus using a gyro sensor or a terrestrial magnetism sensor. The image saving apparatus may determine a position of the image saving apparatus using GPS information.

The image saving apparatus may calculate a geographical position of each object based on a distance from the image saving apparatus to each object that is calculated using a position of the image saving apparatus a direction and a focal distance of the image saving apparatus . The image saving apparatus may store the calculated distance by associating the calculated distance with each corresponding object.

The position information adder may receive position information about each object via the communication unit . The configuration of receiving position information about each object will be described with reference to .

Referring to a screen is a photographing target. A user may control the camera unit to photograph the screen including building and building a mountain and an iron tower by manipulating the image saving apparatus .

Referring to a map may be configured to display geographical positions of photographing targets. The building and the building may be positioned closest to a user and a mountain may be positioned at a point farther away from the building and the building . An iron tower may be positioned farthest away from the user .

Referring to the position information adder may receive the map about a photographing target area via the communication unit . The position information adder may identify a photographing target corresponding to each object using the map .

For example the image saving apparatus may estimate a position of each photographing target displayed on a screen based on a distance from the image saving apparatus to each photographing target. The distance from the image saving apparatus to each photographing target may be calculated based on position information direction information and a focal distance of the image saving apparatus .

The image saving apparatus may map each photographing target on the map . For example if a position of a photographing target is similar to a position of a reference building on the map the image saving apparatus may identify the photographing target as the reference building on the map . The accuracy of an estimated position may be low but the accuracy of a position on the map may be relatively high. The image saving apparatus may increase the accuracy of a position by updating a position of a photographing target with a position of a reference building on the map instead of using the estimated position.

Referring to and the position information adder may identify from the map the respective objects for example the building and the building the mountain and the iron tower that are positioned on the screen corresponding to a photographing target. The position information adder may identify from the map coordinates of each of the identified objects.

The position information adder may identify a direction of the image saving apparatus using a compass an acceleration sensor a gyroscope etc. A direction and a distance of each object that is positioned on the screen corresponding to the photographing target may be calculated based on the direction and position of the image saving apparatus . The position information adder may verify a location of the image saving apparatus using the GPS module and may calculate coordinates of a photographing target corresponding to each object based on the calculated direction and distance.

The grouping unit may group extracted objects as at least one layer based on position information. The grouping as a layer of objects that are extracted from a screen of will be described with reference to .

Referring to and the grouping unit may group objects based on a distance from the camera unit to a photographing target corresponding to each object. Building and building may be disposed closest to the camera unit and may be included in a first layer a mountain positioned behind the building and the building may be included in a second layer and an iron tower disposed behind the mountain may be included in a third layer .

The storage unit may add layer information and position information about each object to information about each object and stores the information in an image file.

The image processing unit may select at least one layer from among a plurality of layers for example the first layer the second layer and the third layer and may perform image processing of objects that are included in the selected layer. For example to express a situation in which the iron tower is on fire the image processing layer may select the third layer that includes the iron tower . The image processing unit may perform image processing of the third layer or the iron tower to be suitable for the situation where the fire has occurred. The storage unit may store the image processed third layer or iron tower in the image file.

The image saving apparatus may receive an additional layer from an external server. A site such as live virtual earth may provide a server that supports open application programming interface API . The image saving apparatus may receive real time map data information that is provided by the server using open API. Additional information about various types of objects on a map may be received in real time.

For example with respect to a measurement result of Seoul Korea the image saving apparatus may receive from a geographic information system GIS map site information about Seoul Korea information about a corresponding topography of Seoul Korea and information that may be used to extract an image for an additional layer.

The image processing unit may add to an image file an additional layer including at least one additional object for example cloud and cloud . An object of an image file and a layer of the image file may be modified. An object or a layer may be added to the image file or subtracted therefrom.

Layer layer and layer of may correspond to the first layer the second layer and the third layer of respectively. Objects and object object and object of may correspond to the building and the building the mountain and the iron tower of respectively. In to express a situation in which it is raining at the location of the the additional layer including objects indicating the clouds and cloud may be added to the image file. The storage unit may store the image file in which the additional layer is added.

The image saving apparatus may synthesize an object within an image and another object or may convert the object to the other object. For example if a waterfall is included in a single image the waterfall and a background screen may be stored as separate individual objects. A user may select to change a background screen of the waterfall into a background screen of a target image. The image saving apparatus may delete from the target image the background screen that is stored as a separate object and may insert into the target image an object corresponding to the background screen of the waterfall. The image saving apparatus may store position information of the deleted background screen as position information of the background screen inserted into the target image. The background screen of the waterfall may be the same as position information of the deleted background screen and may be synthesized with other objects within the target image.

The image processing unit may access an image information server via the communication unit . The communication unit may receive from the image information server information about a photographing target area and the image processing unit may perform image processing of the image file by referring to information about the photographing target area.

For example in a screen photographed by the camera unit may be an image photographed of the photographing target area one year earlier. If a fire occurs in the iron tower the image of the iron tower from one year ago may be completely different from an image of the iron tower that is currently on fire or after the fire.

The communication unit may receive from the image information server a photo of the iron tower that is on fire. The image processing unit may perform image processing of the screen photographed in . The communication unit may extract the iron tower from the third layer and replace the corresponding iron tower included in the third layer with an image of the iron tower on fire or with an image of the fire damage caused to the iron tower by the fire.

The communication unit may receive information about a weather status of a photographing target area from the image information server . Although it may be raining in the photographing target area the image of the photographic target area may not depict rain in a picture taken one year earlier. The communication unit may receive from the image information server the additional layer to depict rain in the photographic target area. The image processing unit may perform image processing of inserting into an image file the additional layer to depict rain.

The image processing unit may exchange at least one layer among the first layer the second layer and the third layer included in the image with another layer. For example the image processing unit may exchange the third layer including the iron tower with a layer including a cloud. In this case the image saving apparatus may receive a layer for exchange from the external server.

The image saving apparatus may store the photograph range of an image in the image file. If the image saving apparatus receives an object to be synthesized with the image from the image information server the image saving apparatus may select the object to be synthesized with the corresponding image using the photograph range of the image.

In a photograph range depicts the photograph range in which the camera unit may be capable of taking a picture. Object object and object are positioned within the photograph range .

Among objects that are included in a measured photograph range may be determined according to multiple parameters. For example referring to the parameters Y low X low Y high and X high may determine the measured photograph range . Y low may be determined to be a position of an object closest to a photographer X low may be determined to be a position of a leftmost positioned object object from a viewpoint of the photographer X high may be determined to be a position of as a rightmost positioned object object from a viewpoint of the photographer and Y high may be determined to be an object object that is farthest from the photographer.

Referring again to the communication unit may transmit the photograph range and may transmit the measured photograph range to the image information server . The communication unit may receive from the image information server a map of the photograph range information about a weather state of the photograph range and the like. The communication unit may receive an object corresponding to the photograph range from the image information server . The received object may correspond to an object in which a change has occurred since the photograph was taken. For example if a new building is built in the photograph range since the photograph was taken the object received by the image saving apparatus may be an object indicating the newly built building. The image saving apparatus may reflect that the building has been built by inserting the received object in the photographed image.

Referring to the image processing unit may perform dynamic image processing of an acquired image by considering a change in a state of the photograph range.

Referring to and the image processing unit may extract reference point reference point reference point reference point reference point and reference point from a stored image and may determine respective corresponding position corresponding position corresponding position corresponding position corresponding position and corresponding position of the extracted reference point reference point reference point reference point reference point and reference point on a map .

The image processing unit may map an object corresponding to a building on the map by referring to the corresponding position corresponding position corresponding position corresponding position corresponding position and corresponding position of the extracted reference point reference point reference point reference point reference point and reference point of the screen .

The image processing unit may divide a stored image into a reference number of areas and may determine center points of divided areas as reference points. For example the image processing unit may divide the stored image on screen into two three four nine etc. images. Center points of the divided images may be determined to be the reference point reference point reference point reference point reference point and reference point of the screen . A position of an object disposed on a reference point may be used to determine a position of the reference point.

The image processing unit may extract a reference number of representative objects from a stored image and may determine a position of an extracted object to be a reference point.

Referring again to the communication unit may receive information about the photograph range from the image information server in the form of map . Information about the photograph range may include information about current weather in the photograph range information about a new structure in the photograph range etc.

The communication unit may receive from the image information server information about the size or shape of a newly built structure in the photograph range of the screen or may receive a picture photographed from the structure. The communication unit may receive coordinates of the new structure from the image information server . Referring to the image processing unit may synthesize an object corresponding to a building and an object corresponding to the newly built structure on the map by referring to the coordinates of the structure .

Referring to and the image processing unit may synthesize an object corresponding to the structure into an image including an object corresponding to the building .

The image processing unit may insert the object corresponding to the structure into the same layer as the object corresponding to the building . The image processing unit may insert into the image an additional layer including the object corresponding to the structure which may have been newly built since the picture was taken.

Referring to a photographing point in time of the image may be different from a current point in time. Therefore even though the image does not accurately reflect the current image of the photograph range the image saving apparatus may perform image processing by receiving information about the photograph range from the image information server and reflecting a change in the photograph range in the image .

The communication unit may receive information about weather of the photograph range from the image information server . The communication unit may additionally receive from the image information server an image and objects to perform image processing of the corresponding weather. The image processing unit may perform image processing of the image based on information about the weather of the photograph range.

For example if a screen is obtained by taking a picture of clear sky the image saving apparatus may receive from the image information server an object that indicates the current weather at the location the picture was taken. For example the image saving apparatus may receive from the image information server an object indicating a cloud and may synthesize the received object with the stored clear sky.

Although depicts image processing of an image by reflecting a change in the photograph range exemplary embodiments are not limited thereto. Image processing may occur according to a user selection regardless of a change in the photograph range. For example image processing may be performed as if it is snowing in the photograph range even though it is raining at the photograph range. A famous structure such as Nam dae moon the Statue of Liberty and the like may be synthesized with respect to a reference point of the photographed image.

The image saving apparatus may also receive from the image information server a parameter used to perform image processing on a corresponding image. The image saving apparatus may receive from the image information server a parameter used to decrease the brightness of a screen. By decreasing the brightness of the screen the image saving apparatus may change an image photographed during the day to appear as if the image is was photographed at night.

The image saving apparatus may delete an object corresponding to the sun from the image photographed during the day and may receive an object indicating the moon from the image information server and then synthesize the received object in the image photographed during the day.

An image file may include information about a plurality of layers for example a first layer a second layer and a third layer . The image file may include information about a satellite picture of an actual object of each layer. Here the information may be updated by reflecting a change in a natural environment weather and the like in the photograph range. The image file may include information about whether a GPS signal is received and information about a GPS position value. Although illustrates a structure of an image file aspects need not be limited thereto such that the structure of the image file may differ from the structure depicted in .

Information about the first layer may include information about a first object a second object and a third object that are included in the first layer . Information about an object included in the first layer may include information about an image of the object and information data about the object. Information about the image of the object may include an image of the object at a photographing point in time and may be stored in a format of joint photographic experts group JPEG . Information about the data of the object may include a weather condition when the object is photographed a photographing time of the object a distance and angle between the camera unit and the object a GPS position value of the object photographing information and information a dynamic object indicator to indicate whether the object is static or dynamic.

In operation the image saving apparatus may extract an object from the photographed picture. For example a tree a mountain a cloud a building a person and the like included in the picture may be individual objects.

In operation the image saving apparatus may add position information to the extracted object. The position information may include information about a distance from the camera unit to a photographing target. For example if the picture photographed in operation includes a tree a mountain a cloud a building a person and the like the position information may include information about a distance from the camera unit to the tree the mountain and the building. The position information may also be a reference distance from the camera unit to the tree the mountain and the building and may also be a relative distance that is obtained by comparing a distance from the camera unit to the tree and a distance from the camera unit to the mountain.

The image saving apparatus may generate distance information using a focal distance of the camera. In operation if the picture is taken the camera may divide a screen and focus on each divided portion. The image saving apparatus may estimate a distance from each portion using a focal distance with respect to a portion. In operation the image saving apparatus may determine an object disposed in a portion of the screen of the camera and may generate information about a distance from the camera to the object according to the position information about the object.

The position information may include information about a geographical position of a photographing target corresponding to each object and may include information about coordinates on a map. The position information may be generated using a GPS signal.

In operation the image saving apparatus may group extracted objects as a layer based on position information.

The image saving apparatus may group as a first layer objects corresponding to a photographing target that are positioned to be closest to the camera and may group as a second layer objects corresponding to a photographing target that are positioned to be further away from the camera than the objects in the first layer.

The image saving apparatus may divide a photographed region into a plurality of zones. The image saving apparatus may group as a first layer objects corresponding to a photographing target that are positioned in a first zone among the plurality of zones and may group as a second layer objects corresponding to a photographing target that are positioned in a second zone.

In operation the image saving apparatus may select at least one layer from among a plurality of layers and may perform image processing of objects that are included in the selected layer. The image saving apparatus may add an additional layer to the image and store the image. The additional layer may include at least one additional object.

In operation the image saving apparatus may add to each object layer information and position information about each object and store the added information in the image file. Individual information about each object may be added to the image file. Additional image processing using the stored image file may be performed. For example an object may be inserted into the stored image file or a layer may be added to the image file. The added layer may correspond to a background of an image and may be used to indicate a change in weather at the location of the photograph a new building and the like.

The exemplary embodiments according to the present invention may be recorded in non transitory computer readable media including program instructions to implement various operations embodied by a computer. The non transitory computer readable medium may include alone or in combination with the program instructions data files data structures and the like. The non transitory computer readable medium and program instructions may be those specially designed and constructed for the purposes of the present invention or they may be of the kind well known and available to those having skill in the computer software arts.

According to exemplary embodiments of the present invention it may be possible to store additional information about individual objects that are included in an image file.

According to exemplary embodiments of the present invention it may be possible to provide a dynamic picture by performing image processing of a picture based on neighboring environmental conditions.

It will be apparent to those skilled in the art that various modifications and variation can be made in the present invention without departing from the spirit or scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

