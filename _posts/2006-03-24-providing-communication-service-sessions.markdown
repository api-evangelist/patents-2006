---

title: Providing communication service sessions
abstract: A communication system and method thereof are configured to provide a service including a communication network including a charging entity and a service provision node. A user terminal is configured to transmit a session control message to the charging entity identifying a service provision threshold determined by a user of the user terminal for a session of the service requested by the user of the user terminal. Monitoring means is configured to monitor provision of the session and, if the provision of the session exceeds the service provision threshold, to notify the service provision node to performs a predetermined action upon receipt of the notification.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08626113&OS=08626113&RS=08626113
owner: Nokia Corporation
number: 08626113
owner_city: Espoo
owner_country: FI
publication_date: 20060324
---
This invention relates to providing communication service sessions in a wireless communication system.

Wireless communication systems enable users to access a wide variety of services whilst facilitating user mobility. Examples of mobile wireless communication systems include the Global System for Mobile Communications GSM and Universal Mobile Telecommunication System UMTS network standards. Many other mobile communication systems both digital and analogue can also be used to provide wireless communication services to users.

In addition to mobile communication systems wireless local area network WLAN systems offer users wireless services. These systems often provide high bandwidth services to users in hotspots areas of limited generally non contiguous coverage. Hotspots are often set up in areas of high user density such as airports or hotels. Examples of WLAN standards include amongst others IEEE 802.11b IEEE 802.11g and HIPERLAN. WLAN systems can be part of or complement mobile communication systems.

The most well established service offered by mobile communication networks is a voice telephony service. This is usually a circuit switched service whereby a channel is established for the duration of the session. In addition modern mobile communication systems offer a variety of other types of service. These services include for example wireless application protocol WAP services Internet access browsing gaming instant messaging and streamed information services amongst many others. Several of these services are supported using packet switched connections whereby packets of data are transmitted across the network when information needs to be sent rather than maintaining a connection for the whole session.

One of the most significant barriers to mass market usage of non voice services such as mobile Internet access is the concern by the end user s about cost both in terms of the magnitude of mobile access and service charges and the complexity and unpredictability of the tariff structure that underlies the charges.

In particular many users are used to the concept of paying for voice services on the basis of the time spent during a call. However many users are unfamiliar with concepts such as paying for the amount of data that is used during a session as is often used to charge for packet switched services. In addition when users are utilising a network that is not their home network this adds another level of uncertainty as to how much a service might cost.

An example of where this sort of uncertainty may arise is where a user of a mobile network is roaming internationally or when using a WLAN access network to connect to his her home mobile network operator services. The user might wish to ensure that a browsing streaming session that he she was about to initiate did not with all charges taken into account exceed a predetermined amount or that a notification would be provided to the user when a pre defined cost had been reached.

Prepaid charging mechanisms are known which protect against an overall overspend on the subscriber s part. Such prepaid mechanisms include Nokia IACC In Advance Credit Check Parlay Charging API Application Programming Interface CAMEL Customised Applications for Mobile Enhanced Logic RADIUS Remote Authentication Dial In User Service with prepaid extensions and Diameter Credit Control. However these mechanisms alone do not allow the user to control the costs of services down to a level of granularity of an individual service session. Other known cost controls can be used by a post paying subscriber to ensure that a predefined spending limit is not exceeded during the subscriber s billing period. These controls have also been described on a service specific basis e.g. to ensure that a subscriber will not spend more than a specific amount e.g. 30 on gaming services on his her monthly bill.

Whilst some limited control of service costs is possible using existing credit control mechanisms such as Diameter Credit Control for example by using the Service Parameter Info attribute value pair AVP this would only provide partial control of the costs of individual service sessions. To provide full control of the costs of individual service sessions additional AVPs would need to be defined and standardised which are not currently present in these mechanisms.

The impact that the uncertainty associated with the charging of non voice and roaming services was not initially envisaged when the networks to support these services were developed. As such there are no existing technical solutions to alleviate this problem. Adding support in the network to allow for greater control of the costs of individual service sessions requires additional signalling and information to be exchanged in the network as well as potentially requiring further user intervention. This obviously impacts the efficiency of service delivery and may increase service delivery latency. The problem which currently exists is how to provide control mechanisms in a wireless communication network in order to increase user confidence in the costs of non conventional services and hence the up take of such services whilst balancing any corresponding impact on the network in terms of extra signalling and delay. Such control mechanisms have not previously been developed as online charging systems and interfaces applications have not hitherto been advanced enough to enable this type of control.

An aim of the present invention is to provide a mechanism that supports user defined one off session specific cost control thereby giving the user of a certain service session confidence as to how much the service will cost.

According to one aspect of the present invention there is provided a method of providing a service in a communications network comprising 

transmitting a session control message from a user to a charging entity in the network identifying a service provision threshold determined by the user for a session of the service requested by the user and

monitoring provision of the session and if it exceeds the service provision threshold notifying a service provision node in the network which performs a predetermined action on receipt of the notification.

The service provision threshold can be monitored as a cost limit or other unit resource limit representing payment or can be converted into a network resource usage threshold for monitoring purposes.

In one embodiment the step of notifying comprises sending a notification message from the charging entity in the network to the service provision node in the network.

In another embodiment the step of monitoring comprises translating the service provision threshold to a network resource threshold at the charging entity transmitting the network resource threshold from the charging entity to the service provision node and monitoring network resource usage.

In another embodiment the step of transmitting a session control message is performed over a wireless channel. In another embodiment the predetermined action comprises terminating the session.

In another embodiment the predetermined action comprises sending a warning message to the user. In another embodiment the method further comprising the step of the user selecting whether to continue or terminate the session in response to the warning message.

In another embodiment the predetermined action is determined by the user. In another embodiment the predetermined action is defined in the session control message.

Preferably the method further comprises the step of authorising the user requesting the session of the service at an authorisation node. In another embodiment the step of authorising further comprises the step of the authorisation node querying a user profile. In another embodiment the step of authorising further comprises determining whether the user should be prompted to determine the service provision threshold for the session of the service.

According to another aspect of the present invention there is provided a communication system for providing a service comprising 

a user terminal arranged to transmit a session control message to the charging entity identifying a service provision threshold determined by a user of the user terminal for a session of the service requested by the user of the user terminal and

monitoring means arranged to monitor provision of the session and if it exceeds the service provision threshold to notify the service provision node which performs a predetermined action on receipt of the notification.

In one embodiment the charging entity is arranged to send a notification message to the service provision node notifying the service provision node that the service provision threshold is exceeded.

In another embodiment the monitoring means is arranged to translate the service provision threshold to a network resource threshold at the charging entity transmit the network resource threshold from the charging entity to the service provision node and monitor network resource usage.

In another embodiment the user terminal is arranged to transmit the session control message over a wireless channel.

In another embodiment the predetermined action comprises the service provision node being arranged to terminate the session.

In another embodiment the predetermined action comprises the service provision node being arranged to send a warning message to the user. In another embodiment the user terminal is arranged to prompt the user to select whether to continue or terminate the session in response to the warning message.

In another embodiment the predetermined action is determined by the user. In another embodiment the predetermined action is defined in the session control message.

Preferably the wireless communication system further comprises an authorisation node arranged to authorise the user requesting the session of the service. In another embodiment the authorisation node is arranged to query a user profile when authorising the user. In another embodiment the authorisation node is arranged to determine whether the user should be prompted to determine the service provision threshold for the session of the service.

Preferably the communications network is one of the following GSM GPRS UMTS or WLAN. Preferably the user terminal is one of the following a mobile phone a personal computer PC or a personal digital assistant PDA .

means permitting a user of the user terminal to define a service provision threshold for a session of a service requested by the user of the user terminal 

transmitting means arranged to transmit a session control message to a charging entity in a network identifying the service provision threshold and

means of establishing the service session over a wireless channel with a service provision node in the network 

According to another aspect of the present invention there is provided a communications network comprising 

a charging entity arranged to receive a session control message transmitted from a user identifying a service provision threshold determined by the user for a session of a service requested by the user 

monitoring means arranged to monitor provision of the session and if it exceeds the service provision threshold send a notification message and

a service provision node arranged to receive the notification message and perform a predetermined action on receipt of the notification message.

Reference will first be made to in which is shown a system for providing per session control of costs for a user. A user can access services over a network using a user terminal . The user terminal comprises a display for displaying information and images and a keypad for entering data. The user terminal may comprise alternative means of data entry such as a touch sensitive screen and a stylus. The user terminal may be for example a mobile telephone a personal computer PC or a personal digital assistant PDA .

The user terminal connects to a network using a wireless communication standard. The wireless communication standard could be GSM GPRS UMTS WLAN or any other standard suitable for communication between the user terminal and the network. Within the network is located a service gateway or portal . The service gateway or portal provides the user terminal with access to the requested service.

The service gateway or portal is connected to a service authorisation node . The service authorisation node can be for example an Authentication Authorisation and Accounting AAA server or a policy server. The service authorisation node has a connection to a user profile which can provide authorisation settings specific to the subscriber.

The service gateway or portal is also connected to a credit control server which manages the charging of the user. The credit control server is connected to a subscriber service session cost limits function which manages the session specific cost limits.

The user profile and the subscriber service session cost limits function are located in the user s home network. The credit control server may also be located in the home network.

The system shown in allows a user to define a one off maximum cost limit for a session that the user is about to begin. The credit control server associated with the service session is advised of a limit that the user has set. When the limit is reached the system allows for the user to be notified and or for the session to be terminated. This permits the setting of different limits for each session depending on the user s requirements and circumstances. The user may require that a new cost limit is set for every session that is started. Alternatively the user may configure their cost limits such that a default cost limit always applies to their sessions unless this is overridden by the user.

An example of the operation of the system shown in for the provision of per session cost limits can be seen in . shows the messages exchanged between the elements of the system in .

In step S a user initiates the use of a session based service for example an Internet browsing session a streamed information feed a gaming service etc. The service is initiated by the user contacting the service gateway or portal .

In step S the service gateway or portal responsible for the service requests authorisation for the use of the specific service by the subscriber from a service authorisation node as mentioned the service authorisation node may be a AAA or policy server .

The service authorisation node queries the user profile in step S to request the subscription specific authorisation settings. Then at step S the user profile responds by providing the user authorisation settings to the service authorisation node . The user authorisation settings may indicate that the user should be prompted to define a session specific limit for the use of the service. In alternative embodiments there may be a global service level setting used to apply this feature for all subscribers using the particular service in which case the service authorisation node can make the decision to prompt the user without the need for the information from the user profile .

In step S the service authorisation node provides all the necessary service authorisation criteria to the service gateway or portal . This includes the need to prompt for a session specific cost limit from the user.

The service gateway or portal utilises a user communication channel to commence or continue a dialog with the user of the user terminal in step S. The user is invited to specify a session cost limit or service provision threshold. This is done by displaying a message on the user terminal display in response to which the user can enter the cost limit or threshold using the user terminal keypad . The cost limit may be specified using currency units or alternative resource units. The user can also specify what action to take when the limit is reached. The action to take can be for example a notification on the user terminal display that the limit has been reached and the user may further have the option of continuing or terminating the session. Alternatively the user may configure the session to be automatically terminated upon reaching the limit. In a further alternative the choice of action may be configured in the network and not by the user. The mechanism utilised for dialogue with the user terminal can be for example the hypertext transport protocol HTTP or the session initiation protocol SIP or any other suitable mechanism.

Once the user has used the user terminal keypad to indicate a session cost limit and any additional information needed to define the behaviour of the system when the limit is reached this information is sent to the service gateway or portal in step S as a session control message.

In step S the service gateway or portal initiates online charging with a credit control server including the need for a session specific cost limitation and the values and attributes that should apply. This may take the form of additional information included within a standard credit control dialog for example using Diameter credit control. shows the structure of a Diameter credit control AVP of the type that can be extended to include information for per session cost control. The AVP shown is a service parameter info AVP . The AVP comprises a header which contains a code that identifies the AVP. In the case of a service parameter info AVP the code is . The AVP also comprises a service parameter type field which defines the type of service. The AVP further comprises a service parameter value field which contains the value of the service parameter type. shows the structure of a Diameter credit control AVP that has been extended to support per session cost control. The extended AVP comprises a header similar to the header shown in but this may be allocated a different AVP code. The extended AVP also comprises the same service parameter type and service parameter value fields as shown in . However the AVP has been extended to include a cost limit value field which contains the value of a cost limit defined by the user. The AVP has also been extended to include an action code field which defines the action to take upon reaching the cost limit.

In other embodiments the extended AVP may also include a separate flag to indicate whether a cost limit has been defined for a session although this may be encoded into the cost limit value field e.g. a value of zero in this field may indicate that no cost limit is set . In further embodiments an entirely new AVP may be used that only contains the header cost limit value field and action code field and is separate from the service parameter info AVP.

In step S the credit control server communicates with a subscriber service session cost limits function that is responsible for storing the temporary service session limit and maintaining counters of usage relative to the limit. The credit control server may be part of a larger charging system that also implements other functions such as correlation balance management offline charging rating management etc. and the cost limits function may be connected to this charging system e.g. the cost limits function is implemented in a rating server a balance server or a dedicated server . Alternatively the cost limits function may be implemented within the larger charging system that also implements the credit control server . In alternative embodiments the session specific cost limit value and the usage counters might be stored in different elements or functions and not in a single subscriber service session cost limits function usage counters are sometimes implemented within the rating system . In further alternative embodiments the session specific cost limit may simply be held in the working memory of the charging system or in the user profile server or service authorisation node .

The service gateway or portal then provides the service to the user terminal in step S. The service gateway or portal continues the session with the credit control server during the lifetime of the related service session as indicated in step S.

If the service usage reported using the session with the credit control server in step S exceeds the defined service session limit then this is captured by the subscriber session cost limits function at step S. Alternatively if the service usage exceeds a specified threshold for example set at 90 of the limit then this may also be captured by the subscriber session cost limits function .

In step S the service gateway or portal is notified of the limit or threshold being exceeded as part of the session with the credit control server . The service gateway or portal then performs the defined actions related to the limit or threshold being exceeded for example notifying the user and or terminating the service session as mentioned above at step S.

Therefore using the above described operation the user can ensure that a predefined cost limit is not exceeded for using a particular service.

An alternative embodiment for the operation of the system shown in for the provision of per session cost limits can be seen in . In the embodiment shown in the steps S to S are identical to those described with reference to above. In step S the service gateway or portal initiates online charging with a credit control server including the need for a session specific cost limitation and the values and attributes that should apply. This may take the form of additional information included within a standard credit control dialog for example using Diameter credit control as described above with reference to . However in the embodiment shown in the subscriber session cost limits function can be omitted. Instead at step S the charging system is used to translate the user specified cost limit via rating to a relevant network resource limit value for example expressed in Kbytes that is communicated to the service gateway or portal . The service gateway or portal then provides the service to the user terminal in step S . The service gateway or portal is then responsible for metering the resource usage against the limit value. When the limit is reached the service gateway or portal performs the defined actions related to the limit or threshold being exceeded for example notifying the user and or terminating the service session as mentioned above at step S .

As mentioned previously per session cost control is advantageous when a user is roaming internationally or when using a different type of network to access services such as a WLAN network. The following illustrative example describes how per session can apply in such a scenario. A user is a subscriber of a mobile operator in a first country. This operator may provide a public WLAN service that allows for the user and other subscribers to use WLAN access in various international partner network affiliated hotspots with authentication and billing being performed by the operator s network. A feature offered by the mobile operator is for subscribers to set session specific charging limits. The user takes advantage of the WLAN service when travelling in a second country and starts a WLAN access session in for example a coffee shop. The user is directed to a landing page that invites the user to set a session specific cost limit in his home currency for example Euros . The user is likely to be unsure of all of the roaming and access charges that will apply so the user defines a warning limit of say 2 Euros. The user can then start using the service. The user is notified for example via a HTTP redirection of the limit being reached after a certain period of time. The user may then decide that the charge is not unreasonable and continue to use the service or the user may decide to terminate the service at this point.

The above is merely an example of how the invention can be used and many other use cases are also possible.

