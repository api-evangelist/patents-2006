---

title: Peer networking host framework and hosting API
abstract: A device hosting framework provides hosting for software-implemented logical devices (including peripheral devices bridges) on a computer to expose their services as controlled devices per a peer networking protocol. The device hosting framework encapsulates discovery, description and control protocol operations of the peer networking protocol, which frees the developers of the hosted devices from having to individually implement the peer networking protocol in the hosted devices' software and need implement only the core functionality of the hosted device. The device hosting framework operates as a host supporting device interoperability via the peer networking protocol for multiple hosted devices.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07774477&OS=07774477&RS=07774477
owner: Microsoft Corporation
number: 07774477
owner_city: Redmond
owner_country: US
publication_date: 20060119
---
This is a continuation of U.S. patent application Ser. No. 09 872 614 filed Jun. 1 2001 which in turn claims the benefit of U.S. Provisional Application No. 60 250 863 filed Dec. 1 2000. Both applications are incorporated herein in their entirety.

This invention relates to peer networking protocols and more particularly relates to host provided peer networking protocol support for hosted devices and software modules.

A peer networking protocol enables peer to peer network connectivity among networked computing devices. Examples of peer networking protocols include the Universal Plug and Play UPnP JINI HAVI Salutation and others. The UPnP protocol for example is designed for pervasive peer to peer network connectivity of PCs of all form factors intelligent appliances and wireless devices using a distributed open networking architecture based on TCP IP and Internet networking standards so as to enable seamless proximity networking in addition to control and data transfer among networked devices in the home office and everywhere in between.

Previously in the UPnP protocol a developer of a logical device including without limitation both hardware devices such as a portable MP3 audio player hardware and software devices such as an MP3 audio jukebox software application running on a personal computer that wished to expose the device for peer networking via the UPnP protocol would individually implement the UPnP protocol in that logical device. Additionally a legacy device built to use a non UPnP connectivity protocol e.g. a personal computer peripheral could be exposed for peer networking via UPnP by implementing a UPnP bridge which adapts between the UPnP protocol and the legacy device s non UPnP connectivity protocol. In either case the logical device developer or UPnP bridge to legacy device developer would have to expend considerable effort and work to implement the UPnP protocol in the individual logical device or bridge. Further where multiple logical devices and or bridges execute using the same hardware computing resources such as where logical devices for the MP3 audio jukebox application and a DVD movie player application together with a UPnP bridge to universal serial bus USB peripheral hardware devices are all running on a same personal computer the separate implementation of the UPnP protocol by each of these logical devices and UPnP bridges results in separate consumption of the computing resources.

The present invention facilitates the development of peer networking capable logical devices eliminating separate and duplicative implementation of a peer networking protocol by individual logical devices by providing peer networking hosting of the logical devices. A peer networking host implements the peer networking protocol and provides a programming interface for logical devices and bridges to expose their services to the peer networking protocol using the peer networking protocol implementation of the host. The logical devices and bridges are thus able to expose their services on the peer networking protocol without individually implementing the peer networking protocol.

In accordance with an embodiment of the invention illustrated herein a device hosting framework provides services for software and devices on a computer hereafter hosted devices to expose themselves as controlled devices per a peer networking protocol e.g. the Universal Plug and Play protocol or another peer networking protocol . The hosted devices can include bridges to computer peripheral devices and software that provide a set of services e.g. the device s functionality . The device hosting framework encapsulates discovery description and control protocol operations of the peer networking protocol which frees the developers of the hosted devices from having to individually implement the peer networking protocol in the hosted devices software and need implement only the core functionality of the hosted device. The device hosting framework operates as a host supporting device interoperability via the peer networking protocol for multiple hosted devices.

The device hosting framework defines application programming interfaces with which the hosted devices obtain hosting support for the peer networking protocol from the device hosting framework. The hosted devices register with the device hosting framework by providing information about their properties. The hosted devices also register service objects with the device hosting framework for each service hereafter hosted services they provide that is to be controllable through the peer networking protocol. The service objects individually implement a programming interface e.g. an IDispatch interface corresponding to a service description per the peer networking protocol for the hosted service that it represents. A utility to automatically generate the programming interface from the service description is provided with the device hosting framework for use by the hosted device s developer.

The device hosting framework services discovery and description requests in the peer networking protocol received from user control point devices that are directed to its hosted devices. The device hosting framework also listens for control requests in the peer networking protocol that are targeted at the hosted devices and services. The device hosting framework translates the control requests into calls to the service objects programming interfaces e.g. IDispatch interfaces . The device hosting framework also translates the return information from the programming interface methods into valid control responses in the peer networking device control protocol.

Additional features and advantages will be made apparent from the following detailed description of the illustrated embodiment which proceeds with reference to the accompanying drawings.

In the following detailed description one implementation of peer networking hosting according to the invention is embodied in methods products and systems that provide a hosting framework and hosting application programming interface herein called the Device Host and the Device Host API shown in to support peer networking interoperability for hosted devices and hosted bridges for bridged devices with other peer networking devices e.g. UPnP devices over a network . The peer networking protocol hosted in the illustrated hosting framework API implementation may be for example the Universal Plug and Play UPnP protocol which is discussed in more detail in the Appendix section below entitled Universal Plug and Play Device Architecture or any other peer networking protocol. In particular one implementation of the Device Host and API detailed below hosts devices under the UPnP protocol. Alternative implementations of the Device Host and API can host devices in other peer networking protocols.

The Device Host API enables software modules the hosted devices and bridges for bridged devices to publish themselves as peer networking enabled devices. These software modules including hosted bridges are referred to collectively as hosted devices. The Device Host encapsulates the discovery description and control protocols of a peer networking protocol thus requiring hosted devices to implement only their core functionality.

One implementation detailed below of the Device Host and Host API is designed to run on a computing device using the Microsoft Windows operating system. Alternative implementations of the Device Host and API can be designed for other computing platforms. The illustrated Device Host API is particularly targeted to hosted devices that are the hardware computing device itself bridges to computer peripherals connected to the computing device e.g. universal serial bus USB devices native IEEE 1394 bus devices native infrared IRDA port devices computer enabled cameras CD ROM and DVD devices and soft devices running on the computing device e.g. an MP3 audio jukebox application running on the computing device . Alternative embodiments can support peer networking hosting for hosted devices that are other kinds of hardware and or software based devices.

The hosted devices register themselves with the Device Host by providing information about their properties. They also register service objects with the Device Host for each service instance they contain. The services on hosted devices are referred to as hosted services. Each service object implements a dispatch interface corresponding to the Service Description for the service that it represents. This dispatch interface is generated automatically from the Service Description by a tool.

The Device Host listens for control requests targeted at the hosted services. It translates these requests into calls to the service objects dispatch interfaces. It also translates the return information from the methods on the dispatch interfaces into valid control responses. The following Device Host Architecture section specifies the parts of the Device Host responsible for receiving control requests performing these translations and returning control responses.

The Device Host API includes discovery description service control and eventing APIs that provide an interface for the hosted devices and bridges to the implementation of those respective layers of the peer networking protocol. These APIs are discussed in more detail in the following sections.

In summary the Device Host of the illustrated embodiment of the invention uses the following terminology.

Device Host The implementation of the Device Host API. The Device Host is called by hosted services to perform communications with a network. Functions performed by the Device Host include processing control messages sending event notifications and sending discovery announcements and search replies. Hosted Service A module written by a client of the Device Host API that exposes a service to the network. A service is able to receive commands from the network a Tape Transport service on a VCR for example would allow the network to stop play or rewind a tape. Hosted Device A collection of hosted services that perform a logical function. A VCR might be a logical device comprised of the Power Tape Transport and Tuner services. Device Host Architecture

For hosting by the Device Host the Hosted Devices and Bridges register their services with the Registrar via a registrar interface described below including providing discovery presentation and control information for their services so that the Device Host can respond to discovery presentation and control requests from other peer networking devices for the Hosted Devices and Bridges. In one implementation of the Host Architecture Hosted Devices and Bridges implemented in any of three ways can be registered with the Registrar including as a Device DLL or as a Device Provider DLL run in a container executable process and as a running executable program . In the Device DLL e.g. clientdevice.dll the devices and services can be COM Objects that support a set of interfaces described below for integrating with the Device Host. A registered Device Provider DLL e.g. clientprovider.dll implements a device provider described more fully below for registering device implemented by other programs. Devices implemented by a separate running executable program e.g. client.exe also can be registered. Any number of Device DLLs Device Provider DLLs and running Device executables can be registered. Alternative implementations of the Device Host can support registration of other types of programs and structures of Hosted Devices.

Once registered the service discovery API and server DLLs provide servicing of discovery requests for the registered services from other peer networked devices . Also the Web server services incoming requests for description presentation service control and eventing addressed to the registered services from the other peer networked devices. The Host Architecture further provides an eventing manager and automation proxy for each registered service to handle eventing and service control operations under the peer networking protocol for the registered services. The eventing manager publishes information of the device state to other peer networking devices that have requested notification under the peer networking protocol. The automation proxy receives service control requests under the peer networking protocol from other peer networking devices via the Web server and converts the service control requests to a procedure invocations of the respective service. Interaction between the registered hosted device services and the Device Host DLLs generally is accomplished through COM inter process procedure calls using a set of COM object interfaces described below.

Alternative implementations of the Device Host can be structured with various other software architectures such as with Device Host operations and interaction implemented in different configurations of executable programs library modules processes objects programming interfaces and procedure calls.

As can be seen from the foregoing discussion of the Host Architecture the implementation of the peer networking protocol is provided to hosted devices and services in Device DLLs Device Provider DLLs and Device executables by the Device Host in Host executables and libraries . This enables the device bridge developer to expose the hosted devices and their services through the peer networking protocol by writing the hosted device program as a library or executable to register and interface with the Device Host for hosting by the Device Host and avoid having to fully implement the peer networking protocol individually in each hosted device.

Further details of the Device Host API and the operation of the Device Host are discussed below. In the following discussion details specific to an implementation of the Device Host for the UPnP protocol on the Microsoft Windows operating system computing platform are described. It should be easily understood that these protocol and computing platform specific details can be readily modified in alternative implementations of the Device Host to support hosting of devices and services by the Device Host under other peer networking protocols on other computing platforms.

The Device Host API is a framework that facilitates implementing device functionality under a peer networking protocol e.g. UPnP or other peer networking protocol on the host computing platform e.g. the Microsoft Windows operating system or other computing platform . The Hosted Devices created with the Device Host API need only implement their core functionality and can rely on the API to handle the peer networking protocol specific details of discovery description control and eventing.

The Device Host API implements the core UPnP protocols discovery description control and eventing. The implementer of a hosted device must provide 

For example the implementer of a clock device provides UPnP device and service descriptions for the clock device and an implementation of the clock functions such as keeping time setting time and responding to queries for the current time . The Device Host API announces the device according to the UPnP discovery protocol responds to queries for the device s description routes control requests to the code that implements the clock functions maintains subscriptions and sends event notifications to subscribers when service state changes.

A UPnP device description is an XML document that describes the properties of a device and the hierarchy of nested devices within it. The schema for UPnP device descriptions known as the UPnP Template Language UTL for devices is defined in the Appendix the UPnP Device Architecture. Device descriptions contain links to service descriptions separate XML documents that define the list of state variables and actions in a service. Again the schema for service descriptions the UPnP Template Language for services is defined in the UPnP Device Architecture.

The implementer of a hosted device provides device and service descriptions for the hosted device. The elements of the device descriptions are defined as in the Appendix the UPnP Device Architecture with the following exceptions 

With reference to the behavior of a device is defined by the services it exposes. Each service has a service description that lists its actions and state variables. Together these comprise the service interface since they define the ways in which control points can interact with the service.

To implement a service a hosted device provides a COM object the service object that exposes the service s interface . In the service description the service interfaces are written in UTL but COM object interfaces are typically specified in IDL . The Device Host API provides a tool that translates a service description written as a service description in UTL to a COM dispinterface description written in IDL.

As an example of this translation consider a service interface description written in UTL. The interface translation tool given this interface definition would produce the IDL interface description shown in .

The hosted device then implements this dispinterface in order to provide the functionality of this service. The hosted device implementer uses the translation tool to translate each of the UTL interfaces of each service in the device description to an IDL interface and then implement each IDL interface in service objects . The objects that implement the service dispinterfaces will be referred to as service objects. In case of UPnP errors the service object would return a DISP E EXCEPTION and fill out the EXCEPINFO parameter to IDispatch Invoke. In particular the bstrSource field will contain the error code and bstrDescription will contain the error description.

In addition to implementing the service objects the hosted device must implement a device control object . The purpose of the device control object is to serve as a central point of management and control for the device s service objects . At registration time the device control object will be passed to the Device Host API and when a control request arrives for one of the device s services the API will call into this device control object to ask for the relevant service object. At that time the device control object can create an instance of the service object or return an interface on an already existing instance.

Device control objects must implement the IUPnPDeviceControl interface defined below. The Device Host API will call the IUPnPDeviceControl Initialize method on the device control object passing it the full text of the UPnP device description it published for the device and an initialization string specified at registration time. From this the device control object can read the UDNs assigned to each of the devices in the device tree.

When the Device Host API needs a pointer to a service object that implements a particular service on the device it will call the IUPnPDeviceControl GetServiceObject method on the device control object. It passes the UDN and the service ID of the service for which it is requesting a service object and the address of an IDispatch pointer at which the method is expected to return the service object. Note that the UDN parameter is necessary because the device control object manages services for the entire device tree including nested devices. The service object being requested might be on one of the nested devices the UDN identifies the device in question.

With reference now to registering a hosted device means providing the Device Host with the device description and its device control object . The Device Host then constructs complete UPnP device descriptions and publish these so that control points e.g. at UPnP Devices of can access them. The Device Host will then announce the presence of the hosted device using UPnP discovery protocols.

Regardless of which method is used the Device Host API publishes and announces the device as soon as it is registered. The difference between the two approaches has to do with when the device code is loaded in the first method the device code is loaded and running at the time of registration in the second method the device code is only loaded when a control or event subscription request arrives. Thus the second approach is slightly more optimized but is not suitable for devices that need to be running before any control or event subscription requests arrive for them.

Device registration happens through the UPnPRegistrar object of the Registrar in the Device Host API . This object exposes the IUPnPRegistrar interface defined in . To register a device with a running device control object an application e.g. the hosted device application client.exe of calls the method IUPnPRegistrar RegisterRunningDevice passing the following arguments 

Registering a device with a device control object that is not running can be done either through a command line tool upnpreg or programmatically via the IUPnPRegistrar RegisterDevice method. This assumes that the device control object has already been registered with COM. The command line tool takes the following parameters 

To register a non running device programmatically an application calls IUPnPRegistrar RegisterDevice and passes it the following 

Whether registered through the command line tool or through the programmatic interface the registrations of non running devices are persisted across system reboots in system registry . Therefore once a device is registered using IUPnPRegistrar RegisterDevice or upnpreg it will be published every time the system boots.

A hosted device can be unregistered using the method IUPnPRegistrar UnregisterDevice of the UPnP Registrar object . This method will remove the hosted device from the Device Host depending on the value of the fPermanent flag. If this flag is not set then the device will be removed however it can be re registered using the IUPnPReregistrar interface. The IUPnPReregistrar ReregisterDevice or the IUPnPReregistrar ReregisterRunningDevice methods using the original root UDN generated by the Device Host and announced on the network. If the flag is not set then the device will get permanently deleted from the Device Host.

Device Providers are registered objects that the system starts on every reboot. Their purpose is simply to register devices with the Device Host API in response to some event.

Device providers are particularly useful for bridging to polled media. Consider for example a peripheral device such as a digital music player connected to a computer via a serial port. To expose the music player as a UPnP device a device control object and a set of service objects would be needed to implement the UPnP music player actions as serial commands. But these objects should only be registered once the music player is plugged into the serial port and available for control. Since the serial port does not offer an explicit notification mechanism for when devices are connected some polling code is needed. This code could be implemented in a device provider object. At system startup the Device Host API instantiates the provider object and tells it to begin polling. When the Device Host API detected the presence of a music player device it instantiates the appropriate device control object and registers it by calling IUPnPRegistrar RegisterRunningDevice . This causes the hosted device to be published and thus exposed to the UPnP network.

The same functionality could be achieved by implementing an NT service that polled the serial port. Device providers simplify things by requiring only the core functionality the polling to be implemented since they rely on the Device Host API to start and stop their execution. Thus all the overhead of implementing an NT service is avoided.

Implementing a Device Provider involves implementing an object that exposes the IUPnPDeviceProvider interface defined below . This object must be registered with the Device Host API using the IUPnPRegistrar RegisterDeviceProvider method. This method takes three arguments 

At registration time and on every system reboot thereafter the system instantiates the device provider object and calls its IUPnPDeviceProvider Start method passing it the initialization string specified during registration.

Once the start method has been called the device provider can do any type of processing and when it deems necessary can register devices by calling IUPnPRegistrar RegisterRunningDevice as described in the previous section.

At system shutdown the Device Host API calls the IUPnPDeviceProvider Stop method to indicate that the device provider should terminate its operations.

Every user defined hosted service object implements a number of standard Device Host interfaces. One of these interfaces is the IUPnPEventSource interface. This interface implements two methods namely Advise and Unadvise . This provides a mechanism for the Device Host to subscribe to event notifications generated by the hosted service.

A hosted service object implements IUPnPEventSource Advise by querying the given IUnknown pointer for the IUPnPEventSink interface. If found it then holds a reference to that interface until IUPnPEventSource Unadvise is called or until the hosted service object is deleted. To remove the subscription the Device Host calls IUPnPEventSource Unadvise and passes in the same object pointer as for Advise . The hosted service will know to remove the subscription if the pointer is the same as the one passed to Advise .

When the hosted service wishes to notify the Device Host that an event has occurred it can then call the IUPnPEventSink OnStateChanged method to do so.

When the Device Host no longer wishes to receive notifications from the hosted service it will call IUPnPEventSource Unadvise passing in the same object pointer that it received in the IUPnPEventSource Advise call.

With reference now to the service control API in the Device Host API implements the UPnP control protocol which is described in more detail in the Appendix Universal Plug and Play Device Architecture. Specifically the service control API is responsible for

The service control API isolates all the UPnP protocol specific processing from the hosted device code making control requests look like simple method calls. shows a control system software architecture of the service control API of the Device Host .

All UPnP control messages travel over HTTP and the Device Host API includes the Web Server as its HTTP server for HTTP requests responses.

The Device Host API sets up the control URLs of hosted devices to point to the Web Server . When the Web Server receives an HTTP request with one of the hosted devices control URLs the Web Server verifies that the HTTP packet contains a control request parses the contents of the request and invokes the Automation Proxy for the service to cause the service to execute the control request. When the hosted device code returns the Web Server forms a UPnP control response and sends this back to the originator of the request over HTTP.

The deserializer makes use of an automation proxy object that provides the data type information required to translate data in the SOAP requests into the binary form required by the service implementations. Once translated the automation proxy object forwards the request to the hosted device code by calling into its service objects .

When the call completes the automation proxy object passes the return information return value and the values of any output arguments to the Web Server . This information passes through the following components 

The same Web Server will receive control requests for all hosted devices on a particular machine and therefore all control URLs will point to this extension. In order to make each service s control URL unique it will include a unique query string. Thus control URLs are of the following form 

This unique identifier is referred to as the service instance name. The randomly generated string in the service instance name ensures that the control URLs for the services on the hosted device are different each time the device is published . The following is an example of a complete control URL for a hosted service 

Given the service instance name in the control URL the Web Server is able to locate the service implementation in the hosted device. To do this the Web Server instantiates the Registrar and queries for the IUPnPRegistrar interface. Since the UPnP registrar is the central repository of information about running devices it is able to locate the service implementation in the hosted device. The Web Server calls IUPnPRegistrar GetAutomationProxy passing it the service instance name. This method returns the IUPnPAutomationProxy interface on the automation proxy object bound to the service implementation. The Web Server can use this automation proxy object to obtain type information from the service description or to invoke control requests on the service object.

The bodies of control requests contain XML encoded according to the SOAP rules. In processing a control request the first task of the SOAP parser is to read the entire request body sent by the client e.g. UPnP Devices of since the extension control block may not contain all of the request. The SOAP parser examines the cbTotalBytes field in the extension control block and if its value is greater than the value in the cbAvailable field the SOAP parser reads the remaining data using the ReadClient Web Server callback function.

Once the data has been read the SOAP parser converts the request from single byte to wide characters creates an XML DOM document object and loads the text into the document object. The SOAP parser then validates that the essential SOAP elements are present and correctly formed and extracts the data pertinent to the request. Specifically the SOAP parser creates an instance of the UPNP SOAP REQUEST structure shown in and populate the structure s fields by walking the XML DOM node tree created from the request text.

With reference to the bstrActionName field in the UPNP SOAP REQUEST structure contains the name of the action extracted from the name of the first child of the SOAP Body element. The pxndlArgs field contains a list of XML nodes that represent the action s arguments. These nodes contain the name of the arguments and their values represented in text form. This structure is passed to the deserializer which converts the argument values from text to their appropriate binary representations.

Using the type information from the UPnP Service Description for the target service the deserializer can convert the arguments in a UPNP SOAP REQUEST structure into their binary form. The deserializer places the deserialized values into a UPNP CONTROL REQUEST structure as defined in .

The deserialized request data is then passed to the automation proxy object that invokes the appropriate method on the service object to fulfill the request. The automation proxy returns with deserialized return information in a UPNP CONTROL RESPONSE structure defined in . This structure contains an anonymous union overlaying the return information for success and failure responses. The HRESULT returned by the automation proxy object determines which set of information should be examined. This information is passed to the Serializer before being encapsulated into a SOAP response.

The serializer converts the binary representations of the return values and output arguments returned by the automation proxy object into text XML form. The serializer does this by consulting the argument type information from the UPnP Service Description and using the XML DOM to encode the data appropriately. The serializer produces an instance of the UPNP SOAP RESPONSE structure defined in .

For success responses the serializer will convert the binary VARIANT representations of the output arguments and return value into XML nodes. The names of the output arguments will be obtained from the IUPnPServiceDescriptionInfo interface on the automation proxy object. For failure responses the serializer simply converts the UPnP error code into a string.

The SOAP Generator forms the XML text of a SOAP response based on the UPNP SOAP RESPONSE structure built by the serializer and returns this to the originator of the request.

With reference again to incoming UPnP control requests follow the UPnP control protocol rules for encoding and message exchange. Service implementations in hosted devices follow the COM Automation rules for method invocation. Automation proxy objects serve as the interface between the UPnP control protocol and COM Automation. Automation proxy objects take UPnP action names and deserialized arguments and make calls to the dispinterfaces on service objects . In addition automation proxy objects map data types of service state variables and action arguments as declared in the UPnP service description to COM automation data types.

The Device Host API obtains service objects by calling into the device control objects of hosted devices. Specifically the Device Host API calls the IUPnPDeviceControl GetServiceObject method to obtain an IDispatch interface on an object that implements a particular service.

The first time the API gets a service object it instantiates an automation proxy object to be bound to it. In the binding operation the Device Host passes the service object s IUnknown pointer and the text of the service description to an initialization function on the automation proxy object . Thereafter the newly created automation proxy object handles all incoming control requests to the service object.

During its initialization the automation proxy object parses the service description and build two internal tables one that stores the data types of service state variables and another that stores the data types of the arguments to the service s actions. These tables will then serve as the source for the data type information the automation proxy returns through its IUPnPServiceDescriptionInfo interface defined in Appendix UPnP Device Host API Reference . Note that these tables store only the names and data types not values of the state variables and arguments.

Automation proxy objects keep no state and after setting up data type tables at initialization time are completely read only. Thus any number of threads can call methods on an automation proxy object concurrently and no explicit synchronization is required. The automation proxy object is free threaded.

Automation proxy objects will be instances of the UPnPAutomationProxy coclass defined in the interface definition language description of .

With reference again to the Eventing API allows hosted devices bridges to notify interested UPnP Devices on the UPnP network of changes to their state.

The eventing API relieves the hosted devices bridges of having to write a UPnP GENA eventing server including accepting and maintaining client event subscriptions and generating UPnP event messages. Additionally the Eventing API provides automatic moderation for certain types of moderated events.

In the software architecture of the Device Host the eventing API is implemented using an eventing manager object . The eventing manager EM object manages subscription information for each service hosted by a device and handles submission of events for that service. If not already created the EM object is created by the Registrar object when a SUBSCRIBE request is received.

The Registrar is passed the UDN and service identifier for a specific service and returns the EM object. Eventing manager objects export the IUPnPEventingManager and IUPnPEventSink interfaces defined in .

The EM object is a light wrapper around the lower level eventing API. All of the methods of both the IUPnPEventingManager and IUPnPEventSink interfaces effect a call to one of the low level eventing APIs. Since the wrapper object is COM based the Web Server has the ability to communicate with the central host service from its own process. The methods are implemented as follows 

The Initialize method of the IUPnPEventingManager interface connects the EM object with the hosted service object supplied by the device writer and the automation proxy for that service. It also communicates the UDN and service identifier of the device and service for which it is handling eventing. Inside the Initialize method the EM object queries the hosted service object it was passed for the IUPnPEventSource interface. It will then call IUPnPEventSource Advise and pass its own outgoing interface IUPnPEventSink to the hosted service object. When the hosted service object wishes to submit an event it will call the OnStateChanged method on this interface. The EM object would then query the service object for the state variable names their new values and their types and internally call the HrSubmitEvent API.

The RenewSubscriber method takes the SID and timeout from the SUBSCRIBE request and renews the corresponding subscription. Upon return the timeout parameter receives the value chosen by the Device Host.

The RemoveSubscriber method takes the SID from the UNSUBSCRIBE request and removes the corresponding subscriber from the list.

The Shutdown method balances out the Initialize method by simply calling Unadvise on the IUPnPEventSource interface it has.

The IUPnPEventSink OnStateChanged method of the IUPnPEventSink interface is called by the hosted service object to notify the EM object that its state has changed. This method is hidden from VB users since they should use the OnStateChangedSafe method instead. The EM object then does the following 

The IUPnPEventSink OnStateChangedSafe method is intended for use by VB programmers so that they may communicate the names and values of variables that have changed to the Device Host. C programmers may call this method as well but it is not expected that they will do so since it requires considerably more work.

Every user defined hosted service object will implement a number of standard Device Host interfaces. One of these interfaces is the IUPnPEventSource interface. This interface implements two methods namely Advise and Unadvise . This provides a mechanism for the corresponding Eventing Manager object to subscribe to event notifications generated by the hosted service. This interface is defined in .

A hosted service will implement the IUPnPEventSource Advise method by querying the given IUnknown pointer for the IUPnPEventSink interface. If found it would then hold a reference to that interface until IUPnPEventSource Unadvise is called or until the hosted service object is deleted. To remove the subscription the EM object calls IUPnPEventSource Unadvise and passes in the same object pointer as for Advise . The hosted service knows to remove the subscription if the pointer is the same as the one passed to Advise .

When the hosted service wishes to notify the Device Host that an event has occurred it can then call the IUPnPEventSink OnStateChanged method to do so.

When the Device Host no longer wishes to receive notifications from the hosted service it calls IUPnPEventSource Unadvise passing in a pointer to its own IUnknown interface the same interface it passed to the Advise call.

A low level eventing API defined in is a private interface between the EM object and the central UPnP host service. It is a highly scalable API that is called for all hosted services on the computer.

All of the low level eventing API functions require the event sources identifier as the first parameter. The reason for this is to ensure that every function operates on a valid event source. Since all access to the event source and subscription information is guarded by a single critical section no eventing function is ever able to access this information without first obtaining the global lock and finding the event source identified by this identifier in the list of event sources. This has little to no effect of performance but guarantees concurrency of threads.

An event source identifier is a concatenation of the UDN of the device and the service identifier. So for example if we have a UDN of uuid 3cbaf80e 401a 4c29 be7c 8573c1af87f9 and a service identifier of clock 1 then the event source identifier would be uuid 3cbaf80e 401a 4c29 be7c 8573c1af87f9clock 1 . This uniquely identifies the event source in the global list of event sources.

When a UPnP hosted service is registered via the Registrar the Device Host will need to register this service as an event source. Part of the registration process involves passing the list of evented state variables and their initial values to the registration so it can be used for the initial event notification message for a new subscriber. This local cache of state variables and their values will be updated each time an event notification is generated.

Event source registration is accomplished with the HrRegisterEventSource API defined in . The following happens when HrRegisterEventSource is called 

When a hosted service is unpublished and thereby no longer accessible to control points its associated event source is deregistered. This is accomplished through the DeregisterEventSource API defined in . This API simply finds the event source in question and removes it from the list of event sources. It then frees any data that this event source referenced. The following happens when HrDeregisterEventSource is called 

The Device Host is responsible for handling and maintaining the subscriber list for each service that it hosts. The Device Host listens for new SUBSCRIBE and UNSUBSCRIBE requests parses them and processes them.

According to the UPnP architecture UPnP devices terminates any subscription that has not been renewed within the specified time period. To this end the Device Host tracks each subscription and its specified lifetime and terminates the subscription if it has not been renewed.

Incoming SUBSCRIBE and UNSUBSCRIBE requests are processed by the Web Server . The messages are parsed and validated for correctness before being passed to the appropriate eventing manager object for processing. The event subscription URL published in the description document for a device contains a parameter to the Web Server that will indicate which device and service the request was sent to. If no services match the identifier in the URL 404 Not Found is sent as a response.

When a SUBSCRIBE request is received it is parsed to obtain the relevant pieces of information namely the Callback NT and Timeout headers. The Callback header contains the URL to which NOTIFY requests should be sent when an event is submitted. The NT header should contain upnp event and nothing else. If a request contains something other than upnp event in the NT header it is ignored and 412 Precondition Failed is the response.

The Timeout header contains the subscriber s request for how long the subscription should last. Per UPnP see Appendix Universal Plug and Play Device Architecture the device controls what the timeout really is but it can choose to honor the subscriber s request. In the Device Host the preferred timeout is specified when the service is registered with the Host. If the timeout is 0 then subscriber s request is always honored. If it is non zero then the subscriber s request is never honored rather the timeout specified to the Host API is used instead.

After the SUBSCRIBE request is parsed and validated a new subscription ID is generated using the UuidCreate function. This along with the timeout value calculated according to the algorithm discussed above is placed into an HTTP response message. After the response is sent the SID and timeout values are associated with the subscriber.

Once a SUBSCRIBE is received and processed a timer is started. The timer will expire after the timeout period for this subscriber has elapsed. If the timer expires the subscription is terminated silently. This entails removing the subscriber from the list and intentionally not re starting the timer.

If a SUBSCRIBE request contains a SID header then it is considered a re SUBSCRIBE request. The SID header should match the one given to the subscriber as a result of the response sent to its initial SUBSCRIBE request. If the SID does not match then the 404 Not Found response is sent.

If a SID header is included in the request along with either an NT header or Callback header then the response 400 Bad Request is sent.

When the SID matches an existing subscription s SID maintained by the Device Host the subscription s timer is reset to the original timeout value. The response 200 OK is then sent along with the same SID header as was included in the request along with the same timeout value included in the original subscription response.

When an UNSUBSCRIBE request is received by the Web Server it is parsed to obtain the relevant pieces of information namely the query string and the SID header. The query string contains the identifier of device and the service from which the subscription should be removed.

If the SID header does not match an existing subscription for the requested service the response 404 Not Found is sent.

After the UNSUBSCRIBE request is parsed and validated the subscription to which the SID belongs is accessed. Its timer is stopped and the subscription is removed from the list. Then the response 200 OK is sent.

When one or more evented service state variables change the service MUST submit their changes as an event notification. The Device Host handles the submission of the NOTIFY request automatically. The hosted service communicates the fact that one or more state variables have changed by calling the IUPnPEventSink OnStateChanged method. This will inform the Device Host that it needs to query the hosted service for the values of these variables.

The HrSubmitEvent API relies on an event queue per subscriber as shown in the event submission architecture of in which to place pending event notifications. When an event is submitted it is placed on the queue for each subscriber for a pool of worker threads to act on sequentially. Each event queue is sequential. An item closer to the front of the queue is always processed prior to an item toward the back of the queue. Event zero notifications for a subscriber always is first in the queue before any other event notifications to that subscriber.

When an item is added to the queue an event is signaled so that a worker thread can begin processing it. Once an item is removed from the queue for processing the worker thread will handle sending the event notification to each subscriber. The heuristics defined here ensure that each subscriber s event queue is processed sequentially with the next item in the queue not processed until the previous item is complete.

The response to a NOTIFY request is ignored since there is no recourse for the device to have in the case of failure. Therefore these return codes will be used strictly for diagnostic purposes.

The initial event notification is sent using the HrSubmitEventZero API defined in . The following is the implementation of this API 

All requests from a control point e.g. at the UPnP Devices of that are sent to a Device Host computer pass through the Web Server that determines if the request is related to a device hosted on the machine. If so they are processed further. When the Device Host publishes a device and its services each service s event subscription URL will point at the Web Server. The query string part of the URL identifies the device and service for which a request is destined. The request method determines if it is related to control eventing or presentation. An example event subscription URL is as follows 

In the case of eventing the request method will be either SUBSCRIBE or UNSUBSCRIBE. Once the Web Server has determined this it processes the request as follows 

The response to an UNSUBSCRIBE does not have any additional headers so no additional work is required to send it.

The system bus may be any of several types of bus structure including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of conventional bus architectures such as PCI VESA AGP Microchannel ISA and EISA to name a few. The system memory includes read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help to transfer information between elements within the computer such as during start up is stored in ROM .

The computer further includes a hard disk drive a magnetic disk drive e.g. to read from or write to a removable disk and an optical disk drive e.g. for reading a CD ROM disk or to read from or write to other optical media. The hard disk drive magnetic disk drive and optical disk drive are connected to the system bus by a hard disk drive interface a magnetic disk drive interface and an optical drive interface respectively. The drives and their associated computer readable media provide nonvolatile storage of data data structures computer executable instructions etc. for the computer . Although the description of computer readable media above refers to a hard disk a removable magnetic disk and a CD it should be appreciated by those skilled in the art that other types of media which are readable by a computer such as magnetic cassettes flash memory cards digital video disks Bernoulli cartridges and the like may also be used in the exemplary operating environment.

A number of program modules may be stored in the drives and RAM including an operating system one or more application programs other program modules and program data as well as the Device Host and API .

A user may enter commands and information into the computer through a keyboard and pointing device such as a mouse . Other input devices not shown may include a microphone joystick game pad satellite dish scanner or the like. These and other input devices are often connected to the processing unit through a serial port interface that is coupled to the system bus but may be connected by other interfaces such as a parallel port game port or a universal serial bus USB . A monitor or other type of display device is also connected to the system bus via an interface such as a video adapter . In addition to the monitor computers typically include other peripheral output devices not shown such as speakers and printers.

The computer operates in a networked environment using logical connections to one or more remote computers such as a remote computer . The remote computer may be a server a router a peer device or other common network node and typically includes many or all of the elements described relative to the computer although only a memory storage device has been illustrated in . The logical connections depicted in include a local area network LAN and a wide area network WAN . Such networking environments are commonplace in offices enterprise wide computer networks intranets and the Internet.

When used in a LAN networking environment the computer is connected to the local network through a network interface or adapter . When used in a WAN networking environment the computer typically includes a modem or other means for establishing communications e.g. via the LAN and a gateway or proxy server over the wide area network such as the Internet. The modem which may be internal or external is connected to the system bus via the serial port interface . In a networked environment program modules depicted relative to the computer or portions thereof may be stored in the remote memory storage device. It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used.

In accordance with the practices of persons skilled in the art of computer programming the present invention is described above with reference to acts and symbolic representations of operations that are performed by the computer unless indicated otherwise. Such acts and operations are sometimes referred to as being computer executed. It will be appreciated that the acts and symbolically represented operations include the manipulation by the processing unit of electrical signals representing data bits which causes a resulting transformation or reduction of the electrical signal representation and the maintenance of data bits at memory locations in the memory system including the system memory hard drive floppy disks and CD ROM to thereby reconfigure or otherwise alter the computer system s operation as well as other processing of signals. The memory locations where data bits are maintained are physical locations that have particular electrical magnetic or optical properties corresponding to the data bits.

The device includes a processing unit and a memory to provide embedded computing capability. The processing unit has hardware interfaces to the operational circuitry that operates devices functions. The processing unit can be a microprocessor or micro controller such as are available from Intel Motorola IBM and others. The memory preferably incorporates RAM and ROM to hold software and data for basic operating code as well as for user applications including the Device Host and API .

The device also includes a network adapter for connecting with a network media that is interconnected with the computer network in which the authoritative names registry described below is implemented in accordance with the invention. The network adapter can be a network interface card or chip set integrated on a single board with the processing unit appropriate to the particular network media . The network media can be any of various wired or wireless network media including Ethernet IEEE 1394 a.k.a. firewire radio frequency including satellite cell pager commercial signal sideband etc. power line carrier PLC phone line and television cable among others.

Various embedded computing devices also connect to the computer network via various network connections to the PCs . These include an audio device e.g. speakers radio tuner microphone and printer which connect to the PC through a USB . Also a digital camera a handheld PC H PC and another personal computing device connect via an infrared port IRDA which also attaches to the PC through the USB . Also lighting switches and like home appliances are connected via an A C power line based networking to the PC . Further a chain of IEEE 1394 cables connect a digital TV DVD player digital video camcorder DV DVC an audio device e.g. CD player recorder radio receiver amplifier and like audio system component and a game console . Devices such as a portable telephone and remote control have a radio frequency network connection with the PC .

With their various inter networked connections the embedded computing devices are visible and accessible from a client device also connected to the computer network.

The IUPnPDeviceControl interface serves as the central point of management for the device and its service objects

The caller should use this interface to re register devices with the UDN originally generated by the device host on a call to IUPnPRegistrar RegisterDevice and IUPnPRegistrar RegisterRunningDevice .

If the method succeeds the return value is S OK. Otherwise the method returns one of the COM error codes defined in WinError.h.

If the method succeeds the return value is S OK. Otherwise the method returns one of the COM error codes defined in WinError.h.

This is the interface you must query for after the device host invokes the Advise method on IUPnPEventSource.

The IUPnPDeviceProvider OnStateChanged method sends an event to the device host with the list of DISPIDs that have changed. The device host will then query your service object to obtain the new values of the state variables. This method is hidden from VB users.

If the method succeeds the return value is S OK. Otherwise the method returns one of the COM error codes defined in WinError.h.

The IUPnPDeviceProvider OnStateChangedSafe should be used from VB and has the same functionality as IUPnPEventSink OnStateChanged.

If the method succeeds the return value is S OK. Otherwise the method returns one of the COM error codes defined in WinError.h.

The IUPnPEventSource interface allows the device host to subscribe unsubscribe to from receiving events from the hosted service.

The device host uses this interface to set up tear down the association between itself and the hosted service for receiving events

The IUPnPEventSource Advise method is invoked by the device host to set up for receiving events from the hosted service. The device host passes in a pointer to its IUnknown interface that the hosted service must query for the IUPnPEventSink interface.

If the method succeeds the return value is S OK. Otherwise the method returns one of the COM error codes defined in WinError.h.

The IUPnPEventSource Unadvise method is invoked by the device host to tell the hosted service that it does not wish to receive events. The device host passes in the same object pointer that it did for the IUPnPEventSource Advise method causing the hosted service to release the reference that it held.

The IUPnPAutomationProxy interface provides a method for executing UPnP control requests by invoking a method on a service object s service specific dispinterface.

The IUPnPServiceDescriptionInfo interface provides methods for obtaining data type information from a Service Description.

This interface will be used by the UPnP Device Host Service Control ISAPI extension and the eventing subsystem.

Universal Plug and Play UPnP is an architecture for pervasive peer to peer network connectivity of intelligent appliances wireless devices and PCs of all form factors. It is designed to bring easy to use flexible standards based connectivity to ad hoc or unmanaged networks whether in the home in a small business public spaces or attached to the Internet. Universal Plug and Play is a distributed open networking architecture that leverages TCP IP and the Web technologies to enable seamless proximity networking in addition to control and data transfer among networked devices in the home office and public spaces.

UPnP is more than just a simple extension of the plug and play peripheral model. It is designed to support zero configuration invisible networking and automatic discovery for a breadth of device categories from a wide range of vendors. This means a device can dynamically join a network obtain an IP address convey its capabilities and learn about the presence and capabilities of other devices. DHCP and DNS servers are optional and are used only if available on the network. Finally a device can leave a network smoothly and automatically without leaving any unwanted state behind.

UPnP leverages Internet components including IP TCP UDP HTTP and XML. Like the Internet contracts are based on wire protocols that are declarative expressed in XML and communicated via HTTP. IP internetworking is a strong choice for UPnP because of its proven ability to span different physical media to enable real world multiple vendor interoperation and to achieve synergy with the Internet and many home and office intranets. UPnP has been explicitly designed to accommodate these environments. Further via bridging UPnP accommodates media running non IP protocols when cost technology or legacy prevents the media or devices attached to it from running IP.

What is universal about UPnP No device drivers common protocols are used instead. UPnP networking is media independent. UPnP devices can be implemented using any programming language and on any operating system. UPnP does not specify or constrain the design of an API for applications running on control points OS vendors may create APIs that suit their customer s needs. UPnP enables vendor control over device UI and interaction using the browser as well as conventional application programmatic control.

The UPnP Forum is an industry initiative designed to enable easy and robust connectivity among stand alone devices and PCs from many different vendors. The UPnP Forum seeks to develop standards for describing device protocols and XML based device schemas for the purpose of enabling device to device interoperability in a scalable networked environment. The UPnP Forum oversees a logo program for compliant devices.

The UPnP Forum has set up working committees in specific areas of domain expertise. These working committees are charged with creating proposed device standards building sample implementations and building appropriate test suites. This document indicates specific technical decisions that are the purview of UPnP Forum working committees.

UPnP vendors can build compliant devices with confidence of interoperability and benefits of shared intellectual property and the logo program. Separate from the logo program vendors may also build devices that adhere to the UPnP Device Architecture defined herein without a formal standards procedure. If vendors build non standard devices they determine technical decisions that would otherwise be determined by a UPnP Forum working committee.

The Universal Plug and Play UPnP Device Architecture described herein defines the protocols for communication between controllers or control points and devices. For discovery description control eventing and presentation UPnP uses the following protocol stack.

At the highest layer messages logically contain only UPnP vendor specific information about their devices. Moving down the stack vendor content is supplemented by information defined by UPnP Forum working committees. Messages from the layers above are hosted in UPnP specific protocols defined in this document. In turn the above messages are formatted using the Simple Service Discovery Protocol SSDP General Event Notification Architecture GENA and Simple Object Access Protocol SOAP . The above messages are delivered via HTTP either a multicast or unicast variety running over UDP or the standard HTTP running over TCP. Ultimately all messages above are delivered over IP. The remaining sections of this document describe the content and format for each of these protocol layers in detail. For reference colors in square brackets above indicate which protocol defines specific message components throughout this document.

The foundation for UPnP networking is IP addressing. Each device has a Dynamic Host Configuration Protocol DHCP client and search for a DHCP server when the device is first connected to the network. If a DHCP server is available i.e. the network is managed the device uses the IP addressed assigned to it. If no DHCP server is available i.e. the network is unmanaged the device uses Auto IP to get an address. In brief Auto IP defines how a device intelligently chooses an IP address from a set of reserved addresses and is able to move easily between managed and unmanaged networks. If during the DHCP transaction the device obtains a domain name e.g. through a DNS server or via DNS forwarding the device uses that name in subsequent network operations otherwise the device uses its IP address.

Given an IP address the first step in UPnP networking is discovery. When a device is added to the network the UPnP discovery protocol allows that device to advertise its services to control points on the network. Similarly when a control point is added to the network the UPnP discovery protocol allows that control point to search for devices of interest on the network. The fundamental exchange in both cases is a discovery message containing a few essential specifics about the device or one of its services e.g. its type identifier and a pointer to more detailed information. The UPnP discovery protocol is based on the Simple Service Discovery Protocol SSDP . The section on Discovery below explains how devices advertise how control points search and details of the format of discovery messages.

The second step in UPnP networking is description. After a control point has discovered a device the control point still knows very little about the device. For the control point to learn more about the device and its capabilities or to interact with the device the control point retrieves the device s description from the URL provided by the device in the discovery message. Devices may contain other logical devices as well as functional units or services. The UPnP description for a device is expressed in XML and includes vendor specific manufacturer information like the model name and number serial number manufacturer name URLs to vendor specific Web sites etc. The description also includes a list of any embedded devices or services as well as URLs for control eventing and presentation. For each service the description includes a list of the commands or actions the service responds to and parameters or arguments for each action the description for a service also includes a list of variables these variables model the state of the service at run time and are described in terms of their data type range and event characteristics. The section on Description below explains how devices are described and how those descriptions are retrieved by control points.

The third step in UPnP networking is control. After a control point has retrieved a description of the device the control point can send actions to a device s service. To do this a control point sends a suitable control message to the URL for control URL for the service provided in the device description . Control messages are also expressed in XML using the Simple Object Access Protocol SOAP . Like function calls in response to the control message the service returns any action specific values. The effects of the action if any are modeled by changes in the variables that describe the run time state of the service. The section on Control below explains the description of actions state variables and the format of control messages.

The fourth step in UPnP networking is eventing. A UPnP description for a service includes a list of actions the service responds to and a list of variables that model the state of the service at run time. The service publishes updates when these variables change and a control point may subscribe to receive this information. The service publishes updates by sending event messages. Event messages contain the names of one of more state variables and the current value of those variables. These messages are also expressed in XML and formatted using the General Event Notification Architecture GENA . A special initial event message is sent when a control point first subscribes this event message contains the names and values for all evented variables and allows the subscriber to initialize its model of the state of the service. To support scenarios with multiple control points eventing is designed to keep all control points equally informed about the effects of any action. Therefore all subscribers are sent all event messages subscribers receive event messages for all evented variables that have changed and event messages are sent no matter why the state variable changed either in response to a requested action or because the state the service is modeling changed . The section on Eventing below explains subscription and the format of event messages.

The fifth step in UPnP networking is presentation. If a device has a URL for presentation then the control point can retrieve a page from this URL load the page into a browser and depending on the capabilities of the page allow a user to control the device and or view device status. The degree to which each of these can be accomplished depends on the specific capabilities of the presentation page and device. The section on Presentation below explains the protocol for retrieving a presentation page.

Addressing is Step 0 of UPnP networking. Through addressing devices get a network address. Addressing enables discovery Step 1 where control points find interesting device s description Step 2 where where control points learn about device capabilities control Step 3 where a control point sends commands to device s eventing Step 4 where control points listen to state changes in device s and presentation Step 5 where control points display a user interface for device s .

The foundation for UPnP networking is IP addressing. Each device has a Dynamic Host Configuration Protocol DHCP client and search for a DHCP server when the device is first connected to the network. If a DHCP server is available i.e. the network is managed the device uses the IP addressed assigned to it. If no DHCP server is available i.e. the network is unmanaged the device uses automatic IP addressing Auto IP to obtain an address.

Auto IP defines how a device a determines if DHCP is unavailable and b intelligently chooses an IP address from a set of link local IP addresses. This method of address assignment enables a device to easily move between managed and unmanaged networks.

The operations described in this section are further clarified in the reference documents listed below. Where conflicts between this document and the reference documents exist the reference document always takes precedence.

A device that supports AUTO IP and is configured for dynamic address assignment begins by requesting an IP address via DHCP by sending out a DHCPDISCOVER message. The amount of time this DHCP Client listens for DHCPOFFERS is implementation dependent. If a DHCPOFFER is received during this time the device continues the process of dynamic address assignment. If no valid DHCPOFFERS are received the device may then auto configure an IP address.

To auto configure an IP address using Auto IP the device uses an implementation dependent algorithm for choosing an address in the 169.254 16 range. The first and last 256 addresses in this range are reserved and is not used.

The selected address then is tested to determine if the address is already in use. If the address is in use by another device another address is chosen and tested up to an implementation dependent number of retries. The address selection is randomized to avoid collision when multiple devices are attempting to allocate addresses.

To test the chosen address the device uses an Address Resolution Protocol ARP probe. An ARP probe is an ARP request with the device hardware address used as the sender s hardware address and the sender s IP address set to 0s. The device will then listen for responses to the ARP probe or other ARP probes for the same IP address. If either of these ARP packets is seen the device considers the address in use and try a new address.

A device that has auto configured an IP address periodically checks for the existence of a DHCP server. This is accomplished by sending DHCPDISCOVER messages. How often this check is made is implementation dependent but checking every 5 minutes would maintain a balance between network bandwidth required and connectivity maintenance. If a DHCP offer is received the device proceeds with dynamic address allocation. Once a DHCP assigned address is in place the device may release the auto configured address but may also choose to maintain this address for a period of time to maintain connectivity.

To switch over from one IP address to a new one the device cancels any outstanding advertisements and reissue new ones. The section on Discovery explains advertisements and their cancellations.

Once a device has a valid IP address for the network it can be located and referenced on that network through that address. There may be situations where the end user needs to locate and identify a device. In these situations a friendly name for the device is much easier for a human to use than an IP address.

Moreover names are much more static than IP addresses. Clients referring a device by name don t require any modification when IP address of a device changes. Mapping of the device s DNS name to its IP address could be entered into DNS database manually or dynamically according to RFC 2136. While computers and devices supporting dynamic DNS updates can register their DNS records directly in DNS it is also possible to configure a DHCP server to register DNS records on behalf of these DHCP clients.

A computer that needs to contact a device identified by a DNS name needs to discover its IP address. The computer submits a DNS query according to RFC1034 and 1035 to the pre configured DNS server s and receives a response from a DNS server containing the IP address of the target device. A computer can be statically pre configured with the list of DNS servers. Alternatively a computer could be configured with the list of DNS server through DHCP or after the address assignment through a DHCPINFORM message.

Discovery is Step 1 in UPnP networking. Discovery comes after addressing Step 0 where devices get a network address. Through discovery control points find interesting device s . Discovery enables description Step 2 where control points learn about device capabilities control Step 3 where a control point sends commands to device s eventing Step 4 where control points listen to state changes in device s and presentation Step 5 where control points display a user interface for device s .

Discovery is the first step in UPnP networking. When a device is added to the network the UPnP discovery protocol allows that device to advertise its services to control points on the network. Similarly when a control point is added to the network the UPnP discovery protocol allows that control point to search for devices of interest on the network. The fundamental exchange in both cases is a discovery message containing a few essential specifics about the device or one of its services e.g. its type identifier and a pointer to more detailed information.

When a new device is added to the network it multicasts a number of discovery messages advertising its embedded devices and services. Any interested control point can listen to the standard multicast address for notifications that new capabilities are available.

Similarly when a new control point is added to the network it multicasts a discovery message searching for interesting devices services or both. All devices listen to the standard multicast address for these messages and responds if any of their embedded devices or services match the search criteria in the discovery message.

To reiterate a control point may learn of a device of interest because that device sent discovery messages advertising itself or because the device responded to a discovery message searching for devices. In either case if a control point is interested in a device and wants to learn more about it the control point uses the information in the discovery message to send a description query message. The section on Description explains description messages in detail.

When a device is removed from the network it multicasts a number of discovery messages revoking it s earlier announcements effectively declaring that it s embedded devices and services will not be available.

To limit network congestion the time to live TTL of each IP packet for each multicast message defaults to 4 and is configurable.

Discovery plays an important role in the interoperability of devices and control points using different versions of UPnP networking. The UPnP Device Architecture defined herein is versioned with both a major and a minor version usually written as major.minor where both major and minor are integers. Advances in minor versions is a compatible superset of earlier minor versions of the same major version. Advances in major version are not required to be supersets of earlier versions and are not guaranteed to be backward compatible. Version information is communicated in discovery and description messages. In the former each discovery message includes the version of UPnP networking that the device supports. As a backup the latter also includes the same information. This section explains the format of version information in discovery messages and specific requirements on discovery messages to maintain compatibility with advances in minor versions.

The standard multicast address as well as the mechanisms for advertising searching and revoking are defined by the Simple Service Discovery Protocol SSDP . The remainder of this section explains SSDP in detail enumerating how devices advertise and revoke their advertisements as well as how control points search and devices respond.

When a device is added to the network the UPnP discovery protocol allows that device to advertise its services to control points. It does this by multicasting discovery messages to a standard address and port. Control points listen to this port to detect when new capabilities are available on the network. To advertise the full extent of its capabilities a device multicasts a number of discovery messages corresponding to each of its embedded devices and services. Each message contains information specific to the embedded device or service as well as information about its enclosing device. Messages include duration until the advertisements expire if the device remains available the advertisements are re sent with with new duration . If the device becomes unavailable the device explicitly cancels its advertisements but if the device is unable to do this the advertisements will expire on their own.

To send and receive advertisements devices and control points use the following subset of the overall UPnP protocol stack. The overall UPnP protocol stack is listed at the beginning of this document. 

At the highest layer discovery messages contain vendor specific information e.g. URL for the device description and device identifier. Moving down the stack vendor content is supplemented by information from a UPnP Forum working committee e.g. device type. Messages from the layers above are hosted in UPnP specific protocols defined in this document. In turn the above messages are delivered via a multicast variant of HTTP that has been extended using General Event Notification Architecture GENA methods and headers and Simple Service Discovery Protocol SSDP headers. The HTTP messages are delivered via UDP over IP. For reference colors in square brackets above indicate which protocol defines specific headers and values in discovery messages listed below.

When a device is added to the network it multicasts discovery messages to advertise its root device to advertise any embedded devices and to advertise its services. Each discovery message contains four major components 

To advertise its capabilities a device multicasts a number of discovery messages. Specifically a root device multicasts 

If a root device has d embedded devices and s embedded services but only k distinct service types this works out to 3 2d k requests. This advertises the full extend of the device s capabilities to interested control points. These messages are sent out as a series with roughly comparable expiration times order is unimportant but refreshing or canceling individual messages is prohibited.

Choosing an appropriate duration for advertisements is a balance between minimizing network traffic and maximizing freshness of device status. Relatively short durations close to the minimum of 1800 seconds will ensure that control points have current device status at the expense of additional network traffic longer durations say on the order of a day compromise freshness of device status but can significantly reduce network traffic. Generally device vendors choose a value that corresponds to expected device usage short durations for devices that are expected to be part of the network for short periods of time and significantly longer durations for devices expected to be long term members of the network.

Due to the unreliable nature of UDP devices send each of the above discovery messages more than once. As a fallback to guard against the possibility that a control point might not receive an advertisement for a device or service the device re sends its advertisements periodically cf. CACHE CONTROL below . Note that UDP packets are also bounded in length perhaps as small as 512 Bytes in some implementations and that there is no guarantee that the above 3 2d k messages will arrive in a particular order.

When a device is added to the network it sends a multicast request with method NOTIFY and ssdp alive in the NTS header in the following format. Values in italics are placeholders for actual values.

 No body for request with method NOTIFY but note that the message has a blank line following the last HTTP header. The TTL for the IP packet defaults to 4 and is configurable.

Listed below are details for the request line and headers appearing in the listing above. All header values are case sensitive except where noted.

When a device and its services are going to be removed from the network the device multicasts a ssdp byebye message corresponding to each of the ssdp alive messages it multicasted that have not already expired. If the device is removed abruptly from the network it might not be possible to multicast a message. As a fallback discovery messages include an expiration value in a CACHE CONTROL header as explained above if not re advertised the discovery message eventually expires on its own and is removed from any control point cache.

 Note when a control point is about to be removed from the network no discovery related action is required. 

When a device is about to be removed from the network it explicitly revokes its discovery messages by sending one multicast request for each ssdp alive message it sent. Each multicast request has method NOTIFY and ssdp byebye in the NTS header in the following format. Values in italics are placeholders for actual values.

 No body for request with method NOTIFY but note that the message has a blank line following the last HTTP header. The TTL for the IP packet defaults to 4 and is configurable.

Listed below are details for the request line and headers appearing in the listing above. All header values are case sensitive except where noted.

Due to the unreliable nature of UDP devices send each of the above messages more than once. As a fallback if a control point fails to receive notification that a device or services is unavailable the original discovery message will eventually expire yielding the same effect.

When a control point is added to the network the UPnP discovery protocol allows that control point to search for devices of interest on the network. It does this by multicasting a search message with a pattern or target equal to a type or identifier for a device or service. Responses from devices contain discovery messages essentially identical to those advertised by newly connected devices the former are unicast while the latter are multicast.

To search for devices and be discovered by control points control points and devices use the following subset of the overall UPnP protocol stack. The overall UPnP protocol stack is listed at the beginning of this document. 

At the highest layer search messages contain vendor specific information e.g. the control point device and service identifiers. Moving down the stack vendor content is supplemented by information from a UPnP Forum working committee e.g. device or service types. Messages from the layers above are hosted in UPnP specific protocols defined in this document. In turn search requests are delivered via a multicast variant of HTTP that has been extended using Simple Service Discovery Protocol SSDP methods headers. Search responses are delivered via a unicast variant of HTTP that has also been extended with SSDP. GENA is not involved when control points search for devices. Both kinds of HTTP messages are delivered via UDP over IP. For reference colors in square brackets above indicate which protocol defines specific headers and values in discovery messages listed below.

When a control point is added to the network it sends a multicast request with method M SEARCH in the following format. Values in italics are placeholders for actual values.

Listed below are details for the request line and headers appearing in the listing above. All header values are case sensitive except where noted.

To be found a device sends a response in the following format. Compare to multicast request with method NOTIFY and ssdp alive in the NTS header above. Values in italics are placeholders for actual values.

Listed below are details for the headers appearing in the listing above. All header values are case sensitive except where noted.

 No UPnP specific errors are defined for search messages. Errors may be returned by layers in the protocol stack below UPnP. Consult documentation on those protocols for details.

Description is Step 2 in UPnP networking. Description comes after discovery Step 1 where control points find interesting device s . And description enables control Step 3 where a control points send commands to device s eventing Step 4 where control points listen to state changes in device s and presentation Step 5 where control points display a user interface for device s .

After a control point has discovered a device the control point still knows very little about the device only the information that was in the discovery message i.e. the device s or service s UPnP type the device s universally unique identifier and a URL to the device s UPnP description. For the control point to learn more about the device and its capabilities or to interact with the device the control point retrieves the device s description from the URL provided by the device in the discovery message.

The UPnP description for a device includes vendor specific manufacturer information like the model name and number serial number manufacturer name URLs to vendor specific Web sites etc. details below . The description also includes a list of any embedded devices or services as well as URLs for control eventing and presentation. This section explains embedded devices the section on Control explains how services are described and the sections on Control Eventing and Presentation explain how URLs for control eventing and presentation are used respectively.

Note that a single physical device may include multiple logical devices. Multiple logical devices can be modeled as a single root device with embedded devices and services or as multiple root devices perhaps with no embedded devices . In either case there is one UPnP description for each root device with embedded device descriptions as needed.

The UPnP description for a device is written by a UPnP vendor. The description is in XML syntax and is usually based on a standard UPnP Device Template. A UPnP Device Template is produced by a UPnP Forum working committee they derive the template from the UPnP Template Language which was derived from standard constructions in XML. This section explains the format for a UPnP device description UPnP Device Templates and the part of the UPnP Template Language that covers devices. The section on Control explains the part of the UPnP Template Language that covers services. 

Retrieving the UPnP description for a device is simple the control point issues an HTTP GET request on the URL in the discovery message and the device returns the description document. The protocol stack method headers and body for the response and request are explained in detail below.

UPnP vendors can differentiate their devices by extending services including additional UPnP services or embedding additional UPnP devices. When a control point retrieves a particular device s description these added features are exposed to the control point for control eventing and presentation. Other means for UPnP vendor differentiation are explained in the control section. 

The remainder of this section first explains how devices are described explaining details of vendor specific information embedded devices and URLs for control eventing and presentation. Then it explains UPnP Device Templates and the UPnP Template Language as it pertains to describing devices. Finally it explains in detail how a control point retrieves a description from a device.

The UPnP description for a device contains several pieces of vendor specific information definitions of embedded devices and services and URLs for control eventing and presentation of the device.

To illustrate these below is a listing with placeholders in italics for actual elements and values. Some of these placeholders would be specified by a UPnP Forum working committee colored red or by a UPnP vendor purple . Elements defined by the UPnP Device Architecture are colored green for later reference. Immediately following the listing is a detailed explanation of the elements attributes and values.

Listed below are details for each of the elements attributes and values appearing in the listing above. All elements and attributes are case sensitive HTTP specifies case sensitivity for URLs other values are not case sensitive except where noted. The order of elements is insignificant.

For future extensibility when processing XML like the listing above devices and control points ignore any unknown elements and any sub elements or content as specified by the Flexible XML Processing Profile FXPP .

XML does not support directly embedding binary data e.g. icons in UPnP descriptions. Binary data may be converted into text and thereby embedded into XML using an XML data type of either bin.base64 a MIME style base 64 encoding for binary data or bin.hex hexadecimal digits represent octets . Alternatively the data can be passed indirectly as it were by embedding a URL in the XML and transferring the data in response to a separate HTTP request the icon s in UPnP descriptions are transferred in this latter manner.

The listing above also illustrates the relationship between a UPnP device description and a UPnP Device Template. As explained above the UPnP description for a device is written by a UPnP vendor in XML following a UPnP Device Template. A UPnP Device Template is produced by a UPnP Forum working committee as a means to standardize devices.

By appropriate specification of placeholders the listing above can be either a UPnP Device Template or a UPnP device description. Recall that some placeholders would be defined by a UPnP Forum working committee colored red i.e. the UPnP device type identifier UPnP services and UPnP embedded devices if any . If these were defined the listing would be a UPnP Device Template codifying the standard for this type of device. UPnP Device Templates are one of the key deliverables from UPnP Forum working committees.

Taking this another step further the remaining placeholders in the listing above would be specified by a UPnP vendor colored purple i.e. vendor specific information. If these placeholders were specified as well as the others the listing would be a UPnP device description suitable to be delivered to a control point to enable control eventing and presentation.

Put another way the UPnP Device Template defines the overall type of device and each UPnP device description instantiates that template with vendor specific information. The first is created by a UPnP Forum working committee the latter by a UPnP vendor.

The paragraphs above explain UPnP device descriptions and illustrate how one would be instantiated from a UPnP Device Template. As explained UPnP Device Templates are produced by UPnP Forum working committees and these templates are derived from the UPnP Template Language. This template language defines well formed templates for devices and services. Below is a listing and explanation of this language as it pertains to devices. The section on Control explains the UPnP Template Language as it pertains to services.

The UPnP Template Language is written in XML syntax and is derived from XML Schema Part 1 Structures Part 2 Datatypes . XML Schema provides a set of XML constructions that express language concepts like required vs. optional elements element nesting and data types for values as well as other properties not of interest here . The UPnP Template Language uses these XML Schema constructions to define elements like specVersion URLBase deviceType et al listed in detail above. Because the UPnP Template Language is constructed using another precise language it is unambiguous. And because the UPnP Template Language UPnP Device Templates and UPnP device descriptions are all machine readable automated tools can automatically check to ensure the latter two have all required elements are correctly nested and have values of the correct data types.

Below is the UPnP Template Language for devices as defined by the UPnP Device Architecture herein. The elements it defines are used in UPnP Device Templates they are colored green here and they are colored green in the listing above. Below is where these elements are defined above is where they are used.

Immediately following this is a brief explanation of the XML Schema elements attributes and values used. The reference to XML Schema at the end of the section has further details.

As explained above after a control point has discovered a device it still knows very little about the device. To learn more about the device and its capabilities the control point retrieves the UPnP description for the device using the URL provided by the device in the discovery message. This is a simple HTTP based process and uses the following subset of the overall UPnP protocol stack. The overall UPnP protocol stack is listed at the beginning of this document. 

At the highest layer description messages contain vendor specific information e.g. device type service type and services. Moving down the stack vendor content is supplemented by information from a UPnP Forum working committee e.g. model name model number and specific URLs. Messages from the layers above are hosted in UPnP specific protocols defined in this document. In turn the above messages are delivered via HTTP over TCP over IP. For reference colors in square brackets above indicate which protocol defines specific header and body elements in the description messages listed below.

Using this protocol stack retrieving the UPnP description for a device is simple the control point issues an HTTP GET request to the URL in the discovery message and the device returns its description in the body of an HTTP response. The headers and body for the response and request are explained in detail below.

First a control point sends a request with method GET in the following format. Values in italics are placeholders for actual values.

Listed below are details for the request line and headers appearing in the listing above. All header values are case sensitive except where noted.

After a control point sends a request the device takes the second step a device sends a response in the following format. Values in italics are placeholders for actual values.

Listed below are details for the headers appearing in the listing above. All header values are case sensitive except where noted.

Control is Step 3 in UPnP networking. Control comes after discovery Step 1 where control points find interesting device s and after description Step 2 where control points learn about device capabilities. Control is intimately linked with eventing Step 4 where control points listen to state changes in device s . Through control control points send actions to devices and poll for values. Control and eventing are complementary to presentation Step 5 where control points display a user interface provided by device s .

After a control point has 1 discovered a device and 2 retrieved a description of the device the control point has the bare essentials for device control. To learn more about the service a control point retrieves a detailed UPnP description for each service.

A UPnP description for a service includes a list of the commands or actions the service responds to and parameters or arguments for each action. A service description also includes a list of variables. These variables model the state of the service at run time and are described in terms of their data type range and event characteristics. This section explains the description of actions arguments state variables and properties of those variables. The section on Eventing explains event characteristics.

Like the UPnP description for a device the UPnP description for a service is written by a UPnP vendor. The description is in XML syntax and is based on a standard UPnP Service Template. A UPnP Service Template is produced by a UPnP Forum working committee they derive the template from the UPnP Template Language augmenting it with human language where necessary. As explained above the UPnP Template Language is derived from standard constructions in XML. This section explains the format for a UPnP service description UPnP Service Templates typical augmentations in human language and the part of the UPnP Template Language that covers services. The section on Description explains the part of the UPnP Template Language that covers devices. 

To control a device a control point requests a device s service to perform an action. To do this a control point sends a suitable control message to the control URL for the service provided in the device description . In response the service provides a simple acknowledgement unlike function calls no service specific value is returned. The effects of the action if any are modeled by changes in the variables that describe the run time state of the service. When these state variables change events are published to all interested control points. This section explains the protocol stack for and format of control messages. The section on Eventing explains event publication.

To prevent a race condition between events headed for control points and requested actions headed for a service control messages may include a key. With each new event message a service generates the service increments the key and includes that key in the event message. When a control point sends a control message it may choose to include a key. If a control message includes a key the service checks to see if the key is current i.e. if no events have been sent since this key was issued. If the key is current or if there was no key in the control message then the service acknowledges the action request. If the key is not current the service fails the action request. This section briefly explains the event key. The section on Eventing explains in detail event messages and event publication.

To determine the current value of a state variable a control point may poll the service. Similar to requesting an action a control point sends a suitable query message to the control URL for the service. In response the service provides the value of the variable. This section also explains the format of these query messages. The section on eventing explains automatic notification of variable values.

The remainder of this section first explains how services are described explaining details of actions arguments state variables and properties of those variables. Second it explains UPnP Service Templates typical ways to augment service descriptions with human language and the UPnP Template Language as it pertains to services. Third it explains how a control point retrieves a service description. Finally this section explains in detail how control and query messages are formatted and sent to devices.

The UPnP description for a service defines actions and their arguments and state variables and their data type range and event characteristics.

Each action may have zero or more arguments. Each argument corresponds to a state variable. This direct manipulation programming model reinforces simplicity.

To illustrate these points below is a listing with placeholders in italics for actual elements and values. For a standard UPnP service some of these placeholders would be defined by a UPnP Forum working committee colored red or specified by a UPnP vendor purple . For a vendor unique service all of these placeholders would be specified by a UPnP vendor. Elements defined by the UPnP Device Architecture are colored green for later reference. Immediately following the listing is a detailed explanation of the elements attributes and values.

Listed below are details for each of the elements attributes and values appearing in the listing above. All elements and attributes are case sensitive values are not case sensitive except where noted. Except where noted the order of elements is insignificant.

For future extensibility when processing XML like the listing above devices and control points ignores any unknown elements and any sub elements or content as specified by the Flexible XML Processing Profile FXPP .

Note that it is logically possible for a service to have no actions but have state variables and eventing such a service would be an autonomous information source. Conversely it is also logically possible for a service to have no state variables and no eventing but have actions such a service might be stateless and cause short term environmental effects.

Services standardized by UPnP Forum working committees are versioned. Every later version of a service is a superset of the previous version i.e. it includes all actions and state variables exactly as they are defined by earlier versions of the service. The UPnP service type remains the same across all versions of a service whereas the service version is larger for later versions.

The listing above also illustrates the relationship between a UPnP service description and a UPnP Service Template. As explained above the UPnP description for a service is written by a UPnP vendor in XML following a UPnP Service Template. A UPnP Service Template is produced by a UPnP Forum working committee as a means to standardize devices.

By appropriate specification of placeholders the listing above can be either a UPnP Service Template or a UPnP service description. Recall that some placeholders would be defined by a UPnP Forum working committee colored red i.e. actions and their parameters and states and their data type range and event characteristics. If these were specified the listing above would be a UPnP Service Template codifying the standard for this type of service. Along with UPnP Device Templates cf. section on Description UPnP Service Templates are one of the key deliverables from UPnP Forum working committees.

Taking this another step further the remaining placeholders in the listing above would be specified by a UPnP vendor colored purple i.e. additional vendor specified actions and state variables. If these placeholders were specified as well as the others the listing would be a UPnP service description suitable for effective control of the service within a device.

Put another way the UPnP Service Template defines the overall type of service and each UPnP service description instantiates that template with vendor specific additions. The first is created by a UPnP Forum working committee the latter by a UPnP vendor.

The paragraphs above explain UPnP service descriptions and illustrate how one would be instantiated from a UPnP Service Template. Like UPnP Device Templates UPnP Service Templates are produced by UPnP Forum working committees and these templates are derived from the UPnP Template Language. This template language defines well formed templates for devices and services. The section on Description explains the UPnP Template Language as it pertains to devices. As explained in the section on Description the UPnP Template Language is written in XML syntax and is derived from XML Schema Part 1 Structures Part 2 Datatypes . Below is a listing of this language as it pertains to services. The elements it defines are used in UPnP Service Templates they are colored green here and they are colored green in the listing above. Below is where these elements are defined above is where they are used.

Immediately following this is a brief explanation of the XML Schema elements attributes and values used. The reference to XML Schema at the end of the section has further details.

As is the case with describing devices some properties of services are difficult to capture in the XML Schema formalism. For services in particular it is useful to describe the effect actions have on state variables. This procedural information is awkward to describe in a declarative language like XML so below is a recommended vocabulary for UPnP Forum working committees to use when defining service actions or for UPnP vendors to use when they wish to document the effects of extra actions.

As explained above after a control point has discovered a device and has retrieved a device description it may need to learn more about the services provided by the device. Nearly identical to the process for retrieving a device description a control point may retrieve a service description using a description URL in the description vs. discovery message. For details on retrieving a service description please consult the corresponding discussion on retrieving a device description in the section on Description. 

To send actions and receive confirmation control points and devices use the following subset of the overall UPnP protocol stack. The overall UPnP protocol stack is listed at the beginning of this document. 

At the highest layer control and query messages contain vendor specific information e.g. URL for control and argument values. Moving down the stack vendor content is supplemented by information from a UPnP Forum working committee e.g. service types action names argument names. Messages from the layers above are hosted in UPnP specific protocols defined in this document. In turn the above messages are formatted using a Simple Object Access Protocol SOAP header and body elements and the messages are delivered via HTTP over TCP over IP. For reference colors in square brackets above indicate which protocol defines specific header elements in the subscription messages listed below.

The Simple Object Access Protocol SOAP defines the use of XML and HTTP for remote procedure calls. UPnP uses SOAP to deliver control messages to devices and return acknowledgement or failure codes back to control points.

SOAP defines additional HTTP headers and to ensure that these are not confused with other HTTP extensions SOAP follows the HTTP Extension Framework and specifies a SOAP unique URI in the MAN header and prefixes the HTTP method with M . In this case the method is M POST. Using M POST requires the HTTP server to find and understand the SOAP unique URI and SOAP specific headers.

To provide firewalls and proxies greater administrative flexibility SOAP specifies that requests first be attempted without the MAN header or M prefix. If the request is rejected with a response of 405 Method Not Allowed then a second request is sent using the MAN header and M prefix. If that request is rejected with a response of 501 Not Implemented or 510 Not Extended the request fails. Other HTTP responses is processed according to the HTTP specification. 

Below is a listing of a control message sent using the POST method without the MAN header followed by an explanation of the headers and body. This is immediately followed by a listing of a control message sent using the M POST method and MAN header.

As explained above a control message may include an key to indicate whether the control point has received the most recent message. To include a key the body of a control message includes two SOAP headers one for the event subscription UUID and one for the key itself. Both are illustrated in the listings below. The section on Eventing explains the contents of the two headers in detail.

To send a requested action to a device a control point sends a request with method POST in the following format. Values in italics are placeholders for actual values.

Listed below are details for the request line headers and body elements appearing in the listing above. All header values and element names are case sensitive values are not case sensitive except where noted. Except where noted the order of elements is insignificant.

If a request with POST is rejected with a response of 405 Method Not Allowed then a control point sends a second request with method M POST and MAN in the following format. Values in italics are placeholders for actual values.

 Message body for request with method M POST is the same as body for request with method POST. See above. 

If a service accepts an action request from a control point the service sends a response in the following format. Values in italics are placeholders for actual values.

Listed below are details for each of the headers and body elements appearing in the listing above. All header values and element names are case sensitive values are not case sensitive except where noted. Except where noted the order of elements is insignificant.

If the service does not accept an action request from a control point the service sends a response in the following format. Values in italics are placeholders for actual values.

 Headers for a response when a service does not accept an action request are the same as headers for a response when a service does. See above. 

In addition to sending requested actions to a service control points may also poll the service for the value of a state variable by sending a query message. A query message may query only one state variable multiple query messages is sent to query multiple state variables.

To query for the value of a state variable a control point sends a request in the following format. Values in italics are placeholders for actual values.

Listed below are details for the request line headers and body elements appearing in the listing above. All header values and element names are case sensitive values are not case sensitive except where noted. Except where noted the order of elements is insignificant.

If a request with POST is rejected with a response of 405 Method Not Allowed then a control point sends a second request with method M POST and MAN as explained above.

To answer a query for the value of a state variable the service sends a response in the following format. Values in italics are placeholders for actual vaules.

Listed below are details for each of the headers and body elements appearing in the listing above. All header values and element names are case sensitive values are not case sensitive except where noted. Except where noted the order of elements is insignificant.

If the service cannot provide a value for the request then the service sends a response in the following format. Values in italics are placeholders for actual values.

Eventing is Step 4 in UPnP networking. Eventing comes after discovery Step 1 where control points find interesting device s and after description Step 2 where control points learn about device capabilities. Eventing is intimately linked with control Step 3 where control points send actions to devices. Through eventing control points listen to state changes in device s . Control and eventing are complementary to presentation Step 5 where control points display a user interface provided by device s .

After a control point has 1 discovered a device and 2 retrieved a description of the device the control point has the bare essentials for eventing. As is the case with control to learn more about the device s services the control point retrieves a detailed UPnP description for each service of interest.

As the section on Control explains a UPnP description for a service includes a list of actions the service responds to and a list of variables that model the state of the service at run time. If one or more of these state variables are evented then the service publishes updates when these variables change and a control point may subscribe to receive this information.

To subscribe to eventing a control point sends a subscription message. If the subscription is accepted the service responds with a duration for the subscription. To keep the subscription active a control point renews its subscription before the subscription expires. When a control point no longer needs eventing from a particular service the control point cancels its subscription. This section explains subscription renewal and cancellation messages in detail below.

The service publishes changes to state variables by sending event messages. Event messages contain the names of one of more state variables and the current value of those variables expressed in XML. A special initial event message is sent when a control point first subscribes this event message contains the names and values for all evented variables and allows the subscriber to initialize its model of the state of the service. To support scenarios with multiple control points eventing is designed to keep all control points equally informed about the effects of any action. Therefore all subscribers are sent all event messages subscribers receive event messages for all evented variables not just some and event messages are sent no matter why the state variable changed either in response to a requested action or because the state the service is modeling changed . This section explains the format of event messages in detail below.

Some state variables may change value too rapidly for eventing to be useful. One alternative is to filter or moderate the number of event messages sent due to changes in a variable s value. Some state variables may contain values too large for eventing to be useful for this or other reasons a service may designate one or more state variables as non evented and never send event messages to a subscriber. To determine the current value for such non evented variables control points poll the service explicitly. This section explains how variable eventing is described within a service description. The section on Control explains how to poll a service for a variable value.

To prevent a race condition between events headed for control points and requested actions headed for a service control messages may include a key. With each new event message a service generates the service increments the key and includes that key in the event message. When a control point sends a control message it may choose to include a key. If a control message includes a key the service checks to see if the key is current i.e. if no events have been sent since this key was issued. If the key is current or if there was no key in the control message then the service acknowledges the action request. If the key is not current the service fails the action request. This section explains details of event keys and the synchronization between control and event messages.

To send and receive subscription and event messages control points and services use the following subset of the overall UPnP protocol stack. The overall UPnP protocol stack is listed at the beginning of this document. 

At the highest layer subscription and event messages contain vendor specific information like URLs for subscription and duration of subscriptions or specific variable values. Moving down the stack vendor content is supplemented by information from a UPnP Forum working committee like service identifiers or variable names. Messages from the layers above are hosted in UPnP specific protocols defined in this document. In turn the above messages are formatted using General Event Notification Architecture GENA headers and the messages are delivered via HTTP over TCP over IP. For reference colors in square brackets above indicate which protocol defines specific header elements in the subscription messages listed below. The remainder of this section first explains subscription including details of subscription messages renewal messages and cancellation messages. Second it explains in detail how event messages are formatted and sent to control points the initial event message and how event keys synchronize control and eventing. Finally it explains the UPNP Template Language as it pertains to eventing. 4.1 Eventing Subscription

The service may wish to persist subscriptions across power failures. While control points can recover from complete network failure if the problem is brief and localized to the device reusing stored subscriptions may speed recovery.

The list of subscribers is updated via subscription renewal and cancellation messages explained below and event messages explained later in this section.

To subscribe to eventing for a service a control point sends a subscription message containing a URL for the publisher a service identifier for the publisher and a delivery URL for event messages. The subscription message may also include a requested duration for the subscription. The URL and service identifier for the publisher come from a description message. As the section on Description explains a description message contains a device description. A device description contains among other things for each service an eventing URL in the eventSubURL element and a service identifier in the serviceId element these correspond to the URL and service identifier for the publisher respectively.

The subscription message is a request to receive all event messages. No mechanism is provided to subscribe to event messages on a variable by variable basis. A subscriber is sent all event messages from the service. This is one factor to be considered when designing a service.

If the subscription is accepted the service responds with unique identifier for this subscription and a duration for this subscription. A duration is chosen that matches assumptions about how frequently devices are removed from the network if devices are removed every few minutes then the duration is similarly short allowing a service to rapidly deprecate any expired subscribers if devices are semi permanent then the duration is very long minimizing the processing and traffic associated with renewing subscriptions.

As soon as possible after the subscription is accepted the service also sends the first or initial event message to the subscriber. This message includes the names and current values for all evented variables. The data type and range for each variable is described in a service description. The section on Control explains this in more detail. 

To keep the subscription active a control point renews its subscription before the subscription expires by sending a renewal message. The renewal message is send to the same URL as the subscription message but the renewal message does not include a delivery URL for event messages instead the renewal message includes the subscription identifier. The response for a renewal message is the same as one for a subscription message.

If a subscription expires the subscription identifier becomes invalid and the service stops sending event messages to the control point and can clean up its list of subscribers. If the control point tries to send any message other than a subscription message the service will reject the message because the subscription identifier is invalid. To send control messages to the service the control point sends a subscription message and get a new subscription identifier.

When a control point no longer needs eventing from a particular service the control point cancels its subscription. Canceling a subscription generally reduces service control point and network load. If a control point is removed abruptly from the network it might be impossible to send a cancellation message. As a fallback the subscription will eventually expire on its own unless renewed.

Below is an explanation of the specific format of requests responses and errors for subscription renewal and cancellation messages.

For each service in a device a description message contains an eventing URL eventSubURL sub element of service element in the device description and the UPnP service identifier serviceId sub element in service element in device description . To subscribe to eventing for a particular service a subscription message is sent to that service s eventing URL. The message contains that service s identifier as well as a delivery URL for event messages. A subscription message may also include a requested subscription duration.

To subscribe to eventing for a service a control point sends a request with method SUBSCRIBE and NT and CALLBACK headers in the following format. Values in italics are placeholders for actual values.

Listed below are details for the request line and headers appearing in the listing above. All header values are case sensitive except where noted.

To accept the subscription the service assigns a unique identifier for the subscription assigns a duration for the subscription and sends an initial event message explained in detail later in this section . To accept a subscription request a service sends a response in the following format. Values in italics are placeholders for actual values.

Listed below are details for headers appearing in the listing above. All header values are case sensitive except where noted.

If a service cannot accept another event subscriber or if there is an error with the subscription request the service sends a response with one of the following errors.

Other errors may be returned by layers in the protocol stack below UPnP. Consult documentation on those protocols for details.

To renew a subscription to eventing for a particular service a renewal messages is sent to that service s eventing URL. However unlike an initial subscription message a renewal message does not contain either the service s identifier nor a delivery URL for event messages. Instead the message contains the subscription identifier assigned by the service providing an unambiguous reference to the subscription to be renewed. Like a subscription message a renewal message may also include a requested subscription duration.

The renewal message uses the same method as the subscription message but the two messages use a disjoint set of headers renewal uses SID and subscription uses NT and CALLBACK. A message that includes SID and either of NT or CALLBACK headers is an error.

To renew a subscription to eventing for a service a control point sends a request with method SUBSCRIBE and SID header in the following format. Values in italics are placeholders for actual values.

Listed below are details for the request line and headers appearing in the listing above. All header values are case sensitive except where noted.

To accept a renewal the service reassigns a duration for the subscription. No initial event message. See below. To accept a renewal a service sends a response in the same format as a response to a request for a new subscription.

If a service cannot accept the renewal or if there is an error with the renewal request the service sends a response with one of the following errors.

Other errors may be returned by layers in the protocol stack below UPnP. Consult documentation on those protocols for details.

When eventing is no longer needed from a particular service a cancellation message is sent to that service s eventing URL. The message contains the subscription identifier. Canceling a subscription generally reduces service control point and network load. If a control point is removed abruptly from the network it might be impossible to send a cancellation message. As a fallback the subscription will eventually expire on its own unless renewed.

To cancel a subscription to eventing for a service a control point sends a request with method UNSUBSCRIBE in the following format. Values in italics are placeholders for actual values.

Listed below are details for the request line and headers appearing in the listing above. All header values are case sensitive except where noted.

To cancel a subscription a service sends a response in the following format. Values in italics are placeholders for actual values.

If there is an error with the cancellation request the service sends a response with one of the following errors.

Other errors may be returned by layers in the protocol stack below UPnP. Consult documentation on those protocols for details.

A service publishes changes to its state variables by sending event messages. These messages contain the names of one or more state variables and the current value of those variables. Event messages is sent as soon as possible to get accurate information about the service to control points and allow control points to display a responsive user interface. If the value of more than one variable is changing at the same time the service bundles these changes into a single event message to reduce processing and network traffic.

As explained above an initial event message is sent when a control point first subscribes this event message contains the names and values for all evented variables and allows the subscriber to initialize its model of the state of the service. This message is sent as soon as possible after the service accepts a subscription.

Event messages are tagged with an event key to detect a race condition between event messages headed for control points and control messages headed for a device. A separate event key is maintained by the service for each subscription to facilitate error detection as explained below . The event key for a subscription is initialized to 0 when the service sends the initial event message. For each subsequent event message the service increments the event key for a subscription and includes that updated key in the event message. Any implementation of event keys handles overflow and wrap the event key back to 1 not 0 . Control point also handles this special case when the next event key is not an increment of the previous key.

If there is no response from a control point to the event message the service continues to send event messages to the control point until the subscription expires.

To repair an event subscription e.g. if a control point has missed one or more event messages a control point unsubscribes and re subscribes. By doing so the control point will get a new subscription identifier a new initial event message and a new event key. With these the control point can resume sending successful control messages to the service.

To send an event message a service sends a request with method NOTIFY in the following format. Values in italics below are placeholders for actual values.

Listed below are details for the request line headers and body elements appearing in the listing above. All header values are case sensitive except where noted. All body elements and attributes are case sensitive body values are not case sensitive except where noted. Except where noted the order of elements is insignificant.

For future extensibility when processing XML like the listing above devices and control points ignore any unknown elements and any sub elements or content as specified by the Flexible XML Processing Profile FXPP .

If there is an error with the event message the control point responds with one of the following errors.

Other errors may be returned by layers in the protocol stack below UPNP. Consult documentation on those protocols for details.

The UPnP Template Language defines well formed templates for devices and services. To a lesser extent it also provides a template for the body of event messages. The section on Description explains the UPnP Template Language as it pertains to devices and the section on Control explains the UPnP Template Language as it pertains to services. As explained in those sections the UPnP Template Language is written in XML syntax and is derived from XML Schema Part 1 Structures Part 2 Datatypes . Below is a listing of this language as it pertains to eventing. The elements it defines are used in event messages they are colored green here and they are colored green in the listing above. Below is where these elements are defined though it is a minimal definition above is where they are used.

Immediately following this is a brief explanation of the XML Schema elements attributes and values used. The reference to XML Schema at the end of this section has further details.

As explained in the section on Control the UPnP Template Language for services also specifies a sendEvents attribute for a state variable. The default value for this attribute is yes. To denote that a state variable is evented the value of this attribute is yes or the attribute is omitted in a service description to denote that a state variable is non evented the value is no. Note that if all of a service s state variables are non evented the service has nothing to publish and control points cannot subscribe and will not receive event messages from the service.

It is useful to augment the description of devices and services with annotations that are not captured in the UPnP Template Language. To a lesser extent there is value in these annotations to capture event filtering or moderation.

As explained above some state variables may change value too rapidly for eventing to be useful. Below is a recommended vocabulary for UPnP Forum working committees or UPnP vendors to document moderation in the number of event messages sent due to changes in a variables value.

Presentation is Step 5 in UPnP networking. Presentation comes after discovery Step 1 where control points find interesting device s and after description Step 2 where control points learn about device capabilities. Presentation exposes an HTML based user interface for controlling and or viewing device status. Presentation is complementary to control Step 3 where control points send actions to devices and eventing Step 4 where control points listen to state changes in device s .

After a control point has 1 discovered a device and 2 retrieved a description of the device the control point is ready to begin presentation. If a device has a URL for presentation then the control point can retrieve a page from this URL load the page into a browser and depending on the capabilities of the page allow a user to control the device and or view device status. The degree to which each of these can be accomplished depends on the specific capabilities of the presentation page and device.

The URL for presentation is contained within the presentation URL element in the device description. The device description is delivered via a description message. The section on Description explains the device description and description messages in detail.

Retrieving a presentation page is a simple HTTP based process and uses the following subset of the overall UPnP protocol stack. The overall UPnP protocol stack is listed at the beginning of this document. 

At the highest layer the presentation page is specified by a UPnP vendor. Moving down the stack the UPnP Device Architecture specifies that this page be written in HTML. The page is delivered via HTTP over TCP over IP. For reference colors in square brackets are included for consistency with other sections in this document.

To retrieve a presentation page the control point issues an HTTP GET request to the presentation URL and the device returns a presentation page.

Unlike the UPnP Device and Service Templates and standard device and service types the capabilities of the presentation page are completely specified by the UPnP vendor. The presentation page is not under the auspices of a UPnP Forum working committee. The page is an HTML page it is version HTML 3.0 or later. However other design aspects are left to the vendor to specify. This includes but is not limited to all capabilities of the control point s browser scripting language or browser plug ins used and means of interacting with the device. To implement a presentation page a UPnP vendor may wish to use UPnP mechanisms for control and or eventing leveraging the device s existing capabilities but is not constrained to do so.

Having described and illustrated the principles of our invention with reference to an illustrated embodiment it will be recognized that the illustrated embodiment can be modified in arrangement and detail without departing from such principles. It should be understood that the programs processes or methods described herein are not related or limited to any particular type of computer apparatus unless indicated otherwise. Various types of general purpose or specialized computer apparatus may be used with or perform operations in accordance with the teachings described herein. Elements of the illustrated embodiment shown in software may be implemented in hardware and vice versa.

In view of the many possible embodiments to which the principles of our invention may be applied it should be recognized that the detailed embodiments are illustrative only and should not be taken as limiting the scope of our invention. Rather we claim as our invention all such embodiments as may come within the scope and spirit of the following claims and equivalents thereto.

