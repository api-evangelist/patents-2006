---

title: Method, system, personal security device and computer program product for cryptographically secured biometric authentication
abstract: A system is used for authorizing access to a Personal Security Device. This system comprises a Personal Security Device  and another device  which is in functional communication with said Personal Security Device. Said Personal Security Device comprises identification information retrieval data and a biometric authentication application  which transfers said identification information retrieval data to said other device  in response to an identified match between biometric data sent by said other device and a predetermined biometric reference. Said other device  comprises a security executive application  for retrieving an Identification Information with at least said identification information retrieval data, thus generating a retrieved Identification Information, and transferring said retrieved Identification Information to said Personal Security Device . Said Personal Security Device comprises a security executive application  for authorizing access in response to an identified match between said transferred retrieved Identification Information and a predetermined Identification Information stored in said Personal Security Device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07787661&OS=07787661&RS=07787661
owner: ActivIdentity, Inc.
number: 07787661
owner_city: Fremont
owner_country: US
publication_date: 20060329
---
The present invention relates to a biometric authentication method which incorporates strong cryptography to ensure a security level with a false acceptance rate maintained at 1 1 000 000 compliant with FIPS 140 requirements FIPS Federal Information Processing Standards issued by the NIST National Institute of Standards and Technology .

More specifically the invention relates to a method for authorizing access to a Personal Security Device. It also relates to a system a Personal Security Device and a computer program product for implementing such a method.

The term Personal Security Device PSD as described herein includes hardware based security devices such as cryptographic modules smart cards integrated circuit chip cards portable data carriers PDC subscriber identification modules SIM wireless identification modules WIM USB token dongles identification tokens secure application modules SAM hardware security modules HSM secure multi media tokens SMMT trusted platform computing alliance chips TPCA and like devices.

Biometric authentication suffers from inadequate security when processed using a PSD such as a smart card. Due to the probabilistic nature of biometric authentication the ability to obtain FIPS 140 certification is feasible but the quality settings that are necessary to enable the 10 6 FAR level of accuracy cannot be deployed. Unfortunately the inability to utilize biometric authentication for a high level of accuracy increases administrative costs for password resets etc. It would therefore be advantageous to provide a mechanism to implement fingerprint biometric authentication technologies in high security environments.

In order to improve security of biometric authentication when processed using a PSD there is provided a method for authorizing access to a Personal Security Device wherein said Personal Security Device is in functional communication with another device comprising 

The term biometric data as described herein may refer to a biometric sample such as a raw biometric image captured from a biometric scanning device or to a biometric template such as the output result of some set of image processing operations on a raw biometric sample for example minutia extraction core extraction ridge flow metrics etc.

Analogously the term biometric reference as described herein may refer to a biometric sample such as a raw biometric image captured from a biometric scanning device or to a biometric template such as the output result of some set of image processing operations on a raw biometric sample for example minutia extraction core extraction ridge flow metrics etc.

There is also provided a method for authorizing access to a Personal Security Device wherein said Personal Security Device is in functional communication with another device connected to a biometric device the method comprising 

There is also provided a system for authorizing access to a Personal Security Device comprising a Personal Security Device and another device which is in functional communication with said Personal Security Device wherein 

There is also provided a computer program product for implementing a method for authorizing access to a Personal Security Device wherein said Personal Security Device is in functional communication with another device the computer program product comprising a computer readable medium carrying computer executable instructions that implement the method wherein the method comprises 

Preferably the Identification Information is a Personal Identification number PIN and or the identification information retrieval data are decrypting data for decrypting said Identification Information transferred to said Personal Security Device.

The features and advantages of the invention will become apparent from the following detailed description when considered in conjunction with the accompanying drawings. Where possible the same reference numerals and characters are used to denote like features elements components or portions of the invention. Optional components are generally shown in dashed lines.

This invention addresses inherent limitations of biometric authentication and provides cryptographic security enhancements which greatly improve the security of a Personal Security Device and especially of proprietary information stored within said Personal Security Device. Where necessary applications used to implement the various embodiments of the invention are envisioned to be programmed in a high level language such as Java C and C C or Visual Basic .

Referring to a schematic diagram illustrating a computer system and associated peripherals is depicted. In a networking environment the depicted computer system is intended to apply to both a terminal and a server .

The computer system includes a processor a main memory and a display interface that electrically couples a visual display device to the computer system . The visual display device may include a touch sensitive screen.

The computer system further includes a secondary memory subsystem which includes itself a hard disk drive a removable storage drive and an auxiliary removable storage interface . Said removable storage drive is electrically coupled to a removable storage unit and said auxiliary removable storage interface is electrically coupled to a removable storage unit . The removable storage units are intended to include flash memory devices such as USB based solid state hard drives and related logical media drives.

The computer system further includes a communications interface which is coupled to a network via a network interface port . The network includes traditional wired optical or wireless networks which may incorporate a secure communications protocol such as Secure Socket Layer SSL Transport Layer Security TLS Private Communications Technology PCT or Internet Protocol Security IPsec .

A Personal Security Device for instance a smart card is operably coupled to the communications interface .

The smart card includes a wireless optical and or electrical connection means including an input port compatible with the communications interface a microprocessor a cryptography co processor volatile and non volatile memory electrically coupled to the processor and co processor and a runtime operating environment. The smart card includes the necessary cryptography extensions available to the runtime environment and is capable of performing symmetric and asymmetric cryptographic functions compatible with the computer system s and or an authentication server s cryptography software.

The smart card further includes at least one security executive application and at least one biometric authentication Match On Card or MOC application. Other security applications and security policies may be provided to allow implementation of various embodiments of the invention.

User input devices such as a mouse and a keyboard are operatively coupled to the communications interface via an appropriate interface port . Lastly a biometric scanner is likewise coupled to the communications interface via an appropriate interface port . The biometric scanner is used to capture biometric samples from one or more entities which become stored in a credential store.

The appropriate interface ports and the connection means include available PS 2 USB parallel Firewire PCI ISA and serial interface ports. Other proprietary interfaces with the communications interface are likewise anticipated.

The processor main memory display interface secondary memory subsystem and communications interface are electrically coupled to a communications infrastructure commonly referred to as an I O bus or system bus.

The computer system further includes an operating system one or more security applications a smart card application programming interface where necessary one or more smart card aware applications cryptography software capable of performing symmetric and asymmetric cryptographic functions compatible with that of the smart card and or an authentication server and compatible biometric authentication applications preferably supporting the various standards for interfacing biometric authentication applications to other security applications such as for example BioAPI supported frameworks proposed by the BIOAPI Consortium www.bioapi.org .

Referring to a schematic diagram illustrating a system for implementing the invention is provided. This system comprises a smart card which includes a biometric authentication application MOC a card security executive application and at least one secured object . The card security executive application the secured object and a card s unique identifier are maintained within a security domain controlled by the card security executive application . The secured object may include security services confidential information electronic wallets and cryptographic key stores.

The system further comprises another device for instance a terminal as described in reference to which includes at least one terminal security executive application coupled to a biometric scanner and a server as described in reference to which includes at least one server security executive application which interfaces with the terminal security executive application over a network .

Referring to successive steps of a method for initializing the system described in reference to are illustrated.

In a first step thanks to the biometric scanner a user provides the terminal security executive application with an initial biometric sample and an Identification Information such as a Personal Identification Number. The initial biometric sample is processed by the terminal security executive application and sent over the network to the server security executive application during a step . In the following step the initial biometric sample is cross referenced by the server security executive application as a biometric reference using the card s unique identifier .

Then in step the server security executive application causes a symmetric key SKC to be generated which is sent along step with the biometric reference over the network using a secure channel SSL or equivalent to the terminal security executive application .

In step the terminal security executive application routes the received biometric reference to the card s biometric authentication application for future use in matching with biometric data to be received.

In step the received symmetric key SKC is used by the terminal security executive application to encrypt a copy of the user s Personal Identification Number PIN . According to a first embodiment of the invention see the resulting cryptogram F PIN is maintained by the terminal security executive application . Alternatively according to a second embodiment of the invention see the resulting cryptogram F PIN can be sent by the terminal security executive application to the server security executive application where it is maintained.

The symmetric cryptographic key SKC is then sent to the card s biometric authentication application where it is maintained during a step .

The Personal Identification Number is also sent by the terminal security executive application to the card security executive application where it is maintained during a step .

Optionally once the smart card has received the symmetric key SKC the biometric reference and the Personal Identification Number the system initialization comprises a last step wherein the Personal Identification Number is converted by the card security executive application into a 20 bit binary form which is combined not shown with a binary random number of at least 108 bits to arrive at a total bit length of at least 128 bits. The combination of the Personal Identification Number and of the random number does not include information which would simplify a cryptographic attack. This combination is then encrypted with the symmetric key SKC using a cryptographically strong algorithm such as AES or 3DES. Likewise the symmetric key SKC length should be at least 64 bits.

According to a preferred embodiment of the invention the card s biometric authentication application is programmed to release the symmetric cryptographic key SKC to the terminal security executive application only upon a successful biometric authentication. According to a preferred embodiment of the invention too the card security executive application requires a match of the Personal Identification Number in order to allow access to the secured object .

Referring to the system of is partially represented after initialization performed according to the first embodiment of the invention.

The biometric reference represented by reference and the symmetric key SKC represented by reference are maintained by the card s biometric authentication application . The Personal Identification Number represented by reference is maintained by the card security executive application . The resulting cryptogram F PIN represented by reference is maintained by the terminal security executive application . In another possible embodiment the biometric reference may be maintained by another device than the smart card .

Referring to a method for authorizing access to a PSD according to the first embodiment of the invention is depicted.

The terminal security executive application processes the received biometric sample in step and sends the processed biometric sample i.e. biometric data to the card s biometric authentication application in step . Then in step the card s biometric authentication application compares the received biometric data with the stored biometric reference . If a match is found the symmetric key SKC is released step to the terminal security executive application .

During this step of releasing the symmetric key from the smart card to the terminal security executive application the symmetric key should be protected for integrity and confidentiality and its origin should be identified. The state of the art is to use key agreement techniques such as protection against replay and man in the middle between the smart card and the terminal prior to transmitting the symmetric key.

Then in step the terminal security executive application uses the symmetric key SKC to decrypt the cryptogram F PIN . The resulting decrypted binary string is converted by the terminal security executive application into a plaintext string which is then sent step to the card security executive application for comparison step with the stored Personal Identification Number . If a match is determined access to the secured objects is allowed in step by the card security executive application .

Optionally a second symmetric key may be retained by the terminal and combined with the symmetric key SKC to both encrypt the Personal Identification Number and decrypt the resulting cryptogram F PIN . One skilled in the art will appreciate that a split or composite key arrangement operates analogously to the arrangement described herein. Therefore the cryptographic key transferred by the smart card may not be the only secret necessary to decrypt the cryptogram F PIN .

Referring to the system of is represented after initialization performed according to the second embodiment of the invention.

The biometric reference and the symmetric key SKC are maintained by the card s biometric authentication application . The Personal Identification Number is maintained by the card security executive application . The resulting cryptogram F PIN is maintained by the server security executive application and is retrievable from a data store based on the card s unique identifier . In another possible embodiment the biometric reference may be maintained by another device than the smart card .

Referring to a method for authorizing access to a PSD according to the second embodiment of the invention is depicted.

The terminal security executive application processes the received biometric sample in step and sends the processed sample i.e. biometric data to the card s biometric authentication application in step .

In addition the terminal security executive application receives in step the card s unique identifier from the smart card and sends step a request over the network to the server security executive application to retrieve the cryptogram F PIN corresponding to the card s unique identifier . The server security executive application retrieves said cryptogram F PIN from its data store in step and sends it to the terminal security executive application step .

The foregoing described embodiments of the invention are provided as illustrations and descriptions. They are not intended to limit the invention to precise the form described. It is intended that changes and modifications can be made to the described embodiments without departing from the true scope and spirit of the invention as defined in the claims.

In particular it is contemplated that functional implementation of the invention described herein may be implemented equivalently in hardware software firmware and or other available functional components or building blocks. No specific limitation is intended to a particular security system or arrangement.

It is also contemplated that a method or a system according to the invention may not be used only for accessing secured objects stored in a PSD. More generally it may be used to simply activate the PSD and gain PSD holders privileges inside the PSD applications.

It is also contemplated that the terminal may be replaced by an interface device relying on a server for process execution. More generally the storage and decryption of the encrypted Personal Identification Number may be centralized to allow for roaming.

It is also contemplated that a method or a system according to the invention is not limited to the transfer of a cryptographic key from the PSD to the terminal in response to a successful match. More generally the PSD transfers identification information retrieval data i.e. data necessary as input to a retrieval process including but not limited to decryption wherein the output of that retrieval process is a retrieved Identification Information such as a Personal Identification Number. Such identification information retrieval data may include for instance a card authenticator including but not limited to the Personal Identification Number or a signed authorization or privilege that can be validated or authenticated by the terminal to free a card access secret or key.

It is also contemplated that a method or a system according to the invention includes the following variants 

