---

title: Entitlement validation system for games
abstract: An entitlement validation system for laser tag games having a laser tag vest arranged to be activatable for enabling game play has a ticketing module arranged to issue a ticket with a machine readable identification code upon payment made for a selected game, and to update a game entitlement database having identification codes matched with corresponding selected games, a ticket reader arranged to read the identification code of a ticket presented for game activation, a game controller arranged to receive the identification code transferred from the ticket reader and to activate the game equipment upon verifying of entitlement by matching the received identification code with the corresponding selected game in the database. The system may have a base station arranged as a communications link between the ticket reader and the game controller. The ticket reader may be integrated into the game equipment or installed in a validation activation station.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09070126&OS=09070126&RS=09070126
owner: LASERFORCE INTERNATIONAL PTY LTD.
number: 09070126
owner_city: Queensland
owner_country: AU
publication_date: 20130502
---
THIS INVENTION relates to an entitlement validation system for games and in particular but not limited thereto the system is for a laser tag game.

A large number of games such as laser tag games are played with a game equipment such as a laser tag vest which must be activated by a responsible personnel of a business. The personnel will need to check that the customer has paid for the game before activating the game equipment. In all current laser tag game systems known to the applicant the processes of customer payment and activation of game equipment are completely separate.

The game equipment will work even if the customer has not paid. Fraud prevention if any can only be done after the fact by reconciling the number of games played against the number of games paid for.

To minimise game leakage due to people playing without payment or continuing to play after completion of paid for games resources including additional personnel must be extended to do the reconciliation processes for the equipment being used by customers. The reconciliation processes therefore add substantial costs to businesses.

An object of the present invention is to provide an entitlement validation system for games which alleviates or reduces to a certain level one or more of the above mentioned prior art problems.

In one aspect therefore the present invention resides in an entitlement validation system for games having a game equipment arranged to be activable for enabling game play. The system comprises a ticketing module arranged to issue a ticket with a machine readable identification code upon payment made for a selected game and to update a game entitlement database having identification codes matched with corresponding selected games a ticket reader arranged to read the identification code of a ticket presented for game activation a game controller arranged to receive the identification code transferred from the ticket reader and to activate the game equipment upon verifying of entitlement by matching the received identification code with the corresponding selected game in the database.

The ticketing module may have selectors for different games and or services. The ticketing module may also have one or more slots for insertion of coins and or notes and or transaction cards such as credit cards and debit cards. The ticketing module is preferably a point of sale POS terminal.

The identification code on the issued ticket may be in the form of a barcode or carried on a magnetic strip or RFID tag or other mechanism.

The system may have a base station arranged as a communications link between the ticket reader and the game controller. Preferably the base station is arranged to receive data representing the identification code and selected game from the ticket reader and to transfer the received data to the game controller. The ticket reader may be integrated into the game equipment or installed in a validation activation station such as a booth where the customer stands.

In preference the game controller upon verifying a match of the data representing the received identification code with the corresponding selected game which has not been marked as consumed in the database is arranged to transfer an activation signal to the game equipment. The activation signal may be transferred directly to the game equipment or via the base station.

The game controller may be arranged to update the database by inserting data representing consumption of the game corresponding to the identification code following transfer of the activation signal.

The game controller may also be arranged to transfer a rejection signal to the game equipment where entitlement of the identification code cannot be verified. Preferably the game equipment has an indication unit arranged to provide a visual and or audio indication upon receiving an activation signal and or the rejection signal.

Referring to the drawings and initially to there is shown an embodiment of the game entitlement verification system according to the present invention. The system in this embodiment is for a laser tag game having a laser tag vest game equipment activation of which is to be controlled depending on verification of entitlement of a machine readable ticket .

The ticket is issued by a ticketing module which is a POS terminal in this embodiment. Upon receiving an appropriate payment for a game or service an operator can press a ticket issue button not shown for issuing a machine readable ticket for the selected game service. The module may be a fully automated POS terminal which has selection buttons for selection of a game or service and payment slots where cash or a transaction card can be inserted for making payment. The selection buttons may be in the form of icons on a monitor.

As shown in the ticket for this embodiment is in the form of a plastic card with a substantially rectangular shaped plastic body A and a magnetic strip B where an identification code not shown is stored. The ticket can be in any other form having an identification code which can be read by a machine. Examples of such identification codes are a barcode RFID tag text numeral reference and other mechanism.

The ticketing module has a data storage where a database containing identification codes of issued tickets and selected games for the issued tickets are stored. The database also has markings for consumed games. An example of the database is as follows 

The vests game equipment has a ticket reader and is in wireless communication with a game controller via a wireless base station .

To play a game the laser tag vest game equipment must receive an activation signal from the controller . The system requires an issued ticket to be verified for determining whether the customer presenting the ticket read by the reader does or does not have entitlement to play. In the determining process the base station retrieves the data representing the identification code on the read ticket and transfers the data to the controller . The controller then searches the database in the storage for a match with any of the ticket IDs in the database. If a match is found and the game for this ID has not been consumed the controller sends an activation signal for the game type and number of games listed for this ID. The base station transfers the activation signal to the vest which on receiving this signal provides a verbal indication that the selected game is ready to be played. If a match is not found the controller sends an invalid signal to the vest . The vest than provides a verbal message to inform customer that the ticket is not valid.

The laser tag game controller communicates with the POS terminal by way of an application programming interface API . This API has two functions 

The machine readable ID on the ticket the Ticket ID can be anything as long as it uniquely identifies the ticket. A simple incrementing number sequence like 00017321 00017322 etc may be suitable in many situations. This number is then encoded in the barcode or magnetic stripe on the card. In the case of RFID cards these normally come pre programmed with a unique identifier the Card ID and this can be used as the ticket ID.

In an alternate embodiment the game type mentioned above is filled in by the laser tag game controller. An example of the process for this alternate embodiment is as follows 

Whilst the above has been given by way of illustrative example of the present invention many variations and modifications will be apparent to those skilled in the art without departing from the broad ambit and scope of the invention as herein set forth in the following claims.

