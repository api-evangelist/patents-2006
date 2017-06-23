---

title: Method and system for expression evaluation
abstract: A method to analyze impact of changes to a model includes accessing a proposed change to a model. An expression that is relevant to the proposed change is accessed. An instances set associated the expression is obtained. The instance set is evaluated to determine an impact of the proposed change to the model. An application utilizes the expression of a model. An impact analyzer assesses impact of a change to the model by evaluating at least one of the one or more expressions and returning an evaluation set for use by the application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07584163&OS=07584163&RS=07584163
owner: SAP AG
number: 07584163
owner_city: Walldorf
owner_country: DE
publication_date: 20060914
---
The present application relates generally to the technical field of expression evaluation and in one specific example to a method and system for evaluating expressions associated with a model.

Models of applications may be represented by modeling languages. While modeling languages may be used to describe structural relationships with the models the modeling languages typically do not provide a mechanism for describing expressions associated with the model. A formal expression language may be used along with the modeling language to describe the expressions associated with the model.

When changing a model associated with a number of expressions each of the number of expressions may be reevaluated to ensure that the resulting model is still valid. The reevaluation of the number of expressions associated with a model of substantial size may be processing intensive on a computing system even though a subset of the number of expressions may only be effected by the change.

Example methods and systems for evaluating expressions associated with a model are described. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of example embodiments. It will be evident however to one skilled in the art that the present invention may be practiced without these specific details.

A model may have expressions to further define the model. Modifications to the model may necessitate reevaluating at least some of the expressions for certain instances of the model. When a proposed change to a model with one or more expressions may be accessed one or more instances sets associated with each of the one or more expressions may be obtained. Each instance set may include a starting point and a reverse navigation path.

An impact of the proposed change to the model may be assessed by evaluating relevant expressions for which the instance sets are evaluated using the starting points and the reverse navigation paths.

Referring to a system for accessing a model according to an example embodiment is illustrated. For example the model may represent a relationship a real word domain such as an organization user interface UI elements of an application system components of a software architecture the elements contained in a business object implementing an enterprise service and the like. In an example embodiment the model may be a model or a metamodel.

The model may be represented by a modeling language and one or more expressions may further define the model . The modeling language may describe the model in a program neutral way. In an example embodiment the modeling language used to represent the model may be uniform modeling language UML a subset of UML or the meta object facility MOF . For example the modeling language may be used to diagram structural relationships by use of a class diagram. In an example embodiment the language used to represent the one or more expressions may be object constraint language OCL .

The expressions may be in a formal language used to describe expressions on the model such as one or more constraints for the model and model to model transformation rules. In an example embodiment the expressions of the model may be represented in a separate expression language to the modeling language . By way of example an expression on a model may be to provide all employees that work under a particular boss such that evaluation of the expression may return a set of the employees that work for the particular boss.

In an example embodiment a change to the model may trigger a need or desire to reevaluate a subset of the one or more constraints such that the model may continue to be valid after the change has been applied to the model . For example a formal language used to describe the constraints may be object constraint language OCL expressions. In an example embodiment the constraints may include invariants pre conditions post conditions and operation definitions.

By way of example if the model is of a company a constraint on the model may be that an employee of a department cannot earn more money than a boss of the department or that for a particular job title the employee cannot earn more than a certain amount of money per year.

In an example embodiment dependency of a target model from a source model may be described by the expressions such that regeneration of pieces of the target model may occur from a change in the source model . The pieces may be identified by the expressions such that monitoring model change events that affect those expressions may determine pieces of the target model to regenerate. For example evaluation of the expressions may provide a value of an attribute that may be assigned to a model element of the target model and generate a list of elements of the source model to consider in a loop used to generate portions of the target model .

A compiler may compile the model into programming language code that may be used by the application . By way of example the model may be a model for a company including departments and employees. The compiler may generate the programming language objects from the model . The programming language objects may be in the Java programming language such that generated classes may enable access to a department or an employee creation of a department modification of the relationship between the department and an employee in the model .

In an example embodiment the compiler may compile code of the model before use by an application . In an example embodiment the compiler may compile the code at run time.

The application may use the programming language objects that are generated by the compiler to work with the model . In an example embodiment the application may be an editor a simulation tool a graphical user interface GUI and the like. The application and the compiler may operate on a computing system . An example embodiment of the computing system is described in greater detail below.

In an example embodiment the model may be an underlying structure that enables alteration of a way that the application functions. For example elements of a user interface for manipulating the model may be enabled or disabled depending on a query of a state of the model .

Referring to an apparatus for model interpretation according to an example embodiment is illustrated. The apparatus may include an application in communication with an impact analyzer an event framework and an expression evaluator .

In an example embodiment the application may be a subset of the application such that the application may be a portion of the application that utilizes the expressions of the model see . For example the application may be a constraint checker or a model transformation engine.

Changes to the model are sent to the application via an event framework . By subscribing to the event framework whenever a change occurs to the model for example by introducing a new employee or changing a boss of a department the event framework may notify the application that the model has changed. In an example embodiment a filter may be used to specify selected notifications to be received by the application based on an event kind and an event type.

When the application receives notification from the event framework that a change has occurred to the model the application knows that expressions attached to the model may need to be re evaluated by the expression evaluator .

In an example embodiment without use of the impact analyzer the application may re evaluate all the expressions on the model whenever anything changes in the model . For example if a model has several hundred elements and several dozens of expressions on the model re evaluation may involve re evaluating thousands of the expressions even though most values associated with the expressions have not changed.

The application may provide the impact analyzer with the expressions that are on the model . The impact analyzer may then assess an impact of changes to the model by evaluating the expressions and return to the application events that the application needs to subscribe to in the event framework . By subscribing the application to the event framework the event framework may indicate to the application a subset of changes that may have an impact on the expressions instead of all of the changes to the model .

Once the application has subscribed to the event framework and receives a notification from the event framework regarding a change to the model the application may provide the impact analyzer with the event and receive the expression to be re evaluated based on the change in a form of an evaluation set. By way of example if a wage of an employee has changed the event framework may notify the application to re evaluate the expression that checks an employee s wage against the wage of his boss.

The application may provide the evaluation set to the expression evaluator for evaluation. An example embodiment of the evaluation set and a method for evaluating the evaluation set is described in greater detail below.

By way of an example the model may describe a company with all departments and employees the expressions on the model may define business rules of the company the application may be a company software management program and the application may be a constraint checker. Changes to the model may include hiring employees firing employees providing bonuses to the employees and the like. For these changes to the model the application may use the impact analyzer to determine the changes in the model are relevant to the business rules of the company. The changes may be provided to the impact analyzer which then returns an evaluation set. The evaluation set may be provided to the expression evaluator to determine whether the changes evaluate to true thereby indicating that the business rules are still being met after the change. If the business rules are not met after the change a component of the system may be notified of a violation of the business rules the application could roll back the recently made changes an e mail may be sent to provide a notification of the violation a transaction within the model may be aborted and the like.

The results of the evaluation by the expression evaluator may be provided to the application such as a set of attribute values or a collection of model elements. For example if the expressions are constraints the results of the valuation may be a set of two fold values. The application in the form of a constraint checker may expect that all the values in the set of two fold values are true.

By way of example a source model may be a database a target model may be a UML diagram and the expressions may be a set of transformation rules that indicate which piece of the database maps onto a piece of the UML diagram. The database may include a model for an employee with an attribute salary such the employee may have a box that has a title string employee with one field with a name salary . If the name of the attribute is changed from salary to wage the model to model transformation would know to change a particular box in the UML diagram. The expression may be used to access the name string in the source model and pass the name string into the target model .

By way of example a source model may be a company model and a target model is an organization chart. A first transformation rule may indicate to start an organization chart first with a boss and then have an expression that obtains the boss from a department. The expression evaluator may then return the employee that is the boss of that department which information may be used to draw a first box. A second transformation rule may indicate to next draw all the employees that work for the boss in the department in the organization chart such that a next expression would provide all the employees that work for the boss. The expression evaluator may then return a collection of employees as elements. The application may then iterate over the sets of employees and draw boxes in the organization chart while inserting names in the organization chart as appropriate.

Referring to an apparatus to assess impact is illustrated. The impact analyzer see may include the apparatus . The apparatus may include an analyze component a filter component and a housekeeping component . In an example embodiment the apparatus may act as an application programming interface API for the impact analyzer .

The analyze component may receive a number of expressions from the application and may return a subscription filter to the application that may be used to subscribe to the event framework see . For example the analyze component may analyze the events to which the application has subscribed in the event framework to be informed regarding changes to the model of interest given the provided expressions to the model see .

Once the application has subscribed to the event framework when an event is sent to the application the filter component may determine which of the expressions of the model should be evaluated based on the event that occurred.

The housekeeping component may provide housekeeping for the analyze component and the filter component . For example the housekeeping component may build an event cache during a first phase to enable a fast lookup during a second phase.

In an example embodiment the first phase may be when the analyze component analyzes the events to which the application has subscribed in the event framework .

In an example embodiment the second phase may be when the application provides the events from the event framework to the impact analyzer . The apparatus may then use the housekeeping component to access the expressions for evaluation based on the notification received from the event framework and provide the expressions back to the application that are relevant for the events.

In an example embodiment the information regarding the changes to the model that will affect the expressions may be associated with the housekeeping component as internal events. For example use of the internal events may be limited to inside the impact analyzer . The internal events may be transformed by the housekeeping component into model change event filters that the application may use to subscribe to through the event framework .

Referring to a system to assess impact is illustrated. For example the system may analyze impact by analyzing expressions see and returning an event subscription filter and the expressions to be evaluated in response to an event.

The system includes an analyze function that calls a class scope analysis and an instance scope analysis . In an example embodiment the analyze component see may include the analyze function the class scope analysis and the instance scope analysis .

The class scope analysis may parse the expressions received from the analyze function and provide an output that identifies the events that are relevant to the expressions . In an example embodiment all instances of the context for each event may be taken into account by the class scope analysis .

In an example embodiment the output of the class scope analysis may be an attributed abstract syntax tree AST . The internal events may be attached to each node of the attributed AST based on relevancy. For example tags may be included on nodes of the AST to indicate portions of the expression that are irrelevant for certain event types.

In an example embodiment the output of the class scope analysis may be a key value path where the key is the event type plus the expression and the value is the expressions needed to compute the model event for which evaluation of the expression is needed. In an example embodiment the class scope analysis may store the key value path in an event cache .

The instance scope analysis may access the output from the class scope analysis and associate navigation paths with the output such as reverse navigation paths. For example the reverse navigation paths may lead from instances affected by the events to context instances of an affected expression . The output from the instance scope analysis may be stored in an event cache .

In an example embodiment the instance scope analysis may traverse the AST to determine for which instances the expression may need to be evaluated. The instance scope analysis may traverse the AST and override entries in the event cache by repairing the expressions that have been stored by the class scope analysis .

In an example embodiment after the class scope analysis is applied the event cache may contain all the expressions that are all instances. The instance scope analysis may traverses the AST again and replace the expressions by more appropriate and finer grained expressions that indicate the instances in which the expressions are to be considered.

The event cache may act as a data structure for the impact analyzer . In an example embodiment the output from the class scope analysis may be stored in the event cache . In an example embodiment the instance scope analysis may revise the output stored in the event cache to include the reverse navigation path.

A filter generator may create filter expressions e.g. a subscription filter such as for events matching the model change events relevant to the expressions from information stored in the event cache by the instance scope analysis .

For example after the instance scope analysis the event cache has information identifying which events are relevant for the expressions . The filter generator may use the information stored in the event cache to identify to which events the application needs to subscribe by passing the information back to the application through the analyze function .

In an example embodiment the event cache may store information about event types. For example the information stored may include the expressions that need to be evaluated when a value of an attribute wage changes within a type employee. A particular instance of the expression may be used as an input for a filter such that the filter may indicate that the wage for an employee has risen to a certain amount.

An event mapper may provide a mapping between the model change events and the internal events. For example notifications that contain model change events may be mapped by the event mapper to internal events that may then be used to access information in the event cache .

During execution of a filter function the events may be accessed in the event cache and returned information may be converted into an evaluation set. For example the evaluation set may be provided to the application as a result of the filter function see .

In an example embodiment the event mapper may relate an event instance to an event type. The event type may then be passed onto the event cache which may then perform a look up within the event cache and return an evaluation set and an evaluation unit to the filter function .

Referring to a data structure to evaluate an expression is illustrated. For example the data structure may demonstrate what the application may receive from the impact analyzer as a result of executing the filter function see .

An evaluation set may consist of a number of evaluation units and each of the evaluation units may contain a statement and a number of instance sets . For example the statement may include an expression of what to evaluate and the instance set may include a number of instances in the model for which the statement is to be evaluated.

In an example embodiment the evaluation set may define a number of evaluation units to consider for a change to the model see . For example the evaluation set may be provided to the application as a result of the filter function see .

In an example embodiment when a model change event is received the impact analyzer may access information stored for the model change event and use the stored information to return the evaluation set to the application .

Each instance set may be a data structure usable by the application that can be passed on to the expression evaluator see . The expression evaluator may loop over the evaluation set and select each of the evaluation units . For each evaluation unit the expression evaluator may examine the navigation paths defined by the expressions and starting points defined by the objects of the instance sets . After the instance sets have been computed the expression evaluator may perform an evaluation by examining the instance sets .

For example a change in the model may have an influence on more than one statement that are attached to the model . The change may trigger the re evaluation of more than one statement which may be the evaluation set .

The statement may be a container that contains the expression and an object . In an example embodiment the object may be model elements that are related to the statement . In an example embodiment the expression may be formulated in a same language as the one or more expressions .

In an example embodiment the object may be used to provide context or type information such as the elements in the model that should be considered. In an example embodiment the object may be used to define a starting point in the instance set .

The application may receive a notification from the event framework regarding what has been changed in the model . The impact analyzer may identify a number of statements in the form of the evaluation units to be re evaluated.

In an example embodiment the instance set may be described by a particular statement that could be used to compute the instance set instead of having the instance set be a set of objects that have already been computed.

In an example embodiment the expression evaluator see FIG. may evaluate the evaluation set by accessing the evaluation set looping over the evaluation units that are in the evaluation set selecting the instance sets for each of the evaluation units computing the instance sets and then performing an evaluation of the expression for the evaluation units with the instance sets for the evaluation units in the evaluation sets .

In an example embodiment the evaluation set may include a single evaluation unit. For example the statement may be to check that a wage of an employee is not higher than the wage of a boss while the instance set may contain a starting point of a particular employee e.g. employee A and the statement that is needed to compute the relevant instances starting with the particular employee would be self. A computation may be made by determining whether the wage of the particular employee is higher than the wage of the boss.

In an example embodiment if a particular employee e.g. employee B is a boss of one or more other employees and the wage of the particular employee changes it may not be sufficient to check the wage of the particular employee against the wage of the boss of a department since the particular employee is the boss of the department. Rather a check would be made as to whether any of the employees of the department has a higher wage than the wage of the particular employee. The object of the instance set may be the particular employee and the expression that would be used to calculate all the instances may be self.employees or self.department.employees. The expression obtained for the expression evaluator would include first obtaining the instances and then evaluating the instances to determine whether the wage of the employees are lower than the wage of the boss.

Referring to a data structure for unit evaluation according to an example embodiment is illustrated. In an example embodiment the evaluation unit see may include the data structure .

The data structure may include a statement and one or more instances sets . .. The one or more instance sets . .may reflect different instances in which the statement may need to be re evaluated for a change to the model see . The statement see may be the statement . In an example embodiment the statement may be a first field in the data structure and the instance sets . .may be a second field.

Within the data structure if the statement is to be evaluated the elements in the model that may need to be considered to perform the evaluation may be a number of the instance sets . .. The instances sets . .may be used instead of actually providing references or pointers to the elements in the model .

The instance sets . .may respectively include starting points . .and navigation paths . .. The navigation paths . .may include an expression that can navigate from the starting point . .to something in the model which when traversed may collect the instances in a particular instance set . The instance sets . .may identify what should be evaluated for the statement . For example the navigation path may be an expression that provides what to compute back to the filter function see .

In an example embodiment the expression evaluator see may receive the instance sets . .. For each instance set in an evaluation unit see the expression evaluator may start at a starting point and evaluate along a navigation path .

In an example embodiment the instance sets . .may evaluate to a set of context instances that may be considered for the change to the model . For example if a change may affect o particular statement the instance sets . .associated with the statement may be evaluated to determine an impact of the change.

In an example embodiment the use of the instance sets . .instead of computing the instances may enable further optimization. For example transforming the expressions as the navigation paths into highly optimized proprietary queries in an internal query language may provide for improved performance.

In an example embodiment the use of the data structure instead of objects may enable a reduced number of instances for which an expression see may need to be evaluated.

In an example embodiment if the statement is to check a wage of an employee against the wage of his boss and a first instance set . is a starting point of a particular employee the navigation path . may be self in a programming language e.g. do not navigate beyond the starting point . . For a second instance set . the starting point . may be a boss of the employee and the navigation path . may be to collect all the employees that work in or that directly report to the boss.

In an example embodiment the navigation path . may collect all of the instances to evaluate from a particular starting point .. For example during construction of an instance set . a starting point . may be an element that has been changed and the navigation path . may be an expression that enables collection of all instances to be evaluated for the statement .

Referring to a method to register a model with a filter is shown in accordance with an example embodiment. In an example embodiment the method may operate on the impact analyzer .

At block the expressions may be accessed for the model see . For example the expressions may be received through the impact analyzer see . For example the analyze component see may be called with the expressions .

The method determines at block changes to the model that may have an effect on the expressions . For example the model change events relevant to the expressions may be matched with internal events at the block .

In an example embodiment the internal event may be used to identify event types. The event cache may store information for the event types e.g. a wage of an employee has changed and what may be received from the event framework is event instances e.g. a wage of a particular boss or a particular employee that has changed .

In an example embodiment the internal event may be a description of the event type and in event mapping the internal event may be determined from an event instance. Once an event type is known information may be accessed in the event cache . The event cache may include an expression that relates to wage such that the expression may be reevaluated when an attribute to the model changes.

At block a filter matching the changes to the model that will have an effect on the expressions may be provided. For example the filter may be provided from the impact analyzer to the application . In an example embodiment filter expressions may be generated from the matching internal events.

In an example embodiment at the block the internal events are mapped to event types that are known to the event framework to generate a filter.

In an example embodiment identified expressions may be parsed into an attribute structure reverse navigation paths may be generated and the statement see internal events and reverse navigation paths may then be associated.

Referring to a method to register a model with a filter is shown in accordance with an example embodiment. In an example embodiment the method may operate on the application .

At block the expressions see may be provided such as from the application to the impact analyzer see . In an example embodiment the expressions may be provided from the application to the analyze component see .

A filter matching changes to the model that will effect the expressions may be received at block . In an example embodiment the filter matching changes may be received by the application from the impact analyzer .

At block the filter may be registered. For example registering the filter may enable the application to subscribe to events received from the event framework . Upon completion of the block the method may terminate.

In an example embodiment the methods and may reduce a number of the expressions to be evaluated for a given modification to the model . For example the use of the methods and may result in a reduction of complexity for enforcing well formedness rules and in applying only transformations to a source model that actually result in different model elements in a target model .

Referring to a method in accordance with an example embodiment to respond to a notification is shown. In an example embodiment the method may operate on the application see .

At block a notification may be received regarding a change to a particular model see . For example the application may receive a change notification identifying events associated with a particular expression .

The method may forward the notification at block . For example the notification may be forwarded from the application to the impact analyzer .

In response to the forwarded notification identification may be received regarding the expressions and associated instances for which reevaluation should be performed at block . For example the identification may be received by the application from the impact analyzer .

Referring to a method in accordance with an example embodiment to respond to a notification is shown. In an example embodiment the method may operate on the impact analyzer .

At block a notification may be received regarding a change to a particular model see . For example the change notification may be received by the impact analyzer from the application see .

The method may identify the statements and the associated instance sets . .for which reevaluation should be performed at block see .

In an example embodiment an AST with events attached to relevant nodes may be outputted and stored the events may then be identified in the event cache and the events may be converted into the evaluation units see .

The method may provide the identification at block . For example the identification may be provided from the impact analyzer to the application . In an example embodiment providing the identification may include returning evaluation units .

Referring to an example object graph is illustrated. In an example embodiment the object graph is an object graph of an example model see .

The object graph as shown may include two departments . The department may include an employee that manages the department and three employees that work in the department . The department may include an employee that manages the department and three employees that work in the department .

Referring to an example data structure to evaluate expression is illustrated. The data structure may be an example of the data structure see given the object graph see . The OCL statement 

In an example embodiment an evaluation set may be an example of the evaluation set evaluation units may be the evaluation units a statement my be the statement an instance set may be the instance set an object may be the object an expression may be the expression an object may be the object a statement may be the statement an object may be the object and an expression may be the expression . It may be appreciated that the dependencies of the evaluation unit are not shown in this example.

Referring to a data structure for unit evaluation according to an example embodiment is illustrated. The data structure may be an example of the data structure see given the object graph see the OCL statement 

In an example embodiment a statement may be an example of the statement a first instance set may be an example of the instance set . a second instance set may be an example of the instance set . a starting point may be an example of the starting point . a navigation path may be an example of the navigation path . a starting point may be an example of the starting point . and a navigation path may be an example of the navigation path . see .

The example computer system includes a processor e.g. a central processing unit CPU a graphics processing unit GPU or both a main memory and a static memory which communicate with each other via a bus . The computer system may further include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alphanumeric input device e.g. a keyboard a cursor control device e.g. a mouse a disk drive unit a signal generation device e.g. a speaker and a network interface device .

The disk drive unit includes a machine readable medium on which is stored one or more sets of instructions e.g. software embodying any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processor during execution thereof by the computer system the main memory and the processor also constituting machine readable media.

The software may further be transmitted or received over a network via the network interface device .

While the machine readable medium is shown in an example embodiment to be a single medium the term machine readable medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term machine readable medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of the present invention. The term machine readable medium shall accordingly be taken to include but not be limited to solid state memories optical and magnetic media and carrier wave signals.

Thus a method and system for evaluating constraints associated with a model have been described. Although the present invention has been described with reference to specific example embodiments it will be evident that various modifications and changes may be made to these embodiments without departing from the broader spirit and scope of the invention. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense.

The Abstract of the Disclosure is provided to comply with 37 C.F.R. 1.72 b requiring an abstract that will allow the reader to quickly ascertain the nature of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims. In addition in the foregoing Detailed Description it can be seen that various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting an intention that the claimed embodiments require more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Detailed Description with each claim standing on its own as a separate embodiment.

