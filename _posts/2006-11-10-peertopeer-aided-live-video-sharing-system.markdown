---

title: Peer-to-peer aided live video sharing system
abstract: Video data from an upload client is received at a hosting node. A request from a download client is received at a bootstrapping node to receive the video data. The download client to receive the video data directly from the hosting node when the hosting node is below a threshold, wherein the threshold is based at least in part on the maximum number of download clients the hosting node can stream to simultaneously. The download client to receive the video data from peers in a peer-to-peer overlay when the hosting node above the threshold.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07733808&OS=07733808&RS=07733808
owner: Microsoft Corporation
number: 07733808
owner_city: Redmond
owner_country: US
publication_date: 20061110
---
A number of applications and services that support sharing video files exist on the Internet. For example some web sites allow users to upload video files to a database. These videos are also searchable via metadata provided in the submission process. Users can even charge audiences to view the videos.

Other web sites let video producers upload their video onto servers arrange them into programs display them to other Internet users and make money if anyone watches them. However these video hosting services are only for sharing stored video files. They do not enable the user to share the user s video or camera with others in real time.

Some web sites offer a comprehensive search engine of webcams from around the world. The portal maintains a database of live webcams on the Internet allowing users to search by keyword or browse through the categories and subcategories. Users can see what is happening around the world in real time. However these sites only provide searching and indexing of real time cameras. They do not provide any infrastructure support for sharing live videos.

Some video chatting services allow users to share cameras with others in real time. However most of these video charting applications use unicast methods to send video from the capturer to audiences and therefore can only serve a limited number of users in each session.

Overall an efficient way for an ordinary Internet user to share a live video with a large audience in real time is still lacking.

The following presents a simplified summary of the disclosure in order to provide a basic understanding to the reader. This summary is not an extensive overview of the disclosure and it does not identify key critical elements of the invention or delineate the scope of the invention. Its sole purpose is to present some concepts disclosed herein in a simplified form as a prelude to the more detailed description that is presented later.

Embodiments of the invention are directed to a system and method for sharing live video streams on a large scale through the Internet using a Shared Video Service SVS . Embodiments herein include a peer to peer streaming technique where video data packets are exchanged among the audience. This technique relieves load and bandwidth stress on a content server and ensures the scalability of the SVS.

Many of the attendant features will be more readily appreciated as the same become better understood by reference to the following detailed description considered in connection with the accompanying drawings.

The detailed description provided below in connection with the appended drawings is intended as a description of the present examples and is not intended to represent the only forms in which the present examples may be constructed or utilized. The description sets forth the functions of the examples and the sequence of steps for constructing and operating the examples. However the same or equivalent functions and sequences may be accomplished by different examples.

Although not required embodiments of the invention will be described in the general context of computer readable instructions being executed by one or more computing devices. Computer readable instructions may be distributed via computer readable media discussed below . Computer readable instructions may be implemented as program modules such as functions objects application programming interfaces APIs data structures and the like that perform particular tasks or implement particular abstract data types. The functionality of the computer readable instructions may be combined or distributed as desired in various environments.

Embodiments of the invention are directed to a system and method for sharing live video streams on a large scale through the Internet called a Shared Video Service SVS . SVS enables a user to share captured video with other people in real time specify the metadata of the shared video for indexing and retrieval search video of interest on the service using metadata and watch shared video in real time. It will be understood that the term video includes a video and an audio portion. One skilled in the art will appreciate that embodiments of the invention may also be used with audio only streams or video only streams.

Turning to a Shared Video Service SVS system includes a transmission subsystem and a management subsystem . Transmission subsystem is responsible for video uploading downloading and peer to peer P2P relaying. Management subsystem provides functionalities for browsing searching indexing and managing shared videos.

When a user wants to share video through the SVS the user sends a live or recorded video to an SVS hosting node. The hosting node receives video from the upload client and stores it. The video may include a live video stream captured by the upload client in real time or a video file i.e. recorded video stored on the upload client. In one embodiment the user is required before to logon to the SVS prior to uploading any video.

Viewers at the download clients may browse and search for available videos on the SVS. Each shared video may have some associated metadata stored in the database server such as category location tags and the like. Viewers can browse and search the videos using this metadata.

When viewers request a particular video a hosting node connects with a bootstrapping node to stream the video to the viewer. The video streamed to the viewer may be being captured live or may be sent from a video file being sent by an upload client to the system in real time.

In one embodiment to overcome limited bandwidth of the hosting nodes a P2P streaming mechanism is designed to assist in video transmission. When the video hosting node reaches a threshold such as its maximum capacity the P2P mechanism begins working. All the download clients within the same video session form a location aware overlay and live peer to peer streaming performed in a receiver driven fashion.

Transmission subsystem includes an upload client one or more download clients a hosting node additionally hosting nodes and are shown and a bootstrapping node .

Upload client acts as the source of a video. In one embedment upload client captures live video encodes the video streams generates the packets and transmits them onto hosting node in real time. In another embodiment upload client sends a pre recorded video file in a live fashion to hosting node . In this embodiment the video was captured and recorded at an earlier time. However the recorded video is sent to hosting node and streamed to download clients in real time.

Turning to a flowchart shows the operations of uploading a video to the SVS in accordance with an embodiment of the invention. To start a video session upload client first contacts bootstrapping node to request an available hosting node shown at block . Bootstrapping node responds with address information for an available hosting node shown at block . The bootstrapping node schedules a hosting node to the upload client according to the current loads of all the hosting nodes.

Next upload client sends an upload request to hosting node shown at block . After receiving an Acknowledgement ACK message from hosting node shown at block upload client then starts to send the video packets to hosting node in their sequencing order shown at block . After upload client starts successfully sending video to hosting node hosting node registers the information of the new video session with bootstrapping node shown at block . Bootstrapping node updates database server with video session information. The video being sent by upload client is now available for viewing at download clients . As discussed below database server tracks all video sessions within the SVS and may be searched by a user.

Turning to a flowchart shows the operations of requesting a video by a download client in accordance with an embodiment of the invention. A download client contacts bootstrapping node to join an existing video session shown at block . A downloading client also referred to as a streaming client only needs to know the bootstrapping node s address before beginning to view a video. Download client also discovers some peers i.e. other download clients within the same video session and form its own neighborhood through the P2P overlay shown at block .

The bootstrapping node determines if the status of the video session is at a threshold shown at block . In one embodiment the threshold is based at least in part on the maximum capacity of the hosting node. The maximum capacity of the hosting node is the maximum number of download clients per video session the hosting node can stream to simultaneously. The maximum capacity may be affected by load limitations of the hosting node e.g. SERVER FULLLOAD traffic load on the network any combination thereof and the like. The threshold may be set at maximum capacity or at a portion of maximum capacity e.g. 90 . If the hosting node is at the threshold for this video session then the download client works in P2P mode and obtain the streaming packets from its overlay peers shown at block . Otherwise the download client contacts hosting node to obtain the video directly from hosting node shown at block .

In one embodiment when running in P2P mode the download client uses a prefetch pull streaming algorithm to get data from its peers discussed below in section 2 . The download client also periodically updates the peers according to the observed throughput. In one embodiment the download client starts playback when a specified time interval has elapsed after receiving the first packet. At the download client the received packets are first buffered in a transmission buffer pool and then pulled on demand by the playback module of the download client.

Hosting node handles the video upload from an upload client and streaming to the download clients i.e. peers . The hosting node can be a dedicated server or a client node. For both cases the hosting node has limited bandwidth and is assumed to be able to serve only a limited number of directly streaming download clients. The hosting node receives video packets from an upload client and sends the video packets to the download clients in real time.

Each hosting node can manage multiple video sessions. Each video session is identified by a video s identification ID . Each video session serves a number of download clients and an upload client.

A hosting node registers its address with the bootstrapping node when joining the SVS e.g. on boot up and un registers itself on exit from the SVS. A hosting node also periodically reports its load including its total number of download clients and upload clients to the bootstrapping node so that the bootstrapping node can manage the load balancing of all the hosting nodes.

A bootstrapping node is deployed to help the download client peers to join the video session and discover other peers. The bootstrapping node handles all the requests from upload and download clients. It helps all the downloading clients to form a location aware overlay through a membership overlay algorithm discussed in section 2 below . The bootstrapping node may include a dedicated server or a client computer. In one embodiment the bootstrapping node may be deployed on the same computer together with the hosting node.

Bootstrapping node may include the following functionalities hosting node management video session management P2P bootstrapping support and video entry management.

In one embodiment bootstrapping node performs hosting node management. Each hosting node reports its address and streaming load to the bootstrapping node. When an upload client starts to upload the upload client first contacts the bootstrapping node and queries for an available hosting node to host the video. The bootstrapping node schedules a hosting node to the upload client according to the current loads of all the hosting nodes.

In one embodiment bootstrapping node performs video session management. After an upload client starts successfully sending video to the hosting node the hosting node registers the information of the new video session with the bootstrapping node. Such video session information may include video bit rate resolution frame rate and the like.

The bootstrapping node monitors all the video sessions. The bootstrapping node records all download clients that receive streaming packers directly from a hosting node. When the bootstrapping node finds that a hosting node has reached its load threshold e.g. maximum capacity it notifies the newly joined download client to get video from other peers i.e. streaming in a P2P fashion.

In one embodiment bootstrapping node performs P2P bootstrapping support. For each video session the bootstrapping node may maintain a peer cache that contains a number of the random peers watching the video. The peer cache is periodically updated. If any peer wants to watch a shared video it first contacts the bootstrapping node to join a corresponding streaming overlay. The bootstrapping node helps all the watching peers to form a location aware overlay through the membership overlay algorithm.

In one embodiment bootstrapping node performs video entry management. When a new video session is established the bootstrapping node calls a web service to add the entry into a database at a database server . When a video session is destroyed bootstrapping node calls the web service to remove the entry from the database at a database server . When the bootstrapping node exits the SVS the bootstrapping node calls the web service to remove all the video entries from the database.

Referring again to video management subsystem includes a database server a web server and a browsing sharing user interface UI .

All the video session entries and their metadata are stored and managed by database server . Each video has a unique entry record in the database. In one embodiment the primary key of the record is the video ID. Each record may also include other metadata such as title author name width height bit rate and frame rate of the video. The indexing table of the location category and tags are also stored in database server . Thus all shared videos can be retrieved through these metadata. In one embodiment video metadata is directly provided by upload client to database server through a web service and browsing sharing UI .

Web server is deployed as a unique entry point for the whole Shared Video Service. Some web services are developed on the web server to manage all the video entries and their metadata. These web services include the functionalities of browsing searching and authoring videos.

Web services of web server may be accessed using browsing sharing user interface . UI responds to user actions or queries calls the web services and generates the appropriate views to users. Through user interface users are able to browse all shared videos by metadata share personal videos author the metadata of individual shared video entries and the like. Once a user finds a video of interest the user may select the video through UI . The user s system i.e. download client may then request the video as described above in connection with download clients . Also a user at upload client may use UI for uploading a video to the system.

Embodiments of the SVS may be used in various scenarios. In one example in a breaking news event such as a disaster or an accident a by stander person holds his or her camera phone and transmits live video to SVS. Official news agency coverage of the event may begin much later if at all. In another example a camera from a window of a building is pointed to the intersection of two roads. Video is transmitted to the SVS in real time. Drivers who will use this intersection watch the traffic situations in advance during driving or in congestion. In another example in an exploration or a journey a traveler keeps his camera open. SVS subscribers watch the journey in real time. In yet another example television stations and news agencies may provide television programs and news through SVS.

Turning to an example of a computing device for implementing one or more embodiments of the invention is shown. Configurations of computing device may be used as a bootstrapping node a hosting node an upload client or a download client as described herein. Computing device may also be used as a database server or a web server as described herein.

In one configuration computing device includes at least one processing unit and memory . Depending on the exact configuration and type of computing device memory may be volatile such as RAM non volatile such as ROM flash memory etc. or some combination of the two. This configuration is illustrated in by dashed line .

Additionally device may also have additional features and or functionality. For example device may also include additional storage e.g. removable and or non removable including but not limited to magnetic or optical disks or tape. Such additional storage is illustrated in by storage . In one embodiment computer readable instructions to implement embodiments of the invention may be stored in storage . Storage may also store other computer readable instructions to implement an operating system an application program and the like.

The term computer readable media as used herein includes computer storage media. Computer storage media includes volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Memory and storage are examples of computer storage media. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVDs or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can be accessed by device . Any such computer storage media may be part of device .

The term computer readable media may include communication media. Device may also include communication connection s that allow the device to communicate with other devices such as with other computing devices through network . Communication media typically embodies computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media. The term modulated data signal means a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic radio frequency infrared and other wireless media.

Device may also have input device s such as keyboard mouse pen voice input device touch input device laser range finder infra red cameras video input devices also referred to as video capture devices such as cameras and or any other input device. Output device s such as one or more displays speakers printers and or any other output device may also be included. Input devices and output devices may be coupled to computing device via a wired connection wireless connection or any combination thereof. In the following description and claims the term coupled and its derivatives may be used. Coupled may mean that two or more elements are in contact physically electrically magnetically optically etc. . Coupled may also mean two or more elements are not in contact with each other but still cooperate or interact with each other for example communicatively coupled .

Those skilled in the art will realize that storage devices utilized to store computer readable instructions may be distributed across a network. For example a computing device accessible via network may store computer readable instructions to implement one or more embodiments of the invention. Computing device may access computing device and download a part or all of the computer readable instructions for execution. Alternatively computing device may download pieces of the computer readable instructions as needed or some instructions may be executed at computing device and some at computing device . Those skilled in the art will also realize that all or a portion of the computer readable instructions may be carried out by a dedicated circuit such as a Digital Signal Processor DSP programmable logic array and the like.

This invention includes a system and method to allow sharing a live video stream from one computer to a large audience through the Internet. Most of current live streaming servers on the Internet use unicast techniques to send streaming video to their clients. That means each streaming client establishes a separate data channel with servers to receive an identical copy of the original video stream. When the number of the streaming clients increases the bandwidth of a server will be exhausted. Therefore such a transmission scheme is not scalable and cannot support large scale video services or applications.

Embodiments herein include a system and method for streaming a live video from a hosting node to many download clients. Through embodiments of the system video from a camera connected to a computer or a file stored on a computer can be quickly and efficiently streamed out to a large number of download clients through the Internet.

Aspects of the P2P technique include 1 a separate bootstrapping node to handle all the joining requests from new clients. This isolates the hosting node from a flash crowd of download clients to a video session and makes the video session more stable 2 an algorithm to build a location aware overlay so that the peer joins the session with less latency and the streaming session will have less stress on the underlying physical network and 3 a prefetch pull method to improve the throughput of the peer to peer streaming system.

An efficient peer to peer streaming algorithm is developed to leverage the resource of downloading clients within the same video session. Therefore the hosting node s load will be kept constant and the live video streaming session will be able to serve many more users than traditional streaming servers. Live video streaming has more stringent requirements than other file transfer applications. Meanwhile most download client peers have limited bandwidth. Therefore the peer to peer streaming algorithm should make efficient use of network resources to reduce latency and maximize the throughput.

Turning to an SVS system is shown a management subsystem is not shown for clarity . Embodiments herein of peer to peer streaming include a two layer overlay. The lower layer of peer to peer overlay includes a membership overlay which is used for discovering nearby peers and disseminating messages. The upper layer includes a streaming overlay which is used for transmitting real time streaming packets. Embodiments of a new peer joining P2P overlay and streaming operations of new peer are discussed below. It will be noted that an OutView InView partner list and candidate list is shown only for new peer for clarity but it will be understood that each peer i.e. download client in P2P overlay includes these components. As used herein a download client may be referred to as a peer or a node of P2P overlay .

In the membership overlay each peer i.e. each download client has a number of neighbors. The connection between a peer and its neighbor is modeled as a directional edge. Each peer maintains a node set called OutView which stores all its neighbors. It also maintains a node set called InView that stores all peers that take it as their neighbor. Each peer sends messages to the neighbors in its OutView and receives message from the neighbors in its InView.

In the streaming overlay each peer has a number of partners. The partners of a peer are a set of peers that can provide streaming packets to the peer more quickly and efficiently than other peers of the P2P overlay. The partners are not necessary the nearest peers. Although nearby peers can provide data in smaller latency some of them may lack available bandwidth to serve the peer. The connection between a peer and its partner is modeled as an un directional edge i.e. the peer and its partner exchange data. A location aware overlay construction algorithm is designed to help the peer to construct an unstructured membership overlay and quickly find its peers.

Embodiments herein include a prefetch pull combined algorithm designed to exchange packets with partners. It also monitors the throughputs between itself and its partners and dynamically adjusts the peers named as partners to get best streaming performance. It also includes a loop avoidance mechanism to prevent a peer from receiving the same data packets more than once.

Location aware means that the peer to peer overlay is aware of the underlying physical network topology and tries to align the peer to peer communication with the underlying physical channel. In the membership overlay each peer tries to find a number of nearby neighbors and a number of random neighbors. The OutView of each peer includes nearby neighbors and l random neighbors in one embodiment the settings used are k 8 and l 3 .

In one embodiment a nearby neighbor may be measured by roundtrip time for packets between peers. In another embodiment a nearby neighbor may be measured by Internet Protocol IP address difference between peers.

Bootstrapping node maintains a peer cache for the peer to peer overlay . The peer cache contains the hosting node and a queue of random nodes whose size is no more than a constant L.

Bootstrapping node periodically discovers new random node s on the overlay to update peer cache . For this update bootstrapping node keeps M daemon processes on the bootstrapping node. Each daemon simulates a random walk process on overlay . Bootstrapping node uses the node visited by the random walk every c steps as a sample and use the sampled nodes to update the peer cache queue in a First In First Out FIFO order.

Referring to a flowchart shows an embodiment of joining a membership overlay by new peer . A new peer first sends a join request to the bootstrapping node shown at block . The bootstrapping node then selects k records from peer cache which are nearest to new peer . The bootstrapping node also selects l random peers from the rest of the peer cache. The bootstrapping node returns the selected peer information back to the new peer shown at block . If the cache size is less than k l the bootstrapping node sends information on all peers to the new peer.

After receiving the peer records shown at block the new peer joins the membership overlay shown at block .

1 new peer P takes the l random peers as the random neighborhood. If there are no random peers in the records the random neighborhood will be empty.

2 new peer P takes the k nearest peers as the initial nearest neighborhood and starts the following locating process 

b for each peer Q when it receives a NE query new peer P selects k nearest peers to new peer P from all its neighbors including InView and OutView and returns them as an acknowledgement of the NE query to new peer P.

d repeat step a c until convergence. Convergence occurs when the median of the distances to the nearest peers does not change. At this point new peer P stops the locating process and adds the k nearest peers observed so far to its OutView.

The new peer as well as the other peers may perform membership overlay maintenance after having joined P2P overlay shown at block of . Embodiments of membership overlay maintenance include handling a loss of communication with a peer and refining the overlay membership to adjust for peers entering or leaving the overlay.

Embodiments herein include techniques for peer failure handling. A peer may suffer from a system failure or a network disconnection. In the membership overlay each peer stays alive with all its neighbors so that peer failure can be detected. Periodically each peer sends heartbeat message to all its neighbors such as those in the InView and OutView . When a peer does not receive a heartbeat message from one of its neighbor peers for a long time it removes the peer from the InView and or OutView. When a peer receives a low level connection broken event with one of its neighbor peer it also removes the peer from the InView and or OutView.

Embodiments herein include techniques for refining the overlay membership. In order to handle the dynamic change of Internet topology and peers join and leaving each peer is able to atomically refine its neighborhood. In one embodiment each peer periodically performs the following operations in this order to refine the overlay membership 

1 the peer checks the nearest neighborhood if it is less than k 2 it starts a new query process to update the nearest neighborhood. In this step the peer s nearest neighborhood has become too small and needs to be increased to ensure uninterrupted streaming.

2 the peer checks the random neighborhood if it is less than l say i it contacts the bootstrapping node the bootstrapping node selects l i random nodes from the cache and return them to the peer. The peer then adds them to the random neighborhood.

3 if a peer in the random neighborhood already exists in the nearest neighborhood the peer removes it from the random neighborhood. However the connection with the peer does not change and the peer still exists in the peer s OutView while it is now regarded as one of the nearest neighbors instead of a random neighbor.

The streaming overlay is a mesh with every node having a few 4 6 partners to exchange streaming packets. Peers select their partners from a candidate list . A heartbeat mechanism is employed to maintain the partnership and to detect peer failures. Peers keep on refining their partners to achieve better streaming performances.

There are two entities involved in this phase candidate lists and partners. Referring to flowchart of embodiments of candidate list operations are shown. The initial candidate list is obtained when a peer joints an overlay shown at block . In one embodiment a new joining peer obtains the candidate list from the nearest in view peers in the member join process.

The candidate list is periodically updated including add refresh and remove shown at block . Each peer periodically floods its alive information to its neighbors within two hops. The peer which receives an alive message updates the entry in its partner candidate list or adds a new entry if the peer has not been on the list. This peer also checks the lifetime of each entry and removes an entry if the time exceeds a given threshold.

Referring to flowchart of embodiments of partner operations are shown. The initial partners are selected when the new peer joins the overlay by selecting 1 5 nearest partners from the candidate list shown at block .

Partnership maintenance is performed shown at block . Heartbeat messages are exchanged periodically between partners. When a partner failure is detected the nearest available peer from the candidate list is selected to replace this partner. In the meantime the failed partner is deleted from the candidate list.

The partners are refined to achieve better performance shown at block . In one embodiment the refinement procedure includes the following 

a a routine refinement occurs periodically such as every 10 seconds. The candidate list is checked to see whether there are any nearer nodes other than the current partner s . If so this nearer node becomes a new partner.

b after each transmission round if the bidirectional throughput to a partner is smaller than a given threshold this partner is disconnected and a new partner is selected from the candidate list. The disconnected partner is given a poor flag in the candidate list. It will not be re selected unless there are no other usable nodes.

Once a partnership is established a peer starts exchanging media data with its partners. Each peer uses a prefetch pull strategy to get media data packets from its partners. Before describing the prefetch pull strategy the following concepts are discussed.

Media Buffer Each peer in a streaming overlay has a media buffer to accommodate the received packets of the video stream. The media buffer may include a FIFO packet queue. The size L of the packet queue is fixed. If the media buffer is full the oldest packet is removed as a new packet arrives.

Buffer Map A buffer map is a bit vector with size of L. Each bit in the buffer map represents the availability of a single packet in the packet queue. Given the start sequence number and the buffer map one can know which media packets are available in its packet queue. During streaming each peer periodically publishes its buffer map to its partners.

Media Strips In embodiments of the streaming algorithm each video packet has a unique sequence number which is assigned by the hosting program and the sequence number is used as an index of the video packet. Furthermore a video stream is divided into P strips and a packet with sequence number s belongs to the strip s mod P .

Prefetch means that a peer can order some strips from one partner and some strips from other partners. Turning to flowchart of an embodiment of a prefetch pull strategy is shown. Periodically there is a prefetch process. A peer assigns P prefetch tasks each task corresponds to one strip to its partners shown at block . The prefetch task of strips is assigned to a partner according to the bandwidth and latency of the partner. In one embodiment the statistic information of previous received packets in the prefetch scheduling is used. A strip is assigned to the partner from whom the peer has received maximal packets of that strip by now.

Each node also periodically receives prefetch requests from their partners due to the symmetric partnership shown in block . An older prefetch request is updated by a new prefetch request from the same partner.

Whenever a peer receives a packet block it hashes the packet to one strip shown in block . In one embodiment peer uses the function s mod P as described above. The peer determines whether there are any prefetch requests regarding this strip having been received from any partners. If so the peer immediately forwards the packet to the requesting partner s . This forward operation may be referred to as a push shown at block .

Because each peer independently schedules its own pre fetching process it is possible that several peers may form pre fetching circles. In a pre fetching circle a peer receives two or more copies of the same packet because the peer has previously sent out a packet request to all of its partners. This wastes bandwidth and reduces streaming performance. To resolve this pre fetching circle problem each peer records and updates its partners buffer maps once it has received pushed a packet from to a partner so that the peer will not push the same packet to a partner more than once shown at . In one embodiment the peer maintains a local copy of each partner s buffer map that is updated each time a packet is received or pushed by the peer. Local copies of the buffer maps at a peer are added removed as the peer s partners are added removed.

In one embodiment the pre fetching algorithm is a best effort algorithm there is no retransmission scheme to guarantee the quality of service QoS . It is possible that some packets are lost due to network packet loss or congestion. In order to handle the possible pre fetching failure of some packets embodiments herein include a pulling strategy to proactively pull needed packets from partners if a pull condition is triggered shown in block . For a pre fetching failure there are two pull conditions to trigger a pull for a packet a general pull and an urgent pull.

In a general pull the peer takes the available packet with the maximum sequence number in the peer s own buffer map as a reference denoted as position E. Any non received packet whose sequence number is smaller than E TH1 is scheduled to be pulled where TH1 is a constant threshold. The non received packet is pulled from a random selected partner whose buffer map local copies of buffer maps stored at the peer shows that it has the packet. Once a peer receives a pull request it sends the required packet s as an acknowledgement.

In order to further reduce a failure possibility an urgent pull request is scheduled if the peer fails to receive a packet in a certain time period TH2 before its playback time where TH2 is another constant threshold. At the peer a media playback module gets media data packets from the P2P streaming module for playing back the video. In embodiments herein the playback timing is independent from the streaming scheme. The playback can start at a time several seconds after the first packet in the stream is received at the peer.

Embodiments herein include a peer to peer video streaming system that includes a location aware unstructured peer to peer overlay and a prefetch pull based streaming algorithm for transmitting video data among peers. Through embodiments of the system live video streams can be sent to a large amount of receivers in a cost effective way.

An embodiment of a P2P protocol design for communication between peers is described as follows. It will be understood that embodiments of the invention are not limited to use with the following P2P protocol design and other protocols may be used to implement embodiments of the invention.

To support efficient communication among peers an extensible multiple layer protocol stack is used. The structure of the protocol stack is illustrated in .

The Link Layer is the lowest layer of the SVS protocol stack. The Link Layer tries to establish and manage all incoming outgoing connections through the underlying transportation protocols such as TCP UDP and HTTP HTTPS.

Because the peer may use multiple protocols to transmit data one peer can have multiple addresses and ports. All of these addresses and ports of a peer are defined as the peer s ContactInfo and stored in the following format 

The definition of the ContactInfo makes it possible to support any common Internet protocols through the Link Layer modules. The Link Layer also monitors the status of the underlying connections and reports the events such as link failure or congestion to the upper peer layer. When necessary the Link Layer level also performs Firewall traversal to help establish the connection between peers.

The Peer layer is built on top of the Link layer and is responsible for application level networking.

Each peer is assigned a unique 128 bit ID. The Peer Layer protocol uses the peer ID as the application level address. After establishing application level connection through peer layer s hand shake protocol two peers can send and receive data simply through their IDs. The underlying communication events also are mapped into high level peer behaviors such as peer failure peer connected peer disconnected and the like.

Through the design of link layer and peer layer the peer level communication is abstracted from the underlying transportation protocols. The upper peer to peer applications and protocols can be developed solely based on the uniform peer level communication interface. Such a design is very flexible. It makes the peer to peer development much easier and can support efficient transportation protocols as well.

As described above in section 2 for a peer to peer streaming application two application level protocols are developed 1 membership overlay protocol which helps peers form a location aware network 2 streaming overlay protocol which enables peers to exchange streaming packets.

The Link layer is the lowest layer of the SVS protocol stack which is in charge of the incoming and out going IP links including TCP UDP and HTTP HTTPS. All packets in the SVS system pass through this layer. An embodiment of the Link Layer Protocol LLP header has the format as shown in .

R 1 bit field indicates whether this packet is supposed to be sent via a reliable transmission channel. If this packet is received from the UDP channel an ACK might needs to be sent upon receiving this message.

To establish the UDP connection a SYN message is first sent to the receiver with a SEQNUM. If the receiver receives the packet it returns an SYN ACK with the same SEQNUM. Once the sender receives the SYN ACK it makes sure that the connection is established. This mechanism is only used for UDP channels.

The Probe and Answer Probe messages are a pair of messages used to measure the end to end latency. Both messages have the same body structure a DWORD field that contains a timestamp. For every 10 seconds a host sends a Probe message to every available UDP channel. The timestamp in the packet indicates the sending time. Upon receiving this message the peer changes the message ID to Answer Probe and sends the packet back immediately. When the host receives the return packet it can calculate the Round Trip Time RTT by subtracting the timestamp carried in the packet from the current time. The result is reported to the network monitor.

In SVS there are basically two kinds of packets control messages and video streams. While the loss of media data affects the communication quality the loss of control messages is usually damaging. For example loss of the subscription request keeps the subscriber waiting loss of network status updates may result in network congestion. In one embodiment the TCP channel is used in transmitting the control messages.

The LLP ACK message is used to acknowledge the receipt of a need ack packet. The body of the packet contains an 8 bit sequence number which indicates which packet the peer has received. An 8 bit field for the sequence number is used because the volume of need ack packets probably will not be large.

In one embodiment the bandwidth measurement packet structure of DigiMetro is used. DigiMetro is an application level multicast system for multi party video conferencing. The packet body has the format shown in . The first 16 bit field ROUND NUMBER indicates which round of measurement this packet belongs to. This is to avoid mixing packets from consecutive measurement processes. The second 16 bit field SEQ NO contains the in sequence number of this packet. The 32 bit timestamp records the sending time TIMESTAMP .

The network monitor also allows the user to set and process the bandwidth measurement data at the application layer. Examples of the application layer assigned data are the user s display image and the most recent I frame of the real time video. This data can be passed to the network monitor through the exposed interface. By default the network monitor uses a block of nonsense data for bandwidth measurement. The developer can also set a callback function if the developer wishes to process the measurement data. The structure of the data part can be defined by the developer.

Message type LLP DATA indicates that this packet belongs to an upper layer. In such a case the Link management layer should detach the LLP header and pass the LLP data to the upper level protocol.

The Transport Level Protocol TLP handles the message from the connect level. The TLP header has the data fields as shown in .

OVERLAY PORT 16 bit field contains the overlay port number of the packet source. By using this port one can easily dispatch messages to different modules. In addition one can also establish multiple overlay structures based on the same lower layers.

Unlike DigiParty a multiparty video conferencing system the Hello message is only used as a keep alive message. For every 5 seconds a host sends a Hello message to every available UDP and IP multicast channel to keep the link alive. If a host has not received the Hello message for 30 seconds from a specific link it assumes that the connection is broken.

The SYN message is mainly used for setting up a connection. After a connection object accepts a TCP connection request the first message it receives from this connection should be a SYN message. Otherwise the host closes this connection. A host also uses the SYN message to ping its peers through UDP and IP multicast channels. Upon receiving the SYN message the peer manager checks whether there already exists a Peer object which is associated with the SENDER ID. If so it updates the connectivity information for the object e.g. set the UDP channel status to available if the SYN message is received from UDP . Otherwise the peer manager creates a new Peer object and associates it with the SENDER ID in the packet header. The body of the SYN message contains the SENDER ID.

Message type PLP DATA indicates that this packet belongs to an upper layer. In such a case the Link management layer should detach the Peer Layer Protocol PLP header and pass the PLP data to the upper level protocol.

Through maintaining a consistent membership overlay the system connects all peers together with location awareness. Peers can join and find nearest neighbors very quickly. Though the streaming partners do not necessary correspond to the nearest nodes and the streaming overlay does not necessarily match the topology the location aware property of the membership overlay can facilitate a peer to find good streaming partners. In addition the membership overlay also supports abundant distributed operations through P2P communication. The protocol of the membership overlay is described as follows.

m MsgType is a 16 bit message word. In embodiments herein all incoming messages are delivered to both of the membership overlay and the streaming overlay. The value of the highest bit of the message type is used to distinguish the messages. A message whose highest bit is 1 is processed by the streaming overlay. Otherwise it is a message for the membership overlay.

For message types of the membership overlay the higher byte is the destination description. The lower byte contains the message ID.

Random walk is a basic function or message of a membership overlay. Random walk can be used to select random neighbors when a peer tries to join a membership overlay and can be used to select random nodes over the membership overlay. In some embodiments of the protocol biased forwarding and biased halting schemes are not supported. Once a peer received a random walk message from its neighbor it decreases the hop number of the message. If the hop number is larger than zero the peer only selects a random peer from destination neighbors refer to the Membership Overlay Message Destination Description in the previous section and directly forwards the message. Otherwise the peer will not forward further and send a random walk acknowledge message to the peer which is the source of the random walk message for a SVSOVERLAY RANWALK D message the membership overlay delivers the data payload to the upper layer i.e. the streaming overlay and does not send an acknowledge message to the source peer. The upper layer can send their own acknowledge message according the received data. 

There are two message types including SVSOVERLAY RANWALK and SVSOVERLAY RANWALK D. SVSOVERLAY RANWALK is a message only for membership overlay maintaining such as peer joining and membership refinement. SVSOVERLAY RANWALK D is a data conveying message for the upper layer.

A flood message is also a basic function or message of a membership overlay. Once a peer receives a flood message from its neighbor it decreases the hop number of the message. If the hop number is larger than zero the peer directly forwards the message to destination neighbors please refer to the Membership Overlay Message Destination Description in the previous section . Otherwise the peer will not forward message. There are two message types including SVSOVERLAY RANWALK and SVSOVERLAY RANWALK D. SVSOVERLAY RANWALK is a message only for membership overlay maintaining such as peer joining and membership refinement. SVSOVERLAY RANWALK D is a data conveying message for the upper layer. For a SVSOVERLAY RANWALK D message the membership overlay delivers the data payload to the upper layer.

As mentioned above a peer can query random out links from the bootstrapping node. An embodiment of a query message is defined as below.

Once a bootstrapping node receives a MOVERLAY QUE RAND message it replies with an acknowledgement MOVERLAY ACK RAND.

As mentioned earlier a peer may query k nearest peers from the bootstrapping node and its out links. An embodiment of the query message is as follows.

Once a bootstrapping node or a normal peer receives a MOVERLAY QUE NEAR message it finds out the m Num nearest peers from its cached peers and replies with an acknowledgement MOVERLAY ACK NEAR.

When a peer A wants to add a peer B as its out link it sends a connection request to peer B. Peer B can determine to accept or reject the request. An embodiment of the message is as follows 

When a new peer tries to join a membership overlay it first connects to a bootstrapping node and sends a join message to the bootstrapping node. Below is an embodiment of a join message sent by a peer and its acknowledge from a bootstrapping node.

When a peer tries to quit a membership overlay it sends a quit to the bootstrapping node and all its neighbors. This message has no acknowledge message. Any peer who receives this message only deletes the peer from its neighborhood.

A new joined peer can query partner candidates from another peer in the overlay by sending the following request message 

The queried peer sends back the following acknowledge message which includes all of its partner candidates 

When a peer wants to establish the partnership with another peer it sends the following partnership message 

When the peer starts receiving streaming packets and becomes available for other peers to get data from it it notifies its neighbors in two hops through the following message. The neighbors add it to their candidates lists. An embodiment of an availability notification message is as follows 

When a peer needs to prefetch media data from another peer it sends the following subscribe message to it.

When the destination peer receives the message and decides to accept or reject this subscription and send a acknowledge message back.

To reflect the status of the current buffer each peer may advertise its buffer map to all its partners through the following message 

According to the partner s buffer map a peer can send the pull request message to pull the packet from the partner 

The first several peers in the streaming overlay network download from the hosting node directly using the following messages 

The media data message includes the actual video streaming packets with a global numbered sequence number.

Various operations of embodiments of the present invention are described herein. In one embodiment one or more of the operations described may constitute computer readable instructions stored on computer readable media which if executed by a computing device will cause the computing device to perform the operations described. The order in which some or all of the operations are described should not be construed as to imply that these operations are necessarily order dependent. Alternative ordering will be appreciated by one skilled in the art having the benefit of this description. Further it will be understood that not all operations are necessarily present in each embodiment of the invention.

The above description of embodiments of the invention including what is described in the Abstract is not intended to be exhaustive or to limit the embodiments to the precise forms disclosed. While specific embodiments and examples of the invention are described herein for illustrative purposes various equivalent modifications are possible as those skilled in the relevant art will recognize in light of the above detailed description. The terms used in the following claims should not be construed to limit the invention to the specific embodiments disclosed in the specification. Rather the following claims are to be construed in accordance with established doctrines of claim interpretation.

