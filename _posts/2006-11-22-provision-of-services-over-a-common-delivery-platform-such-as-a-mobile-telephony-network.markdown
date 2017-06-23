---

title: Provision of services over a common delivery platform such as a mobile telephony network
abstract: A system for providing services to subscribers of a network supports the provision of a plurality of different services to multiple subscribers. Multiple processing units are provided, each providing a respective execution environment for a respective set of software applications. A data structure is provided containing data identifying the sets of software applications or software application components of the sets of software applications, and different developers are provided with different access rights to the data in the data structure. Different software applications or software application components are associated with different access right levels. This provides a software development environment in which a common services repository is provided with different access rights implemented for accessing the repository.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08375360&OS=08375360&RS=08375360
owner: Hewlett-Packard Development Company, L.P.
number: 08375360
owner_city: Houston
owner_country: US
publication_date: 20061122
---
This invention relates to the provision and use of multiple electronic services over a common delivery platform that is connected to a telecommunications network such as a mobile telephone network or a broadband network.

There has been an explosive growth in the range of services which can be accessed using mobile telephony devices such as mobile telephones and PDAs.

As the range of services grows different standards and protocols are suitable for different classes of service. For example a mobile telephone may be used to operate real time services web services and rich media services.

Real time services typically implement well established telephony functions such as call divert messaging call forwarding functions and ring back functions to name a few . These real time services are characterised by the fact that dynamic status information such as whether or not a telephone is engaged at a particular point in time dictates the functions to be implemented. These real time services control the mobile connections in real time and are therefore synchronous in nature. A particular set of protocols and standards is appropriate for implementing these functions for example signalling system 7 SS7 and SIP interfaces which can be controlled from a JAIN SLEE type environment. The processor for implementing the functions will typically support state based processing.

Web services typically implement more adaptive functions and can use a wide range of data resources from third parties. For example web services can include banking services shopping notifications such as sports and traffic news and software download functions. There are two types of web services. Well known operations on the internet are often called web services these are content oriented operations. There is also emerging a more formalised service oriented form these web services are self contained modular business components that have open Internet oriented standards based interfaces. The standards behind web services were created out of the industry s need for standard and open protocols to link businesses together. With the emergence of more formalised web services customers suppliers and trading partners can communicate independently of hardware operating system or programming environment. XML based standards such as SOAP UDDI and WSDL enable web services to be easily published located and invoked over open Internet protocols like HTTP. Web services are asynchronous and are delivered on a best effort basis. Web services standards have been taken from a number of standards bodies. The emerging more formalised web services also need the ability to be discoverable at runtime and during development.

Standards for rich media services are currently being formulated for example for high speed real time applications such as processing of live image data such as video streams. Implementation is typically with proprietary standards. These services will require the use of further protocols standards and processing methods which are now emerging for example vector oriented processing techniques.

It can be seen from the above that the range of different services and service types suitable for implementation using mobile telephony gives rise to many different environments for the creation of services and applications. Each of these environments requires programmers with different skills and software tools and a highly distributed non homogenous environment results.

The access for users to the different services hosted by different service providers also gives rise to a complicated user access environment as access to different services will be based on different access policies typically based on the identity of the user. Individual users can have many different identities such as passwords usernames . One solution is to use a federated identity scheme in which different service providers accept each others authentication of a user so that a single sign on SSO operation can be carried out by the user to enable the user to browse between different services of different service providers. Single sign on schemes are known for implementation typically in a web container. There are also many different types of application programming interface for example CORBA based Java based and .NET based.

According to the invention there is provided a system for providing services to subscribers of a network wherein the system supports the provision of a plurality of different services to multiple subscribers and comprises 

The invention also provides a software development method for the development of software for providing a service to subscribers of a network wherein the network supports the provision of a plurality of different services to subscribers the method comprising 

The invention also provides a method of developing software for providing a service to subscribers of a network wherein the network supports the provision of a plurality of different services to subscribers the method comprising 

Examples of the invention provide a system for providing services to subscribers of a network wherein the system supports the provision of a plurality of different services to multiple subscribers. Multiple processing units are provided each providing a respective execution environment for a respective set of software applications. A data structure is provided containing data identifying the sets of software applications or software application components of the sets of software applications and different developers are provided with different access rights to the data in the data structure. Different software applications or software application components are associated with different access right levels. This provides a software development environment in which a common services repository is provided with different access rights implemented for accessing the repository.

An example of the application and service delivery system for a mobile telephony network is described below which provides an example of an implementation of the invention. The example given has numerous novel features and the scope of this patent is to be determined by the claims which focus on certain of the aspects described below. It should be understood that the invention as claimed can be used in many different contexts and it should not be assumed that all features of the system and methods described below are essential to the implementation of the invention as claimed.

Unit represents the network for example 2G mobile 3G mobile or fixed and data is transferred between the network and the network operator application service delivery system. All physical data interaction with the network subscribers takes place using the network . As shown the network may be implemented using a number of different technologies and this invention can be applied to conventional or indeed future mobile broadband and fixed telephony networks protocols.

The Real Time Services container hosts real time applications which typically depend on dial events of the subscriber equipment for example a handset or software agent on a PC. These applications are therefore implemented using state based techniques. Examples of the types of function implemented by applications hosted in the container are conference functions call forwarding functions presence information gathering push to talk over cellular functions walkee talkee type multi user operation ring back functions and messaging functions. These functions are characterised by synchronous run time functionality. These functions can be implemented in a high throughput low latency event processing application environment such as the Service Logic Execution Environment SLEE for example JAIN SLEE which is the Java standard for a telecommunications SLEE.

Access to the services hosted by the container may depend on the authentication using a SIM card or EP address supported by other credentials.

The Real Time Messaging Container is an environment currently under development for the streamed delivery of live rich media i.e. video content. Proprietary implementations are currently used and standards are now beginning to emerge. This is expected to include the use of vector oriented processing environments.

The Web Services Container hosts applications which involve increased interaction with third parties and may typically involve user interactions for example menu based selections. The Web Services environment uses synchronous protocols and is a highly distributed environment for example using J2EE and .NET application servers.

Access to the services hosted by the container is typically permitted on the basis of identity which is verified through a registered password or by cryptographic means.

Each container can be implemented using a modular software approach in which a particular application will call upon different software components for example service enablers resource adaptors and these may be shared between different applications. In this way an application is operated by an orchestration process which runs logic using modular service enablers resource adaptors. An application may involve use of service enablers inside or outside the network application service delivery system that is controlled by the operator. An application in a container may be itself made available for re use by other applications. Applications can be created in a variety of ways including but not restricted to programmatic languages like Java and execution of business process languages like BPEL.

The architecture shown in illustrates that each container hosts respective sets of business services unit . The sets of business service unit present the available functions and call upon service enablers in the respective containers to enable the business services to be executed. These business services are realised by orchestrations.

The containers are connected to each other through gateways as shown in . As shown gateways are provided between each pair of containers a service gateway between Containers a messaging gateway between the Containers a gateway between the Containers as well as a media gateway directly between the network and each of the three containers. Each container also implements policy enforcement.

The gateways control the routing of data such as requests for services between the containers and can be used to provide policy control points. The different services hosted by the containers will typically have different access conditions and the policy control points implement these conditions.

The architecture outlined above provides a simple structure with different standards used in different parts of the structure so that services and applications can be implemented in the most efficient manner.

The different containers may implement different access rights to third parties. For example the Web Services Container is preferred when allowing third parties to register services to the container and this registration right may be reserved to the network operator. Use of service enablers by third parties external to the network system may also be through a gateway with different access rights.

The hatched regions indicate where newly created services and service components are created. The arrows also indicate schematically that service capabilities created in one layer can be exported to the execution environment above i.e. to be available to more developers .

Each of the services implemented by the execution environments is associated with a respective homogenous service binding which provides the set of rules governing the interface with the service and defining the common structure of messages to be sent and received. Each service binding defines the way an API Application Program Interface is described and is a specific class of API.

To enable more effective reuse of software components and to facilitate the design and implementation of services for operation over the mobile network a common service repository is provided.

The common service repository may be an actual database in a single physical location or it may be virtual and physically distributed throughout the system. The common service repository stores information about available completed applications and service components namely service enablers resource adaptors and these are registered so that they are appropriately indexed. Each application or service component entry includes an API or service binding so that the repository includes multiple different types of service binding . The service repository serves all of the different types of execution environment for example the three different types of execution environment defined by the containers in .

In order to access the common service repository a developer read interface is provided. Access control filters ACF control the output to the developer and a library adaptor LA formats the output into a form suitable for a specific software development kit SDK .

By way of example shows the interface between four different software development kits and the common services repository. As shown schematically in each software development kit may be associated with a different development level of the structure of which is shown schematically in at .

Each execution environment is associated with a different API or service binding or set of APIs and service bindings. Data is stored in the common service repository according to the API service binding. For example a similar indexing structure may be used as in a conventional UDDI registry of white yellow and green pages. The white entry provides service provider contact details the yellow entry provides business details and the green entry provides technical interface details such as the API identity and the location of the API.

Developers create their application or service in their selected standard software development kit for example Borland JBuilder. The library of each SDK provides details of all available services and service enablers obtained from the common service repository. The library of each SDK will contain a list only of the services and service enablers which can be exported to the SDK taking into account an access policy. A direct portal interface can also be provided to the common service repository rather than through the SDK again subject to access controls.

Once a developer has completed an application or service component this can be registered in the common service repository using a developer write interface portal . The hosting details can also be registered for use by subsequent hardware configuration and software redeployment management systems.

New services are loaded into the service delivery environment using the hardware configuration and software redeployment management systems.

An operator s service delivery environment will comprise one or more of the containers of the system architecture of .

It can be seen that the common service repository contains a list of all the applications and services that a telecommunications operator can provide both internally and externally to the market through their various channels. Entries are provided for complete applications as well as application fragments and services that can be reused by other applications. The entries include the details of the programmatic interfaces of the application fragments and services.

The common service repository is structured taking into account the system architecture. For example the architecture described above has three containers each providing different execution environments. The common service repository can accordingly host entries relating to three service bindings or three sets of service bindings one for each execution environment. Multiple service bindings can be supported for a container for example two containers may have just one type of service binding whereas the other may have two classes of service binding.

The common service repository enables all services and application fragments to be found in one location or one virtual location and also enables the details of respective service bindings to be discovered from the same location.

This also enables the discovery of simple services to be composed into higher level services and enables the discovery of services for orchestration of services namely organising the flow of services within a container.

Access to the common service repository is controlled so that different developers have different access rights to discover application fragments and services. Some will be limited by their development tools and others may be limited by trust levels. For example an internal developer will have greater access rights than an external developer. By updating service component libraries in the SDKs used by developers from the common service repository developers can use the standard application creation tools they are familiar with.

The functionality of the common service repository can be enhanced by providing state information in the repository. shows a state model and this is explained further with reference to which shows that the common service repository is provided with a service sequence database which can provide additional information to the execution environment particularly to a state based service of the execution environment.

The service sequence database is used to describe relationships between the services. For example one service may require another to be run before it can be run. One service may require that it is followed by one or more other services. The required logic is created through the write interface and is saved in the service sequence part of the common service repository for access by means of the developer read interface.

As shown in the service sequences can be exported by an export unit to the execution environment for use by a state based service of that target execution environment.

This state based information enables a state table to be formed for the services of the repository. This can be used both for verification where the service sequence is known in advance and for state based programming purposes using a state model. Examples of the type of applications which will have particular services which follow or precede are services implementing different ringback tones for different callers or implementing push to talk over cellular functions.

The generation of a state model based on the different service components stored in the service repository enables state based programming to be used for sequencing the execution of service components even when those components are created independently. The advantages of state based programming are well known. For example the execution of software components is enabled without the risk of long term pausing of active processes blocking access or overloading the execution environment with parked execution threads.

By deriving a state table from the different software components in the repository the entry of state related information is simplified and a link is provided between the service creation tools and the execution environment. The common service repository thus draws together all of the resources for the creation of services in a most efficient manner.

As mentioned above developers of the network operator can register services in the common service repository and third party developers can also register services and service sequences.

The third party services are not always made available to others immediately and typically are first tested and the business relationship is first established. For this purpose the service repository is provided with a third party quarantine area . The third party services and service sequences are quarantined while the services and business conditions are tested or finalised by a third party evaluation unit . Only then are third party service registry pages and if required the service sequence pages available for use by other developers.

As discussed above there are many different execution environments in the system described. Different users will invoke and be subscribed to different services provided by the system. Access to the different services is typically permitted on the basis of the identity of the user. However users may have many different identities relevant to different services different passwords account numbers reference numbers MSISDN number etc and this complicates the task of providing user authentication for the different services offered by the network operator.

To overcome these difficulties the system is provided with a common user identity repository. This user identity repository provides a single identity system which the services may use and draws together all the smaller pieces of information about an individual user held in disparate systems.

The common user identity repository may again be provided as a single physical entity for example an Oracle database or it may be distributed as a number of databases for example with one in each container. The user identity repository is shown schematically in as block CUR common user repository .

When authentication of the user can be achieved the CUR provides a single identity for users for all access to services within the system. Thus regardless of the entry point of a user request into the control system a common identity is applied to the request to enable all other parts of the system to which the request is routed to recognise the user and derive the access rights of the user. In one possible implementation this can be achieved by re writing the http request header or equivalent of user requests with the user identity from the CUR. This task can be carried out by a traffic interceptor associated with the CUR. All traffic such as service requests passes through the traffic interceptor.

This mechanism enables direct access to all data in the CUR without the need to cross reference multiple instances of the name of a user.

If the user cannot be authenticated special identities can be applied depending on the access interface for example unknown public user trusted operator user and unknown developer.

The interceptor intercepts any new request and checks if the requestor identity is on the authenticated list typically forming part of the CUR and typically a locally cached copy. This list provides a mapping of input IDs to the CUR ID. If an input is received from an already authenticated user the CUR ID is placed in the request header and the request is forwarded with the new CUR identity.

If the requestor identity is not recognised an authentication function is implemented and the previously unrecognised user ID is added to the authenticated users list and an existing or new CUR identity is added to the request as before.

The request has then entered the system and while the request is within a trusted zone the CUR ID is the only identity information needed to make service invocation requests.

However to increase security and access flexibility each service can also be provided with a service interceptor. Upon receipt of a service invocation request these check if the CUR identity is valid and also if the user corresponding to the CUR identity has the required access rights. For example a check may be made of the age of the user the subscription status whether the CUR is part of a group membership scheme etc.

A refinement to this system enables different levels of trust to be attributed to different information data. For example a user may be authenticated to the common user repository in more than one way. There will exist a set of attributes about the user bound to the identity of the user and examples of these are 

These different information sources provide different levels of security and are established to provide different access rights. For example a user name and password for access to a portal service may be to enable a set of web pages to be accessed which are customised to the needs of the user. The authentication process may not enable any billing operations to be carried out and the level of security may be relatively low. It would therefore be undesirable for a user to gain access to higher security level information for example access to credit limit information or bills using this information.

In general terms it would be undesirable to allow a weakly authenticated connection to be used to modify data associated with another level of authentication or even to allow access over a weakly authenticated connection to that data. While hierarchical authentication schemes may be used this is not required.

There is therefore a need for levels of trust to be built into the system even when a single user identity from the common user repository is to be used to provide a common identity of a user for all services.

A set of data is considered active if the user has been authenticated using that data set for the session currently in progress. The common user repository thus includes data fields associated with the different data sets and these include timestamps to enable the active data set or sets to be determined. The active status of a user s authentication may also be retained in a service interceptor s cache which may itself be another portion of the common user repository.

The different sets are linked by links in the form of trust relationships and these links take into account a trust model that exists between the sets. These sets of information may form a simple hierarchy or a stack with progressively increasing levels of authentication associated with progressively increasing levels of trust. However a mesh type trust relationship may instead exist as shown schematically in . The links are based on a mapping of the various authenticated identities of the user. These may show that further authentication is required before an application user may safely imply attributes in the CUR are about the same user.

The different levels of authentication may for example comprise a simply identity request identity and password SIM or smart card identity public key authentication etc.

The trust relationship between sets may not be reciprocal and a more complicated chain of trust relationships will be established.

When information from the common user repository is read out written or modified the trust relationship is used. Thus the trust relationships can be used to implement a system in which 

The trust relationships together define a trust model which is a software implemented set of relationships between the different sets of data.

The manner in which a user has been authenticated to the user repository which determines which data set is active together with the trust relationships can be used to determine the actions that may be carried out namely services that can be invoked by the user and the access rights to information in the common user repository. System manager interfaces will additionally be provided permitting general access.

When a request is received from a user to invoke a service if the authentication level which has been used to provide the common user repository identity and the trust relationships are not sufficient to allow access to the server a response can be generated which requests further authentication.

A user dials in to the network and this is by means of a connection to the network . This provides access to the real time services container simply on the basis of the MSISDN of the telephone used. In a 2G network this was authenticated using the SIM card in the users mobile device.

The real time services container accesses the common user repository to obtain the single user identity and adds this to the header of the request message. This access to the common user repository may for example be made by a Home Subscriber Server HSS of the container .

The call may be directed to a number of a specific service for example for purchasing music and this service may be hosted by the web services container.

At this stage it can be determined that the authentication level associated with the interaction with the user so far is not sufficient for the request to be routed to the purchasing application in the web services container. The common user repository may then require further information to provide authentication associated with the appropriate set of user data before the request can be routed to the web services container through gateway .

Alternatively the level of authentication may be sufficient to allow browsing of the services provided. However if a purchase request is made by the user then further authentication will again be required.

There are a number of policy control points at which the active authentication level and trust relationship are used to determine if a request can be pushed forward. These are provided at each gateway. Furthermore additional direct access routes into services may be provided for the network operator and these portals not shown in will also be provided with access control.

The trust relationships in the common user repository may change over time and the system administrator can implement these changes.

The trust relationships can be described by listings numeric levels text files or state based relationships. The trust relationships enable a single common user repository to be created in a single real or virtual database rather than using separate databases with different access rights. This enables a more complete understanding of a user profile to be obtained and kept up to date and consistent.

The access rights determined by the trust model determine not only access to hosted services but also to the data in the common user repository. For example the trust model can be used to implement a system in which a subscriber or other user can access and modify data in the common user repository only if they have been authenticated by defined authentication credentials or authentication credentials determined by the trust model to be better.

The common user repository can be implemented as a single actual or virtual database. Alternatively multiple databases can be used each containing a set of attributes. One of these databases may be a home location register or a home subscriber server as used in 2G and IMS networks. These databases are then linked by a further table in another database that includes references to indicate how a user is authenticated to each database. This table then identifies the trust relationships.

A status field can be used to indicate the state of a particular set of attributes such as currently active inactive or a permanent status.

A further refinement of the system is that any container but most likely the web container also includes a state machine to interpret the user s accessibility status. As mentioned above Web service interactions are essentially synchronous in nature and any state information is temporary in nature and is not generally utilised.

However some state information can also be derived from web based communications concerning the dynamic status of a multiple transaction user session. This dynamic status information can also be placed in the common user repository. Thus the common user repository can also include dynamic network based information about links and devices and the dynamic state in a state model of the user session. This dynamic state is understood using a programmable state model.

A state machine typically located in the web container provides the model of the interaction state for any interactions by means of the web container. This model may for example include their location within a set of web pages being browsed the devices of the user that are active identification of the sessions that are running.

A service delivery platform unit of the web container can be used to derive the state information. As an example this information from the web container state machine can identify the best device to send data to when a user has multiple devices. The same common user identity can be used for all devices but the state based analysis of the status of multiple devices of a user can dictate the device to which a service should be delivered. For example a colour map should be sent to a PDA with a larger display in preference to a mobile telephone if this PDA device is active.

The state machine can also be programmed to interpret user interactions. If for example a user has not used a device for 6 hours should the system assume that the user is still available For some cases for example a static PC during work hours it may be correct to assume that the user is in fact available whereas the user is probably not available at the same static PC out of work hours. The user state must have rules to interpret inactivity. Rules for purposes such as timing out sessions and reroute requests can be added to the state table models. The state machine also takes account of the level of authentication of a user by accessing information in the common user repository in particular by determining which data set is or sets are active for the user.

The invention has been described in connection with an example of the application service delivery system for a mobile telephony network operator. The significance of this application is that many different types of service are provided to many different users and with different access rights and authentication protocols being used for different services. There are other technical arenas in which the same issues may arise and various aspects used in the system described above can be applied to other contexts. These include fixed and broadband networks.

One example of system has been described above and which embodies the invention as claimed. The system has been described only in sufficient detail to enable a full understanding of the concepts underlying the invention. Other features will be required to implement a practical control system and these will be apparent to those skilled in the art. However a brief discussion of key additional features is provided below 

The common management and billing unit has not been described above. This can be conventional and will include a billing module an asset management module customer relationship management module as well as a policy control unit. Management and billing may use the services provided in each container and may be made available as services in each container.

The system will additionally comprise an IP switching fabric unit and messaging service units for example a short messaging service unit which will again be conventional. SIP protocols may be used on the IP switching fabric inside as well as outside of the application service delivery system.

The common user identity used by the system does not necessarily need to be a new identity. For example the MSISDN number may be used as the common user repository single identity.

The system has been described above in connection with users of the system with mobile telephones or PDA devices. However the users may be automated devices. For example the services provided by the system may include such functions as taking meter readings providing traffic data to a car navigation system such as congestion data or routing data. The user can then be an electricity meter or a car navigation system. However the principles of service delivery as outlined above remain the same.

For completeness shows a complete system using the system described above to provide services to multiple users including automated users such as a meter or navigation system and human users with telephones or computer terminals . The system is linked to a network of base stations which provide the mobile network coverage and also links to the internet . also shows a wireless LAN base station as well as a wired terminal connecting to the internet .

The scope of the invention should of course be determined with reference to the accompanying claims rather than the specific preferred example described above.

