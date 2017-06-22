---

title: System and method for mapping a voice identity across multiple telephony networks with time attributes
abstract: A method and system includes: one or more phone systems; a policy processor coupled to the phone systems; and a voice identity mapping policy stored in a data storage, the data storage being accessible to the policy processor. The voice identity mapping policy includes: a plurality of search voice identities mapped to one or more target voice identities, where the plurality of the search voice identities are applicable to a plurality of users, where each of the search voice identities and the target voice identities comprises a username for one of the plurality of users, and time attributes indicating when the voice identity mapping policies are valid. When a voice identity for a recipient of a call is received, the policy processor checks for the voice identity mapping policy associated with the voice identity. The call is then forwarded to the target voice identity in the voice identity mapping policy.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09413895&OS=09413895&RS=09413895
owner: TP LAB, INC.
number: 09413895
owner_city: Palo Alto
owner_country: US
publication_date: 20130605
---
This application is a continuation of co pending U.S. patent application Ser. No. 11 926 390 filed on Oct. 29 2007 which in turn is a continuation in part of U.S. patent application Ser. No. 10 980 046 filed on Nov. 2 2004 and issued as U.S. Pat. No. 7 391 858 on Jun. 24 2008.

This invention relates generally to telecommunications and more specifically to how calls are routed based on mapping multiple voice identities.

The widespread adoption of numerous telephony and data communication technologies such as cellular phones voice over IP virtual private networks broadband access digital subscriber lines cable modems and other access methods have changed the way people use phones and the way people communicate. Increasingly people are associated with multiple telephone numbers that require callers who are trying to reach them to try multiple telephone numbers.

Typically a corporate telephone system user will have a corporate extension telephone number a personal or corporate mobile telephone and possibly a remote home or branch office telephone number. To finally reach a user a caller may need to dial two or more telephone numbers before they finally reach the user to whom they wish to speak. In addition to the time it takes the caller to dial multiple telephone numbers it takes even more time for the user to then retrieve multiple messages when a caller leaves repetitive voice messages on multiple voice message systems. In this scenario time is not the only asset at stake. Information can also be lost or confused by redundant voice messages on multiple systems making for inefficient communication that can cost time money and opportunities.

In one scenario of a work place a user typically has an office phone on his desk and carries a personal cellular phone. When the user is in his office he can be reached on his office phone and his cellular phone. When he is in a meeting or in a break room he can only be reached directly on his cellular phone. When a caller tries to reach a user on his office phone and cannot reach him the caller has to try to call the user s cellular phone. When the user cannot be reached on either phones the caller may decide to leave him a voice mail on either one or more of the user s voice answering systems.

In another scenario the user visits a branch office in a different city. He carries along his cellular phone. In the branch office he has an office phone with a phone number different from that of his original office phone. The user would need to inform callers of the new phone number if he wants to be reached on the branch office phone. In this scenario callers may have to try three phone numbers the original office phone number a temporary office phone number and a cellular phone number before they actually reach the user.

In another scenario the user travels abroad to another country. He decides not to bring his cellular phone because he does not have international roaming services. Instead he rents a local cellular phone. He would then need to inform potential callers of the new temporary phone number. Callers not informed of the new temporary phone number would have to try his office phone cellular phone and then perhaps leave him a voice mail possibly never knowing whether or not the user receives the voice message. The user would then have to check his voice messages very frequently in order to respond to the calls promptly. In this scenario the user severely limits his accessibility.

In yet another scenario a user occasionally works from home according to some schedule. While working at home the user s home phone is his primary means for communication. For callers who are aware that the user works from home on any particular day they would call his home phone. Other callers who do not know the user s work schedule would have to leave voice mail on his office phone. In order to ensure that he is responding to telephone calls promptly the user would need to check his office based voice messages continuously throughout the day. Despite the fact that a user has access to one or more telephones it is not always easy for callers to reach them easily.

Thus there is a need for a system that transparently allows a caller to efficiently reach a user or his primary voice message system.

This invention resides in a system and method to map a voice identity to a telephone number. The voice identity including a username. A user has a plurality of phones and each phone has a phone number. The user informs potential callers of the user s voice identity which includes the user s username. The user has immediate access to one or more of the phones. When a caller places a call using the user s voice identity the phone call is routed to one of his immediately accessible phones or a designated voice application such as voice mail based on a voice identity mapping policy.

A voice identity is a designation assigned to a specific user that callers can use to reach that user. Typically a voice identity is a telephone number or an extension number. illustrates a voice identity with voice identity sub number. Here is the primary voice identity number and is an optional voice identity sub number. If multiple users share the same voice identity number voice identity sub number further distinguishes an individual user. In one embodiment of the present invention the voice identity number corresponds to a main corporate telephone number and voice identity sub number corresponds to an internal extension number.

In one embodiment the user has a residential phone. The residential phone number is the user s voice identity number without a voice identity sub number.

In one embodiment the user works for a company. The user has an office desk phone which is assigned an extension number. Within the corporate system the office desk phone extension is the user s voice identity number without a voice identity sub number. Optionally in the same embodiment the user is also assigned an external phone number that is used outside the company. The external phone number is yet another voice identity.

In one embodiment a company has a main business phone number and the user is assigned an extension number. To reach the user an external caller would first dial the company s business phone number and then the extension. In this embodiment the voice identity comprises two parts the business phone number is the voice identity number and the extension is the voice identity sub number.

In one embodiment the user is assigned an internal extension that is tied to a voice mail box but is not tied to any office phone. In such an embodiment the internal extension is the user s voice identity.

In one embodiment the user subscribes to voice over IP services receives a username with which callers within the voice over IP service can use to reach him. In such an embodiment the username can be a voice identity without sub number. In one embodiment a voice over IP service is based on instant messaging IM technologies such as Yahoo Messenger Microsoft Messenger AOL IM Skype or other IM based voice services. In one embodiment the username can be an IM identity or an email account identity. In one embodiment the voice over IP services include a corporate phone service and the username can be an employee s computer user identity.

In one embodiment a user receives a username and additionally a phone number with which callers outside the voice over IP service can reach him. Both the username and the phone number can be voice identities. Optionally the voice over IP service provider has a main phone number and each user is assigned an internal number. A caller outside the service first calls the voice over IP service provider s main phone number and then enters the internal number to reach the user. The voice over IP service provider main phone number is the voice identity number and the internal number is the voice identity sub number.

In one embodiment a caller intends to leave a user a voice mail message. In this embodiment the voice mail number is the user s voice identity. Typically a voice mail number is a phone number. If more than one user uses the same phone number as a voice identity number that voice mail number can further include a sub number to identify a specific user. The sub number is the voice identity sub number for the user.

In the above examples example 1 has voice identity number 1 415 555 1234 and no voice identity sub number example 2 has voice identity number extension 9876 and no voice identity sub number example 3 has voice identity number 1 510 555 6789 and voice identity sub number 4567.

A voice identity can be a phone number with which a user receives the phone call. Typically the voice identity is associated with a phone at which the user receives the call. In one embodiment the user does not intend to receive phone calls but rather to receive voice mail instead. In such an embodiment there is no phone associated with a phone number voice identity. Instead the voice identity is merely an access number to call the user s voice mail system.

A voice identity mapping allows a user to associate a voice identity to another voice identity. illustrates a voice identity mapping. Here is the search voice identity that callers actually call to reach a specific user and is the target voice identity at which the user will receive the call. Typically when a caller calls the search voice identity the call is forwarded to the target voice identity. In common phone usage the search voice identity is the same as the target voice identity such that no call forwarding is necessary.

Optionally a voice identity mapping further comprises a time attribute . The time attribute indicates when a voice identity mapping is valid.

Example 1 illustrates the search voice identity is extension 4567 without sub number with the target voice identity 1 415 555 9876 without a sub number and a time attribute that reads the mapping is valid between 12 midnight to 8 am Monday through Friday and between 6 pm in the evening to 12 midnight Monday through Friday.

Example 2 illustrates a search voice identity 1 650 555 4321 and target voice identity 1 510 555 4165 with a time attribute indicating the mapping is valid between 12 midnight Saturday to 12 midnight Monday.

Example 3 illustrates a search voice identity 1 650 555 4322 and target voice identity 1 510 555 4167 with a time attribute reading the mapping is active between the dates Sep. 21 1995 and Mar. 3 1996 inclusively.

A voice identity mapping policy is a group of one or more voice identity mappings. In one embodiment a voice identity mapping policy applies specifically to one user.

In one embodiment a voice identity mapping policy applies to a group of users. In this embodiment some voice identity mappings may be specific to individual users while other voice identity mappings may apply to a plurality of users.

In above Voice Identity Mapping Policy 1 the voice identity mapping policy has six voice identity mappings. The user is an employee in a company. The company has a main business phone number 1 800 555 5600. The user has an office desk phone with an extension 4567. The user also has a personal cellular phone 1 415 555 1234. At home the user has two phone lines. The main home phone line has number 1 415 555 2300. The second home phone line which he uses for Internet dial up access has number 1 415 555 2598. The user s parents live in Canada and have a home phone 1 416 555 4165.

Voice identity mappings 1 and 2 of Voice Identity Mapping Policy 1 above indicates the user desires to forward his business phone to his main home phone during non working hours weekdays between 6 pm and 8 am and weekends. Voice identity mapping 3 states calls placed to the user s cellular phone number are forwarded to his main home phone. Voice identity mapping 4 shows the user s second home phone line is always forwarded to the main home phone line. Voice identity mapping 5 shows the user has a vacation trip to visit his parents in Canada during summer of 2002 from August 7 to 14.

When a call is made the voice identity mappings in a policy are applied to the call. The mappings are applied until no more mapping is found applicable. If no mapping is found applicable in the process the voice identity mapping policy is not applicable to the call. Otherwise the final resulting target voice identity is used for the completion of the call according to the voice identity mapping policy. The attributes of all applicable mappings are enforced.

In a voice identity mapping policy the target voice identity of a voice identity mapping may be a search voice identity of another voice identity mapping. The target voice identity of the latter mapping can be the search voice identity of yet another voice identity mapping. It is perfectly legitimate that among a group of voice identity mappings target voice identities and search voice identities can form a transitive chain where a target voice identity of a voice identity mapping is the search voice identity of the next voice identity mapping.

In one embodiment a voice identity mapping policy may not yield a resulting target voice identity when applied to a call. When this happens the call cannot be completed according to the voice identity mapping policy.

In one embodiment when a call cannot be completed according to a particular voice identity mapping policy a policy processor uses the original search voice identity as the resulting target voice identity.

In another embodiment when a call cannot be completed according to a particular voice identity mapping policy a policy processor rejects the call.

In one embodiment when a call cannot be completed according to a particular voice identity mapping policy a policy processor selects another voice identity mapping policy matching the original search voice identity. If there is no further matching voice identity mapping policy the policy processor may reject the call or uses the original search voice identity as the resulting target voice identity.

In the example Voice Identity Mapping Policy 1 above the target voice identity of voice identity mapping 1 is a search voice identity of the voice identity mapping 5. The target voice identity of the voice identity mapping 5 is not a search voice identity of any voice identity mapping. During the time between 6 pm to midnight on Fridays any call to corporate extension 4567 is forwarded to 1 415 555 2300. One or more phones associated with the resulting target voice identity will ring and the user answers the call. If the process cannot be completed due to transitive mapping the call cannot be completed.

In one embodiment if a call cannot be completed due to transitive mapping the call is forwarded to the first target voice identity.

Upon successful authentication the gatekeeper passes the user s access information to a policy processor . If the information indicates creation of a new voice identity mapping policy the policy processor verifies the correctness by prompting the user to confirm and stores the new voice identity mapping policy into data storage . If the information indicates modification of an existing voice identity mapping policy the policy processor verifies the correctness by prompting the user to confirm and stores the modified voice identity mapping policy into data storage .

In one embodiment gatekeeper is software application executed on an integrated application server in a telephony system.

In one embodiment gatekeeper is software application executed on a stand alone computer system coupled to a telephony system.

In one embodiment gatekeeper is application specific integrated circuit coupled to a telephony system.

In one embodiment policy processor is software application executed on an integrated application server in a telephony system.

In one embodiment policy processor is software application executed on a stand alone computer system coupled to a telephony system.

In one embodiment policy processor is application specific integrated circuit coupled to a telephony system.

In one embodiment the phone system is an IP telephony system comprising of a soft switch. Optionally the IP telephony system further comprises a media gateway.

Upon receiving the calling number the phone system queries the voice identity mapping policy processor . The input called number is fed to the policy processor . The policy processor treats the input called number as a search voice identity. It matches the search voice identity against the search voice identities of voice identity mapping policies in the database through coupling . If there is no match the policy processor informs the phone system through that no policy applies and the phone system should proceed with the normal call processing.

In one embodiment policy processor is software application executed on an integrated application server in phone system .

In one embodiment policy processor is software application executed on a stand alone computer system coupled to phone system .

In one embodiment policy processor is application specific integrated circuit coupled to phone system .

If there is a match the policy processor selects one matching voice identity mapping policy from the database . In one embodiment the policy processor selects the first matching voice identity mapping policy.

In one embodiment the policy processor selects the most frequently applied matching voice identity mapping policy amongst all matching voice identity mapping policies.

In one embodiment the policy processor selects the most recently applied matching voice identity mapping policy.

The policy processor determines from the policy the first voice identity mapping whose search voice identity matches the input voice identity. It further validates the attributes of the voice identity mapping. If the attribute contains a time attribute the policy processor validates with the current time. If the time is not valid the policy processor determines the next voice identity mapping in the voice identity mapping policy. If the policy processor exhausts all voice identity mappings in the selected voice identity mapping policy without finding a valid voice identity mapping it selects another matching voice identity policy from the database until no more voice identity policies can be found or a voice identity mapping is validated.

In one embodiment when no voice identity policy can be found the policy processor informs the phone system through to direct the call to the phone number indicated by the input voice identity.

In one embodiment when policy processor validates a voice identity mapping it determines the target voice identity from the voice identity mapping. Policy processor uses the target voice identity as the input voice identity and repeats the process above to determine a voice identity mapping policy and a voice identity mapping.

The policy processor processes accordingly and identifies a chain of zero or more voice identity mappings that are applicable to the original input voice identity with a current input voice identity. The policy processor informs the phone system through the result that the call should be forwarded to the current input voice identity. The phone system further processes the call to the resulting phone number.

In one embodiment a voice identity mapping policy contains transitive mappings such that a target voice identity of a voice identity mapping is the search voice identity of another voice identity mapping. Optionally the time attributes may contain overlapping time periods in which two or more voice identity mappings are valid at the same time. In such an embodiment a transitive mapping occurs. Policy processor may not be able to terminate the processing due to transitive mappings. The policy processor may decide after a number of mapping selections to stop further processing.

In one embodiment the policy processor stops after a set number iterations of finding matching voice identity mappings.

In one embodiment the policy processor checks if a matching voice identity mapping was used previously during the processing of the input voice identity. If a repeat is found the policy processor determines that the processing may not terminate and stops the processing.

In one embodiment the policy processor checks for repeating target voice identity and stops upon a repeat. The policy processor concludes there is no matching voice identity mapping within the policy.

In one embodiment the policy processor determines existence of transitive mappings and stores in the database voice identities that cannot be resolved successfully due to the transitive mappings. Upon receiving the input search voice identity the policy processor first checks if the input search voice identity matches any identified irresolvable voice identities before searching for a matching voice identity mapping or voice identity mapping policy.

In one embodiment human operators upon receipt of work orders configure the forwarding entries manually.

In one embodiment phone systems have an application programming interface allowing another system to automatically configure the forwarding entries.

In after the policy processor receives a voice identity mapping policy as described for it processes the voice identity mappings in a voice identity mapping policy to determine based on the time attributes the date and time when the voice identity mappings should be activated or de activated. The policy processor determines the next time instance when one or more of the voice identity mappings are to be activated. It sets up a timer for the time instance. It monitors the time based on the time input from the clock . When the timer expires the policy processor retrieves the voice identity mapping policy associated with the time from the data storage . Policy processor selects all voice identity mappings that are to be activated at a particular time processes the selected voice identity mappings into a list of phone number forwarding mappings. It further splits the list of phone number forwarding mappings into multiple lists one for each of phone systems based on the phone numbers owned by each phone system. The policy processor generates for each list of phone number forwarding mappings intended for a phone system a forwarding configuration . It then passes the forwarding configuration to the phone systems .

In one embodiment the forwarding configuration is a work order such that a human operator can configure the phone system .

In another embodiment forwarding configuration is sent to the phone system using the application programming interface for phone systems. In addition to sending the forwarding configuration lists to the phone systems the policy processor sets up a timer for the next voice identity mapping activation change either to activate a voice identity mapping or to deactivate a voice identity mapping.

In one embodiment the each of phone systems may have different phone number forwarding capabilities. For example phone system may not handle transitive forwarding mappings while phone systems and can. When the policy processor generates the forwarding configuration list for phone system it retrieves the information about the capability of the phone system from the data storage . It then resolves all transitive mappings in the forwarding configuration and generates a forwarding configuration without transitive mapping.

In a caller makes a call from a phone . The phone number information is sent to the phone system . The phone system checks against the forwarding mapping configuration to see if there is a matching forwarding mapping. If a matching forwarding mapping exists phone system determines the next phone number to which the call should be forwarded based on the forwarding mappings and uses the next phone number for call routing. If no matching forwarding mapping exists the phone system continues the call routing based on the original phone number. Phone system upon call routing processing which is known to the skill in the art may determine that the next phone number belongs to phone system . The phone system would then pass phone number which may be the next phone number to the phone system . The phone system processes the incoming phone number similarly to that of the phone system and may determine that the next phone number belongs to phone system . The phone system would then pass the phone number information to the phone system . The phone system processes the incoming phone number similarly to that of phone system . This process continues with zero or more phone systems until a phone system determines there are no forwarding mappings and routes the call according to its internal routing protocols.

Telephone service operator offers a plurality of voice services provided by a plurality of phone systems Class 5 telephony switch corporate PBX mobile switching center and IP telephone system . In one embodiment the plurality of voice services include residential voice services corporate voice services mobile voice services and voice over IP services. In one embodiment Class 5 telephony switch provides residential voice services corporate PBX provides corporate voice services mobile switching center provides mobile voice services and IP telephony system provides voice over IP services. Telephone service operator offers voice identity mapping services among the phone systems Class 5 telephony switch corporate PBX mobile switching center and IP telephone system . Operator includes policy processor and data storage . Data storage includes voice identity mapping policies for the voice identity mapping services. Policy processor connects to data storage and the plurality of phone systems Class 5 telephony switch corporate PBX mobile switching center and IP telephone system .

Foregoing described embodiments of the invention are provided as illustrations and descriptions. They are not intended to limit the invention to precise form described. In particular it is contemplated that functional implementation of invention described herein may be implemented equivalently in hardware software firmware and or other available functional components or building blocks and that networks may be wired wireless or a combination of wired and wireless. Other variations and embodiments are possible in light of above teachings and it is thus intended that the scope of invention not be limited by this Detailed Description but rather by Claims following.

