---

title: Method, system and network server for recording use of network service capability by applications
abstract: The present invention discloses method, system and network server for recording use of network service capability by applications (APPs), and the key points of the methods comprise: a network server acquires an identity of the APP and type information of the network service capability providing services for the APP, conducts service logic processing, and writes a message of use of network service capability, which comprises at least the identity of the APP and the type information of the network service capability providing services for the APP. With the methods of this invention, the purpose of making effective records of use of network service capability by APPs provided by service providers is implemented. Furthermore, management of APPs, such as charging, may be conducted by utilizing the records.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08612568&OS=08612568&RS=08612568
owner: Huawei Technologies Co., Ltd.
number: 08612568
owner_city: Shenzhen
owner_country: CN
publication_date: 20060609
---
This application claims priority to Chinese Patent Application No. 200510076965.X filed Jun. 9 2005 all of the disclosure of which is hereby incorporated by reference in its entirety.

The present invention relates to network management techniques and in particular to method system and network server for recording use of network service capability by applications provided by service providers.

Along with the fast development of the communication technology and the Internet merging of the fixed networks the mobile networks and the Internet has become a general trend and demands for network services are gradually becoming diversified integrated and individualized. Under these circumstances an open next generation network architecture is progressively taking shape which can merge networks of various different structures and comprehensively provide multimedia services.

The fundamental purpose of developing the networks is to provide people with plenty of services and the service evolvements are driving forces of the fast development of the next generation networks NGN . In order to realize merging of the service layers a certain approach is required e.g. universal network interfaces to shield technical details of the bottom layers of different networks so that the upper layer service applications would have nothing to do with specific network structures and services across networks of various different structures could be implemented in a uniform way.

The infrastructure of a network is provided by a network service provider which is the running basis of practical applications provided by a service provider such as a network operator a virtual operator or a third party service provider. With the development of technology it is possible to adopt a uniform set of interfaces for abstractly representing service capability of the network and provide them to the service provider so as to mask discrepancies of the networks and make the networks transparent to the applications APPs provided by the service provider and thus the applications could uniformly use the capability of the merged network. A representative example herein is a Parlay OSA Application Programming Interface API architecture including Parlay X Web Services which defines a set of open interfaces independent of specific techniques and networks and introduces an application developing mode of the Internet thereby providing a technical foundation for the merging of IT applications with telecommunication networks. So far the Parlay OSA API has won support from numerous standardization organizations and manufacturers and has become a standard of open network API oriented to Next Generation Networks.

With gradual opening up of the networks and extensive use of such techniques as interface technique an issue of how to manage the service providers becomes increasingly prominent. As there is no record for the use of network service capability by applications provided by a service provider in the prior art it is impossible to conduct management such as charging and performing statistics based on the use of network service capability by the applications provided by the service provider.

In the existing fixed networks mobile networks and Internet there are records of information such as time duration flow volume and terminal addresses for users when they consume services and management could be carried out in connection with these records. Below is a brief description of the structure of the network system in the prior art by taking a system for charging as an example.

Here the APP is for initiating an invocation request to the logic processing module in the network server where the request contains an identity of the APP itself and invocation parameters or for receiving performing results from the logic processing module in the network server.

The logic processing module functions to obtain the identity of the APP and the invocation parameters from the received invocation request and after validating the invocation parameters in the request are appropriate determine type information of the network service capability providing services to the APP according to the received invocation request and send a network operating command to the network operation processing module or receive the processing result of network operations from the network operation processing module .

The network operation processing module is responsible for analyzing the network operating command received from the logic processing module sending the analyzed command to the corresponding network function performing module analyzing the processing result of network operations received from the network function performing module and returning the analyzed result to the logic processing module .

The network function performing module is adopted to perform network operations in accordance with the received command.

The subscriber CDR recording module is in use for receiving the statistical information from the network operation processing module which includes time duration and or flow volume as well as terminal addresses recording the received information and sending the recorded information to the subscriber CDR processing module.

The subscriber CDR processing module takes charge of pricing the received statistical information in accordance with a pre configured charging matrix of a subscriber s CDR and generating an account bill for the subscriber.

For the system as shown in it is possible for the network side to actively initiate a notifying message without subscription by the APP. In this case the network function performing module is further used for submitting information of a network event to the network operation processing module when a preset triggering condition of the network side initiative operation is met.

The network operation processing module is further used for analyzing the received information of the network event before submitting the analyzed information to the logic processing module .

The logic processing module is further used for based on the received information of the network event and a preset corresponding relation between the network event and an identity of the APP obtaining the identity of the APP corresponding to the received network event and type information of the network service capability providing services for the APP and sending a notifying message to the APP .

Whichever processing is made at the network side the network side will only perform charging for user equipments UE . Charging for the UEs is mainly implemented by means of statistics of time duration and or flow volume according to the recorded terminal addresses or other identifiers of the terminals. These recording methods however are not applicable for recording and managing applications provided by service providers for it is quite possible that the time durations or flow volumes consumed by the applications of the service providers are the same or nearly the same while it doesn t indicate that the occupied network resources of the applications are the same. Therefore how to make effective records of different network resources occupied by different service providers and amount of the resources used i.e. use of network service capability by the APPs remains an issue to be solved.

In view of the above in one aspect this invention provides a method for recording use of network service capability by APPs so as to make effective records of the network service capability used by the APPs provided by service providers. Meanwhile in another aspect this invention provides a method for recording use of network service capability in connection with a notifying invocation request. In yet another aspect this invention provides two systems and a network server for recording use of network service capability by APPs so as to implement the above methods.

A method for recording use of network service capability by an application APP comprising the steps of 

initiating by the APP an invocation request containing an identity of the APP and invocation parameters to a network server 

obtaining by the network server the identity of the APP and type information of the network service capability requested by the APP from the received invocation request 

recording by the network server a message of use of network service capability which at least comprises the identity of the APP and the type information of the network service capability providing services for the APP.

sending by the network server a list of use of network service capability which records multiple messages of use of network service capability to a pre configured network usage list processing module and the network usage list processing module pricing the received list of use of network service capability according to the acquired charging matrix of use of network service capability and producing a charging account for the APP.

Said list of use of network service capability is in a form of a file or a database and said network usage list processing module obtains the list of use of network service capability by way of FTP or reading the database.

configuring triggering conditions which are determined according to functions of the network side for the network side to initiatively send a notifying message to an APP and

when a triggering condition of the APP is currently met obtaining the identity of the APP corresponding to the received network event as well as type information of the network service capability providing services for the APP based on a pre configured corresponding relation between a network event and an identity of the APP performing service logic processing invoking a notifying interface of the APP sending a notifying message to the APP and recording a message of use of network service capability by the network server 

said message of use of network service capability at least comprises the identity of the APP and the type information of the network service capability providing services for the APP.

an application APP a network server including a logic processing module and a network operation processing module and one or more network function performing module said network server also includes a network usage recording module wherein

said APP is for initiating an invocation request to the logic processing module in the network server where the invocation request contains an identity of the APP and invocation parameters or for receiving a performing result from the logic processing module in the network server 

said logic processing module is for obtaining the identity of the APP and the invocation parameters from the received invocation request determining the type information of the network service capability providing services for the APP according to the received invocation request after deciding the invocation parameters in the request are legitimate and sending network operating commands to the network operation processing module or receiving the processing result of network operation from the network operation processing module or sending to the network usage recording module the obtained identity of the APP initiating the request and the type information of the network service capability providing services for the APP 

said network operation processing module is for analyzing the network operating command received from the logic processing module sending the analyzed command to the network function performing module corresponding to the command and analyzing the processing result of network operation returned from the network function performing module before returning the analyzed result to the logic processing module 

said network function performing module is for implementing network operation in accordance with the received command 

said network usage recording module is for recording based on the received information a message of use of network service capability which at least comprises an identity of the APP and type information of the network service capability providing services for the APP.

A system for recording use of network service capability by an APP comprising an application APP a network server including a logic processing module and a network operation processing module a network function performing module wherein a network usage recording module is included in the network server and

said network function performing module is for submitting information of a network event to the network operation processing module in the network server when a pre configured triggering condition of initiatively informing by the network side is met 

said network operation processing module is for analyzing the received information of the network event before submitting the analyzed information to the logic processing module in the network server or for analyzing the network operating command received from the logic processing module sending the analyzed command to the network function performing module corresponding to the command and analyzing the processing result of network operation received from the network function performing module before returning the result to the logic processing module 

said logic processing module is for according to the received information of the network event as well as a pre configured corresponding relation between the network event and the identity of the APP acquiring the identity of the APP corresponding to the received network event and the type information of the network service capability providing services for the APP or sending the network operating command to the network operation processing module or sending a notifying message to the APP according to the processing result of network operation returned from the network function performing module or sending the acquired information to the network usage recording module 

said network usage recording module is for recording a message of use of network service capability which at least comprises an identity of the APP and type information of the network service capability providing services for the APP.

A network server for recording use of network service capability by an APP comprising a logic processing module a network operation processing module and a network usage recording module wherein

said logic processing module is for obtaining the identity of the APP and the invocation parameters from a received invocation request determining the type information of the network service capability providing services for the APP according to the received invocation request after deciding the invocation parameters in the request are legitimate and sending network operating commands to the network operation processing module or receiving the processing result of network operation from the network operation processing module or sending to the network usage recording module the obtained identity of the APP initiating the request and the type information of the network service capability providing services for the APP and

said network operation processing module is for analyzing the network operating command received from the logic processing module or analyzing the processing result of network operation before returning the analyzed result to the logic processing module and

said network usage recording module is for recording based on the received information a message of use of network service capability which at least comprises an identity of the APP and type information of the network service capability providing services for the APP.

The present invention provides two methods for recording the use of network service capability by APPs of which the key points are that a network server acquires information of a basic attribute of an APP and type information of the network service capability providing services for the APP implements service logic processing and then generates a message of use of network service capability which at least comprises a serial number of this message an identity of the APP type information of the network service capability and an end mark of the message. With the method of the present invention the purpose of effectively recording the use of network service capability by APPs provided by service providers is realized. In addition the records can be used to carry out further management for the APPs e.g. charging. As a result it is possible to charge an APP based on its use of network service capability which is fair for the public. Furthermore as charging for APPs is realized new benefits are brought to network service providers which compensate construction cost of network infrastructures.

At the same time the present invention provides two systems and a network server for recording the use of network service capability by APPs which facilitates implementation of the above methods.

This invention is hereinafter described further in detail with reference to the accompanying drawings and specific embodiments.

The idea of this invention is to record use of network service capability by APPs. In this way it is possible to carry out management such as charging and statistics for the APPs in a more purposeful way.

The so called network service capability refers to capability abstracted from a certain network service provided by a network server e.g. call routing call supervising voice playing acquiring more in coming numbers adding members to a group sending a text message sending a multimedia message acquiring location information of a terminal submitting a location change for a terminal sending a USSD message deducting cost according to amount reserving cost according to amount and prolonging time of cost reservation. Each network service may be discerned as a kind of network service capability. Use the above network services once by an APP would be considered as one use of network service capability by the APP.

It is well known that an APP may use the capability of a network side server synchronously or asynchronously or it can use notifying capability of a network side server either. The implementation of the present invention is described hereinafter with reference to the above three application circumstances.

Furthermore there may be another circumstance for i.e. the APP has not conducted a subscription while the network side initiatively issues a notifying message. At this time there is no scenario of but only and in

Here records for messages of use of network service capability triggered by an invocation request initiated by the APP or triggered by initiative of the network side may exist simultaneously or separately.

It is via an interface that the above APP initiates an invocation request to the network server where the interface is a message communication interface a file interface or an API. Further said message communication interface comprises a network protocol message interface where a network protocol message is but not limited to a TCP IP message an HTTP message or an XML message. Moreover said API based invocation may comprise a local invocation or a remote invocation. The remote invocation could be in the form of Common Object Request Broker Architecture Corba or Web Service or Remote Method Invocation RMI Internet Inter ORB Protocol IIOP or Distributed Component Object Model DCOM .

The specific network system and implementing procedure in accordance with the present invention are hereinafter described respectively.

Here the APP is for initiating an invocation request to the logic processing module in the network server where the request contains an identity of the APP itself and invocation parameters or for receiving performing results from the logic processing module in the network server.

The logic processing module is for acquiring the identity of the APP and the invocation parameters from the received invocation request and after validating the invocation parameters in the request are appropriate determining type information of the network service capability providing services to the APP according to the received invocation request and sending a network operating command to the network operation processing module or receiving the processing result of network operation from the network operation processing module or sending the acquired identity of the APP initiating the request and the type information of the network service capability providing services for the APP to the network usage recording module .

The network operation processing module is for analyzing the network operating command received from the logic processing module sending the analyzed command to the corresponding network function performing module analyzing the processing result of network operation received from the network function performing module and returning the analyzed result to the logic processing module .

The network function performing module is for performing network operation in accordance with the received command.

The network usage recording module is for recording based on the received information a message of use of network service capability which may comprise an identity of the APP and type information of the network service capability providing services for the APP . Further the message of use of network service capability may comprise a serial number and an end mark as well.

The above invocation request that the logic processing module receives from the APP is a synchronous invocation request or an asynchronous invocation request or a notifying invocation request based on interfaces. If the invocation request that the logic processing module receives from the APP is an asynchronous invocation request after receiving the logic processing result from the network operation processing module and acquiring state information on whether this service logic processing has successfully used the network service capability the logic processing module will callback the APP and notify the APP of the performing result.

If the invocation request that the logic processing module receives from the APP is a notifying invocation request then the invocation request will further comprise information of a network event subscribed. The logic processing module after deciding that a triggering condition required by the subscription is currently satisfied will acquire the identity of the APP initiating the request and the type information of the network service capability providing services to the APP inform the network operation processing module to operate the network and invoke a notifying interface of the APP after receiving the operation result of the network from the network operation processing module . After that notify the APP of the event subscribed and write a record of use of network service capability again.

For the system as shown in when the network side initiatively sends a notice the relations among the APP the network server comprising the logic processing module and the network operation processing module the network function performing module and the network usage recording module included in the network server are as follows 

The network function performing module is for submitting the information of network event to the network operation processing module within the network server when a pre configured triggering condition for the network to initiate a notice is satisfied.

The network operation processing module is for analyzing the received information of the network event before submitting the analyzed information to the logic processing module within the network server or for analyzing a network operating command received from the logic processing module sending the analyzed command to the network function performing module corresponding to the command and analyzing the operation result of network received from the network function performing module before returning the result to the logic processing module .

The logic processing module is for based on the received information of the network event and a pre configured corresponding relation between the network event and an identity of the APP acquiring the identity of the APP corresponding to the received network event and the type information of the network service capability providing services for the APP or sending a network operating command to the network operation processing module or sending a notifying message to the APP according to the operation result of network returned from the network operation processing module or sending the acquired information to the network usage recording module .

The network usage recording module is for use in the same operation as described above and no further description is given here.

If it is desired to carry out charging management for the APP whichever connecting mode is employed the system as shown in may further comprise a network usage list processing module which receives a list of use of network service capability for recording multiple messages of use of network service capability from the network usage recording module prices the list of use of network service capability according to a pre configured charging matrix of use of network service capability and produces a charging bill for the APP . In this pricing procedure it is possible to price for each message of use of network service capability or a combination of multiple messages of use of network service capability which depends on specific needs.

The above list of use of network service capability for recording multiple messages of use of network service capability is saved as a file or a database and the network usage list processing module acquires the list of use of network service capability by way of FTP or reading the database.

The above message of use of network service capability further comprises an APP priority identifier a QoS level identifier of the APP one or more subscriber numbers starting time and ending time of a request an initiator ID and state information on whether a service logic processing has successfully used the network service capability.

When it is needed to charge according to a message of use of network service capability the message of use of network service capability further comprises an identity of a charging mode and a current session identity where the identity of the charging mode includes an identity of free charge an identity of charging by pieces of message or an identity of charging by monthly payment. Preferably the identity of a charging mode could be configured in a changing matrix in stead of comprised in the message.

The message serial number is constituted jointly by submitting time of the message a feature code of network service capability and a serial number. The type information of the network service capability providing services for the APP comprises a serial number of the capability type and an interface type used by the APP where the capability type comprises network service capability for voice services network service capability for data services or network service capability for management and the type information of the network service capability providing services for the APP further comprises a serial number of a capability server.

Moreover in the system as shown in the existing portion of charging for terminals may remain unchanged. Thus the system as shown in may further comprise a subscriber CDR processing module and a subscriber CDR recording module inside the network server .

Here the subscriber CDR recording module is for receiving statistical information including time duration and or flow volume as well as terminal addresses from the network operation processing module recording the received information and sending the recorded information to the subscriber CDR processing module .

The subscriber CDR processing module is for pricing the received statistical information in accordance with a pre configured charging matrix of a subscriber s CDR and producing the subscriber s account bill.

Step A network server receives a synchronous invocation request from an APP and the request comprises an identity of the APP and invocation parameters.

Step The network server acquires the identity of the APP and invocation parameters from the invocation request validates whether the invocation parameters are appropriate. If yes perform Step otherwise perform Step .

Step Write a message of use of network service capability which includes information representing the state that this service logic processing has failed to use the network service capability. The information representing the state that this service logic processing has failed to use the network service capability is identified by a state code and the state code points out cause of failure which hereby is that the invocation parameters are not appropriate.

Step Perform service logic processing. The specific procedure comprises instructing the network function performing module which possesses network service capability corresponding to contents of the invocation request to implement network operation and receiving a performing result returned from the network function performing module.

Step Acquire state information on whether this service logic processing has successfully used the network service capability according to the performing result received.

Step Write a message of use of network service capability which contains the state information as this service logic processing has succeeded in using the network service capability and end this procedure. Here the state information on whether the service logic processing has successfully used the network service capability can be identified by a state code which hereby is set for indicating success.

There are two methods for recording the state information on whether the service logic processing has successfully used the network service capability 

One is to decide whether the service logic processing is successful if yes record the state information as the service logic processing has succeeded in using the network service capability otherwise record the state information as the service logic processing has failed to use the network service capability the other is to record the state information as the service logic processing has succeeded in using the network service capability as long as the service logic processing is finished without considering whether the service logic processing is successful or not.

After executing the above Step a step of sending to the APP the result of the invocation by the network server may be further comprised.

Step A network server receives an asynchronous invocation request from an APP where the request comprises an identity of the APP and invocation parameters.

Step The network server acquires the identity of the APP and the invocation parameters from the invocation request and validates whether the invocation parameters are legitimate if yes perform Step otherwise perform Step .

Step Write a message of use of network service capability which includes state information as this service logic processing has failed to use the network service capability. The state information as this service logic processing has failed to use the network service capability is identified by a state code which also identifies cause of the failure. Here the cause of the failure is that the invocation parameters are not legitimate.

Step Perform service logic processing. The specific procedure comprises instructing the network function performing module which possesses network service capability corresponding to contents of the invocation request to implement network operation and receiving the performing result returned from the network function performing module.

Step Acquire the state information on whether this service logic processing has successfully used the network service capability according to the received performing result.

Step Write a message of use of network service capability which contains the state information as this service logic processing has succeeded in using the network service capability. Here the state information on whether the service logic processing has successfully used the network service capability is identified by a state code which is set hereby indicating success.

There are two methods for recording the state information on whether the service logic processing has successfully used the network service capability 

One is to decide whether the service logic processing is successful if yes record the state information as the service logic processing has succeeded in using the network service capability otherwise record the state information as the service logic processing has failed to use the network service capability the other is to record the state information as the service logic processing has succeeded in using the network service capability as long as the service logic processing is finished without considering whether the service logic processing is successful or not.

Step Perform a callback to the APP and notify the APP of the performing result. If the service logic processing is successful it is indicated hereby that a correct result is returned if the service logic processing fails it is indicated hereby that an error is returned.

Step A network server receives a notifying invocation request from an APP which contains an identity of the APP invocation parameters and information adopted to subscribe an event for the APP i.e. a triggering condition for the network to issue a notice.

Steps are the same as Steps i.e. a notifying invocation request sent by the APP may be a synchronous invocation request. Of course this notifying invocation request may be an asynchronous invocation request as well.

Step Decide whether the triggering condition required by the subscription of a network event in the notifying invocation request is currently met if yes perform Step otherwise repeat Step .

Step Decide whether a notifying interface of the APP is found if yes perform Step otherwise perform Step .

Step Invoke the notifying interface of the APP and notify the APP of the network event it has subscribed to.

Step Write a message of use of network service capability and end the procedure. The message of use of network service capability contains state information on whether this service logic processing has successfully used the network service capability.

There are two methods for recording the above state information on whether the service logic processing has successfully used the network service capability 

One is that the network server decides whether the information returned from this APP indicates normal after notifying the APP if yes record the state information as the service logic processing has succeeded in using the network service capability otherwise record the state information as the service logic processing has failed to use the network service capability the other is to record the state information as the service logic processing has succeeded in using the network service capability after the network notifies the APP without considering whether the information returned from the APP indicates normal or not.

As shown in when recording the use of network notifying capability Steps may be skipped and the recording procedure directly starts from Step . Obviously before performing Step it is needed to carry out configuration according to functions of the network side i.e. pre configure triggering conditions for the network side to initiatively send a notifying message to the APP and the triggering conditions are determined according to the functions of the network side. When a triggering condition for the APP is currently met the network server based on the pre configured corresponding relation between the network event and an identity of the APP acquires the identity of the APP corresponding to the received network event and the type information of the network service capability providing services for the APP performs service logic processing thereafter invokes a notifying interface of the APP sends a notifying message to this APP and records again a message of use of network service capability. For example a function of notifying the transmission state of short message has been pre configured at the network side and this function does not require a subscription of a user. Every time the user sends a short message a report about the receiving state will be obtained from the receiver e.g. the information that the receiver has received or has not received the message. That is some notifying functions require subscription in advance by an APP e.g. daily news or weather forecast while other notifying functions does not require subscription beforehand and so long as such functions have been pre configured on a network server the network side will perform the notifying functions when a triggering condition is met. Which functions require subscription in advance for notifying services and which functions does not have such requirement can be configured freely according to specific demands.

In the performing process of any of the flowcharts shown in and the network server may further implement an operation of recording a log the specific method of which is the same as the prior art and no further description is hereby given.

The contents of the message of use of network service capability mentioned in and as well as their corresponding meanings are shown in Table 1.

Refer to Table 1 an item which has a mark of M in the attribute column is essential in a message of use of network service capability while an item with the attribute of O is optional. That is a message of use of network service capability at least comprises an identity of the APP and type information of the network service capability providing services for the APP. A serial number and or an end mark may be contained in the message but they are not mandatory. Further the message of use of network service capability may comprise a current session identity session ID assigned for the current session which could be used as a correlator to associate several corresponding network usages an APP priority identifier an identifier of QoS level of the APP one or more subscriber numbers which could jointly be used with the identity of the APP for measuring the use of the network service capability starting time of a request and ending time of a request an initiator ID and state information on whether this service logic processing has successfully used the network service capability. When it is needed to charge according to the message of use of network service capability it will further comprise an identity of charging mode and said identity of charging mode comprises an identity of free charge an identity of charging per message or an identity of charging by monthly payment.

Contents in the description column of Table 1 e.g. digits formats and sequences of time information as well as examples thereof are only preferred embodiments and practical applications are not limited to the contents hereby presented. The items of No. 3 No. 5 are basic attributive information of an APP the items of No. 6 No. 8 are type information of a network service capability providing services for the APP and the item of No. 15 is used only when a server is to perform charging management of the APP. Of course the item of No. 15 could be set as a part of a charging matrix and it may not be contained in this message. Also if no charging management is to be made the item of No. 15 may not be comprised in this message either. And if other managements are to be made other item for representing the managements may be added into the above information.

The type of capability numbering No. 6 in Table 1 includes without limitation network service capability for a voice service e.g. call routing call supervising voice playing or acquiring more in coming numbers network service capability for a data service e.g. sending a text message sending a multimedia message acquiring location information of a terminal submitting a change of terminal location and sending a USSD message and network service capability for management e.g. adding member to a group deducting cost according to amount reserving amount according to cost prolonging time of cost reservation configuring network QoS and adding policy fields.

Here Step 1 manifests that an APP invokes an enableCallNotification to instruct the object of IpCallControlManager at the server side to enable the call notification function. As the enableCallnotification is a synchronous invocation the object of IpCallControlManager records a message of use of network service capability which indicates that the APP has used the network service capability once after receiving the notification.

Step 2 manifests that the object of IpCallControlManager at the server side invokes the callEventNotify to notify the object of IpAppCallControlManager of the arrival of a call event. As the IpCallControlManager object server has sent a notifying message the IpCallControlManager object of the server side records a message of use of network service capability after sending the notifying message where the message of use of network service capability indicates that the APP has used the network service capability once. In Step 2.1 the object of IpAppCallControlManager at the APP side will send the received notifying message to the APP and in Step 2.1.1 the APP will also return appropriate information after receiving the notifying message. However whether Step 2.1 and Step 2.1.1 have been successfully performed or not the object of IpAppCallControlManager will conduct a record because the APP has used network service capability once and yet whether to record the use of network service capability as success will depend on pre configured principles.

Step 3 represents that the APP invokes the superviseCallReq to ask the IpCall object at the server side to supervise a call. As the superviseCallReq is an asynchronous invocation the IpCall object at the server side records a message of use of network service capability which indicates that the APP has used the network service capability once after receiving the request.

Step 4 manifests that the APP invokes the routeReq to ask the IpCall object at the server side to carry out call routing. As the routeReq is an asynchronous invocation the IpCall object at the server side records a message of use of network service capability after receiving the request for indicating that the APP has used the network service capability once.

Step 5 demonstrates that the IpCall object invokes the routeRes to return a message of successful routing to the IpAppCall object at the APP side. In Step 5.1 the IpAppCallControlManager object at the APP side will notify the APP of the received notifying message.

Step 6 shows that the IpCall object at the server side invokes the superviseCallRes to report a call supervising information to the IpAppCall object at the APP side. In Step 6.1 the IpCallControlManager at the APP side will notify the APP of the received notifying message.

As seen from the above whether or not Steps 5 5.1 6 6.1 have been performed successfully the server side will record a message because the APP has used network service capability once. However whether to record a successful use of network service capability by this processing depends on pre configured principles.

Step 7 manifests that the APP invokes the createUICall to ask the IpUIManager object to create a call related user interaction object. As this createUIManager is a synchronous invocation the object of IpUIManager at the server side records a message of use of network service capability indicating one use of network service capability by the APP after receiving the request.

Step 8 means that the APP invokes the sendInfoReq to ask the object of IpUICall at the server side to send a message to a user. As this sendInfoReq is an asynchronous invocation the object of IpUICall at the server side records a message of use of network service capability indicating one use of network service capability by the APP after receiving the request.

Step 9 means the object of IpUICall at the server side reports the transmission state to the object of IpAppUICall at the APP side via the sendinfoRes. In Step 9.1 the object of IpAppUICall at the APP side notifies the APP of the received notifying message.

Step 10 means that the APP invokes a release procedure to instruct the IpUICall object to release the call related user interaction object. As the invocation of release procedure is a synchronous invocation the IpUICall object at the server side records a message of use of network service capability indicating one use of network service capability by the APP after receiving the release message.

Step 11 means that the APP invokes a release procedure to instruct the IpCall object to release a call object. As the invocation of release procedure is a synchronous invocation the IpCall object at the server side records a message of use of network service capability indicating one use of network service capability by the APP after receiving the release message.

As seen from the above in practical applications as long as an APP has used the capability of a server at the network side once the server will record a message. In the embodiment shown as multiple API invocations by the IpCall object employ a uniform session ID and multiple API invocations by the IpUICall object uniformly use another session ID.

Although the application scenarios shown in and are based on the API invocations defined by Parlay OSA the methods in accordance with the present invention are applicable to invocations based on non API interfaces as well.

As shown in from the INVITE message to the ACK message the APP has used the session connecting capability of the network once. Therefore after receiving the ACK message the SoftSwitch writes a message of use of network service capability.

As shown in from the INVITE message to the ACK message the APP has used the session connecting capability of the network once and after the setup of session connection the APP has used the voice playing capability twice. Therefore the APP has altogether used the network service capability three times.

Here the SUBMIT SM has used the short message sending capability of SMSC and the DELIVER SM has used the short message notifying capability of SMSC e.g. a user sends a short message to an APP or an APP receives a state report of short message.

A plurality of messages of use of network service capability form a list of use of network service capability. After recording the list of use of network service capability by the APP the network server may perform management on the APP. An example of perform charging management is hereinafter given to specifically describe the process of managing an APP by utilizing a list of use of network service capability.

Step The network usage list processing module acquires a list of use of network service capability of the APP.

Step Price the acquired message of use of network service capability according to the charging matrix of use of network service capability. In the pricing process it is possible to price each message of use of network service capability or price a combination of multiple messages of use of network service capability where the specific pricing policy depends on specific demands.

Here is an example of on how the messages contained in the list of use of network service capability are adopted for generating a charging bill according to a charging matrix. The charging matrix could be set beforehand with reference to policies such as price for each message or price for a combination of multiple messages associated with session IDs or price according to the message and the amount of users or if the number of times of invocating an interface exceeds 10000 a discount is provided etc. When the charging matrix is set as price for each message a charging bill for the use of the SendBulkSMS interface is the same as the use of the SendSMS interface. When the charging matrix is set as price according to the message and the amount of users a charging bill for the use of the SendBulkSMS interface is generated on taking the amount of users into account. Thus the charging bill of the use of a SendSMS interface is different from that of a SendBulkSMS interface because the SendBulkSMS causes several network operations simultaneously while the SendSMS may only cause a network operation. When pricing Message to Message which have a same session ID since it has been designated that applying a charging policy for pricing Message to Message while applying another charging policy for pricing Message and Message the charging bill for the use of Message to Message is different from that of Message and Message . That is messages with the same session ID could be priced freely according to a preset policy.

As seen from the above this invention provides a method for recording use of network service capability by APPs with a flexible and configurable granularity. And it is possible to conduct management such as charging and performing statistics based on the recorded use of network service capability.

To sum up the foregoing only describes preferred embodiments of the invention and is not for limiting the protection scope thereof.

