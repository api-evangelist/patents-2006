---

title: Query framework system and method
abstract: A query framework system is provided. The query framework system comprises a query framework service for consuming a query and returning a result set, a provider application programming interface for defining a consistent application programming interface for providers, one or more providers incorporating query processing logic, and a configuration repository for storing the list of the providers in the query framework system and their properties.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07716212&OS=07716212&RS=07716212
owner: International Business Machines Corporation
number: 07716212
owner_city: Armonk
owner_country: US
publication_date: 20060622
---
This application hereby incorporates by reference Canadian Patent Application 2 510 630 filed on Jun. 23 2005.

The invention relates generally to data access middleware and in particular to a query framework system and method.

Prior business intelligence BI query engines are not extensible are not data agnostic and can not support the various requirements of a corporate performance management or a BI solution in a consistent manner. They can only support some of the BI requirements using fragmented and inconsistent sub engines each providing a subset of the solution. This inconsistency filters up to the front end of the solution and present the BI user with an inconsistent user experience.

In accordance with an embodiment of the present invention there is provided a query framework system. The query framework system comprises a query framework service for consuming a query and returning a result set a provider application programming interface for defining a consistent application programming interface for providers one or more providers incorporating query processing logic and a configuration repository for storing the list of the providers in the query framework system and their properties.

In accordance with another aspect of the present invention a system with query processing operations distributed across multiple reusable components query framework providers is provided. A set of providers is defined that comprises a system performing processing of data agnostic BI queries.

The present inventions allows for the building of business intelligence BI and corporate performance management CPM systems that query data using a BI query language that is data agnostic. The invention can also be applied to query processing systems supporting any other structured query language for example SQL or MDX.

The ability to support an end to end CPM solution Planning Business Intelligence and Score Carding using the same query engine and hence the same underlying software platform is an advantage of the query framework system . Other advantages include the flexibility of the overall system architecture which is easily maintainable and extendable. Customers other solution providers and OEMs can build on top of this framework their own business logic and hence customize an out of the box CPM. Also the benefit to the end user in terms of consistency in his her experience whether reporting ad hoc querying or analyzing data from various types of data source technology is another advantage.

Query processing usually is done in two phases query planning and query execution. During query planning a query received from a user is gradually transformed into an execution plan the tree of nodes representing operations to be performed during execution phase. Distributed query planning in the query framework system is achieved by breaking the full query into portions supported by corresponding providers. During the planning phase providers receive a designated query portion to apply planning actions. Providers analyze the designated query part and contribute to planning of this portion if they detect that their planning functionality is applicable to a given query portion. Providers may prepare the query portion i.e. plan the actions to be performed during the execution phase and replace this query portion with its execution plan. Providers may transform this query portion into another form in order to facilitate its preparation by other providers. The sequence of the provider invocation during query planning is predefined and stored in the configuration repository. The sequence of the provider invocation during the execution phase is driven by the execution plan built as a result of the planning phase. Provider execution method manipulates the data received from underlying datasources or other providers in order to produce the result master dataset returned back to a system user.

Existing data processing frameworks like ODBC or OLEDB effectively provide an ability to distribute execution of a query across different components. Yet the sequence of these operations had to be defined by a client application that would have to specify exactly what components are to be used to execute given query.

The query framework system allows to distribute not only the query execution phase functionality across multiple components but also to distribute the planning logic. It does not require a client application to be responsible for formulation of an operation execution sequence. Instead the configuration of the query framework would determine the execution operation sequence the execution plan during distributed query planning phase.

The main principle the distributed planning is based on is the ability of providers to recognize and extract the operations they can support out of a query portion they receive during the planning phase. Decomposition providers can break a full query into a tree of smaller sub queries to make it possible for providers to take a responsibility for those sub queries they can actually support.

Another cornerstone of the query framework is the unified Provider API interface that includes not only the methods involved in data retrieval but also the methods invoked during query planning. All providers are required to implement this interface and hence all providers are capable of participation in the query planning process.

Provider API as well as the client facing query framework API also serve the data agnostic function i.e. these interfaces provide an access and ability to manipulate both relational and multidimensional or OLAP data.

The query framework can be filled with any set of providers. It is recognized though that the following categories of providers will provide the completeness and flexibility of the query processing system as well as reusable nature of the system components query framework providers. The categories are query transformation providers service provider and query planning providers.

Query planner providers provide access to data either through internal operations or by calling external components providing data. The operation of query planner providers typically involves translation of the BIQuery language into the query language of underlying data sources such as relational databases supporting SQL query language. Query planner providers plan and execute a query portion or whole query that the coordinator designates to them. A result of execution is one or more master datasets.

Service providers handle operations that are not supported by planner providers. During query planning the service provider take the responsibility for the portion of a query not supported by planner providers. During execution service providers perform post processing of data returned by query planner providers. This category of providers can be replaced newly added or extracted out the system with minimum disruption to the query framework system.

Query transformation providers are involved in the query planning process. They are to perform query manipulations required to facilitate query planning process. Important instances of query transformation providers are query refinement providers query decomposition providers and query optimization providers. The refinement provider enhances a query specification to disambiguate clarify and make it easier to work with by other providers in the query framework system. The decomposition providers break a complex query into an equivalent combination of simpler queries. Decomposition allows the coordinator to distribute only portions of a full query to appropriate providers that do not support all operations involved in the full query. Query optimization providers are to transform a query in order to speed up a query execution.

The provider of the decomposition into primitive operations can be present in the query framework system to play a special role of insuring the system completeness given the system also has service providers associated with every primitive operation. The primitive operation denotes a simplest operation that constitutes an indivisible query part. The examples of primitive macro operations that can be recognized in the SQL query language are filter operation grouping and aggregation operation sorting operation joining operation etc.

Query framework configuration repository contains the parameters of the system as a whole the list of providers and their properties. A provider becomes integrated into the query framework system once it is described in the configuration repository so the query framework is easily extendable.

A provider is described by its identifier the name of a shared library DLL containing the provider functionality. It is defined whether a provider is optional or mandatory for the system work the property that separates essential system functionality from an additional plug ins.

Properties of a provider connection and metadata cache can be configured by the system defaults or can be overridden by the configuration parameters defined for specifically for a given provider.

Provider configuration has the section provider details that contains parameters applicable only to a given provider and interpreted by the provider itself.

The configuration repository also contains operation support tables of those providers that do not support the Discover method. It simplifies the access and maintenance of the operation support tables of those providers that do not require being self described in the system through the Discover method.

The query framework system coordination planner or coordinator is the component that is responsible for delegating the planning and execution of a BIQuery or its portions to a list of available providers. The coordinator makes use of available query transformation providers planner providers and service providers to refine plan decompose and execute a query.

The coordinator is designed to have no specific knowledge about the available providers. Their capabilities in terms of the supported operations and the sequence of their invocation are discovered at run time based on the information stored in the configuration repository and with the information returned by the provider method describing the provider properties. This design is intended to support feature providers to seamlessly plug in to the coordination layer in order to extend the query framework system functionality examples are disclosure avoidance provider or Custom Add on Filters .

During the query planning phase of query processing the coordinator invokes providers according to the query processing sequence stored in the configuration repository . The coordinator extracts the query portion supported by a given provider according to the operation support table of this provider. If the extracted query portion is empty the provider is not invoked. The coordinator then sends the extracted portion to the provider planning method and incorporates the result of the planning back into the query. One or more passes over the query processing sequence are expected to result into a completely planned query comprising a query execution plan the tree of executable operations.

The execution plan is used by the coordinator in order to guide the provider invocation during the execution phase of query processing. The coordinator first invokes providers responsible for the leaf nodes of the execution plan tree. The coordinator sends the executable operation definition to the execution method of corresponding provider and collects result datasets the provider returns. The collected result master datasets are passed by the coordinator to the providers higher in the execution plan tree as non leaf nodes in the execution plan denote operations applied on top of one or more input master data streams.

Using this mechanism the coordinator distributes parts of the decomposed query among one or more planner providers for execution. The planner providers execute the query with the help of data providers and return master datasets pointers to the coordinator . The coordinator then distributes the other parts of the decomposed query among service providers passing them pointers to the master datasets as input stream. The service providers apply local query operations on these input streams and return result master datasets to the query framework service which in turn returns them to the consumer application that submitted the original BIQuery for execution. This final result set returned to the client could span multiple planners and data source types.

Preferably the coordinator shares the same interface the provider API with all providers in the query framework . The coordinator acts as any other component in the system. Hence as any other component it can be replaced if needed. Adherence to the same interface also allows for recursive calls from other providers needed in some cases in order to force execution of the BlQuery portions that have to be processed out of the ordinary sequence.

The coordination layer of the query framework system architecture is the layer composed of the coordinator and the available query transformation providers which encapsulate query refinement decomposition and optimization functionality and the available service providers which encapsulate local execution tabular operations and multi cube joining functionality . The coordination layer of the query framework breaks any client dependency on the data source technologies available underneath the query framework service . In other words the coordination layer provides data agnostic query capabilities that can span relational multidimensional and proprietary vendor data sources to clients of the query framework system that use high level and simple BIQuery semantics. Data agnostic query capability is the main role of the query framework coordination layer. Another important role is the centralization of common query operations across all types of planner providers. Common functionality that would have been implemented repeatedly by each planner provider should be factored out to this layer.

The following is an example of a set of providers that comprises a query framework system capable of handling data agnostic BI queries.

This system can include a relational query planner an OLAP query planner a multidimensional operation decomposition provider a local tabular operation provider a tabular function decomposition provider a tabular operation decomposition provider a master detail provider a report mode provider and a cube builder provider .

The relational query planner is to handle query operation that can be converted into SQL statements. The relational query provider sends its queries to relational data sources.

The OLAP query provider handles query operations that can be converted into MDX statements. The OLAP query provider sends its queries to OLAP data sources.

The multidimensional operation decomposition provider performs a decomposition of queries containing OLAP operations on top of relational datasources. It may decompose a query into 4 sub queries a sub query that contains only relational operations a sub query responsible for the pivoting operation a sub query containing a OLAP functions and a sub query providing a final post processing of the result of first three sub queries.

The cube builder provider performs a pivoting operation of transforming a tabular stream into a cube dynamically created to represent pivoted dataset.

The local tabular operation provider can apply SQL operations to an input data stream. This provider can be implemented as an extension of the functionality of the relational query provider that treats an input data stream as a special relational datasource.

The tabular operation decomposition provider is responsible for handling operations over tabular streams like union except or intersect on top of OLAP datasources that do not support these operations natively.

The tabular function decomposition provider is responsible for decomposing the queries containing SQL like functions on top of OLAP datasources that do not support these operations natively.

The master detail provider is to handle master detail links between two independents queries. The master detail provider as well as the tabular operation decomposition provider allow combining data from relational and OLAP datasources.

The report mode provider extends the OLAP finctionalities by lifting limitation of MDX query language unioning of members from different dimensions projecting the same dimension on two or more edges and unioning member tuples of different size.

The functionality of the described providers can be rearranged in a different set of components by combining the feature of several providers into a single one or conversely by distributing a functionality of a single provider to a set of several components.

Other components may be added to the system including a no data mode provider a translator a post processor a metadata query provider a drill through provider and an OLAP data provider . shows in a block diagram a more detailed example of a query framework system .

The provider API and the operation support table OST are central to the query framework architecture. In particular the Prepare method of the provider API and the OST are be the basis for the query planning process.

The operation support table is associated with every relevant provider. It defines which operations from a predefined set are supported by a given provider. Operations are recognizable patterns in a tree of query blocks or in a tree of a query block specification. Operations are associated with a given node of a corresponding tree and searched for in the context of this node. The coordinator defines these patterns and provides the logic of spotting them in a query block tree and reporting supported unsupported association of an operation with each provider.

The operation support table allows for an initial distribution of the operations involved in the query between providers participating in the query framework. In most use cases that are handled by a query engine this initial distribution based on the data source type will be sufficient. That is all current queries involving only dbQuery subjects and current relational expressions are assigned to the relational planner based on the corresponding data source type in the OST . Also all current queries involving mdQuery subjects and dimensional expressions will be assigned to the OLAP planner based on the corresponding data source type in the OST .

The coordinator owns two resources pools a request resource pool and a connection resource pools. These pools contains resources that can be reused between different stages of query processing and shared across different provider participating in an execution of the a given request or associated with a given connection. Request resource pool contains resources pertaining to the same client query set to the query framework system. Connection resource pool contains resources that depends only on the properties of the connection and hence can be reused for multiple requests performed though the connection. The resource pools are accessible for all providers to add and read instances of the resources. The request resource pool is destroyed by the coordinator once the input request is completely processed. The connection resource pool get destroyed when the connection is closed. Resources are classified into types. A resource type denotes the semantics of a resource items and also is associated with the interface class used to access the content of a resource item. Some resource item types can be predefined in a query processing system for resources needed by every provider. Other types are specific for a given provider and are dynamically generated.

In each name prefix Provider is replaced with abbreviation that uniquely identifies the provider type. Each such class inherits from the standard Query Framework Service QFS class with a similar name less the prefix Provider. For example VendorQFSConnection inherits from QFSConnection.

Each method that a provider has to implement is defined as abstract in its parent class and has a provider prefix in its name. For example QFSMetadataQuery requires that the related provider class implements ProviderExcute method. Provider is not allowed to overload other methods from the parent class.

Methods with the provider prefix are called by equivalent non abstract methods of the parent giving the provider a chance to perform processing that is provider specific. For example ProviderQFSConnection ProviderDiscover is called by method QFSConnection Discover .

Provider authors can use the provided GenericProvider as the basis of their implementation and for more detailed information on methods and classes that are implemented.

Preferably Provider is packaged in a form of shared library DLL that is loaded by QFS on demand. Provider remains loaded in memory as long as there is at least one connection open to it. After all connections to the provider are closed provider library is unloaded by QFS.

Every time QFS needs to open a new connection it calls provider method NewConnectionObject which returns a new instance of a connection object ProviderQFSConnection. At this point connection to data source has not yet been established. It is opened when ProviderQFSConnection ProviderConnect method is called. Concurrent calls can be made to this method from multiple threads and so it must be implemented to be thread safe.

After connection is initialized it is used to query provider for properties ProviderQFSConnection ProviderDiscover and create new metadata and data query objects ProviderQFSConnection ProviderNewMetadataQuery and ProviderQFSConnection ProviderNewQuery .

ProviderQFSMetadataQuery object is used to execute metadata queries on the data source. ProviderQFSMetadataQuery ProviderExecute is called to perform actual execution.

ProviderQFSQuery object is used to execute data queries on the data source. ProviderQFSQuery ProviderPrepare is called during planning stage of query processing in order to invoke provider query planning logic. ProviderQFSQuery ProviderExecute is called to perform actual execution and its result is an instance of ProviderQFSMasterDataset that is then used to retrieve results of query execution in binary form.

ProviderQFSMasterDataset is used to request information about different portions of the result set in the form of ProviderQFSPartialDataset objects. Each of those data sets is then queried using instances of ProviderQFSIterator.

When provider is no longer needed it is unloaded from memory. At this moment its ProviderTerminate method is executed giving it a chance to free system resources. This method is called only once.

ProviderCancel method is used to cancel query that is currently being executed. This method is called at any point in time during query processing from a separate thread and therefore must be thread safe.

The systems and methods according to the present invention may be implemented by any hardware software or a combination of hardware and software having the functions described above. The software code either in its entirety or a part thereof may be stored in a computer readable memory. Further a computer data signal representing the software code that may be embedded in a carrier wave may be transmitted via a communication network. Such a computer readable memory and a computer data signal are also within the scope of the present invention as well as the hardware software and the combination thereof.

While particular embodiments of the present invention have been shown and described changes and modifications may be made to such embodiments without departing from the true scope of the invention.

