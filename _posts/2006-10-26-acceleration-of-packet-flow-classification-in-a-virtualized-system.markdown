---

title: Acceleration of packet flow classification in a virtualized system
abstract: A computer system having a plurality of virtual machines is provided. Each virtual machine in the computer system has an associated policy (rules) database and database (policy table) for storing rules and a database lookup associated with the policy database. One policy database/database lookup pair per virtual machine allows each virtual machine to have a different set of packet processing rules and security policies for handling the same key. In addition, the policy database associated with one virtual machine may be updated and the database lookup associated with the policy database re-generated independently without requiring any update of the policy database lookups associated with any of the other policy databases in the computer system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08010990&OS=08010990&RS=08010990
owner: Intel Corporation
number: 08010990
owner_city: Santa Clara
owner_country: US
publication_date: 20061026
---
This disclosure relates to packet flow classification and in particular to acceleration of packet flow classification in a virtualized system having a plurality of virtual machines.

A computer system is a layered device that includes a hardware layer a firmware and operating system layer and an applications program layer. The hardware layer of the computer system is often referred to as a physical hardware platform. The platform may include processors chipsets communications memory boards and systems. Typically a single operating system controls all hardware layer resources in the computer system.

The computer system s physical resources may be virtualized to allow multiple operating systems to run on a single physical platform. A virtualized system may include a virtual machine monitor that arbitrates access to the physical platform s resources so that multiple operating systems can share them. The virtual machine monitor presents to each operating system a set of platform interfaces that constitute a virtual machine. Thus one computer system hardware platform can function as multiple virtual machines platforms .

The physical platform may include a network processor that is a programmable device that is optimized for processing packets at high speed. Typically the network processor classifies a received packet using a tuple of a set of fields from headers included in the packet. For example the tuple of a set of fields may include a Transport Control Protocol TCP source port field TCP destination port field Internet Protocol IP source address field and IP destination address field. Using this tuple of a set of fields as a key a database storing policy entries policy table or policy database may be queried to identify a configured policy that dictates how to handle the packet.

The policy entries in the policy database are typically stored as linked lists or as linear arrays. In order to improve searching performance a lookup mechanism is typically implemented. One implementation of a lookup mechanism is a Recursive Flow Classification RFC algorithm which is discussed at http klamath.stanford.edu pankaj thesis chapter4.pdf.

One limitation of the RFC algorithm is that lookup efficiency decreases exponentially as the number of policy entries in the database increases. Another limitation is that each time the database is updated an RFC table associated with the database needs to be re generated. The regeneration process can be quite slow with the time taken to generate an RFC table from a database being directly proportional to the number of policy entries in the database.

Although the following Detailed Description will proceed with reference being made to illustrative embodiments of the claimed subject matter many alternatives modifications and variations thereof will be apparent to those skilled in the art. Accordingly it is intended that the claimed subject matter be viewed broadly and be defined only as set forth in the accompanying claims.

Typically flow classification acceleration supports a single operating system. However in a virtualized system each virtual machine may have a different operating system with each operating system having a different flow classification policy. For example each operating system may have different security policies and packet processing rules. Combining all of the packet processing rules from each virtual machine into a single database policy table shared among all of the virtual machines may result in a decrease in the database lookup efficiency. Furthermore a single database may require resolving conflicting packet processing rules for different virtual machines associated with the same key for example a tuple of a set of fields from headers included in the packet .

In an embodiment of the invention each virtual machine in a computer system has an associated policy rules database policy table for storing rules and a database lookup associated with the policy database. One policy database database lookup pair per virtual machine allows each virtual machine to have a different set of packet processing rules and security policies for handling the same key.

Furthermore the policy database associated with one virtual machine may be updated and the database lookup associated with the policy database re generated independently without requiring any update of the policy database lookups associated with any of the other policy databases in the system.

An embodiment of the invention will be described for a system that handles Internet Protocol security architecture IPsec packets. IPsec enables selection of security protocols and determines algorithms and cryptographic keys to be used. The security services include access control connectionless integrity data origin authentication and rejection of replayed packets. IPsec provides security services at the Internet Protocol IP layer. IPsec uses two protocols to provide traffic security Authentication Header AH and Encapsulating Security Payload ESP . These protocols may be applied alone or in combination with each other to provide a desired set of security services in Internet Protocols such as Internet Protocol version 4 IPv4 and Internet Protocol version 6 IPv6 .

The IPsec affords protection to Internet Protocol IP traffic based on requirements defined by a Security Policy Database SPD that may be established and maintained by a user or system administrator. For example a policy or rule may be created in the SPD through an advertised Application Programming Interface API . The rules and policy entries in the SPD dictate how received data packets traffic are handled that is the SPD includes actions for handling received packets. Based on Internet Protocol IP and Transport Control Protocol TCP header information a received packet may be matched against entries in the SPD and based on the policy or rule in the matching entry the packet is either discarded allowed to bypass IPsec or IPsec security services are performed.

The Host Central Processing Unit CPU may be any one of a plurality of processors such as a single core Intel Pentium IV processor a single core Intel Celeron processor an XScale processor or a multi core processor such as Intel Pentium D Intel Xeon processor or Intel Core Duo processor or any other type of processor.

The memory may be Dynamic Random Access Memory DRAM Static Random Access Memory SRAM Synchronized Dynamic Random Access Memory SDRAM Double Data Rate 2 DDR2 RAM or Rambus Dynamic Random Access Memory RDRAM or any other type of memory.

The ICH may be coupled to the MCH using a high speed chip to chip interconnect such as Direct Media Interface DMI . DMI supports 2 Gigabit second concurrent transfer rates via two unidirectional lanes.

The ICH may include a Peripheral Component Interconnect PCI or Peripheral Component Interconnect Express PCI e bus controller for controlling communication with devices coupled to the ICH that communicate with the ICH over a PCI or PCI e bus .

A network processor that includes an embodiment of a packet classifier according to the principles of the present invention may be coupled to the ICH through the PCI or PCI e bus . The network processor may include at least one micro engine that processes packets which may be received over a wide area network WAN through a phy coupled to the network processor or may be received from a local area network LAN through a switch or hub coupled to another phy .

The system may support virtualization that is provide the ability to create separate partitions called virtual machines . Each virtual machine includes an operating system guest operating system and one or more applications and interfaces to a virtual machine manager VMM . Each operating system operates independently from the operating systems in the other virtual machines . The VMM allocates platform resources such as memory to each virtual machine .

The VMM runs directly on the system s hardware and emulates a complete hardware environment for each virtual machine . The applications and guest operating system in each virtual machine are not aware that they are sharing the system hardware.

Thus with each virtual machine having its own operating system different applications and operating system combinations may be executed on the same system for example both 32 bit and 64 bit guest operating systems may be provided in the system allowing both 32 bit and 64 bit applications to run on the same system. Also update and recovery tools may be restricted to one virtual machine and virus prone activities may be isolated by restricting them to one virtual machine so that they will not infect the entire system.

For example a portion of a managed computer system may be isolated to perform system upgrades and maintenance without interrupting the end user or the same computer system may function independently as both a business and a personal system keeping software and virus attacks separate or virtual partitions may be created in a computer system to isolate multiple user environments.

Each virtual machine has a respective policy table stored in memory . One of the micro engines may include a packet classifier to direct a received packet to the policy database policy table associated with one of a plurality of virtual machines to identify the processing policy rule to handle the received packet.

Network processing has traditionally been partitioned into control plane and data plane processing. Data plane tasks are typically performance critical and non complex for example classification forwarding filtering header checking modification protocol conversion and policing. Control plane tasks are typically performed less frequently and are not as performance sensitive as data plane tasks for example connection setup and teardown routing protocols fragmentation and reassembly.

The CPU may be a 32 bit general purpose processor which may be used for offloading control plane tasks and handling exception packets from the micro engines . In an embodiment each micro engine is a 32 bit processor with an instruction set and architecture specially optimized for fast path data plane processing. Control and status registers that may be accessed by all of the micro engines may be stored in the memory which is shared by all of the micro engines .

The communications protocol interface buffers network packets as they enter and leave the network processor . In one embodiment the communications protocol interface may provide support for handling Gigabit Ethernet packets as they enter and leave the network processor .

In the embodiment shown all of the virtual machines share the micro engines in the network processor . Each virtual machine has an associated policy database and policy database lookup . The policy database lookup is stored in memory that is accessible by all of the micro engines . The policy database is stored in memory as discussed in conjunction with . Each virtual machine also includes an associated Virtual Machine VM cache table which is a cache of the most recently used rules retrieved by the virtual machine from the associated policy table .

Each policy database policy database lookup pair and VM cache table is associated with a unique identifier that uniquely associates the policy database to the virtual machine . In an embodiment in which each virtual machine has a respective dedicated network interface the unique identifier may be the network interface in the network processor through which a packet is received. The network interface dedicated assigned to a virtual machine may be one port in the communications protocol interface or in an embodiment having a plurality of communication protocol interfaces each virtual machine may be assigned a communications protocol interface .

In the embodiment shown the network interface through which a packet is received incoming network interface is used to identify the policy database to be used for processing the received packet. After the respective policy database has been identified policy database processing proceeds using the associated policy database lookup to identify a policy rule. After the policy rule is identified the identified policy rule is used to process the received packet.

The policy rule for the received packet stored in the policy database may be to drop the received packet forward the packet without processing to the next hop that may be identified from headers in the packet forward the received packet with the associated policy rule information to the virtual machine associated with the received packet for further processing or other accelerated packet services may be performed on the received packet.

In one embodiment the packet classifier in the micro engine may include a function as shown in Table 1 below to select the policy database policy data lookup pair based on the network interface through which the packet was received.

The selection of the particular virtual machine may be made dependent on the interface through which the packet was received. For example the communications protocol interface may include a plurality of input ports that may be coupled to communication links with a virtual machine associated with each input port.

Each packet received by an input port is forwarded through the communication protocol interface to one of a plurality of micro engines . In the embodiment shown one of the micro engines includes a packet classifier that classifies a packet based on contents of headers included in the packet to determine how to process the packet. Upon receiving a packet the packet classifier in the micro engine extracts a tuple of a set of fields from the contents of the packet. For example the tuple of a set of fields may include a Transport Control Protocol TCP source port field TCP destination port field Internet Protocol IP source address field and IP destination address field.

In one embodiment a five tuple set of fields is selected that includes IP source address field IP destination address field IP protocol number and the next layer source and destination ports. The next layer may be TCP or User Datagram Protocol UDP or any other next layer.

The five tuple set of fields key is extracted from the packet headers by the packet classifier and may be forwarded to a database lookup associated with the virtual machine to provide an index which may be used to search a packet processing policy database .

There are many classification algorithms which may be used by a database lookup that are designed to work in two dimensions that is with two header fields. Other classifier algorithms that work with more than two header fields and are commonly referred to as classifiers that perform classification in multiple dimensions.

The Recursive Flow Classification RFC algorithm is a multi dimensional classification algorithm which maps S bits in a packet header to T bits of an identifier index to a database table The RFC algorithm is discussed at http klamath.stanford.edu pankaj thesis chapter4.pdf. In each of P phases the RFC algorithm performs a reduction by mapping one set of values to a smaller set. The mapping is performed recursively through a plurality of phases. The final phase provides a value which corresponds to the class identifier of the packet. In one embodiment the database lookup uses the RFC algorithm to provide an index to a policy database storing the rule associated with a key.

An embodiment of the invention will be described for the RFC algorithm. However the invention is not limited to the RFC algorithm. Other embodiments of the invention may use any other fast path processing algorithm for example a binary search algorithm a backtracking search algorithm a hierarchical trie query algorithm a cross producting algorithm a tuple space search algorithm a two dimensional search algorithm or any other algorithm for providing an index from a value.

The five tuple set of fields is forwarded to the database lookup that uses the RFC algorithm and is associated with the virtual machine to find an index to a packet processing policy database associated with the virtual machine . Using this tuple of a set of fields as a key the RFC algorithm in the database lookup provides an index to the policy database which stores policy entries. The policy database may be queried using the index to determine a configured policy that dictates how to handle the packet.

In one embodiment the packet processing policy database is a security policy database SPD used to enforce a security policy in an IPsec environment. IPsec may operate in a host system or a security gateway. The SPD is established and maintained by a user or system administrator. Packets are selected for one of three processing modes based on IP and transport layer header information matched against entries in the SPD. Each packet is either discarded bypasses IPsec or is afforded IPsec security services. In the case of a received IPsec packet the rule stored in the packet policy database may be to forward the packet to the associated virtual machine for further processing drop the packet or to perform other services.

The SPD specifies what services are to be offered to IP packets datagrams and how the services are to be applied. Traffic that is not allowed to be delivered is discarded traffic that is allowed to pass without IPsec protection is allowed to pass through and the SPD may specify security services and protocols to be employed for traffic that is afforded IPsec protection.

At block a packet is received through the communication protocol interface . Processing continues with block .

At block a virtual machine VM is selected based on the incoming packet interface that is based on the network interface through which the packet was received. Processing continues with block

At block a policy cache VM cache associated with the selected VM is searched using the result of a hash function performed on a tuple of fields from the header of the packet. Processing continues with block .

At block if there is a matching entry in the VM cache processing continues with block . If not processing continues with block .

At block a database lookup associated with the virtual machine receives a tuple of fields from the header of the packet. As discussed earlier the database lookup may use an RFC algorithm to perform a multi dimensional search for an index to a policy database based on a key extracted from the received packet. If this is the first packet in a flow that is between a particular IP and or level 4 source address and destination address a rule action for the packet is discovered using the database lookup to generate an index to the policy database . The database lookup identifies an index for a rule stored in the policy database . The discovered rule may be already stored in the respective VM cache table in memory . If this packet is not the first packet in the flow there is already an entry and action in the respective VM cache table which was previously created as will be discussed later in conjunction with block . Processing continues with block .

At block if a match is found for the key in the database lookup processing continues with block . If not processing continues with block .

At block the match index may be used to obtain the rule associated with the packet from the policy database table entry in the respective policy table indicated by the index provided by the associated database lookup . Processing continues with block .

At block a VM cache table associated with the selected virtual machine is updated with the packet and rule information. Processing continues with block .

At block the received packet is processed based on the rule policy retrieved from the policy table . As previously discussed the rule may indicate that the packet is to be discarded forwarded to the virtual machine for further processing or forwarded to a next hop without any processing by the virtual machine .

At block the database lookup was unable to find a match based on the key extracted from the received packet the packet is forwarded to the virtual machine associated with the database lookup for further processing.

In one embodiment a security gateway includes a platform having a plurality of virtual machines . The security gateway analyzes and processes packets entering the platform.

In another embodiment Universal Thread Management UTM services are deployed in the platform in separate virtual machines domains for added isolation. A UTM system typically has a large data throughput requirement. Thus typically hardware acceleration is used to meet the required data throughput.

It will be apparent to those of ordinary skill in the art that methods involved in embodiments of the present invention may be embodied in a computer program product that includes a computer usable medium. For example such a computer usable medium may consist of a read only memory device such as a Compact Disk Read Only Memory CD ROM disk or conventional ROM devices or a computer diskette having a computer readable program code stored thereon.

While embodiments of the invention have been particularly shown and described with references to embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of embodiments of the invention encompassed by the appended claims.

