---

title: Validating function calls in source code
abstract: There is disclosed a method, apparatus and computer program for validating a function call in source code, a valid function call referencing a message in a message bundle using a message key specified in the function call, the valid function call operable to produce output using the referenced message. First a function call to validate is located. Then it is determined whether a message bundle associated with a message key specified in the function call can be located. Responsive to this being possible, an attempt is made to access the referenced message within the message bundle using the message key. An error message is output should validation of the function call fail.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07865881&OS=07865881&RS=07865881
owner: International Business Machines Corporation
number: 07865881
owner_city: Armonk
owner_country: US
publication_date: 20061026
---
In today s global market it is increasingly important for any human readable output created by computer software to be internationalised. A common mechanism used to achieve internationalisation is the use of message bundles. Rather than hard coding the human readable text a key is provided instead and this key is then used to look up the message in the associated bundle. By providing different message bundles for different languages the software becomes internationalised without the source code itself containing any text that is specific to a particular language. In addition to using a key to lookup a message a typical message bundle implementation will allow additional parameters to be provided that are then substituted into the message at defined points.

European Patent 1315086 describes a method and processing unit for providing localised versions of a software application allowing maintenance of a single code version. Text elements may be centrally maintained and handled in a text element file while the code may only include references to the individual text elements at specified locations.

A major problem with current message bundle implementations is that they are entirely reliant on the software developer specifying a message bundle correctly specifying a key that exists in the message bundle as well as the correct number of parameters to be substituted into the message. Should the developer get this wrong the end user may be presented with an obscure error code rather than the intended concise description of the solution to the problem they are experiencing. This inevitably leads to a marked decrease in customer satisfaction and an increased number of calls being made to customer support 

There are a number of known solutions to the problem of ensuring that software source code conforms to sets of configurable rules many of which have been productised such as Parasoft s JTest and IBM s Rational Application Developer 6.0. However these existing solutions are unable to cope with the inherent complexity of validating code that is internationalised through the use of message bundles they are not capable of identifying the relationship between a method call and the message bundle from which it will extract its internationalised text.

According to a first aspect there is provided a method for validating a function call in source code a valid function call referencing a message in a message bundle using a message key specified in the function call the valid function call operable to produce output using the referenced message the method comprising locating a function call to validate determining whether a message bundle associated with a message key specified in the function call can be located responsive to locating the message bundle attempting to access the referenced message within the message bundle using the message key and outputting an error message should validation of the function call fail.

Preferably to determine whether the message bundle can be located the style of API being used to produce the output is determined. Preferably it can then be determined where a component for producing the output is initialised. If it is determined that the component is initialised separately from the source code then it is preferably identified where the initialisation took place e.g. in another source code file . It is then preferably possible to attempt to load the source code in which the component being used to produce the output is initialised.

To identify where the initialisation took place e.g. either in the source code itself or separately the source code may be examined to determine how the component is referenced and such information can then be used to determine in which source code file initialisation took place. For example the component may simply be referenced by a shortname that is then qualified by a source code import statement. Alternatively there may be no relevant import statements and associated files may instead have to be searched for the component e.g. those in the same package .

In a preferred embodiment the name of the message bundle is determined based on knowledge of the style of API. E.g. configuration information may indicate that the name of the message bundle is always provided to a component using a particular style of API as the second parameter 

If the name of the message bundle is provided as a string then an attempt is preferably made to access the message bundle using this string.

If on the other hand the name of the message bundle is provided as a reference to a variable then the name of a field being accessed and from where that field is accessed e.g. the class is preferably determined. An attempt is then made to load the source code in which the component is initialised. Once the source code has been loaded the name of the message bundle is then preferably determined and an attempt is then made to access the message bundle.

If it is not possible to load the source code in which the component is initialised then the binary version of the source code in which the component is initialised is preferably loaded. If the name of the message bundle is provided as a static value then the message bundle name can preferably be retrieved. If the name is provided dynamically then the binary version is preferably executed to retrieve the name of the message bundle.

In a preferred embodiment once a referenced message has been accessed then any source code provided inserts for the message are validated.

In accordance with a preferred embodiment to validate any source code provided inserts for the message it is determined if there is a mismatch between the number of inserts provided and the number of inserts required by the referenced message.

Preferably each provided insert and required insert has an associated type and this is used to determine whether the provided insert type and the required insert type match.

Preferably the message has meta data associated therewith detailing the type of each required insert.

According to a second aspect there is provided an apparatus for validating a function cast in source code a valid function call referencing a message in a message bundle using a message key specified in the function call the valid function call operable to produce output using the referenced message the apparatus comprising means for locating a function call to validate means for determining whether a message bundle associated with a message key specified in the function call can be located means responsive to locating the message bundle for attempting to access the referenced message within the message bundle using the message key and means for outputting an error message should validation of the function call fail.

According to a third aspect there is provided a computer program for validating a function call in source code a valid function call referencing a message in a message bundle using a message key specified in the function call the valid function call operable to produce output using the referenced message the computer program comprising program code means adapted to perform the following method when the program is run on a computer locating a function call to validate determining whether a message bundle associated with a message key specified in the function call can be located responsive to locating the message bundle attempting to access the referenced message within the message bundle using the message key and outputting an error message should validation of the function call fail.

Disclosed is a mechanism by which any message bundle keys contained in a product s source code can be automatically validated to ensure that they correctly map to a message in an associated message bundle and if so that the correct number of parameters has been supplied for that message.

The feature that underpins this mechanism is its ability to understand the relationship between code that supplies message bundle keys and parameters and the message bundle itself. This relationship is not straightforward as the identity of the message bundle that is used by a particular call may not be defined locally in some cases the message bundle s identity Is specified in an entirely separate source file. This will be addressed in more detail later.

Some source code contains a number of function calls each of which should result in the output of an internationalised message e.g. an error message . The invention in accordance with a preferred embodiment provides a mechanism for testing that such function calls do indeed produce the intended output.

Thus at step a configuration file is accessed configuration file accessor to identify those function calls that need to link to a message bundle so as to return and output an appropriate message. Such functions may by way of example be tracing functions e.g. trace.warning trace.error trace.info trace.audit and trace.severe .

At step the list of functions are identified function call identifier . The source code is then parsed into an Abstract Syntax Tree AST by parser component step to locate any of the identified function calls within the code step .

At step the configuration file is accessed again configuration file accessor and is used to determine which parameter within the source code is the message key step . For example the configuration file may indicate that for the trace.warning call the message key is the second parameter.

Thus as indicated above an understanding of the API in question is used to locate the appropriate message bundle. For example In the case of the java.util.logging API the message bundle is supplied as a parameter when the Logger object is being created 

In this case the message bundle accessor knows that as an instance named logger is being used to output the translated message it must look to where it was initialised to determine the name of the message bundle that is to be used.

By way of another example an alternative API may specify the message bundle on a call to a factory that creates the object used to output internationalised messages as illustrated in the following code snippet 

The message bundle accessor knows that as tc is being used in the info call it must took to where tc was initialised to determine the name of its message bundle. Having determined the message bundle s name it can then given an understanding of the code s classpath load the bundle and check that there is a message in the bundle for the key ABC that takes a single parameter.

Note in spite of all of the above it may not be possible to locate the message bundle it may not exist step . In which case an error message is output step .

If however the message bundle can be located the message bundle accessor component attempts to access the relevant message using the message key step . At step a test is performed to determine whether the requested message key exists. If no such key exists then an appropriate error message is output at step error message outputter .

If on the other hand the message key is a valid one then the message bundle accessor retrieves a message requiring n inserts step . For example the message might be An error has occurred in function 0 on 1 2 of 3 . With such a message four inserts are sought. The number of inserts required can be determined from the referenced message itself.

A test is performed at step to determine whether the number of inserts provided as part of the source code function call m matches the required number of inserts n . The configuration file is used to determine which of the parameters provided by the function call are to be classed as inserts . For example one should be the message key as described above and so this parameter is not classed as an insert.

If the answer is no then an informative error message is output by the error message outputter component step .

If the correct number of inserts are provided in the source code then it is determined whether the provided inserts m are of the right type step . Each provided insert will have an associated type e.g. char nt float or a newly defined type and each message preferably has meta data associated therewith that denotes a type for each required insert. For example a retrieved message may be An error has occurred in function 0 function name on 1 day 2 number of 3 month. In this example function name day number and month is the type information. Each type has a type definition that is preferably defined in a type database not shown . For example type name function name which is a char 8 type name day which may be any one of Monday Tuesday Wednesday Thursday Friday Saturday Sunday etc.

Type checking is performed by type checker component . If there are any inconsistencies then an informative error message is output step .

If on the other hand the provided insert types match the expected insert types then the function call is validated step and processing moves to identify and validate the next function call in the abstract syntax tree.

A typical implementation of the invention would be as an extension to an integrated development environment IDE as a plugin. The implementation would typically provide a number of default relationships for the various logging APIs that are commonly used allowing the user to quickly and easily configure it for use in their development project.

Whilst the invention has been described in terms of the use of message bundles in the process of internationlising software the invention is not limited to such. The invention is applicable to the validation of any software using message bundles in other ways.

Further whilst the location of a message bundle has been described in terms of object oriented technology no limitation is intended. It is equally possible in the procedural programming environment.

