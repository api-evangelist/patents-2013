---

title: Electronic device and method for managing names of electronic device
abstract: In a method for naming an electronic device, a hash table including indices and corresponding character strings is preset. The electronic device is controlled to enter into a searchable state, and inserts a default name of the electronic device in a searchable device list. A shaking angle of the electronic device is calculated according to detected coordinate values acquired from a gravity sensor, when the electronic device is shaking in the searchable state and the default name needs to be changed. A hash value is calculated using the shaking angle, a UNIX timestamp, a number of the indices in the hash table, and a predetermined formula. The method further determines an index that is the same as the hash value, determines a character string corresponding to the determined index, and renames the electronic device using the determined character string.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09043335&OS=09043335&RS=09043335
owner: Chi Mei Communication Systems, Inc.
number: 09043335
owner_city: New Taipei
owner_country: TW
publication_date: 20130417
---
Embodiments of the present disclosure relate to management technology and particularly to an electronic device and method for managing names of the electronic device.

Multiple electronic devices may be connected to exchange data. For example the electronic devices may establish a data connection e.g. a BLUETOOTH connection a WIFI connection to transmit files. Before establishing the data connection an electronic device needs to search for a target electronic device and sends a connection request to the target electronic device. Generally the electronic device has to find the target electronic device in a searchable device list. However the searchable device list may have many device names. That is it is inefficient for a user of the electronic device to find the target electronic device to establish the data connection. Therefore an efficient method for managing names of electronic device is desired.

All of the processes described below may be embodied in and fully automated via functional code modules executed by one or more general purpose electronic devices or processors. The code modules may be stored in any type of non transitory computer readable medium or other storage device. Some or all of the methods may alternatively be embodied in specialized hardware. Depending on the embodiment the non transitory computer readable medium may be a hard disk drive a compact disc a digital video disc a tape drive or other suitable storage medium.

The naming system recognizes a user gesture e.g. a shaking gesture and generates a corresponding naming parameter when the electronic device needs to establish a data connection with other electronic devices and names renames the electronic device using the naming parameter thereby making a new name of the electronic device easily found by other electronic devices.

For example it is assumed that the electronic device needs to connect to an electronic device A a user of the electronic device may hold the electronic device to perform a predetermined gesture such as shaking the electronic device . The naming system may recognize the performed gesture and then rename the electronic device . For example the electronic device may be renamed using one of preset names such as I am Hank or Hey I am here. Then the electronic device A may recognize the electronic device according to the new name.

In one embodiment the electronic device may be a mobile phone a tablet computer a personal digital assistant a notebook computer or any other device. In one embodiment the naming system may include computerized instructions in the form of one or more programs that are executed by the at least one processor and stored in the storage device . The storage device stores one or more programs such as operating systems applications of the electronic device and various kinds of data such as images. In some embodiments the storage device may be an external storage card such as a memory stick a smart media card a compact flash card a secure digital card or any other type of memory storage device.

The display device may be a liquid crystal display LCD or a touch sensitive display a capacitive touch panel for example. The gravity sensor may be used to measure a tilt angle vibration dynamic distance and speed and other parameters.

In step S the setting module sets a hash table and stores the hash table in the storage device . As shown in an exemplary hash table includes a plurality of indices and corresponding predetermined character strings. Each of the indices corresponds to a character string. In some embodiments the character strings are used to name the electronic device .

For example in an index corresponds to a character string I am Hank an index corresponds to a character string Hi are you looking for me I am here. 

In other embodiments the setting module predetermines the character strings according to user input and presets formats or limitations of the character strings. For example as shown in the setting module may insert specified characters e.g. or before and or after a character string I am Tom. 

In step S the control module controls the electronic device to enter into a searchable state to allow the electronic device to be searched by other electronic devices hereinafter the other electronic devices are referred to as a target electronic devices . For example when the electronic device is in the searchable state the target electronic device may find the electronic device and request a wireless connection e.g. BLUETOOTH WIFI with the electronic device .

In some embodiments the control module inserts a default name of the electronic device in a searchable device list. For example the default name of the electronic device may be an original name preset when the electronic device is manufactured such as ABC123 where ABC represents a trademark of the electronic device and 123 represents a model number. The default name also may be preset by a user of the electronic device such as Hank for example.

In step S the determination module detects whether the electronic device is shaking using the gravity sensor . If the electronic device is shaking the procedure goes to step S. If the electronic device is not shaking step S is repeated.

In some embodiments shaking the electronic device is a predetermined gesture to invoke a renaming procedure to update the default name of the electronic device when the electronic device is in the searchable state. In other embodiments before invoking the renaming procedure a prompt message is outputted to prompt the user in step S.

In step S the determination module outputs the prompt message to prompt the user whether the default name of the electronic device needs to be changed receives user input and determines whether the default name of the electronic device needs to be changed according to the user input. For example the prompt message may be displayed on the display device .

If the default name of the electronic device needs to be changed the procedure goes to step S. If the default name of the electronic device does not need to be changed the procedure ends.

In step S the calculation module calculates a shaking angle of the electronic device according to detected coordinate values acquired from the gravity sensor . As shown in a 3D coordinate system based on the center of the electronic device is constructed. Axes of X Y and Z in are merely one example and may be changed according to user requirements. In other embodiments a 2D coordinate system may be constructed on the electronic device . In some embodiments the shaking angle may be calculated according to a formula of arctan Y X 180 represents the shaking angle X and Y represent the detected coordinate values. In some embodiments coordinate values of X and Y are selected to calculate the shaking angle. For example x 0.2 y 7.4 3.14 arctan 7.4 0.2 180 3.14 88.5 .

In step S the acquisition module acquires a UNIX timestamp from the electronic device . In some embodiments the acquisition module may acquire the UNIX timestamp of the electronic device using application programming interface API functions.

In step S the calculation module calculates a hash value using the shaking angle the UNIX timestamp a number of the indices in the hash table and a predetermined formula. The predetermined formula is V abs T mod N where V represents the determined hash value T represents the UNIX timestamp represents the shaking angle and N represents the number of the indices in the hash table.

For example T 1334204567 88.45 N 100 V abs 1334204567 88.45 mod 100 118010393951.15 mod 100 51.15 and then an integer 51 is determined to be the hash value.

In step S the naming module determines an index that is the same as the calculated hash value and determines a character string corresponding to the determined index. For example as shown in the determined character string that corresponds to the hash value 51 is I am Tom . 

In step S the naming module renames the electronic device using the determined character string. Accordingly by utilizing the above mentioned steps the electronic device may be renamed easily by performing the predetermined gesture when the electronic device is in the searchable state and the target electronic devices may find the electronic device quickly.

It should be emphasized that the above described embodiments of the present disclosure particularly any embodiments are merely possible examples of implementations set forth for a clear understanding of the principles of the disclosure. Many variations and modifications may be made to the above described embodiment s of the disclosure without departing substantially from the spirit and principles of the disclosure. All such modifications and variations are intended to be included herein within the scope of this disclosure and the present disclosure and protected by the following claims.

