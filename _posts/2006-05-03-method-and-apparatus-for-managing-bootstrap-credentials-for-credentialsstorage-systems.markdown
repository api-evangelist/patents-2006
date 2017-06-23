---

title: Method and apparatus for managing bootstrap credentials for credentials-storage systems
abstract: One embodiment of the present invention provides a system that facilitates accessing a credential. During operation, the system receives a request at a credentials-storage framework (CSF) to retrieve the credential. If a target credential store containing the credential is not already connected to the CSF, the system looks up a bootstrap credential for the target credential store in a bootstrap credential store, which contains bootstrap credentials for other credential stores. Next, the system uses this bootstrap credential to connect the CSF to the target credential store. Finally, the system retrieves the credential from the target credential store, and returns the credential to the requestor.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08220033&OS=08220033&RS=08220033
owner: Oracle International Corporation
number: 08220033
owner_city: Redwood Shores
owner_country: US
publication_date: 20060503
---
The present invention relates generally to mechanisms for providing security within computer systems. More specifically the present invention relates to a method and apparatus for managing bootstrap credentials for credentials storage systems.

Middle tier applications running on top of application servers typically need to communicate with Enterprise Information System EIS tiers to access application specific information related to end users. To facilitate these communications middle tier applications typically store end user credentials in back end systems such as RDBMS LDAP servers.

However this type of solution is incomplete because bootstrap credentials for credentials storage systems still need to be managed. One common way to resolve this problem is to prompt the administrator for the credentials storage system to obtain bootstrap credentials during system startup. However in cases where the administrator is not present for example in cron jobs or in restart scenarios this is not a viable option. Another common way to resolve this problem is to store the bootstrap credentials in a local configuration file of the credentials storage system. For example a bootstrap credential can be stored in an XML file that contains the host port and username password of the backend system. However this solution begs the question of how to secure these all important bootstrap credentials when they are stored in such local files.

Hence what is needed is a method and apparatus that facilitates securely storing bootstrap credentials for a credentials storage system without the above described problems.

One embodiment of the present invention provides a system that facilitates accessing a credential. During operation the system receives a request at a credentials storage framework CSF to retrieve the credential. If a target credential store containing the credential is not already connected to the CSF the system looks up a bootstrap credential for the target credential store in a bootstrap credential store which contains bootstrap credentials for other credential stores. Next the system uses this bootstrap credential to connect the CSF to the target credential store. Finally the system retrieves the credential from the target credential store and returns the credential to the requestor.

In a variation of this embodiment the system performs authorization checks to verify that the requestor is authorized to receive the credential prior to retrieving the credential for the requester.

In a variation of this embodiment looking up the bootstrap credential in the bootstrap credential store involves first asserting a privileged mode and then while in privileged mode looking up the bootstrap credential in the bootstrap credential store.

In a variation on this embodiment during the lookup process the bootstrap credential store receives a request to perform the lookup. In response to this request the bootstrap credential store determines whether the request is being made while the CSF is operating in privileged mode and also checks a policy to determine whether the code that is making the request is authorized to make the request. If the CSF is operating in privileged mode and the request is consistent the policy the bootstrap credential store retrieves the bootstrap credential and returns the retrieved bootstrap credential to the CSF.

In a further variation while determining whether the code that is making the request is authorized to make the request the system asks a class loader to examine a signature on the code.

In a further variation upon receiving the request the system identifies the target credential store by looking up a configured credential provider for the requestor.

In a further variation communications between the CSF and the target credential store take place through a standardized service provider interface SPI which can be used to communicate with many different types of credential stores.

In a variation of this embodiment the credential can include a user name and password a token or a digital certificate.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not intended to be limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to magnetic and optical storage devices such as disk drives magnetic tape and CDs compact discs and DVDs digital versatile discs or digital video discs.

One embodiment of the present invention provides a credentials storage framework CSF which accesses a bootstrap credential store to obtain bootstrap credentials for other credential stores. Instead of storing the bootstrap credential for a given credential store in a configuration file or prompting the user every time the application server starts up the system stores the bootstrap credentials in a bootstrap credential store which can be implemented as an encrypted wallet. Note that the system manages correlations between credential stores and associated bootstrap credentials internally within CSF thereby eliminating the need to store the bootstrap credentials and related metadata in a configuration file.

An advantage of this solution over the other common alternatives such as prompting an administrator or storing bootstrap credentials in a configuration file is that the solution provides more security. Another advantage of this solution is that it avoids the need for an administrator to always be present to facilitate secure failure restarts for the system.

One disadvantage of this solution is that some amount of overhead is involved in creating managing a bootstrap credential store to serve other credential stores. However this disadvantage is mitigated by the fact that the number of bootstrap credentials should be relatively small.

Hence one embodiment of the present invention provides a mechanism for managing bootstrap credentials for credential stores in a reasonably secure and efficient manner without sacrificing usability or functionality. This in turn facilitates building secure highly available and feature rich middle tier apps such as portals and business intelligence applications. One embodiment of the present invention is described in more detail below.

Application typically needs to present credentials to obtain access information contained within entities in EIS tier . For example as is illustrated in application uses credentials and to access database file system and application respectively. These credentials can generally include any type of credential such as a user name and password a token or a digital certificate. Furthermore the credentials can be associated with different entities such as an end user or an application.

Hence one embodiment of the present invention allows an application to be developed against a lightweight credential store mechanism and then deployed to a production test environment where a directory based credential store mechanism is deployed.

To enable this type of pluggability a standard provider interface such as a service provider interface SPI is provided to facilitate plugging in third party credential store implementations.

Referring to a number of entities such as a resource adapter and application or an OC4J J2EE server interact with CSF API . At the same time a number of different types of credential stores and interact with SPI . In additional to credential stores a bootstrap credential store also interacts with SPI . Note that bootstrap credential store can be implemented as an encrypted wallet.

In response to the request the CSF performs authorization checks to verify that the calling application in this case the portlet is authorized to receive the requested credential step . While making these authorization checks the CSF can consult a security subsystem to see if the calling application the portlet is authorized to make the call. For example these authorization checks can involve consulting a security policy a classloader and a public key infrastructure PKI .

These authorization checks can based on a caller identity which is the identity of the authenticated principal end user that originally made the request say via a browser to the portlet. Note that the calling application the portlet must first authenticate the user prior to calling the CSF unless the calling application is a system application that does not operate within a caller context. The authorization checks performed by the CSF can also be based on the caller code which is the code portlet that is making the CSF.getCredentials call.

If the CSF determines that the either the caller identity or the caller code is not trusted the CSF returns a failure to the calling application.

On the other hand if the CSF ascertains that both the caller identity and the caller code are trusted the CSF proceeds to invoke the underlying credential store implementation. In doing so the CSF first identifies a target credential store by looking up a configured credential provider for the user or application step .

Next the system determines whether the target credential store is already connected to the CSF step . If so the CSF retrieves the desired credential from the target credential store step .

If not the CSF asserts privileged mode step and looks up a bootstrap credential for the target credential store in the bootstrap credential store step . Next the CSF uses the bootstrap credential to connect the CSF to the target credential store step and retrieves the desired credential from the target credential store step .

Finally the system returns the desired credential to the requester which in this case is the portlet step . The portlet can then use this credential to access application specific information for example information related to the user from the credential store.

First the bootstrap credential store receives a request to perform a lookup step . Upon receiving the request the bootstrap credential store first determines if the request is made in privileged mode step . If not the system returns a failure step .

Otherwise if the request was made in privileged mode the system asks a class loader to examine a signature on the code which in this case is the code for the CSF to determine whether the use of the code is consistent with a configured policy for the bootstrap credential store steps and . If not the system returns a failure step .

Otherwise if the code is consistent with the policy the bootstrap credential store retrieves the requested bootstrap credential step and then returns the bootstrap credential to the requester which is this case is the CSF step .

The foregoing descriptions of embodiments of the present invention have been presented for purposes of illustration and description only. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

