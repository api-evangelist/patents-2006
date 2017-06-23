---

title: Implementation system for business applications
abstract: The system comprises a man-machine interface for controlling the application, a server running the application, a server hosting the service and a server for automatically calling the service, including memory resources containing the data describing the service, receive the data related to the service and transform that data so that it can be processed in the application server, all of which under the control of the man-machine interface and the application server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08209710&OS=08209710&RS=08209710
owner: Xcalia
number: 08209710
owner_city: Paris
owner_country: FR
publication_date: 20060105
---
This invention relates to an implementation system for business applications that can be used to federate the data received from data providers into a common set and process said set in real time.

The first developments of this variety were produced in certain major corporations. They were used during the manufacturing stage to computer process the IT data received from specific businesses by automatically transferring a computer file in so called neutral format.

The emergence of Intranets and the Internet and especially the growth in the number of computerized businesses has led to the need for increased automatic exchanges between those businesses.

International organizations began thinking of SOAs Service Oriented Architectures in which the business applications are based on services instead of coded entities for the purpose of more effectively gearing the new information technologies towards the company s businesses and introducing a higher degree of flexibility into their working environment.

Services or functional services are actually taken to mean functional IT modules such as functional modules of payroll invoicing production management technical data and client systems or CAD Computer Aided Design and CAM Computer Aided Manufacturing modules and so on. The last meaning given will be used in the remainder of this document.

Currently an approach extending that used for neutral formats involves developing a standard bus capable of supporting computer exchanges between heterogeneous services or businesses. The ESB Enterprise Service Bus is one example. Such a solution works all the time that the exchange requirements are low but beyond that the solution is not necessarily efficient.

Furthermore the work performed by standardization groups such as OMG Object Management Group JDO Java Data Object JCA Java Connector Architecture JMS Java Messaging Service EJB Enterprise JavaBeans and SOAP Service Oriented Architecture Protocol is common knowledge.

These working groups particularly rely on the capacities of the Java languages programming language for the Web as well as the WSDL Web Service Definition Language and OWL languages Web Ontology Language for developing business applications on the Web.

Work is also focusing on languages for corporate metadata such as EMD Enterprise Metadata Discovery but it is still unfinished or deliberately incomplete.

Obviously the first step in all this work is to manage to formally describe the most common services and businesses by using data describing the services known as metadata but the problem is a difficult one due to the diversity and complexity.

For example if we consider an application used by a consumer goods company to view its customer invoices on the Web this Java business application must have access to the data relating to an invoicing service a customer service and a product service. This data is presumed to reside in memory blocks but it is not. In the current example it can only be retrieved by querying an RDBMS and must be translated into XML data. As most of these operations are manual the invoices cannot be viewed in real time which means that the system is impracticable.

In brief and to simplify matters an SQL application cannot be used to query or even call callable services over the Web and conversely a Web based Java application cannot be used to call and query a service related to an RDBMS or a transaction processing system nor receive data associated with the requested service.

Consequently even if the data describing the services or businesses in question were available it would be impossible to create a consistent dataset containing federated data from the Web and from an RDBMS or OODBMS or in any other system above and especially process that set in real time.

The applicant has been present in the market for several years via its work in the field of query software for large capacity databases such as RDBMS and OODBMS and other data sources available on the Web XML and binary files. As part of its wish to extend the scope of its products to SOA service oriented architectures the applicant came upon the idea for its invention.

Therefore the invention relates to an implementation system for business applications based on at least one callable functional service comprising a man machine interface for controlling the application a server running the application a server hosting the service and a server for automatically calling the service including memory resources containing the data describing the service and business on the application and designed to call the service receive the data related to the service and transform that data so that it can be processed in the application server all of which under the control of the man machine interface and the application server.

The server for automatically calling the service acts as an intermediary between the server running the application and the server hosting the service.

To do so the server for automatically calling the service comprises an intermediation module designed to substitute for the business application during the time required to send a service related data business query to the server hosting the service and return the data to it. The business application can therefore process the service related data in real time.

The server for automatically calling the service preferably comprises a mapper module featuring the memory resources containing the data describing the service and the data describing the business on the application for calculating the data describing the execution of the business queries and arranging them in the memory resources. In particular this allows for the subsequent processing of business requirements that are not known during development.

The intermediation module has the advantage of featuring an execution block for substituting for the business application during a query phase. To do so the application query phase is executed via a compiled query program where said compiled program is enhanced with call commands for the intermediation module in the appropriate parts of the program when post compiling on said program.

To query the service related data the intermediation module is designed to extract the data describing the execution of the business queries from the memory resources containing them and to query the service related data the execution block features a translation function designed to translate the queries to the service into calls compliant with the API Application Programming Interface a selection function designed to select a driver according to the type of server hosting it and a command function for the selected driver and for executing the translated queries.

As the implementation system preferably contains at least two callable services the intermediation module features a rule engine block designed to calculate schedule and arrange the data describing the organization of the calls to said services in a program memory block.

The rule engine block is designed to calculate execution rules for the calls to the services according to a business application query the data describing the services and business and the grammar.

A noteworthy characteristic of the invention is that there is no need to translate the data related to one of the services into data related to one of the other services to execute the business application. The native data for each service is used in Web language such as XML which ensures that the results are as integral and complete as possible where this data alone is capable of meeting the most demanding of production requirements.

The server for automatically calling the service is preferably connected to a general purpose computer network of the Internet or Intranet variety to serve as a data server or benefit from the Web services and can be called from the server running the application and is connected to a company s specific computer network such as an Ethernet type of database management systems hosting services.

In the example in the intermediate server is linked to the application server by an Intranet for example also by an Ethernet link and to the Internet on the one hand to be controlled if required from a Web based application and on the other to query Web services such as by using a Web language e.g. WSDL or SOAP .

Each service comprises an API so that it can be called programmed and executed by the network channel to which it is connected.

The business application is based on the processing of service data which can be retrieved by calling the services from among and . It is controlled by the interface .

It conventionally features all the control command methods not represented such as a supervisor and real time monitors an input output module and specifically in this case a mapper module or EDME Entity Data Mapping Engine and an intermediation module .

The mapper module is a mapping engine for the data describing the services and the BMM Business Method Model metadata on the business application .

The mapping of the data describing the services and the BMM metadata are stored as mapping tables in a fourth memory block for each application query when executed in real time by the mapper .

For example by considering the application mentioned earlier for viewing invoices as illustrated in memory blocks and are initialized with the SEM and SMM metadata of all services of use to the business application where for each service the metadata describes the structure of the service in memory block and the method for creating the structure of the service in memory block based on the bibliographical SDM Service Description Model metadata .

In the example in an initial service is a database of the structure identified as SEM containing hierarchical data or entities where the customer reference entity covers the account invoice and product reference entities. The structure of the second service identified as SEM cannot be seen and more simply contains a product reference entity with which a product description is associated.

Based on a list of BMM business data subject to an application query for the product feature description of a product subject to a customer invoice the mapper module deduces the mapping table indicating the useful services and supplying the useful entities for providing the service responses to the query and stores it in memory . An incompatibility between the business requirements and the available services may be detected at this level of processing.

Furthermore the mapper module arranges the metadata in memory blocks and for services and into a directory which is arranged by the references of the callable services with the characteristics of the corresponding APIs .

The intermediation module comprises an execution block a rule engine block containing an engine program M a memory block containing the elements for the specific grammar or metalanguage and a program memory block .

The input output block comprises a set of bidirectional drivers adapted to the APIs of the different systems hosting the services a service response processing block and a transceiver block .

Block comprises a function for transforming the service responses into data that can be read by the application and a function for sending to the application .

The execution block comprises a selection function designed to select the required driver according to the type of server hosting the service a translation function designed to translate the queries to the services into calls compliant with their respective APIs and a function for controlling the selected driver and executing the translated queries.

The rule engine retrieves the contents of memory blocks and computes a query execution program and arranges the program in program memory block .

The query execution program in memory block is computed as a program in formal language referred to here as SEL Symbolic Execution Language or BPEL Business Process Execution Language and which can be considered as the data describing the organization of the calls to the services.

The SEL is the terminal language calculated from the contents of memory blocks and considered as a non terminal language by applying the specific grammar .

Although the contents of memory blocks and change with each query the grammar is invariable and depends only on the configuration of the system . It is initially established according to the known mathematical methods in the field of artificial intelligence and expert systems and is subsequently an integral part of the system . Part of its listing in XSD format XML Scheme Definition is given in the appendix.

To go back to the simple example of displaying customer invoice details the engine program M of the rule engine calculates the contents of program memory block meaning the execution program in symbolic execution language SEL .

To do so the engine program M first analyzes the SEM metadata according to the analysis rules included in program M and predetermined by the structure of the services concerned and the facts. It deduces the SMM generation methods according to the effect rules included in program M and predetermined by the results demanded from the various services taking account of the hierarchical dependency links such as those identified as and between the entities of the SEM data structure seen above.

Then according to the mapping performed above the SMM and data in and the specific grammar for the rule engine it computes the execution program for the calls to services and which orchestrates two successive calls one to service to find the product reference in the invoice of the customer performing the query and the other to service to find the features of the product above. In this case the system has transformed two real hierarchical databases into a virtual relational database.

The application query is executed by running a service query program belonging to the application and expressed in a precompiled language from the man machine interface .

To ensure that the program can access the services it is enhanced with call commands for the intermediation module at appropriate parts of the program. Enhancement can be executed when post compiling the program following compilation.

As the query program is programmed in Java language the calls to the intermediation module and the response from the module are programmed to comply with the currently known data access standards such as JDO JSR12 and SDO.

Finally the BMM metadata for all applications is arranged in directory according to the business and application references when initially integrating the system .

To perform a business application query the user orders a launch stage for the application via the interface keyboard for the server .

During stage the application launches a Java query program that executes a call to the intermediation module of the intermediate server which is sent during stage by the network channel the input output block and the transceiver block . The call is referenced A like the application and contains the Ei entity references.

During stage the intermediation module searches in directory for one or more service references from to be queried from the E entities subject to the query performed by the reference A application . Two cases may arise as follows 

In stage the execution module retrieves the SMMj contents and the mapping in memory blocks and respectively and runs the rule engine block which generates the query execution program BPEL in stage from the grammar that it arranges in program memory block .

In stage the execution block reads the formal BPEL language in memory block uses the selection function to select the API driver of the service on the server hosting the service translates it via its translation function into queries for the selected API and executes the API queries via its function by the channel for drivers and in the input output block .

In stage the selected service processes the API query and in stage retrieves the data from the relevant database or performs the usual transactions with its data provider such as the Internet .

In stage the selected service returns the retrieved data in native format in Web language e.g. XML which ensures that the results are as integral and complete as possible to the input output block which during stage resends it to the execution block to complete by looping back to stage the execution of the BPEL program in memory block or to launch stage for resending via block of the input output block to the application via the Intranet channel .

When the service data is received during stage the application is rerun as if the data were present in the memory of the server hosting the application.

It can be seen that the intermediate server is a true server for automatically calling the services that acts as an intermediary between a business server comprising business applications and complementary computerized services hosted on the heterogeneous systems of a mixed range of data providers.

