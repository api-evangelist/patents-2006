---

title: Measuring quality of software modularization
abstract: Quality of modularization of source code is tested using different perspectives such as a structural modularity perspective, an architectural modularity perspective, a size perspective, and a similarity of purpose perspective. A history of changes in modularization may be kept such that the degree to which given source code is well-modularized can be determined over time. The changes made to the code by individual programmers may be kept, such that the degree to which their coding enhanced or harmed modularization may be tracked.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08146058&OS=08146058&RS=08146058
owner: Infosys Limited
number: 08146058
owner_city: Bangalore
owner_country: IN
publication_date: 20061215
---
This application is a continuation of Sarkar et al. U.S. application Ser. No. 11 610 442 filed Dec. 13 2006 entitled EVALUATING PROGRAMMER EFFICIENCY IN MAINTAINING SOFTWARE SYSTEMS which is incorporated by reference herein.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by any one of the patent disclosure as it appears in the United States Patent and Trademark Office patent files or records but otherwise reserves all copyright rights whatsoever. Portions copyright IEEE IEEE Transactions on Software Engineering 2007 used with permission.

The field relates generally to developing metrics to determine software quality. More particularly the field relates to metrics developed to determine level of modularization of a software program.

Large software systems are generally developed systematically using structured development methodology. One common aspect is to organize the software into logical modules. Modules ideally are logical groupings of functions and related data structures that together offer a well defined service. Correct module use promotes encapsulation. That is implementation details are hidden and interaction details with other modules and the rest of the world are consistently implemented through a set of published application programming interface API functions.

Modules themselves may be organized in layers. Layers typically are organized hierarchically such that modules in a given layer are only allowed to call modules in lower layers. Systems which are well modularized and which use layers properly are easier to understand as each change to the system only affects a small portion of the overall system. Thus changes have less overall effect. For example it takes less time to add new functionality change existing functionality and test and release the resulting modified modules even by those who are not conversant with the software.

Various measures of modularization have been proposed to determine modularization quality such as cohesion metrics coupling metrics and combined cohesion coupling metrics. Cohesion measures how self contained code is that is how well the code in a module works together to provide a specific piece of functionality without the need for assistance from other modules. For example cohesion can be measured as the ratio of the number of internal function call dependencies that actually exist to the maximum possible internal dependencies.

Coupling measures the dependency of different code groupings that is within a module to what degree changes in one function may affect other. Low coupling usually implies high cohesion and vice versa. Ideally modules should have high cohesion be self contained and low coupling be relatively independent of other modules. 

One common metric Modularization Quality MQ is a combined cohesion coupling metric and is calculated as the difference between the average cohesion and the average coupling.

Variations on the MQ which have been developed include a modified MQ which is the sum of modularization factors MF for clusters. For a given cluster MF can be calculated as

Metrics have also been derived from a relational graph representation of software artifacts such as functions data types variable etc. Relations such as function call dependencies type declaration of variables macro definitions and so on are mapped between modules. This class of metrics measures the degree of association between a module and other modules.

Other metrics include measures of how many methods are packed into classes the depth of inheritance trees inheritance fan out and measures of the degree of couplings between objects where couplings are created by one object invoking a method on another object.

Tools which have been developed for software clustering have also albeit indirectly proposed modularization metrics. Software clustering tools may be used to determine or more usually recover the underlying architecture of a software system after some catastrophic event. These tools attempt to partition a software system into logical cohesive subsystems. For example automated software partitioning tools have been developed which quantitatively characterize modules by the degree to which the functions packaged within the same module contain shared information such as by determining the degree of commonality of the names of data objects within the functions. Modules can also be characterized on the basis of function call dependencies such that if a function A calls a function B then functions A and B are presumed to belong to the same module. Other metrics have also been proposed. These include quantitatively characterizing the degree to which functions packaged within the same module contain shared information. Functions may share information for example on the commonality of the names of data objects.

Structural information such as shared name substrings for functions and variables function call dependencies and so on can also be used to determine modularization. Another approach is to try to isolate omnipresent objects which are heavily used object and functions. Analyses such as those described earlier relating to cohesion and coupling are then performed. This is done with the belief that omnipresent objects unless specially categorized distort the coupling cohesion analysis.

However these complexity metrics do not analyze the software from a coherent set of perspectives that together give an overall impression of how well the system is modularized from a variety of perspectives. That is they do not analyze a system at large in terms of their modules the cohesiveness of the modules the interactions between modules and how well the system has been divided into layers super modules. Furthermore even the best designed system can have its modularity degrade as the system ages and is maintained.

Even though a legacy application development can begin as a well modularized system with a layered architecture it gradually degrades over a period of time as the system is maintained. The degradation in modularity can happen due to ad hoc bug fixes and enhancements which disregard modularity design principles such as have been discussed. Such degradation in modularity can cause a formerly robust system to become rigid and fragile.

In such a scenario a manager who has responsibility for maintenance and enhancement of a legacy application is not in a position to take appropriate corrective measures in spite of realizing the gradual degradation of the maintainability of the system if he or she has no way to accurately measure the type and location of the degradation or who specifically is causing the degradation. Because there is currently no good way to measure this degradation there is similarly no good way to determine when the degradation occurs or who or what is the likely cause of such degradation.

As the deterioration of modularity is not recognized there is no reason for programmers unaware of the problem to concentrate on fixing the problem. Furthermore there is no way to measure how well an individual programmer may be preserving or degrading the modularity of the system.

Thus there is a need for systems and methods to measure system modularity that is modularization quality.

In an exemplary embodiment a modularization evaluator may be used to determine the quality and or the degree of modularization of a portion of software source code. This modularization evaluator may have a number of modules.

Modularization quality of modules may be evaluated using a structural modularity perspective which measures function call traffic through an Applications Programming Interface API of at least one module. This metric may be calculated by one or more of the following indices a model interaction index an implicit dependency index a non API function closedness index and an API function usage index.

Modularization quality of modules may be evaluated using an architectural modularity perspective that measures organization of modules into hierarchical partitions. This metric may be calculated by one or more of the following indices a layer organization index a cyclic dependency index a model interaction stability index and a testability index.

Modularization quality of modules may be evaluated using a size perspective that measures uniformity of module sizes in relation to total size of the source code and which may have one or more of the following indices a module size uniformity index and a module size boundedness index.

Modularization quality of modules may be evaluated using a similarity of purpose perspective that measures similarity of purpose of groupings within the source code and which may have one or more of the following indices a concept domination metric and a coherency metric.

A history of changes in modularization as reflected in the source code may be kept such that the degree to which given source code is well modularized can be determined over time. The changes made to the code by individual programmers may be kept such that the degree to which their coding enhanced or harmed modularization may be tracked.

The foregoing and other objects features and advantages of the invention will become more apparent from the following detailed description which proceeds with reference to the accompanying figures.

The technologies described herein can be used in any of a variety of scenarios in which accurate determination of modularization of a software system or a portion of a software system is useful. For example owners of software systems consisting of legacy code which may consist of a million lines or more may need to know whether the code should be automatically or semi automatically modularized. To make this determination the current degree of modularization must be understood. Furthermore once such code is modularized the success of the modularization can be determined by applying any of the techniques taught herein.

As another example a company wishing to maintain existing code with a high degree of modularization can use the systems and methods herein to measure the quality of code at different times and thus take steps to ensure that the code s modularization does not degrade over time.

As a further example a company can track the changes made by specific programmers to code which may be legacy code and by applying the modularization metrics taught herein can determine the degree to which various programmers inadvertently introduced changes into the given body of software that has led to deterioration of the system modularity.

Source code includes any computer programming files that are human readable but that can be converted to machine readable form. The type of source code used is not a limitation on the embodiments described herein. For example and without limitation the source code can be written in one or more than one programming languages thousands of which exist. Examples of possible source code programming languages include but are not limited to COBOL C C and Java.

A module is a logically cohesive unit of code. This may include files functions data structures variables and the like. For example it may be a group of related classes in object oriented programming may be substantially all the code in a single file may be a group of related files or the modules may be organized in a different fashion.

The word function here indicates any software grouping with input output functions such that procedures subprograms etc. are included.

At source code e.g. the source code of representing at least a portion of a software program is received. At the modularization of the source code is evaluated. As described in the examples modularization can be evaluated by a variety of metrics including but not limited to coupling based structural metrics size based metrics architectural metrics metrics based on similarity of purpose and the individual metrics contained therein.

At the results e.g. the modularization quality evaluation results of the evaluation of the modularization of the source code is generated using the output of the source code evaluation .

In any of the examples herein the exemplary modularization quality evaluation results can comprise any one or more of the modularization metrics described herein.

The degree and quality of modularization can be observed from various perspectives which guide but do not drive the specifics of the various modularization metrics. Each of the modularization metrics embodiments discussed in any of the examples may incorporate one or more of the following modularization principles discussed below.

A module ideally groups a set of data structures and functions that together offer a well defined service similarity of purpose. The following principles can be used to determine if individual modules have a similar purpose 

Encapsulating the implementation code of a module and requiring that the external world interact with the module through its published API s is a widely accepted design practice. The following modularization principles can be used to capture these notions 

One of the most significant reasons for object oriented software development is that the classes subclassing can be easily extended whenever one desires a more specialized functionality. Extending object oriented software through the notion of subclassing allows for a more organized approach to software development and maintenance since it allows for easier demarcation of code authorship and responsibility. While module level compartmentalization of code does not lend itself to the types of software extension rules that are easy to enforce in object oriented approaches one nonetheless wishes for the modules to exhibit similar properties when it comes to code extension and enhancement. The following principle captures these aspects of code modularization 

Testing is a major part of software development. A common form of testing requirements based testing ensures that at a minimum the software conforms to chosen standards and protocols. Testing must also ensure that the software behaves as expected for a full range of inputs both correct and incorrect from users and processes at the level of program logic in the individual functions and at the module interaction level. Furthermore testing must take into account the full range of competencies of other agents that are allowed to interact with the software. Testing procedures can easily run into combinatorial problems when modules cannot be tested independently. For example if each module is to be tested for N inputs the two interdependent modules must be tested for Ninputs. Modularization must therefore strive to fulfill the following principle 

Cyclic dependencies between modules of a body of software should be minimized. Cyclic dependencies exist when two or more modules depend on each other. This leads to combinatorial problems when testing difficulty in testing modules separately and most troublingly the requirement that modules must be aware of the evolution of internal details of other modules defeating the purpose of modularity. Cyclic dependencies becomes even more of a problem when modules are organized in horizontal layers as often happens in reasonably sized reasonably designed software systems. Layering serves an important organizational function modules in one layer can optimally only seek the services of the layers below it. When modules in one layer require the services of higher layers as indicated by cyclic dependencies the purpose of layering is defeated. Therefore modularization should follow the principle 

It is believed that modules of a large software system should be roughly the same size. As is intuitively plausible the number of defects in a module goes up with the size of the module. But counterintuitively the overall number of defects in a large software system also rises when the individual modules are too small. Therefore modularization should follow the principles 

The modularization metrics embodiments taught herein relate to at least one of the principles enumerated in this example.

Modern software engineering dictates that software should generally be organized along a set of modules. One way of thinking about modules is that they capture a set of design decisions which are hidden from other modules. Furthermore the interaction between modules should primarily be through module interfaces. A module can also be thought of as grouping a set of functions and data structures. This often leads to a specific module implementing one or more business concepts. This grouping may take place for example on the basis of similarity of purpose or on the basis of commonality of goal. The difference between the two is subtle but important. As example of a module that represents the first type of grouping is the java.util package of the Java platform. The different classes of this package provide different types of containers for storing and manipulating objects. A module such as the java.net package is designed to provide support for networking commonality of goal. The asymmetry between modules may be exemplified by the fact that you are likely to use a java.util class in a java.net based program but much less likely to do so the other way around.

In either case modules promote encapsulation information hiding by separating the module s interface from its implementation. The module interface expresses the elements that are provided by the module for use by other modules. In a well organized system the interface elements are visible to other modules while the implementation hidden from other modules contains the working code that corresponds to the elements declared in the interface. Such a module interface is known as its Application Programming Interface API . It is widely accepted that the overall quality of software is generally enhanced when interactions between modules are restricted to take place through the published API s for the module.

The architectural description of the source code is a description of how the source code is partitioned into modules that is what portion of the code belongs to which module. This description may also include a description of how the modules are organized into layers. This organization description may be in the form of original design documents or the organization description may be built into the source code itself in which case there are markers of some kind in the code that indicate which portions of the code belong to which modules and to which layers. Modularization of code may be determined by someone of skill in the art and may be entered by hand either in part or for the entire system being evaluated into a user interface of the modularization evaluator. The architectural description may be derived from modularization results received from an automatic modularizer in which case the output of the automatic modularizer is used either as is or converted to a form that the modularization evaluator can read.

In any of the examples herein describing evaluating source code a model of the source code can be evaluated instead of or in addition to the source code. shows an exemplary system to evaluate modularization quality of the source code using a model of the source code. Source code e.g. the source code of is received. A source code model extractor parses the source code and derives a high level model of the source code . This high level model can be used for the source code in any of the examples given herein.

The high level model can comprise file information function information function dependency information global variable information data structure information dependency between global variables and functions data structures and functions and other programming constructs. In one embodiment the source code information is stored in an SQL Structured Query Language database.

Source code e.g. the source code of is received. This source code is used as input for any of the evaluators shown.

The structural perspective modularity evaluator evaluates the source code from a coupling based structural perspective that provides various measures of the function call traffic through the API s of the modules in relation to the overall function call traffic producing modularization quality evaluation results .

The architectural perspective modularity evaluator evaluates the source code by determining how well modules within the source code are organized into higher level structures with an emphasis on the horizontally layered structures. The architectural perspective modularity evaluator produces modularization quality evaluation results .

The similarity of purpose modularity evaluator evaluates the source code based on clues provided within the source code on the purposes of the modules and their constituent parts. In software it is frequently the case that either the name of a function the names of variables within a function words within the comments of a function etc. hold some clue as to the purpose of the function inside the module and to the purpose of the module itself. The developers of complex software often leave behind clues as they name variables comment code write debugging routines and the like. These clues can be thought of as concepts. For example given the case of a module devoted to interest calculations in banking software a concept might be the word interest which is likely to show up in various artifacts of the module either in its full or an abbreviated form. With regard to software characterization such concepts may then be used by the similarity of purpose modularity evaluator to assess whether or not the software adheres to the principles that are based on the semantics of the module contents. The similarity of purpose modularity evaluator produces modularization quality evaluation results .

The size perspective modularity evaluator evaluates whether the modules within the software code are approximately equal in size and whether the average module size is appropriate for the software code as a whole. The size perspective modularity evaluator produces modularization quality evaluation results .

At modularization quality is evaluated via a structural perspective. At modularization quality is evaluated via an architectural perspective. At modularization quality is evaluated via a testability perspective. At modularization quality is evaluated via a size perspective. At modularization quality results are generated based on the one or more perspective evaluations.

Any of the modularization indices discussed for example in connection with example 8 may be used for the evaluation by the modularization results evaluator . This metric index may be any number at any scale. A metric index normalizer then normalizes the metric index to produce a normalized index such that its value lies between 0 and 1 with 0 being the lowest worst score poor modularization and 1 indicating the highest score possible the best possible modularization. The normalized index can then be used as the entire or as a portion of any of the modularization quality evaluation results described herein such as the modularization quality evaluation results .

In any of the examples herein normalization can normalize an index so that it falls within a range e.g. 0 1 0 11 and the like .

If M denotes a set of elements M denotes its cardinality that is the total count of the elements in the set.

All of the functions in S will be denoted by the set F . . . . These are assumed to be distributed over the M modules.

K denotes the total number of calls made to a function belonging to a module m. Of these K denotes the number of calls arriving from other modules and K indicates the number of calls from within the same modules. It follows therefore that K K K .

K m denotes the total number of external function calls made to the module m. If m has . . . functions then

In any of the examples herein API functions as opposed to non API functions can be identified using the heuristic that an ideal API function is called generally by functions belonging to other modules. Similarly an ideal non API function is never exposed that is it is never called by functions from other modules. Using this heuristic a function can be declared to be API or non API depending on the relative frequency of the function being called from other modules versus the frequency the function is called by its home module. Two threshold parameters and are defined. For a function f in a module m having K f number of calls made to it where K f are the external calls made to it and K f are the internal calls made to it. If K f K f f is considered to be an API function for m. Similarly a function f in the module m is treated as a non API function if K f K f .

It should be noted that each of the structural indices and are expressed as normalized values with the worst value being 0 and the highest being 1. Other equally valid indices with a different range of values are also envisioned following the teachings here.

The module interaction index abbreviated MII calculates how effectively a module s API functions have been used by the other modules in the system. The total number of function calls or close to the total made through modules is calculated. This can be calculated in any fashion as known to someone of skill in the art. The total number of API functions made through modules is also calculated.

Assume that a module m has n functions . . . out of which there are n1 API functions . . . . Also assume that the system S has m. . . mmodules. Then the model interaction index MII for modules calculated becomes the total number of function calls made through the API in the module as calculated divided by the total number of function calls made in any fashion within the module as calculated. Expressed using the notation described in example 12 this becomes 

For the entire system the MII is the sum of individual MII module values divided by the total number of modules or 

As an alternative formulation of the module interaction index K and K can be calculated as a weighted sum of the number of times the function and are called externally. For example if a function in a module m is called 5 times from module mand 7 times from module m rather than K 5 1 as in the previous calculation K w 5 w 7 . Each module would be weighted depending on its relative importance with relation to module m. The weights generally would be values between 0 and 1. If both weights equal 1 the formula reduces to the previous version of MII. Similarly MII S can be a simple average a weighted average a median value etc.

The module interaction index measures if a given software system adheres to the module encapsulation principle discussed with reference to example 3. Recall that this principle suggests that a well designed module should expose a set of API functions through which other modules would interact. The API functions can be thought of as the service that the module has to offer. Since these API functions are meant to be used by the other modules the internal functions of a module typically do not call API functions of the module. Therefore to the maximum extent possible a non API function of a module should not receive any external calls.

Certain types of modules such as driver modules are used in some systems to orchestrate the other modules. For these driver modules MII m may be very close to 0. In such cases it should still be understood that the overall goal of a modularization effort should be to achieve a large MII for those modules in which such a measurement makes sense.

The implicit dependency index abbreviated IDI measures the number of functions that write to global entities in modules other than the ones they reside in. An insidious form of dependency between modules comes into existence when a function in one module writes to a global variable that is read by a function in another module. The same dependence occurs when a function in one module writes to a file whose contents are important to the execution of another function in a different module such as when modules interact with one another through shared database files. Such dependencies can be thought of as implicit dependencies.

Detecting implicit dependencies often requires a dynamic runtime usage scenario analysis of the software. Such analysis is both time consuming and difficult and becomes more so the larger the size of the system under consideration. An easier metric is proposed here. The Implicit Dependency Index IDI is constructed by recording for modules the number of functions that write to global entities such as variables files databases when the global entities are also accessed by functions in other modules. This is done on the belief that the larger this count is in relation to the total inter module traffic the more implicit dependencies exist.

To calculate the IDI some new notation must first be defined. D m m i j denotes the number of dependencies created when a function in mwrites to a global entity that is subsequently accessed by some function in m. Let D m m i j denote the number of explicit calls made by functions in mto functions in m. C m is the set of modules that depend on mby having at least one implicit dependency. This metric assumes that the larger Dis in relation to D the worse the modularization of the software. The metric IDI is defined as follows 

As an alternative formulation of APIU m modules m C m that have indirect dependencies with m can be weighted. Using the same notation as the previous metrics IDI m can be generalized as 

With regard to where this metric belongs in the landscape of principles presented in example 3 ideally all interaction between modules should be through published API functions implying that the number of implicit dependencies must be few and far between. Therefore in an ideal API based system the IDI would be equal to one. This is in conformance with the principle of module encapsulation which requires a minimum of such implicit non API based communications.

The non API function closedness index abbreviated NC calculates how effectively a module s non API functions are used. Ideally the non API functions of a module should not bypass the API that is they should not expose themselves to the external world. In reality however a module may exist in a semi modularized state where inter module calls are made outside the APIs. This is especially true in large legacy systems that have been only partially modularized. In this intermediate state functions may exist that participate both in inter module and intra module call traffic. The extent of this traffic is measured using the non API function closedness index .

Extending the notation presented in example 13 let Frepresent the set of functions within a module m Frepresent the set of API functions within module m and Frepresent the non API functions within module m. Ideally F F F. However it is difficult enough to categorize a function with enough particularity to determine whether it is an API function or a non API function so it is understood that the theoretical ideal will most likely not be met.

In any case NC is measured for a specific module by dividing the number of non API functions by the sum of the total number of functions minus the API functions. In the notation we have defined this becomes 

For the system NC the index is the total of the individual module indices divided by the total number of modules or 

As an alternative formulation of NC m user defined weights can be introduced for each or some of the sets of functions such that 

Similarly NC s can be calculated as a simple average as is shown above a weighted average a median value etc.

As a well designed module does not expose the non API functions to the external world and assuming we correctly categorize functions as either API functions or non API functions F Fshould be equal to F. Therefore NC m 1 for an ideal module with NC m 0 for a module where non API functions are exposed.

The API function usage index abbreviated APIU determines what fraction of the API functions exposed by a module are being used by the other modules. When a big monolithic module presents a large and versatile collection of API functions offering many different services any one of the modules with which it interfaces may need only a fraction of its services. That is any single module interacts with it may only use a small portion of its API. This indicates improper module design and suggests that the module does not have a coherent purpose. It is considered a better design for such modules to be split into smaller or at least different modules which offers a set of services the bulk of which will be used by most of the modules that access it.

To calculate this metric suppose that m has n API functions and that nnumber of the API functions are called by a module m. Also suppose that there are k modules m. . . mthat call one or more of the API function of module m. The APIU for a single module is equal to the sum of the number of API functions in m called by each module that interfaces with m divided by the quantity equal to the total number of modules that interface with m multiplied by the number of functions in m Mathematically this can be written as 

It can be seen that APIU m equals 0 if m has no API functions or if there are no other modules that interact with m.

The APIU of a system S is the sum of the APIU s of individual modules divided by the number of modules with a non zero number of APIU functions which can be expressed as 

As an alternative formulation of APIU m each module m. . . mwhich calls one or more of the API function of module m may be assigned an importance for their interaction with m. This importance is modeled as w m and can be a number between 0 and 1. The alternate formula for APIU m then becomes 

When the weights are equal to 1 the formula reduces to the previous version of APIU. Furthermore APIU S can be processed a simple average as shown above a weighted average a median value etc.

This metric characterizes the software albeit indirectly and partially in accordance with the similarity of purpose principles. For example maximizing module coherence on the basis of commonality of goals requires that the modules not be monolithic pieces of code which provide disparate services. Making modules focused with regard to the nature of their services should push the APIU metric at least closer to its maximum value 1. However it should be noted that this metric does not actually analyze the specificity of the API functions but is merely an artifact that occurs when such specificity exists. Therefore this APIU metric can be considered in conjunction with the other metrics for its full benefit.

At module interaction is calculated. This can produce a module interaction index . In an exemplary embodiment to calculate the module interaction index for each module the total number of external function calls made through APIs for that specific module are calculated. Also the total number of external calls to each module is calculated. At results can be generated using the module interaction index .

At the implicit dependency of a module is calculated. This can produce an implicit dependency index .

At the non API function closedness index is calculated. This can produce a non API function closedness index .

At after one or more structural performance module evaluations have been calculated results can be generated from the one or more calculated indices.

Architecture here can mean an organization of modules into higher level structures especially the horizontally layered structures. Generally good software design requires that modules in any one layer are only allowed to call modules in layers below them. This keeps the lower modules which should have more basic functionality more stable with respect to any future changes. However imposing or preserving such layering on modules is complicated by the presence of cyclic dependencies between modules. The metrics here relate the layered organization of modules in the presence of possible cyclic dependencies.

It should be noted that each of the architectural modularity indices and are expressed as normalized values with the worst value being 0 and the highest being 1. Other equally valid indices with a different range of values are also envisioned following the teachings here.

The Cyclic Dependency Index abbreviated Cyclic measures the extent of cyclic dependencies between the modules of a system. This metric is based on the notion of strongly connected components abbreviated SCC in a directed module dependency graph MDG where M represents the nodes corresponding to the modules and E represents the arcs between nodes indicating pairwise dependencies between modules. An arc connecting two nodes indicates that the two modules corresponding to the nodes are either explicitly or implicitly dependent on each other. As mentioned with reference to the implicit dependency index discussed with reference to example 15 implicit dependencies come into play when a function in one module calls a function in another module. Implicit dependencies appear through shared global variables such as when a function in one module writes into a file that is read by another module.

An SCC in the graph MDG is a maximal set of vertices i.e. modules in which there exists a path from all or substantially all vertices in the SCC set to all or substantially all other vertices in the same set. With this definition the SCC has the property of being able to capture multiple cycles. Thus an SCC of 1 indicates the maximum number of cycles in that nodes modules are connected. As the number of cyclic dependencies decrease the SCC increases with the maximum value being the number of modules being measured. This is because an SCC has the property that if the module dependency graph MDG contains no cycles then the number of strongly connected components SCC is exactly equal to the number of nodes modules in the graph. In such a case for every SCC SCC 1.

A cyclic dependency metric can now be formed by comparing the sum of the cardinalities of SCC s with cardinality of the module dependency graph itself as shown below 

This metric is aligned with the principle minimization of cyclic dependencies among modules. The value of Cyclic M equals 1 for a system having no cycles with the value of a system where every module is connected to every other module being 1 divided by the number of modules.

The layer organization index abbreviated LOI measures how well the layers only call modules from layers at the same level or below them. A layer can be thought of as a horizontal partitioning of a system. There are generally two types of layering. The first type of layering is closed. Here a function in layer Lcan only make calls to the functions in the immediately lower layer L. The second type of layering is open. With it a function in layer Lcan make calls to functions in any lower layer.

Calculating the layer organization index can be performed as follows. Suppose that L denotes an assignment of a set of modules M to a set of layers L. . . L where Lis the first layer Lthe second etc. in which modules have been organized. Thus L m is the layer where m resides. The notation indicates that calls from possible layers are considered except for the layer L. K m denotes the number of external calls made to a module m residing in layer L from modules residing in layers other than L. Let K m be the number of external calls made to a module m residing in layer L from the modules in the immediate upper layer L.

The Layer Organization Index LOI for the layer Lis defined as the number of calls to modules in the layer Lfrom the immediate upper layer divided by total number of calls to the modules in the layer excluding inter layer calls. This can be written as 

The above metric will now be extended to the entire system. When measuring the system level metric the cycles that exist among the modules and the cycles that exist across layers are explicitly addressed. Often peer modules collaborate heavily among themselves to perform a complex business workflow. Such collaboration can result in cycles. Such cycles among peer modules are generally acceptable when and only when all such modules are in the same layer. It is not acceptable but rather is highly undesirable for such modules to engage in cyclic dependencies across a layer violating the layering principle.

The LOI metric presented next is forgiving of cyclic dependencies within a given layer but penalizes any cyclic dependencies across layers. Let us assume that the system consists of q number of strongly connected components SCCs where number of modules in an SCC is 1 i.e. SCC 1 which indicates that cyclic dependencies exist between modules in different layers. When the module graph is acyclic q M that is every module has its own independent SCC. Conversely when the module graph is completely cyclic q 1 as only a single SCC is needed as it contains every module.

Next let L SCC be the set of layers which have dependencies in SCC. That is a module in a Layer L is a node in SCC. This can be written L SCC L m m SCC. As discussed earlier cyclic dependencies can exist within modules of the same layer that is L SCC 1 but the opposite case where cycles are formed by modules in multiple layers i.e. L SCC 1 is heavily discouraged. The following index calculation the Desirability Property Formula returns an index which measures the amount of cycles formed by modules in multiple layers where p is the number of layers in the system and where M 1 is the total number of modules in the system organized in p layers.

When the module dependency graph is acyclic SCC 1 for each i and q the total number of modules such that after summation of the formula above the divisor equals 0 which yields the best result 1.

At the other extreme when the module dependency graph is completely cyclic such that all M modules distributed in p layers exist in one SCC. In such a case SCC 1 M 1 with q 1. Thus the formula equals 0 the worst possible result. It should be noted that the normalization of the formula done here is an exemplary embodiment with possible best and worst results falling into different ranges.

Also observe that the value of the formula decreases as more layers participate in each cycle as the value SCCi is raised exponentially by the number of layers in its cycle.

Observe that the system level LOI is impacted both by inter layer calls and by the number of layers within each SCC that is how many layers participate in each cycle.

Also as another alternate formulation the system level LOI can be weighted such that wand ware any two user defined numbers whose values add up to 1. This gives the following formula 

This metric models and attempts to maximize the unidirectionality of control flow in layered architectures and also strongly penalizes cycles across multiple layers. Therefore the metric LOI conforms to the acyclic dependency principle.

The module interaction stability index abbreviated MISI is designed to measure the degree to which modules in lower layers are more stable than modules in upper layers.

Software of any serious complexity is often ordered at a minimum into layers. In such architectures the modules in the lower layers should be more stable than the modules in the upper layers such that the most changes made to the overall software should be ideally in the upper layers with the fewest changes in the lowest layers. This means among other things that changes to the upper layers should not impact the lower layers.

However measuring such characteristics is challenging as it is difficult to anticipate when and to what degree a given module will be changed as such changes often depend on unpredictable external situations such as market pressure and customer requests. Therefore the module interaction stability index measures not the degree to which modules change but rather the degree to which a change in a given module will affect the surrounding modules.

Following the notation already developed within this example let L M L1 . . . Lp be the assignment of the modules to different layers and L m be the layer where module m resides. In the stack of layers let Land Lbe the uppermost and lowermost layers respectively. The layers are now rank ordered with the operator defined as and 1 

For a given module m let fanin m be the set of modules that depend on m and let fanout m be the set of modules that m depends on. This notion of dependencies is discussed with relation to the implicit dependency index mentioned with reference to example 15. The instability I m of a module m is defined as 

A stable module defined as SD m is defined as a module that m depends on that has a lower instability I than m and that resides in either the same layer or a lower layer than m. This can be expressed as follows 

SD m m fanout m I m I m L m L m MISI for a module m can now be defined as the stability of m SD m divided by the fanout of m. This is expressed 

For a well modularized system modules should depend on modules that are more stable and that reside in lower layers. Hence SD m fanout m and MISI m 1. If a system has a high MISI index then any changes or extensions made to the system will affect only a small number of modules in the upper layers of the system.

In the definition if MISI above the formula for stability is based on the fan in and fan out dependencies of modules. Alternatively instability of a module can be based on the probability the module will be changed in the next release or revision etc. of the software. This probability can be calculated based on the past module history. In such a case the following equations can be used to determine the instability I m of a module m as shown.

Let Rev be the set of revisions r . . . r of the given software and let Chg M Rev be the assignment of modules to the set of revisions in which the modules were changed. The instability I m of m can now be defined as 

With this definition of I m SD m and MISI m are defined as above. Furthermore the system level MISI can be generalized like the previously defined metrics.

As another alternative MISI S can be calculated as a simple average as shown above a weighted average a median value etc.

The testability index also called the normalized testability dependency metric NTDM determines the testability dependence of modules that is the degree to which modules rely on the input or output of other modules. A module that has few dependencies on other modules is easier to test. A testability dependence is created if the assessment of the correctness of the input output relationships during the testing of a module depends on the correctness of the input output relationships of another module. That is if the testing of module mrequires another module mto produce intermediate results that are then used in m then there is a testability dependence between the two modules. The extent of such testability dependencies are measured with the normalized testability dependency metric as explained below.

Let dep m be the number of modules on which a given module mhas a testability dependence. The testability dependence count TDC is defined as the sum of the testability dependencies dep m for substantially all modules in the system written as 

The NTDM metric index is the normalized ratio of TDC the sum of the testability dependencies for all or substantially all modules to the total number of modules to wit 

Note that TDC varies from 0 to M M 1 depending on the testability dependencies between the modules. The upper limit is reached when a module has a testable dependency on every other module i.e. M 1 while the lower limit is reached when a module has no testable dependencies on other modules. The value of NTDM will be 1 when the modules are independently testable i.e. when dep m 0 and 0 when every module is testably dependent on every other module.

The NTDM formulation shown above is based on the count of testability dependent modules. As an alterative formulation the strength of the testability dependence can also be measured.

As above let MDG be the module dependency graph where the nodes of the graph represent modules in the system and of the graph represent the pairwise dependence between the modules. Let path m m be the length of the shortest path from mto m. As before let dep m be the set of modules that a given module mis testably dependent upon. An alternate definition of the Testability Dependency can be defined as 

This metric characterizes software according to the principle of maximization of the stand alone testability of modules.

At a layer organization of given source code such as the source code can be calculated. This can produce an index such as the layer organization index of .

At cyclic dependency of given source code such as the source code can be calculated. This can produce an index such as the cyclic dependency index of .

At model interaction stability of given source code such as the source code can be calculated. This can produce an index such as the model interaction stability index of .

At testability of given source code such as the source code can be calculated. This can produce an index such as the testability index of .

At after one or more architectural modularity evaluations have been calculated results can be generated from the one or more calculated indices.

The module size uniformity index abbreviated MSUI measures how similar in size each module is within a specified portion of source code. Within reason modules generally should be roughly equal in size. A strong deviation from this uniform size constraint generally is indicative of poor modularization. The indices calculated using size perspective possess a bias towards making the modules as equal in size as possible subject to other modularization constraints. The size constraint can be expressed in terms of the average size of the modules and the standard deviation from the average associated with the module sizes. The module size uniformity index can be defined as the ratio of the absolute values of average size minus the standard deviation divided by the average size plus the standard deviation. This can be expressed as 

The closer this index is to 1 the greater uniformity of module sizes. As an aside this formula assumes that the standard deviation and the average size value are not equal which will lead to an incorrect 0 value of the metric as the numerator of the ratio will equal zero. Calculation of this metric should take measures to check for this disallowed value.

It is evident that MSUI increases as the standard deviation of the average module size decreases. This adheres to the module size principle and aims to measure the maximum of module size uniformity as discussed in example 3.

The module size boundedness index attempts to determine a correct size for a module. Even if modules are all approximately the same size the size could itself either too small or too large. It is often recommended that ideally no module should significantly exceed some recommended particular size generally expressed in terms of the number of lines of code. Assuming that this magic number is the average deviation in module length from this magic number is first calculated by Sz where Szis the number of lines of module m. Further let max Ideally 0 and a histogram of values will have a single bar of height M the number of modules at 0. However in practice a histogram of s could be spread over the range 0 of values.

The module size boundedness index is a measure as to what extent the deviations depart from the ideal.

A rationale based on the Lullback Leiber KL divergence for measuring the distance between two probability distributions is used. If it could be assumed that every measured size deviation between 0 and has a non zero probability of occurrence then it can be shown that the KL distance between the ideal and the actual distributions for the deviations would be log prob 0 where prob 0 is proportional to the actual number of modules whose size deviations from the magic size are zero. This measure can be weighted in some embodiments by because as becomes a negligible fraction of it is unimportant how the deviations are distributed in the range 0 as they are too small to care about. Therefore the following formula can be used to measure the extent to which the distribution of the actual size deviations differs from the ideal distribution 

It is evident from the module size uniformity index equation that module size uniformity increases as the standard deviation of the module sizes from the average module size decreases. This addresses the principle related to module size. Similarly the MSBI equation above measures the extent to which the module size bound as specified by is honored by the individual modules. This metric also addresses the principle Observance of Module Size Bounds. 

As an alternate module size boundedness index the following formula can be used. Recall that a magic number can be defined at the ideal size of a module for a system expressed in lines of code. Assuming that this magic number is the average deviation in module length from this magic number can first be calculated as shown below 

As a fraction of the largest of either the magic length or of any of the module lengths this deviation can be re expressed as 

This alternate MSBI measures the extent to which the module size bound specified by has been honored during the design of individual modules. It also adheres to the module size principle specifically to the observance of the module size bounds as discussed in example 3.

As another alternative MSBI a variation of the original formula can be used to calculate d. For example 

At module size uniformity of given source code such as the source code can be calculated. This can produce an index such as the module size uniformity index of .

At module size boundedness can be calculated. This can produce an index such as the module size uniformity index of .

At after one or more size performance module evaluations have been calculated results can be generated from the one or more calculated indices.

The English language constructs used to build a program such as words used in comments variable names function names and so on can be used to give clues to the purposes of functions modules layers and other software groupings. These clues can be referred to as concepts. The metrics in this example exploit these concepts to determine if the software groupings functions modules etc. have a similar purpose.

To determine any of the metrics in this example a concept set that is a set of words that may appear as keywords and or synonyms and or abbreviations of those words can be made accessible. This concept set may be assembled by hand by a person familiar with the source code may be partially assembled by hand and partially automated or may be assembled in another way.

Definitions that will be used for the indices described in this example are now described. Let C c . . . c denote a set of N concepts for a given system S. Also let F . . . indicate the set of functions distributed over M modules m . . . m The word function here indicates any software grouping with input output functions such that procedures subprograms etc. are included as previously mentioned. For this example the symbol mindicates the set of functions that are in m. For functions the number of occurrences of concepts which may include its synonyms abbreviations etc. and which may be found in the concept set are searched in the function signature and the function body. The concept frequency H c is denoted as the frequency of occurrences of the concept c C for a given functions F.

As an illustration of the concept content of a body of software the Apache httpd 2.0.53 is analyzed for the concept set authentication caching protocol logging. Table 1 below shows the frequencies of these concepts and their synonyms in the software. In this example H authentication 3.

The frequency distribution of these concepts in an exemplary embodiment is then normalized. A particular concept may occur more frequently than other concepts across all or substantially all functions typically a concept associated with the overall purpose of the software code . To avoid such a concept skewing the overall distribution substantially each concept frequency in an exemplary embodiment is normalized by its global maximum. As an example let H c maxH c F. Frequencies can be normalized as follows 

The concept domination metric and or the coherency metric after calculation can then be used as modularization quality evaluation results .

The concept domination metric abbreviated CDM determines if the concepts in the module have a non uniform probability distribution. If a module is highly purpose focused a probability distribution of the concepts in the module will be highly peaked at the concept corresponding to the purpose of the module. Therefore the more non uniform the probability distribution of the concepts in a module the more likely that the module conforms to singularity of purpose. The CDM can give a measure of the non uniformity of the probability distribution of the concepts. In the worst case all concepts will be evenly distributed which gives a CDM of zero in an exemplary embodiment. Other CDMs produce a worst case with a different value. As an example in an exemplary CDM concepts which may be words selected beforehand abbreviations portions of words and so forth are determined. This determination may comprise counting the occurrences of the concepts estimating the occurrences or may be done some other way. The number of or a portion of the concepts that occur in each or some of the modules is then determined.

As another example to create an exemplary CDM a normalized concept frequency is created. This can be created as follows for a given module m the frequency of occurrences of a concept ccan be obtained from the normalized concept frequency of functions that constitute a module. This can be expressed as 

The concept cis then found that maximizes for each module i.e. max Next the normalized frequency is converted into a discrete probability measure 

The Kullback Leibler divergence of a uniform probability distribution is then measured from the probability distribution g in an equation known as the divergence equation 

The dispersion of the concepts in any given module m is defined relative to concepts whose normalized frequencies of occurrence are within a predefined threshold of g c . This permits the purpose of a module to be stated in terms of not just one dominating concept but by a set of concepts that are more or less equally important. The following rule partitions the set C of concepts for a specific module m into two subsets Cand C.

Note that the existence of Cis predicated on divergence which may be KL divergence exceeding a certain threshold. If the KL divergence does not exceed the threshold the concept distribution is too uniform to allow for the partitioning of C into a subset Cof dominating concepts.

The following lemma establishes at least some desirable properties for the divergence and the concept subsets Cand C.

Lemma When the total number of concepts satisfies N 2 the KL g divergence of the divergence equation above is bounded by 0 k . When a module contains only one concept the KL g distance becomes maximum i.e. equal to k. Proof Being non negative the divergence KL g is bounded on the low side by 0. KL g becomes zero when the discrete probability distribution gis uniform. At the other extreme when a module m contains only one concept c C g c 1 and for all or substantially all other c C g c 0. In which case KL g log N log 1 which is equal to k.

The dispersion Dfor a module m with respect to the concept cand other almost equally frequently occurring concepts in Cis defined by 

The value of Dwill always be close to 1 when Cis of low cardinality and has the maximum concept frequency. Note that when Cis not zero its cardinality is always low. Furthermore then Chas maximum concept frequencies the following equation holds 

As an alternate formulation of the CDM metric the dispersion Dm can be calculated using weights where wand ware two numbers between 0 and 1 which sum to 1 using the formula shown below 

As another alternate formulation D the concept domination metric can be calculated as either a weighted average or a median value rather than the simple average shown above.

This CDM metric measures the extent to which modules in a software system are cohesive with respect to concepts words etc. that contain the largest number of clues within modules. This metric corresponds to the principle maximization of module coherence on the basis of similarity and singularity of purpose. As the CDM metric also measures the dispersion of concepts in that its value increases as the dispersion increases the CDM metric also corresponds to the principle minimization of purpose dispersion. 

The concept coherency metric measures mutual information existing between a concept and a module. If a concept is central to the services offered by a module then the mutual information between the module and the concept should be high. Such mutual information becomes high when each is able to predict the likelihood of the other with some probability. If a concept is orthogonal to the services offered by a module neither concept nor module can tell much about the likelihood of the occurrence of the other the mutual information between the two will be close to zero.

To formulate the concept coherency metric let C be a random variable whose value can be any element in the set C of defined concepts as discussed earlier in this example. Similarly let M be a random variable that can take on any value from the set M of modules. The mutual information between the concepts and the modules is then given by where H C denotes the entropy associated with concepts in the system and H C M denotes the conditional entropy of the concepts in terms of the modules. The entropy H C can be expressed by 

It may be further observed that in the worst case all of the software may be in a single module that is a monolithic system having 1. Here the I C M becomes 0 as shown below 

Similarly to the concept domination metric the concept cohesion metric adopts an information theoretic approach to measure the extent to which modules in a given system consisting of source code such as the source code are cohesive with respect to the main concepts embodied in the modules. Like the concept domination metric this metric also corresponds to the principle maximization of module coherence on the basis of similarity and singularity of purpose as discussed with reference to example 3.

At concept domination of given source code such as the source code can be calculated. This can produce an index such as the concept domination metric of .

At coherency of given source code such as the source code can be calculated. This can produce an index such as the concept domination metric and or the coherency metric .

At after one or more similarity of purpose modularity evaluations have been calculated results can be generated from the one or more calculated indices.

At source code is received. This source code may be the source code of . At a concept term map is received. This concept term map may be a concept set as discussed with reference to example 19. For example it may be an input file containing a set of business concept names and the associated terms keywords and abbreviations that can be used to identify a business concept. This concept term map may be created manually automatically or by some combination of the two.

A keyword extractor then extracts concept terms received from the concept term map from the source code producing a concept frequency distribution . The keyword extractor may input the keywords from the concept term map as regular expressions and then may compute a concept frequency distribution for functions by counting the occurrences of the keywords in the function signature return types and data structures used by the function. Function calls need not be considered in the counting process as they can skew the concept distribution frequencies. For example suppose that a customer update function calls an account handling function several times. If the concept account is looked for in the function call called by the customer several occurrences of the concept account will be found without the concept otherwise being mentioned in the function. If the number of occurrences is sufficiently high account might appear incorrectly as the dominating concept in .

This concept frequency distribution can in an exemplary embodiment be stored in a metadata database . A metric calculator such as the similarity of purpose metric calculator can then use at least the concept frequency distribution with other inputs to produce at a minimum the concept domination metric and the coherency metric . Similarly an evaluator may be used to aid in the calculations of the concept domination metric and or the coherency metric or other indices as described in the examples herein.

At occurrences of the concepts are counted in the source code. At results of the concept extraction the concept counts are generated. The concept count results may be a listing of how may of the concepts appear within various functions modules layers etc may be an analysis of the concept counts and so forth.

For instance programmer P may have modified a file F whose version is 0.1 . Modifications are stored in D with new version of file being 0.2 . The modifications can be those modifications that are generally tracked in version control software. The following modifications are typically stored modification in file details modification in function details modification in global variable details modification in data structure details modification in function dependency modification in dependency between global variables and functions and changes in dependency between data structures and functions.

In one embodiment of the present technique the programmer code modification history extractor parses the source code modification history data source code modification history of and stores the programmer file and version information and the exact changes in a secondary storage such as the code modification history store. In another embodiment the secondary storage can be a conventional relational database. The programmer code modification history extractor can extract at least some portion of the following information or other information from the modification history data name of the programmer name of the file source code the programmer has modified the version of the file and date of creation the nature of the change in the file with respect to its previous version.

In one embodiment the changes with respect to the previous version that can be retrieved include the functions that have been added modified deleted the data structures global variables that have been added modified deleted which function dependencies global variable function dependencies data structure function dependencies have been added modified deleted. In one embodiment the above information can be stored various database tables.

At the source code modification history is received. At the programmer coding history is extracted from the source code modification history. At the programmer coding history results are generated using at least in part the programmer coding history .

A programmer history such as the programmer history of is used by a history parser which reads the parsed programmer history not shown into the metadata database . A module analyzer is also present which in an exemplary embodiment accepts as input an architectural description of the source code outputs a module analysis not shown and stores it in the metadata database . A metrics calculator which may be a modularization evaluator then uses information stored in the metadata database to produce modularization quality evaluation results .

A model extractor takes as input source code which may be source code of . The model extractor then extracts a source code model which then may be stored in a source code database which may be a stand alone database or may be a portion of a larger database. A modules list which may be an architectural description may be used by the module extractor to produce the source code model .

A series of perspective evaluators A B . . . N may then take as input the programming coder history the source code model and the modules list to evaluate the quality of modularization of the software producing modularization metrics. Examples of such metrics include but are not limited to structural metrics described with reference to examples 15 and 16 architectural metrics described with reference to examples 15 and 16 size based metrics described with reference to examples 17 and 18 and similarity of purpose metrics described with reference to examples 19 and 20 .

In at least one embodiment at least one of these metrics is calculated using a before and after technique. For example prior to a code change by one or more programmers and subsequent e.g. immediately subsequent to the code change. The definition of code change is meant to be very flexible and embraces any sort of change or changes that are desired to be measured. Calculation of the metrics can be triggered based on a threshold amount of time that has passed i.e. every week month quarter etc. or based on a threshold number of lines of code written and so forth.

In such a case the change in the modularization metric values indicates whether the programmer s change decreased the modularity of the system increased the modularity of the system or maintained the modularity unchanged.

The metrics generated can then be stored in a programmer performance information repository . Changes in metric values can be aggregated to arrive at the overall effect of the change which in turn can represent the performance of the programmer for that given change.

A user interface can be used to specify report parameters for a report generator . The report generator can pull information from for example the user interface and the programmer performance information repository to generate a programmer performance report .

The programmer performance report may indicate a series of modularization metrics for one or more programmers. The change in the modularization metric values can indicate whether the programmer s change decreased the modularity of the system increased the modularity of the system or maintained the modularity unchanged.

In another embodiment a final performance score for respective programmers is calculated based on the performance for each or a set of individual changes number of changes made and consistency of performance. In another embodiment based on the modularity metric scores programmers who have caused deterioration low scores of the system are identified. In another embodiment for identified low scoring programmers the source code changes made by them are analyzed and the type of changes which caused maximum damage is derived.

In another embodiment analysis on the source code changes made by poor scoring programmers is performed to determine the modularity principles that were not followed. In another embodiment the programmer performance report is generated based on the metric values for the final version of the system for programmers. In another embodiment of the present technique refactoring solutions for improving the modularity of the system are presented.

A source code change determiner which may be a commercially available version control software then determines the difference between the source code and the changed source code to produce source code modularization changes which may be source code modularization results. By looking at the modularization results generated by the source code and the different modularization results generated from the changed source code in some embodiments the source code change determiner can then determine which changes led to the differences in the modularization results .

Examples of changes that lead to difference in modularization include but are not limited to addition or deletion of functions introduction of unwanted dependencies between functions in different modules a function using a global element used by a function in another module failure to use the API properly ad hoc function calls calling functions in a higher layer from a lower layer and so on.

An exemplary report format that provides a diagnostic report related to the modularity of a system is described here an example report for the system Slim Tool is shown in example 38. The report may have three parts described below.

Part B gives a more detailed description of each metric with respect to the Structural Information Size and Architecture viewpoints in some embodiments. In an exemplary embodiment if the user clicks any one of the metric links e.g. MII Module Interaction Index link a detailed report for that particular metric is shown. An exemplary report for the MII metric has been shown in Example 39.

Part C gives analysis of modules from various design principles for example categorizing modules depending on whether or not they obey one of the design principle taught herein. For instance under the design principle All inter module interactions should only be through API functions there are various categories of modules which violate and obey the design principle.

Individual modules may also have reports. Example 41 shows an exemplary model analysis report containing a detailed analysis with respect to a given module and functions inside the module. The sections shown in this report are easily extendible for other type of metrics as and when they are introduced.

A sample system metric report is shown below. The system metric may have a system health overview chart which charts a selection of the system metric values that have been produced for a system using embodiments taught herein. For example shows a System Health View Chart that can be used to give an overall view of how well a system has been modularized.

These metrics measure the function call traffic through the API functions of modules in relation to the overall function call traffic

This metric can calculate how effectively a module s API functions have been used by the other modules in the system.

This metric is based on the principle that the non API functions of a module should not be exposed to the other modules. This metric measures the extent to which non API functions are being accessed by the other modules.

This index can determine what fraction of the API functions exposed by a module is being used by other modules. The intent of this index is to discourage the formation of large monolithic modules offering disparate services and encourage modules that offer specific functionalities. Any module A that depends on a module B should utilize some portion of the functionality offered by module B. Multiple modules should not depend on module B for varied functionality unless Module B is a utility module.

This index can measure the number of implicit dependencies that are created when the given module writes into global variables with assumption being that any global variable that is written into may be accessed by another module. This index discourages the use of global variables for transfer of data across modules. Ideally inter module interaction should be through function calls preferably through API functions .

This class of metrics attempts to measure how modular the system is in terms of the individual module s sizes. These metrics need not be applicable at Module level. The computed values are at system level.

This can index measure how similar the module sizes are with respect to a magic optimal size which can be provided by a subject matter expert.

These metrics measure the extent of organization of the modules into higher level structures especially the horizontal layered structures. The assumption behind these metrics is that not all of the modules exist in the same level of utility and that there exists some hierarchy.

This index measures the number of cyclic dependencies that exist across modules within a system. Modules A B and C are said to be in a cycle when A depends on B B depends on C and C depends on A. This metric need not be applicable at Module level.

A module is assumed to be well layered when calls that are made to modules in a given layer are made from modules in the layer immediately above them. This index can measure the extent to which this principles in followed. This metric need not be applicable at Module level.

This index can measure the stability of intermodule dependencies. Assuming that large software systems are organized into horizontal layers a desirable property of this architecture may be that the modules in the lower layer be more stable in relation to the modules in the upper layers. Thus changes made to the overall software should be concentrated to the upper layers. Also to the extent possible the changes should not impact the lower layers. This metric is based on the assumption that each module should depend on other modules that are in the same or lower layers. The value of this metric may indicate the changeability of the system.

Testability dependence can be created if the assessment of the correctness of the input output relationships during the testing of a module depends on the correctness of the input output relationship of another module. That is if the testing of module m requires another module m to produce intermediate results that then are used in module m there is a testability dependence between the two modules. This metric is based on the principle that every module should be dependent for testability on as few modules as possible.

These metrics can be based on the assumption that the purpose of any module is to provide a specific service and clues as to what that service is is provided by the variable names function names etc. that are used in the code. These keywords themselves are only a manifestation of the concept which is representative of the service that the module tries to provide.

This index measures the dominant concepts in a module. In a modularized system ideally each module should have only one dominant concept. A high number of dominant concepts in a module can indicate that the module provides different types of services.

This metric is based on the notion that if a concept is central to the services offered by a module then the mutual information between the module and the concept should be high. Mutual information between a concept and a module becomes high when each is able to predict the likelihood of the occurrence of the other with a high probability. This metric need not be measured at module level.

The various dimensions along which the quality of the software is improved by the encapsulation provided by modularization include understandability testability changeability analyzability and maintainability. Listed below are the Design Principles which when adhered to can ensure good modularization. These principles have been derived based on Research Literature as well as experience. For each of the below mentioned principles we list the modules that grossly violate the principles and provide details about the same so that corresponding changes can be made so as to improve the modularity of the system.

Modules that have a high percentage of implicit dependencies through global variables with other modules are 

Modules that do not provide a complete service No other module utilizes ALL of the API functions of the given module are 

Modules that provide disparate services API functions are utilized by a majority of the other system modules are 

Module Should More or Less be of Uniform Size this Uniform Size is a Magic Size that is Decided Upon by a Domain Expert 

Modules Should Not be Cyclically Dependent Cyclic Dependencies Occur when there is a Sequence of Function Calls Between Modules that Starts and Ends at the Same Module .

Module Dependencies Should be Unidirectional. Modules Should Only Depend on Modules in the Immediate Lower Layers.

Modules Should be Dependent Only on Other Modules that More Stable Than Them Typically modules in a lower level of call hierarchy should be more stable 

The service that is provided by a module can be determined by considering the concepts that the module encapsulates. A business concept is the functionality or the idea that a module encapsulates e.g. in a banking application the concepts would be loans interest term deposits etc. It is often recommended that a module be centered around one two concepts. For example a module may implement the concept loan. It is not necessary that a concept is implemented by only one module. For instance various services around the business concept loan can be implemented by several modules. But it is not recommended that one module implements many concepts. That is one should not implement a module that implements loan credit card and calendar. 

An exemplary metric report for a system with five modules reporting on the Model Interaction Index MII is shown below. The MII is discussed in greater detail with reference to example 15. The MII value in use here has been normalized such that the value ranges from 0 worst to 1 best . A chart which shows MII distribution across system modules is shown with reference to . Even though not shown similar charts for other indexes such as the non API Function Closedness Index the API Function Usage Index the Implicit Dependency Index can also be included.

An exemplary detailed report for a system level metric is shown below Module level diagnosis need not be provided for all metrics. For example Size based metrics Layering Cyclic Dependencies Domain Concept distribution in the system are reported only at the module level within these reports.

With reference to a Module size chart displays actual module sizes for a given set of modules in KLOC Thousands of lines of code not including blank comment lines the average size and the Magic size of modules as received from for example a domain expert. Very large or very small modules tend to be prone to a larger number of errors and hence often require higher maintenance. Good modules should more or less be of similar size and should not be particularly deviant from the magic module size. The chart below gives the actual number of lines of code in KLOC for a selected set of modules.

The table below indicates the layers to which a module belongs and the Layer organization index LOI of a particular layer. No. of back calls from layer are the number of module dependencies that layer has with modules in upper layers. No. of skip calls from layer measure the number of calls that are made to layers below which are not the immediately adjacent layers.

The Cyclic Dependencies table shows the number of cycles in the system and the participating modules in each of the cycles. Cyclic dependencies occur when there is a sequence of function calls between modules that starts and ends at the same module. The largest cycle is reported for each module. Cycles within cycles are not reported. If there are four modules M M M and M and M has a function call to M M has a function call to M M calls M and M has a function call back to M then M M M and M are in a cycle which would most likely be reported. However the cycles within this cycle would not be reported such as a cycle consisting of M M and M.

An exemplary modularity detail report is shown below for an exemplary module module. The report has among other features a detailed analysis for a given module and for the functions inside the module. The report refers to functions but the term should be understood to mean any named block of code that performs a task such that it encompasses functions procedures methods and the like.

The functions implemented in the module have been classified as API these should be the only functions that expose the functionality of the module to other modules INTERNAL these functions are typically not accessed by other modules BAD these are the non API functions of the module that are accessed by other modules and DEAD These may be functions that are neither accessed by nor access other modules 

The programmer modified code is then used by a perspective evaluator which may be any of the perspective evaluators A . . . N and which may return one or more of the modularization indices or metrics discussed herein. This index or indices may then be used a portion or as the entire programmer evaluation results such as the programmer evaluation results 

In an exemplary embodiment the change in at least one the metric value indicates whether the programmer s change decreased the modularity of the system increased the modularity of the system or maintained unchanged. Change in each of the metric values can be aggregated to arrive at the overall effect of the change or changes to the system made by the programmer which in turn represents the performance of the programmer for that given change or set of changes.

In another embodiment a final performance score for a programmer is calculated based on the performance for each individual change number of changes made and consistency of performance.

At the portion s of the source code that has been modified by the programmer is evaluated using at least one modularization metric. These modularization metrics may be any of the perspective evaluators A . . . N any of the modularization metrics discussed in any of the examples and so on. This may generate programmer evaluation results such as the programmer evaluation results .

At which is optional the programmer is ranked based on the programmer evaluation results against other programmers. This evaluation may be with other programmers working on the same source code programmers working on other source code in the same system programmers working on different systems and so forth.

Once programmer evaluation results are known corrective action can be taken to improve the overall quality of service of the maintenance by providing specific feedback to the programmers who have caused significant degradation of the software. As the specific portions of the software which were changed have been identified the changes that the programmer made that caused the degradation in modularization can be identified and fixed. Thus programmers will be much less likely to perform such activities in the future which cause modularity degradation. This in turn will keep the software more modular and maintainable.

This randomization very roughly simulated what can happen over time as a large system is maintained new features are added and the software generally evolves to meet changing hardware and functional requirements.

For four systems Linux shown in Mozilla shown in Postgresq shown in and Apache shown in each system is analyzed using the metrics described herein twice. First the system with its modularization intact as originally designed by humans is analyzed. Second the original modular structure of the software is destroyed by randomly assigning functions and files to modules breaking the internal coherence of the module the random modularization as shown in . Then the broken systems are analyzed using the same metrics.

The graphs and show the result of this analysis. As can be seen the metrics other than the size based metrics take a turn for the worse with random modularization. However the size based metrics especially the MSUI metric do not show large variation when moving from the human supplied to the randomized modularization. The reason for this is not difficult to understand. Since the randomization mechanism is based on a uniform random number generator the functions are more or less equally distributed across modules resulting in a small standard deviation in module size.

The IDI metric also does not show major variation between human and random variation. Recall that the IDI of a module is the ratio of external function call count to the inter module dependency count using both functions and global variables. The randomization process randomly assigns functions to modules. However the function global variable dependency obtained by static analysis of the source code is not changed by the randomization process. As a result the inter module dependency count through the unchanged global variables is unchanged for the large part. Furthermore the random assignment of functions to modules in many cases does not have significant impact on the total count of external function calls.

These observations regarding the relative values of the various metrics speaks to the fact quality of modularization is best understood through a variety of metrics.

The graph shows a comparison of modularization results between two different Mozilla versions mozilla 19980408 and mozilla 19981211. Previously published reports indicate that mozilla 19981211 is better modularized than mozilla 19980408 borne out by this analysis.

To analyze how concepts might be dispersed and concentrated across modules in a system the frequency distribution for the concepts were examined. If a module had roughly equal occurrences of multiple concepts it is difficult if not impossible to determine a dominating concept for the module and thus difficult to attribute a similarity of purpose for the module. As shown at the module os beos is dominated by the concept platform On the contrary both randomly modularized systems show no such concept domination as is to be expected as functions assigned randomly to a module would have few dominating concepts.

The graph shows the frequency that the concept parser occurred in multiple modules of the source code for mysql. The graph shows the frequency concept parser occurred in multiple modules of the source code for mysql after the modules had been randomized. Similar to the results for httpd above as can be seen the concept parser occurs in just a small number of modules in the human modularized version but occurs in almost all modules in the random modularization .

This example documents experiments performed using methods taught herein. The open source application Apache httpd web server was used for the experiments documented herein. To evaluate the maintenance scenario shown in the source code was modified to add additional functions and to modify the function calling patterns. To analyze the capability of the tool to evaluate programmer multiple versions of the system were created as shown in . Each version then had its source code altered. In both cases neither the inherent structure of the modules was not changed nor was the overall architecture of system.

The type of deterioration that is introduced into the system through these changes is quantified using MII module interaction index shown at in and APIU API function usage index shown at in metrics. A comparison of the MII and APIU values before and after deterioration is shown below and in at .

Similarly the chart at shows the system level deterioration in modularization as shown by decrease in the LOI layer organization index shown at NTDM testability index shown at in IDI implicit dependency index shown at in and CDM Concept domination metric shown at in .

To analyze the characteristics of layer organization index specifically with respect to the code deterioration consider the httpd 2.0.53 system module dependencies. An analysis of the module dependencies between modules of httpd 2.0.53 reveal that there exists a set of modules that are mutually dependent on each other. These modules are listed below.

One of the modularity deterioration patterns is the addition of a new module dependency that creates a set of mutually dependent modules or that increases the number of modules that are mutually dependent. This code deterioration is created by adding a new dependency of module srclib apr threadproc netware on module server mpm beos. i.e. srclib apr threadproc netware server mpm beos

This type of deterioration is quantified using the metrics LOI and NTDM. A comparison of the metric values before and after modification is as shown below and in .

According to the principle of module interaction interaction between modules should be explicit i.e. through function calls and not through global variables i.e. Implicit . To simulate a deterioration of modularity by violating this principle new implicit dependencies between modules server and aaa have been added. The deterioration is quantified using the Implicit Dependency Index IDI metric. A comparison of the metric values before and after the deterioration is shown below and in .

Module aaa handles authentication and only authentication in httpd. The deterioration in modularity of aaa is simulated by mixing in disparate concepts server and proxy . This is achieved by randomly adding 50 functions from module server and 30 functions from module proxy to module aaa.

This type of modularity deterioration is measured using the CDM metric. A comparison of pre and post deterioration metric values are as follows and shown in .

Version 0 depicts the original snapshot of modules srclib apr memory unix server mpm experimental leader and their interactions.

The module srclib apr memory unix has two internal functions run child cleanups and cleanup pool for exec. Programmer adds a new function dependency from module srclib apr misc netware to these two internal functions thereby violating the module interaction principle.

The change in MII metric values from version to version as a result of the code change by programmer is as follows 

Programmer p adds some of the server and proxy functionality in module aaa an authentication module. This change violates the similarity of purpose principle. The change in CDM metric value from version1 to version2 is as follows 

In the module server mpm experimental leader interaction with other modules violated the MII principle in version . The functions process socket and make child were invoked by srclib apr misc network even though they were internal functions within a different module.

In version3 as part of the refactoring exercise programmer introduced a new api function process api that exposed the functionality of the two internal functions to the external modules with process api directly calling those two internal functions. The change in the MII metric from version to version was as follows 

With reference to the computing environment includes at least one central processing unit and memory . In this most basic configuration is included within a dashed line. The central processing unit executes computer executable instructions and may be a real or a virtual processor. In a multi processing system multiple processing units execute computer executable instructions to increase processing power and as such multiple processors can be running simultaneously. The computing environment may also include a graphics processing unit GPU which assists in creating or speeding up graphics processing and display. Memory may be volatile memory e.g. registers cache RAM non volatile memory e.g. ROM EEPROM flash memory etc. or some combination of the two. The memory stores software implementing the described methods for measuring quality of software modularization. A computing environment may have additional features. For example the computing environment includes storage one or more input devices one or more output devices and one or more communication connections . An interconnection mechanism not shown such as a bus a controller or a network interconnects the components of the computing environment . Typically operating system software not shown provides an operating environment for other software executing in the computing environment and coordinates activities of the components of the computing environment .

The storage may be removable or non removable and includes magnetic disks magnetic tapes or cassettes CD ROMs CD RWs DVDs or any other medium which can be used to store information and which can be accessed within the computing environment . The storage stores instructions for the software implementing methods for measuring quality of software modularization.

The input device s may be a touch input device such as a keyboard mouse pen or trackball a voice input device a scanning device or another device that provides input to the computing environment . For audio the input device s may be a sound card or similar device that accepts audio input in analog or digital form or a CD ROM reader that provides audio samples to the computing environment . The output device s may be a display printer speaker CD writer or another device that provides output from the computing environment .

The communication connection s enable communication over a communication medium to another computing entity. The communication medium conveys information such as computer executable instructions compressed graphics information or other data in a modulated data signal.

Computer readable media are any available media that can be accessed within a computing environment . By way of example and not limitation with the computing environment computer readable media include memory storage communication media not shown and combinations of any of the above.

Any of the methods described herein can be performed via one or more computer readable media e.g. storage media having computer executable instructions for performing such methods.

The technologies of any example described herein can be combined with the technologies of any one or more other examples described herein.

In view of the many possible embodiments to which the principles of the disclosed technology may be applied it should be recognized that the illustrated embodiments are only examples of the technology and should not be taken as limiting the scope of the following claims. We therefore claim as our invention all that comes within the scope and spirit of these claims.

