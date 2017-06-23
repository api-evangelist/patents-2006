---

title: Data providing system and apparatus and methods of same
abstract: A content provider  distributes a secure container  storing content data encrypted using content key data, content key data encrypted using distribution key data, and encrypted usage control policy data indicating the handling of the content data to a SAM of a user home network  etc. The SAM , etc. decrypts the content data and usage control policy data stored in the secure container  and determines the purchase mode and usage mode and other handling of the content data based on said decrypted usage control policy data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07886159&OS=07886159&RS=07886159
owner: Sony Corporation
number: 07886159
owner_city: Tokyo
owner_country: JP
publication_date: 20060403
---
This is a continuation of U.S. application Ser. No. 09 786 516 filed on Jun. 27 2001 now U.S. Pat. No. 7 073 073 which claims priority to Japanese Application Nos. 11 192413 filed Jul. 6 1999 Application No. 11 193561 filed Jul. 7 1999 Application No. 11 193562 filed Jul. 7 1999 and Application No. 2000 126305 filed Apr. 21 2000 all of which are incorporated herein by reference to the extent permitted by law.

The present invention relates to a data providing system and a data providing apparatus and methods of the same for providing content data and a management apparatus and a data processing apparatus used in the same.

There is a data providing system for distributing encrypted content data to data processing apparatuses of users concluding a predetermined contract and comprising the related data processing apparatuses decrypt reproduce and store the content data.

As one of such data providing systems there is a conventional EMD electronic music distribution system for distributing music data.

In the EMD system shown in content providers and encrypt content data and and copyright information and by session key data obtained after mutual authentication and supply them to a service provider on line or off line. Here the copyright information and include for example SCMS serial copy Management system information electronic watermark information requesting burying in content data and information concerning the copyright requesting burying in a transmission protocol of the service provider .

The service provider decrypts the received content data and and copyright information and by using the session key data.

Then the service provider buries the copyright information and in the content data and decrypted or received off line to generate content data and . At this time the service provider changes a predetermined frequency domain of for example the electronic watermark information in the copyright information and and buries it in the content data and and buries the SCMS information in a network protocol used when transmitting the related content data to the user.

Further the service provider encrypts the content data and by using content key data Kca Kcb and Kcc read from a key database . Thereafter the service provider encrypts a secure container with the encrypted content data and stored therein by the session key data obtained after the mutual authentication and transmits the same to a CA conditional access module existing in terminal equipment of the user.

The CA module decrypts the secure container by using the session key data. Further the CA module receives the content key data Kca Kcb and Kcc from the key database of the service provider by using an electronic settlement and CA or other charging function and decrypts them by using the session key data. Due to this in the terminal equipment it becomes possible to decrypt the content data and by using the content key data Kca Kcb and Kcc.

At this time the CA module performs charge processing in units of content generates charging information in accordance with the result of this encrypts this by the session key data and then transmits the same to a right clearing module of the service provider .

In this case the CA module collects the items it desires to manage relating to the service provided by the service provider itself that is the contract update information of the user and the monthly base fee or other network rent performs charge processing in units of content and secures the security of a physical layer of the network.

The service provider distributes profit between the service provider and the content providers and when receiving the charge information from the CA module .

At this time the profit is distributed from the service provider to the content providers and via for example the JASRAC Japanese Society for Rights of Authors Composers and Publishers . Further the profit of the content provider is distributed to the copyright owner artist song writer and or composer and affiliated production company of the related content data by the JASRAC.

Further the terminal equipment when storing the content data and decrypted by using the content key data Kca Kcb and Kcc in a RAM type storage medium or the like rewrites the SCMS bits of the copyright information and to control copying. Namely the user side controls copying to protect the copyright based on the SCMS bits buried in the content data and

The SCMS was established for preventing storing from a CD compact disc to a DAT digital audio tape . Copying between one DAT and another DAT is still possible. Further even when burying electronic watermark information in the content data when a problem arises only the content provider which provided the content data concerned is specified. Illegal copying is not prevented by technical means.

Accordingly in the EMD system shown in there is the problem in that the right profit of the content provider is not sufficiently protected.

Further in the above EMD system since the copyright information of the content provider is buried in the content data by the service provider the content provider must inspect if the information has been buried as requested. Further the content provider must inspect if the service provider has distributed the content data as contracted. For this reason there is the problem that the load for the inspection is large.

Further in the EMD system the charging information from the terminal equipment of the user is processed by the right clearing module of the service provider so there is a concern if the profit which should be received by the content provider in accordance with the usage of the content data by the user can be suitably received by the content provider.

The present invention was made in consideration with the problem of the above related art and has as an object thereof to provide a data providing system and a data providing apparatus and methods of the same and a data processing apparatus and a management apparatus capable of suitably protecting the profits of the owners of rights related parties of a content provider.

Further the present invention has as another object the provision of a data providing system and a data providing apparatus and methods of the same and a data processing apparatus and a management apparatus capable of reducing the load of the inspection for protecting the profits of the owners of rights of a content provider.

In order to solve the problems of the prior art and achieve the above objects the data providing system of a first aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus wherein the data providing apparatus distributes a module storing the content data encrypted by using content key data encrypted content key data and an encrypted usage control policy data indicating handling of the content data to the data processing apparatus and wherein the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

In the data providing system of the first aspect of the invention the module storing the content data encrypted by using the content key data the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

By storing the usage control policy data indicating the handling of the related content data in the module storing the content data in this way in the data processing apparatus it becomes possible to handle use the content data based on the usage control policy data generated by related parties of the data providing apparatus.

Further in the data providing system of the first aspect of the invention preferably the data providing apparatus distributes the module storing the encrypted content key data and the usage control policy data to the data processing apparatus by using distribution key data and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module by using the distribution key data.

Further the data providing system of the first aspect of the invention preferably further has a management apparatus for managing the distribution key data and distributing the distribution key data to the data providing apparatus and the data processing apparatus.

Further a data processing apparatus of a second aspect of the invention is a data processing apparatus utilizing content data distributed from a data providing apparatus which receives a module storing content data encrypted by using content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data from the data providing apparatus decrypts the content key data and the usage control policy data stored in the related received module and determines the handling of the content data based on the related decrypted usage control policy data.

Further a data providing system of a third aspect of the invention is a data providing system comprising a data providing apparatus a data distribution apparatus and a data processing apparatus wherein the data providing apparatus provides a first module storing content data encrypted by using content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data distribution apparatus the data distribution apparatus distributes a second module storing the encrypted content data content key data and usage control policy data stored in the provided first module to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data based on the related decrypted usage control policy data.

In the data providing system of the third aspect of the invention the first module storing the content data encrypted by using the content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data is provided from the data providing apparatus to the data distribution apparatus.

Next the second module storing the encrypted content data content key data and usage control policy data stored in the provided first module is distributed from the data distribution apparatus to the data processing apparatus.

Next in the data processing apparatus the content key data and the usage control policy data stored in the distributed second module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

Further in the data providing system of the third aspect of the invention preferably the data distribution apparatus distributes the second module storing price data indicating the price of the content data to the data processing apparatus.

Further a data providing system of a fourth aspect of the invention is a data providing system comprising a data providing apparatus at least a first data distribution apparatus and a second data distribution apparatus and a data processing apparatus wherein the data providing apparatus provides a first module storing content data encrypted by using content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the plurality of data distribution apparatuses the first data distribution apparatus distributes the second module storing the encrypted content data content key data and usage control policy data stored in the provided first module to the data processing apparatus the second data distribution apparatus distributes a third module storing the encrypted content data content key data and usage control policy data stored in the provided first module to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and the third module and determines the handling of the content data based on the related decrypted usage control policy data.

Further a data providing system of a fifth aspect of the invention is a data providing system comprising at least a first data providing apparatus and a second data providing apparatus a data distribution apparatus and a data processing apparatus wherein the first data providing apparatus provides a first module storing first content data encrypted by using first content key data encrypted first content key data and encrypted first usage control policy data indicating the handling of the first content data to the data distribution apparatus the second data providing apparatus provides a second module storing second content data encrypted by using second content key data encrypted second content key data and encrypted second usage control policy data indicating the handling of the second content data to the data distribution apparatus the data distribution apparatus distributes a third module storing the encrypted first content data the first content key data and the first usage control policy data stored in the provided first module and the encrypted second content data the second content key data and the second usage control policy data stored in the provided second module to the data processing apparatus and the data processing apparatus decrypts the first content key data and the first usage control policy data stored in the distributed third module determines the handling of the first content data based on the related decrypted first usage control policy data decrypts the second content key data and the second usage control policy data stored in the distributed third module and determines the handling of the second content data based on the related decrypted second usage control policy data.

Further a data providing apparatus of a sixth aspect of the invention is a data providing apparatus for distributing content data to a data processing apparatus for using the content data and distributes a module storing content data encrypted by using the content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data processing apparatus.

Further a data providing method of a seventh aspect of the invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus comprising the steps of distributing a module storing content data encrypted by using content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data from the data providing apparatus to the data processing apparatus and having the data processing apparatus decrypt the content key data and the usage control policy data stored in the distributed module and determine the handling of the content data based on the related decrypted usage control policy data.

Further a data providing method of an eighth aspect of the invention is a data providing method using a data providing apparatus data distribution apparatus and data processing apparatus comprising the steps of providing a first module storing content data encrypted by using content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data from the data providing apparatus to the data distribution apparatus distributing a second module storing the encrypted content data content key data and usage control policy data stored in the provided first module from the data distribution apparatus to the data processing apparatus and having the data processing apparatus decrypt the content key data and the usage control policy data stored in the distributed second module and determine the handling of the content data based on the related decrypted usage control policy data.

Further a data providing method of a ninth aspect of the invention is a data providing method using a data providing apparatus at least a first data distribution apparatus and second data distribution apparatus and a data processing apparatus comprising the steps of providing a first module storing content data encrypted by using content key data encrypted content key data and encrypted usage control policy data indicating the handling of the content data from the data providing apparatus to the data distribution apparatuses distributing a second module storing the encrypted content data content key data and usage control policy data stored in the provided first module from the first data distribution apparatus to the data processing apparatus distributing a third module storing the encrypted content data content key data and usage control policy data stored in the provided first module from the second data distribution apparatus to the data processing apparatus and having the data processing apparatus decrypt the content key data and the usage control policy data stored in the distributed second module and the third module and determine the handling of the content data based on the related decrypted usage control policy data.

Further a data providing method of a 10th aspect of the invention is a data providing method using at least a first data providing apparatus and second data providing apparatus a data distribution apparatus and a data processing apparatus comprising the steps of providing a first module storing first content data encrypted by using first content key data encrypted first content key data and encrypted first usage control policy data indicating the handling of the first content data from the first data providing apparatus to the data distribution apparatus providing a second module storing second content data encrypted by using second content key data encrypted second content key data and encrypted second usage control policy data indicating the handling of the second content data from the second data providing apparatus to the data distribution apparatus distributing a third module storing the encrypted first content data the first content key data and the first usage control policy data stored in the provided first module and the encrypted second content data the second content key data and the second usage control policy data stored in the provided second module from the data distribution apparatus to the data processing apparatus and having the data processing apparatus decrypt the first content key data and the first usage control policy data stored in the distributed third module determine the handling of the first content data based on the related decrypted first usage control policy data decrypt the second content key data and the second usage control policy data stored in the distributed third module and determine the handling of the second content data based on the related decrypted second usage control policy data

Further a data providing system of an 11th aspect of the invention is a data providing system comprising a data providing apparatus data processing apparatus and management apparatus wherein the data providing apparatus distributes content data and usage control policy data indicating the handling of the related content data to the data processing apparatus and requests to the management apparatus to certify legitimacy of the usage control policy data the data processing apparatus uses the distributed content data based on the distributed usage control policy data and the management apparatus manages the data providing apparatus and the data processing apparatus and certifies the legitimacy of the usage control policy data in response to a request from the data providing apparatus.

At this time the legitimacy of the usage control policy data is certified by the management apparatus by the management apparatus preparing for example signature data with respect to the usage control policy data.

In the data providing system of the 11th aspect of the invention the content data and the usage control policy data indicating the handling of the related content data are distributed from the data providing apparatus to the data processing apparatus.

Next the data processing apparatus uses the distributed content data based on the distributed usage control policy data.

Further the legitimacy of the usage control policy data is certified in the management apparatus in response to a request from the data providing apparatus.

Further in the data providing system of the 11th aspect of the invention preferably the data providing apparatus makes the request by transmitting a module storing the usage control policy data its own identifier and at least signature data generated by using its own secret key data with respect to the usage control policy data to the management apparatus.

Further in the data providing system of the 11th aspect of the invention preferably the management apparatus distributes public key certificate data for certifying the legitimacy of the public key data corresponding to the secret key data of the data providing apparatus to the data providing apparatus together with the signature data generated by using its own secret key data and the data providing apparatus makes a request by transmitting a module storing the public key certificate data the usage control policy data its own identifier and the signature data to the management apparatus.

Further in the data providing system of the 11th aspect of the invention preferably the management apparatus manages distribution key data distributes the related distribution key data to the data processing apparatus generates signature data generated by using its own secret key data with respect to the usage control policy data in response to a request from the data providing apparatus encrypts a module storing the related generated signature data and the usage control policy data by using the distribution key data and transmits the same to the data providing apparatus the data providing apparatus distributes a module received from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the module received from the data providing apparatus by using the distribution key data verifies the legitimacy of the signature data stored in the related module by using the public key data of the management apparatus and uses the distributed content data based on the usage control policy data stored in the module when it decides it is legitimate.

Further a data providing system of a 12th aspect of the invention is a data providing system comprising a data providing apparatus data processing apparatus and management apparatus wherein the data providing apparatus encrypts content data by using content key data distributes the related encrypted content data to the data processing apparatus and requests to the management apparatus to certify the legitimacy of the content key data the data processing apparatus decrypts the distributed content data by using the content key data and uses the related decrypted content data and the management apparatus manages the data providing apparatus and the data processing apparatus and certifies the legitimacy of the content key data in response to a request from the data providing apparatus.

In the data providing system of the 12th aspect of the invention the content data encrypted by using the content key data is distributed from the data providing apparatus to the data processing apparatus.

Next the data processing apparatus decrypts the distributed content data by using the content key data and uses the related decrypted content data.

Further the legitimacy of the content key data is certified in the management apparatus in response to a request from the data providing apparatus.

Further a data providing system of a 13th aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data and usage control policy data indicating the handling of the related content data to the data distribution apparatus and requests to the management apparatus to certify the legitimacy of the usage control policy data the data distribution apparatus distributes the provided content data and the usage control policy data to the data processing apparatus the data processing apparatus uses the distributed content data based on the distributed usage control policy data and the management apparatus manages the data providing apparatus and the data processing apparatus and certifies the legitimacy of the usage control policy data in response to a request from the data providing apparatus.

In the data providing system of the 13th aspect of the invention the content data encrypted by using the content key data is distributed from the data providing apparatus to the data processing apparatus.

Next the data processing apparatus decrypts the distributed content data by using the content key data and uses the related decrypted content data.

Further the legitimacy of the content key data is certified in the management apparatus in response to a request from the data providing apparatus.

A data providing system of a 14th aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus encrypts content data by using content key data provides related encrypted content data and usage control policy data indicating the handling of the related content data to the data distribution apparatus and requests to the management apparatus to certify the legitimacy of the content key data the data distribution apparatus distributes the provided content data and the usage control policy data to the data processing apparatus the data processing apparatus uses the content data containing the decryption of the content data using the content key data based on the distributed usage control policy data and the management apparatus manages the data providing apparatus and the data processing apparatus and certifies the legitimacy of the content key data in response to a request from the data providing apparatus.

In the data providing system of the 14th aspect of the invention the content data encrypted by using the content key data and usage control policy data indicating the handling of the related content data are provided from the data providing apparatus to the data distribution apparatus.

Next the content data and the usage control policy data provided from the data distribution apparatus to the data processing apparatus are distributed to the data processing apparatus.

Next the data processing apparatus uses the content data containing the decryption of the content data using the content key data based on the distributed usage control policy data.

Further the management apparatus certifies the legitimacy of the content key data in response to a request from the data providing apparatus.

Further a management apparatus of a 15th aspect of the invention is a management apparatus for managing a data providing apparatus for distributing content data and usage control policy data indicating the handling of the related content data and a data processing apparatus for using the distributed content data based on the distributed usage control policy data and certifies the legitimacy of the usage control policy data in response to a request from the data providing apparatus.

Further a management apparatus of a 16th aspect of the invention is a management apparatus for managing a data providing apparatus for distributing content data encrypted by using content key data and usage control policy data indicating the handling of the related content data and a data processing apparatus for decrypting the content data distributed based on the distributed usage control policy data by using the content key data then using the related content data and certifies the legitimacy of the content key data in response to a request from the data providing apparatus.

Further a management apparatus of a 17th aspect of the invention is a management apparatus for managing a data providing apparatus for providing content data and usage control policy data indicating the handling of the related content data a data distribution apparatus for distributing the provided content data and the usage control policy data and a data processing apparatus for using the content data distributed based on the distributed usage control policy data and certifies the legitimacy of the usage control policy data in response to a request from the data providing apparatus.

Further a data providing method of an 18th aspect of the invention is a data providing method using a data providing apparatus data processing apparatus and management apparatus comprising the steps of distributing content data and usage control policy data indicating the handling of the related content data from the data providing apparatus to the data processing apparatus having the data processing apparatus use the distributed content data based on the distributed usage control policy data and certifying the legitimacy of the usage control policy data in the management apparatus in response to a request from the data providing apparatus.

Further a data providing method of a 19th aspect of the invention is a data providing method using a data providing apparatus data processing apparatus and management apparatus comprising the steps of distributing content data encrypted by using content key data from the data providing apparatus to the data processing apparatus having the data processing apparatus decrypt the distributed content data by using the content key data and certifying the legitimacy of the content key data in the management apparatus in response to a request from the data providing apparatus.

Further a data providing method of a 20th aspect of the invention is a data providing method using a data providing apparatus data distribution apparatus data processing apparatus and management apparatus comprising the steps of providing content data and usage control policy data indicating the handling of the related content data from the data providing apparatus to the data distribution apparatus distributing the provided content data and the usage control policy data from the data distribution apparatus to the data processing apparatus having the data processing apparatus use the distributed content data based on the distributed usage control policy data and certifying the legitimacy of the usage control policy data in the management apparatus in response to a request from the data providing apparatus.

Further a data providing method of a 21st aspect of the invention is a data providing method using a data providing apparatus data distribution apparatus data processing apparatus and management apparatus comprising the steps of providing content data encrypted by using content key data and usage control policy data indicating the handling of the related content data from the data providing apparatus to the data distribution apparatus distributing the content data and the usage control policy data provided from the data distribution apparatus to the data processing apparatus to the data processing apparatus using the content data containing the decryption of the content data using the content key data based on the distributed usage control policy data in the data processing apparatus and certifying the legitimacy of the content key data in the management apparatus in response to a request from the data providing apparatus.

Further a data providing system of a 22nd aspect of the invention is a data providing system comprising a data providing apparatus data processing apparatus and management apparatus wherein the data providing apparatus distributes content data and usage control policy data indicating the handling of the related content data to the data processing apparatus the data processing apparatus determines at least one of a purchase mode and a usage mode of the distributed content data based on the distributed usage control policy data and transmits log data indicating the log of at least one of the related determined purchase mode and usage mode to the management apparatus and the management apparatus manages the data providing apparatus and the data processing apparatus and performs profit distribution processing for distributing the profit obtained accompanied with the purchase and the usage of the content data in the data processing apparatus to related parties of the data providing apparatus based on received log data.

In the data providing system of the 22nd aspect of the invention the content data and the usage control policy data indicating the handling of the related content data are distributed from the data providing apparatus to the data processing apparatus.

Next the data processing apparatus determines at least one of the purchase mode and the usage mode of the distributed content data based on the distributed usage control policy data.

Next the log data indicating the log of at least one of the related determined purchase mode and usage mode is transmitted from the data processing apparatus to the management apparatus.

Next the management apparatus manages the data providing apparatus and the data processing apparatus and perform the profit distribution processing for distributing the profit obtained accompanied with the purchase and the usage of the content data in the data processing apparatus to related parties of the data providing apparatus based on the received log data.

Further a data providing system of a 23rd aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data and usage control policy data indicating the handling of the related content data to the data distribution apparatus the data distribution apparatus distributes the provided content data and the usage control policy data to the data processing apparatus the data processing apparatus has a first module for communicating with the data distribution apparatus and a second module for determining at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmitting log data indicating the log of the related determined purchase mode and usage mode to the management apparatus and the management apparatus manages the data providing apparatus data distribution apparatus and data processing apparatus and performs profit distribution processing for distributing the profit obtained accompanied with the data processing apparatus receiving the distribution of the content data and purchasing and using the content data to related parties of the data providing apparatus and the data distribution apparatus based on the log data received from the second module.

In the data providing system of the 23rd aspect of the invention the content data and the usage control policy data indicating the handling of the related content data are provided from the data providing apparatus to the data distribution apparatus.

Next the provided content data and the usage control policy data are distributed from the data distribution apparatus to the data processing apparatus.

Next the data processing apparatus determines at least one of the purchase mode and the usage mode of the distributed content data based on the distributed usage control policy data.

Next the log data indicating the log of the determined purchase mode and usage mode is transmitted from the data processing apparatus to the management apparatus.

Next the management apparatus performs profit distribution processing for distributing the profit obtained accompanied with the data processing apparatus receiving the distribution of the content data and purchasing and using the content data to related parties of the data providing apparatus and the data distribution apparatus based on the received log data.

Further a data providing system of a 24th aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data and usage control policy data indicating the handling of the related content data to the data distribution apparatus the data distribution apparatus distributes the provided content data and the usage control policy data to the data processing apparatus and performs charge processing concerning the distribution of the content data based on a data distribution apparatus use purchase log data received from the data processing apparatus the data processing apparatus has a first module for creating the data distribution apparatus use purchase log data indicating the log of the purchase of the content data distributed from the data distribution apparatus and transmitting the same to the data distribution apparatus and a second module for determining at least one of the purchase mode and the usage mode of the distributed content data based on the distributed usage control policy data and transmitting a management apparatus use log data indicating the log of the related determined purchase mode and usage mode to the management apparatus and the management apparatus performs profit distribution processing for distributing the profit obtained accompanied with the purchase and the usage of the content data in the data processing apparatus to related parties of the data providing apparatus and the data distribution apparatus based on the management apparatus use log data.

Further a data providing system of a 25th aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides the content data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus the data processing apparatus uses the distributed content data and the management apparatus manages operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus.

Further a data providing system of a 26th aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus the data processing apparatus uses the distributed content data and the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus wherein the transmission of data among the data providing apparatus the data distribution apparatus the data processing apparatus and the management apparatus is carried out by using mutual authentication using a public key encryption method signature creation signature verification and encryption of data by a common key encryption method.

Further a data providing system of a 27th aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus the data processing apparatus uses the distributed content data and the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by itself by using its own secret key data when each of the data providing apparatus the data distribution apparatus and the data processing apparatus supplies the data to another apparatus and generates and manages public key certificate data of public key data corresponding to the secret key data of the data providing apparatus the data distribution apparatus and the data processing apparatus when the legitimacy of the signature data corresponding to the data is verified by using the public key data of the related other apparatus when receiving the supply of the related data from the other apparatus wherein the data providing apparatus the data distribution apparatus and the data processing apparatus acquire the their own public key certificate data from the management apparatus before communicating with the other apparatus and transmit the related acquired public key certificate data to the other apparatus.

Further a data providing system of a 28th aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus the data processing apparatus uses the distributed content data and the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates the signature data indicating that the related data is generated by itself by using its own secret key data when each of the data providing apparatus the data distribution apparatus and the data processing apparatus supplies data to another apparatus and generates and manages public key certificate data of public key data corresponding to the secret key data of the data providing apparatus the data distribution apparatus and the data processing apparatus when the legitimacy of the signature data corresponding to the data is verified by using the public key data of the related other apparatus when receiving the supply of the related data from the other apparatus wherein the data providing apparatus the data distribution apparatus and the data processing apparatus acquire their own public key certificate data from the management apparatus before communicating with the other apparatus and transmit the related acquired public key certificate data to the other apparatus at the communication.

Further a data providing system of a 29th aspect of the invention has a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus the data processing apparatus uses the distributed content data and the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by itself by using its own secret key data when each of the data providing apparatus the data distribution apparatus and the data processing apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data providing apparatus the data distribution apparatus and the data processing apparatus when the legitimacy of the signature data corresponding to the data is verified by using the public key data of the related other apparatus when receiving the supply of the related data from the other apparatus and generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and thereby to restrict the communication or the distribution using public key certificate data specified by the public key certificate revocation list by the data providing apparatus the data distribution apparatus and the data processing apparatus.

Further a data providing system of a 30th aspect of the invention has a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when the data providing apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data providing apparatus for when another apparatus verifies the legitimacy of the related signature data by using the public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data distributes the related public key certificate revocation list to the data processing apparatus and the data processing apparatus verifies whether or not public key certificate data of the data providing apparatus providing the distributed content data is invalid based on the public key certificate revocation list distributed from the management apparatus and controls the usage of the distributed content data based on the result of the related verification.

Further a data providing system of a 31st aspect of the invention has a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when the data providing apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data providing apparatus for when another apparatus verifies the legitimacy of the related signature data by using the public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data distributes the related public key certificate revocation list to the data distribution apparatus and the data distribution apparatus verifies whether or not public key certificate data of the data providing apparatus providing the provided content data is invalid based on the public key certificate revocation list distributed from the management apparatus and controls the distribution of the provided content data to the data processing apparatus based on the result of the related verification.

Further a data providing system of a 32nd aspect of the invention has a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when the data distribution apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data distribution apparatus for when another apparatus verifies the legitimacy of the related signature data by using the public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data providing apparatus the data providing apparatus verifies whether or not public key certificate data of the data distribution apparatus of the destination of provision of the content data is invalid and controls the provision of the content data to the data distribution apparatus based on the result of the related verification the data distribution apparatus distributes the provided content data to the data processing apparatus and the data processing apparatus uses the distributed content data.

Further a data providing system of a 33rd aspect of the invention has a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when the data distribution apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data distribution apparatus for when another apparatus verifies the legitimacy of the related signature data by using the public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data distribution apparatus the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data and the distributed public key certificate revocation list to the data processing apparatus and the data processing apparatus verifies whether or not public key certificate data of the data distribution apparatus distributing the distributed content data is invalid based on the distributed public key certificate revocation list and controls the usage of the distributed content data based on the result of the related verification.

Further a data providing system of a 34th aspect of the invention has a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when the data distribution apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data distribution apparatus for when another apparatus verifies the legitimacy of the related signature data by using public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data processing apparatus the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus and the data processing apparatus verifies whether or not public key certificate data of the data distribution apparatus distributing the distributed content data is invalid based on the distributed public key certificate revocation list and controls the usage of the distributed content data based on the result of the related verification.

Further a data providing system of a 35th aspect of the invention has a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatus generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when the data distribution apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data distribution apparatus for when another apparatus verifies the legitimacy of the related signature data by using public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data providing apparatus the data providing apparatus provides content data and the public key certificate revocation list to the data distribution apparatus the data distribution apparatus distributes the provided content data and public key certificate revocation list to the data processing apparatus and the data processing apparatus verifies whether or not public key certificate data of the data distribution apparatus distributing the distributed content data is invalid based on the distributed public key certificate revocation list and controls the usage of the distributed content data based on the result of the related verification.

Further a data providing system of a 36th aspect of the invention has a data providing apparatus data distribution apparatus a plurality of data processing apparatuses and a management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatuses generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when a data processing apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data processing apparatuses for when another apparatus verifies the legitimacy of the related signature data by using the public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data providing apparatus the data providing apparatus provides content data and the public key certificate revocation list to the data distribution apparatus the data distribution apparatus distributes the provided content data and a public key certificate revocation list to the data processing apparatuses and the data processing apparatuses verify whether or not public key certificate data of the other data processing apparatuses are invalid based on the public key certificate revocation list distributed from the data distribution apparatus and control the communication with other data processing apparatuses based on the result of the related verification.

Further a data providing system of a 37th aspect of the invention has a data providing apparatus data distribution apparatus a plurality of data processing apparatuses and a management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatuses generates signature data indicating that the related data is generated by an apparatus itself by using its own secret key data when a data processing apparatus supplies data to another apparatus generates and manages public key certificate data of public key data corresponding to the secret key data of the data processing apparatuses for when another apparatus verifies the legitimacy of the related signature data by using the public key data corresponding to the secret key data generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data providing apparatus the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data and the distributed public key certificate revocation list to the data processing apparatuses and the data processing apparatuses verify whether or not public key certificate data of other data processing apparatuses are invalid based on the public key certificate revocation list distributed from the data distribution apparatus and control the communication with other data processing apparatuses based on the result of the related verification.

Further a data providing system of a 38th aspect of the invention has a data providing apparatus data distribution apparatus a plurality of data processing apparatuses and a management apparatus wherein a data processing apparatus supplies registration data indicating an already registered data processing apparatus connected in a predetermined network to which is connected to the management apparatus refers to a revocation flag in registration data supplied from the management apparatus and restricts communication with another data processing apparatus having public key certificate data indicated as invalid by the revocation flag the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatuses generates and manages public key certificate data of public key data corresponding to the secret key data for when a data processing apparatus generates signature data indicating legitimacy of data using its own secret key data when supplying data to another apparatus generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data stores the related public key certificate revocation list generates new registration data by setting the revocation flag in the registration data supplied from data processing apparatuses based on the related public key certificate revocation list and distributes the related generated registration data to the data processing apparatuses the data providing apparatus provides content data to the data distribution apparatus and the data distribution apparatus distributes the provided content data to the data processing apparatuses.

Further a data providing system of a 39th aspect of the invention has a data providing apparatus data distribution apparatus a plurality of data processing apparatuses and a management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatuses generates and manages public key certificate data of public key data corresponding to the secret key data for when a data processing apparatus generates signature data indicating the legitimacy of data by using its own secret key data when supplying the related data to another apparatus generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data providing apparatus the data providing apparatus provides content data and the public key certificate revocation list to the data distribution apparatus the data distribution apparatus distributes the provided content data and the public key certificate revocation list to the data processing apparatuses and a data processing apparatus sets a revocation flag in registration data indicating an already registered data processing apparatus connected in a predetermined network to which it is connected based on the distributed public key certificate revocation list and restricts communication with another data processing apparatus having public key certificate data indicated as invalid by the related revocation flag.

Further a data providing system of a 40th aspect of the invention has a data providing apparatus data distribution apparatus a plurality of data processing apparatuses and a management apparatus wherein the management apparatus manages the operation of a data providing service by the data providing apparatus the data distribution apparatus and the data processing apparatuses generates and manages public key certificate data of public key data corresponding to the secret key data for when a data processing apparatus generates signature data indicating the legitimacy of the data by using its own secret key data when supplying the related data to another apparatus generates a public key certificate revocation list for specifying public key certificate data to be invalidated among the generated public key certificate data and distributes the related public key certificate revocation list to the data distribution apparatus the data providing apparatus provides content data to the data distribution apparatus the data distribution apparatus distributes the provided content data and the public key certificate revocation list to the data processing apparatuses and a data processing apparatus sets a revocation flag in registration data indicating an already registered data processing apparatus connected in a predetermined network to which it is connected based on the distributed public key certificate revocation list and restricts communication with another data processing apparatus having public key certificate data indicated as invalid by the related revocation flag.

Further a data providing system of a 41st aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data and usage control policy data indicating the handling of the related content data to the data distribution apparatus the data distribution apparatus distributes the provided content data and the usage control policy data to the data processing apparatus the data processing apparatus has a first module for communicating with the data distribution apparatus and a second module for determining at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmitting log data indicating the log of the related determined purchase mode and usage mode to the management apparatus the management apparatus manages the data providing apparatus data distribution apparatus and data processing apparatus and has a settlement function for performing profit distribution processing for distributing the profit obtained accompanied with the data processing apparatus receiving distribution of the content data and purchasing and using the content data to related parties of the data providing apparatus and the data distribution apparatus based on the log data received from the second module and performing settlement based on the result of the related profit distribution processing and a right management function for registering the usage control policy data.

Further a data providing system of a 42nd aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus provides content data and usage control policy data indicating the handling of the related content data to the data distribution apparatus the data distribution apparatus has a charging function for performing settlement processing by using settlement claim data distributed from the management apparatus and distributes the provided content data and the usage control policy data to the data processing apparatus the data processing apparatus has a first module for communicating with the data distribution apparatus and a second module for determining at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmitting log data indicating the log of the related determined purchase mode and usage mode to the management apparatus the management apparatus manages the data providing apparatus data distribution apparatus and data processing apparatus and has a settlement claim data creation function for performing profit distribution processing for distributing the profit obtained accompanied with the data processing apparatus receiving distribution of the content data and purchasing and using the content data to related parties of the data providing apparatus and the data distribution apparatus based on the log data received from the second module creating settlement claim data used when performing settlement based on the result of the related profit distribution processing and supplying the same to the data distribution apparatus and a right management function for registering the usage control policy data.

Further a data providing system of a 43rd aspect of the invention is a data providing system comprising a data providing apparatus data distribution apparatus data processing apparatus and management apparatus wherein the data providing apparatus has a charging function for performing settlement processing by using settlement claim data distributed from the management apparatus and provides content data and usage control policy data indicating the handling of the related content data to the data distribution apparatus the data distribution apparatus distributes the provided content data and the usage control policy data to the data processing apparatus the data processing apparatus has a first module for communicating with the data distribution apparatus and a second module for determining at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmitting log data indicating the log of the related determined purchase mode and usage mode to the management apparatus the management apparatus manages the data providing apparatus data distribution apparatus and data processing apparatus and has a settlement claim data creation function for performing profit distribution processing for distributing the profit obtained accompanied with the data processing apparatus receiving the distribution of the content data and purchasing and using the content data to related parties of the data providing apparatus and the data distribution apparatus based on the log data received from the second module creating settlement claim data used when performing settlement based on the result of the related profit distribution processing and distributing the same to the data providing apparatus and a right management function for registering the usage control policy data.

Further a management apparatus of a 44th aspect of the invention is a management apparatus for managing a data providing apparatus for distributing content data and usage control policy data indicating the handling of the related content data and a data processing apparatus for determining at least one of a purchase mode and a usage mode of the distributed content data based on the distributed usage control policy data and creating log data indicating the log of at least one of the related determined purchase mode and usage mode and receives the log data from the data processing apparatus and performs profit distribution processing for distributing the profit obtained accompanied with the purchase and the usage of the content data in the data processing apparatus to related parties of the data providing apparatus based on the related received log data.

Further a management apparatus of a 45th aspect of the invention is a management apparatus for managing a data providing apparatus for providing content data and usage control policy data indicating the handling of the related content data a data distribution apparatus for distributing the provided content data and the usage control policy data and a data processing apparatus for determining at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and creating log data indicating the log of at least one of the related determined purchase mode and usage mode and performs profit distribution processing for distributing the profit obtained accompanied with the data processing apparatus receiving the distribution of the content data and purchasing and using the content data to related parties of the data providing apparatus and the data distribution apparatus based on the received log data.

Further a data processing apparatus of a 46th aspect of the invention is a data processing apparatus for receiving distribution of content data and usage control policy data indicating the handling of the related content data from a data providing apparatus and transmitting the log data to a management apparatus for performing profit distribution processing for distributing the profit obtained accompanied with the purchase and usage of the related distributed content data to related parties of the data providing apparatus based on the predetermined log data determines at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmits the log data indicating the log of the determined designation mode and usage mode to the management apparatus.

Further a data processing apparatus of a 47th aspect of the invention is a data processing apparatus for receiving distribution of content data and usage control policy data from a data distribution apparatus receiving the provision of content data and usage control policy data indicating the handling of the related content data from a data providing apparatus and transmitting log data to a management apparatus for performing profit distribution processing for distributing the profit obtained accompanied with the purchase and usage of the distributed content data to related parties of the data providing apparatus and the data distribution apparatus based on predetermined log data and has a first module for communicating with the data distribution apparatus and a second module for determining at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmitting log data indicating the log of the related determined purchase mode and usage mode to the management apparatus.

Further a data processing apparatus of a 48th aspect of the invention is a data processing apparatus for receiving the distribution of content data and usage control policy data indicating the handling of the related content data from a data providing apparatus via a data distribution apparatus and transmitting the log data to a management apparatus for performing profit distribution processing for distributing the profit obtained accompanied with the purchase and usage of the related distributed content data to related parties of the data providing apparatus and the data distribution apparatus based on the management apparatus use log data and has a first module for creating data distribution apparatus use purchase log data indicating the log of the purchase of the content data distributed from the data distribution apparatus and transmitting the same to the data distribution apparatus and a second module for determining at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmitting the management apparatus use log data indicating the log of the related determined purchase mode and usage mode to the management apparatus.

Further a data providing method of a 49th aspect of the invention is a data providing method using a data providing apparatus data processing apparatus and management apparatus comprising the steps of distributing content data and usage control policy data indicating the handling of the related content data from the data providing apparatus to the data processing apparatus having the data processing apparatus determine at least one of the purchase mode and the usage mode of the distributed content data based on the distributed usage control policy data and transmitting log data indicating the log of at least one of the related determined purchase mode and usage mode to the management apparatus and having the management apparatus perform profit distribution processing for distributing the profit obtained accompanied with the purchase and the usage of the content data in the data processing apparatus to related parties of the data providing apparatus based on the received log data.

Further a data providing method of a 50th aspect of the invention is a data providing method using a data providing apparatus data distribution apparatus data processing apparatus and management apparatus comprising the steps of providing content data and usage control policy data indicating the handling of the related content data from the data providing apparatus to the data distribution apparatus distributing the provided content data and the usage control policy data from the data distribution apparatus to the data processing apparatus having the data processing apparatus determine at least one of the purchase mode and the usage mode of the distributed content data based on the distributed usage control policy data and transmitting log data indicating the log of the related determined purchase mode and usage mode to the management apparatus and having the management apparatus perform profit distribution processing for distributing the profit obtained accompanied with the data processing apparatus receiving the distribution of the content data and purchasing and using the content data to related parties of the data providing apparatus and the data distribution apparatus based on the log data received from the second module.

Further a data providing method of a 51st aspect of the invention is a data providing method using a data providing apparatus data distribution apparatus data processing apparatus and management apparatus comprising the steps of providing content data and usage control policy data indicating the handling of the related content data from the data providing apparatus to the data distribution apparatus distributing the content data and the usage control policy data provided from the data distribution apparatus to the data processing apparatus to the data processing apparatus having the data processing apparatus generate data distribution apparatus use purchase log data indicating the log of the purchase of the content data distributed from the data distribution apparatus and transmitting the same to the data distribution apparatus determine at least one of a purchase mode and usage mode of the distributed content data based on the distributed usage control policy data and transmit management apparatus use log data indicating the log of the related determined purchase mode and usage mode to the management apparatus having the management apparatus clear the profit obtained accompanied with the purchase and the usage of the content data in the data processing apparatus to related parties of the data providing apparatus and the data distribution apparatus based on the management apparatus use log data and having the data distribution apparatus perform charging processing concerning the distribution of the content data based on the data distribution apparatus use purchase log data received from the data processing apparatus.

Below an explanation will be made of an EMD electronic music distribution system according to embodiments of the present invention.

In the present embodiment the content data distributed to the user means digital data wherein the information per se has value such as music data video data and a program. The explanation will be made below by taking as an example music data.

As shown in the EMD system has a content provider an EMD service center clearing house below also described as ESC and a user home network .

Here the content provider EMD service center and SAMs to correspond to the data providing apparatus management apparatus and data processing apparatuses of the present invention.

In the EMD system the content provider transmits usage control policy UCP data indicating the content of the right such as license conditions of content data C of the content which it is to provide to the EMD service center as a high reliability authority manager. The usage control policy data is authorized certified by the EMD service center .

Further the content provider encrypts the content data C by content key data Kc to generate a content file CF and at the same time encrypts the content key data Kc by distribution key data KDto KDof a corresponding period distributed from the EMD service center . Then the content provider distributes a secure container module of the present invention storing encapsulating the encrypted content key data Kc and content file CF and its own signature data to the user home network by using a network such as the Internet digital broadcasting and storage medium.

In this way in the present embodiment by encapsulating and providing the digital content data C the digital content which had been closely tied to a conventional storage medium is separated from the storage medium thus value can be imparted to the digital content by itself.

Here the secure container is the product capsule forming the most basic unit when selling the content data C product no matter which distribution route distribution channel it is provided through. Specifically the secure container is a product capsule containing the encryption information for the charging signature data for verifying the legitimacy of the content of the content data C the legitimacy of the party preparing the content data and the legitimacy of the distributor of the content data and the information relating to the copyright such as the information concerning the electronic watermark information buried in the content data.

The AV apparatuses to include the SAMs to . The SAMs to are connected to each other via a bus for example an IEEE Institute of Electrical and Electronics Engineers serial interface bus.

The SAMs to decrypt the secure container received by the network apparatus from the content provider via the network or the like on line and or the secure container received from the content provider at the AV apparatuses to via storage media off line by using the distribution key data KDto KDof the corresponding period and then verify the signature data.

The secure container supplied to the SAMs to is reproduced or stored to a storage medium after the purchase and or usage mode is determined in accordance with the operation of the user in the network apparatus and the AV apparatuses to .

The SAM to store logs of the purchase and or usage of the secure container mentioned above as usage log data .

The usage log data is transmitted from the user home network to the EMD service center in response to for example a request from the EMD service center .

The EMD service center determines calculates the charged content based on the usage log data and performs settlement at a settlement organization such as a bank via a payment gateway . By this the money paid by a user of the user home network to the settlement organization is paid to the content provider by the settlement processing by the EMD service center .

Further the EMD service center transmits a settlement report data to the content provider every predetermined period.

In the present embodiment the EMD service center has a certificate authority function a key data management function and a right clearing profit distribution function.

Namely the EMD service center plays the role as a second certificate authority with respect to a route certificate authority constituting the highest authority manager at a neutral position located below the route certificate authority and certifies the legitimacy of the related public key data by attaching a signature using the secret key data of the EMD service center to public key certificate data of public key data used for the verification processing of the signature data in the content provider and the SAMs to . Further as mentioned before one of the certificate authority functions of the EMD service center is for the EMD service center to register and authorize the usage control policy data of the content provider .

Further the EMD service center has a key data management function for managing the key data for example the distribution key data KDto KD.

Further the EMD service center has a right clearing profit distribution function of performing settlement with respect to the purchase and or usage of content by a user based on a suggested retailer s price SRP described in the authorized usage control policy data and the usage log data input from the SAMs to and distributing the money paid by the user to the content provider .

Further in the flow of the data related to the data transferred between the content provider and the EMD service center is shown.

Note that in the figures starting from the flow of the data input and output to and from the signature data processor and the encryptor decryptor using session key data Kis omitted.

As shown in and the content provider has a content master source server an electronic watermark information adder a compressor an encryptor a random number generator an encryptor a signature processor a secure container generator a secure container database a storage unit a mutual authenticator an encryptor decryptor a usage control policy data generator a SAM manager and an EMD service center manager .

The content provider registers for example public key data generated by itself and its own ID card and bank account number account number for settlement in the EMD service center off line before communicating with the EMD service center and acquires its own identifier identification number CP ID. Further the content provider receives public key data of the EMD service center and public key data of the route certificate authority from the EMD service center .

The content master server stores the content data of the master source of content to be provided to the user home network and outputs content data S to be provided to the electronic watermark information adder .

The electronic watermark information adder buries a source watermark Ws a copy control watermark Wc a user watermark Wu etc. in the content data S to generate content data S and outputs the content data S to the compressor .

The source watermark Ws is information concerning the copyright such as the name of the owner of the copyright of the content data ISRC code authoring date authoring apparatus ID identification data and destination of the distribution of the content. The copy control watermark Wc is information containing a copy prohibit bit for preventing copying through an analog interface. The user watermark Wu contains for example the identifier CP ID of the content provider for specifying a source of distribution and a destination of distribution of the secure container and identifiers SAM IDto SAM IDof the SAMs to of the user home network .

Further the electronic watermark information adder buries the link use ID for searching of the content data by a search engine as electronic watermark information in the content data S if necessary.

In the present embodiment preferably the information content and the burial position of each electronic watermark information are defined as the electronic watermark information management data. The electronic watermark information management data is managed in the EMD service center . The electronic watermark information management data is used when for example the network apparatus and the AV apparatuses to in the user home network verify the legitimacy of the electronic watermark information.

For example in the user home network based on the electronic watermark information management data the burying of a false electronic watermark information can be detected with a high probability by deciding that the electronic watermark information is legitimate when both of the burial position of the electronic watermark information and the content of the buried electronic watermark information coincide.

The compressor compresses the content data S by an audio compression method such as ATRAC3 Adaptive Transform Acoustic Coding 3 trademark and outputs compressed content data S to the encryptor .

The encryptor uses the content key data Kc as a common key encrypts the content data S by a common key encryption method such as DES Data Encryption Standard or Triple DES to generate the content data C and outputs this to the secure container generator .

Further the encryptor encrypts A V decompression software Soft and meta data Meta by using the content key data Kc as the common key then outputs the same to the secure container generator .

DES is an encryption method for processing 64 bits of a plain text as a block by using a 56 bit common key. The DES processing is comprised by a portion for scrambling the plain text to transform the same to encrypted text data scrambler and a portion for creating key magnification key data used in the data scrambler from the common key data key processor . All algorithms of DES are disclosed so the fundamental processing of the data scrambler will be briefly explained here.

First 64 bits of the plain text are divided into an upper significant 32 bit Hand a lower significant 32 bit L. Using as input the 48 bit magnification key data Ksupplied from the key processor and the lower significant 32 bit L the output of an F function obtained by scrambling the lower significant 32 bit Lis calculated. The F function is comprised by two types of basic transformations of substitution for replacing the numerals by a predetermined rule and transposition for switching the bit positions by a predetermined rule. Next an exclusive OR of the upper significant 32 bit Hand the output of the F function is calculated and the result thereof is made L. Further Lis made H.

Then based on the upper significant 32 bit Hand the lower significant 32 bit L the above processing is repeated times. The thus obtained upper significant 32 bit Hand lower significant 32 bit Lare output as the encrypted text. The decryption is realized by performing the above procedure in the reverse direction by using the common key data used in the encryption.

The random number generator generates a random number of predetermined number of bits and outputs the related random number as the content key data Kc to the encryptor and the encryptor .

Note that it is also possible to generate the content key data Kc from the information concerning the music provided by the content data. The content key data Kc is updated for example every predetermined time.

The encryptor receives as its inputs the distribution key data KDto KDof the corresponding period among the distribution key data KDto KDreceived from the EMD service center and stored in the storage unit as will be mentioned later encrypts the content key data Kc usage control policy data SAM program download containers SDCto SDC and a signature certificate module Modshown in by the DES or other common encryption method using the related distribution key data as a common key then outputs them to the secure container generator .

In the signature certificate module Modas shown in signature data SIGto SIG a public key certificate CERof public key data Kof the content provider and signature data SIGof the EMD service center with respect to the related certificate CERare stored.

Further the SAM program download containers SDCto SDCstore download drivers used when downloading programs in the SAMs to a UCP L Label R Reader indicating the syntax grammar of a usage control policy data UCP U and lock key data for locking or unlocking rewrite and erase operations of the storage units flash ROMs built in the SAMs to in units of blocks.

Note that the storage unit is provided with various databases for example a database for storing public key certificate data a database for storing distribution use data KDto KD and a database for storing the key file KF.

The signature processor takes a hush value of the data to be signed and generates the signature data SIG thereof by using the secret key data Kof the content provider .

Note that the hush value is generated by using the hush function. The hush function is a function for receiving as the input the data covered compressing the related input data to data having a predetermined bit length and outputting the same as a hush value. The hush function is characterized in that it is difficult to predict the input from the hush value output many bits of the hush value change when one bit of the data input to the hush function changes and it is difficult to find input data having an identical hush value.

The secure container generator as shown in generates the content file CF storing header data and the content data C A V decompression software Soft and meta data Meta input from the encryptor and encrypted by the content key data Kc.

Here the A V decompression software Soft is the software used when decompressing the content file CF in the network apparatus and the AV apparatuses to in the user home network and is for example an ATRAC3 type decompression software.

Further the secure container generator generates a key file KF storing as shown in the content key data Kc usage control policy data UCP SAM program download containers SDCto SDC and the signature certificate module Modencrypted by the distribution key data KDto KDof the corresponding period input from the encryptor .

Then the secure container generator generates a secure container storing the content file CF and the key file KF shown in and the public key data Kand the signature data SIGof the content provider shown in stores this in a secure container database and then outputs the same to the SAM manager in response to a request from the user.

In this way in the present embodiment an in band method storing the public key certificate CERof the public key data Kof the content provider in a secure container and transmitting it to the user home network is employed. Accordingly it is not necessary for the user home network to communicate with the EMD service center for obtaining the public key certificate CER.

Note that in the present invention it is also possible to employ an out of band method where the user home network obtains the public key certificate CERfrom the EMD service center without storing the public key certificate CERin the secure container .

The mutual authenticator generates session key data common key Kby mutual authentication between the EMD service center and the user home network when the content provider transfer data on line between the EMD service center and the user home network . The session key data Kis newly generated at each mutual authentication.

The encryptor decryptor encrypts the data to be transmitted by the content provider to the EMD service center and the user home network on line by using the session key data K.

Further the encryptor decryptor decrypts the data received by the content provider from the EMD service center and the user home network on line by using the session key data K.

The usage control policy data generator generates the usage control policy data and outputs this to the encryptor .

The usage control policy data is a descriptor defining the operation rules of the content data C and describes for example the suggested retailer s price SRP intended by the operator of the content provider and the copying rules of the content data C therein.

The SAM manager encrypts the secure container by using the distribution key data KDto KDetc. and stores the same on a storage medium when distributing the secure container to the user home network off line by using a ROM type storage medium such as a CD ROM or DVD digital versatile disc . Then this storage medium is supplied to the user home network off line by sale or the like.

In the present embodiment the secure container product capsule is defined by the application layer in the OSI layer as shown in . Further capsules corresponding to the presentation layer and the transport layer are separately defined from the secure container as transport protocol for transporting the secure container. Accordingly the secure container can be defined without depending on the transport protocol. Namely no matter what the mode that is on line or off line of supplying the secure container to the user home network the container can be defined and generated according to a common rule.

For example when supplying the secure container by using the network the secure container is defined in a region of the content provider and the presentation layer and the transport layer are considered as transport tools for transporting the secure container to the user home network .

Further in the off line case a ROM type storage medium is considered as a transport carrier for transporting the secure container to the user home network .

Further the RAM region stores signature data generated by using a MAC message authentication code function using as arguments the key file KF and public key certificate data CERshown in and and storage key data Khaving an inherent value in accordance with the type of the apparatus and data obtained by encrypting the related key file KF and public key certificate data CERby using media key data Khaving a value inherent in the storage media.

Further the RAM region stores a public key certificate revocation list for specifying the content provider and SAMs to which became invalid due to for example an illegal action.

Further the RAM region as will be mentioned later stores usage control status UCS data generated when the purchase and or usage mode of the content data C are determined in the SAMs to of the user home network etc. By this by the storage of the usage control status data in the RAM region the ROM type storage medium having the purchase and or usage mode determined therein is obtained.

The media SAM for example stores the media ID as the identifier of the ROM type storage medium and the media key data K.

Further the SAM manager encrypts the secure container in the encryptor decryptor by using the session key data Kand then distributes the same via the network to the user home network when distributing the secure container to the user home network on line by using a network digital broadcast or the like.

In the present embodiment as the SAM manager EMD service center manager and a content provider manager and a service provider manager mentioned later use is made of for example a communication gateway having a tamper resistant structure making it difficult to monitor and tamper the internal processing content.

Here for the distribution of the content data C from the content provider to the user home network use is made of the secure container of the common mode storing the usage control policy data in both of the case of distribution using a storage medium as mentioned above and the case of distribution on line by using a network. Accordingly in the SAMs to of the user home network in both of the off line and on line cases right clearing based on the common usage control policy data is possible.

Further as mentioned above in the present embodiment the in band method of enclosing the content data C encrypted by the content key data Kc and the content key data Kc for decrypting the related encryption in the secure container is employed. In the in band method there is the advantage that it is not necessary to separately distribute the content key data Kc and the load of network communication can be reduced when it is desired to reproduce the content data C at an apparatus of the user home network . Further the content key data Kc is encrypted by the distribution key data KDto KD but the distribution use public key data KDto KDare managed by the EMD service center and have been distributed to the SAMs to of the user home network in advance when the SAMs to access to the EMD service center the first time therefore in the user home network the usage of the content data C off line becomes possible without connecting with the EMD service center on line.

Note that the present invention has the flexibility of enabling use of the out of band method of separately supplying the content data C and the content key data Kc to the user home network .

When receiving six months worth of the distribution key data KDto KDand the corresponding signature data SIGto SIG the public key certificate CERcontaining the public key data Kof the content provider and the signature data SIGthereof and the settlement report data from the EMD service center the EMD service center manager decrypts them in the encryptor decryptor by using the session key data K and then stores them in the storage unit .

The settlement report data describes for example the content of the settlement concerning the content provider performed with respect to the settlement organization shown in by the EMD service center .

Further the EMD service center manager transmits a global unique identifier Content ID of the content data C to be provided the public key data K and their signature data SIGto the EMD service center and receives as its input public key certificate data CERof public key data Kfrom the EMD service center .

Further the EMD service center manager generates a module Modstoring the global unique identifier Content ID of the content data C to be provided the content key data Kc and the usage control policy data therein and a usage control policy registration request use module Modstoring signature data SIGthereof as shown in when registering the usage control policy data in the EMD service center encrypts them in the encryptor decryptor by using the session key data K and then transmits the same via the network to the EMD service center . As the EMD service center manager as mentioned before use is made of for example a communication gateway having the tamper resistant structure making it difficult to monitor and tamper with the internal processing content.

Below an explanation will be made of the flow of the processing in the content provider by referring to and .

Note that as a prerequisite of the following processing a related party of the content provider performs processing for registration at the EMD service center off line by using for example its own ID card and bank account for the settlement processing and obtains a global unique identifier CP ID. The global unique identifier CP ID is stored in the storage unit .

Below an explanation will be made of the processing when the content provider requests public key certificate data CERfor certifying the legitimacy of the public key data Kcorresponding to its own secret key data Kto the EMD service center by referring to and .

Step SA The content provider generates a random number by using a random number generator configured by for example a true random number generator and generates the secret key data K.

Step SA The content provider generates public key data Kcorresponding to the secret key data Kand stores the same in the storage unit .

Step SA The EMD service center manager of the content provider reads the identifier CP ID of the content provider and the public key data Kfrom the storage unit .

Then the EMD service center manager transmits a public key certificate data issuance request containing the identifier CP ID and the public key data Kto the EMD service center .

Step SA The EMD service center manager receives as its inputs the public key certificate data CERand signature data SIGthereof from the EMD service center in response to the related issuance request and writes the same into the storage unit .

Below an explanation will be made of the processing for receiving the distribution key data from the EMD service center by the content provider by referring to .

Note that as the prerequisite for the following processing the content provider must have already obtained the public key certificate data CERfrom the EMD service center .

The EMD service center manager receives as its inputs six months worth of the distribution key data KDto KDand their signature data SIGto SIGthereof from the EMD service center and stores them in a predetermined database in the storage unit .

Then in the signature processor after the legitimacy of the signature data SIGto SIGstored in the storage unit is confirmed the distribution key data KDto KDstored in the storage unit are handled as valid data.

Below an explanation will be made of the processing when the content provider transmits the secure container to the SAM of the user home network referring to and .

Note that in the following example the case of transmitting the secure container from the content provider to the SAM is illustrated but the same applies also to the case of transmitting the secure container to the SAMs to except it is transmitted to the SAMs to via the SAM .

Step SB Content data S is read from the content master source server and output to the electronic watermark information adder .

The electronic watermark information adder buries the electronic watermark information in the content data S to generate content data S and outputs this to the compressor .

Step SB The compressor compresses the content data S by for example the ATRAC3 method to generate content data S and outputs this to the encryptor .

Step SB The random number generator generates a random number to generate the content key data Kc and outputs this to the encryptor .

Step SB The encryptor encrypts the content data S and the meta data Meta and A V decompression software Soft read from the storage unit by using the content key data Kc and outputs the same to the secure container generator . In this case the meta data Meta does not have to be encrypted.

Then the secure container generator generates the content file CF shown in . Also in the signature processor the hush value of the content file CF is taken and the signature data SIGis generated by using the secret key data K.

Step SB The signature processor takes the hush value with respect to each of the content data C content key data Kc and the usage control policy data and generates the signature data SIG SIG and SIGindicating the legitimacy of the creator provider of the data by using the secret key data K.

Further the encryptor encrypts the content key data Kc usage control policy data SAM program download containers SDto SD and signature certificate module Modshown in by the distribution key data KDto KDof the corresponding period and outputs the same to the secure container generator .

Further the signature processor takes the hush value of the key file KF and generates the signature data SIGby using the secret key data K.

Step SB The secure container generator generates the secure container storing the content file CF and the signature data SIGthereof shown in the key file KF and the signature data SIGthereof shown in and the public key certificate data CERand the signature data SIGthereof shown in therein and stores this in the secure container database

Step SB The secure container generator reads the secure container to be provided to the user home network in response to for example a request from the user from the secure container database encrypts the same in the encryptor decryptor by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the SAM and then transmits the same to the SAM of the user home network via the SAM manager .

Below an explanation will be made of the processing in the case where the content provider requests to the EMD service center to register and authorize the usage control policy data and the content key data Kc by referring to .

The processing for requesting authorization of the usage control policy data and the content key data Kc is carried out for every content data C.

In this case the signature processor finds the hush value of the module Modcomprised by the global unique identifier Content ID of the content data C and the content key data Kc read from the storage unit and the usage control policy data input from the usage control policy data generator and generates the signature data SIGby using the secret key data K.

Then it encrypts the right registration request use module Modshown in in the encryptor decryptor by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the EMD service center then transmits it from the EMD service center manager to the EMD service center .

In the present embodiment the case where the content provider does not receive the authorization certificate module certifying that the content provider is authorized from the EMD service center after the EMD service center authorizes the usage control policy data and the content key data Kc that is the case where the encryption is carried out in the content provider by using the distribution key data KDto KDto generate the key file KF is illustrated.

Note that in the present invention it is also possible to transmit an authorization certificate module Modshown in encrypted by using the distribution key data KDto KDfrom the EMD service center to the content provider after authorization of the usage control policy data and the content key data Kc in the EMD service center .

The authorization certificate module Modstores a module Modstoring the global unique identifier Content ID of the content data C content key data Kc and the usage control policy data input from the usage control policy data generator and signature data SIGof the module Modusing the secret key data K.

In this case the content provider stores the authorization certificate module Modin for example the secure container and distributes the same to the SAMs to .

Note that it is also possible that the EMD service center generate six months worth of the authorization certificate module Modencrypted by using the distribution key data KDto KDcorresponding to different months and transmit them to the content provider together.

The EMD service center has a certificate authority CA function a key management function and a right clearing profit distribution function.

As shown in the EMD service center has a key server a key database a settlement processor a signature processor a settlement organization manager a certificate usage control policy manager a CER database a content provider manager a CP database a SAM manager a SAM database a mutual authenticator and an encryptor decryptor .

Note that in in the flow of the data among the functional blocks in the EMD service center the flow of the data related to the data transferred with the content provider is shown.

Further in in the flow of the data among the functional blocks in the EMD service center the flow of the data related to the data transferred between the SAMs to and the settlement organization shown in is shown.

The key server reads the distribution key data having the term of validity of one month stored in the key database in response to a request and outputs the same to the content provider manager and the SAM manager .

Further it is comprised by a series of the key databases for storing the key data such as the storage key data K media key data K and MAC key data Kother than the key database distribution key data KD.

The settlement processor performs the settlement processing based on the usage log data input from the SAMs to suggested retailer price data SRP input from the certificate usage control policy manager and the sale price generates the settlement report data and a settlement claim data outputs the settlement report data to the content provider manager and outputs the settlement claim data to the settlement organization manager .

Note that the settlement processor monitors whether or not the transaction was conducted by an illegal dumping price based on the sale price.

Here the usage log data indicates the log of the purchase and the usage reproduction storing transfer etc. of the secure container in the user home network and is used when determining the payment of the license fee stored to the secure container in the settlement processor .

The usage log data describes for example the identifier Content ID of the content data C stored in the secure container the identifier CP ID of the content provider distributing the secure container the compression method of the content data C in the secure container the identifier Media ID of the storage medium storing the secure container the identifier SAM ID of the SAMs to receiving the distribution of the secure container the USER ID of the related SAMs to etc. Accordingly when the EMD service center must distribute money paid by the user of the user home network to a party other than the owner of the content provider for example the license owner of for example the compression method or the storage medium the EMD service center determines the sum to be paid to each other party based on a distribution rate table determined in advance and generates the settlement report data and the settlement claim data in accordance with the related determination. The related distribution rate table is generated for example for every content data stored in the secure container .

Further the settlement claim data is authorized data enabling claim of payment of money to the settlement organization and is generated for each individual owner of a right when for example the money paid by the user is distributed to a plurality of owners of rights.

Note that the settlement organization sends a record of use of the related settlement organization to the EMD service center when the settlement is finished. The EMD service center notifies the content of the related record of use to the corresponding owner of a right.

The settlement organization manager transmits the settlement claim data generated by the settlement processor via the payment gateway shown in to the settlement organization .

Note that as will be mentioned later it is also possible that the settlement organization manager transmit the settlement claim data to an owner of a right such as the content provider and that the owner of the right itself performs the settlement at the settlement organization by using the received settlement claim data .

Further the settlement organization manager takes the hush value of the settlement claim data in the signature processor and transmits signature data SIGgenerated by using the secret key data Ktogether with the settlement claim data to the settlement organization .

The certificate usage control policy manager reads the public key certificate data CERand public key certificate data CERto CERetc. registered and authorized in the CER database and at the same time registers and authorizes the usage control policy data and the content key data Kc etc. of the content provider in the CER database

Note that it is also possible that databases for storing the public key certificate data CERto CER the usage control policy data and the content key data Kc be individually provided.

At this time the certificate usage control policy manager takes the hush value of for example the usage control policy data and the content key data Kc and generates the authorized public key certificate data having the signature data using the secret key data Kattached thereto.

The content provider manager has the function of communicating with the content provider and can access the CP database for managing the identifier CP ID etc. of the registered content provider .

The SAM manager has the function of communicating with the SAMs to in the user home network and can access the SAM database storing the identifier SAM ID of the registered SAM and the SAM registration list etc.

First the flow of the processing when transmitting the distribution key data from the EMD service center to the content provider and the SAMs to in the user home network will be explained while referring to and .

As shown in the key server reads for example six month worth of the distribution key data KDto KDfrom the key database every predetermined period and outputs the same to the content provider manager .

Further the signature processor takes the hush value of each of the distribution key data KDto KD generates the signature data SIGto SIGcorresponding to them and outputs them to the content provider manager .

The content provider manager encrypts these six months worth of the distribution key data KDto KDand their signature data SIGto SIGby using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator shown in and then transmits the same to the content provider .

Further as shown in the key server reads for example three months worth of the distribution key data KDto KDfrom the key database for every predetermined period and outputs the same to the SAM manager .

Further the signature processor takes the hush value of each of the distribution key data KDto KD generates the signature data SIGto SIGcorresponding to them by using the secret key data Kof the EMD service center and outputs them to the SAM manager .

The SAM manager encrypts these three months worth of the distribution key data KDto KDand their signature data SIGto SIGby using the session key data Kobtained by mutual authentication between the mutual authenticator and the SAMs to and then transmits the same to the SAMs to .

Below an explanation will be made of the processing where the EMD service center receives a request for issuance of public key certificate data CERfrom the content provider by referring to and .

Step SC When receiving a request for issuance of public key certificate data containing the identifier CP ID of the content provider public key data K and signature data SIGfrom the content provider the content provider manager decrypts them by using the session key data Kobtained by mutual authentication between the mutual authenticator and the mutual authenticator shown in .

Step SC After confirming the legitimacy of the related decrypted signature data SIGat the signature processor it confirms whether or not the content provider issuing the related public key certificate data issuance request is registered in the CP database based on the identifier CP ID and the public key data K.

Step SC The certificate usage control policy manager reads the public key certificate data CERof the related content provider from the CER database and outputs the same to the content provider manager .

Step SC The signature processor takes the hush value of the public key certificate data CER generates the signature data SIGby using the secret key data Kof the EMD service center and outputs this to the content provider manager .

Step SC The content provider manager encrypts the public key certificate data CERand the signature data SIGthereof by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator shown in and then transmits the same to the content provider .

Below an explanation will be made of the processing where the EMD service center receives a request for issuance of public key certificate data CERfrom the SAM by referring to and .

Step SD When receiving a request for issuance of public key certificate data containing the identifier SAM ID of the SAM the public key data K and the signature data SIGfrom the SAM the SAM manager decrypts them by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the SAM .

Step SD After confirming the legitimacy of the related decrypted signature data SIGat the signature processor it is confirmed whether or not the SAM issuing a request for issuance of the related public key certificate data is registered in the SAM database based on the identifier SAM ID and the public key data K.

Step SD The certificate usage control policy manager reads the public key certificate data CERof the related SAM from the CER database and outputs the same to the SAM manager .

Step SD The signature processor takes the hush value of the public key certificate data CER generates signature data SIGby using the secret key data Kof the EMD service center and outputs this to the SAM manager .

Step SD The SAM manager encrypts the public key certificate data CERand the signature data SIGthereof by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the SAM and then transmits the same to the SAM .

Note that the processing where the SAMs to request public key certificate data is basically the same as the case of the SAM mentioned above except the object is replaced by the SAMs to .

Note that in the present invention the EMD service center can generate the public key certificate data CERof the public key data Ktoo at the time of shipping when for example storing the secret key data Kand the public key data Kof the SAM in the storage unit of the SAM at the time of shipping of the SAM .

At this time it is also possible to store public key certificate data CERin the storage unit of the SAM at the time of shipping.

Below an explanation will be made of the processing where the EMD service center receives a request for registration of the usage control policy data and the content key data Kc from the content provider by referring to and .

Step SE When receiving the usage control policy registration request module Modshown in from the content provider the content provider manager decrypts the usage control policy registration request module Modby using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator shown in .

Step SE The signature processor verifies the legitimacy of the signature data SIGby using the public key data Kread from the key database

Step SE The certificate usage control policy manager registers the usage control policy data and the content key data Kc stored in the usage control policy registration request module Modin the CER database

Below an explanation will be made of the processing where the settlement processing is carried out in the EMD service center by referring to and .

Step SF When receiving as its input the user log data and a signature data SIGthereof from for example the SAM of the user home network the SAM manager decrypts the usage log data and the signature data SIGby using the session key data Kobtained by the mutual authentication between the mutual authenticator and the SAM verifies the signature data SIGby the public key data Kof the SAM and then outputs the same to the settlement processor .

Step SF The settlement processor performs the settlement processing based on the usage log data input from the SAM manager and the suggested retailer price data SRP and the sale price contained in the usage control policy data read from the CER database via the certificate usage control policy manager and generates the settlement claim data and the settlement report data . Note that the settlement claim data and the settlement report data can be generated whenever the usage log data is input from the SAM too or can be generated for every predetermined period too.

Step SF The settlement processor outputs the settlement claim data to the settlement organization manager .

The settlement organization manager transmits the settlement claim data and the signature data SIGthereof via the payment gateway shown in to the settlement organization after the mutual authentication and the decryption by the session key data K.

Note that it is also possible for the EMD service center to transmit the settlement claim data to the content provider and for the content provider to claim money at the settlement organization by using the settlement claim data .

Step SF The settlement processor outputs the settlement report data to the content provider manager .

The settlement report data as mentioned above describes for example the content of the settlement concerning the content provider performed with respect to the settlement organization shown in by the EMD service center .

The content provider manager encrypts the settlement report data by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator shown in and then transmits the same to the content provider .

Further it is also possible that the EMD service center register authorize the usage control policy data as mentioned above and then encrypt the authorization certificate module Modshown in by the distribution key data KDto KDand transmit the same from the EMD service center to the content provider .

Further the EMD service center performs the processing at the time of shipment of the SAMs to and the registration processing of the SAM registration list other than the above. These processings will be explained later.

Note that it is also possible that the AV apparatuses to have the network communication function or do not have the network communication function but utilize the network communication function of the network apparatus .

Further it is also possible for the user home network to have only the AP apparatus not having a network function.

As shown in the network apparatus has the SAM a communication module a decryption decompression module a purchase usage mode determination controller a download memory a reproduction module and an external memory .

The SAMs to are modules for the charge processing in units of content and communicate with the EMD service center .

The SAMs to for example are managed in specifications and versions by the EMD service center and are licensed to manufactures of home apparatuses as black box charging modules for charging in units of content when desired to be mounted. For example a manufacturer developing a home apparatus cannot learn the internal specifications of the ICs integrated circuit of the SAMs to . The EMD service center standardizes the interfaces etc. of the related ICs. These are mounted in the network apparatus and the AV apparatuses to accordingly.

The SAMs to are hardware modules IC modules etc. with processing contents completely shut off from the outside and thereby having tamper resistance preventing the processing contents from being monitored or tampered with from the outside and preventing data stored in the inside in advance and the data being processed from being monitored and tampered from the outside.

When realizing the functions of the SAM to in the form of ICs the ICs have secret memories and store secret programs and secret data therein. The SAMs are not limited to the physical mode of ICs. If the functions can be built into a portion of the apparatus it is also possible to define that portion as a SAM.

Note that in the flow of the data related to the processing for inputting the secure container from the content provider and decrypting the key file KF in the secure container is shown.

As shown in the SAM has a mutual authenticator encryptor decryptors and a content provider manager an error corrector a download memory manager a secure container decryptor a decryption decompression module manager an EMD service center manager a usage monitor a charge processor a signature processor a SAM manager a media SAM manager a stack work memory and an external memory manager .

Note that the AV apparatuses to do not have download memories therefore there are no download memory managers in the SAMs to .

Note that the predetermined functions of the SAM shown in are realized by executing a secret program in for example a not illustrated CPU.

Further the stack memory stores the usage log data and the SAM registration list after the following processings as shown in .

Here the memory space of the external memory cannot be seen from the outside for example a host CPU of the SAM . Only the SAM can manage the access with respect to the storage region of an external memory .

Further as the stack memory use is made of for example a SARAM. As shown in the secure container content key data Kc usage control policy data UCP a lock key data Kof a storage unit the public key certificate CERof the content provider the usage control status data UCS the SAM program download containers SDCto SDC etc. are stored.

Below an explanation will be made of the processing content of the functional blocks when inputting the secure container from the content provider among the functions of the SAM by referring to .

When the SAM transfers data on line with the content provider and the EMD service center the mutual authenticator performs the mutual authentication between the content provider and the EMD service center to generate the session key data common key Kand outputs this to the encryptor decryptor . The session key data Kis newly generated whenever mutual authentication is carried out.

The encryptor decryptor encrypts and or decrypts the data transferred with the content provider and the EMD service center by using the session key data Kgenerated by the mutual authenticator .

The error corrector corrects the error of the secure container and outputs the result to the download memory manager .

Note that it is also possible that the user home network have the function of detecting whether or not the secure container has been tampered with.

In the present embodiment the case where the error corrector was included in the SAM was illustrated but it is also possible to impart the function of the error corrector to the outside of the SAM for example the host CPU .

The download memory manager encrypts the secure container after the error correction by using the session contained Kobtained by the mutual authentication after the mutual authentication between the mutual authenticator and a media SAM when the download memory has the media SAM having the mutual authentication function as shown in and writes the same into the download memory shown in . As the download memory use is made of a nonvolatile semiconductor memory for example a memory stick.

Note that as shown in when a memory not provided with a mutual authentication function such as an HDD hard disk drive is used as a download memory the interior of the download memory is not secure therefore the content file CF is downloaded in the download memory and the key file KF having the high secrecy is downloaded in the stack memory shown in .

The secure container decryptor decrypts the key file KF stored in the secure container input from the download memory manager by using the distribution key data KDto KDof the corresponding period read from the storage unit and confirms the legitimacy of the signature data SIGto SIG that is the legitimacy of the creator of the content data C content key data Kc and the usage control policy data in the signature processor and then writes the decrypted data into the stack memory .

The signature processor verifies the signature data in the secure container by using the public key data Kof the EMD service center read from the storage unit and the public key data Kof the content provider .

The storage unit stores as secret data which cannot be read and rewritten from the outside of the SAM as shown in the distribution key data KDto KD SAM ID user ID password information reference use ID SAM registration list storage key data K public key data Kof the route CA public key data Kof the EMD service center media key data K public key data Kof the EMD service center secret key data Kof the SAM public key certificate data CERstoring public key data Kof the SAM therein signature data SIGof the public key certificate CERusing the secret key data Kof the EMD service center the original key data for the mutual authentication with the decryption decompression module and the original key data for the mutual authentication with the media SAM.

Further the storage unit stores a secret program for realizing at least part of the functions shown in .

As the storage unit use is made of for example a flash EEPROM electrically erasable programmable RAM .

Below an explanation will be made of the flow of the processing when inputting the secure container from the content provider in the flow of the processing of the SAM .

First the flow of the processing in the SAM when storing the distribution key data KDto KDreceived from the EMD service center in the storage unit will be explained by referring to .

In this case first the mutual authentication is carried out between the mutual authenticator and the mutual authenticator shown in .

Next three months worth of the distribution key data KDto KDencrypted by the session key data Kobtained by the related mutual authentication and the signature data SIGto SIGthereof are written from the EMD service center via the EMD service center manager into the stack memory .

Next the encryptor decryptor uses the session key data Kto decrypt the distribution key data KDto KDand the signature data SIGto SIG.

Next the signature processor confirms the legitimacy of the signature data SIGto SIGstored in the stack memory then writes the distribution key data KDto KDinto the storage unit .

Below an explanation will be made of the flow of the processing in the SAM when inputting the secure container from the content provider and decrypting the key file KF in the secure container by referring to and .

Step SG The mutual authentication is carried out between the mutual authenticator of the SAM shown in and the mutual authenticator shown in .

The encryptor decryptor decrypts the secure container received from the content provider via the content provider manager by using the session key data Kobtained by the related mutual authentication.

Step SG The signature processor verifies the signature data SIGshown in and then confirms the legitimacy of the signature data SIGand SIGby using the public key data Kof the content provider stored in the public key certificate data CERshown in .

When the legitimacy of the signature data SIGand SIGis confirmed the content provider manager outputs the secure container to the error corrector .

The error corrector corrects the error of the secure container and then outputs the result to the download memory manager .

Step SG The download memory manager performs the mutual authentication between the mutual authenticator and the media SAM shown in and then writes the secure container into the download memory .

Step SG The download memory manager performs the mutual authentication between the mutual authenticator and the media SAM shown in and then reads the key file KF shown in stored in the secure container from the download memory and outputs the same to the secure container decryptor .

Then the secure container decryptor decrypts the key file KF by using the distribution key data KDto KDof the corresponding period input from the storage unit and outputs the signature data SIGand SIGto SIGstored in the signature certificate module Modshown in to the signature processor .

Step SG The signature processor verifies the signature data SIGshown in and then verifies the signature data SIGto SIGby using the public key data Kstored in the public key certificate data CERshown in . By this the legitimacy of the creator of the content data C content key data Kc and the usage control policy data is verified.

Step SG The secure container decryptor writes the key file KF into the stack memory when the legitimacy of the signature data SIGto SIGis confirmed.

Below an explanation will be made of the processing content of the functional blocks related to the processing for using and or purchasing the content data C downloaded in the download memory by referring to .

The usage monitor reads the usage control policy data and the usage control status data from the stack memory and monitors so that the content is purchased and or used within the range permitted by the related read usage control policy data and usage control status data .

Here the usage control policy data has been stored in the key file KF shown in stored in the stack memory after decryption as explained by using .

Further the usage control status data is stored in the stack memory when the purchase mode is determined by the user as will be mentioned later.

The charge processor generates the usage log data in response to a control signal S from the purchase usage mode determination controller shown in .

Here the usage log data describes the log of the purchase and usage modes of the secure container by the user as mentioned before and is used when performing the settlement processing in accordance with the purchase of the secure container and determining the payment of the license fee in the EMD service center .

Further the charge processor notifies the sale price or the suggested retailer price data SRP read from the stack memory to the user according to need.

Here the sale price and the suggested retailer price data SRP have been stored in the usage control policy data of the key file KF shown in stored in the stack memory after decryption.

The charge processing by the charge processor is carried out based on the content of the rights such as the license conditions indicated by the usage control policy data and the usage control status data under the monitoring of the usage monitor . Namely the user purchases and uses the content within the range according to the related content of rights etc.

Further the charge processor generates the usage control status UCS data describing the purchase mode of the content by the user and writes this into the stack memory .

As the purchase modes of the content there are for example a straight purchase without restriction as to reproduction by the purchaser and copying for the usage of the related purchaser and a reproduction charge charging whenever it is reproduced.

Here the usage control status data is generated when the user determines the purchase mode of the content then is used for control so that the user uses the related content within the range permitted by the related determined purchase mode. The usage control status data describes the ID of the content the purchase mode the price in accordance with the related purchase mode the SAM ID of the SAM with the purchase of the related content performed therefor USER ID of the purchasing user etc.

Note that where the determined purchase mode is the reproduction charge for example the usage control status data is transmitted from the SAM to the content provider in real time simultaneously with the purchase of the content data C and the content provider indicates to the EMD service center to obtain the usage log data at the SAM within the predetermined period.

Further where the determined purchase mode is a straight purchase for example the usage control status data is transmitted in real time to both of the content provider and the EMD service center . In this way in the present embodiment in the both cases the usage control status data is transmitted in real time to the content provider .

The EMD service center manager transmits the usage log data read from the external memory via the external memory manager to the EMD service center .

At this time the EMD service center manager generates the signature data SIGof the usage log data by using the secret key data Kin the signature processor and transmits the signature data SIGtogether with the usage log data to the EMD service center .

The usage log data can be transmitted to the EMD service center in response to for example a request from the EMD service center or periodically or can be transmitted when the amount of the log information contained in the usage log data becomes the predetermined amount or more. The related amount of information is determined in accordance with for example the storage capacity of the external memory .

The download memory manager outputs the content data C read from the download memory the content key data Kc read from the stack memory and the user watermark data input from the charge processor to the decryption decompression module manager in the case where for example the reproduction operation of the content is carried out in response to a control signal S from the purchase mode determination controller shown in .

Further the decryption decompression module manager outputs the content file CF read from the download memory and the content key data Kc and a semi disclosure parameter data read from the stack memory to the decryption decompression module manager when performing a trial listening operation of the content in response to the control signal S from the purchase mode determination controller shown in .

Here the semi disclosure parameter data is described in the usage control policy data and indicates the handling of the content in the trial listening mode. In the decryption decompression module it becomes possible to reproduce the encrypted content data C in the semi disclosure state based on the semi disclosure parameter data . As the procedure of the semi disclosure there is for example a procedure of designating the blocks to be decrypted and the blocks not to be decrypted by using the content key data Kc limiting the reproduction function at the time of trial listening or limiting a trial listening enable period by the semi disclosure parameter data by utilizing the fact that the decryption decompression module processes the data signal in units of predetermined blocks.

First an explanation will be made of the flow of the processing up to when the purchase mode of the secure container downloaded in the download memory from the content provider is determined by referring to and .

Step SH In the charge processor it is decided whether or not the control signal S indicating the trial listening mode was generated by the operation of the purchase usage mode determination controller shown in by the user. When it is decided that it was generated the processing of step SH is carried out while when it was not so generated the processing of step SH is carried out.

Step SH By the charge processor for example the content file CF stored in the download memory is output via the decryption decompression module manager to the decryption decompression module shown in .

At this time the mutual authentication between the mutual authenticator and the media SAM and the encryption and or decryption by the session key data Kand the mutual authentication between the mutual authenticator and the mutual authenticator and the encryption and or decryption by the session key data Kare carried out with respect to the content file CF.

Further the content key data Kc and the semi disclosure parameter data read from the stack memory are output to the decryption decompression module shown in . At this time after the mutual authentication between the mutual authenticator and the mutual authenticator the encryption and decryption by the session key data Kare carried out with respect to the content key data Kc and the semi disclosure parameter data .

Next the decrypted semi disclosure parameter data is output to a semi disclosure processor and the content data Cis decrypted using the content key data Kc by the decryptor by semi disclosure under the control from the semi disclosure processor .

Next the content data C decrypted by semi disclosure is decompressed at a decompression unit and then output to an electronic watermark information processor .

Next the user watermark data is buried in the content data C in the electronic watermark information processor then the content data C is reproduced at the reproduction module and the audio in accordance with the content data C is output.

Step SH When the user determines the purchase mode by operating the purchase usage mode determination controller the control signal S indicating the related determined purchase mode is output to the charge processor .

Step SH In the charge processor the usage log data and the usage control status data in accordance with the determined purchase mode are generated the usage log data is written into the external memory via the external memory manager and the usage control status data is written into the stack memory .

Thereafter in the usage monitor control monitoring is carried out so that the content are purchased and used within the range permitted by the usage control status data .

Step SH The usage control status data is added to the key file KF stored in the stack memory to generate a new key file KFhaving the purchase mode determined therein shown in mentioned later. The key file KFis stored in the stack memory .

As shown in the usage control status data stored in the key file KFhas been encrypted by utilizing the CBC mode of the DES by using the storage key data K. Further the MAC value generated by using the related storage key data Kas the MAC key data that is MAC is added. Further a module comprised by the usage control status data and the MACis encrypted by utilizing the CBC mode of the DES by using the media key data K. Further the MAC value generated by using the related media key data Kas the MAC key data that is MAC is added to the related module.

Below an explanation will be made of the flow of the processing in the case where the content data C having the purchase mode already determined and stored in the download memory is reproduced by referring to and .

Step SI The charge processor receives as its input the control signal S designating the content to be reproduced in accordance with the operation by the user.

Step SI In the charge processor the content file CF stored in the download memory is read based on the control signal S under the monitoring of the usage monitor .

Step SI The related read content file CF is output to the decryption decompression module shown in . At this time the mutual authentication is carried out between the mutual authenticator shown in and the mutual authenticator of the decryption decompression module shown in .

Further the content key data Kc read from the stack memory is output to the decryption decompression module .

Step SI The decryptor of the decryption decompression module decrypts the content file CF using the content key data Kc and the decompression processing by the decompression unit and reproduces the content data C at the reproduction module .

Step SI The charge processor updates the usage log data stored in the external memory in response to the control signal S.

The usage log data is read from the external memory and then passes through the mutual authentication and is transmitted via the EMD service center manager together with the signature data SIGto the EMD service center .

Below an explanation will be made of the flow of the processing in the SAM in a case where as shown in for example the content file CF having the purchase mode already determined and downloaded in the download memory of the network apparatus and the key file KF are transferred to the SAM of the AV apparatus via the bus by referring to and .

Step SJ The user operates the purchase usage mode determination controller and indicates the transfer of the predetermined content stored in the download memory to the AV apparatus and the control signal S in accordance with the related operation is output to the charge processor .

By this the charge processor updates the usage log data stored in the external memory based on the control signal S.

Step SJ The download memory manager outputs the content file CF shown in read from the download memory to the SAM manager .

Step SJ The key file KFshown in read from the stack memory is output to the signature processor and the SAM manager .

Step SJ The signature processor generates signature data SIGof the key file KFread from the stack memory and outputs this to the SAM manager .

Further the SAM manager reads public key certificate data CERshown in and signature data SIGthereof from the storage unit .

Step SJ The mutual authenticator outputs the session key data Kobtained by the mutual authentication with the SAM to the encryptor decryptor .

Step SJ The encryptor decryptor encrypts the data by using the session key data Kand then output it to the SAM of the AV apparatus shown in .

At this time parallel to the mutual authentication between the SAM and the SAM the mutual authentication of the bus as the IEEE1394 serial bus is carried out.

Below as shown in the flow of the processing in the SAM when writing the content file CF etc. input from the SAM into a storage media such as a RAM type will be explained by referring to and .

Step SK The SAM manager of the SAM receives as its inputs the content file CF shown in key file KF and the signature data SIGthereof shown in and public key certificate data CERand the signature data SIGthereof shown in from the SAM of the network apparatus as shown in .

Then the encryptor decryptor decrypts the content file CF the key file KFand the signature data SIGthereof and the public key certificate data CERand the signature data SIGthereof input by the SAM manager by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator of the SAM .

Next the key file KFand the signature data SIGthereof and public key certificate data CERand the signature data SIGthereof decrypted by using the session key data Kare written into the stack memory .

Step SK The signature processor verifies the signature data SIGread from the stack memory by using the public key data Kread from the storage unit and confirms the legitimacy of public key certificate data CER.

Then the signature processor confirms the legitimacy of the signature data SIGby using the public key data Kstored in the public key certificate data CERwhen confirming the legitimacy of the public key certificate data CER.

Next when the legitimacy of the signature data SIG that is the legitimacy of the creator of the key file KF is confirmed it reads the key file KFshown in from the stack memory and outputs it to the encryptor decryptor .

Note that in the related example the case where the creator of the key file KFand the source of transmission were the same was explained but when the creator of the key file KFand the source of transmission are different the signature data of the creator and the signature data of the transmitter are generated with respect to the key file KFand the legitimacy of both signature data is verified at the signature processor .

Step SK The encryptor decryptor sequentially encrypts the key file KFby using the storage key data K media key data K and purchaser key data Kread from the storage unit and outputs the same to the media SAM manager .

Note that the media key data Kis stored in the storage unit in advance by the mutual authentication between the mutual authenticator shown in and the media SAM of the RAM type storage media shown in .

Here the storage key data Kis the data determined in accordance with the type of the apparatus for example a SACD super audio compact disc or DVD digital versatile disc apparatus CD R apparatus and MD Mini Disc apparatus AV apparatus in the related example and is used for establishing a one to one correspondence between the types of the apparatuses and the types of the storage media. Note that the physical configurations of the disc media are the same between an SACD and a DVD so there is a case where the storage and or reproduction of the SACD storage media can be carried out by using a DVD apparatus. The storage key data Kplays the role of preventing illicit copying in such a case.

Further the media key data Kis data unique to the storage medium the RAM type storage medium in the related example .

The media key data Kis stored in the storage media the RAM type storage media shown in in the related example side and preferably performs the encryption and decryption using the media key data Kin the media SAM of the storage media from the viewpoint of the security. At this time the media key data Kis stored in the related media SAM when the media SAM is mounted in the storage media while is stored in for example a region in the RAM region out of the management of the host CPU when the media SAM is not mounted in the storage media.

Note that as in the present embodiment it is also possible that the mutual authentication be carried out between the apparatus side SAM SAM in the related example and the media SAM media SAM in the related example the media key data Kbe transferred to the apparatus side SAM via the secure communication route and the encryption and decryption using the media key data Kbe carried out in the apparatus side SAM.

In the present embodiment the storage key data Kand the media key data Kare used for protecting the security of the level of the physical layer of the storage media.

Further the purchaser key data Kis the data indicating the purchaser of the content file CF and is allocated to the related purchased user by the EMD service center when the user purchases the content by for example a straight purchase. The purchaser key data Kis managed in the EMD service center .

Step SK The media SAM manager outputs the content file CF input from the SAM manager and the key file KFinput from the encryptor decryptor to the storage module shown in .

Then the storage module writes the content file CF and key file KFinput from the media SAM manager into the RAM region of the RAM type storage media shown in . In this case it is also possible that the key file KFbe written into the media SAM .

Below the flow of the processing when determining the purchase mode in the AV apparatus when a user home network receives off line the distribution of the ROM type storage medium shown in having the not yet determined purchase mode of the content will be explained by referring to and .

Step SL The SAM of the AV apparatus first performs the mutual authentication between the mutual authenticator shown in and the media SAM of the ROM type storage media shown in and then receives as its input the media key data Kfrom the media SAM .

Note that it is also possible that the related input not be carried out when the SAM holds the media key data Kin advance.

Step SL The key file KF and signature data SIGthereof and the public key certificate data CERand signature data SIGthereof shown in stored in the secure container stored in the RAM region of the ROM type storage media are input via the media SAM manager and are written into the stack memory .

Step SL The signature processor after confirming the legitimacy of the signature data SIG fetches the public key data Kfrom public key certificate data CERand verifies the legitimacy of the signature data SIG that is the legitimacy of the creator of the key file KF by using this public key data K.

Step SL When the legitimacy of the signature data SIGis confirmed at the signature processor the key file KF is read from the stack memory to the secure container decryptor .

Then the secure container decryptor decrypts the key file KF by using the distribution key data KDto KDof the corresponding period.

Step SL The signature processor after confirming the legitimacy of a signature data SIGM stored in the key file KF by using the public key data K verifies the legitimacy of the signature data SIGto SIG that is the legitimacy of the creator of the content data C content key data Kc and the usage control policy data by using the public key data Kstored in the public key certificate data CERin the key file KF.

Step SL The charge processor decides whether or not a control signal S indicating the trial listening mode was generated by the operation of the purchase usage mode determination controller shown in by the user and where the generation is decided the processing of step SL is carried out and while where the generation is not decided the processing of step SL is carried out.

Step SL After the mutual authentication between the mutual authenticator shown in and the decryption decompression module shown in the decryption decompression module manager of the SAM outputs the content key data Kc stored in the stack memory the semi disclosure parameter data stored in the usage control policy data and the content data C read from the ROM region of the ROM type storage media to the decryption decompression module shown in . Next the decryption decompression module decrypts the content data C in the semi disclosure mode by using the content key data Kc and then decompresses it and outputs it to a reproduction module . Then the reproduction medial reproduces the content data C from the decryption decompression module in the trial listening mode.

Step SL The purchase mode of the content is determined by the purchase operation of the purchase mode determination controller shown in by the user then the control signal S indicating the related determined purchase mode is input to the charge processor .

Step SL The charge processor generates the usage control status data in response to the control signal S and writes this into the stack memory .

Step SL For example a new key file KFshown in storing the usage control status data in the key file KF shown in is output from the stack memory to the encryptor decryptor .

Step SL The encryptor decryptor sequentially encrypts the key file KFshown in read from the stack memory by using the storage key data K media key data K and the purchaser key data Kread from the storage unit and outputs the same to the media SAM manager .

Step SL After the mutual authentication between the mutual authenticator shown in and the media SAM shown in the SAM manager writes the key file KFinput from the encryptor decryptor via a storage module shown in into the RAM region or the media SAM of the ROM type storage media .

At this time the usage control status data and the usage log data generated by the charge processor are read from the stack memory and the external memory at the predetermined timing and transmitted to the EMD service center .

Below as shown in an explanation will be made of the flow of the processing when reading the secure container from the ROM type storage media having the not yet determined purchase mode in the AV apparatus and transferring the same to the AV apparatus determining the purchase mode at the AV apparatus and writing the same into RAM type storage media by referring to and .

Step SM The mutual authentication is carried out between the SAM of the AV apparatus and the media SAM of the ROM type storage media then a media key data Kof the ROM type storage media is transferred to the SAM .

At this time similarly the mutual authentication is carried out between the SAM of the AV apparatus and a media SAM of the RAM type storage media then a media key data Kof the RAM type storage media is transferred to the SAM .

Step SM The SAM sequentially decrypts the key file KF the signature data SIG and the public key certificate data CERand the signature data SIGthereof of read from the RAM region in the encryptor decryptor shown in by using the distribution key data KDto KDof the corresponding period.

Next the content file CF decrypted in the encryptor decryptor is output to the encryptor decryptor encrypted by using the session key data Kobtained by the mutual authentication between the SAM and and then output to the SAM manager .

Further the key file KF decrypted in the encryptor decryptor is output to the encryptor decryptor and the signature processor .

Step SM The signature processor generates the signature data SIGof the key file KF by using the secret key data Kof the SAM and outputs this to the encryptor decryptor .

Step SM The encryptor decryptor encrypts the public key certificate data CERof the SAM and the signature data SIGthereof the key file KF and the signature data SIGthereof read from the storage unit and the content file CF shown in read from the ROM region of the ROM type storage media by using the session key data Kobtained by the mutual authentication between the SAM and and then outputs the same to the SAM of the AV apparatus via the SAM manager .

Step SN In the SAM as shown in the content file CF input from the SAM via the SAM manager is decrypted by using the session key data Kin the encryptor decryptor and then written into a RAM region of the RAM type storage media via the media SAM manager .

Further the key file KF and the signature data SIGthereof and the public key certificate data CERand the signature data SIGthereof input from the SAM via the SAM manager are written into the stack memory and then decrypted by using the session key data Kin the encryptor decryptor .

Step SN The related decrypted signature data SIGis verified in the signature processor . When the legitimacy thereof is confirmed the legitimacy of the signature data SIG that is the legitimacy of the source of transmission of the key file KF is confirmed by using the public key data Kstored in the public key certificate data CER.

Then when the legitimacy of the signature data SIGis confirmed the key file KF is read from the stack memory and output to the secure container decryptor .

Step SN The secure container decryptor decrypts the key file KF by using the distribution key data KDto KDof the corresponding period and writes the related decrypted key file KF into the stack memory after the predetermined signature verification.

Thereafter the usage control policy data stored in the key file KF already decrypted and stored in the stack memory is output to the usage monitor . Then the usage monitor manages the purchase mode and the usage mode of the content based on the usage control policy data .

Step SN The charge processor decides whether or not the control signal S indicating the trial listening mode is generated by the operation of the purchase usage mode determination controller of by the user performs the processing of step SN when it decides it is generated and performs the processing of step SN when it is not generated.

Step SN When the trial listening mode is selected by the user the content data C of the content file CF already decrypted by the session key data K the content key data Kc stored in the stack memory the semi disclosure parameter data and the user watermark data obtained from the usage control policy data are output to the reproduction module via the decryption decompression module manager shown in after the mutual authentication. Then the reproduction module reproduces the content data C corresponding to the trial listening mode.

Step SN The purchase and or usage mode of the content is determined by the operation of the purchase usage determination controller shown in by the user then the control signal S in accordance with the related determination is output to the charge processor .

Step SN The charge processor generates the usage control status data and the usage log data in accordance with the determined purchase and or usage mode and writes this into the stack memory and the external memory .

Step SN For example the key file KFshown in storing the usage control status data read from the stack memory is generated then this is output to the encryptor decryptor .

Step SN The encryptor decryptor sequentially encrypts the data by using the storage key data K media key data K and the purchaser key data Kread from the storage unit and outputs it to the media SAM manager .

Step SN The media SAM manager writes the key file KFinto the RAM region or the media SAM of the RAM type storage media by the storage module shown in .

Further the usage control status data and the usage log data are transmitted to the EMD service center at the predetermined timing.

When realizing the functions of the SAMs to as hardware by using an ASIC type CPU including a memory data having a high degree of secrecy such as the security functional module for realizing the functions shown in the program module for performing the right clearing of the content and the key data are stored in that memory. A series of right clearing use program modules such as an encryption library module public key code common key code random number generator hush function a program module for the usage control of the content and a program module of the charge processing are mounted as for example software.

For example a module such as the encryptor decryptor shown in is installed as an IP core in the ASIC type CPU as hardware due to the problem of for example processing speed. Depending to the clock speed or performance of CPU code system etc. it is also possible to install the encryptor decryptor as software.

Further as the storage unit shown in the program module for realizing the functions shown in and the memory for storing the data use is made of for example a nonvolatile memory flash ROM while as the working memory a high speed writable memory such as an SRAM is used. Note that other than them as the memory included in the SAMs to it is also possible to use a ferroelectric memory FeRAM .

Further the SAMs to include other than the above a clock function used for the verification of the date in the term of validity and the contract period etc. for the usage of the content.

As mentioned above the SAMs to have tamper resistant structures shutting off the program module data and the processing content from the outside. In order to prevent the program and content of data having high secrecy stored in the memory inside the IC of the related SAM or the values of the group of registers and the encryption library related to the system configuration of the SAMs or the group of registers of the clock from being read and newly written via the bus of the host CPU of the apparatuses with the SAMs to mounted thereon that is in order to prevent the host CPU of the mounted apparatus from accessing the allocated address space each SAM sets an address space not visible from the host CPU of the mounted apparatus side using an MMU memory management unit for managing the memory space on the CPU side.

Further the SAMs to have structures durable also against X rays or heats or other physical attack from the outside and further have structures whereby even if real time debugging reverse engineering using a debugging tool hardware ICE software ICE or the like is carried out the processing content cannot be understood or whereby a debugging tool per se cannot be used after the manufacture of ICs.

The SAMs to themselves are usual ASIC type CPUs including memories in the hardware structure. Their functions depend on the software for operating the related CPUs but they differ from the general ASIC type CPUs in the point that they have encryption functions and tamper resistant hardware structures.

When realizing all of the functions of the SAMs to by software there is the case where the software processing is carried out by enclosing the same inside a module having tamper resistance and the case where they are achieved by software processing on the host CPU mounted on a usual set and contrivances made to make deciphering impossible at only the time of the related processing. The former is the same as the case where the encryption library module is stored in the memory not as an IP core but as a usual software module and can be considered similar to the case where it is realized as hardware. On the other hand the latter is referred to as tamper resistant software whereby even if the state of execution can be deciphered by an ICE debugger the sequence of execution of a task is scattered in this case the task is cut so that each cut task piece has meaning as a program that is there is no influence upon the lines before and after that or the task per se is encrypted and can be realized in the same way as a task scheduler MiniOS aimed at one type of secure processing. The related task scheduler is buried in the target program.

As shown in the decryption decompression module has the mutual authenticator decryptor decryptor decompression unit electronic watermark information processor and semi disclosure processor .

The mutual authenticator performs the mutual authentication with the mutual authenticator shown in and generates the session key data Kwhen the decryption decompression module receives as its input the data from the SAM .

The decryptor decrypts the content key data Kc semi disclosure parameter data user watermark data and content data C input from the SAM by using the session key data K. Then the decryptor outputs the decrypted content key data Kc and the content data C to the decryptor outputs the decrypted user watermark data to the electronic watermark information processor and outputs the semi disclosure parameter data to the semi disclosure processor .

The decryptor decrypts the content data C in the semi disclosure state by using the content key data Kc under the control of the semi disclosure processor and outputs the decrypted content data C to the decompression unit .

The decompression unit decompresses the decrypted content data C and outputs the same to the electronic watermark information processor .

The decompression unit performs the decompression processing by using the A V decompression software stored in the content file CF shown in and performs the decompression processing by for example the ATRAC3 method.

The electronic watermark information processor buries the user watermark in accordance with the decrypted user watermark data in the decrypted content data C to generate new content data C. The electronic watermark information processor outputs the related new content data C to the reproduction module .

In this way the user watermark is buried at the decryption decompression module when reproducing the content data C.

Note that in the present invention it is also possible that the user watermark data not be buried in the content data C.

The semi disclosure processor indicates the blocks not to be decrypted and the blocks to be decrypted in for example the content data C to the decryptor based on the semi disclosure parameter data .

Further the semi disclosure processor performs control to for example limit the reproduction function at the time of trial listening or limit the possible listening period based on the semi disclosure parameter data .

The reproduction module performs the reproduction in accordance with the decrypted and decompressed content data C.

Next an explanation will be made of the data format when transferring data with the signature data generated by using the secret key data attached thereto and public key certificate data among the content provider EMD service center and user home network .

In this case a module Modencrypted by the session key data Kobtained by the mutual authentication between the content provider and the SAM is transmitted from the content provider to the SAM .

The module Modstores the public key certificate data CERstoring the secret key data Kof the content provider the signature data SIGobtained based on the secret key data Kwith respect to the public key certificate data CER and the data Data to be transmitted.

In this way by transmitting the module Modstoring the public key certificate data CERfrom the content provider to the SAM when verifying the signature data SIGat the SAM it becomes unnecessary to transmit the public key certificate data CERfrom the EMD service center to the SAM .

In this case a module Modshown in encrypted by the session key data Kobtained by the mutual authentication between the content provider and the SAM is transmitted from the content provider to the SAM .

The module Modstores the data Data to be transmitted and the signature data SIGbased on the secret key data Kthereof.

Further a module Modshown in encrypted by the session key data Kobtained by the mutual authentication between the EMD service center and the SAM is transmitted from the EMD service center to the SAM .

The module Modstores the public key certificate data CERof the content provider and the signature data SIGbased on the secret key data Kthereof.

In this case a module Modencrypted by the session key data Kobtained by the mutual authentication between the content provider and the SAM is transmitted from the SAM to the content provider .

The module Modstores the public key certificate data CERstoring the secret key data Kof the SAM the signature data SIGbased on the secret key data Kwith respect to public key certificate data CER and the data Data to be transmitted.

In this way by transmitting the module Modstoring the public key certificate data CERfrom the SAM to the content provider when verifying the signature data SIGin the content provider it becomes unnecessary to transmit the public key certificate data CERfrom the EMD service center to the content provider .

In this case a module Modshown in encrypted by the session key data Kobtained by the mutual authentication between the content provider and the SAM is transmitted from the SAM to the content provider .

The module Modstores the data Data to be transmitted and the signature data SIGbased on the secret key data Kthereof.

Further a module Modshown in encrypted by a session key data Kobtained by the mutual authentication between the EMD service center and the content provider is transmitted from the EMD service center to the content provider .

The module Modstores the public key certificate data CERof the SAM and the signature data SIGbased on the secret key data Kthereof.

In this case a module Modencrypted by the session key data Kobtained by the mutual authentication between the content provider and the EMD service center is transmitted from the content provider to the EMD service center .

The module Modstores the public key certificate data CERstoring the secret key data Kof the content provider the signature data SIGbased on the secret key data Kwith respect to public key certificate data CER and the data Data to be transmitted.

In this case a module Modshown in encrypted by the session key data Kobtained by the mutual authentication between the content provider and the EMD service center is transmitted from the content provider to the EMD service center .

The module Modstores the data Data to be transmitted and the signature data SIGbased on the secret key data Kthereof.

At this time the public key certificate data CERof the content provider has been already registered in the EMD service center .

In this case a module Modencrypted by the session key data Kobtained by the mutual authentication between the EMD service center and the SAM is transmitted from the SAM to the EMD service center .

The module Modstores the public key certificate data CERstoring the secret key data Kof the SAM the signature data SIGbased on the secret key data Kwith respect to public key certificate data CER and the data Data to be transmitted.

In this case a module Modshown in encrypted by the session key data Kobtained by the mutual authentication between the EMD service center and the SAM is transmitted from the SAM to the EMD service center .

The module Modstores the data Data to be transmitted and the signature data SIGbased on the secret key data Kthereof.

At this time the public key certificate data CERof the SAM has been already registered in the EMD service center .

Below an explanation will be made of the processing for registration at the EMD service center at the time of shipping of the SAMs to .

Note that the processing for registration of the SAMs to is the same so the processing for registration of the SAM will be explained below.

At the time of shipping of the SAM the key data shown below is initially registered in the storage unit shown in etc. via the SAM manager by the key server of the EMD service center shown in .

Further the SAM stores in the storage unit etc. for example at the time of shipping the program etc. used when the SAM accesses the EMD service center the first time.

Namely the storage unit stores for example the identifier SAM ID of the SAM given the on the left side in the storage key data K the public key data Kof the route certificate authority the public key data Kof the EMD service center the secret key data Kof the SAM the public key certificate data CERand the signature data SIGthereof and the original key data for creating the authentication use key data between the decryption decompression module and the media SAM at the time of initial registration.

Note that it is also possible to transmit the public key certificate data CERfrom the EMD service center to the SAM when registering the same after the shipping of the SAM .

Here the public key data KR CA of the route certificate authority uses an RSA generally used in electronic business transactions over the Internet etc. and has a data length of for example 1024 bits. The public key data KR CA is issued by the route certificate authority shown in .

The public key data Kof the EMD service center is generated by utilizing an elliptical curve code having a short data length and a strength equivalent to the RSA or more and has a data length of for example 160 bits. Note that when considering the strength of the encryption desirably the public key data Khas 192 bits or more. Further the EMD service center registers the public key data Kin the route certificate authority .

Further the route certificate authority generates the public key certificate data CERof the public key data K. The public key certificate data CERstoring the public key data Kis preferably stored in the storage unit at the time of shipping of the SAM . In this case the public key certificate data CERis signed by the secret key data Kof the route certificate authority .

The EMD service center generates a random number to generate the secret key data Kof the SAM and generates the public key data Kforming the pair together with this.

Further the EMD service center is given the authentication of the route certificate authority issues the public key certificate data CERof the public key data K and attaches the signature data to this by using its own secret key data K. Namely the EMD service center achieves the function of the second CA certificate authority .

Further the SAM is allocated a unique identifier SAM ID under the management of the EMD service center by the SAM manager of the EMD service center shown in . This is stored in the storage unit of the SAM and at the same time stored also in the SAM database shown in and managed by the EMD service center .

Further the SAM is connected to the EMD service center by for example the user after shipping for the registration procedure. At the same time the distribution use public key data KDto KDare transferred from the EMD service center to the storage unit .

Namely the user utilizing the SAM must perform the registration procedure at the EMD service center before downloading the content. This registration procedure is performed off line by for example mail by the user entering information identifying itself using for example a registration form attached when purchasing the apparatus with the SAM mounted thereon in the related example the network apparatus .

The EMD service center issues the identifier USER ID unique to the user in accordance with the registration procedure of the SAM by the user manages the correspondence between the SAM ID and the USER ID in for example the SAM database shown in and utilizes the same at the time of charging.

Further the EMD service center allocates the information reference use identifier ID and the password used at the first time to the user of the SAM and notifies these to the user. The user can inquired about information for example the state of usage usage log of the content data up to the present at the EMD service center by using the information reference use identifier ID and the password.

Further the EMD service center confirms the ID at the credit card company or the like and confirms the user off line at the time of registration.

Next as shown in an explanation will be made of the procedure for storing the SAM registration list in the storage unit inside the SAM .

The SAM shown in acquires the SAM registration list of the SAMs to present in its own system by utilizing a topology map generated when starting up the power of the apparatus connected to the bus or connecting a new apparatus to the bus when using for example an IEEE 1394 serial bus as the bus .

Note that the topology map generated in accordance with the IEEE 1394 serial bus that is the bus is generated to cover the SAMs to and the SCMS processing circuits and when for example as shown in in addition to the SAM to the SCMS processing circuits and of the AV apparatuses and are connected to the bus .

Accordingly the SAM fetches the information for the SAMs to from the related topology map to generate the SAM registration list.

Then the SAM registers the related SAM registration list in the EMD service center and acquires a signature.

These processings are automatically carried out by the SAM by utilizing the session of the bus . An instruction for registration of the SAM registration list is issued to the EMD service center .

The EMD service center confirms the term of validity when receiving the SAM registration list shown in from the SAM . Then the EMD service center sets up the corresponding portion by referring to the existence of the settlement function designated by the SAM at the time of registration. Further the EMD service center checks the revocation list and sets a revocation flag in the SAM registration list. The revocation list is the list of the SAMs for which usage is prohibited invalidated by the EMD service center for the reason of for example illicit usage.

Further the EMD service center fetches the SAM registration list corresponding to the SAM at the time of settlement and confirms if the SAM described therein is contained in the revocation list. Further the EMD service center attaches a signature to the SAM registration list.

Note that the SAM revocation list is generated covering only the SAMs of the identical system connected to the identical bus and that the validity and invalidity of the related SAM are indicated by the revocation flag corresponding to each SAM.

Step S The EMD service center transmits the public key certificate data CERof the public key data Kof the content provider to the content provider after the content provider passes through the predetermined registration processing.

Further the EMD service center transmits the certificate CERto CERof the public key data Kto Kof the SAMs to to the SAMs to after the SAMs to pass through the predetermined registration processing.

Further the EMD service center transmits six months worth of the distribution key data KDto KDeach having a term of validity of one month to the content provider after the mutual authentication and transmits three months worth of the distribution key data KDto KDto the user home network .

In this way the EMD system distributes the distribution key data KDto KDto the SAMs to in advance therefore even in the case where the SAMs to are off line from the EMD service center the secure container distributed from the content provider can be decrypted and purchased and used in the SAMs to . In this case the log of the related purchase and or usage is described in the usage log data . The usage log data is automatically transmitted to the EMD service center when the SAMs to and the EMD service center are connected. Therefore the settlement processing in the EMD service center can be reliably carried out. Note that the SAMs for which the usage log data cannot be collected by the EMD service center in a predetermined period are invalidated by the revocation list.

Note that the usage control status data is transmitted from the SAMs to to the EMD service center in real time in principle.

Step S The content provider transmits the right registration request module Modshown in to the EMD service center after the mutual authentication.

Then the EMD service center registers and authorizes the usage control policy data and the content key data Kc after the predetermined signature verification.

Step S The content provider performs the encryption by using the distribution key data KDto KDof the corresponding period etc. generates the content file CF and the key file KF shown in and distributes the secure container storing them and public key certificate data CERshown in to the user home network on line and or off line.

Step S The SAMs to of the user home network decrypt the secure container by using the distribution key data KDto KDof the corresponding period etc. verify the signature etc. for verifying the legitimacy of the creator and the transmitter of the secure container and confirm whether or not the secure container was transmitted from a legitimate content provider .

Step S The SAMs to determine the purchase and or usage mode based on the control signal S in accordance with the operation of the purchase usage mode determination controller shown in by the user.

At this time the usage monitor shown in manages the purchase and or usage mode of the content file CF by the user based on the usage control policy data stored in the secure container .

Step S The charge processor shown in of each of the SAMs to generate the usage log data and the usage control status data describing the operation of the settlement of the purchase and or usage mode by the user based on the control signal S and transmits the same to the EMD service center .

Step S The EMD service center performs the settlement processing based on the usage log data in the settlement processor shown in and generates the settlement claim data and the settlement report data . The EMD service center transmits the settlement claim data and the signature data SIGthereof via the payment gateway shown in to the settlement organization . Further the EMD service center transmits the settlement report data to the content provider .

Step S The settlement organization verifies the signature data SIG then distributes the money paid by the user to the owner of the content provider based on the settlement claim data .

As explained above the EMD system distributes the secure container of the mode shown in from the content provider to the user home network and performs the processing for the key file KF in the secure container in the SAMs to .

Further the content key data Kc and the usage control policy data stored in the key file KF are encrypted by using the distribution key data KDto KDand are decrypted inside only the SAMs to holding the distribution key data KDto KD. Then the SAMs to determine the purchase mode and the usage mode of the content data C based on the handling content of the content data C described in the usage control policy data which a module having tamper resistance.

Accordingly according to the EMD system the purchase and usage of the content data C in the user home network can be reliably carried out based on the content of the usage control policy data generated by the related parties of the content provider .

Further the EMD system enables common right clearing of the content data C in the SAMs to both on line and off line by distributing the content data C from the content provider to the user home network by using the secure container in both cases.

Further the EMD system enables use of common right clearing rules when purchasing using storing and transferring the content data C in the network apparatus and the AV apparatuses to in the user home network by performing processing always based on the usage control policy data .

In the above embodiment as shown in the case where the key file KF was encrypted by using the distribution key data KD in the content provider and where the key file KF was decrypted by using the distribution key data KD in the SAMs to was illustrated but the encryption of the key file KF using the distribution key data KD is not always necessary when the secure container is directly supplied from the content provider to the SAMs to as shown in .

In this way the encryption of the key file KF by using the distribution key data KD exhibits a large effect when suppressing illegal action by the service provider by giving the distribution key data KD to only the content provider and the user home network when supplying content data from the content provider to the user home network via the service provider as in the second embodiment mentioned later.

Note that in the case of the first embodiment as well the encryption of the key file KF by using the distribution key data KD is effective in the point of improving the ability to suppress illicit usage of the content data.

Further in the above embodiment the case where the suggested retailer price data SRP was stored in the usage control policy data in the key file KF shown in was illustrated but it is also possible to store the suggested retailer price data SRP price tag data other than the key file KF in the secure container . In this case the signature data generated by using the secret key data Kis attached to the suggested retailer price data SRP.

In the first embodiment as shown in the case where the EMD service center performs the settlement processing in the settlement organization via the payment gateway by using the settlement claim data generated by an apparatus itself was illustrated but it is also possible to transmit for example the settlement claim data from the EMD service center to the content provider as shown in and have the content provider itself perform the settlement processing with respect to the settlement organization via the payment gateway by using the settlement claim data .

In the above first embodiment the case where the secure container was supplied from the single content provider to the SAMs to of the user home network was illustrated but it is also possible to supply secure containers and from two or more content providers and to the SAMs to .

In this case the EMD service center distributes six months worth of distribution key data KDto KDand KDto KDto the content providers and

Further the EMD service center distributes three months worth of the distribution key data KDto KDand KDto KDto the SAMs to .

Further the content provider supplies the secure container storing a content file CFa encrypted by using a unique content key data Kca and a key file KFa encrypting the content key data Kca and a usage control policy data etc. by using the distribution key data KDto KDof the corresponding period to the SAMs to on line and or off line.

At this time as the identifier of the key file use is made of the global unique identifier Content ID distributed by the EMD service center . The content data is centrally managed by the EMD service center .

Further the content provider supplies the secure container storing a content file CFb encrypted by using unique content key data Kcb and a key file KFb encrypting the content key data Kcb and usage control policy data etc. by using the distribution key data KDto KDof the corresponding period to the SAMs to on line and or off line.

The SAMs to decrypt the secure container by using the distribution key data KDto KDof the corresponding period determine the purchase mode of the content after the predetermined signature verification processing etc. and transmit usage log data and usage control status data generated in accordance with the related determined purchase mode and usage mode to the EMD service center .

Further the SAMs to decrypt the secure container by using the distribution key data KDto KDof the corresponding period determine the purchase mode of the content after the predetermined signature verification processing etc. and transmit usage log data and usage control status data generated in accordance with the related determined purchase mode and usage mode to the EMD service center .

The EMD service center generates settlement claim data for the content provider based on the usage log data and performs the settlement processing with respect to the settlement organization by using this.

Further the EMD service center generates settlement claim data for the content provider based on the usage log data and performs the settlement processing with respect to the settlement organization by using this.

Further the EMD service center performs the authorization by registering the usage control policy data and . At this time the EMD service center distributes the global unique identifier Content ID with respect to the key files KFa and KFb corresponding to the usage control policy data and

Further the EMD service center issues public key certificate data CERa and CERb of the content providers and and attaches its own signature data SIGand SIGto them to certify the legitimacy.

In the above embodiment the case where the content data was directly distributed from the content provider to the SAMs to of the user home network was illustrated but in the present embodiment an explanation will be made of the case of distributing the content data provided by the content provider to the SAM of the user home network via the service provider.

As shown in the EMD system has a content provider an EMD service center a user home network a service provider a payment gateway and a settlement organization .

The content provider EMD service center SAMs to and service provider correspond to the data providing apparatus management apparatus data processing apparatus and data distribution apparatus of the present invention.

The content provider is the same as the content provider of the first embodiment except for the point that it supplies the content data to the service provider .

Further the EMD service center is the same as the EMD service center of the first embodiment except for the point that the authentication function key data management function and right clearing function are provided also with respect to the service provider in addition to the content provider and SAMs to .

Further the user home network has a network apparatus and AV apparatuses to . The network apparatus includes a SAM and a CA module while the AV apparatuses to include the SAMs to .

Here the SAMs to are the same as the SAMs to of the first embodiment except for the point that they receive the distribution of a secure container from the service provider and the point that they perform the verification processing of the signature data and the preparation of an SP use purchase log data data distribution apparatus use purchase log data for the service provider in addition to the content provider .

In the EMD system the content provider transmits the usage control policy UCP data similar to that of the first embodiment mentioned before indicating the content of the right such as the license conditions of the content data C of the content to be provided by itself to the authority manager having a high reliability that is the EMD service center . The usage control policy data is registered in the EMD service center and authorized certified .

Further the content provider encrypts the content data C by the content key data Kc to generate the content file CF. Further the content provider encrypts the content key data Kc and the usage control policy data by using the distribution key data KDto KDof the corresponding period distributed from the EMD service center to generate the key file KF storing them. Then the content provider supplies the secure container storing the content file CF key file KF and its own signature data to the service provider by using the Internet or other network a digital broadcast storage medium or an informal protocol or off line or the like.

When receiving the secure container from the content provider the service provider verifies the signature data and confirms if the secure container was generated by a legitimate content provider and the legitimacy of the sender.

Next the service provider generates price tag data PT indicating the price obtained by adding the price of its service to the price SRP with respect to the content intended by the content provider notified for example off line.

Then the service provider generates the secure container storing the content file CF and key file KF fetched from the secure container the price tag data and the signature data by its own secret key data Kwith respect to them.

At this time the key file KF is encrypted by the distribution key data KDto KD and the service provider does not hold the related distribution key data KDto KD therefore the service provider cannot view or rewrite the content of the key file KF.

The service provider distributes the secure container to the user home network on line and or off line.

At this time in the off line case the secure container is supplied to the SAMs to as it is. On the other hand in the on line case the mutual authentication is carried out between the service provider and the CA module the secure container is encrypted by using the session key data Kin the service provider and transmitted and the secure container received at the CA module is decrypted by using the session key data Kand then transferred to the SAMs to .

Next the SAMs to decrypt the secure container by using the distribution key data KDto KDof the corresponding period distributed from the EMD service center then perform the verification processing of the signature data.

The secure container supplied to the SAMs to is reproduced and stored in the storage medium after the purchase and or usage mode is determined in accordance with the operation of the user in the network apparatus and the AV apparatuses to .

The SAMs to store the log of the purchase and or usage of the secure container as the usage log data .

The usage log data log data or the management apparatus use log data is transmitted from the user home network to the EMD service center in response to for example a request from the EMD service center .

The EMD service center determines calculates the charge content for each of the content provider and the service provider based on the usage log data and performs the settlement at the settlement organization such as the bank via the payment gateway based on the results. By this the money paid by the user of the user home network is distributed to the content provider and the service provider by the settlement processing by the EMD service center .

In the present embodiment in the same way as the first embodiment by providing the content data C of digital by encapsulation value can be imparted to the digital content itself by separating the conventional digital content which had been closely attached to the storage medium from the storage medium.

Here the secure container is the most basic product capsule when selling the content data C product no matter which distribution channel delivery channel it is provided over. Specifically the secure container is a product capsule containing the encryption information for the charging the signature data for verifying the legitimacy of the content of the content data C the legitimacy of the party preparing the content data and the legitimacy of the distributor of the content data and information relating to the copyright such as the information concerning the electronic watermark information to be buried in the content data.

Further in the present embodiment the EMD service center has the certificate authority function key data management function and the right clearing profit distribution function.

Namely the EMD service center plays the role of the second certificate authority with respect to the highest authority manager at the neutral position that is the route certificate authority and certifies the legitimacy of the related public key data by attaching the signature based on the secret key data of the EMD service center to public key certificate data of public key data to be used for the verification processing of the signature data in the content provider service provider and the SAMs to . Further as mentioned before the registration and authorization of the usage control policy data of the content provider and the price tag data of the service provider are achieved by the certificate authority function of the EMD service center .

Further the EMD service center has a key data management function for managing for example the key data of the distribution key data KDto KD.

Further the EMD service center has a right clearing profit distribution function of performing settlement with respect to the purchase and or usage of the content by the user of the user home network based on the usage control policy data registered by the content provider the usage log data input from the SAMs to and the price tag data registered by the service provider and distributing and paying the money paid by the user to the content provider and the service provider .

As shown in the content provider has a content master source server electronic watermark information adder compressor encryptor random number generator encryptor signature processor secure container generator secure container database storage unit mutual authenticator encryptor decryptor usage control policy data generator EMD service center manager and service provider manager .

In components given the same references as those of are the same as the components of the same references explained in the first embodiment by referring to and .

Namely the content provider has a configuration providing the service provider manager in place of the SAM manager shown in .

The service provider manager provides the secure container input from the secure container generator to the service provider shown in off line and or on line. The secure container in the same way as the first embodiment stores the content file CF and the signature data SIGthereof the key file KF and the signature data SIGthereof and the public key certificate data CERand the signature data SIGthereof shown in and .

When distributing the secure container to the service provider on line the service provider manager encrypts the secure container by using the session key data Kin the encryptor decryptor and then distributes the same via the network to the service provider .

Further the flow of the data in the content provider shown in similarly applies also to the service provider .

The service provider distributes the secure container storing the content file CF and key file KF in the secure container provided from the content provider and the price tag data generated by itself to the network apparatus and the AV apparatuses to of the user home network on line and or off line.

The service modes of the distribution of content by the service provider may be roughly classified into an independent service and a linked service.

An independent service is for example a service exclusively for download for individually distributing the content. Further a linked service is a service for distributing content linked to a program and CM advertisement . For example content such as the theme song and insertion song of a drama is stored in the stream of the drama program. The user can purchase content such as the theme song and insertion song in the stream when watching the drama program.

Note that in the flow of the data when supplying the secure container in accordance with the secure container supplied from the content provider to the user home network is shown.

As shown in the service provider has a content provider manager a storage unit a mutual authenticator an encryptor decryptor a signature processor a secure container generator a secure container database a price tag data generator a user home network manager an EMD service center manager and a user preference filter creator .

Below an explanation will be made of the flow of the processing in the service provider when creating the secure container from the secure container supplied from the content provider and distributing this to the user home network by referring to and .

Step SZ The content provider manager receives the supply of the secure container shown in from the content provider on line and or off line and writes the secure container into the storage unit .

At this time the content provider manager decrypts the secure container in the encryptor decryptor by using the session key data Kobtained by the mutual authentication between the mutual authenticator shown in and the mutual authenticator shown in in the on line case and then writes the same into the storage unit .

Step SZ The signature processor verifies the signature data SIGshown in of the secure container stored in the storage unit by using the public key data Kof the EMD service center read from the storage unit and after the legitimacy thereof is confirmed fetches the public key data Kfrom public key certificate data CERshown in .

Step SZ The signature processor verifies the signature data SIGand SIGshown in and of the secure container stored in the storage unit by using the related fetched public key data K.

Step SZ The price tag data generator generates the price tag data indicating the price obtained by adding the price of its own service to the price with respect to the content requested by the content provider notified from for example the content provider off line and outputs this to the secure container generator .

Step SZ The signature processor takes the hush values of the content file CF key file KF and price tag data generates signature data SIG SIG and SIGby using a secret key data Kof the service provider and outputs the result to the secure container generator .

Step SZ The secure container generator generates the secure container storing the content file CF and the signature data SIGthereof the key file KF and the signature data SIGthereof the price tag data and the signature data SIGthereof and the public key certificate data CERand the signature data SIGthereof shown in to and stores the same in the secure container database . Then the secure container generator reads the secure container in response to a request from the user home network from the secure container database and outputs the same to the user home network manager .

At this time the secure container may be a composite container storing a plurality of content files CF and a plurality of key files KF corresponding to them too. For example it is also possible to store a plurality of content files CF concerning music a video clip a lyric card liner notes and a jacket in a single secure container . It is also possible that these plurality of content files CF etc. be stored in the secure container with a directory structure.

Further when the secure container is transmitted by a digital broadcast an MHEG Multimedia and Hypermedia Information Coding Experts Group protocol is used while when it is transmitted by the Internet an XML SMIL HTML Hyper Text Markup Language protocol is used.

At this time the content file CF and the key file KF are centrally managed by the content provider and do not depend on the protocol for transmitting the secure container . Namely the content file CF and the key file KF are stored in the secure container by tunneling the MHEG and HTML protocols.

Step SZ The user home network manager supplies the secure container to the user home network off line and or on line.

When distributing the secure container to the network apparatus of the user home network on line the user home network manager encrypts the secure container by using the session key data Kin the encryptor decryptor after the mutual authentication and then distributes the same via the network to the network apparatus .

Note that when broadcasting the secure container via for example a satellite the user home network manager encrypts the secure container by using scramble key data Kor the like. Further the scramble key data Kis encrypted by using work key data K while the work key data Kis encrypted by using master key data K.

Then the user home network manager transmits the scramble key data Kand the work key data Ktogether with the secure container to the user home network via the satellite.

Further for example it stores the master key data Kin an IC card or the like and distributes the same to the user home network off line.

Further when receiving the SP use purchase log data concerning the content data C distributed by the related service provider from the user home network the user home network manager writes this into the storage unit .

The service provider refers to the SP use purchase log data when determining the service content in the future. Further the user preference filter creator analyzes the preference of the users of the SAMs to transmitting the related SP use purchase log data based on the SP use purchase log data to generate anuser preference filter data and transmits this via the user home network manager to the CA module of the user home network .

In the flow of the data relating to the communication with the EMD service center in the service provider is shown.

Note that as the prerequisite of the following processing the related party of the service provider performs processing for registration at the EMD service center off line by using for example its own ID card and bank account for the settlement processing and acquires the global unique identifier SP ID. The identifier SP ID is stored in the storage unit .

First an explanation will be made of the processing when the service provider requests the public key certificate data CERfor certifying the legitimacy of the public key data Kcorresponding to its own secret key data Kto the EMD service center by referring to .

First the service provider generates a random number by using the true random number generator to generate the secret key data K generates the public key data Kcorresponding to the related secret key data K and stores the same in the storage unit .

The identifiers SP ID and the public key data Kof the EMD service center manager and the service provider are read from the storage unit .

Then the EMD service center manager transmits the identifier SP ID and the public key data Kto the EMD service center .

Then the EMD service center manager receives as its inputs the public key certificate data CERand the signature data SIGthereof from the EMD service center in accordance with the related registration and writes the same into the storage unit .

Next an explanation will be made of the processing of the case where the service provider registers the price tag data in the EMD service center and authorizes the same by referring to .

In this case the signature processor finds the hush value of a module Modstoring the price tag data generated by the price tag data generator and the global unique identifier Content ID read from the storage unit and generates the signature data SIGby using the secret key data K.

Further it reads the public key certificate data CERand the signature data SIGthereof from the storage unit .

Then the encryptor decryptor encrypts a price tag registration request use module Modshown in by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the EMD service center then transmits it from the EMD service center manager to the EMD service center .

Note that it is also possible that the global unique identifier SP ID of the service provider be stored in the module Mod.

Further the EMD service center manager writes settlement report data received from the EMD service center into the storage unit .

Further the EMD service center manager stores marketing information data received from the EMD service center in the storage unit .

The marketing information data is used as a reference when the service provider determines the content data C to be distributed from then on.

The EMD service center plays a role as the certificate authority CA key management authority and right clearing authority as mentioned before.

As shown in the EMD service center has a key server key database a settlement processor a signature processor a settlement organization manager a certificate usage control policy manager a CER database a content provider manager a CP database a SAM manager a SAM database a mutual authenticator an encryptor decryptor a service provider manager an SP database a user preference filter creator and a marketing information data creator .

In the functional blocks given the same references as those of and have substantially the same functions as those of the functional blocks having the same references explained in the first embodiment.

Note that in the flow of the data related to the data transferred between the EMD service center and the service provider in the flow of the data among the functional blocks in the EMD service center is shown.

Further in the flow of the data related to the data transferred between the EMD service center and the content provider in the flow of the data among the functional blocks in the EMD service center is shown.

Further in the flow of the data related to the data transferred between the EMD service center and the SAMs to shown in and the settlement organization in the flow of the data among the functional blocks in the EMD service center is shown.

The settlement processor performs the settlement processing based on the usage log data input from the SAMs to and the suggested retailer price data SPR and the price tag data input from the certificate usage control policy manager as shown in . Note that at this time the settlement processor monitors the existence of dumping etc. by the service provider .

The settlement processor generates settlement report data and settlement claim data for the content provider as shown in by the settlement processing and outputs them to the content provider manager and the settlement organization manager .

Further by the settlement processing as shown in and it generates the settlement report data and settlement claim data for the service provider and outputs them to the service provider manager and the settlement organization manager .

Here the settlement claim data and are authorized data enabling claim of payment of money to the settlement organization based on the related data.

Here the usage log data is used when determining the payment of the license fee related to the secure container in the same way as the usage log data explained in the first embodiment. The usage log data for example as shown in describes the identifier Content ID of the content data C stored in the secure container the identifier CP ID of the content provider providing the content data C stored in the secure container the identifier SP ID of the service provider distributing the secure container the signal original data of the content data C the compression method of the content data C in the secure container the identifier Media ID of the storage medium storing the secure container the identifier SAM ID of the SAMs to receiving the distribution of the secure container and the USER ID of the user of the related SAMs to . Accordingly in a case where the money paid by the user of the user home network must be distributed to the license owners of for example the compression method and the storage medium other than the owners of the content provider and the service provider the EMD service center determines the sum of money to be paid to the other parties based on the distribution rate table determined in advance and generates the settlement report data and settlement claim data in accordance with the related determination.

The certificate usage control policy manager reads the public key certificate data CER public key certificate data CER public key certificate data CERto CER etc. registered and authorized in the CER database and registers and authorizes the usage control policy data and content key data Kc of the content provider and the price tag data of the service provider etc. in the CER database

At this time the certificate usage control policy manager takes the hush values of the usage control policy data content key data Kc price tag data etc. attaches the signature data using the secret key data K and thereby generates the authorized public key certificate data.

The content provider manager has the function of communicating with the content provider and can access the CP database for managing the registered identifier CP ID etc. of the content provider .

The user preference filter creator generates user preference filter data for selecting the content data C in accordance with the preference of the users of the SAMs to transmitting the related usage log data based on the usage log data and transmits the user preference filter data to the SAMs to transmitting the related usage log data via the SAM manager .

The marketing information data creator generates the marketing information data indicating the state of purchase etc. of the entire content data C distributed to the user home network by for example a plurality of service providers based on the usage log data and transmits this via the service provider manager to the service provider . The service provider determines the content of the service to be provided from then on with the marketing information data as a reference.

The transmission of the distribution key data KDto KDfrom the EMD service center to the content provider and the transmission of the distribution key data KDto KDfrom the EMD service center to the SAMs to are carried out in the same way as the case of the first embodiment.

Further the processing in the case where the EMD service center receives a request for issuance of public key certificate data from the content provider is carried out in the same way as the case of the first embodiment except for the point that the certificate usage control policy manager performs the registration with respect to the CER database.

Below an explanation will be made of the processing in the case where the EMD service center receives a request for issuance of public key certificate data from the service provider by referring to and .

Step SO When receiving a request for registration of public key certificate data containing the identifier SP ID public key data K and signature data SIGof the service provider given by the EMD service center in advance from the service provider the service provider manager decrypts them by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator shown in .

Step SO After confirming the legitimacy of the related decrypted signature data SIGat the signature processor it is confirmed whether or not the service provider issuing a request for issuance of the related public key certificate data is registered in the SP database based on the identifier SP ID and the public key data K.

Step SO The certificate usage control policy manager reads the public key certificate data CERof the related service provider from the CER database and outputs the same to the service provider manager .

Step SO The signature processor takes the hush value of the public key certificate data CER generates the signature data SIGby using the secret key data Kof the EMD service center and outputs this to the service provider manager .

Step SO The service provider manager encrypts the public key certificate data CERand the signature data SIGthereof by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator shown in and then transmits the same to the service provider .

Note that the processing where the EMD service center receives a request for issuance of public key certificate data from the SAMs to is similar to the first embodiment.

Further also the processing where the EMD service center receives the request for registration of the usage control policy data from the content provider is similar to that of the first embodiment.

Next an explanation will be made of the processing where the EMD service center receives the request for registration of the price tag data from the service provider by referring to and .

Step SP When the service provider manager receives the price tag registration request module Modshown in from the service provider it decrypts the price tag registration request module Modby using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator shown in .

Step SP The legitimacy of the signature data SIGstored in the related decrypted price tag registration request module Modis confirmed in the signature processor .

Step SP The certificate usage control policy manager registers and authorizes the price tag data stored in the price tag registration request module Modin the CER database

Next an explanation will be made of the processing where the settlement is carried out in the EMD service center by referring to and .

Step SQ When receiving as its inputs the usage log data and signature data SIGthereof from for example the SAM of the user home network the SAM manager decrypts the usage log data and the signature data SIGby using the session key data Kobtained by the mutual authentication between the mutual authenticator and the SAMs to verifies the signature data SIGby using the public key data Kof the SAM and then outputs the same to the settlement processor .

Step SQ The settlement processor performs the settlement processing based on the usage log data input from the SAM and the suggested retailer price data SRP and the price tag data input from the certificate usage control policy manager .

The settlement processor generates the settlement report data and the settlement claim data for the content provider and the settlement report data and the settlement claim data for the service provider as shown in by the settlement processing.

Note that it is also possible that the settlement processing by the settlement processor be carried out whenever the usage log data is input and for every predetermined period.

Step SQ As shown in and the settlement claim data and for the content provider and the service provider are generated and output to the settlement organization manager .

The settlement organization manager performs the mutual authentication of the settlement claim data and and the signature data generated for them by using the secret key data Kand the decryption by the session key data Kand then transmits the same to the settlement organization via the payment gateway shown in .

By this the money of the sum indicated in the settlement claim data is paid to the content provider and the money of the sum indicated in the settlement claim data is paid to the service provider .

Note that it is also possible for the EMD service center to transmit the settlement claim data and to the content provider and the service provider . In this case the content provider and the service provider claim the money to the settlement organization based on the related received settlement claim data and

Step SQ The settlement report data Sand Sfor the content provider and the service provider are output via the content provider manager and the service provider manager to the content provider and the service provider .

The EMD service center performs the processing at the time of shipping of the SAMs to and the registration processing of the SAM registration list in the same way as the EMD service center of the first embodiment other than the above.

The network apparatus includes the CA module and the SAM . Further the A V apparatuses to include the SAMs to .

Note that it is also possible that the AV apparatuses to have a network communication function or do not have a network communication function but utilize the network communication function of the network apparatus via the bus .

Further it is also possible that the user home network have only AV apparatuses not having the network function.

As shown in the network apparatus has a communication module a CA module a decryption module a SAM a decryption decompression module a purchase usage mode determination controller a download memory a reproduction module and an external memory .

In components given the same references as those of are the same as the components of the same references explained in the first embodiment.

Specifically the communication module outputs the secure container received from the service provider by a satellite broadcast or the like to the decryption module . Further the communication module outputs the user preference filter data receiving the SP use purchase log data via a telephone line or the like at the service provider to the CA module and at the same time transmits the SP use purchase log data input from the CA module to the service provider via a telephone line or the like.

As shown in the CA module has a mutual authenticator a storage unit an encryptor decryptor and an SP use purchase log data creator .

When transferring data between the CA module and the service provider via the telephone line the mutual authenticator performs the mutual authentication with the service provider to generate the session key data Kand outputs this to the encryptor decryptor .

The storage unit stores the master key data Ksupplied from the service provider off line by using an IC card etc. after for example a contract is established between the service provider and the user.

The encryptor decryptor receives as its inputs the encrypted scramble key data Kand work key data Kfrom a decryptor of the decryption module and decrypts the work key data Kby using the master key data Kread from the storage unit . Then the encryptor decryptor decrypts the scramble key data Kby using the related decrypted work key data Kand outputs the related decrypted scramble key data Kto the decryptor .

Further the encryptor decryptor decrypts the user preference filter data received by the communication module from the service provider via a telephone line or the like by using the session key data Kfrom the mutual authenticator and outputs the same to a secure container selector of the decryption module .

Further the encryptor decryptor decrypts the SP use purchase log data input from the SP use purchase log data creator by using the session key data Kfrom the mutual authenticator and transmits the same via the communication module to the service provider .

The SP use purchase log data creator generates the SP use purchase log data indicating the purchase log of the content data C inherent in the service provider based on the control signal S in accordance with the purchase operation of the content data C by the user by using the purchase usage mode determination controller shown in or the usage control status data from the SAM and outputs this to the encryptor decryptor .

The SP use purchase log data contains for example the information to be collected from the user concerning the distribution service by the service provider monthly base fee network rent contract update information and the purchase log information.

Note that the CA module communicates with a charge database a customer management database and a marketing information database of the service provider when the service provider has the charge function. In this case the CA module transmits the charge data for the distribution service of the content data to the service provider .

The decryptor receives as its inputs the encrypted secure container scramble key data K and the work key data Kfrom the communication module .

Then the decryptor outputs the encrypted scramble key data Kand work key data Kto the encryptor decryptor of the CA module and receives as its input the decrypted scramble key data Kfrom the encryptor decryptor .

Then the decryptor decrypts the encrypted secure container by using the scramble key data Kand then outputs the same to the secure container selector .

Note that when the secure container is transmitted from the service provider by the MPEG2 Transport Stream system for example the decryptor fetches the scramble key data Kfrom an ECM Entitlement Control Message in a TS packet and fetches the work key data Kfrom an EMM Entitlement Management Message .

The ECM other than the above contains for example program attribute information for every channel. Further the EMM other than this contains individual trial listening contract information different for every user auditor etc.

The secure container selector filters the secure container input from the decryptor by using the user preference filter data input from the CA module selects the secure container in accordance with the preference of the user and outputs the same to the SAM .

Note that the SAM has basically the same function and structure as the SAM of the first embodiment mentioned before by using to except it performs the processing concerning the service provider in addition to the content provider for example it performs the signature verification processing for the service provider .

Namely the SAMs to are modules for performing the charge processing in units of content and communicate with the EMD service center .

Note that in the flow of the data related to the processing of receiving as the input the secure container from the service provider and decrypting the key file KF in the secure container is shown.

As shown in the SAM has a mutual authenticator encryptor decryptors and error corrector download memory manager secure container decryptor decryption decompression module manager EMD service center manager usage monitor signature processor SAM manager storage unit media SAM manager stack memory service provider manager charge processor signature processor and external memory manager .

Note that the predetermined functions of the SAM shown in are realized by executing a secret program in the CPU in the same way as the case of the SAM .

In functional blocks given the same references as those of are the same as the functional blocks having the same references explained in the first embodiment.

Further the external memory shown in stores the usage log data and the SAM registration list after the processing explained in the first embodiment and the processing mentioned later.

Further the stack memory as shown in stores the content key data Kc usage control policy data UCP lock key data Kof the storage unit public key certificate data CERof the content provider public key certificate data CERof the service provider usage control status data UCS SAM program download containers SDCto SFDC price tag data etc.

Below an explanation will be made of the functional blocks newly given references in among the functional blocks of the SAM .

The signature processor verifies the signature data in the secure container by using the public key data Kof the EMD service center public key data Kof the content provider and the public key data Kof the service provider read from the storage unit or the stack memory .

The charge processor performs the charge processing in accordance with the purchase and or usage mode of the content by the user based on the control signal S from the purchase usage mode determination controller shown in and the price tag data read from the stack memory as shown in .

The charge processing by the charge processor is carried out based on the content of the right such as the license conditions indicated by the usage control policy data and the usage control status data under the monitoring of the usage monitor . Namely the user can purchase and use the content within the range according to the related content of the right etc.

Further the charge processor generates the usage log data in the charge processing and writes this into the external memory via the external memory manager .

Here the usage log data is used when determining the payment of the license fee related to the secure container in the EMD service center in the same way as the usage log data of the first embodiment.

Further the charge processor generates the usage control status UCS data describing the purchase and or usage mode of the content by the user based on the control signal S and writes this into the external memory via the external memory manager .

As the purchase modes of the content there are for example a straight purchase without restriction as to reproduction by the purchaser and copying for the usage of the related purchaser and a reproduction charge charging whenever it is reproduced.

Here the usage control status data is generated when the user determines the purchase mode of the content then is used for control so that the user uses the related content within the range permitted by the related determined purchase mode. The usage control status data describes the ID of the content the purchase mode the straight purchase price the SAM ID of the SAM with the purchase of the related content performed therefor USER ID of the purchasing user etc.

Note that when the determined purchase mode is the reproduction charge for example the usage control status data is transmitted from the SAM to the service provider in real time and the service provider indicates to the EMD service center to take the usage log data from the SAM .

Further when the determined purchase mode is a straight purchase for example the usage control status data is transmitted to the service provider and the EMD service center in real time.

Further the SAM outputs the user preference filter data received by the EMD service center manager from the EMD service center to the service provider manager . Then the service provider manager filters the secure container input from the decryption module shown in based on the user preference filter data selects the secure container in accordance with the preference of the user and outputs the related selected secure container to the error corrector . By this the SAM can perform the processing for selection of the content data C based on the preference of the related user obtained from the state of purchase of the content data C by the related user covering all service providers contracted with the user of the related SAM .

The flow of the processing when storing the distribution key data KDto KDreceived from the EMD service center in the storage unit is similar to that of the case of the SAM mentioned before.

Below an explanation will be made of the flow of the processing in the SAM when receiving as its input the secure container from the service provider and decrypting the key file KF in the secure container by referring to and .

Step SR The mutual authentication is carried out between the mutual authenticator and the mutual authenticator of the service provider shown in .

The encryptor decryptor decrypts the secure container shown in to received from the service provider via the service provider manager by using the session key data Kobtained by the related mutual authentication.

Step SR The signature processor verifies the signature data SIGshown in and then confirms the legitimacy of the signature data SIG SIG and SIGby using the public key dataof the service provider stored in the public key certificate data CERshown in .

When the legitimacy of the signature data SIG SIG and SIGis confirmed the service provider manager outputs the secure container to the error corrector .

The error corrector corrects the error of the secure container and then outputs the result to the download memory manager .

Step SR The download memory manager performs the mutual authentication between the mutual authenticator and the media SAM shown in and then writes the secure container into the download memory .

Step SR The download memory manager performs the mutual authentication between the mutual authenticator and the media SAM shown in and then reads the key file KF shown in stored in the secure container and outputs the same to the secure container decryptor .

Then the secure container decryptor decrypts the key file KF by using the distribution key data KDto KDof the corresponding period input from the storage unit .

Step SR The secure container decryptor outputs the signature data SIGand SIGto SIGstored in the signature certificate module Modshown in to the signature processor .

The signature processor verifies the signature data SIGshown in and then verifies the signature data SIGto SIGby using the public key data Kstored in public key certificate data CER.

Step SR The secure container decryptor writes the key file KF into the stack memory when the legitimacy of the signature data SIGto SIGis confirmed.

Below an explanation will be made of the flow of the processing until the purchase mode of the secure container downloaded from the service provider on the download memory is determined by referring to and .

Step SS The charge processor decides by the operation of the purchase usage mode determination controller shown in by the user whether or not the control signal S indicating the trial listening mode was input. Where it decides it was input it executes the processing of step SS while when it decides it was not input executes the processing of step SS.

Step SS For example the content file CF stored in the download memory is output to the decryption decompression module shown in via the decryption decompression module manager .

At this time with respect to the content file CF the mutual authentication between the mutual authenticator and the media SAM the encryption and or decryption by the session key data K the mutual authentication between the mutual authenticator and the mutual authenticator and the encryption and or decryption by the session key data Kare carried out.

Further the content key data Kc and semi disclosure parameter data read from the stack memory are output to the decryption decompression module shown in . At this time after the mutual authentication between the mutual authenticator and the mutual authenticator the encryption and decryption by the session key data Kare carried out with respect to the content key data Kc and the semi disclosure parameter data .

Next the decrypted semi disclosure parameter data is output to the semi disclosure processor and the decryption of the content data C using the content key data Kc by the decryptor is carried out by semi disclosure under the control from the semi disclosure processor .

Next the content data C decrypted by semi disclosure is decompressed at the decompression unit and then output to the electronic watermark information processor .

Next he user watermark data is buried in the content data C in the electronic watermark information processor then the content data C is reproduced at the reproduction module and the audio in accordance with the content data C is output.

Step SS When the user trying out the content determines the purchase mode by operating the purchase usage mode determination controller the control signal S indicating the related determined purchase mode is output to the charge processor .

Step SS The charge processor generates the usage log data and the usage control status data in accordance with the determined purchase mode writes the usage log data into the external memory via the external memory manager and writes the usage control status data into the stack memory .

Below the usage monitor performs control monitor so that the purchase and usage of the content are carried out within the range permitted by the usage control status data .

Step SS The usage control status data is added to the key file KF stored in the stack memory and a new key file KFshown in having the determined purchase mode is generated. The key file KFis stored in the stack memory .

As shown in the usage control status data stored in the key file KF is encrypted by utilizing the CBC mode of the DES by using the session key data K. Further the MAC value generated by using the related storage key data Kas the MAC key data that is the MAC is attached. Further the module comprised by the usage control status data and the MACis been encrypted by utilizing the CBC mode of DES by using the media key data K. Further a MAC value generated by using the related media key data Kas the MAC key data that is the MAC is attached to the related module.

Next an explanation will be made of the flow of the processing in the case where the content data C having the purchase mode already determined stored in the download memory is reproduced by referring to and .

Step ST For example in accordance with the operation by the user the designation of the content to be reproduced is received at the SAM.

Step ST Under the monitoring of the usage monitor the content file CF stored in the download memory is read based on the control signal S.

Further the content key data Kc read from the stack memory is output to the decryption decompression module .

Step ST The decryptor of the decryption decompression module decrypts the content file CF using the content key data Kc and the decompression processing by the decompression unit and reproduces the content data C at the reproduction module .

The usage log data is transmitted together with the signature data SIGgenerated by using the secret key data Kto the EMD service center via the EMD service center manager at the predetermined timing.

Below an explanation will be made of the flow of the processing in the SAM in the case of as shown in transferring for example the content file CF having the purchase mode already determined and downloaded in the download memory of the network apparatus to the SAM of the AV apparatus via the bus by referring to and .

Step SU The user operates the purchase usage mode determination controller and indicates to this to transfer the predetermined content stored in the download memory to the AP apparatus and outputs the control signal S in response to the related operation to the charge processor .

By this the charge processor updates the usage log data stored in the stack memory based on the control signal S.

Step SU The download memory manager outputs the content file CF shown in read from the download memory to the SAM manager .

Step SU The key file KFhaving the purchase mode already determined shown in read from the stack memory is output to the signature processor and the SAM manager .

Step SU The signature processor generates the signature data SIGof the key file KFand outputs this to the SAM manager .

Step SU The SAM manager reads the public key certificate data CERshown in and the signature data SIGthereof from the storage unit .

Further the mutual authenticator outputs the session key data Kobtained by performing the mutual authentication with the SAM to the encryptor decryptor .

Step SU The encryptor decryptor encrypts and generates the related secure container by using the session key data Kand outputs it to the SAM of the AV apparatus shown in .

Below an explanation will be made of the flow of the processing in the SAM when writing the content file CF etc. input from the SAM into a RAM type storage medium or the like by referring to and .

Step SV The SAM manager of the SAM receives as its inputs the content file CF shown in the key file KFand the signature data SIGthereof shown in and the public key certificate data CERand the signature data SIGthereof shown in from the SAM of the network apparatus as shown in .

Then the encryptor decryptor decrypts the content file CF the key file KFand the signature data SIGthereof the public key certificate data CERand the signature data SIGthereof received by the SAM manager as inputs by using the session key data Kobtained by the mutual authentication between the mutual authenticator and the mutual authenticator of the SAM .

Next the content file CF decrypted by using the session key data Kis output to the media SAM manager .

Further the key file KFand the signature data SIGthereof and the public key certificate data CERand the signature data SIGthereof decrypted by using the session key data Kare written into the stack memory .

Step SV The signature processor verifies the signature data SIGread from the stack memory by using the public key data Kread from the storage unit and confirms the legitimacy of the public key certificate data CER.

Then the signature processor confirms the legitimacy of the signature data SIGby using the public key data Kstored in the public key certificate data CERwhen confirming the legitimacy of the public key certificate data CER.

Step SV When the legitimacy of the signature data SIGis confirmed the key file KFshown in is read from the stack memory and output to the encryptor decryptor .

Then the encryptor decryptor sequentially encrypts the key file KFby using the storage key data K media key data K and the purchaser key data Kread from the storage unit and outputs the same to the media SAM manager .

Step SV The media SAM manager outputs the content file CF input from the SAM manager and the key file KFinput from the encryptor decryptor to the storage module shown in .

Then the storage module writes the content file CF and the key file KFinput from the media SAM manager into the RAM region of the RAM type storage media shown in .

Note that in the processing in the SAM the flow of the processing in the AV apparatus when determining the purchase mode of a ROM type storage medium having the not yet determined purchase mode of the content and the flow of the processing when reading the secure container from a ROM type storage medium having the not yet determined purchase mode in the AV apparatus and transferring this to the AV apparatus and writing the same into the RAM type storage medium are the same as the case of the SAM of the first embodiment except the point that the verification of the signature data using the secret key data of the service provider is carried out and the point that the price tag data is stored in the key file having the purchase mode determined.

Here an explanation will be made by illustrating the case where the secure container is transmitted from the service provider to the user home network on line.

Note that as the prerequisite of the following processing it is assumed that the content provider service provider and SAMs to have already been registered at the EMD service center .

Step S The EMD service center transmits the certificate CERof the public key data Kof the content provider together with its own signature data SIGto the content provider .

Further the EMD service center transmits the certificate CERof the public key data Kof the content provider together with its own signature data SIGto the service provider .

Further the EMD service center transmits six months worth of the distribution key data KDto KDeach having a term of validity of one month to the content provider and transmits three months worth of the distribution key data KDto KDto the SAMs to of the user home network .

Step S The content provider transmits the right registration request module Modshown in to the EMD service center .

Then the EMD service center registers and authorizes certifies the usage control policy data and content key data Kc after the predetermined signature verification.

Step S The content provider supplies the secure container storing the data shown in and to the service provider after the processing for preparation of the signature data and the encryption processing using the distribution key data KDto KDof the corresponding period etc.

Step S The service provider verifies the signature data SIGshown in and then verifies the signature data SIGand SIGshown in by using the public key data Kstored in the public key certificate data CERto confirm if the secure container was transmitted from a legitimate content provider .

Step S The service provider generates the price tag data and generates the secure container shown in storing the price tag data .

Step S The service provider transmits the price tag registration request module Modshown in to the EMD service center .

Then the EMD service center registers and authorizes the price tag data after the predetermined signature verification.

Step S The service provider transmits the secure container generated at step S on line or off line to the decryption module of the network apparatus shown in in response to the request from for example the CA module of the user home network .

Step S The CA module generates the SP use purchase log data and transmits this to the service provider at the predetermined timing.

Step S Each of the SAMs to after verifying the signature data SIGshown in verifies the signature data SIG SIG and SIGshown in B and C by using the public key data Kstored in the public key certificate data CERto confirm if the secure container is transmitted from a legitimate service provider .

Step S Each of the SAMs to decrypts the key file KF shown in by using the distribution key data KDto KD. Then each of the SAMs to after verifying the signature data SIGshown in verifies the signature data SIG SIG and SIGshown in by using the public key data Kstored in the public key certificate data CERto confirm if the content data C content key data Kc and usage control policy data were generated by a legitimate content provider .

Step S The user operates the purchase usage mode determination controller of to determine the purchase and or usage mode of the content.

Step S Based on the control signal S generated at step S the SAMs to generate the usage log data of the secure container .

The usage log data and the signature data SIGthereof are transmitted from the SAMs to to the EMD service center .

The EMD service center determines calculates the charge content for each of the content provider and the service provider based on the usage log data and generates the settlement claim data and based on the result thereof.

The EMD service center transmits the settlement claim data and together with its own signature data to the settlement organization via the payment gateway . By this the money paid by the user of the user home network to the settlement organization is distributed to the owners of the content provider and the service provider .

As explained above the EMD system distributes the secure container of the format shown in from the content provider to the service provider and distributes the secure container storing the content file CF and key file KF in the secure container as they are from the service provider to the user home network and performs the processing for the key file KF in the SAMs to .

Also the content key data Kc and usage control policy data stored in the key file KF are encrypted by using the distribution key data KDto KDand decrypted in only the SAMs to holding the distribution key data KDto KD. The SAMs to are modules having tamper resistance. The purchase mode and the usage mode of the content data C are determined based on the handling content of the content data C described in the usage control policy data .

Accordingly according to the EMD system the purchase and usage of the content data C in the user home network can be reliably performed based on the content of the usage control policy data generated by the related parties of the content provider regardless of the processing in the service provider . Namely according to the EMD system it is possible to prevent the usage control policy data from not being able to be managed by the service provider .

For this reason according to the EMD system even in a case where the content data C is distributed to the user home network via a plurality of service providers of different series the right clearing for the related content data C in the user home network can be performed based on the common usage control policy data generated by the content provider .

Further the EMD system enables common right clearing of the content data C in the SAMs to both on line and off line by distributing the content data C from the content provider to the user home network by using the secure container in both cases.

Further the EMD system enables use of common right clearing rules when purchasing using storing and transferring the content data C in the network apparatus and the AV apparatuses to in the user home network by performing processing always based on the usage control policy data .

Further according to the EMD system since the EMD service center has an authentication function key data management function and right clearing profit distribution function the money paid by the user accompanied with the usage of the content is reliably distributed to the owners of the content provider and the EMD service center according to the ratio determined in advance.

Further according to the EMD system the usage control policy data for the same content file CF supplied by the same content provider is supplied as it is to the SAMs to regardless of the service mode of the service provider . Accordingly the SAMs to can use the content file according to the intention of the content provider based on the usage control policy data .

Namely according to the EMD system when the service using the content and the user use the content the rights and profit of the owner of the content provider can be reliably protected by technical means without depending on an inspection organization as in the conventional case.

In components given the same references as those of are the same as the components having the same references explained in the second embodiment.

As shown in the EMD system supplies the same secure container from the content provider to the service providers and

The service provider provides the service of providing for example a drama program as content. This service generates a secure container storing the content data C related to the related drama program and price tag data uniquely generated for the related content data C and distributes this to the network apparatus .

Further the service provider provides for example a karaoke service. This service generates a secure container storing the content data C related to the related karaoke service and price tag data uniquely generated for the related content data C and distributes this to the network apparatus .

Here the formats of the secure containers and are the same as that of the secure container explained by using .

The CA modules and receive the distribution of the secure containers and from the service providers and in response to their own requests.

Next the CA modules and generate SP use purchase log data and in accordance with the distributed secure containers and and transmit them to the service providers and

Further the CA modules and decrypt the secure containers and by the session key data Kand then output the same to the SAMs to .

Next the SAMs to decrypt the key files KF in the secure containers and by using the common distribution key data KDto KD perform the processing concerning the purchase and or usage of the content in accordance with the operation from the user based on the common usage control policy data and generate the usage log data in accordance with that.

The EMD service center based on the usage log data determines calculates the charge content for each of the content provider and the service providers and and generates the settlement claim data and corresponding to them based on the results thereof.

The EMD service center transmits the settlement claim data and to the settlement organization via the payment gateway . By this the money paid by the user of the user home network to the settlement organization is distributed to the owners of the content provider and the service providers and

As mentioned above according to the EMD system when supplying the same content file CF to the service providers and the usage control policy data for the related content file CF is encrypted by the distribution key data KDto KDand supplied to the service providers and and the service providers and distribute the secure containers and storing the encrypted usage control policy data as it is to the user home network. For this reason the SAMs to in the user home network can perform right clearing based on the common usage control policy data no matter from which of the service providers or the content file CF is distributed.

Note that in the first modification the case where two service providers were used was illustrated but in the present invention any number of the service provider may be used.

In components given the same references as those of are the same as the components having the same references explained in the second embodiment.

As shown in the EMD system supplies the secure containers and from content providers and to the service provider .

The service provider provides the service by using the content supplied by for example the content providers and generates the price tag data for the secure container and the price tag data for the secure container and generates a secure container storing them.

As shown in the secure container stores the content data CFa CFb key files KFa and KFb price tag data and and signature data based on the secret key data Kof the service provider for each of them.

The secure container is received at the CA module of the network apparatus of the user home network and then processed at the SAMs to .

The SAMs to decrypt the key file KFa by using the distribution key data KDato KDa perform the processing concerning the purchase and or usage in accordance with the operation from the user for the content file CFa based on the usage control policy data and describe the log thereof in the usage log data .

Further the SAMs to decrypt the key file KFb by using distribution key data KDbto KDb perform the processing concerning the purchase and or usage in accordance with the operation from the user for the content file CFb based on the usage control policy data and describe the log thereof in the usage log data .

The EMD service center determines calculates the charge content for each of the content providers and and the service provider based on the usage log data and generates settlement claim data and corresponding to them based on the results thereof.

The EMD service center transmits the settlement claim data and via the payment gateway to the settlement organization and distributes the money paid by the user of the user home network to the settlement organization to the owners of the content providers and and the service provider by this.

As mentioned above according to the EMD system as the usage control policy data and of the content files CFa and CFb stored in the secure container those generated by the content providers and are used as they are therefore the SAMs to reliably carry out the right clearing for the content files CFa and CFb based on the usage control policy data and according to the intention of the content providers and

Note that in the second modification shown in the case where two content providers were used was illustrated but any number of the content providers may be used.

In the second embodiment the case where the EMD service center performed the settlement of the content provider and the service provider with respect to the settlement organization was illustrated but in the present invention for example as shown in it is also possible that the settlement claim data for the content provider and the settlement claim data for the service provider be generated based on the usage log data in the EMD service center and that they be transmitted to the content provider and the service provider .

In this case the content provider performs the settlement at a settlement organization via a payment gateway by using the settlement claim data . Further the service provider performs the settlement at a settlement organization via a payment gateway by using the settlement claim data

In the second embodiment the case where the service provider did not have a charging function as in for example the current Internet was illustrated but where the service provider has a charging function as in the current digital broadcasting the CA module generates a usage log data with respect to the service of the service provider concerning the secure container and transmits it to the service provider .

Then the service provider performs the charge processing based on the usage log data to generate the settlement claim data and performs the settlement at the settlement organization via the payment gateway by using this.

On the other hand the SAMs to generate usage log data with respect to the right clearing of the content provider concerning the secure container and transmit them to the EMD service center .

The EMD service center generates the settlement claim data based on the usage log data and transmits this to the content provider .

The content provider performs the settlement at the settlement organization via the payment gateway by using the settlement claim data

In the embodiment as shown in the case where the user preference filter data was generated based on the usage log data received from the SAM etc. in the user preference filter creator of the EMD service center was illustrated but it is also possible that for example the usage control status data generated at the usage monitor such as the SAM shown in be transmitted to the EMD service center in real time and that the user preference filter data be generated based on the usage control status data in the SP use purchase log data .

The content provider the service provider and the SAMs to can register their secret key data K K and Kto Kin the EMD service center too other than their public key data K K and Kto K.

By doing this it becomes possible for the EMD service center to tap communication concerned in the communication between the content provider and the service provider the communication between the service provider and the SAMs to and the communication among the SAMs to in the user home network by using the secret key data K K and Kto Kin response to demands from the nation or the police organization at the time of an emergency.

Further it is also possible that the secret key data Kto Kbe generated for the SAMs to by the EMD service center at the time of shipping and that they be stored in the SAMs to and at the same time held registered by the EMD service center .

In the above embodiment the case where public key certificate data CER CER and CERto CERwere acquired from the EMD service center in advance when the content provider service provider and SAMs to communicated with respect to each other and were transmitted to the destination of communication by the in band method was illustrated but in the present invention various modes can be employed as the mode of transmission of public key certificate data to the destination of communication.

For example it is also possible that the public key certificate data CER CER and CERto CERbe acquired from the EMD service center in advance when the content provider service provider and the SAM to communicate with respect to each other and be transmitted to the destination of communication by the in band method preceding the related communication.

Further it is also possible for the content provider the service provider and the SAM to to acquire the public key certificate data CER CERand CERto CERfrom the EMD service center at the time of communication.

Note that in components given the same references as those of are the same as the components having the same references. Further a user home network is the same as the user home network mentioned before. In a user home network SAMs to are connected via a bus that is an IEEE 1394 serial bus.

When the content provider acquires the public key certificate data CERof the service provider there are for example a case where the public key certificate data CERis transmitted from the service provider to the content provider preceding the communication in and a case where the content provider orders the public key certificate data CERfrom the EMD service center in .

Further when the service provider acquires the public key certificate data CERof the content provider there are for example a case where the public key certificate data CERis transmitted from the content provider to the service provider preceding the communication in and a case where the service provider orders the public key certificate data CERfrom the EMD service center in .

Further when the service provider acquires the public key certificate data CERto CERof the SAMs to there are for example a case where the public key certificate data CERto CERare transmitted from the SAMs to to the service provider preceding the communication in and a case where the service provider orders the public key certificate data CERto CERfrom the EMD service center in .

Further when the SAMs to acquire the public key certificate data CERof the service provider there are for example a case where the public key certificate data CERis transmitted from the service provider to the SAMs to preceding the communication in and a case where the SAMs to order the public key certificate data CERfrom the EMD service center in etc. .

Further when the SAM acquires the public key certificate data CERof the SAM there are for example a case where the public key certificate data CERis transmitted from the SAM to the SAM preceding the communication in and a case where the SAM orders the public key certificate data CERfrom the EMD service center in etc. .

Further when the SAM acquires the public key certificate data CERof the SAM there are for example a case where the public key certificate data CERis transmitted from the SAM to the SAM preceding the communication in a case where the SAM orders the public key certificate data CERfrom the EMD service center by itself and a case where the SAM orders the public key certificate data CERvia the network apparatus with the SAM mounted therein in .

Further when the SAM acquires the public key certificate data CERof the SAM there are for example a case where the public key certificate data CERis transmitted from the SAM to the SAM preceding the communication in a case where the SAM orders the public key certificate data CERfrom the EMD service center by itself in and a case where the SAM orders the public key certificate data CERvia the network apparatus in the user home network

Further when the SAM acquires the public key certificate data CERof the SAM there are for example a case where the public key certificate data CERis transmitted from the SAM to the SAM preceding the communication in a case where the SAM orders the public key certificate data CERfrom the EMD service center by itself in and a case where the SAM orders the public key certificate data CERvia the network apparatus in the user home network

In the second embodiment in order to prevent a content provider a service provider and SAMs to used for an illegal action etc. from communicating with another apparatus in the EMD service center the public key certificate revocation list for invalidating the public key certificate data of the apparatus used for the related illegal action is generated. Then the related public key certificate revocation list CRL is transmitted to the content provider service provider and SAMs to .

Note that it is also possible that the public key certificate revocation list CRL be generated in for example the content provider the service provider and the SAMs to other than the EMD service center .

First an explanation will be made of the case where the EMD service center invalidates the public key certificate data CERof the content provider .

As shown in the EMD service center transmits a public key certificate revocation list CRLindicating the invalidation of the public key certificate data CERto the service provider in . When verifying the signature data input from the content provider the service provider decides the validity of the public key certificate data CERby referring to the public key certificate revocation list CRL verifies the signature using the public key data Kwhen it decides that it is valid and invalidates the data from the content provider without verifying the signature when it decides that it is invalid. Note that it is also possible not to invalidate the data but reject the communication.

Further the EMD service center transmits the public key certificate revocation list CRLto for example the SAM in the user home network by utilizing distribution resources of the service provider by either one of the broadcast type or on demand type in . When verifying the signature data of the content provider stored in the secure container input from the service provider the SAM decides the validity of the public key certificate data CERby referring to the public key certificate revocation list CRLverifies the signature using the public key data Kwhen it decides it is valid and invalidates the related secure container without verifying the signature when it decides it is invalid.

Note that it is also possible for the EMD service center to directly transmit the public key certificate revocation list CRLto the SAM via the network apparatus in the user home network in .

Next an explanation will be made of the case where the EMD service center invalidates the public key certificate data CERof the service provider .

As shown in the EMD service center transmits a public key certificate revocation list CRLindicating the invalidation of the public key certificate data CERto the content provider in . When verifying the signature data input from the service provider the content provider decides the validity of the public key certificate data CERby referring to the public key certificate revocation list CRL verifies the signature using the public key data Kwhen it decides it is valid and invalidates the data from the service provider without verifying the related signature when it decides it is invalid.

Further the EMD service center transmits the public key certificate revocation list CRLto for example the SAM in the user home network by utilizing the distribution resources of the service provider by either the broadcast type or on demand type in . When verifying the signature data of the content provider stored in the secure container input from the service provider the SAM decides the validity of the public key certificate data CERby referring to the public key certificate revocation list CRL verifies the signature using the public key data Kwhen it decides it is valid and invalidates the related secure container without verifying the signature when it decides it is invalid.

In this case in the service provider the module for transferring the public key certificate revocation list CRLmust have tamper resistance. Further in the service provider the public key certificate revocation list CRLmust be stored in a region where tampering by related parties of the service provider is difficult.

Note that it is also possible for the EMD service center to directly transmit the public key certificate revocation list CRLto the SAM via the network apparatus in the user home network in .

Next an explanation will be made of a case where the EMD service center invalidates for example the public key certificate data CERof the SAM .

As shown in the EMD service center transmits a public key certificate revocation list CRLindicating the invalidation of the public key certificate data CERto the content provider in . The content provider transmits the public key certificate revocation list CRLto the service provider . The service provider transmits the public key certificate revocation list CRLto for example the SAM in the user home network by utilizing its own distribution resources by either the broadcast type or on demand type in . When verifying the signature data of the SAM added to the data input from the SAM the SAM decides the validity of the public key certificate data CERby referring to the public key certificate revocation list CRL verifies the signature using the public key data Kwhen it decides it is valid and invalidates the related data without verifying the signature when it decides it is invalid.

In this case in the service provider the module for transferring the public key certificate revocation list CRLmust have tamper resistance. Further in the service provider the public key certificate revocation list CRLmust be stored in a region where tampering by related parties of the service provider is difficult.

It is also possible for the EMD service center to transmit the public key certificate revocation list CRLto the SAM via the service provider in .

Note that it is also possible for the EMD service center to directly transmit the public key certificate revocation list CRLto the SAM via the network apparatus in the user home network in .

Further the EMD service center generates and stores the public key certificate revocation list CRLindicating the invalidation of for example the public key certificate data CERof the SAM .

Further the user home network generates a SAM registration list SRL of the SAMs connected to the bus and transmits this to the EMD service center in .

The EMD service center identifies the SAMs for example SAM for which invalidation is indicated by the public key certificate revocation list CRLamong the SAMs to indicated in the SAM registration list sets revocation flags corresponding to the related SAMs in the SAM registration list SRL so as to indicate the invalidity and thereby generates a new SAM registration list SRL.

Next the EMD service center transmits the related generated SAM registration list SRL to the SAM in .

The SAM determines the existence of the verification of the signature data and whether or not the communication is permitted by referring to the revocation flags of the SAM registration list SRL when communicating with another SAM.

Further the EMD service center generates the public key certificate revocation list CRLand transmits this to the content provider in .

The content provider transmits the public key certificate revocation list CRLto the service provider in .

Next the service provider transmits the public key certificate revocation list CRLto the SAM by either the broadcast type or on demand type by utilizing its own distribution resources in .

The SAM identifies the SAM for example SAM for which invalidation is indicated by the public key certificate revocation list CRLamong the SAMs to indicated in the SAM registration list generated by itself and sets revocation flags corresponding to the related SAMs in the SAM registration list SRL so as to indicate the invalidity.

After that the SAM determines the existence of the verification of the signature data and whether or not communication is permitted by referring to the revocation flags of the related SAM registration list SRL when communicating with another SAM.

Further the EMD service center generates the public key certificate revocation list CRLand transmits this to the service provider in .

Next the service provider transmits the public key certificate revocation list CRLto the SAM by either one the broadcast type or on demand type by utilizing its own distribution resources in .

The SAM specifies the SAMs for example SAM for which invalidation is indicated by the public key certificate revocation list CRLamong the SAMs to indicated in the SAM registration list generated by itself and sets revocation flags corresponding to the related SAMs in the SAM registration list SRL so as to indicate the invalidity.

After that the SAM determines the existence of the verification of the signature data and whether or not communication is permitted by referring to the revocation flags of the related SAM registration list SRL when communicating with another SAM.

In the related EMD system in the electronic settlement clearing house performs the settlement processing profit distribution processing based on the usage log data from the SAMs of the user home networks and generates the settlement claim data of the content provider and the service provider and performs settlement at the settlement organization via the payment gateway .

Further the right management clearing house generates the settlement reports of the content provider and the service provider in accordance with the settlement notification from the electronic settlement clearing house and transmits them to the content provider and the service provider .

Further it performs the registration authorization etc. of the usage control policy data and the content key data Kc of the content provider .

Note that as shown in when the right management clearing house and the electronic settlement clearing house are accommodated in a single apparatus the EMD service center shown in is formed.

Further in the present invention for example as shown in it is also possible to provide the functions of a right management clearing house in the EMD service center perform the registration etc. of the usage control policy data in the right management clearing house and at the same time generate the settlement claim data of the service provider based on the usage log data from the SAMs and transmit this to the service provider . In this case the service provider utilizes its own charge system as an electronic settlement clearing house and performs the settlement based on the settlement claim data from the right management clearing house .

Further in the present invention for example as shown in it is also possible to provide the function of a right management clearing house in the EMD service center perform the registration etc. of the usage control policy data in the right management clearing house and at the same time generate the settlement claim data of the content provider based on the usage log data from the SAM and transmit this to the content provider . In this case the content provider utilizes its own charge system as an electronic settlement clearing house and performs the settlement based on the settlement claim data from the right management clearing house .

In the second embodiment the case where the secure container of the format shown in was provided from the content provider to the service provider and the secure container of the format shown in was distributed from the service provider to the user home network in the EMD system shown in was illustrated.

Namely in the second embodiment as shown in and the case of storing a single content file CF and a single key file KF corresponding to the related content file CF in the secure container and the secure container was illustrated.

In the present invention it is also possible to store a plurality of content files CF and a plurality of key files KF corresponding to the related plurality of content files CF in the secure container and the secure container .

As shown in the secure container stores the content files CF CF and CF the key files KF KF and KF the public key certificate data CER the signature data SIG and the signature data SIG.

Here the signature data SIGis generated by the content provider taking the hush values with respect to all of the content files CF CF and CF the key files KF KF and KF the public key certificate data CER and the signature data SIGusing the secret key data Kof the content provider .

The content file CFstores a header link data LD meta data Meta content data C and an A V decompression software Soft.

Here the content data Cand the A V decompression software Softis encrypted by using the content key data Kcmentioned above while the meta data Metais encrypted by using the content key data Kcaccording to need.

Further the content data Cis compressed by for example the ATRAC3 method. The A V decompression software Softis the software for the decompression of the ATRAC3 method.

The content file CFstores the header link data LD meta data Meta content data C and an A V decompression software Softare stored.

Here the content data Cand the A V decompression software Softare encrypted by using the content key data Kcmentioned above while the meta data Metais encrypted by using the content key data Kcaccording to need.

Further the content data Cis compressed by for example the MPEG2 method. The A V decompression software Softis the software for the decompression of the MPEG2 method.

The content file CFstores a header link data LD meta data Meta content data C and an A V decompression software Soft.

Here the content data Cand the A V decompression software Softare encrypted by using the content key data Kcmentioned above while the meta data Metais encrypted by using the content key data Kcaccording to need. Further the content data Cis compressed by for example the JPEG method. The A V decompression software Softis software for the decompression of the JPEG method.

The key file KFstores a header content key data Kcencrypted by using the distribution key data KDto KD usage control policy data SAM program download container SDC and signature certificate module Mod.

Here the signature certificate module Mod as shown in stores the signature data SIG SIG and SIGgenerated by taking the hush values of the content data C content key data Kc and the usage control policy data and using the secret key data Kof the content provider the public key certificate data CERof the public key data K and the signature data SIGof the EMD service center with respect to the related public key certificate data CER.

The key file KFstores a header content key data Kcencrypted by using the distribution key data KDto KD usage control policy data SAM program download container SDC and a signature certificate module Mod.

Here the signature certificate module Mod as shown in stores the signature data SIG SIGand SIGgenerated by taking the hush values of the content data C content key data Kc and the usage control policy data and using the secret key data Kof the content provider public key certificate data CER and signature data SIGwith respect to the related public key certificate data CER.

The key file KFstores a header content key data Kcencrypted by using the distribution key data KDto KD usage control policy data a SAM program download container SDC and a signature certificate module Mod.

Here the signature certificate module Mod as shown in stores the signature data SIG SIG and SIGgenerated by taking the hush values of the content data C content key data Kc and usage control policy data and using the secret key data Kof the content provider public key certificate data CER and signature data SIGwith respect to the related public key certificate data CER.

When receiving the distribution of the secure container shown in the service provider confirms the legitimacy of the signature data SIGby using the public key data Kstored in the public key certificate data CERafter confirming the legitimacy of the related public key certificate data CERby using the public key data Kof the EMD service center .

Then when confirming the legitimacy of the signature data SIGas shown in the service provider generates the secure container storing the content files CF CF and CFand the key files KF KF and KFobtained from the secure container public key certificate data CERof the service provider signature data SIG price tag data and and a signature data SIG.

Further the signature data SIGis generated by taking the hush value with respect to all of the content files CF CF and CF key files KF KF and KF public key certificate data CER signature data SIGand the price tag data and and by using the secret key data Kof the service provider .

In the user home network the SAMs to confirm the legitimacy of the signature data SIGstored in the secure container then confirm the legitimacy of the signature data SIGby using the public key data Kstored in the public key certificate data CER.

Thereafter the SAMs to perform the right clearing for the content data C C and Cin accordance with the link statuses indicated in the links LD LD and LDbased on the key files KF KF and KF.

Note that in the eighth modification the case where the signature data SIGwith respect to all of the content files CF CF and CF key files KF KF and KF public key certificate data CER and signature data SIGwas generated in the content provider as shown in was illustrated but it is also possible to generate the signature data for each of for example the content files CF CF and CFand the key files KF KF and KFand store this in the secure container

Further in the eighth modification the case where the signature data SIGwith respect to all of the content files CF CF and CF key files KF KF and KF public key certificate data CER signature data SIG and price tag data and was generated in the service provider as shown in was illustrated but it is also possible to generate the signature data for each of them and store them in the secure container

Further in the eighth modification the case where the secure container stored a plurality of content files CF CF and CFprovided from the single service provider in the single secure container and distributed it to the user home network was illustrated but it is also possible to distribute a plurality of content files CF provided from a plurality of content providers and in the single secure container and distribute the same to the user home network as shown in .

Note that the format shown in can be similarly applied to also the case where the secure container is transmitted from the content provider to the user home network shown in in the first embodiment.

Further in the above embodiment the case where the settlement processing was carried out based on the usage log data input from the SAM in the EMD service center was illustrated but it is also possible to transmit the usage control status data from a SAM to the EMD service center whenever the purchase mode of the content is determined in the SAM and perform the settlement processing by using the received usage control status data in the EMD service center.

Below the concept of the content file CF and the key file KF etc. generated in the content provider will be summarized.

When the content provider provides content by using the Internet as shown in a content file CF containing a header content ID encrypted content data C using the content key data Kc and signature data is generated as shown in . After the usage control policy data indicating the handling of the related content data C and the content key data Kc are encrypted by the distribution key data of the predetermined reliable managers that is the EMD service centers and they are stored in the key file KF. Further the key file KF stores a header and the content ID and according to need the meta data and the signature data.

Then the content file CF and key file KF are provided directly from the content provider to the user home networks and or provided from the content provider to the user home networks and via the service provider .

Further when the content provider provides the content by using the Internet as shown in it is possible even if the content key data Kc is not stored in the key file KF but the content key data Kc encrypted by the distribution key data of the predetermined reliable managers that is the EMD service centers and are provided from the EMD service centers and to the user home networks and .

Further when the content provider provides the content by using a digital broadcast for example as shown in it provides the content data C encrypted by using the content key data Kc and the signature data from the content provider to the user home networks and directly or via the service provider . In this case the key data blocks corresponding to the key file KF shown in are provided from the content provider to the user home networks and directly or via the service provider .

Further in this case for example as shown in it is also possible to provide the content key data Kc encrypted by the distribution key data of the EMD service centers and as the predetermined reliable managers from the EMD service centers and to the user home networks and .

As explained above according to the present invention the profit of related parties of the data providing apparatus is suitably protected.

Also according to the present invention the illicit tampering with the usage control policy data etc. can be suitably avoided.

Further according to the present invention the load of the inspection for protecting the profit of the related parties of the data providing apparatus can be reduced.

