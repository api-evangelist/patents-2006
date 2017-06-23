---

title: Access control in a communication network
abstract: A method of controlling access to services of an IP Multimedia Subsystem (IMS) by a user based upon the user's location. In response to a user requesting access to a service, information identifying the user's location is provided to the IMS. Within the IMS, the provided information is compared with authorization information stored in a database. The authorization information includes information identifying prohibited and/or allowed access locations. Dependent upon the result of the comparison, access to the IMS services is allowed or denied.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08270418&OS=08270418&RS=08270418
owner: Telefonaktiebolget LM Ericsson (publ)
number: 08270418
owner_city: Stockholm
owner_country: SE
publication_date: 20060314
---
The present invention relates to access control in communication networks for example in IP Multimedia Subsystem networks.

IP Multimedia services provide a dynamic combination of voice video messaging data etc. within the same session. By growing the number of basic applications and the media which it is possible to combine the number of services offered to the end users will grow and the inter personal communication experience will be enriched. This will lead to a new generation of personalised rich multimedia communication services including so called combinational IP Multimedia services which are considered in more detail below.

IP Multimedia Subsystem IMS is the technology defined by the Third Generation Partnership Project 3GPP to provide IP Multimedia services over mobile communication networks 3GPP TS 22.228 TS 23.218 TS 23.228 TS 24.228 TS 24.229 TS 29.228 TS 29.229 TS 29.328 and TS 29.329 Releases 5 to 7 . IMS provides key features to enrich the end user person to person communication experience through the use of standardised IMS Service Enablers which facilitate new rich person to person client to client communication services as well as person to content client to server services over IP based networks. The IMS makes use of the Session Initiation Protocol SIP to set up and control calls or sessions between user terminals or user terminals and application servers . The Session Description Protocol SDP carried by SIP signalling is used to describe and negotiate the media components of the session. Whilst SIP was created as a user to user protocol IMS allows operators and service providers to control user access to services and to charge users accordingly.

Users of the IMS will access the services provisioned by the IMS via an access network and more specifically via Access Points APs of an access network. An example of an AP may be a base station of a WLAN or a Node B of 3GPP cellular network. It may be desirable to allow operators of IMS networks to control which APs may be used to access to their networks. For example a network operator may have negotiated a special tariff with a company that depends upon the company s employees accessing the operator s IMS network only via APs of the network operator.

According to a first aspect of the present invention there is provided a method of controlling access to services of an IP Multimedia Subsystem by a user based upon the user s location the method comprising 

The user may request access to the communication network by sending a SIP REGISTER method to the IP Multimedia Subsystem and the IP Multimedia Subsystem makes a registration decision based upon the comparison between the provided location information and authorisation information stored on the database.

In a preferred embodiment of the invention said database is part of a Home Subscriber Server of a 3G network core network. However this need not be the case and the database may be a standalone node that can be contacted directly by the authorising node e.g. by the S CSCF P CSCF or I CSCF.

A method according to any one of the preceding claims wherein the location information is provided to the IP Multimedia Subsystem by the user. Alternatively the location information is obtained from an access point by a node of the IP Multimedia Subsystem.

Typically said user requests access to the IP Multimedia Subsystem via an access point and said information identifying the user s location is an identification of the access point. Preferably the identification information comprises the access point s Media Access Control MAC address. A Connectivity Session Location and Repository Function may maintain identification information in respect of the access point and provide this to an authorising node of the IP Multimedia Subsystem.

In a preferred embodiment of the invention said comparison of the provided identification information with authorisation information stored on a database is performed at a Call Session Control Function of the IP Multimedia Subsystem network. Said Call Session Control Function may be one of a Serving Call Session Control Function a Proxy Call Session Control Function and an Interrogating Call Session Control Function.

Typically said database stores information identifying prohibited and or allowed locations on a per user basis said user request identifying the user.

According to a second aspect of the present invention there is provided an access point for providing a gateway to allow a user to access services of an IP Multimedia Subsystem and comprising 

According to a third aspect of the present invention there is provided User Equipment for accessing services of an IP Multimedia Subsystem the User Equipment comprising 

Preferably said means for sending the location information to the IP Multimedia Subsystem is arranged to include the information in a service registration message.

According to a fourth aspect of the present invention there is provided a Call Session Control Function for use in an IP Multimedia Subsystem comprising 

According to a fifth aspect of the present invention there is provided a system for controlling access to services of an IP Multimedia Subsystem by a user based upon the user s location the system comprising 

When a user wishes to access services provisioned by an IP Multimedia Subsystem IMS network the user must typically register with his or her home network this may occur at power on of the user s device . An IMS SIP client in the user equipment initiates the registration process by sending a SIP REGISTER message to a Serving Call Session Control Function S CSCF allocated to the user within the home network. On receipt of the REGISTER message the home network can allow or deny access to the IMS network by the user. A user s device or User Equipment UE will communicate with the IMS via some suitable Access Point AP . In the case of a mobile wireless terminal the AP may be a base station of a Wireless Local Area Network WLAN . Example APs are illustrated in the IMS over 3GPP architecture illustrated in . In addition to controlling user access to the IMS on the basis of user identity the IMS operator may wish to control access based upon the used APs. In order to do this the home network must have some means to identify the APs.

In a first embodiment information identifying the AP is retrieved and provided by the UE to the user s home network for verification against an authorisation database DB . The authorisation DB comprises information identifying which APs are authorized to access the IMS network. This may be a list of allowed APs a list of non allowed APs or a list of both allowed and non allowed APs. The authorisation DB is preferably provided as part of the Home Subscriber Server HSS a component of the 3G IMS core network although it is possible that the DB may be separate from the HSS. The list of allowed non allowed APs may be specific to a particular user.

When a user seeks to access the IMS network from his or her User Equipment the IMS SIP client in the User Equipment obtains the AP Media Access Control MAC address and or other attributes that identify the AP used to identify the AP on the radio link layer typically during the process of establishing the wireless link and IP connectivity. The MAC address is available in the lower protocol layers of the terminal so it needs to be possible for the IMS SIP client to obtain the identification information. This may be done in an appropriate Application Programming Interface API . Of course if the AP identity is broadcast by the AP on a higher layer there may be no need for an API.

After steps to steps and are carried out in order to authorise the used AP. This involves the S CSCF querying the HSS to find out if access from the identified AP is to be allowed for the user. Once the authorisation has been given a SIP 200 OK message is returned to the UE by the S CSCF at steps to . As is illustrated at step the S CSCF also optionally authorises the P CSCF. This adds a further level of security to the authorisation process and is particularly appropriate when a P CSCF is allocated to a user or enterprise.

Steps and may be performed at an earlier stage in the registration procedure for example after step in or even earlier if performed by intermediate nodes see below . Hence the UE includes the MAC address in the initial register message as well as later register messages as it does not know at which stage the S CSCF will authorise the AP.

In the case of a user attempting to access the network from a non allowed AP the SIP registration is rejected. The signalling sequence of is followed in this case. Steps to are identical to those shown in for an authorized AP. However in this second scenario the S CSCF query of the HSS leads to denial of access to the IMS network at steps and . A SIP 403 Forbidden message is returned to the UE at steps to . A text string explaining the reason for rejection could be included and displayed on the UE.

In the event of refusal of registration when the IMS SIP client is attempting to register from a non authorized AP the IMS SIP client may build a list of non authorised APs and not attempt to register with the home network via one of the non authorised APs.

In the embodiment described above where information identifying the AP is provided to the user s home network by the client the authorisation process does not require support in the network providing connectivity between the User Equipment UE and the IMS domain. However an alternative approach allows access network information to be retrieved by the user s home network thus requiring new network support to be provided.

According to this alternative approach information in the SIP message sent by the IMS SIP client to the user s home network is used to validate the origin of the SIP REGISTER e.g. by examining the VIA header checking for example that the correct P CSCF is being used. The different hosts and IP addresses traversed may also indicate the origin of the registration request. As part of the SIP registration procedure the P CSCF includes the AP MAC address and possibly other attributes that identify the AP . P Access Network Info header may be used to transport this information.

The HSS or other database may authorise the AP based upon any appropriate combination of the information retrieved from the CLF . For example the UE identified by the SIP URI need not be taken into account and only the AP MAC address is checked in combination with for example the originating P CSCF. Alternatively the SIP URI may be checked together with the AP MAC address and the P CSCF identity to decide whether or not access is to be allowed. This might be appropriate for example where predetermined users are authorised to access the network from predefined APs.

In the example in the registration to the IMS network is allowed and the SIP 200 OK message is returned to the UE at steps to . In the case of a non allowed AP the SIP registration is rejected the process following the sequence shown in . A SIP 403 Forbidden message is returned to the UE at steps to . The SIP 403 Forbidden message may be accompanied by a text string explaining the reasons for rejection.

According to a further embodiment a request for accessing an IMS network is made using a Generic Access Network GAN as illustrated in . The same principles described for the first and second embodiments apply. In this third embodiment the user s home network is accessed using the GAN and General Packet Radio Service GPRS . The AP provides IP connectivity for the UE and this is used to access a GAN Controller GANC in the GAN. When the UE has established the transmission link over the GAN and GPRS it attempts to register with the IMS domain as described for the first or second specific embodiments.

It will be appreciated by persons skilled in the art that various modifications may be made to the embodiments described above without departing from the scope of the present invention. For example the above description refers mainly to wireless access solutions e.g. a mobile terminal with Wireless Local Area Network WLAN . However the invention may be adapted for fixed access networks for example in the case of a PC with an IMS SIP client where the IMS SIP client is only allowed to be used on a certain PC or on a certain network.

In the WLAN case the prime identifier of the AP is the hardware address of the AP i.e. the MAC address. However other attributes may be considered as alternatives or in combination with the MAC address for example the Service Set Identifier SSID network identifier encryption keys used on the wireless network etc.

In the case of a PC where the client is tied to a specific PC the MAC address of the PC could be used. Where a PC is only allowed access to a particular network a network identifier for example an identifier received with Dynamic Host Configuration Protocol DHCP options could be used or the IP address of the enterprise Domain name server DNS which may also be obtained via DHCP.

In the case of a mobile cellular terminal the GSM UTRAN cell where the mobile terminal is currently located is known to the network and to the terminal and can also be used as identification information by the S CSCF HSS.

In the various embodiments considered above it is the S CSCF of the IMS which is responsible for authorising an AP via the HSS or other database. However it will be appreciated that other nodes within the IMS may take responsibility for this for example the P CSCF or the I CSCF. In this case the P CSCF or I CSCF will communicate directly with the HSS or other database. Alternatively it may be possible to perform authorisation at the CLF.

