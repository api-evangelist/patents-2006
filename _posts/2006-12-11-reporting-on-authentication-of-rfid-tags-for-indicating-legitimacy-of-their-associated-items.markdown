---

title: Reporting on authentication of RFID tags for indicating legitimacy of their associated items
abstract: RFID readers, computers, and methods are provided for reporting on the authentication of one or more RFID tags associated with a proffered item, while requiring special permissions be cleared before reporting. In some embodiments, a question is input about whether a Declared Password (DP) is regarded as proper for an Item Identifier (II), both of which have been input from the tags. An answer is generated for the question from the reference database, and transmitted to the user. The answer does not reveal an Actual Code that is indeed regarded as proper, unless the user first demonstrates they already know it. Beyond the authentication of the tag, the answer can further indicate the legitimacy of the proffered item, for a supply chain, at a Customs Office, etc.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07633376&OS=07633376&RS=07633376
owner: Impinj, Inc.
number: 07633376
owner_city: Seattle
owner_country: US
publication_date: 20061211
---
This utility patent application claims the benefit of U.S. Provisional Application Ser. No. 60 749 864 filed on 2005 Dec. 12 which is hereby claimed under 35 U.S.C. 119 e . The provisional application is incorporated herein by reference for all purposes.

The present application may be found to be related to U.S. patent application entitled HANDLING LEGITIMATE AND UNAUTHORIZED ITEMS IN SUPPLY CHAIN ACCORDING TO AUTHENTICATION OF THEIR RFID TAGS Ser. No. 11 637 372 filed with the USPTO on the same day as this patent application.

The present application may be found to be related to U.S. patent application entitled DETERMINING AUTHENTICATION OF RFID TAGS FOR INDICATING LEGITIMACY OF THEIR ASSOCIATED ITEMS Ser. No. 11 637 479 filed with the USPTO on the same day as this patent application.

The present description addresses the field of Radio Frequency IDentification RFID systems and more specifically to systems devices and methods for reporting on whether RFID tags are authenticated to indicate the legitimacy of items they are attached to.

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers the latter are also known as RFID reader writers or RFID interrogators . RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a power management section a radio section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

A problem has been that legitimate supply chain activities are undermined by illegitimate activities. This problem is now described in more detail.

Link is for a manufacturer which manufactures an item . Item can be anything that is bought and sold for money such as a consumer good a component for a consumer good and so on. Item travels within the chain according to the general direction of arrow . For example item can be transported according to transportation links and and then stored in a warehouse . Warehouse can serve as a distribution center from where item can be directed via another transport link to a desired retail outlet . While there it can be bought by consumer for money .

Money ultimately pays for item . Here money is shown traveling within chain according to the general direction of arrow opposite of arrow for paying for every one of the activities and services of chain . Payment however need not be made explicitly at each node between successive links. Items can be manufactured and delivered across links according to supply agreements while payment is made according to arrangements specified in related legal agreements.

Domain also includes unauthorized overproduction by a manufacturer . That is even a legitimate manufacturer after fulfilling an order to manufacture a certain supply of items manufactures more of them and sells them in the gray market. Domain can also include theft from any link in chain which results in item being diverted into the gray market.

Items emerge from illegitimate domain by a number of activities such as introduction or reintroduction into legitimate supply chain fraudulent returns by some posing as consumers and direct sales to consumers .

The illegitimate activities of domain hurt honest businesses and in turn consumers in the form of higher prices.

The problem of introduction or reintroduction and fraudulent returns is now described in more detail.

Agent does not know whether proffered item is legitimate or not. Agent may be concerned about accepting items in such transactions if the items are illegitimate. Indeed the activity of offering arrow could be part of the legitimate progress of item within a supply chain or a fraudulent import or a fraudulent reintroduction or even a fraudulent return .

The concern of agent is shown by thought bubble . Should he accept the proffered item Should he also pay or promise to pay money for it or give it an import license 

Note that the concern is not alleviated by the fact that proffered item is even tagged by an RFID tag . The concern can also be whether tag is legitimate or stolen counterfeit cloned by replicating the data of a legitimate tag etc.

More particularly RFID readers computers software and methods are provided for reporting on the authentication of one or more RFID tags associated with a proffered item while requiring special permissions be cleared before reporting. In some embodiments a question is input about whether a Declared Password DP is regarded as proper for an Item Identifier II both of which have been input from the tags. An answer is generated for the question from the reference database and transmitted to the user. The answer does not reveal an Actual Code that is indeed regarded as proper unless the user first demonstrates that he already knows it.

Beyond the authentication of the RFID tag the answer can further indicate the legitimacy of the proffered item. When an item s RFID tag data is not authenticated a conscientious person can refuse to accept it a Customs Agent can intercept it etc. This will in turn diminish the incentive for illegitimate activities.

The invention offers the advantage that protection is accomplished by how the reference database is hosted. This avoids the need to add defensive features to the RFID tags so they could withstand attacks. As such the expense of generating RFID tags need not increase.

These and other features and advantages of the invention will be better understood from the specification of the invention which includes the following Detailed Description and accompanying Drawings.

The present invention is now described. While it is disclosed in its preferred form the specific embodiments of the invention as disclosed herein and illustrated in the drawings are not to be considered in a limiting sense. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. Indeed it should be readily apparent in view of the present description that the invention may be modified in numerous ways. Among other things the present invention may be embodied as devices methods software and so on. Accordingly the present invention may take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment combining software and hardware aspects. This description is therefore not to be taken in a limiting sense.

As has been mentioned the present invention includes a scheme for authenticating RFID tags to indicate the legitimacy of their associated items. The scheme is now described in more detail.

Tag is formed on a substantially planar inlay which can be made in many ways known in the art. Tag includes an electrical circuit which is preferably implemented in an integrated circuit IC . IC is arranged on inlay .

Tag also includes an antenna for exchanging wireless signals with its environment. The antenna is usually flat and attached to inlay . IC is electrically coupled to the antenna via suitable antenna ports not shown .

The antenna may be made in a number of ways as is well known in the art. In the example of the antenna is made from two distinct antenna segments which are shown here forming a dipole. Many other embodiments are possible using any number of antenna segments.

In some embodiments an antenna can be made with even a single segment. Different places of the segment can be coupled to one or more of the antenna ports of IC . For example the antenna can form a single loop with its ends coupled to the ports. When the single segment has more complex shapes it should be remembered that at the frequencies of RFID wireless communication even a single segment could behave like multiple segments.

In operation a signal is received by the antenna and communicated to IC . IC both harvests power and responds if appropriate based on the incoming signal and its internal state. In order to respond by replying IC modulates the reflectance of the antenna which generates the backscatter from a wave transmitted by the reader. Coupling together and uncoupling the antenna ports of IC in rapid succession can modulate the reflectance as can a variety of other means.

In the embodiment of antenna segments are separate from IC . In other embodiments antenna segments may alternately be formed on IC and so on.

The electrical circuit in IC includes a memory which can store data and optionally . These data are typically in the form of 0s and 1s whose combination means something either directly according to protocols or by encryption. Such data is written at different portions of memory as will be evident to a person skilled in the art referenced by proper pointers and so on. These data can be communicated to an RFID reader that interrogates RFID tag as will be described later in this document.

In the example of data is for an Item Identifier II . According to a comment the II can be a code for identifying the item that tag is associated with. For more robustness it is preferable that if RFID tagged items are presented in a group each tag have its own unique II although that is not necessary.

Any code can be used as an II or a portion of an II. For example the II can include a designation about the item which is assigned according to a proprietary scheme of assigning identifying numbers. Or the scheme can be a scheme known to the public such as devised by an organization called EPCglobal. EPCglobal s scheme includes numbers that are unique and are called Electronic Product Code EPC . In addition one or more IIs can be used for the item.

In addition data is a stored Declared Password DP . According to a comment DP is a declared password for II . In some embodiments DP can be read from tag separately from II . In some embodiments DP can be inputted by being interpreted from II .

Any code can be used as a DP or a portion of a DP. For example a DP can be a binary code such as 4 8 or 16 bits long. All or a portion of it can optionally be generated by a random process to confound efforts to discern patterns in numbering of tags. Or a portion of the DP can designate another action pertaining to the item that tag is attached to namely it can be a date stamp or time stamp for its receipt and so on. In addition one or more DPs can be used for an II.

According to a comment tag is authorized i.e. considered legitimate if its DP is regarded as proper for its II according to a reference database . Of course to preserve the secrecy of which DPs correspond to which IIs access to the data of reference database is controlled by permissions according to a variety of possibilities as described later in this document.

In some instances reference database is a default for the transaction. In other instances reference database is identified with the help of Reference Database Identifier RDI data . RDI data can be obtained from tag separately from it e.g. electronically from another party or both. For example RDI data can be a reference database identifier code.

RDI data can be obtained from tag in a number of ways. One such way is to scan tag with an RFID reader and read out RDI data along with II data and DP data . Another way is to assign an II such that the RDI can be determined from the II . One more way is to assign a DP such that the RDI can be determined from the DP .

In some instances reference database is accessible by an electronic communications network. This is preferable if reference database is hosted by an Authentication Service for IIs or the like. In those instances the first RDI can be used to identify reference database in the network. For example it can include a network address or contact information for an operator of the database such as the Authentication Service.

As will be realized a number of implementations are possible. For example one RDI can correspond to one II and be used to select between one or more inputtable IIs. Selection can be according to consistency in coding locations in tag memory of where data is stored etc. In addition one RDI can correspond to one DP and be used to select between one or more inputtable DPs and so on. Multiple RDIs can be available and one or more can be used for a pair of II and DP to authenticate tag and so on.

At optional operation a party can be proffered an item which is associated with one or more Radio Frequency Identification RFID tags. Proffering can be as shown above in . The proffered item can be associated with one or more Radio Frequency Identification RFID tags in any number of ways. One or more RFID tags can be used for the item. If the item includes individual components the item may have multiple tags even if each component started out with only one tag. The RFID tag or tags can be attached to the item or to its package. The attachment can be removable or not and so on as is known in the art of RFID tagging.

At next operation it is determined whether an authentication condition is met. If it is not met then at next operation the item proffered at operation is rejected for the proposed exchange or transaction. In the case of imports rejection can be by denying importation. At optional next operation another action can be taken such as returning the item if already delivered reporting the proposed transaction confiscating the item for surrendering it to authorities destroying it in some circumstances and so on. If at operation the authentication condition is met then at next operation the proffered item is accepted for the exchange or transaction or importation.

A number of authentication conditions can be used according to the invention. In the preferred embodiment the authentication condition includes that an Item Identifier II can be read from the one or more RFID tags of operation . The readable II can be stored either in a single tag or in a combination of tags which can be cooperating or not. If the item is scanned by an RFID reader the II will be read.

According to some optional embodiments it can be required that according to operation the II be listed as corresponding to the proffered item in an Item Identifier II database . This way agent can check whether the II of the tag is realistic for the proffered item. Checking will depend on how II database is hosted.

II database can be hosted so that it is accessible publicly or with very few restrictions such as merely registering a user by name not affiliation type. For example if the II is the EPC the organization that administers them EPCglobal can offer a lookup system.

Alternatively II database can be hosted so that it is accessible privately for one two or more parties that have permissions as indicated by optional II permissions clearance block .

As will be realized from this entire document in some instances it behooves agent and others in the supply chain to insist that a consistent Item Identifier be used for each transition or transaction of the item as it advances through the links of the supply chain. This way verifiability will be improved. One such way is for all to implement a well known and easily accessible system like the EPC system.

The authentication condition can also include as indicated at operation that the II be authorized. In many embodiments this means that a stored Declared Password DP can be inputted from the one or more RFID tags and that the DP is regarded as proper for the II as per a reference database whose data is available only subject to permissions. In some preferred embodiments the DP is readable from the same RFID tag as the II.

At optional operation an RDI is acquired. The RDI corresponds to data of tag and can be acquired either by scanning the item that has tag on it or be received separately from a party proffering the item tagged with tag or otherwise be or become known. In some embodiments it can be required that the RDI be readable from the tag as part of the authentication condition.

At optional operation an II is acquired. The II corresponds to data of tag and can be acquired either by scanning the item that has tag on it or be received separately from a party preferring the item tagged with tag or otherwise be or become known.

Operation enables optional operation to take place. If the II is wrong for item then the proffered item can be rejected as per operation .

If the II is right for item then it is determined whether the II is authorized. At a next operation an inputtable DP is acquired. At a next operation it is determined whether the acquired DP is regarded as proper for the acquired II by the reference database identified by the RDI of operation . Execution proceeds according to the determination with accepting the item operation if the DP is regarded as proper or rejecting the item operation if the DP is not proper.

Operation may be performed in any number of ways as will be seen in this document. One such way is to construct a question about whether the acquired II is regarded as proper for the acquired DP and apply the question to the reference database. The reference database can be the same as was described for reference database . Depending on how reference database is hosted a REF reference database permissions clearance block may have to be cleared. REF permissions clearance block may be the same or different than II permissions clearance block and represents a group of permissions.

In a preferred embodiment the REF permissions include that a DP that is indeed regarded as proper for the readable II is generally not revealed to the offeror. It is revealed only indirectly if the offeror first demonstrates they already know of a DP that is regarded as proper for the readable II. The reason this is preferred is to ensure that an offeror within the not legitimate domain cannot learn a valid DP and write it to the tag memory. It will be understood that even if they obtain a valid DP by scanning an authorized similar item that obtained DP will become invalid if and when the owner of the authorized similar item changes the DP both on the tag and on the reference database.

The REF permissions can include variations. For example a DP that previously could be determined as regarded as proper for the readable II can be revealed to the offeror but it will be of no more value and so on.

Another variation is that the same restriction also applies to agent in other words they cannot learn from the reference database the valid DP but only get their questions answered about whether a proposed DP is regarded as proper. This way agent learns the valid DP only if he first demonstrates he already knew it.

In some embodiments the REF permissions include that agent needs no permission to be able to determine whether an inputtable DP is regarded as proper for the readable II by the reference database. This could be with or without agent being required to merely register as a user by name and possibly receiving a user code when they log in.

In other embodiments the REF permissions include that agent needs further permissions to be able to determine whether an inputtable DP is regarded as proper for the readable II by the reference database. In some of these embodiments they may obtain review privileges such as from the offeror . In some of those embodiments agent can then deny other privileges to offeror thus continuing the chain of succession. The ability to change the DP is one such opportunity once agent changes it upon accepting the proffered item agent can no longer change it. There can be also other abilities such as ability to access the readable II and so on.

The reference database may be local. In other embodiments the reference database is remote and accessed over an electronic communications network. This is preferred if the REF permissions of clearance block are to be enforced. Another such way is to form a local database with data received from the reference database and then perform the determination with the data received in the local database. The determination can be performed by an RFID reader or related software components or other instrumentalities as will be seen in .

If the acquired DP is not regarded as proper for the acquired II a suitable report can be generated which can be called a lack of authentication report. Such a report can be generated by any involved party or even the host itself of the reference database as will be seen later in this document in more detail. Any number of items can be included in the report such as a time a date the acquired II the acquired DP and other data about the item being proffered. The lack of authentication report or a version of it can be caused to be transmitted to a monitoring party such as a specially contracted party or a police department. Transmission could be across an electronic communications network. In addition a version of the lack of authentication report can be caused to be written to the one or more RFID tags if they are available.

In some embodiments one could determine from operation that the acquired II is not regarded as proper for the acquired DP. In addition one could further determine that the proffered item has been declared in the reference database as missing.

As will be realized the authentication condition can relate only to the tag data. In some embodiments the party being proffered the item e.g. party can acquire this data by scanning the tag. It is noteworthy that in other embodiments the above described data about the tag can become known before the item is received.

More particularly the II and the DP can be acquired independently from receiving the item with the one or more RFID tags. They can be furnished before physically receiving the proffered item with the one or more RFID tags. For example party can before actually delivering item learn this data by reading the tag and then transmit this data to party for authentication in advance. If the authentication condition is not met then party can reject the proffered item without physically receiving it. In fact party can inform party to not even bother delivering. Additionally if the proffered tagged item is expected but not physically received when expected the reference database can be updated to declare the item as missing.

Additionally if the proffered tagged item is expected but not physically received when expected the reference database can be updated to declare the item as missing.

In other embodiments the proffered item is physically received and the II and the DP are acquired by scanning the delivered item with an RFID reader. Again if the DP is regarded as not proper for the II the delivered item can be returned without being accepted. Or it can be made available to legal authorities.

In such instances it is advisable to think of the whole manner of how the transaction takes place and also reflect portions of it in the legal agreements. For example it could be stipulated what constitutes delivery what constitutes acceptance and so on. Parties may consent in advance to forfeit items they proffer whose RFID tags do not meet the authentication condition and so on.

In other embodiments the proffered item is received and scanned but more time is needed to check the authentication condition. Such a received item can be tentatively stored and held in escrow without being accepted. Then it can be determined whether the DP is regarded as proper or not for the II. If not the escrowed item can be returned or made available to legal authorities and so on.

In some embodiments if the DP is regarded as proper for the II an updated DP can be caused to be stored in the one or more RFID tags in lieu of the DP that was stored there. This can be by writing over the DP or writing the updated DP at a new location of the user memory and adjusting a pointer by cross referencing the II with the updated DP. In some of those embodiments a whole new II can be written and so on. This can take place whether the item is tagged with a single tag or a system of cooperating tags and so on. In addition the reference database is changed to regard the updated DP as now proper for the II or the whole new II etc.

As in the proffered item has tag . Within link there is now an RFID reader suitable for scanning item at it is delivered.

When RFID reader scans item it reads RFID tag as follows. RFID reader transmits an interrogating Radio Frequency RF wave . RFID tag in the vicinity of RFID reader senses interrogating RF wave and generates wave in response. RFID reader senses and interprets wave .

Reader and tag exchange data via wave and wave . In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and decoded from RF waveforms.

Encoding the data in waveforms can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a delimiter a calibration symbol and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired. In turn when the waveforms are processed internally by reader and tag they can be equivalently considered and treated as numbers having corresponding values and so on.

In this case data II and data DP are read from the tag and stored in a memory of reader as respectively data II data DP and optionally RDI . In the preferred embodiment data II is identical to data II and data DP is identical to data DP . It could be however that first data II is stored in tag while second data II is stored in reader the conversion from the first data II to the second data II taking place according to some rule like an II rule. Similarly first data DP could be stored in tag while second data DP is stored in reader the conversion from the first to the second taking place according to some rule like a DP rule. Same also with data RDI .

Local block is responsible for communicating with the RFID tags. Local block includes a block of an antenna and a driver of the antenna for communicating with the tags. Some readers like that shown in local block contain a single antenna and driver. Some readers contain multiple antennas and drivers and a method to switch signals among them including sometimes using different antennas for transmitting and for receiving. And some readers contain multiple antennas and drivers that can operate simultaneously. A demodulator decoder block demodulates and decodes backscattered waves received from the tags via antenna block . Modulator encoder block encodes and modulates an RF wave that is to be transmitted to the tags via antenna block .

Local block additionally includes an optional local processor . Processor may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation digital and or analog processors such as microprocessors and digital signal processors DSPs controllers such as microcontrollers software running in a machine such as a general purpose computer programmable circuits such as Field Programmable Gate Arrays FPGAs Field Programmable Analog Arrays FPAAs Programmable Logic Devices PLDs Application Specific Integrated Circuits ASIC any combination of one or more of these and so on. In some cases some or all of the decoding function in block the encoding function in block or both may be performed instead by processor .

Local block additionally includes an optional local memory . Memory may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation nonvolatile memories NVM read only memories ROM random access memories RAM any combination of one or more of these and so on. Memory if provided can include programs for processor to run if provided.

In some embodiments memory stores data read from tags or data to be written to tags such as Electronic Product Codes EPCs Tag Identifiers TIDs and other data. Memory can also include reference data that is to be compared to the EPC codes instructions and or rules for how to encode commands for the tags modes for controlling antenna and so on. In some of these embodiments local memory is provided as a database.

Some components of local block typically treat the data as analog such as the antenna driver block . Other components such as memory typically treat the data as digital. At some point there is a conversion between analog and digital. Based on where this conversion occurs a whole reader may be characterized as analog or digital but most readers contain a mix of analog and digital functionality.

If remote components are indeed provided they are coupled to local block via an electronic communications network . Network can be a Local Area Network LAN a Metropolitan Area Network MAN a Wide Area Network WAN a network of networks such as the internet and so on. In turn local block then includes a local network connection for communicating with network .

There can be one or more remote component s . If more than one they can be located at the same place with each other or in different places. They can access each other and local block via network or via other similar networks and so on. Accordingly remote component s can use respective remote network connections. Only one such remote network connection is shown which is similar to local network connection etc.

Remote component s can also include a remote processor . Processor can be made in any way known in the art such as was described with reference to local processor .

Remote component s can also include a remote memory . Memory can be made in any way known in the art such as was described with reference to local memory . Memory may include a local database and a different database of a Standards Organization such as one that can reference EPCs.

Of the above described elements it is advantageous to consider a combination of these components designated as operational processing block . Block includes those that are provided of the following local processor remote processor local network connection remote network connection and by extension an applicable portion of network that links connection with connection . The portion can be dynamically changeable etc. In addition block can receive and decode RF waves received via antenna and cause antenna to transmit RF waves according to what it has processed.

Block includes either local processor or remote processor or both. If both are provided remote processor can be made such that it operates in a way complementary with that of local processor . In fact the two can cooperate. It will be appreciated that block as defined this way is in communication with both local memory and remote memory if both are present.

Accordingly block is location agnostic in that its functions can be implemented either by local processor or by remote processor or by a combination of both. Some of these functions are preferably implemented by local processor and some by remote processor . Block accesses local memory or remote memory or both for storing and or retrieving data.

Reader system operates by block generating communications for RFID tags. These communications are ultimately transmitted by antenna block with modulator encoder block encoding and modulating the information on an RF wave. Then data is received from the tags via antenna block demodulated and decoded by demodulator decoder block and processed by processing block .

RFID reader system can be implemented as a combination of hardware and software. It is advantageous to consider such a system as subdivided into components or modules. Each of these modules may be implemented by itself or in combination with others. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination. An example of such a subdivision is now described.

It will be recognized that some aspects are parallel with those of . In addition some of them may be present more than once.

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor.

System moreover includes an Application Programming Interface module which is also known as API Modem API and MAPI. In some embodiments module is itself an interface for a user.

System further includes a host processor . Processor exchanges signals with MAC layer via module . In some embodiments host processor is not considered as a separate module but one that includes some of the above mentioned modules of system . A user interface is coupled to processor and it can be manual automatic or both.

Host processor can include applications for system . In some embodiments elements of module may be distributed between processor and MAC layer .

It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. That which is to be transmitted becomes ultimately signals for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

Returning now to reader is coupled via a communication link to reference database described above. In this particular embodiment reference database is provided outside the control of link although that is not necessarily the case as will be seen later in this document.

Link may optionally include a hub within the control of its agents and employees. Hub is a centralized data processing hub for link or for the locale of reader . In some instances two hubs may be provided one for the link and one for the locale and so on. Hub is coupled with reader via a communication link through which data can be exchanged.

In some embodiments a communications network is provided. Network can be an electronic communications network such as the internet. Network is coupled with hub via a communication link and with reference database via a communication link . As such links and together form link in this embodiment.

It will be recognized that optional hub and optional network can equivalently be considered parts of reader if one also considers the descriptions associated with and .

It is noteworthy that communications from reader and or hub result in transmitting across link at least a question signal QS to reference database when a determination is attempted as to whether a read DP is regarded as proper for a read II . More particularly question signal QS is first received by a host of reference database as will be seen later in this document.

Moreover an answer signal AS can be transmitted from reference database across link to hub and or reader . It will be recognized that signals QS and AS can travel all three links at once or at different times such as for performing batch jobs. For example read II and DP data from reader can be stored in hub for many tagged items and later checked with reference database when traffic via network permits it.

Reference database is hosted by a suitable host . Host further controls permissions for accessing reference database and performs other functions as described in more detail later in this document.

When many links in a supply chain are equipped as shown in different overall schemes can result. Some such schemes are now described.

For each of links authentication can take place at any suitable portion. Drawing also shows nodes and . These nodes are locations within the supply chain where custody of items is transferred and therefore is advantageous to have authentication take place there. Of course authentication can take place at other nodes and so on.

Host is implemented separately from supply chain in these embodiments. In fact it can be implemented by an Authentication Service whose function relative to supply chain is to authenticate RFID tags. Accordingly Authentication Service can be independent and even implemented as a business charging fees for storing data authenticating DPs maintaining users permissions generating reports and the like.

Links and include nodes which further have communication links with host for accessing the reference database. Some of the links could use an external communications network while others need not as will be determined by a person skilled in the art.

Since the reference database is wholly within the control of the owner of link they can set up permissions any way they like. For example they can give more permissions to themselves than to the agents of the other links.

In fact a number of schemes are possible that are hybrids of the above described. Additionally such schemes can be superimposed on one another with multiple DPs and even multiple IIs per tag. Such determinations are made by the relative desires of supply chain participants through their link to control unauthorized items.

Host also includes machines such as computers memory storage programs data and the like as will be discerned from a person having ordinary skill in the art. In the embodiment of host includes a server computer with a connection to an electronic communications network not shown . Connection can be like connection and so on. Additional structures and features of host are implemented on or supported by server or other computers hardware connected and interoperating as will be evident to a person skilled in the art.

Host also includes an interface for checking whether an inputted DP corresponds to an inputted II. As such interface may communicate with server reference database and other modules as designed.

Host moreover includes a permissions clearance module for example for implementing REF permissions clearance . Accordingly module may interact with interface reference database and other modules as designed.

Host further includes an optional database for maintaining registered users and optionally also their allocated permissions and so on. As will be realized database can be implemented in conjunction with reference database .

Host additionally includes an optional interface for registering users and thus permitting remote users to affect at least some of their data in database . It can also include a related optional interface for registered users to log in and access interface .

Host can also include an optional report generation module for generating reports. These reports can include lack of authorization reports owner reports automatic or according to requests routine or custom and so on.

As seen also above the invention includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system.

These methods can be implemented in any number of ways including the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the program.

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

An economy is achieved in the present document in that a single set of flowcharts is used to describe methods in and of themselves along with operations of hardware and or software. This is regardless of how each element is implemented.

At optional operation a Reference Database Identifier RDI is input. It can be the only RDI or a first one with a second RDI being inputted later. The RDI is input in any number of ways such as described elsewhere in this document.

The RDI is data as described above which is used for identifying the reference database that will be relevant for the method of flowchart . In some embodiments the reference database is local such as when it is locally controlled or has been formed with data received from a remote reference database which could have permissions etc.

In other embodiments the reference database is accessible from an electronic communications network and the input RDI to be used to locate the reference database in the network. For example it can include a network address or contact information for an operator of the database.

At another operation a first Item Identifier II is input from one or more RFID tags associated with an item. The first II is input in any number of ways such as described elsewhere in this document.

At another next operation a first Declared Password DP is obtained from the one or more RFID tags which corresponds to the first II. The first DP is input in any number of ways such as described elsewhere in this document.

At optional next operation a question is generated about whether the first DP is regarded as proper or not for the first II. The question is generated in any number of ways which substantially involve correlating the first DP and the first II. In some instances instead of the first DP the question can use a second DP that is findable from the first DP by applying a DP rule. In some instances instead of the first II the question can use a second II that is findable from the first II by applying an II rule.

The question is then applied to data of a reference database and an answer is generated in response to such applying. The reference database can be the one identified by the RDI if one has been input.

At next operation the answer to the question is input. As per the above the answer is preferably as to whether the first DP is regarded as proper or not for the first II.

At optional next operation it is determined from the answer whether the first DP is regarded as proper or not for the first II.

If the answer indicates that the first DP is regarded as proper for the first II then the tag is considered authenticated. Accordingly the proffered item can be considered legitimate and advance along the supply chain. Indicators can be triggered such as a green light at the location of the tagged proffered item and so on.

At an optional next operation an updated DP is input and caused to be stored in the reference database and also in the tag in lieu of the previous DP. Such will help thwart counterfeiting efforts as will be described later.

The updated DP can be generated in any number of ways. It can be generated as part of the method or inputted externally such as from the reference database. It can be generated from an event like a time stamp or at least a portion of it can be generated at random. If at random then it can be checked whether by some small chance the at random actually has a default value that entails a preset custom meaning for the reference database which should be otherwise avoided for a DP. If that is the case one more DP can be generated and used and so on.

If the answer indicates that the first DP is regarded as not proper for the first II then the tag is not considered authenticated. Accordingly the proffered item can be considered illegitimate and be rejected from the supply chain. For example at a next operation a flag can be set which would not be set if the answer indicated that the first DP is regarded as proper for the first II. The flag can be set in software middleware hardware and trigger other actions such as visible or audible indicators.

Setting the flag can have a number of results. For example a flashing red light can be triggered by the flag. According to an optional operation an instruction can be generated to reject the proffered item. According to another next operation a lack of authentication report can be generated and transmitted as per the above.

Reference database can be accessible via host in a number of ways. In some such ways no prior authorization or permission is needed by client computer to receive the answer to the question. In other instances the reference database is accessible such that the answer is transmitted only subject to REF permissions being cleared as has been described above. This is most easily enforceable when a party transmitting the question does not have full control of data of reference database as host is implemented separately. Often these permissions require that a user code be transmitted to the host in connection with transmitting the question.

The communications between client computer and host are encoded in question signals QS and answer signals AS. Sample such communications are described where the operator of client computer is considered the user.

According to a communication the user logs in to the host. Logging in can also be performed at a time when the user transmits the user code. Prior to logging in the user will probably need to register with host such as in database of .

According to a communication communication is acknowledged. Such acknowledging is often designated as ACK . In preferred embodiments acknowledging happens in conjunction with permissions being confirmed according to the user code and prior to generating answers.

According to a communication the user transmits a question as to whether a specific DP is regarded as proper for a specific II according to reference database . The question is intended to be applied to reference database .

In some embodiments prior to applying the question the user needs to obtain additional review privileges from a previous party. Only when these are granted from the previous party will the question be applied to the reference database. This feature is useful when custody of the RFID tagged items changes. Moreover upon being granted such privileges the prior party might lose some privileges e.g. by the user denying them to the prior party. And equally when the user is done they might grant such review privileges to the next party for applying the question to reference database and so on.

According to a communication an answer is transmitted to the question of communication . It will be recognized that communication is input by client computer according to operation of method .

According to a communication the user transmits an update which includes a new DP that is to be regarded as proper by reference database for the II just investigated. It will be recognized that the update of communication is the same as in operation of method .

If this takes place according to permissions then the update of communication is permitted only if the answer of communication was yes. As will be described later in this document such updates effectively cut off the prior party from knowing any more of a DP than is regarded as proper for the II of the tag and thus from being able to update the DP.

According to a communication communication is acknowledged. Then communications can take place for authenticating data of another tag and so on.

Many other actions are also possible. For example the DP can be caused to no longer be stored as regarded as proper for the II. This can be for example by a delete command. Such can happen from a link in the supply chain beyond which authentication is no longer desired or beneficial. Deletion can also save in fees if host charges by how long data is retained.

Alternately records in reference database may expire on their own either by agreement or by planning or by allocated customer credit. In this instance a deadline can be determining after which the DP will no longer be confirmable as regarded as proper for the II by reference database . If needed an action can be taken to extend the deadline. The deadline can be determined in any number of ways such as from the first DP.

The records show different fields along columns. Column can be the Item Identifier II for which a proprietary or well known number can be used. In some embodiments the Electronic Product Code EPC can be used for the II.

Column can hold the value of a last updated Associated Code AC a code thus associated with the corresponding II of column . The AC is like the good password which the legitimate tag also uses as its Declared Password. The question becomes given any RFID tag is its DP the same as the AC 

For the II whose authorization is being checked the inputted DP is tested for whether it matches the AC that is associated with the II. Matching can be for DP equaling AC exactly or be different according to a translation rule and so on. According to some embodiments of the REF permissions it is the AC that is not given out to a user unless they first demonstrate they know it or they know a DP that is related to it by the translation rule.

Only one column is shown. If the DP must equal the AC exactly to pronounce a match it means there is only one AC that the reference database regards as proper for the II. Also that there is only one DP that the user can enter to authenticate the II. This is preferred as it increases the robustness of the protection but not necessary. In fact the system can be defined so that more than one DPs can be used to authenticate the II either by both matching a single AC or by matching more than one ACs defined for the II.

Referring briefly to an optional use of field is now described. All possible AC values are shown in set . In a first embodiment any such value can be regarded as proper for an II by the reference database.

In a second embodiment set is split into a first subset and a second subset . Any AC value in first subset can be regarded as proper for an II by the reference database. The AC values in second subset however cannot be regarded as proper for an II according to some definitions.

Second subset is thus taken out of set to reserve useful values that can serve as default and be associated with special meanings. For example if the ACs are 4 bits long value 0000 can be reserved to designate that the association has recently expired but could be revived if a fee is paid. For another example value 1111 can be reserved to designate that a previous owner has designated this item missing. Of course other default values and designations are possible as may be requested.

Second subset is thus properly regarded as optional. If second subset is provided with at least one such reserved default value the second embodiment will result. Alternately if second subset is the null set i.e. having no values the first embodiment results where all AC values can be regarded as proper.

Of course when updated new DP values are assigned care should be taken that they do not by chance be those of second subset . These new DP values from the point of view of the reference database are new AC values. When generated they should be checked and if by any chance they have such a default value another such value should be generated.

Returning now to all the remaining fields are optional. It is in any event a good idea to maintain them for generating reports.

Column can hold the user name or user code of a user that entered this entry. Column can hold the date and the time that the entry of column was made. Column can hold the expiration date and time of a record.

Column can hold the previous AC of the record before there was an update with the value in column . Column can hold the present owner s user name or user code which may be the party with the most privileges. In most embodiments column is the same as column . Column can hold the user name or user code of a declared next owner such as someone being granted review privileges as per the above. Other fields are also possible.

It will be further observed that different fields include different privacy levels which means that different ones of them can be revealed to different parties under different circumstances and in different manners. Many embodiments are possible such as for example the REF permissions described above. In the example of according to a key column with the IIs has a privacy level A column with the ACs has a privacy level B and all the other columns have different privacy levels C D etc. Privacy levels and REF permissions can also be enforced from the host.

It will be recognized that much of this description has many common aspects with what is already described above which is why many such common aspects are not repeated for describing flowchart . Plus much of the description of flowchart also applies to aspects above. Also many of the variations below can generate individual components of an answer that is transmitted.

At optional operation a log in attempt is received from a user such as by receiving the above described communication . The log in attempt is just one way for inputting user information such as a user code.

At optional operation it can be verified whether the attempt of operation is from a legitimate user. This can be performed in a number of ways. For example it can be verified that the user is within a list of users. In this or a prior step the user preferably becomes registered with the list by meeting the posed requirements and so on. If the user is unauthorized then at a next optional operation a suitable operation is performed for the unauthorized user such as rejecting the log in attempt creating a report transmitting an answer that informs of the status and so on.

If the user is authorized at next operation an Item Identifier II is input. As per the above the II could be an EPC etc. More strictly speaking a first II is inputted from one or more RFID tags associated with an item and a second II is inputted at operation which is derived by applying an II rule to the first II. As also per the above the first II can be the same as the second II but that is not necessary as long as some rule is followed that correlates the second II with the first II.

At optional next operation it is inquired whether the II inputted at operation matches one of the IIs in a list of records such as a list made from fields . If not then at a next optional operation a suitable operation is performed for the II not on the list such as transmitting an answer that informs the user generating and transmitting a lack of authentication report as per the above and so on.

If there is a match at operation it generally identifies a third II that is stored in reference database and matches the second II. To pronounce a match the third II could be identical to the second II or not as long as some rule is followed that correlates the third II with the second II.

If the user is authorized at next operation a Declared Password DP is input. More strictly speaking a first DP is inputted from the one or more RFID tags associated with the item and a second DP is inputted at operation which is derived by applying a DP rule to the first DP. As also per the above the first DP can be the same as the second DP but that is not necessary as long as some rule is followed that correlates the second DP with the first DP.

Inputting the II at operation and the DP at operation is performed in a context of inputting a question as to whether the second DP is regarded as proper or not for the second II by reference database .

At next operation it is determined whether the DP inputted at operation matches an Associated Code AC that is stored in the reference database as being associated with the third II. This is if a value of the AC belongs in first subset of possible AC values. However and as per the above if the value belongs in second subset a mismatch can be pronounced without considering the DP. In fact the answer can include a customized meaning associated with the value in second subset such as MISSING or EXPIRED . This will not occur of course if second subset is the null set.

If there is a mismatch at operation then at a next optional operation a suitable operation is performed for the mismatched II such as transmitting an answer that informs the user creating a report and so on.

In some embodiments it is determined whether the DP has a value that belongs in second subset of possible AC values. If so operation includes setting an intrusion flag if it is deemed that this is a rogue attempt.

In some embodiments operation includes incrementing a failure counter which counts failed attempts. Since such failed attempts could be suspect further operations can be controlled in terms of the failure counter. For example the failure counter can be reset for the user or the II if the inconsistency is resolved otherwise. For another example if the failure counter exceeds a threshold further actions can be taken such as discontinuing generating answers performing an intervention and so on.

Before generating an answer to the question a number of actions can take place. For example permissions can be confirmed such as according to the user information and so on. In some instances permissions can be updated for example upon receiving a suitable request from another user or granting privileges such as review privileges and so on.

Then an answer can be generated which is also responsive to the question as to whether the DP is regarded as proper for the II. Briefly it is regarded as proper if the DP matches the AC that is stored in the reference database as being associated with the II in the reference database and the AC has an AC value that belongs in first subset of AC values that are regarded as proper. And the DP is not regarded as proper if the second DP does not match the AC value or if the AC value belongs in second subset of AC values that are regarded as not proper.

At next operation the answer is transmitted. The answer can be directed to any client computer that is requested. A default is to transmit the answer to the client computer from which the II is inputted.

It should be appreciated that when the answer is transmitted it causes answer signal AS to reproduce in a client computer an answer. The same applies with all other communications of the type described in .

In some instances the answer is transmitted without the user needing to clear any permissions. In some instances the answer is transmitted only subject to REF permissions being cleared.

Referring to a conceptual diagram illustrates that host of reference database does not reveal an Associated Code AC except if it is first demonstrated that a valid DP is already known for an II according to embodiments of the REF permissions. A table shows possible questions and their answers.

The first question that reveals only the II receives no answer. Within host a received II can be used with reference database to determine the AC associated with the inputted II. But the AC itself is not reported out in response to the first question. Or it could be revealed but then immediately changed so what was revealed is no longer valid.

The second question furnishes the II of interest along with the Declared Password DP. Within host a decision box determines whether the DP is equal to the AC. If not the answer reports that without revealing the AC. If yes the user has demonstrated first that they know the AC by having inputted it as the DP.

Returning to at optional next operation an updated AC is stored in the reference database in lieu of the former AC. The updated AC can be inputted externally or generated and transmitted to the user. At least a portion of it can be generated at random but then it can be checked to ensure it does not have a value within the second subset if it does one more AC can be generated and used instead of the second AC.

Referring now to a diagram shows the effects of updating while using a single reference database. For a single Item Identifier II different nodes update the AC to different values from AC1 to AC2 to AC3 to AC4 to AC5 to AC6 to AC7. Each time one link updates it none of the other links can update it any more.

An indirect result is that the threat of RFID tag cloning is thwarted. If a legitimate RFID tag is procured and its II and DP read this data is useless. Any clones with the same data will not be accepted once the DP of the legitimate item is updated.

Referring now to the result can be appreciated. By demanding that RFID tags can be authenticated before moving on to the next link the unauthorized items will be thwarted from entering at those links. More particularly the invention prevents reintroduction activities and fraudulent returns . When that happens there is less incentive for counterfeiting unauthorized overproduction and theft .

There are many possible extensions of the invention. One group of embodiments has to do with deleting records from the reference database for example as per a deletion request. Or letting them expire after a deadline after which the answer is not transmitted. There can be a grace period before which an expired entry can be revived and after which the result would be different. Also a deadline can be extended and so on. The deadline can be encoded in the AC and so on.

Numerous details have been set forth in this description which is to be taken as a whole to provide a more thorough understanding of the invention. In other instances well known features have not been described in detail so as to not obscure unnecessarily the invention.

The invention includes combinations and subcombinations of the various elements features functions and or properties disclosed herein. Elements having been shown in one combination could appear also in another.

The following claims define certain combinations and subcombinations which are regarded as novel and non obvious. Additional claims for other combinations and subcombinations of features functions elements and or properties may be presented in this or a related document.

