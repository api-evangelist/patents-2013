---

title: Configuration of third party applications in a sandboxed environment
abstract: A profile manager application is installed in an electronic device that fetches configuration profiles for third party applications from a remote server. Using code libraries incorporated in the third party applications and URL based commands, the profile manager application communicates with the third party applications to configure them according to the corresponding configuration profiles, even though the third party applications are running in a sandboxed environment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09319270&OS=09319270&RS=09319270
owner: FrontRange Solutions, Inc.
number: 09319270
owner_city: Milpitas
owner_country: US
publication_date: 20130412
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 623 489 filed on Apr. 12 2012 the disclosure of which is hereby incorporated by reference.

The present disclosure relates to the communication between third party applications in a sandboxed environment on an electronic device. More particularly it relates to a system method and application employing such communication for the configuration of third party applications.

A shortcoming in some operating systems such as iOS is that third party applications also called apps cannot be configured using configuration profiles within the operating system. Configuration profiles within the operating system can be used for configuring parts of the operating system and for controlling certain hardware functionality of the device. As there is no support in this respect for third party apps each third party app must be configured by the user of the device unless the user simply wishes to use whatever default configuration is provided by the third party app.

A sandbox is a security mechanism employed in some operating systems for isolating running programs. It is often used to execute programs from third parties for example. The sandbox typically provides a limited set of resources for the programs to run in which are usually less than the full set of resources that are available on the device and that would be available to the OS itself. By limiting what third party programs can do sandboxing reduces the conflict between programs and the likelihood of crashes improving the apparent reliability of the programs. It also protects the device from malware and other malicious code that can be injected into running applications.

A drawback of sandboxing may be seen in a corporate scenario. If a company wishes its employees to install a particular third party app on their mobile devices then it may be the case that the third party app needs to be configured according to the requirements of the company. The problem is that many employees will have difficulty configuring the third party apps the way the company requires which may involve entering server and or port addresses. Even for those with competence in this area there is still the possibility of making typing errors and there may be some reluctance or procrastination on the part of the employees to actually carry out the configuration.

While sandboxing can be beneficial one of its drawbacks is that third party applications are not intended to communicate with each other and cannot readily do so. However it would be useful to somehow use one third party application to configure other third party applications.

Disclosed herein are a system and process for configuring third party applications in a sandboxed environment on a mobile electronic device. Third party app developers are provided with special libraries that they can add to their code. Third party apps with the included libraries are able to communicate with other third party apps that include complementary libraries or code and are installed in the same mobile device. Communication between the third party apps is two way and occurs via URL commands containing the data that is to be communicated and occurs even when the third party apps are in a sandboxed environment. As an example a profile manager app provided by a company may be used to provide configuration profiles to several other third party apps installed on employee devices.

This summary is not an extensive overview intended to delineate the scope of the subject matter that is described and claimed herein. The summary presents aspects of the subject matter in a simplified form to provide a basic understanding thereof as a prelude to the detailed description that is presented below. Nothing in this summary or the following detailed description including the appendices is intended to imply that any particular feature component or characteristic is essential to the invention the scope of protection is defined by the claims.

Mobile Device This refers to any portable electronic device such as a laptop a notebook a netbook a tablet an electronic book a smart phone a game console and any other portable computing device.

Third Party App A software application that can be installed on a mobile device typically written by an individual or company other than the company providing the operating system for the device. Well known examples of third party apps include the Facebook and LinkedIn apps. These are different from built in apps such as YouTube and iTunes which are or have been included with the operating system of the mobile device and do not usually require a separate installation. Third party apps for some mobile devices may fall into two different categories these being apps that are made available to the general public through an app store and apps that are not made generally available. These latter apps are called enterprise apps or in house apps and are usually distributed by a company to a limited but possibly large number of employees or other users. This invention disclosed herein applies to both categories of third party app. When used herein the term third party app relates predominantly to third party apps other than the profile manager app described below.

Profile Manager App This is a third party application that can be installed on a mobile device and forms part of some embodiments of the present invention. It receives and stores configuration profiles from a remote server and makes them available to other third party apps.

Configuration Profile Software applications generally present the user with a choice of various settings. For example one of the settings for a weather application may require a user to set a home town for which the weather is to be forecast. Another setting for the weather application may be whether the view displayed on the screen of the mobile device should be hourly or daily. Another typical example of a configuration profile which is particularly common for in house apps is the setting of a server address and a port number. Sometimes the configuration profile of an app is referred to as its settings. In other cases certain functional features of the mobile device its operating system or settings of built in apps may be set by a configuration profile. This may be recommended by the providers of third party apps or required by administrators and may involve controlling access to email use of the camera WiFi etc. While the present invention relates to the setting of configuration profiles for third party apps it may also include functionality for the setting of configuration profiles for device features the operating system and or built in apps. Note that an app may have multiple configuration profiles each configuring different parts of the app.

Configuration Profile Settings A third party app uses the settings in a configuration profile to configure itself. This could involve saving the configuration settings in a store in the third party app. The configuration profile itself as a whole is not sent to nor stored by the third party app. The configuration profile is only stored by the profile manager app.

URL Scheme Sometimes referred to as a URL protocol handler. For a third party app to be opened by a link or another third party app a URL scheme typically must be registered with the operating system and the third party app to be opened typically must be registered as such. Whenever a URL command is invoked the operating system checks that it corresponds to the registered format contained in the URL scheme before processing the command.

Delegate A design pattern used in software development which is like a subroutine to which values can be passed and from which response values can be received. Delegation is where a controller defines a protocol e.g. a set of method definitions describing what a delegate object must do in order to be allowed to respond to a controller s events. This allows the controller to call methods on its delegate with the knowledge that the delegate will respond to the method calls. Other software patterns that provide similar results may be used instead such as forwarding inheritance mixins callback methods or functions including closures .

Library A portion of computer readable code that is typically used in common by several applications. Libraries may be stored separately from the applications or they may be incorporated. Certain parts of a library or the third party app using it may be customized. When used herein the term library generally refers to the library of the present invention supplied to the third party apps.

API Application Programming Interface. A source code based structure that allows software components to communicate with each other.

An embodiment of a system for configuring third party apps is shown in . The system comprises one or more servers having one or more processors connected to one or more non transient computer readable media or memories . Memory stores computer readable instructions that when processed by the processor cause the system to function according to the process described herein. Memory also stores data which includes one or more configuration profiles that are to be installed on one or more remote electronic devices and applied to third party apps on those devices. Identification of the devices and the third party apps is also stored in memory . The server is connected to a network which may for example include the internet a telecommunications network or both. A terminal is connected to the network . An administrator may use a mobile device management console running on or accessible at the terminal to enter data and manage the configuration profiles and the devices and third party apps to which they should be applied.

One or more devices are connectable to network each including one or more processors that control operation of the device including communication with the server . Connections to the network may be wired or wireless. The processor is connected to one or more non transient computer readable media or memory . The memory stores an operating system for the device . Within the operating system one or more registered URL schemes are stored. When a URL is used to open a third party app its format must conform to a registered URL scheme and the third party app to which it is bound must be installed on the device .

When a third party app is installed its URL scheme is registered inside the OS . The registration of the URL scheme is performed by the third party app and not by the profile manager app also stored in memory . The profile manager app does not need to know anything about the specific third party apps that it can manage. The benefit of this is that further third party apps with configuration profile support can be added without any changes to the profile manager app .

The profile manager app is set up to communicate with the server to receive configuration profiles for possible eventual application to third party apps . The profile manager app also includes a URL handler which allows it to be opened by the third party apps and to receive data from them. Prior configuration profiles may also be stored in the memory . The profile manager app also stores prior configuration profiles .

Third party apps and possibly other third party apps are stored in memory of device . Each third party app to be provided with settings from a respective configuration profile includes a respective library . In other embodiments within the purview of the present invention such a library may be shared between third party apps rather than being embedded in each individual one. The libraries provide the common functionality of two way communication with the profile manager app. Each third party app has a URL handler that receives and processes URL commands from the profile manager app . Each of these URL handlers must be registered with a unique URL scheme in order to be able to uniquely address a specific third party app. Configuration profile data received in the URL handlers is extracted from them by the library . The libraries provide a class that forwards configuration profile settings to delegates . The class has a method for setting a configuration profile and another method for removing a configuration profile. A configuration profile may be set in whole or in part or it may be removed in whole or in part. Current or existing configuration profiles may be updated. On removal of a configuration profile the third party app can also remove any stored data relating to the profile. The actual configuration profile is set by the corresponding delegate in each of the third party apps .

As shown in third party app App A has default or blank settings which may later be replaced by settings from configuration profile Pr. A . Third party app App B has already had its configuration profile settings Pr. B A set.

Prior to the process an administrator responsible for a group of one or more remote mobile devices has created a new configuration profile such as profile to be applied to the respective third party app using an administrator s management console on terminal connected to the server .

In step the configuration profile is assigned to a particular device . While it may be assigned directly it may alternately be assigned to a device by way of a policy in which one or more devices are identified to receive the configuration profile which may itself be one of several configuration profiles assigned to the device.

In step a message is sent from the server to the mobile device that is to receive the configuration profile . This may be a push notification for example. In alternate embodiments other known methods for the device to obtain the message may be used.

In step after receipt of the notification which typically contains an identifier of the profile manager app the operating system of the mobile device determines whether the profile manager app is running as the foreground app in the mobile device. If the profile manager app is not running in the foreground i.e. suspended or unopened a pop up message appears on the device in step notifying the user of the device that a new configuration profile is available. Note that in some embodiments step may be omitted. The notification can be of any appropriate form and may include buttons such as View Now and View Later one of which can be selected by the user depending respectively on whether the user wants to view the new profile now or later. Other methods of notification may alternately be used such as email or text messaging. Other buttons or other titles for the buttons may be used in other embodiments. If the user selects View Later the process ends at step but if the user selects View Now then information about the new configuration profile is fetched from the server in step . This information may be for example the name of the third party app the reason for the change the level of importance etc. If the process ended at step the following time that the user brings the profile manager app to the foreground step will be executed and all the following steps will continue from there on.

If at step the profile manager app is already running in the foreground on the device then the process would move directly to step in which information about the new configuration profile is retrieved from the server and stored in the repository within the profile manager app.

After the device has received information about the configuration profile a confirmation request is displayed on the device in step asking whether the user wants to apply the configuration profile. Note that step may be optional in other embodiments. The user is given a choice of Cancel and OK . If the user selects Cancel the process ends at step . If however the user selects OK then in step the configuration profile is fetched from the server . In following step the third party app to which the configuration profile is destined is called using a URL based command with the configuration data appended in the command. In step the third party app then comes to the foreground either from the background state or from being completely off and instructions contained in the library incorporated in the third party app are executed to apply the new configuration profile . Note that in certain operating systems the third party app may not be brought to the foreground. After the library has executed feedback is provided in step to the profile manager app informing it of success partial success or failure for example.

Feedback messages are reported back to the profile manager app again using a URL based command. This callback command is compiled and invoked by the library and causes the third party app to close down or suspend its operation and the profile manager app to come to the foreground.

Depending on the operating system however the profile manager app may not come to the foreground if there is no error. In other cases the profile manager app may stay in the foreground. Also note that depending on the operating system the third party app and the profile manager app may continue receiving CPU cycles in the background. On some operating systems the full workflow could all be executed without either the third party app or the profile manager app coming to the foreground. In cases where the setting of the new configuration profile has been stopped by the user it may be completed at a later time when the user opens the profile manager app . For example now referring to the flowchart of in step the profile manager app having been brought to the foreground by the user fetches a list of available configuration profiles from the server .

In step the profile manager app displays a list of the available configuration profiles to the user. In step the profile manager app receives a selection from the user indicating which of the profiles is to be installed. The next and subsequent steps are the same as step and subsequent ones as shown in . In some embodiments more than one profile may be selected each one being set sequentially via a series of URL commands. The selection of a profile may be considered to be confirmation as in step that it is to be installed.

Referring to a flowchart is shown which corresponds to steps of in more detail. Before the start of this process it is assumed that the configuration profiles are already stored in the profile manager app in device but not yet installed in their respective third party apps .

In step the configuration profile data is encoded from XML into Base64 and may optionally be encrypted beforehand. Alternately the configuration profile data is not encoded from XML but from a binary plist format which is more efficient. In step based on the content in the configuration profile the profile manager app determines which third party app to call or equivalently which URL handler to call and compiles a URL command based on the URL scheme corresponding to the third party app. The URL scheme is provided in the configuration profile itself so that the profile manager app does not need to have any specific knowledge about the different third party apps it is required to configure. This makes the system extremely flexible. In step the URL command is passed to the operating system which in step closes down the profile manager app and opens the corresponding third party app calling its URL handler.

In step the library incorporated in the third party app handles the URL call and in step the library extracts the configuration profile data from the corresponding parameter in the URL command. In step the extracted configuration profile data is passed to a delegate within the third party app that can configure it. In step the delegate within the third party app undertakes the configuration.

Referring to a high level flowchart is shown of a process carried out by the system for removing a current configuration profile setting from a third party app. Many of the steps are similar to those shown in . This resetting is achieved by replacing the existing settings with prior settings that are stored in the profile manager app . If there are no prior settings then null values are used.

Prior to the process an administrator responsible for a group of one or more remote mobile devices has specified that a configuration profile is to be removed from a third party app using an administrator s management console on terminal connected to the server .

In step a Delete Profile instruction is assigned to a particular device . While it may be assigned directly it may alternately be assigned to a device by way of a policy in which one or more devices are identified to receive the Delete Profile instruction.

In step a message is sent from the server to the mobile device that is to receive the Delete Profile instruction. This may be a push notification for example. In alternate embodiments other known methods for the device to obtain the message may be used.

In step after receipt of the notification which typically contains an identifier of the profile manager app the operating system of the mobile device determines whether the profile manager app is running as the foreground app in the mobile device. If the profile manager app is not running in the foreground i.e. suspended or unopened a pop up message appears on the device in step notifying the user of the device that a current configuration profile is to be removed or simply that a current configuration profile needs to be updated. Note that in some embodiments step may be optional. The notification can be of any appropriate form and may include buttons such as View Now and View Later one of which can be selected by the user depending on whether the user wants to view the updated profile or instruction for the current profile s removal now or later. If the user selects View Later the process ends at step but if the user selects View Now then information about the current configuration profile to be deleted is fetched from the repository of the profile manager app in step . This information may be for example the name of the third party app the reason for the change the level of importance etc. If the process ended at step the following time that the user brings the profile manager app to the foreground step will be executed and all the following steps will continue from there on.

If at step the profile manager app is already running in the foreground on the device then the process moves directly to step in which information about the current configuration profile to be deleted is retrieved from the repository within the profile manager app.

In step the third party app from which the current configuration profile is to be removed is called using a URL based command with null or prior values of configuration data appended in the command. In step the third party app then comes to the foreground either from the background state or from being completely off and instructions contained in the library incorporated in the third party app are executed to apply the null or prior configuration profile effectively removing the existing one. Note that in certain operating systems the third party app may not be brought to the foreground. After the library has executed feedback is provided in step to the profile manager app informing it of success partial success or failure for example. Feedback messages are reported back to the profile manager app again using a URL based command.

Below is a description of an exemplary embodiment for an operating system such as iOS and profile manager app such as AbsoluteApps provided by Absolute Software. Many of these details are examples only not limitations.

The library implements a class named ABTConfigManager which is the main API that the third party app developers interact with. The class is designed as a singleton and is instantiated and configured by the code in the third party app once at application startup. The following examples are illustrated using Objective C code a standard programming language for iOS application development.

The class is guaranteed to be called before the URL handler of the third party app. Also the code in the third party app calls the following in its URL handler 

This method will return a Boolean indicating whether the configuration URL was handled or not so that it is very easy for the third party app to integrate by making this the first call in its URL handler continuing to process its own URLs only if the ABTConfigManager did not handle the configuration URL.

When the third party code configures the ABTConfigManager it specifies a delegate to be called when configuration requests are received. This delegate is responsible to apply or reset configurations thus it implements two methods 

The first method is called when a new configuration needs to be applied and the second method is called when a previously applied configuration is removed i.e. when the corresponding values need to be reset to default values. When the delegate of the third party app applies a configuration it is assumed that all configuration values have been applied if the applyConfiguration method returns YES. If third party delegate only applies one or some of the values contained in the profile it should call for each key that was applied one of the following 

This recording is used to specify which values configured by a configuration profile need to be reset to default values when a configuration profile is removed. Also if the third party code calls ABTConfigurationSet didApplyConfigurationForKey oldValue to register the applied values the old value passed will be used to perform a rollback if application of the profile fails.

4. Implement the ABTConfigManagerDelegate protocol and handle methods to apply reset configuration sets.

When the third party code implements all of the above configuration profile support for the third party app will be available and manageable through Absolute s mobile device management console.

The library is implemented as a static link library plus header file since this is a requirement as per the iOS SDK Software Development Kit . When ABTConfigManager is instantiated it grabs the bundle identifier via 

The third party developer provides an API key that is used in conjunction with the bundle identifier to validate the token passed in the URL. The bundle identifier is used to determine the default URL scheme and for validation of the token passed in the URL. This is to ensure a safe communication channel and disallow others from using the URL handler as a backdoor for sneaking in settings. The URL sent by AbsoluteApps consists of the following components 

Action This can either be SetConfiguration or RemoveConfiguration for example. In other embodiments different strings such as apply and reset may be used.

Token This is a secure token generated from the bundle identifier to verify that the URL was indeed sent from AbsoluteApps assuming that only AbsoluteApps has the knowledge to create a valid token.

ConfigProfileData This is the compressed and optionally encrypted configuration profile data. The key in the URL will be different data but this is the meaning of that component.

If ABTConfigManager recognizes the URL as being a Set Configuration Profile URL by checking the URL scheme it always returns YES from ABTConfigManager handleConfigURL regardless of whether the parameters are valid or not. This ensures that the third party code is not trying to handle URLs that are generated by Absolute Software but for some reason have invalid parameters. When processing a Set Configuration Profile URL ABTConfigManager first verifies the token to ensure that it is a legal call to modify the configuration. If the token is not valid a message is printed to a log file and the error is reported back to AbsoluteApps via the callback URL. If the token exists and is valid ABTConfigManager unpacks the configuration profile data and calls the delegate s method for each payload contained in the configuration profile by constructing a temporary ABTConfigurationSet object for each payload. When the third party delegate returns YES from its delegate method and the action was SetConfiguration ABTConfigManager collects the keys of the modified configuration values from the ABTConfigurationSet object and passes that information back to AbsoluteApps so that the keys to be reset are recorded.

For RemoveConfiguration actions only the final result is reported back to AbsoluteApps since we do not need to record which configuration values have been reset.

Payload data The dictionary sent in the URL is described in Appendix 3. The dictionary is flattened into binary property list format prefixed with a magic byte sequence compressed using Zlib and for the library with encryption support encrypted. The resulting data is Base64 encoded and passed in the URL. By repacking the configuration file data removing unneeded values using binary plist format and compressing a manageable amount of data is obtained that can be passed in the URL.

The code in the library that decodes the payload data should be stable with respect to invalid data. For example it should not try to allocate arbitrary amounts of memory e.g. due to a maliciously crafted Zlib archive and it should verify the type of the data sent e.g. by checking the first bytes of the data to verify that the unpacked data is in fact a binary plist .

Encryption Two versions of the library are provided one without encryption for customers that do not yet use encryption in their apps and do not want to go through the process of declaring and or registering their use of encryption with the US Bureau of Industry and Security or other registration offices for country specific regulations regarding the use of strong encryption and one with strong encryption for customers that either already use strong encryption in their apps or have the security requirements and thus already have done or don t mind going through the registration process.

The encryption level is specified in the configuration profile either at the top level or per payload using the key com.absolute.thirdpartyconfig.DataEncryption Boolean value . If the profile payload specifies strong encryption and this is sent to an app that is linked against the library without encryption trying to install the configuration profile will fail i.e. the library will report back an appropriate error .

The library with encryption can be configured to allow unencrypted data but it will default to only allowing encrypted data. If it is not configured to allow unencrypted data trying to install a configuration profile without encryption will fail.

The encryption uses Blowfish as the encryption algorithm using a hash of the bundle identifier plus a fixed secret key as the encoding key. Other encryption algorithms may of course be used in other embodiments. It is important to correctly identify valid un encoded data so that the code that decrypts the data has a way of verifying whether the decoded data is valid. This can be a unique header used by Zlib when compressing the data or another magic byte sequence. In any event data that obviously was not decoded correctly e.g. because the URL was called by a malicious third party app is not proceeded with and the process is abandoned.

1. The URL scheme defaults to a prefix x absolutemanageconfig. concatenated with the third party app s bundle identifier e.g. x absolutemanageconfig.com.acmetop.acmetopapp . . . Note that the third party app can also optionally register a custom URL scheme 

2. The URL contains a verb as the host part which specifies whether this is a request to apply install or reset remove a configuration profile 

b. profile the unique identifier for the profile being applied this needs to be passed to the callback URL

c. payload the unique identifier for the payload being applied this needs to be passed to the callback URL

d. data or data x respectively the unencrypted or encrypted configuration data packed dictionary as described above 

Whether data or data x is used is decided based on the DataEncryption flag in the profile payload as described above in relation to encryption. The library without encryption support does not check for the data x parameter and thus fails when passed encrypted data.

Note If the third party app registers a custom URL scheme instead of using the default URL scheme as described above using ABTConfigManager configureWithURLScheme delegate this URL scheme must be specified in the configuration profile payload using a string value with key com.absolute.thirdpartyconfig.URLScheme .

and the corresponding payload in the configuration profile cf. Appendix 2 must contain the URL scheme specifier 

Callback URL The library uses a fixed callback URL of absoluteapps thirdpartyprofilestatus to report the status of the configuration request. Once ABTConfigManager has finished processing the configuration request it calls back to AbsoluteApps using the callback URL providing status information as follows 

1. The profile parameter is provided as part of the request URL and contains the PayloadUUID value of the configuration profile itself

2. The payload parameter is provided as part of the request URL and contains the PayloadUUID value of the payload sent in the request URL

3. The token parameter is the token sent in the configuration URL. This allows some basic verification that this callback was actually invoked as a callback operation from one of AbsoluteApps configuration calls.

4. The status parameter specifies the result status of the action. Possible values are Success Error or Canceled.

5. For apply actions with status success only the changedValues parameter contains an array containing the keys of the modified values in compressed binary plist format encoded as Base64.

6. For any action with status error the optional errorCode parameter contains a numeric error code identifying the error reason and the optional errorMessage parameter contains a short error message describing the error

Multiple payloads Support is provided for multiple payloads in a third party configuration profile but these are split into separate URL requests in AbsoluteApps . Each configuration URL only handles a single payload. This allows configuration profiles to be created that for example configure an entire set of third party applications with one payload for each third party application. If a third party application is not available on the device installing the configuration profile by AbsoluteApps will still succeed for the third party applications that are installed. If a payload corresponds to a third party app that is not installed this does not make the entire configuration profile fail the corresponding payload is just ignored. As far as the ABTConfigManager implementation is concerned each configuration call will only contain a single dictionary with one set of settings.

Atomicity It is possible to implement some atomicity with respect to applying configuration profiles by allowing the rollback of applied values automatically when an attempt to apply a configuration profile fails. For this purpose the third party developer can call ABTConfigurationSet didApplyConfigurationForKey oldValue for each value that has been applied passing the old value or nil if no value was set before . If the developer registers the applied keys plus old values the library code can rollback the applied values by creating a new ABTConfigurationSet which contains only the applied keys together with the old values and calls the delegate again to apply back the old values before reporting the error back to AbsoluteApps . However due to the nature of the integration i.e. it is the third party developer s responsibility to register applied values AbsoluteApps does not know about the order of the values etc. 100 atomic operations cannot be provided. When there are multiple payloads in a configuration profile the atomicity only extends to each payload but not across payloads.

Removing a configuration profile When removing a configuration profile the third party app is called via the URL handler with an action reset and the list of keys to reset is passed. This list of keys is compiled depending on the third party app s behavior when the configuration profile was applied with respect to calling these ABTConfigurationSet methods 

If the third party app did not call any of the above methods while applying the configuration profile values the list of values to reset will contain all keys that are present in the configuration profile.

If the third party app only called ABTConfigurationSet didNotApplyConfigurationForKey the list will contain all keys that are present in the configuration profile excluding the keys that were recorded using this method

If the third party app tracked each modified value using one of the didApplyConfigurationForKey methods the list will contain only the keys recorded using these methods.

If the third party app should report using a mixture of didApplyConfigurationForKey and didNotApplyConfigurationForKey messages the set of keys recorded through didApplyConfigurationForKey will be used since this will in most cases produce a more accurate set of applied keys.

The third party app s delegate is sent the revertConfigurationSet message with an ABTConfigurationSet containing the list of keys to reset as described above. It is important to note that since we do not preserve the old values once the configuration profile has successfully been applied the old values will not be available to the third party app. In this case only the following methods of the ABTConfigurationSet object will return valid keys 

In a corporate scenario an app with the profile manager app functionality may be downloaded to every employee s mobile device. An example of such app is AbsoluteApps provided by Absolute Software. If a profile manager app can obtain configuration profiles for the various third party apps then these third party apps can be configured with very little effort of the part of the user or even automatically. Company IT administrators may push the third party apps and the profile manager app to the employees devices as well as any updates to them.

Another aspect of the invention is its use for server based applications where data is stored on the mobile device. With an external configuration communication method as described herein the system will allow an administrator or remote server to remotely instruct the third party application to remove data from the mobile device. Data removal is not a function of the library but a function of the third party app that is triggered by the configuration profile removal.

An example of such a use may be the configuration and subsequent de configuration of an email account. An email account may be configured via the system with no further user interaction needed. When an employee leaves a company it may be desirable to remove the configuration profile and together with it all the stored data such as company emails.

The entire processes described above may be carried out entirely in the background with none of the apps being brought to the foreground whether it be the third party apps or the profile manager app.

An additional case is where the system is used to configure apps that are provided as part of the operating system. Such apps may have the libraries embedded or they may have access to shared versions and the library may be provided as part of the operating system.

Another additional case is where the system is used to configure an entire set of applications depending on certain conditions e.g. department organizational unit of the device user such that the entire set of applications is configured consistently and will be reset once the user no longer meets the requirements.

The system can be used to transfer configurations in a safe and secure manner since the entire communication can be encrypted and the user will never have to see or handle the unencrypted configuration parameters which otherwise would need to be transferred via semi insecure channels e.g. sending user credentials by mail passing along user credentials manually or on the phone etc. .

Configurations could be force removed if for example the integrity of a device can no longer be guaranteed. This could occur when an iOS device has been jailbroken and company policy requires the configurations not to be stored on devices that may potentially be compromised.

If a new configuration profile is not applied the user may be reminded from time to time using a notification.

More than one configuration profile may be applied to the device for the same third party app. For example it may be simpler to manage the provision of profiles if they are broken down into constituent portions.

In another embodiment when a user starts the profile manager app or brings it to the foreground then configuration profiles may be automatically installed without the user being given the option to confirm.

The library can be provided to the third party app developers in binary form to shield all mechanics from the app developer. All the developer will need to do is to have a few delegate functions implemented. The library will call the delegates with a configuration set object that allows to iterate the fields that should be configured or set to default values.

On platforms using programming languages that do not allow for dynamic delegation other mechanisms can be used e.g. using abstract classes and or abstract methods or callback functions.

When a user opens the third party app directly no configuration profile is supplied in the command to open it. However in another embodiment the third party app may include a library to proactively check the profile manager app to see whether there is a configuration profile to be installed. The profile manager app will then provide the configuration profile to the third party app in a return URL command.

In the configuration profile may be fetched at the same time as the information about the profile which means that step would occur before step .

For larger amounts of data the process can be repeated several times until all the data has been passed from the profile manager app to the third party app. In that case the configuration profile data is passed in data chunks partial configuration profiles via subsequent URL calls.

Besides the configuration of company recommended apps this process can be used to allow any two or more apps to communicate with each other.

The process may be one way in that it is initiated from the profile manager app and just sends configuration data to the third party app. This is simpler but less than ideal because there is no feedback to the profile manager app.

The functionality of the profile manager app may be embodied in the operating system rather than in a third party application.

Communication modes other than URL commands may be used. The principles disclosed herein can apply to other restricted communication methods that can exist in a sandboxed or other equivalent environment.

Library code may be distributed as a shared library instead of a static link library being embedded in third party application.

The system may be used for mobile application management in general rather than specifically for configuration profile management.

While this invention is particularly suited to iOS operating systems it may be applied where other types of operating system are used.

In other embodiments the profile manager app on the remote device may be supported by an agent. Such an agent as used herein is a software hardware or firmware or any combination thereof agent that is ideally persistent and stealthy and that resides in a host computer or other electronic device. The agent facilitates servicing functions which require communication with a remote server. The agent is tamper resistant and is enabled for supporting and or providing various services such as data delete firewall protection data encryption location tracking message notification and software deployment and updates. An illustrative embodiment of a suitable agent is found in the commercially available product Computrace Agent . The technology underlying the Computrace Agent has been disclosed and patented in the U.S. and other countries the patents having been commonly assigned to Absolute Software Corporation. See for example U.S. Pat. Nos. 5 715 174 5 764 892 5 802 280 6 244 758 6 269 392 6 300 863 6 507 914 and 7 945 709 and related patents filed outside the U.S. Details of the persistent function of the agent are disclosed in U.S. Patent Application Publication Nos. US2005 0216757 and US2006 0272020. All of these documents are fully incorporated by reference as if fully set forth herein. Ideally the agent is also persistent and able to self repair if it includes software. It may in part or in whole be located in the BIOS or equivalent location in an electronic device. Communications may be initiated by the agent by the remote server or by both. The agent may be divided into multiple parts in different locations within an electronic device. The agent may ensure the presence of the safe and its integrity and if it is found to be compromised or out of date it can initiate the download of a new safe from the server.

Implementations on iOS devices typically do not involve an agent supporting the system. Instead a configuration profile is deployed which allows the device to be enrolled thus allowing it to be managed using the native features already available on the device. However if the system is implemented on Android devices for example it would typically be supported by an agent.

In some embodiments an agent is not needed at all. Also an enrollment process is not needed as the installation of the profile manager app may be seen as the enrollment process. Once launched the profile manager app would send additional information to the server.

The present description includes the best presently contemplated mode of carrying out the subject matter disclosed and claimed herein. Steps may be performed in a different order to those shown herein. Some steps may be omitted or repeated and other steps may be added. Repositories may be organized in different ways. While specific terminology may have been used herein other equivalent features and functions are intended to be included. The description is made for the purpose of illustrating the general principles of the subject matter and not be taken in a limiting sense the claimed subject matter can find utility in a variety of implementations without departing from the scope of the invention made as will be apparent to those of skill in the art from an understanding of the principles that underlie the invention.

ABTConfigurationSet This class encapsulates a set of configuration values that should be applied together 

ABTConfigManager This is the class that handles all communication to and from AbsoluteApps and also tells the delegate to apply configuration profiles 

The third party app needs to instantiate and configure ABTConfigManager before the first URL is handled. A good place is NSApplicationDelegate applicationDidFinishLaunching . To instantiate and configure the third party app calls either of the configuration methods 

For the sample configuration profile in Appendix 2 the following dictionary is sent to the third party app via the configuration URL for apply requests. Note that the dictionary is displayed as XML for easier reading but the data sent can be in another format e.g. binary plist.

Here the Version value is used to specify the version of the data protocol used always 1 in the first implementation . Category is the com.absolute.thirdpartyconfig.Category value of the payload contents in the configuration profile. Configuration is the com.absolute.thirdpartyconfig.Configuration dictionary value of the payload contents in the configuration profile. The following dictionary is sent to the third party app via the configuration URL for reset requests. Note that the dictionary is displayed as XML for easier reading but the data sent can be in another format e.g. binary property list.

