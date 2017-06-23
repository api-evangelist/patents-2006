---

title: Emergency recording during VoIP session
abstract: A method and apparatus are provided for recording a call between a client and an agent through an automatic contact distributor. The method includes the steps of the automatic contact distributor receiving a recording request from the agent, the automatic contact distributor activating a recording program, the recording program sniffing traffic within a packet telephone of the agent to detect packets exchanged between the agent and client and the recording program recording the detected packets between the agent and customer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08351593&OS=08351593&RS=08351593
owner: Aspect Software, Inc.
number: 08351593
owner_city: Lombard
owner_country: US
publication_date: 20061106
---
The field of the invention relates to contact centers and more particularly to the recording of calls through a contact center.

Contact centers are generally known. Contact centers are typically used by organizations to handle contacts with clients.

In order to use a contact center the organization may promulgate by advertising or otherwise one or more communication system identifiers e.g. telephone numbers e mail addresses etc. through which a client may contact the organization. Alternatively the organization may obtain a list of communication system identifiers and automatically place calls to clients.

Contacts with clients may be established through any of a number of different communication system mediums e.g. PSTN e mail chat websites etc. . Once a contact is established a controller of the contact center may select and assign the call to an agent of the organization.

Selection of an agent may be based upon any of a number of criteria e.g. longest available agent skill etc. . When based upon skill the controller may first attempt to determine a purpose of the call. Purpose may be determined from the communication system identifier used to contact the organization or upon the identity of the client.

Alternatively in the case of a call originating from a website the purpose of a call may be determined from a web page from which the call originated. In the case of the PSTN the purpose of the call may be determined from the number dialed as provided by DNIS information.

The identity of the client may be determined from call associated information. Call associated information may include ANI information delivered along with a PSTN call or a source IP address in the case of e mail or chat.

In some contact centers voice and data communication with agents is centralized within the contact center and is accomplished under a packet format. In such cases voice calls with clients are supported at least from the contact center to the agent under a VoIP format. A gateway within the contact center may convert between the VoIP on the agent side of the gateway and a switched circuit format for example where the contact with the client is established through the PSTN.

While the use of VoIP on the agent side gives agents far more flexibility in being able to work from remote sites VoIP complicates agent support. For example where an agent perceives a threat the agent may wish to record a call. However there are no network devices that are capable of recording VoIP calls without the unnecessary difficulty of creating a three party connection. Accordingly a need exists for a way of recording VoIP calls that can be placed within the communication system rather than on the agent s computer.

A method and apparatus are provided for recording a call between a client and an agent through an automatic contact distributor. The method includes the steps of the automatic contact distributor receiving a recording request from the agent the automatic contact distributor activating a recording program the recording program sniffing traffic within a packet telephone of the agent to detect packets exchanged between the agent and client and the recording program recording the detected packets between the agent and customer.

Each client may be assumed to have a terminal and a telephone . Clients may use the terminal and or telephone to place receive calls to from the organization through the system .

Included within the system may be two or more agent stations . Each agent station may include a respective terminal and a packet VoIP telephone .

The packet telephones may each be provided with first and second Ethernet interfaces and associated IP addresses . The first Ethernet interface and address may be used for exchanging voice packets with clients . A second Ethernet interface and IP address may be provided for purposes of packet sniffing as described in more detail below.

Each VoIP telephone is provided with its own unique MAC number. Associated with the MAC number is a telephone number. Each time a VoIP telephone is connected to the network the VoIP telephone searches for the nearest server and registers its presence and availability to receive calls.

Each terminal is also provided with an access softphone program . In order to sign into the system to receive calls an agent activates the softphone software enters a unique agent identifier and a telephone number of the associated VoIP telephone .

The softphone software sends the agent identifier and telephone number to an agent sign in application within the host . The sign in application signs the agent into the system as being available for handling calls. To sign the agent into the system the sign in application may save the agent ID a port ID of the agent an IP address e.g. logical workstation number LWN URL etc. of the terminal and also the VoIP IP address and second IP address of the associated VoIP telephone into a respective agent sign in file . To complete the process the sign in application places a call to the telephone number provided by the signing in agent . When the agent answers the call on his VoIP telephone the sign in process is complete.

Once an agent signs into the system the agent is able to receive calls from clients . As calls are received from clients they may arrive through the Internet or through the PSTN . Alternately the system may place calls to clients through the Internet or PSTN .

In the case of a call from a client through the PSTN an automatic call distributor ACD may receive the call along with call associated information. The ACD may receive the call and transfer any call associated information e.g. ANI DNIS etc. to the host .

The host may receive the transferred information assign a unique call ID number and open a call file to track the call. The host may collect the transferred call associated information the call ID as well as an identifier of a trunk upon which the call was received and place the information into the call file .

An agent selection application within the host may select an agent to handle the call. Selection of an agent may be based upon any of a number of different criteria e.g. longest available most skilled etc. .

Once the host has selected an agent the host may set up a connection between the selected agent and client . In this regard a gateway may be provided between the ACD and host in support of a connection between the client and host . The gateway converts voice information from a switched circuit format to a packet format. The host may allocate a channel through the gateway and also a VoIP application within the host or gateway in support of a voice connection between the agent and the client .

The host may then send a Session Initiation Protocol SIP INVITE to a telephone of the selected agent . The phone of the selected agent may respond with a 200 OK and begin ringing. The selected agent may answer the phone and begin conversing with the client. During the conversation the selected agent may access a database within the host make entries and otherwise address the concerns of the client .

Alternatively a client may place a call to the organization using a VoIP telephone on a terminal . The host may detect the call and select an agent substantially as described above. The host may function to redirect packets between the selected agent and client or may simply transfer the call to the agent by functioning as a SIP REDIRECT SERVER.

Upon occasion the client may present a situation where the agent may want to record the call. This situation may arise in the context where the client makes threats or is otherwise abusive.

In order to begin recording the call the agent may activate an emergency recording request softkey on the agent terminal . Activation of the record softkey causes the terminal to send a recording request e.g. a SIP INVITE such as INVITE SOS SPECTRUM.COM to a recording setup application within the host . The Session Description Protocol SDP of the SIP recording request may include G711 recording capabilities.

The packet telephone of the requesting agent or the recording setup application may notify a supervisor about the request for recording. In this regard the recording setup application may send a SIP INVITE e.g. SOS.SUPERVISOR SPECTRUM.COM to a telephone of the supervisor allowing the supervisor to be joined into the call or to monitor the call. Upon detection of the SIP INVITE the supervisor s phone may begin to ring. The supervisor may simply acknowledge the INVITE by activating a softkey on a screen of the phone or answer the INVITE and be joined to the call.

Additionally or alternately the recording setup application may send a notice or e mail that is displayed on a terminal of the supervisor notifying the supervisor of the request e.g. timestamp switch call ID SIP CallID To From via information CallTags and CallID hostname.com . The information within the notice or e mail may provide a reference e.g. softkey that the supervisor can use to later play back the recording.

Within the host the recording setup application may take steps to being recording the conversation. The recording setup application may first recover an IP address of the terminal of the selected agent from within the from field of the recording request. With the IP address of the selected agent the recording setup application may access the agent sign in file and the call file created for the call to recover an IP address of the client the VoIP address and the second IP address of the selected agent .

With the IP addresses of the selected agent and client the recording setup application may send a recording request under a TCP IP format e.g. as a transaction link message to a recording processor either within the host or within a third party host shows the recording processor in both location even though only one would be used . The recording processor may function to collect and record packets exchanged between the agent and client .

Contained or associated with the recording processor is a protocol or network analyzer . The protocol analyzer functions to sniff traffic within a packet telephone of an agent . As used herein the term sniffing traffic means the use of a network analyzer or protocol analyzer program e.g. Ethereal to detect a particular type of traffic within the packet telephone and causing copies of the detected traffic to be routed to the recording processor . In the case at hand the type of traffic that the protocol analyzer detects is any packet between the selected agent and the client . To do this the recording processor may construct a sniffing filter F using the VoIP IP address of the selected agent and the IP address of the client .

In order to allow sniffing within the packet telephone an application programming interface for packet capturing tool e.g. Pcap libpcap WinPcap etc. is provided within each of the agent packet telephones . The packet capturing tool may be accessed through the second IP address hereinafter referred to as the Pcap IP address of the packet telephone . The Pcap IP address is used by the protocol analyzer to sniff traffic within the packet telephone by controlling the Pcap tool within the packet telephone .

In order to begin recording the protocol analyzer may transfer the filter to the Pcap IP address of the packet telephone of the agent along with instructions to begin sniffing for packets that meet the criteria of the filter . Upon receipt of the filter the Pcap tool begins capturing packets exchanged between the agent and client and transfers the packets to the protocol analyzer .

The recording application and protocol analyzer may also retrieve and record contemporaneous traffic between the agent and other entities for purposes of understanding the context of the perceived threat. For example was the agent engaged in too many conversations Was the agent confused as to the scope of the threat 

In this case the protocol analyzer may expand the filter to include any packet from the agent . Packets received by the protocol analyzer may be transferred to the recording processor where the destination IP address may be compared with the IP address of the client . If the IP addresses are different then the protocol analyzer may open a new thread to capture packets between the agent and the other party identified by the different IP address.

As the packets exchanged between the agent and client are received the recording processor may retrieve time stamps from a time base and associate a time stamp with each packet. The time stamped packets may be saved under a G711 format as a WAV file using Transport Level Security TLS within a recording file .

The recording processor may continue to record packets until the recording processing application detects that the agent has hung up or otherwise termination the call. Upon detection of this event the recording processing application may send another transaction link message to the host terminating the recording session.

A specific embodiment of method and apparatus for recording VoIP calls has been described for the purpose of illustrating the manner in which the invention is made and used. It should be understood that the implementation of other variations and modifications of the invention and its various aspects will be apparent to one skilled in the art and that the invention is not limited by the specific embodiments described. Therefore it is contemplated to cover the present invention and any and all modifications variations or equivalents that fall within the true spirit and scope of the basic underlying principles disclosed and claimed herein.

