---

title: Radio access network apparatus and mobile communication system using the same
abstract: The radio access network for allowing to construct a system abundant in scalability in a W-CDMA mobile communication system. A RNC in the radio access network is physically separated into a C plane control equipment for controlling signaling and a U plane control equipment for processing user data, where the user data is transferred between a mobile terminal and a host device via only the U plane control equipment and a control signal is terminated by the U plane control equipment and the C plane control equipment. This allows a system abundant in scalability to be constructed, and even in the case of soft handover across the C plane control equipments, also enables the continuous use of the same U plane control equipment, thereby eliminating the conventional connection path for connecting between RNCs and preventing delay due to passing through the RNCs.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07693524&OS=07693524&RS=07693524
owner: NEC Corporation
number: 07693524
owner_city: Tokyo
owner_country: JP
publication_date: 20060921
---
The present invention relates to a radio access network apparatus and a mobile communication system using it and more particularly to an improvement of a Radio Network Controller RNC in a W CDMA cellular mobile communication system.

An architecture of a W CDMA communication system that is a mobile communication system is shown in . A radio access network RAN is configured with radio network controllers RNC and Nodes B to and is connected with a core network CN as an exchange network via an Iu interface. The Nodes B to are logical nodes for radio transmission reception and more specifically radio base station apparatus.

An interface between the Node B and RNC is referred to as Iub and Iur interface is also standardized as an interface between RNCs. Each Node B covers one or more cells and is connected to a mobile unit UE via a radio interface. The Node B terminates a radio line and the RNC manages the Node B and selectively synthesizes radio paths in the case of soft handover. Note here that the detail of the architecture shown in is specified in 3GPP 3rd Generation Partnership Projects .

The data link layers L are separated into three sublayers of a MAC Media Access Control layer a RLC Radio Link Control layer and a BMC Broadcast Multicast Control layer . The MAC layer has a MAC c sh common share and a MAC d dedicated and the RLC layer has a plurality of RLCs to .

Ellipses in indicate service access points SAP between layers or sublayers where SAPs between the RLC sublayer and the MAC sublayer provide logical channels. That is the logical channels are provided from the MAC sublayer to the RLC sublayer and are classified by functions and logical properties of transmission signals and characterized by transferred information contents.

The logical channels include a CCCH Common Control Channel a PCCH Paging Control Channel a BCCH Broadcast Control Channel and a CTCH Common Traffic Channel for example.

A SAP between the MAC sublayer and the physical layer provides transport channels which are provided from the physical layer to the MAC sublayer . The transport channels are classified by a transmission form and are characterized depending on how and what information is transmitted via a radio interface.

The transport channels include a PCH Paging Channel a DCH Dedicated Channel a BCH Broadcast Channel and a FACH Forward Access Channel for example.

The physical layer and the sublayers to in the data link layer are controlled by the network layer RRC via a C SAP providing a control channel. The detail of the protocol architecture shown in is specified in TR25.925 of 3GPP.

In addition a C Control plane for signaling that transfers a control signal and a U User plane that transfers user data are specified in TR 25.925. The BMC sublayer in L is applied only to the U plane.

The RNCs of the radio access network RAN in the prior art are apparatus in which both functions of controlling the C plane and U plane are physically integrated.

In a mobile communication system including such a RNC that integrally has the control functions of both U plane and C plane the control function of the C plane is sufficient enough to be added in order to enhance the signaling processing capacity however the RNC itself is required to be added. Furthermore although the control function of the U plane is sufficient enough to be added in order to increase the transfer speed of user data the RNC itself is required to be added as well. Therefore the conventional RNC constitution makes constructing a system abundant in scalability quite difficult.

Moreover the following disadvantage arises in soft handover. When a UE mobile unit is in a usual setup status one Radio Link is connected between the RNC and Node B and when the UE is moved and comes into a soft handover status two or more paths are connected between the RNC and a plurality of Nodes B. When the UE comes into the soft handover across RNCs a path is connected utilizing an interface referred to as Iur see between a serving RNC and a drift RNC.

In such a status of soft handover across RNCs a path for user data may be connected from one U plane control function unit to a plurality of Nodes B involved in soft handover however another path for the user data needs to be connected between the serving RNC and the drift RNC wasting resources and causing delay due to passing through the RNCs.

It is therefore an object to provide a radio access network apparatus capable of constructing a system abundant in scalability and a mobile communication system using the same.

Another object of the present invention is to provide a radio access network apparatus which eliminates waste of resources and prevents delay in the case of soft handover and a mobile communication system using the same.

According to the present invention the radio access network apparatus is provided between a mobile terminal and a host device having an switching network in the mobile communication system and is connected with the mobile terminal via a radio interface. The radio access network apparatus comprises user plane controlling means for controlling transfer of user data in relation to the mobile terminal and control plane controlling means for controlling transfer of signaling having a control signal both of which are physically separated from each other.

The user plane controlling means has a function of terminating a data link layer of a protocol for the radio interface and the control plane controlling means has a function of terminating a network layer of a protocol for the radio interface. The user data is transferred between the mobile terminal and the host device via the data link layer of the user plane controlling means and the signaling is transferred via the data link layer of the user plane controlling means and the network layer of the control plane controlling means.

Furthermore the radio access network apparatus further comprises a radio base station having a function of terminating a physical layer of a protocol for the radio interface. The user plane controlling means further includes means for selecting data of high receiving quality from among the user data coming from a plurality of radio base stations involved in a soft handover state and sending out the selected data to the host device. Moreover the user plane controlling means is incorporated into the radio base station. The mobile communication system belongs to a W CDMA cellular system.

The mobile communication system according to the present invention includes the radio access network apparatus described above.

The embodiments of the present invention will be described below with reference to the drawings. is a functional block diagram of the embodiment according to the present invention where the same parts as in are indicated with the same reference numerals and characters. As shown in a RNC is physically separated into a C plane control equipment CPE Control Plane Equipment equivalent to a C plane for controlling signaling and a U plane control equipment UPE User Plane Equipment equivalent to a U plane for controlling user data.

All kinds of signaling between units are communicated directly with a central control processor CP Control Processor provided in the C plane control equipment . However RRC signaling between a mobile unit UE and the RNC cannot be distinctly separated into the C plane and U plane so is transferred to a RRC in the C plane control equipment after the U plane control equipment terminates RLCs and .

In this manner layers in the existing protocol layer architecture of the RNC shown in are separated into a Node B radio base station apparatus for the physical layer PHY denoted as L a U plane control equipment for the data link layers to denoted as L and a C plane control equipment for the network layer and above denoted as L.

The RRC in the C plane control equipment controls each unit for terminating the physical layer in the Node B and a MAC layer a RLC layer and a BMC layer in the U plane control equipment by means of C SAPs Control Service Access Point providing control channels. Signaling NBAP between the Node B and the RNC signaling RNSAP between the RNC and a C plane control equipment CPE in another RNC and signaling RANAP between the RNC and a MSC Mobile Switching Center or an SGSN Serving GPRS Global Packet Radio Service Switching Node are terminated and processed directly by the CP in the C plane control equipment .

Note that the MSC has a circuit switching function and that the SGSN has a packet switching function both of which are included in the core network CN shown in .

The RRC signaling utilized between the RNC and the mobile unit is transferred from the mobile unit via the Node B and the MAC layer and RLC layer in the U plane control equipment and is terminated in the RRC layer in the C plane control equipment . PCH FACH is terminated in the MAC c sh layer and the RLC layer in the U plane control equipment and is transmitted to the C plane control equipment since the relation between the Node B and the U plane control equipment is determined after Logical O M procedure Logical O M is the signaling associated with the control of resources owned by the RNC but physically implemented in the Node B and is specified in 3GPP Specification 25.401 and is not changed as far as station data is not changed.

DCH Dedicated Channel for transmitting user data allows the connection between the arbitrary Node B and the U plane control equipment and is terminated in the MAC d layer and the RLC layer to be transmitted to the MSC having a circuit switching function and the SGSN having a packet switching function through the C plane control equipment after paths between Nodes B are selectively synthesized in a selective synthesis unit of the U plane control equipment .

The selective synthesis unit selectively synthesizes DCHs from a plurality of Nodes B in the case of soft handover and selects a link having the highest link quality receiving quality from among these Nodes B.

The apparatus configuration shown in allows to construct a system abundant in scalability. That is only the C plane control equipment is added in order to enhance signaling processing capacity and only the user plane control equipment is added in order to increase user data transfer speed. Units in the user plane control equipment have no relation with one another and are controlled by the RRC in the C plane control equipment which thus enables implementation thereof as a single unit.

For example in the case that two C plane control equipments are utilized an algorithm such that the C plane control equipment is used when a mobile unit has the terminal number whose last one digit is an even number and the C plane control equipment is used when a mobile unit has the terminal number whose last one digit is an odd number is altered by utilizing three C plane control equipments to into another algorithm such that the C plane control equipment is used when the last one digit of the terminal number is 0 1 2 or 3 the C plane control equipment is used when the last one digit is 4 5 or 6 and the C plane control equipment is used when the last one digit is 7 8 or 9. This allows easy enhancement of processing capacity by 1.5 times.

On the other hand the U plane control equipment which performs transfer of user data has the possibility of lacking processing capacity with increasing quantity of transmitting receiving data to from each mobile unit. In this case by adding a new U plane control equipment processing may easily be dispersed. For example the constitution of connecting three out of Nodes Bto in subordination to each of two U plane control equipments is changed so as to connect two out of the Nodes Bto in subordination to each of three U plane control equipments and which allows an increase of the transfer speed by 1.5 times.

A soft handover request is notified as MESUREMENT REPORT RRC from the terminal UE to the C plane control equipment via the Node B and the U plane control equipment step S . The C plane control equipment obtains an IP address for soft handover in regard to the U plane control equipment and notifies the U plane control equipment of the IP address together with RADIO LINK SETUP REQUEST step S . The U plane control equipment responds to the C plane control equipment by RADIO LINK SETUP RESPONSE step S .

Next the C plane control equipment transmits the IP address of the U plane control equipment obtained for soft handover together with RADIO LINK SETUP REQUEST RNSAP to the C plane control equipment managing the Node B as a moving destination step S . The C plane control equipment transmits the IP address of the U plane control equipment obtained for soft handover together with RADIO LINK SETUP REQUEST NBAP to the Node B step S .

The Node B notifies the C plane control equipment of an IP address of the Nodes B together with RADIO LINK SETUP RESPONSE NBAP step S . Next the C plane control equipment notifies the C plane control equipment of the IP address of the Node B together with RADIO LINK SETUP RESPONSE RNSAP step S . The C plane control equipment notifies the U plane control equipment of the IP address of the Node B by RADIO LINK SETUP INDICATION step S .

By these procedures the IP address of the Node B is notified to the U plane control equipment and the IP address of the U plane control equipment is notified to the Node B thereby allowing the transmission reception of user data. At the same time the C plane control equipment notifies the terminal UE of ACTIVE SET UPDATE RRC step S . Then the terminal UE notifies the C plane control equipment of ACTIVE SET UPDATE COMPLETE RRC step S after which radio synchronization is started between the terminal UE and the Node B step .

After the layer L synchronization for the radio line between the terminal UE and the Node B is completed RADIO LINK RESTORE INDICATION NBAP is notified from the Node B to the C plane control equipment step S . The C plane control equipment transmits RADIO LINK RESTORE INDICATION RNSAP to the C plane control equipment step S after which the path is completely established between the terminal UE and the Node B . Consequently paths for soft handover connected to one U plane control equipment from the Nodes B and are established step S .

Thus in the case of soft handover across RNCs by connecting paths from one U plane control equipment to a plurality of Nodes B without establishing a path between a drift RNC and a serving RNC for user data soft handover may be achieved which enables the continuous use of the same U plane control equipment and thus eliminates the path between RNCs thereby leading to effective utilization of resources and preventing delay due to passing through the RNCs.

Next a conceivable modification is such that the RNC is separated into the C plane control equipment and the U plane control equipment and that the U plane control equipment is incorporated into the Node B. In this case if the U plane control equipment incorporated into the Node B does not have the function of selectively synthesizing user data the selective synthesis unit in soft handover via a plurality of Nodes B is not executable. This means unenjoyment of merits of utilizing CDMA within radio zones. It is thus conceivable to provide each Node B with the function of selectively synthesizing user data to realize communication between Nodes B.

Next shown is how soft handover involving plural Nodes B is executed in the IP network shown in . It is assumed here that the C plane control equipment is notified IP addresses of the Nodes B.

The C plane control equipment designates a Node B controlling cells of the highest quality as a serving Node B. Both the Nodes B compare their own IP addresses to the IP address of the serving Node B and when such own IP address is the same as that of the serving Node B the Node B having the same IP address recognizes itself as the serving Node B step S . Nodes B other than that recognize the IP address of the serving Node B as a transfer destination for UL Up Link data step S .

Each Node B secures resources necessary for setting up a radio link and then returns RADIO LINK SETUP RESPONSE message to the C plane control equipment steps S and S thereafter establishing the synchronization of the U plane step S .

In the case of DL Down Link data transfer step S the serving Node B transfers data to the IP address of the other Node B notified in the RADIO LINK SETUP REQUEST massage step S . In the case of UP Up Link data transfer the serving Node B compares data received from each Node B with one another and transfers data of the highest quality to the host step S .

First a radio link is setup step S for a new Node B Node B in by means of RADIO LINK SETUP REQUEST massage step S and RADIO LINK SETUP RESPONSE message step S and then all the Nodes B involved in soft handover are notified of the IP address of the serving Node B and IP addresses of Nodes B involved in soft handover.

As means for the above a new massage of SOFT HANDOVER INDICATION should be proposed steps S and S . This massage includes the IP address of the serving Node B and IP addresses of Nodes B involved in soft handover. Operations thereafter is the same as those in so are indicated with the same reference numerals and characters.

The example of providing selective synthesis function to each Node B is described above although such installation of the selective synthesis function to the Node B raises a problem of increasing the production cost of the Node B. To solve the problem it is conceivable to provide the selective synthesis function to only one Node B out of plural Nodes B. In this case user data is terminated in the Node B having such selective synthesis function at the time of soft handover via plural Nodes B. This may result in maintained soft handover function which is an advantageous feature of CDMA.

To realize such processing the CN is necessary to have IP addresses locations the presence of the selective synthesis function load status and the like of all Nodes B within the IP network . In the example of the CN notifies the Nodes B and of an IP address of a serving Node B and the Nodes B and transfer data to the serving Node B. The CN also instructs the Nodes B to function as a serving.

When selecting the serving Node B from Nodes B other than those involved in soft handover the CN takes account of physical distances between the Nodes B involved in soft handover and the Node B working as the serving Node and load status of the Nodes B targeted for the serving.

As described in the above according to the present invention a RNC is physically separated into a C plane control equipment as a signaling control unit and a U plane control equipment as a user data processing unit thus allowing a system abundant in scalability to effectively be constructed. In addition each unit in the U plane control equipment has no relation with one another enabling separate installation.

Furthermore even in the case of soft handover across the C plane control equipments the same U plane control equipment may be continuously utilized which eliminates the conventional path between RNCs and thus effectively prevents delay due to passing through the RNCs.

Moreover even in the case that the Node B has the function of terminating user data which is performed in the present RNC and that such Node B is connected to an IP network by providing a selective synthesis function for user data to a predetermined Node B soft handover involving a plurality of Nodes B may effectively be achieved.

