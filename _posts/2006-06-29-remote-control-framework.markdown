---

title: Remote control framework
abstract: A remote control framework enables a plurality of target devices to be controlled by a plurality of remote control devices irrespective of bearer types. In a preferred embodiment any target device may also act as a control device and any control device may also act as a target device. The framework also enables any application running on any target device to be controlled by any controller device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09406219&OS=09406219&RS=09406219
owner: Core Wireless Licensing S.a.r.l.
number: 09406219
owner_city: Luxembourg
owner_country: LU
publication_date: 20060629
---
This application claims the priority of PCT GB2006 002395 filed on Jun. 29 2006 which claims priority to GB 0513312.9 filed on Jun. 29 2005 the entire contents of which are hereby incorporated in total by reference.

For the avoidance of doubt in the following description of the present invention the term device is used to refer to an entity that is capable of being remotely controlled by any type of external device over any type of wired or wireless connection.

The first demonstration of wireless remote control was by Nikola Tesla who exhibited a radio controlled boat on a specially built pond at an electrical exhibition in Madison Square Gardens in 1898. U.S. Pat. No. 613 809 was issued on this invention.

Despite this venerable pedigree the commercial exploitation of remote control technology for domestic electrical and electronic appliances did not occur in earnest for about another 50 years when it was eventually pioneered by Zenith in connection with televisions. Their first television remote control the Lazy Bones appeared in 1950 and this was connected to the television by means of a long wire. Whilst wired remote controls for televisions were not a long lived technology principally because users kept tripping over the cord they have always continued to be manufactured for many other types of electronic appliances from traditional wired remotes such as those for slide projectors and dictaphones to more modern appliances such as digital camcorders the Sony RMVD1 is a recent example of this latter art.

It is wireless remote controls that now comprise the majority of such devices. In 1955 Zenith s Flashmatic was the first wireless television remote control to appear it operated by means of visible light signals made to photoelectric cells on the television. The following year Robert Adler s Space Commander became Zenith s first truly practical wireless remote control it was a mechanically operated ultrasonic device. Ultrasonics remained the basis of remote control technology until the development of infrared transmission devices in the 1980s. Infrared remains the technology of choice for remote control devices today though RF Radio Frequency is commonly used in cases where the line of sight communication required by infrared is impractical.

Although wireless remotes are still the more common variety it is noticeable that wired remotes are making something of a comeback especially on appliances for which wires are needed in any case the clearest example of this is appliances with audio functionality. This includes mobile phones which can be controlled via buttons in a module inserted into the audio lead on hands free headsets and in a rather more sophisticated form on top end digital music players all the market leaders such as the Apple iPod the Creative Zen and the iRiver have optional or integral wired remote controls .

In summary the remote control of modern electrical and electronic appliances is today extremely widespread in any situation where close physical proximity between the person seeking to operate the appliance and the appliance itself is either

Until recently the technology for remote control of appliances was limited in a number of related ways 

It should be noted in this context that the existence of programmable remote controls which can be used with appliances from many different manufacturers is not evidence that they all conform to a common standard. Such programmable devices are able to emulate the operating modes transmission protocols data rates and control codes of each of the various manufacturers rather than being able to run in a single mode that functions in all situations.

However electronic appliances are increasingly becoming multifunctional and programmable the trend is for them to be built around the same type of central processing units and memory that are employed in general purpose computers. There is substantial evidence that where this is the case it is increasingly possible to circumvent the limitations described above.

In the domain of remote control technology appliances that are built around the same processor and memory components that are used in programmable computers are generally now able to utilise standardised communication technologies. Among these standards are 

Although there is an increasing use of standards such as these it is notable that many companies do not utilise them as much as they ought. For example despite the fact that Apple invented Firewire they do not use the technology in their own remote controls people have had to go to some lengths to reverse engineer the proprietary protocols used in the iPod remote control some of which are described at http www.maushammer.com systems ipod remote ipod remote.html .

As well as the above standards based technologies it has also become apparent that where appliances incorporate a programmable digital computer linking two together enables one to control the other provided that both are running compatible software. A larger static appliance such as a personal computer can therefore be controlled by a smaller mobile appliance such as a cellular phone giving in many cases a superset of the functionality of conventional remote controls. Many examples of this technology exist which enable mobile telephones to be used to control media players and other applications on personal computers via Bluetooth such as Bemused http www.compsoc.man.ac.uk ashley bemused and Bluetooth Remote Control http www.labtech.epitech.net remotecontrol which both control Windows PCs. Sailing Clicker enables a mobile telephone to control an Apple Macintosh http homepage.mac.com jonassalling Shareware Clicker while implementations for Linux also exist such as http www.iptel now.de HOWTO BT REMOTE bt remote.html .

The prior art as described above shows a gradual progression from dedicated inflexible and proprietary remote control solutions to versatile flexible and standard based ones.

However all the standards based solutions described above are limited by the fact that they are specific to bearer technologies and very often also specific to transport protocols used with that bearer. Those that are skilled in this art will be aware that many possible bearers for remote control signalling exist including but not limited to 

An appliance that is designed to work with a remote control using any one of these bearers is not currently able to work with any of the other types of bearer irrespective of whether or not the remote control uses standard protocols. An MP3 or other music player designed to be used with its bespoke wired remote control cannot be made to work with a generic Firewire USB Bluetooth or Infrared remote control device even though it may have such an industry standard interface available.

Even with remote control devices making use of the same bearer appliances may fail to work where an incompatible protocol is implemented. For example it is well known that the Bluetooth headset and handsfree profile are sufficiently different that a Bluetooth enabled mobile phone that only supports the headset profile will not work with a Bluetooth peripheral that only supports the handsfree profile this type of incompatibility has caused distress to numerous consumers as there is no easy way of fixing it.

Therefore it is an object of the present invention to provide a remote control interface which at least alleviates the above mentioned problems caused by the close coupling between remote control solutions and specific bearer technologies through the provision of a generic remote control interface that can be used by application software running on an appliance to receive commands to and from any type of remote control device irrespective of the protocol or bearer that it might be used to transport those commands.

The same generic software interface can also be used by a remote control device to send commands to an appliance once again irrespective of any protocol or bearer.

Furthermore any appliance incorporating a programmable computing device which implements this generic software interface can not only use it to receive commands from a remote control device but can also use it in conjunction with a suitable application to act itself as a remote control device.

According to a first aspect of the present invention there is provided a method of enabling one or more target devices to be remotely controlled by one or more controller devices through the use of commands sent over at least one of a plurality of bearers including but not limited to 

According to a second aspect of the present invention there is provided a computing device arranged to operate in accordance with the method of the first aspect.

According to a third aspect of the present invention there is provided an operating system for causing a computing device to operate in accordance with the method of the first aspect.

These and other features of the invention will be more fully understood by reference to the following drawings.

In the following description the generic interface of the present invention is referred to as a Remote Control Framework. It can be used by any applications or software running on the appliance however the remote control framework internally uses bearer plug in modules to send or receive external remote control commands. A plug in can be defined as a replaceable item of executable code that provides specific services to a loosely coupled application or service that can load or invoke it at run time.

Each unique bearer requires its own plug in. Each bearer plug in externally implements the same generic application programming interface API but is internally customised to make use of the specific features and requirements of the relevant bearer technology to send and receive commands to and from the remote control device.

Example bearer plug ins are a Wired Headset an Infrared remote control and the Bluetooth audio video remote control profile AVRCP .

The arrows in show the flow of commands and of control for a typical architecture in accordance with the present invention.

The remote control server has plug ins for AVRCP a wired remote and Infrared available with extensions possible one of which is shown as box in . In this embodiment the remote control server includes a target selector . The target selector performs three roles 

The dotted line in signifies the boundary of the apparatus which is implementing this invention. When the apparatus is being used as a controlled appliance commands are received or come in over this boundary. When the apparatus is being used as a remote control commands are passed or go out over this boundary. The nature of the bearer for these commands is encapsulated within the remote control server .

It should be noted that the further devices shown at the bottom of may themselves be running the remote control framework but they need not be the modules that plug in to the server can be designed to implement any protocol over any type of bearer.

Adding support for extra remote controls for a controlled appliance is simply a matter of adding additional plug in modules to the Remote Control Framework on that appliance. So a USB remote control only requires a USB plug in not shown to be made available to the remote control server for example in lieu of the extension box in . This may be provided as an installable software module on an open operating system alternatively it could be provided as a hardware upgrade by means such as an over the air or service centre upgrade or a user insertable module such as an EPROM which would be recognised by the operating system.

Adding the capability to control additional appliances by a remote control is similarly managed by adding plug in modules to that appliance s own remote control framework.

The example of the present invention which will now be described is an implementation of the invention on a cellular telephone running Symbian OS the advanced operating system for mobile phones produced by Symbian Ltd it therefore uses terms and idioms which will be familiar to those skilled in the art of building devices with this operating system as described in various textbooks on Symbian OS such as Symbian OS Explained by J. Stichbury Wiley 2004 ISBN 0470021306 and in the various development kits published by Symbian Ltd such as those found at http www.symbian.com developer techlib sdl.html . Those skilled in the art will of course appreciate that the sample implementation described here can also be adapted to run on many different operating systems and many different devices.

This example Remote Control System RemCon shows how the invention can be used to control a phone and in particular a music application such as an MP3 player running on the phone from a Bluetooth stereo audio headset. The application being controlled is referred to as a target. For instance in this example the user may interact with a headset to perform functions such as play pause and next track in essence the headset is used for remote control of the phone.

More generally the phone may be controlled by another device over any suitable bearer or protocol. Therefore in order to demonstrate the extensibility of the invention another initial implementation described is that of a relatively basic plug in which works over a serial transport using an arbitrary naive protocol.

The remote control system of the present invention also allows the use of the device as a remote control for other devices. The application on the device for this functionality is referred to as a controller. For example the device might be used for the remote control of a television.

The system is extensible in terms of the transports and protocols collectively known as bearers which may be used to transmit and receive remote control messages. Although in this description headsets are generally envisaged as Bluetooth headsets it is clearly possible to support other types of headsets such as wired ones.

Independently of bearer extensibility the system is also extensible in terms of the messages which may be sent and received. Compliance with a new bearer protocol may also involve therefore supporting new messages.

The system also allows multiple client applications to use it simultaneously. Not just one controller and one target but multiple targets at the same time as multiple controllers.

Controller clients send commands and receive responses. Target clients receive commands and send responses. The controller API allows therefore connectionless operation where commands are routed by the system as decided by the device manufacturers and connection oriented operation where the client specifies the bearer and any relevant addressing information for the remote party . Clients can monitor the states of the various connections extant at any point in time. The system is therefore bearer agnostic.

Some of the components in the architecture shown in implement standard protocols which are well known to those skilled in the art. These include 

There will be at most a single instance of the RemCon server running on the device. It is a transient server that is to say it will not always be in use and in order to save resources it shuts down when there are no clients.

This particular implementation of the remote control system is associated with implementations of the AVRCP and AVCTP extensions to the Bluetooth system. Hence 

While there are two possible types of bearer connection oriented and connectionless this implementation requires that connectionless bearers emulate connection oriented behaviour. The bearer API is therefore connection oriented as is the AVRCP bearer plug in.

Instantiation of a connection oriented bearer causes it to start listening for incoming connections. Such bearers accept incoming connections and notify the RemCon server.

It should be noted that the RemCon server is also able to command a bearer in order to attempt connection to a specific remote device.

When a controller in connectionless mode sends a command the actual bearers to be used and specific connections within those bearers are specified by a plug in normally specific to a device and provided by its manufacturers known here as the Target Selector Plug in TSP this is discussed in more detail below in connection with targets. When a controller in connection oriented mode sends a command the connection used is that already opened by the controller. The TSP is not bypassed however it is able to control whether that controller may send that command to the specified remote at that time.

Bearers are used to transmit commands and receive responses. The server maintains knowledge of commands sent by each controller. Responses coming in over a connection are directed by the server to that controller client which has recently sent the appropriate initiating command over that connection.

The controller API also contains a NotifyConnectionsChange API which delivers information on all the connections over all bearers in the system.

As with controller clients there may be more than one target client operating at once. Target operation is more problematic than controller operation because bearer protocols do not necessarily encapsulate which target an incoming command is intended for. Which target needs to field a particular incoming command changes not only at run time but in ways in which the target client may have no control or even knowledge. By way of illustration if the user is listening to music using an MP3 player application and a call comes in which is picked up by the user the target application for volume control changes initiated by the headset changes from the MP3 player application to the phone application. If the device user interface UI maintains a distinction between Multimedia volume and Call volume then each of these applications needs to listen for volume control changes in order to update their own on screen display.

In effect the system is trying to model what the user thinks is being remotely controlled at any one time. With current practices this is generally quite straightforward a user uses a TV remote control to control a TV and a video remote control to control a video recorder. This makes the mapping between the physical controller and the target explicit.

However with multiple target applications running on a phone being controlled by a single remote controller headset this mapping is more obscure. The following factors are amongst those which may be used to establish the mapping 

The above possibilities which are merely exemplary make it clear that it is impossible for a generic operating system to offer a definitive answer to the mapping problem. The manufacturer of the device who determines the user interface is therefore often better placed to decide mappings.

Hence a mechanism is provided called the Target Selector Plug in TSP which can be used by device manufacturers to implement a set of rules which make best sense according to their user interface system. Thus the TSP is provided with a list of the current client target process IDs and is expected to indicate back to RemCon by process ID a list of target clients to receive the message.

Due to the fact that targets cannot be expected to know which bearer will deliver commands to them whenever a target client connects to the remote control system all available bearers must be loaded and start listening for incoming connections. Note that the target client is agnostic towards bearers but it is not completely unaware of their existence. The NotifyConnectionsChange API previously mentioned is also available to targets.

A single reference implementation of the TSP interface is provided by RemCon. For targeting purposes this interface is provided with an array of potential recipients. In this way it is able to indicate an array of intended recipients and the message will be delivered to each.

As described earlier the TSP is provided for the device manufacturer to implement according to their own particular interface policy.

In a working device a single TSP is provided at read only memory ROM build time. There is logically only one such plug in in the system as there is logically only one correct way to answer the question on a device with just one UI. The commands are actually delivered by RemCon the TSP is merely queried by RemCon so it knows where to deliver the messages.

Target clients are identified for these purposes by process ID and secure ID. RemCon polices the establishment of target clients such that only one is allowed per client process. For each command the TSP is given a list of the IDs of the currently open target clients so it knows which targets are available. The TSP is also at liberty to trigger the opening of further target client applications and add their IDs to the array.

Remote targets are identified by a combination of the bearer s Unique Identifier UID and a bearer specific connection information package. Bearer specific connection packages types should already have been made public to third parties so that connection oriented controllers are able to function correctly.

The TSP API functions via a request callback mechanism for maximum flexibility in its implementation. The callback may be synchronous or asynchronous. The TSP is designed to be capable of understanding any command passed to it by RemCon for addressing sufficient to fulfil its purpose of addressing the command. This includes not only Core API commands but also extension commands. If the TSP errors a command then that command will not be delivered.

There is only one TSP instance in the system. Therefore incoming events from many bearers are queued in RemCon before being sent across an asynchronous API to the TSP. For targets once a command has been addressed it is given to those selected target clients assuming they each have an outstanding receive request.

When the receive request of the target concerned is completed that target processes the given data and usually reposts the request. If the TSP indicates that target X should receive a command when that target has no Receive request outstanding at that point in time then that command is queued until target X posts a Receive request. Incoming responses are also queued in this way.

The framework supports extensions to the core API for instance to support APIs specific to the various device manufacturers. A controller client does not necessarily know when sending a command which bearer it will be sent over. Therefore the packaging of the command into the bearer specific format is carried out server side .

If a converter plug in to convert between a particular bearer format and a particular extension API is not found then that bearer is not able to process messages from that API and they are dropped.

Consequently there are in principle N converters in the system where N is the product of the number of bearers and the number of APIs. In practice N may be less that this because

In the description which follows specific Converters will be named according to the following convention Converter A B is a converter which converts between API A message formats and bearer B message formats. For instance the RemCon work will provide Converter Core Serial and Converter ExtApi1 Serial and the AVRCP will provide Converter Core Avrcp and Converter ExtApi1 Avrcp .

The server owns and controls the command queues. It is the heart of RemCon dealing with all message routing.

It has a member holding the client s process ID. This is used by the session to make sure that at most only one fully instantiated instance of a target session is created per client process.

Objects of this type field client requests holding RMessage2 members for each such asynchronous API for later completion.

The design of the bearer API and the design of the reference serial bearer is described here. Note that each bearer is required to support each and every message in every possible API. It is permissible to do this by returning KErrNotSupported when an attempt to send a message is made but simply ignoring or dropping a message is not allowed. In practice the UID identifying the API is used by bearers to forward the message to the correct converter. If there is no converter for that API then KErrNotSupported is the correct response. If the converter is found but does not for whatever bearer specific reason support the particular message then KErrNotSupported is given back as a response.

Bearers will be plug ins. A bearer uses converter plug ins each bearer has in principle one for each extension API plus one for the Core API to convert each message between the bearer protocol specific message format and the client friendly bearer agnostic message format. If a converter plug in is not supplied for a particular bearer API pair then that bearer will not be able to send or receive messages belonging to that API.

Bearers are instantiated on server startup. The instantiation of a bearer causes it to listen for incoming connections. An incoming connection is accepted automatically by the bearer subject to its own policy. This may include either protocol specific or other security policies while it is clearly desirable to ensure that RemCom is secured this invention does not specify or depend on any particular security model.

RemCon is then notified of the existence of a new connection and relevant remote address etc parameters. Bearers are allowed to support multiplexing or multiple remote control channels . RemCon is informed by the bearer of the states of any bearer connections.

The bearer API is able to support multiple commands and responses being sent simultaneously. If the bearer is able to support queuing then RemCon will be able to post many simultaneously outstanding Send commands on that bearer on one or more connections. If the bearer does not support queuing then it must return an error to RemCon which will complete the client s original request accordingly.

For a connectionless controller once a command has been addressed by a TSP the resulting addressed message s are sent over the relevant bearer connections. If any fails the particular commanded operation is aborted and the controller client is notified of that error.

RemCon provides no API for querying available bearer plug ins this can be achieved using normal operating system OS facilities as necessary because the nature of all plug ins and the interfaces with which they can be used are public information.

A connection oriented bearer supporting only one connection at once will start listening when it is created. When it is connected either by accepting a connection or when driven by a connection oriented controller it notifies RemCon of the state of the connection. If the connection is terminated for any reason the bearer notifies RemCon.

A connection oriented bearer supporting multiple connections e.g. AVRCP will start listening when it is created. If a connection is established using the listener it will continue to listen for further incoming connections. RemCon is kept up to date regarding the states of connections.

Connectionless bearers must emulate the connection oriented behaviour of the bearer API. The serial bearer supports connectionless behaviour and it is able to indicate to RemCon that it is connected when the COM port is opened successfully. If there is a problem opening the port then it will retry to connect after a pause.

Called by RemCon to send messages on a connection. The bearer must indicate the completion of the request i.e. that it has sent the message or queued it for sending synchronously by return.

 param aData API specific message data. If the bearer returns KErrNone it is considered by RemCon to have taken ownership of this.

Note that after accepting a SendCommand request the bearer is required to generate at least one response whether genuinely from the remote party or not .

Called by RemCon to pick up a message previously notified to it by the bearer using NewCommand or NewResponse.

This is called by RemCon to indicate whether there are any controller clients present aControllerPresent and whether there are any target clients present aTargetPresent .

aControllerPresent will be a true value if any controllers are present and EFalse otherwise. Implementers are reminded not to compare to ETrue.

This API is provided to facilitate the creation and destruction of Service Discovery Protocol SDP records by the AVRCP bearer. Failure is not interesting to RemCon hence the void return type.

RemCon has adequate capabilities to use any conceivable transport but it is required to check whether controller clients have capabilities. This API is called so that RemCon can police controller client requests. For connection oriented controllers the check is performed when the client tries to associate itself with the bearer. For connectionless controllers the check is performed after the TSP has chosen a particular bearer for the client s transmission.

CRemConBearerPlug in has a reference to an object of this type which it uses to signal completion of requests to RemCon.

Called by a bearer to indicate completion of an outgoing connection request CRemConBearerPlug in Connect .

Called by a bearer to indicate completion of a disconnection request CRemConBearerPlug in Disconnect .

Called by the bearer when a new message is available in its queues to be picked up by RemCon. RemCon will call Get Response or GetCommand.

Accessor for a converter. The two UIDs given can be used to uniquely identify a converter. Converters are managed by RemCon and merely accessed by bearers via this interface.

The serial bearer is a concrete implementation of the bearer interface. CRemConSerialBearer derives from CRemConBearerPlug in. It owns Active Objects which use RComm Read and RComm Write to receive and send data on a serial line these notify completion through the observer interfaces.

CRemConSerialBearer opens the comm port on instantiation and immediately indicates connect complete to RemCon. When it receives from RemCon a request to Send a command it packages the API UID and operation UID into a fixed width buffer using the appropriate converter and sends it over the serial line without retry. When the RComm Write completes the CRemConSerialBearer is notified and it calls SendComplete on the observer. When it receives from RemCon a request to Receive a command it queues a RComm Read for the fixed buffer size. When this is completed the string is decomposed using the appropriate Converter into an API UID and operation ID which are notified to the observer via ReceiveComplete.

This is called by RemCon to address the given outgoing i.e. from a connectionless controller command aInterfaceUid aOperationId . aConnections is empty when passed in. The TSP appends zero or more TRemoteAddresses and calls OutgoingCommandAddressed on RemCon. The TSP may do this asynchronously. RemCon directs the command to the given bearers with the associated connection information.

This is called by RemCon when a connection oriented controller tries to send a command. The TSP calls OutgoingCommandPermitted with either ETrue the send is permitted or EFalse the send is not permitted .

This is called by RemCon to address the given incoming command. aClients when passed in contains the current set of target clients. The TSP adds or removes zero or more items from this collection and calls IncomingCommandAddressed on RemCon. The TSP may do this asynchronously. The TSP is at liberty to start client applications and add a suitable TClientInfo populated with at least their process ID to the collection. RemCon directs the command to the given clients without assuming that any of them are still extant.

Called by the TSP to indicate that the previous AddressOutgoingCommand request has been answered. the array passed by reference is correctly populated . NB Only one AddressOutgoingCommand may be outstanding at any time but more than one of AddressOutgoingCommand and AddressIncomingCommand may be outstanding at once.

Called by the TSP to indicate that it has decided whether the controller send represented by the most recent call to PermitOutgoingCommand is permitted or not.

Called by the TSP to indicate that the previous AddressIncomingCommand request has been answered the array passed by reference is correctly populated . It should be noted that only one AddressIncomingCommand may be outstanding at any time but more than one of AddressOutgoingCommand and AddressIncomingCommand may be outstanding simultaneously.

This is a simple type wrapping up the client session s process ID and current send message which may be used for security purposes.

The RemCon client side supports sending and receiving commands and responses. It is also extensible. It has three layers as shown in 

The inner client side sends and receives generic data. The data consists of an interface UID associated with a specific outer layer DLL an ID of an operation within that interface and any associated data. The interface UID and the operation ID together constitute a unique message identifier.

Clients link statically to the outer layer DLL s they want to use and to the intermediate layer. On initialisation the client calls a method on the intermediate layer DLL to register an object from the outer layer DLL by its interface UID with the intermediate layer. The intermediate layer presents methods for opening RemCon sessions.

When a message is sent by a client the outer layer DLL adds its interface UID and the intermediate layer simply forwards this data as a whole to RemCon.

When a command is received the TSP decides which target s it is to be delivered to. When a response is received RemCon hands it to the controller client that sent the original request. The RemCon server simply delivers the message to the indicated target RRemCon session s in the inner client side which delivers it to the intermediate layer. The intermediate layer analyses the interface UID of the message and if it has a registered outer layer object with that UID it hands the message to that outer layer object. The outer layer DLL analyses the operation ID optionally decomposes the associated descriptor data and hands the message to the ultimate client via its own API.

The immediate client side is that nearest to the server. It consists of a single R class RRemCon and some auxiliary types.

It is preferable to implement some type of security policing on RemCon accesses at this point to avoid control being given to any entity that may abuse or misuse it. This invention is agnostic with respect to any particular security model.

RRemCon is an abstract base class for session types for the client side of the RemCon server. It is used to provide server heap failure debugging APIs in debug builds of the system only. These are not detailed here. The following APIs are available from instances of derived concrete classes.

Returns the version of the RemCon server. This API is the only one apart from Close that can be called before Connect.

This is the standard session handle connection method. If handle creation is successful a further IPC call is made to the RemCon server to set the type of the client as either target or controller.

When a target client sends a response it is sent on the bearer which transported the original command. This addressing is carried out by RemCon itself. aInterfaceUid contains the UID of the interface core or extension to which the message belongs. aOperationId is the ID of the operation within that interface. aData is any associated data. If the client is a target i.e. sending a response and RemCon server does not remember having delivered a corresponding command to this client the client will be panicked.

On completion aNumRemotes contains the number of remotes the message was sent to. If the message is a response or from a connection oriented controller this will be 1 on success and 0 on failure. If the client is a connectionless controller then aNumRemotes indicates of the remotes the TSP requested the command be sent to how many succeeded at the bearer level . Note that the TSP may say to send the command to 0 remotes. This is not considered as an error but as a success case.

Targets effectively receive commands from all bearers subject to the TSP mechanism. Controller clients have responses delivered to them by virtue of RemCon remembering the controller which originated each command and the connection s over which a command went out.

TRemConAddress indicates the bearer by its implementation UID and bearer specific connection information. If a connection is in the array then it exists as a bearer level connection in RemCon. If it does not exist in the array then it does not exist as a bearer level connection in the system. No other state is relevant. On success the client is responsible for destroying the items in the queue.

Notification for changes to the state of the bearer connections. On completion the client preferably uses GetConnections to examine the actual connections.

Makes the controller connection oriented using the given address. This address is used to send all commands from this session and all responses will come from this remote or be generated by the corresponding bearer . Provided that there are no security related problems with the client RemCon completes GoConnectionOriented accordingly. This is the only security check that RemCon itself does and it is all that stands between a connection oriented client and a bearer. Each command is also permitted by the TSP at send time.

Makes the controller connectionless using the given remote. The TSP will be used to address each command sent.

A controller client may call this API to attempt to create a bearer level connection using the TRemConAddress previously registered with GoConnectionOriented. This API can only be used by connection oriented controllers.

A controller client may call this API to attempt to destroy a bearer level connection using the TRemConAddress previously registered with GoConnectionOriented. This API can only be used by connection oriented controllers.

This is a simple type wrapping a UID the bearer s implementation UID and a narrow buffer to hold the bearer specific connection information.

This is a concrete class. It owns an RRemConController and an RRemConTarget session and for each an Active Object maintaining a Receive request on the session. It is the heart of the client s interaction with RemCon. Clients instantiate a CRemConInterfaceSelector. Instances of the desired API interfaces are created owned by the CRemConInterfaceSelector. They then open a controller and or a target session through the selector s API and then either a send commands and wait for responses using the interface s or b wait for commands and send responses also using the interface s .

These are called by the intermediate layer when a message of the appropriate type comes in with the interface UID belonging to this instantiation of CRemConInterfaceBase.

The provided component includes a core API outer layer DLL. It provides implementations of CRemConInterfaceBase one for a controller client and one for a target client. It also provides a test extension outer layer DLL to present Song Title and Absolute Volume APIs.

It should be noted that a bearer is not obliged to use converters. It can hard code all its conversion code. However this assumes that the bearer will know how to convert any future API extension. This is perfectly acceptable if the bearer is only going to support an already existing set of messages but for extensibility converters should preferably be used.

Called by the bearer to convert interface specific data interface UID operation ID message type and data to the bearer specific packaged form.

Called by the bearer to convert bearer specific data packaged to interface specific data interfaceUID operation ID message type and data .

Called by RemCon to find out if this converter converts between this interface and this bearer. aInterfaceData is the interface identifier in a bearer specific format.

Then the client must create an instance of the interface which they want to use. For example for an application wishing to act as a target and using the Core API 

MRemConCoreApiTargetObserver has pure virtuals to inform the implementer when various incoming Core API commands are delivered. CRemConCoreApiTarget also has methods to allow the app to send responses to these commands.

The client then needs to create a controller or target session. Only one of each may be created per instance of CRemConInterfaceSelector. Only one target may be connected per client process.

The controller session is opened in connectionless mode any commands sent will be routed by the TSP . To make the controller connection oriented the following may be followed 

The client may wish to bring up a bearer level connection at this time to make the sending of the first command quicker 

In the above example the bearer with implementation UID 0x1020453C is used. This is the test serial bearer. Any commands sent by a connection oriented controller are directed to the specific connection given in this call.

The RemCon server is started in its own process by the connection of the first session controller or target . If the server is already running the session will simply be connected.

First the singleton instance of CRemConServer is created. The first thing this server does after C construction is to register itself with the kernel via StartL using its unique server name. If there is already an instance of the server running due to a race condition triggered by more than one client side attempting to connect StartL will leave and the nascent server will be destroyed cleanly. This ensures that there is only ever at most a single fully instantiated RemCon server in the system.

All of the above actions happen synchronously. From this point on the system is successfully instantiated. Immediately after this CActiveScheduler Start is called in the server startup code and any further actions occur asynchronously. These actions include 

To disconnect from RemCon the client must delete any interface objects and then the interface selector. Closure of the last open session triggers the shutdown of the server.

Whenever a session closes its destructor is called. This unconditionally informs the server of the event which removes any commands belonging to that session from the queues and keeps track of the number of open sessions. If the number of open sessions falls to zero then the shutdown timer is started. When the shutdown timer fires the server terminates itself by calling CActiveScheduler Stop. If any new sessions arrive at any time the shutdown timer is cancelled making sure that the server is not terminated when a session is requested.

When CActiveScheduler Stop is called execution returns to the server startup code after the call to CActiveScheduler Start. The server object is destroyed immediately. The following events also occur in the following order 

Destruction of the server once it has started is irrevocable. If a client tries to connect while server shutdown is occurring the kernel will complete the client s attempt to connect with an error. In this circumstance the client side will then restart the server and again try to connect.

An outgoing command scenario may start with a controller client sending a command using an API provided by an instantiated interface for example 

The Core API translates the Play for example request into a generic operation ID and associated data e.g. play speed . It passes this data to the intermediate layer with its interface UID. The intermediate layer uses its controller session to send the message to the server.

The server examines the controller session. A CRemConMessage is constructed containing the connection address if the controller is connection oriented interface UID operation ID associated data message type command or response and the ID of the originating session.

If the session is a connection oriented controller then this message is placed on the outgoing pending access to the TSP queue and given to the TSP for permission granting. If permission is given the message is placed on the outgoing sent queue and delivered to the correct bearer with the given connection address. The bearer indicates synchronously its acceptance of this request if it errors then the message is removed from the outgoing sent queue. The client s send request is completed immediately. If permission is denied by the TSP then the client s request is completed with KErrPermissionDenied.

If the controller is connectionless then the message is placed on the outgoing pending access to the TSP queue and given to the TSP for possibly asynchronous addressing. When the TSP completes the address request the message is removed from the outgoing pending access to the TSP queue and N copies are inserted on the outgoing sent queue one for each address indicated by the TSP and also sent N times to the correct bearer with the relevant addressing information. Any error up to this point rolls back the queues and errors the client. The purpose of the TSP in this scenario is essentially to populate the connection address field of the message in order for it to be sent.

At some later point a remote may send a response to a command that has been sent. The remote address interface UID and operation ID of the response are checked against the outgoing sent queue. If a matching item is found the source session ID of the originating command is used to address the incoming response to a client controller. If a matching command is not found the response is dropped. The response is used to complete a client Receive request and the outgoing sent queue is cleansed of the command which has now been matched up. It should be noted that the intermediate layer CRemConInterfaceSelector maintains an outstanding Receive request on any connected controllers or targets it has. The incoming pending Receive queue may be used to queue both responses and commands when the client does not have a Receive request outstanding.

On the client side the new response is delivered by the server to a specific controller session. The owning interface selector switches on the interface UID and calls NewResponse on the interface. The interface examines the operation ID and optionally decomposes the associated data and for example calls PlayResponse on the observer the client .

In summary the client makes an asynchronous request to send a command. The request is completed and at a later time the client has PlayResponse called on it.

If the TSP directs a Play command to multiple remotes and they each generate a response PlayResponse will end up being called on the client multiple times.

This scenario starts with a bearer delivering an incoming command to RemCon. RemCon creates a CRemConMessage containing the remote address interface UID operation ID associated data and message type command or response . This message is placed in the incoming pending address queue and sent to the TSP for addressing.

The purpose of the TSP in this scenario is essentially to populate the session ID field of the address. Once this is done the message is removed from the incoming pending address queue and N copies added to the incoming delivered queue and each is delivered to the relevant target client the incoming pending Receive queue may be used if the client does not have a Receive request outstanding when the command arrives at the session. The intermediate layer checks the interface UID forwarding the message to the correct interface object. The interface decomposes the message and calls for instance Play on the client indicating that a Play command has been received.

The client may choose to send a response. It calls PlayResponse which sends a message to RemCon via the intermediate layer s target session. The server checks the incoming delivered queue for commands matching the session ID interface UID and operation ID and uses the remote address of the found command to address the response to the correct bearer. The found command is removed from the queue and destroyed.

A remote control client application may be implemented as follows. This scenario involves implementing a client of the remote control system using the existing remote control APIs.

Firstly it is decided whether the application is for a controller or a target. If it is required to remote control other devices a controller application is required. If it is required to be remote controlled a target application is required. It is permitted to be both a controller and a target at any one time.

If a controller is required is it necessary to know which remote to communicate with and over which bearer. If this information is known then the application may operate in connection oriented mode where the remote control system is explicitly told the bearer and the remote s address. If this information is not known then it is required to operate in connectionless mode the default . In this case commands are routed by the system specifically by the Target Selector Plug in as provided by the device manufacturer.

It is then necessary to decide which APIs are required to be used. The Core API is provided which covers many basic operations including Play Stop etc. TrackInfo and Absolute Volume APIs are also provided but without the lower level implementations required to be able to send and receive such messages over Bluetooth. 

The first step is to create an instance of CRemConInterfaceSelector. This is the heart of the client side owning sessions on the server and interface objects and routing messages between them.

Next an instance of the controller interface of the desired API is created in this example the Core API .

This code assumes that this is an object of a type which implements MRemConCoreApicontrollerObserver. This mixin determines how incoming responses to your commands are delivered. Ownership of cont now resides with sel.

At this point the controller session is connectionless. Any commands sent will be addressed by the TSP. If the bearer and remote which are to be controlled are known then the following code may be used 

Once GoConnectionOrientedL succeeds the application is connection oriented and the controller session is dedicated to communicating with the single remote specified. The TSP does not address specific commands but still permits or denies each command sent. Note that no bearer level connection with the remote is established by this operation.

Once connection oriented to reduce the latency of the first command sent it is possible to explicitly set up a bearer level connection with the remote as follows 

If this is not done the server will attempt to bring up a connection as required when the first and any subsequent command is sent. ConnectBearer is provided as a facility to reduce latency.

It is worth noting that bearer level connections should not be controlled arbitrarily. It is only possible to control the bearer level connection on which the application is currently connection oriented . This is the reason for the lack of a TRemConAddress parameter in ConnectBearer and DisconnectBearer.

It should also be noted that the remote may bring up or down the application connection at its own behest. If a remote pulls down the connection then the next command sent will cause the server to try to pull it back up again. This may entail an unexpected delay. If the re connection fails the send will be failed. Despite all this the application will remain connection oriented orientation of connection is independent of any actual bearer level connection.

If the state of connection at the bearer level is considered of interest the following APIs on CRemConInterfaceSelector may be used 

GetConnections supplies all the currently extant connections in the system. NotifyConnectionsChange just indicates when that set has changed.

Only one command send can be outstanding at any time. If a connectionless controller is being implemented the TSP may have addressed the command to multiple remotes. In this case a single command send may result in multiple responses and these are filtered or used as considered appropriate.

If the TSP has sent the command to multiple remotes and one or more of those sends fails an error value will be provided from one of the failed sends. The number of remotes to which the command was successfully sent is also provided. Bearers are obliged to give back a response to each command they send. Depending on the bearer this response may or may not have actually come from the remote. A send either succeeds or fails at the bearer level either the bearer takes responsibility for sending or it does not. Hence even a successful send may not actually result in a transmission to the required remote.

Note that each command sent to a remote involves memory being allocated in the server s heap which is only released on client closure or when a response is received. If there is good reason to believe that any remote for which communication is not required is no longer present then it is preferably arranged to stop sending commands to that remote in order to reduce the load on the memory in the server.

To clean up the involvement in the remote control system all outstanding asynchronous requests should be cancelled and the interface selector should be deleted.

This is very similar to the controller setup except that there is no concept of connection orientation. Targets implement a mixin through which the interface selector delivers incoming commands and instantiates an object to send responses. All incoming commands are addressed by the TSP. Outgoing responses are addressed implicitly to the remote from which the originating command came.

Only one response can be outstanding at any time. If commands come in quickly it is necessary to queue responses to them. However it should be remembered that each command delivered to a target involves memory allocated in the server s heap which is only released on client closure or when a response is sent.

To clean up involvement in the remote control system all outstanding asynchronous requests should be cancelled and the interface selector should be deleted.

To implement a new API two pieces of work need to be undertaken the creation of an outer layer DLL and the creation of a family of converters.

When a client sends a message using an outer layer DLL a bearer receives the following information the UID of the API the message came from the operation ID of the message and a descriptor containing any operation specific data. It is the job of the converter to convert between the data format in the operation specific data and the format required by the bearer.

The Converter API is in remotecontrol converterplug in public but actually include from epoc32 include remcon . The Core Serial converter is in remotecontrol test converters Core Serial.

Following the pattern established in the Core Serial converter a new implementation UID should be allocated for the converter implementing the Converter API as an ECOM plug in.

CRemConConverterPlug in SupportedUids const TUid aInterfaceUid const TUid aBearerUid should be implemented in order to determine whether or not conversion of message formats between the given API and the given bearer are supported.

CRemConConverterPlug in SupportedInterface const TDesC8 aInterfaceData const TUid aBeareruid is then implemented to answer the same support question except posed in a slightly different way. In this case the API is identified by a package in the format of the given bearer. The remaining converter implementation is relatively straightforward.

Converters are stateless synchronous data processing machines. To do the conversion the converter has to know the operation IDs of the API and the API s UID.

However a bearer must explicitly request the help of a converter to understand a message. If the bearer does not then no converter will be invoked the bearer is essentially closed to APIs beyond those it already knows how to do the conversion for. This may be perfectly valid depending on the bearer.

If however a new API is being implemented a converter must be provided for each existing bearer. If this information is not provided then the framework is effectively failing to inform a bearer of how to convert messages between its format and the format of the new API in essence this is tantamount to saying that the new API cannot be used over that particular bearer. This too may be fine depending on the particular framework requirements.

A converter needs not only formatting information published by the API but also formatting information from the bearer. In the nature of things however bearer formats are more likely to exist as published specifications e.g. AVRCP than are proprietary remote control APIs.

It should be remembered that if the TSP gives a command to client X then it is effectively empowering client X to send precisely one response over the bearer which delivered the originating command.

The bearer API is connection oriented. All messages sent and delivered are associated either with a specific recipient address or a specific sender address. The server is responsible for bringing up a bearer level connection to a particular remote before issuing a bearer level send to that remote.

Real bearers may not in fact be connection oriented. For example the test serial bearer simply works over a serial cable. Therefore a it has no bearer specific remote address format so remote addresses simply consist of the serial bearer s UID and b it has to emulate connection oriented behaviour by indicating an incoming connection essentially on start up when it first opens the serial port. This connection never goes down.

Bearers are instantiated at server start up time and should immediately start listening for incoming connections. Each connection is indicated up to the server.

It can be seen from the above description that the present invention provides a generic remote control framework which provides significant advantages over current non generic frameworks including 

Although the present invention has been described with reference to particular embodiments it will be appreciated that modifications may be effected whilst remaining within the scope of the present invention as defined by the appended claims.

One possible example of such a modification of this invention is applicable to a computing device with multiple audio applications all of which have registered to receive remote control commands. Such a device with multiple audio applications may comprise a mobile telephone with many multimedia applications capable of playing audio data such as an MP3 player a radio a browser plug in which can play streamed audio from the internet a voice memo or dictation application and a local voicemail store.

Where all of these applications have registered to receive remote control commands this embodiment would enable correct delivery of such commands in the case where one application was already playing audio by enabling the remote control manager to deliver remote control commands on such a device to the application which is already playing audio.

