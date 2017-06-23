---

title: Data communications
abstract: The present invention provides methods of, computer programs for and apparatus for control and/or observation of a device with communication capabilities by a controller device with hypertext or hypermedia communication capabilities. More particularly, but not exclusively, the present invention relates to methods of, computer programs for and apparatus for control and observation of a consumer electronics device with communications capability from a mobile controller device with hypertext or hypermedia communications capability over a proximity bearer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07565210&OS=07565210&RS=07565210
owner: STMicroelectronic Srl.
number: 07565210
owner_city: Amsterdam
owner_country: NL
publication_date: 20061218
---
This application is a continuation application and claims the benefit under 35 U.S.C. 120 of application Ser. No. 10 915 956 filed on Aug. 11 2004 now abandoned which is hereby incorporated by reference herein. Application Ser. No. 10 915 956 also claimed the benefit under 35 U.S.C. 120 of application Ser. No. 10 705 260 filed on Nov. 10 2003 now abandoned which is hereby incorporated by reference herein. Application Ser. No. 10 705 260 also claimed the benefit under 35 U.S.C. 120 of application Ser. No. 10 389 705 filed on Mar. 12 2003 now abandoned which is hereby incorporated by reference herein. Application Ser. No. 10 389 705 also claimed the benefit under 35 U.S.C. 120 and 365 of PCT application No. PCT GB01 04099 filed on Sep. 13 2001 which is hereby incorporated by reference herein.

The present invention relates to methods of computer programs for and apparatus for control and or observation of a device with communication capabilities by a controller device with hypertext or hypermedia communication capabilities. More particular but not exclusively the present invention relates to methods of computer programs for and apparatus for control and observation of a consumer electronics device with communications capability from a mobile controller device with hypertext or hypermedia communications capability over a proximity bearer.

Techniques of remotely controlling consumer electronics devices such as CD players are known. Conventional remote controllers are device specific and factory programmed i.e. pre programmed in an unchangeable way to operate the particular device. Typically such remote controllers will have keypads with buttons which when pressed will instruct the device to perform a particular function. Often the remote controller will communicate with the device using Infra Red Data Association IrDA as the bearer medium and both the controller and the device will have IrDA communications hardware and software entities i.e. IrDA transmitters and or receivers and IrDA protocol stacks. Most remote controllers have a one way communication relationship with the device they control. Thus instructions are sent from the remote controller to the device but data is not sent from the device back to the remote controller.

Controllers with two way communications relationships with devices are known. For example Sony have developed remote controllers which are factory programmed for Sony devices but which have the capability of receiving status information from those devices and displaying it to a user on a display screen on the remote controller.

User programmable remote controllers are also known. For example the Philips Pronto and the Marantz RC500. Typically user programmable remote controllers are factory programmed for particular devices but may be re programmed by a user to function as remote controllers for new devices by either learning the control messages used by a device specific factory programmed remote controller i.e. by pointing the factory programmed remote controller IrDA transmitter at an IrDA receiver of the re programmable controller which learns the control messages parasitically as the user exercises the control options available on the factory programmed controller or by connecting the re programmable controller to a computing device such as a personal computer PC and downloading control programs pre configured for the new device from the Internet.

Consumer electronics devices connected to the Internet are known. For example microwave ovens are known which may be connected to the Internet using a modem and the public switched telephone network PSTN for downloading cooking settings. Also vending machines such as Coke vending machines are known which have connection to a data network and which include a server such as a finger daemon server for remote interrogation by a client device also connected to the data network. This may be used by a user of the remote client device to find out whether the Coke machine has any cans available for vending without the user needing to physically go to the machine.

One problem with the above described approach to controlling devices is that the controller is typically specific to a particular device or a set of particular devices and must be pre programmed either by the manufacturer or the user with all the capabilities of the controlled device that the user wishes to control. Another problem with the above described approaches to controlling devices is that the method of control is unreliable. For example one way remote controllers have no way of determining whether a user instruction has been properly received by the device. This is particularly the case with IrDA remote controllers which require line of sight to the device. Furthermore with two way communication between remote controller and device reliability can be even more of a problem. For example where the remote controller maintains state relating to the operational status of the device the unreliability of communicating commands to the device and the unreliability of receiving status from the device means that the state maintained in the remote controller may not be synchronised with the actual state of the device.

One problem with the above described approach to receiving status information at a controller device from a controlled device is that the controlled device must have knowledge of the capabilities of the controller device for example the display capabilities of the controller device.

According to a first aspect of the present invention there is provided a method of providing a remote data processing device with control data the control data enabling a user to control the operation of a consumer electronics device both the remote data processing device and the consumer electronics device being capable of communication using a hypermedia data communications protocol the method comprising the following steps 

a the consumer electronics device generating a hypermedia data message the hypermedia data message comprising data representing one or more menu options the menu options corresponding to one or more actions capable of being performed by the consumer electronics device in response to receiving a control message corresponding to one or more of the menu options 

b the consumer electronics device sending the hypermedia data message to the remote data processing device using the hypermedia data communications protocol.

According to a second aspect of the present invention there is provided a method of providing a remote data processing device with data representing the operational state of a consumer electronics device both the remote data processing device and the consumer electronics device being capable of communication using a hypermedia data communications protocol the method comprising the following steps 

a the consumer electronics device generating a hypermedia data message in dependence on the operational state of the consumer electronics device and

b sending the hypermedia data message to the remote data processing device using the hypermedia data communications protocol.

According to a third aspect of the present invention there is provided a method of controlling a consumer electronics device using a remote data processing device both the remote data processing device and the consumer electronics device being capable of communication using a hypermedia data communications protocol the method comprising the following steps 

a the consumer electronics device generating a hypermedia data message the hypermedia data message comprising data representing one or more menu options the menu options corresponding to one or more actions capable of being performed by the consumer electronics device in response to receiving a control message corresponding to one or more of the menu options 

b the consumer electronics device sending the hypermedia data message to the remote data processing device using the hypermedia data communications protocol 

c the remote data processing device presenting the one or more menu options to a user via a man machine interface 

e the remote data processing device generating and sending to the consumer electronics device a control message in response to the user selection 

f the consumer electronics device performing the corresponding action or actions in response to the received control message.

According to a fourth aspect of the present invention there is provided a consumer electronics device adapted to provide a remote data processing device with control data the control data enabling a user to control the operation of the consumer electronics device the consumer electronics device being capable of communication using a hypermedia data communications protocol the consumer electronics device comprising the following 

a means for generating a hypermedia data message the hypermedia data message comprising data representing one or more menu options the menu options corresponding to one or more actions capable of being performed by the consumer electronics device in response to receiving a control message corresponding to one or more of the menu options 

b means for sending the hypermedia data message to the remote data processing device using the hypermedia data communications protocol.

According to a fifth aspect of the present invention there is provided a consumer electronics device adapted to provide a remote data processing device with data representing its operational state the consumer electronics device being capable of communication using a hypermedia data communications protocol the consumer electronics device comprising the following 

b means for sending the hypermedia data message to the remote data processing device using the hypermedia data communications protocol.

According to a sixth aspect of the present invention there is provided a consumer electronics device adapted to be controlled using a remote data processing device the consumer electronics device being capable of communication using a hypermedia data communications protocol the consumer electronics device comprising the following 

a means for generating a hypermedia data message the hypermedia data message comprising data representing one or more menu options the menu options corresponding to one or more actions capable of being performed by the consumer electronics device in response to receiving a control message corresponding to one or more of the menu options 

b means for sending a hypermedia data message to the remote data processing device using the hypermedia data communications protocol 

c means for receiving a control message from the remote data processing device using the hypermedia data communications protocol 

According to a seventh aspect of the present invention there is provided a control unit for a consumer electronics device the control unit being adapted to provide a remote data processing device with control data the control data enabling a user to control the operation of the consumer electronics device the control unit comprising 

b means for generating a hypermedia data message the hypermedia data message comprising data representing one or more menu options the menu options corresponding to one or more actions capable of being performed by the consumer electronics device 

c means for sending the hypermedia data message to the remote data processing device using a hypermedia data communications protocol.

According to an eighth aspect of the present invention there is provided a control unit for a consumer electronics device the control unit being adapted to provide a remote data processing device with data representing its operational state the control unit comprising the following 

c means for sending the hypermedia data message to the remote data processing device using a hypermedia data communications protocol.

According to a ninth aspect of the present invention there is provided a control unit for a consumer electronics device the control unit comprising the following 

a means for generating a hypermedia data message the hypermedia data message comprising data representing one or more menu options the menu options corresponding to one or more actions capable of being performed by the consumer electronics device in response to receiving one or more control messages corresponding to one or more of the menu options 

b means for sending the hypermedia data message to a remote data processing device using a hypermedia data communications protocol 

d means for controlling the consumer electronics device to perform one or more actions in response to a received control message.

According to a tenth aspect of the present invention there is provided an integrated circuit for a consumer electronics device comprising 

According to an eleventh aspect of the present invention there is provided a data processing device comprising proximity bearer communications means and hypermedia transport protocol message generation means wherein the device is adapted to communicate with remote data processing devices using the hypermedia transport protocol over the proximity bearer.

According to a twelfth aspect of the present invention there is provided a method of controlling a consumer electronics device the consumer electronics device being capable of communicating using a hypermedia data communications protocol over a proximity bearer the method comprising the following steps 

b the consumer electronics device determining one or more actions to be performed by the consumer electronics device the determining being performed in dependence on the hypermedia request message 

According to a thirteenth aspect of the present invention there is provided a method of compiling a computer program into a machine code program the computer program being written in a programming language the programming language having native functions or methods for causing the interrogation of electronic input output interfaces and having native functions or methods for causing the generation of menu option descriptions for inclusion in hypermedia data messages.

According to a fourteenth aspect of the present invention there is provided a method of controlling a controlled data processing device using a controller data processing device the controlled device and controller device both being capable of communication using a hypermedia data communications protocol the method comprising the following steps 

a the controlled device sending a hypermedia data message to the controller device using the hypermedia protocol the hypermedia data message comprising one or more hyperlinks 

b the controller device presenting the hypermedia data message to a user of the controller device using a man machine interface of the controller device 

d in response to the user selection the controller device sending a hypermedia request message to the controlled device using the hypermedia protocol and

According to a fifteenth aspect of the present invention there is provided a method of controlling a controlled data processing device using a controller data processing device the controlled device being capable of communication using a data communications protocol the controller device being capable of communication using a hypermedia data communications protocol the method comprising the following steps 

a the controlled device sending a data message to a mediating data processing device using the data communications protocol the mediating device being capable of communication using both the data communications protocol and the hypermedia data communications protocol 

b in response to the data message received the mediating device sending a hypermedia data message to the controller device using the hypermedia data communications protocol the hypermedia message comprising one or more hyperlinks 

c the controller device presenting the hypermedia data message to a user of the controller device using a man machine interface of the controller device 

e in response to the user selection the controller device sending a hypermedia request message to the mediating device using the hypermedia data communications protocol 

f in response to the hypermedia request message received the mediating device sending a control data message to the controlled device using the data communications protocol and

According to a sixteenth aspect of the present invention there is provided a method of receiving status information from a consumer electronics device at a remote data processing device the consumer electronics device and remote device both being capable of communication using a hypermedia data communications protocol over a proximity bearer the method comprising the following steps 

a the consumer electronics device sending a hypermedia data message to the remote device using the hypermedia protocol over the proximity bearer the hypermedia data message comprising data representing the state of the consumer electronics device 

b the remote device receiving the hypermedia data message using the hypermedia data communications protocol over the proximity bearer and

c the remote device presenting the hypermedia data message to a user of the remote device using a man machine interface of the controller device.

According to a seventeenth aspect of the present invention there is provided a method of receiving status information from a consumer electronic device at a remote data processing device the remote data processing device being capable of communication using a hypermedia data communications protocol over a proximity bearer the consumer electronics device being capable of communication using a data communications protocol the method comprising the following steps 

a the consumer electronics device sending a data message to a mediating data processing device using the data communications protocol the mediating data processing device being capable of communication using both the data communications protocol and the hypermedia data communications protocol data message comprising data representing the state of the consumer electronics device the data message comprising data representing the state of the consumer electronics device 

b in response to the data message received the mediating device sending a hypermedia data message to the remote device using the hypermedia data communication protocol over the proximity bearer the hypermedia data message comprising data representing the state of the consumer electronics device 

c the remote device receiving the hypermedia data message using the hypermedia data communications protocol over the proximity bearer and

d the remote device presenting the hypermedia data message to a user of the remote device using a man machine interface of the controller device.

One advantage of the present invention is that it facilitates control and or observation of controlled devices without the controller device needing to have any prior knowledge or expectations of the capabilities of the controlled device save that it is capable of hypermedia communication with the controller device. Thus the controller device need not be pre programmed with device specific information either by a user or manufacturer as has been the case according to the prior art described above.

Another advantage of the present invention is that the control and or observation communication between a controller device and a controlled is reliable and any controlled device operational state maintained by the controller device will be reliably synchronised with the actual operational state of the controlled device.

Another advantage of the present invention is that the controller device need not store data enabling the control and or observation of the controlled device permanently or for as long as required by prior art systems described above.

Another advantage of the present invention is that the controller device need not store data enabling the control and or observation of the controlled device in a manner which are currently not valid due to the operational state of the controlled device as required by prior art systems described above. For example the controller device will not store data enabling the control of a controlled CD player to stop playing a CD when the CD player is not currently playing a CD.

By way of a brief overview the present invention sometimes referred to as the Hypertext or Hypermedia Control System or HCS provides a system for control and or observation of a controlled device such as a consumer electronics device by a controller such as a WAP enabled mobile phone in which the controller need not have any prior knowledge or expectations of the capabilities or even the presence of the controlled device. The controller is essentially stateless and has not been programmed either by the manufacturer or the user of the controlled device. Similarly the controlled device has no pre configured knowledge or expectations of the controller. However the controller and the controlled device are both able to communicate using a hypermedia protocol such as the Hypertext Transfer Protocol HTTP or the Wireless Transfer Protocol WTP . Typically but not necessarily the controller and the controlled device will communicate over a proximity bearer PB such as Bluetooth BT .

Thus a hypermedia control device is able to control a remote device such as a consumer electronics device using a hypertext data communications protocol over a proximity bearer. In other embodiments of the present invention the controller device is able to control the control device using the proximity bearer alone. In other embodiments of the present invention the controller device and the controlled device communicate using a link level communications bearer other than a proximity bearer. For example they may communicate using physical cabling or another data communications network such as an Internet protocol network or a public switched telephone network or a cellular network.

The combination of HCVM and DHCI are also arranged to be capable of interrogating the device controller to receive data representing the operational status of the controlled device. Using this data HCVM and DHCI are able to generate hypermedia data messages comprising data representing the operational state of the control device and sending these data messages to the controller device using the stack and bearer arrangement . Upon receipt of the hypermedia data messages using stack and bearer arrangement the controller device is able to display the hypermedia data message to a user of the controller device using the MMI . For example the controller device may display a Web page or a WAP card or deck to the user via a browser application. Thus the control device is able to present data representing the operational state of the device to a user of a remote controller device in the form of a hypermedia data message.

Furthermore the hypermedia data messages generated by the controlled device may include hyperlinks or other menu options which when presented to a user of the controller device may be selected or activated by the user thereby causing the controller device to generate a hypertext request message or other control message for sending to the control device and thereby controlling the controlled device as has been described above. These hyperlinks or menu options may represent the currently available actions that may be performed by the control device. For example if the control device is a CD player and the CD player is currently playing a CD then a hyperlink or menu option for stopping the CD player may be included in the hypermedia data message but not a hyperlink or menu option for starting the CD player to play a CD.

Thus it can be seen that the control device arrangement as shown in is able to provide a controller device with both its operational status and data enabling the controller device to control the controlled device.

The compiled code is executed by the HCVM but the HCVM does not itself have the ability to generate hypermedia data messages. This is left to the DHCI which functions as a wrapper to the HCVM and generates hypermedia data messages in response to instructions received from the HCVM. This is the case in both embodiments described with reference to and .

Once the PLC of a controlled device has sent a hypermedia data message constituting a home page of the controlled device to the controller device the user of the controller device may navigate through menu options presented on the MMI in a manner similar to navigating through a Internet Web site having first accessed the home page of the Web site. However unlike navigating through a Web site the actions of the user of the controller device may result in the control of the controlled device. Furthermore the current status of the controlled device may be presented to the user of the controller device and menu options corresponding to currently available actions that may be performed by the controlled device are dynamically presented to the user of the controller device as the user navigates controls the controlled device. Thus the controller device is being dynamically programmed to control the controlled device by the controlled device itself.

In and the screen displayed by the phone is not a displayed Web or WAP page or card although if the phone were equipped with its own PLC functioning as a proxy for remote PLCs then a Web or WAP page or card may be displayed by the local PLC. However shows a Web or WAP page or card received from the PLC of the controlled device and presents it to the user of the phone by a browser application. shows another page or card displayed by the phone. The page or card displays status information such as the fact that track is playing and menu options corresponding to actions of the control device that may be instructed by the user. shows a page or card displayed by the phone in which the user may select complex options such as the playing of a selected number of tracks of the CD. This may be achieved by using forms or applets for capturing complex user instructions before generating a hypermedia request message for sending to the controlled device.

The present invention is described in further detail in a technical report document appended hereto as Appendix A.

It is to be understood that the controller devices of the present invention are not limited to mobile phones or PDAs but may be any data processing device whether fixed or mobile which is capable of hypermedia communication whether over a radio interface or over a wired data network. It is also to be understood that the controlled devices according to the present invention may be any data processing devices capable of hypermedia communication whether over a radio interface or over a wired data network. Typically but not necessarily the controlled device will be a consumer electronics device such as a CD player refrigerator etc. Throughout this document the term hypermedia and hypertext have been used to refer to any data representation capable of comprising data object referencing other data objects such as text audio or visual data etc. It is also to be understood that while proximity bearers such as BT and IrDA have been described for providing remote communications between a controller device and a controlled device the present invention may be implemented using a data communication bearer. For example communication may take place over local area networks IP networks public switched telephone network or cellular mobile networks such as GSM.

This document describes the Hypertext Control System HCS which is a system for controlling and observing a device using a controller capable of hypertext communication.

This document describes the Hypertext Control System HCS which is a system for controlling and observing a device using a controller capable of hypertext communication. More particular but not exclusively the system relates to methods of computer programs for and apparatus for control and observation of a device from a mobile communications device via a proximity bearer.

The Wireless Application Protocol WAP is a standard for the presentation and delivery of wireless information and telephony services on mobile phones and other wireless terminals.

To date wireless terminal manufacturers representing 90 percent of the worlds market across all technologies have joined the WAP Forum .

The WAP has been developed as much as possible with the use of existing industry standards in particular Internet standards. The WAP forum also has formal liaison with International standards and specifications bodies such as 

W3C TIA ETSI etc These facts make WAP of particular interest as a vehicle for such control systems such as HCS.

The markup language used in WAE is Wireless Markup Language WML . WML is a tag based document language specified as an XML document type. Thus WML may be generated with many standard authoring tools. Dyamic WML can be generated by such standard mechanisms as CGI Perl ASP and similar. WML coding has been specially designed to make efficient use of Wireless bearers.

Bluetooth is a short range radio link intended to be a cable replacement between portable and or fixed electronic devices.

Bluetooth operates in the unlicensed ISM band at 2.4 GHz. A frequency hop transceiver is applied to combat interference and fading. The symbol rate is 1 Ms s and a slotted channel is applied with a nominal slot length of 625 micro seconds. A TDD multiplex system is used for full duplex operation. Bluetooth can support up to 3 simultaneous voice channels at 64 k bps.

The Bluetooth Link manager supports inquiry and paging procedures which allow a Bluetooth module discover which units are in its transmission range. This GIAC general inquiry mode allows the source bluetooth device to select certain device types via. a DIAC dedicated inquiry access code 

This is the transport layer of Bluetooth with provision for RS 232 serial port emulation. This protocol supports up to 60 simultaneous connections between Bluetooth Devices.

This is the Service Discovery Protocol which provides a means for applications to discover which services are available and to determine the characteristics of those available services using an existing L2CAP connection. The service discovery application does not make use of the SDP as a means of accessing services but rather as a means of informing the user of a Local Device the services that are available on the Local Device and or via Remote devices.

This is the Logical Link control and application Protocol. This provides connection oriented and connectionless services to the upper layers.

This establishes a link between the hardware and the protocol stack. and is specific to the Baseband implementation.

The system allows direct connection of IC controllers for interfaces such as LCD controllers. I O ports and as in the example in this document MMI controllers.

Each device connected to the bus has an individual address to allow any device to communicate with ay other device on the bus. Communication is done on a master slave basis however the bus is a true multi master bus with collision detection and arbitration between masters.

Serial 8 bit data transfer is supported fro 100 Kb s to 400 Kb s. The supporting interface chips have spike filtering on the data lines and the maximum number of chips that can be connected is only limited by the line maximum capacitance of 400 pF.

BlueVelvet is a complete Bluetooth system fully integrated in a single silicon chip. The chip integrates RF front end baseband ROM RAM MCU ARM7TDMI operating to up to 40 MHz and Peripherals A pure CMOS solution is used to achieve a very low cost solution. The RF CMOS8 process especially optimized for Bluetooth single chip system is used.

BlueVelvet is compliant with Bluetooth specification V1.0 for Class 2 0 dBm and for Class I 20 dBm using an external power amplifier.

This is a System which allows any device capable of Hypertext communication to control observe a Device which contains a HCS Link Controller HCS LC . The communication between the Controller and the Controlled Device is typically but not necessarily a Proximity Bearer PB . In the case of a Proximity bearer this HCS LC is simply called a Proximity Link Controller PLC .

The diagram above shows the modular system overview of the HCS. We have segmented the system into natural modules and domains relating to the Hypertext Controller HC and the Device Domain DD . The Device Domain includes the PLC Domain which performs the Hypertext Control and Access as in most use cases the PLC is situated within the consumer electronic product.

A Proximity Bearer PB may be defined as a wireless communication channel within an area of less than about 100 meters. An example of such a Bearer is Bluetooth where most communication takes place between devices within a 10 meter radius.

This is an apparatus capable of hypertext based control and or observation of a selected device over a proximity bearer. More particular but not exclusively the HC apparatus may be a mobile communications device or a personal digital assistant PDA . The HC may have a standard Proximity bearer baseband module or indeed a PLC as described in this HCS description.

This is an apparatus used for detection of devices that are operating using the same bearer or bearers that manages the proximity bearer physical link link integrity and networking over the bearer link status unique link identification connection control amongst other functions. The PLC may additionally include the HCRF and Hypertext Control Interpreter HCI .

This is a filter that directs control and observation related Hypertext Request to the Hypertext Control Interpreter.

This is a computer program that interprets Hypertext Requests using a Hypertext Control Virtual Machine that executes compiled Hypertext Control Language HIPE programs.

This is a virtual Hypertext machine used by the DHCI program to generate the correct Hypertext format and encoding in response to the HC requests. It may also have included in it the format and encoding of the command set for the Device in which the PLC resides . This allows the programmer of a HCI to issue commands in an abstract way to the Device and issue Hypertext responses independent of the Hypertext type used.

A Hypertext Protocol Stack is a protocol stack based on the ISO model that is required for a particular Hypertext Protocol to be used. For example with a WAP mobile phone the WAP Server Protocol stack is required on the PLC for WML based communication and related encoding to take place.

Note This functionality may alternately be included in a Command transcoder module if the device manufacturer wished to keep proprietary the format and encoding of the device commands allowing third party programming of the DHCI 

The HC typically a mobile communications device or a personal digital assistant PDA provides or has access to module providing the following 

Whereas it is not excluded that the HC MMI may have HCS specific commands it is not a requirement. Typically all of these requirements are fulfilled by a communications device with Hypertext enabled for communications over a detected proximity bearer. eg Mobile phone with a WAP enabled Bluetooth bearer 

This module is typically but not essentially a component of the PLC which provides the following functions 

This module has the task of recognizing the returned requests for URL based upon their header information and routing it to the DHCI to allow execution of the related Device command.

The HCRF uses a Uniform Resource Locator data string prefix up to the full length of the URL data string or coded version thereof to identify Hypertext Requests to be filtered into the Hypertext Control Interpreter. The URL will include the prefix which identifies its control observation request purpose and other parts of the URL may optionally include a data string describing the requested control or observation command . Alternatively the control and observation command data may be stored in other parts of the Hypertext Request such as HTTP Headers in HTTP protocol. Other protocols that may be used for hypertext communication are but are not limited to WSP protocol.

The Hypertext Control Language is required to include the following functionality regarding its syntax 

This module handles Hypertext Protocol Session as well as configuring the HCVM for execution of required Compiled Code necessary to perform a specific observation or control or menu display task. This module can be seen as a configuration module for the HCVM. The main required functions are 

The DHCI produces hypertext or encoded version of the hypertext in the same Hypertext syntax and human language as the Hypertext Request that was issued by the Hypertext Controller. The menu language may be specified by a Hypertext Protocol Header such and a HTTP Header in HTTP e.g. Accepts or by a Hypertext Controller Identifier specific setting stored on the PLC.

The DHCI takes the form of a program written in a language called HIPE. This program is compiled to an intermediate format which is readable by the HCVM.

In this way the different responses in the different natural languages may be pre compiled. The knowledge about hypertext encoding is considered fixed and this is part of the HCVM.

This module is a component of the PLC and is the virtual hypertext machine on which the DHCI code is run. It provides the following functions 

This module adapts its state dependant on the programming of the DHCI as the DHCI will prime the module and configure the HCVM with the following information 

The HCVM will return out of the function producing the required Hypertext as output in standard or encoded form and passing suc Hypertext content to the DHCI.

Note This functionality may alternately be included in a Command transcoder module if the device manufacturer wished to keep proprietary the format and encoding of the device commands allowing third party programming of the DHCI 

In one embodiment HIPE and CC are generating Hypertext responses that assumes that the Consumer Device bus provides only command responses. An alternative method is to allow a consumer device to create menu syntax and the PLC DHCI converts such syntax into required hypertext and hyperlinks.

The HC user selects the option on an MMI menu to enter into Hypertext over PB CED detection mode. Such a menu option may be denoted by Find Local Devices on a phone MMI menu. After detection is completed the user is presented with a list of the available devices to connect to. This list typically contains device descriptive text extracted from the PB Profile information conveyed upon detection.

Upon choosing PB Detection the HC shall commence filtered detection of PB Devices. The filtering is done by forming an internal list of all CED devices which responded to the unique PB Device Access Request URL request from the HC. The device shall respond to the HC with a PB Device Access Response. These responses are recorded and provide CED name identifiers which are presented to the user as a typical HC system menu option or Hypertext option .

The user now selects from the list the Device Access Response of the Device to be controlled. This issues a request to the Device for access. The PLC looks in the PB Hypertext Controller Device Access Register HC DAR upon reception of every Hypertext command for control or observation and since this is an initial access by the controller device there is no matching entry in the register for the controller device. If the PB is Bluetooth the Bluetooth Identifier may be used to identify the HC which is obtained by the DHCI of the PLC from the Proximity Bearer Stack of the PLC.

The non existence of a matching HCID in this register shall result in the Controller receiving a Hypertext response requesting a device specific Access Code. If correct the device shall 1 register the HCID along with its access classification in the HC DAR and 2 serve the Control and Observation Deck associated with this access code to the controller device.

In all subsequent access made by a controller device on a PLC the HCID shall be recognized as an allowed controller and shall be directly served with Hypertext containing Hyperlinks to Control and Observation functionality.

Global and user specific settings may be configured optionally after entry of the PLC Maser PIN code. The security aspects of such configuration options are covered in the Security Issues section

The Command is issued simply by making the request for a link concerning the control itself usually by making a key press on a mobile communications device or selecting and pressing an area of a touch screen. Audio and tactile input is allowed for such selection. This Command is encoded as a Hypertext Request and later identified in the PLC by the HCRF and filtered to the DHCI for interpretation.

The Hypertext Request can be any of the common fixed and mobile Internet Hypertext Protocols WAP WSP HTTP cHTML HTTP . The Hypertext Response will be of the same type as the Hypertext Request. For example if the Hypertext Request was a WAP WML request the response will be in encoded WML.

The HIPE language allows the definition of devices within the language. Devices are defined as bus devices that can be accessed over a specified bus and device identifier. Such busses include serial IC USB SCSI and others. The language can be used to construct specific functions that will send command strings and receive status strings or acknowledgements back from a identified device on a specific bus.

For example the following command from the sample program included in Appendix 1 sends a command to a CD player and waits for a response with timeout 

The output parameter is a byte stream that is relayed to the device cd. The input parameter is the byte stream that will be received back from the CD player device.

The Hypertext Response is produced by the DHCI. The DHCI configures the HCVM to output a specific type of Hypertext. The HCVM runs Compile Code that has been compile and assembled form source files that have been programmed in a special language called HIPE. The generated hypertext from the HCVM forms the basis of the DHCI Hypertext Response to the HC.

The interpretation of the requests has been programmed in the DHCI code which runs on the HCVM. The HCVM allows the DHCI code to be very compact and to support multiple Hypertext languages and have multi lingual or even user selectable human language responses. Example of a HIPE L program is described in the Language Overview

A Hypertext Encoder may need to be optionally present in system if the DHCI does not produce encoded form of Hypertext for certain Hypertext Language and Protocol combinations for example iMode and HTTP or WML and WSP. The DHCI may also generate already encoded hypertext i.e. WBXML encoded WML format is output directly from the HCVM for WML.

Note The Compiled Code CC is the binary file that is produced by compiling and assembling a source code of a program written in the HIPE Language. The CC is of a specific type as it contains device specific control and or observation command definitions for one or more devices. Furthermore the CC contains control and observation menu definitions defined in one or more human languages used for internationalization. The CC is intended to be stored in storage accessible to the Blue Velvet Chip. The HCVM the interprets the COMPILED CODE is capable of using menu definitions defined in the CC to generate the appropriate Hypertext Responses to a Hypertext Request that has been requested by from the HC and passed into the HCVM by the DHCI.

When a user using the HC attempts access to a CED several methods of user authentication and HC authorization can take place. The techniques usually involve user use level or Master PIN codes 

3. Use a Master PIN code to subscribe a HC and each time authenticate user using a user specific PIN.

4. Use a Master PIN code to subscribe a HC and each time authenticate user using a use level specific PIN.

It is intended that the device manufacturer shall set up a list of all the functionality s and data controllable or displayable by a device and the Master Code shall allow the user to attribute groupings of these functionality s to each of the 4 user classes. In this way closed controller user groups can be supported.

The PB channel should be encrypted for all security sensitive applications such as door access car access mobile commerce applications etc.

The BTi system is an implementation of the HCS system using Bluetooth as the Proximity Bearer PB and WML as the Hypertext Language. In particular the controlling device is a mobile device Phone or PDA which is capable of WAP over Bluetooth. The controlled device is a CD player with an integrated amplifier. The PLC is a Bluetooth silicon module called Blue Velvet into which the DHCI has been embedded although a less integrated solution is also possible. Thus it is possible to communicate between the Mobile device and the audio controller using WML.

As stated above the Controller is and device which is capable of performing WAP over Bluetooth. No other special requirements exist for the Controller

The BTi PLC is a specially adapted version of the STMicroelectronics Blue Velvet Chip. The Hardware changes to the Blue Velvet chip depend of the level of integration required but the minimum changes involve an increase of the present internal memory to incorporate the SW required for BTi support and the addition of internal or external protected flash for the implementation of the Access Control Security Registers.

The figure below shows the system overview. A Bluetooth enabled mobile phone is within 10 meters range of a SONY CDP 123 CD player. The Phone is also WAP enabled allowing WAP over Bluetooth bearer communication. The user wishes to use the Mobile Phone as an HC described earlier in order to control and observe the CD Player actions.

The Mobile Phone scans the Bluetooth Neighborhood. Following the Bluetooth enquiry for a number of seconds a list of available devices that are in the Bluetooth neighborhood are displayed. The user of the mobile phone then selects the desired device in the example case the user selects the SONY CDP 123 CD player device . Following this device selection a PIN code may optionally be required requesting the user for either master PIN or user PIN entry. The Security Description is described in the Security MMI Use Case section below . Alternatively and on successful PIN code entry the user specific device state dependent main menu of the device is displayed showing a stopped CD player. If the CD is playing then a state dependent menu is returned. Particular attention is draw to the generation of complex functions such as Select Track where user of the HC can easily select the desired CD tracks to listen to. Following the Selection the user can Play the Disk and only the selected Tracks will be played.

The HC will time out after a period of non use. The Bluetooth link will be terminated by the HC master . Subsequent control of the previously selected device will require initial device selection and access procedures as outlined earlier in this section.

A Master PIN code may optionally be requested. A regular user or use level pin code may optionally be requested. If the user of the HC enter an invalid code as Invalid PIN error warning may be displayed. Repeated incorrect code entry can disable use of the HC with a specific Hypertext Controller Identifier HCID for control of the selected CED device.

Note Hypertext Controller Identifier HCID may be a communications protocol identifier attributed to a Hypertext Controller such as the Bluetooth ID in Bluetooth or the MSISDN in GSM. It may also be a proximity identifier such as a vehicle registration number were the device requires proximity to the vehicle.

HIPE is a new language for interactive control using hypertext languages for user interaction. The language named HIPE L Hypertext Interactive Proximity Environment Language is intended to be used in devices capable of using proximity bearers such as Bluetooth and Wireless LAN primarily devices capable of proximity ad hoc networking . However it can be used for any kind of control through Web WAP or other Hypertext standards.

The example below shows control of basic CD player function using a IC bus controlled CD player. The program enables the user to control the player in English and Croatian dependent on jumper settings .

The HIPE language uses HTTP Protocol Header information URL request and information relayed in HPS structured information.

