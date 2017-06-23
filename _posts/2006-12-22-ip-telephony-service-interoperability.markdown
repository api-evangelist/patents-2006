---

title: IP telephony service interoperability
abstract: The invention concerns a residential gateway device designed for a decentralized client equipment and comprising converting means for providing interoperability between to separate IP telephony services.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08576856&OS=08576856&RS=08576856
owner: France Telecom
number: 08576856
owner_city: Paris
owner_country: FR
publication_date: 20061222
---
This application claims priority from PCT FR2006 002865 filed Dec. 22 2006 which claims priority from French Application FR 05 13373 filed Dec. 27 2005 both of which are hereby incorporated by reference in their entirety.

The present invention therefore has applications in the field of voice on IP but also in other fields such as Internet videoconferencing.

IP telephony sometimes called Internet telephony and often abbreviated as VoIP Voice over IP is a technique which makes it possible to communicate via the Internet network or any other network accepting the TCP IP protocol. Unlike STN switched telephone network or RTC from the French R seau t l phonique Commut depending on dedicated telephone exchanges IP telephony allows the transport of telephone conversations over the whole of the digital or analog network accepting the TCP IP protocol for example Ethernet ISDN Integrated Services Digital Network or RNIS from the French R seau Num rique Int gration de Services PPP Point to Point Protocol etc.

A user of a given IP telephony service has client equipment for example domestic equipment configured for this IP telephony service. The client equipment typically comprises a terminal to provide a user interface. The client equipment also comprises a home gateway to provide the interface with the IP network in accordance with the given IP telephony service.

 Home Gateway is understood to mean a client gateway that is to say a gateway located at the user end unlike a network equipment situated in the network under the control of an operator. It may for example be a gateway for domestic use within a home or it may be a gateway for professional use within a business. In general it is a gateway for client use.

The user of an IP telephony service may converse with any other user of the same IP telephony service that is to say with any other user having a client equipment configured for that IP telephony service.

Two users Bob and Alice of this IP telephony service have equipments and respectively each comprising a terminal connected to a home gateway . The gateways provide an interface between the terminals and the internet .

The terminals may be of various types for example a conventional fixed telephone a mobile telephone personal digital assistant a computer provided with an IP telephony service etc.

A user of a first IP telephony service referred to as the caller may wish to converse with a user of a second IP telephony service distinct from the first service referred to as the recipient.

The caller may then for example configure his client equipment so that he may himself become a user of the second IP telephony service.

According to another possibility the communication between the two users Bob and Alice may be carried out via a centralized gateway installed between the networks of the two IP telephony service providers as shown in .

In this example the data exchanged between Bob and Alice pass through the centralized interconnection gateway which makes it possible to convert the data transmitted by Bob in accordance with one of the two IP telephony services into data in accordance with the other IP telephony service and vice versa.

The centralized interconnection gateway is managed by the operators of the two IP telephony services and may cover a relatively wide geographic area comprising for example a whole country.

According to a third possibility and insofar as the recipient has an E164 number commonly called a telephone number data may be exchanged by means of two transits as shown in .

The data sent by the caller Bob flows in the IP network as far as the gateway . It is then converted into data in accordance with a format adapted to STN before arriving at the gateway . The data then undergoes a second conversion in order to flow on the IP network as far as the recipient Alice. In the other direction the data sent by Alice is first converted by the gateway and then by the gateway .

The gateways are managed in a centralized manner and may cover a relatively wide geographic area comprising for example several countries.

Furthermore the possibility of communication shown in may only be envisaged insofar as Alice has an E164 number.

A purpose of the present invention is to make communications between two users of distinct IP telephony services more flexible and easier to manage.

According to a first aspect the present invention relates to a home gateway device intended for a decentralized client equipment and comprising data conversion means for providing interoperability between two distinct IP telephony services.

Such a device allows a decentralized conversion of data exchanged between users of two distinct IP telephony services.

Thus a user of a service wishing to converse with a user of another service does not need to configure his client equipment in order to himself become a user of that other service as in the prior art.

Moreover by having several home gateways according to the first aspect of the invention it is possible to avoid the installation and maintenance of a centralized interconnection gateway dedicated to interoperability between these two IP telephony services. The communications between users of two distinct IP telephony services are thus easier to manage for the operators.

Furthermore in the prior art the data exchanged are likely to transit on the switched telephone network STN . Home gateways according to the first aspect of the invention make it possible to avoid such a transit on a paid network. The communications may thus remain cheap even between users of two distinct IP telephony services.

Moreover communication between users of different services may be possible even when the recipient does not have an E164 number.

Advantageously a network address is allocated to the home gateway device. The home gateway device also comprises receiving means for receiving a request for at least one address of a gateway device able to convert data in order to provide interoperability between two given distinct IP telephony services and means of sending a response to the request said response comprising the network address allocated to the home gateway device.

Thus it is possible to search in a network for which home gateway is able to provide interoperability between the two IP telephony services. Only a relatively small number of home gateways according to the first aspect of the invention may thus be installed in the network. The installation of communication support devices between users of two distinct IP telephony services is thus relatively simple.

The present invention is not of course limited to such a routing method. For example the home gateway of each user of a service may be arranged to make it possible to achieve interoperability between said service and another service. When a user of said service wishes to converse with a user of the other service interoperability is achieved in situ by the caller s home gateway. No search for a gateway able to achieve interoperability is necessary. Similarly when a user of the other service wishes to converse with a user of said service interoperability may be achieved by the latter s home gateway that is to say the recipient s home gateway.

According to a second aspect the present invention relates to an interoperability method intended to be used by a first home gateway device of a client equipment comprising the following steps 

This method makes it possible to achieve interoperability between IP telephony services in a decentralized manner.

Thus it is possible to search in a network for which device comprises conversion means for providing interoperability between the two IP telephony services.

Alternatively no search in the network is carried out. The home gateway device implementing the steps of the method according to the second aspect of the invention may be associated with a given user.

Advantageously the request is received from the second home gateway device. The latter itself carries out the search for home gateways able to provide interoperability.

Alternatively the request may be received from a server device. The second home gateway device sends for example to the server an address of the recipient. The server searches in the network for which home gateway is able to provide the interconnection and returns one or more results to the second home gateway device.

The server device may cover a more or less extended region. It only carries out a search for addresses of home gateways able to achieve interoperability. The server may therefore be less powerful than the centralized interconnection gateways of the prior art and therefore easier to install and to maintain.

According to a third aspect the present invention relates to a routing method for IP telephony services comprising 

Advantageously and in particular when the routing method is used by a server the routing method may comprise prior to the sending step a step of receiving from the second home gateway device a request for at least one address of a gateway device able to convert data in order to provide interoperability between two given distinct IP telephony services. The routing method then also comprises a step of sending at least one of the addresses contained in the group of responses to the second home gateway device.

Advantageously the routing method according to the third aspect of the invention also comprises a step consisting in choosing a single address from among the responses of the group of responses received. Thus the chosen address may be sent to the second home gateway device.

Alternatively the server may transmit to the caller s home gateway device all of the addresses of the group of responses. The choice of the address to which the data to be exchanged will be sent is then made by the caller s home gateway device or by a third party device.

The request may for example be sent to a plurality of home gateway devices in which case the group of responses comes from said home gateway devices.

The request may alternatively be sent to an indexing server storing interoperability parameters. The indexing server is able to provide information regarding the home gateway devices able to provide interoperability.

According to a fourth aspect the invention relates to a routing device for IP telephony services comprising sending means for sending a request for at least one address of a home gateway device able to convert data in order to provide interoperability between two given distinct IP telephony services and receiving means for receiving a response said response comprising an address of a home gateway device.

The routing device according to the fourth aspect of the invention makes it possible to search for home gateways in order to achieve interoperability in a decentralized way.

The routing device may for example comprise a server in indexing server and or a caller s home gateway. The present invention is not limited by the form of the routing device.

Advantageously sending means for example a caller s home gateway device make it possible to transmit data according to a first IP telephony service to a home gateway device whose address is contained in the received group of responses and receiving means for example the caller s home gateway device make it possible to receive data in accordance with said first IP telephony service from said home gateway device.

The data according to the first service thus pass through a home gateway found by the routing device.

Alternatively the routing device may not comprise a home gateway. The routing device then offers to the caller s gateway one or more addresses of gateways able to provide interoperability. The caller s gateway transmits data to this address or if applicable to one of those addresses.

Advantageously receiving means for example a server device make it possible to receive a request for at least one address of a gateway device able to convert data in order to provide interoperability between two given distinct IP telephony services said request being received from a home gateway device. Sending means for example also the server device make it possible to send at least one address to this home gateway device.

Advantageously the routing device also comprises an indexing server for storing parameters concerning the interoperability capability of a plurality of home gateway devices. The indexing server makes it possible to avoid interrogating a plurality of home gateway devices one by one.

The term home gateway device is equally understood to mean a home gateway or client gateway or any client device or even a device connected to a relatively small number of client equipments. The present invention is distinguished from the prior art at least in that the interoperability between two IP telephony services is achieved in a decentralized manner.

The term data conversion is also understood to mean data processing for example transcoding or adaptation of one protocol to another or a simple retransmission of data with adaptation of the signaling or of the message headers. The present invention is not therefore limited by the form of the conversion provided that it allows the passage of data from one of the two services to the other service and vice versa if required.

A first user Bob of a first IP telephony service referred to as the caller wishes to converse with a second user Alice of a second IP telephony service distinct from the first IP telephony service referred to as the recipient. Bob and Alice respectively have client equipments in this case home equipments each comprising a terminal and a home gateway device .

The communication is carried out via a first home gateway device of a first client equipment . The client equipment belongs to a third party user Patrick. The client equipment comprises a terminal and the gateway .

The gateway comprises data conversion means not shown in for providing interoperability between the two IP telephony services the operation of which is described below.

During operation the gateway receives from the gateway of the caller Bob also called the second home gateway device data transmitted in accordance with the first IP telephony service. Using conversion means the gateway converts this data into data in accordance with the second IP telephony service and then transmits it to the gateway of the recipient Alice also called the third home gateway device .

In the same way Patrick s home gateway may receive from Alice s gateway data in accordance with the second IP telephony service. This data is converted into data in accordance with the first IP telephony service and is transmitted to Bob s gateway .

Interoperability between the first and second IP telephony services is thus achieved through Patrick s gateway .

The client equipment comprises a home gateway and terminals . The terminals may for example comprise a fixed telephone a computer and a personal digital assistant PDA . On the computer there may for example be installed two service accounts corresponding to first and second distinct IP telephony services. The fixed telephone makes it possible to provide a user interface for a third IP telephony service and the personal digital assistant makes it possible to provide a user interface for a fourth IP telephony service.

The home gateway comprises conversion means comprising a programming interface or API Application Programming Interface for each IP telephony service and an interoperability software layer . The programming interfaces comprise software stacks of the IP telephony services for which the home gateway hosts an interoperability function.

This network is shown in layers each layer corresponding to a service. The spots on a first layer represent the home gateways of users having subscribed to the first IP telephony service. The spots on the second layer represent the home gateways of users having subscribed to the second IP telephony service. Finally the spots on the third layer represent the home gateways of users having subscribed to a third IP telephony service.

The spots remaining white represent home gateways of users having subscribed to a single IP telephony service.

On the other hand the black spots represent home gateways of users having subscribed to several IP telephony services. These home gateways may be arranged to provide interoperability between IP telephony services.

For example the gateway belongs both to the first layer and to the third layer . This gateway may be arranged in such a way as to provide interoperability between the corresponding services namely the first service and the second service. The arrows shown in dotted lines indicate a change of network.

Each IP telephony service has its own logical architecture organization. The first service has for example a centralized architecture the second service uses a Distributed Hash Table DHT and the third service has a P2P Peer to Peer architecture.

When a user of the first IP telephony service having the home gateway wishes to communicate with a user of the second IP telephony service one or more intermediate home gateways offering interoperability between several services may be called upon. In particular the gateway may search for the home gateways belonging both to the first layer and to the second layer . Examples of different ways of carrying out such a search also called routing are shown in and .

Once the routing is completed the gateway sends to a chosen home gateway for example gateway data in accordance with the first service. Gateway converts this data into data in accordance with the second service and transmits it to the recipient s gateway . In the reverse direction gateway converts the data received from the recipient s gateway into data in accordance with the first service and transmits it to the caller s home gateway . The arrows drawn in continuous line represent the path followed by the exchanged data.

In this embodiment the routing device comprises only one home gateway of a user not shown in of a first IP telephony service.

When that user referred to as the caller wishes to converse with a user referred to as the recipient of another IP telephony service the gateway sends to a plurality of home gateways a request R for at least one address of a home gateway able to provide interoperability between the two IP telephony services. The plurality of home gateways comprise for example a predefined number of home gateways using the first IP telephony service.

In this example the home gateways incapable of providing interoperability abstain from responding. Gateway responds by sending its address HGW  to gateway .

Gateway possibly chooses one of the home gateways from among those having sent their address on the basis of appropriate criteria for example distance or the congestion on the network.

Gateway then sends data in accordance with the first IP telephony service to the chosen gateway in this case home gateway . This data comprises data for opening an IP telephony session as well as actual information data. Gateway also receives data from gateway . The exchanged data is represented by a double arrow.

In this other embodiment the request R is sent to the plurality of home gateways by a server device in communication with the home gateway .

The server device may possibly receive a set of responses comprising several responses for example a negative response NOK and two addresses HGW  HGW . The server device chooses an address from among the received addresses and sends it to the home gateway . It is to the home gateway corresponding to that address that the home gateway subsequently sends data in accordance with the first IP telephony service not shown .

In this embodiment an indexing server stores in a memory parameters relating to the capability of a plurality of home gateways not shown of interoperability between a first and a second IP telephony service.

In this embodiment a certain number of home gateways are able to communicate with the indexing server . In an alternative embodiment which is not shown each gateway is associated with an indexing server storing parameters relating to the interoperability capability of a plurality of home gateways. The home gateway and the associated server may even be disposed in the same casing.

Returning to it suffices for the gateway to interrogate the indexing server so that the latter returns the address HGW  of a home gateway capable of providing interoperability. Gateway then sends data in accordance with the first IP telephony service to the gateway corresponding to this address and receives from that gateway other data in accordance with the first service as represented by the double arrow.

The transmission and receiving of data in accordance with the first service may be preceded by an exchange between the home gateway and the home gateway . During this exchange the gateway requests gateway to put it in contact with the recipient. For example gateway sends a message P comprising the address of the recipient an identifier of the recipient s service for example the second IP telephony service and an interoperability request. The recipient s address may for example comprise a pseudonym. The present invention is not of course limited by such an implementation of the exchange. The message P may for example comprise only a universal address of the recipient and an interoperability request.

If the gateway responds favorably gateway then sends data in accordance with the first IP telephony service. Gateway then uses APIs corresponding to the two services concerned in order to achieve interoperability. The home gateway therefore acts as an intermediary between the user of one service and the user of the other service. This function may be limited to signaling that is to say the gateway is restricted to transmitting the data or it may also comprise a processing of the exchanged data that is to say the data in accordance with the first service is processed in order to comply with the requirements of the second service and vice versa. The processing may for example comprise a change of protocol or even a transcoding.

The embodiments illustrated in and show only non limiting possibilities of implementation of the routing.

