---

title: Method and system for processing asynchronous event notifications
abstract: Method and system for managing asynchronous event notifications (AENs) including comparing an AEN sequence number at a shared memory location with an AEN sequence number at a local memory location controlled by a application; acquiring an AEN from the shared memory, if the sequence number of the AEN in the local memory is different from the sequence number of the AEN in shared memory; determining if a version number of the AEN is current; and generating an AEN if the version number is not current, wherein the generated AEN allows other applications to update AEN version numbers. The system includes firmware code executed in an adapter; an adapter driver executed on a host computing system stores the AENs in a memory buffer; and a plurality of applications that use a shared memory where AENs and a version number associated with the AENs are stored.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07457887&OS=07457887&RS=07457887
owner: QLOGIC, Corporation
number: 07457887
owner_city: Aliso Viejo
owner_country: US
publication_date: 20060810
---
The present invention relates to computing systems and more particularly to managing asynchronous event notifications AENs .

Conventional computing systems typically include several functional components. These components may include a central processing unit CPU memory input output I O devices and streaming storage devices for example tape drives . In most conventional computing systems a memory or main memory may be coupled to the CPU via a system bus or a local memory bus. Generally the memory is used to provide the CPU access to data and or program information that is stored in the memory at execution time. Typically the memory is composed of random access memory RAM circuits.

Conventional computing systems often referred to as host systems are used for various applications and in multiple environments including networks for example storage area networks SANs . Generally a SAN is a high speed sub network of shared storage devices for example disks and tape drives. Typically SANs are used to store and access data.

Host systems typically communicate with storage systems via a host bus adapter HBA also referred to as a controller and or adapter using an interface for example the PCI or PCI X PCI Express bus interface.

Asynchronous event notifications are sent by HBAs or other hardware devices to notify software applications of certain events. For example if a network cable is disconnected from a HBA the HBA may send an AEN to all applications notifying them of the event i.e. network cable disconnect .

The term software application as used herein includes software programs running on host systems or otherwise. Software applications may include management software used by a host system to monitor network events diagnostic software programs used to diagnose and fix hardware software problems and the like.

Typically information passed by AENs use a data structure format. The data structure format of the AEN is used by plural software applications to understand AEN content and when needed to respond to the AEN.

If a software application does not have the correct version of the data structure for an AEN then the AEN information may be difficult to decipher and the software application may fail to appropriately respond. If the format of the data structure changes at any time all software applications sharing the AENs should be upgraded so that they continue to function properly. Conventional computing systems do not provide an efficient way to upgrade software applications in conjunction with changes to AEN data structure formats.

In one aspect of the present invention a method for managing AENs is provided. The method includes comparing an AEN sequence number at a shared memory location with an AEN sequence number at a local memory location controlled by an application acquiring an AEN from the shared memory if the sequence number of the AEN in the local memory is different from the sequence number of the AEN in shared memory determining if a version number of the AEN is current and generating an AEN if the version number is not current wherein the generated AEN allows other applications to update AEN version numbers.

In yet another aspect a system for managing asynchronous event notifications AENs is provided. The system includes firmware code executed in a adapter wherein the firmware code generates AENs after detecting certain events an adapter driver executed on a host computing system stores the AENs in a memory buffer and a plurality of applications that use a shared memory where AENs and a version number associated with the AENs are stored and when an application compares an AEN sequence number at a shared memory location with an AEN sequence number at a local memory location controlled by the application acquires an AEN from the shared memory if the sequence number of the AEN in the local memory is different from the sequence number of the AEN in shared memory determines if a version number of the AEN is current and generates an AEN if the version number is not current wherein the generated AEN allows other applications to update AEN version numbers.

This brief summary has been provided so that the nature of the invention may be understood quickly. A more complete understanding of the invention can be obtained by reference to the following detailed description of the other embodiments thereof in connection with the attached drawings.

To facilitate an understanding of the various adaptive aspects of the present invention the general architecture and operation of a system using a HBA is described. The specific architecture and operation of the other embodiments are described with reference to the general architecture.

Host computing system interfaces with HBA using an adapter interface and bus A. Bus A may be a PCI PCI X PCI Express or any other standard non standard bus. The standard bus specifications are incorporated herein by reference in their entirety.

In one embodiment HBA is used to interface host computing system with storage sub systems and via network for example a SAN. SAN is used interchangeably for network throughout this specification .

HBA includes host interface that is used to interface with host computing system . In one aspect host interface may be a PCI PCI X PCI Express based interface. HBA interacts with network via a network interface A. The structure configuration of interface A will depend on the protocols networks standards for example Fibre Channel Ethernet InfiniBand and others .

HBA also includes a processor for executing software instructions out of memory via bus A . These software instructions are referred to as firmware . Processor may be a reduced instruction set computer RISC or any other processor.

Plural software applications such as Application Application . . . Application n may be running on host computing system or plural host computing systems. Each software application and has an application programming interface API and that interfaces with driver . Driver is used by host computing system to interface with HBA .

In one embodiment each software application and has local memory for example local memory and that is allocated by operating system . Local memory and may be used by each corresponding software application and to store data and commands. Local memory and may be part of memory .

Shared memory which may also be part of memory may be used as a shared resource by the plural software applications. Shared memory may be used by individual software applications to store AENs and their corresponding sequence version numbers.

In one embodiment the AENs are pre defined and are generated for specific events. The AENs may be issued in a sequence and each AEN has a sequence number. For example an AEN issued at time t may have a sequence number 0001 the next AEN may have a sequence number of 0002 and so forth. The sequence number is created by the software application that retrieves the AEN from driver .

The AENs also have a version number that is based on the data structure of the AENs as stored in shared memory . Software Applications and regularly poll driver and check shared memory to acquire the AENs.

The process for generating and managing the AENs according to embodiments of the present invention is now described with respect to the process flow diagrams of .

In step S a software application is initialized for example software application is initialized. In step S software application queries operating system to determine if shared memory exists. If shared memory exists then software application attaches i.e. interfaces to shared memory which allows access to software application and the process continues.

In step S if upon query shared memory is determined not to exist then in step S software application creates shared memory based on operating system approval . Software application also stores a version number in shared memory that denotes the data structure for AENs A. Thereafter in step S other software applications for example software applications and begin to operate.

In step S HBA through firmware sends the AEN event to driver . In step S driver stores the AEN event in buffer .

If the sequence number is the same then in step S software application polls driver for the AENs. Software application then acquires the AENs stored in buffer .

In step S software application increments the AEN sequence number and maintains the sequence number to ensure that it has the latest AEN. Thereafter in step S the AEN is stored in shared memory .

If in step S the sequence number in shared memory is different from the sequence number in local memory then in step S software application acquires the AEN from shared memory .

In step S software application compares the version number for the AEN with a current version number. If the version numbers do not match in step S software application creates an out of sync AEN message and stores it in shared memory . Thereafter software application increments the sequence number. In one embodiment a flag is set in shared memory and an Out of Sync AEN message is sent to all software applications so that the software applications can inform a user that a software application should be upgraded. Once the software applications upgrade is complete all the software applications have consistent data structures and thus the AENs can be processed correctly.

In step S if the version number in step S is current then software application performs the task in response to the AEN.

It should be understood that reference in the embodiments described herein to software application is done simply to illustrate the process steps of the present invention but that the present invention is not limited to any particular type of software application. Furthermore the adaptive aspects of the present invention are not limited to a HBA and any device that is generating AENs shared between plural software applications can benefit from the foregoing approach.

In one embodiment of the present invention by generating an out of sync AEN message different applications can inform the user that a software application should be upgraded and hence maintain AEN data structure consistency within the shared memory resource where AENs are stored.

Although the present invention has been described with reference to specific embodiments these embodiments are illustrative only and not limiting. Many other applications and embodiments of the present invention will be apparent in light of this disclosure and the following claims.

