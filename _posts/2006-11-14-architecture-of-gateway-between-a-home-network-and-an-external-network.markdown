---

title: Architecture of gateway between a home network and an external network
abstract: A Home Gateway (HGW) interconnects a Home Network (HN) and an External Network (EN), and is adapted to communicate with the HN and EN at a Network layer. HGW is provided with a Service Application Programming Interface Layer (SAPI Layer) capable of performing, at an Application layer, mediator functions for supporting communication and services between the HN and EN. Devices of the HN are able to communicate with devices of EN via the HGW, and to actualize services via the HGW.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08391299&OS=08391299&RS=08391299
owner: ECI Telecom Ltd.
number: 08391299
owner_city: Petach-Tikva
owner_country: IL
publication_date: 20061114
---
The invention relates to the field of services for the home user in the broadband networks environment. In particular the present invention relates to architecture of a gateway intended for supporting both communication between a home network and an external network and services for users of the home network.

The design and creation of services in the Home Network Environment has encountered many hurdles the biggest is the need for every device on the network to be able to communicate with the different servers in the Home Network HN and in the outside External say Internet Network. Although many protocols standardized many various services the current technology is still oriented to specific services and does not provide the flexibility to create new services without going through the whole process of standardization of the new services from end to end with all participants in the service actualization process.

Presently existing home or residential gateways between a home network and an external network such as Internet Ethernet etc. are capable of supporting communication between the two networks and enable providing some basic services for users of the home network for various network devices . However it should be noted that the mentioned capability is ensured by using or providing quite complex hardware and software means both at the side of home network devices and at the side of servers of the external network such as IP servers . Any new and or technologically advanced service which is desired for the home network devices becomes problematic beginning from just installing and connecting a new home network device up to any novel service requiring participation of a group of network devices of the interconnected networks . The problem stems from the need of intervention into the existing software architecture of the home network devices of the home gateway and or of the external networks services and thus from the need of seeking and producing new program patches for performing each of the newly required services.

A schematic example of a simple service can be seen in prior art illustrating the message interplay related to a Content Retrieval service the details are provided to demonstrate the complexity of the service performed by the prior art gateway . First phase demands IP initialization of the Home Network Residential Gateway RG from a Dynamic Host Control Protocol DHCP Server . Then Home Network Devices generally marked get their Local IP addresses from the RG . Second Phase includes Configuration of the HND by an Auto Configuration Server ACS . Third Phase is the phase where the HND can access the content which is provided by HTTP Server . The service creation and service actualization for other services is even more complicated then the content retrieval service. In other services different protocols can be involved e.g. SIP or H.232 other servers can be used Call Server Video Servers .

In case the desired service demands a combination of services e.g. a combination of voice data and video specific applications say similar to Net Meeting must be built on a PC like device for that specific service without having a possibility to use them for other services.

In parallel to the service actualization the end to end network must be configured to support the service. In the solutions that exist today these tasks are split between the service provider from server to the residential or home Gateway and the user from the Gateway to the HND . Harmonization of these tasks is still under debate either RG will take care of assuring end to end requirements or external controller will do it as part of IMS IP Multimedia Subsystem concept.

Addresses of Network layer commands arriving to the Gateway either from the side of Home Network or from the side of External Network have to be translated in any direction. The function of coordination the Home Network Devices addresses with External Network IP addresses is usually performed with the aid of modules like NAT Network Address Translation ALG Application Level Gateway or Proxy. NAT is indicated as in ALG and Proxy are respectively marked as and in .

In presently known solutions many of the HN attributes are discovered configured and directly controlled by the IN or Service providers e.g. Technical Report DSL Forum TR 094 August 2004 www.dslforum.org techwork tr TR 094.pdf.

Having described today s solution for service creation and delivery it is evident that any attempt to introduce new services demands understanding of Home Network technologies Provider Network architectures and protocols as well as the capability to integrate all technologies into a valid end to end service delivery platform.

U.S. Pat. Nos. 6 930 598 B2 Home Gateway Server Appliance and U.S. Pat. No. 6 317 884 B1 Video Data and Telephony Gateway describe various solutions that still do not solve the problem of cumbersome and complex coordination of services and protocols of different inter communicating networks as well as the problem of intrinsic capabilities of different network devices belonging to these different networks.

A relatively novel technology called PARLAY http www.parlay.org en specifications has been developed for supporting telecommunication services between a number of standard network applications and a telecommunication network. The Parlay Group aims to link Information Technology IT applications with the capabilities of the telecommunications world by specifying and promoting application programming interfaces APIs that are easy to use rich in functionality and based on open standards. Parlay integrates telecom network switches with IT applications via a secure measured and billable interface. Parlay presents the notion of an API that allows applications to interface the Telecommunication Network for example a central office of a PSTN network with the aim to allow multiple network services to be then offered to telephony users.

U.S. Pat. No. 6 690 782 B2 describes a way of implementing the Parlay concept between an application layer a service layer and a protocol layer of a telecommunications network. Neither Parlay nor the U.S. Pat. No. 6 690 782 B2 has reference to a home network specific home network devices nor specific home network services.

The Inventors point out that there has been a long felt need of providing such a home residential gateway for interconnecting a home network with an external network which would overcome disadvantages of the presently used home gateways i.e. would alleviate communication between the home network and the external network and creation of various new services for users of the home network. Providing such a home gateway is the object of the invention.

To achieve the above object this invention proposes a new architecture of a home gateway HGW to be placed and utilized for communication and service actualization between a home network HN and an External Network EN the HGW being adapted to communicate with the HN and EN at a Network layer and being provided with a Service Application Programming Interface Layer SAPI Layer capable of performing at an Application layer mediator functions for supporting communication and services between the HN and the EN.

More particularly when the HN comprises a number of different home network devices HNDs and an external network EN comprises one or more external network devices ENDs said SAPI Layer of the HGW enables any one of the home network devices HNDs 

In other words the preferred embodiment of the HGW which should probably become widespread or even standard in the closest future ensures communication and services for said different HNDs even in case when no one of the HNDs has individual capability of communicating with the ENDs. The new architecture of HGW will therefore result in a possibility for a user to utilize simple and economic HNDs and in the long term in simplifying all types of home network devices HNDs.

The proposed invention also allows the communication and actualization of services in the opposite direction too by enabling network devices belonging to the external network ENDs to communicate with the network devices of the home network via the HGW by utilizing the novel mediator functions of the HGW. Preferably the External Network is an Internet Network.

Actually the proposed concept aims at creating a so called service level partitioning between the Home Network and the External or Provider Network. The architecture presented in the present description resolves the complexities of service creation and actualization from the user side of the network i.e. from the Home network and creates a Service Application Layer between the user side and the External Network so that the Service Application Layer masks the complexities of the External network beyond the Residential Home Gateway.

The main component of the Service Application Programming Interface Layer in the novel architecture of the HGW is formed by a group of Home network Application level Programming Interfaces HAPIs or HAPI modules that together compose a Home Network Application Layer HAPI Layer . Each of said HAPIs being designed to present a predetermined Application level Programming Interface API to at least one of the home network devices HNDs. The Home Network Application layer will be further shortly referred to as HAPI layer.

The HAPI layer of the SAPI Layer Service Application Programming Interface Layer can be defined as comprising a functionally complete set of Home network Application Programming Interface modules HAPIs . The functionally complete set of HAPIs can be understood as such a set of interfaces that enables performing within the HGW at least the functions that otherwise would have to be performed by said individual capabilities interfaces of all the HNDs connected to said HGW. It should be kept in mind that the mentioned individual capability or interface of a Home Network Device HND supports communication and services between the HND and the External Network EN .

The functionally complete set of HAPIs in the HAPI layer therefore makes unnecessary said individual capabilities of the HNDs i.e. HNDs could be produced without their complex individual interfaces.

Owing to the above described features the Service Application layer SAPI Layer is adapted to perform services within the Home Network access the External Network usually Internet for services outside the home network and combine services from both within the Home and in the External Network.

The SAPI Layer allows home network devices to provide new services for the home network user that activates HND without being aware of the details of the home network and its devices nor the External Network behind the Home Gateway. Since the SAPI Layer represents the services capabilities of both Home Network and its devices and the External Network and its devices the home network user s access to services at the external network shall be performed by activating specific HAPI s that own the capability to reach the external network servers. Similarly access of the home user to services within the home network is also performed by activating one or more specific HAPIs and their interaction with one another and the relevant HNDs. In view of the above the new architecture of HGW allows easy development of services for the home user based on using the HAPI layer and developing it by programmers of any qualification.

In other words the plurality of HAPIs modules of the HAPI Layer shall allow easy creation and actualization of services by service programmers even by those unable to understand the technologies behind the services both within the Home Network and in the Outside Provider External Networks since the creation of a modified or new service would require just composing a specific group of HAPI modules and actualizing thereof in a predetermined order of interaction.

The creation of a unified and probably of a standardized SAPI Layer and a standardized HAPI Layer means that Home Network devices will be able to get services from the External Network and shall facilitate many new services that cannot be implemented with currently known capabilities of residential home gateways.

From the point of protocol layers the invention can be formulated as proposing a Home Gateway HGW architecture for providing communication and or service via a Home Gateway HGW interconnecting a Home Network and an External Network and capable of terminating any one of incoming Network layer communication and or service commands and converting them into Application layer commands handling the Application layer commands within the Home Gateway for ensuring required services and establishing required communication the HGW further converting the Application layer commands for issuing outgoing commands as Network layer commands.

It is the Service Application Programming Layer SAPI layer of the HGW who is responsible for translating all Network layer commands incoming the HGW from either the Home Network Devices or the External Network Devices into Application layer commands and of handling said Application layer commands at the SAPI layer the SAPI layer is also responsible for outputting said Application layer commands either towards the Home Network Devices or the External Network Devices in the form of Network layer commands.

More specifically and in a particular case the proposed HGW is intended for communication and service actualization between an external network EN and a home network HN comprising a plurality of home network devices HNDs said HGW is provided with a plurality of Home Application Programming Interface HAPI modules forming a Home Network Application Layer which can be shortly called HAPI layer in the HGW the Home Gateway HGW being operative 

It should be noted that since the HGW is capable of translating any incoming Network layer commands into Application layer commands the commands incoming the HGW from said HNDs and is not requesting communication and or services involving participation of the ENDs e.g. related just to internal home network services and or communications will also be translated into the Application layer commands to be handled at the HAPI layer for further re translating said Application layer commands back to the IP layer commands to be issued to the Home Network Device s .

It should further be noted that the SAPI layer of the Home Gateway HGW may also comprise an External or Provider Network Interface Layer ENI layer for serving network devices of the EN ENDs . ENDs for example may be IP Servers .

The External Network Interface Layer preferably has functions with respect to the External Network EN analog to the functions which the HAPI layer has with respect to the Home Network HN.

When the SAPI layer comprises the HAPI layer and the ENI layer the internal communication within the SAPI layer between the HAPI layer and the ENI layer is preferably provided at the Application layer commands.

One of the major advantages of this invention is the creation of a unite and stable demarcation point between HN and EN say Internet network IN . This function is performed by the SAPI Layer within the HGW. The Unite Demarcation Point solves several problems that exist in today s networks when HN is a sub network within the IN. The unite demarcation point is efficient both at the network layer and at the service layer.

The IP Layer Addressing of the two realms IN and HN may be completely separate. The interface between the two networks is at the service application layer over the SAPI not at the network layer over IP .

This means that there is no need to perform at the HGW any Network Address Translation that causes problems for many applications e.g. L3 VPN VoIP and demands application specific algorithms to correct the problems caused by network translation e.g. Application Level Gateways for many on line gaming services Instead of that the HGW performs translation of incoming IP commands into commands of the Application layer to be handled in the SAPI layer of HGW and also performs translation of Application layer commands into outgoing IP layer commands.

The HGW performs all the tasks needed for services of the two networks. The HGW will perform the requests of the HN via the HAPI and all the tasks and services required by the IN EN entities over the applicable protocols of the ENI layer.

The HGW may be trusted by both providers Network and Services so there is no need to make other HNDs trusted although the HGW can serve as a relay if the HND must be a trusted device .

Creating a clear demarcation between HN and IN is not mandatory but it may appeal to some of the network providers. The demarcation point does not preclude the possibility to offer Remote HN Management Services. The remote Management shall be relayed via the HGW as any other service.

This demarcation point shall reduce the amount of knowledge the IN provider or Services provider have about the HN and HNDs on it.

The HGW will transfer only data that is requested by server when requested. This makes the HN a separate network that does not have to be discovered and directly controlled by the service provider. Remember that in the prior art many of the HN attributes where discovered configured and directly controlled by the IN or Service providers.

In order to implement the above mentioned objectives concerning developing new services for the Home Network HAPIs forming the HAPI layer preferably have specific structure and format.

HAPI shall have the format of a client server API. Depending on the side that needs a service done than some HAPI will behave with HGW as a Server and with HND as Client. Other HAPIs shall behave with HND as a Server and with HGW as a Client.

The HAPI implementation sequence shall define the message interplay and activities performed by the client or server at each step of the process. The implementation process shall also define irregular behavior and the actions to be taken in case of irregular conditions errors in message communications problems SW and HW problems.

In addition to the HAPI Layer HAPI s the HGW preferably comprises a Home Network Services Framework HNSF module capable of providing generic services to the HAPI layer to any of the HAPIs and to the Provider Network Interface Layer. The HNSF is considered to be part of the HAPI Layer.

For example HNSF may handle all real time issues for the HAPI layer and the Provider external Network Interface Layer.

According to a second aspect of the invention there is provided a system comprising the new Home Gateway HGW wherein the system also includes a Home network with Home Network Devices and an External Network with its entities ENDs the Home network and the External Network being capable of communicating with one another via the HGW.

According to yet another aspect of the invention there is proposed a method of providing communication and or services via a Home Gateway HGW interconnecting a Home Network and an External Network the method comprising

More particularly the method includes preliminarily providing in the HGW a Service Application Programming Interface Layer SAPI Layer comprising a functionally complete set of Home network Application Programming Interface modules. As has been explained above the functionally complete set can be defined as such a set of interfaces that enables performing in the HGW at its SAPI layer at least the functions that otherwise would have to be performed by said individual capabilities interfaces of all the HNDs belonging to the HN and connected to said HGW. We keep in mind that the individual capabilities or interfaces of the HNDs are to be understood as enabling to the HNDs communication with the EN and or support services involving the ENDs.

An additional subject of the invention is a software product comprising software implementable instructions and or data for carrying out the above described method as well as a carrier medium carrying the software product.

In view of the principles stated above and taking into account specific features which will be described below in more detail the present invention proposes 

Owing to the new architecture of the HGW the HNDs do not need to have individual capabilities interfaces for supporting communication services with one another and with ENDs across the networks since all the required interfaces the so called functionally complete set of HAPIs are provided in the HGW. The new architecture of HGW allows easy creation of new and modified services for HNDs since this process does not require knowledge of HNDs ENDs and high qualification from users programmers and providers. For example newly created advanced services for HNDs may be a providing popping up messages concerning all HNDs in a display of an HNDs presently active b providing home maintenance or household operations by remotely controlling HNDs by e mail etc. Combinations are numerous and can be dictated and limited only by the number and nature of HND devices connected to the HGW and the set of HAPIs currently available in the HGW.

The HAPI Layer shall provide to the HN devices HND HNDN any of the known interfaces and some additional complementing interfaces in order to perform for the HN devices both old and new services without a need for the HNDs to interact themselves with network nodes outside the HN.

The side preferably only HNDs but possibly also external network s IP servers that wishes to activate a service shall be responsible for activating the applicable HAPI Classes with the correct attributes features and in the needed sequence in order to actualize the service. Some of the HAPIs may be organizers for other ones.

Once HAPI classes are defined and the HAPI layer is built in general every service developer will be able to design new services or modify existing services by just creating a new process of activating the old existing or additional new different HAPI classes or by changing their specific attributes.

This methodology of new services creation shall allow the introduction of services by extending the HAPI Layer for new HNDs and or by Software SW upgrades to existing HNDs without any involvement of the Network or Service Provider. Specific OAM Operations Administration and Management classes within the HAPI Layer shall perform the aspects of a service that must be coordinated with the provider by activating predefined OAM HAPIs.

Example Suppose the HGW and HNDs support Standard TV STV and a new Set top Box is introduced with High Definition TV HDTV Capabilities.

The new HDTV STB shall use the same HAPI elements of the STV service with modified attributes of Bandwidth required in the HN. All other attributes may remain unchanged. Note that the change of attributes means there is no need to change SW version of the RG HGW . The HGW will have to ensure that the new bandwidth is delivered on the provider s network BW QOS . The HGW shall also have to ensure that the Service Provider delivers the service authentication Billing specific streaming contents selection . . . . However if we speak about the Home Network and devices in the HN the same HAPI can implement both STV and HDTV.

For the development of Home Network Services the developer has to understand the services he she can receive from each and every HAPI and their Interface requirements in order to design a service. The developer does NOT need to understand anything about the Residential Gateway HGW nor the Internet Provider External Network behind it.

With reference to an HND e.g. that wishes to initiate a service shall define the parameters of the services HAPIs demand to be indicated e.g. HAPI and HAPI and send the service invocation messages to them. The interface between a Network Device and the HAPI layer can consist of a whole protocol at the Internet layer including specific order and timing of the messages.

The HAPI then activates the required process to actualize the service. This is achieved by activating the proper networking and application layer protocols over the Internet Network to the Internet Servers e.g. . In other words the incoming Internet layer commands are terminated at the HAPI Layer converted into the Application layer commands and upon processing issued at the Internet layer for example via the ENI layer .

In this method the actualization of Home Network Services is divided between two Networks with the HGW RG serving as a service level mediator. There is no need to set up sessions in which one end is in an HND and the other end is in an IS. Sessions are established from HND to HGW and HGW to IS separately. All real time and coordination organizing issues if needed can be handled by a frame service HAPI module HNSF in the HAPI Layer of the HGW.

With the HAPI layer services for the HN are performed by the HGW and there is no need for the devices on the HN to know how to reach through the HGW and get services performed by an External Network Server. It is the HGW task to mask all the details of the Network outside and serve as a service level mediator between the two networks.

Class 1 HAPI shall be used for services being master or complete services upon which many services can expand. In the near term these HAPI will resemble the tailored solutions for Data Services Voice Services and Video Services but they will differ from existing solutions by implementing them in the HGW as Proxy Services. This will allow the HGW to serve legacy HNDs which are unable to address the HAPI for services.

Class 2 HAPI shall serve as building blocks for new services. The HND shall create services of concatenating and or interleaving processes that activate these building blocks HAPIs. Although the HND does not reach through the HGW to get services on Internet Servers the HGW shall implement this part of the service by performing the services requested by the HND over the Class 1 Class 2 HAPIs.

An additional HAPI type is a so called frame service HAPI module HNSF which is responsible for interconnecting various HAPIs and creating interactions there between for known and new services.

 Details and Examples of Various Classes of HAPIs will be Presented at the End of the Detailed Description Section 

Then the service crosses the external network over Layer 3 and arrives to the Internet Server where it is converted to the Application level that provides the service required.

In contrast schematically depicts the protocol layer diagram of the current invention. The most important detail in the diagram is that at the newly proposed HGW there is no direct Layer 3 Network Layer connection between HN and EN. At the HGW the service on the HN side is handled at the Application Layer commands by the activation of the HAPI layer modules of various classes HAPI Layer . In some cases the Application layer commands may pass in the same form to an optional External Network Interfaces layer ENI Layer .

From the Application Layer commands at the HGW the service continues to the EN IP realm of Layer 3 i.e. already in the form of Internet layer commands and crosses the EN to the Internet Server that performs the service at its application level. The service direction can be reverted. The service can be implemented from Internet Server downwards to the HND with utilizing the HGW again splitting the Layer 3 connection and providing connectivity at the Application layer between the two IP realms of EN and HN .

 The Following Section of the Detailed Description is Intended to Disclose the HAPI Layer Details and Examples 

All the examples below assume that the phases such as taking care of initialization configuration and mutual discovery of all participants are finished.

VoIP Call is an example of a complicated service. With today s technology the HND a VoIP Phone must implement the whole VOIP Protocol SIP or H.323 in order to implement the service. This is not sufficient since the NAT functionality in the HGW RG will interfere with the VOIP services addressing data contained in the messages body. Therefore the RG must implement an ALG for VoIP or perform the task of the proxy for the service.

Class 2 HAPIs comprise building blocks of services. The building blocks can serve to create complete services there from. The building blocks can be used at all stages of traffic creation. The HGW RG shall also provide framework services timers mail boxes event detector etc that will aid the service creation process by sequencing the proper method in the right timing. The timing depends on the presetting of the framework controller via the Framework HAPI. Some Class 2 HAPI Examples are presented below.

HND Discovery Upon power on HND looks for RG and notifies him about HND capabilities. The RG may use this data to update Network Service Provider on the change in the HN.

RG Authentication HND may Request to authenticate HND. Once HND is authenticated there is no need for additional authentication towards Network or Service provider.

HND Auto Configuration HND can ask and be configured by RG. Configuration Data may reside in RG or be requested from the Network in both cases the HAPI for HND is the same.

HND Configuration Update RG may change update the configuration of HND. Origin of change request may be RG or Network but in both cases the HND uses the same HAPI.

HND Request Streaming Download HND may ask for a streaming service. The request is received by RG HGW . RG performs all the steps required to allow the service including 

RG HGW Requests Streaming Upload Streaming contents can be uploaded from an HND to the network. The process is similar to download with source and destination reversed.

The RG shall provide framework services that will allow the HNDs and other HAPIs to create sequences of activities.

The Service Call a predefined list of phone numbers to invite them to a special Sale at the local store.

Implementation The message is recorded and the list of phones defined. The Timers are set to start calling at date XX YY DD at MM HH and call at each phone with intervals of P minutes. If there is no answer than call again within Q hours.

This type shall include combinations of class 1 and class 2 HAPI to create new services and variations of services.

The Expanded Class 1 HAPI Class allows breakpoint in the service implementation sequence so that the HND can take different actions in different situations. For example 

In this example the HGW activates several building blocks that are offered to the HND via predefined HAPI Layer 

The Expanded Content Retrieval Service can be further expanded to include other activities like Billing 

In this example the HAPI includes also Interaction with User via HND and Payment Method that activated Secure session in the HGW.

Note that in this case all aspects of secure payments may reside in HGW only for all HNDs in the HN including passwords credit card data authentication methods for other site etc . So the user does not have to input all this data and interact with other sites in order to make the payment. All data and interactive sessions may be provided by the HGW.

It should be appreciated that various additional HAPI modules can be created and introduced in the SAPI layer of the proposed Home Gateway in addition to the basic ones forming the functionally complete set of HAPIs for a Home Gateway serving a particular Home Network. The scope of the invention is defined by the claims which follow.

