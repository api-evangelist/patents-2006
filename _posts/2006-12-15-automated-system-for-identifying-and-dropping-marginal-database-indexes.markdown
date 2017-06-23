---

title: Automated system for identifying and dropping marginal database indexes
abstract: A method and system for managing indexes used to retrieve data from a database stored on a computer, includes determining whether any marginal indexes exist in the database, and removing one or more of the marginal indexes from the database. An index is considered marginal when: (1) it is an access path for one or more queries but the index's performance is matched or nearly matched by one or more other alternative access paths, and/or (2) its overhead has become a concern. These steps or functions are invoked by one or more statements or instructions that cause the computer to perform a Drop Index Analysis on a specified list of tables in the database for a specified workload. The Drop Index Analysis allows users to specify: (1) how many indexes to consider dropping, and/or (2) how much disk space that dropped indexes should free up.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07761445&OS=07761445&RS=07761445
owner: Teradata US, Inc.
number: 07761445
owner_city: Miamisburg
owner_country: US
publication_date: 20061215
---
This invention relates in general to database management systems performed by computers and in particular to an automated system for identifying and dropping marginal database indexes.

Relational DataBase Management Systems RDBMS using a Structured Query Language SQL interface are well known in the art for use in data warehouses. The SQL interface has evolved into a standard language for RDBMS software and has been adopted as such by both the American National Standards Institute ANSI and the International Standards Organization ISO .

In an RDBMS all data is externally structured into tables. A table in a relational database is two dimensional consisting of rows and columns. Each column has a name typically describing the type of data held in that column. As new data is added more rows are inserted into the table. A user query selects some rows of the table by specifying clauses that qualify the rows to be retrieved based on the values in one or more of the columns.

The SQL interface allows users to formulate relational operations on the tables either interactively in batch files or embedded in host languages such as C COBOL etc. Operators are provided in SQL that allow the user to manipulate the data wherein each operator performs functions on one or more tables and produces a new table as a result. The power of SQL lies on its ability to link information from multiple tables or views together to perform complex sets of procedures with a single statement.

The SQL interface allows users to formulate relational operations on the tables. One of the most common SQL queries executed by the RDBMS is the SELECT statement. In the SQL standard the SELECT statement generally comprises the format SELECT FROM WHERE GROUP BY HAVING ORDER BY . The clauses generally must follow this sequence but only the SELECT and FROM clauses are required.

Generally the result of a SELECT statement is a subset of data retrieved by the RDBMS from one or more existing tables stored in the relational database wherein the FROM clause identifies the name of the table or tables from which data is being selected. The subset of data is treated as a new table termed the result table.

Indexes are beneficial to the execution of SQL statements because of their ability to improve query performance. One drawback to indexes is the additional disk space they require and the resources needed to maintain them during SQL updates and bulk load operations. Users must consider these tradeoffs before deciding to initially create a new index.

Over the course of time the factors involved in this initial decision may change and users may wish to drop one or more existing indexes. Disk space can become scarce and users may wish to drop indexes in an effort to reclaim the space they occupy. Update and load operations may become more frequent over time leading to excessive index maintenance costs. In such cases users would like to identify the set of existing indexes if any that can be dropped without significantly impacting query performance. Essentially users are always looking for the minimal set of indexes that can deliver the required query performance.

Query performance is often dependent on physical database design which is an essential step to implementing a high performance data warehouse. During this process users make choices regarding the physical characteristics of their relational tables and columns. The process of making these choices manually is difficult and mistaken prone for even experienced users. For this reason vendors often provide tools or wizards that examine a user s workload and make index recommendations.

The current focus of such tools is on the creation of new indexes to improve workload performance. Current tools are also capable of identifying unused indexes and recommending their removal. However one important capability that has been overlooked is the identification and removal of marginal indexes whose benefit to query performance is positive but insignificant especially when other factors are considered.

Although a given index may be chosen as an optimal access path it is not uncommon for alternative access paths to exist that would deliver similar performance. Because the optimization process does not reveal its sub optimal plans users may not be aware that a smaller set of defined indexes may be able to deliver similar workload performance with only a minor degradation.

Techniques have been developed for solving this problem. However all known physical database design processes for indexes concentrate on the selection of new indexes or the removal of completely unused indexes. No known solutions focus on removing marginal indexes or helping users to identify the minimal set of required indexes.

Consequently there is still a need in the art for additional optimization techniques. The present invention satisfies this need.

To overcome the limitations in the prior art described above and to overcome other limitations that will become apparent upon reading and understanding the present specification the present invention discloses a method and system for managing indexes used to retrieve data from a database stored on a computer.

Generally this entails determining whether any marginal indexes exist in the database and removing one or more of the marginal indexes from the database. An index is considered marginal 1 when it is an access path for one or more queries but the index s performance is matched or nearly matched by one or more other alternative access paths and or 2 when its overhead has become a concern.

An Index Wizard tool performs these steps or functions and is invoked by one or more statements or instructions that cause the computer to perform a Drop Index Analysis on a specified list of tables in the database for a specified workload. Preferably the Drop Index Analysis allows users to specify 1 how many indexes to consider dropping and or 2 how much disk space that dropped indexes should free up.

In the following description of the preferred embodiment reference is made to the accompanying drawings which form a part hereof and in which is shown by way of illustration a specific embodiment in which the invention may be practiced. It is to be understood that other embodiments may be utilized and structural changes may be made without departing from the scope of the present invention.

The present invention discloses an improved method and system for automatically determining the best set of marginal indexes to drop in a relational database management system where the term marginal describes an index a that serves as the best access path for one or more queries but whose performance can be nearly matched by other alternative access paths and b whose disk space or maintenance overhead has become a concern.

Operators of the computer system typically use a client such as a terminal workstation computer or other input device to interact with the computer system . This interaction generally comprises statements that conform to the Structured Query Language SQL standard and extensions thereto and invoke functions performed by a Relational DataBase Management System RDBMS executed by the system .

In the preferred embodiment of the present invention the RDBMS comprises the Teradata product offered by NCR Corporation the assignee of the present invention and includes one or more Parallel Database Extensions PDEs Parsing Engines PEs and Access Module Processors AMPs . These components of the RDBMS perform the functions necessary to implement the RDBMS and SQL functions i.e. definition compilation interpretation optimization database access control database retrieval and database update.

Generally the PDEs PEs and AMPs comprise instructions and or data that are tangibly embodied in and or accessible from a device or media such as RAM ROM one or more of the DSUs and or a remote system or device communicating with the computer system via one or more of the DCUs . The PDEs PEs and AMPs each comprise instructions and or data which when executed invoked and or interpreted by the PUs of the computer system cause the necessary steps or elements of the present invention to be performed.

Those skilled in the art will recognize that the exemplary environment illustrated in is not intended to limit the present invention. Indeed those skilled in the art will recognize that other alternative environments may be used without departing from the scope of the present invention. In addition it should be understood that the present invention may also apply to components other than those disclosed herein.

In the preferred embodiment work is divided among the PUs in the system by spreading the storage of a partitioned relational database managed by the RDBMS across multiple AMPs and the DSUs which are managed by the AMPs . Thus a DSU may store only a subset of rows that comprise a table in the partitioned database and work is managed by the system so that the task of operating on each subset of rows is performed by the AMP managing the DSUs that store the subset of rows.

The PDEs provides a high speed low latency message passing layer for use in communicating between the PEs and AMPs . Further the PDE is an application programming interface API that allows the RDBMS to operate under different operating systems in that the PDE isolates most of the operating system dependent functions from the RDBMS and performs many operations such as shared memory management message passing and process or thread creation.

The PEs handle communications session control optimization and query plan generation and control while the AMPs handle actual database table manipulation. Preferably the PEs fully parallelize all functions among the AMPs .

The system does face the issue of how to improve workload performance through the addition and removal of indexes. Tools are necessary for resolving these issues. Specifically tools are necessary for assisting in the physical database design processes for indexes specifically on removing marginal indexes. Such a tool is described in more detail below.

The Index Wizard tool includes a user interface performed by the Client and various back end components of the PE that contain the intelligence for evaluating index candidates. These components of the PE include a Query Analyzer Query Optimizer Search Engine and Index Simulator which perform the following functions 

With regard to the addition of new indexes the Index Wizard tool performs logic referred to as Index Analysis which is invoked using the following SQL statement 

where is the name previously associated with one or more queries. The result of this SQL statement is a set of recommended index definitions defined on the tables specified in . The recommendations are stored within a named set of pre defined dictionary tables that is identified by . One of the primary options supported in the SET clause is the maximum number of new indexes to recommend per table.

With regard to the removal of existing indexes the Index Wizard tool performs logic referred to as Drop Index Analysis which is invoked using the following SQL statement 

Thus the syntax used to support the Index Analysis is extended for the Drop Index Analysis to include an optional DROP clause that changes the goal of the Index Wizard tool from the creation of new indexes to the removal of marginal indexes. In addition the SET clause includes two options to permit further control over the indexes to consider dropping 1 users can specify the number of indexes they would like to consider dropping or 2 users can specify the minimum amount of disk space in bytes that the dropped indexes should free up.

The basic approach used in Index Analysis when recommending new indexes is to let the Query Optimizer choose the indexes it likes. The Query Optimizer is repeatedly called with different sets of simulated candidate indexes. The Search Engine is a combinatorial search engine that is used to explore the solution space consisting of various combinations of promising new index recommendations. The set of candidate indexes that results in the lowest estimated workload costs is retained as the final recommendation.

This same basic approach is used in Drop Index Analysis to recommend a set of existing marginal indexes to drop. The Query Optimizer is repeatedly called with different sets of existing indexes whose definitions have been temporarily removed from consideration by the Query Optimizer . The set of dropped indexes that results in the lowest estimated workload cost is retained as the final recommendation. Hence the basic approach of the present invention is to let the Query Optimizer decide which indexes it can live without.

The Drop Index Analysis is performed by first calling the Query Analyzer to collect the list of existing indexes on the tables to be analyzed along with the estimated disk space occupied by each of them. Note that the primary index of each table is not included in this list as it cannot be dropped.

The Search Engine is then called to enumerate sets of candidate indexes to be dropped. If the NUM INDEXES TO DROP option has been specified with a value of N the Search Engine enumerates only those combinations that consist of N indexes. If the DISK SPACE TO FREE option has been specified with a value of D those combinations whose total estimated space is less than D are skipped by the Search Engine and are not further considered.

For each enumerated candidate set the Search Engine calls the Index Simulator to simulate the non existence i.e. removal of each index by removing its definition from the dictionary information accessible by the current session.

The Query Optimizer is then called to estimate the cost of executing each query without the candidate indexes. The set of dropped indexes that results in the lowest estimated cost for the entire workload least degradation is retained as the final recommendation. Drop recommendations are stored in the specified in the form of DROP INDEX SQL text.

The recommended set of indexes to drop will result in the least possible amount of degradation to query performance. This degradation may or may not be acceptable to users and hence it must be carefully considered prior to actually dropping the recommended indexes.

Consider the following example which assumes a table t1 with four secondary indexes whose definition is as follows 

Following is the estimated cost for each query along with the access path chosen by the Query Optimizer .

Based on the specified DISK SPACE TO FREE parameter 1 MB the Search Engine immediately eliminates INDEX d1 from consideration because it occupies less than 1 MB. Based on the specified NUM INDEXES TO DROP parameter the Search Engine then enumerates all candidates consisting of a single index as shown below.

As shown above for each candidate the Query Optimizer is invoked to generate the resulting plan including access paths and cost for each query in the workload.

Dropping INDEX a1 or INDEX c1 results in a very expensive full table scan on queries 1 and 3 respectively. However dropping INDEX b1 results in only a minor performance degradation in query 2 550 ms vs. 500 ms due to the existence of an alternative access path using INDEX a1 . Hence the final recommendation would be to drop the index on column b1 . Doing so would free up disk space of 7.5 MB and would only slightly increase the total cost of the workload.

Consequently the present invention leverages an existing architecture to solve a related but separate problem from the creation of new indexes. The selection process considers a large number of candidates and performs a query optimization to evaluate and rank each candidate by its impact on estimated query costs. This approach ensures consistency with the index selection process used in query optimization and avoids duplication of the cost model used in query optimization. Rather than introducing a separate and potentially conflicting set of rules and costs the approach taken by the present invention is to let the query optimization process decide which indexes it can live without.

Specifically this logic represents the Index Wizard tool determining whether any marginal indexes exist in the database. As noted above an index is marginal when 1 it is an access path for one or more queries but the index s performance is matched or nearly matched by one or more other alternative access paths and or 2 its overhead has become a concern.

Moreover this logic may be invoked by one or more statements or instructions that cause the computer to perform a Drop Index Analysis on a specified list of tables in the database for a specified workload. These instructions allow users to specify 1 how many indexes to consider dropping and or 2 how much disk space should be freed up from the dropped indexes.

Block represents the Index Wizard tool identifying existing indexes in the database that potentially could be dropped along with an estimated disk space occupied by each of the indexes.

Block represents the Index Wizard tool performing a combinatorial search in order to collect a list of the sets of indexes in the database to be analyzed. Note that a primary index for each table in the database is not included in the list.

Block is a decision block that represents the Index Wizard tool determining whether the search is complete. If so control transfers to Block otherwise control transfers to Block .

Block represents the Index Wizard tool identifying the current best set of N candidate indexes for removal if any. At this block the Index Wizard tool may issue a report or display a message and prompt the user for further processing such as the actual removal of the current best set fN candidate indexes from the database.

Block represents the Index Wizard tool generating the next set of N candidate indexes to be analyzed i.e. enumerating only those sets of candidate indexes that contain N indexes where N is typically a user specified value.

Block is a decision block that represents the Index Wizard tool determining whether the set of N candidate indexes represents sufficient freed disk space in accordance with the user s specification i.e. ensuring that the Index Wizard tool enumerates only those sets of candidate indexes that contain D disk space where D is typically a user specified value. If so control transfers to Block otherwise control transfers to Block .

Block represents the Index Wizard tool simulating removal of the set of N candidate indexes from the database in order to determine whether any marginal indexes exist in the database.

Block represents the Index Wizard tool invoking the query optimizer to generate one or more plans after the simulated removal of the set of N candidate indexes from the database. These plans estimate the cost of executing each query in a specified workload without the removed indexes. Specifically the Index Wizard tool repeatedly performs query optimization on the specified workload using different sets of existing indexes for a specified list of tables in the database whose definitions have been temporarily removed from consideration by the query optimization.

Block is a decision block that represents the Index Wizard tool determining whether the generated plans have a cost less than the cost of the current best set of N candidate indexes. If so control transfers to Block otherwise control transfers to Block .

Block represents the Index Wizard tool saving the set of N candidate indexes from the database as the current best set of N candidate indexes. Consequently a set of N candidate indexes that results in a lowest estimated cost for the specified workload is retained as a recommendation for dropped indexes.

This concludes the description of the preferred embodiment of the invention. The following describe some alternative embodiments for accomplishing the same invention. In one alternative embodiment any type of computer such as a mainframe minicomputer or personal computer could be used to implement the present invention. In addition any DBMS that uses indexes could benefit from the present invention.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

