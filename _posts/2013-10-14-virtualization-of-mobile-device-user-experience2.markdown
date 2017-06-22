---

title: Virtualization of mobile device user experience
abstract: A device virtualization service (DVS) is provided that uses a generalized thick client resident on a mobile device to provide user interface generation support to a myriad of services providing mobile device content. The DVS abstracts device specifics from services to provide device independent user experiences to be described by the service and then rendered on the device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09542062&OS=09542062&RS=09542062
owner: Microsoft Technology Licensing, LLC
number: 09542062
owner_city: Redmond
owner_country: US
publication_date: 20131014
---
This application is a continuation of U.S. patent application Ser. No. 11 474 303 filed on Jun. 23 2006 the entirety which is incorporated herein by reference.

User satisfaction with a program application or service running on a mobile device often depends on the user interface UI associated with the mobile device. With some mobile devices a UI is supplied to a mobile device via the Internet. With web based provisioning of a user interface a web page is built on a server and provided to the user through the web browser available on the mobile device. The interactivity between the user and the web page is limited to the browser s rendering capabilities which also limits the interactivity between the user and the program. Mobile devices also have a limited bandwidth of communication. A lower bandwidth can create higher latency for the receipt and transmission between the web page produced on the user s mobile device and the application resident on an external server.

A UI may also be associated with a mobile device by downloading the entire program or application to the mobile device. The entire program may consume a large portion of the memory of the mobile device. Also a UI may be associated with a mobile device by downloading a thick client to the mobile device. The variety of mobile devices available and the variety of thick clients may result in compatibility problems that arise as these types of clients are used. Also building a thick client for each of the various mobile device results in development testing and economic inefficiencies.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

A device virtualization service provides a generic thick client to a mobile device. The generic thick client facilitates providing customizable user interfaces on multiple mobile device platforms without requiring the developer to generate the user interface to write specialized code for each mobile device model. In this manner Internet services may provide data and information to mobile devices without regard to the type of device on which the information is being rendered.

Embodiments are herein described more fully below with reference to the accompanying drawings which form a part hereof and which show specific examples for practicing the embodiments. However embodiments may be implemented in many different forms and should not be construed as limited to the embodiments set forth herein rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the subject matter to those skilled in the art. Embodiments disclosed may be practiced as methods systems or devices. Accordingly embodiments disclosed may take the form of an entirely hardware implementation an entirely software implementation or an implementation combining software and hardware aspects. The following detailed description is therefore not to be taken in a limiting sense.

When reading the discussion of the routines presented herein it should be appreciated that the logical operations of various embodiments are implemented 1 as a sequence of computer implemented acts or program modules running on a computing system and or 2 as interconnected machine logic circuits or circuit modules within the computing system. The implementation is a matter of choice dependent on the performance requirements of the computing system implementing the invention. Accordingly the logical operations illustrated and making up the embodiments described herein are referred to variously as operations structural devices acts or modules. These operations structural devices acts and modules may be implemented in software in firmware in special purpose digital logic and any combination thereof.

Referring now to the drawings in which like numerals represent like elements various aspects of the present invention will be described. In particular and the corresponding discussion are intended to provide a brief general description of a suitable computing environment in which embodiments of the invention may be implemented.

Generally program modules include routines programs components data structures and other types of structures that perform particular tasks or implement particular abstract data types. Other computer system configurations may also be used including hand held devices multiprocessor systems microprocessor based or programmable consumer electronics minicomputers mainframe computers and the like. Distributed computing environments may also be used where tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules may be located in both local and remote memory storage devices.

Referring now to an exemplary computer architecture for a computing device utilized in various embodiments will be described. The computer may be configured as a personal computer a mobile computer and the like. As shown computing device includes a central processing unit CPU a system memory including a random access memory RAM and a read only memory ROM and a system bus that couples the memory to the CPU . The computing device further includes a mass storage device for storing an operating system application programs and other program modules which will be described in greater detail below.

The mass storage device and its associated computer readable media provide volatile and non volatile storage for the computing device . The computer readable media may include any type of removable and or non removable media.

The computing device operates in a networked environment using logical connections to remote computers through a network such as the Internet. The computing device may connect to the network through a network interface unit connected to the bus .

The computing device may also include an input output controller for receiving and processing input from a number of devices such as a keyboard mouse electronic stylus and the like. Similarly the input output controller may provide output to a display screen a printer or some other type of device not shown .

As mentioned briefly above a number of program modules and data files may be stored in the mass storage device and RAM of the computing device including an operating system suitable for controlling the operation of a networked computer. The mass storage device and RAM may also store one or more program modules. In particular the mass storage device and the RAM may store a device virtualization service DVS module .

The configuration of DVS module is dependent on whether the computing device has been configured as a service provider server that provides service data and interaction a DVS server that configures data for transmission to a mobile device or a mobile device itself. For a service provider computing device DVS module provides configuration files and communication protocols for communicating data to the DVS server in a generalized format. For DVS server DVS module provides translation and packaging configuration data for translating data received from the service server. The DVS module packages the data for efficient transmission to the mobile device. For the mobile device itself DVS module may include a thick client application for rendering the resulting user interface on the screen of the mobile device. A thick client also known as a fat client or rich client is a client that performs data processing operations and relies on an associated server for data storage.

Throughout the specification and claims the following terms take the meanings explicitly associated herein unless the context clearly dictates otherwise. In some aspects Device Virtualization Service or DVS refers to any portion of a network configuration whether referring to the server side or client side in the communication for generating a user interface on a mobile device from generalized data passed through a DVS server.

In some aspects DVS server refers to a server that is configured to obtain generalized data from services facilitate translating and packaging the generalized data into an optimized format facilitate forwarding the optimized data to a mobile device facilitate event handling for communication between the mobile device and the service as well as perform other additional tasks.

In some aspects Event refers to an interaction with the user interface rendered on the mobile device that triggers communication back to and from the service associated with the user interface.

In some aspects Widget refers to a user interface element for providing a user experience UX . As one exemplary definition for a widget a widget may be an interface component such as a display frame or a text box.

The Device Virtualization Service DVS facilitates projecting a user experience UX onto a mobile device. In one embodiment the DVS provides an interface API that allows the service to provide a set of User Interface UI pages which in turn lay out widgets of those pages. The widgets may include data tables for efficient storage of the data included on the pages. The Device Virtualization Service DVS abstracts device specifics from services that want to expose an end user experience on the device. The DVS provides a device independent UX to be described by the service and then rendered on the device. The DVS may also enable a service to obtain device capabilities such as screen size audio and video COmpress DECompress technology CODEC supported so that the service can provide appropriate media to the device.

Service may correspond to a service for providing media or another service for providing news or sports headlines. The particular type of service may vary without affecting the scope or applicability of the disclosure. Service may be physically represented by a server or other computing device that stores and manages data. particular to the service and is responsible for communication of the data to other devices.

DVS server is configured to receive data from service package the data for transmission transmit the data to the mobile device e.g. for rendering handle events that occur on the mobile device and communicate those events. A more detailed discussion of the operation of DVS server is provided below in the discussion of .

Once the packaged data is received at the mobile device e.g. the mobile device uses a DVS generalized thick client to render the data. The generalized thick client may render a user interface for multiple services without having customized programming resident on the mobile device for each service. A more detailed discussion of the processes involved for system are provided below in the discussion of .

An application programming interface API allows the service to obtain a set of device characteristics to customize the data it provides for a specific mobile device. For instance the service may determine the pixel resolution of the device the media formats the device supports which media settings provide the optimal device playback and the like.

A typical service such as a music service often provides a series of page layouts for the various different portions of their service experience. For example the music service may include a browse by artist page a browse by genre page and the like. The music service may also provide a media preview page and a purchase confirmation page. The navigation between the pages is defined by behaviors attached to one or more widgets on the pages. In this way the service has substantial control over the flow of the UI.

At operation a message is sent to the mobile device with a network address where the mobile device can locate and download the generalized thick client. In one embodiment the DVS server sends the mobile device a Short Messaging Service SMS message that includes a Uniform Resource Locator URL that indicates a location for downloading the generalized thick client. Processing continues at operation .

At operation the user selects or clicks on the URL sent in the SMS message to commence the download process that downloads the generalized thick client to the mobile device. Processing continues at operation .

At operation an Internet service server or HTTPS server authenticates a User ID that was encoded in the URL sent to the user s mobile device. The authentication ensures that the mobile device that sent the SMS message is the device receiving the downloaded client application. A cookie is sent to the mobile device that includes the encrypted user ID and hash so that the mobile device is identified as an authenticated mobile device for future communications. Along with the cookie the generalized thick client is downloaded to the mobile device. Processing continues at block .

At block the generalized thick client is installed on the mobile device. One or more installation wizards may be used for the installation or other methods of installation may be used. Once the generalized thick client is installed processing continues to operation .

At operation the thick client is activated by the user for receiving data related to the service. Once the thick client is activated processing continues to operation .

At operation a device key is requested to authenticate that the user of the mobile device and the mobile device are authorized to access the service data. Processing continues at operation .

At operation the cookie is validated to ensure that the mobile device is the mobile device authorized for viewing the service data. In another embodiment a username password may be used for validating the user of the mobile device as capable of viewing the service data. If authentication fails the credentials of the user or the mobile device s credentials may be challenged. If challenged processing moves to operation .

At operation the user interface generating the rendered version of the service data may transition to request the user s credentials as a result of the credential challenge. A user interface screen may be presented for entering a user ID and password for authentication. Once the credentials are provided processing returns to operation where the mobile device may again be authenticated with the service server. Once authenticated processing continues at operation .

At operation device key pairs are generated for securing the communication of the service to the mobile device. A device record is generated indicating the device is accessing the service data at this time. Processing continues at operation .

At operation the device private key device ID and a next sequence number is returned to the mobile device. The device private key is used to authenticate the data s source as the data is received by the mobile device. The device ID provides a unique identifier of the device for the service and may be used in future communications for expediting service data provisioning. The next sequence number indicates where the device is currently with regard to receiving the service data. For example the service may be a news service that sends news items to mobile devices. If the user has not received the news service items in a while that is reflected in the sequence number. Every news item since the time indicated by the sequence number may then be forwarded to the mobile device. Processing continues at operation .

At operation the private key device ID and sequence number are saved to the mobile device. Processing then continues at operation .

At operation the actual data for the service is requested from the DVS server. The DVS server is sent an encrypted version of the device private key device ID sequence number and hash along with a version number of the generalized thick client that the mobile device is running. Once the request is provided to the DVS server processing continues with operation .

At operation the DVS server decrypts the device ID sequence number hash and version number using the public key of the private public key pair and validates them. Processing then continues to operation .

At operation the DVS server returns a next sequence number the actual service data and any special actions e.g. debug mode enable encrypted using the public key to the mobile device. Processing continues to operation .

At operation the generalized thick client interprets the service data and displays the top level page for the service. Once complete the user may then interact with the data and processing moves to other tasks.

Process is one aspect for provisioning the mobile device for receiving service data for rendering on a mobile device. Other methods may be used. Additionally a higher level description of the interaction between the DVS server and the mobile device is provided below in the discussion of . It is understood however that the authentication processes depicted in process are equally applicable to the other processes described herein.

At operation the UX definition is received by the DVS server. In one embodiment the UX definition is provided as an Extensible Markup Language XML file. Other embodiments may receive the UX definition according to other formats. Processing continues at operation .

At operation the UX definition file received from the service is compiled into binary code. The binary code is a compact form of the data that may be transmitted to the mobile device while preserving the limited bandwidth of communication. Once the binary is generated processing continues to operation .

At operation the binary code is forwarded to the mobile device for rendering the user interface for the service. In one embodiment the binary code is forwarded according to the authentication processes described above with relation to . Processing continues with decision operation .

At decision operation a determination is made whether an event has occurred with relation to the user interface rendered with the service data. An event notification may be received by the DVS server that indicates such an event e.g. a mouse click . If an event has occurred processing continues with operation .

At operation the event is routed to the service server for handling. Once the event is routed to the service server process ends and moves onto other tasks such as routing responses back to the mobile device receiving additional events or logging the mobile device out of the service session.

Many widgets may obtain their values by binding to the service provided data tables. The table formats and data are specified by the service. The aforementioned music service example may include tables for the artists albums genres and tracks. Tables may contain one or more fields whose values link to rows in other tables. For example the artist and album tables would likely link to the genre table to indicate the genre for a particular artist or album. Similarly the album table would link to the artist table to indicate the artist of a particular album.

The binding may be associated in the page definition. A data binding is provided for a widget to link to a particular data table. The table may also be filtered to entries with a particular value in a field in the table. For example to display the albums by a particular artist the album table may be filtered to rows in which the ArtistID field contains the selected ArtistID value. There may be an optional format specification provided to translate the value stored in the table into text that is displayable to the user. For example a timestamp value stored numerically may be displayed in several different ways h mm hh mm hh mm ss etc. .

When the service has provided this DVS data to the DVS servers as previously described the data is compiled into a binary format appropriate for the user s mobile device. This allows a layer of abstraction between the services that use DVS and the device clients. Accordingly the DVS may hide many of the differences between specific mobile device client implementations. For example some devices may have the ability to expose the native media player via the user interface widgets provided by the generalized thick client. Other devices may only offer the ability to play audio via a native playback user interface that is separate from the service provided user interface. These differences may be abstracted so that the service does not require knowledge of the device specifics.

The device virtualization service may support mobile phones mobile PDAs laptops and desktops television set to boxes and any other network connected device with a user interface. The user interface is generated with better bandwidth utilization due to the binary packaging of the data before transmission to the mobile device and with better memory utilization by retaining data storage for producing the service content external to the mobile device. Additionally service providers are able to provide a customized user interface without customized code for the various mobile device types currently available.

The above specification examples and data provide a complete description of the manufacture and use of the composition of the invention. Since many embodiments of the invention can be made without departing from the spirit and scope of the invention the invention resides in the claims hereinafter appended.

