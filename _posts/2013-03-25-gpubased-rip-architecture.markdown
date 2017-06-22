---

title: GPU-based RIP architecture
abstract: A method of printing document data in page description language format using a plurality of graphics processing units. The plurality of tiles representing the document using the assigned graphics processing units are rendered in parallel with one another, and the rendered tiles are transmitted, bypassing the central processing units, from each of the graphics processing units to a corresponding one of a plurality of print head controllers, with the rendered tiles transmitted at a higher frequency than a frequency at which the plurality of tiles is output from each print head controller. The rendered tiles are repeatedly transmitted until each print head controller completes output of the previous band.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09152894&OS=09152894&RS=09152894
owner: Canon Kabushiki Kaisha
number: 09152894
owner_city: Tokyo
owner_country: JP
publication_date: 20130325
---
This application claims the benefit under 35 U.S.C. 119 of the filing date of Australian Patent Application No. 2012201865 filed 29 Mar. 2012 hereby incorporated by reference in its entirety as if fully set forth herein.

The current invention relates to the field of raster image processing for high speed digital printing presses.

Increasing speed of digital printers has created a need for matching high speed RIP Raster Image Processing systems. An RIP system converts Page Description Language PDL data such as Portable Document Format PDF developed by Adobe Systems Inc. or XPS developed by Microsoft Corporation into pixel data that can be used as input to a digital printer.

Traditionally RIP systems have utilized general purpose processors CPUs or custom hardware. Recently Graphics Processing Units GPUs originally designed for 3D rendering applications such as computer games and computer aided design CAD have become very powerful and provide much higher performance to price ratio than general purpose CPUs. A RIP system built with GPUs may be cheaper than an equivalently performing CPU based system.

There are several existing examples of using GPUs in RIP systems. These existing systems typically comprise a host system containing a CPU a main memory and one or more GPU cards connected by a peripheral bus such as PCI e. Each GPU card contains a graphics processing unit GPU a memory and one or more video output interfaces for connecting display devices. In one known GPU based RIP system pixels rendered on a GPU are transferred back to host system main memory where additional colour processing may be performed by a general purpose processor CPU . In alternative known systems rendered pixels are transferred from memory associated with a GPU to a printer via another device connected to a peripheral bus such as for example a PCI e network card. Transferring the pixel data from GPU to main memory and from main memory to another device may require more bandwidth than such a peripheral bus can provide. In this case the GPUs will not be used to their full potential due to the bottleneck of output bandwidth from the transfer to the CPU or a network interface.

One known system addresses the above problem by compressing pixel data before sending the compressed pixel data across a peripheral bus. Although the data transfer time may be reduced the extra time required for compression data transfer and decompression negates the benefit.

It is an object of the present invention to substantially overcome or at least ameliorate one or more disadvantages of existing arrangements.

According to a first aspect of the present disclosure there is provided a method of rendering a document data in page description language format using a plurality of graphics processing units via video interface said method comprising 

converting the document data to a set of rendering commands corresponding to a plurality of bands using at least one central processing unit wherein each of the plurality of bands includes a plurality of tiles and each of the tiles included in a band is associated with one of a plurality of swathes 

assigning each of the plurality of tiles to one of the plurality of graphics processing units in accordance with a swathe associated with each of the plurality of tiles 

rendering the plurality of tiles representing the document using the assigned graphics processing units in parallel with one another 

transmitting the rendered tiles from each of the graphics processing units to a corresponding one of a plurality of print head controllers bypassing the central processing units wherein the rendered tiles are transmitted at a higher frequency than a frequency at which the plurality of tiles is output from each print head controller and the rendered tiles are repeatedly transmitted until each print head controller completes output of the previous band and

outputting from each of the print head controllers the rendered tiles forming a complete band for printing the rendered tiles.

According to still another aspect of the present disclosure there is provided a system for printing document data in page description language format using a plurality of graphics processing units via a video interface said system comprising 

a processor coupled to said memory for executing said computer program said computer program comprising instructions for 

converting the document data to a set of rendering commands corresponding to a plurality of bands using at least one central processing unit wherein each of the plurality of bands includes a plurality of tiles and each of the tiles included in a band is associated with one of a plurality of swathes 

assigning each of the plurality of tiles to one of the plurality of graphics processing units in accordance with a swathe associated with each of the plurality of tiles 

rendering the plurality of tiles representing the document using the assigned graphics processing units in parallel with one another 

transmitting the rendered tiles from each of the graphics processing units to a corresponding one of a plurality of print head controllers bypassing the central processing units wherein the rendered tiles are transmitted at a higher frequency than a frequency at which the plurality of tiles is output from each print head controller and the rendered tiles are repeatedly transmitted until each print head controller completes output of the previous band and

outputting from each of the print head controllers the rendered tiles forming a complete band for printing the rendered tiles.

According to still another aspect of the present disclosure there is provided a non transitory computer readable medium having a computer program stored thereon for printing document data in page description language format using a plurality of graphics processing units said program comprising 

code for converting the document data to a set of rendering commands corresponding to a plurality of bands using at least one central processing unit wherein each of the plurality of bands includes a plurality of tiles and each of the tiles included in a band is associated with one of a plurality of swathes 

code for assigning each of the plurality of tiles to one of the plurality of graphics processing units in accordance with a swathe associated with each of the plurality of tiles 

code for rendering the plurality of tiles representing the document using the assigned graphics processing units in parallel with one another 

code for transmitting the rendered tiles from each of the graphics processing units to each of a corresponding one of a plurality of print head controllers bypassing the central processing units wherein the rendered tiles are transmitted at a higher frequency than a frequency at which the plurality of tiles is output from each print head controller and the rendered tiles are repeatedly transmitted until each print head controller completes output of the previous band and

code for outputting from each of the print head controllers the rendered tiles forming a complete band for printing the rendered tiles.

Where reference is made in any one or more of the accompanying drawings to steps and or features which have the same reference numerals those steps and or features have for the purposes of this description the same function s or operation s unless the contrary intention appears.

A GPU based RIP computer system is described below with reference to . The computer system may be used for implementing printing methods as described below.

The system comprises a Graphics Processing Unit GPU card configured within a computer module . As seen in the GPU card comprises a memory unit . The memory unit is typically formed from semiconductor random access memory RAM . The GPU card also comprises a video interface .

The computer module is connected to an associated print controller configured within a printer . The computer module is also connected via a network card to an engine controller of the print controller . The print controller also comprises a video receiver .

GPU cards used with conventional software applications e.g. games and computer aided design CAD transfer rendered pixels directly to a display device via a standard video interface such as the Digital Video Interface DVI D standard developed by the Digital Display Working Group DDWG or DisplayPort developed by the Video Electronics Standards Association VESA .

A video interface such as the video interface associated with the GPU card may be configured to continuously transmit an image held in the memory of the GPU card . The image is typically transmitted at a fixed rate e.g. a refresh rate of video display device and at a resolution that the GPU card allows. An area of the memory where the transmitted image is held is called a frame buffer .

An audio video interface connects the computer module to a video display . The audio video interface may be embedded for example in another GPU card.

The computer system described here may be configured to perform double buffering . The GPU card in the computer system comprises two frame buffers which may be configured within memory . The GPU card renders into a first one of the frame buffers while a second one of the frame buffers is read by the video receiver of the print controller . Once the GPU card has finished rendering a frame roles of the two frame buffers are swapped. In particular the first frame buffer is read by the video receiver of the print controller and the GPU card begins rendering into the recently output second frame buffer.

The computer system may also be configured to perform an additional synchronization function called Vsync where the CPU stops the frame buffers from being swapped while one of the frame buffers is being read by the video receiver .

Double buffering and Vsync may be used by the computer system to avoid transmitting incomplete images.

The GPU card transmits contents of one of the frame buffers to video receiver of the print controller at a fixed video rate regardless of whether content within the frame buffer has changed. Rendered image tiles are transmitted to a spool or frame buffer of the print controller at a higher frequency rate than the frequency rate at which contents of the spool is output from the print controller .

The computer system may be configured so as to respond to an external signal indicating when an image should be captured and transmitted to the video receiver of the printer . The external signal may be triggered by pressing a button for example on keyboard . Alternatively the external signal may be triggered by an HTTP command received on network interface .

The size of an image stored in one of the frame buffers configured within the memory may be smaller than a typical print image size. The computer system may be configured to render printable images in tiles where each tile is small enough to fit into one of the frame buffers configured within memory . The image or the content in one of the frame buffers of the memory may be referred to as a frame .

As seen in the printer typically includes at least one processor unit CPU and a memory unit . The memory unit typically has semiconductor random access memory RAM and semiconductor read only memory ROM . The CPU memory and print controller of the printer typically communicate via an interconnected bus . The print controller comprises the video receiver for receiving input image data and a spool for queuing the received image data. The print controller also comprises controllers collectively referred to as an engine controller for performing various electromechanical or electro photographic functions of the printer e.g. marking and transporting paper . The print controller also comprises a print head controller for controlling a print head of the printer . The engine controller and print head controller may be collectively be referred to as a print engine . In one implementation the print engine is a high speed high volume press print engine.

As seen in the computer system comprises the computer module to which may be connected user input devices such as the keyboard and a mouse pointer device and output devices including the printer and the display device for local user feedback. An external Modulator Demodulator Modem transceiver device may be used by the computer module for communicating to and from a communications network via a connection . The communications network may be a wide area network WAN such as the Internet a cellular telecommunications network or a private WAN. Where the connection is a telephone line the modem may be a traditional dial up modem. Alternatively where the connection is a high capacity e.g. cable connection the modem may be a broadband modem. A wireless modem may also be used for wireless connection to the communications network . A PDL print job may be delivered to the computer module via the network .

The computer module typically includes at least one processor unit CPU and the memory unit . The CPU is typically a multi processor device having multiple cores for execution of a plurality of threads in a distributed manner permitting accelerated processing. The memory unit typically has semiconductor random access memory RAM and semiconductor read only memory ROM .

The computer module also includes a number of input output I O interfaces including the audio video interface and the video interface of the GPU card that couple to the video display and to the video receiver of the printer respectively.

The computer module also includes an I O interface card comprising an I O interface that couples to the keyboard mouse or other human interface device not illustrated .

As described above the network interface is connected to the engine controller . In some implementations the modem may be incorporated within the computer module for example within the network card .

The computer module also comprises a local network interface card comprising a local network interface which permits coupling of the computer system via a connection to a local area communications network known as a Local Area Network LAN . PDL print jobs for the printer may be provided to the computer system via the network . As illustrated in the local communications network may also couple to the wide network via a connection which would typically include a so called firewall device or device of similar functionality. The local network interface of the network card may comprise an Ethernet circuit card a Bluetooth wireless arrangement or an IEEE 802.11 wireless arrangement however numerous other types of interfaces may be practiced for the interface .

The interfaces and may afford either or both of serial and parallel connectivity the former typically being implemented according to the Universal Serial Bus USB standards and having corresponding USB connectors not illustrated . Storage devices are provided and typically include a hard disk drive HDD . Other storage devices such as a floppy disk drive and a magnetic tape drive not illustrated may also be used. An optical disk drive is typically provided to act as a non volatile source of data. Portable memory devices such optical disks e.g. CD ROM DVD Blu ray Disc USB RAM portable external hard drives and floppy disks for example may be used as appropriate sources of data to the system .

The components to of the computer module typically communicate via an interconnected bus and in a manner that results in a conventional mode of operation of the computer system known to those in the relevant art. For example the CPU is coupled to the system bus using a connection . Likewise the memory and optical disk drive are coupled to the system bus by connections . Examples of computer platforms on which the described arrangements can be practised include IBM PC s and compatibles Sun Sparcstations Apple Mac or a like computer systems.

One or more steps of the printing methods to be described may be implemented using the computer system wherein the processes of may be implemented as one or more software application programs executable within the computer system . In particular the printing methods can be effected by instructions see in the software that are carried out within the computer system . The software instructions may be formed as one or more code modules each for performing one or more particular tasks. The software may also be divided into two separate parts in which a first part and the corresponding code modules performs the printing methods and a second part and the corresponding code modules manage a user interface between the first part and the user.

One or more of the components to described here may also be implemented as one or more software code modules of the software application programs executable within the computer system .

The software may be stored in a computer readable medium including the storage devices described below for example. The software is loaded into the computer system from the computer readable medium and then executed by the computer system . A computer readable medium having such software or computer program recorded on the computer readable medium is a computer program product. The use of the computer program product in the computer system preferably effects an advantageous apparatus for high speed printing.

The software is typically stored in the HDD or the memory . The software is loaded into the computer system from a computer readable medium and executed by the computer system . Thus for example the software may be stored on an optically readable disk storage medium e.g. CD ROM that is read by the optical disk drive . A computer readable medium having such software or computer program recorded on it is a computer program product. The use of the computer program product in the computer system preferably effects an apparatus for high speed printing.

In some instances the application programs may be supplied to the user encoded on one or more CD ROMs and read via the corresponding drive or alternatively may be read by the user from the networks or . Still further the software can also be loaded into the computer system from other computer readable media. Computer readable storage media refers to any non transitory tangible storage medium that provides recorded instructions and or data to the computer system for execution and or processing. Examples of such storage media include floppy disks magnetic tape CD ROM DVD Blu ray Disc a hard disk drive a ROM or integrated circuit USB memory a magneto optical disk or a computer readable card such as a PCMCIA card and the like whether or not such devices are internal or external of the computer module . Examples of transitory or non tangible computer readable transmission media that may also participate in the provision of software application programs instructions and or data to the computer module include radio or infra red transmission channels as well as a network connection to another computer or networked device and the Internet or Intranets including e mail transmissions and information recorded on Websites and the like.

The second part of the application programs and the corresponding code modules mentioned above may be executed to implement one or more graphical user interfaces GUIs to be rendered or otherwise represented upon the display . Through manipulation of typically the keyboard and the mouse a user of the computer system and the application may manipulate the interface in a functionally adaptable manner to provide controlling commands and or input to the applications associated with the GUI s . Other forms of functionally adaptable user interfaces may also be implemented such as an audio interface utilizing speech prompts output via the loudspeakers not shown and user voice commands input via the microphone .

When the computer module is initially powered up a power on self test POST program executes. The POST program is typically stored in a ROM of the semiconductor memory of .

A hardware device such as the ROM storing software is sometimes referred to as firmware. The POST program examines hardware within the computer module to ensure proper functioning and typically checks the CPU the memory and a basic input output systems software BIOS module also typically stored in the ROM for correct operation. Once the POST program has run successfully the BIOS activates the hard disk drive of . Activation of the hard disk drive causes a bootstrap loader program that is resident on the hard disk drive to execute via the CPU . This loads an operating system into the RAM memory upon which the operating system commences operation. The operating system is a system level application executable by the CPU to fulfil various high level functions including processor management memory management device management storage management software application interface and generic user interface.

The operating system manages the memory to ensure that each process or application running on the computer module has sufficient memory in which to execute without colliding with memory allocated to another process. Furthermore the different types of memory available in the system of must be used properly so that each process can run effectively. Accordingly the aggregated memory is not intended to illustrate how particular segments of memory are allocated unless otherwise stated but rather to provide a general view of the memory accessible by the computer system and how such is used.

As shown in the CPU includes a number of functional modules including a control unit an arithmetic logic unit ALU and a local or internal memory sometimes called a cache memory. The cache memory typically include a number of storage registers in a register section. One or more internal busses functionally interconnect these functional modules. The CPU typically also has one or more interfaces for communicating with external devices via the system bus using a connection . The memory is coupled to the bus using a connection .

The application program includes a sequence of instructions that may include conditional branch and loop instructions. The program may also include data which is used in execution of the program . The instructions and the data are stored in memory locations and respectively. Depending upon the relative size of the instructions and the memory locations a particular instruction may be stored in a single memory location as depicted by the instruction shown in the memory location . Alternately an instruction may be segmented into a number of parts each of which is stored in a separate memory location as depicted by the instruction segments shown in the memory locations and .

In general the CPU is given a set of instructions which are executed therein. The CPU waits for a subsequent input to which the CPU reacts to by executing another set of instructions. Each input may be provided from one or more of a number of sources including data generated by one or more of the input devices data received from an external source across one of the networks data retrieved from one of the storage devices or data retrieved from a storage medium inserted into the corresponding reader all depicted in .

The execution of a set of the instructions may in some cases result in output of data. Execution may also involve storing data or variables to the memory .

The disclosed arrangements use input variables which are stored in the memory in corresponding memory locations . The disclosed arrangements produce output variables which are stored in the memory in corresponding memory locations . Intermediate variables may be stored in memory locations and .

Referring to the CPU of the registers the arithmetic logic unit ALU and the control unit work together to perform sequences of micro operations needed to perform fetch decode and execute cycles for every instruction in the instruction set making up the program . Each fetch decode and execute cycle comprises 

Thereafter a further fetch decode and execute cycle for the next instruction may be executed. Similarly a store cycle may be performed by which the control unit stores or writes a value to a memory location .

Each step or sub process in the processes of is associated with one or more segments of the program and is performed by the register section the ALU and the control unit in the CPU working together to perform the fetch decode and execute cycles for every instruction in the instruction set for the noted segments of the program .

One or more steps of the methods to be described may also be implemented using the printer wherein one or more steps of the processes of may be implemented as one or more software application programs executable within the printer . The software application programs are executed in a similar manner to execution of the application programs executable within the computer module .

As described above the print engine i.e. comprising the engine controller and print head controller may be a high speed high volume press print engine. In one implementation the print engine of the printer may be a high speed press print engine of a type referred to as a web fed digital press . In a web fed digital press paper passes through the print engine in a continuous sheet called a web. The paper enters the print engine from a roll passes through the print engine and exits on to another roll or into finishing equipment such as a cutter and folder.

The GPU card connects to the print controller via the video interface bypassing the CPU . As described above the print controller comprises the video receiver the spool the engine controller and the print head controller . The print controller is connected to the network interface via a connection which provides a bidirectional communication channel. The print head controller may communicate with the GPU card via the bidirectional communication channel . The engine controller indicates to the print head controller how much ink from each print head e.g. and should be released at a certain time and at a certain position on a piece of paper.

In the GPU based RIP computer system the document data in page description language format is converted to three dimensional 3D drawing commands by an Application Programming Interface such as the Open Graphics Library OpenGL standard specification. Such an application programming interface may be implemented as one or more software code modules of the software application program being executed by the CPU . OpenGL is a standard specification defining a cross language cross platform API for writing applications that produce 2D and 3D computer graphics. OpenGL defines over two hundred and fifty 250 different function calls which may be used to draw complex three dimensional scenes from simple primitives.

Three dimensional 3D drawing commands generated on the computer system are rendered on the GPU card . Additional processing such as colour conversion and halftoning may also be performed on the GPU card using OpenGL shaders or a general purpose GPU compute language such as OpenCL.

OpenCL is a framework for writing programs that execute across heterogeneous platforms consisting of CPUs GPUs and other processors. OpenCL includes a language based on the ISO IEC 9899 1999 version of the C programming language standard or C99 for writing kernels i.e. functions that execute on OpenCL devices plus APIs that are used to define and then control platforms. OpenCL provides parallel computing using task based and data based parallelism.

The video interface in the GPU card transmits rendered images at a constant video rate regardless of whether the frame buffer configured within the memory has been updated or not. The video rate may be significantly higher than the rate at which the contents of the frame buffer are printed by the system . If the system does not update and swap the frame buffers fast enough duplicate images will be transmitted. The time taken to render drawing commands e.g. OpenGL or other GPU graphic rendering APIs depends on the number and complexity of drawing commands so it is difficult to ensure that the frame buffers of the GPU card are always swapped in time.

The print controller is configured to discard duplicate images. The video receiver may receive additional information identifying which image is to be printed and which image is a duplicate.

The metadata includes at least an identification number or attribute of a frame or an image in the frame buffer. The system embeds a different identification number for each frame of a tile that is swapped into the frame buffer of the GPU card . The video receiver checks the identification number or attribute of each image received directly from the GPU card bypassing the CPU . If the identification number or attribute is different from the image before then the image is added to the spool otherwise the image is discarded. The metadata also includes a band identification number band ID to specify which band each rendered tile is located in.

The metadata includes the size of the image bit depth number of colour channels and the position of a tile in a full print image.

Video interfaces typically only support image formats suitable for display devices such as RGB Red Green Blue with twenty four 24 or thirty 30 bits per pixel. Printers typically use CMYK Cyan Magenta Yellow or Black image format with four 4 or eight 8 bits per pixel. In the case of spot colours additional channels may be used. As the print image has the print format the video receiver uses the metadata to interpret the received image in the correct format.

The video receiver assembles tile images received from the GPU card directly bypassing the CPU into a full print image or print band in the spool . The engine controller is signalled when all the tiles of a print image or a print band are received and the print image or print band is complete.

To ensure each rendered image is sent to the printer the system waits for at least one refresh period before swapping content of the frame buffers and also checks that the video receiver has not asserted that the spool is full and cannot receive more image data. The refresh period is also referred to as wait time for swapping the frame buffers.

Conventional video interfaces carry information in one direction. Thus for such conventional video interfaces the process of communicating between a GPU card such as the GPU card and a video receiver such as the video receiver is not possible. Therefore the print controller comprising the video receiver as seen in has a connection which provides an additional bidirectional communication channel between the computer module and the print controller . Such a bidirectional communication channel may be used to signal to the system when the spool is full and is unable to receive any more image data.

Some video interface standards such as DisplayPort have a low bandwidth bidirectional communication channel. However such a channel is only available to a graphics driver and is not capable of carrying notification messages that a spool e.g. the spool is full and cannot receive any more image data.

In another implementation the computer module comprises a plurality of GPU cards which may be configured to communicate with each other. Data on one GPU card may be transferred to another GPU card in rendering images. In such an arrangement a parallel computing architecture such as Compute Unified Device Architecture CUDA version 4 and above and GPUDirect v2.0 may be used to support Peer to Peer communication. Alternatively scalable link interface SLI technology may be used to allow multiple GPU cards to render a tile. For example half of such a tile may be rendered on a master GPU card and the other half of the tile may be rendered on a slave GPU card. A resulting rendered image from the slave GPU card may be sent to the master GPU card which combines two half images into one image and then outputs the combined image to the frame buffer. Such an architecture may be used for synchronising a plurality of tiles associated with a complete swathe with one another. The complete swathe may be divided into the plurality of tiles and hence the plurality of tiles is associated with the complete swathe.

CUDA is an architecture developed to provide developers access to a virtual instruction set and memory of parallel computational elements on GPUs. Using CUDA the GPU cards become accessible for general purpose computation like CPUs. Unlike CPUs however GPU cards have a parallel throughput architecture that emphasizes executing many concurrent threads slowly rather than executing a single thread very quickly. Such parallel throughput architecture may be utilized in the rendering of the image tiles in parallel with one another giving the unique advantage of fast rendering. Image rendering in CUDA may use different rendering pipeline to the OpenGL s rendering pipeline. CUDA also provides several advantages including 

Data transfer between GPU cards may be direct via GPUDirect or SLI hardware. Such GPUDirect or SLI hardware may be used for load balancing.

In an implementation comprising a plurality of GPU cards a tile may be dynamically assigned to a least busy GPU card for rendering and the rendered pixels transferred to another GPU card that associates to a targeted swathe of the tile. For example a tile to be printed in swathe one 1 may be sent to GPU card two 2 for rendering but rendered pixels of the tile are transferred back to GPU card one 1 and then passed to a corresponding swathe controller.

The allocation of a GPU card which does not belong to the swathe associated with the tile needs to be handled carefully. The data transfer time needs to be included for the total rendering time. For example the GPU cards may be allocated as described above when total time of tile rendering on GPU card two 2 plus the pixel data transfer time from GPU card two 2 to GPU card one 1 is less than the total time of waiting time on GPU card one 1 and tile rendering time on GPU card one 1 .

A method of receiving an image will be described in detail below with reference to . The method may be implemented as one or more code modules of the software application program resident in memory of the printer and being controlled in its execution by the print controller under execution of the CPU .

The method begins at image receiving step where a new image is received by the video receiver at a video rate which is a rate higher than the rate at which contents of one of the frame buffers configured within memory is printed by the system .

In one implementation the image received at step is a rendered tile of a page to be printed by the print controller . Tiles are constituted to form a print image band which spans the width of the page. Each of the images received at step has additional information in the form of an associated identification number or attribute which uniquely identifies the image or frame as described above. For example the identification number combines the band identification and tile identification numbers.

At comparing step the print controller under execution of the CPU is used to compare the identification number associated with the image received at step against the identification number of a previously received image. If the print controller determines that the identification numbers or attributes are different then the image is added to the spool configured within memory in spooling step . Otherwise the received image is discarded in discarding step .

In checking step the print controller determines if the image received at step completes a print image band . If the received image completes a print image band then the engine controller is notified in signalling step that the spool contains data that is ready to be printed. A print image band is completed when all the tiles that constitute the band have been received by the print controller and stored in the spool . However if the spool is determined to be full in decision step then the method proceeds to step .

At asserting step the video receiver asserts a full signal and ignores any received images until the engine controller releases some data from the spool in releasing step . The full signal may be asserted at step by modifying for example a full flag stored within the memory . The full signal is sent to the computer module by the engine controller .

When data has been released from the spool at step the CPU clears the asserted full signal at clearing step . In this instance the video receiver transmits a signal to the computer module indicating that the print controller may receive images again. The signal transmitted by the video receiver at step is transmitted to the computer module via the engine controller and the connection . Following step the method may be executed again for a next print image band.

Alternatively steps and of the method may be replaced with print flow control steps and as shown in . In particular when the spool is determined to have reached a water mark at decision step the method may proceed to step instead of step .

As seen in at determining step the CPU determines an estimated waiting time to release the rendered tiles from the spool . The estimated waiting time may be determined based on an image receiving rate in the video receiver a printing rate in print head controller and or a spool size in spool . Other factors may also be used to determine the estimated waiting time at step . Following step the method concludes at wait signal step where the CPU sends a wait signal together with the estimated wait time to the CPU .

A method of rendering an image tile will be described in detail below with reference to . One or more steps of the method may be implemented as one of more software code modules of the software application program resident in the hard disk drive and being controlled in its execution by the CPU .

The method begins at setting step where the CPU sets an initial wait time. The initial wait time may be longer than the video refresh period and is set up for a rendered tile being swapped to the frame buffer configured within the memory and the content of the frame buffer is received by the video receiver . The initial wait time is the period between two Vsync synchronization functions plus some overhead.

At assigning step the CPU assigns and sends commands for rendering a tile of a full print image to the GPU card . In response to receipt of the commands the GPU card renders the tile into the memory of the GPU card .

In another implementation the computer module may contain a plurality of GPU cards. In this instance at step the CPU selects one of the plurality of GPU cards of the computer module in accordance with a swathe associated with each of the plurality of tiles assigns an image tile to the selected GPU card and renders the tile on the selected GPU card. The allocation of an output image as seen in is performed in step of the method . The rendered image is at the print image area within the output image .

In an implementation where double buffing is being used in the frame buffer there are two frame buffers. One of the frame buffers is called a render frame buffer and the other frame buffer is called a transmit frame buffer. A tile may be rendered directly to the render frame buffer or the tile may be rendered first to a texture and then copied to the render frame buffer configured in memory of the GPU card .

In the method of the tile is rendered to the render frame buffer directly. Data in the transmit frame buffer may be transmitted periodically via the video interface to the printer . At step a new identification number of a frame is added by the CPU to the metadata associated with the output image of the rendered tile resulting from step . Also band identification numbers band IDs to specify which band each rendered tile is located in are added to the metadata at step . The metadata may include the tile number tile size colour bit depth etc.

In decision step if the CPU determines that the print controller has sent a wait signal as at step to the CPU then the method proceeds to step . The wait signal sent from the print controller indicates that the GPU card should wait to send more rendered tiles to the printer until the spool in the print controller has been reduced to a certain size. At incrementing step the waiting time is incremented by the estimated waiting time from the wait signal. The method proceeds to decision step .

At decision step if the CPU determines that the wait time has elapsed i.e. the data in the transmit frame buffer has been received by the video receiver of the printer then the method proceeds to step . Otherwise the method proceeds to step .

The method concludes at step where the CPU sends a signal to the GPU card so that the rendered tile in the render frame buffer i.e. resulting from step is swapped into the transmit frame buffer configured within the memory .

In one implementation the computer module may comprise a plurality of GPU systems and as seen in . In this instance an associated print controller may also comprise a plurality of video receivers and as shown in if each of the GPU systems and has a plurality of video interfaces similar to the video interface . Each of the GPU systems or may be configured to have one 1 GPU card e.g. which includes multiple M video interfaces i.e. 1 M .

Alternatively each of the GPU systems or may have multiple GPU cards which are linked using scalable linked interfaces SLI . However in this instance only a master GPU card has a video interface i.e. M 1 .

In still another alternative implementation the GPU cards of a GPU system e.g. may have a combination of 1 M and M 1 video interface configurations.

The GPU systems and and print controller of may be required when a single GPU card e.g. cannot render images as fast as the print engine i.e. comprising the engine controller and print head controller can output the rendered images. The GPU systems and of may be used when the video interface has insufficient bandwidth to transport the rendered images as fast as the print engine can output the rendered images.

Each GPU system or of the module may be associated with one or more swathes. In this instance each swathe is associated with one GPU system.

The conversion of PDL data to 3D drawing commands creates a plurality of streams of 3D drawing commands. Each stream of 3D drawing commands may be assigned to one of the GPU systems and . Each GPU system or renders the images required for the swathe associated with that GPU system or in parallel with one another.

The print controller comprises a swathe controller e.g. for each GPU system e.g. GPU system . Each swathe controller or contains one or more video receivers or a spool and a print head controller that controls print heads associated with the swathe. In one implementation each video receiver or may have an associated spool or another spool not shown in respectively. Each swathe controller or may be configured for synchronising a plurality of tiles obtained from dividing a complete swathe into multiple tiles e.g. Swathe 1 Swathe 2 or Swathe 3 with one another.

Each print head controller e.g. connects to a single engine controller . The engine controller signals each print head controller e.g. of each swathe controller e.g. when to mark paper being printed. In one implementation the engine controller signals each print head controller of the swathe controllers e.g. to print the rendered tiles on the paper when all the rendered tiles in the same band across the width of a web to be printed have been received. The print head controller e.g. is synchronised with other print head controllers to output the rendered tiles in the same band.

In another implementation the engine controller signals each print head controller e.g. to initiate the marking of the page as the rendered tiles have been received in order e.g. from left to right of a band across the width of the web to be printed .

As described above extra information or metadata may be associated with each output image in the frame buffer configured within the memory . Similar to the video receiver the video receivers and read the metadata in the output image and add a printable image area to the spool . The engine controller coordinates the outputting of each of the image spools e.g. spool and spools from the swathe controllers and via the associated print head controllers.

In one implementation the computer module may comprise a plurality of CPUs each connecting to a plurality of GPU systems e.g. and . A plurality of CPUs configured in such a manner allows maximum scalability of a high performance print system.

In an alternative implementation a post rendering process e.g. colour conversion and dithering may be performed on a tile after the tile has been rendered using a GPU card. The pixel data produced from such post rendering is placed in the frame buffer configured within memory to be transferred to the swathe controller . The size of pixel data after post rendering has been performed on the pixel data may be smaller than the size of the frame buffer configured within memory . For example pixels may be dithered from eight 8 bpp bits per pixel to two 2 bpp reducing the pixel data size by three quarters .

In one implementation a plurality of dithered tiles or images may be compacted into one frame and sent to the video receiver within a frame.

The video receiver requires extra information to extract a plurality of tiles from a frame. Such extra information may include the number of tiles in a frame and location of each tile. The number of tiles and the size of the pixel data for each tile may be contained in a higher level of metadata of a frame as shown in . Each rendered tile may be associated with metadata e.g. and associated print images e.g. . In the example of the metadata is associated with the print image and the metadata is associated with the print image .

In one implementation the GPU card comprises an intermediate buffer called a render spool configured within GPU memory . The GPU card may alternatively comprise textures to spool more than one rendered tile. The frame buffer in the GPU memory may be configured using a double buffering method. A render frame buffer may be used to retain rendered pixels while a transmit frame buffer contains pixel data transferred out of the GPU card via the video interface .

A method of spooling rendered tiles will now be described with reference to . The method may be implemented as one or more code modules of the software application program and being controlled in its execution by the CPU .

In accordance with the method if there is more than one dithered tile in the render spool configured within the memory and each of the dithered tiles has a smaller size than the original size of an associated rendered tile then a number of the dithered tiles may be compacted into the render frame buffer. The compacting occurs if the render frame buffer is not ready to receive any data.

The method begins at step where the CPU sets an initial wait time. Then at decision step the CPU determines if there is a tile to render. If there is no tile to render then the method concludes. Otherwise if there is a tile to render then the method proceeds to step .

At decision step the CPU determines if the render spool configured within the GPU memory is full. If the render spool is not full then the method proceeds to step . At step the CPU issues a render command to the GPU card to render the tile and then dither the rendered tile to the render spool configured within GPU memory . The dithering method may be implemented with the compute uniform device architecture CUDA . If the CPU determines that the render spool is full at step then the method proceeds directly to step . At decision step the CPU checks if there has been any wait signal received as at step from the engine controller of the printer . If a wait signal has been received by the CPU the method proceeds to step . Otherwise if the CPU has not detected any wait signal from the printer then the method proceeds to step .

At step the CPU increments the wait time by an amount indicated by the wait signal received from the engine controller of the printer .

Then the method proceeds to next decision step . At decision step if the CPU determines that the render frame buffer is free i.e. contents of the frame buffer have already been swapped to the transmit frame buffer by the GPU card then the method proceeds to adding step . Otherwise if the render frame buffer is not free then the method proceeds to step .

At adding step the CPU adds a new identification number or attribute of the frame including the number of tiles to be included in the frame to the metadata of an output image . Also band identification numbers band IDs to specify which band each rendered tile is located in are added to the metadata at step .

Then at compacting step the CPU compacts the dithered tiles from the render spool to an output image or to the frame as seen in . For example a first dithered tile may be copied to print image 1 area of the frame and a second dithered tile may be copied to print image 2 area . Metadata for the first tile and metadata for the second tile are also created in step . In particular at compacting step the CPU determines the maximum number of tiles that can be compacted into a frame configured within memory . Once the maximum number of tiles has been determined the CPU copies a number of tiles from the render spool into the frame at step . The actual number of tiles copied into the frame is equal to or less than the maximum number of compacted tiles allowed depending on the number of tiles spooled in the render spool configured within GPU memory . The actual number of tiles may be written by a GPU command in accordance with the compute unified device architecture CUDA from the GPU card to the top level metadata e.g. metadata associated with the frame configured within memory .

At step the CPU determines if the wait time has elapsed i.e. the data in the transmit frame buffer has been received by the video receiver . If the CPU determines that the wait time has elapsed then the method proceeds to step . Otherwise the method proceeds to step .

At swapping step the CPU swaps the content of the render frame buffer configured within the GPU memory to the transmit frame buffer configured within memory using an OpenGL command from the GPU card .

Then at setting step the CPU sets a flag indicating that the render frame buffer is free. Also at step the CPU resets the wait time to the initial wait time. Then the method proceeds to step .

At decision step the CPU determines if the render spool is empty. If there are more tiles in the render spool configured within memory then more compact actions and swapping buffers are required and the method returns to step . Otherwise if the render spool is empty then the method returns to step to render more tiles.

The method may be also implemented asynchronously. For example instead of polling the wait signal at step to continue step or step a wait signal arriving at the CPU from the printer may trigger step . If an asynchronous method is used for the method the control flow and the steps may be changed accordingly.

Both method and method may be modified to handle error signals from the engine controller of the printer .

A method of rendering a document in page description language format using a plurality of graphics processing unit GPU cards or graphics processing units will now be described with reference to . The method will be described with reference the GPU systems and and the print controller of . One or more steps of the method may be implemented as one or more software code modules of the software application program and or the software application program .

The method begins at step where at least CPU is used for converting the document data to a set of drawing commands corresponding to a plurality of bands. Each of the plurality of bands includes a plurality of tiles and each of the tiles included in a band is associated with a plurality of swathes i.e. swathe 1 swathe 2 swathe n . Each tile represents at least a portion of the document.

At the next step the CPU is used for assigning each of the plurality of tiles to one of the plurality of graphics processing unit GPU in a GPU system or in accordance with a swathe associated with each of the plurality of tiles.

Then at step the CPU sends a signal to each of the assigned GPU systems or . In response to receipt of the signal each assigned graphics processing unit GPU card in GPU system or operating in parallel with one another start rendering one or more of the plurality of tiles representing the document into the memory . Each of the rendered tiles has a band identification number band ID in the form of an identifier identifying which band each rendered tile is located in as described above with reference to .

The plurality of rendered tiles are transmitted from the assigned GPU cards in GPU systems and or to each of the corresponding print head controllers e.g. bypassing the central processing unit CPU . The rendered tiles are transmitted by the GPU cards in the GPU systems and or at a higher frequency than a frequency at which the plurality of tiles is output from the print head controller . One of the transmitted tiles may be discarded. Such discarded tiles are identified by one of the print head controllers e.g. by referring the band ID of the tiles as being a duplicate. Tiles associated with the band ID e.g. band ID 2 may continue to be transmitted and discarded until the corresponding print head controllers e.g. completes output of the previous band e.g. band ID 1 . The rendered tiles forming a complete band are output from one of the print head controllers e.g. for the rendered tiles.

The arrangements described are applicable to the computer and data processing industries and particularly for high speed high volume printing.

The foregoing describes only some embodiments of the present invention and modifications and or changes can be made thereto without departing from the scope and spirit of the invention the embodiments being illustrative and not restrictive.

In the context of this specification the word comprising means including principally but not necessarily solely or having or including and not consisting only of . Variations of the word comprising such as comprise and comprises have correspondingly varied meanings.

