---

title: Restricting recordal of user activity in a processing system
abstract: A method/system for restricting recordal of user activity in a processing system. In one form, the method comprises intercepting a kernel API call of the processing system , determining if a process initiating the kernel API call is malicious, and in response to a positive determination, terminating the determined process. A table can be updated with request information of the process and it can be determined if a trend of requests exists for the status of the input device, and in response to a positive determination of a trend, the process may be terminated.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08028301&OS=08028301&RS=08028301
owner: Symantec Corporation
number: 08028301
owner_city: Mountain View
owner_country: US
publication_date: 20060224
---
This application claims the benefit of priority from Provisional Application Ser. No. 60 661 695 entitled Method And System For Preventing Recordation Of User Activity In A Processing System and filed on Mar. 14 2005. Provisional Application Ser. No. 60 661 695 is hereby incorporated by reference in its entirety.

The present invention generally relates to a method system and or computer readable medium of instructions for restricting recordal of user activity in a processing system and more particularly to a method system and or computer readable medium of instructions for restricting or preventing user performed keystrokes and or mouse actions to be recorded by a software program or device such as for example keylogger software.

A keylogger as used herein refers to software or hardware that is designed to record and or store keystrokes which a user types on a keyboard of a processing system. A keylogger can be designed to be unobtrusive or hidden to the user and usually operates without the knowledge of the user. By recording keystrokes a keylogger may transfer such recorded details to another person or entity wherein the details may comprise usernames passwords or credit card details. This information may then be used to the detriment of the user of the processing system without their knowledge.

A keylogger blocker as used herein refers to software or hardware that is designed to restrict a keylogger from operating normally or recording keystrokes made by a user.

A hook also known as a hook procedure or hook function as used herein generally refers to a callback function provided by a software application that receives certain data before the normal or intended recipient of the data. A hook function can thus examine or modify certain data before passing on the data. Therefore a hook function allows a software application such as a keylogger to examine data such as keystrokes before the data is passed to the intended recipient.

An API Application Programming Interface hook also known as an API interception as used herein as a type of hook refers to a callback function provided by an application that replaces functionality provided by an operating system s API. An API generally refers to an interface that is defined in terms of a set of functions and procedures and enables a program to gain access to facilities within an application. An API hook can be inserted between an API call and an API procedure to examine or modify function parameters before passing parameters on to an actual or intended function. An API hook may also choose not to pass on certain types of requests to an actual or intended function.

A process as used herein is at least one of a running software program or other computing operation or a part of a running software program or other computing operation that performs a task.

A hook chain Microsoft Windows specific definition as used herein is a list of pointers to special application defined callback functions called hook procedures. When a message occurs that is associated with a particular type of hook Microsoft Windows passes the message to each hook procedure referenced in the hook chain one after the other. The action a hook procedure can take depends on the type of hook involved. For example the hook procedures for some types of hooks can only monitor messages others can modify messages or stop their progress through the chain restricting them from reaching the next hook procedure or a destination window.

A kernel as used herein refers to the core part of an operating system responsible for resource allocation low level hardware interfaces security etc.

An interrupt as used herein is at least one of a signal to a processing system that stops the execution of a running program so that another action can be performed or a circuit that conveys a signal stopping the execution of a running program.

In a networked information or data communications system a user has access to one or more terminals which are capable of requesting and or receiving information or data from local or remote information sources. In such a communications system a terminal may be a type of processing system computer or computerised device personal computer PC mobile cellular or satellite telephone mobile data terminal portable computer Personal Digital Assistant PDA pager thin client or any other similar type of digital electronic device. The capability of such a terminal to request and or receive information or data can be provided by software hardware and or firmware. A terminal may comprise or be associated with other devices for example a local data storage device such as a hard disk drive or solid state drive.

An information source can comprise a server or any type of terminal that may be associated with one or more storage devices that are able to store information or data for example in one or more databases residing on a storage device. The exchange of information ie. the request and or receipt of information or data between a terminal and an information source or other terminal s is facilitated by a communication means. The communication means can be realised by physical cables for example a metallic cable such as a telephone line semi conducting cables electromagnetic signals for example radio frequency signals or infra red signals optical fibre cables satellite links or any other such medium or combination thereof connected to a network infrastructure.

A signature based keylogger blocker relies on a database of signatures for known keylogger software. Signatures are collections of information which contain a description of keylogger software and may comprise characteristics such as file size file name a cryptographic hash or checksum or pseudo code which represents program flow.

These signatures are read by the keylogger blocker and used to determine whether or not to allow execution of a suspected process. A problem with signature based keylogger blockers is that they require constant maintenance and updating of the signature database in order to be effective. Signature based keylogger blockers do not restrict the operation of a keylogger which is not covered in the signature database.

A behaviour based keylogger blocker attempts to restrict keylogger software from functioning correctly by examining behaviour of keylogger software and restricting suspicious activity. Currently available behaviour based keylogger blockers can restrict some known and unknown keyloggers from recording keystrokes however currently known behaviour based keylogger blockers are not sufficient to stop keylogger software from establishing a hook in the hook chain and thus these keylogger blocker programs may be easily bypassed by keyloggers. Additionally currently known behaviour based keylogger blockers fail to restrict or terminate a keylogger s process and notify a user in real time.

Referring to there is illustrated a system structure used by presently known keylogger blockers. On start up this system structure installs a system wide keyboard hook onto the hook chain C . Whenever a particular hook is called which the keylogger blocker wishes to restrict propagating through the hook chain the next hook in the chain E is not called or a system buffer containing keystates is cleared. This method restricts information propagating to all other installed hooks such as keyboard hooks. However this restriction of the propagation of information is risky as other hooks further down the hook chain may not receive required data and may subsequently stall an operating system running on the processing system.

There exists a need for a method system and or computer readable medium of instructions to at least restrict or prevent the recordal of keystrokes and or mouse actions which address or at least ameliorate problems inherent in the prior art.

The reference to any prior art in this specification is not and should not be taken as an acknowledgment or any form of suggestion that such prior art forms part of the common general knowledge.

According to a first broad form the present invention provides a method of restricting recordal of user activity in a processing system the method comprising 

Preferably but not necessarily the method comprises performing behavioural analysis of the process to determine if the process is malicious.

Also preferably but not necessarily determining if the process is malicious comprises checking if the API call is related to a user interface.

In particular but non limiting forms determining if the process is malicious comprises checking if the API call is related to a graphical user interface. In one form determining if the process is malicious comprises checking if the process comprises a hidden window.

In another particular but non limiting form determining if the process is malicious comprises comparing the process to one or more signatures of known keylogger programs.

In accordance with a specific optional embodiment in response to a positive determination of a malicious process the method comprises identifying the process.

Optionally the process is identified by at least one of a name of the process a process identity a user with which the process is associated a time the process was initiated a parent process identity number a processing cycle for the process and or one or more associated open port numbers.

According to one embodiment prior to the process being terminated the method comprises prompting a user to authorise the termination of the process.

According to another non limiting embodiment the method comprises generating a file comprising data related to the process and storing the file in a storage device.

According to a second broad form the present invention provides a processing system for restricting recordal of user activity in the processing system comprising 

According to a third broad form the present invention provides a method of restricting recordal of user activity in a processing system the method comprising 

determining if a process initiating the input device API call is requesting a state of the input device and

In one non limiting embodiment the method comprises intercepting the API call for at least one of the following input devices a keyboard and or a mouse.

In another non limiting embodiment in response to a positive determination of the process requesting the state of the input device the method comprises identifying the process.

Optionally the process is identified by at least one of a name of the process a process identity a user with which the process is associated a time the process was initiated a parent process identity number a processing cycle for the process and or one or more associated open port numbers.

In one particular but non limiting form the request information comprises at least one of the name of the process the process identity the user with which the process is associated the time the process was initiated the parent process identity number associated processing cycles for the process and or one or more associated open port numbers.

performing a behavioural analysis of the process by determining if a trend exists based on whether the process is polling the state of the input device at least one of 

In another non limiting embodiment prior to the process being terminated the method comprises prompting a user to authorise the termination of the process.

Optionally the method comprises generating a file comprising data related to the process and storing the file in a storage device.

According to a fourth broad form the present invention provides a processing system for restricting recordal of user activity in the processing system comprising 

means to determine if a process initiating the input device API call is requesting a state of the input device and

According to a fifth broad form the present invention provides a method of restricting recordal of user activity in a processing system the method comprising 

determining if a process initiating the kernel device driver API is attempting to perform an activity comprising at least one of 

In one particular but non limiting form the method comprises intercepting the kernel device driver API call for at least one of the following input devices a keyboard and or a mouse.

Optionally the method comprises determining if a user prompt is to be displayed to a user warning the user of the process attempting to perform the activity.

In one non limiting embodiment the user prompt requests a response indicating whether the process is permitted to perform the activity and the method comprises receiving response data indicating whether the user has permitted the activity to be performed by the process.

According to a sixth broad form the present invention provides a processing system for restricting recordal of user activity in the processing system comprising 

means to determine if a process initiating the kernel device driver API call is attempting to perform an activity comprising at least one of 

According to a seventh broad form the present invention provides a method of restricting recordal of user activity in a processing system the method comprising 

determining if a process is attempting to alter an input device interrupt related to the interrupt structure and

In one particular but non limiting form the method comprises intercepting a hook for writing to kernel structures.

based on the results on the comparison determining whether the process is attempting to alter an input device interrupt related to the monitored interrupt structure.

in response to a discrepancy between the global internal table and the temporary table copying the global internal table to the kernel structure.

According to an eighth broad form the present invention provides a processing system for restricting recordal of user activity in the processing system comprising 

means to determine if a process is attempting to alter an input device interrupt related to the monitored interrupt structure and

means to restrict the alteration of the input device interrupt in response to a positive determination.

According to a ninth broad form the present invention provides a computer readable medium of instructions for giving effect to any of the aforementioned methods or systems. In one particular but non limiting form the computer readable medium of instructions are embodied as a software program.

The following modes given by way of example only are described in order to provide a more precise understanding of the subject matter of a preferred embodiment or embodiments.

A particular embodiment of the present invention can be realised using a processing system an example of which is shown in . In particular the processing system generally comprises at least one processor or processing unit or plurality of processors memory at least one input device and at least one output device coupled together via a bus or group of buses . In certain embodiments input device and output device could be the same device. An interface can also be provided for coupling the processing system to one or more peripheral devices for example interface could be a PCI card or PC card. At least one storage device which houses at least one database can also be provided. The memory can be any form of memory device for example volatile or non volatile memory solid state storage devices magnetic devices etc. The processor could comprise more than one distinct processing device for example to handle different functions within the processing system . Input device receives input data and can comprise for example a keyboard a pointer device such as a pen like device or a mouse audio receiving device for voice controlled activation such as a microphone data receiver or antenna such as a modem or wireless data adaptor data acquisition card etc. Input data could come from different sources for example keyboard instructions in conjunction with data received via a network. Output device produces or generates output data and can comprise for example a display device or monitor in which case output data is visual a printer in which case output data is printed a port for example a USB port a peripheral component adaptor a data transmitter or antenna such as a modem or wireless network adaptor etc. Output data could be distinct and derived from different output devices for example a visual display on a monitor in conjunction with data transmitted to a network. A user could view data output or an interpretation of the data output on for example a monitor or using a printer. The storage device can be any form of data or information storage means for example volatile or non volatile memory solid state storage devices magnetic devices etc.

In use the processing system is adapted to allow data or information to be stored in and or retrieved from via wired or wireless communication means the at least one database . The interface may allow wired and or wireless communication between the processing unit and peripheral components that may serve a specialised purpose. The processor receives instructions as input data via input device and can display processed results or other output to a user by utilising output device . More than one input device and or output device can be provided. It should be appreciated that the processing system may be any form of terminal server specialised hardware or the like.

The processing system may be a part of a networked communications system. Processing system could connect to network for example the Internet or a WAN. Input data and output data could be communicated to other devices via the network. The transfer of information and or data over the network can be achieved using wired communications means or wireless communications means. A server can facilitate the transfer of data between the network and one or more databases. A server and one or more databases provide an example of an information source.

Referring now to there is illustrated an example flow chart showing the process of intercepting an API call. At step an event occurs in the processing system. At step an operating system running in the processing system registers the occurrence of the event. At step the operating system passes the registered event to the hook chain. At step the event is passed to each hook in the hook chain such that different applications processes and devices may be notified of the registered event. Once the event has propagated throughout the hook chain the method comprises at step an application receiving notification of the event being registered by the processing system. At step the application initiates an API call to an API procedure so as to carry out a response to the registered event. If an API hook has been established between the API call and the API procedure the API call is intercepted before it reaches the API procedure. The API call may be allowed to continue calling the API procedure at step or the API call may not be passed on to the API procedure as shown at step .

An example method for restricting recordal of user activity in a processing system using interception of a kernel API call will now be described with reference to .

In particular at step the method comprises intercepting a kernel API call. Then at step the method comprises determining if a process initiating the kernel API call is malicious. If the process is determined to be malicious the method comprises terminating the determined process at step . If the process is determined not to be malicious the method may optionally return to the beginning of the method and continue to determine whether any other processes are malicious.

A more detailed example of a method for restricting recordal of user activity in a processing system using interception of kernel API calls will now be described with reference to .

In particular at step the processing system is configured to intercept a kernel API call. The kernel API call may or may not be intercepted in processes system wide although usually this may be done system wide. However a person skilled in the art will appreciate that it is not essential that the kernel API call be system wide.

At step the behaviour of the process is analysed to determine if the process is suspicious. This may comprise for example determining if the API call is GUI or non GUI related whether the process comprises a hidden window comparing the process to signatures of known keylogger programs and comparing the process to other common behavioural traits of keylogger software. If the process is determined to be suspicious the method moves to step .

At step the method comprises the processing system determining whether the initiating process of the intercepted API call is malicious based on the results of step . If the processing system determines that based on the behavioural analysis the initiating process is malicious the method moves to step otherwise the API call is passed to the API procedure as shown at step and the method returns to intercepting other kernel API calls at step .

At step the method comprises identifying the requesting or initiating process. Thus process information is generated in regard to the particular process wherein the process information may comprise at least one of a name of the process a process identity number a user that the process belongs a time the process was started a parent process identity number associated processing cycles for the process and or any associated open port number.

At step the method comprises the determined process being terminated or killed. Therefore the process stops requesting notification of the particular event occurring. For example if the determined malicious process were a keylogger attempting to establish a hook in the hook chain to subsequently record keystrokes the process would be restricted from being inserted into the hook chain.

Optionally as indicated by the dotted outline at step the user may be notified of the determined process and its subsequent termination. Additionally the user may be prompted to authorise the termination of determined process. Optionally the generated process information and determined parameters may be stored in file stored in the processing system s data store such that a record of the terminated process may be subsequently viewed by a user.

An example method for restricting recordal of user activity in a processing system using interception of an input device API call for the processing system will now be described with reference to .

In particular at step the method comprises intercepting an input device API call. Then at step the method comprises determining if a process is requesting a state of an input device using the intercepted input device API.

In response to a positive determination of a process requesting the state of an input device the method comprises at step updating a table stored in the processing system s data store with request information related to the determined process. In response to a negative determination the input device API call is allowed to proceed to the API procedure at step and as such the method continues to intercept appropriate API calls at step .

At step the method comprises determining if a trend of requests exists by the process. If a trend exists the method moves to step to terminate the process. Otherwise the method optionally continues to monitor processes requesting the state of the input device at step .

A more detailed example of a method for restricting recordal of user activity in a processing system using interception of an input device function for the processing system will now be described with reference to .

In particular at step the method comprises intercepting an input device API call. Typically this would comprise intercepting a keyboard wide or mouse wide API call.

At step the processing system is configured to determine if the initiating process of the input device API call is requesting the state of an input device such as a keystroke pressed on a keyboard. In response to a positive determination the method continues to step otherwise the method continues to monitor processes requesting the state of the input devices being monitored.

At step the method comprises determining the requesting process. This step would be similarly performed to step previous discussed.

At step the method comprises generating request information related to the requesting process. Thus the process information generated in step as well as parameter information may be used for generating request information for the associated process.

At step the method comprises updating a table with the generated request information. The table is typically stored in the processing system s data store i.e. memory. The table typically comprises past request information for processes that have requested the status of the monitored input devices. Therefore the table may be used by the processing system for determining a trend in requests for the status as performed at step .

At step the information stored in the request information undergoes a behavioural analysis. This may comprise analysis of a continual polling of the status polling at regular intervals such as every tenth of a second whether the GUI or non GUI related whether there is hidden windows and other such variations of suspicious behaviour.

At step the method comprises the processing system determining using the results of the behavioural analysis whether the initiating process is malicious. If the process is determined to not be malicious the method continues back at step . However if the process is determined to be malicious the process is terminated at step .

Optionally as indicated by the dotted outline at step the user may be notified of the process as earlier described in relation to .

An example of a method for restricting recordal of user activity in a processing system using interception of a kernel device driver API call for the processing system will now be described with reference to .

In particular at step the method comprises intercepting a kernel device driver API call. Then at step the method comprises determining if a process is attempting to alter a device driver using the intercepted device driver API call. In response to a positive determination of a process attempting to maliciously alter the device driver the method comprises restricting the process from calling the API procedure at step .

A more detailed example of a method for restricting recordal of user activity in a processing system using interception of a kernel device driver API call for the processing system will now be described with reference to .

In particular at step the method comprises intercepting a kernel device driver API call. Therefore any attempted modification alteration replacement or deletion of a device driver is intercepted such as the alteration of a mouse or keyboard driver.

At step the method comprises determining whether a process initiating the API call is attempting to alter a device driver. In response to a positive determination the method continues to step otherwise the method continues to monitor any intercepted processes that may be altering a device driver.

At step the method comprises determining if the user requires a prompt regarding the determined process attempting to alter the device driver. If the user requires prompting the method moves to step otherwise the API call is passed to the API procedure at step and the method continues to step where kernel device driver API calls are continued to be intercepted.

Thus at step a prompt may be displayed comprising for example a graphical window warning of the determined process and requesting the user to provide a response to the prompt. The prompt may request an indication as to whether the user wishes to proceed with allowing the process to alter the device driver.

At step the processing system receives a response from the user regarding the prompt. At step the method comprises determining using the received response whether the user wishes to allow the process to continue altering the device driver. In response to the user indicating that the user does wish to allow the process to continue altering the device driver the API call is passed to the API procedure as illustrated by step . However if the user indicated that the device driver is not to be altered the method moves to step .

At step the method comprises restricting the process from altering the device driver by not allowing the API call passing to the API procedure.

At step the method optionally comprises notifying the user of the terminated process similarly described to step .

An example of a method for restricting recordal of user activity in a processing system by monitoring an interrupt structure of a kernel for the processing system will now be described with reference to .

In particular at step the method comprises monitoring the interrupt structure of the operating system kernel. This allows for particular interrupts associated with redirecting parameters associated with keystrokes to malicious programs.

Alternatively this may comprise for example the kernel structure being read and stored in a global internal table and additionally a temporary internal table is created which can be compared to the global table repeatedly to determine if an alteration has occurred.

At step the method comprises determining whether a process is attempting to alter an input device interrupt in the interrupt structure. In response to determining that the process is attempting to alter the input device interrupt the method comprises at step restricting the process from altering the interrupt structure and thus restricting parameters such as keystrokes to be recorded.

This may comprise for example restricting the next hook in the hook chain from being called as this method restricts the kernel structure from being altered. The user may be notified of a process being restricted from altering the kernel structure.

Alternatively this may comprise for example comparing the internal temporary table to the global table. If a change has occurred in the temporary table a comparison to the global table may determine a discrepancy and as a result of this determination the global table is written back to the kernel structures. Additionally the user may be notified of the restriction of a process altering the kernel structures.

It will be appreciated by the person skilled in the art that any combination of keylogger blocking methods described in through to may be used together in order to increase the success of detecting a keylogger program.

Referring now to there are illustrated example system structures that provide various embodiments of behaviour based keylogger blockers.

Illustrated in is a system for providing a keylogger blocker based on kernel API call interception. The keylogger components of keylogger software are prevented from functioning correctly by examining keylogger behaviour blocking suspicious activity by preventing the keylogger establishing a hook in the hook chain and terminating the suspicious process. This can be achieved as follows 

2 On any calls to the kernel APIs B examine specified parameters and determine whether a process is malicious. If this is the case terminate the calling process H and optionally notify the user and 

3 On any calls to the keyboard mouse state APIs B update an internal table stored at either F or G . This table can contain the calling process and last request for information using the API. If it is determined that the exhibited behaviour is suspicious then the calling process H is terminated and the user is optionally notified.

Determining whether calls to state APIs are suspicious can be achieved by constant periodic or routine eg. intermittent but with a short and somewhat constant timeframe polling of the keyboard state.

An example of pseudocode that may be used for providing a keylogger blocker based on API interception is shown below.

Illustrated in is a system for providing a keylogger blocker based on driver interception and or substitution. Keyboard loggers may replace the system keyboard driver with their own code which apart from controlling the keyboard directly or indirectly can be used to record all keys pressed by a user. This behaviour can be detected and prevented as follows 

b Prompt the user E as to whether the change should be allowed and process the system request accordingly.

Illustrated in is a system for providing a keylogger blocker based on kernel mode interrupt. More advanced keyboard loggers may use undocumented or exploitable features of an operating system kernel to set up or install code which is called whenever the keyboard hardware interrupt is invoked. Internal kernel structures can be monitored and any changes to the keyboard interrupt handler can be prevented as follows 

A first example of pseudocode that may be used for providing a keylogger blocker based on kernel mode interrupt is shown below.

A second example of pseudocode that may be used for providing a keylogger blocker based on kernel mode interrupt is shown below.

The embodiments illustrated in may be implemented separately or in any combination as a software package or component. Such software can then be used to pro actively seek to prevent any malicious software based keylogger from being invoked on a terminal. Various embodiments can be implemented for use with the Microsoft Windows operating system or any other modern operating system.

Optional embodiments of the present invention may also be said to broadly consist in the parts elements and features referred to or indicated herein individually or collectively in any or all combinations of two or more of the parts elements or features and wherein specific integers are mentioned herein which have known equivalents in the art to which the invention relates such known equivalents are deemed to be incorporated herein as if individually set forth.

Although a preferred embodiment has been described in detail it should be understood that various changes substitutions and alterations can be made by one of ordinary skill in the art without departing from the scope of the present invention.

