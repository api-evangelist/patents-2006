---

title: System and method for on-demand integrated archive repository
abstract: System, method and computer program product for creating, managing, and accessing an information repository including a source database and an archive database. A source database and the archive database are defined to a same schema. A user terminal presents a common user interface for accessing the source database and the archive database. A timed archive agent, an end user archive agent, and a criteria based archive agent archive source data from the source database as archive data to the archive database. A criteria based restore agent and an end user restore agent are provided to restore archive data from the archive database as source data to the source database. An integrated functions agent assembles compiled data from source data and archive data and present the compiled data to the user interface.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07809689&OS=07809689&RS=07809689
owner: International Business Machines Corporation
number: 07809689
owner_city: Armonk
owner_country: US
publication_date: 20060126
---
Copending U.S. patent application Ser. No. 11 122 584 filed 5 May 2005 entitled METHOD SYSTEM AND PROGRAM PRODUCT FOR USING ANALYSIS VIEWS TO IDENTIFY DATA SYNCHRONIZATION PROBLEMS BETWEEN DATABASES and Ser. No. 10 040 844 filed 7 Jan. 2002 for a workstation management tool are assigned to the same assignee hereof and contain subject matter related in certain respects to the subject matter of the present application. The above identified patent applications are incorporated herein by reference.

This invention relates to computer databases. More particularly it relates to a system and method for creating managing and accessing an archive database information repository .

Very often a database will grow too large or may contain sensitive information that needs to be isolated from general use. Such information is generally considered old data and is moved to an archive generally for the purpose of maintaining an audit trail.

There is a need in the art however for not discarding or simply archiving excess information but rather for maintaining such information out of the way of end users and yet kept within a production setting where it can be queried in live time along with the production data.

System method and computer program product for creating managing and accessing an information repository including a source database and an archive database by defining the source database and the archive database to a same schema providing to a user terminal a common user interface for accessing the source database and the archive database selectively executing a timed archive agent an end user archive agent and a criteria based archive agent for archiving source data from the source database as archive data to the archive database selectively executing a criteria based restore agent and an end user restore agent to restore archive data from the archive database as source data to the source database and executing an integrated functions agent to assemble compiled data from source data and archive data and present the compiled data to the user interface.

Other features and advantages of this invention will become apparent from the following detailed description of the presently preferred embodiment of the invention taken in conjunction with the accompanying drawings.

In accordance with a preferred embodiment of the invention a system and method is provided for creating maintaining and using an integrated archive repository or mirror database application having a schema identical in all relevant respects to that of an original database source application or production repository or database.

In accordance with some criteria such as a straight scheduled archive archive on demand information becoming sensitive soft document deletion and so forth information is moved from the source application to a mirror archive where the information is available for secure direct access by qualified personnel and also for restoration on demand to the source application and for integration with the source information to support reports measurements audits and so forth.

Thus information is not merely archived but placed in an alternative repository where it remains integrated with the original repository thus keeping the information in a production setting. That alternative repository is a database which sits outside of the production application and to which information is removed when no longer used by the application. This can be queried in live time along with the production data but it is still out of the end user s way.

Referring to source database information is directed to and received from archive database by way of several agents including timed archive end user archive criteria based archive criteria based restore and end user restore . Measurements reporting audits and integrated functions receives data from both archive database and source database . End user terminal accesses source database and archive database .

Referring to in accordance with an exemplary embodiment of the invention a work station life cycle management system includes a set of applications including a client information manager and database a workstation planning and deployment manager and database and an archive client manager and database . The client information manager CIM or source program for archived data may be for example a database and an access program.

The client information manager CIM includes a database with information about people in an organization such as a division of a corporation and the type of computing equipment they have at their workstation or otherwise in their respective offices or otherwise allocated for a person s use.

The workstation planning and deployment manager includes a deployment database showing for each such division the personal workstation computing budget to which the division is entitled and provides for the scheduling and deployment of equipment and related reporting according to that budget.

The archive client manager and database provides for storage of information which must be isolated for security reasons. This is a criteria based archived database of persons who had a machine deployed including transitioned employees and includes the same information in the same format as for the client information manager .

Another example of information stored to archive database and of uses of such information include new hires and transfers between divisions who need to be moved into CIM database and deployed equipment upon arrival on the job. An asset manager may enter such information to archive database and move it into CIM database at his discretion.

A timed archive of information from CIM database to archive database may be a complete or partial archive of database which enables CIM database to be purged of selected records to manage the size of that database .

In order to provide certain reporting features including measurements and auditing all databases and are connected through a refresh plan reports function or agent . For example such reports may provide for each information technology IT representative for each division a report of business areas supported and the deployment of equipment against a deployment budget. Agent in this example in order to show how many individuals have received laptops will need to access both CIM database and archive database .

A specific example of how this reporting function may work suppose an employee who was scheduled for a desk top in the first quarter experiences a job change that requires that he be deployed a lap top immediately. Deployment and reporting agent is operated by asset manager to show from CIM database allocation of the latest equipment deployed to this employee and to show from archive database previous deployments to this employee during the planning period.

The design of each database is common so that agent can generate reports accessing them all. Each database is provided lookup views at a user interface UI which is the same. This is so that the user can get the same data from each of the databases listed and do comparisons and compilations upon the data contained in each including the archive repository.

Referring to and several exemplary user interfaces UIs illustrate user access to databases and for entering and extracting information and facilities for defining maintaining and selecting execution agents and .

Referring to a typical user interface includes a title bar and plurality of action selection tabs a tool bar a navigation bar application tabs and an application window in this embodiment showing tabs for selecting client information manager and CIM archive manager respectively.

Referring to illustrates a UI for looking at employees or clients. Selection of button brings up a view for accessing client information manager under tab . Selection of tab displays table of contents TOC a portion of which is shown a scroll bar for positioning the TOC to the illustrated portion is not shown . Selection of item in TOC brings up in panel a list of clients from CIM source database with each row including fields for PLAN QUARTER TYPE IT REP information technology representative BA business area and STATUS. Table 1 is an example of such a listing.

Referring to an example UI illustrates an example display of information selected from CIM archive database . Selection of CIM archive button brings up a view for selecting under tab a display including TOC . Selection of item in TOC brings up in panel a list of clients from CIM archive database with each row including fields for PLAN QUARTER TYPE IT REP BA and STATUS. Table 2 is an example of such a listing.

Information added to archive database may be based on criteria and will normally not be just a snapshot of the CIM database . An example of such a criteria would be an employee in CIM database who is no longer in the organization shown in the business area BA field. His record in CIM may be moved to archive database on a record basis either automatically or on demand.

Referring to a user interface illustrates an exemplary report generated in accordance with fields responsive to selection of button under technology group TG workplace data manager WPDM business information executive BIE tab from source database and archive database by planning deployment manager . Action tabs are provided to update allocations update inventory transfer allocation inventory refresh plan reports and archive . These functions are performed with respect to a selected entry from display a view in which the action Refresh Plan Reports exists which is the action that calls an agent to work on the selected entry. Table 3 provides an example of report .

Update allocations and update inventory neither pertinent to the present invention update sets of numbers in the database WPDM. Transfer allocation inventory not pertinent to the present invention moves certain numbers to and from different database documents as a method of transferring governing control over those numbers.

Refresh plan reports allows the user to retrieve a set of information from the three databases previously described. It runs an agent to pull in information from all these databases and build a viewable report Table 3 that identifies problems or mishaps in the deployment process.

Referring to a user interface illustrates an individual record for an information technology IT representative. User selection of button brings up under tab a report for an individual IT representative in this case for Kimberly from Table 3 prepared from source database by planning and deployment manager .

Referring to a user interface illustrates a report of transitioned employees generated by selection of client information button under clients tab and selection of transitioned employees from TOC . Field definitions define the fields in the listing . Action buttons clear disposition clear critical unflag workstation archive transitioned clients and clear archive transitioned clients perform the specified action with respect to employee selected by the user from list . For example selection of button moves the highlighted employee record from source database to archive database .

Referring to user interface illustrates agent which is displayed under tab responsive to selection of button and of item from TOC . The initialize agent object upon being selected from objects displays agent code listing which is further shown in Table 4.

It is an advantage of the present invention that there is provided a system and method maintaining excess and sensitive information out of the way of end users and yet within a production setting where it can be queried in live time along with the production data.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

Furthermore the invention can take the form of a computer program product accessible from a computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer readable medium can be any apparatus that can store the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device . Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

A data processing system suitable for storing and or executing program code will include at least one processor coupled directly or indirectly to memory elements through a system bus. The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

Input output or I O devices including but not limited to keyboards displays pointing devices etc. can be coupled to the system either directly or through intervening I O controllers.

Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters.

It will be appreciated that although specific embodiments of the invention have been described herein for purposes of illustration various modifications may be made without departing from the spirit and scope of the invention.

Accordingly the scope of protection of this invention is limited only by the following claims and their equivalents.

