---

title: Method and device for managing applications of a mobile terminal
abstract: A method and system for managing a set of applications stored on a mobile terminal, comprising an access to said set of applications enabling at least one specific function to be accessed by at least one application using an application manager.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08781529&OS=08781529&RS=08781529
owner: NXP B.V.
number: 08781529
owner_city: Eindhoven
owner_country: NL
publication_date: 20061016
---
This is a U.S. National Phase Application under 35 USC 371 of International Application PCT FR2006 051036 filed on Oct. 16 2006.

This application claims the priority of French application no. 05 10575 filed Oct. 17 2005 the entire content of which is hereby incorporated by reference.

The invention relates to mobile telecommunications and more particularly to managing applications in a mobile terminal.

At present users of mobile telephone or smart phone type mobile terminals are confronted with an ever richer offer of services. Over and above standard telephone services users are offered diverse and varied services such as messaging audio and video streaming games content downloading calendar etc. These services are accessible locally on the mobile terminal via a mobile network GSM GPRS UMTS etc. or via a near field connection for example using exchange protocols such as IrDA Bluetooth or RFID.

These services rely on applications that are stored either directly in the mobile terminal or in microchip cards or smart cards. A service can call on one or more applications.

For example in the Java system an application in the mobile terminal corresponds to a mobile information device profile applet MIDlet i.e. a Java application that can be executed on a Java mobile. Thus the presentation part e.g. Java MIDlet that manages the man machine interface MMI of the application is specific to the mobile terminal on which it is executed. It is responsible for the graphical interface of the application and for managing access to certain resources of the mobile terminal or network for example GSM call set up WAP server connection SMS message sending etc. . Note that a MIDlet is generally a specific applet which does not require integrating a new application into the mobile terminal.

Moreover when an application is in a smart card type microchip card it corresponds to a Cardlet Java Card applet . Under such circumstances the business part which manages the application data e.g. the Java Cardlet can be stored either in a SIM card of the mobile terminal or in a dedicated component for example a Smart MX component.

It is important to note that the deployment and management of these applications also referred to as cards have not been standardized and so different card providers offer their own solutions . in particular in terms of management. Thus from the user s point of view the multiplicity of cards or applications increases the complexity of managing the applications.

One aspect of the present invention provides a method of managing a set of applications stored in a mobile terminal including access to said set of applications enabling at least one application of said set to access a particular function by means of an applications manager. By application set is meant one or more applications.

Thus the method of the invention offers unique access to a plurality of applications stored in the mobile terminal.

According to a first feature of the invention the method further includes storing information relating to said at least one application in storage means.

Thus a list of applications installed in the mobile terminal and any other information relating to those applications can be accessed simply and quickly.

According to a second feature of the invention the method further includes storing in a transaction log information relating to transactions effected via the mobile terminal by the user.

According to a third feature of the invention the method further includes administration by a security module of security data relating to said at least one application.

To provide a particular service said at least one application advantageously recovers parameters relating to said at least one application from the applications handler.

Thus the method of the invention offers mobile terminal users an overview enabling them to access simply and quickly services corresponding to the plurality of applications installed in the mobile terminal.

Thus this method recovers manages and displays information relating to applications in a simple and intuitive way.

Another aspect of the invention is directed to a system for managing a set of applications stored in a mobile terminal including an applications handler comprising access means to said set of applications enabling at least one application of said set to access a particular function.

According to one feature of the invention the applications handler comprises storage means for storing information relating to said at least one application.

According to another feature of the invention the applications handler comprises a transaction log for storing information relating to transactions effected by users via their mobile terminal.

According to a further feature of the invention the applications handler comprises a security module for administering security data relating to said at least one application.

The system advantageously includes a centralized applications manager connected to the applications handler for generating a unified view of said set of applications.

Another aspect of the invention is directed to a mobile terminal including a management system with the above features.

Another aspect of the invention is directed to a computer program including code instructions for executing the method having the above features of managing a set of applications stored in a mobile terminal when the program is executed by the management system of the mobile terminal.

Furthermore shows that the applications handler includes storage means also referred to as the applications repository and where appropriate a transaction log and a security module .

Thus the storage means store information relating to any application already installed in the mobile terminal or any new application to be integrated into the mobile terminal. For example the storage means can include a list of applications installed in the mobile terminal and parameters associated with each of those applications . An application can be managed by the applications handler when it is stored in the storage means .

The transaction log stores information relating to transactions effected by the user via the mobile terminal. That information can include transaction start and end times of day and the result of the transaction.

Likewise the security module administers security data including security keys and codes relating to any application for example.

More particularly the centralized applications manager includes a graphical user interface GUI and a connector . This connector which can take the form of a Java MIDlet is used to exchange information relating to said at least one application between the graphical user interface and the applications handler . It recovers and updates information relating to the applications . This connector therefore effects protocol adaptation using protocols based for example on Java Specification Request 177 Security and Trust Services API for J2ME to dialogue with a SIM card or based on Java Specification Request 257 Contactless Communication API to manage contactless communication.

The graphical user interface of the centralized applications manager therefore offers the user the graphical interfaces needed to manage the applications and to construct a unified view of those applications . This view is constructed by the connector in conjunction with the applications handler which offers a set of particular functions.

In this example the access means of the applications handler offer said at least one application or the centralized applications manager at least one particular function from a set of particular functions including 

The storage means can include for a given application the index of the application the identifier of the application the name of the application the PIN protection state of the application for example a true state signifies obligatory PIN verification and a false state signifies no PIN verification and the activation state of the application for example a true state signifies an activated and therefore usable application and a false state signifies a deactivated and therefore unusable application .

The transaction log can contain information on all transactions effected by the user via the mobile terminal. A record of a transaction can be defined by the identifier of the application and significant data of the transaction for example the transaction start time of day the transaction end time of day the amount of credit used the amount of credit remaining the result of the transaction etc. .

Moreover the security module contains and administers the security code s e.g. PIN s of the applications the maximum number of attempts authorized before blocking the number of successive failed attempts and the PIN unblocking key PUK .

Thus the applications handler can manage the parameters of the applications name activation flag etc. storing the applications and the record of transactions relating to the use of the applications . It also offers business data consultation functions specific to each application security parameter PIN security code verification PIN unblocking management functions activation flag reading functions or transaction storage functions. In other words the applications handler knows the applications installed in the mobile terminal and their parameter settings.

The centralized applications manager in conjunction with the applications handler enables users to list all applications available to them to list information in the sense of business data relating to a particular application to select a particular application and look up its parameter settings entry of code obligatory or not application activated etc. to consult the list of the latest transactions effected using an application and to set application parameters modify PIN activate an application deactivate an application activate PIN protection etc. In other words the centralized applications manager can manage construct and display a unified view of the applications available on users mobile terminals.

Moreover when the applications are executed in the mobile terminal they render a set of services to the user. Execution of an application can be linked to another application or to a system external to the terminal for example activation of a Cardlet by a local external reader for a service payment service . Any application installed and operational in the mobile terminal is necessarily known to and registered with the applications handler . Thus the applications handler stores any new application in the storage means of the manager system for the applications of the mobile terminal.

Moreover to provide a particular service the corresponding application recovers from the applications handler parameters related to that application in order to render a service to the user.

This diagram shows a Java mobile terminal including a communication baseband module providing the basic functions of the mobile terminal a subscriber identification module SIM an adaptation and mapping layers AML module a near field communication NFC module an antenna and a Smart MX card component .

The Smart MX card component is a smart card controller combining DES Data Encryption Standard or RSA Rivest Shamir Adleman coprocessors and enabling implementation of operating systems OS such as Java Open Platform. It also has ISO 14443 or ISO 7816 interfaces and stores Java Card applications Cardlet Assistant and partner applications Cardlets Partner and the relevant data. The Smart MX component also includes an open platform operating system based on the JCOP Java Card Open Platform standard.

Thus the applications handler corresponds to the Cardlet Assistant and takes the form of a Java Card application also known as a Cardlet which comprises four sub elements corresponding to the access means the storage means the transaction log and the security module . The applications handler is resident in the Smart MX card component .

Moreover the applications correspond to Java Card Java applications known as Cardlets Cardlets Partner stored in the Smart MX card component .

The communication baseband module includes a man machine interface MMI native to the mobile terminal a Java applications module and a Java Micro Edition component .

The Java applications module includes a Card Summary Java MIDlet that corresponds to the centralized applications manager . Thus including the graphical user interface and the connector this Java MIDlet offers the user a unified view of the applications Cardlets .

The Java 2 Micro Edition component comprises all the elements necessary for executing Java MIDlets in the mobile terminal . Thus it comprises a virtual machine and the application programming interfaces API necessary for executing MIDlets and the API for dialogue with the subscriber identification module SIM card the Java applications available on the Smart MX card component or the near field communication NFC module of the mobile terminal .

The adaptation and mapping layers AML module comprises various abstraction adaptation and mapping layers enabling communication between the communication baseband module and in particular the MIDlets the Smart MX card component and the near field communication NFC module of the mobile terminal .

The near field communication module enables near field communication via the antenna between the mobile terminal and an external reader or an RFID radio frequency identification tag. The near field communication module also enables communication between the centralized applications manager Card Summary and the applications handler Cardlet Assistants and the applications Cardlet Partners .

Where appropriate the subscriber identification module SIM card can contain Cardlet applications represented in dashed line .

The management system includes one or more computer programs including code instructions for executing the management method of the invention when executed by the various elements of the system for managing applications in a mobile terminal.

Following a request for the selection of a particular application from the user via the man machine interface steps E E the graphical user interface of the centralized applications manager forwards the request to the connector step E which then recovers via the access means of the applications handler 

The connector forwards all this information to the graphical user interface step E which forwards it to the man machine interface step E where the information including the list of the latest transactions the activation state and PIN protection state corresponding to the application are displayed on the man machine interface step E .

To optimize the access and processing time for future operations some or all of this information can be stored in the connector . Under such circumstances subsequent invoking of the access means of the applications handler is no longer systematic.

If a security code e.g. a PIN is required the user enters their PIN via the man machine interface step E . This PIN is then forwarded to the access means of the applications handler via the centralized applications manager including the graphical user interface and the connector steps E to E . The verification is effected by the security module step E which in the event of an error increments a counter that counts the number of consecutive incorrect PINs. The security module forwards the verification state true false to the man machine interface via the access means the connector and the graphical user interface steps E to E .

If the number of incorrect PIN attempts is reached the application and the PIN are blocked. Unblocking can be effected only by a human operator. Only an external security system can unblock PUK the PIN step E in the access means of the applications handler . Note that any failure during this phase permanently blocks the PIN. In the step E the access means forward the unblocking code to the security module that effects the verification and in the event of a positive verification result unblocks the PIN it then forwards the verification state true false to the access means step E which in turn forward it step E to the external security system .

In this example the user requests a list of applications from the man machine interface of the mobile terminal steps E E . This operation can equally be effected by the graphical user interface to update or refresh the existing list. For this purpose the graphical user interface calls up a list of applications available or installed in the mobile terminal from the access means via the connector steps E E . The access means call on the storage means steps E . In return the man machine interface recovers a list of available applications in the form of a list containing at least the names and indices of those applications steps E E . That list is then available at the man machine interface step E .

When modifying the PIN for a particular application the user sends the identifier of the application via the man machine interface at the same time as the old and new PINs step E . A PIN must be verified before updating it globally or otherwise .

Following the request by the user to change the PIN the graphical user interface receives the message from the man machine interface step E and forwards to the access means of the applications handler via the connector steps E E the new PIN the old PIN and when updating the PIN of an application the identifier of that application. The security module receives the message step E and then verifies the validity of the PIN on the basis of the old PIN and then with a positive result proceeds to update the PIN using the new PIN that has been sent. The result of modifying the PIN yes no is sent via the security module to the man machine interface via the elements and respectively steps E to E .

Following a request by the user via the man machine interface to activate an application step E the graphical user interface receives the message from the man machine interface step E and sends the access means of the applications handler via the connector an identifier of the application and an activation variable set to true steps E E . If the application had been deactivated its activation is then stored in the storage means step E . If not an error message is sent back for display on the man machine interface of the mobile terminal. In any event the storage means send the activation result true false to the man machine interface via the elements and respectively steps E to E .

Following a request for deactivation of an application from the user via the man machine interface step E the graphical user interface receives the message from the man machine interface step E and sends the access means of the applications handler via the connector steps E E an identifier of the application and an activation variable set to false. If the application had been activated its deactivation is then stored in the storage means step E . If not an error is sent back for display on the man machine interface of the mobile terminal. In any event the storage means send the deactivation result true false to the man machine interface via the elements and respectively steps E to E .

Following a request to activate an application a list of applications or all applications from the user via the man machine interface step E the graphical user interface receives the message from the man machine interface step E and sends the activation request via the connector to the access means of the applications handler steps E E . The absence of parameters indicates that the activation applies to all applications. The request to activate one or more applications contains a list of applications to be protected. In both situations the request contains a protection activation variable set to true. The request is then processed by the storage means step E which verifies the possibility of activation function already activated non existing application etc. before execution. The storage means send the activation result true false to the man machine interface via the elements and respectively steps E to E .

Following a request from the user via the man machine interface for deactivation of an application a list of applications or all applications step E the graphical user interface receives the message from the man machine interface step E and forwards the deactivation request via the connector to the access means of the applications handler steps E E . The absence of parameters indicates that the activation applies to all the applications. The deactivation request for one or more applications contains a list of applications that are no longer to be protected. In both situations the request contains a protection activation variable set to false. The request is then processed by the storage means step E which verify if activation is possible function already deactivated non existing application etc. before execution. The storage means send the deactivation result true false to the man machine interface via the elements and respectively steps E to E .

Steps E to E recover the activation state of an application. The graphical user interface recovers the activation state of an application based on its identifier or its index from the access means of the applications handler via the connector . The request is processed by the storage means which send back the activation state activated deactivated of the application.

Thus the graphical user interface sends this request via the connector to the access means of the applications handler steps E E . The request is then processed by the storage means step E which sends the activation state activated deactivated to the graphical user interface via the elements and respectively steps E to E .

Steps E to E recover the code protection state of the application. The graphical user interface recovers from the access means of the applications handler via the connector the code e.g. PIN protection state of an application based on its identifier or its index. The request is processed by the storage means which send back the code e.g. PIN protection state activated deactivated of the application.

Thus the graphical user interface sends this request via the connector to the access means of the applications handler steps E E . The request is then processed by the storage means step E which sends the activation state activated deactivated to the graphical user interface via the elements and respectively steps E to E .

Steps E to E recover a list of the transactions of an application on the basis of its name or its index. Thus the graphical user interface sends this request via the connector to the access means of the applications handler steps E E . The request is processed by the transaction log step E which then sends the list of the latest transactions for the application to the graphical user interface via the elements and respectively steps E to E .

Steps E to E recover the identifier of an application . Thus the graphical user interface sends this request via the connector to the access means of the applications handler steps E E . The request is processed by the storage means step E which then sends the unique identifier of the application to the graphical user interface via the elements and respectively steps E to E .

Following a request from the user via the man machine interface for display of the business data related to an application steps E E the graphical user interface recovers on the basis of the identifier of the application a list of this data directly from the application via the connector of the centralized applications manager steps E to E . The application must first have been selected by the connector steps E . If the application does not exist non existent identifier an unknown application message can be displayed on the man machine interface .

Alternatively business data of an application can be recovered via the access means of the applications handler .

Steps E to E read the activation flag of the application . Prior to any use of a service reading the application flag step E determines if the application associated with the service in the user s mobile terminal is activated or not. Accordingly the access means of the applications handler consult the storage means holding that information step E . The storage means send the activation state true false to the application steps E E .

Steps E to E read the PIN activation flag. Prior to use of a service reading the PIN activation flag step E determines if a PIN verification phase is required. Thus the access means of the applications handler consult the storage means holding that information step E . The storage means send the PIN activation state true false to the application steps E E .

Steps E to E recover the PIN step E that enables an authorized application to recover the PIN of the user for the application concerned. Thus the access means of the applications handler consult the security module holding that information step E . The security module sends the requested PIN to the application steps E E .

Steps E to E store a transaction. At the end of provision of a service the application stores the transaction in the transaction log via the access means of the applications handler steps E E . During this phase the application specifies its identifier or its index and information constituting the transaction. That information preferably includes the identifier of the user the transaction type the transaction state yes no the time of day supplied by the application the duration and if necessary the amount.

