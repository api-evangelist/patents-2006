---

title: Method for monitoring control devices
abstract: A method for carrying out a control device monitoring, a program flow control being implemented for at least one event-synchronous process in the control device monitoring. The monitoring module is developed for carrying out a control device monitoring, A program flow control is implemented for at least one event-synchronous process in the control device monitoring.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08806443&OS=08806443&RS=08806443
owner: Robert Bosch GmbH
number: 08806443
owner_city: Stuttgart
owner_country: DE
publication_date: 20060508
---
The present invention relates to a method for monitoring control devices a monitoring module for monitoring control devices a computer program having program code means and a computer program product having program code means.

The monitoring of control devices is usually performed using a program execution control for time synchronous processes. This program flow control ensures that for the control device monitoring important program parts are run through cyclically in a specified time pattern and in a specified sequence. Accordingly the control device monitoring is tied to a fixedly specified scheme in time.

German Patent Application No. DE 100 61 001 describes a method for controlling technical procedures. In this context a control program is processed wherein the control program is subdivided into several tasks and each task includes at least one process. Individual processes of the tasks are listed in the sequence of their processing in this instance. A process sequence stored during the processing of the control program is thus able to be reproduced completely.

The present invention relates to a method for carrying out a control device monitoring a program flow control being implemented for at least one event synchronous process in the control device monitoring.

By the use of this method it is possible to broaden common time synchronous program flow controls by implementing the program flow control for event synchronous processes in the control device monitoring which can specify a scheme for monitoring the control device.

The control device monitoring should particularly be carried out for a control device that is developed for the regulation control influencing and the like of a system. In this context it is provided that at least one event occurs for the system and or within the system. Consequently the program flow control for the control device monitoring takes place synchronously with the at least one event. The control device monitoring and the implemented program flow control can accordingly be aligned with a method of functioning of the control device so that the control device monitoring is carried out as a function of and or consideration of the at least one event.

Control devices can be used in different mechatronic systems for instance motor vehicles or commercial vehicles. Using these control devices different systems for which the events occur and or operate during an operation can be controlled. Consequently it is possible to take into consideration various real operating states that can be characterized by the events for control device monitoring.

In a preferred embodiment a program flow control for at least one rotational speed synchronous process can be implemented as a special event synchronous process in the control device monitoring.

The monitoring module according to the present invention is developed for carrying out a control device monitoring a program flow control for at least one event synchronous process being implemented in the control device monitoring.

The computer program according to the present invention having program code means is provided to implement all steps of the method according to the present invention when the computer program is executed on a computer or a corresponding computing unit especially in the monitoring module according to the present invention.

The computer program product according to the present invention having program code means that are stored on a computer readable storage medium is suitable for executing all the steps of the method according to the present invention if the computer program is executed on a computer or a corresponding computing unit in particular in a monitoring module according to the present invention.

In the usual methods for control device monitoring a program flow control is provided for time synchronous processes. It follows a program flow shown in the diagram in by a dashed meandering line which progresses according to a specified scheme in time. In the present case program flow control includes a task which includes several processes which according to program flow are run through or processed one after the other.

In a first process a first query is first of all carried out as a function of a first check word MoCPFC Set Checkword A . This is followed by a response MoCPFC Check . Correspondingly in an additional process that follows in the course of program flow there follows a query which is carried out as a function of a second check word. MoCPFC Set Checkword Z whereupon a response ensues MoCPFC Check . These queries and the results of responses are supplied to a data file PFC state data for task as shown by the bent arrows. This data file includes a counter MoCPFC Counter query words MoCPFC Checkword check sums MoCPFC Checksum as well as partial responses MoCPFC PartResp . Data for this data file are supplied from an additional module MoCCom Co proc .

To close query program flow arrives at a closing process MoCPFC . This closing process is ended by a comparison MoCPFC End between this comparison and data file an exchange of data takes place as shown by the bent double arrow. Furthermore start commands MOCPFC START ID and or restart commands MOCPFC RESTART ID are transferred to this comparison from a data file for configuration data PFC configuration data which is at the end of the program flow. Moreover as indicated by the bent double arrow between comparison and a data file MoCCom data which includes query routines such as MoCCom stQueryNew MoCCom Query an exchange of data takes place.

This program flow control ensures that for the control device monitoring important program parts are run through cyclically in a specified time pattern and in a specified sequence in this case following program flow . A process and a program module are recognized as being processed if they are begun correctly and terminated correctly. In this connection a module frame for a process in the form of an initial processing in this case a query and a final processing in this case a response has to be sufficient for the following conditions A through D 

 A Every respective process and every respective module has to be processed in a specified time pattern. A processing of the program flow control must be constantly active so as not to permit any errors within a processing pattern.

 B A missing processing of one of processes must not be able to be replaced by a single or multiple processing of another process or module.

 C Errors within a program flow of important program parts have to lead to a specified error reaction.

 D For different queries program flow control has to lead to different responses in order to prevent that a sequence control that has once run through correctly will constantly lead to the correct response. Furthermore a safeguarding of a memory TOM in an established area has to take place separately in order to ensure that a program code between the initial and final processing of program modules is correct.

Conditions or requirements A B and C that were named above can be fulfilled because of a module specific establishment of individual module detections and their steady cyclical processing to form partial responses to queries of a separate hardware monitoring module. The last requirement D fulfills the merging of stipulated queries into program flow control to form reponses.

The control device monitoring for time synchronous processes as shown in presupposes that the program parts are processed time synchronously and that response contributions are supplied time synchronously and cyclically to databank .

In a schematic representation shows a preferred specific embodiment of a program flow control for time synchronous processes which is implemented into a control device monitoring for generating a response contribution from a time synchronous sub process t snc Sub Process A using a plausible counter reading from an event synchronous process n sync. Process A within a program flow control .

Starting from an interrupt for an event synchronous function part or event synchronous process an identifier set Flag is set at beginning of a program code. If at the end of the program code of the event synchronous process this identifier is still set a counter is incremented increase counter and the identifier is subsequently reset again reset flag .

This counter is evaluated and analyzed or valued into time synchronous sub process . By comparison of a counter reading check counter value having event dependent applicable and usable window boundaries and in a special case having rotational speed dependent window boundaries a plausibility check is carried out with regard to counter reading . These window boundaries have to be applied or used while taking into consideration the expected callup frequency of event synchronous process and of the time pattern of time synchronous sub process .

After plausibility check as was brought out in there takes place a query after a check word MoCPFC Set Checkword Z as well as a corresponding response MoCPFC Check . Thereafter a resetting reset counter of the counter reading can take place. If the event synchronous counter reading related to a working point in this case the rotational speed is plausible a response contribution for the event synchronous functional component is sent from time synchronous sub process according to response . If the counter reading is implausible with respect to the working point no response contribution is sent that is after a debounce an error response is carried out. After the sending of the response contribution the counter in time synchronous sub process is reset to zero again.

The method presented is implementable by the deactivation of event synchronous processes which supply a contribution to response for program flow control by subsequent error response at debounced activation of an output stage of a control device.

In the case of the above mentioned specified error response what is involved is a deactivation performed after a debouncing of a system to be controlled by the control device. In this connection the system is transferred into a safeguarded state. In one possible specific embodiment such a system may be an end of injection stage for shutting off an injection within a motor vehicle.

A proper execution of program parts of the control device monitoring is monitored for various control devices using the so called MISR check sum method. A result of program flow control goes as a partial response into the query communication response communication having a monitoring module.

The method can be used for all control devices in which a program flow control is implemented for the control device monitoring.

