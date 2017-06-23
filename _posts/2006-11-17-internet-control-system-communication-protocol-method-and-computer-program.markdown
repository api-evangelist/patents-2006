---

title: Internet control system communication protocol, method and computer program
abstract: A control system, method and computer program are provided for communicating control information in a control system. The control system includes a master controller and a plurality of devices. Each of the plurality of devices have a number of channels. Each channel has an identifying number and a plurality of channel states. The method includes at least initially directing one or more messages sent to and from each device to the master controller, sending a first type of control message from the master controller to respective devices, and sending a second type of control message and a third type of control message from the master controller to respective devices. A control message of the first type directs the respective device to place one of its channels in a specified channel state. A control message of the second type directs the respective device to set the level of a specified parameter to a certain value, and a control message of the third type comprises a character string of variable length.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07673030&OS=07673030&RS=07673030
owner: AMX LLC
number: 07673030
owner_city: Richardson
owner_country: US
publication_date: 20061117
---
The present application is a continuation of and claims priority to U.S. patent application Ser. No. 09 561 105 entitled Internet Control System and Method filed in the U.S. Patent and Trademark Office on Apr. 28 2000 now U.S. Pat. No. 7 213 061 and having a common inventor as the present document which claims priority to U.S. provisional application Ser. No. 60 131 605 filed in the U.S. Patent and Trademark Office on Apr. 29 1999. All of the above provisional and non provisional patent applications are hereby incorporated by reference.

This invention is related in general to the field of network control systems. More particularly the invention is related to an Internet control system communication protocol method and computer program.

In a fully automated environment appliances that change the various parameters of the environment can be inked to a control area network CAN and a controller. The appliances may include heating ventilation and air conditioning HVAC systems lighting systems audio visual systems telecommunications systems security systems surveillance systems and fire protection systems for example. One or more easy to use user interface such as a touch panel may be electronically linked to the control area network to accept user input and display current system status. AMX Corporation of Dallas Tex. designs and manufactures such networked appliance control systems.

In accordance with the present invention a system and method of Internet control network is provided which eliminates or substantially reduces the disadvantages associated with prior control systems.

In one aspect of the invention the boundaries between the Internet and the control area network are made transparent and the Internet becomes a device on the control area network. The Internet is controllable by user input entered on the user interface such as touch panel. The Internet is further capable of receiving commands from the master controller in the control area network.

In another aspect of the invention Internet applications such as web browsers and applications executing on web servers of information content providers become devices on the control area network. The Internet applications are capable of sending commands to and receiving commands from the control area network.

In yet another aspect of the present in invention a communication protocol is provided. The communication protocol comprises a packet protocol. The packet protocol has a protocol field for indicating the type of protocol a length of data field for listing the length in bytes of the data field a data field containing sub protocol data and a checksum for determining the integrity of the packet.

In yet another aspect of the invention a dynamic message protocol generator is provided to enable a scripting language such as VBScript or JavaScript capable of directly communicating on any TCP IP network connection.

System includes a control network portal coupled between the Internet and one or more control area networks and . Control area networks and are local area networks operating under transport protocols such as Ethernet and AXLink and PhastLink of AMX Corporation Dallas Tex. the assignee of the present invention that interconnect a variety of devices appliances and or equipment. The underlying network connectivity may be wired wireless power line carriers or any suitable transmission medium. Coupled to control area networks and are a plurality of devices appliances and or equipment including control area network user interfaces CAN UI F master controllers and Internet appliances . Some devices may be coupled to control area networks and via additional intermediate communications devices such as an RS 232 controller not shown .

Control area network user interface device is any device that is capable of receiving user input and displaying or indicating control network status. For example a touch panel a computer terminal with a monitor keyboard and pointing device and any device with similar functionalities may serve as control area network user interface . As described in detail below with the use of control area network portal of the present invention Internet applications are also capable of functioning as control area network user interface devices without the use of custom and dedicated applications on the user s end.

Master controller is generally a CPU based controller that controls the communications among user interface and Internet appliances . It is operable to receive user inputs received by user interface devices such as commands and instruct the appropriate Internet appliance to act according to the command. Master controller may also poll each device in control area network periodically to monitor its status. The system status and or the status of each device may be sent to control area network user interface devices for display.

Internet appliances are devices that can receive commands from master controller and operate or act according to the command. Internet appliances may include equipment that affect or monitor the various parameters of the premises. For example Internet appliances may include heating and air conditioning lighting video equipment audio equipment sprinklers security cameras infrared sensors smoke detectors etc. in a residential or commercial control area network. Household appliances such as a hot tub fireplace microwave oven coffee maker etc. may also be Internet appliances coupled to the network. Internet appliances may also be capable of providing a current status of its operational state to master controller such as on off temperature settings current ambient temperature light intensity settings volume settings threshold settings and predetermined alphanumeric strings reflective of operational states.

Master controller is also operable to receive user input from nodes of the Internet via control network portal . Connected to Internet are content providers and which may also function as control area network user interface devices. Content providers and are typically web servers that generate and provide static and or dynamic information and content in the form of web pages. Content provider applications executing on the web server are able to mine data stored in databases not shown . The web pages are typically developed with hypertext markup language HTML and various other scripting languages and programming environments such as Microsoft Active Server Pages ASP Common Gateway Interface CGI Internet Server Application Programming Interface ISAPI JAVA ActiveX Cold Fusion etc. that make the web pages more dynamic and interactive.

Also connected to the Internet are web browsers and that may also serve as control area network user interfaces. Web browsers and are application programs that can be used to request web pages from content providers and and decode the web pages. Web browser applications include NETSCAPE NAVIGATOR and MICROSOFT INTERNET EXPLORER for example. Typically a user executes a web browser application on her personal computer and accesses the World Wide Web via a dial up connection to an Internet service provider. The Internet or World Wide Web may also be accessed via other means such as cable modems and digital subscriber lines DSL . The user makes a request for a particular web page or particular web site by entering or specifying a uniform resource locator URL . The URL is associated with an Internet protocol IP address of the specified web site. Every computer connected to the World Wide Web and Internet has a unique IP address. This address is used to route message packets to specific computers and users. Internet protocol or IP is the message transport and communications protocol of the Internet and World Wide Web.

When the web browser requests a certain URL a connection is first established with a web server of a content provider that is addressed by the URL. A hypertext transport protocol HTTP request is then issued to the web server to download an HTML file. The web server receives the request and sends a web page file to the web browser which decodes the file to display information in specified format on the screen. Web pages with dynamic content provided by gateway interfaces such as CGI and ISAPI are executable applications that are run by the web server upon user request. The executing gateway application is able to read parameter information associated with the request and generate an output in the form of an HTML file in response to the parameter values. Another way to add dynamic and interactive content to web pages uses ASP. ASP scripts are server side executable scripts that are directly incorporated in the HTML web pages. Upon request for the page the web server executes the ASP script in response to input parameter values and generates the web page with dynamic content.

Using control network portal users may access control area networks and via web browsers and accessing web pages provided by control network portal or value added web pages provided by content providers and . For example a user who has a control area network deployed in her luxury residence to control various aspects of the home environment may use a web browser application to remotely monitor her home. She may change the temperature setting to decrease energy use for example because she will be leaving on a business trip straight from work. She may also use the surveillance cameras to visually ensure security has not been breached. She may even be able to remotely program her VCR to record certain favorite programs that will be broadcast while she is away.

An example of value added web pages provided by content providers is the provision of an interactive version of the television programming web page www.tvguide.com. A user may request this web page determine available program choices and click on a certain program. Options may be provided to enable the user to turn on the television and tune to a particular channel scheduled to broadcast the selected program or to program the VCR to record the selected program.

Another example of value added web pages provided by content providers is the provision of a secured web page that an electric company may access to slightly raise the temperature settings of the air conditioning systems of its participating customers in anticipation of high demand brown out conditions. Yet another example is a web page that a security company may use to access monitor and control the security surveillance and fire protection systems of its customers.

It may be noted that control network portal may be implemented by a single stand alone system that has sufficient memory and processing power or several separate systems with distinct functions as shown in . Web server is operable to receive requests of web pages from web browser and to respond by generating and providing the requested web pages. The information content of the web pages may be dynamically obtained by communicating with IA server which is operable to communicate with master controller via control network server to obtain status and other information. Control network server is used only if there is protocol conversion or other control issues needed to operate the control area network. It may be thought of logically that IA server is directly coupled to the network and functions as a device on the network. Commands entered at a web browser are sent to web server which relays the commands to master controller via IA server and control network server . Master controller then instructs appropriate appliances and or systems in the control network to act according to the received command.

IA server includes a CGI handler which communicates with CGI process and an ASP handler which communicates with ASP process . Handlers and are operable to provide a translation function from IP to a protocol used in the control area networks such as PhastLink or AXLink in AMX Corporation control area networks. IA server is operable to spawn a software logical or virtual device that is representative of or associated with a physical device directly connected to a control area network or a content provider coupled to the Internet. Multiple software logical devices may be connected to a single control area network or content provider if needed. Devices whether physical or logical are assigned a system identifier system ID and a unique device identification number device ID used to indicate the destination or origination of messages. One or more protocol converters may be provided to translate from the protocol used internally in IA server such as ICSP to other protocols used in the control area networks such as AxLink or PhastLink. A protocol converter is not necessary if the protocols employed in IA server and a control area network are the same.

By the use of software logical devices Internet applications such as web content providers appear to IA server no different than devices connected to a control area network. Therefore it appears that Internet applications like content providers on the web are able to directly communicate with the master controllers of the control area networks to issue commands to devices in the control area networks. Similarly Internet applications appear to be devices on the control area network that can be controlled by the master controller. The master controller is able to issue commands to the Internet applications.

Referring to which shows a flowchart of an embodiment of a process in which a command entered at a CAN user interface is delivered to a content provider on the Internet according to the present invention. A user enters data on a user interface device coupled to a control area network as shown in block . The user interface device may be a touch panel or a computer terminal with a monitor keyboard and mouse for example. The user may enter an alphanumeric string click on a button icon on the screen push a button on the touch panel or effect any other suitable input. The data entry may require the user to also submit the entered data such as pushing a Submit or Enter button as shown in block . The user interface device then forms a control system message incorporating the entered data and the sender and recipient of the message as shown in block . The master controller then sends the message onto the control area network as shown in block . The sender and recipient are specified by a unique combination of system ID and device ID. The recipient may be determined by the data entered by the user. For example the user may have pushed a button associated with updating the web page of the content provider. The content provider is previously assigned a unique combination of system ID and a device ID.

The master controller on that network receives the message and processes the message as shown in block . An output channel state associated with the submit button of the user interface device is turned ON by the master controller to indicate that the data is being sent. The ON state of the output channel of the submit button is conveyed to the user interface which may highlight the submit button or display a predetermined character string as a means of feedback to the user. In block the master controller then forwards the message to the protocol converter associated with the recipient software logical device in the IA server. The protocol converter then translates the message from the sender protocol to the recipient protocol as shown in block . Note that protocol conversion is not necessary or is null if the sender protocol is the same as the recipient protocol.

In block the translated message is then sent or otherwise conveyed to the software logical device that represents the recipient convent provider. The recipient software logical device receives the message and stores the message content in a data structure at a specific location specified by an index value such as a number which corresponds to the channel number of the recipient software logical device as shown in block . The stored message is accessible by specifying the index number. The software logical device then changes the state of an output channel of the same channel number to ON as shown in block . It may be noted that each device whether physical or logical may have one or more channels each indicative of a specific function parameter or property. Further each channel may have an input and an output channel state.

Periodically or at its discretion the recipient Internet application checks the output channel states of the software logical device associated therewith as shown in block . The Internet application recognizes that an output channel state is ON and therefore the data associated with that channel has been changed. In block the Internet application queries the software logical device for the data by specifying the index value. In response the software logical device sends the message to the Internet application as shown in block . The Internet application receives the message and uses and acts according to the data in an appropriate manner. The software logical device turns OFF the input channel state as shown in block and turns ON the output channel state of the same index value as shown in block .

The master controller recognizes a change in the input channel state of the software logical device representing the Internet application as shown in block . In response the master controller turns OFF the output channel of the user interface device which is used to notify the user that the requested action has been completed as shown in block . A change in the color or shade of the displayed button or the display of a predetermined string may be used to inform the user as shown in block . The process ends in block .

The software logical device then stores the message content in an indexed position in a data structure as shown in block . The software logical device turns ON the input channel associated with the index number as shown in block . The master controller becomes aware of the input channel state change by periodically polling the channel states as shown in block . The master controller may alternatively be triggered to query the channel states by some mechanism other than time. The master controller then requests the message content at the specified index number be sent to it as shown in block . The software logical device then sends the message content to the master controller which forwards the message content to the physical device in the control system as shown in block . The device receives the data and acts accordingly as shown in block . The master controller may also send the same data to a user interface in the control area network to update the display as shown in block . The software logical device then turns OFF the input and output channels as shown in block . The OFF states of the input and output channels notifies the Internet application which may periodically poll the software logical device to determine the input and output channel states that appropriate action has been taken in response to the entered data as shown in block . The process ends in block .

It may be noted that the use of input and output channel states to notify the recipient that data is available and the sender that an action has been completed is merely provided herein as an example. Other means may be used for this function.

Internet is coupled to an Internet appliance server . Internet appliance server is coupled to a plurality of control area networks . Each control area network has one master and a variety of control area network devices which can include touch panels audio visual equipment and the like. Control area network devices are equivalent to the Internet appliances described previously.

Web servers are computers having a processor such as an INTEL or Motorola processor and memory. Web server runs a web server program operable to provide web pages to a requesting user the requesting user typically using a web browser.

Databases are operable to store information that can be used by web servers to provide content that may be required by a control area network device . This can include information such as CD lists television listings sports data stock information or any other type of information that may be used by control access network device .

Internet is the collection of networks located across the world interconnected for user and computer communication including the part of the Internet known as the World Wide Web. While system shows web server connected to the Internet web servers can be connected to any system of wide area networks local area networks or Intranets.

Internet appliance server is a device operable to act as a gateway between devices connected to the Internet and control area network . Internet appliance server is in one embodiment operable to translate messages generated by web server to messages useable by control area network devices .

In system devices communicate with other devices on the same control area network or different control area networks . Devices also receive messages generated outside the control area network or generated by the master . All message sent by device is routed through the master on the control area network .

In operation messages in the first protocol such as Phastlink PL or ICSP developed by AMX Corporation are received by a communication line from a source such as a master controller . Message handler receives the messages. Message handler is responsible for receiving the message and sending the message to the appropriate port .

Port is a control output or input on the device that is discreetly addressable. An example of a port could be an infrared generator device. There can be multiple ports in a device. Each port would be numbered separately. Ports can communicate with the outside world through an RS 232 interface different interfaces or no interface at all.

As part of a port channels are provided. A channel is a part of port and can take on a binary value of either on or off. In one embodiment each port can have up to 65 535 channels . Channels are typically connected to relays which can be in an on or off condition. Relay is connected to a contact out which allows on or off control of whatever port is connected to. Channels are bi directional and can be input channels output channels or input output channels.

Levels are in some ways similar to channels. The main difference is that levels can take on any number of values instead of just a binary 0 or 1. Typical uses for levels include setting volume level setting light level etc.

Thus the purpose of message in this protocol is to send and receive controls for devices which are attached to control area network as well as send and receive status and routing information. For example for the device shown above a message could be sent to device which would turn on a television set a volume level for the television and then perhaps scroll some information across television screen. This could be accomplished by a message sent to device and interpreted by message handler . The message may have a command to turn the television set on and that would be sent to the channel which would then control the relay to turn the television on. To set the volume level the message command to set the level at a certain value is received at message handler . The command goes to level and then to the voltage regulator which in turn would then set the level by two pin connector . The scrolling message might then go through the port through the RS 232 port and displayed on the television connected to serial port DB 9 .

A device can be a user interface or a controlling device or both. User interfaces are things such as touch panels one way wireless handheld transmitter or custom panels. The controlling device provides the control methods for a device. For example IR generators are controlling devices that can control a VCR television or other item. Each device in the system has its own unique device number as well as port numbers and channels and levels that could be accessed.

Additionally an RS 232 driver is coupled to ICSP connection manager via a PPP driver coupled to a TCP IP stack and an IP port connection manager . ICSP connection manager is coupled to ethernet driver via TCP IP stack and IP port connection manager . RS 232 driver provides connectivity to RS 232 devices and Ethernet driver provides connectivity to devices attached to an Ethernet connection.

ICSP connection manager is coupled to ICSP message dispatcher . ICSP message dispatcher can send messages to different managers including a diagnostic manager a device manager or a configuration manager .

PL to ICSP protocol conversion converts from phastlink PL to ICSP and vice versa. In some embodiments PL to ICSP protocol conversion is operable to de multiplex incoming multiple messages into multiple messages destined for ICSP connection managers and multiple outgoing messages into a single packet for PL devices. AXlink to ICSP protocol conversion converts messages between devices that use the AXlink protocol to ICSP protocol and vice versa.

ICSP connection manager is operable to provide routing functionality. ICSP connection manager can route to local masters local devices remote masters and remote devices. Routing is accomplished by first routing a message to the appropriate system master and then to the correct device. The destination will be contained in the header of the packet as discussed below.

IP port connection manager is operable to manage all IP connections except standard Internet protocols. Standard Internet protocol provides for standard protocols such as HTTP FTP SMNP and SMTP.

ICSP message dispatcher determines the category of the message such as diagnostic message device specific messages and configuration messages and routes them to their specific message managers. These include the diagnostic manager the device manager and the configuration manager and any other managers.

Destination system field allows for the addressing of the message to reach a specific system. A system is in one embodiment a complete control area network with a single master. Thus message can be directed to one of many different control area networks. In one embodiment control system field is two bytes in size. Destination device field lists the number the device that the message is being sent. The device range can be anywhere between 0 and 65 535. Destination port field lists the specific port of the device that the message is destined for. In one embodiment the protocol supports up to 65 535 ports on the device.

Source system field is the number of a system where the message originates. Source device field lists the device that the message originated from. If the device number is 0 this indicates that the master of that control area network is the enunciator of the communication. Source port field lists the port where the message originated.

An important aspect of addressing is the sequencing of messages. There are certain messages and circumstances under which messages must be delivered in the order intended. This requires that each device be guaranteed the correct order for delivery. However while messages destined for a certain device must be delivered in the order intended out of order messages are possible when destined for different devices.

Allowed hop count field indicates how many hops can occur before the message is purged from the system. Each time a message passes through a master the allowed hop count field is decremented by one and checked to see if it reaches zero. Once the count reaches zero the master generates an error message indicating that the message has not reached the sender with an air. Message I.D. field contains the unique identification number for a message. This message I.D. is used by low level communication algorithms to correlate in the original message with its acknowledge and response.

Message command field and message data represent the actual message being sent in the packet. Each packet is decoded by reading the message field and performing the appropriate functions. Some commands are designed for communication between a device manager located in the master and other ones are intended for communication with the connection manager located in the master. TABLE A below lists exemplary messages that are valid between a device manager and the device or master. First column lists the command the second column lists the value of the command the third column lists the valid response from the device for that command and the fourth column lists the valid response for the master of that command and the fifth column lists the description of the command. For example command input channel OFF status is sent from a device to a master which sends the input channel off status to the master. The value of the command sent in the command value of the command field is 0x0085. Because the device is sending the message there is no response for the device. The master response is 0x0001 which is the command for acknowledge and the description of the command indicates that the input channel is in the off status. Thus this command would be sent by a device after being queried by the master to say that its input channel is in the off status or it can be sent unsolicited. The master would then send back an acknowledgment.

The Value field from TABLE A is placed in the MC MessageCommand field of the packet. Any Message Data required is placed in the variable length MD MessageData field.

This message is generated by the master or device to confirm receipt of a message sent. The MessageID field must match the original message s MessageID and the Response bit should be set.

This message is generated by the master when the destination system device for the message does not exist. This message indicates that a previous message was not routable by the master. The MessageID field must match the original message s MessageID and the Response bit should be set.

The Input Channel ON message is generated when a button is PUSHed or Input channel is turned ON from a device port or a master.

The Input Channel OFF message is generated when a button is RELEASEd or Input channel is turned OFF from a device port or a master.

The Output Channel ON Status message is generated when an Output channel is turned ON from a device port. Note that when the master turns a channel ON it assumes the channel is ON. Therefore the device should not send this message in response to the channel being turned ON by the master.

The Output Channel OFF Status message is generated when an Output channel is turned OFF from a device port. Note that when the master turns a channel OFF it assumes the channel is OFF. Therefore the device should not send this message in response to the channel being turned OFF by the master.

The Input Output Channel ON Status message is generated when an Input Output channel is turned ON from a device port.

The Input Output Channel OFF Status message is generated when an Input Output channel is turned OFF from a device port.

The Feedback Channel ON message is generated for diagnostic purposes only. See the Diagnostic Manager specification for more information.

The Feedback Channel OFF message is generated for diagnostic purposes only. See the Diagnostic Manager specification for more information.

The Value Type Specifier field specifies how the following data MD . . . is interpreted. The table below indicates the values of MD as they correlate to data types.

The LevelType command is used to query a device to determine the dynamic range supported by the device. This information is then used to generate messages appropriate to the device.

The String message is generated by the master to communicate a String. The format of a String is similar to a C Language string however the semantics are different. A String in a control system context is used to generate a control message. This control message could cause a laser disc player to begin playing a disc display a message to the user of the system or any number of any other uses. The string will be converted as necessary to any format that the device supports as determined by the StringSize message.

The Command message is generated by the master to communicate a command string. The format of a Command is similar to a C Language string however the semantics are different. A Command in a control system context is used to generate a control message. This control message is generally intended to command the controlling device not the controlled device. For example a command to an RS232 port might enable XON XOFF flow control. This command affected the controlling device but not the controlled device.

The Request Output Channel Status message is generated by the master to request the status of a single Output Channel or status of all Output Channels.

This message requests from the destination device the number of ports supported by the device. The initial assumption that the master makes is that each device in the system has one port. If the device does not respond the master assumes that it has one port.

This message is the response from a master to the Request Port Count message above. It is sent by a device upon reporting if the device has more than one port.

This message requests from the destination device the number of output channel supported by the specified device port. The initial assumption that the master makes is that each device port in the system has 256 channels.

This message is the response from a master to the Request Output Channel Count message above. It is sent by a device port upon reporting if the device has more than 256 channels.

This message requests from the destination device the number of levels supported by the specified device port. The initial assumption that the master makes is that each device port in the system has eight levels.

This message is the response from a master to the Request Level Count message above. It is sent by a device port upon reporting if the device has more than eight levels.

This message requests the number of elements per string and the string types supported by the device port. The initial assumption that the master makes is that each device port in the system supports 64 elements string and only supports 8 bit character strings.

This message is the response from a master to the Request String Size message above. It is sent by a device port upon reporting if the device port supports more than 64 byte strings or more than 8 bit character strings. It returns the maximum number of elements string the device supports and the types of strings supported.

Note that when transferring messages the size of the message will be determined by the smaller of the maximum string size supported by the device and maximum packet size supported by the low level bus protocol.

This message requests the number of elements per command and the string types supported by the device port. The initial assumption that the master makes is that each device port in the system supports 64 elements command and only supports 8 bit character arrays.

This message is the response from a device to the Request Command Size message above. It is sent by a device port upon reporting if the device port supports more than 64 byte commands or more than 8 bit character commands. It returns the maximum number of elements command the device supports and the types of strings supported.

Note that when transferring messages the size of the message will be determined by the smaller of the maximum command size supported by the device and maximum packet size supported by the low level bus protocol.

This message requests a list of data types supported for the specified level. The initial assumption that the master makes is that each device port level only supports 8 bit unsigned values BYTE Type 0x10 .

This message is the response from a master to the Request Level Size message above. It is sent by a device port upon reporting if the device port level supports more BYTE Type 0x10 levels. It returns a list of data types supported by Level.

Note that when transferring levels the master will typecast from larger sized types to the largest type supported by the device. For example if the users Axcessprogram sends a FLOAT to a device that supports only BYTE CHAR and INTEGER types the master typecasts the FLOAT to an INTEGER before sending to the device.

This message is the response from a master to the Request Status Code message above. It is sent by a device port if the device port needs to update the master of a status change.

For each device and sub device that contains re programmable electronic components within the device the following information is replied 

ObjectID An 8 bit unique within the device identifier that identifies this structure of information. This is used to construct an internal device hierarchy for display to the user.

Version A NULL terminated text string that indicates the revision level of the re programmable component.

Manufacturer String A NULL terminated text string that indicates the name of the device manufacturer.

Extended Address Format An 8 bit value that indicates the type of device specific addressing information to follow.

Extended Address Length An 8 bit value that indicates the length of device specific addressing information to follow.

This message indicates that all data Device Info messages have been sent as a result of a Request Device Info message. This message indicates to the requesting device that all Device Info information has been provided.

This message requests that the master respond with its status. Generally Master Status message will be unsolicited this message is included for completeness.

This message is the response to the Request Master Status message above but more commonly will be sent by the master unsolicited.

The Diagnostic Messages will be better specified during after the Diagnostic Manager specification is complete.

This message is used by the IDE to request that diagnostic information be sent to the requesting device. If any flag bits are set unsolicited diagnostic messages of the specified type s will be sent to the device. If all bits are zero then no diagnostic message will be sent to the device.

This message is used by the IDE to request a list of online devices for the receiving NetLinx master. The master will respond with Device Info message s for each device currently online. In addition it will generate a Port Count message for each device.

This message indicates that all requested devices from the Request Devices Online message have been sent. This message is used by the IDE to determine when all online device information has been received.

This message is used by the IDE to request the status of the specified device. The master responds with Output ON messages for each output channel that is on Feedback ON messages for each feedback channel that is on etc. See the Diagnostic Manager specification for more information.

This message indicates that all of the Request Device Status information has been sent. This message is used by the IDE to determine when all device status information has been received.

This message is used by the IDE to request the current asynchronous notification list from the master. The master generates a series of Asynchronous Notification List messages one for each entry in the list to the requesting device.

This message is generated by the master in response to the Request Asynchronous Notification List message. For each entry in the master s list one of these messages will be generated. If there are no entries then the number of entries field will be zero. See the Diagnostic Manager specification for more information.

This message is used to add an entry into the Asynchronous Notification List or modify an existing entry. The master will generate a Completion Code Configuration Manager message 0x0213 message indicating success or failure of this command. A special sentinel value of Device 0 Port 0 and System 0 indicates that the flags should be applied to the global filter.

This message is used to delete an all entr y ies from the Asynchronous Notification List. The master will generate a Completion Code Configuration Manager message 0x0213 message indicating success or failure of this command. A special sentinel value of Device 0 Port 0 and System 0 indicates that the global filter should be deleted. Another special sentinel value of Device 65535 Port 65535 and System 65535 indicates that all entries should be deleted.

Table B lists commands between connection manager and devices. Again the first column is the name of the command the second column is the value of the command the third column is the device response the fourth column is the master response and the last column is the description of the command. For example on the second row if the blink command sent by a master to a device the value of the command is 0x0502 and in response to that command the device says nothing nor does the master. The description of the command is given to all devices to make the LED blink. As this occurs the master determines whether the device is online and sends back a visual indication.

This message is sent by a master to request determine the presence of the specified device in the system.

This message is the response to the Ping Request message above. The device responds with this message to inform the requester that the device is still on line.

The blink message is a broadcast message that is transmitted to every device periodically. The time period of the message may be dependent upon the medium in which the message will be sent.

The time period for Blink messages is not determined at this time. Each device implementation may not require that the Blink message be periodically sent at any anticipated rate. The ideal rate will be determined based upon the quantity of bus traffic. It may someday even be determined dynamically.

The MSB Bit is set when the master initially powers up on line. In response to bit being set the receiving device should place itself in the off line state turn all channels off and set all levels to zero or prepare itself to send status updates as necessary to the master . The master shall send 3 consecutive blink messages with bit set.

This message requests from the destination master a Blink message response. The response will not be a global response it will be destined only to the requester.

This message is the response to the Request Dynamic Device Address message below. It returns a device number for temporary use by the requesting device.

The device can use this device number for as long as it has communication with the master. The returned device number may the one suggested by the device in the Request Dynamic Device Address message or may be different.

This message requests a device number from a master. The Newbee flag must be set in the message header.

This message requests that the Connection manager redirect strings coming from the specified source device to the specified destination device. This will also prohibit strings from the source device getting sent to the interpreter until the PassThrough is disabled. This message will cause an RXON message to be sent to the source AXLink device.

This message is sent by a master to request notification of specific messages that are received from OR sent to the specified device. Typically the notification messages are Device Manager messages specified above .

The following message command values are not actual messages but rather virtual commands to the Notification Manager that function as follows 

This message is used by the IDE to request that diagnostic information be sent to the requesting device. If any flag bits are set unsolicited diagnostic messages of the specified type s will be sent to the device. If all bits are zero then no diagnostic message will be sent to the device.

This message is used by the IDE to request a list of online devices for the receiving NetLinx master. The master will respond with Device Info message s for each device currently online. In addition it will generate a Port Count message for each device.

This message indicates that all requested devices from the Request Devices Online message have been sent. This message is used by the IDE to determine when all online device information has been received.

This message is used by the IDE to request the status of the specified device. The master responds with Output ON messages for each output channel that is on Feedback ON messages for each feedback channel that is on etc. See the Diagnostic Manager specification for more information.

This message indicates that all of the Request Device Status information has been sent. This message is used by the IDE to determine when all device status information has been received.

This message is used by the IDE to request the current asynchronous notification list from the master. The master generates a series of Asynchronous Notification List messages one for each entry in the list to the requesting device.

This message is generated by the master in response to the Request Asynchronous Notification List message. For each entry in the master s list one of these messages will be generated. If there are no entries then the number of entries field will be zero. See the Diagnostic Manager specification for more information.

This message is used to add an entry into the Asynchronous Notification List or modify an existing entry. The master will generate a Completion Code Configuration Manager message 0x0213 message indicating success or failure of this command. A special sentinel value of Device 0 Port 0 and System 0 indicates that the flags should be applied to the global filter.

This message is used to delete an all entr y ies from the Asynchronous Notification List. The master will generate a Completion Code Configuration Manager message 0x0213 message indicating success or failure of this command. A special sentinel value of Device 0 Port 0 and System 0 indicates that the global filter should be deleted. Another special sentinel value of Device 65535 Port 65535 and System 65535 indicates that all entries should be deleted.

Places removes the device into from the Identify state. While the device is in the identify state a press of the identify button causes the device to take on the specified Device System. The device should respond with the Identify Mode Address Response report its old device as off line then report the new device as on line.

This command initiates the transfer of data for a device or master. It is intended that this transfer mechanism be common to all types of file transfers including firmware upgrades IR data touch panel design files.

Requests for the device to respond with the list of IP addresses the device or master attempts to contact.

The response to the request above one IP Address List message will be generated for each IP address in the list.

Set the IP address es of the DNS servers and the domain name. A maximum of three 3 IP addresses may be specified. The search order is same as the order provided. A NULL must be provided for empty entries.

Set the IP address subnet mask and gateway of the unit s Ethernet interface. A NULL must be provided for empty entries.

Request the device s Ethernet interface IP address subnet mask and gateway of the unit s Ethernet interface. The response to this message is the Get Ethernet IP Address message.

Request the device s current time and date. The response to this message is the Get Time and Date message.

Indicates successful unsuccessful completion of a previous message. In the case where the device settings such as device number are being modified the completion code message is generate using the old device information before the new settings take effect.

Indicates that the device has received the Identify Mode Address Enable and has had a button pressed on the device to indicate it should take on the ID Mode device and system number.

The included message protocol and its packet are designed to be sent independent of any transport protocol. Thus this message can be sent by a TCP IP protocol over any connection or by a lontalk protocol which is based on the phastlink protocol developed by AMX Corporation. This protocol can also be carried over on RS232 PPP connections. This protocol supports master to master PC to master and PC to device communication.

Communication components are usually represented using the seven layer ISO model. Operating Systems such as Windows NT 9x provide most of these layers with a powerful object oriented abstraction at the application layer. Under Windows at the application layer the software developer is presented with a Berkley Sockets interface. With this interface the developer can establish two way communication using an object known as a Socket . Applications can choose to be clients or servers. Though this is a powerful abstraction there is no facility to help the application developer formulate a protocol in terms of the packets of information sent back and forth on the wire. The services that are available deal with namespace resolution and sending and receiving of blocks of binary data. Typically the client and server portions of the application are written to understand each other s messages on the wire. The messages consist of structures of binary information. To formulate such messages the developer usually has to program in a low level language such as C or C .

The Internet has given rise to a whole new species of developers called Web developers . On an average they are not low level programmers who can code in C or C and instead use some combination of HTML Java JavaScript and VBScript. Except for the full Java language the other languages are scripting languages .

The primary goal of the AMX Corporation dynamic messaging components invention is to make a scripting language such as VBScript or JavaScript or even Visual Basic capable of directly communicating on any TCP IP network connection. This means that these dynamic messaging components have to give the script writer the ability to i form binary messages and transmit them on a network connection and ii receive binary messages from a network connection understand their format and unpack them to extract individual fields in the message. As explained later in this document it will be seen that apart from these two basic requirements current communication protocols require more complex features that these components now provide.

To meet the primary goal explained above the dynamic messaging components were chosen to be implemented using the Microsoft Component Object Model or COM. This is primarily because presently no other programming model allows a scripting language to use self describing objects with such ease of use. COM objects are well understood by the developer community and the model is mature and stable. However other suitable programming models may be used if desired.

To effect the requirements enumerated above three distinct objects or components are provided. They include a binary message descriptor layout manager object a message instance object that represents one network message and a transport object that manages the buffered network transmission issues.

The message descriptor layout manager object allows a script to define the structure of binary messages that represent packets of information sent back and forth on a network connection. The message structures are identified using unique names. Once defined these structures can later be used to form instances of messages or define more complex structures which contain embedded structures in them. Referring to for an example of the message descriptor layout manager object which includes a binary message structure that may be sent or received according to the communication protocol. The packet structure includes a message header structure that is an embedded structure within the message. The message header includes a packet protocol identifier 2 bytes a packet size in bytes 4 bytes a packet version 2 bytes and a packet type 2 bytes . Message structure further includes a message body which contains data according to the message type. For example the message body may include an element 1 2 bytes an element 2 a variable length element whose size is specified by element 1 and an element 3 which is a NULL terminated string.

To further describe this message structure two additional message structures are defined the message header and the entire message. The entire message contains the header structure as an embedded structure within itself. The following pseudo code shows the general format of the description 

The operations methods that the layout manager provides allow a script to define the individual components of a binary message. The operations generally take the form 

For example to add the PacketSize element to the message the AddPrimitive operation is used. The element type is specified as LONG meaning it is an integer 4 bytes in size. Adding elements to a message has to be done within a BeginDefineLayout EndDefineLayout pair of operations. This indicates to the layout manager when a new message structure definition begins and ends. Once a message structure is defined completely it may be used as an element type in further message definitions. In the example above the AddStruct operation was used to make Packet Header Structure an element in the structure definition of message Packet Type 1 . Embedding structures within structures allows for definition of very complex messages.

The example also illustrated yet another important concept. This is the ability to define variable length elements within a message structure. The element named element 2 is of variable length. It is a byte char array whose length is specified within the message by the preceding element named element 1 . Dynamically sized elements of this type are pretty common in many communication protocols.

Due to their very nature some dynamically sized elements do not have to have an explicit element specify their size. An example of such an element type is a NULL terminated string. A NULL terminated string is a sequence of bytes in which the byte value of 0 is a special value indicating the end of the sequence. Since the end of the sequence is specified by this special value its length does not have to be explicitly stored. The example shows that element 3 is a NULL terminated string and the operation AddSZString is used to add it.

BeginDefineLayout starts definition of a new message cannot be called while already defining a message .

EndDefineLayout ends definition of a current message cannot be called if not currently defining a message .

AddPrimitive adds a primitive element to a message structure. Primitive elements form the basic entities of a binary message. Primitive elements includes characters 1 byte 2 byte integers 4 byte integers floating point numbers 4 bytes and double precision floating point numbers 8 bytes .

AddPrimitiveDynamicArray adds a dynamic array of primitive elements to a message structure. The array does not have to be fixed in size rather the name of another integer type element is used to contain the actual length of this element inside a specific instance of this message structure. The size element has to have been already defined within the message structure. In other words the length of this dynamic element is specified by an element within the message and that element should be stored in a position physically above the dynamic element.

AddStruct adds a structure element to a message structure. The structure element must already have been defined.

AddStructDynamicArray adds a dynamic array of structure elements to a message structure. The same rules as that of AddPrimitiveDynamicArray applies to this method.

AddSZStringArray adds an array of NULL terminated string elements to a message structure. The array does not have to be fixed in length rather the last string element of the array has to be terminated with two NULL characters rather than one NULL character.

AddPadding adds padding of specified byte amount to a message structure after an element. This method is used to align individual elements of a structure to be on specific byte boundaries.

AddAlignmentPadding adds padding to a message structure after an element to align to the specified alignment boundary. Byte alignments can be made to occur on 2 4 8 or 16 byte boundaries. This method is used to align individual elements on specific byte boundaries when the element sizes are not fixed. The message instance object of the dynamic messaging component allows a script to create an instance of a previously defined message in memory fill the message with values for the individual fields of the message and then with the help of transport object which is described in the next section transmit the message over a network connection. The message instance object also allows a script to receive an instance of a message over a network connection unpack the message and access the values of the individual elements in the message.

The message structure previously defined will be used again to show how an instance of that message could be created in memory. illustrates an instance of the message whose structure was described in the previous section. Message includes a message header that has the following exemplary values packet protocol identifier 1 packet size in bytes 23 packet version 1 and packet type 3 . The message body may contains the following elements element 1 5 size of following dynamic array in bytes element 2 hello array of 5 characters and element 3 world.backslash.0 NULL.backslash.0 terminated string .

In the pseudo code above a message instance object is created which is then used to set the various values for the elements within the message. The code to actually transmit the message is described below.

The first operation performed is the CreateMessage operation. This operation allows a script to create a message of a given type. The message type is previously defined within this or some other script using the message descriptor layout manager object. The meaning of the second boolean argument FALSE in this case is explained below. Following the creation of the message two operations are performed to set the lengths of the two dynamic fields within the message. The two fields are element 2 and element 3 . element 2 is a dynamic array of characters and element 3 is a NULL terminated string. After a message is created sizes of all dynamic elements within the message have to be specified because that is how the Message Instance object knows how much memory this message will occupy. If there are no dynamic elements in the message this step can be completely avoided.

The third step is actually setting the values of the various fields elements in the message. In this message there are two parts header and body. The various operations supported by the Message Instance object provide scripts extreme flexibility in writing values of elements into a message. In this instance methods like SetInt2 SetInt4 SetCharArray and SetSZString are used. Also once all dynamic elements have been explicitly sized the Message Instance object knows what the entire size of the message is so the GetMessageSize operation can be used to get the size. This operation is used in writing the message size into the PacketSize element of the header. The sequence of set operations has to be enclosed within a pair of BeginSetLayout EndSetLayout operations so that the Message Instance knows when a message is ready to be transmitted.

Now that a complete example of a message instance has been illustrated the following section enumerates all the operations methods provided by the Message Instance.

CreateMessage creates an instance of a message given its type. Optionally this method can be used to transform a message of one type to another type.

SetSZStringLength sets the length of a NULL terminated string. The string may be by itself an element in the message or could be part of a string array.

BeginSetLayout notifies the message instance object that Set methods are about to be called which will write values to individual elements within the message.

EndSetLayout notifies the Message Instance object that the message should now readied for transmission as all the individual element values have been set.

BeginGetLayout notifies the Message Instance object that the message should be un packaged so that individual elements can be read out of it.

EndGetLayout notifies the Message Instance object that the script is done reading values out of the message.

Send using an instance of the transport object streams the message instance over a network connection.

Receive using an instance of the transport object receives a message instance from a network connection.

SetConvert sets network to host and host to network byte swapping transformation mode. In this mode all incoming messages are assumed to be in network format and all outgoing messages are converted to network format.

Pushback allows for message overflow underflow. When an incoming message is partially formed or contains more than a full message the partial message bytes can be pushed back into the transport object which can be retrieved later.

Message layout and message instance creation are set forth above. The final step in network connectivity is the actual transport. Message layout and message instancing are actions that give rise to blocks of bytes in the memory of the web server or wherever the script is being executed . To be able to communicate on a network a live connection has to be made to be able to send and receive data. The third object inside the AMX Corporation dynamic messaging components module is a transport object implemented specifically to handle TCP IP networks. The two previous objects do not in anyway assume what kind of a network connection they are communicating over. The transport object s interface is specified independent of the nature of the network. The transport object has a built in asynchronous message handler that can fire scripts when messages arrive outside of a script s Receive method call.

DisableAsyncHandler during some operations it is desirable not to have the asynchronous message processor fire external scripts this method allows a script to disable the asynchronous message processor during which time all incoming messages are buffered up.

EnableAsyncHandler enables the asynchronous message processor from this point onward every incoming asynchronous message will result in an external script being executed.

GetHost returns the network address of the remote computer to which the transport object is currently connected.

GetPort returns the port on the remote computer to which the transport object is currently connected.

The sequence of operations to create and send a message instance is given in the exemplary pseudo code below 

The dynamic messaging components are used in the communication between the ASP based web server and the Internet appliance server. The various web pages that deal with controlling and administering the Internet appliance server use these objects to create and send TCP IP messages to the IA server.

Although several embodiments of the present invention and their advantages have been described in detail it should be understood that mutations changes substitutions transformations modifications variations and alterations can be made therein without departing from the teachings of the present invention the spirit and scope of the invention being set forth by the appended claims.

