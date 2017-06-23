---

title: Intelligent physical mail handling system
abstract: A system and method for handling unwanted physical mail pieces having a sorter and imager which intercepts one or more pieces of physical mail, which produces an electronic image of a front panel of each piece of mail, and which physically retains pieces of mail in temporary physical storage, and which cooperates with an optical recognizer to determine an intended recipient for each retained piece of mail, further cooperating with a server that notifies the intended recipients and receives a choice for disposition of the mail, and including a destruction which destroys said pieces of mail rejected by the intended recipient.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08346674&OS=08346674&RS=08346674
owner: International Business Machines Corporation
number: 08346674
owner_city: Armonk
owner_country: US
publication_date: 20061030
---
This invention pertains to technologies employed to handle physical mail such as paper envelopes parcels catalogs fliers leaflets and packages.

Paper junk mail or snail mail sent out each year is rising at an alarming rate. Most of this mail is sent unsolicited such that it is unknown whether the recipients wish to receive it or not. Some schemes such as coupon methods allow the senders or sponsors of the junk mail to determine the effectiveness of the mail campaigns by tracking the number of coupons redeemed.

However it is estimated that over half of this mail is never even opened by the recipients amounting to approximately 4 million tons of wasted materials not including wasted resources such as fuel to deliver the mail and fuel to remove the discarded mail.

In a first problem with the status quo this junk mail often contains personal information such as the recipients names and addresses. Many recipients have purchased paper shredders in order to destroy unwanted mail before discarding it.

In a second problem with the status quo recycling costs are generally considered to be high for such materials.

One attempt to solve or reduce this problem is a service currently provided by the Direct Marketing Association DMA through their Mail Preference Service MPS . In this scheme consumers but not businesses can register for a nominal fee which places their name and address in a do not mail database. Members of the DMA are required by the rules of membership to delete these addressees from their mailing lists. Additionally if an unwanted piece of mail is received by a subscriber to the service the subscriber can forward it at the cost of forwarding postage plus a small handling fee to have it processed by the DMA presumably to notify the sender to remove the addressee from their mailing list. This scheme does not reduce mail from non DMA members as membership is voluntary and it is costly to the consumer. Further it is not applicable to businesses.

Therefore there is a growing need to handle unwanted physical mail more efficiently and cost effectively for consumers and businesses.

This invention provides a low cost user friendly labor saving seamless method for identifying and stopping junk mail being delivered thereby saving the postal department time and energy to delivering such high volume of junk mails and also providing the users a hassle free method to sort through this mail.

This invention makes use of a webportal where images of mail received by the user are uploaded the user then identifies the mail they would like to receive or not by identifying that mail as trash or putting it in a spam list. This portal is connected to a scanner at the postal department from where these images are received. After user selection has been made the webservice then downloads the information into a database connected to a scanner and a shredder which then act in accordance to user preference.

According to another aspect of the present invention the system learns which senders are to be blocked and can automatically disposition or dispose of future mail without requiring the addressee s interaction.

According to another aspect of the present invention the system can provide notifications of pending and held mail to the intended recipient via a number of interface processes including but not limited to an interactive web page text messages text paging electronic mail email facsimile fax and interactive television iTV .

According to another aspect of the present invention the system accumulates statistics for individuals or groups of individuals regarding their acceptance and rejection rates sorts and processes the information according to specific senders according to specific sender industries etc. and provides this statistical information to interested parties such as direct marketing companies for their use in analyzing and improving the effectiveness of their campaigns including but not limited to removing recipients from their own mailing lists who reject their mailings regularly.

According to yet another aspect of the present invention direct marketing advertisers and bulk mail generators are enabled to load mail image and data directly into the system s databases prior to actually producing or posting the physical mail pieces. The intended recipients may review the mail and reject or accept it. Accepted mail is then produced and posted thereby avoiding production and postage of unwanted mail.

According to still another aspect of the present invention mail received by a recipient at their home or office is physically discarded into a collection bin. Contents of this bin are periodically collected and returned to a processing center where it is scanned and the data is extracted regarding which sender s sent rejected mail and which recipients rejected mail. This data is then processed similarly to provide the senders with useful information about which recipients are discarding their mail so that their campaigns can be further refined.

In other aspects of the present invention businesses processes are provided which allow for reduction of costs by bulk mail producers and senders and which allow for revenue generation by operators of the invention through selling of the aggregated and processed rejection acceptance information.

The inventors of the present invention have recognized a problem unaddressed in the art regarding the inability of bulk mail producers postal agencies and mail customers to control costs minimize waste and reduce frustration by avoiding the sending delivery or both of unwanted physical e.g. real mail leaflets fliers letters catalogs and parcels. The inventors have realized that processes which depend on returning of unwanted mail especially those which incur a fee further exasperate the problem by adding cost labor and transportation resource consumption as well as increasing frustration instead of reducing it.

Turning to and overview of a system according to the invention is shown. Some components of this system may already exist in some postal handling centers such as mail sorting and scanning e.g. imaging systems but they are integrated according to the invention in a different manner from their present use.

Unsorted physical mail pieces are received by the handling center such as a post office from a bulk mail sender or direct marketing advertiser. These types of pieces of bulk mail are typically identical in size appearance and shape except that they usually have different addressees indicated on their front panel. The addressee indications are often made using adhesive labels which have been computer printed and machine applied to the pieces of mail. Some bulk mail however such as catalogs and certain advertisement fliers have computer controlled addressee information printed directly only them without the need for a label. These pieces are sometimes presorted by bundling them according to like destinations such as by ZIP Code which sometimes entitles the sender to a reduced postage rate. The pieces are received by the post office or processing center often in large tubs bins or boxes.

They are loaded into a sorter which quickly scans and images them using an imager . Addressee information is recognized using Optical Character Recognition OCR . According to the invention instead of temporarily using this OCR information for routing of the letter to bins headed for the destination post office this information is then saved in image form and preferably data form such as text in a database.

Next instead of routing the mail normally for delivery to the recipient s physical mail box mail which is addressed to subscribers of the special bulk mail blocking service Bulk Blocker is routed to temporary physical storage either at the destination post office at the origin post office or at a storage facility intermediate to the origin and destination.

A bulk blocker server then makes these images and data regarding held mail available to the intended recipient s client system such as the subscriber s web browser personal digital assistant PDA cell phone interactive television facsimile machine etc. through a network such as the Internet an intranet a telephone network a wireless network etc.

Using the client system the intended recipient reviews the images of the mail the data from the front panels or both and indicates which pieces of mail to forward and which pieces to destroy. Optionally the recipient may configure preferences and system may optionally adjust or otherwise learn recipient preferences for automatic handling or classification of held mail.

The server receives these choices from the client system and uses these choices to generate commands to cause the unwanted mail to be discarded or destroyed . To accomplish this one embodiment of the invention utilizes an imager and sorter to find the unwanted mail in the temporary physical storage and to route the found unwanted mail to a trash container or shredding system.

Turning to a general logical process according to the invention is shown for handling mail as described in conjunction with . The physical mail is received automatically sorted and automatically scanned to yield front panel images and information regarding the sender and the addressee. If the addressee is a subscriber to the bulk blocker service processing continues otherwise the mail piece is automatically routed to the recipient normally .

For mail which is to be handled by the invention the front panel image and preferably optically recognized information is stored and the subscriber is notified of pending held mail . After the subscriber has selected a disposition option for the mail such as discarding returning or forwarding the system then destroys the piece of mail or forwards it to the recipient as appropriate.

According to another aspect of the invention the subscriber of the bulk block service may be notified in one or more ways of pending held mail. Turning to several methods of such notification are illustrated including retrieving a set of preferences for the subscriber to determine which notification methods to use and then formatting the front panel images data or both to produce an appropriate notification medium or media.

In one option the subscriber may log into a web portal through the server for example and review lists and images of pending held mail using an interactive web page . In another optional embodiment the subscriber may receive a pager message Short Message Service SMS or instant messenger IM message containing a text description of the invention and optionally an image of the piece of mail or a link to an image. Such a text message may appear in one embodiment as follows 

Similarly a fax message can be sent to the subscriber s fax machine an email can be sent or a screen can be displayed on an interactive television . Other notifications such as an outbound automated telephone call to a home office or mobile telephone placed by an Interactive Voice Response IVR system may be made as well.

The subscriber s choice may be indicated back to the server using any suitable return messaging methods such as a return text message return email web page button a returned fax page a returned pager message etc. In many embodiments the choice submission method will be symmetrical with the notification method but this is not required by the invention. For example the notification can be made by one or more methods such as a pager message and an email but the choice can be received via an interactive web page. Additionally the subscriber s choice may be received relatively soon after the notification is sent or it may be received at a considerable delay from the time of the notification.

In the latter case where the subscriber s choice is not received for some lengthy amount of time the system may be optionally configured to forward stored and held mail without further approval by the subscriber. In this manner mail which has been held for a maximum allowable time can be automatically routed to the subscriber thereby reducing and managing the physical storage requirements of the service provider.

Turning to an available embodiment of the invention which provides feedback services to the senders of unwanted mail is shown. In this arrangement the server is further configured to collect choices from subscribers and to aggregate and process that acceptance data to yield information which would be useful for the senders to further refine their marketing and mailing strategies.

For example data can be aggregated by targeted subscriber to indicate a specific subscriber s likelihood of accepting unsolicited mail such as showing 

This likelihood of acceptance can be further broken down by correlating sender industry segment with acceptance and rejection rate 

The information can also be aggregated and processed by group of recipients such as by demographic groups. For example the data for recipients in a certain ZIP code or having suite or apartment numbers or having male names etc. can be combined reported. Such an example is 

This information can be formatted into human readable form such as a print out or report as machine readable format such as comma separate variable CSV text computer files or Electronic Data Interchange EDI messages or both.

The information can be sent to client systems of the bulk mailers for further processing such as updating mailing lists refining marketing messages etc.

According to another aspect of the present invention not only are costs reduced through the avoidance of producing mailing and transporting unwanted mail but the aggregated intelligence can be sold to third parties including but not limited to bulk mailers to generate revenue as shown in . In this business process embodiment of the invention the users preferences may also be combined with the acceptance reports as part of the intelligence product.

 a establishing a commercial agreement between a service provider and a recipient to provide a bulk mail blocking service 

 b establishing a commercial agreement between said service provider and a bulk mail sender to report acceptance information regarding sender s mail blocked or accepted by said recipient 

 d reporting to said sender acceptance intelligence about acceptance by said recipient of said intercepted mail.

A alternative business method according to the invention which provides group or demographic based reporting includes in at least one embodiment 

 a establishing a commercial agreement between a service provider and a group of recipients to provide a bulk mail blocking service 

 b establishing a commercial agreement between said service provider and a bulk mail sender to report acceptance information regarding sender s mail blocked or accepted by said recipients 

 d aggregating and processing information regarding acceptance of said intercepted mail by said recipients as a group and

Turning to the system and interactions of is further refined to modulate a mail production system . This system allows the bulk mail senders to provide front panel images front panel data or both directly into the front panel images database and front panel data database before the mail pieces are sent and optionally even before they are produced.

In this manner the system operates as discussed in the foregoing paragraphs to notify the subscriber of pending mail albeit virtual mail which has not be intercepted by the invention yet. The intended recipients can then accept or reject the mail in a similar fashion as they can accept or reject actual mail.

In this configuration however the acceptance reports sent to the bulk mailers who can then make decisions on whether or not to mail or even produce the pieces of mail.

If the unaddressed mail pieces have already been produced addressing and mailing of pieces to the rejecting addressees can be avoided thereby saving postage on those pieces. The mail production systems are instructed not to print labels or mail pieces addressed to the subscribers who rejected the virtual mail. In this step a first level of cost savings are realized.

Further as a mailing campaign if the overall success or acceptance rate of a particular piece of mail does not receive a predetermined level of acceptance the entire mailing campaign can be canceled. If the mail pieces have not been produced then the entire cost of postage and production can be avoided otherwise at least the cost of postage can be reduced.

In this latter example bulk mailers are enabled by the invention to test market virtual mailing campaigns without actually committing to production and mailing of the pieces. If a campaign does not meet a targeted success rate then it can be modified and re attempted e.g. virtual mail pieces images and data can be loaded into the databases and . This can be iterated until the message and format of the mailing has been optimized for success concluding with an actual production cycle of mail pieces and posting them to the addressees.

To these ends the aforementioned business processes may also be enhanced and refined to take advantage of these system provisions.

In another embodiment of the invention physical mail is delivered to the intended recipients mailboxes . The recipients then manually sort through the mail pieces discarding the pieces which they regard as junk or unwanted into a collection bin . Periodically or on demand the mail pieces are collected and transported to an imaging station where they are imaged and input into the front panel databases and further processed as previously discussed.

As an addendum to the aforementioned business processes revenue may be generated through charging a fee to the subscribers for the collection and processing of the unwanted mail in return for the removal of the mail and for the reduction of unwanted mail.

In yet another embodiment of the invention as shown in on site preprocessing of the unwanted mail may be provided through a combination scanner imaging and shredding system. In this system located at the addressee s site the recipient determines which mail is unwanted after opening and reading it or in an unopened state. The recipient then feeds this unwanted mail into a slot or bin of the preprocessor which routes the mail through a scanner to extract an image of the sender s information and the recipient s information . The piece of mail continues physically such as through gravity feed or friction feed into a shredder stage which destroys the physical mail dropping or depositing the shredded mail into a collection basket.

Simultaneously or periodically the scanner stage connects to the server or to the OCR Front Panel Images portions of the aforementioned system arrangements and transmits images of the mail which was received into the preprocessor . Transmission may be made using facsimile via a Plain Old Telephone System POTS or though a data connection such as a modem via POTS or via an Internet LAN Cable modem wireless or other data connection.

When the images are received they can be optically processed to recognize the recipient s name and address as well as the sender s name and address and then this information can be added to the front panel databases directly or included in acceptance reports to the senders.

Accordingly the aforementioned business processes may also be inclusive of revenue generation through the selling or leasing of the preprocessors through charging for the reporting service or both.

In one embodiment of the invention the functionality of the system including the previously described logical processes are performed in part or wholly by software executed by a computer such as personal computers web servers web browsers or even an appropriately capable portable computing platform such as personal digital assistant PDA web enabled wireless telephone or other type of personal information management PIM device.

Therefore it is useful to review a generalized architecture of a computing platform which may span the range of implementation from a high end web or enterprise server platform to a personal computer to a portable PDA or web enabled wireless phone.

Turning to a generalized architecture is presented including a central processing unit CPU which is typically comprised of a microprocessor associated with random access memory RAM and read only memory ROM . Often the CPU is also provided with cache memory and programmable FlashROM . The interface between the microprocessor and the various types of CPU memory is often referred to as a local bus but also may be a more generic or industry standard bus.

Many computing platforms are also provided with one or more storage drives such as hard disk drives HDD floppy disk drives compact disc drives CD CD R CD RW DVD DVD R etc. and proprietary disk and tape drives e.g. Tomega Zip and Jaz Addonics SuperDisk etc. . Additionally some storage drives may be accessible over a computer network.

Many computing platforms are provided with one or more communication interfaces according to the function intended of the computing platform. For example a personal computer is often provided with a high speed serial port RS 232 RS 422 etc. an enhanced parallel port EPP and one or more universal serial bus USB ports. The computing platform may also be provided with a local area network LAN interface such as an Ethernet card and other high speed interfaces such as the High Performance Serial Bus IEEE 1394.

Computing platforms such as wireless telephones and wireless networked PDA s may also be provided with a radio frequency RF interface with antenna as well. In some cases the computing platform may be provided with an infrared data arrangement IrDA interface too.

Computing platforms are often equipped with one or more internal expansion slots such as Industry Standard Architecture ISA Enhanced Industry Standard Architecture EISA Peripheral Component Interconnect PCI or proprietary interface slots for the addition of other hardware such as sound cards memory boards and graphics accelerators.

Additionally many units such as laptop computers and PDA s are provided with one or more external expansion slots allowing the user the ability to easily install and remove hardware expansion devices such as PCMCIA cards SmartMedia cards and various proprietary modules such as removable hard drives CD drives and floppy drives.

Often the storage drives communication interfaces internal expansion slots and external expansion slots are interconnected with the CPU via a standard or industry open bus architecture such as ISA EISA or PCI. In many cases the bus may be of a proprietary design.

A computing platform is usually provided with one or more user input devices such as a keyboard or a keypad and mouse or pointer device and or a touch screen display . In the case of a personal computer a full size keyboard is often provided along with a mouse or pointer device such as a track ball or TrackPoint . In the case of a web enabled wireless telephone a simple keypad may be provided with one or more function specific keys. In the case of a PDA a touch screen is usually provided often with handwriting recognition capabilities.

Additionally a microphone such as the microphone of a web enabled wireless telephone or the microphone of a personal computer is supplied with the computing platform. This microphone may be used for simply reporting audio and voice signals and it may also be used for entering user choices such as voice navigation of web sites or auto dialing telephone numbers using voice recognition capabilities.

Many computing platforms are also equipped with a camera device such as a still digital camera or full motion video digital camera.

One or more user output devices such as a display are also provided with most computing platforms. The display may take many forms including a Cathode Ray Tube CRT a Thin Flat Transistor TFT array or a simple set of light emitting diodes LED or liquid crystal display LCD indicators.

One or more speakers and or annunciators are often associated with computing platforms too. The speakers may be used to reproduce audio and music such as the speaker of a wireless telephone or the speakers of a personal computer. Annunciators may take the form of simple beep emitters or buzzers commonly found on certain devices such as PDAs and PIMs.

These user input and output devices may be directly interconnected to the CPU via a proprietary bus structure and or interfaces or they may be interconnected through one or more industry open buses such as ISA EISA PCI etc.

The computing platform is also provided with one or more software and firmware programs to implement the desired functionality of the computing platforms.

Turning to now more detail is given of a generalized organization of software and firmware on this range of computing platforms. One or more operating system OS native application programs may be provided on the computing platform such as word processors spreadsheets contact management utilities address book calendar email client presentation financial and bookkeeping programs.

Additionally one or more portable or device independent programs may be provided which must be interpreted by an OS native platform specific interpreter such as Java scripts and programs.

Often computing platforms are also provided with a form of web browser or micro browser which may also include one or more extensions to the browser such as browser plug ins .

The computing device is often provided with an operating system such as Microsoft Windows UNIX IBM OS 2 IBM AIX open source LINUX Apple s MAC OS or other platform specific operating systems. Smaller devices such as PDA s and wireless telephones may be equipped with other forms of operating systems such as real time operating systems RTOS or Palm Computing s PalmOS .

A set of basic input and output functions BIOS and hardware device drivers are often provided to allow the operating system and programs to interface to and control the specific hardware functions provided with the computing platform.

Additionally one or more embedded firmware programs are commonly provided with many computing platforms which are executed by onboard or embedded microprocessors as part of the peripheral device such as a micro controller or a hard drive a communication processor network interface card or sound or graphics card.

As such and describe in a general sense the various hardware components software and firmware programs of a wide variety of computing platforms including but not limited to personal computers PDAs PIMs web enabled telephones and other appliances such as WebTV units. As such we now turn our attention to disclosure of the present invention relative to the processes and methods preferably implemented as software and firmware on such a computing platform. It will be readily recognized by those skilled in the art that the following methods and processes may be alternatively realized as hardware functions in part or in whole without departing from the spirit and scope of the invention.

Alternative embodiments of the present invention include some or all of the foregoing logical processes and functions of the invention being provided by configuring software deploying software downloading software distributing software or remotely serving clients in an on demand environment.

Software Deployment Embodiment. According to one embodiment of the invention the methods and processes of the invention are distributed or deployed as a service by a service provider to a client s computing system s .

Turning to the deployment process begins by determining if there are any programs that will reside on a server or servers when the process software is executed. If this is the case then the servers that will contain the executables are identified . The process software for the server or servers is transferred directly to the servers storage via FTP or some other protocol or by copying through the use of a shared files system . The process software is then installed on the servers .

Next a determination is made on whether the process software is to be deployed by having users access the process software on a server or servers . If the users are to access the process software on servers then the server addresses that will store the process software are identified .

In step a determination is made whether the process software is to be developed by sending the process software to users via e mail. The set of users where the process software will be deployed are identified together with the addresses of the user client computers . The process software is sent via e mail to each of the user s client computers. The users then receive the e mail and then detach the process software from the e mail to a directory on their client computers . The user executes the program that installs the process software on his client computer then exits the process .

A determination is made if a proxy server is to be built to store the process software. A proxy server is a server that sits between a client application such as a Web browser and a real server. It intercepts all requests to the real server to see if it can fulfill the requests itself. If not it forwards the request to the real server. The two primary benefits of a proxy server are to improve performance and to filter requests. If a proxy server is required then the proxy server is installed . The process software is sent to the servers either via a protocol such as FTP or it is copied directly from the source files to the server files via file sharing . Another embodiment would be to send a transaction to the servers that contained the process software and have the server process the transaction then receive and copy the process software to the server s file system. Once the process software is stored at the servers the users via their client computers then access the process software on the servers and copy to their client computers file systems . Another embodiment is to have the servers automatically copy the process software to each client and then run the installation program for the process software at each client computer. The user executes the program that installs the process software on his client computer then exits the process .

Lastly a determination is made on whether the process software will be sent directly to user directories on their client computers . If so the user directories are identified . The process software is transferred directly to the user s client computer directory . This can be done in several ways such as but not limited to sharing of the file system directories and then copying from the sender s file system to the recipient user s file system or alternatively using a transfer protocol such as File Transfer Protocol FTP . The users access the directories on their client file systems in preparation for installing the process software . The user executes the program that installs the process software on his client computer then exits the process .

Software Integration Embodiment. According to another embodiment of the present invention software embodying the methods and processes disclosed herein are integrated as a service by a service provider to other software applications applets or computing systems.

Integration of the invention generally includes providing for the process software to coexist with applications operating systems and network operating systems software and then installing the process software on the clients and servers in the environment where the process software will function.

Generally speaking the first task is to identify any software on the clients and servers including the network operating system where the process software will be deployed that are required by the process software or that work in conjunction with the process software. This includes the network operating system that is software that enhances a basic operating system by adding networking features. Next the software applications and version numbers will be identified and compared to the list of software applications and version numbers that have been tested to work with the process software. Those software applications that are missing or that do not match the correct version will be upgraded with the correct version numbers. Program instructions that pass parameters from the process software to the software applications will be checked to ensure the parameter lists matches the parameter lists required by the process software. Conversely parameters passed by the software applications to the process software will be checked to ensure the parameters match the parameters required by the process software. The client and server operating systems including the network operating systems will be identified and compared to the list of operating systems version numbers and network software that have been tested to work with the process software. Those operating systems version numbers and network software that do not match the list of tested operating systems and version numbers will be upgraded on the clients and servers to the required level.

After ensuring that the software where the process software is to be deployed is at the correct version level that has been tested to work with the process software the integration is completed by installing the process software on the clients and servers.

Turning to details of the integration process according to the invention are shown. Integrating begins by determining if there are any process software programs that will execute on a server or servers . If this is not the case then integration proceeds to . If this is the case then the server addresses are identified . The servers are checked to see if they contain software that includes the operating system OS applications and network operating systems NOS together with their version numbers that have been tested with the process software . The servers are also checked to determine if there is any missing software that is required by the process software .

A determination is made if the version numbers match the version numbers of OS applications and NOS that have been tested with the process software . If all of the versions match and there is no missing required software the integration continues in .

If one or more of the version numbers do not match then the unmatched versions are updated on the server or servers with the correct versions . Additionally if there is missing required software then it is updated on the server or servers . The server integration is completed by installing the process software .

Step which follows either or determines if there are any programs of the process software that will execute on the clients. If no process software programs execute on the clients the integration proceeds to and exits. If this is not the case then the client addresses are identified .

The clients are checked to see if they contain software that includes the operating system OS applications and network operating systems NOS together with their version numbers that have been tested with the process software . The clients are also checked to determine if there is any missing software that is required by the process software .

A determination is made if the version numbers match the version numbers of OS applications and NOS that have been tested with the process software . If all of the versions match and there is no missing required software then the integration proceeds to and exits.

If one or more of the version numbers do not match then the unmatched versions are updated on the clients with the correct versions . In addition if there is missing required software then it is updated on the clients . The client integration is completed by installing the process software on the clients . The integration proceeds to and exits.

Application Programming Interface Embodiment. In another embodiment the invention may be realized as a service or functionality available to other systems and devices via an Application Programming Interface API . One such embodiment is to provide the service to a client system from a server system as a web service.

On Demand Computing Services Embodiment. According to another aspect of the present invention the processes and methods disclosed herein are provided through an on demand computing architecture to render service to a client by a service provider.

Turning to generally speaking the process software embodying the methods disclosed herein is shared simultaneously serving multiple customers in a flexible automated fashion. It is standardized requiring little customization and it is scalable providing capacity on demand in a pay as you go model.

The process software can be stored on a shared file system accessible from one or more servers. The process software is executed via transactions that contain data and server processing requests that use CPU units on the accessed server. CPU units are units of time such as minutes seconds hours on the central processor of the server. Additionally the assessed server may make requests of other servers that require CPU units. CPU units are an example that represents but one measurement of use. Other measurements of use include but are not limited to network bandwidth memory usage storage usage packet transfers complete transactions etc.

When multiple customers use the same process software application their transactions are differentiated by the parameters included in the transactions that identify the unique customer and the type of service for that customer. All of the CPU units and other measurements of use that are used for the services for each customer are recorded. When the number of transactions to any one server reaches a number that begins to effect the performance of that server other servers are accessed to increase the capacity and to share the workload. Likewise when other measurements of use such as network bandwidth memory usage storage usage etc. approach a capacity so as to effect performance additional network bandwidth memory usage storage etc. are added to share the workload.

The measurements of use used for each service and customer are sent to a collecting server that sums the measurements of use for each customer for each service that was processed anywhere in the network of servers that provide the shared execution of the process software. The summed measurements of use units are periodically multiplied by unit costs and the resulting total process software application service costs are alternatively sent to the customer and or indicated on a web site accessed by the computer which then remits payment to the service provider.

In another embodiment the service provider requests payment directly from a customer account at a banking or financial institution.

In another embodiment if the service provider is also a customer of the customer that uses the process software application the payment owed to the service provider is reconciled to the payment owed by the service provider to minimize the transfer of payments.

The server central processing unit CPU capacities in the On Demand environment are queried . The CPU requirement of the transaction is estimated then the servers available CPU capacity in the On Demand environment are compared to the transaction CPU requirement to see if there is sufficient CPU available capacity in any server to process the transaction . If there is not sufficient server CPU available capacity then additional server CPU capacity is allocated to process the transaction . If there was already sufficient available CPU capacity then the transaction is sent to a selected server .

Before executing the transaction a check is made of the remaining On Demand environment to determine if the environment has sufficient available capacity for processing the transaction. This environment capacity consists of such things as but not limited to network bandwidth processor memory storage etc. . If there is not sufficient available capacity then capacity will be added to the On Demand environment . Next the required software to process the transaction is accessed loaded into memory then the transaction is executed .

The usage measurements are recorded . The usage measurements consists of the portions of those functions in the On Demand environment that are used to process the transaction. The usage of such functions as but not limited to network bandwidth processor memory storage and CPU cycles are what is recorded. The usage measurements are summed multiplied by unit costs and then recorded as a charge to the requesting customer .

If the customer has requested that the On Demand costs be posted to a web site then they are posted . If the customer has requested that the On Demand costs be sent via e mail to a customer address then they are sent . If the customer has requested that the On Demand costs be paid directly from a customer account then payment is received directly from the customer account . The last step is to exit the On Demand process.

Grid or Parallel Processing Embodiment. According to another embodiment of the present invention multiple computers are used to simultaneously process individual audio tracks individual audio snippets or a combination of both to yield output with less delay. Such a parallel computing approach may be realized using multiple discrete systems e.g. a plurality of servers clients or both or may be realized as an internal multiprocessing task e.g. a single system with parallel processing capabilities .

VPN Deployment Embodiment. According to another aspect of the present invention the methods and processes described herein may be embodied in part or in entirety in software which can be deployed to third parties as part of a service wherein a third party VPN service is offered as a secure deployment vehicle or wherein a VPN is build on demand as required for a specific deployment.

A virtual private network VPN is any combination of technologies that can be used to secure a connection through an otherwise unsecured or untrusted network. VPNs improve security and reduce operational costs. The VPN makes use of a public network usually the Internet to connect remote sites or users together. Instead of using a dedicated real world connection such as leased line the VPN uses virtual connections routed through the Internet from the company s private network to the remote site or employee. Access to the software via a VPN can be provided as a service by specifically constructing the VPN for purposes of delivery or execution of the process software i.e. the software resides elsewhere wherein the lifetime of the VPN is limited to a given period of time or a given number of deployments based on an amount paid.

The process software may be deployed accessed and executed through either a remote access or a site to site VPN. When using the remote access VPNs the process software is deployed accessed and executed via the secure encrypted connections between a company s private network and remote users through a third party service provider. The enterprise service provider ESP sets a network access server NAS and provides the remote users with desktop client software for their computers. The telecommuters can then dial a toll free number to attach directly via a cable or DSL modem to reach the NAS and use their VPN client software to access the corporate network and to access download and execute the process software.

When using the site to site VPN the process software is deployed accessed and executed through the use of dedicated equipment and large scale encryption that are used to connect a company s multiple fixed sites over a public network such as the Internet.

The process software is transported over the VPN via tunneling which is the process of placing an entire packet within another packet and sending it over the network. The protocol of the outer packet is understood by the network and both points called tunnel interfaces where the packet enters and exits the network.

Turning to VPN deployment process starts by determining if a VPN for remote access is required . If it is not required then proceed to . If it is required then determine if the remote access VPN exits .

If a VPN does exist then the VPN deployment process proceeds to identify a third party provider that will provide the secure encrypted connections between the company s private network and the company s remote users . The company s remote users are identified . The third party provider then sets up a network access server NAS that allows the remote users to dial a toll free number or attach directly via a broadband modem to access download and install the desktop client software for the remote access VPN .

After the remote access VPN has been built or if it has been previously installed the remote users can access the process software by dialing into the NAS or attaching directly via a cable or DSL modem into the NAS . This allows entry into the corporate network where the process software is accessed . The process software is transported to the remote user s desktop over the network via tunneling. That is the process software is divided into packets and each packet including the data and protocol is placed within another packet . When the process software arrives at the remote user s desktop it is removed from the packets reconstituted and then is executed on the remote users desktop .

A determination is made to see if a VPN for site to site access is required . If it is not required then proceed to exit the process . Otherwise determine if the site to site VPN exists . If it does exist then proceed to . Otherwise install the dedicated equipment required to establish a site to site VPN . Then build the large scale encryption into the VPN .

After the site to site VPN has been built or if it had been previously established the users access the process software via the VPN . The process software is transported to the site users over the network via tunneling. That is the process software is divided into packets and each packet including the data and protocol is placed within another packet . When the process software arrives at the remote user s desktop it is removed from the packets reconstituted and is executed on the site users desktop . Proceed to exit the process .

In another embodiment of the invention logical processes according to the invention and described herein are encoded on or in one or more computer readable media. Some computer readable media are read only e.g. they must be initially programmed using a different device than that which is ultimately used to read the data from the media some are write only e.g. from the data encoders perspective they can only be encoded but not read simultaneously or read write. Still some other media are write once read many times.

Some media are relatively fixed in their mounting mechanisms while others are removable or even transmittable. All computer readable media form two types of systems when encoded with data and or computer software a when removed from a drive or reading mechanism they are memory devices which generate useful data driven outputs when stimulated with appropriate electromagnetic electronic and or optical signals and b when installed in a drive or reading device they form a data repository system accessible by a computer.

Similarly another form of computer readable media is a flexible removable floppy disk which is inserted into a drive which houses an access head. The floppy disk typically includes a flexible magnetically encodable disk which is accessible by the drive head through a window in a sliding cover .

A Compact Disk CD is usually a plastic disk which is encoded using an optical and or magneto optical process and then is read using generally an optical process. Some CD s are read only CD ROM and are mass produced prior to distribution and use by reading types of drives. Other CD s are writable e.g. CD RW CD R either once or many time. Digital Versatile Disks DVD are advanced versions of CD s which often include double sided encoding of data and even multiple layer encoding of data. Like a floppy disk a CD or DVD is a removable media.

Another common type of removable media are several types of removable circuit based e.g. solid state memory devices such as Compact Flash CF Secure Data SD Sony s MemoryStick Universal Serial Bus USB FlashDrives and Thumbdrives and others. These devices are typically plastic housings which incorporate a digital memory chip such as a battery backed random access chip RAM or a Flash Read Only Memory FlashROM . Available to the external portion of the media is one or more electronic connectors for engaging a connector such as a CF drive slot or a USB slot. Devices such as a USB FlashDrive are accessed using a serial data methodology where other devices such as the CF are accessed using a parallel methodology. These devices often offer faster access times than disk based media as well as increased reliability and decreased susceptibility to mechanical shock and vibration. Often they provide less storage capability than comparably priced disk based media.

Yet another type of computer readable media device is a memory module often referred to as a SIMM or DIMM. Similar to the CF SD and FlashDrives these modules incorporate one or more memory devices such as Dynamic RAM DRAM mounted on a circuit board having one or more electronic connectors for engaging and interfacing to another circuit such as a Personal Computer motherboard. These types of memory modules are not usually encased in an outer housing as they are intended for installation by trained technicians and are generally protected by a larger outer housing such as a Personal Computer chassis.

Turning now to another embodiment option of the present invention is shown in which a computer readable signal is encoded with software data or both which implement logical processes according to the invention. is generalized to represent the functionality of wireless wired electro optical and optical signaling systems. For example the system shown in can be realized in a manner suitable for wireless transmission over Radio Frequencies RF as well as over optical signals such as InfraRed Data Arrangement IrDA . The system of may also be realized in another manner to serve as a data transmitter data receiver or data transceiver for a USB system such as a drive to read the aforementioned USB FlashDrive or to access the serially stored data on a disk such as a CD or hard drive platter.

In general a microprocessor or microcontroller reads writes or both data to from storage for data program or both . A data interface optionally including a digital to analog converter cooperates with an optional protocol stack to send receive or transceive data between the system front end and the microprocessor . The protocol stack is adapted to the signal type being sent received or transceived. For example in a Local Area Network LAN embodiment the protocol stack may implement Transmission Control Protocol Internet Protocol TCP IP . In a computer to computer or computer to periperal embodiment the protocol stack may implement all or portions of USB FireWire RS 232 Point to Point Protocol PPP etc.

The system s front end or analog front end is adapted to the signal type being modulated demodulate or transcoded. For example in an RF based system the analog front end comprises various local oscillators modulators demodulators etc. which implement signaling formats such as Frequency Modulation FM Amplitude Modulation AM Phase Modulation PM Pulse Code Modulation PCM etc. Such an RF based embodiment typically includes an antenna for transmitting receiving or transceiving electromagnetic signals via open air water earth or via RF wave guides and coaxial cable. Some common open air transmission standards are BlueTooth Global Services for Mobile Communications GSM Time Division Multiple Access TDMA Advanced Mobile Phone Service AMPS and Wireless Fidelity Wi Fi .

In another example embodiment the analog front end may be adapted to sending receiving or transceiving signals via an optical interface such as laser based optical interfaces e.g. Wavelength Division Multiplexed SONET etc. or Infra Red Data Arrangement IrDA interfaces . Similarly the analog front end may be adapted to sending receiving or transceiving signals via cable using a cable interface which also includes embodiments such as USB Ethernet LAN twisted pair coax Plain old Telephone Service POTS etc.

Signals transmitted received or transceived as well as data encoded on disks or in memory devices may be encoded to protect it from unauthorized decoding and use. Other types of encoding may be employed to allow for error detection and in some cases correction such as by addition of parity bits or Cyclic Redundancy Codes CRC . Still other types of encoding may be employed to allow directing or routing of data to the correct destination such as packet and frame based protocols.

Parallel data can be represented as the flow of data signals aligned in time such that parallel data unit byte word d word etc. is transmitted with each bit D Dbeing on a bus or signal carrier simultaneously where the width of the data unit is n 1. In some systems Dis used to represent the least significant bit LSB and in other systems it represents the most significant bit MSB . Data is serialized by sending one bit at a time such that each data unit is sent in serial fashion one after another typically according to a protocol.

As such the parallel data stored in computer memory is often accessed by a microprocessor or Parallel to Serial Converter via a parallel bus and exchanged e.g. transmitted received or transceived via a serial bus . Received serial data is converted back into parallel data before storing it in computer memory usually. The serial bus generalized in may be a wired bus such as USB or Firewire or a wireless communications medium such as an RF or optical channel as previously discussed.

In these manners various embodiments of the invention may be realized by encoding software data or both according to the logical processes of the invention into one or more computer readable mediums thereby yielding a product of manufacture and a system which when properly read received or decoded yields useful programming instructions data or both including but not limited to the computer readable media types described in the foregoing paragraphs.

While certain examples and details of a preferred embodiment have been disclosed it will be recognized by those skilled in the are that variations in implementation such as use of different programming methodologies computing platforms and processing technologies may be adopted without departing from the spirit and scope of the present invention. Therefore the scope of the invention should be determined by the following claims.

