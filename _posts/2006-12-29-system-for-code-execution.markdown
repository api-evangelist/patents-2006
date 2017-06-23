---

title: System for code execution
abstract: System for executing software application is provided. The system includes a non-volatile memory device that includes a plurality of memory cells, wherein a read only segment of a plurality of memory cells stores: (a) code for a micro-operating system for running a virtual engine; (b) code for the virtual engine that provides a virtual environment, independent of a host operating system; (c) code for a virtual operating system that is executed in the virtual environment; and (d) code for a software application, wherein the code for the software application can be executed in different host system platforms in the virtual environment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07890724&OS=07890724&RS=07890724
owner: SanDisk Corporation
number: 07890724
owner_city: Milpitas
owner_country: US
publication_date: 20061229
---
Computing systems stand alone and networked are commonplace. The Internet has increased the popularity of electronic commerce where users of computing systems conduct millions of electronic transactions. This increase in popularity has also made computing systems and user information vulnerable to pirates sometimes known as hackers .

Operating systems are computer programs used to perform certain computing tasks such as for example managing input output tasks peripheral devices for example storage devices and file systems. Operating systems provide a software platform on top of which other software applications are written. Software applications are used for various tasks including for example word processing electronic mail email and Internet browsing. Some common operating systems include Windows Linux IBM OS 2 MacOS UNIX and MS DOS.

Many operating systems are pirated or hacked i.e. they experience unauthorized use or interruption through use of disruptive software programs such as those known as computer viruses worms key loggers and root kits. Securing operating systems and overall application code execution is a challenge.

Furthermore software applications will often run on multiple operating systems or hardware platforms. Typically separate code for a software application must be created for each different environment platform. This is expensive and undesirable. An efficient method and system are desirable for managing code for software applications to be used on different hardware and software platforms.

In one embodiment of the present invention a non volatile memory device is provided. The non volatile memory device includes a plurality of memory cells wherein a read only segment of a plurality of memory cells stores a code for a micro operating system for running a virtual engine b code for the virtual engine that provides a virtual environment independent of a host operating system c code for a virtual operating system that is executed in the virtual environment and d code for a software application wherein the code for the software application can be executed on different host system platforms in the virtual environment.

In yet another embodiment of the present invention a system for code execution is provided. The system includes a host computing system and a non volatile memory device operationally coupled to the host computing system. The non volatile memory device includes a plurality of memory cells wherein a read only segment of the plurality of memory cells stores a code for a micro operating system for running a virtual engine b code for the virtual engine that provides a virtual environment independent of a host operating system c code for a virtual operating system that is executed in the virtual environment and d code for a software application wherein the code for the software application can be executed on different host system platforms in the virtual environment.

This brief summary is not intended to limit the invention to any particular embodiment. Rather the invention is intended to cover the subject matter defined by the claims appended hereto and all equivalents.

To facilitate an understanding of the preferred embodiment the general architecture and operation of a computing system non volatile memory storage device will first be described. The specific architecture and operation of the preferred embodiment will then be described with reference to the general architecture.

Read only memory ROM is provided to store invariant instruction sequences such as start up instruction sequences or Basic Input Output Operating System BIOS sequences.

Input Output I O devices A such as for example a keyboard a pointing device mouse a monitor a modem and the like are also provided for receiving input output instructions.

Host system optionally connects to a computer network not shown via network interface A. One such network is the Internet that allows host system to download applications code documents and others electronic information.

Host system is coupled to a non volatile memory device for example a flash memory device or card that includes a controller module may also be referred to as memory controller or controller and solid state memory modules may also be referred to as cells cell arrays shown as Memory Module and Memory Module n . Controller module interfaces with host system via a bus interface directly via system bus B or any other peripheral bus not shown .

Non volatile memory device may also include a processor shown as crypto engine A that performs various cryptographic functions for example encrypting and or decrypting stored content. Crypto engine A may also be used to authenticate a non volatile memory device as described below.

In some embodiments non volatile memory devices are flash memory devices. There are currently many different flash memory cards that are commercially available examples being the CompactFlash CF the MultiMediaCard MMC Secure Digital SD miniSD Memory Stick SmartMedia and TransFlash cards. Although each of these cards has a unique mechanical and or electrical interface according to its standardized specifications for example the Universal Serial Bus USB specification based interface incorporated herein by reference in its entirety the flash memory included in each card is very similar. These cards are all available from SanDisk Corporation assignee of the present application.

SanDisk Corporation also provides a line of flash drives under its Cruzer trademark which are hand held memory systems in small packages that have a Universal Serial Bus USB plug for connecting with a host by plugging into the host s USB receptacle. Each of these memory cards and flash drives includes controllers that interface with the host and control operation of the flash memory on the card or drive.

Host systems that use such memory cards and flash drives are many and varied. They include personal computers PCs laptop and other portable computers cellular telephones personal digital assistants PDAs digital still cameras digital movie cameras and portable audio players. Host systems typically include a built in receptacle for one or more types of memory cards or flash drives but some require adapters into which a memory card is plugged.

A NAND architecture of the memory cell arrays is currently preferred although other architectures such as NOR can also be used instead. Examples of NAND flash memories and their operation as part of a memory system may be had by reference to U.S. Pat. Nos. 5 570 315 5 774 397 6 046 935 6 373 746 6 456 528 6 522 580 6 771 536 and 6 781 877 and United States Patent Application Publication number 2003 0147278.

The various embodiments described herein are not limited to the foregoing structures. Various other structures and memory types may be used for example non flash memory devices can be used with this invention such as one time programmable memory devices or 3D memory devices which may include a monolithic three dimensional memory array. In a three dimensional memory array multiple memory levels are formed above a single substrate such as a wafer with no intervening substrates. The layers forming one memory level are deposited or grown directly over the layers of an existing level or levels. In contrast stacked memories have been constructed by forming memory levels on separate substrates and adhering the memory levels atop each other as in Leedy U.S. Pat. No. 5 915 167 Three dimensional structure memory. The substrates may be thinned or removed from the memory levels before bonding but as the memory levels are initially formed over separate substrates such memories are not true monolithic three dimensional memory arrays.

A host interface interfaces with host system while a flash interface interfaces with memory modules .

Accordingly in one embodiment non volatile memory device conforms to the USB specification i.e. can be accessed via a USB interface . Standard USB based application programming interface API may be used for reading or writing data.

Non volatile memory device appears to host having a plurality of Logical Units LUNs of storage space and each LUN may appear to be of a different class of storage device. For example non volatile memory device may appear to have both a standard Mass Storage Class volume LUN A which imitates the behavior of a SCSI Hard Disk Drive and a MMC Class volume which imitates the behavior of a CD ROM LUN B .

LUN B may store a plurality of software applications a minimal version of an operating system Micro OS code for a virtual engine and other information discussed below with respect to .

Hidden area C is secured and is not available without proper authentication. Proprietary APIs may be used to access hidden area C. In one aspect a protected or secured area means an area that is read only and accessible only by an appropriate authenticated entity for example a host program and the like. Hidden area C may store device certificates and security keys and other code as described below with respect to .

It is noteworthy that although host system has been described above as having a CPU ROM RAM and other components the adaptive aspects of the present invention may be implemented on a thin client i.e. a host system that has limited computing abilities. For example a USB reader executor with a keyboard mouse video card network card and CPU can execute whatever code application is stored on non volatile memory device instead of a desktop or notebook computer.

Micro OS is a minimal version of an operating system i.e. it has reduced functionality compared to a standard operating system. Micro OS is used to control the overall environment in which code for a virtual engine is executed. Micro OS may be customized to run code for the virtual engine described below. Micro OS may be stored in the read only segment B .

Application may be a software application that a user may want to execute on different hardware software platforms. More than one application may be stored in non volatile memory device .

Application may include a web browser for example Firefox that a user uses to browse websites. The web browser may run on any computer connected to the Internet. The web browser receives and sends requests to a web server and acquires information from a World Wide Web WWW a network of computers. A web server is a program that upon receipt of a request sends requested data to a requesting user.

Virtual engine or machine VE includes code for providing a virtual environment. The virtual environment provides a software platform that is independent of a host operating system. Code that is executed in the virtual environment is not controlled by the host operating system but instead is controlled by a virtual operating system executed within the virtual environment.

VE also includes executable code for different operating systems executed in the virtual environment independent of the underlying host operating system. Micro OS controls the overall execution of VE .

Code blocks for different operating systems are shown as VOS VOS VOS and VOSn. VOS may be used to execute a Windows based operating system VOS may be used for a Linux operating system VOS may be used for a UNIX based operating systems and so forth. The operating system specific code VOS VOSn is executed in a virtual environment independent of the host system operating system. VE allows a user to use non volatile memory device on different hardware software platforms.

Different types of virtual engines may be used to implement the adaptive aspects of the present invention. For example VMWare Player and VMWare Ace available from VMware Corporation VirtualPC available from Microsoft Corporation and others may be used. It is noteworthy that more than one virtual engine may be stored and used for application execution. This will make it more difficult for pirates to break into the operating system because the viruses or other disruptive software will have to hook to low level support for two or more virtual engines instead of one virtual engine.

The non volatile memory device during an authentication stage as described below uses device certificates .

Security keys may be used to generate a one time password to authenticate a user device. Security keys may be used by crypto engine A to encrypt stored content using standard or proprietary encryption techniques.

Virtual private network VPN code is provided to facilitate a VPN connection as described below. Access to VPN code is limited by storing in LUN B so that a virtual connection is difficult to pirate or break into.

It is noteworthy that executable code for a plurality of software components Micro OS application firmware device certificates security keys virtual engine and VPN code may be stored in secured segment C or in read only segment B. Furthermore executable code for the plurality of components may be bifurcated and partially stored in the read only segment B and secured segment C.

After the host operating system is detected in step S non volatile memory device and a user using the device are authenticated. In one aspect server authenticates non volatile memory device using device certificates . A standard or proprietary technique may be used to authenticate non volatile memory device . For example a public key infrastructure PKI certificate for example may be used to authenticate non volatile memory device . A user using non volatile memory device may also have to authenticate itself before being allowed access to non volatile memory device . This may be performed by using a unique user specific password generated by using security keys . Crypto engine A may be used to authenticate non volatile memory device and the user. Step S attempts to prevent unauthorized use of non volatile memory device .

In step S non volatile memory device loads code VOS VOS VOS or VOSn for a virtual machine into RAM . In one aspect of the present invention controller may execute virtual engine code to initialize a virtual environment. In another aspect virtual engine code execution may be split such that one code segment is executed by the host CPU and another segment is executed by non volatile memory device . This makes pirating or hacking difficult.

After virtual engine code is initialized all other applications code for example application is executed in a virtual environment independent of the host operating system.

In step S host system opens a virtual private network VPN connection not shown to an enterprise server or gateway not shown . The nature of the network connection will depend on the connection e.g. whether the connection is to a web server or local area network. VPN code may be used to open the VPN connection.

In step S application is executed in the appropriate virtual operating system environment. Application is executed in a virtual environment controlled by virtual engine independent of the host operating system. Hence it is difficult to break into hack into application execution.

In one aspect of the present invention code for application is written so that it may be executed in a virtual environment which may be independent of a host system operating system. Hence different versions for application for different operating systems and platforms are not needed. This reduces overall cost of code development maintenance.

In another aspect of the present invention because virtual engine and application are stored in a read only segment for example B or C of non volatile memory device they are difficult to pirate.

In yet another aspect of the present invention a secure environment is provided to a user to conduct electronic commerce transactions for example bank transactions without changing overall user experience. Once non volatile memory device is connected and the virtual environment is launched the user simply navigates to a website with minimal pirating risk.

While the present invention is described above with respect to what is currently considered its preferred embodiments it is to be understood that the invention is not limited to that described above. To the contrary the invention is intended to cover various modifications and equivalent arrangements within the spirit and scope of the appended claims.

