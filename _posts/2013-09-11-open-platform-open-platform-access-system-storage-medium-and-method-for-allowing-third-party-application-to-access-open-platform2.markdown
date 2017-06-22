---

title: Open platform, open platform access system, storage medium, and method for allowing third party application to access open platform
abstract: The present invention relates to the technical field of computers. Provided are an open platform, open platform access system, storage medium, and method for allowing a third party application to access an open platform, the method comprising: acquiring the identification information a user uses to access a target open platform; according to the acquired identification information and the corresponding relationship between the pre-established identification information of the user in the target open platform and the identification information in a preset open platform, determining the identification information of the user in the preset open platform; according to the identification information of the user in the preset open platform, invoking via the open interface of the preset open platform the data of the target open platform stored in the preset open platform. The present invention allows a third party application to access a plurality of target open platforms only by connecting to a preset open platform, without maintenance and joint debugging of multiple sets of codes, thus effectively saving resources, and accelerating the launching of the third party application on the target open platform.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09635098&OS=09635098&RS=09635098
owner: TENCENT TECHNOLOGY (SHENZHEN) COMPANY LIMITED
number: 09635098
owner_city: Shenzhen, Guangdong
owner_country: CN
publication_date: 20130911
---
This application claims the priority of Chinese Application No. 201210351808.5 filed on Sep. 20 2012 by Tencent Technology Shenzhen Co. Ltd. entitled Method For Allowing Third Party Application To Access Open Platform And Open Platform Access System the disclosure of which is hereby incorporated by reference in its entirety.

The present disclosure is related to the field of computer technologies in particular to a method for allowing a third party application to access an open platform an open platform access system an open platform and a storage medium.

A third party application refers to an external application based on an open platform. A third party application developer as an independent content provider gains certain brand benefits and capital income through issuing products on the open platform. With the advance of open strategies it becomes more important to allow the third party application to login more open platforms such as a social network platform with the minimal cost and the lowest price.

In a current technical solution for allowing a third party application to login a plurality of open platforms the third party application developer modifies service logic codes according to an Open Application Programming Interface OpenAPI access protocol provided by the open platform to be accessed jointly tests interfaces such as a payment interface and a relationship chain interface in combination with the open platform to be accessed and finds another machine for deploying service codes passing the joint test so as to launch the third party application on the open platform.

To allow a third party application to access to a plurality of open platforms the third party application is required to interface with the plurality of open platforms so that a plurality of sets of service codes need for maintaining and a plurality of joint tests shall be conducted resulting in a slow speed of allowing the third party application to access the open platforms further a resource waste is caused because service codes for different platforms are required to be deployed on different machines.

One aspect of embodiments of the present invention is to provides an open platform an open platform access system a method for allowing a third party application to access an open platform and a storage medium to solve the following problems in the prior art that to allow a third party application to access to a plurality of open platforms the third party application is required to interface with the plurality of open platforms so that a plurality of sets of service codes need for maintaining and a plurality of joint tests shall be conducted resulting in a slow speed of allowing the third party application to access the open platforms further a resource waste is caused because service codes for different platforms are required to be deployed on different machines.

acquiring the identification information used by a user to access a target open platform when receiving the information that the user is operating a third party application to access the target open platform wherein the third party application is an application already launched on a preset open platform 

determining the identification information of the user in the preset open platform according to the acquired identification information and the corresponding relationship between the pre established identification information of the user in the target open platform and the identification information of the user in the preset open platform which preferably acquires and stores the data of the target open platform through an open interface in advance 

invoking the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

a data acquiring unit configured to form a user access account number interoperability between a present open platform and a target open platform and to acquire and store the data of the target open platform and

an open interface unit configured to open an interface for the target open platform to invoke functional interfaces and or the data of the present open platform according to requirements of the target open platform.

an acquiring unit configured to acquire the identification information used by a user to access a target open platform when receiving the information that the user is operating a third party application to access the target open platform wherein the third party application is an application already launched on a preset open platform 

a determining unit configured to determine the identification information of the user in the preset open platform according to the acquired identification information and the corresponding relationship between the pre established identification information of the user in the target open platform and the identification information of the user in the preset open platform 

an invoking unit configured to invoke the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

A storage medium containing computer executable instructions wherein the computer executable instructions when being executed by a processor are configured to perform a method for allowing a third party application to access an open platform wherein the method comprises 

acquiring the identification information used by a user to access a target open platform when receiving the information that the user is operating a third party application to access the target open platform wherein the third party application is an application already launched on a preset open platform 

determining the identification information of the user in the preset open platform according to the acquired identification information and the corresponding relationship between the pre established identification information of the user in the target open platform and the identification information of the user in the preset open platform 

invoking the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

Compared with the prior art embodiments of the present invention have the following beneficial effect. In the present invention by storing the data of the target open platform into the preset open platform in advance the data of the target open platform stored by the preset open platform can be invoked by open interfaces of the preset open platform when the user operates the third party application to access the target open platform. Whereas when the third party application needs to access a plurality of target open platforms the third party application is only required to interface with the target open platform to invoke corresponding target open platform data from the preset open platform without developing a plurality of sets of service code or making corresponding code maintaince and join test for the plurality of target open platforms. Moreover all service codes of the third party application with respect to all target open platforms can be deployed on a machine of the preset open platform system therefore resources are preserved efficiently and the speed for get online on the target open platform by the third party application is improved. Moreover functions of the third party application are enriched since the third party application can use various functional interfaces of the preset open platform.

The present disclosure is further described in detail below in conjunction with the accompanying drawings and embodiments to make objectives technical solutions and advantages of the disclosure more apparent. It should be understood that specific embodiments described here are only used to explain but not to limit the present disclosure.

An embodiment of the present invention provides a method for allowing a third party application to access an open platform including 

acquiring identification information used by a user to access a target open platform when receiving information that the user is operating a third party application to access the target open platform where the third party application is an application already launched on a preset open platform 

determining identification information of the user in the preset open platform according to the acquired identification information and a pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform preferably data of the target open platform is acquired and stored in advance by the preset open platform through an open interface and

invoking the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

a data acquiring unit configured to form user access account interoperability between the present open platform i.e. the open platform including the acquiring unit and a target open platform and to acquire and store data of the target open platform in advance and

an open interface unit configured to open an interface where the interface is used by the target open platform to invoke a functional interface and or data of the present open platform according to requirements of the target open platform.

an acquiring unit configured to acquire identification information used by a user to access a target open platform when receiving information that the user is operating a third party application to access the target open platform where the third party application is an application already launched on a preset open platform 

a determining unit configured to determine identification information of the user in the preset open platform according to the acquired identification information and the pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform where data of the target open platform is acquired and stored by the present open platform through an open interface in advance and

an invoking unit configured to invoke the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform. The present disclosure is described below in detail in combination with specific embodiments.

Step S acquiring identification information used by a user to access a target open platform when receiving information that the user is operating a third party application to access the target open platform where the third party application is an application already launched on a preset open platform.

In this embodiment the third party application refers to an external application based on the open platform. A third party application developer which is an independent content provider gains certain brand benefits and capital income through issuing products thereof on the open platform.

In this embodiment the target open platform may be the Friends social network platform the KAIXIN social network platform etc.

In this embodiment when attempting to login the target open platform for the first time the user is first required to register user identification information. When attempting to login the target open platform for the next time the user can login the target open platform by inputting the identification information. Here the identification information includes an account an account name or a login password of the user or any combination thereof.

Step S determining identification information of the user in the preset open platform according to the acquired identification information and the pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform where preferably data of the target open platform is acquired and stored by the preset open platform through an open interface in advance.

In this embodiment user access account interoperability between the present open platform and the target open platform is realized through the pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform.

In this embodiment the pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform is searched for according to the identification information used by the user to login the target open platform to determine the identification information of the user in the preset open platform.

In this embodiment the user registers the user identification information with the preset open platform in advance so that the user can login the preset open platform by inputting the user identification information.

In this embodiment the stored data of the target open platform may be user relationship chain data and user information data in the target open platform.

In this embodiment by introducing the data of the target open platform into the preset open platform the third party application developer can use the data of the target open platform almost without any code modification. That is the user can operation information of the third party application over the preset open platform without interfacing with the target open platform or maintaining codes.

Step S invoking the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

In this embodiment the preset open platform stores the data of at least one target open platform so that the third party application developer can access each of the at least one target open platform by interfacing with the preset open platform.

Optionally the preset open platform may be provided in advance with a plurality of functional interfaces such as a payment interface and a security interface. The target open platform may share resources of the preset open platform by invoking the functional interfaces of the preset open platform through the open interface of the present open platform according to the identification information of the user in the preset open platform.

In this embodiment the data of the target open platform is stored in the preset open platform in advance so that the data of the target open platform stored by the preset open platform can be invoked by an open interface of the preset open platform when the user operates the third party application to access the target open platform. Also to access a plurality of target open platforms the third party application is only required to interface with the target open platform to invoke data of the respective target open platforms without developing a plurality of sets of service codes and maintaining and jointly testing the service codes with respect to the plurality of target open platforms. Moreover all service codes of the third party application with respect to all target open platforms can be deployed on a machine for the preset open platform system thereby effectively saving resources and improving the speed of launching the third party application on the target open platform. Moreover functions of the third party application are enriched using various functional interfaces of the preset open platform.

In Step S prompting the user whether to bind the identification information of the user in the target open platform and the identification information of the user in the preset open platform when receiving information that the user is operating the third party application to access the target open platform for the first time where the third party application is an application already launched on the preset open platform.

In this embodiment prompt information including a voice prompt a dialogue box prompt may be used to prompt the user whether to bind the identification information of the user in the target open platform and the identification information of the user in the preset open platform.

In step S when information that the user determines to bind the identification information of the user in the target open platform and the identification information of the user in the preset open platform is received binding and storing the identification information of the user in the target open platform and the identification information of the user in the preset open platform.

In step S acquiring the identification information used by the user to access the target open platform.

In step S determining the identification information of the user in the preset open platform according to the acquired identification information and the pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform which preferably acquires and stores the data of the target open platform through an open interface in advance.

In step S invoking the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

In this embodiment implementing processes of steps S are similar to those of steps S S detailed described above with reference to the first embodiment.

For a better understanding an implementing process for the third party application to access the KAIXIN social network platform is described below. However the present invention is not limited thereto. Reference is now made to which shows a structural diagram of an architecture by which a user operates a third party application to access the KAIXIN social network platform. The access process is described below.

When the user logins the KAIXIN social network platform for the first time to use the third party application the user is prompted to bind the user s Kaixin ID and QQ number. When information that the user approves to the bind the user s Kaixin ID and QQ number is bound. According to a bound QQ number the Tencent OpenAPI platform acquires and stores data of the KAIXIN social network platform. Since the Tencent OpenAPI platform has already stored the user relationship chain and open application interface programs the third party application can support the KAIXIN social network platform and the third party application can also use Tencent cloud computing devices such as a payment system a security system.

When the user uses the third party application to access the Tencent OpenAPI platform for the next time the user can find the stored corresponding relationship between the user s Kaixin ID and QQ number then the user invokes directly data of the KAIXIN social network platform stored in the Tencent OpenAPI platform and platform data of the Tencent OpenAPI platform itself.

The process mentioned above for the user to use the third party application to access the Tencent OpenAPI platform greatly improves the speed to access the KAIXIN social network platform for the third party application which has already got online by the Tencent OpenAPI platform because user data relationship chains of the KAIXIN social network platform are stored by the Tencent OpenAPI platform. The third party application no longer needs to find machine deployed codes. Instead the third party application can reuse the Hosting machine provided by Tencent. On the KAIXIN social network platform the third party application can use mature payment interfaces of the Tencent OpenAPI platform. The Tencent OpenAPI platform provides an OpenAPI which supports KAIXIN social network relationship chains and personal data and can be used by the third party application directly.

In addition when accessing a plurality of target open platforms such as a space platform and a friend platform the operation process of the third party application is similar to operation process for accessing the KAIXIN social network platform therefore will not be described unnecessarily here. At this moment the third party application is only required to interface with the preset open platform but not different target open platforms therefore greatly improves the speed for the third party application to access the target open platform. The third party application no longer needs to find machine deployed codes. Instead the third party application can reuse a host device corresponding to the preset open platform. Moreover latency for the third party application to access the target open platform can be decrease because the data of the target open platform are stored by the preset open platform.

Furthermore the preset open platform may be provided with a plurality of functional interfaces such as a payment interface a security interface therefore the KAIXIN social network platform the space platform and the friend platform may share resources by invoking interface data of the preset open platform.

The data acquiring unit is configured to form user access account interoperability between a present open platform and a target open platform and to acquire and store the data of the target open platform and

The open interface unit is configured to open an interface for the target open platform to invoke the data of the present open platform according to requirements of the target open platform.

In this embodiment the preset open platform is provided with a plurality of functional interfaces to be invoked by the target open platform such that resource share can be achieve among the plurality of f target open platform to saving resources effectively.

In this embodiment the user access account interoperability is formed between the open platform and the target open platform. The data of the target open platform are acquired and stored in advance. The interface is opened for the target open platform to invoke the data of the present open platform according to requirements of the target open platform. By the account interoperability between the target open platform and a plurality of target open platforms the third party application can use data stored by the preset open platform to access the target open platform uniformly without developing a plurality of sets of service code or making corresponding code maintaince and join test for the plurality of target open platforms.

The open platform access system comprises an acquiring unit a determining unit and an invoking unit .

The acquiring unit is configured to acquire the identification information used by a user to access a target open platform when receiving the information that the user is operating a third party application which is an application already launched on a preset open platform to access the target open platform.

The determining unit is configured to determine the identification information of the user in the preset open platform according to the acquired identification information and the pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform.

The invoking unit is configured to invoke the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

The preset open platform can acquire and store the data of the target open platform via an open interface in advance.

The preset open platform is provided with a plurality of functional interfaces. The invoking unit is further configured to invoke functional interfaces of the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

The data of the target open platform comprises the user relationship chain data and the user information data in the target open platform.

The open platform access system provided in this invention can be used in above mentioned corresponding first embodiment of method. That is the method for allowing a third party application to access an open platform described in the first embodiment may be run in the open platform access system provided by the fourth embodiment of the invention. Details are the same to the description made with reference to the first embodiment therefore will not be repeated unnecessarily.

The system comprises a prompting unit a binding unit an acquiring unit a determining unit and an invoking unit .

The prompting unit is configured to prompt the user whether to bind the identification information of the user in the target open platform and the identification information of the user in the preset open platform when receiving the information that the user is operating the third party application to access the target open platform for the first time and to start the binding unit if information that the use determines the bind is received.

The binding unit is configured to bind and store the identification information of the user in the target open platform and the identification information of the user in the preset open platform.

The acquiring unit the determining unit and the invoking unit have the same function and operation approach with those of the acquiring unit the determining unit and the invoking unit in the fourth embodiment respectively.

The open platform access system provided in this invention can be used in above mentioned corresponding second embodiment of method. That is the method for allowing a third party application to access an open platform described in the second embodiment may be run in the open platform access system provided by the fifth embodiment of the invention. Details are the same to the description made with reference to the second embodiment therefore will not be repeated unnecessarily.

In each of the embodiments above when receiving the information that the user is operating a third party application to access the target open platform the identification information used by a user to access a target open platform can be acquired from the received information.

Furthermore the present invention provides a storage medium containing computer executable instructions wherein the computer executable instructions when being executed by a processor are configured to perform a method for allowing a third party application to access an open platform wherein the method comprises 

acquiring the identification information used by a user to access a target open platform when receiving the information that the user is operating a third party application to access the target open platform where the third party application is an application already launched on a preset open platform 

determining the identification information of the user in the preset open platform according to the acquired identification information and the pre established corresponding relationship between the identification information of the user in the target open platform and the identification information of the user in the preset open platform 

invoking the data of the target open platform stored in the preset open platform via an open interface of the preset open platform according to the identification information of the user in the preset open platform.

It may be understood by one of ordinary skills in the art that all or a part of the steps for realizing the above embodiments may be accomplished through instructing related hardware by programs. Related programs may be stored in a computer readable storage medium such as a ROM RAM a magnetic dis or a compact disk.

The above description only shows some preferred embodiments of the disclosure rather than limiting the scope of the invention. All modifications equivalent substitutions improvements etc. made without departing from the concept and principles of the invention should fall within the protection scope of the invention.

