---

title: Messaging service system and method to be performed in such a system
abstract: The invention relates to a method and a Messaging Service system which includes one or more Messaging Service terminals and a control means being adapted for communication with a printing means. The Messaging Service terminal is adapted to send a message to the control means, which message contains a print-related information section and a message content section representing the message content. The print-related information section contains print-related information and designates the delivery of the message content section to the printing means or to a second Messaging Service terminal. The system is preferably implemented as a Multimedia Messaging Service (MMS) system. The message content section may represent one or more images. The print-related information section is preferably contained in a header of the message, and may contain authorization information related to printing or copying rights for printing or copying the message content, preferably the image or images represented by the message content section, by the second Messaging Service terminal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=RE045643&OS=RE045643&RS=RE045643
owner: Vringo, Inc.
number: RE045643
owner_city: New York
owner_country: US
publication_date: 20130726
---
The invention relates to a messaging service system preferably a Multimedia Messaging Service MMS system in which messages can be transmitted which contain an information section and a message content section such as an image section. Such a MMS system is suitable for transmitting information of multimedia type such as images e.g. photographs audio information and also pure text or graphic information. The invention furthermore relates to a method for transmitting messages containing an information section and a message content section e.g. an image data section.

Messaging services are frequently used for swiftly sending messages e.g. between mobile phones. As an example SMS Short Message System messages can be sent from one user equipment such as a mobile station for instance mobile phone to another user equipment which may be a mobile or stationary network component.

MMS Multimedia Messaging Service provides an advanced messaging service which is able to send multimedia type information such as images audio data or the like from one equipment to another equipment. The multimedia messaging service MMS is a system application which allows a WAP Wireless Application Protocol client to provide a messaging operation with a variety of media types. The WAP defines a specification for developing applications operating over wireless communication networks. A user may therefore send multimedia messages over a WAP equipment such as a mobile terminal. Such messages can then be displayed on a display of the receiving equipment e.g. a mobile terminal. Although this type of messaging service is beneficial in that it allows the sending of a variety of different types of data it nevertheless is subject to some restrictions regarding usability.

According to one aspect of the invention a Messaging Service system is provided which includes at least one first Messaging Service terminal and a control means being adapted for communication with a printing station the first Messaging Service terminal being adapted to send an image message to the control means the message containing a print related information section and a message content section representing the message content wherein the print related information section contains print related information and designates the delivery of the message content section to the printing station or to a second Messaging Service terminal.

Furthermore the invention provides according to another aspect a method to be performed in a Messaging System in particular a Multimedia Messaging Service MMS system including at least one first Messaging Service terminal and a control means being adapted for communication with a printing station the first terminal sending a message to the control means wherein the message contains a print related information section and a message content section representing the message content preferably one or more images the print related information section containing print related information and designating the delivery of the message content to the printing station or to a second Messaging Service terminal.

The present invention provides a messaging service wherein the messages contain print related information section. The print related information preferably indicates whether printing of the message contents such as one or more images is allowed or prohibited. The print related information may also indicate print restrictions such as maximum number of allowed prints of the message. The print related information may also indicate a desired printing of the message content requested by the sending terminal. This print related information section provides an additional functionality to the messaging service in that it allows restricts or inhibits a printing of the message contents.

Such an additional functionality is in particular of advantage in a multimedia messaging service MMS which is adapted to send images such as graphic pictures or photographs in addition to other information such as pure text information. However the invention may also be implemented in a messaging service of other type such as SMS Short Message Service or USSD Unstructured Supplementary Service Data messages.

A system or a method in accordance with the invention allows a user to deliver and print e.g. images such as photographs preferably taken by using a digital camera the images being printable on a suitable hard copy output device. Such a hard copy output device e.g. includes printers of any type such as a personal photo quality color printer an internal company printer connected via e.g. an Ethernet LAN Local Area Network or a user specified developing and printing service.

The images may be taken using any kind of imaging preferably digital imaging. The image capturing device can be a MMS terminal a digital camera or any other suitable type of imaging device. Image processing such as filtering reduction and or interpolation of the image may be performed before printing the image. The printing services used for printing the image can be a traditional or digital print processing house. The printed images may be transferred from or to the print ordering station by any suitable method such as wireless data transfer or galvanic transport.

As an example a MMS user may have taken a picture using a multimedia terminal and transferred the image to a MMS center MMSC which serves as control means or server of the MMS system. Via this MMSC the image is delivered to the recipient specified by the sender. When the recipient wants to print the received image she he may e.g. order a print from the originating user which can either explicitly give permission for printing one or more pictures sent to the MMSC or may initially mark any sent image as being acceptable or prohibited to print. The recipient can then request a local or remote printing of the desired image.

The messaging service is thus extended to convey printing information or other authorization data which preferably are included in the same message as the picture sent to the recipient. Images can therefore be marked or tagged for print. As an alternative the image originator which will usually be the copyright holder and the recipient can perform a negotiation before effecting any print of a transmitted image. According to the invention the method of output e.g. on a local printer or an external print service can also be designated.

Images can be transmitted to a printer based on user supplied profile data or direct indication of a printer address.

According to the present invention manual steps for ordering the printing of images can be eliminated. The invention provides a solution preferably for multimedia terminals able to capture images and to send images directly to a printer system for printing e.g. either to a local printer or to an external printing service .

In accordance with one of the aspects of the invention the originating terminal e.g. MMS terminal can indicate during upload of the image whether the image is to be stored in the messaging service server for subsequent processing and or printing.

Furthermore according to another aspect of the invention the printing information is preferably embedded inside a messaging service message such as a MMS message. Possible printing information may include permission to view only permission to print once or several times up to a defined upper limit size of print print quality printer address payment method etc.

The negotiation process performed between the originating and receiving users terminals may lead to the embedding of the negotiated and accepted printing parameters in the initial image uploaded to the messaging service center including information relating to e.g. charging constraints on printing routing information indicating the requested printer etc. In such a case the negotiation process may be performed before actually transmitting a picture to the receiving terminal.

According to the invention a print specific payload may be included in any operation or message to from a user equipment and the associated server. The payload e.g. the print header may contain the address and parameters defining where to output send and print the message. This can be realized by the addition of one or more print related fields to the message such as the MMS message. When a print is requested after the message has already been delivered to the receiving terminal the MMS message may include a print field indicating the state such as the print request which message is sent to the originating terminal. A print request primitive may be provided to indicate this request. Likewise a print status response will be provided which indicates printing allowed prohibited restricted . When the print rights are defined by the sending MMS terminal beforehand the message sent by the originating user contains a print header which already contains all print right fields.

This concept may also be applied for printing messages of other type such SMS messages which may then be redirected directly to a printer such a local desktop printer if available.

In a preferred embodiment a user may directly specify a print service which is selected for printing the transmitted image or images. The printer specifying information is relayed to the control means such as MMSC via a specific print command request. A response from the control means may inform the user on the print authorization and conditions such as the price for printing the image or images. This information can be encapsulated and sent as a print order via a messaging service such as MMS or e mail.

When uploading an image to another terminal the sending terminal preferably indicates if the image is to be stored by the control means for further processing and printing.

The invention provides enhanced print services in that print information is embedded inside a messaging service message preferably a MMS Multimedia Messaging Service message. Furthermore such print related information may also specify that the control means is to store the complete message or at least the message content such as one or more images even after delivery to the recipient. Therefore when the recipient subsequently wishes to print the message e.g. the image it is only necessary to inform the control means of the printing request which thereupon performs the necessary steps such as transmitting the image to a printing device or service.

In accordance with a preferred aspect of the invention print related information such as printing information printing copyright cost printer address information or information on from where whom to get the printing permission is embedded inside the message such as MMS message itself when the message is first sent.

The print related information section is preferably contained in a header of the message. Such header is usually provided for indicating the addresses of the sender and recipient and is therefore only to be extended so as to include information field s for the print related information. Hence no additional message is to be sent for the print related information and the existing messaging service can be used without need of specifying new standards. Merely the definition of the information section has to be specified so as to provide one or more additional fields for the print related information.

The print related information may contain authorization information. The recipient and or control means thus are informed on the printing or copying rights related to the transferred message content such as the image or images. When the print related information indicates inhibition to print general allowability or printing only up to an upper limit such as e.g. five prints of the original no additional signaling and message communication with the sender is necessary. The recipient merely has to request if printing is allowed a printing service either directly or via the control means to make and deliver the intended prints.

Preferably the control means is adapted to store the print related information such as authorization information and is thus able to check it for print permission when the recipient is requesting a print. This structure reduces the signaling and messaging load of the network.

When the recipient desires to print the received message content such as text graphic or image such as a photograph and the print related information indicates a necessary communication with the sending terminal in order to clarify print conditions the control means informs the sending terminal on the intended print and receives therefrom data specifying the print conditions or restrictions such as maximum number of allowable prints costs for printing the image and the like. Hence the sending terminal is in this case not forced to specify all printing conditions in his first message but may deliver or specify them only after receipt of a query indicating a desire to print the sent image.

Preferably the control means comprises a memory for storing the message contents such as one or more images received from the first terminal and transmitted to the second terminal. When the second terminal is issuing a print command to the control means it is unnecessary to transmit the image data from the recipient terminal or sending terminal to the control means. This reduces the total amount of traffic occurring in the network.

The printing station may be an external printing station which e.g. is specifically adapted for printing images such as color photographs with high quality.

The invention is furthermore characterized in that the network components such as the terminals and or the control means are adapted to perform the functions as defined above and in the following description. Therefore the network components as such are likewise to be considered as representing independent implementations of the invention.

The system furthermore comprises or cooperates with a printing service which may be a local printer or an external printing service for example.

Although the term image is used here this term is to include pictures of any kind such as graphic representations sketches and the like. This image may be sent in or as the MMS message with MIME content type MIME Multipurpose Internet Mail Extension such as e.g. JPEG image.

The steps and messages shown in will be described below in detail referring to the numbering attached to the individual messages of . In step . the MMS terminal originating an image or picture sends this image or picture to the MMS terminal using the multimedia messaging service. The MMS message originated from terminal includes a header containing print related information and the picture data. This MMS message is first directed to the MMS server which transfers in step . the received message to the MMS terminal based on the recipient address indicated in the MMS message. After viewing the received image the user of the MMS terminal decides in the present example to print the image if allowed and therefore sends in step . a request message to MMS server inquiring on the permission to print.

In step . the request sent in step . is transferred by MMS server to the originating MMS terminal either in unchanged manner or in translated form such as a text or other type such as special indication message.

MMS terminal checks the requested permission to print and after deciding thereon sends a response which in the present example is the message shown in step . i.e. a message permission granted constraint parameters . The constraint parameters may e.g. represent limitations on the maximum number of allowable prints the size of prints the print resolution etc. If no constraints are provided the constraint parameters need not be sent or may by set to zero or default value. This message sent to MMS server in step . is transferred to the MMS terminal as a response which indicates permission granted and eventually may include print parameters according to any constraint parameters if provided.

In step . the MMS terminal after deciding on the print parameters if any and the acceptance thereof sends a request message to the MMS server requesting a print of the image and eventually indicating additional parameters which may define a printer to be used and or user profile issues.

The MMS server selects an appropriate printer or printing server and in the case of sends a message to the external printing service transferring the image and print parameters to the printing service step . . Furthermore in the step . the MMS server sends a confirmation to MMS terminal stating that the image is being processed i.e. that printing is performed.

When the external printing service has completed the printing job it sends a message to the MMS server confirming that the image has been printed step . . Thereafter the MMS server sends a notification step . to the MMS terminal informing it on the effected print and eventually additionally sends a message step . to the originating MMS terminal informing same on the print of the image by MMS terminal .

In the notification sent in . the MMS server may also inform MMS terminal on the location where the printed image is waiting for being collected in particular in a case when several different printers are available for printing.

Alternatively the constraint parameters may also indicate an upper limit of allowable number of prints such as five prints. The MMS server then sets a counter counting the number of prints of the image requested by MMS terminal . When the maximum allowable number is reached all subsequent printing requests are rejected. When the print permission should be given for multiple prints without any upper limit the user of MMS terminal is informed in step . that the image can be printed as many times as desired.

The constraint parameters of message . may include additional or other parameters such as allowed printing resolution. This may in particular be of importance for professional images where print permission may be given for low resolution printing only or for high quality professional printing. Fees charged for these different printing possibilities may be negotiated or may be fixed and will depend on the decision of the user of MMS terminal having the copyright of the image in question.

During the request print negotiation phase the MMS terminal may also state in the message sent in step . price charging information as one of the constraint parameters. Additionally the MMS terminal may wish to stenographically embed a digital water mark in the image so that the copyright holder i.e. in this case the user of MMS terminal can be identified. For further details regarding the embedding of watermarks see EP 0 862 318 A2.

The response of step . may include information regarding the size or quality of image the user of MMS terminal is allowed to print. For example full reproduction of an art work may not be allowed. As an alternative or additional feature cryptographic information may be passed to allow subsequent decryption and printing by the user of the MMS terminal . Such a feature enhances the security against unallowed copying or reproduction of an image by third parties or by the user of MMS terminal e.g. when trying to print an image exceeding the printing rights granted to the user of MMS terminal .

The print image request sent in step . may be used to perform a printer discovery and or indicate a print user profile. The request sent in step . may contain specific routing addressing information indicating which printer should print the image. As an example the image may be further transferred e.g. via e mail to a print server on the user s corporate LAN local area network . This print server may provide a special print service. In such a case the request message of step . preferably contains additional information such as the address of the machine to transfer the image to and the alphanumeric name or address of the printer.

In case the user of MMS terminal does not wish or is unable to directly indicate the printer to be used the print service preferably uses a default printer from which the printed image or images is are then to be collected. For example a command print to may be left blank in the message of step . which means the use of the default printer.

When an external print service is used additional information is preferably carried inside the message in a secure way e.g. in encrypted manner for example the user s name address print quantity output size payment method etc.

When the recipient terminal requests one or more hardcopies prints of the transmitted image no permission request and response messages are to exchanged because permission and conditions if any to print is already defined during the initial delivery of the image from the originating terminal to the server . Hence steps . to . of can be omitted leading to a reduction of the signaling and traffic load of the network components handling such messages. Steps . to . of essentially correspond to steps . to . of . In step . of the response may include additional print job information signaling the printer or printing service used for printing the image informing the user where to collect the print charge information for printing charges and the like.

Such inclusion of print authentication information into the MMS message offers an easy access determination to works such as copyright protected works e.g. images. The copyright owner can easily define the copy protection of the image and may either give permission to print the image or mark it as view only i.e. not printable etc.

In step . of the message sent from MMS terminal A to the MMS server includes the print authentication information as embedded information. The print authentication information defines print parameters relating to restrictions e.g. which persons are allowed to print the image.

The print authentication information and or the dialogue performed according to steps . to . of which relates to permission to print image can be extended so as to include transfer of charging information. In this case the print authentication information or response issued from the originating terminal assumed to be handled by the copyright holder will indicate the costs charged for printing. If the recipient terminal user requests to print the image the user of terminal will be billed based on the charge information set by the user of terminal .

The transferring of charging information can be reduced to a print profile or print charging profile for each user in particular each recipient user. In such a case the MMS server preferably comprises a set of tariff clauses which are used to inform the recipient user about the charges. This relieves the originating user of terminal from specifically setting a desired monetary unit amount. Such a strategy may be well compatible with current charging gateways of networks such as GSM networks.

According to the print parameters are embedded in the initial image upload to the MMS server as performed in step . Therefore no other additional message is to be sent from MMS terminal for ensuring a correct print.

In step . the MMS server sends the image contents to the printing service and requests print of the images in the appropriate format. In particular in a case where several images are contained in the image upload message of step . the order of printing thereof may be specifically defined. Alternatively the images may be printed in the order as received. The printing service sends a print order response in step . confirming the print request. Finally the MMS server sends a print response in step . to MMS terminal informing the latter on the performed print.

The originating user may give explicit permission for printing all pictures sent to an MMS server or he can mark any individual image sent as being OK to print or containing restrictions for print . A negotiation between two users parties of the MMS terminals may be performed including designation of the method of output. The print service to be used may be specified by the user of the originating or receiving terminal. Such information is preferably relayed to the MMS server and e.g. charge information is returned to a user subscriber .

The print field shown in may be provided as a specific extension of the message such as a MMS message. For instance the Send Request table specified in MMS Message Encapsulation Draft of WAP FORUM may be extended to include the following fields 

The print fields may additionally contain a field format which may be or include a specific identifier which identifies the print parameters which can be used. This field can also contain or define a link to further messages which may carry e.g. print information such as DPOF Digital Print Order Format information.

An additional field print to may be provided for indicating the address which defines the address of the printer or service to perform the print.

The above example of a print field is suitable e.g. for WAP MMS messages. Any other suitable language such as XML may likewise be used to carry the necessary information such as parameters.

Any suitable method such WAP message encapsulation can be used after appropriate extension to include appropriate additional fields and or the fields values may sent as a message content e.g. a user multipart message encoded in an appropriate language such as XML.

The message sent from terminal to terminal does not need to include a print destination. When the terminating mobile terminal forwards the message to the printing service the print destination will then be defined according to the selection of terminal .

In such a case the message sent from terminal in step . may include an indication print destination defining the print service to be addressed by terminal when desiring to print the message.

In the following some specific examples of information sections of messages will be described. The words and or values used below are illustrative examples only.

Again the message content when sending any of the above values can indicate the REASON why the printing is allowed restricted forbidden.

This is optionally carried in the MT case however the recipient user will nearly always specify where he she wants to print the messages.

In the MO case with NO destination mobile the PRINT Destination is likely to be the MMS Destination address and is probably not needed here.

It can be used to further restrict output in the MO MT case where its content can indicate Service Only thus the user is not allowed local output laser printer etc.

If the WAP Message Encapsulation Message protocol data units and fields are NOT used then a PRINT directive or MIME type can be used to carry XML encoded data to achieve the same goal.

Although the invention has been described by mainly referring to images transported as messages the messages may also contain another message contents such as pure text. The invention is applicable to messages of any such type when it is intended or requested to print such messages.

While the invention has been described with reference to specific embodiments the description is illustrative of the invention and is not to be construed as limiting the invention. Various modifications and applications may occur to those skilled in the art without departing from the true spirit and scope of the invention as defined by the appended claims.

