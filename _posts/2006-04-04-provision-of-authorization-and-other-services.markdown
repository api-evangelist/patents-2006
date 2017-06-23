---

title: Provision of authorization and other services
abstract: Methods, apparati, and computer-readable media for providing authorization and other services. In a preferred embodiment, an authorization service includes both a messaging specification and a set of rules that govern its use. A first customer wishing to use the authorization service prepares a request that complies with the service's messaging specification and transmits it to a first participant. The first participant transmits the request to a second participant, which processes the request according to authorization information provided by a second customer and rules that have been specified for the service. The second participant then prepares a response that complies with the service's messaging specification.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08892475&OS=08892475&RS=08892475
owner: Identrust, Inc.
number: 08892475
owner_city: San Francisco
owner_country: US
publication_date: 20060404
---
This patent application is a continuation of U.S. patent application Ser. No. 09 950 059 filed Sep. 10 2001 now U.S. Pat. No. 7 072 870 which patent application claims priority upon U.S. provisional patent application Ser. No. 60 231 313 filed Sep. 8 2000 entitled Authorization Credential Service and Authorization Credential Service Proposal U.S. provisional patent application Ser. No. 60 231 315 filed Sep. 8 2000 entitled Authorization Credential Service Proposal and U.S. provisional patent application Ser. No. 60 231 318 filed Sep. 8 2000 entitled Authorization Credential Service all four of which patent applications are hereby incorporated by reference in their entireties into the present patent application.

The world of electronic commerce has created new challenges to establishing relationships between contracting parties. One of those challenges springs from the fact that the parties to the transaction cannot see or hear each other and cannot otherwise easily confirm each other s identity and authority to act.

One remedy for this problem is to provide each contracting party with a private key for signing transmitted messages. The signing party makes available an associated public key that decrypts messages signed with the party s private key and thus enables a receiving party to confirm the identity of the sender.

But the sender s public key may not be known a priori to the recipient. In that event the sender may transmit with its signed message a digital certificate issued by a certification authority. The certificate is itself a signed electronic document signed with the private key of the certification authority certifying that a particular public key is the public key of the sender.

In some cases the recipient may be unfamiliar with the public key of the certification authority or may not know whether the certificate is still valid. In that event the recipient may wish to check the validity of the certificate. In addition the recipient may wish to check whether or not the sender is authorized to sign the transmitted message.

Methods apparati and computer readable media for providing authorization and other services. In a preferred embodiment these services are provided within the context of a four corner trust model. The four corner model preferably comprises a subscribing customer sometimes referred to as the buyer and a relying customer sometimes referred to as the seller who engage in an on line transaction.

In a preferred embodiment the subscribing customer is a customer of a first financial institution referred to as an issuing participant. The issuing participant acts as a certification authority for the subscribing customer and issues the subscribing customer a hardware token including a private key and a digital certificate signed by the issuing participant.

In a preferred embodiment the relying customer is a customer of a second financial institution referred to as the relying participant. The relying participant acts as a certification authority for the relying customer and issues the relying customer a hardware token including a private key and a digital certificate signed by the relying participant. The system also includes a root entity that maintains a root certification authority that issues digital certificates to the issuing and relying participants.

The present system provides a generalized framework for designing and implementing one or more authorization services that may be used to confirm the authority of an individual to act on behalf of a customer. Such authorization services may be used for example to determine whether a particular employee is authorized to purchase certain goods negotiate a particular contract or undertake to perform in a particular manner on behalf of its employer.

In a preferred embodiment authorization services in the present system may be designed and implemented in accordance with the following process. First a customer and its participant work together to define a desired authorization service. The authorization service definition preferably includes both a messaging specification for the service and a set of rules that govern its use as described in more detail below.

Second the proposed authorization service is presented to a policy management authority maintained by the root entity for approval. The policy management authority reviews the proposed authorization service for compliance with system operating rules and specifications promulgated by the root entity.

Third if the proposed authorization service is approved by the root entity policy management authority the service is implemented within the four corner model.

When a relying customer wishes to utilize an approved authorization service it prepares an authorization request that complies with the service s messaging specification and transmits the request to its relying participant.

The relying participant transmits the request to the issuing participant which processes the request in accordance with authorization information provided by the subscribing customer as well as any implementation rules that have been specified for the service. The issuing participant then prepares an authorization response that complies with the service s messaging specification and transmits the response to the relying participant. The relying participant transmits the authorization response to its relying customer.

The features and advantages described in the specification are not all inclusive and many additional features and advantages will be apparent to one of ordinary skill in the art in view of the drawings specification and claims hereof.

The present disclosure relates to a system and method for providing authorization and other services. In a preferred embodiment these services are provided within the context of a four corner trust model. A preferred embodiment of a four corner model suitable for use in the present system is shown in .

As shown in the four corner model preferably comprises a first institution and a second institution . First institution is referred to as the issuing participant because it is a participant in the present system and issues to its customers tokens that include a private key and a digital certificate signed by the issuing participant as described below. Second institution is referred to as the relying participant because it is a participant in the present system and its customers rely on representations made by issuing participant and issuing participant s customers as described below. Participants may preferably be banks or other financial institutions.

Also shown in are a first customer and a second customer . First customer and second customer are preferably customers of issuing participant and relying participant respectively. First customer is referred to as the subscribing customer because this customer subscribes to services provided by issuing participant . First customer is also sometimes referred to as the buyer because it typically fills that role in transactions with second customer as described below.

Second customer is referred to as the relying customer because it relies on representations made by both issuing participant and subscribing customer . Second customer is also sometimes referred to as the seller because it typically fills that role in transactions with first customer as described below. It should be recognized however that although the description below speaks primarily in terms of a buyer and a seller first customer and second customer may instead have different roles in a given transaction. For example first customer may be a borrower repaying a loan to second customer .

As will be recognized although the preferred embodiments described below speak primarily in terms of customer acting as a subscribing customer and customer acting as a relying customer the roles of these two customers may at times be reversed even within a single transaction and with respect to a single document. For example in connection with a particular transaction customers may prepare a contract to be signed by both parties. With respect to customer s signature on the contract customer is the subscribing customer and customer is the relying customer. By contrast with respect to customer s signature on the contract customer is the subscribing customer and customer is the relying customer.

It should also be noted that each customer may be a business entity such as a corporation that employs many individuals. In such cases customers preferably authorize some or all of these individual employees to transact and utilize system services on their behalf. Issuing participant preferably issues a separate smartcard token having a distinct private key and associated digital certificate to each authorized employee of subscribing customer . Similarly relying participant in its capacity as issuing participant to relying customer preferably issues a separate smartcard token having a distinct private key and associated digital certificate to each authorized employee of relying customer . The digital certificates preferably include the individual employee s name and identify the customer for whom he or she works. In an alternative embodiment the private key may instead be included in a software token provided to the individual.

It should be recognized that although the description that follows may speak in terms of messages or other data being signed by a subscribing customer or relying customer the signature may in fact typically be created by an individual employee using his or her digital certificate and associated private key acting on behalf of his or her employer.

Also shown in is a root entity . Root entity is preferably an organization that establishes and enforces a common set of operating rules for facilitating electronic commerce and electronic communications. Root entity may be owned jointly by a plurality of banks and or other financial institutions that have agreed to adhere to these operating rules. One exemplary embodiment of such a root entity is described in copending U.S. application Ser. No. 09 502 450 filed Feb. 11 2000 entitled System and Method for Providing Certification Related and Other Services and in copending U.S. application Ser. No. 09 657 623 filed Sep. 8 2000 entitled System and Method for Providing Certificate Related and Other Services which are hereby incorporated by reference.

Root entity is also preferably provided with a central repository . Central repository is preferably adapted to store data such as for example messaging specification and other data as described in more detail below.

Participants and are each preferably provided with a directory . Directory is preferably adapted to store data such as for example credential records and messaging specification data as described in more detail below.

Subscribing customer is preferably provided with a Web browser adapted to receive and transmit information via the Internet. Subscribing customer is also preferably provided with a smartcard subsystem adapted to sign electronic messages. In a preferred embodiment smartcard subsystem may include a smartcard reader a smartcard driver a smartcard token and other software as described in U.S. provisional application Ser. No. 60 224 994 filed Aug. 14 2000 entitled Signing Interface Requirements Smart Card Compliance Requirements Warranty Service Functional Requirements and Additional Disclosure and copending U.S. application Ser. No. 09 928 999 filed Aug. 14 2001 entitled System and Method for Secure Smartcard Issuance which are hereby incorporated by reference. In a preferred embodiment the smartcard token is issued to subscribing customer by its issuing participant .

Subscribing customer is also preferably provided with a signing interface . Signing interface is adapted to invoke smartcard to execute a digital signature as described in U.S. provisional application Ser. No. 60 224 994 filed Aug. 14 2000 entitled Signing Interface Requirements Smart Card Compliance Requirements Warranty Service Functional Requirements and Additional Disclosure and U.S. application Ser. No. 09 929 035 filed Aug. 14 2001 entitled System and Method for Facilitating Signing by Buyers in Electronic Commerce which are hereby incorporated by reference.

Relying customer is preferably provided with a Web server adapted to receive and transmit information via the Internet and a bank interface for accessing system services. An exemplary bank interface is described in copending U.S. application Ser. No. 09 657 604 filed on Sep. 8 2000 entitled System and Method for Facilitating Access by Sellers to Certificate Related and Other Services which is hereby incorporated by reference. Relying customer is preferably further provided with an HSM for signing and verifying signatures on messages.

Customers are also each preferably provided with a directory that is adapted to store data such as for example credential records and messaging specification data as described in more detail below.

In a preferred embodiment each system entity is further preferably provided with two digital certificates and corresponding private keys to facilitate authentication an identity certificate and a utility certificate.

The identity private key is used to produce digital signatures that are required by root entity as evidence of an entity s contractual commitment to the contents of an electronic transaction such as a purchase order.

The utility private key is used to provide additional transactional security. Typically utility certificates are used to support secure socket layers SSL to sign secure multipurpose internet mail extension S MIME messages and for other utility applications. Any reference in this document to the term certificate refers to an identity certificate unless otherwise stated.

In a preferred embodiment root entity in its capacity as a certification authority uses a root private key to create the digital certificates of each system participant e.g. issuing participant and relying participant . In addition it uses the root private key to create digital certificates for each system component maintained by root entity that has digital signing capability including OCSP responder and transaction coordinator .

In addition each system participant e.g. issuing participant and relying participant in its capacity as a certification authority uses the private key associated with its certificate from root entity to create the digital certificates of its customers e.g. subscribing customer and relying customer . In addition it uses this private key to create digital certificates for each system component that it maintains that has digital signing capability including its OCSP responder and transaction coordinator . In an alternative embodiment the digital certificates for system components with digital signing capability that are maintained by a participant may be issued by root entity .

It should be noted that the system entities may each be provided with additional components not shown in such as the components described in copending U.S. application Ser. No. 09 657 605 filed on Sep. 8 2000 entitled System and Method for Providing Certificate Validation and Other Services U.S. provisional application Ser. No. 60 224 994 filed Aug. 14 2000 entitled Signing Interface Requirements Smart Card Compliance Requirements Warranty Service Functional Requirements and Additional Disclosure U.S. provisional application Ser. No. 60 259 796 filed Jan. 4 2001 entitled Warranty Manager Application Programming Interface Warranty Messaging Specification and Warranty Manager Functional Requirements and copending U.S. application Ser. No. 09 928 998 filed Aug. 14 2001 entitled System and Method for Providing Warranties in Electronic Commerce.

The authorization services described herein provide a mechanism by which a first customer e.g. customer may confirm the authority of an individual to act on behalf of a second customer e.g. customer . For example authorization services may be used to confirm the authority of an individual to sign a particular document or to undertake a particular financial or performance obligation on behalf of the second customer. More specifically authorization services maybe used to cite just a few specific examples to determine whether a particular employee is authorized to purchase a particular class of goods negotiate a particular type of contract or undertake to perform in a particular manner on behalf of the second customer.

It should be recognized that the present system is intended to support a wide variety of authorization services that are preferably tailored to the business needs of a particular customer or industry. It is therefore impossible to describe completely every possible authorization service that may be supported by the present system. Rather the description below provides a generalized framework for defining and implementing authorization services in a variety of business settings.

To facilitate understanding of this generalized framework an exemplary embodiment for defining and implementing a particular authorization service is described below. The exemplary embodiment comprises a hypothetical subscribing customer ABC Co. that is a customer of an issuing participant Bank A and a hypothetical relying customer XYZ Co. that is a customer of a relying participant Bank B. ABC Co. employs an office manager known as John Smith who is authorized to transact on behalf of ABC Co. in particular ways as described in more detail below.

As noted above in a preferred embodiment authorization services are designed and implemented in the present system using the following steps. First a customer and its participant work together to define a desired authorization service. The authorization service definition preferably includes both a messaging specification for the service and a set of rules that govern its use as described in more detail below.

Second the proposed authorization service is presented to a policy management authority maintained by root entity for approval. The policy management authority reviews the proposed authorization service for compliance with system operating rules and specifications promulgated by root entity .

Third if the proposed authorization type is approved by the root entity policy management authority the service is implemented within the four corner model.

The first and second steps are described in more detail in connection with below. The third step is described in more detail in connection with below.

In step subscribing customer and issuing participant work together to identify the particular customer and employee information needed to respond appropriately to such an authorization request. For example it may be determined that each employee of ABC Co. has a title and that the types and amount of goods and services that the employee is authorized to obtain on behalf of ABC Co. are a function of that title. As will be recognized this information will typically vary significantly from authorization service to authorization service as a function of the customer industry or type of authorization desired.

In step subscribing customer and issuing participant work together to define a credential record format for storing the categories of information e.g. title purchasing limit identified in step . This credential record format is preferably customized as appropriate for the particular customer and industry to which the authorization service pertains.

In a preferred embodiment each credential record comprises one or more pairs of roles and attributes. A role is a characteristic relevant to the authority of an individual to take a particular action. An attribute represents the particular value assigned to a role for a given individual.

For example in the exemplary embodiment it may be determined that each credential record should comprise the following roles 

In step subscribing customer and issuing participant work together to identify any additional information that may be necessary to properly respond to authorization requests for the authorization type being defined. In a preferred embodiment this information may include definition information and mapping information.

Definition information is information used to construe particular attributes assigned to one or more employees of subscribing customer . For example as noted above the purchasing authority role for ABC Co. s office manager may be assigned the attribute Office Supplies. Definition information is preferably used to define the scope of this attribute. For example definition information may be provided that defines Office Supplies as including pens pencils paper adhesive tape etc. but as excluding either explicitly or by implication desks telephones photocopy machines etc. As described below Bank A may refer to this definition information in responding to authorization requests concerning the purchasing authority of John Smith.

Mapping information is information used to interpret an authorization request received from an entity that uses different terminology than subscribing customer to describe the same things. For example seller XYZ Co. may be located in the United Kingdom where the term sellotape is used to described what ABC Co. located for example in the United States would refer to as adhesive tape. Mapping information may be used to translate terms in an authorization request into appropriate terminology that matches that used by ABC Co.

Additional mapping data may also preferably be maintained by issuing participant to allow for example for currency conversion. Thus for example if seller XYZ Co. is located in the United Kingdom it may specify a purchase amount in an authorization request in pounds sterling. Bank A may use dynamically maintained mapping information to translate the purchase amount to dollars if for example ABC Co. specified its employee purchasing limits in that currency.

In step issuing participant and subscribing customer preferably work together to create a messaging specification that defines a format for authorization requests and responses to be used in connection with the defined authorization service. As noted the present system is intended to support a wide variety of authorization services each of which may be defined as desired by issuing participant and subscribing customer . Accordingly in a preferred embodiment the messaging specification may define messages in any suitable format such as extensible markup language XML hypertext markup language HTML etc.

For purposes of the exemplary embodiment described herein it will be assumed that all messages are to be defined in XML format. As such the messaging specification created by issuing participant and subscribing customer preferably comprises a document type definition DTD that provides the formal description of all valid XML authorization request and response messages used in connection with the authorization service being defined. Exemplary embodiments for such authorization request and response messages are described below.

In a preferred embodiment an authorization service may be designed to support static authorization requests dynamic authorization requests or both.

A dynamic authorization request is a request for approval that an individual is authorized to perform a certain act or undertake a particular transaction. For example a dynamic authorization request may specify that a proposed transaction has a value of 500 and seek to determine whether a particular individual is authorized to transact in that amount. A dynamic authorization response preferably returns a Boolean value e.g. Authorized or Not Authorized .

A static authorization request is a request for the attribute s of one or more roles associated with a particular individual. For example a static request may seek the signing limit of a particular corporate officer. A static authorization response returns the particular attribute s requested.

In step issuing participant and subscribing customer preferably work together in order to define a set of implementation rules that govern use of the authorization service being defined. As noted above the present system is designed to be flexibly adaptable to the needs of various businesses in various industries. Accordingly it is impossible to create a complete list of all such rules that might be proposed by a particular subscribing customer and or issuing participant . Illustrative examples of such rules however may include the following 

1. Issuing participant may respond to a request for authorization concerning purchase of office supplies only if the request is received from a company that sells office supplies.

2. Issuing participant may respond to a request for authorization concerning purchase of office supplies only if the request is received from a company on a list of approved suppliers established by subscribing customer .

3. Issuing participant may respond to a request for authorization concerning purchase of office supplies only if the request is received from a particular company e.g. XYZ Co.

4. Issuing participant may respond to a request for authorization concerning purchase of office supplies only if the request is received from an individual with a title of sales manager. 

5. Issuing participant may respond to a request for authorization concerning purchase of office supplies only if the request is received from a particular individual employed by XYZ Co. e.g. Jane Doe.

It should be noted that the implementation rules may differ as a function of authorization request type i.e. a static vs. dynamic authorization request . In particular a subscribing customer may wish to establish more restrictive rules for responding to static authorization requests than dynamic information requests.

It should also be noted that it may often be possible to enforce one or more implementation rules by properly defining the messaging specification for the proposed service. For example a subscribing customer may wish to permit issuing participant to respond to authorization requests only from relying customers that are in possession of a signed purchase order from subscribing customer . This implementation rule may be enforced by defining an authorization request message format that includes a signed purchase order field in which relying customer must include a signed purchase order from subscribing customer .

In a preferred embodiment the implementation rules may also define access controls that limit the ability of relying customers to obtain the messaging formats for the proposed service. As will be recognized the very structure of an authorization request or authorization response message and the fields it comprises may reveal valuable business information regarding the structure of a business entity. Such message format data may also provide an attacker with information that might be useful in generating forged authorization requests or responses. Accordingly in a preferred embodiment the implementation rules also define access controls that limit access to messaging specification data for the proposed service. For example access controls may be used to determine whether or not a particular relying customer is entitled to receive the message format for a particular type of authorization request. In a preferred embodiment these implementation rules are typically enforced by root entity which is responsible for responding to requests for message format data as described in more detail below.

In step issuing participant presents the proposed authorization service including its messaging specification and implementation rules to a policy management authority maintained by root entity . In step the root entity policy management authority reviews the proposed service for compliance with system operating rules and specifications promulgated by root entity and determines whether or not to approve the proposed service.

If the root entity policy management authority does not approve the proposed service it notifies issuing participant of this fact step . The policy management authority may include with the denial suggested amendments to the messaging specification or implementation rules that would conform the authorization service to the operating rules and specifications promulgated by root entity and permit approval of the proposed service.

If the root entity policy management authority approves the proposed service then in step root entity stores the messaging specification and implementation rules for the service in central repository and notifies issuing participant of the approval.

Once approval notification is received issuing participant stores the approved messaging specification and implementation rules in directory and notifies subscribing customer of the approval step . In step subscribing customer supplies attribute information to issuing participant to populate credential records for subscribing customer s employees. For example as noted above ABC Co. may have an employee whose name is John Smith whose title is Office Manager and who is therefore authorized to purchase up to 1000 of office supplies. In the exemplary embodiment ABC Co. would transmit this attribute information and analogous information for its other employees to Bank A.

In step issuing participant establishes a credential record for each employee of subscribing customer identified to it in step . In the exemplary embodiment for example a credential record for John Smith may appear as follows 

In step issuing participant stores the credentials records in directory . In a preferred embodiment this information may also be stored at subscribing customer in directory .

The authorization service is now ready for use by system customers as described in the following section.

A preferred embodiment of a process flow for using an approved authorization service is now described in connection with . It should be recognized that the present system is intended to provide authorization services in a wide variety of situations in which one entity might seek authorization of another to transact or undertake some obligation. It is therefore impossible to describe completely every possible situation in which the authorization services of the present system might be used. The exemplary preferred embodiment described below describes a typical example purchase of goods by one customer from another in which authorization of an individual might be sought. It will be recognized however that the authorization services of the present system may be used in many other circumstances such as to confirm the authorization of one individual to negotiate a particular contract before commencing negotiations which may be time consuming and costly with that individual.

For purposes of the present exemplary embodiment it will be assumed that the components shown in as being associated with the subscribing customer are owned and maintained by ABC Co. and assigned for use to John Smith its office manager. It will further be assumed that the components shown in as being associated with the relying customer are owned and maintained by XYZ Co. It will further be assumed that the components shown in as being associated with the issuing participant and relying participant are owned and maintained by Bank A and Bank B respectively.

Beginning with in step John Smith the office manager for ABC Co. visits the Web site of XYZ Co. using his browser . The parties preferably authenticate themselves to each other over an SSL session with their utility keys.

Once John Smith agrees to a transaction e.g. to purchase 200 of adhesive tape Web server communicates data to be digitally signed to browser e.g. a purchase order for the agreed to transaction step . In step the data to be signed is forwarded to smartcard subsystem which signs the data to create a digitally signed document.

In step browser receives the digitally signed document and transmits it to Web server or another appropriate location specified by XYZ Co. In a preferred embodiment this signing process may be facilitated by using a signing interface to invoke smartcard subsystem as described in U.S. provisional application Ser. No. 60 224 994 filed Sep. 8 2000 entitled Signing Interface Requirements Smart Card Compliance Requirements Warranty Service Functional Requirements and Additional Disclosure and copending U.S. application Ser. No. 09 929 035 filed Aug. 14 2001 entitled System and Method for Facilitating Signing by Buyer s in Electronic Commerce which are hereby incorporated by reference.

In step XYZ Co. receives the digitally signed document. In step XYZ Co. decides to confirm that John Smith is authorized to sign the purchase order.

In step XYZ Co. determines whether it has previously obtained the appropriate message format for the desired authorization request to be created. As noted the desired authorization request may be a static authorization request or a dynamic authorization request depending on the type of information that XYZ Co. would like to obtain. If XYZ Co. has previously obtained the appropriate message format processing proceeds to step described below.

Otherwise in step XYZ Co. generates a request for the appropriate authorization request message format signs the request and sends the request to Bank B message in . In step Bank B transmits the request to root entity message in .

In step root entity receives the request and retrieves from central repository the access control implementation rules developed by Bank A and ABC Co. for the authorization service identified in the request. In step root entity applies these access control implementation rules to determine whether or not XYZ Co. is authorized to receive the requested authorization request message format.

If XYZ Co. is not authorized to receive the requested message format then in step root entity generates a rejection message indicating this fact signs it and transmits it to Bank B message in . In step Bank B transmits the rejection message to XYZ Co. message in and processing concludes.

Otherwise in step root entity retrieves from central repository the requested authorization request message format creates a signed message that includes the requested message format and transmits the message to Bank B message in . In step Bank B transmits the message to XYZ Co. message in .

In step XYZ Co. uses the authorization request message format to generate an authorization request for some aspect of the transaction documented by the digitally signed document.

Assuming for purposes of the present exemplary embodiment that the authorization service permits a relying customer to make a dynamic request to determine whether an employee of ABC Co. is authorized to purchase a particular type and value of goods an exemplary dynamic authorization request message might include the following fields 

Authorization Request Message Code indicating that the message is a request for authorization and specifying a particular authorization service by number 

An exemplary XML implementation of a dynamic authorization request generated for John Smith s authorization to purchase 200 worth of adhesive tape may be as follows 

Alternatively assuming for purposes of the present exemplary embodiment that the authorization service permits a relying customer to make a static request to determine the purchasing authority of an employee of ABC Co. an exemplary static authorization request message might include the following fields 

Authorization Request Message Code indicating that the message is a request for authorization and specifying a particular authorization service by number 

An exemplary XML implementation of a static authorization request to determine the type and value of items that John Smith is authorized to purchase i.e. his purchasing authority and purchasing limit may be as follows 

Continuing with in step XYZ Co. signs the authorization request message and sends it to Bank B message in . In step Bank B transmits the authorization request message to Bank A message in .

In step Bank A receives the request and checks its repository to determine whether or not it has the appropriate messaging specification data in order to generate a response to the authorization request. If Bank A has the appropriate messaging specification data processing proceeds to step described below.

Otherwise which may occur for example if the authorization service that is the subject of the request was developed by a different system participant then in step Bank A generates a request for the appropriate response message format signs the request and sends the request to root entity message in .

In step root entity receives the request and retrieves from central repository any applicable access control implementation rules necessary to process the request. In step root entity applies these rules to determine whether or not it will release the requested authorization response message format to Bank A.

If Bank A is not authorized to receive the requested message format then in step root entity generates a rejection message indicating this fact signs it and transmits it to Bank A message in . In step Bank A generates a message indicating that it cannot process the authorization request signs it and transmits it to Bank B message in . In step Bank B transmits the message to XYZ Co. and processing ends message in .

Otherwise in step root entity retrieves from central repository the requested authorization response message format creates a signed message that includes the requested message format and transmits the message to Bank A message in .

In step Bank A retrieves from directory the appropriate credential record for the individual that is the subject of the authorization request e.g. John Smith . In addition Bank A retrieves from directory any necessary definition and mapping information for processing the request. Bank A uses this information to process the authorization request from XYZ Co.

For example if the authorization request seeks to determine whether John Smith is authorized to purchase 200 of adhesive tape Bank A reviews John Smith s purchasing authority attributes and any necessary related definition or mapping information and his purchasing limit and determines on these facts that John Smith is authorized to conduct the transaction.

It should be noted that in the present exemplary embodiment it is assumed that the purchasing limit attribute assigned to John Smith is a per transaction limit. It will be recognized that subscribing customer may alternatively or in addition assign to its employees time based e.g. monthly or other purchasing limits. If for example John Smith was also assigned a monthly limit Bank A would preferably track all purchases made by John Smith and maintain a running total of those purchases during the last month. Upon receipt of an authorization request for a specified transaction amount Bank A would add this transaction amount to John Smith s running total for the month compare the sum to John Smith s monthly purchasing limit and issue a positive authorization only if the sum did not exceed the monthly purchasing limit.

In step Bank A uses the authorization response message format to generate an appropriate response to XYZ Co. s authorization request. Continuing with the exemplary embodiment a response to the dynamic authorization request described above may include the following fields 

Authorization Response Message Code indicating that the message is an authorization response message and specifying a particular authorization service by number 

Authorization Response Message Code indicating that the message is an authorization response message and specifying a particular authorization service by number 

In step Bank A signs the authorization response message and sends it to Bank B message in . In step Bank B transmits the authorization response message to XYZ Co. message in . If the authorization response is satisfactory to XYZ Co. then in step XYZ Co. sends a confirmation message for the transaction to John Smith at ABC Co. Otherwise if the authorization response is not satisfactory to XYZ Co. then in step XYZ Co. may send a message to John Smith at ABC Co. disaffirming the transaction.

In a preferred embodiment an authorization request by a relying customer may preferably be bundled and processed concurrently with a request for another system service such as certificate validation. Preferred embodiments for validating a subscribing customer s certificate are described for example in copending U.S. application Ser. No. 09 657 605 filed Sep. 8 2000 entitled System and Method for Certificate Validation and Other Services which is hereby incorporated by reference. A summarized version of that certificate validation process is described below in connection with the bundled authorization certificate validation services. This preferred embodiment is now described in connection with .

Beginning with in step subscribing customer visits relying customer s Web site. The parties preferably authenticate themselves to each other over an SSL session with their utility keys.

In step Web server communicates data to be digitally signed to browser e.g. a purchase order for an agreed to transaction . In step the data to be signed is forwarded to smartcard subsystem which signs the data to create a digitally signed document. In step browser receives the digitally signed document and transmits it to Web server or another appropriate location specified by relying customer . In a preferred embodiment this signing process may be facilitated by using a signing interface to invoke smartcard subsystem as described in U.S. provisional application Ser. No. 60 224 994 filed Sep. 8 2000 entitled Signing Interface Requirements Smart Card Compliance Requirements Warranty Service Functional Requirements and Additional Disclosure which is hereby incorporated by reference.

In step relying customer receives the digitally signed document. In step relying customer generates an authorization request message in accordance with steps as described above. In step relying customer creates an OCSP request for subscribing customer s digital certificate. In step relying customer concatenates the two requests and signs the resulting message. In a preferred embodiment the messaging specification for the authorization service may include a single request that seeks both authorization and certificate validation. In step relying customer transmits the request s to relying participant message in .

In step relying participant identifies the issuing participant that issued the digital certificate that is the subject of the OCSP request and in step transmits the request to that participant i.e. issuing participant in the present example message in .

In step issuing participant processes the authorization request in accordance with steps as described above. In step issuing participant creates an OCSP response for the validation request using its OCSP responder . In step issuing participant concatenates the authorization response message and OCSP response and signs the resulting message. In a preferred embodiment the messaging specification for the authorization service may include a single response message for responding to a bundled authorization certificate validation request.

In step issuing participant transmits the response s to relying participant message in . In step relying participant transmits the response s to relying customer message in . In step relying customer reviews the response s . If the authorization and validation responses are satisfactory to relying customer then in step XYZ Co. sends a confirmation message for the transaction to subscribing customer . Otherwise if one or more of the service responses are not satisfactory to relying customer then in step relying customer may send a message to subscribing customer disaffirming the transaction.

It will be recognized that in other preferred embodiments system services other than certificate validation may be processed concurrently with the authorization service. These system services may for example include a warranty service.

It should be noted that in a preferred embodiment all inter entity messages transmitted and received by participants and root entity may be routed through an appropriate system component adapted for such processing such as for example transaction coordinator .

It should be noted that although the preferred embodiments described above speak primarily in terms of a transaction conducted by an individual employee of subscribing customer the transaction may alternatively be automatically conducted by an appropriate server maintained by subscriber customer . In that case relying customer may for example seek an authorization that the subscribing customer will stand behind a transaction conducted with the server.

It should also be recognized that although in the preferred embodiments described above subscribing customer and issuing participant work together to design a desired authorization service in an alternative preferred embodiment issuing participant or other entities such as root entity may design in advance one or more authorization services and seek approval from the policy management authority for them. Once approved these may serve as off the shelf authorization services that may be offered to a subscribing customer . In particular it may be desirable to design and seek approval for industry specific authorization services that an issuing participant expects will be popular with its customers.

While the invention has been described in conjunction with specific embodiments it is evident that numerous alternatives modifications and variations will be apparent to those skilled in the art in light of the foregoing description.

