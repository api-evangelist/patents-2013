---

title: Device authentication using display device irregularity
abstract: A device authentication server authenticates a remotely located device using data representing pixel irregularities of a display of the device. Since each display will deteriorate in a unique and randomized way, a unique mapping of pixel irregularities of a display of a device will be unique. By combining unique map of pixel irregularities of a display of the remotely located device, the device can be distinguished from similar devices when other attributes alone are insufficient to uniquely identify the device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08695068&OS=08695068&RS=08695068
owner: Uniloc Luxembourg, S.A.
number: 08695068
owner_city: Luxembourg
owner_country: LU
publication_date: 20130606
---
This application claims priority to U.S. Provisional Application No. 61 816 136 which was filed Apr. 25 2013 and which is fully incorporated herein by reference.

The present invention relates generally to network based computer security and more particularly to methods of and systems for authenticating a device for computer network security.

Device identification through digital fingerprinting has proven to be invaluable in recent years to such technologies as security and digital rights management. In security authentication of a person can be restricted to a limited number of previously authorized devices that are recognized by their digital fingerprints. In digital rights management use of copyrighted or otherwise proprietary subject matter can be similarly restricted to a limited number of previously authorized devices that are recognized by their digital fingerprints.

Digital fingerprints are particularly useful in uniquely identifying computing devices that are historically know as IBM PC compatible . Such devices have an open architecture in which various computer components are easily interchangeable with compatible but different components. There are two primary effects of such an open architecture that facilitate device identification through digital fingerprints.

The first facilitating effect is diversity of device components. Since numerous components of IBM PC compatible devices are interchangeable with comparable but different components generation of a digital fingerprint from data associated with the respective components of the device are more likely to result in a unique digital fingerprint.

The second facilitating effect is discoverability of details of the various components of IBM PC compatible devices. Since the particular combination of components that make up a given device can vary widely and can come from different manufacturers the components and the operating system of the device cooperate to provide access to detailed information about the components. Such information can include serial numbers firmware version and revision numbers model numbers etc. This detailed information can be used to distinguish identical components from the same manufacturer and therefore improves uniqueness of digital fingerprints of such devices.

Laptop computing devices evolved from desktop computing devices such as IBM PC compatible devices and share much of the architecture of desktop computing devices albeit in shrunken form. Accordingly while users are much less likely to replace graphics circuitry in a laptop device and components therefore vary less in laptop devices laptop devices still provide enough detailed and unique information about the components of the laptop device to ensure uniqueness of digital fingerprints of laptop devices.

However the world of computing devices is rapidly changing. Smart phones that fit in one s pocket now include processing resources that were state of the art just a few years ago. In addition smart phones are growing wildly in popularity. Unlike tablet computing devices of a decade ago which were based on laptop device architectures tablet devices available today are essentially larger versions of smart phones.

Smart phones are much more homogeneous than older devices. To make smart phones so small the components of smart phones are much more integrated including more and more functions within each integrated circuit IC chip. For example while a desktop computing device can include graphics cards and networking cards that are separate from the CPU smart phones typically have integrated graphics and networking circuitry within the CPU. Furthermore while desktop and laptop devices typically include hard drives which are devices rich with unique and detailed information about themselves smart phones often include non volatile solid state memory such as flash memory integrated within the CPU or on the same circuit board as the CPU. Flash memory rarely includes information about the flash memory such as the manufacturer model number etc.

Since these components of smart phones are generally tightly integrated and not replaceable the amount and variety of unique data within a smart phone that can be used to generate a unique digital fingerprint is greatly reduced relative to older device architectures. In addition since it is not expected that smart phone components will ever be replaced there is less support for access to detailed information about the components of smart phones even if such information exists.

Accordingly it is much more difficult to assure that digital fingerprints of smart phones and similar portable personal computing devices such as tablet devices are unique. What is needed is a way to uniquely identify individual devices in large populations of homogeneous devices.

In accordance with the present invention a device authentication server authenticates a remotely located device using data representing pixel irregularities of a display of the device. Some LED monitors allow pixels to be read such that data representing the color actually shown by the pixels can be obtained. By writing test data to each pixel and reading the color displayed by the pixel hot and dead sub pixels can be identified. Since each display will deteriorate in a unique and randomized way a unique mapping of pixel irregularities of a display of a device will be unique.

By combining unique map of pixel irregularities of a display of the remotely located device the device can be distinguished from similar devices when other attributes alone are insufficient to uniquely identify the device.

For registration for subsequent authentication of the device the device provides the device authentication server with data representing a relatively complete set of pixel irregularities sometimes referred to as pixel irregularity data that the device retrieves from the display. The device authentication server stores this data and uses it subsequently as reference pixel irregularity data.

In subsequent authentication of the device the device authentication server sends a device key challenge to the device. The device key challenge specifies a randomized selection of device attribute parts to be collected from the device and the manner in which the device attribute parts are to be combined to form a device key. The device key is data that identifies and authenticates the device and includes a device identifier and pixel irregularity data.

The device authentication server authenticates the device when the device identifier of the device key identifies the device and the pixel irregularity data is consistent with the reference pixel irregularity data.

In accordance with the present invention a device authentication server authenticates a computing device using data representing pixel irregularities of a display of device . Pixel irregularities include dead pixels hot pixels and stuck pixels. These pixel irregularities differ between even otherwise identical devices since pixel failure in displays is a relatively random event.

In most displays in use today a pixel is instructed to display a given color by writing three 3 bytes to the pixel one byte representing an amount of red one byte representing an amount of green and one byte representing an amount of blue. Such bytes are frequently represented in human readable form as six 6 hexadecimal digits the first two 2 representing a red value the middle two 2 representing a green value and the last two 2 representing a blue value. For example FF0000 represents fully bright red 00FF00 represents fully bright green and 0000FF represents fully bright blue.

While RGB color schemes are described herein it should be appreciated that other color schemes are amenable to device identification in the manner described herein.

Each pixel typically includes three 3 sub pixels one red one green and one blue each of which is controlled by a respective byte in an RGB color value. Dead pixels are pixels that appear black regardless of red green and blue RGB or other color values written to the pixel. In effect a dead pixel is a pixel that displays 000000 regardless of what RGB value is written to the pixel. Hot pixels are pixels that appear white i.e. display FFFFFF regardless of the RGB value written to the pixel.

Stuck pixels are pixels in which only one or more sub pixels are dead or hot. For example if a pixel has a dead red sub pixel the first byte of the displayed color will always be 00 regardless of the first byte of the RGB value written to the pixel writing 888888 to the pixel results in display of the color 008888 thus erroneously displaying a color with a hue that is less red than intended. Similarly if a pixel has a hot green sub pixel the second byte of the displayed color will always be FF regardless of the second byte of the RGB value written to the pixel writing 888888 to the pixel results in display of the color 88FF88 thus erroneously displaying a color with a hue that is more green than intended.

A stuck pixel can include three 3 failed pixels. For example if the red and blue sub pixels are dead and the green sub pixel is hot the pixel will display 00FF00 regardless of the RGB value written to the pixel and will therefore always display fully bright green giving the appearance of being stuck on green. In fact dead and hot pixels can be considered special cases of stuck pixels.

Such pixel irregularities result from failure of display hardware in which data storage cells for given sub pixels fail and become either fully on or fully off. Such hardware failures are due to IC or other digital logic hardware irregularities during manufacture and therefore happen largely randomly in the field. Accordingly a map of pixel irregularities for a given device can be unique even among nearly identical devices.

Device authentication system includes device a server and a device authentication server that are connected to one another through a wide area computer network which is the Internet in this illustrative embodiment. Device can be any of a number of types of networked computing devices including smart phones tablets netbook computers laptop computers and desktop computers. Server is a server that provides services to remotely located devices such as device but that is configured to require authentication of device prior to providing those services. Device authentication server is a server that authenticates devices sometimes on behalf of other computers such as server .

In this illustrative embodiment a map of pixel irregularities of device are combined with other attributes of device to uniquely identify and authenticate device . Such other attributes include hardware and system configuration attributes of device that make up an internal state of device . Device attributes are described briefly to facilitate understanding and appreciation of the present invention.

Known device record includes device attributes both of which are described in greater detail below. Each device attribute includes an identifier and a value . Other than maps of pixel irregularities examples of device attributes of device include a serial number of a storage device within device and detailed version information regarding an operating system executing within device . In the example of a serial number of a storage device identifier specifies the serial number of a given storage device such as C or dev sda1 as the particular information to be stored as value and value stores the serial number of the given storage device of device .

In the example of maps of pixel irregularities value will be in the form of pixel map that is described in greater detail below in the context of registration of device for subsequent authentication.

For subsequent authentication of device registration in the manner illustrated in transaction flow diagram retrieves tag data from device .

In step device sends a request for registration to device authentication server . The request can be in the form of a URL specified by the user of device using a web browser executing in device and conventional user interface techniques involving physical manipulation of user input devices . Web browser and user input devices and other components of device are described in greater detail below.

The request sent to device includes content that causes web browser of device to gather attribute data representing hardware and other configuration attributes of device . In one embodiment a web browser plug in is installed in device and invoked by web browser processes the content of the web page to gather the attribute data in step . In other embodiments the attribute data can be gathered in step by other forms of logic of device such as DDK generator installed in device . The various elements of device and their interaction are described more completely below.

The content that causes web browser of device to gather attribute data representing hardware and other configuration attributes of device includes extraction logic for each of the attributes web browser is to gather. In an alternative embodiment DDK generator already includes extraction logic for all attributes and device receives data identifying the particular attributes requested by device authentication server . Extraction logic defines the manner in which a client device is to extract data to be stored as value of device attribute .

In step device writes test pixel data to each and every pixel of an LED monitor reads the data stored by each pixel and compares the data written to the data read to identify failed sub pixels. For example device can write RGB values in which no byte is either FF or 00 and determining which sub pixels store sub pixel values that are either FF or 00 . RGB values of AAAAAA and 555555 have alternating 0 and 1 bits and are good candidates for RGB values to use for testing for sub pixel irregularities. Alternatively device can test separately by writing FFFFFF and 000000 to each pixel in separate passes. Writing FFFFFF to a pixel can test for dead sub pixels and writing 000000 to a pixel can test for hot sub pixels.

While many displays do not support reading of pixel data displayed by the monitor some LED monitors currently support such reading. In the future reading of pixel data can be much more widely supported. In addition while only fully on and fully off sub pixels are described herein as pixel irregularities it should be appreciated that monitors can make detection of other irregularities available and can then be used for device identification in the manner described herein.

Since writing to pixels causes at least properly functioning pixels to change color writing and reading all pixels at once might produce a visible flash that could be annoying or confusing to the user. In some embodiments no more than a few pixels are written and read at any time. The particular pixels written to at any one time are spread widely throughout the display to avoid more than a single pixel flashing in any sizable area of the display at any time. Any visible artifacts of a few individual pixels flashing at a time are much less noticeable.

In one embodiment device represents the map of pixel irregularities in a pixel map that is generally of the form shown as pixel map . Pixel map includes a number of pixel records each of which represents a pixel irregularity. The particular pixel represented by pixel record is sometimes referred to as the subject pixel in the context of .

Irregularity represents the particular irregularity of the subject pixel. In this illustrative embodiment irregularity represents irregularity types for each sub pixel red green and blue. The irregularity types include dead hot and none. A dead pixel would be represented as red dead green dead and blue dead. A pixel in which only the blue sub pixel is hot would be represented as red none green none and blue hot. This can be represented in only six 6 bits each pair representing one of the three irregularities for a respective sub pixel e.g. 00 for none 01 for dead and 10 for hot the first two bits for red the second two bits for blue and the last 2 bits for green.

X and Y specify the particular location of the subject pixel in LED display . Thus X and Y uniquely identify the subject pixel.

As a whole pixel map represents a complete map of pixel irregularities of a given display. It should be appreciated that there are many ways to represent a map of pixel irregularities of a given display.

It is not necessary that the map be complete. However it is preferred that the particular representation of a map of pixel irregularities be one from which device authentication server can assess a rate of change in pixel irregularities overall over time. Sub pixels do not heal themselves. Accordingly over time a device s map of pixel irregularities should not show fewer irregularities or the absence of previously observed irregularities. In addition the observed rate of growth of pixel irregularities should increase within a range of reasonably expected rates of growth. The representation of a map of pixel irregularities should allow assessment of an observed rate of growth.

One example of such a representation gathered in step is illustrated by logic flow diagram . In step device writes test data to all pixels in the manner described above. In step device reads data stored at all pixels. As discussed above the writing and reading can be done in batches of less than the entirety of the display.

In step device divides the entirety of the read pixel data into areas of equal size. For example LED monitor is divided into 16 areas of equal size.

Loop step and next step define a loop in which device processes each of areas according to step . During each iteration of the loop of steps the particular area processed by device A is sometimes referred to as the subject area.

In step device builds an array specifying sub pixel irregularities in the subject area. shows illustrative examples of such arrays as arrays A C. In this illustrative example the test data written to all pixels in step is AAAAAA alternating 1s and 0s in binary. In array A data read from a given location of the subject area is AAAAAA and therefore contains no sub pixel irregularities. Such is represented in array A at a location corresponding to the given pixel location by R 0 G 0 and B 0 indicating no sub pixel irregularities wherein 0 indicates no irregularity. In array B data read from the given location of the subject area is 000000 and therefore represents a dead pixel. Such is represented in array B at a location corresponding to the given pixel location by R 1 G 1 and B 1 indicating three dead sub pixels wherein 1 indicates a dead sub pixel. In array C data read from the given location of the subject area is AA00FF and therefore represents a stuck pixel in which the green sub pixel is dead and the blue sub pixel is hot. Such is represented in array C at a location corresponding to the given pixel location by R 0 G 1 and B 2 indicating three dead sub pixels wherein 2 indicates a hot sub pixel.

After the subject array is built and represents any and all sub pixel irregularities of the subject area processing by device transfers through next step to loop step in which device processes the next area according to the loop of steps . When all areas have been processed according to step processing by device transfers from loop step to step .

In step device sums the arrays built in the multiple performances of step . Device sums arrays A C by summing the sub pixel values at corresponding locations and storing the summed values in a corresponding location in array . For example summing the sub pixel values of arrays A C described above the sub pixel values for the same location within array is R 1 G 2 B 3.

In step device encodes array in a lossless image format. Array is already in a form that can readily be represented as a bitmap image. However a number of losslessly compressed image formats are known and can be used to represent array using significantly less data. Lossless compression preserves all pixel data perfectly such that it can be retrieved after decompression. In this illustrative example of such a losslessly compressed image format is the known PNG portable network graphics format. After step processing according to logic flow diagram and therefore step completes.

The result is that pixel map is in the form of a PNG image and is therefore lightweight for transportation through computer networks. It is preferred that the number of areas of equal size is limited in number to no more than 128. Accordingly the sum of sub pixel states 0 2 in value will never exceed the maximum value of a sub pixel 256 FF in hexadecimal .

In this illustrative embodiment device in particular web browser plug in or DDK generator encrypts the attribute data using a public key of device authentication server and public key infrastructure PKI in step thereby encrypting the attribute data such that it can only be decrypted by device authentication server .

In step device authentication logic of device authentication server creates a device registration record for device from the received attribute data. Device authentication server creates a device registration record in the form of known device record for device by creating a globally unique identifier for device as device identifier and storing the values of the respective attributes including the tag data received in step as value in respective device attributes . Known device record is described more completely below in greater detail.

In step device authentication server sends a report of successful registration to device providing device identifier of device for subsequent identification. After step processing according to transaction flow diagram completes and device is registered for subsequent authentication with device authentication server .

Known device record is a registration record and in this illustrative example represents registration of device . Known device record includes a device identifier and a number of device attributes which are described briefly above. Each device attribute includes an identifier specifying a particular type of information and a value representing the particular value of that type of information from device . For example if identifier specifies a serial number of a given storage device value stores the serial number of that storage device within device . Similarly if identifier specifies pixel irregularities for a display of device value stores data representing the map of pixel irregularities.

In this illustrative embodiment value stores the tag data in the form of pixel map or in a lossless image format as described above. In alternative embodiments value can store an abstraction of the pixel map. For example value can store a hash of the pixel map.

Device attribute also includes extraction logic comparison logic alert logic and adjustment logic . The particular device attribute represented by device attribute is sometimes referred to as the subject device attribute in the context of .

Extraction logic specifies the manner in which the subject device attribute is extracted by device . Logic flow diagram described above is an example of extraction logic for a map of pixel irregularities.

Comparison logic specifies the manner in which the subject device attribute is compared to a corresponding device attribute to determine whether device attributes match one another. An example of comparison logic is described more completely below in conjunction with logic flow diagram .

Alert logic can specify alerts of device matches or mismatches or other events. Examples of alert logic include e mail SMS messages and such to the owner of device and or to a system administrator responsible for proper functioning of device .

Adjustment logic specifies the manner in which the subject device attribute is to be adjusted after authentication. For example if the map of pixel irregularities received for authentication indicates further pixel deterioration greater irregularities than indicated by the map of pixel irregularities already stored in value adjustment logic can cause value to be updated to store the newly received map of pixel irregularities.

Device attribute is shown to include the elements previously described for ease of description and illustration. However it should be appreciated that a device attribute for a given device can include only identifier and value while a separate device attribute specification can include extraction logic comparison logic alert logic and adjustment logic . In addition all or part of extraction logic comparison logic alert logic and adjustment logic can be common to attributes of a given type and can therefore be defined for the given type.

Transaction flow diagram illustrates the use of device authentication server to authenticate device with server .

In step device sends a request for a log in web page to server by which the user can authenticate herself. The request can be in the form of a URL specified by the user of device using web browser and conventional user interface techniques involving physical manipulation of user input devices .

In step server sends the web page that is identified by the request received in step . In this illustrative example the web page sent to device includes content that defines a user interface by which the user of device can enter her authentication credentials such as a user name and associated password for example.

In step web browser of device executes the user interface and the user of device enters her authentication credentials e.g. by conventional user interface techniques involving physical manipulation of user input devices . While the user is described as authenticating herself in this illustrative example it should be appreciated that device can be authenticated without also requiring that the user of device is authenticated.

In step device sends the entered authentication credentials to server . In this illustrative embodiment device also sends an identifier of itself along with the authentication credentials. Server authenticates the authentication credentials in step e.g. by comparison to previously registered credentials of known users. If the credentials are not authenticated processing according to transaction flow diagram terminates and the user of device is denied access to services provided by server . Conversely if server determines that the received credentials are authentic processing according to transaction flow diagram continues.

In step server sends a request to device authentication server for a session key using the device identifier received with the authentication credentials.

In response to the request device authentication server generates and cryptographically signs a session key. Session keys and their generation are known and are not described herein. In addition device authentication server creates a device key challenge and encrypts the device key challenge using a public key of device and PKI.

To create the device key challenge device authentication server retrieves the known device record representing device using the received device identifier and comparing it to device identifier . The device key challenge specifies all or part of one or more of device attribute to be included in the device key and is described in greater detail below.

In step device authentication server sends the signed session key and the encrypted device key challenge to server .

In step server sends a device authenticating page to device along with the device key challenge. The device authenticating page includes content that provides a message to the user of device that authentication of device is underway and content that causes device to produce a dynamic device key in the manner specified by the device key challenge.

The device key challenge causes web browser of device to generate a device identifier sometimes referred to herein as a dynamic device key DDK for device e.g. dynamic device key . In one embodiment a web browser plug in is installed in client device and invoked by web browser processes the content of the web page to generate the DDK. In other embodiments DDK of device can be generated by other forms of logic of device such as DDK generator which is a software application installed in device .

The device key challenge specifies the manner in which DDK is to be generated from the attributes of device represented in device attributes . The challenge specifies a randomized sampling of attributes of device allowing the resulting DDK to change each time device is authenticated. There are a few advantages to having DDK represent different samplings of the attributes of device . One is that any data captured in a prior authentication of device cannot be used to spoof authentication of device using a different device when the challenge has changed. Another is that since only a small portion of the attributes of device are used for authentication at any time the full set of attributes of device cannot be determined from one a few several or even many authentications of device .

The device key challenge specifies items of information to be collected from hardware and system configuration attributes of device and the manner in which those items of information are to be combined to form DDK . In this embodiment the challenge specifies one or more attributes related to pixel irregularity data of device .

To provide greater security DDK includes data representing the pixel irregularity data obfuscated using a nonce included in the challenge. While use of randomized parts of the pixel irregularity data precludes capture of any single DDK to be used in subsequent authentication use of the nonce thwarts collection of randomized parts of the pixel irregularity data over time to recreate enough of tag log to spoof authentication in response to a given challenge.

In step device gathers pixel irregularity data for inclusion in the DDK according to the device key challenge. In this illustrative embodiment device performs step in a manner analogous to that described above with respect to logic flow diagram FIG. .

Once DDK is generated according to the received device key challenge device encrypts DDK using a public key of device authentication server and PKI.

In step device sends the encrypted dynamic device key to server and server sends the encrypted dynamic device key to device authentication server in step .

In step device authentication logic of device authentication server decrypts and authenticates the received DDK. Step is shown in greater detail as logic flow diagram .

In step device authentication logic identifies device . In this illustrative embodiment the received DDK includes a device identifier corresponding to device identifier . Device authentication logic identifies device by locating a known device record in which device identifier matches the device identifier of the received DDK.

In test step device authentication logic determines whether device is identified. In particular device authentication logic determines whether a known device record with a device identifier matching the device identifier of the received DDK is successfully found in known device data . If so processing transfers to step . Otherwise processing transfers to step which is described below.

In step device authentication logic retrieves the known device record for the identified device e.g. device using the identifier determined in step .

In step device authentication logic authenticates the received DDK using the retrieved device record . Device authentication logic authenticates by applying the same device key challenge sent in step to the known device record that corresponds to the identified device. In this illustrative embodiment the device key challenge produces a DDK in which a portion of the DDK generated from non interactive attributes can be parsed from a portion generated from interactive attributes such that device can be authenticated separately from the user of device .

In test step device authentication logic determines whether the received DDK authenticates device by comparing the resulting DDK of step to the received DDK. In this illustrative embodiment device authentication logic uses comparison logic for each of the device attributes included in the device key challenge.

The portion of step in which device authentication logic determines whether the pixel irregularity portion of the dynamic device key matches is shown in greater detail as logic flow diagram .

In step device authentication logic determines the an amount by which the pixel irregularity data from the dynamic device key exceeds the reference pixel irregularity data from known device record .

In test step device authentication logic determines whether the amount determined in step is negative i.e. that the pixel irregularity data from the dynamic device key is less irregular than the reference pixel irregularity data from known device record . LED displays are presumed to not be able to heal accordingly device determines that the pixel irregularity data does not match if the amount is negative. Conversely if the amount is non negative processing transfers to test step .

In test step device authentication logic determines whether the amount determined in step exceeds a predetermined reasonable rate of deterioration. To make such a determination the reference pixel irregularity data from known device record is associated with a time stamp specifying when the reference pixel irregularity data was first stored in known device record . Accordingly device authentication logic can determine over what time span the pixel irregularities of device is reported to have grown.

If the amount determined in step exceeds the predetermined reasonable rate of deterioration device authentication logic determines that the pixel irregularity data does not match. Conversely if the amount determined in step does not exceed the predetermined reasonable rate of deterioration device authentication logic determines that the pixel irregularity data match.

In this illustrative embodiment the matching of the pixel irregularity data is not dispositive of whether the dynamic device key as a whole matches. Instead the match or lack thereof influences an overall estimated likelihood that device is in fact the device represented by known device record .

If the received DDK does not authenticate device processing transfers to step and authentication fails or alternatively to step in which device authentication logic sends another device key challenge to re attempt authentication. If the received DDK authenticates device processing transfers to step .

In step device authentication logic applies adjustment logic of each of device attributes uses to generate the received DDK. For example adjustment logic can specify that since device is authenticated device authentication logic incorporates the newly received pixel irregularity data into value . After step processing according to logic flow diagram and therefore step completes.

As described above authentication failure at either of test steps and transfers processing to step . In step device authentication logic determines that device is not authentic i.e. that authentication according to logic flow diagram fails.

In step device authentication logic logs the failed authentication and in step applies alert logic to notify various entities of the failed authentication. After step processing according to logic flow diagram and therefore step completes.

In step device authentication server sends data representing the result of authentication of device to server .

In step server determines whether to continue to interact with device and in what manner according to the device authentication results received in step .

Server computer is shown in greater detail in . Server includes one or more microprocessors collectively referred to as CPU that retrieve data and or instructions from memory and execute retrieved instructions in a conventional manner. Memory can include generally any computer readable medium including for example persistent memory such as magnetic and or optical disks ROM and PROM and volatile memory such as RAM.

CPU and memory are connected to one another through a conventional interconnect which is a bus in this illustrative embodiment and which connects CPU and memory to network access circuitry . Network access circuitry sends and receives data through computer networks such as wide area network .

A number of components of server are stored in memory . In particular web server logic and web application logic including authentication logic are all or part of one or more computer processes executing within CPU from memory in this illustrative embodiment but can also be implemented using digital logic circuitry.

Web server logic is a conventional web server. Web application logic is content that defines one or more pages of a web site and is served by web server logic to client devices such as device . Authentication logic is a part of web application logic that carries out device authentication in the manner described above.

Device authentication server is shown in greater detail in . Device authentication server includes one or more microprocessors collectively referred to as CPU memory a conventional interconnect and network access circuitry which are directly analogous to CPU memory conventional interconnect and network access circuitry respectively.

A number of components of device authentication server are stored in memory . In particular device authentication logic is all or part of one or more computer processes executing within CPU from memory in this illustrative embodiment but can also be implemented using digital logic circuitry. Known device data is data stored persistently in memory and includes known device records such as known device record for all devices that can be authenticated by device authentication logic . In this illustrative embodiment known device data is organized as all or part of one or more databases.

Device is a personal computing device and is shown in greater detail in . Device includes one or more microprocessors collectively referred to as CPU that retrieve data and or instructions from memory and execute retrieved instructions in a conventional manner. Memory can include generally any computer readable medium including for example persistent memory such as magnetic and or optical disks ROM and PROM and volatile memory such as RAM.

CPU and memory are connected to one another through a conventional interconnect which is a bus in this illustrative embodiment and which connects CPU and memory to one or more input devices output devices and network access circuitry . Input devices can include for example a keyboard a keypad a touch sensitive screen a mouse a microphone and one or more cameras. Input devices detect physical manipulation by a human user and in response to such physical manipulation generates signals representative of the physical manipulation and sends the signals to CPU . Output devices can include for example a display such as a liquid crystal display LCD and one or more loudspeakers. LED monitor is an LED monitor used to display visual data to the user. Network access circuitry sends and receives data through computer networks such as wide area network .

A number of components of device are stored in memory . In particular web browser operating system DDK generator and social networking application are each all or part of one or more computer processes executing within CPU from memory in this illustrative embodiment but can also be implemented using digital logic circuitry. As used herein logic refers to i logic implemented as computer instructions and or data within one or more computer processes and or ii logic implemented in electronic circuitry.

Web browser plug ins are each all or part of one or more computer processes that cooperate with web browser to augment the behavior of web browser . The manner in which behavior of a web browser is augmented by web browser plug ins is conventional and known and is not described herein.

Operating system is a set of programs that manage computer hardware resources and provide common services for application software such as web browser web browser plug ins and DDK generator . Operating system includes a monitor driver that communicates at a device level with LED monitor to write pixel data to and read pixel data from LED monitor .

Pixel map is data stored persistently in memory and each can be organized as all or part of one or more databases. Pixel map is generally of the structure of pixel map .

The above description is illustrative only and is not limiting. The present invention is defined solely by the claims which follow and their full range of equivalents. It is intended that the following appended claims be interpreted as including all such alterations modifications permutations and substitute equivalents as fall within the true spirit and scope of the present invention.

