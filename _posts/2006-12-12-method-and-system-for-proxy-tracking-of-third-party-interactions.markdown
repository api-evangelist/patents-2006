---

title: Method and system for proxy tracking of third party interactions
abstract: A computer-implemented method and system is operable to: receive a tracking event from a client, recognize tracking specific parameters in the tracking event, generate a tracking entry corresponding to the tracking event, use a tracking service API to send the tracking entry to a second server, and redirect the client to an intended target corresponding to the tracking event.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08612569&OS=08612569&RS=08612569
owner: eBay Inc.
number: 08612569
owner_city: San Jose
owner_country: US
publication_date: 20061212
---
This patent application claims the benefit of the filing date of U.S. Provisional Patent Application Ser. No. 60 749 732 filed Dec. 12 2005 and entitled METHOD AND SYSTEM FOR PROXY TRACKING OF THIRD PARTY INTERACTIONS .

This disclosure relates to methods and systems supporting online consumer interactions by a user in a networked system.

Conventional network based marketplaces e.g. consumer websites provide users with functionality to browse a collection of items e.g. goods or services at a website and to make purchases using a variety of means. In some cases users merely search for items using a natural search entry. In other cases users click on links provided in paid advertising. Usually affiliates and or a publication system provide some added value that enables users to quickly access a merchant site associated with a searched item or an advertisement. In most cases links are provided so users can click through to a merchant site. It is necessary to keep a record of these user clicks so that the affiliates and or advertisers can be properly credited for the user click throughs. However conventional systems for tracking these click events are flawed. The widespread use of anti spyware blocking software can prevent accurate tracking of the use of the site. Natural search tracking issues can cause inaccurate payouts for affiliates. Conventional systems cause numerous connections and redirects to external third party sites from clients. The lengthy redirect chain increases the likelihood of a single outage blocking off a portion of desired traffic. These and other problems have made the conventional tracking systems inefficient.

In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of an embodiment of the present invention. It may be evident however to one skilled in the art that the various embodiments of the present invention may be practiced without these specific details.

An example embodiment describes a tracking method and system to allow affiliates and partners to point their links directly to the publication system e.g. a database marketplace such as www.ebay.com or other publication system such as http base.google.com base default or www.yahoo.com so that the publication system receives the link popularity value of those links.

One affiliate entry path goes through numerous redirects as shown in the conventional affiliate link entry system illustrated in .

An example embodiment described herein moves the calls made to affiliate tracking partners of the publication system e.g. advertising servers such as Mediaplex behind the publication system servers. In this manner the publication system s tracking and ad serving technologies are moved off of the client tier. The publication system s servers proxy any tracking requests to the third party via an asynchronous backchannel. The publication system s server will proxy any ad serving requests to the third party via a synchronous call. To keep the impact of the interface as low as possible the requests may appear to come directly from HTTP clients i.e. browsers as much as possible. This means that enough context from the original requests may be collected so that the HTTP request made to an advertising server e.g. Mediaplex appears to be from the original client.

Example functionality of the features of one embodiment can be broken down into the following areas. Each area is described below in its own section.

In an example embodiment this pool may serve as the focal point for all the publication system to tracking partner communications. The interface for this pool is described below. Clients of this service may be other publication system commands. This pool is in an example embodiment not referenced externally.

The trackImpression operation is used to track impressions or ROI events. It is invoked as part of the natural search and ROI event scenario. It has one input a TrackingRequest which is defined in the Web Service Definition Language WSDL in the following way.

The trackImpression operation in an example embodiment uses the input from the TrackingRequest to send a request to a tracking partner the result of which is used to build the TrackingResponse.

The specific data elements are listed below. However the below descriptions are not intended as limiting definitions of the respective terms and the terms may be construed more broadly than the below provided descriptions.

The trackEntry operation may in one example embodiment be used to track entry to the publication system site. It is invoked as part of the affiliate and paid search scenarios. It has one input an EntryTrackingRequest and one output an EntryTrackingResponse. These two objects extend the corresponding objects from the impression tracking operations. The inputs and outputs are detailed below using WSDL.

The additional fields in the objects defined above have the following meanings in an example embodiment.

The interface between the publication system and a specific tracking partner according to an example embodiment is described below. Whether or not an external call to a specific tracking partner is made may be controlled by a feature contingency as detailed below.

Further a sampling percentage stored in the PUBLICATION SYSTEM SITE PARAMETER table detailed below may also be used to allow us to dial up the traffic.

In an example embodiment the publication system internal Tracking Service provider may serve as the primary interface or proxy between the publication system and it s tracking partners. The internal communication between this service and other the publication system components may be based on the well known XML based communication SOAP protocol. To ensure the high availability of this functionality within the publication system this Tracking Service may be set up as a publication system internal Web Service pool as described above fronted by a load balancer. The web service pool is herein referred to as the Rover Web Service pool. In an alternative embodiment the communication between the publication system and a partner Tracking Service may happen in the form of an HTTP request.

An architectural overview of an example embodiment is shown in . The example embodiment as shown in depicts the Tracking Service architecture according to an example embodiment. At the top of the stack the publication system Tracking Service layer provides an abstraction between the client e.g. Search ViewItem etc. . . . and the Rover Web Service component . Beneath the abstraction the Web Service Client and the Web Service Presentation components provide yet another layer of abstraction for sending and receiving SOAP based requests from the client and the Rover Web Service component respectively. In the example embodiment shown in the Rover Web Service component uses a conventional SOAP interface. In other embodiments a Representational State Transfer REST style interface can be used if the SOAP overhead becomes too expensive.

The tracking service in one example embodiment presents a Java API application programming interface to be used for sending data to the tracking partner. The API is designed to handle requests from any one or more of multiple application servers as well as the Rover Web Service pool based on the deliverable configuration. The API consists of a TrackingServiceManager class which serves as the primary entry point to access the service TrackingServiceConfig class and a series of helper classes. A UML unified modeling language diagram illustrated in presents an overview of the Java API in an example embodiment.

The TrackingServiceManager in one example embodiment serves as the main entry for accessing the publication system Tracking Service. Based on the deliverable configuration and the requested the publication system tracking partner the manager returns the appropriate tracking service instance. If the call is originated from the Rover Web Service pool the manager returns an instance of the requested tracking service e.g. a tracking partnerInvocation which is capable of sending and receiving data to and from the requested partner via HTTP. On the other hand if the call is from one of the application servers an instance of the publication systemTrackingService may be returned instead.

A TrackingServiceManager initialization sequence diagram of an example embodiment is illustrated in .

A Tracking partner connection parameter param detection sequence diagram of an example embodiment is illustrated in .

Each tracking service in an example embodiment can be statically and dynamically configured through a configuration category bean. Beans are well known forms of reusable software components. At server start up time the bean is initialized with properties that are specified in a configuration file TrackingService.xml associated with the deliverable. In this file it is possible to have the configuration of one or more internal and or external tracking services. Rover Web Service deliverable one or more publication system partner configurations can be specified in this deliverable. An example is illustrated below.

Given a TrackingRequest as detailed above a specialized PartnerTrackingUrlBuilder may be made available through the TrackingServiceManager to construct a partner URL. Based on the initial TrackingServiceManager.getService call and the tracking service configuration a publication system partner URL builder is created and made available for the client to construct a partner tracking URL from the given request.

A tracking response helper class TrackingResponseHandler appropriately adds partner cookies into or from the tracking response.

This command is used to track an event. It may send a request to the tracking partner and return a 1 pixel .gif. If it is required to display the containing page referring URL then the tag that invokes this command must be wrapped in JavaScript that passes the referring URL as a parameter. Because the command may need to be placed on https or http pages it is always sent https.

https rover.the publication system.com roverroi tracking provider id tracking data segment tranType transaction type siteId site id parameter1 value1 parameter2 value2 .

Where tracking provider id may be 1 for a specific tracking partner and tracking data segment may be the rotation id for example 711 518 1801 6. The transaction type is the same string passed on existing tags. For example BIN FP for a fixed price BIN. The site id is the numeric site id for the tag for example 0 the publication system US or 100 US Autos .

As an example this tracking command also referred to herein as a rover command is represented as follows.

https rover.the publication system.com roverroi 1 711 518 1801 6 TranType BIN FP BIN FP 11233 1siteId 0 mpuid 2577082 4735966129

This tracking command may cause the following to be sent to a pay tracking partner via the invocation as described above.

http adfarm.a tracking partner.com ad bk 711 518 1801 6 BIN FP 1 BIN FP 11233 1 mpuid 2577082 4735966129

This command in an example embodiment implements the universal tracking URL as described herein. It causes entry to the publication system site after first recording a referral for the affiliate with a trading partner.

http rover.the publication system.com rover tracking provider id tracking data segment channel PID affiliate id . . . loc target location 

Where tracking provider id is 1 for a specific tracking partner and tracking data segment is the rotation id for example 711 1751 2978 71. The channel indicates the IM channel for this link and is defined as follows.

The affiliate id indicates the affiliate or partner responsible for the link. Finally target location is the target location for the link.

http rover.the publication system.com rover 1 711 1751 2978 71 1 PID 123456 loc http 3A 2F 2Fcgi.the publication system.com 2F Sub Zero Stainless All Fridge All Freezer 2 Built In NR W0QQitemZ7541240878

http adfarm.a tracking partner.com ad ck 711 1751 2978 71 mpre PID 123456 loc http 3A 2F 2Fcgi.the publication system.com 2F Sub Zero Stainless All Fridge All Freezer 2 Built In NR W0QQitemZ7541240878

The search front end is updated to recognize the tracking command specific parameters use the Tracking Service API to send the tracking entry and then redirect to the intended entry target. The tracking service APIs provide a way to do this at the callBizTier level as shown in the example below.

In addition to these search pages the Product Detail Pages and the Product Based Search single domain pages may also support the optimized URL.

The view item front end is updated to recognize the tracking command specific parameters use the Tracking Service API to send the tracking entry and then redirect to the intended entry target. The logic is similar to what is described above for Search front end integration.

All the existing external ROI placements for a tracking partner need an additional placement to call the tracking command. This may be accomplished by defining Rover the web service pool as an additional provider and adding additional tracking tags as needed. The list of tracking tags for which this may be performed is shown below.

To facilitate the testing and validation of the links to Rover the web service pool the ROI tag validation process may be enhanced to allow an alternate host name in the tag for staging versus production. This may allow the new tags to be validating using a tracking command running in staging as opposed to the production pool.

The generation of Rover A tracking partner ROI tags may be controlled by a feature contingency. An example is shown below.

Further a sampling percentage stored in the PUBLICATION SYSTEM SITE PARAMETER table is also used to allow us to dial up the traffic.

With the streamlining of the affiliate and paid search entry paths to the site the ability to distinguish natural search entries to the site may be compromised. Checking the referrer against a list of search engines is no longer sufficient. To that end in an example embodiment a new cookielet is being dropped during the paid internet marketing paths affiliates paid search . . . that identifies the request as one that should not be flagged as a result of a natural search result referral regardless of the actual referrer.

JavaScript in the footer for a Natural Search entry is changed to detect the pim cookielet. If the pim cookielet is set then it is cleared. If not set then a call to the natural search entry command is added adding the containing page s referrer URL as a parameter as long as the page is not a homepage. An example of this logic follows.

This command may check the referrer of the containing page against a list of known search engine patterns. If a match is found then the Tracking Service API is invoked to track the natural search entry.

The list of search engine URL patterns is the same list used by search processor traffic source detection. Search processor has implemented a process that allows this list to be updated independently of a train roll.

The command is wrapped in JavaScript to add the referrer as described above and is similar to the Impression tracking command described earlier. In an example embodiment the syntax core is as follows.

https rover.the publication system.com roverns tracking provider id tracking data segment mpvl referrer URL 

Where tracking provider id is 1 for a specific tracking partner and tracking data segment is the rotation id for example 711 13271 9788 0. The referrerURL is the URL of the referrer of the page containing the natural search tracking link.

https rover.the publication system.com roverns 1 711 13271 9788 0 mpvl http 3A www.google.com search . . . .

This natural search entry tracking command may cause the following command to be sent to a specific tracking partner via invocation of the TrackImpression operation described above.

The mpcl parameter is supplied as the referrer of the natural search entry tracking command. The cachebuster mpt parameter is computed by the natural search entry tracking command.

In every command Rover may integrate back end Natural Search entry detection. To accomplish this the WebDispatcher.dispatch method may be enhanced to check for a natural search entry and if detected may invoke the Rover Web Service to track the link. An example embodiment of this is shown in . The logic may parallel what is done in JavaScript for the similar check. An example in one embodiment is provided below.

The Search processor has implemented a process that allows this list to be updated independently of a train roll.

The generation of a call to a tracking partner via the web service is controlled by a feature contingency. An example is provided below.

Further a sampling percentage stored in the PUBLICATION SYSTEM SITE PARAMETER table is also used to allow us to dial up the traffic.

The code called by the JavaScript may generate the Rover format links based on a Feature Contingency and sampling percentage. The feature contingency is defined as in an example provided below.

The sampling is based on a hash of the Search processor GUID. The decision to include a request or not can be computed this way. An example is provided below.

The code called by the JavaScript may generate the Rover format links based on a Feature Contingency and sampling percentage. The feature contingency is defined as in the following example.

The Keyword linking tools returns a list of URLs and may generate Rover style links based on a Feature Contingency and sampling percentage. The feature contingency is defined as in the following example.

 is the sampling rate to apply to requests to determine if a given request should use Rover style links. This is an integer from 0 to 100.

The decision to include a request in the sample or not is computed the same way as for the Product Kit described above.

The reporting and alerting for Rover relies on OLAP in one embodiment. An accumulator i may focus on the inputs and outputs from the web service tier as shown in .

An alert and or email may be sent to an operational or administrative center if any of the following events occur.

The number of Timeouts per call to MPLX exceeds a predetermined percentage. This level may be configurable.

The number of errors returned from MPLX per call to MPLX exceeds a predetermined percentage. The percentage that triggers an alert may be configurable.

An alert and or email may be sent to an operational or administrative center if the number of Errors per Referral exceeds a predetermined percentage.

The inner CAL transaction may be used to track statistics on the calls to the external partner. These may include the following data items.

Below is an example list of tracking partner external ROI tags that may be replicated as roverroi commands.

 1 1 0 1 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 0 Reg 1 mpuid D1 1 0 sysdate sysdate 

 2 1 0 2 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 0 Conf 1 mpuid D1 1 0 sysdate sysdate 

 3 1 0 3 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 0 Bid 1 D3 Bid 3 1 mpuid D1 1 D2 2 sysdate sysdate 

 4 1 0 4 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 0 Sell 1 D3 Sell 3 1 mpuid D1 1 D2 sysdate sysdate 

 5 1 0 5 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 8 BIN ABIN 1 D3 BIN ABIN 3 1 mpuid D1 1 D2 2 sysdate sysdate 

 6 1 0 6 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 6 BIN FP 1 D3 BIN FP 3 1 mpuid D1 1 D2 2 sysdate sysdate 

 7 1 0 7 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 10 BIN Store 1 D3 BIN Store 3 1 mpuid D1 1 D2 2 sysdate sysdate 

 8 1 0 8 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 6 Sell BIN 1 D3 Sell BIN 3 1 mpuid D1 1 D2 2 sysdate sysdate 

 9 1 0 9 https F10 F10 adfarm.mediaplex.com ad bk F8 F8 711 518 1801 4 Store Build Conf 1 mpuid D1 1 0 sysdate sysdate .

In an example embodiment all the calls to an advertising server such as Mediaplex are made from a publication system server. The general configuration is depicted in .

As shown in requests from publication system clients are processed by various publication system commands . To make tracking requests to an advertising server such as Mediaplex these commands invoke an internal Web Service . The internal Web Service takes as input all the necessary information to simulate the invocation as if it came directly from the client . This information includes the following from the original client request.

The publication system s Web Service may make simulate a request from the client browser for the calls to an advertising server such as Mediaplex by using existing HTTP headers and parameters to convey information. The requests may use HTTP 1.0 protocol. Specifically chunked encoded responses are not expected. All parameters values are URL encoded as necessary and standard parameter syntax is used i.e. name value pairs separated by ampersand .

There are two main types of calls supported in an example embodiment entry tracking and ROI tracking each is explained in more detail below.

Each HTTP request to an advertising server such as Mediaplex may include the following headers as appropriate.

This header is added to clearly identify the request as being a publication system Rover request rather than one from an end user s browser. The value may be a version number of the following example form. . . The maintenance level is optional. Initially the value may be 1.0

The Accept Language header passed from the client s browser to the publication system may be propagated to an advertising server such as Mediaplex through the use of the same header.

The host name of the targeted an advertising server such as Mediaplex server may be supplied as a Host header value.

The referrer passed to the publication system if any may be propagated to Mediaplex as the Referrer header. If no referrer is passed to the publication system then none may be passed to Mediaplex.

The user agent string passed to the publication system if any may be propagated to Mediaplex as the User Agent header. If no user agent string is passed to the publication system then none may be passed to Mediaplex.

To conserve the time required to establish TCP IP socket connections to the Mediaplex servers connections may be pooled and the request may employ keep alive to manage their life cycle. By default the Rover Web Server may discard socket connections after 10 seconds or 50 uses whichever comes first. Although these values can be overridden by the server as described below.

Since Rover is essentially proxying the request for Mediaplex the publication system may adopt the convention of sending an X Forwarded For header with the remote IP address of the client. The X Forwarded For header is a non standard widely used header that was introduced by the Squid proxy see 4 . If the incoming request to the publication system already has an X Forwarded For header Rover may add the client remote IP address to the end as part of a comma separated list. If there is no X Forwarded For header on the incoming request then Rover may include one on the request that just has the remote IP address of the incoming request.

Since Rover is essentially proxying the request for Mediaplex the publication system may adopt the convention of sending an X Forwarded Host header with the host name of the server in the original client request. This may come with the Host header passed by the client. If there is no Host header on the incoming request then Rover may use a publication system domain as the value for the X Forwarded Host header.

Mediaplex can implement a redirect in a number of ways. A proxy server like Rover may wish to receive the indication in a specific way to allow further processing. To support flexibility on both sides of the interface Mediaplex may recognize a new request header called X Mediaplex Redirect Type. This header can take three possible values 

The Rover Web Service client may process the Keep Alive response header to adjust the lifespan of connected sockets to Mediaplex. As noted above Rover may attempt to keep the connection on a socket to Mediaplex open for a limited time span and number of requests to amortize the overhead of establishing the connection. By default this may be for 10 seconds or 50 requests whichever comes first. However the Mediaplex server can modify this behavior by sending a Keep Alive header.

As described herein the Keep Alive header can pass back parameters to adjust the lifespan of a connection. The parameters that Rover may honor are shown below in an example embodiment.

Rover may use the more restrictive value for both parameters between its internal default and the values returned in a response.

In the event of status moved temporarily or moved permanently responses from entry tracking requests the Location header may be used to send the redirect back to the original client.

Responses from Mediaplex may send values for the svid and mojo1 cookies. Set Cookie headers for these cookies and only these named cookies may be interpreted to obtain values for these cookies. The values may be stored on behalf of Mediaplex for the external client that initiated the request. If cookies are used to accomplish this they may be in the publication system controlled domains. The value for these cookies may be provided when a subsequent request is made as described above.

In general the other attributes of the Set Cookie header besides name and value are ignored. The exception is that an expires attribute with a date in the past may cause the cookie to be deleted from its publication system managed storage. The values stored for these cookies may have strict length limits

In most cases a call to an affiliate payment server e.g. Commission Junction or CJ is used to properly credit an affiliate for a transaction. This type of call replaces the current affiliate payment server advertising server e.g. CJ Mediaplex redirect chain. That is where the current scheme begins with a call to 

The publication system Rover Web Service may make just one call to http adfarm.mediaplex.com ad ck . . . . with the expectation that the advertising server e.g. Mediaplex may internally make a call to an affiliate payment server e.g. CJ as necessary. That call may have the following form 

Note that the response of this command may be different than the existing ad ck commands because it may not be desirable to redirect to the existing RedirectEnter publication system command.

This type of entry is from clicking on ad placements that lead to the publication system. These types of entries have a form shown in the following example.

Natural search entry can be detected on any page served by the publication system. JavaScript running on the page accomplishes this. For this use case the context diagram looks slightly different as shown in .

In this case the referrer passed may be the URL of the search engine page and not the URL of the page running the detecting JavaScript. This type of entry has the form shown in the following example.

ROI calls to the advertising server e.g. Mediaplex have widely varying parameters for different transaction types. The calls however look like the example shown below.

Unlike Natural Search entries the referring URL from the client is not passed through to the advertising server e.g. Mediaplex for ROI events. Also although the existing ROI events are sent as https requests the ROI tags sent from Rover would be using the HTTP protocol.

In alternative embodiments the machine operates as a standalone device or may be connected e.g. networked to other machines. In a networked deployment the machine may operate in the capacity of a server or a client machine in server client network environment or as a peer machine in a peer to peer or distributed network environment. The machine may be a personal computer PC a tablet PC a set top box STB a Personal Digital Assistant PDA a cellular telephone a web appliance a network router switch or bridge or any machine capable of executing a set of instructions sequential or otherwise that specify actions to be taken by that machine. Further while only a single machine is illustrated the term machine shall also be taken to include any collection of machines that individually or jointly execute a set or multiple sets of instructions to perform any one or more of the methodologies discussed herein.

The example computer system includes a processor e.g. a central processing unit CPU a graphics processing unit GPU or both a main memory and a static memory which communicate with each other via a bus . The computer system may further include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alphanumeric input device e.g. a keyboard a user interface UI navigation device e.g. a mouse a disk drive unit a signal generation device e.g. a speaker and a network interface device .

The disk drive unit includes a machine readable medium on which is stored one or more sets of instructions and data structures e.g. software embodying or utilized by any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processor during execution thereof by the computer system the main memory and the processor also constituting machine readable media.

The software may further be transmitted or received over a network via the network interface device utilizing any one of a number of well known transfer protocols e.g. HTTP .

While the machine readable medium is shown in an example embodiment to be a single medium the term machine readable medium may be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term machine readable medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of the present invention or that is capable of storing encoding or carrying data structures utilized by or associated with such a set of instructions. The term machine readable medium shall accordingly be taken to include but not be limited to solid state memories optical and magnetic media and carrier wave signals.

Although an embodiment of the present invention has been described with reference to specific example embodiments it will be evident that various modifications and changes may be made to these embodiments without departing from the broader spirit and scope of the invention. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense.

