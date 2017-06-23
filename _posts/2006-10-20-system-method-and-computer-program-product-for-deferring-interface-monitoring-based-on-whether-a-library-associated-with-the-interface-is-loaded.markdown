---

title: System, method and computer program product for deferring interface monitoring based on whether a library associated with the interface is loaded
abstract: An interface monitoring system, method and computer program product are provided. In use, an interface is identified. In addition, monitoring of the interface is deferred based on whether a library associated with the interface is loaded.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08739188&OS=08739188&RS=08739188
owner: McAfee, Inc.
number: 08739188
owner_city: Santa Clara
owner_country: US
publication_date: 20061020
---
The present invention relates to monitoring interfaces and more particularly to monitoring interfaces contained in libraries.

Interfaces such as application program interfaces API s are generally monitored for various reasons. For example interfaces may be monitored for security purposes for understanding a flow of applications for tracking problems associated with applications etc. Traditionally monitoring interfaces has involved hooking the interfaces such that invocations of the interfaces e.g. via calls made with respect to the interfaces etc. are handled by a monitoring application. However hooking interfaces contained in libraries e.g. dynamic link libraries DLLs may potentially cause problems when such libraries are artificially e.g. prematurely etc. loaded for monitoring purposes.

An interface monitoring system method and computer program product are provided. In use an interface is identified. In addition monitoring of the interface is deferred based on whether a library associated with the interface is loaded.

Coupled to the networks are servers which are capable of communicating over the networks . Also coupled to the networks and the servers is a plurality of clients . Such servers and or clients may each include a desktop computer lap top computer hand held computer mobile phone personal digital assistant PDA peripheral e.g. printer etc. any component of a computer device and or any other type of logic for that mater. In order to facilitate communication among the networks at least one gateway is optionally coupled therebetween.

The workstation shown in includes a Random Access Memory RAM Read Only Memory ROM an I O adapter for connecting peripheral devices such as disk storage units to the bus a user interface adapter for connecting a keyboard a mouse a speaker a microphone and or other user interface devices such as a touch screen not shown to the bus communication adapter for connecting the workstation to a communication network e.g. a data processing network and a display adapter for connecting the bus to a display device .

The workstation may have resident thereon any desired operating system. It will be appreciated that an embodiment may also be implemented on platforms and operating systems other than those mentioned. One embodiment may be written using JAVA C and or C language or other programming languages along with an object oriented programming methodology. Object oriented programming OOP has become increasingly used to develop complex applications.

Of course the various embodiments set forth herein may be implemented utilizing hardware software or any desired combination thereof. For that matter any type of logic may be utilized which is capable of implementing the various functionality set forth herein.

As shown in operation an interface is identified. In the context of the present description the interface may include any computer code data structure or protocol that facilitates communication between a first instance of hardware or software with another instance of hardware or software. In one optional embodiment such hardware or software may be a component of any of the devices described above with respect to . In another embodiment the interface may include a software interface. For example the interface may include an application programming interface API for facilitating communication between an application and an underlying operating system.

Additionally the interface may be identified in one possible embodiment by identifying an invocation of the interface. Optionally such invocation of the interface may involve a call to the interface. In another embodiment the call to the interface may be made by an application. Of course it should be noted however that the interface may be identified in any desired manner that at least potentially prompts the monitoring thereof.

Still yet monitoring of the interface is deferred based on whether a library associated with the interface is loaded as shown in operation . In the context of the present description the library may include any collection of computer code that may be used by other computer code. In one optional embodiment the library may include a library that at least in part contains the interface. In this way the library may include a hosting library that hosts the interface.

As another option the library may include at least one linked library. For example loading of the library may optionally include loading any linked libraries associated therewith. In one exemplary embodiment the linked library may include a dynamic link library DLL . Thus the library associated with the interface may be loaded explicitly e.g. independent of linked libraries etc. or implicitly e.g. as a library linked to another library being loaded etc. .

Further it should be noted that the library may be loaded in any desired manner. Just by way of example the library may be loaded into a process. Of course such loading may include anything that results in the library being made at least in part accessible to the computer code adapted for using the same.

Moreover monitoring of the interface may include hooking the interface in one exemplary embodiment. Such hooking may even allow a flow of the interface and an application associated therewith etc. to be monitored. Of course in the context of the present description such interface monitoring may involve the identification of any desired aspect of the interface for any purpose.

In one embodiment the interface monitoring may be initiated if it is determined that the library associated with the interface is loaded. In another embodiment the interface monitoring may be deferred if it is determined that the library associated with the interface is not loaded. In this way artificial e.g. premature etc. loading of the library for monitoring purposes may optionally be avoided which may therefore possibly limit the amount of intrusion necessary for monitoring the interface.

More illustrative information will now be set forth regarding various optional architectures and features of different embodiments with which the foregoing framework may or may not be implemented per the desires of the user. It should be strongly noted that the following information is set forth for illustrative purposes and should not be construed as limiting in any manner. Any of the following features may be optionally incorporated with or without the exclusion of other features described.

As shown in operation an API is identified. As described above with respect to the API may be identified based on an invocation of the API e.g. a call made to the API etc. . Of course however the API may be identified in any desired manner.

It is then determined whether a library associated with the API has been loaded as shown in decision . For example such library may be loaded in an associated process. In one embodiment the determination may be made based on an interception of an invocation of a library loading interface e.g. Microsoft Windows LoadLibrary interface etc. .

In another embodiment the determination may be made by intercepting a file system event. Optionally such file system event may be intercepted by a file system filter. Further the file system event may indicate that the library has been loaded. Just by way of illustration the file system event may involve mapping a file that contains an on disk image of the library. Of course it should be noted that it may be determined that the library associated with the API has been loaded in any desired manner.

If it is determined that the library associated with the API has been loaded the API is hooked in a normal fashion as shown in operation . The API may be hooked by intercepting calls made in association with the API for example. Thus determining that the library associated with the API has been loaded may indicate that the API is reliably available for monitoring purposes.

If however it is determined that the library associated with the API has not been loaded the API is added to a list of pending API s to be hooked as shown in operation . Such list of pending API s to be hooked may include any number of API s which have been identified as in operation but for which a library has not yet been loaded. It should be noted that the list of pending API s to be hooked may include any desired data structure e.g. queue list database etc. capable of storing data associated with API s to be hooked. Thus API s may be processed based on whether an associated library has been loaded in a manner that will be set forth.

As shown in operation an invocation of an API is intercepted. The invocation of the API may be intercepted by monitoring API invocations e.g. calls made to the API etc. . In one optional embodiment the invocation of the API may be intercepted by hooking the API. In use the invocation of the API may be performed within a process that is independent separate from a monitoring of API s.

It is then determined whether the API is utilized at least in part for loading a library as shown in decision . In one embodiment such determination may be made by following the flow of the invoked API. From such flow it may be determined if a request to load a library has been made by the API.

If it is determined that the API is not utilized at least in part for loading a library a next invocation of an API may be intercepted in a similar manner as described above with respect to operation . If however it is determined that the API is utilized at least in part for loading a library a list of API s for which monitoring is pending may be processed as described in more detail with respect to . In addition a next invocation of an API may be intercepted as described above with respect to operation . In this way libraries that have been loaded may be continuously identified such that API s within the list of API s for which monitoring is pending may be processed to determine whether monitoring may be initiated.

In another embodiment and as described above with respect to loaded libraries may be identified based on intercepted file system events. For example such file system events may indicate that a library has been loaded. Accordingly file system events may be identified by monitoring such file system events.

As shown in operation the intercepted invocation of an API is allowed to complete processing of a library load request. Accordingly such API may be utilized in loading a library such as that described above with respect . As a result a library is allowed to be loaded based on a library load request associated with the API.

The list of pending API s to be hooked is then retrieved as shown in operation . The list of pending API s to be hooked may be retrieved by being read accessed etc. Further as shown in operation the list of pending API s to be hooked is processed.

One example of processing such list of pending API s to be hooked will now be described in more detail with respect to . Specifically the list of pending API s to be hooked may be processed based on the identified library load request. Of course it should be noted that such list may be processed in any desired manner that results in a potential situation where additional API s with loaded libraries may be monitored.

As shown in operation a first API is retrieved from the list of pending API s to be hooked. The first API may be retrieved by reading such API from the list for example. It is then determined whether the API is available in a current process as shown in decision . In particular it is determined whether a library e.g. host library etc. associated with the API is loaded by virtue of the library load request noted in operation of .

If it is determined that such a library is loaded the API is hooked as shown in operation . Accordingly a determination that the library is loaded may indicate that the API is available for hooking. In addition an entry for such API e.g. data associated therewith etc. is removed from the list of pending API s to be hooked as set forth in operation . Thus the list of pending API s to be hooked may be updated as libraries associated with API s included therein are loaded.

If however it is determined that such a library is not loaded then it is determined whether there is another API in the list of API s to be hooked. Note operation . Thus API s for which a library has not been loaded may remain in the list until an associated library is loaded. As shown it may also be determined whether there is another API in the list upon removing an API entry from such list operation . If it is determined that another such API exists the next API in the list of API s to be hooked is retrieved as shown in operation .

In this way each API in the list of API s to be hooked may be checked to determine if a library associated therewith has been loaded. In the context of a primary loaded library that includes at least one linked library e.g. a linked library that has been loaded as a consequence of the loading of the primary library etc. the identification of the loaded library as described in may allow API s in the list to be checked against all loaded libraries including such linked libraries. As a result API s in the list may be checked against all loaded libraries regardless of the identified loaded library that initiated such a check. Thus API s available for hooking may be efficiently identified.

In addition the utilization of a list of pending API s to be hooked may limit intrusion with respect to artificially e.g. prematurely etc. loading libraries for monitoring purposes. In particular libraries may be allowed to load as they normally would in a situation not including any sort of monitoring such that monitoring of associated API s may be deferred until associated libraries are loaded.

Accordingly a plurality of situations associated with artificially loading such libraries may optionally be prevented. In one embodiment side effects within a process that would not normally be utilized for loading a library may be avoided. For example library initialization code associated with a library that could potentially cause problems within a process in which such code would not normally be run may be prevented.

In another embodiment timing within a process in which a library would normally be run in may be maintained. For example library initialization code that is dependent on a load order with respect to other libraries may be run such that the load order is maintained. By way of illustration it may be ensured that a persistent variable that library initialization code depends upon is available at the time the library is loaded.

Moreover a reference count associated with the library may be prevented from being increased such that the library is incapable of being unloaded. Thus processes expecting to unload and or reload the library e.g. for updating purposes etc. may not necessarily encounter any problems that may otherwise occur if the library is artificially loaded for monitoring purposes. In this way such processes may be able to proceed in a normal fashion.

While various embodiments have been described above it should be understood that they have been presented by way of example only and not limitation. Thus the breadth and scope of a preferred embodiment should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

