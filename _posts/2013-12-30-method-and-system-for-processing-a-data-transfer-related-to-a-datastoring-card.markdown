---

title: Method and system for processing a data transfer related to a data-storing card
abstract: In a method for processing a data transfer, an electronic device accesses card-specific data and a card account number from a data-storing card. The electronic device generates a device-generated authentication number which is associated with the data transfer, and which is transmitted, together with the card account number and the card-specific data, to a network platform. The network platform compares an inputted authentication number from a portable device and the device-generated authentication number, and transmits to-be-transferred data to the portable device when the authentication numbers correspond with each other.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09021571&OS=09021571&RS=09021571
owner: Yi-Fen Chou
number: 09021571
owner_city: Keelung
owner_country: TW
publication_date: 20131230
---
The invention relates to a method and a system for processing a data transfer more particularly a method and a system for processing a data transfer which is related to data stored in a data storing card.

Nowadays pocket sized physical cards that are capable of holding information therein e.g. a magnetic strip card a smart card or the like have been utilized for providing of many functions such as electronic transaction services provided by a vendor and the like. Accordingly the information held in a smart card may include personal information associated with a holder of the smart card authentication credential a balance of an electronic purse application for performing specific functions or the like.

The mobile device is also widely used in conjunction with such physical cards for performing these functions. For example a smart card may be coupled to the mobile device through one of the SIM card slot and the SD card slot for contact type cards or through a wireless module that supports near field communication NFC Radio frequency identification RFID for contactless type cards thereby allowing the mobile device to access the information stored in the smart card.

However in most cases different vendors or banks issue their own cards. For a user that employs services from many vendors banks he or she inevitably needs to carry many physical cards and the SIM card slot and or the SD card slot need to be frequently coupled to the physical cards which may lead to inconvenience. It is thus desirable to reduce the number of physical cards that have to be carried without compromising the convenience brought about by the functions associated with the physical cards.

Therefore one object of the present invention is to provide a method for processing a data transfer related to data stored in a data storing card.

Accordingly a method of the present invention is to be implemented using a data transferring system and comprises 

 A when the data storing card is coupled to an electronic device of the data transferring system accessing by the electronic device card specific data and a card account number from the data storing card 

 B generating by the electronic device a device generated authentication number associated with the data transfer 

 C transmitting by the electronic device the card account number the card specific data and the device generated authentication number to a network platform of the data transferring system 

 F comparing by the network platform the inputted authentication number and the device generated authentication number and

 G when the inputted authentication number is deemed to correspond with the device generated authentication number transmitting by the network platform to be transferred data which is derived from the card specific data to the portable device.

Another object of the present invention is to provide a data transferring system that is capable of implementing the aforementioned method in order to process a data transfer related to a data storing card that stores card specific data and a card account number.

Accordingly a data transferring system of the present invention comprises an electronic device a portable device and a network platform. In some embodiments the data transferring system may comprise an external device for electrical connection to the portable device and the data storing card.

The electronic device is configured to be coupled to the data storing card for accessing the card specific data and the card account number from the data storing card. The network platform is operable to communicate with the portable device and the electronic device.

When coupled to the data storing card the electronic device is configured to generate a device generated authentication number associated with the data transfer and to transmit the card account number the card specific data and the device generated authentication number to the network platform.

The portable device is configured to receive an inputted authentication number and to transmit the inputted authentication number to the network platform.

The network platform is configured to compare the inputted authentication number with the device generated authentication number. When the inputted authentication number is deemed to correspond with the device generated authentication number the network platform is configured to transmit to be transferred data which is derived from the card specific data to the portable device.

Before the present invention is described in greater detail it should be noted that like elements are denoted by the same reference numerals throughout the disclosure.

The portable device may be embodied as a personal digital assistant PDA a mobile telephone a tablet computer or other computing devices that support communication with a mobile network. In this embodiment the portable device includes a baseband module a control module and a storage module .

The baseband module is an input output device that supports International Organization for Standardization ISO 7816 Universal Asynchronous Receiver Transmitter UART specification. In the embodiments the baseband module is configured to communicate with the network platform for transceiving data therewith and may include an application processor not shown in the Figures that provides software management such as executing the OS and or a booting sequence. The baseband module may also include a baseband processor not shown in the Figures for handling radio functions such as telephone and or text message.

The control module is coupled to the baseband module and the storage unit . In this embodiment the control module is embodied as an integrated circuit IC chip that supports Java functions and ISO 7816 standard and is configured to control transmission of data received by the baseband module to the storage module for storage in the storage module .

In the embodiments the portable device may further include a card connector coupled to the control module thereby allowing communication between the portable device and a data storing card. The card connector may support ISO 7816 and or ISO 14443 standard such that communication between the card connector and the data storing card may be performed with or without physical contact.

In the embodiments a data storing card may be embodied as but is not limited to a subscriber identity module SIM card an Europay MasterCard or Visa EMV bank card a secure digital SD card or its variations miniSD microSD etc or other cards that support ISO 7816 or ISO 14443 standard or other communication protocols e.g. Bluetooth or transmissions in industrial scientific and medical ISM radio bands . A set of card specific data is stored in the data storing card . The card specific data may include personal information associated with a card holder activity record of the card holder a value or a bonus value associated with the data storing card etc.

In the embodiments the storage module may be implemented using software hardware or a combination thereof. In some embodiments the storage module is integrated with the control module . The storage module is configured to store information such as an operating system a software application a JAVA applet such as a SIM application toolkit STK or the like. The above mentioned information may be obtained using over the air OTA technology.

In this embodiment the control module is an integrated circuit IC application chip having a Java card based design that implements a JAVA virtual machine and may be implemented with the baseband module onto a single IC chip. It is noted that in embodiments where the storage module is integrated with the control module the storage module is implemented using the JAVA virtual machine.

In some embodiments the control module may be an individual electronic card detachably connected to the portable device . The effect of using the Java card based design structure for the control module is that the control module can be operated to process applications that are compatible with the Java card based design structure e.g. applications related to EMV People s bank of China PBOC certificate authority CA and public key infrastructure PKI and that the Java card based design structure enables OTA configuration such that the operating system software applications and information stored in the control module may be updated and maintained conveniently.

In the embodiments the electronic device may be a point of sale POS machine and is configured to be coupled to the data storing card using contact contactless communication technologies. The electronic device may be installed with an application programming interface API that when executed causes the electronic device to perform various operations and functions.

In the embodiments the network platform may include a card person management system a security application management system a user card management system and a communication interface for communicating with the baseband module of the portable device .

The card person management system is stored with personal information associated with the customers of various vendors. In some embodiments various lists may be created for managing the personal information. One of a symmetric key algorithm and an asymmetric key algorithm can be employed when storing such information. The network platform may include a hardware security module HSM for managing the personal information.

The security application management system is stored with a plurality of executable programs e.g. JAVA applets mobile software applications or the like which may be tailor made for the vendors and may be downloaded by the portable device . One of the symmetric key algorithm and the asymmetric key algorithm can be employed when storing the executable programs. The HSM may be similarly used to manage the executable programs.

The communication interface is coupled to the baseband module of the portable device and the electronic device and is operable to transmit information thereto using one of a text message general packet radio service GPRS internet protocol suite TCP IP etc.

Referring to a particular function of the data transferring system is illustrated. Specifically a method is executed by the data transferring system in order to perform a data transfer related to the data storing card in which the data stored in the data storing card is transferred to the portable device .

In the embodiments the method may take place at a location of a POS of a vendor e.g. a coffee shop a department store or the like with which the data storing card serving for example as a membership card is associated. The data storing card stores card specific data and a card account number.

The user of the portable device may request that the data stored in the data storing card be transferred into the portable device thereby eliminating the need to carry the data storing card . The vendor may also offer the user to have the data stored in the data storing card transferred into the portable device .

In such cases the data storing card is coupled to the electronic device see and the vendor may then activate the API to execute the subsequent steps. In step S with the use of for example a card reader the electronic device is able to access the card account number and the card specific data from the data storing card and subsequently store the card specific data in the user card management system . In the embodiments the card account number may include at least one of a phone number associated with the portable device an identification number of a user of the portable device a birth date of the user of the portable device and a card number of the data storing card and the like.

In step S the electronic device generates a device generated authentication number associated with the data transfer. The device generated authentication number may be generated based upon the card account number that is received in step S. The electronic device then transmits the card account number the card specific data and the device generated authentication number to the network platform via the baseband module and the communication interface in step S.

The user of the portable device attempts to locate to be transferred data which is derived from the card specific data and is desired to be transferred to the portable device in the application management system of the network platform . In this embodiment the to be transferred data includes an executable application APP that can be found in a typical mobile software distribution platform such as App Store Google Play Samsung Apps or the like. The APP is associated with the vendor and is executable by the portable device . Once the APP is located i.e. the user finds a download link of the APP in the mobile software distribution platform the user of the portable device may initiate the download i.e. by pressing the download button on an interface of the portable device . In response the control module generates a request for data transfer and to transmit the request to the network platform via the baseband module .

Then in step S the portable device displays a dialog box now shown in the Figures that allows the user of the portable device to input an inputted authentication number therethrough. This step may be a result from a response to the request for data transfer from the network platform which requests authentication from the portable device . In some embodiments the user of the portable device is informed by the vendor of the device generated authentication number. The user subsequently inputs the device generated authentication number into the dialog box to serve as the inputted authentication number. The inputted authentication number received by the portable device is then transmitted to the network platform .

After the network platform receives the inputted authentication number in step S the network platform compares the inputted authentication number and the device generated authentication number. When the inputted authentication number is deemed to correspond with the device generated authentication number in step S the network platform transmits the to be transferred data to the portable device . Specifically the network platform associates the card specific data retrieved from the data storing card with the APP stored in the application management system and transmits the associated card specific data and the APP to the portable device .

In some embodiments the network platform deems the inputted authentication number to correspond with the device generated authentication number when the inputted authentication number is found to be identical to the device generated authentication number. In other embodiments the network platform transmits the to be transferred data when the inputted authentication number is deemed to logically correspond with the device generated authentication number.

Conversely when the inputted authentication number is deemed to not correspond with the device generated authentication number the flow proceeds to step S in which the network platform generates an error message indicating that the inputted authentication number is incorrect and transmits the error message to the portable device for display to the user. In this case the portable device is still allowed to download the APP but the card specific data is not associated with the APP and not subsequently transmitted to the portable device .

In response to receipt of the to be transferred data by the baseband module in step S the control module of the portable device controls transmission of the to be transferred data to the storage module for storage in the storage module . As a result the card specific data that is originally stored in the data storing card is now stored in the storage module and can be accessed by the portable device by the APP. Accordingly the user of the portable device does not need to bring the data storing card the next time he or she intends to obtain products and or services that are originally associated with the data storing card . In other words the portable device may serve as a virtual JAVA card that is capable of performing the functions of the data storing card . Moreover the card connector is left available as a result of the method and may therefore be utilized for other purposes.

The method of this embodiment may be particularly useful for products and or services that are said to have stickiness e.g. that attract the customers to spend more time and or money on the products and or services thus the customers sticking to them . Such sticky products and or services may include daily transportation services such as bus or mass rapid transit MRT and products in a convenient store or the like. When the method of this embodiment has been used to transfer various sticky products and or services to the portable device the user of the portable device only needs to execute the various APPS that correspond to the sticky products and or services when attempting to access the sticky products and or services instead of using various physical cards.

In a modification of this embodiment see the portable device may include a SIM card connector which is coupled to the baseband module and which is to be coupled to a SIM card . In addition the card connector may be coupled to the baseband module instead of the control module .

As shown in the second preferred embodiment of the data transferring system according to the present invention has a structure similar to that of the first preferred embodiment. The main difference between this embodiment and the first preferred embodiment resides in the following.

The portable device in this embodiment includes the SIM card connector and the SIM card may include a storage module in which the to be transferred data may be stored. As a result the storage module of the portable device of the first preferred embodiment may be omitted. The control module in this embodiment is coupled to the baseband module and the SIM card connector and is configured to control transmission of the to be transferred data received by the baseband module to the SIM card that is coupled to the SIM card connector for storage in the storage module of the SIM card .

As shown in the third preferred embodiment of the data transferring system according to the present invention has a structure similar to that of the second preferred embodiment. The main difference between this embodiment and the second preferred embodiment resides in that the control module of the portable device may be further omitted. As a result the baseband module is configured to transmit the to be transferred data received thereby to the SIM card that is coupled to the SIM card connector for storage in the storage module of the SIM card .

The third preferred embodiment has the same advantages as those of the previous preferred embodiments.

As shown in the fourth preferred embodiment of the data transferring system according to the present invention has a structure similar to that of the embodiment of . The main difference between this embodiment and the embodiment of resides in that the data transferring system further comprises an external device detachably coupled to the control module of the portable device and configured to be coupled to the data storing card . The card connector of the portable device of in this regard may be omitted. The external device may be embodied as a smart card reader that provides an interface to the data storing card using micro universal serial bus USB or its variations miniUSB microUSB etc. . In some embodiments the external device may be configured to communicate with the portable device wirelessly via for example wireless fidelity wi fi Bluetooth near field communication NFC Radio frequency identification RFID infrared radiation or the like.

The fourth preferred embodiment has the same advantages as those of the previous preferred embodiments.

In a modification of this embodiment see the external device is detachably coupled to the baseband module of the portable device and that the portable device includes the card connector . In the presence of the external device the card connector is available to be coupled to various other cards.

In cases where the user of the portable device is not interested in storing the to be transferred data in his her device e.g. due to storage space limitations the to be transferred data may be transmitted to other peripheral components that are able to communicate with the portable device .

For example a storage module of the external device may be utilized for storing the to be transferred data. As shown in in the fifth preferred embodiment of the data transferring system the external device is coupled to the control module of the portable device and includes a storage module for storing the to be transferred data therein. The control module is configured to control transmission of the to be transferred data received by the baseband module to the external device for storage in the storage module of the external device .

As shown in the sixth preferred embodiment of the data transferring system according to the present invention has a structure similar to that of the fifth preferred embodiment. The main difference between this embodiment and the fifth preferred embodiment resides in that the portable device includes the SIM card connector and the card connector that are coupled to the baseband module . Furthermore the control module is omitted in this embodiment such that the baseband module is configured to transmit the to be transferred data to the external device for storage in the storage module .

The fifth and sixth preferred embodiments have the same advantages as those of the previous preferred embodiments.

In some embodiments the to be transferred data may be transmitted to the data storing card or another data storing card for storage in a storage module thereof.

In the seventh preferred embodiment of the data transferring system see the control module of the portable device is coupled to the baseband module and the external device and is configured to control transmission of the to be transferred data received by the baseband module to the external device for storage in the storage module of the data storing card that is coupled to the external device .

In a modification of this embodiment see the baseband module is coupled to the external device and is configured to transmit the to be transferred data to the external device for storage in the storage module of the data storing card that is coupled to the external device .

The seventh preferred embodiment has the same advantages as those of the previous preferred embodiments.

To sum up embodiments of this invention enable the portable device having other peripheral components i.e. the SIM card the data storing card or the external device attached thereto to serve as a virtual JAVA card that is capable of performing the functions that originally require various physical cards since the card specific data and the corresponding APPs are both retrieved by and made accessible to the portable device . When a number of products and or services are integrated into the portable device in such manner the corresponding physical cards not in need may be then returned to the vendors or discarded. The card connector may also be left available for other uses.

This invention may be particularly useful when the user of the portable device is interested in utilizing a large number of sticky products and or services.

While the present invention has been described in connection with what are considered the most practical and preferred embodiments it is understood that this invention is not limited to the disclosed embodiments but is intended to cover various arrangements included within the spirit and scope of the broadest interpretation so as to encompass all such modifications and equivalent arrangements.

