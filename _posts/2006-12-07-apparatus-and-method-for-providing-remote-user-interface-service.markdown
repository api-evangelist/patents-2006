---

title: Apparatus and method for providing remote user interface service
abstract: An apparatus and method for providing Remote User Interface (RUI) service are provided. The apparatus includes a service browser module and a virtual RUI server module. The service browser module communicates with a service registry, which is located outside a home network, and provides a service search User Interface (UI) to allow an RUI client, which is located inside a home network, to search for services that are present outside the home network. The virtual RUI server module is responsible for intermediation so that the services present outside the home network can be used through a service UI.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07743042&OS=07743042&RS=07743042
owner: Samsung Electronics Co., Ltd.
number: 07743042
owner_city: Suwon-si
owner_country: KR
publication_date: 20061207
---
This application claims priority from Korean Patent Application No. 10 2006 0005510 filed on Jan. 18 2006 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference in its entirety.

Apparatuses and methods consistent with the present invention relate to providing remote user interface service and more particularly to providing a Remote User Interface RUI service which can extend Universal Plug and Play UPnP service outside a home network using Open Service Gateway Initiative OSGi technology.

UPnP RUI is a UPnP standard technology for providing user interfaces UIs between UPnP devices connected to a home network. For example UPnP RUI technology allows application UIs which reside in a Personal Computer PC located in a study room to be accessed and manipulated through a digital television DTV located in a living room.

The RUI server provides a service UI for providing applications or services to a remote RUI client through a UPnP network.

The RUI client is a device for remotely executing or manipulating the applications of the RUI server through the service UI provided by the RUI server . Accordingly the RUI client has a function of outputting the service UI which is provided by the RUI server onto a screen to allow a user to access or manipulate the service UI.

Each of the UPnP device RUI server and the RUI client provides a UPnP action to the RUI control point and the RUI control point is responsible for controlling the RUI server and the RUI client . For example when a specific service UI which can be used by the RUI client is selected from among the service UIs of the RUI server the RUI control point issues a connection command to the RUI client so that the RUI client can receive the selected service UI.

For example when a user selects the RUI client through the RUI control point to display a service UI the RUI control point receives a device profile which is supported by the RUI client selected by the user through a predetermined action for example a getDeviceProfile action . In this case the device profile is a kind of remote UI protocol for example XHT and HTML that enables the rendering of the RUI client .

The RUI control point calls the predetermined action for example getCompatibleUIs action of the RUI server using the device profile as a factor . In this case the RUI control point can receive a list of service UIs that are compatible with the RUI client among the service UIs provided by the RUI server through the call.

At the next operation the RUI control point selects a desired service UI from among the compatible service UIs extracts Uniform Resource Locator URL information corresponding to the selected service UI and calls a Connect action so that the RUI client connects to the RUI server to receive a corresponding service .

The RUI client can remotely use the service of the RUI server using the URL of the service UI through the Connect action . In this case the communication method thereof is implemented using a separate remote protocol method other than UPnP.

However the related art UPnP RUI described above which is located outside the home network does not propose an RUI model that can provide service from outside the home network due to the limited characteristics of UPnP technology therefore such an RUI model is desired.

Exemplary embodiments of the present invention overcome the above disadvantages and other disadvantages not described above. Also the present invention is not required to overcome the disadvantages described above and an exemplary embodiment of the present invention may not overcome any of the problems described above.

The present invention provides an apparatus and method for providing UPnP RUI service outside a home network using OSGi technology.

According to an aspect of the present invention there is provided an apparatus for providing RUI service the apparatus including a service browser module communicating with a service registry which is located outside a home network and providing a service search UI to allow an RUI client which is located inside a home network to search for services that are present outside the home network and a virtual RUI server module being responsible for intermediation so that the services present outside the home network can be used through a service UI.

According to another aspect of the present invention there is provided a method of providing RUI service the method including communicating with a service registry which is located outside a home network and providing a service search UI to allow an RUI client which is located inside a home network to search for services that are present outside the home network downloading and installing a virtual RUI server bundle to and on an OSGi gateway when a desired service is selected through the service search UI and performing intermediation so that the services present outside the home network can be used through a service UI.

The advantages and characteristics of the present invention and the method of achieving them will be apparent with reference to exemplary embodiments described in detail later in conjunction with the accompanying drawings. However the present invention is not limited to the exemplary embodiments disclosed below but may be implemented in various ways. Furthermore the exemplary embodiments are provided to complete the disclosure of the present invention and to fully notify those skilled in the art of the scope of the present invention. Like reference numerals are used throughout the different drawings to designate like components.

Universal Description Discovery and Integration UDDI is an extensible Markup Language XML based registry for businesses in a worldwide business list on the Internet. UDDI enables uninterrupted interactive online transactions and the interactive operation of electronic e commerce on the World Wide Web WWW and prepares a list using business names products or locations or web services and then provides the list to users.

Exemplary embodiments of the present invention are described in detail with reference to the accompanying drawings below.

UPnP RUI server service is basically provided such that services outside a home network can be searched for and used in the home network using the existing UPnP RUI standard technology.

The UPnP RUI service providing apparatus includes a service browser module and a virtual RUI server module .

The service browser module communicates with a service registry which is located outside the home network and provides a service search UI to allow an RUI client which is located inside the home network to search for services which are present outside the home network. In this case a UDDI server may be used as the service registry and Simple Object Access Protocol SOAP may be used as a communication protocol.

The service browser module includes a search proxy module a management module and a service search UI providing module .

The search proxy module functions to search for services which have been registered in the service registry located outside the home network and select a desired service from among found services.

The management module functions to download a virtual RUI server bundle which performs a proxy function of standing proxy for the call of a service to allow the service selected by a user to be used in the home network from a service provider and to install or delete the downloaded virtual RUI server bundle on or from an OSGi gateway. In this case the virtual RUI server bundle may be constructed using set details of user preference information about security and languages and may be used to implement a function as an intermediary service module in the RUI service providing apparatus .

The service search UI providing module which is located in an upper layer communicates with the service registry which is located outside the home network and provides the service search UI to allow the RUI client which is located inside the home network to search for services that are present outside the home network.

The virtual RUI server module is responsible for intermediation so that the services outside the home network can be used through a service UI.

The virtual RUI server module includes an intermediary service module and a user preference processing module .

The intermediary service module functions to mediate the services through the service UI for provision of the services while communicating with the RUI client located inside the home network. Furthermore the intermediary service module functions to receive events from the service provider which is located outside the home network and transmit the received events to the RUI control point which is located inside the home network using the UPnP RUI server service. The RUI server bundle may perform the proxy function through the implementation of the intermediary service module .

The user preference processing module stands proxy for and processes the set details of user preference information about security and languages which will be used at the time of using of the service.

The term module as used herein means a hardware component such as a Field Programmable Gate Array FPGA or an Application Specific Integrated Circuit ASIC which performs certain tasks.

The service browser module communicates with the service registry which is located outside the home network and provides the service search UI to allow the RUI client which is located inside the home network to search for services that are present outside the home network at operation S

Furthermore the virtual RUI server bundle which stands proxy for a corresponding service from the service provider is downloaded and installed to and on the OSGi gate through the management module of the service browser module so that the service selected by the user can be used in the home network at operation S

Thereafter the virtual RUI server module performs intermediation through the virtual RUI server bundle so that the RUI client and RUI control point in the home network can use services that are present outside the home network through the service UI based on the UPnP RUI standard at operation S

The RUI control point in the home network receives a device profile from the RUI client through a predetermined action for example a getDeviceProfile action at operation S.

Furthermore the RUI control point receives a list of service search UIs which are compatible with the RUI client among service search UIs from the search UI providing module through a predetermined action for example a getCompatibleUIs action using the device profile as a factor and then selects a specific UI at operation S.

The RUI control point calls a predetermined action Connect action and issues a command to allow the RUI client to display the selected UI. The RUI client searches for services and selects a desired service for example a music listening service or a weather forecasting service through the service search UI at operation S. In this case the user preference information about security and languages which will be used at the time of using of the service may be set.

Furthermore the RUI client which is located inside the home network communicates with the service registry which is located outside the home network through the service browser module and performs a function of searching for services through the search proxy module and selecting a desired service from among the found services.

At the next operation the service browser module downloads the virtual RUI server bundle which stands proxy for a corresponding service from the service provider to the OSGi gateway via the management module and installs the downloaded virtual RUI server bundle on the OSGi gateway to allow the service which is selected by the user to be used in the home network and then the management module performs advertisement via a UPnP network at operation S. In this case the user preference information set at the time of the user s selection of the service is also transmitted so that the virtual RUI server bundle to which the user preference information is applied can be downloaded through the user preference processing module .

When the RUI control point finds the virtual RUI server bundle the service search process is completed. Furthermore the service browser module can install the downloaded virtual RUI server bundle using the Application Programming Interface API of an OSGi framework. The RUI client and the RUI control point in the home network can use service through the selected service UI using the virtual RUI server bundle installed and found through the service search process.

The RUI control point in the home network first receives a device profile from the RUI client to receive a list of service UIs which can be displayed by and which are compatible with the RUI client in the home network among service UIs at operation S.

The RUI control point makes a request to the virtual RUI server bundle so that the list of service UIs which are compatible with the RUI client among the service UIs that are provided by the service provider located outside the home network can be received through the device profile at operation S. In this case the virtual RUI server bundle accesses the service provider which is located outside the home network through the intermediary service module and requests the list of compatible service UIs therefrom.

The RUI control point selects a service UI for a desired service from the list of service UIs compatible with the RUI client and then transmits the URL of the selected service UI to the RUI client at operation S.

The service browser module communicates with the service registry which is located outside the home network through the interface of the UPnP service provider and provides a service search UI to allow the RUI client which is located inside the home network to search for services that are present outside the home network.

When a user selects a desired service through the service search UI provided by the service browser module the service browser module downloads and installs the virtual RUI server bundle to and on the OSGi gateway so that the desired service can be used in the home network. In this case the service registry is storage in which meta information about services to be provided is registered by various service providers on the Internet.

The virtual RUI server module performs intermediation through the virtual RUI server bundle so that the RUI client and the RUI control point in the home network can use services which are present outside the home network through the service UI based on the UPnP RUI standard.

The RUI control point in the home network can receive the URL of a service UI which will be output through the RUI client using the UPnP RUI server service provided by the virtual RUI server module . The URL is a URL for RUI intermediary service provided by the virtual RUI server module rather than the actual location of the service provider located outside the home network. That is the RUI client in the home network adopts the above described method in order to use services which are present outside the home network via the virtual RUI server module instead of directly connecting the services. The reason for this is to allow the virtual RUI server module to stand proxy for the user preference information such as security at the time of selection of a desired service.

Furthermore when the above described method is used the service provider which is located outside the home network can transmit events to the RUI control point through the virtual RUI server module located on the OSGi gate even though the RUI control point in the home network is not assigned a public Internet Protocol IP . Documents and standards related to the exemplary embodiments of the present invention include UPnP Device Architecture V1.0 UPnP RUI Client Server Device Template V1.1 UPnP RUI Client Server Service Template V1.1 and OSGi revision 3.0.

With reference to an operation of searching for services which are present outside the home network in the home network an operation of actually using a service UI an operation in which the RUI control point in the home network receives events from services that are present outside the home network and an operation of deleting services registered in the home network are described in more detail with respect to the service browser module and the virtual RUI server module below.

The RUI control point and the RUI client in the home network can search for services which are present outside the home network using the service search UI provided by the service browser module and can select a desired service from among the found services.

The RUI control point in the home network receives the device profile of the RUI client through a getDeviceProfile action to receive the service search UI which is used to search for the services that are present outside the home network from the service browser module .

The RUI control point receives a list of service search UIs which is compatible with the RUI client among service search UIs provided by the service provider from the service browser module through a getCompatibleUIs action using the device profile as a factor and selects a specific UI and .

Next the RUI control point calls the Connect action of the RUI client and issues a command so that the RUI client can display the selected UI .

The RUI client searches for services and selects a desired service for example a music listening service or a weather forecasting service through the service search UI. In this case user preference information about security and languages which will be used at the time of using of the service may be set. Thereafter the service browser module which is located inside the home network communicates with the service registry located outside the home network and performs a function of searching for services and selecting a desired service from among the found services .

The service browser module then downloads the virtual RUI server bundle which stands proxy for the service selected by the user from the service provider that provides the corresponding service and . In this case the user preference information set at the time of the user s selection of the service is also transmitted to the service provider so that the virtual RUI server bundle to which the user preference information is applied can be downloaded.

The service browser module installs the downloaded virtual RUI server bundle on the OSGi gateway. After the installation the service browser module performs advertisement via the UPnP network . Thereafter when the RUI control point finds the virtual RUI server bundle the service search process is completed.

The service search is basically performed using the UPnP RUI technology so that the RUI client and the RUI control point which follow the existing UPnP RUI standard can perform a service search function without requiring implementation of a separate service.

The RUI client and the RUI control point in the home network can use services through the selected service UI using the virtual RUI server bundle installed and found through the service search process.

The RUI control point in the home network first receives a device profile from the RUI client through a getDeviceProfile action in order to receive a list of service UIs that can be displayed by that are compatible with the RUI client in the home network among service UIs .

Next the RUI control point makes a request to the virtual RUI server bundle so that the list of service UIs which are compatible with the RUI client among the service UIs provided by the service provider located outside the home network can be received through the device profile .

In this case the virtual RUI server bundle accesses the service provider which is located outside the home network through the intermediary service module and requests the list of compatible service UIs therefrom .

The RUI control point selects a service UI for a desired service from the list of service UIs compatible with the RUI client and then transmits the URL of the selected service UI to the RUI client and .

As described above the RUI client in the home network uses the services via the virtual RUI server bundle without directly connecting to the service provider located outside the home network. The reason for this is to allow the virtual RUI server bundle to internally process the user preference information.

The service search is performed using the UPnP RUI technology so that the RUI client and the RUI control point which follow the existing UPnP RUI standard can perform the operation of using services without requiring implementation of a separate service.

The possibility that the device in a home network is not assigned a public IP according to given conditions is high. When an event for example an update of the list of service UIs occurs from the service provider located outside the home network the OSGi gateway assigned the public IP can transmit the event to the RUI control point in the home network via the virtual RUI server bundle on the OSGi gateway and . In this case the virtual RUI server bundle transmits the event through the intermediary service module .

The method of using services is performed based on the UPnP RUI technology so that the RUI client and the RUI control point which follow the existing UPnP RUI standard can perform the operation of using services without requiring implementation of a separate service.

In the same manner as the service search deletion can be performed using a service management UI provided by the service browser module when a service user in the home network desires to delete the existing service for a reason such as the expiration of a service use period.

The RUI control point in the home network receives the device profile of the RUI client through a getDeviceProfile action to allow the RUI client to connect to the service management search UI .

Next the RUI control point receives a list of service management UIs which are compatible with the RUI client using the device profile and selects a desired service management UI from the corresponding list and .

Furthermore the RUI control point transmits the URL of the selected service management UI to the RUI client and then the RUI client connects to the corresponding service management UI using the URL received from the RUI control point and .

When a user makes a request for the deletion of a specific service through the corresponding service management UI the service browser module internally deletes the virtual RUI server bundle for the corresponding service .

The service deletion is basically performed using the UPnP RUI technology so that the RUI client and the RUI control point which follow the existing UPnP RUI standard can perform the deletion function without requiring implementation of a separate service.

As described above in accordance with the image capturing device and the method of operating the same according to the exemplary embodiments of the present invention one or more of the following effects may be realized 

First UPnP RUI devices which are operated only in the existing home network can receive RUI services from outside the home network.

Second since UPnP RUI which was limited only to the UI in the home network can be received from outside the home network a greater variety of types of content and service can be used.

Third since service can be provided using the existing UPnP RUI method the technological burden of providing service is reduced.

Although the exemplary embodiments of the present invention have been disclosed for illustrative purposes those skilled in the art will appreciate that various modifications additions and substitutions are possible without departing from the scope and spirit of the invention as disclosed in the accompanying claims.

