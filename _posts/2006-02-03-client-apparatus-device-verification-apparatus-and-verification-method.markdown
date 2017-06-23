---

title: Client apparatus, device verification apparatus, and verification method
abstract: A client apparatus for utilizing services by executing service programs includes a policy holding unit, a verification unit, a verification result holding unit, and a verification result notification unit. The policy holding unit holds a service-specific verification policy pre-checked by a device verification apparatus. The verification unit verifies an operation and configuration of the client apparatus itself by using the verification policy when the service program is executed. The verification result notification unit notifies the verification result to the device verification apparatus, which requests the verification result.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07693835&OS=07693835&RS=07693835
owner: NTT DoCoMo, Inc.
number: 07693835
owner_city: Tokyo
owner_country: JP
publication_date: 20060203
---
This application is based upon and claims the benefit of prior Japanese Patent Application P2005 29758 filed on Feb. 4 2005 and Japanese Patent Application P2006 19524 filed on Jan. 27 2006 the entire contents of which are incorporated by reference herein.

The present invention relates to a client apparatus and an apparatus and a verification method for verifying a device.

It is necessary to verify security of a client apparatus when information communication services are provided to the client apparatus such as a cellular phone PDA or a PC.

For example there has been disclosed a technology which allows a device verification apparatus to investigate security or trustworthiness by utilizing a trusted module in a client apparatus and a service provider to decide permission of service provisioning based on the investigation result for example see Japanese Patent Laid Open Publication No. 2003 76585 . According to this technology the investigation result contains a list of hash values of a software group disposed in the client apparatus and digitally signed by the trusted module. The service provider holds the list of valid hash values of the software group in the client apparatus and compares each hash value with the valid hash value after verification of the signature of the investigation result to check presence of alteration. The service provider can reject service provision to the client apparatus when it detects alteration of certain software or when a hash value of software other than a valid software group is contained. Hence the service provider can provide services upon verification of the security of the client apparatus.

However the aforementioned conventional technology doesn t have means for applying a service specific verification policy to each service and means for deciding permission of provisioning of each service according to the verification result. Thus it is hard to decide permission of service provision based on verification of operation behavior and configuration of the client apparatus because service providers can have service specific requirements for operation and configuration of client apparatus. Besides the conventional technology may cause users serious inconvenience because access to all service are prohibited when abnormality is detected by the verification.

Additionally the aforementioned conventional technology doesn t have means for checking the security of a verification policy itself. Thus it is possibility to lose security of the client apparatus and privacy of user by introducing malicious or defective verification policy to the client apparatus.

The present invention has been developed with the foregoing problems in mind and objects of the invention are to provide a client apparatus a device verification apparatus and verification method which guarantee that the client apparatus satisfies the policy of the each service and protect security and privacy of the client apparatus by verification of security of policy itself.

A first aspect of the present invention is to provide a client apparatus for utilizing services by executing a provided service program the client apparatus including A a policy holding unit configured to hold a service specific verification policy pre checked by a device verification apparatus. B a verification unit configured to verify an operation of the client apparatus itself when the service program is executed by using the verification policy C a verification result holding unit configured to hold a verification result of the verification unit and D a verification result notification unit configured to notify the verification result to the device verification apparatus which requests the verification result.

A second aspect of the present invention is to provide a device verification apparatus comprising A a policy holding unit configured to hold a verification policy corresponding to a service program B a policy verification unit configured to check security of the verification policy C a policy deployment unit configured to deploy the verification policy pre checked by the policy verification unit according to a request of a client apparatus which executes the service program and D a verification result holding unit configured to hold a verification result obtained from the client apparatus which verifies its own operation when the service program is executed by using the verification policy.

A third aspect of the present invention is to provide a verification method for verifying a client apparatus utilizing services by executing a provided service program the verification method comprising A checking security of the verification policy corresponding to the service program B deploying the verification policy which is pre checked by the checking step in a client apparatus which executes the service program C verifying an operation of the client apparatus itself when the service program is executed by using the verification policy and D notifying the verification result to a device verification apparatus which requests the verification result.

Various embodiments of the present invention will be described with reference to the accompanying drawings. It is to be noted that the same or similar reference numerals are applied to the same or similar parts and elements throughout the drawings and the description of the same or similar parts and elements will be omitted or simplified.

A first embodiment is directed to a case where after checking of security of a verification policy of each service provider a device verification apparatus provides the verification policy to a trusted verification module in a client apparatus and decides permission of service provision according to a verification result notified by the trusted verification module.

As shown in a verification system of the first embodiment includes a device verification apparatus a client apparatus and a server apparatus .

In one client apparatus and one device verification apparatus are shown. According to the first embodiment however one device verification apparatus is connected to a plurality of client apparatus . The client apparatus and the device verification apparatus are connected to each other through a network. A connection form thereof may be by wire or radio and any system such as a packet line switching or serial parallel communication can be employed.

The device verification apparatus and the client apparatus are connected to the server apparatus which provides services to the client apparatus through a certain type of connections. The server apparatus is a server operated by a service provider to provide information communication services such as digital contents a database on line shopping on line game and banking. For example the information communication services include VPN Virtual Private Network services for providing access to a corporate intranet mail service and wireless LAN service.

The client apparatus includes a service program execution unit a verification unit a verification result notification unit a policy holding unit and a verification result holding unit .

The service program execution unit executes a service program to utilize services of the service provider and may simultaneously execute a plurality of service programs. The service program is client software such as a VPN client a mail reader a viewer a player or a browser of contents or a database.

The policy holding unit holds a service specific verification policy pre checked by the device verification apparatus described below. A list of service programs installed in the client apparatus is transmitted to the device verification apparatus to request a necessary verification policy. The verification policy is presumed to be directly obtained from the device verification apparatus through communication. However it may be obtained by using a storage medium such as a memory card. It may be obtained together with the service program from the server of the service provider. The policy holding unit may check security of the verification policy. For example to check the security of the verification policy it tests a digital signature of the verification or it checks whether the policy tries to perform unauthorized or unnecessary access to privacy or critical information in client apparatus. The verification policy may take the form of rules or program codes. The policy holding unit rejects and discards the verification policy when the policy is judged to be unsecured.

The verification unit verifies an operation state or a configuration of the client apparatus itself when the service program is executed by using a verification policy corresponding to the service program. The verification unit may verify the client apparatus upon reception of a notification from the outside. When a plurality of service programs is operated each corresponding verification policy is investigated. The verification policy may contain a command of calling a function of the client apparatus and the verification unit may perform function calls according to a result of the verification. As an example of the function of the client apparatus there is a charging function or an access control function. For example a verification policy specifies charging function should be called when the result of the verification satisfies a certain condition. Another example is blocking application programming interface API when the result of the verification satisfies a certain condition. The verification unit must have tampering resistance against attacks including disturbing verification processing and alteration of a verification result by software of an external device or the client apparatus. Accordingly for example the verification unit can be mounted by using a smart card IC card or a trusted platform module TPM whose specification is defined by Trusted Computing Group www.trustedcomputing . Alternatively a mechanism of a virtual machine monitor VMM may be introduced to the client apparatus to accommodate multiple virtual machines on the client apparatus. Thus a virtual machine running the trusted verification unit can be isolated from another virtual machine which executes the service program.

The verification policy is obtained from the device verification apparatus or the server apparatus . The verification policy has verification rules unique to the service program and enables verification of 1. Operation 2. Presence of untrusted or unnecessary application programs running in the client apparatus and 3. Presence of untrusted modules such as device drivers running in the client apparatus. In addition integrity of system application files timestamp of an anti virus pattern files status of a specific port of a firewall or the like may be tested. The verification policy may call functions including charging logging and so on. As examples of verification policies a verification policy for a service program of mail services and a verification policy for banking services are each shown in . In the example of the mail services a rule is set to block access to a mail transmission service correspond to an api rock function in line or execute special charging correspond to an accounting function in line according to an amount of transmitted mails when frequent mail transmissions are detected correspond to a rate monitor function in line and line . In the case of the banking service a rule is set to block the banking program accessing the banking server and transmit a log correspond to lines when detecting untrusted programs running in the client apparatus correspond to line . An example of untrusted programs refers to programs without digital signature by a trusted party As shown in the verification policy may be in a form of a rule or a program code. In the case of the form of the rule the verification unit interprets the rule to perform verification. In the case of the form of the program code the verification unit executes a program of its verification policy.

The verification result holding unit gets and holds a verification result verification log from the verification unit . The verification result may include a frequency of mail transmission the number of times and or time of locking mail transmission in the case of the mail service of . As for the banking service events of blocking a banking service or a type of untrusted application may be included in the result. Additionally a name or a type of a connected network a type of a connected add on device may be contained in the verification result. The verification result held in the verification result holding unit may be deleted when it is notified by the verification result notification unit described below.

The verification result notification unit notifies the verification result to the external device which requests it. The verification result notification unit may notify the verification result in response to a request from the device verification apparatus or to the device verification apparatus at the timing designated by a verification policy. Examples of external devices are the device verification apparatus the server apparatus and the like. When the verification result is notified to prevent alteration of the verification result or pretension as the verification unit the verification unit may digitally sign or encrypt the verification result.

The monitoring unit may monitor an operation and configuration information of the client apparatus and notifies monitoring information to the verification unit . For example it monitors a start end of the service program an active foreground or inactive sleep mode or background state of the service program a type or a state connection or disconnection of a connected network a type or a state of a add on device a state of integrity of a file and the like. A state change a periodic timer abnormality detection or the like may trigger off the notification of the monitoring information to the verification unit. It should be noted that an internal storage device such as an RAM or an external storage device such as a hard disk or a flexible disk may be used for the policy holding unit and the verification result holding unit .

The client apparatus of the first embodiment may be configured by incorporating the service program execution unit the verification unit the verification result notification unit and the like as modules in a CPU. These modules can be realized by executing a program special for using a predetermined programming language in a general purpose computer such as a personal computer.

The client apparatus may include a program holding unit not shown for storing a program to cause the CPU to execute service program execution processing verification processing verification result notification processing or the like. For example the program holding unit is a recording medium such as an RAM an ROM a hard disk a flexible disk a compact disk an IC chip or a cassette tape. According to such a recording medium the program can be easily stored transported or sold.

The device verification apparatus includes a policy holding unit a policy verification unit a policy deployment unit a service provisioning control unit a service charging unit a verification result notification unit a verification result holding unit a verification result presentation unit and a verification result requesting unit .

The policy holding unit holds a verification policy corresponding to a service program. This verification policy is obtained from the server apparatus which provides the service program. For example it is provided by a service provider a service program developer a network operator or the like.

The policy verification unit checks security of the verification policy. For example to protect user resources or privacy information in the client apparatus the policy verification unit interprets or investigates whether the verification policy performs unauthorized or unnecessary access. When the verification policy is judged to be unsafe the policy verification unit rejects deployment of the policy in the client apparatus.

The policy deployment unit deploys a verification policy whose security is confirmed by the policy verification unit in the trusted verification unit of the client apparatus which executes the service program. Specifically the policy deployment unit establishes a secure channel with the verification unit and then sends the verification policy. To prevent alteration of the verification policy or pretension as a verification apparatus the verification policy may be digitally signed or encrypted.

The policy deployment unit may deploy the verification policy in the client apparatus designated by the server device which provides the service program or in the client apparatus which accesses the server apparatus .

The verification result holding unit obtains a verification result from the client apparatus to hold it. For example the verification result verification log can contain timestamp and event information.

The verification result held in the verification result holding unit may be deleted after a passage of predetermined time.

The service provisioning control unit decides permission of access of the client apparatus to the server apparatus based on the verification result. For example when the client apparatus operates to violate the verification policy the service provisioning control unit rejects access from the client apparatus to the server apparatus or redirects access to a particular apparatus like recovery servers and quarantine servers . In when the client apparatus transmits a lot of e mails or launches untrustworthy programs access to the servers is rejected. Access can be blocked by any means. For example 1. the device verification apparatus itself receives an access request from the client apparatus and passes a permitted access request to the server apparatus 2. an access control unit on a path from the client apparatus to the server apparatus blocks requests when receiving a blocking request from the device verification apparatus . Moreover the device verification apparatus can validate or invalidate access certificates or access tickets for the client apparatus to perform access control.

The verification result requesting unit requests a verification request to the client apparatus . The request of the verification result may require that the client apparatus should execute verification upon receiving the request of the verification result and return the result. Otherwise it may require that the client apparatus should just return a cached verification result in the client apparatus. A filtering request of the verification result may be included. Further the verification result requesting unit may receive a request from the external device to request a verification report from the client apparatus . For example the external device is the server apparatus or the access control unit. It can request verification report from the client apparatus at arbitrary timing.

The service charging unit charges usage of the service program by the client apparatus based on the verification result. For example charging may be carried out according to the number of times of viewing listening or playing pay per view or pay per play or according to service usage time. Alternatively charged information may be notified to the server apparatus to settle money payment collection of fees or the like.

The verification result notification unit notifies the verification result to the service apparatus . The verification result notification unit may notify verification results of a plurality of client apparatus en bloc or notify an encrypted or signed verification result.

The verification result presentation unit presents the verification result to an output unit. The output unit is a screen of a monitor or the like and a liquid crystal display LCD alight emitting diode LED panel an electroluminescence EL panel or the like can be used. The output unit may be a printer.

For each of the policy holding unit and the verification result holding unit an internal storage device such as an RAM may be used or an external storage device such as a hard disk or a flexible disk may be used.

The device verification apparatus of the first embodiment may be configured by incorporating the policy verification unit the policy deployment unit the service provisioning control unit the service charging unit the verification result notification unit and the like as modules in a CPU. These modules can be realized by executing a program special for using a predetermined programming language in a general purpose computer such as a personal computer.

The device verification apparatus may include a program holding unit not shown for storing a program to cause the CPU to execute policy verification processing policy deployment processing service provisioning control processing service charging processing verification result notification processing or the like. For example the program holding unit is a recording medium such as an RAM an ROM a hard disk a flexible disk a compact disk an IC chip or a cassette tape. According to such a recording medium the program can be easily stored transported or sold.

First referring to a method for deciding permission of service provisioning when the device verification apparatus receives access from the client apparatus to the server apparatus .

First in step S upon reception of access from the client apparatus to the server apparatus the policy holding unit checks that it holds a verification policy corresponding to the service program. If it holds the policy the process proceeds to step S where judges that the service does not need any verification and access to the service is permitted.

If it holds the verification policy the process proceeds to step S where the verification result notification unit requests a notification of a verification result from the verification unit of the client apparatus .

At this time if the request of the notification of the verification request fails in step S the verification result notification unit judges that deployment of the verification policy in the client apparatus has failed. Then the policy deployment unit deploys the verification policy in step S The verification request may fail when a reply from the client apparatus is not returned within certain time limit time out is broken or is outdated with an old verification policy version. On the other hand if a response of the verification result is successfully obtained in step S a digital signature of the verification result is checked and the verification result is interpreted.

Next if there is no violation of verification rules in the verification result in step S the process proceeds to step S to permit access to the server apparatus . In this case the service may be charged. This permission deciding procedure may be applied to access control for Internet access by VPN or the like in addition to the access to the server apparatus .

On the other hand if the access to the service is rejected with the verification result for example if a lot of e mails are transferred or an untrustworthy application is starting up referring to the verification policy of the process proceeds to step S to reject the access to the server apparatus. Alternatively the access is redirected to a particular apparatus such as recovery servers and quarantine servers.

As a first modified example in step S if the verification policy corresponding to the service program is not held the policy holding unit may ask the server apparatus about presence of a verification policy. The policy holding unit obtains the verification policy from the server apparatus if there is a verification policy or judges that a service needs no verification to permit access if not.

The example where the device verification apparatus itself receives the access request from the client apparatus and passes the permitted access request alone to the server apparatus has been described with reference to the flowchart of . As a modified example an access control unit that independently enforces access control may be deployed between the client apparatus and the server apparatus and the access control unit may receive a request from the client apparatus. In this case upon reception of the request from the client apparatus the access control unit may query the device verification apparatus about access control decision to pass or judge the client request.

As a second modified example in step S the verification unit may check the security of the client apparatus according to the verification policy and call an access control function of the client apparatus for restricting access to the service or call a charging function of the client apparatus for charging.

Next referring to a method for deploying verification policy in the client apparatus when the device verification apparatus obtains the verification policy from the server apparatus will be described.

First in step S the policy holding unit obtains a verification policy from the server apparatus to hold it. Then in step S the policy verification unit checks security of the verification policy.

If the policy verification unit judges in step S that the verification policy is not safe in step S it notifies rejection of the policy together with a policy verification result to the server apparatus . On the other hand if it is judged that the verification policy is safe in step S the policy holding unit updates a verification policy corresponding to the service.

Then in step S the policy deployment unit deploys the verification policy in each target client apparatus . A list of target client apparatus is provided from the server apparatus or obtained by referring to a database for managing the list of client apparatus of service users.

Subsequently in step S the procedure is finished when verification policies are deployed in all the client apparatus. For a client apparatus in which verification policy deployment has failed because of disconnection to the network power OFF or the like deployment is tried again after a passage of certain time. The policy deployment unit may set an upper limit on the number of retry times.

In the above explanation the device verification apparatus actively deploys the policy by connecting to the client apparatus . But as a modified example the device verification apparatus may deploy the policy according to a request from the policy holding unit of the client apparatus . The request may include the list of service program on the client apparatus . The device verification apparatus may deploy all necessary policies to the client apparatus based on the list.

As another modified example the verification unit may update the policy at the case of the reply from the client apparatus is broken time out or outdated as mentioned in the step S of the .

Next referring to a method of introducing a verification policy when the client apparatus receives a verification policy deployment request from the device verification apparatus will be described.

First in step S a verification policy deployment request is received from the device verification unit . Next in step S the policy holding unit confirms whether the verification policy is legitimate and safe or not by checking a digital signature or scanning contents of the verification policy.

If the verification policy is legitimate and safe in step S the policy holding unit introduces or updates a verification policy. On the other hand if the verification policy is not legitimate or safe for example the verification policy isn t from the legitimate device verification apparatus the verification policy is altered or contents of the verification policy include rules or codes infringing security or privacy of the client apparatus in step S the policy holding unit rejects the deployment request.

Next referring to a method of notifying a verification result when the client apparatus receives a verification policy notification request from the device verification apparatus will be described.

In step S the client apparatus receives a verification policy notification request from the device verification apparatus . Then in step S the verification unit confirms whether the request is from a legitimate device verification apparatus or not by checking a digital signature.

If the request is from the legitimate device verification apparatus in step S the verification result notification unit acquires a verification result from the verification result holding unit and notifies the verification result to the device verification apparatus . In this case the notified verification result may be deleted from the verification result holding unit . On the other hand if the request is not from the legitimate apparatus in step S the verification result notification unit rejects the notification request.

As a modified example the notification request of the verification policy may include the timeframe or update request on the verification result. The verification result notification unit may interpret the notification request of the verification policy. And in the S if necessary the verification result notification unit may start up the verification unit and let the verification unit verify the operation and configuration of the client apparatus . After a new verification result is acquired the verification result notification unit may acquire the new verification result from the verification result holding unit and notice the new verification result to the devise verification apparatus .

According to the client apparatus the device verification apparatus and the verification method of the first embodiment the verification unit of the client apparatus can verify the client apparatus according to the service specific verification policy whose security is confirmed by the device verification apparatus . Thus it is possible to inspect an operation or a set state of the client apparatus security information a version of installed software and the like by utilizing a verification policy whereby a safer service provisioning environment can be provided. It is possible to guarantee that the client apparatus satisfies the policy of the each service. Security and privacy of the client apparatus can be protected by checking verification policy itself. Moreover only affected services can be blocked to maintain user convenience when detecting the violation of verification policy.

The verification policies are managed in a concentrated manner by the device verification apparatus and deployed in the client apparatus after checking its safety. Thus it is possible to maintain security of the client apparatus and to reduce management or deployment loads of the server apparatus .

The policy holding unit of the client apparatus may hold a verification policy obtained only from a predetermined particular apparatus. When an optional apparatus can introduce a verification policy to the verification unit of the client apparatus it is possible to prevent damaging security or privacy of the client apparatus.

As the client apparatus includes the verification result holding unit verification results can be transmitted en bloc to the device verification apparatus . Even when a communication amount is reduced or the client apparatus is temporarily out off from the network the verification results can be transmitted to the device verification apparatus at the time of connection thereafter.

The verification result held in the verification result holding unit of the client apparatus may be deleted after its notification to the device verification apparatus . Thus it is possible to prevent squeezing of a storage capacity or overflowing of verification logs caused by an increase in verification results verification logs held by the client apparatus .

The policy holding unit of the client apparatus may check security of the verification policy. Accordingly it is possible to improve the security of the verification policy more.

The policy holding unit of the client apparatus may obtain a necessary policy from the device verification apparatus to update it. Accordingly the client apparatus can always hold a proper policy.

The verification unit of the client apparatus may execute verification upon reception of a notification from the external device. Accordingly the client apparatus can execute verification based on a request from the external device.

The client apparatus further includes the monitoring unit for monitoring the operation and the configuration information of the client apparatus to notify the monitoring information to the verification unit . Accordingly the client apparatus can always have the monitoring information.

The verification result notification unit of the client apparatus may notify the verification result to the device verification apparatus at the timing specified by the verification policy. Accordingly the client apparatus can notify the verification result at the suitable timing based on the verification policy.

The verification policy may contain a command of calling the function of the client apparatus and the verification unit may call the function according to the result of the verification. Thus the client apparatus can perform a suitable operation such as charging or locking functions based on the verification result.

The device verification apparatus of the first embodiment obtains the verification result based on the verification policy provided to the client apparatus and decides permission of access to the server apparatus after its interpretation. Thus the server apparatus can provision services with trusting the client apparatus .

The policy verification unit of the device verification apparatus checks security of the verification policy. Thus it is possible to protect security and privacy of the client apparatus.

The service provisioning control unit of the device verification apparatus decides permission of access from the client apparatus to the server apparatus based on the verification result. Thus only the client apparatus proved by the device verification apparatus can access the server apparatus .

The service charging unit of the device verification apparatus charges use of services based on the verification result. Thus it is possible to execute flexible charging according to the number of viewing listening or playing times or time paper view paper play or the like based on the verification result of the client apparatus. It is also possible to reduce loads of charging or verification processing on the service provider.

The verification result held in the verification result holding unit of the device verification apparatus may be deleted after a passage of predetermined time. Thus it is possible to prevent squeezing of the storage capacity or overflowing of verification logs caused by an increase in verification results verification logs of the device verification apparatus .

The verification result presentation unit of the device verification apparatus presents the verification result to the output unit. Thus the operator of the device verification apparatus can present a reason for charging services or stopping service provisioning to the user.

The verification policy held in the policy holding unit of the device verification apparatus may be obtained from the server apparatus . Thus it is possible to check the service program according to a request from each service provider whereby safer service provisioning and finer charging are enabled. Additionally it is possible to deal with even a change of the verification policy of the service provider.

The policy deployment unit of the device verification apparatus deploys a verification policy in a client apparatus designated by the server apparatus or a client apparatus which accesses the server apparatus . Thus the server apparatus can leave deployment of the verification policy to the device verification apparatus to reduce its processing load and management cost. Additionally it is possible to provision safe services by surely deploying the verification policy in the client apparatus which accesses the server apparatus .

The verification result notification unit of the device verification apparatus notifies a verification result to the server apparatus . Hence the service provider itself can execute flexible charging or selection of permission of service provisioning.

The policy holding unit of the device verification apparatus may obtain the verification policy from the server apparatus to update it. Hence the device verification apparatus can always hold a proper policy.

The device verification apparatus includes the verification result requesting unit for requesting a report of the verification result of the client apparatus . Hence the device verification apparatus can receive the verification result from the client apparatus at arbitary timing.

Furthermore the verification result requesting unit may receive a request from the external device and request the client apparatus to report the verification result. Hence it is possible to receive the verification result according to the request from the external device.

In the second embodiment the client apparatus includes the service program execution unit and the monitoring unit in an environment domain 2 isolated from an environment domain 1 which is the verification unit deployed in.

As shown in according to the second embodiment the client apparatus includes the verification unit the policy holding unit the verification result holding unit and the verification result holding unit in the environment domain 1 the service program execution unit and the monitoring unit in the other environment domain 2 isolated from domain 1.

The second embodiment is similar to the first embodiment except for that the verification unit verifies actions of the service program and thus explanation of components will be omitted.

The verification method of the second embodiment is similar to the first embodiment except for that the verification unit verifies actions of the service program and thus explanation of components will be omitted.

As shown in the monitoring unit in the S monitors an operation and configuration information of the client apparatus . In the S if the monitoring unit detects change of the monitoring stats the monitoring unit notifies monitoring information to the verification unit . For example it monitors a start end of the service program an active active window state or inactive execution in sleep or background state a type or a state connection or disconnection of a connected network a type or a state of a connected external device a state of integrity of a file and the like.

And in the S the monitoring unit notifies the monitoring result to the verification unit and starts up verification unit .

In the S the verification unit verifies client apparatus according to the monitoring result and verification policy. And in the S the verification unit executes necessary action for example logging or calling the function of the client apparatus such as access control.

As a modified embodiment the verification unit may request a monitoring result to the monitoring unit and receive the monitoring result.

According to the second embodiment the monitoring unit and the service program execution unit is deployed in the isolated environment. Hence as compared with the first embodiment the protection of the verification unit or access control function and charging function of the client apparatus can be improved. In other words verification or the other function of the client apparatus can be executed safely without being influenced by attacks and failure in isolated environment.

According to the first embodiment the device verification apparatus receives an access request and transfers only a permitted access request based the verification result to the server apparatus . According to a third embodiment however a access control apparatus is deployed between the client apparatus and the service apparatus . The access control apparatus receives an access request from the client apparatus.

As shown in the verification system of the third embodiment includes the device verification apparatus the client apparatus the server apparatus and the access control apparatus.

The third embodiment is similar to the first embodiment except for that the access control apparatus receives an access request from the client apparatus to the server apparatus the access control apparatus requests a verification about necessary service to the devise verification apparatus and the access control apparatus controls an access to the server apparatus . And thus explanation of components will be omitted.

According to the verification system of the third embodiment it is possible to perform flexible configuration as plural access control apparatus and scatter loads by separating access function into the access control apparatus .

According to the first embodiment the device verification apparatus decides permission of service provisioning and executes charging based on the verification result. According to a forth embodiment however a service apparatus service provider performs such processing.

As shown in a verification system of a second embodiment includes a device verification apparatus a client apparatus and a server apparatus .

The second embodiment is similar to the first embodiment except for deployment of the service provisioning control unit and the service charging unit deployed in the device verification unit according to the first embodiment in the server apparatus and thus explanation of components will be omitted.

Next referring to a verification method according to the second embodiment will be described. Referring to a method for notifying a verification result when the device verification apparatus receives access from the client apparatus to the server apparatus will be described.

First upon reception of access from the client apparatus to the server apparatus in step S in step S the policy holding unit judges holding of a verification policy corresponding to the service program. If the policy is not held the process judges a service which needs no verification to permit the access.

If the verification policy is held the process proceeds to step S where the service provisioning control unit requests a notification of a verification result to the verification unit of the client apparatus .

At this time if the request of the notification of the verification request fails in step S incorrect deployment of the verification policy in the client apparatus is judged in step S to deploy the verification policy. On the other hand if a response of the verification result is obtained in step S a digital signature of the verification result is checked and the verification result is interpreted.

Next in step S the verification result notification unit notifies the verification result to the server apparatus . The server apparatus decides permission of service provisioning or executes charging by using the verification result.

According to the forth embodiment the server apparatus decides permission of service provisioning or executes charging. Hence as compared with the first embodiment a processing load of the device verification apparatus can be reduced more.

According to a fifth embodiment a device verification apparatus verifies not only an operation of a client apparatus but also an operation of a server apparatus .

Referring to a verification system of the fifth embodiment includes a device verification apparatus a client apparatus and a server apparatus . Configurations of the device verification apparatus and the client apparatus are similar to those of the first embodiment and thus description thereof will be omitted.

The server apparatus includes a service program holding unit a verification unit a verification result notification unit a policy holding unit and a verification result holding unit .

The verification unit checks the service program based on a verification policy held by the policy holding unit .

The verification result notification unit notifies a verification result to the device verification apparatus .

In other words the verification unit the verification result notification unit the policy holding unit and the verification result holding unit of the server apparatus have functions similar to those of the verification unit the verification result notification unit the policy holding unit and the verification result holding unit of the client apparatus respectively.

The device verification apparatus decides permission of access from the client apparatus to the server apparatus or access from the server apparatus to the device verification apparatus . In other words when a verification result of the server apparatus is valid access is permitted because the server apparatus can be judged to be normal. When not valid access is rejected because the server apparatus is judged to be abnormal.

For each of the policy holding unit and the verification result holding unit an internal storage device such as an RAM or an external storage device such as a hard disk or a flexible disk may be used.

The server apparatus of the fifth embodiment can be configured by incorporating the verification unit the verification result notification unit and the like as modules in a CPU. These modules can be realized by executing a program special for using a predetermined programming language in a general purpose computer such as a personal computer.

The server apparatus may include a program holding unit not shown though for storing a program which causes the CPU to execute verification processing verification result notification processing and the like. For example the program holding unit is a recording medium such as an RAM an ROM a hard disk a flexible disk a compact disk an IC chip or a cassette tape. According to such a recording medium the program can be easily stored transported and sold.

According to the client apparatus the device verification apparatus the server apparatus and the verification method of the fifth embodiment the operations of the client apparatus and the server apparatus can be verified and the operations can be verified more minutely.

The present invention has been described according to the foregoing first to second embodiments. However it should be understood that the description and drawings which partially constitute the present disclosure do not limit this invention. From this disclosure various alternative embodiments embodiments and operational technologies will become apparent to those skilled in the art.

For example according to the foregoing embodiments the verification result is received to select permission of service provisioning each time the client apparatus accesses the server apparatus . However the device verification apparatus may memorize previous verification time of the client apparatus and verification of access which arrives within given time may be omitted.

Various modifications will become possible for those skilled in the art after receiving the teachings of the present disclosure without departing from the scope thereof.

