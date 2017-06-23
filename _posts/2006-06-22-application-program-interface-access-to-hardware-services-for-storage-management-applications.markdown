---

title: Application program interface access to hardware services for storage management applications
abstract: A method and device for using a set of APIs are provided. Some of the functions which used to be performed by software are now accelerated through hardware.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07594049&OS=07594049&RS=07594049
owner: 
number: 07594049
owner_city: 
owner_country: 
publication_date: 20060622
---
This application claims is a continuation application of the utility application filed May 2 2003 now U.S. Pat. No. 7 093 038 titled APPLICATION PROGRAM INTERFACE ACCESS TO HARDWARE SERVICES FOR STORAGE MANAGEMENT APPLICATIONS with a Ser. No. 10 428 638 which claimed priority to Provisional Application No. 60 380 160 filed May 6 2002 entitled APPLICATION PROGRAM INTERFACE ACCESS TO HARDWARE SERVICES FOR STORAGE MANAGEMENT APPLICATIONS which is hereby incorporated in its entirety by reference.

The present invention generally relates to an application program interface API more specifically the present invention relates to an API having access to hardware services for storage management applications. Yet more specifically the present invention relates to a Virtualization Acceleration Application Programming Interface VAAPI 

Application program interface API also known as application programming interface is known in the art. API can be considered as a set of specific methods prescribed by a computer operating system or by an application program which a programmer who is writing an application program can make request of the operating system or another application.

The explosive growth if storage networks is being driven by the collaboration of business computing and the need for business continuity. The storage data management silicon model makes the assumption that the next logical step in managing storage networks is to move some of the storage management functionality into storage network with the implementation located in switches router appliances NAS and SAN attached arrays. This model envisions storage virtualization application implemented onto storage network nodes using specialized storage data management silicon to ensure that the node does not become a severe performance bottleneck to the network traffic flowing through it.

To implement storage virtualization in the network the storage virtualization application is effectively split into two function components the control path and the data path as shown in . The control path is responsible for all of the control functions of virtualization including setting up the configuration changing the configuration network and availability management fault tolerance and error recovery. The data path component is responsible for moving the I O through the virtualization application.

The performance characteristics of the storage virtualization engine in this paradigm depends on the amount of the data path that is implemented in hardware. A silicon assisted solution can significantly reduce latencies over software solutions and increase IOP performance many times.

Therefore it is desiouse to have specialized APIs residing in the datapath. Further it is desiouse to have a storage network I O handling framework and a set of APIs for better performance.

A storage network I O handling system including a set of APIs are provided for enabling the separation of Control path configuration and complex exception handling and data path storage I O execution and relatively simpler exception handling related computing.

A storage network I O handling system including a set of APIs is provided in which the data path processing is kept relatively simple in comparison to control path processing and the system is being accelerated with specialized hardware HW for achieving higher performance.

A storage network I O handling system including a set of specialized APIs is provided for defining abstracted interfaces to the configuration information repository from the Storage Management applications in the control path.

A storage network I O handling system including a set of APIs is provided for defining a set of APIs for device configuration configuration loading exception reporting and access to HW accelerated I O processing pipeline such as a storage management processor.

A storage network I O handling system including a set of APIs is provided for optimizing storage network environments with emphasis on performance and ease of development.

A storage network I O handling system including a set of APIs is provided for facilitating implementations with 10 or greater performance scalability characteristics as compared to known processor implementations

A storage network I O handling system including a set of APIs is provided with the system further having an extensible and partition able framework that allows easy integration with a vendor s unique content and APIs

A storage network I O handling system including a set of APIs is provided for leveraging the industry standardization efforts as much as possible. For example CIM and WBEM are heavily leveraged in the repository component of the present application.

A storage network I O handling system including a set of APIs is provided for easy adaptation for implementations other than only CIM WBEM including SNMP and proprietary interfaces

A storage network I O handling system including a set of APIs is provided for a wide adoptablity or support to other vendor storage systems.

Accordingly a method is provided. The method includes providing a virtual disk for an I O request providing an I O execution plan based upon the I O request providing an I O plan executor in hardware and using the I O plan executor to execute the I O plan thereby at least some storage related function are performed by the I O plan executor in hardware.

Accordingly a storage virtualization engine coupled to a control path and a data path is provided. The engine comprising a software sub engine having the control path and data path and a virtualization repository a hardware sub engine having an accelerated data path an VAAPI coupling the software sub engine with the hardware sub engine a management application coupled to the software sub engine wherein command therefrom are processed by the control path thereby some function are performed by hardware through the VAAPI and data are accelerated through the accelerated data path.

Accordingly a storage management system having a control path and a data path is provided. The system comprising a storage virtualization engine the engine includes a software sub engine having the control path and data path and a virtualization repository a hardware sub engine having an accelerated data path an VAAPI coupling the software sub engine with the hardware sub engine a management application coupled to the software sub engine wherein command therefrom are processed by the control path thereby some function are performed by hardware through the VAAPI and data are accelerated through the accelerated data path.

The present invention provides a Virtualization Acceleration Application Programming Interface VAAPI which is interposed between a hardware layer and a software layer. For detailed description of VAAPI please refer to infra. The present invention intendes to create or modify existing storage virtualization applications to take advantage of the fast path acceleration provided by storage data management silicon which is included in a commonly assigned application entitled STORAGE MANAGEMENT PROCESSOR provisional application No. 60 427 593 filed on Nov. 19 2002. Further VAAPI is a strategy to bring concurrence within the storage virtualization industry for the use of a common platform. By providing hardware assisted data movement and related functionality through VAAPI virualization application vendors can boost their performance while positioning their technology on an open platform.

Referring to VAAPI is a storage network I O handling framework and a set of APIs for the following purposes. The purposeses include enabling separation of a control path configuration and complex exception handling and data path storage I O execution and relatively simpler exception handling related computing. The data path processing is kept relatively simple in comparison to control path processing and data path is being accelerated with specialized HW for achieving higher performance. VAAPI further defines abstracted interfaces to the configuration information repository from the Storage Management applications in the control path and defines a set of APIs for device configuration configuration loading exception reporting and access to HW accelerated I O processing pipeline in a storage management processor silicon .

VAAPI resides in the datapath and is a mechanism for implementing the steady state portion of I O in hardware for maximum performance. A storage virualization map not shown is created in the control portion of the storage virtualization and is then pushed to the silicon via the VAAPI interface . If no exceptions to the I O occur it is handled completely in the storage data management silicon with no external processor not shown intervention. In the case of exceptions the VAAPI framework is able to push the I O and the exception to the external processor for processing. The VAAPI framework allows for dynamic updates of the mapping tables maintained in the storage data management silicon . Changes in configurations can occur during runtime via the control portion and be pushed to the silicon via VAAPI without requiring I O interruption.

The steady state component of the data path that is implemented in the storage data management silicon is referred to as the Accelerated Path AP .

The present invention provides the VAAPI which may operate in new virtualization environments that use Common Information Model Web Based Enterprise Management CIM WBEM interfaces look like the one shown in . Compared with the interface of the present invention includes a VAAPI layer interposed between a hardware subsystem which includes an accelerated data path and a hardware acceleration interface . Hardware subsystem is adapted to receive data flow which terminates at terminating points . Terminating points may be such devices as hard disks virtual disks or tapes. Hardware acceleration interface is interposed between accelerated data path and VAAPI layer .

In the present invention such as in the CIM based approach necessary strategic foundations are provided while offering a common basis for adapting to a variety of other environments such as those using Simple Network Management Protocol SNMP or proprietary protocols.

Further the present invention comtemplates a system that has a management application component and a Virtualization Engine . The management application generates and handles the control path information. For example it may use CIM WEBM based interfaces to exchange control information with the Virtualization Engine which is implemented in the hardware.

As can be seen the present invention provides VAAPI layer and hardware subsystem over prior art systems such as the one shown in .

The control path may populate a virtualization repository such as the CIM based repository using standard CIM WBEM formats. A Mapping Table not shown is implemented in the hardware and provides the mapping from the virtual storage to the physical storage. The CIM base repository provides the static information for the storage mapping in the hardware.

In there are two repositories shown one for the software environment and one for the hardware environment. The software repository supports existing vendor s current protocols and related data structures. The hardware repository supports CIM WBEM and is provided by the hardware acceleration vendor. The two repositories need to populate each other and maintain a certain level of synchronization. This functionality is in part accomplished by the VAAPI interface .

Along with normal data and address flows VAAPI also supports delegation of high usage control functions from the software virtualization engine to the hardware virtualization engine . This transfer helps improve data rates and related performances. In order to accomplish this delegation function VAAPI must also include the interfaces for the software control path module to interact with the hardware acceleration engine . This permits VAAPI to handle some of the exception conditions that are normally handled by the current software based Control Path component.

The overall processing of an I O is shown in a flowchart of . Referring to a virtual disk for an I O is identified from the transport protocol information and validated for proper access and proper client etc step . An appropriate I O execution plan is identified for the I O request the logical block addresses are translated to physical block addresses and the corresponding physical devices are identified step . If the I O plan can be handled by the acceleration hardware then the I O is handed off to the I O plan executor hardware step . If it is determined that the I O plan is not executable by the acceleration hardware it is then sent to the control path software step . In case of any exception in the I O plan the plan is sent to the control path software step . The control path software analyzes the incoming I O plans step and after performing required I O operations and or I O exception processing operations step resubmits the original I O plan to the acceleration hardware.

To accomplish the previously described hardware software based shared processing scheme there are requirements for sharing information and control at various places within the hardware storage virtualization environment. These interface points are broadly defined in terms of the following API groups. The groups are CIM WBEM APIs RI APIs alternative RI APIs AP APIs I O APIs and UA APIs.

CIM WBEM APIs are Standard CIM WBEM APIs used to access a CIM implementation. These APIs are defined in CIM WBEM standards documents. RI APIs are APIs used by the control path software for interfacing with the storage virtualization information repository. Implementation of this API group is preferably based on top of CIM WBEM APIs with the repository related software provided. RI APIs Alternative are if the storage virtualization information repository of a vendor is such that the repository could not be translated to a CIM repository then the RI APIs are to be implemented on top of vendor provided APIs. AP APIs are APIs the control path software uses to populate the acceleration hardware with the storage virtualization information that it gets with the RI APIs. I O APIs are APIs used in the control path software for sharing the control and data related to an I O plan with the acceleration hardware. UA APIs are APIs that provide utility functions e.g. Free buffers etc. 

The repository used by the hardware AP environment is an implementation of standard CIM model with standard CIM WBEM APIs that are supported over an HTTPS XML protocol. These APIs are not described in this document since they are described elsewhere in standards documents.

The AP APIs and the corresponding RI APIs are further classified into the following groups based on their information content. Normally for any AP APIs there will be a complimentary API in the RI API.

The following are subcategories associated with VAAPI. These configurations are Virtual Disk Configuration Storage Services Configuration I O Plan Exception Handling Configuration CP AP Shared I O plans AP Pass through I O plans Physical Devices Discovery and Management CP AP Transaction Management Event Handling Performance and Statistics and Utility Functions.

This group of APIs deals with configuration related to individual virtual disk and basic virtualization i.e. disk concatenation and striping . In the VAAPI framework I Os that requires involvement of multiple virtual disks are categorized as Storage Services related I Os. For example mirroring snapshot on line migration etc. are termed as storage services and configuration requirements for these services are handled through a group of APIs termed as Storage Services Configuration that is described later.

The following are examples of VAAPIs of the present invention. The prefixes used to mark this group of APIs are RI RepositoryInterface and AP Accelerated Path .

This group of APIs deals with configuration related to various storage services applications like mirroring snapshot on line migration dynamic multi path etc. This configuration group may involve more than one virtual disks. For example establishing a mirror virtual disk for another virtual disk is done through an API in this group.

The APIs in this group provide configuration related to handling of exceptions in an I O plan in the accelerated path.

The APIs are prefixed with PERI Plan Exception Repository Interface and PEAP Plan Exception Accelerated Path .

The I O APIs provide the facility for dealing with I Os that are generated in the acceleration path and then handled through the control path in case of I O exception. These APIs are prefixed with IO.

a note about ownership of an I O plan. At any point in time an I O plan is either owned by the accelerated path hardware or the control path software. By default the APIs deal with the I O plans that are not owned by the accelerated path. The APIs that deal with I O plans owned by the accelerated path are suffixed with Inap.

These APIs are used to create I O plans from the control path and send it to the devices in a passthrough mode through the acceleration path. These APIs are prefixed with IOP.

These APIs are used to provide a transaction management facility for updating the shared data structures between the control path and the acceleration path in a way that preserves the integrety of the modified data with respect to its use by multiple processors.

In case of any exception while processing an I O from a client according to an I O plan the complete I O plan along with the data is made available to the control path software. The APIs in this group provide the facilities to decode information from the I O plans. Also this API group provides APIs for determining the recipients of the exception information and APIs for sending the exception information.

The APIs in this group are prefixed with EHRI Event Handling Repository Interface and EHAP Event Handling Accelerated Path .

This API group provides access to various performance related counters and values in the accelerated path of the Storage Virtualization Engine. The API group is prefixed with PSRI PerformanceStatisticsRepositoryInterface and PSAP PerformanceStatisticsAcceleratedPath .

These APIs will provide utility functions and are prefixed with UA. Two examples of the API in this category are 

Briefly the following changes need to be implemented in an existing virtualization environment to utilize VAAPI with hardware acceleration. The primary driver will supports API calls including the verbs and formats as specified in VAAPI. The following identifies several of the important areas of impact.

If the Information Repository of the existing application is not CIM based the vendor will either need to convert the existing SNMP or proprietary formats into the CIM object model so that the current VAAPI implementation can get required information from the CIM or the vendor needs to implement the repository interface components of VAAPI on top of the proprietary repository.

The hardware acceleration component may not be able to handle certain error conditions. These error conditions need to be forwarded to the existing virtualization engine software based to process and report them. The vendor needs to provide entry points into the existing code to allow this access

The data path and control path of the existing software based virtualization engine will also need to support the hardware based accelerated data path through VAAPI. This will require changes to the control path and data path components of the virtualization engine

One embodiment of the invention is implemented as a program product for use with a computer system such as for example the storage network environment as shown in and described below. The program s of the program product defines functions of the embodiments including the methods described below with reference to and can be contained on a variety of signal bearing media. Illustrative signal bearing media include but are not limited to i information permanently stored on non writable storage media e.g. read only memory devices within a computer such as CD ROM disks readable by a CD ROM drive ii alterable information stored on writable storage media e.g. floppy disks within a diskette drive or hard disk drive or iii information conveyed to a computer by a communications medium such as through a computer or telephone network including wireless communications. The latter embodiment specifically includes information downloaded from the Internet and other networks. Such signal bearing media when carrying computer readable instructions that direct the functions of the present invention represent embodiments of the present invention.

Further the program product can be embedded within a processor such as a storage network processor. The processor may be embodied in an adapter card of a server or other type of computer work station.

In general the routines executed to implement the embodiments of the invention whether implemented as part of an operating system or a specific application component program module object or sequence of instructions may be referred to herein as a program . The computer program typically is comprised of a multitude of instructions that will be translated by the native computer into a machine readable format and hence executable instructions. Also programs are comprised of variables and data structures that either reside locally to the program or are found in memory or on storage devices. In addition various programs described hereinafter may be identified based upon the application for which they are implemented in a specific embodiment of the invention. However it should be appreciated that any particular program nomenclature that follows is used merely for convenience and thus the invention should not be limited to use solely in any specific application identified and or implied by such nomenclature.

While the foregoing is directed to embodiments of the present invention other and further embodiments of the invention may be devised without departing from the basic scope thereof and the scope thereof is determined by the claims that follow.

