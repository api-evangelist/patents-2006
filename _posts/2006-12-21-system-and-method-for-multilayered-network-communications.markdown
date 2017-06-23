---

title: System and method for multi-layered network communications
abstract: A multi-layered network for transporting data comprises a first network layer that provides a first session topology, and a second network layer that provides a second session topology. The second network layer uses the first network layer to transport data. In one embodiment of the invention, the data sent by the second layer is real-time audio data, such as voice. Each session topology may be either peer-to-peer or client/server. The first and second layers may have different topologies and/or different session hosts. A deterministic algorithm is provided whereby a new session host is selected when the current host leaves the session.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07730206&OS=07730206&RS=07730206
owner: Microsoft Corporation
number: 07730206
owner_city: Redmond
owner_country: US
publication_date: 20061221
---
This application is a continuation of U.S. patent application Ser. No. 09 800 394 entitled System and Method for Multi Layered Network Communication filed on Mar. 6 2001 which claims the benefit of U.S. Provisional Application No. 60 187 511 entitled DirectPlay Voice For DirectX 8.0 filed on Mar. 7 2000 both of which are hereby incorporated by reference.

The present invention relates generally to the field of computer networking. More particularly the invention provides an audio engine which sends audio or other data using a transport layer and which creates and dynamically morphs an audio session whose topology is independent of the underlying transport layer s session topology.

The world wide increase in computer networking bandwidth has enabled large amounts of data to be transmitted quickly and at low cost. The availability of great bandwidth has invited the creation of applications that communicate data in quantities that were previously thought to be too costly or too cumbersome. One such application is real time voice transmission. The notion of carrying on a video conference or a video game between participants in different cities around the world was once unheard of. Today applications that permit such activities are available as a cutting edge technology soon such applications and the devices that support them will become commonplace. However such applications require the transmission of real time voice over a data network and such voice transmission presents various problems.

First network topologies are constantly evolving. Traditionally network communication has used a client server model in which one network node the server is the focal point for all communication from a group of other nodes the clients the clients communicate with the server but do not communicate with each other. The client server model is in some contexts giving way to a federated or peer to peer model in which each node can communicate directly with any other node or at least in which the network provides a level of abstraction that makes it appear to each node as if such communication is possible . A voice transport that is dependent upon one model may not work in an environment that is dependent upon another model.

Second the networks that provide the underlying data transport are constantly evolving as well. For example data may be transmitted over a telephone line Digital Subscriber Line DSL cable Ethernet etc. Each type of connection may use different protocol. Networks are typically built in layers each of which provides its own protocol that may be used on top of another layer. As future communication technologies become more widespread e.g. wireless data networking satellite networking etc. these technologies may have their own peculiarities. If voice transport is dependent upon any protocol structure of network layers or underlying communications medium it cannot easily be adapted to future technologies or even to the multitude of presently available communication technologies.

Third conventional voice networking implementations require a fixed host for the voice session and if the host leaves the session the session cannot continue which results in termination of the session.

While systems exist that either support real time voice communication or can be adapted to do so e.g. NetMeeting Hear Me Net 2 Phone AOL Messenger applications based on the H.323 suite of protocols they do not address the drawbacks discussed above. Thus in view of the foregoing there is a need for a networking system that overcomes the drawbacks of the prior art.

The present invention provides a communication architecture that transports voice using any network or combination of network layers that supports both guaranteed and non guaranteed messaging. The voice transport system of the present invention supports various topologies for digital voice communication. For example a voice transport system in accordance with the invention may support a peer to peer b forwarding c mixing and d echo. Additionally the invention supports all of these voice topologies regardless of whether the underlying session transport layer used to transport voice packets employs a client server or peer to peer topology for data delivery.

A voice transport system in accordance with the invention packages voice data into frames and provides the frames to an underlying data network for delivery. For example the voice transport system may deliver data using the DirectPlay networking protocol which is part of the DirectX application programming interface provided by Microsoft Corporation of Redmond Wash. The voice transport system provides a protocol that enables voice connections and communications to take place on top of such a data network.

The protocol includes a connection process a disconnection process a format for the transmission of voice data a host migration process and a set of general messages used during a voice session. The connection process includes the exchange of a set of messages that permits a node to join a voice session provided that the joining node has a connection in the underlying transport. The disconnection process includes the exchange of a set of messages that permits a node to leave a voice session. The voice transmission format includes a voice packet header with a variety of message types.

The host migration process is used to change the host of a voice session e.g. if the current host has left the session. The host is the primary keeper of the name table in a peer to peer session. When such a host leaves a voice session a new host must be selected in order for the session to continue. Each node in a session has a host order ID which may be assigned at the time the node joins the session. At the time that a host leaves the session it runs a host migration election algorithm to determine whether there is any node that can take over as host. If there is no such node the host sends a session lost message which tells any node in the process of connecting that the host is leaving. If there is a node that can take over as host the host sends a host migrate leave message. In response all nodes run the host selection algorithm. The new host discovers that it is in fact the new host by running the algorithm. Once the new host discovers that it is the new host it sends a host migrated message to all other nodes to notify those nodes that it is the new host. The other nodes respond with a confirmation message.

Communication between the voice layer and the session transport layer is provided by a set of application programmer interfaces APIs . The transport layer exposes an API which is callable by the voice layer. The voice layer calls this API in order to send and receive data over the session transport layer. The voice layer exposes an API which is used by the session transport layer to notify the voice layer of events e.g. the entry or exit of a node from the session transport layer.

One exemplary application of the invention is voice messaging in a multi player game where the different players are connected by a data network such as the Internet. The different player machines may use a session transport layer to communicate various information with each other e.g. the position of the player in the playing domain and the voice transport layer may use the session transport layer to transmit voice packets during the game e.g. a player uses a microphone to send a voice message to other players which is transmitted by the voice layer over the session transport layer . However it will be appreciated that the invention may be used in any context in which real time voice communication is desirable particularly those contexts in which voice data is transmitted together with other types of data e.g. video conferencing virtual meetings telephony etc. It should also be appreciated that digital voice is merely a type of data and the architecture of the present invention may be used to transport any type of data whether or not such data is voice or even audio.

Networks are built in layers. One layer of a typical network is a basic data delivery protocol such as the User Datagram Protocol UDP . A next second layer may be a transport protocol which provides such features as session management and guaranteed delivery. The second layer provides these features by performing various bookkeeping tasks e.g. keeping track of which nodes are current members of a session and by using the first layer to send administrative data between the nodes. In some applications it may be useful to provide a third layer. For example the second layer may perform general data transport and the third layer may be an audio engine which collects audio data e.g. with a microphone packages the audio data and uses the second layer to perform the actual sending and receiving of audio data. The third layer may provide its own protocol and or networking features. For example the third layer may provide audio sessions that can be connected to disconnected from hosted configured etc. independently of any sessions that may exist on the second layer. The present invention provides a protocol for such a third layer as well as various techniques used in the course of operating such a layer.

The invention is operational with numerous other general purpose or special purpose computing system environments or configurations. Examples of well known computing systems environments and or configurations that may be suitable for use with the invention include but are not limited to personal computers server computers hand held or laptop devices multiprocessor systems microprocessor based systems set top boxes programmable consumer electronics network PCs minicomputers mainframe computers distributed computing environments that include any of the above systems or devices and the like.

The invention may be described in the general context of computer executable instructions such as program modules being executed by a computer. Generally program modules include routines programs objects components data structures etc. that perform particular tasks or implement particular abstract data types. The invention may also be practiced in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network or other data transmission medium. In a distributed computing environment program modules and other data may be located in both local and remote computer storage media including memory storage devices.

With reference to an exemplary system for implementing the invention includes a general purpose computing device in the form of a computer . Components of computer may include but are not limited to a processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit . The system bus may be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of bus architectures. By way of example and not limitation such architectures include Industry Standard Architecture ISA bus Micro Channel Architecture MCA bus Enhanced ISA EISA bus Video Electronics Standards Association VESA local bus and Peripheral Component Interconnect PCI bus also known as Mezzanine bus .

Computer typically includes a variety of computer readable media. Computer readable media can be any available media that can be accessed by computer and includes both volatile and nonvolatile media removable and non removable media. By way of example and not limitation computer readable media may comprise computer storage media and communication media. Computer storage media includes both volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical disk storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can accessed by computer . Communication media typically embodies computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media. The term modulated data signal means a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above should also be included within the scope of computer readable media.

The system memory includes computer storage media in the form of volatile and or nonvolatile memory such as read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help to transfer information between elements within computer such as during start up is typically stored in ROM . RAM typically contains data and or program modules that are immediately accessible to and or presently being operated on by processing unit . By way of example and not limitation illustrates operating system application programs other program modules and program data .

The computer may also include other removable non removable volatile nonvolatile computer storage media. By way of example only illustrates a hard disk drive that reads from or writes to non removable nonvolatile magnetic media a magnetic disk drive that reads from or writes to a removable nonvolatile magnetic disk and an optical disk drive that reads from or writes to a removable nonvolatile optical disk such as a CD ROM or other optical media. Other removable non removable volatile nonvolatile computer storage media that can be used in the exemplary operating environment include but are not limited to magnetic tape cassettes flash memory cards digital versatile disks digital video tape solid state RAM solid state ROM and the like. The hard disk drive is typically connected to the system bus through an non removable memory interface such as interface and magnetic disk drive and optical disk drive are typically connected to the system bus by a removable memory interface such as interface .

The drives and their associated computer storage media discussed above and illustrated in provide storage of computer readable instructions data structures program modules and other data for the computer . In for example hard disk drive is illustrated as storing operating system application programs other program modules and program data . Note that these components can either be the same as or different from operating system application programs other program modules and program data . Operating system application programs other program modules and program data are given different numbers here to illustrate that at a minimum they are different copies. A user may enter commands and information into the computer through input devices such as a keyboard and pointing device commonly referred to as a mouse trackball or touch pad. An audio input device such as microphone may be provided. Other input devices not shown may include a joystick game pad satellite dish scanner or the like. These and other input devices are often connected to the processing unit through a user input interface that is coupled to the system bus but may be connected by other interface and bus structures such as a parallel port game port or a universal serial bus USB . A monitor or other type of display device is also connected to the system bus via an interface such as a video interface . In addition to the monitor computers may also include other peripheral output devices such as speakers and printer which may be connected through an output peripheral interface .

The computer may operate in a networked environment using logical connections to one or more remote computers such as a remote computer . The remote computer may be a personal computer a server a router a network PC a peer device or other common network node and typically includes many or all of the elements described above relative to the computer although only a memory storage device has been illustrated in . The logical connections depicted in include a local area network LAN and a wide area network WAN but may also include other networks. Such networking environments are commonplace in offices enterprise wide computer networks intranets and the Internet.

When used in a LAN networking environment the computer is connected to the LAN through a network interface or adapter . When used in a WAN networking environment the computer typically includes a modem or other means for establishing communications over the WAN such as the Internet. The modem which may be internal or external may be connected to the system bus via the user input interface or other appropriate mechanism. In a networked environment program modules depicted relative to the computer or portions thereof may be stored in the remote memory storage device. By way of example and not limitation illustrates remote application programs as residing on memory device . It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used.

As described above in connection with two or more computing devices may communicate with each other via a computer network. For example shows computing devices and communicatively coupled by inter alia wide area network . As previously noted wide area network may comprise the Internet. A computer network such as wide area network may be built in layers. shows an example of a network that is built in layers.

In the example of wide area network comprises various layers including layers and . Layer is the basic network layer that provides a delivery protocol allowing data to be delivered over network . Layer uses layer to provide actual data delivery but layer provides some level of abstraction beyond mere data delivery. For example layer may implement one or more networking abstractions. As one non limiting example layer may be a session transport layer that supports the networking model of a session i.e. two nodes can communicate if they are in the same session. In this case layer provides the function of allowing nodes to connect to or disconnect from a session as well as generating and sending between nodes the administrative data that supports the model of a session. However layer employs layer to provide the actual data delivery. That is when layer receives data to be sent from one node to another it packages the data and provides the package to layer with instructions to deliver the package to a specified destination as indicated by arrow . Likewise when layer generates administrative data that supports say the session concept e.g. requests to connect or disconnect from a session dropped session signals etc. layer provides such messages to layer for delivery to their destinations.

Exemplary network includes a third layer which may for example be a session presentation layer that provides an additional level of networking abstraction on top of layer . In the present example layer provides basic data delivery layer supports the model of sessions between nodes and layer may provide support for say audio delivery. For example layer may receive live audio e.g. a human voice from a microphone attached to a computing device in the form of a digital signal for delivery to a particular node on the network. In this case layer may package the audio into frames as it is captured and provide the frames to layer for delivery to a destination node in the session provided by layer as indicated by arrow . As discussed below layer may provide its own sessions independently of the session that layer provides. When layer receives the packaged audio frame it uses layer to provide the actual delivery of the data in the frames. When data is received at the receiving node the data may be unpackaged by each of the successive layers. That is when a package is received at the receiving node layer unpackages the contents and provides the contents to layer as indicated by arrow . In the case where the package contents is actually a second package to be process by layer layer further unwraps this second package and provides the second package s contents to layer as indicated by arrow .

In one example layer is a basic data delivery protocol that is capable of providing at least non guaranteed packet delivery. A non limiting example of such a protocol is the User Datagram Protocol UDP although it will be appreciated that layer may comprise any data delivery protocol. Moreover layers and may include any protocol that provides any sort of networking abstraction beyond basic data delivery. For example layer may be a protocol that handles all data delivery between players computing devices in multi player games. Moreover these multi player games may allow players to exchange data with each other and layer may support a voice communication facility that packages digital audio data captured by the respective players microphones and transmits the digital audio data using layer . While depicts network having three layers it will be appreciated that three layers are merely exemplary and a network may have any number of layers.

Data is first delivered to layer which wraps data in package . For example if layer is an audio networking layer then data may be digital audio data captured by a microphone as noted above. Layer wraps a frame of audio data into package and provides package to layer . Layer in turn wraps package into package and provides package to layer . Layer then wraps package into package . The result is the series of nested packages shown in .

The nesting of packages may be accomplished by each layer s appending its own header to data as shown in . For example when raw data is provided to layer layer appends header thereby producing a package that contains header followed by data . When layer provides the package to layer layer appends header thereby producing a package that contains header followed by header . Layer then provides the package to layer layer appends header thereby producing a package that contains header followed by header followed by header followed by data . When the data is transported to its destination the headers may be stripped in reverse order i.e. layer receives a package with headers and strips header and provides the resulting package i.e. a package with headers and to layer and so on. The top level then strips the last header to yield data . It should be understood that the reference to headers and is merely exemplary as each layer may append data to the package in any manner regardless of whether such data is a header. For example one or more of the layers may append data to the end of the package as a footer. 

Networks may provide sessions having various topologies. Examples of such topologies are peer to peer and client server. In a peer to peer topology each node in a session can communicate directly with each other node in the session. One node in the session may be designated as a host. The host maintains a name table of all the nodes in the session. Like a peer to peer session a client server session also has a host. However in a client server session each client node can communicate directly only with the host or server . Any message from one client node to another is routed through the host.

A session transport layer may provide a session topology such as the peer to peer topology depicted in or the client server topology depicted in . For example layer shown in may implement a client server topology wherein every node in a session communicates with every other node through a host. In this case layer may use layer to communicate data from a client node to the host. For example if client node shown in uses layer to send data to client node then layer uses layer to send the data from client node to host node . The layer logic at host node receives the data and delivers it to layer . Layer at host node determines that the data is destined for client node e.g. the destination information may be in the layer header attached to the data . Layer at host node provides the data to layer for delivery to client node .

Alternatively layer may implement a peer to peer session topology. In this case layer uses layer to send data directly from the source node to the destination node without routing each message through the host.

Just as a session transport layer may provide a session having a particular topology as shown in an audio layer may also provide an audio session having a topology. As discussed above in connection with inasmuch as audio is merely a type of data a network may provide an audio layer e.g. layer on top of a session transport layer e.g. layer . That is the audio layer may provide various functionality for processing audio but may use the session transport layer to send the audio data. Moreover the audio layer may provide a session that is independent of the data transport session the audio layer session may have a topology that differs from the topology of the underlying data transport session. show examples of audio session topologies.

An audio network layer may be built on top of a session transport layer. For example an audio layer may provide any or all of the audio session topologies depicted in and may then use a session transport layer to send the audio data to the other nodes in the audio session. With reference to the layer model shown in and discussed above the audio layer may for example correspond to layer while the session transport layer may correspond to layer . Moreover the session transport layer may have a session topology that differs from and is independent of the audio layer. For example the audio layer may provide a peer to peer session topology depicted in while the session transport layer provides a client server session topology depicted in . In a preferred embodiment of the invention an audio layer having any of the session topologies shown in may be built on top of a session transport layer that has any of the session topologies shown in .

Suppose for example that node A sends audio data to node B . Since the audio session is client server with node as the host node can send directly only to node within the audio session. As noted above the underlying transport session is a peer to peer session which does permit node to communicate directly with node however from the perspective of the audio layer node is not directly addressable from node . Thus audio layer provides the audio data to the transport layer with instructions to deliver the data to node . The data may be packaged with a header that indicates that node is to forward the data to node . It will be observed that the transport layer is configured to deliver data directly from node to node but the audio layer is not configured to communicate in this manner. Thus when the transport layer receives the data it simply delivers the data to node as it has been requested to do by the audio layer. It should further be observed that the transport layer s delivery of the data from node to is performed in accordance with the transport layer s topology. In this example the transport layer is peer to peer and thus supports direct communication between any nodes in the session. In another example the transport session could be client server where node is the host of the transport session. In such a case the transport layer would fulfill delivery of the data provided by the audio layer by sending the data through the host node this is another example of how transport layer sends data in accordance with the transport layer s topology.

The ability of the audio layer to support a session model e.g. client server in this example without concern as to how the data actually gets delivered demonstrates the generality and flexibility provided by building one network layer on top of another. In a preferred embodiment of the invention an audio layer having any session topology may work with a session transport layer having any session topology. That is the session topology of the audio layer may be selected without regard to the session topology of the underlying transport.

The audio layer ID is a number used to identify the node in audio layer . Transport layer and audio layer may have different identifiers for the same node but transport layer s identifier for a particular node is not known to audio layer . Transport layer maintains a table that correlates transport session IDs with audio session IDs. The host order ID is a number that is used by an exemplary host migration algorithm discussed below in order to elect the new host of a session if the existing host leaves the session.

As discussed above an audio layer may be built on top of a session transport layer. One exemplary use of such a multi layered structure is in the case of multi player games where the different players communicate with each other over a computer network. For example a game may employ a session transport layer to communicate basic information about the game e.g. player position player score players entering and leaving the game etc. . Such a game may also employ an audio layer to support voice communication between the players. In other words the audio layer may collect audio data e.g. through the players microphones and use the session transport layer to transport that audio data to other players. An example of such a multi layered system is the DirectX application programming interface API provided by Microsoft Corporation. The DirectX API provides a data communication API that supports data communication between players in multi player games. The data communications API uses a protocol that facilitates communication between players machines over various different types of network connections. Moreover the DirectX API also provides a voice communication API that supports voice communication between players and that uses the data communication protocol to transport voice data between players. This is an example of a voice layer being built on top of a session transport layer. It will be understood that the DirectX API as well as gaming environment are merely exemplary. The invention applies to any application in which it may be useful transport both audio and other types of data between nodes in a network whether or not such application is a game. Moreover the DirextX API is merely one example of a system that supports an audio layer built on top of a session transport layer.

An exemplary protocol for an audio layer includes five aspects 1 connection 2 disconnection 3 transmission of audio data 4 general messages and 5 host migration. These aspects of the exemplary audio layer protocol are described below.

Connection is the process by which a client node connects to an audio session. Preferably the client is connected to a session in the underlying transport before connecting to the audio session i.e. the transport is a member of the underlying data layer session that is used to transport audio data . Messages sent during the connection process are sent by guaranteed delivery.

An exemplary process for connecting to a session is shown in . A client node initiates the connection process block by sending a connection request CONREQ message to all other nodes in the session. If the session is a client server session then the CONREQ message is sent to the host since it is only possible for a non host node to send to the host in a client server session. . If the client does not hear a response from the host within a timeout period then the client re sends the CONREQ message. Preferably the CONREQ message contains the protocol version of the client.

The host after receiving the CONREQ message block responds with a connection accept CONACCEPT message if the client is allowed to connect. Preferably the CONACCEPT message contains a compression type used for the session session type session flags and protocol version. If the client is to be denied the connection a connection reject message is sent from the server to the client which describes the reason the client was denied the connection. For example a client may be denied a connection if its protocol version is incompatible with the audio session or if the host encounters an internal error. Receipt of a connection reject message causes the client to discontinue the attempt to connect to the session.

The client upon receiving the CONACCEPT message attempts to initialize itself using the settings specified in the CONREQ message block . If the client cannot initialize itself with the given settings e.g. the protocol version is not compatible or the client does not have the specified compression type then it discontinues its connection attempt. If the client is successful in initializing itself with the given settings it responds to the server with a confirmation SETTINGSCONFIRM message. The SETTINGSCONFIRM message preferably contains configuration information about the client.

The server upon receiving the SETTINGSCONFIRM message block adds the newly connected client to the list of members in the audio session e.g. by adding the newly connected client to the name table. If the audio session is peer to peer then the host sends all the clients in the session a message to that effect. In the example of where the audio session is a voice communication session for a multi player game the message is labeled PLAYERJOIN . It will be understood however that audio sessions are not limited to the gaming context where clients are players. Any message that indicates that a new client has joined the audio session regardless of whether the new client is a player may be used without departing from the spirit and scope of the invention. The exemplary PLAYERJOIN message preferably contains information about the newly connected client including their host order ID described below in connection with host migration configuration information and an audio session ID. The audio session ID is a numeric identifier given to the audio protocol by the transport it is using e.g. the session transport layer used by the voice layer may assign an audio session ID to each client that joins the audio session . The audio session ID is used to uniquely identify a client within the audio session. The other clients in the audio session receive the PLAYERJOIN message and update their local list of clients e.g. their local copy of the name table to include the newly connected client block .

If the session is peer to peer the server then sends a NAMETABLE message to the client. The NAMETABLE message contains a list of the clients who are currently in the audio session including configuration information about those clients host order ID and audio session Ids for each node in the session . Receipt of the NAMETABLE message finalizes the new client s connection to the session block . In the case where the audio session has a client server topology a NAMETABLE message is typically not sent to the newly connected client since clients generally do not store a copy of the name table in client server topologies.

Disconnection is the process by which a client node that is a member of an audio session disconnects from that session. All messages related to the disconnection process are preferably sent by guaranteed delivery.

An exemplary disconnection process is shown in . A client node initiates the process of disconnecting from an audio session by sending the host a disconnection request DISCONNECTREQ message block which is received by the host block . If the session is peer to peer then the host sends the other clients in the session a message indicating that the client is disconnecting from the session. In the example of where the audio session is a voice session between players in a multi player game the message that is sent to the other clients in the session is labeled PLAYERQUIT. However it will be understood that this label is merely exemplary and any message may be sent which indicates to other members of the session that the disconnecting client is leaving the session. The exemplary PLAYERQUIT message preferably contains a reason code for the disconnection as well as the audio session ID of the disconnecting client. For example the reason code may indicate success in the case where a client leaves the session upon its own request. However if the client disconnects abnormally in a peer to peer session then the host sends all of the other clients in the session a PLAYERQUIT message with a reason code indicating connection lost. Upon receiving the PLAYERQUIT message block the other clients in the audio session delete the disconnecting client from their respective local copies of the name table

Upon receiving the DISCONNECTREQ message from the disconnecting client the host responds to the disconnecting client with a confirmation message DISCONNECTCONFIRM . Once the client receives the DISCONNECTCONFIRM message it is disconnected from the voice session block . It should be noted that if a server receives a DISCONNECTREQ message from any client it responds with a DISCONNECTCONFIRM message regardless of whether it knows about the client. This is to handle a condition where the host leaves the session after a client has sent a DISCONNECTREQ.

Audio data is transmitted from one member of an audio session to another in the form of an audio packet. shows an exemplary format for an audio packet . Audio packet comprises a header followed by a frame of audio data . In a preferred embodiment of the invention audio data is compressed although it should be appreciated that an audio packet may contain uncompressed audio. Header comprises fields for audio packet type message number and sequence number .

The audio packet type contained in field indicates the packet type from among several types of packets. Preferably the packet type is one of the following 

Message number indicates which message an audio packet is a part of. Messages may be delimited in various ways. In the case where the audio data to be transmitted over a network is speech a message may for example be defined as a single sequence of unbroken speech the current message ends when the speaker pauses and a new message begins when the speaker resumes speaking. When messages are delimited by pauses one optimization that may reduce the number of messages transmitted is to allow a message to contain a pre determined number of pauses or to require that a pause be a minimum duration e.g. one second although the optimal duration depends on the type of compression used. Each delimited message is assigned a message number typically in a sequence where the first message is number zero. A message may be transmitted in more than one packet each packet that contains audio data from a given message includes that message s number in message number field .

Sequence number indicates a packet s position in the sequence of packets used to transmit a message. Each packet in a message is assigned a sequence number which is included in header of audio packet . Thus when a message is transmitted using more than one packet sequence number can be used to reconstruct a voice message from its component packets. Sequence numbers preferably start at zero for the first packet in a voice message and increment by one for each subsequent packet. Sequence numbers may wrap after a certain value has been reached.

Audio data may be lost received out of order or duplicate packets may be received. The data in packet header e.g. message number and sequence number allows a voice engine to handle all of these cases.

A protocol for an audio layer may include a miscellaneous set of messages as described below. These messages support various housekeeping tasks in the functioning of the audio layer 

As previously described every session has a host. When a host leaves the session another node in the session must become the host. Host migration is the process by which another node becomes the host when the host leaves the session. The host migration technique provided by the invention uses a host election algorithm. The host election algorithm deterministically identifies a host based on which nodes are in a session. The premise of using a host election algorithm is that every node in a session uses the same algorithm and thus each node in the session acting independently can identify the same host by running the host election algorithm.

In response to receiving the message sent at step each of the remaining clients runs the host election algorithm step . As noted above since each client uses the same host election algorithm each client will independently identify the same node as the new host. In one example each node is assigned a host order ID at the time the node joins the session. Such a host order ID is a sequence number that indicates the node s order of preference to become the host. Thus the host election algorithm may be to use the node having the lowest host order ID among all of the nodes that remain in the session. It will be understood however that using a host order ID in this manner is merely exemplary and any host election algorithm that deterministically identifies the host may be used without departing from the spirit and scope of the invention.

At step the node that has been identified as the new host by the host election algorithm sends the other remaining nodes a message indicating that it is ready to take over as the new host. At step the remaining non host nodes send the host a message in order to confirm their presence.

In host is disconnected from the session and nodes and run the host election algorithm. The host election algorithm selects the new host e.g. by selecting the remaining node with the lowest host order ID. The new host discovers that it is the new host by running this algorithm. In the example of node is the newly elected host.

In new host has initialized itself as host and sends a message HOSTMIGRATED to the remaining non host nodes and to indicate that it is ready to be the new host.

In the clients have received the HOSTMIGRATED message and respond with a SETTINGSCONFIRM message. The SETTINGSCONFIRM message is similar to the SETTINGSCONFIRM message discussed above and shown in in relation to the connection process. However where the SETTINGSCONFIRM message is issued during host migration by a client who is already in the session the client s SETTINGSCONFIRM message includes the client s host order ID which indicates to the new host that the new host should not assign a new host order ID to the existing client node. The host then runs the portion of the connection process that begins as step shown in FIG. i.e. by issuing PLAYERJOIN and NAMETABLE messages. If a client is connecting during a host migration process the new client re sends its SETTINGSCONFIRM message to the newly elected host this allows a client to connect even if the host changes during the connection. Any new clients who connect after a host migration are given a host order ID that is offset by the client s host order ID when it was elected. The purpose of using an offset value is to ensure that newly added session members are always assigned higher host order IDs than nodes that are already in the session. Thus the offset from the current host s host order ID is chosen to be large enough so that it is unlikely that a newly assigned host order ID will be lower than any existing host order ID in the session.

Audio layer includes a protocol engine one or more data queues and a name table . Protocol engine contains the functionality to engage in the various aspects of the protocol for an audio layer as described above. For example protocol engine generates and receives the various messages related to connection disconnection host migration etc. Data e.g. audio data captured with a microphone is provided to protocol engine for delivery to other nodes in an audio session. Name table includes a list of members of an audio session as described above in connection with . Data queue s buffer data received from other nodes so that such data may be rendered over a sound rendering system. Audio layer exposes an API which in the example of is named IDirectPlayVoiceNotify. API is called by transport layer to communicate events e.g. the arrival of data to audio layer

Session transport layer is a data transport which is used by audio layer to send and receive audio data and audio session data as described above. Session transport layer exposes an API which in the example of is named IDirectPlayVoiceTransport. Audio layer uses session transport layer by calling API . For example Audio layer may call a method in API in order to provide session transport layer with a frame of audio data to be sent to another node.

The IDirectPlayVoiceNotify interface e.g. API implemented by audio layer contains methods to allow session transport layer to inform audio layer when important transport level events occur. The types of events that can be generated are described below 

When these events occur data transport layer calls into audio layer through the IDirectPlayVoiceNotify NotifyEvent function. Audio layer then handles the event and returns.

Additionally the IDirectPlayVoiceNotify interface is used to inform audio layer that data has arrived that it is audio layer specific. The session transport layer strips any transport specific headers footers from the audio data before giving it to audio layer . This result is that audio layer does not have to perform any additional processing to determine the contents of a data packet. The DirectPlayVoice API described below in Appendix A provides an implementation of the specified interface.

The IDirectPlayVoiceTransport API e.g. API preferably provides the following functions to the voice engine 

To support this interface i.e. API session transport layer preferably meets the following requirements 

If these requirements are met then the session transport layer can implement the IDirectPlayVoiceTransport interface and the audio layer will run on the transport. The DirectPlayVoice API described below in Appendix A supports this interface.

In order to start using the interfaces the audio layer and transport layer must be linked. To perform the link the audio layer must first be given a pointer to the transport layer interface. Give the pointer the audio layer queries the transport layer preferably using COM to retrieve the transport layer s IDirectPlayVoiceTransport interface. It then calls the IDirectPlayVoiceTransport Advise method which passes transport layer a pointer to audio layer . The transport layer then queries the audio layer using COM to retrieve the audio layer s IDirectPlayVoiceNotify interface. Once this process is complete the two layers are linked and communication can begin. When the audio layer wishes to disconnect from the transport layer it uses the IDirectPlayVoiceTransport UnAdvise method.

It is noted that the foregoing examples have been provided merely for the purpose of explanation and are in no way to be construed as limiting of the present invention. While the invention has been described with reference to various embodiments it is understood that the words which have been used herein are words of description and illustration rather than words of limitations. Further although the invention has been described herein with reference to particular means materials and embodiments the invention is not intended to be limited to the particulars disclosed herein rather the invention extends to all functionally equivalent structures methods and uses such as are within the scope of the appended claims. Those skilled in the art having the benefit of the teachings of this specification may effect numerous modifications thereto and changes may be made without departing from the scope and spirit of the invention in its aspects.

The following is an exemplary Application Programmer Interface API for a voice engine as described above. For example the voice engine may be layer of network in which uses data transport layer to transport the audio data that is generates. The voice engine may expose the following exemplary API in order to allow applications to use the voice engine. The API includes various functions structures and constants. It will be understood that these functions structures and constants are merely exemplary any combination or subset of these components or equivalent components is included within the spirit and scope of the invention.

Applications use the methods of the IDirectPlayVoiceClient interface to manage clients in a voice session.

If the method is processed synchronously and is successful it returns DV OK. By default this method is run asynchronously and returns DVERR PENDING. On error this method will return one of the following values.

You must test the sound devices selected for playback and capture by invoking the setup wizard before connecting the client to the DirectPlay Voice session. On application startup check the audio configuration by using IDirectPlayVoiceTest CheckAudioSetup. If this method returns DVERR RUNSETUP the sound configuration specified has not been tested. The setup wizard needs to be run only once for any configuration.

If the buffer or a portion of the buffer is locked when DirectPlay Voice attempts to write to it the method will return DVERR INVALIDBUFFER and DirectPlay Voice will disconnect from the session. You will also receive a DVMSGID SESSIONLOST message. The hResult member of the associated structure will be set to DVERR LOCKEDBUFFER. Subsequent method calls will return a DVERR NOTCONNECTED error code.

If full duplex operation is not supported DirectPlay Voice falls back to half duplex listen only mode. To determine if you are in half duplex mode call IDirectPlayVoiceClient GetSoundDeviceConfig after you have completed the connection. If you are in half duplex mode the dwFlags member of the DVSOUNDDEVICECONFIG structure will have the DVSOUNDCONFIG HALFDUPLEX flag set.

Regardless of how the interfaces are obtained the DirectPlayVoiceClient object maintains a reference through a call to AddRef to the IDirectSound and IDirectSoundCapture interfaces it uses until IDirectPlayVoiceClient Disconnect is called. When Disconnect is called the DirectPlayVoiceClient object calls Release on both interfaces.

If this method is called synchronously by setting the DVFLAGS SYNC flag the DVMSG CONNECTRESULT message is not sent to the message handler. In this case the connection result is determined by the return value of this method.

If this method is called asynchronously by default calling this method immediately returns a DVERR PENDING error value and proceeds to process the connection request in the background. The status of the connection is not be known until the DirectPlay Voice client generates a DVMSG CONNECTRESULT message with the connection result.

Any calls to IDirectPlayVoiceClient Connect while a connection is pending return DVERR ALREADYPENDING. Additionally only one connection can be pending at a time.

A transport session must be started on the specified DirectPlay object before calling this method. A successful call to IDirectPlayVoiceClient Initialize must be made before calling the Connect method.

Retrieves a 3 D sound buffer for a player or group. You can use the methods of the 3 D sound buffer object to change the virtual 3 D position of incoming voice transmissions from the specified group or player.

Variable of type DVID that specifies the identification of the player or group that the user wants to reserve a buffer for. You can also specify DVID REMAINING to create a 3 D user buffer for all players or groups that do not have a user buffer. If DVID REMAINING is specified the lpdsBufferDesc must be NULL and the dwPriority and dwFlags parameters must be set to 0.

Pointer to an IDirectSoundBuffer interface which is used to create the Microsoft DirectPlay Voice main buffer. This can be either NULL or a user created Microsoft DirectSound buffer. If this member is set to NULL then DirectPlay Voice creates a buffer for you.

Direct pass through. This value is passed in the dwPriority parameter when the call to IDirectSoundBuffer Play is made. For more information see IDirectSoundBuffer8 Play which is publicly available in the document of Microsoft DirectX . This parameter must be 0 if lpdsMainBufferDesc is NULL.

Direct pass through. This value is passed to the dwFlags parameter when the call to IDirectSoundBuffer Play is made. For more information see IDirectSoundBuffer8 Play which is publicly available in the document of Microsoft DirectX . This parameter must be 0 if lpdsMainBufferDesc is NULL.

If the DirectPlay voice session is a mixing server session this method fails and returns DVERR NOTALLOWED.

Although you can access all the member functions of the 3 D sound buffer object because the DirectPlay voice client uses the buffer to stream incoming audio do not use the Lock UnLock or Play methods of the DirectSound 3DBuffer object.

If the user specifies a buffer DirectPlay uses that buffer for the player s or group s buffer. User created buffers have the following restrictions.

The buffer must not be locked when you pass it to DirectPlay. When the buffer for the individual user is no longer required or when a player leaves the voice session it is important to call IDirectPlayVoiceClient Delete3DSoundBuffer to free up resources.

If the buffer or a portion of the buffer is locked when DirectPlay Voice attempts to write to it the method will return DVERR INVALIDBUFFER. If you lock the buffer after the method has returned you will receive a DVMSGID SESSIONLOST message. The hResult member of the associated structure will be set to DVERR LOCKEDBUFFER. Subsequent method calls will return a DVERR NOTCONNECTED error code.

Returns exclusive control of the 3 D sound buffer object to the Microsoft DirectPlay voice client object.

Pointer to the user buffer to delete. This must be a user buffer obtained through the IDirectPlayVoiceClient Create3DSoundBuffer method.

If the DirectPlay Voice session is a mixing server session this method fails and returns DVERR NOTALLOWED.

On calling this method all recording and playback is stopped. If a connection is being processed it is canceled by this call.

Unless the DVFLAGS SYNC is specified calling this method immediately returns a DVERR PENDING error value and proceeds to process the disconnection request in the background. The status of the disconnection is not known until the DirectPlay Voice client generates a DVMSG DISCONNECTRESULT message that contains the disconnection result. Only one disconnection can be pending at a time. If you call IDirectPlayVoiceClient Disconnect while a disconnect is pending DirectPlay will return a DVERR ALREADYPENDING error value.

If this method is called synchronously by setting the DVFLAGS SYNC flag the method does not return until the Disconnect method completes. The result of the disconnection is the return value from this method. No DVMSGID DISCONNECTRESULT message is generated.

You can call this method only after a connection is successfully established with a Microsoft DirectPlay Voice session.

Pointer to buffer that receives an array of DVCOMPRESSIONINFO structures one structure for every compression type supported through this object.

Pointer to a DWORD where the method writes the number of elements returned in the array of DVCOMPRESSIONINFO structures. This contains the number of structures only if the buffer specified in the pData is large enough to hold the information.

If the buffer passed is not large enough to store the list of compression types the method returns DVERR BUFFERTOOSMALL and the pdwDataSize parameter is set to the minimum required size.

This method may be called only after a connection is successfully established with a Microsoft DirectPlay Voice session.

Pointer to a DVSOUNDDEVICECONFIG structure that is filled with the configuration of the sound device.

Pointer to a DWORD that specifies the size of the buffer in pSoundDeviceConfig parameter. If the buffer is too small the method returns DVERR BUFFERTOOSMALL and this parameter contains the size of the required buffer.

You can call this method only after a connection is successfully established with a Microsoft DirectPlay Voice session.

Member to fill with an array of DVIDs that specify the targets that were set by the IDirectPlayVoiceClient SetTransmitTargets or IDirectPlayVoiceServer SetTransmitTargets method. You can retrieve the number of targets by specifying NULL for this parameter.

Number of DVIDs in the array. When you call this method this should be the same value as the number of targets set in the IDirectPlayVoiceClient SetTransmitTargets method. If the call is successful Microsoft DirectPlay returns the number of elements written to the pdvIDTargets array.

The value returned in the pdvIDTargets parameter can be player or group DVIDs or the DVID ALLPLAYERS constant.

If the buffer specified inpdvIDTargets is not large enough to store the list of targets this method returns DVERR INVALIDPOINTER and pdwNumTargets is set to the required number of elements.

Initializes the DirectPlayVoiceClient object by associating it with a DirectPlay object. Additionally this method registers a message handler with the DirectPlayVoiceClient object.

Pointer to the IUnknown interface for the DirectPlay object that this DirectPlayVoiceClient object should use.

User defined callback function that is called when there is a DirectPlayVoiceClient message to be processed. Threads within the DirectPlayVoiceClient object call the callback function so it will not be called in the context of your process s main thread.

Pointer to an application defined structure that is passed to the callback function each time the function is called.

Array of DWORDs that contain the message identifiers that you want DirectPlay Voice to send to your callback function. If a message identifier is not specified in this array it is not sent. Each message identifier should appear only once in the array and only valid message identifiers are allowed. For example DVMSGID CONNECTRESULT is not valid for the server interface but is for the client interface. To enable all messages specify NULL for this value.

Number of elements specified in the pdwMessageMask parameter. If pdwMessageMask is NULL this must be 0.

You can call IDirectPlayVoiceClient SetNotifyMask to change the notify mask during the course of the voice session.

You can call this method only after a connection is successfully established with a Microsoft DirectPlay Voice session.

Calling this method sets all the parameters in the DVCLIENTCONFIG structure. Therefore to leave a setting unmodified you must retrieve the current configuration with IDirectPlayVoiceClient GetClientConfig. Then modify the parameters to change and call IDirectPlayVoiceClient SetClientConfig.

If the session is running in half duplex the members of GetClientConfig related to recording are ignored.

Pointer to an array of DWORDs containing the message identifiers that you want Microsoft DirectPlay Voice to send to your callback function. If a message identifier is not specified in this array it is not sent. Each message identifier should appear only once in the array and only valid message identifiers are allowed. For example DVMSGID CONNECTRESULT is not valid for the server interface but is for the client interface. To enable all messages specify NULL for this value.

Number of elements specified in the pdwMessageMask parameter. If pdwMessageMask is NULL this must be 0.

Pointer an array of DVIDs that specify your targets. To specify no targets pass NULL for this parameter. Additionally this parameter can be set to the following value.

For Microsoft DirectX 8.0 the number of individual targets that you can transmit to is limited to 64. If you exceed this value the method will fail and return DVERR NOTALLOWED. However you can transmit to more than 64 players. To do so form the players into groups and then use the group as your target.

The pdvIDTargets parameter specifies an array of player and or group DVIDs. There must be no duplicate targets in this parameter and all entries must be valid DVIDs. If a target contains a player as its individual DVID and through a group that the target belongs to Microsoft DirectPlay Voice ensures duplicate speech packets are not sent to the player.

If the session was created with the DVSESSION SERVERCONTROLTARGET flag only the server can set the targets for this local client. A call to this method returns DVERR NOTALLOWED.

Applications use the methods of the IDirectPlayVoiceServer interface to manage the host of the voice session.

Pointer to the buffer that receives an array of DVCOMPRESSIONINFO structures that describe the compression types supported by this object.

Pointer to a DWORD where the method writes the number of elements returned in the array of DVCOMPRESSIONINFO structures.

If the buffer is not large enough to store the list of compression types the method returns DVERR BUFFERTOOSMALL and the pdwDataSize parameter is set to the minimum required size.

A successful call to IDirectPlayVoiceServer StartSession must be made before this method can be called.

Array of DVIDs that specify the current targets of the player or group that were set by the IDirectPlayVoiceServer SetTransmitTargets method. You can retrieve the number of targets by specifying NULL for this parameter.

Number of DVIDs in the array. When you call this method this should be the same value as the number of targets set in the IDirectPlayVoiceServer SetTransmitTargets method. If the call is successful Microsoft DirectPlay returns the number of elements in the pdvIDTargets array.

This method can be used only if the DVSESSION SERVERCONTROLTARGET flag is specified on creation of the DirectPlay Voice session. If the flag is not specified this method returns DVERR NOTALLOWED.

Initializes the DirectPlayVoiceServer object by associating it with a DirectPlay object. Additionally this method registers a message handler with this interface.

Pointer to the IUnknown interface for the DirectPlay object that this DirectPlayVoiceServer object should use.

User defined callback function that is called when there is a DirectPlayVoiceClient message to process. A thread within the DirectPlayVoiceClient object calls the callback function so it is not called in the context of your process s main thread.

Pointer to an application defined structure that is passed to the callback function each time the method is called.

Array of DWORDs that contain the message identifiers that you want DirectPlay Voice to send to your callback function. If a message identifier is not specified in this array it is not sent. Each message identifier should appear only once in the array and only valid message identifiers are allowed. For example DVMSGID CONNECTRESULT is not valid for the server interface but is for the client interface. To enable all messages specify NULL for this value.

Number of elements specified in the lpdwMessageMask parameter. If lpdwMessageMask is NULL this must be 0.

You can call IDirectPlayVoiceServer SetNotifyMask to change the notify mask during the course of the voice session.

Pointer to an array of DWORDs that contain the message identifiers that you want Microsoft DirectPlay Voice to send to your callback function. If a message identifier is not specified in this array it is not sent. Each message identifier should appear only once in the array and only valid message identifiers are allowed. For example DVMSGID CONNECTRESULT is not valid for the server interface but is for the client interface. To enable all messages specify NULL for this value.

Number of elements specified in the pdwMessageMask parameter. If pdwMessageMask is NULL this must be 0.

After the Microsoft DirectPlay voice session has started not all the session properties of the DVSESSIONDESC structure can be changed. For more information see DVSESSIONDESC.

List of player DVIDs and or group DVIDs that are the target for audio transmission. To specify no targets pass NULL for this parameter. Additionally this parameter can be set to the following value.

For Microsoft DirectX 8.0 the number of individual targets that you can transmit to is limited to 64. If you exceed this value the method will fail and return DVERR NOTALLOWED. However you can transmit to more than 64 players. To do so form the players into groups and then use the group as your target.

There must be no duplicate targets in this parameter and all entries must be valid DVIDs. If a target contains a player as its individual DVID and through a group that the target belongs to Microsoft DirectPlay Voice ensures duplicate speech packets are not sent to the player.

This method can be used only if the DVSESSION SERVERCONTROLTARGET flag is specified on creation of the DirectPlay Voice session. If the flag is not specified this method returns DVERR NOTALLOWED.

Starts an initialized Microsoft DirectPlay Voice session within a running DirectPlay transport session. This method must be successfully called before the clients can complete a connection to the voice session.

The IDirectPlayVoiceServer Initialize method must be called before this method is called. The voice session can be hosted on any client in the session if the voice session is peer to peer. If the voice session is not peer to peer it must be hosted on the transport client which is the host of a active transport session.

The DVSESSIONDESC structure contains the type of voice session to start. The type of voice session can have a dramatic effect on the CPU and bandwidth usage for both the client and the server. You can set the guidCT member of DVSESSIONDESC to DPVCTGUID DEFAULT.

The host will not migrate regardless of session and transport settings. Use this flag when you want to shut down the voice session completely.

This method returns DVERR ALREADYPENDING if it is called while another thread is processing a StopSession request.

Applications use the CheckAudioSetup method of the IDirectPlayVoiceTest interface to test the Microsoft DirectPlay Voice audio configuration.

Runs the Audio Setup Wizard on the specified devices. This wizard runs a series of tests on the devices to determine if they are capable of full duplex audio and to ensure that the microphone is plugged in and working correctly on the capture device.

Pointer to the GUID that identifies the playback device to test. If NULL is passed for this parameter Microsoft DirectPlay Voice tests the system default playback device defined by Microsoft DirectSound . You can also pass one of the DirectSound default GUIDs 

Pointer to the GUID that identifies the capture device to test. If NULL is passed for this parameter DirectPlay Voice tests the system default capture device defined by DirectSound . You can also pass one of the DirectSound default GUIDs 

The default system capture device. You can also specify this device by passing a NULL pointer in the device GUID parameter.

The default voice communications capture device. Typically this is a secondary device such as a USB headset with microphone.

The test wizard invoked by this method is modal. If the calling application has a window that should be the parent window of the wizard it should pass a handle to that window in this parameter. If the calling application does not have a window it can pass NULL. If the DVFLAGS QUERYONLY flag is specified this parameter is not used and the application can pass NULL.

Audio setup is not run. Instead the method checks the registry to see if the devices have been tested. If the devices have not been tested the method returns DVERR RUNSETUP. If the devices have been tested the method returns DV FULLDUPLEX if the devices support full duplex audio or DV HALFDUPLEX if the devices do not support full duplex audio.

Passing this flag enables the Back button on the wizard s Welcome page. If the user clicks the Back button on the Welcome page the wizard exits and CheckAudioSetup returns DVERR USERBACK.

This method contains user interface UI elements and displays dialog boxes. If the DVFLAGS QUERYONLY flag is specified the tests are not actually run and no UI is raised. Instead the registry is checked to determine the results of a previous test of these devices.

If the user cancels the wizard the CheckAudioSetup call returns DVERR USERCANCEL. The calling application can then handle the situation appropriately. For example in DirectPlay Voice part of the gaming options control panel application if the user clicks Cancel the dialog box displays a message indicating that voice cannot be used because the wizard has been canceled.

This method might return DVERR INVALIDDEVICE if the device specified does not exist. Also if you specify the default device and this method still returns this error then there are no sound devices on the system.

Microsoft DirectPlay Voice generates the DVMSGID CONNECTRESULT message when the connect request generated through a call to the IDirectPlayVoiceClient Connect method has completed. This message is sent only if the Connect method is called asynchronously.

Microsoft DirectPlay Voice generates the DVMSGID CREATEVOICEPLAYER message when a new player joins the voice session.

Upon connecting to a voice session clients will receive one of these messages for each player in the voice session. These messages are sent only to clients in peer to peer voice sessions.

Players do not join the voice session until they have called IDirectPlayVoiceClient Connect. Therefore it is possible for a player to be in the transport session but not part of the voice session.

The DVMSG CREATEVOICEPLAYER structure contains information for the DVMSGID CREATEVOICEPLAYER system message.

The specified player is running in half duplex mode. The player will only be able to receive voice not transmit it.

Player context value for the player in the voice session. This value is set through this parameter when this message is received.

For clients Microsoft DirectPlay Voice generates the DVMSGID DELETEVOICEPLAYER message when a player quits the voice session. This message is available only to clients in peer to peer voice sessions.

For the host Microsoft DirectPlay Voice generates the DVMSGID DELETEVOICEPLAYER message when a player quits the voice session.

Players do not leave the voice session until they have called IDirectPlayVoiceClient Disconnect or they have disconnected from the transport session. Therefore a client might be part of the transport session but not part of the voice session.

The DVMSG DELETEVOICEPLAYER structure contains information for the DVMSGID DELETEVOICEPLAYER system message.

Pointer to the context value set for the player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

Microsoft DirectPlay Voice generates the DVMSGID DISCONNECTRESULT message when the disconnect request generated through a call to the IDirectPlayVoiceClient Disconnect method has completed. This message is sent only if the Disconnect method is called asynchronously.

The DVMSG DISCONNECTRESULT structure contains information for the DVMSGID DISCONNECTRESULT system message.

The DVMSGID GAINFOCUS message is sent to notify you that you have begun capturing audio. It is sent when an application that has lost capture focus recovers it. There is no data associated with this message. Refer to the Microsoft DirectSound documentation for more information on capturing audio.

Microsoft DirectPlay Voice generates the DVMSGID HOSTMIGRATED message when the voice host has changed.

If the local client has become the new voice session host this member will point to a newly created IDirectPlayVoiceServer object that can be used by the local client for providing host services. If the local client is not the new host then this member will be NULL. If this parameter points to an IDirectPlayVoiceServer interface you must call IDirectPlayVoiceServer AddRef to increment the interface s reference count. Call IDirectPlayVoiceServer Release when you no longer need the interface.

Microsoft DirectPlay Voice generates the DVMSGID INPUTLEVEL message periodically to notify the user of the input level from the microphone. The period of notification is set by the dwNotifyPeriod member of the DVCLIENTCONFIG structure. If the notification period is set to 0 this message will not be sent. In addition if the client is running in half duplex mode this message is not available.

Integer representing peak level across the current frame which corresponds to approximately 1 10 second of audio stream. The current frame typically lags 50 200 ms behind real time. This value can range from 0 through 99 with 0 being completely silent and 99 being the highest possible input level.

Current recording volume for the client. The value can range from 10 000 to 0. This member is available even when automatic gain control is active.

Pointer to the context value set for the local player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

The DVMSGID LOCALHOSTSETUP message is sent when the local client is elected to become the new voice host during host migration. The message is sent before the DVMSGID HOSTMIGRATED message and gives you the chance to set the callback function and context value that will be used when creating the new host object. If you do not set either of the values then the new server interface will have no callback function. Once the application returns from handling this message it will receive the DVMSGID HOSTMIGRATED message. The new message has the following associated structure which is passed in the void field of the message handler.

The DVMSG LOCALHOSTSETUP structure contains information for the DVMSGID LOCALHOSTSETUP system message.

The DVMSGID LOSTFOCUS message is sent to notify you that you have stopped capturing audio. It is sent when an application that has capture focus loses it to another application. There is no data associated with this message. Refer to the Microsoft DirectSound documentation for more information on capturing audio.

Microsoft DirectPlay Voice generates the DVMSGID OUTPUTLEVEL message periodically to notify the user of the output level of playback. The period of notification is set by the dwNotifyPeriod member of the DVCLIENTCONFIG structure. If the notification period is set to 0 this message will not be sent.

Integer representing the current output level of playback. This value is in the range from 0 through 99 with 0 being completely silent and 99 being the highest possible output level.

Pointer to the context value set for the local player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

Microsoft DirectPlay Voice generates the DVMSGID PLAYEROUTPUTLEVEL message periodically to notify the user of the output level of an individual player s voice stream. It is generated while voice is being played back for an individual player. If multiple player voices are being played one message for each player speaking will be sent each notification period.

The period of notification is set by the dwNotifyPeriod member of the DVCLIENTCONFIG structure. If the notification period is set to 0 this message will not be sent.

The DVMSG PLAYEROUTPUTLEVEL structure contains information for the DVMSGID PLAYEROUTPUTLEVEL system message.

Integer representing the current output level of the player s voice stream. This value is in the range from 0 through 99 with 0 being completely silent and 99 being the highest possible output level.

Pointer to the context value set for the player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

Microsoft DirectPlay Voice generates the DVMSGID PLAYERVOICESTART message when an incoming audio stream begins playing back.

The DVMSG PLAYERVOICESTART structure contains information for the DVMSGID PLAYERVOICESTART system message.

Pointer to the context value set for the player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

Microsoft DirectPlay Voice generates the DVMSGID PLAYERVOICESTOP message when an incoming audio stream stops.

The DVMSG PLAYERVOICESTOP structure contains information for the DVMSGID PLAYERVOICESTOP system message.

Pointer to the context value set for the player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

Microsoft DirectPlay Voice generates the DVMSGID RECORDSTART message when audio input on the local client begins. This can be caused by the voice activation sensitivity level being exceeded or when a valid target is specified in push to talk mode.

Pointer to the context value set for the local player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

Microsoft DirectPlay Voice generates the DVMSGID RECORDSTOP message when audio input on the local client stops. This can be caused by the voice activation sensitivity level not being reached or when a target is deselected in push to talk mode.

Pointer to the context value set for the local player. This value is set through the pvPlayerContext member of the DVMSG CREATEVOICEPLAYER message structure.

Microsoft DirectPlay Voice generates the DVMSGID SESSIONLOST message when the voice session terminates.

Microsoft DirectPlay Voice generates the DVMSGID SETTARGETS message when the IDirectPlayVoiceClient SetTransmitTargets or IDirectPlayVoiceServer SetTransmitTargets methods are called.

Controls the run time parameters for the client. The structure is first used in the call to IDirectPlayVoiceClient Connect where it sets the initial state of these parameters. The structure can be retrieved after a connection has been made by calling IDirectPlayVoiceClient GetClientConfig and set using IDirectPlayVoiceClient SetClientConfig.

Activates automatic gain control. With automatic gain control Microsoft DirectPlay Voice adjusts the hardware input volume on your sound card automatically to get the best input level possible. You can determine the current input volume by looking at the IRecordVolume member after a call to IDirectPlayVoiceClient GetClientConfig or by looking at the IRecordVolume member of DVMSG INPUTLEVEL messages.

Activates the echo suppression mode. This mode reduces echo introduced by configurations with external speakers and extremely sensitive microphones. While remote players voices are being played back on the local speaker the microphone is automatically muted. If the local player is transmitting the playback of remote player voices is buffered until local input stops. After local input stops playback resumes.

Mutes playback of the main sound buffer. Only sound buffers created through calls to IDirectPlayVoiceClient Create3DSoundBuffer will be heard.

Mutes playback of all DirectPlay Voice output and stops playback. This also stops decompression of incoming packets so CPU usage is reduced. Packets are effectively discarded while this flag is specified.

Mutes input from the microphone and stops recording. This also stops compression so CPU usage is reduced.

In addition to the preceding flags the method of transmission is controlled by setting only one of the following flags or by not specifying either flag.

Places the transmission control system into automatic voice activation mode. In this mode the sensitivity of voice activation is determined automatically by the system. The input level is adaptive adjusting itself automatically to the input signal. For most applications this should be the setting used. This flag is mutually exclusive with the DVCLIENTCONFIG MANUALVOICEACTIVATED flag.

Places the transmission control system into manual voice activation mode. In this mode transmission of voice begins when the input level passes the level specified by the dwThreshold member. When input levels drop below the specified level transmission stops. This flag is mutually exclusive with the DVCLIENTCONFIG AUTOVOICEACTIVATED flag.

If you do not specify either DVCLIENTCONFIG MANUALVOICEACTIVATED or DVCLIENTCONFIG AUTOVOICEACTIVATED the system will operate in push to talk mode. In push to talk mode as long as there is a valid target specified the input from the microphone will be transmitted. Voice transmission stops when a NULL target is set or the current target leaves the session or is destroyed.

Value indicating what the volume of the recording should be set to. See the IDirectSoundBuffer8 SetVolume method for valid values.

If automatic gain control is enabled this value can be set to DVRECORDVOLUME LAST which tells the system to use the current volume as determined by the automatic gain control algorithm. If a value other than DVRECORDVOLUME LAST is specified in combination with automatic gain control this value will be used to restart the algorithm at the specified value.

On return from a call to IDirectPlayVoiceClient GetClientConfig this value will contain the current recording volume. When adjusting the recording volume DirectPlay Voice will adjust the volume for the microphone if a microphone volume is present for the card and the master recording volume if one is present on the card . If neither a microphone volume nor a master record volume is present DirectPlay Voice will be unable to adjust the recording volume.

Value indicating what the volume of the playback should be set to. Adjusting this volume adjusts both the main buffer and all 3 D sound buffers. See the IDirectSoundBuffer8 SetVolume method for valid values. You can specify DVPLAYBACKVOLUME DEFAULT to use a default value that is appropriate for most situations full volume .

Input level used to trigger voice transmission if the DVCLIENTCONFIG MANUALVOICEACTIVATED flag is specified in the dwFlags member. When the flag is specified this value can be set to anywhere in the range of DVTHRESHOLD MIN to DVTHRESHOLD MAX. Additionally DVTHRESHOLD DEFAULT can be set to use a default value.

If DVCLIENTCONFIG MANUALVOICEACTIVATED or DVCLIENTCONFIG AUTOVOICEACTIVATED is not specified in the dwFlags member of this structure indicating push to talk mode this value must be set to DVTHRESHOLD UNUSED.

Buffer quality setting for the adaptive buffering algorithm. For most applications this should be set to DVBUFFERQUALITY DEFAULT. It can be set to anything in the range of DVBUFFERQUALITY MIN to DVBUFFERQUALITY MAX. In general the higher the value the higher the quality of the voice but the higher the latency. The lower the value the lower the latency but the lower the quality.

Buffer aggressiveness setting for the adaptive buffer algorithm. For most applications this can be set to DVBUFFERAGGRESSIVENESS DEFAULT. It can also be set to anything in the range of DVBUFFERAGGRESSIVENESS MIN and DVBUFFERAGGRESSIVENESS MAX. In general the higher the value the quicker the adaptive buffering adjusts to changing conditions. The lower the value the slower the adaptive buffering adjusts to changing conditions.

Value indicating how often you want to receive DVMSGID OUTPUTLEVEL and DVMSGID INPUTLEVEL if session is full duplex messages. If this value is set to 0 these messages are disabled. The value specifies the number of milliseconds between these messages. DVNOTIFYPERIOD MINPERIOD specifies the minimum period between messages that is allowed.

Describes the desired or current session settings for the Microsoft DirectPlay Voice server. This structure is used by the voice session host to configure the session and by the session host and clients to retrieve information about the current session. The dwFlags dwSessionType and guidCT members can only be set when the host starts the voice session. The host can change the buffer settings at any time.

The voice host will not migrate regardless of the transport settings. If this flag is not specified the voice host will migrate if the transport supports it.

The clients are unable to control the target of their speech. Only the server player can control the target of their speech. If the server does not specify this flag only the clients can control the target of their speech. This flag can be specified only in multicast and mixing sessions.

The type of DirectPlay Voice session to run. The DVSESSIONTYPE PEER flag is not available in client server sessions all other flags are valid for all session types. This member can be one of the following values.

Voice session will use a mixing server. In this mode of operation all voice messages are sent to the server which mixes them and then forwards a single premixed stream to each client. This reduces the bandwidth and CPU usage on clients significantly at the cost of increased bandwidth and CPU usage on the server.

Voice messages will be routed through the session host. This will save bandwidth on the clients at the expense of bandwidth usage on the server. This option is only useful if the session host has a high speed connection.

The buffer quality setting. This member is unused for all session types except mixing sessions. For all sessions except mixing sessions set this member to DVBUFFERQUALITY DEFAULT.

Allowable values are between DVBUFFERQUALITY MIN and DVBUFFERQUALITY MAX. Additionally this member can be set to the following value.

Specifying this value tells DirectPlay Voice to use the system default for this value which is adjustable through a registry entry that can also be set through Sounds and Multimedia in Control Panel.

Buffer aggressiveness setting. This member is unused for all session types except mixing sessions. For all sessions except mixing sessions set this member to DVBUFFERAGGRESIVENESS DEFAULT.

Allowable values are between DVBUFFERAGGRESIVENESS  MIN and DVBUFFERAGGRESIVENESS  MAX. Additionally this member can be set to the following value.

Specifying this value tells DirectPlay Voice to use the system default for this value which is adjustable through a registry entry that can also be set through Control Panel.

Used to set and retrieve information about the sound device configuration and cannot be changed once a connection has been made. After a connection is made you can retrieve the current sound device configuration by calling IDirectPlayVoiceClient GetSoundDeviceConfig.

Tells Microsoft DirectPlay Voice to attempt to automatically select or unmute the microphone line in the mixer for the specified recording device.

Tells DirectPlay Voice to initialize itself in half duplex mode. In half duplex mode no recording takes place. If the initialization of the sound system fails in full duplex mode this flag will be set by the system.

Tells DirectPlay Voice to use Microsoft DirectSound Normal Mode when initializing the DirectSound object. If this flag is not specified the DirectSound object is initialized with DirectSound Priority Mode. See documentation for IDirectSound8 SetCooperativeLevel for more information. If a valid DirectSound object is specified in the lpdsPlaybackDevice member this flag is ignored.

Set by DirectPlay Voice if there are no volume controls available on the recording device you specified. You cannot set this flag.

The voice application will never go out of focus. In other words the application will never release the sound capture device. Use of this flag is not recommended.

Applications should set the DVSOUNDCONFIG NOFOCUS or DVSOUNDCONFIG STRICTFOCUS flags only when strictly necessary. Instead you should normally use the default behavior that results when neither flag is set.

When this structure is used in the IDirectPlayVoiceClient Connect method this member specifies the GUID of the device used for playback. This must be specified even if the lpdsPlaybackDevice member is used. You can also specify the following default GUIDs provided by DirectSound.

When this structure is used in the IDirectPlayVoiceClient GetSoundDeviceConfig method this member contains the actual device GUID used for playback.

When this structure is used in the IDirectPlayVoiceClient Connect method this member specifies the DirectSound object you want DirectPlay Voice to use for playback. The GUID specified in guidPlaybackDevice must match the one used to create the device specified by this parameter. If you used NULL when specifying the device when you created your DirectSound object pass DSDEVID DefaultPlayback for this member.

When this structure is used in the IDirectPlayVoiceClient GetSoundDeviceConfig method this member contains a pointer to the DirectSound object being used by DirectPlay Voice. This will either be a pointer to the object specified when Connect was called or a pointer to a newly created and initialized DirectSound object. If you want to use this DirectSound object you must store the pointer and increment the reference count by calling AddRef on the DirectSound interface.

When this structure is used in IDirectPlayVoiceClient Connect method this member specifies the GUID of the device used for capture. This must be specified even if the lpdsCaptureDevice member is used. If you used NULL when specifying the device when you created your DirectSoundCapture object pass DSDEVID DefaultCapture for this member. When this structure is used in the IDirectPlayVoiceClient GetSoundDeviceConfig method this member will contain the actual device GUID used for capture.

When this structure is used in the IDirectPlayVoiceClient Connect method this member specifies the DirectSound object you want DirectPlay Voice to use for capture. The GUID specified in guidCaptureDevice must match the one used to create the device specified by this parameter. If you want to have DirectPlay Voice create the DirectSoundCapture object for you specify NULL for this member.

When this structure is used in the IDirectPlayVoiceClient GetSoundDeviceConfig method this member contains a pointer to the DirectSoundCapture object being used by DirectPlay Voice. This will either be a pointer to the object specified when Connect was called or a pointer to a newly created and initialized DirectSoundCapture object. If you want to use this DirectSoundCapture object you must store the pointer and increment the reference count by calling AddRef on the IDirectSoundCapture8 interface. If the DirectPlay Voice object is operating in half duplex mode this member will be NULL.

Must be set to the handle of the window that will be used to determine focus for sound playback. See IDirectSound8 SetCooperativeLevel for information on DirectSound focus. If you do not have a window to use for focus use GetDesktopWindow to use the desktop window.

Pointer to an IDirectSoundBuffer8 interface which is used to create the DirectPlay Voice main buffer. This can be either NULL or a user created DirectSound buffer. If this member is set to NULL DirectPlay Voice will create a buffer for the main voice buffer. If users specify a buffer here DirectPlay Voice will use their buffer for the main voice buffer. User created buffers have the following restrictions.

Passed directly to the dwFlags parameter of the IDirectSoundBuffer8 Play method when Play is called for the main buffer. The DSBPLAY LOOPING flag is automatically added to this field. See the documentation on IDirectSoundBuffer8 Play for details. This parameter must be 0 if the lpdsMainBufferDesc member of this structure is NULL.

Passed directly to the dwPriority parameter of the IDirectSoundBuffer8 Play method when Play is called on the main buffer. See documentation for IDirectSoundBuffer8 Play for more information. This member must be set to 0 if lpdsMainBufferDesc is NULL.

Not an error this return indicates that an asynchronous operation has reached the point where it is successfully queued.

The IDirectPlayVoiceClient Initialize or IDirectPlayVoiceServer Initialize method must be called before calling this method.

The specified audio configuration has not been tested. Call the IDirectPlayVoiceTest CheckAudioSetup method.

The following are the functions for exemplary IDirectPlayVoiceNotify and IDirectPlayVoiceTransport interfaces. The functions are for the purpose of this example described in C and C . In C the THIS and THIS parameters are not required. In C they are and they specify a pointer to the interface that the function is being called on. It will be understood that the interfaces provided in this Appendix is exemplary and an interface that includes any combination or subset of these or equivalent functions and structures is included within the spirit and scope of the invention.

The following three functions are standard COM interfaces which are described at http msdn.microsoft. com

Removes one reference from the interface instance. If the reference count reaches 0 the interface instance is destroyed. Returns 0 if the reference count is 0 a positive number otherwise.

Initializes the DirectPlayVoice interface associated with this interface. During this call DirectPlayVoice will call GetSessionInfo on the associated Transport interface.

Called by the DirectPlay engine or applicable session transport layer when an event occurs that DirectPlayVoice needs to be informed about. See descriptions of DVEVENT XXXXX listed in Appendix A for how the parameters are used for each message.

The following three functions are standard COM interfaces which are described at http msdn.microsoft.com

Removes one reference from the interface instance. If the reference count reaches 0 the interface instance is destroyed.

Advises the transport to call us back via the interface passed in the LPUNKNOWN parameter. This function calls QueryInterface on the LPUNKNOWN for an IDirectPlayVoiceNotify. Must call IDirectPlayVoiceNotify Initialize on the interface before returning.

LPUNKNOWN IUnknown interface instance that supports the IDirectPlayVoiceNotify interface for the IDirectPlayVoiceNotify to make notifications on.

Tells the transport that we no longer need to be called back on our notify interface. The transport should Release the instance of the notify interface that they have.

HRESULT SendSpeech THIS DVID dvidFrom DVID dvidTo PDVTRANSPORT BUFFERDESC pdvBufferDesc LPVOID pvContext DWORD dwFlags PURE 

pdvBufferDesc A reference counted structure describing the data to be sent. pvContext User context for send. This will be passed back to the application when the send completes. dwFlags Flags for the send this can have either both just one or neither of the following specified 

If DVTRANSPORT SEND GUARANTEED is specified then data must be sent guaranteed. Otherwise data can be sent unguaranteed.

If DVTRANSPORT SEND SYNC is specified then this function does not return until the packet has been sent. Otherwise the function returns immediately and will call the voice layer with a DVEVENT SENDCOMPLETE event when the send has completed.

Fills the passed structure with details on the session that is running on the transport object. See description of DVTRANSPORTINFO for details.

pdvidTargetList An array of targets that this packet should be sent to. The number of elements must equal the value passed to dwNumTargets.

pvContext User context for send. This will be passed back to the application when the send completes.

If DVTRANSPORT SEND GUARANTEED is specified then data must be sent guaranteed. Otherwise data can be sent unguaranteed.

If DVTRANSPORT SEND SYNC is specified then this function does not return until the packet has been sent. Otherwise the function returns immediately and will call the voice layer with a DVEVENT SENDCOMPLETE event when the send has completed.

Checks to see if the specified ID is a valid Group ID dvidGroup ID of the entity to check LPBOOL Pointer to BOOL to place result. TRUE for Valid Group FALSE if it is not.

The following structures are used by the exemplary IDirectPlayVoiceNotify and IDirectPlayVoiceTransport interfaces 

lRefCount Reference count of the structure when this reaches 0 it should be destroyed. It is set to 1 initially.

dwObjectType DVTRANSPORT OBJECTTYPE SERVER if this object belongs to a voice host DVTRANSPORT OBJECTTYPE CLIENT if this object belongs to a voice client.

dwSessionType DVTRANSPORT PEERTOPEER for a peer to peer transport DVTRANSPORT SESSION CLIENTSERVER for a client server transport.

