---

title: Utilizing early exclusive volume access and direct volume manipulation to remove protected files
abstract: Upon detection of a rootkit, a host computer system is rebooted. The boot process is interrupted. Access to a media, e.g., a volume or disk, containing the rootkit is gained and the media is directly accessed. The rootkit is disabled, e.g., renamed or deleted, and the host computer system is rebooted a second time. If the rootkit has not been previously removed, e.g., only renamed, the rootkit is removed, e.g., using a conventional antivirus application. Thus, upon detection of a rootkit, the rootkit is removed without a clean boot.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07926106&OS=07926106&RS=07926106
owner: Symantec Corporation
number: 07926106
owner_city: Mountain View
owner_country: US
publication_date: 20060406
---
The present invention relates to computer system security. More particularly the present invention relates to a system and method of removing malicious code from a computer system.

Increasingly various forms of malicious code such as spyware and computer viruses protect their presence on computer systems using a variety of stealth and persistence techniques. These techniques actively prevent detection and removal of the malicious code from a running system.

To remove the malicious code a clean boot is typically required. Unfortunately there are many complications associated with a clean boot. The host computer system s BIOS must be configured properly and the clean boot media e.g. a floppy disk CD or DVD must be available and used.

In accordance with one embodiment of the present invention upon detection of a rootkit the host computer system is rebooted. The boot process is interrupted. Access to a media e.g. a volume or disk containing the rootkit is gained and the media is directly accessed. The rootkit is disabled e.g. renamed or deleted and the host computer system is rebooted a second time. If the rootkit has not been previously removed e.g. only renamed the rootkit is removed e.g. using a conventional antivirus application.

Thus upon detection of a rootkit the rootkit is removed without a clean boot i.e. without use of a separate clean boot media such as a floppy disk CD DVD or other media. Further the rootkit is removed without reconfiguration of the BIOS of the host computer system.

Embodiments are best understood by reference to the following detailed description when read in conjunction with the accompanying drawings.

Common reference numerals are used throughout the drawings and detailed description to indicate like elements.

In accordance with one embodiment referring to upon detection of a rootkit in a ROOTKIT DETECTED CHECK OPERATION the host computer system is rebooted in a REBOOT HOST COMPUTER SYSTEM OPERATION . The boot process is interrupted in an INTERRUPT BOOT PROCESS OPERATION . Access to the media e.g. volume or disk containing the rootkit is gained in a GAIN ACCESS TO THE MEDIA OPERATION and the media is directly accessed in a DIRECTLY ACCESS THE MEDIA OPERATION . In a DISABLE ROOTKIT OPERATION the rootkit is disabled e.g. renamed or deleted and the host computer system is rebooted a second time in a REBOOT HOST COMPUTER SYSTEM OPERATION . If the rootkit has not been previously removed e.g. only renamed the rootkit is removed in a CLEAN HOST COMPUTER SYSTEM OPERATION e.g. using a conventional antivirus application.

Thus upon detection of a rootkit the rootkit is removed without a clean boot i.e. without use of a separate clean boot media such as a floppy disk CD DVD or other media. Further the rootkit is removed without reconfiguration of the BIOS of the host computer system.

More particularly is a diagram of a client server system that includes a malicious code removal application executing on a host computer system in accordance with one embodiment of the present invention.

Host computer system sometimes called a client or user device typically includes a central processing unit CPU sometimes called a processor an input output I O interface and a memory . Host computer system further includes standard devices like a keyboard a mouse a printer and a display device as well as one or more standard input output I O devices such as a compact disk CD or DVD drive floppy disk drive or other digital or waveform ports for inputting data to and outputting data from host computer system .

In one embodiment malicious code removal application is loaded into host computer system via I O device such as from a CD DVD or floppy disk containing malicious code removal application .

Host computer system is coupled to a server system of computer system by a network . Server system typically includes a display device a processor a memory and a network interface . Additional computer systems such as a hacker e.g. a second computer system are also associated with network .

Network can be any network or network system that is of interest to a user. In various embodiments network interface and I O interface include analog modems digital modems or a network interface card.

Malicious code removal application is stored for example in memory of host computer system and executed on host computer system .

The particular type of and configuration of host computer system server system and hacker computer system are not essential to this embodiment of the present invention.

Herein in one embodiment malicious code is defined as any computer program module set of modules or code that enters a computer system environment without an authorized user s knowledge and or without an authorized user s consent. A computer virus is one example of a malicious code. For example the malicious code is propagated from hacker computer system to host computer system .

Some malicious codes sometimes called rootkits prevent other applications such as user mode antivirus AV applications from accessing selected objects such as files by overriding selected user mode and or kernel mode API functions that allow iteration of files or subdirectories in a directory effectively locking the affected files or subdirectories. Thus an AV application attempting to iterate the files or subdirectories is prevented from enumerating the files or subdirectories thereby preventing malicious code detection and deletion by the AV application.

Application is a user mode application for example is an AV application. To access files and other data application originates a system call to file system driver for example using an application programming interface API . File system driver e.g. a kernel mode component is a driver for file system . File system driver receives the system call from application and translates the system call into a specific command for file system .

File system is the system that the operating system uses to organize and keep track of files. In one embodiment a file is a collection of data that has a file name.

File system in turn uses volume manager to access volumes in which the files are located. Volume manager manages the volumes of the host computer system. In one embodiment a volume is a fixed amount of storage medium e.g. a particular number of bytes of a hard drive sometimes called disk of the host computer system. For example a single hard drive is partitioned into volumes although a volume can span more than one hard drive.

Volume manager in turn uses disk manager to access the disk in which the volume containing the files are located. Disk manager manages the hard disk e.g. facilitates read write to specific bits of the hard disk.

Rootkit includes a malicious file system module e.g. a driver loaded in memory and a malicious code module e.g. a file on disk. Illustratively rootkit is in the same volume of the host computer system as the operating system.

In one example upon booting of the computer system malicious code module is executed e.g. due to an entry in the registry to create malicious file system module within file system . For example the file name of malicious code module is included in the list of files to be executed during booting of the computer system. Malicious file system module has hijacked sometimes called infected or hooked file system to protect sometimes called stealth rootkit .

For example malicious file system module prevents other applications such as user mode antivirus AV applications e.g. application from accessing rootkit by overriding selected user mode and or kernel mode API functions that allow iteration of files or subdirectories in a directory effectively locking the affected files or subdirectories. Although one example of a rootkit is set forth for purposes of illustration rootkits are well known to those of skill in the art and any one of the number of rootkits e.g. user mode or kernel mode rootkits can be disabled in accordance with embodiments of the present invention.

From an ENTER OPERATION flow moves to a ROOTKIT DETECTED CHECK OPERATION . In ROOTKIT DETECTED CHECK OPERATION a determination is made as to whether a rootkit i.e. malicious code is detected. A rootkit can be detected using any one of a number of techniques well known to those of skill in the art and the particular technique used to detect a rootkit is not essential to this embodiment of the present invention.

If a rootkit is not detected flow remains at ROOTKIT DETECTED CHECK OPERATION . Conversely if a rootkit is detected flow moves from ROOTKIT DETECTED CHECK OPERATION to a REBOOT HOST COMPUTER SYSTEM OPERATION . For example rootkit is detected and flow moves from ROOTKIT DETECTED CHECK OPERATION to REBOOT HOST COMPUTER SYSTEM OPERATION .

In REBOOT HOST COMPUTER SYSTEM OPERATION the host computer system e.g. host computer system is rebooted i.e. restarted. Illustratively a reboot API is called to reboot the host computer system. During rebooting the host computer system is shut down and then a boot process is initiated.

From REBOOT HOST COMPUTER SYSTEM OPERATION flow moves to an INTERRUPT BOOT PROCESS OPERATION . In INTERRUPT BOOT PROCESS OPERATION the boot process of the host computer system initiated during REBOOT HOST COMPUTER SYSTEM OPERATION is interrupted. As is well known to those of skill in the art the boot process is the starting up of a host computer system which involves loading the operating system and other basic software. In one embodiment the boot process is interrupted to prevent execution of malicious code module which otherwise would be executed during booting of the host computer system. By preventing execution of malicious code module creation of malicious file system module is prevented.

In one embodiment a native application e.g. a module of malicious code removal application is used to interrupt the boot process. A native application is an application designed to run in the computer environment machine language and OS being referenced i.e. is written to a specific set of software platform APIs and a specific microprocessor. As such a native application can be created early in the boot process and interrupts the boot process once created. A native application uses the operating system but is launched early in the boot process for example before most drivers are loaded.

For example a native application e.g. a windows native application is created early in the boot process and prior to execution of malicious code module . Native application prevents execution of malicious code module and thus prevents creation of malicious file system module in accordance with this example. In another example malicious code module is executed and malicious file system module is created. Native applications are well known to those of skill in the art and for example are described in Inside Native Applications by Mark Russinovich 3 pages 1998 which is herein incorporated by reference in its entirety.

From INTERRUPT BOOT PROCESS OPERATION flow moves to a GAIN ACCESS TO THE MEDIA OPERATION . In GAIN ACCESS TO THE MEDIA OPERATION access to the media e.g. volume or disk containing the rootkit is gained. In various embodiments the access is 1 exclusive e.g. exclusive read and write 2 shared e.g. shared read and write or 3 partially shared and partially exclusive e.g. shared read and exclusive write. In one embodiment access to the volume and or disk is gained by obtaining a handle to the volume and or disk.

In another embodiment exclusive access to the volume is gained by unmounting or locking the volume. In one embodiment the volume is unmounted by making the volume inaccessible e.g. the volume cannot be referenced except to the native application for example native application . Stated another way the volume is unmounted by making the volume exclusively accessible to the native application.

In another embodiment the volume is locked by making the volume inaccessible except to the native application for example native application . For example the volume can be referenced however the volume is locked such that only the native application has access to the volume. Stated another way the volume is locked by making the volume exclusively accessible to the native application.

By unmounting or locking the volume conflicts or other complications arising from access of the volume by applications other than the native application or by the operating system are avoided.

From GAIN ACCESS TO THE MEDIA OPERATION flow moves to a DIRECTLY ACCESS THE MEDIA OPERATION . In DIRECTLY ACCESS THE MEDIA OPERATION the media e.g. volume or disk is directly accessed e.g. by the native application. For example native application uses volume manager which uses disk manager or uses disk manager directly to directly access the volume or disk. The media is directly accessed to allow direct use e.g. reading from and writing to of the media. More particularly directly accessing the media means to access the media without use of i.e. bypassing file system and or the operating system in one embodiment.

From DIRECTLY ACCESS THE MEDIA OPERATION flow moves to a DISABLE ROOTKIT OPERATION . In DISABLE ROOTKIT OPERATION the malicious code e.g. rootkit is disabled.

In one embodiment the malicious code e.g. malicious code module is deleted sometimes called removed from the media. In another embodiment the malicious code e.g. malicious code module is renamed. In either event the media is directly accessed e.g. by the native application to delete or rename the malicious code.

As discussed above in one embodiment the malicious code is in a file and the file has a filename. In DISABLE ROOTKIT OPERATION the filename of the file containing the malicious code is changed sometimes called renamed.

By renaming the malicious code the malicious code will not be executed on subsequent booting of the host computer system or during the present boot process . As discussed above the filename of the file containing the malicious code is listed for execution during booting of the host computer system. By renaming the file containing the malicious code the original filename for the file containing the malicious code is disassociated with the file containing the malicious code i.e. the new filename is associated with the file containing malicious code. Accordingly when the original filename is retrieved for execution there is no associated file for execution due to the renaming and the malicious code is not executed. However the malicious code still remains on the host computer system although under a different filename.

From DISABLE ROOTKIT OPERATION flow moves to a REBOOT HOST COMPUTER SYSTEM OPERATION . In REBOOT HOST COMPUTER SYSTEM OPERATION the host computer system is rebooted a second time in a manner similar to that discussed above with regards to REBOOT HOST COMPUTER SYSTEM OPERATION and so is not repeated here. However in one embodiment in REBOOT HOST COMPUTER SYSTEM OPERATION the host computer system boot process which was interrupted in INTERRUPT BOOT PROCESS OPERATION is resumed and the host computer system is not rebooted from the beginning.

During the rebooting of the host computer system in one embodiment the malicious code is not executed as the malicious code has been removed in DISABLE ROOTKIT OPERATION .

In another embodiment as discussed above malicious code module is renamed during DISABLE ROOTKIT OPERATION . In accordance with this embodiment the original filename of malicious code module is retrieved for execution. However because malicious code module has a new filename i.e. has been renamed malicious cold module is not executed and thus malicious file system module is not created. In this manner the ability of rootkit to hide itself e.g. from application is defeated.

From REBOOT HOST COMPUTER SYSTEM OPERATION flow moves optionally to a CLEAN HOST COMPUTER SYSTEM OPERATION or directly to an EXIT OPERATION or returns to ROOTKIT DETECTED CHECK OPERATION if CLEAN HOST COMPUTER SYSTEM OPERATION is not performed . In CLEAN HOST COMPUTER SYSTEM OPERATION the host computer system is cleaned of malicious code. Illustratively the host computer system is scanned by an antivirus application e.g. application using any one of a number of techniques well known to those of skill in the art and any malicious code located is deleted or disabled. For example malicious code module which his been renamed and any associated registry entries are located and deleted.

As discussed above in one embodiment the malicious code is removed during DISABLE ROOTKIT OPERATION . In accordance with this embodiment CLEAN HOST COMPUTER SYSTEM OPERATION is unnecessary and in one embodiment is not performed so is an optional operation.

From CLEAN HOST COMPUTER SYSTEM OPERATION or from REBOOT HOST COMPUTER SYSTEM OPERATION if CLEAN HOST COMPUTER SYSTEM OPERATION is not performed flow moves to and exits at an EXIT OPERATION or returns to ROOTKIT DETECTED CHECK OPERATION and awaits detection of the next rootkit.

As set forth above upon detection of a rootkit the rootkit is removed without a clean boot i.e. without use of a separate clean boot media such as a floppy disk CD DVD or other media. Further the rootkit is removed without reconfiguration of the BIOS of the host computer system.

Referring again to although malicious code removal application is referred to as an application this is illustrative only. Malicious code removal application should be capable of being called from an application or the operating system. In one embodiment an application is generally defined to be any executable code. Moreover those of skill in the art will understand that when it is said that an application or an operation takes some action the action is the result of executing one or more instructions by a processor.

While embodiments in accordance with the present invention have been described for a client server configuration an embodiment of the present invention is carried out using any suitable hardware configuration or means involving a personal computer a workstation a portable device or a network of computer devices. Other network configurations other than client server configurations e.g. peer to peer web based intranet and internet network configurations are used in other embodiments.

Herein a computer program product comprises a non transitory medium configured to store computer readable code in accordance with an embodiment of the present invention. Some examples of non transitory computer program products are CD ROM discs DVDs ROM cards floppy discs magnetic tapes computer hard drives and servers on a network.

As illustrated in this medium belongs to the computer system itself. However the medium is also removed from the computer system. For example malicious code removal application is stored in memory that is physically located in a location different from processor e.g. memory of server system . Processor should be coupled to the memory . This could be accomplished in a client server system or alternatively via a connection to another computer via modems and analog lines or digital interfaces and a digital carrier line.

More specifically in one embodiment host computer system and or server system is a portable computer a workstation a two way pager a cellular telephone a digital wireless telephone a personal digital assistant a server computer an Internet appliance or any other device that includes components that execute malicious code removal application in accordance with at least one of the embodiments as described herein. Similarly in another embodiment host computer system and or server system is comprised of multiple different computers wireless devices cellular telephones digital telephones two way pagers personal digital assistants server computers or any desired combination of these devices that are interconnected to perform the methods as described herein.

In view of this disclosure malicious code removal application in accordance with one embodiment of the present invention can be implemented in a wide variety of computer system configurations. In addition malicious code removal application could be stored as different modules in memories of different devices. For example malicious code removal application could initially be stored in server system and as necessary a portion of malicious code removal application could be transferred to host computer system and executed on host computer system . Consequently part of the malicious code removal functionality would be executed on processor of server system and another part would be executed on processor of host computer system . In view of this disclosure those of skill in the art can implement various embodiments of the present invention in a wide variety of physical hardware configurations using an operating system and computer programming language of interest to the user.

In yet another embodiment malicious code removal application is stored in memory of server system . Malicious code removal application is transferred over network to memory in host computer system . In this embodiment network interface and I O interface would include analog modems digital modems or a network interface card. If modems are used network includes a communications network and malicious code removal application is downloaded via the communications network.

This disclosure provides exemplary embodiments of the present invention. The scope of the present invention is not limited by these exemplary embodiments. Numerous variations whether explicitly provided for by the specification or implied by the specification or not may be implemented by one of skill in the art in view of this disclosure.

