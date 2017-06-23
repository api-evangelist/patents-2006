---

title: Identity validation
abstract: Techniques for validating identities are provided. A sign-on request is authenticated for a given principal. Attributes associated with that principal are acquired from an identity service and compared against local maintained attributes for that principal. If the identity-service acquired attributes match the local attributes, then the principal is validated for access. During principal access, selective events drive updates to the identity-service acquired attributes, and the comparison with the local attributes is performed again to determine whether the validated principal is to be invalidated or is to remain validated.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08069476&OS=08069476&RS=08069476
owner: Novell, Inc.
number: 08069476
owner_city: Provo
owner_country: US
publication_date: 20060601
---
The invention relates generally to security and more particularly to techniques for validating an identity.

Commerce and affairs are increasingly being transacted over the Internet. That is enterprises and individual users now have sufficient infrastructure and software services to conduct secure and insecure transactions.

One downside to this environment is that a single user often needs to have a plethora of identities for the variety of services and resources that the user consumes over the Internet. This can become a challenging and daunting situation and may often result in the user consuming less resources when that user forgets or mismanages his her identities.

To solve this problem a variety of single sign on services have been offered to users over the Internet. Essentially a user can sign on to such a service and then access all the other services associated with the user assuming those other services are registered with the single sign on service. In this manner the user does not have to manage each available service which the user may need to supply credentials to for purposes of gaining access.

However these single sign on services still do not ensure user security when an intruder intercepts or acquires a particular credential of the user for a particular service. So the user can still be exposed with each individual service being managed by a single sign on service. Moreover if an intruder gains the credentials necessary to access the single sign on service then every service of the user is exposed and vulnerable. This latter situation can be devastating to a user.

It is also worth noting that some user identities are associated with enterprises for which they work or are otherwise employed. Such users may also have access to services and resources which if acquired by competitors or criminals could be extremely harmful to their enterprises.

In various embodiments techniques for validating identities are presented. More specifically and in an embodiment a method for validating a principal s true identity is provided. Initially a sign on token is received from a principal. Next first principal attributes are requested from an identity service and second principal attributes are independently acquired. Finally the principal is validated for access when the first principal attributes match the second principal attributes.

As used herein a service is a type of resource that is accessible over a network. The service is implemented as instructions that when loaded and accessed by a machine performs one or more functions that the service is advertised to perform. A principal is another type of resource that may be an automated service or may logically represent a physical resource within an electronic environment such as but not limited to a user a device a group of users a group of devices an object etc.

An identity service refers to a special type of service that is designed to manage and supply authentication services and authentication information for principals and for other services. So an identity service may authenticate a given principal for access to a variety of local and external services being managed by that identity service. A single principal may have multiple identity services.

According to an embodiment some example identity services are described in Techniques for Dynamically Establishing and Managing Authentication and Trust Relationships filed on Jan. 27 2004 and having the U.S. Ser. No. 10 765 523 Techniques for Establishing and Managing a Distributed Credential Store filed on Jan. 29 2004 and having the U.S. Ser. No. 10 767 884 and Techniques for Establishing and Managing Trust Relationships filed on Feb. 3 2004 and having the U.S. Ser. No. 10 770 677 all of which are commonly assigned to Novell Inc. of Provo Utah and the disclosures of which are incorporated by reference herein.

An identity service may also provide single sign on services to a principal. That is a principal may sign on to an identity service and acquire identities and credentials to access a variety of other services.

A principal is recognized via an identity. An identity is authenticated via various techniques e.g. challenge and response interaction cookies assertions etc. that use various identifying information e.g. identifiers with passwords biometric data digital certificates digital signatures etc. . A true identity is one that is unique to a principal across any context that the principal may engage in over a network e.g. Internet Intranet etc. . However each principal may have and manage a variety of identities where each of these identities may only be unique within a given context given service interaction .

As used herein attributes may be viewed as types of identifying information such as but not limited to birth date mother s maiden name pet s name last transaction for a given context age employment income level social security number SSN etc.

The true identity of a principal is typically managed and controlled by an identity service such as the ones enumerated above. The identity service may also manage the principal s other identities that the principal uses with services for which the principal interacts in a variety of different contexts.

A service provider hereinafter SP is a service that a principal interacts with in a given context. For example a SP may be a principal s corporate network connection. The corporate network connection may also be used by the principal to access local services within a secure environment of the corporation and external services that reside outside the environment of the corporation. A service may also be any Internet accessible or World Wide Web WWW service accessible to the principal. For example a SP can be a banking service an auction service a store s service a search service an electronic mail email service and others.

In this manner some SP s may provide federated identity services for sub services that they trust or securely communicate with. For example eBay is an online auctioning service where a user principal can authenticate to eBay via the WWW to acquire an eBay specific identity. Once signed into eBay i.e. SP specific context the user can access other services where the user may have a different identity such as PayPal .

According to an embodiment a principal signs into an identity service to acquire a sign on token. This token is presented to a desired SP for which the principal wants to gain access. The SP authenticates the principal in response to the token. If this is a first time that the principal accessed the SP then the principal supplies attributes to the SP and the SP retains these attributes. The types or categories of attributes may be driven by policy. The SP also acquires a second set of attributes directly from the identity service for that principal. Again the types and categories of second attributes may be driven by policy. The SP compares the principal acquired attributes against the identity service acquired attributes and if they match the principal is validated for access if they do not match the principal s access is terminated.

Various embodiments of this invention can be implemented in existing network architectures. In some cases the techniques presented herein may be implemented as enhancements to existing services. These enhancements may be integrated into the existing services or accessed externally via Application Programming Interfaces API s . In some cases the enhancements may be unknown to the existing services such that the existing services are not even aware of the techniques being processed. This can occur when the techniques are implemented as a transparent proxy on behalf of the services. According to the techniques presented herein are implemented in whole or in part in the Novell network and proxy server products email products identity service products operating system products and or directory services products distributed by Novell Inc. of Provo Utah.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms operating and server systems or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension only and is not intended to limit aspects of the invention.

At a sign on token is received from a principal. The sign on token represents a credential from the principal being presented to the validation service for purposes of gaining access to the validation service and its features or other services trusted by the validation service. According to an embodiment the sign on token may be an assertion in a Security Assertion Markup Language SAML or Liberty Alliance format.

In an embodiment the principal initially interacts with an identity service and authenticates to that identity service. The principal then requests an identity that is recognized by the validation service and the identity service supplies the sign on token. The principal then presents this sign on token to the validation service for purposes of gaining access to the resources of the validation service.

In some cases after the sign on token is received the validation service may according to policy engage in a challenge response dialogue with the principal to further authenticate the principal. For example the principal may be asked to supply a password.

At the validation service requests first principal attributes from an identity service. The validation service and the identity service are in trusted relationships and communicate with one another in a secure manner. According to an embodiment at the validation service identifies the specific attributes or types of attributes to request from the identity service in response to a policy. Attributes as defined above include identifying information about the principal. The first principal attributes are maintained managed and supplied by the identity service and the validation service receives the first principal attributes directly from the identity service.

At the validation service acquires second principal attributes. The second principal attributes are managed and controlled by the validation service. According to an embodiment at the second principal attributes are acquired directly from the principal during a first access attempt. That is if the principal has never before interacted with the validation service then the validation service engages the principal to obtain values for the desired second principal attributes.

In another embodiment at the validation service obtains the second principal attributes from a repository in response to an identity associated with the principal. So if the principal has previously interacted with the validation service then the second principal attributes are retrieved by the validation service within a local environment of the validation service.

The second principal attributes are not acquired from the identity service they are independently maintained and controlled by the validation service.

As an example consider a user principal that accesses an identity service to acquire an identity and credentials sign on token to access eBay . eBay includes a front end service that interacts with the validation service. The validation service first determines if the credentials are sufficient for access. Next the validation service contacts the identity service and acquires the user s mother s maiden name and birth date first principal attributes . If the user has not yet ever accessed eBay then the validation service engages the user to acquire values for the user s mother s maiden name and birth date second principal attributes . If the user has accessed eBay then the validation service acquires values for the user s mother s maiden name and birth date from a repository.

At the validation service validates the principal when the first principal attributes match the second principal attributes. So in the prior example the validation service will validate the eBay user for access to eBay if the identity service supplied values for the user s mother s maiden name and birth date match the validation service acquired values for the user s mother s maiden name and birth date. Not all the attributes have to be compared with one another. In fact policy may drive selective comparisons with respect to the attributes.

The fact that the validation service performs an independent assessment of the principal even when the principal is authenticated for access pursuant to the sign on token provides additional security for a principal. Thus if a user s identity is compromised and access is attempted to the validation service the validation service supplies added validation on the identity presented to ensure the principal is legitimate.

According to an embodiment at the validation service may also monitor the access session of the principal once access is granted. This can be done by detecting events that are raised or trapped during the session with the principal. Again the events may be defined by policy. When such an event is detected during a session with the principal the validation service updates the first principal attributes by consulting the identity service again for updated values. The updated version of the first principal attributes can then be compared to the second principal attributes to ensure access is still acceptable to the validation service. In this manner the validation can be regular or continuous during a session with the principal.

In some cases at the validation service may identify some events as an attempt by the principal to access a sensitive restricted or regulated resource. The validation service may also detect a situation where the principal is attempting to perform a single sign on request or operation on another service which is trusted and which communicates with the validation service. These types of events are cases where the validation service may want to perform updates on the first principal attributes in a real time dynamic and on demand fashion.

At the validation service denies access when the first principal attributes do not match the second principal attributes.

Initially a principal has gained authenticated access to the monitor service. This can occur in the manners discussed above with respect to the validation service represented by the method of the . As the principal performs operations during that access referred to as a session the monitor service watches or listens to decide whether special actions are warranted.

Accordingly at the monitor service detects an event during a session with a principal. In an embodiment at the monitor service may recognize the event as a single sign on request or any other federated identity type request. That is the event is raised or issued when the principal attempts to perform some federation of the identity with which the principal is currently operating under within the session. For example if the principal is permitted to create an identity for a sub service then this is aggregating identities associated with the principal and is considered one type of federation of identities.

At the monitor service evaluates a policy in response to the detected event. In an embodiment at the monitor service may decide in response to that evaluation whether the event is acceptable or warrants immediate termination. In other words the principal may be restricted from performing some operations such as operations associated with identity federation and if the detected event within the policy instructs the monitor service terminates the principal s session and corresponding access.

According to an embodiment at each event or event type may be used to identity a specific policy. The monitor service then dynamically and in real time evaluates and processes that policy.

At the monitor service acquires first attributes about the principal from an identity service. A discussion of this technique was described above with respect to the validation service represented by the method of the .

At the monitor service compares the first attributes against second attributes. In an embodiment at the second attributes are acquired from an initial registration of the principal and or from memory storage. If the first attributes match the second attributes then the monitor service is reasonable assured that the principal is who it purports to be.

At the monitor service decides whether to terminate the session or permit it to proceed. The session is terminated if the evaluated policy dictates or if the first attributes did not match the second attributes. At the event is ignored and the session is permitted to continue unabated when the policy permits and when the first attributes matched the second attributes. Termination may occur for a variety of additional reasons such as a dropped connection between the monitor service and the identity service such that the monitor service is unable to communicate with the identity service specific dynamically evaluated policies may also dictate that the session be terminated. Therefore the session may be terminated for a variety of additional and configurable situations.

Again the proxy identity service presents an alternative perspective to the validation service and the monitor service represented by the methods and of the respective. In an embodiment the proxy identity service is added as a front end service to an existing service provider SP . In some cases the SP is not even aware of the existence of the proxy identity service. The proxy identity service processes to validate principal identities attempting to access the SP and can monitor actions taken to perform regular and continual validation against the principal identity. In an embodiment the proxy identity service is a transparent proxy.

In still other situations the proxy identity service may be at least partially integrated into an existing SP using an API. In these cases the proxy identity service may be viewed as a forward or reverse proxy.

At the proxy identity service identifies a principal that is requesting access to the SP. The principal is authenticated for access. Authentication may be achieved via an assertion or token being presented where that assertion or token is from a trusted and known identity service associated with the proxy identity service and the SP. In some cases policy may drive the proxy identity service to engage the principal to acquire some additional credentials such as a password.

At the proxy identity service acquires information on the principal from the identity service. The type of information is also driven by policy. Examples of the type of information were discussed above in the context of attributes which are identifying information for the principal and which the principal supplied to the identity service.

At the proxy identity service locates local information on the principal. Examples of the type of local information was discussed above in the context of local attributes which are managed and controlled locally by the validation service and the monitor service represented by the methods and of the respectively.

According to an embodiment at the proxy identity service may interact directly with the principal during an initial registration to acquire the local information about the principal. Thereafter the local information is retrieved from a local data store e.g. directory file database repository data warehouse etc. .

At the proxy identity service validates the principal as legitimate when the information obtained from the identity service matches the local information obtained locally and independently by the proxy identity service . If the match is not achieved then the proxy identity service determines something is not right with the principal and its identity and access to the SP is terminated and not granted.

In an embodiment at the proxy identity service also monitors a session associated with the principal and the SP. During this session the proxy identity service looks for a federated identity request and if detected a policy is evaluated to determine if this is permissible. Additionally the identity service is consulted again in a dynamic and real time fashion to acquired updated information on the principal. The session is allowed to continue if the policy permits the federated identity request being made by the principal within the session and if the updated information matches the local information.

In one situation at the federated identity request is recognized as a single sign on request. That is the principal is attempting to gain access to another different service or resource via the SP with the single sign on request. Other types of federated identity requests may exist as well such as but not limited to requests to create a new identity for the principal with respect to a resource requests to modify an existing identity and others.

The identity validation system includes an identity service and a service provider SP . In some embodiments the identity validation system may also include a local repository and or a policy store . The identity service and the SP interact with a principal . Each of these and their interactions with one another will now be discussed in greater detail.

The identity service may be viewed as a type of single sign on service. Some example identity services were presented above and incorporated by reference above. According to an embodiment an existing identity service is enhanced to provide the interaction discussed herein.

The identity service authenticates the principal and manages various identities of the principal . The principal acquires an identity for accessing the SP . That identity may not be the true identity of the principal rather the identity is one recognized and used by the SP . The identity service also supplies credentialing information a token and or an assertion which the principal may use to gain authentication to the SP .

It is to be noted that although reference is made to a single principal herein that the identity validation system operates simultaneously on a plurality of principals .

The SP is configured to interact with a principal requesting access to local and external services of the SP . To do this the SP first assures itself that the principal is legitimate. This can be done via the credential information supplied by the identity service or it can be done via a password being directly supplied by the principal .

During a first access or registration the SP initially acquires attributes for the principal . These initially acquired attributes are retained by the SP and are used to perform additional checks against a principal s identity for each subsequent access and during sessions that the principal may subsequently have with the SP .

The SP also regularly and in real time consults the identity service to acquire updated attributes for the principal . These updated attributes are compared against the initially acquired attributes to determine if access is to be granted or terminated at any particular point in time.

Example processing associated with the SP was presented in detail above with respect to the validation service the monitor service and the proxy identity service represented by the methods of the respectively.

According to an embodiment the identity validation system also includes a local repository to house and to retrieve the initially acquired attributes. The repository may be directory a database a warehouse a file and the like.

In an embodiment the identity validation system also includes a policy store . The policy store is used for housing policies for events detected during sessions between the SP and the principals . Event types or identifiers may be indexed into the policy store for purposes of acquiring specific policies to evaluate and enforce for detected events.

In fact a variety of policies may drive the SP . For example a policy may drive the attributes acquired from the identity service . Another policy may drive how the principal is to be initially authenticated. In other words if a password is required for access even with a single sign on token or other credential. Still another policy may determine whether access of the principal is to be terminated in response to a detected event such as a single sign on attempt or other federated identity type of operation.

According to an embodiment the SP is implemented as a proxy service to an existing service that the principal desires access to. In one situation the proxy is a transparent proxy such that the service is unaware of the existence and operations being performed on its behalf by the SP .

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

The Abstract is provided to comply with 37 C.F.R. 1.72 b and will allow the reader to quickly ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

