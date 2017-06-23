---

title: Method and system for executing a container managed application on a processing device
abstract: There is provided a system for executing a container-managed application in a processing device, the system comprising a shared service container providing at least one common service for the processing device, executed in at least one process and at least one container-managed application, each comprising an application executed in a given process and accessing at least one service of the application and the at least one common service using a single service discovery API.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07877091&OS=07877091&RS=07877091
owner: Research In Motion Limited
number: 07877091
owner_city: Waterloo, ON
owner_country: CA
publication_date: 20060418
---
This patent application claims priority of U.S. Patent No. 60 672 091 that was filed Apr. 18 2005 and which is entitled Method and system for executing a container managed application on a processing device the specification of which is hereby incorporated by reference.

This application relates to the field of computer programs. More precisely this application pertains to a method and system for executing a container managed application in a processing device.

Having a container based execution framework is already known on wireless devices. A service container architecture such as OSGI provides the ability to manage software components. The containers are usually limited to executing all components in one process displaying a single user interface and executing a single instance of an application.

It will be appreciated that a process may be regarded as the context in which an application is executed by the operating system.

Also it is known for a process to send messages to each other through inter process message pipes or application program interface API calls.

Unfortunately various issues may arise from inter process communication in a container based environment. In fact it will be appreciated that in the case of container managed applications the decision is made by the container based on an application descriptor. The container that makes a decision about access to the component principally identifies the client client s security roles and roles required to get access to the component or its method. It is therefore possible that the container maliciously accesses some resources.

It will be noted that throughout the appended drawings like features are identified by like reference numerals.

According to one aspect there is provided a system for executing a container managed application in a processing device the system comprising a shared service container providing at least one common service for the processing device executed in at least one process and at least one container managed application each comprising an application executed in a given process and accessing at least one service of the application and the at least one common service using a single service discovery API.

According to another aspect there is provided a method for accessing a service on a processing device the method comprising providing a shared service container comprising at least one common service to the processing device executed in at least one process and in a container managed application comprising applications executed in a corresponding process accessing a given service of one of the applications and the common service using a single service discovery API.

In this specification the term process is intended to mean a program in execution which progresses in a sequential manner i.e. a call stack .

In this specification the term service container is intended to mean a process that can host software components .

Now referring to there is shown one embodiment of a system wherein a program script of an application may access a service comprised in a service container. It will be appreciated that this may be used in any type of processing device such as for instance in a personal data assistant PDA a cell phone or the like.

More precisely the system comprises a shared process which comprises a shared service container . The system further comprises at least one application process each of which comprises a corresponding service container. In the embodiment disclosed in the system comprises a first application process comprising service container and a second application process comprising service container .

The service container of the shared process provides services such as lifecycle management related services communication related services security related services storage related services etc. to at least one application as explained further below.

In the embodiment disclosed in the shared service container comprises a first common service a second common service and a third common service .

The shared service container of the shared process further comprises a pluggable interface and a service discovery application programming interface API .

The pluggable interface is adapted for providing an interface between the service discovery API and at least one common service.

The service discovery API is used for accessing at least one of the common services as further explained below.

The service container comprises a pluggable interface at least one application service and a service discovery API .

In the embodiment disclosed in the service container comprises a first application service a second application service and a third application service .

Each application service is used by a given application. It will be appreciated that the application service is dedicated to a single application.

The pluggable interface is adapted for providing an interface between the service discovery API and the at least one application service.

The service discovery API is used for accessing at least one of the application services as further explained below.

The service container comprises a pluggable interface at least one application service and a service discovery API .

It will be appreciated that an application service comprises application specific services that are only logical within the context of logic execution and or script interpretation of a single program such as a user interface.

In the embodiment disclosed in the service container comprises a first application service a second application service and a third application service .

Each application service is used by a given application. It will be appreciated that a given application service is dedicated to a predetermined application.

The pluggable interface is adapted for providing an interface between the service discovery API and the at least one application service.

The service discovery API is used for accessing at least one application service as further explained below.

Now referring to there is shown how a service is accessed when an application is executed according to an embodiment.

According to step a shared service container providing at least one common service executed in at least one process is provided.

It will be appreciated that the shared service container comprises at least a common service and a service discovery API.

It will be appreciated that the service discovery provided in the shared service container comprises an indication of the common services that are comprised in the shared service container.

Still referring to and according to step a given service is accessed using a single service discovery API in a container managed application.

According to step a search is performed in order to find out if the given service is available locally. It will be appreciated that in fact a service may be available inter alia locally to an application or it may be available in the shared service container.

It will be appreciated that the search is initiated in response to one of an invoke command and an event signal performed by an executing program script.

It will further be appreciated that the search is performed using the service discovery API. As explained above the service discovery API is aware of the local services available.

In the case where the given service is not available locally in the service container of the application a search is performed to find out if the given service requested is available in the shared service container.

According to step a test is performed in order to find out if the given service requested is available in the shared service container.

In the case where the given service requested is available in the shared service container and in the case where the service requested is available locally and according to step a reference is returned to a caller.

The skilled addressee will appreciate that having a service discovery API is of great advantage as it enables an application to have access to a service in a transparent manner which is of great advantage for security purposes

It will also be appreciated that the shared service container is executed in a first given process while other applications are executed using other processes.

It will also be appreciated that the shared service container may be executed in a single as well as in multiple processes.

While illustrated in the block diagrams as groups of discrete components communicating with each other via distinct data signal connections it will be understood by those skilled in the art that the preferred embodiments are provided by a combination of hardware and software components with some components being implemented by a given function or operation of a hardware or software system and many of the data paths illustrated being implemented by data communication within a computer application or operating system. The structure illustrated is thus provided for efficiency of teaching the present preferred embodiment.

It should be noted that the present application can be carried out as a method can be embodied in a system a computer readable medium or an electrical or electro magnetical signal.

The embodiments described above are intended to be exemplary only. The scope is therefore intended to be limited solely by the scope of the appended claims.

