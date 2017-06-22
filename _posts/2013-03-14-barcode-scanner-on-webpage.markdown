---

title: Barcode scanner on webpage
abstract: A hybrid electronic barcode reader application sharing the processes between document formats of the world wide web with associated native executables or hardware from a mobile device. The two disparate platforms exchange information between the mobile device and web page and allow the web page to operate device hardware to complete the application. The focus then returns to the originating web page.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08955739&OS=08955739&RS=08955739
owner: Best Buzz, LLC
number: 08955739
owner_city: Dallas
owner_country: US
publication_date: 20130314
---
The present invention is a useful and novel method for adding new barcode scanning capabilities to mobile landing pages. Mobile barcode scanners have previously been constrained to software applications associated and stored on the mobile device. Landing pages were unable to simulate the results of mobile barcodes scanners because they didn t have access to the hardware required.

Mobile landing pages or landing pages are a collection of images files data text links movies applications or clips located in a single address on the internet. Mobile landing pages are designed to detect the type of device including make and model and then setting the screen width to match the physical size of the device s screen. Mobile landing pages provide a variety of unique challenges for the developer including brevity of the copy on a single page legible text and images without zooming using only mobile friendly plug ins call friendly phone number using click to call map linked to address links are large enough to be thumb friendly with zooming favoring local content using geographic identification technologies and keeping fillable forms brief.

Applications tied to the webpage began to grow in popularity after Google s successful implementation of HTML5 based apps. The competitive advantage for web based application was the ability to expand audience reach and quickly issue version updates.

A native mobile application or app is software written for mobile devices that performs a specific task such as a barcode scanner game calculator music player etc The application is specifically designed to run on a device s operating system and machine firmware therefore an app must be adapted for different devices. Apps exploded in popularity in 2008 when Apple introduced the App Store. Apple solved many app development impediments by providing a standardized software development kit SDK to third party developers and then providing a built in billing feature through Apple iTunes.

Although not supported quantitatively native mobile applications are largely viewed as the more successful platform compared with web based applications. There are approximately five hundred thousand 500 000 native mobile applications currently offered today. However there are relatively poor statistics on the number of web apps for making a direct comparison.

As smartphone technology evolves two different camps of development have formed. One vision sees the development of web based applications as the future of mobile application development. Web applications can be developed without the restrictions inherent in native mobile application approval. Web applications also are platform independent so developers don t have the burden of writing the application in all the available operating systems. As of this writing there are a dozen different mobile operating systems. So writing to web based applications is cheaper faster and easier than native applications. However web applications have a perception problem with consumers. They view the web as place for a quick one time data feed. For repeated needs consumers turn to native applications.

Other developers believe the early trend of natively installed applications will maintain its dominance in how technology is delivered. Much of this opinion has to do with the significant resources already committed to the approach by developers. Updating a dozen platforms is seen as a given instead of an obstacle. Additionally current native programming allows for more sophisticated look feel and functionality than web based applications.

The New York Times pontificated on the conflict between the two development styles and declared THE Web is poised for a comeback. That may be an exaggeration of the rife between the camps but we believe new Hyper Text Markup Language HTML will blur the distinction to the consumer. Since they are both presented on the same mobile screen consumers will find it more and more difficult to differentiate between a native application and a web based application. This will lead marketers to ask if the current nature of web applications is more important than technology flashiness.

The ability to combine the mobile phone s hardware into landing page capabilities has been previously limited by operating system functionality carrier limitations and artificial technical restrictions adopted by application distributors. We anticipate we will see these restrictions soften and then finally fall away. This will provide new capabilities to streamline the interface between executables on a webpage and the required application hardware resources on the device.

There are limited examples of resource sharing by a mobile landing page and native applications on the mobile device. The two most common examples are related to mapping capabilities and the out call function of the telephone. For instance a user would perform an internet search for ABC Plumbing which returns a listing of various plumbing companies using the name. The search page may display a telephone number that can be dialed by clicking on the number and the user confirming they wish to call. The user may also find a similar phone on the landing page of the ABC Plumbing s website. Like the search engine the user only needs to click the phone number and confirm the desire to complete the call. When the call is ended the user remains in the phone application until they give the commands to toggle away.

Similarly a user can click on an address or map in the internet search page and be routed to one of three options 

In the third option the address is transferred to the local mapping application and the application is automatically launched. Like in the telephone example the user remains in the mapping application until they toggle away.

The addressable problem with these current implementation examples is the mobile landing page loses focus which is undesirable for marketers and developers. Marketers want to maintain the longest possible engagement with the end user. Not only is time spent on a mobile landing page a common measure of design success the mobile forum is a rare opportunity to engage a consumer without distracting outside advertising messages. So marketers are hesitant to send the consumer to an outside resource they don t control directly.

Passing data between mobile landing pages and native applications is inherently difficult and can lead to a skewing of the associated reporting data. For instance if a user were to click a link in a native social media application the application does not transmit the referral information to the web page. The webpage would read the referral as a direct hit to the website and dramatically skew critical metrics.

When passing data from the mobile landing page to the application there are several methods available to the programmer. For instance a session key is a single use alphanumeric string for encrypting communication within the same session. The purpose of the session key is two fold. First a session key is used to secure the communications between two computers or processors. Second the session key is transmitted with each subsequent communication to provide a cohesive string of communication.

An application programming interface API is a system of rules and regulations for passing data between two unrelated software programs. These APIs are a combination of the proprietary information encoded in a standardized format.

A characteristic of all the programming techniques for passing data is they comprise an alphanumeric string referred to as a session string in the present invention.

However what is missing in the data pass is the ability to swap information from the webpage to the native application and back to the webpage. Take the example of a car dealership with a mobile landing page showing inventory on a particular lot. A consumer shopping the lot notices a car they wish to investigate for more information. For this process to work in a desirable manner 

However steps and would not happen in the prior art. Instead the scanner may parse the information determine the brand and model of the VIN and route the consumer to a website that may be competitive with the owner of the originating mobile landing page. It may route the consumer automatically to a website preferred by the developer such as insurance or vehicle history websites. If the consumer was routed to the originating dealership through a web search it would likely happen by coincidence only. This then makes it undesirable for the dealership to use mobile barcode scanning technology on the mobile landing page. Instead the developers would have to explore less precise ways and less desirable ways for the consumer to find information on a vehicle on their lot.

All the previous designs for combining the resources of a mobile landing page with mobile device resources heretofore known suffer from a number of disadvantages 

When the mobile landing page links to a native application it is unable to force a return focus to the originating mobile landing page after the application s task is completed. So the mortgage consumer would be left in the calculator application until the user toggles back to the browser. This is a paramount concern of brand and website developers when considering if the landing page should use an outside application on the local mobile device.

An invention which meets the needs stated above is a system and method employing a native barcode scanning application or camera to add barcode scanning capabilities to a mobile landing page.

Accordingly besides the objects and advantages of the system for website calling a native application described above several objects and advantages of the present invention are 

Further objects and advantages of this invention will become apparent from a consideration of the drawings and the ensuing description of the drawings.

Turning to the logic flow chart depicts the software processes related to a landing page calling a predetermined barcode scanner application native on the device . The flow chart shows how the mobile landing page interacts with the device and mobile scanner application .

Starting on the left side of the flow chart the invention begins with an originating mobile landing page . This landing page comprises any webpage containing a scanner link originating the process of scanning a barcode . The landing page will have original content besides the scanner link . The content comprises text or images which may comprise a notice of scanner availability and directions on how to use the scanner .

The present invention is based on the originating mobile landing page offering a link to a barcode scanner . This barcode scanner link has the function of initiating the sequence of events to capture a barcode using a camera on a mobile device . In order to allow the user to access the scanner and then automatically return to the originating landing page the scanner link uses a session string generator to create a session string . The session string is an alphanumeric attribute string acting as a carrier of data and instructions for the entire communications session. The session string facilities the passing of information across the assortment of platforms software hardware and devices. The session string is not fixed and may add and subtract information from the string as it passed across the assorted hardware and software applications associated with scanning a barcode.

The session string generator first creates the session string comprising the address of the originating mobile landing page and a script . A first portion of the session string is the alphanumeric address of the originating mobile landing page which may be in the form of a uniform resource locator URL tiny URL domain name numeric internet protocol address or any other form of an address to a web location. The address of the originating mobile landing page allows the present invention to return the user to the originating mobile landing page after scanning of the barcode .

A second component generated by the session string generator is a script . A script is any alphanumeric string used to pass instructions and associated data from the mobile landing page to the barcode scanner or camera and then returned it back to the mobile landing page . In this figure we are passing the data to a barcode scanner application. In we will look at how the script works when calling a camera or camera application instead of the mobile barcode scanner application.

Therefore the data in the session string comprises the address of the originating mobile landing page and a script of instructions to the software and hardware components. It may also comprise a unique identifier such as an index of the entire communications session.

Once the session string generator creates the session string it is sent to the device where the script calls the scanner and then instructs the scanner to capture a barcode . The camera hardware is wrapped in software code that may be used to operated the camera hardware. In layman terms the script instructs the device and or mobile barcode scanner application to 

Capturing the barcode is completed by the mobile barcode scanner by using the device s camera . The remainder of the normal functions of the mobile barcode scanner such as retrieving a web page or running a price comparison are eliminated in the present invention. After passing the session string with the digitized barcode to the mobile landing page the application s role is complete.

The digitized barcode is generally executed by decoding the physical barcode into an alphanumeric sequence. However it can also be completed with a capture of a still or moving image. This second method would then require another program located on the originating mobile landing page to decode the image into the alphanumeric string.

This process then alters the session string by adding the digitized barcode information so the session string now comprises 

This session string is then passed back to the originating mobile landing page and the focus returns to the mobile landing page located in the session string . The landing page can further use the digitized barcode to perform an endless variety of functions such as 

Referring now to the logic flow chart demonstrates the software processes related to a mobile landing page calling a undetermined barcode scanner application native to the device .

While the figure differentiates the two platforms of landing page and device it should be further understood the image of the mobile landing page is displayed on the device .

The barcode scanner may be selected by the user the device s operating system or a combination of both.

In layman terms this additional step alters how the script instructs the device or mobile barcode scanner application to 

Finally turning to depicting the data movement between the originating mobile landing page and the device s camera or camera application .

In this embodiment the mobile landing page and the device still share resources but the barcode scanner application resides on the mobile landing page .

The mobile landing page will display the originating content and a scanner link . The content comprises text or images which may also comprise a notice of scanner availability and or directions on how to use the scanner .

The camera hardware would generally be wrapped with an application. However in one embodiment of the present invention the camera is directly operated by a scanner on the mobile landing page .

Once the scanner link is activated by the user the scanner is launched on the mobile landing page . The scanner initiates the session string generator to create the session string to pass to the camera . The session string would comprise a script to operate with the device s operating system and may also include the address of the originating mobile landing page .

The script activates the camera or camera application and then instructs the hardware device to scan the physical barcode and pass the digitized barcode to the originating mobile landing page . The script attaches the digital representation of the scanned barcode which may be the image of the barcode to the session string . The capture of the barcode by the camera produces an image or digitized barcode . The photographic image can be further processed on the device to produce a digital alphanumeric string of the data encoded in the barcode . If the photographic image is passed to the mobile landing page the image is further digitized to the encoded alphanumeric string at the mobile landing page . The script is responsible for providing the instructions to the camera and device to 

Benefits other advantages and solutions to problems have been described herein with regard to specific embodiments. However the advantages associated benefits specific solutions to problems and any element s that may cause any benefit advantage or solution to occur or become more pronounced are not to be construed as critical required or essential features or elements of any or all the claims of the invention. As used herein the terms comprises comprising or any other variation thereof are intended to cover a non exclusive inclusion such that a process method article or apparatus composed of a list of elements that may include other elements not expressly listed or inherent to such process method article or apparatus.

From the description above a number of advantages become evident for the Barcode Scanner on Webpage. The present invention provides all new benefits for participating parties including programmers advertisers and brand owners operating system developers and end users including 

