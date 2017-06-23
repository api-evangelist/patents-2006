---

title: Method and system for access authentication
abstract: A method and a system for access authentication. A shared services resource includes a second factor authentication module. At least one network resource each include a first factor authentication module. A trusted computing base communicates with the shared services and the at least one network resource through a pipe. An assertion may be obtained on a trusted computing base for accessing at least one network resource. At least one of the at least one network resource may be accessed with the trusted computing base when the assertion has been obtained by the trusted computing base and is valid.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07673332&OS=07673332&RS=07673332
owner: eBay Inc.
number: 07673332
owner_city: San Jose
owner_country: US
publication_date: 20060731
---
The present application relates generally to the technical field of data processing and in one specific example to a method and system for access authentication.

Persons that access network resources such as websites may conduct e commerce transactions and be involved in other communications where information is transmitted over a network. Transmitting of such information over the network may expose the user to risks of third parties that may seek unauthorized access for nefarious purposes. The third parties may seek such access by obtaining a password or other login information for the network resources.

Operators of the network resources may seek ways to secure their network resources to prevent activity that is not authorized by the users. For example operators may require users to meeting a password criteria such as being of a certain length and or including special characters or to frequently change their passwords.

Example methods and systems for access authentication are described. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of example embodiments. It will be evident however to one skilled in the art that the present invention may be practiced without these specific details

A trusted computing base TCB may be used to access one or more network resources and an optional shared services resource over a network. The trusted computing base may be coupled to a computing system such that a TCB agent of the trusted computing base may be in communication with a host agent of the computing system. A pipe may be established between the TCB agent and the one or more network resources and an optional shared services resource. As used herein a pipe may be a connection for data transfer between computing devices. The network resources may include a first factor authentication module and an optional second factor authentication module and the shared services resource may include a second factor authentication module and an optional first factor authentication module. A second factor authentication or an assertion may be authenticated to provide access control to the one or more network resources.

The use of the method and system may enable enhanced authentication for access such as transactions that a user may have with network resources such as websites. For example the enhanced authentication may increase the probability of detecting unauthorized account usage of the user of the TCB. The enhanced authentication may also increase the difficulty in gaining access to an account of the user with the network resource. The method and system may also enable the use of a single password to access multiple network resources

An Application Programming Interface API server and a web server are coupled to and provide programmatic and web interfaces respectively to one or more application servers . The application servers host one or more marketplace applications and payment applications . The application servers are in turn shown to be coupled to one or more databases servers that facilitate access to one or more databases .

The marketplace applications may provide a number of marketplace functions and services to users that access the networked system . The payment applications may likewise provide a number of payment services and functions to users. The payment applications may allow users to accumulate value e.g. in a commercial currency such as the U.S. dollar or a proprietary currency such as points in accounts and then later to redeem the accumulated value for items e.g. products or services that are made available via the marketplace applications . While the marketplace and payment applications and are shown in to both form part of the networked system it will be appreciated that in alternative embodiments the payment applications may form part of a payment service that is separate and distinct from the networked system .

Further while the system shown in employs a client server architecture the present invention is of course not limited to such an architecture and could equally well find application in a distributed or peer to peer architecture system for example. The various marketplace and payment applications and could also be implemented as standalone software programs which do not necessarily have networking capabilities.

The web client accesses the various marketplace and payment applications and via the web interface supported by the web server . Similarly the programmatic client accesses the various services and functions provided by the marketplace and payment applications and via the programmatic interface provided by the API server . The programmatic client may for example be a seller application e.g. the TurboLister application developed by eBay Inc. of San Jose Calif. to enable sellers to author and manage listings on the networked system in an off line manner and to perform batch mode communications between the programmatic client and the networked system .

The networked system may provide a number of publishing listing and price setting mechanisms whereby a seller may list or publish information concerning goods or services for sale a buyer can express interest in or indicate a desire to purchase such goods or services and a price can be set for a transaction pertaining to the goods or services. To this end the marketplace applications are shown to include at least one publication application and one or more auction applications which support auction format listing and price setting mechanisms e.g. English Dutch Vickrey Chinese Double Reverse auctions etc. . The various auction applications may also provide a number of features in support of such auction format listings such as a reserve price feature whereby a seller may specify a reserve price in connection with a listing and a proxy bidding feature whereby a bidder may invoke automated proxy bidding.

A number of fixed price applications support fixed price listing formats e.g. the traditional classified advertisement type listing or a catalogue listing and buyout type listings. Specifically buyout type listings e.g. including the Buy It Now BIN technology developed by eBay Inc. of San Jose Calif. may be offered in conjunction with auction format listings and allow a buyer to purchase goods or services which are also being offered for sale via an auction for a fixed price that is typically higher than the starting price of the auction.

Store applications allow a seller to group listings within a virtual store which may be branded and otherwise personalized by and for the seller. Such a virtual store may also offer promotions incentives and features that are specific and personalized to a relevant seller.

Reputation applications allow users that transact utilizing the networked system to establish build and maintain reputations which may be made available and published to potential trading partners. Consider that where for example the networked system supports person to person trading users may otherwise have no history or other reference information whereby the trustworthiness and credibility of potential trading partners may be assessed. The reputation applications allow a user for example through feedback provided by other transaction partners to establish a reputation within the networked system over time. Other potential trading partners may then reference such a reputation for the purposes of assessing credibility and trustworthiness.

Personalization applications allow users of the networked system to personalize various aspects of their interactions with the networked system . For example a user may utilizing an appropriate personalization application create a personalized reference page at which information regarding transactions to which the user is or has been a party may be viewed. Further a personalization application may enable a user to personalize listings and other aspects of their interactions with the networked system and other parties.

The networked system may support a number of marketplaces that are customized for example for specific geographic regions. A version of the networked system may be customized for the United Kingdom whereas another version of the networked system may be customized for the United States. Each of these versions may operate as an independent marketplace or may be customized or internationalized presentations of a common underlying marketplace. The networked system may accordingly include a number of internationalization applications that customize information and or the presentation of information by the networked system according to predetermined criteria e.g. geographic demographic or marketplace criteria . For example the internationalization applications may be used to support the customization of information for a number of regional websites that are operated by the networked system and that are accessible via respective web servers .

Navigation of the networked system may be facilitated by one or more navigation applications . For example a search application as an example of a navigation application may enable key word searches of listings published via the networked system . A browse application may allow users to browse various category catalogue or inventory data structures according to which listings may be classified within the networked system . Various other navigation applications may be provided to supplement the search and browsing applications.

In order to make listings available via the networked system as visually informing and attractive as possible the marketplace applications may include one or more imaging applications utilizing which users may upload images for inclusion within listings. An imaging application also operates to incorporate images within viewed listings. The imaging applications may also support one or more promotional features such as image galleries that are presented to potential buyers. For example sellers may pay an additional fee to have an image included within a gallery of images for promoted items.

Listing creation applications allow sellers conveniently to author listings pertaining to goods or services that they wish to transact via the networked system and listing management applications allow sellers to manage such listings. Specifically where a particular seller has authored and or published a large number of listings the management of such listings may present a challenge. The listing management applications provide a number of features e.g. auto relisting inventory level monitors etc. to assist the seller in managing such listings. One or more post listing management applications also assist sellers with a number of activities that typically occur post listing. For example upon completion of an auction facilitated by one or more auction applications a seller may wish to leave feedback regarding a particular buyer. To this end a post listing management application may provide an interface to one or more reputation applications so as to allow the seller conveniently to provide feedback regarding multiple buyers to the reputation applications .

Dispute resolution applications provide mechanisms whereby disputes arising between transacting parties may be resolved. For example the dispute resolution applications may provide guided procedures whereby the parties are guided through a number of steps in an attempt to settle a dispute. In the event that the dispute cannot be settled via the guided procedures the dispute may be escalated to a third party mediator or arbitrator.

A number of fraud prevention applications implement fraud detection and prevention mechanisms to reduce the occurrence of fraud within the networked system .

Messaging applications are responsible for the generation and delivery of messages to users of the networked system such messages for example advising users regarding the status of listings at the networked system e.g. providing outbid notices to bidders during an auction process or to provide promotional and merchandising information to users . Respective messaging applications may utilize any one have a number of message delivery networks and platforms to deliver messages to users. For example messaging applications may deliver electronic mail e mail instant message IM Short Message Service SMS text facsimile or voice e.g. Voice over IP VoIP messages via the wired e.g. the Internet Plain Old Telephone Service POTS or wireless e.g. mobile cellular WiFi WiMAX networks.

Merchandising applications support various merchandising functions that are made available to sellers to enable sellers to increase sales via the networked system . The merchandising applications also operate the various merchandising features that may be invoked by sellers and may monitor and track the success of merchandising strategies employed by sellers.

The networked system itself or one or more parties that transact via the networked system may operate loyalty programs that are supported by one or more loyalty promotions applications . For example a buyer may earn loyalty or promotions points for each transaction established and or concluded with a particular seller and be offered a reward for which accumulated loyalty points can be redeemed.

Referring to a system for network resource access according to an example embodiment is shown. A trusted computing base TCB may communicate with a computing system through a TCB agent and a host agent respectively.

The TCB may be implemented in software hardware or a combination of hardware and software. For example the TCB may be implemented as a token a smart card a flash memory device a universal serial bus USB device a dongle a digital music player and the like.

In an example embodiment the TCB may manage credentials for a user of the TCB . For example the user may decide on the credentials to include on the TCB to enable connections to one or more network resources . .and or a shared services resource .

In an example embodiment the TCB agent may be installed on the TCB prior to distribution to a user of the TCB . In an example embodiment the TCB agent may be installed by a user of the TCB such as from data stored on a CD ROM or downloaded from a network resource .

The host agent may communicate with the TCB agent on the TCB and a remote access client on a computing system . In an example embodiment the remote access client may enable the computing system to access the one or more network resources . .on a network . In an example embodiment the remote access client may enable the computing system to access the one or more network resources . .and the shared services resource on the network .

The remote access client may include a web client or a programmatic client see . Examples of the remote access client include a web browser a financial agent e.g. an Internet wallet a communication agent e.g. an instant messenger a telecommunication agent e.g. for conducting voice over internet protocol or a combination thereof. In an example embodiment the remote access client may be a SKYPE agent by Skype Limited and the financial agent may be Yahoo Wallet by Yahoo Inc.

The remote access client may communicate over a network with the network resources . .. In an example embodiment the network resources . .may include web pages websites telecommunication agents and the like. For example the network resources .may include the networked system see . In an example embodiment the network may include the network see .

In an example embodiment the host agent may be a first telecommunication agent and the network resources . .may also be telecommunication agents. In an example embodiment the shared services resource may enable use of a shared infrastructure with the network resources . .

Referring to a system for communicating between a computing system and a TCB to an example embodiment is shown. In an example embodiment the computing system may include the computing system and the host agent may include the host agent see . In an example embodiment the TCB may include the TCB and the TCB agent may include the TCB agent see .

The computing system may include a computing interface . . and the TCB may include a TCB communication interface . .. The TCB may communicate through the TCB communication interface . . with the computing interface . . of the computing system . In an example embodiment the TCB communication interface . . and the computing interface . . may include hardware software or a combination of software and hardware. For example the TCB communication interface . . and the computing interface . . may include universal serial bus USB IEEE 1394 FIREWIRE and other wired and wireless communication interface.

In an example embodiment the TCB may dock with computing system . In an example embodiment TCB may include a communication layer to enable communications with the computing system . In an example embodiment the TCB may only communicate with the computing system locally such as through a port of the computing system .

The TCB agent may include access to private files stored on the TCB . The private files may include a private key user login information for an operator of the TCB a one time password OTP generation agent a private queue of a certificate login credentials private keys pins uniform resource locators URLs and the like. In an example embodiment the private files may not normally be accessed except by the TCB agent . In an example embodiment the TCB may be federal information processing standards FIPS compliant.

In an example embodiment the TCB may be a removable device and can connect to any computing system with the computing interface . .. For example the TCB may not be tied to a single computing system and can be moved to any number of other computing systems on the network see .

Referring to an example embodiment of a network resource is shown. In an example embodiment the network resources . . see may include the network resource .

The network resource may include a first factor authentication module . The first factor authentication module may seek at least a first factor authentication to enable a user to access the network resource . For example the first factor authentication may be user login information such that a user name and password or pin are provided to satisfy the first factor authentication module . In an example embodiment the TCB agent see may seek re verification of a first factor authentication after an access time period expires.

Referring to an example embodiment of a network resource is shown. In an example embodiment the network resources . . see may include the network resource .

The network resource may include a first factor authentication module . In an example embodiment the first factor authentication module may be the first factor authentication module see .

The network resource may include a second factor authentication module . The second factor authentication module may seek a second factor authentication to enable a user to access the network resource . For example the second factor authentication may be a one time password OTP a certificate biometrics credentials and the like.

Referring to an example embodiment of a shared services resource is shown. The shared services resource may include a second factor authentication module . In an example embodiment the second factor authentication module may be the second factor authentication module see .

In an example embodiment the shared services resource may further include a first factor authentication module not shown . In an example embodiment the use of the shared services resource may enable a user of TCB to access the network resources . . see .

Referring to a system for accessing a resource through a pipe is shown. In an example embodiment the resource may be the network resource . . see . In an example embodiment the resource may be the shared services resource .

A TCB may be coupled to a computing system and communicate through a first pipe . In an example embodiment the TCB may be the TCB see . In an example embodiment the computing system may be the computing system see .

The TCB may utilize a TCB agent to communicate through a first pipe with a host agent . In an example embodiment the TCB agent may be the TCB agent and the host agent may be the host agent see .

The host agent may communicate with a remote access client through a second pipe on the computing system . In an example embodiment the remote access client may be a programmatic client or web client see .

The remote access client may communicate with the resource through a third pipe . In an example embodiment the first pipe the second pipe and the third pipe may be utilized together to enable communication between the TCB remote access client and the resource .

Referring to a method according to an example embodiment for access control is shown. The TCB may be configured to enable access for the one or more network resources . . at block see and . For example the configuration may include connecting to and or configuring the TCB with the computing system . An example embodiment of configuring the TCB for access is described in greater detail below.

Login information may be provided to the TCB at block . In an example embodiment a user of the TCB may provide a user name and password or pin to log into the TCB such as directly on the TCB or through use of a computing system. In an example embodiment a user of the TCB may automatically log into the TCB after the TCB is configured at block .

An assertion may be obtained at block . For example the assertion may be a verification or a signed statement that the second factor authentication has been verified. In an example embodiment the assertion may be obtained from the second factor authentication module of the network resource . In an example embodiment the assertion may be obtained from the second factor authentication module of the shared services resource .

In an example embodiment the assertion may be valid for a duration of the access time period. In an example embodiment obtaining the assertion may enable access to one or more of the one or more network resources . . .

At decision block a determination is made as to whether the assertion has been obtained and is still valid. In an example embodiment the assertion may still be valid if the access time period has not expired. In an example embodiment the assertion may be valid if the assertion was obtained at block and not from an unauthorized source. In an example embodiment the assertion may have been obtained if the assertion was obtained has authentication information for a selected network resource .

If the determination is not valid the method may return to block or block . In an example embodiment the method may return to block when the assertion is invalid. In an example embodiment the method may return to block when the method is attempting to obtain a new assertion.

If the assertion has been obtained and is still valid the network resource may be accessed using the TCB at block . An example embodiment of accessing the network resource using the TCB is described in greater detail below.

After the completion of block a user of the TCB may utilize the network resource. For example the user may conduct e commerce transactions with the network resource communicate with the network resource or access the network resource .

At decision block the method determines whether another network resource within a community is attempting to be accessed. For example the community may be one or more network resources . .associated with a common resource with a second factor authentication module such as the shared services resource or the network resource .

If the method seeks to access another network resource within the community the method returns to decision block . If the method does not seek to access another network resource within the community the method proceeds to decision block .

The method determines whether another network resource outside of the community is attempting to be accessed at decision block . If the method seeks to access another network resource outside of the community the method returns to block . If the method does not seek to access another network resource outside of the community the method may terminate.

Referring to a method according to an example embodiment for access control is shown. The TCB is configured for one or more network resources . . at block see and . In an example embodiment configuring the TCB at block may be configuring the TCB at block see . An example embodiment of configuring the TCB for access is described in greater detail below.

Login information may be provided to the TCB at block . In an example embodiment providing the login information at block may be providing the login information at block .

The method may verify and access a particular network resource through the second factor authentication module using the TCB at block . For example the second factor authentication module may be on the network resource being accessed at block on a different network resource then the network resource being accessed or may be accessed through the network resource on the shared services resource . In an example embodiment the TCB may be able to directly access the shared services resource . An example embodiment for verifying and accessing the particular network resource is described in greater detail below.

After completion of block a user of the TCB may utilize the network resource . For example the user of the TCB may utilize the network resource as described for after the completion of block .

At decision block the method may determine whether access to another resource is being attempted. If access to another resource will be attempted the method may return to block . If access to another resource is not being attempted the method may terminate.

In an example embodiment the method see may be a synchronous method for access control. In an example embodiment the method may be a asynchronous method for access control.

Referring to a method according to an example embodiment for creating a pipe for resource access is shown.

A secure link with the resource see may be established at block . For example establishing the secure link may include connecting the TCB with the resource via secure socket layers SSL .

A domain name associated with the network resource may be verified at block . In an example embodiment verifying the domain name may include using domain name system DNS to verify the domain name.

A pipe may be created from the TCB agent to the resource at block . In an example embodiment the pipe may be a secure pipe.

In an example embodiment creating the pipe may include creating the first pipe from the TCB agent to the host agent creating the second pipe from the host agent to the remote access client and creating the third pipe from the remote access client to the resource see .

Referring to a method according to an example embodiment for network resource access is shown. For example block may include implementing the method see .

The network resource may be accessed at block . For example accessing the network resource may include specifying a particular network resource for which access is desired. In an example embodiment accessing the network resource may include identifying a location of the network resource on the network .

The network resource may be verified at block . In an example embodiment verifying the network resource may include verifying the network resource using domain name system DNS . In an example embodiment verifying the network resource may be utilizing a secure socket layer SSL session and verifying a certificate of the network resource .

The method may send the first factor authentication and the second factor authentication from the TCB to the network resource through a pipe at block . For example the pipe may include the first pipe the second pipe and the third pipe see .

The first factor authentication may be verified at block . For example the network resource may verify the login information such as by checking to make sure a provided user name and password are valid.

At decision block the method may attempt to obtain verification of the second factor authentication by determining whether second factor authentication is available on the network resource that has been accessed and verified at blocks . For example the method may determine whether the network resource includes the second factor authentication module see .

If the network resource includes second factor authentication the method may verify the second factor resource with the network resource at block . For example the method may verify the validity of a certification or may insure that an OTP is correct.

If the network resource does not include second factor authentication the method at block may verify the second factor authentication with an external resource such as the shared services resource or another network resource with the second factor authentication module .

Referring to a method according to an example embodiment for network resource access is shown. For example block may include the method see .

The shared services resource is accessed at block . For example the shared services resource may be accessed directly from the TCB . In an example embodiment the TCB may include the first factor authentication and the second factor authentication.

An authentication request may be sent to the second factor authentication module in the shared services resource at block . For example the authentication request may be sent from the TCB over the pipe.

A current validated assertion may be received from the shared services resource at block . For example the shared services resource may validate the second factor authentication with the second factor authentication module and return the current validated assertion to the TCB .

The current validated assertion may be verified on the TCB at block . The assertion may be provided to the network resource through a pipe between the TCB and the network resource at block . Upon completion of block the method may terminate.

Referring to a method according to an example embodiment for configuring the TCB is shown see . The TCB may be connected to the computing system at block . For example the TCB may be physically logically or both physically and logically connected to the computing system .

A session key may be embedded within the host agent at block . For example the session key may be generated at block such as by the host agent .

A portion of the host agent may be hashed at block . In an example embodiment a random or pseudorandom portion of the host agent may be hashed. In an example embodiment a selected portion of the host agent may be hashed. In an example embodiment the hash may be performed by a crypto hash function.

The hashed portion of the host agent may be encrypted at block . The encrypted hash portion may be provided to the TCB agent at block . Upon completion of block the method may terminate.

Referring to a method according to an example embodiment for creating a pipe to a resource is shown. For example block may include the method .

The first factor authentication and the second factor authentication are accessed at block . For example the first factor authentication and the second factor authentication may be accessed by the TCB agent see . The first factor and the second factor may then be encrypted with a data encryption key at block .

The data encryption key may be encrypted with a public key from the resource see at block . The encrypted first factor the encrypted first factor and the encrypted data encryption key may be transmitted to the remote access client and the resource at block .

The exemplary computer system includes a processor e.g. a central processing unit CPU a graphics processing unit GPU or both a main memory and a static memory which communicate with each other via a bus . The computer system may further include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alphanumeric input device e.g. a keyboard a cursor control device e.g. a mouse a disk drive unit a signal generation device e.g. a speaker and a network interface device .

The disk drive unit includes a machine readable medium on which is stored one or more sets of instructions e.g. software embodying any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processor during execution thereof by the computer system the main memory and the processor also constituting machine readable media.

The software may further be transmitted or received over a network via the network interface device .

While the machine readable medium is shown in an exemplary embodiment to be a single medium the term machine readable medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term machine readable medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of the present invention. The term machine readable medium shall accordingly be taken to include but not be limited to solid state memories optical and magnetic media and carrier wave signals.

Thus a method and system to access authentication have been described. Although the present invention has been described with reference to specific exemplary embodiments it will be evident that various modifications and changes may be made to these embodiments without departing from the broader spirit and scope of the invention. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense.

The Abstract of the Disclosure is provided to comply with 37 C.F.R. 1.72 b requiring an abstract that will allow the reader to quickly ascertain the nature of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims. In addition in the foregoing Detailed Description it can be seen that various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting an intention that the claimed embodiments require more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Detailed Description with each claim standing on its own as a separate embodiment.

