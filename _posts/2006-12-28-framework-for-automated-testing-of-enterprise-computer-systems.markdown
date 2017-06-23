---

title: Framework for automated testing of enterprise computer systems
abstract: An automated testing framework enables automated testing of complex software systems. The framework can be configured for test selection, flow definition, and automated scheduled testing of complex computer systems. The framework has facilities for result analysis, comparison of key performance indicators with predefined target values, and test management.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07620856&OS=07620856&RS=07620856
owner: SAP Portals Israel Ltd.
number: 07620856
owner_city: Ra'anana
owner_country: IL
publication_date: 20061228
---
This invention relates to testing of complex computer systems. More particularly this invention relates to an automated framework for managing testing of enterprise computer systems.

Enterprise software systems such as portal based network environments have become almost essential for operation of large modern businesses and include a variety of complex software. For example such environments can now be implemented using SAP NetWeaver available from SAP AG Neurottstra e 16 69190 Waldorf Germany. This technology supports integration and application platform requirements and facilitates the development deployment and administration of enterprise services.

Such systems involve large numbers of modules often produced by different vendors and employing diverse operating systems. Implementing and successfully coordinating these systems may require the construction and maintenance of complex landscapes and connection frameworks in order that the user be able to seamlessly access and harness the diverse modules. Furthermore such modules are continually updated by their producers which imposes an ongoing requirement for compliance validation and performance optimizations.

In order to enable clients to test its portal technology SAP provides a tool known as the Extended Computer Aided Test Tool eCATT which falls into the category of Computer Aided Software Engineering CASE tools. The primary aim is the automatic testing of SAP business processes. Each test generates a detailed log that documents the test process and results allowing evaluation of the quality of the system being tested. The tool enables automatic testing in a graphical user interface GUI in the Microsoft Windows and Java environments. In order to offer a complete test solution that covers other GUIs eCATT has interfaces to various third party tools. Typical applications for eCATT include testing transactions reports and scenarios Business Application Programming Interfaces BAPI remote systems databases applications and GUT S.

U.S. Patent Application Publication No. 2005 0166094 describes a tool for testing performance of interrelated components of complex software systems. A system known termed an Automated Multidimensional Traceability Matrix is proposed to store relationship information between test cases predetermined scenarios involving a series of specified transactions to test the behavior of one or more software components of the complex software system and or individual components of the complex software system. When a component is modified information in the Automated Multidimensional Traceability Matrix is then accessed to automatically generate a list of test cases that may need to be run to efficiently test the functioning of the complex software system.

According to disclosed embodiments of the invention an improved automated testing framework for complex computer systems is provided. The framework can be configured for test selection flow definition and automated scheduled testing of complex computer systems. The framework has facilities for result analysis comparison of key performance indicators KPI with predefined target values test management and reporting. Through an elaborately developed graphical user interface and wizard the framework readily accommodates changes in the environment of the system to be tested without need for redefining the test flow.

An embodiment of the invention provides a computer implemented method for automatically testing data processing system performance which is carried out using a graphical user interface to establish a configuration of a data processing system to be tested. The configuration includes a network topology and the network elements of the data processing system in the network topology. With the graphical user interface the method includes selecting resources for testing the data processing system defining a testing cycle for the configuration the testing cycle including a series of actions. The method is further carried out by executing the testing cycle using the configuration of the data processing system and automatically controlling the resources to obtain recorded performance indicators of the data processing system automatically analyzing the recorded performance indicators and generating a visual presentation of the performance indicators.

One aspect of the method includes iterating the testing cycle and comparing results of the iterations.

According to yet another aspect of the method executing the testing cycle includes detecting an abnormal condition and responsively thereto performing a predefined sequence of actions.

According to still another aspect of the method the predefined sequence of actions includes a thread dump.

According to an additional aspect of the method defining a testing cycle includes identifying key performance indicators in a key performance indicator description language.

According to one aspect of the method defining a testing cycle includes stating the series of actions in an extendible flow language.

According to aspect of the method establishing a configuration of a data processing system includes automatically mapping machines and server instances participating in a cluster of the data processing system.

Software product and apparatus for carrying out the method are provided in other disclosed embodiments of the invention.

In the following description numerous specific details are set forth in order to provide a thorough understanding of the present invention. It will be apparent to one skilled in the art however that the present invention may be practiced without these specific details. In other instances well known circuits control logic and the details of computer program instructions for conventional algorithms and processes have not been shown in detail in order not to obscure the present invention unnecessarily.

Software programming code which embodies aspects of the present invention is typically maintained in permanent storage such as a computer readable medium. In a client server environment such software programming code may be stored on a client or a server. The software programming code may be embodied on any of a variety of known media for use with a data processing system such as a diskette or hard drive or CD ROM. The code may be distributed on such media or may be distributed to users from the memory or storage of one computer system over a network of some type to other computer systems for use by users of such other systems.

Turning now to the drawings reference is initially made to which is a simplified pictorial diagram of a test framework which is suitable for carrying out aspects of the invention. In a current embodiment the test framework shown below a broken line is implemented on a central web based server . Alternatively the test framework may be implemented as a plurality of computers linked together in a data network. Using the facilities of the system projects can be created and managed in which test suites execute in real time or on schedule to test performance of a complex computer system indicated representatively above the line as a constellation comprising any number of clients and servers all linked together via a data network .

The test framework is programmed with suitable software for carrying out the functions described hereinbelow. Thus although the test framework is shown as comprising a number of separate functional blocks these blocks are not necessarily separate physical entities but rather represent different computing tasks or data objects stored in a memory. These tasks may be carried out in software running on a single processor or on multiple processors. The software may be provided to the processor or processors on tangible media such as CD ROM or non volatile memory. Alternatively or additionally aspects of the test framework may comprise a digital signal processor or hard wired logic.

A block diagram of a software suite is shown which executes in the server . The software suite includes a wizard based project definition module whose function is to allow one or more operators to create and maintain projects to test aspects of the computer system . Interaction between the operator and the software suite occurs via a graphical user interface GUI .

Once projects are created test suites are executed under control of an execution engine . The execution engine may invoke the services of known third party load testing and performance monitoring tools . One of the applications currently included among the tools is Mercury LoadRunner which is a tool for running load tests and analyzing the load results. An analysis module evaluates results of test suite execution. The analysis module may invoke LoadRunner analysis facilities if needed. Additionally or alternatively the analysis module may invoke internally developed analysis modules for analyzing test results e.g. certain memory and error logs which may not be amenable to LoadRunner. The software suite includes an interface with external tools such as LoadRunner.

The projects defined using the test framework are kept in a database such that the project can be rerun whenever relevant environment is modified. The graphical user interface provided in the test framework is flexible enough to easily accommodate such modifications without need for laborious manual reconfiguration of the framework or hard coding new test flows.

A project in the test framework is a basic entity that encompasses a testing scheme a testing cycle results analysis corrective actions and iteration of the cycle until performance is satisfactory. Typically a project applies to a particular configuration of a complex computer system being tested referred to as its system landscape . The system landscape includes the topology of the system e.g. its network addresses and access passwords. The system landscape also includes such system components as servers network elements their capabilities and installed software.

A wizard used by the project definition module produces screen displays that enable the user to establish basic properties of a new project. A project name and description are assigned.

The wizard enables the operator to define a landscape and to select resources to be used to control and evaluate the test flow. One screen display presents a number of machine selections. In a current operating environment the machines are a LoadRunner machine a Quick Test Professional QTP machine a Lightweight Directory Access Protocol LDAP server and application servers. For some cases none of the machines is needed. If a SAP cluster is chosen then at least one SAP central services SCS instance of each cluster should be selected. The rest of the cluster is automatically discovered and configured. Alternatively the user can choose to include Microsoft Internet Information Services IIS as the application server. The wizard enables an automatic presentation of a mapping of the machines and server instances participating in a cluster of interest that is being tested.

Reference is now made to which is a diagram illustrating an exemplary landscape that may be defined using a wizard in accordance with a disclosed embodiment of the invention. A LoadRunner machine is attached as a landscape resource to a cluster as a third party tool. The cluster includes dialog instances a SCS instance and a central instance .

During project definition the user selects key performance indicators typically using the wizard. As explained in further detail below the user selects the actions he wants to perform and builds a flow. Results of the execution of the flow include KPI s that are produced during the run. For each project the user may select a file that includes the KPI s he wishes to include. This file known as a KDL file is described below. The user has the ability to compose multiple KDL files and may choose one of them or may prefer a pre defined KDL file. This choice can be done at any time even after a test has run. Indeed a KDL file can be composed at a later time and applied retroactively. A specialized view known as a KPI view described below may be generated whenever a test is run. This view is derived from test result files.

KPI s available in a current embodiment are presented below in Table 3. The output of the selection step is emitted as a file written in a specialized KPI description language known as KDL an example of which is provided in Computer Program Listing Appendix 2. KDL is an implementation of XML. A schema for KDL is presented in Computer Program Listing Appendix 6. The use of KDL provides convenient editing capabilities. The output constitutes a template that is later loaded by the test framework when a project is executed. In one aspect of the invention KDL files may be managed by users at any time after project definition. Furthermore a project may include many KDL files. Normally one of these is selected for use in a run and is referenced in the project s report file Report.rbl see Computer Program Listing Appendix 3 . KDL files are versatile and can be shared by many projects that deal with the same key performance indicators.

Reference is now made to which is a KDL syntax diagram describing a scheme whereby KPI s are collected in accordance with a disclosed embodiment of the invention.

The wizard offers an option to create a project without a landscape. This option is useful for example if only off line analysis is required e.g. analysis of error or memory logs that are not found on a live system landscape but rather were imported from a remote system for analysis.

As part of the project definition the wizard executes a search to determine available installations in the enterprise. If more than one system is installed the user is invited to select the relevant system on another screen display not shown .

The wizard invites the user to choose the first use for the current project. The following concepts are employed in this phase. An action means a single operation. A step means a sequence of actions. A flow means a sequence of steps and actions. The wizard offers several options for the first use of the project 

 1 A cycle option indicates that a flow i.e. a sequence of steps and actions is to be repeated and the results combined in a regression test which will run in periodically or after each code change.

 2 An investigation option allows failed steps to be identified and rerun without changing any cyclical flows. Results eventually appear in an investigation section of a report.

 3 A single action option allows running only one action rather than a sequence of actions. This option is useful for running designated actions for example analysis of a log or when restarting the entire system landscape. This is also useful for off line analysis.

While the wizard asks the user to select one of the above modes for first use the user may switch to any of the modes during the life of a project as described below.

In projects that involve a cycle the wizard enables the user to define the flow. Reference is now made to which is a screen display produced by a wizard used by the project definition module in accordance with a disclosed embodiment of the invention. A left pane of a dialog box displays a list of predefined steps that are available for selection. Additionally a selection is available for creating user defined steps. On the screen display the selection has been chosen and a smaller dialog box has appeared inviting the user to assign a name for the step that is to be created. The new step has already appeared under its default name on a right pane which is partially obscured by the dialog box .

Once the new step has been created its definition is completed by assignment of actions to be taken. Reference is now made to illustrating a screen display produced by a wizard used by the project definition module in accordance with a disclosed embodiment of the invention. The screen display is similar to the screen display . In the pane there is an expanded actions pool . In the actions pool a predefined step standard MBTF step has been further expanded to display several actions. Some of these have been selected and assigned to a newly created step now named MyFirstStep using a conventional drag and drop technique. For example an action Restart and Clean has been chosen from the pane and appears as a first action of the step in the pane . Another action Backup and Analyze logs has been selected and is discussed below. A detailed description of the predefined actions is presented below in Table 2. In the user has approved his selections and has saved the result as confirmed by a popup display .

The output of the flow wizard is emitted as a document written in a specialized flow language known as Extendible Flow Language XFL . A XFL example is presented in Computer Program Listing Appendix 1. XFL is a specialization of XML. A XML scheme describing XFL is given in Computer Program Listing Appendix 5. Exemplary layout information for a XFL file is given in Computer Program Listing Appendix 7.

XFL has two purposes. First XFL describes the flow of a project. Reference is now made to which is a diagram illustrating a XFL scheme of actions that the test framework is to perform in accordance with a disclosed embodiment of the invention.

Second XFL describes actions available to the test framework . Reference is now made to which is an exemplary diagram showing available actions and indicating logical groups e.g. J2EE actions in accordance with a disclosed embodiment of the invention. A logical group is indicated by a block . In addition predefined steps not shown may be represented.

Referring again to the test framework provides a flow editor via the graphical user interface . Using the editor the user can use drag and drop techniques to move actions from groups or use predefined steps to create a desired flow.

The server includes a server having a file called TC actions.XFL which contains basic actions. These are listed below in Table 2. The file TC actions.XFL can be edited by the administrative operators who can add other XFL files and may also add Perl scripts that implement the actions found in the XFL files. These files are combined to create the actions pool that is displayed in .

KPI s which are disclosed in further detail hereinbelow can be added to Perl scripts by the administrator. This usually results in an API being called that adds KPI s of interest to a result file. Normally such KPI s are also included in a KDL file which is described below.

The follow code fragment is a commented XFL example of an action. Default names in such XFL code are editable by the user.

The wizard then invites the user to assign properties to the new flow. Some options offered are as follows 

 Send email notification when done running for receiving e mail at the end of the each running of a flow Don t overwrite previous results . If not selected each run will overwrite the results of the previous run. Optionally emails may be directed to a user defined distribution list. Links may be included to obtain direct comparison with a selected number of previous results.

Continuing to refer to the execution engine scans an internal database and determines that a project is scheduled to run. It then creates an instance of a scenario object implemented by a module scenario.pm which based on the information created using the wizard defines the landscape and conditions on which the test is to be run. The execution engine then dynamically creates a Perl script dynamicscript.pl which actually runs the flow on the defined landscape and under the conditions defined. Because the script dynamicscript.pl is generated dynamically some changes in the environment that may have occurred between runs are automatically accommodated.

Execution of a project by the execution engine is accompanied by the generation of a report. The test framework provides a screen display illustrating summary results of a project run. It is possible to observe in detail the history and analysis of the flow for example the fact that particular steps of the flow were successfully executed. An option to invoke the analysis module to analyze results such as LoadRunner results is discussed below.

Many useful views of data measured during a project run are generated by the test framework . Reference is now made to which is a screen display illustrating a collection of key performance indicators that were measured during a project run in accordance with a disclosed embodiment of the invention. An entry indicates the average transaction response time of different user dialog steps simulated by LoadRunner. also illustrates another feature of the test framework namely the capability for the user to change modes of operation. It will be recalled that a project can be operated in a cyclical mode an investigative mode and a single action mode. Any of these modes can be enabled by respectively selecting a cycle tab an investigation tab or a single action tab .

Data from different runs may be compared. Reference is now made to which is a screen display in which aspects of two runs of the same project are presented in a side by side comparison in accordance with a disclosed embodiment of the invention. A key performance indicator minor garbage collection GC out of total time has been selected. A bar graph and a bar graph show values of the performance indicator that were observed during performances on Jul. 4 2006 and Jul. 19 2006 respectively.

When a flow is executed a result folder is created. This contains all the logs and reports that were generated and collected during the run e.g. J2EE logs LoadRunner LR reports and other analyses.

The test framework provides a scheduler for executing a project run at a future time or repeatedly at intervals.

An option Action Backup and Analyze Logs not shown is available. This option allows the user to view a detailed analysis of the logs produced on the landscape during the current run. It is also possible to view the detailed messages e.g. errors and exceptions. Original log files may be conveniently accessed using links.

From the actions pool the user may select an option Run Monitored LoadRunner not shown . The user is generally required to supply a LoadRunner scenario. The test framework automatically modifies the scripts of the LoadRunner scenario so that periodically during the run LoadRunner reports current response times and the number of failed transactions to the server .

When a combination of failed transaction and response time exceeds a predefined limit an impending crash situation is identified. The test framework responsively generates thread dumps and backs up the server logs and garbage collection logs of the affected server all automatically and just prior to an actual crash.

A summary crash detection report occurring during an execution of a project in a monitored mode is available in which certain configuration information regarding the crash detector and information concerning crashes are displayed. Links to a full report are provided.

Additionally or alternatively using the crash detection facility a thread dump interval can be set. Thread dumps are descriptions of thread actions in a running Java Virtual Machine JVM . Using a built in API of the J2EE engine the test framework produces the thread dumps which can later be analyzed in order to detect abnormal conditions in the JVM.

In one aspect of the invention the test framework harnesses the facilities of third party tools e.g. LoadRunner which is adapted to performance analysis. If an option is selected LoadRunner results of a project run relating to transaction response time are imported and summarized. It is possible to access the original LoadRunner Report which may contain information that is more detailed.

As another example or performance analysis the test framework can organize and present memory utilization data that were measured during a project run. An option Action Backup and Analyze GC Logs not shown is available. Selection of this option enables aspects of memory behavior during the project run to be viewed.

Reference is now made to which is a screen display that presents garbage collection activity occurring during an execution of a project in accordance with a disclosed embodiment of the invention. Assume that the landscape configuration chosen for the project includes one or more application servers that handle client requests and a dispatcher server that dispatches client requests to the application servers. This configuration is used for example in versions of the J2EE engine. The screen display presents series of three graphs for an application server. Although not shown on the screen display respective series of graphs are displayable for each application server in the system being evaluated.

Leftmost graphs in the series present heap size plotted against elapsed time during the run. This graph presents two states of the heap before and after garbage collection. This graph may display problematic memory behavior that can lead to an out of memory crash. Observation of an unchanged heap size before and after garbage collection or observation of a constantly increasing heap size over time are other indications of memory allocation problems. It should be noted that this memory analysis is the result of the action Backup and Analyze GC Logs which was included in the flow that produced the results shown in . If a crash protect option is selected the analysis is performed automatically upon detection of a system crash.

Center graphs display garbage collection duration These are composite displays in which minor garbage collection and full garbage collection data appear as bands respectively. The graphs are interpreted by correlation with corresponding rightmost graphs which display recycled bytes. In the graphs recycled byte data from minor garbage collection and full garbage collection appear as bands respectively. The series is similar. In general the more recycled bytes the longer the garbage collection duration. The finding of a small number of recycled bytes when the system is under memory load may be an indication of malfunctioning garbage collection which may lead to an out of memory crash.

While not shown in another performance indicator that can be displayed is the total response time during browser navigation during the test. This performance indicator is a KPI that can be extracted from LoadRunner results. It is one of the most important as it closely relates to user satisfaction.

The test framework is also capable or reporting garbage collection data and statistics in tabular form both for a cluster globally and per server node.

The use of class histograms is a useful way to monitor memory consumption of classes. Memory consumption for every class in use may be presented on a class histogram upon a thread dump. The histograms resulting from different thread dumps may be compared thereby following memory behavior for every class. Using this facility memory leaks can be localized to specific classes. Class histograms are produced by the test framework using a built in API of the J2EE server and are analyzed by the analysis module . This aspect of the analysis is a result of an action Analyze Class Histogram not shown selected from the actions pool .

Reference is now made to which is a screen display that presents a series of several class histogram produced during execution of a project in accordance with a disclosed embodiment of the invention. The memory usage of three suspect classes is indicated by lines at different times during a project run. A generally increasing memory usage is observed for each of these classes.

In the course of operation a number of separately obtained results are more conveniently presented together. The test framework provides a Merge Results feature that enables different steps to be consolidated on one result line.

Reference is now made to which is a screen display showing details of four project runs in accordance with a disclosed embodiment of the invention. The screen display further indicates a user selection of a portion of the results of different runs. Results indicated as skipped were not selected. All other results were selected. The selected results are then presented in tables or graphs with comparisons as appropriate. For example results corresponding to a box portal scalability have been selected from two runs indicated by columns and shown by boxes respectively. These results are typically presented together in a graph or table.

Reference is now made to which is a flow chart of a method for evaluating the performance of complex software systems in accordance with a disclosed embodiment of the invention. At initial step definition of a new project is initiated typically using the services of a wizard or similar program.

Next at step the configuration of the data processing system to be tested is determined. This involves defining the network topology of and selecting network elements of the data processing system in the network topology. These elements may include servers client work groups and network routine elements. Essentially this step is a definition of the system landscape.

Next at step resources required to execute the test cycle are selected. Various third party tools such as the above noted LoadRunner performance tool may be recruited for use.

Next at step test flow e.g. a sequence of actions are chosen. These actions may control the resources selected in step as well as the elements chosen in step . Scheduling issues are typically addressed at this step. For example the test cycle may be automatically iterated at predefined intervals.

Next at step the performance test is executed one or more times. Performance indicators are recorded as described above.

Next at step the recorded performance indicators are analyzed. Visual presentations e.g. tables and histograms are prepared.

At final step the data prepared in step is evaluated by a human operator. Corrective action is initiated as required.

Computer Program Listing Appendix 1 is an example of a flow created by a user using an extended flow language which is an extension of XML. Key performance indicators of interest defined by the user are stored in a KDL file an example of which is presented in Computer Program Listing Appendix 2. This file contains KPI descriptions ranges and degradation conditions. Computer Program Listing Appendix 3 contains a file in which KPI s to be included in reports are set by the user. Computer Program Listing Appendix 4 is an exemplary result file.

It will be appreciated by persons skilled in the art that the present invention is not limited to what has been particularly shown and described hereinabove. Rather the scope of the present invention includes both combinations and sub combinations of the various features described hereinabove as well as variations and modifications thereof that are not in the prior art which would occur to persons skilled in the art upon reading the foregoing description.

