---

title: Extensible network services system
abstract: Automatically finding and using network services. An extensible framework is defined which allows any network service, new or old, to be defined. A base schema is defined that defines existing network services, and extension schemes may also be defined which are specific to new network services. A vendor can define the schemas in XML, as well as using software plug-ins and configuration data. The information is stored on a network provider's server. Clients can browse the network providers server for available services. Any available services can be accepted. When this happens, a form is provided to the client; the client fills out the form; and returns it. The information on the form is associated with the XML schemas and used to select and automatically configure the network service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07805502&OS=07805502&RS=07805502
owner: Intel Corporation
number: 07805502
owner_city: Santa Clara
owner_country: US
publication_date: 20061027
---
This application is a divisional application of and claims priority to U.S. application Ser. No. 09 772 518 filed Jan. 29 2001 now U.S. Pat. No. 7 136 908.

A network is formed by any two computers or processors which are connected by an information line. A provider of network services is often called a service provider. A specialized kind of service provider is an Internet service provider or ISP. More generally however an xSP may be a provider of an unspecified type of network services to users.

Many service providers provide simple bandwidth. However there has been a demand for these providers to provide more advanced services such as virtual private networking voice over IP Internet Protocol IDS Intrusion Detection Systems and quality of service systems. Many of these services and other similar services which can be provided over a network are generically referred to as network services.

E commerce transactions and sales often define sale items using extensible markup language or XML. XML can provide a way to describe the common characteristics of goods. The goods may be generically described using their common elements such as price product description number of goods in inventory source item numbers and other information.

Certain network services are available for purchase on line. Often the purchase may either include a line of services from a single vendor or a single type of network service such as bandwidth. The single type of network service may be offered from different vendors at common locations using a common description. However new and emerging network services may not be susceptible of description over that common schema.

The present application describes a system for describing configuring and selling advanced network services. These services can be dynamically deployed discovered and used by customers.

The system and method described herein includes defining the service using common elements with other existing services and unique elements which may be for this service only or for multiple services. The defined service is posted on a service directory and found by a searching client.

XML may be used to create a language for describing advanced network services and extensions for services. The present system teaches using dynamically defined documents. The documents can be defined in terms of tags and data associated with the tags. In a specific mode the tags and documents are formed in XML and XML schema is used to dynamically add newly developed services. Any service can be defined using this schema since the newly developed services can be defined as newly defined documents.

A basic block diagram of the system is shown in . A client on a network is connected to a server over a network Channel . The channel can be any existing form of network. A client may make network requests and receive responses from the server and any other services associated with the server or designated by the server.

The server and other information storage elements that are associated with the server stores information about the network services. shows the basic architecture but need not actually be in the server.

A service directory stores service information that is described in a specified form. The service information describes the network services. The information can include base information describing common information to multiple services and extended information which can further describe the specific services.

The information needs to be sufficient to allow the client to identify those services it is interested in and initiate a service request. As described herein the initiation of service request will also include information that allows the service to be automatically configured. The available services are described in the directory formed of service descriptions which are XML documents. The services that are available from a particular server may be registered within the service directly by the vendor or gathered automatically by the service which can search publically available sources. This schema using XML schema notation may be used to create the service description.

A client may identify a desired service within the server. The client indicates the desirability of the service to the server. The client may need an interface routine in order to interact with the framework and provide necessary information. Therefore each XML description may include an applet associated with the description. The applet is downloaded at . The alternative to an applet could include a form that is presented to the client and allows the client to fill out specified required data for the identified service. The applet may also provide an interaction environment with the server that will be used for contract negotiation for the service as well as an authentication of the client for the service. Purchases of services may also be accomplished in an automated way and may not specifically require filling out the form manually on the client.

The form sent at is filled out on the client either automatically or manually and returned at . The returned form is sent to the request server which processes the information in the form and initiates services responsive to the information in the form. Service requests and responses are written using multiple XML schema documents. The information within the documents may include a base schema with a common service vocabulary that represents common elements of the specified services. The specific services are also described within an extension schema that includes additional elements required for that service. In addition an XML stylesheet language transform or XSLT document may be defined to describe the transformation between the service elements and an application programming interface API required by the service developer or vendor. Those results may be sent to a middleware service provider shown as .

Either the middleware service provider or the requests server itself may return status and information about the specified network service to the client at .

The service s middleware components accept the requests from the client and direct them to a service developer or vendor provided service. This may use plug ins for example. The services may have their own defined APIs for the specific services in the middleware based on the target of the XSLT transformation. Moreover the network element may support standard network APIs.

The basic architecture shown in may be used according to the flowcharts of the specific embodiments given herein. shows a flowchart that may be carried out when the vendor wishes to develop a network service of any type. The procedure in is as follows. At the vendor defines one or more service XML extension schemas which define unique information about the service. The service XML schemas include the information that is not covered by the service base XML schemas that define common information about network services. The schemas accommodate all service information and service responses as well as the service requests associated therewith.

At the vendor develops a service software plug in for the middleware layer that forms the processing for the service. The vendor also defines an XSLT document that describes the transform between the service documents and the service middleware plug in API. These components may be used to automatically configure the network service in the middleware.

At the vendor creates a service description document to store at a service directory. The service description document may include an extension schema and may include an XML stylesheet transform document if the vendor will be providing more than just basic information contained in the base schema for the service description. The vendor may also describe a client side applet which may be used to elicit additional specific service data upon service enactment. After the vendor s portion of the framework may be completed.

A network provider such as an xSP may wish to offer the vendor s services. This is carried out as follows. At one or more network elements are selected to provision the service. A service description document and possibly client applets for the service are provided to the service directory . A service request server is selected at to handle the management of the service. This is registered as the handler for the service with the service directory .

At the service extension schema documents from are installed at the service request server . The middleware server is registered with the service request server as the plug in handler for the specified service. Then the plug in from is installed at the middleware server at and network elements are registered for the plug in to utilize the service.

At the client submits the final information. This information is converted into XML documents based on each field in the form being related to an XML tag. The XML documents as created conform to the request schema as defined by the vendor at .

These documents are then processed by the service requester and transformed into requests directed to the middleware plug in . The middleware plug in processes the requests and programs network elements or other resources to set up the service at . This may include use of another supporting service discovered through the service directory which can be utilized in a automated way with XML requests sent by the middleware plug in in which case the middleware plug in becomes the client of another service.

Any responses may be propagated back to the client. The client may make subsequent interactive requests as well. These take the form of service requests and response documents between the client and the framework. This mechanism also allows the framework to be used to get services with arbitrary requirements and attributes.

Any service can be defined in terms of new XML tags. The base XML schemas define common parts of the network elements. The extension XML schemas can be used to define anything including new or old parts of the network elements.

This provides a way for a client to discover available network services on demand using standard web tools such as browsers and XML processors.

The system described herein may be used for different network services including but not limited to bandwidth reservation voice over IP firewalls and other intrusion detection software server load balancing and the like.

Although only a few embodiments have been disclosed in detail above other modifications are possible. All such modifications are intended to be encompassed within the following claims in which 

