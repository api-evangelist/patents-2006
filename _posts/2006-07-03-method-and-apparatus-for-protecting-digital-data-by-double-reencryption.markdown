---

title: Method and apparatus for protecting digital data by double re-encryption
abstract: In addition to re-encrypting the data using an unchangeable key, the data is double re-encrypted using a changeable key. The changeable key is used first and the unchangeable key is then used, or in another case, the unchangeable key is used first, and the changeable key is then used. In the aspect of embodiments, there is a case adopting a software, a case adopting a hardware, or a case adopting the software and the hardware in combination. The hardware using the unchangeable key developed for digital video is available. In adopting the software, encryption/decryption is performed in a region below the kernel which cannot be handled by the user to ensure the security for the program and for the key used. More concretely, encryption/decryption is performed with RTOS using a HAL and a device driver, i.e., a filter driver, a disk driver and a network driver, in an I/O manager. Either one of two filter drivers, with a file system driver between them, may be used. Further, both filter drivers may be used.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08024810&OS=08024810&RS=08024810
owner: Intarsia Software LLC
number: 08024810
owner_city: Las Vegas
owner_country: US
publication_date: 20060703
---
This application is a Continuation of prior U.S. application Ser. No. 09 806 510 filed Apr. 16 2001 U.S. Pat. No. 7 093 295 titled METHOD AND APPARATUS FOR PROTECTING DIGITAL DATA BY DOUBLE RE ENCRYPTION by Makoto Saito.

The present invention relates to a system for managing digital contents. In particular the present invention relates to a system used for managing copyrights of digital content for which copyrights are claimed and for protecting the secrecy of the digital content so as to achieve enhanced digital content distribution and to realize digital content commerce.

Hitherto widely spread analog content deteriorate in quality each time it is stored copied edited and transferred. Hence no serious detriment from copyright violations occurs during these operations. However digital content does not deteriorate in quality after repeated storing coping editing and transferring. Thus the control of digital content copyright is an important issue.

Digital data such as digital video data digital audio data etc. is usually supplied to users on a payment basis accompanying a broadcast transfer of a DVD etc. In these cases the data is encrypted and supplied in a manner which excludes unpaid viewing. The encrypted and supplied digital data is decrypted using a crypt key which is supplied to the user by certain means before the data is viewed. Because the quality of decrypted digital data does not deteriorate even when it is stored copied or transferred if the data is stored copied or transferred by the user secondary viewing free of charge may occur. Non authorized re use of the decrypted digital data content is against the benefit of the data content provider. In this respect systems and equipment have been developed to prohibit re use i.e. secondary utilization such as storage copying or transferring the digital data content.

However the prohibition of the secondary utilization makes it less attractive for users of the digital data content and it is now recognized that this may hinder the propagation of the use of the digital data content. In this respect it is now proposed to prevent illegitimate use by re encrypting the decrypted digital data content so that the use of the digital data content is more attractive for users.

When the digital data which is stored in a medium and is given or lent to a user or which is transferred to the user is used for secondary utilization such as storing copying or transferring it is impossible for the copyright owner to protect his or her copyright s in the digital data which is in the hands of the users. Therefore a certain method is required to protect copyrights automatically and forcibly.

Under such circumstances the present inventor has made various proposals with the purpose of protecting digital content copyrights.

In Japanese Patent Laid Open Publications 46419 1994 GB 2269302 U.S. Ser. No. 08 098 415 and 141004 1994 U.S. Pat. No. 5 794 115 U.S. Pat. No. 5 901 339 the present inventor proposed a system for managing copyrights by obtaining a permit key from a key control center via a public telephone line and also an apparatus for such a purpose in Japanese Patent Laid Open Publication 132916 1994 GB 2272822 U.S. Ser. No. 08 135 634 .

Also in Japanese Patent Laid Open Publications 271865 1995 EP0677949A2 U.S. Ser. Nos. 08 416 037 and 185448 1996 EP0704785A2 U.S. Ser. No. 08 536 747 a system for copyright management of the digital contents was proposed.

In these systems and apparatus those who wish to view an encrypted program makes a viewing request to a management center via a communication line using a communication device. Upon receipt of the viewing request the management center transmits a permit key and charges and collects a fee.

Upon receipt of the permit key the requestor transmits the permit key to a receiving device by on line or off line means. When the permit key is received the receiving device decrypts the encrypted program by using the permit key.

The system described in Japanese Patent Laid Open Publication 271865 1995 EP0677949A2 U.S. Ser. No. 08 416 037 uses a program for managing the copyright and copyright information in addition the key for use permission to manage the copyright of the digital content in displaying including process to sound storing copying editing and transferring the digital contents including real time transmission of digital video content in a database system. The program for copyright management watches and manages in a manner that the digital content is not used outside the use permission or user s request.

Japanese Patent Laid Open Publication 271865 1995 EP0677949A2 U.S. Ser. No. 08 416 037 describes that the digital content is supplied from a database in the encrypted state and is decrypted by the copyright management program only when it is displayed or edited and is again in the encrypted state when it is stored copied or transferred. Further it describes that the copyright management program itself is encrypted and is decrypted by using a permit key and the decrypted copyright management program performs decryption and encryption of the copyrighted data and that when a utilization other than storing and displaying the data is performed copyright information including information of the person who performed the utilization is added to the original copyright information and stored as history.

Japanese Patent Laid Open Publication 287014 1996 U.S. Pat. No. 5 867 579 EP0715241A 2 proposed an apparatus for decryption re encryption having a configuration of a board a PCMCIA card an IC card or an IC for the copyright management and a crypt key escrow system. This application also describes the copyright management method applied to a video conference system and an electronic commerce system. U.S. Pat. No. 5 805 706 also describes an apparatus for decryption re encryption having an IC configuration.

Japanese Patent Laid Open Publication 272745 1996 U.S. Pat. No. 5 646 999 EP0709760 proposed a system in which the copyright of original data and the copyright of new data produced by editing the original data or editing a plurality of original data are protected by confirming the validity of a use request based on a digital signature on an edit program in combination with the use of a secret key cryptosystem and a public key cryptosystem.

Japanese Patent Laid Open Publication 288940 1996 U.S. Pat. No. 5 740 246 EP0719045A2 proposed various forms for applying the copyright management system to a database system a video on demand VOD system or an electronic commerce system.

Japanese Patent Laid Open Publication 288940 1996 U.S. Pat. No. 5 848 158 EP0746126A2 proposed a system in which copyrights of original data and new data are protected by using a third crypt key and a copyright label in case of using and editing a plurality of data.

As it can be understood from the data copyright management systems and the data copyright management apparatus proposed by the present inventor as described above the management of data copyrights can be accomplished by encryption decryption re encryption and limiting usage of digital content by the copyright management program. The cryptography technique and usage limitation can be realized by using a computer.

In a case where secret information is exchanged via a network the information is encrypted for preventing piracy.

It is described in U.S. Pat. No. 5 504 818 and U.S. Pat. No. 5 515 441 that information piracy during transmission is prevented by encryption. Using a plurality of keys in such a case is described in U.S. Pat. Nos. 5 504 116 5 353 351 5 475 757 and 5 381 480 and performing re encryption is described in U.S. Pat. No. 5 479 514.

The protection of copyrights in the secondary utilization of digital data by the copyright management program can be realized by re encryption re decryption of the decrypted digital data and by managing and performing the re encryption re decryption by using the copyright management program.

Of course it goes without saying that the means for carrying out re encryption re decryption includes cases where software is used and cases where hardware is used.

Here the operation to obtain encrypted data C from non encrypted data M by using a key K is expressed as and to obtain decrypted data M from encrypted data C by using the key K is expressed as .

When re encryption re decryption of the decrypted data M is repeated re encryption is expressed as 1 1 where i is a positive integer and re decryption is expressed as 1 1 .

Referring to description will be given on an arrangement of a conventional set top box STB and on a method for protecting the digital data performed in the set top box.

Description is not given here on peripheral circuits not directly related to encryption decryption e.g. the description for an amplifier unit and a compression expansion unit is omitted.

When the encrypted digital data C is supplied to the set top box the encrypted digital data C is decrypted by a decryption unit using the first changeable key K obtained from a key center via the same route as or via a different route from that of the encrypted digital data C 1 1 and data M thus decrypted is outputted to a display unit or the like.

In a case where the decrypted data M is stored in a medium such as a digital versatile disk DVD RAM or a hard disk etc. or it is transferred externally via a network the decrypted data M is re encrypted by an encryption unit within an unchangeable key encryption decryption unit using an unchangeable key K 

In a case where the re encrypted data C is used again the re encrypted data C read from a storage medium of the external device or transferred via the network is re decrypted using the unchangeable key K by a decryption unit of the unchangeable key encryption decryption unit 

In this case in order to ensure security it may be arranged in such a manner that the re encrypted data C in the storage medium is erased when the re encrypted data C is read from the storage medium via a route shown by a broken line in the figure and that the data re encrypted again by using the unchangeable key K is re stored.

In U.S. Pat. No. 5 805 706 an integrated circuit for performing re encryption re decryption is described.

In the set top box as arranged above it is easy to handle because re encryption re decryption is automatically carried out by the hardware by using the unchangeable key K and it is effective for forcible re encryption re decryption of the digital data which must be protected.

However since the unchangeable key K is placed in the device and since there is the possibility that the unchangeable key K may be known to others it may become impossible to protect the digital data thereafter.

To solve the above problem the present invention provides a method and an apparatus for double re encrypting the data by using a changeable key in addition to re encrypting by using an unchangeable key.

In use of the unchangeable key and the changeable key there are cases where the changeable key is used and an unchangeable key is then used and where the unchangeable key is used first and the changeable key is then used.

The key used first when re encrypting is the final key used when decrypting and accordingly even if data which is subsequently re encrypted is cryptanalyzed security is highly ensured. Therefore in a case where a changeable key is used first and an unchangeable key is next used for re encryption the possibility that the changeable key is known to others is very low even when the unchangeable key has been known to the others.

In the aspects of the embodiments of the present invention software and or hardware may be used. In an embodiment using hardware hardware using the unchangeable key developed for digital video can be used.

In an embodiment using software in order to ensure the security of the program and the key used encryption decryption is performed in a region under a kernel which cannot be handled by users. More concretely encryption decryption is performed at a filter driver a device driver i.e. a disk network driver and a real time OS using HAL in an I O manager. There are two filter drivers with a file system driver interposed between them and either one of the filter drivers may be used or both may be used.

Referring to description will be given on an arrangement of a set top box STB of a first embodiment of the present invention and a method for protecting the digital data in the set top box.

In the set top box of this embodiment as with the conventional set top box example as shown in description is not given on peripheral circuits not directly related to encryption decryption e.g. an amplifier unit a compression expansion unit and an interface unit to the outside.

The difference of the present embodiment from the conventionally proposed set top box shown in is that a changeable key encryption decryption unit for performing decryption using a second changeable key K is inserted between an unchangeable key encryption decryption unit performing encryption decryption by using the unchangeable key K and a decryption unit .

In reference numeral represents digital data supplied by broadcasting means such as digital terrestrial wave broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by digital storage medium such as a DVD a CD etc. The digital data is encrypted by using a first changeable key K to prevent illegitimate use 1 1 and is supplied to a set top box .

When the encrypted digital data C is supplied to the set top box the encrypted digital C is decrypted by the decryption unit using the first changeable key K obtained from a key center vis the same route as or via a route different from that of the encrypted digital data C 1 1 and the decrypted data M is outputted to a display unit or the like.

In a case where the decrypted data M for which copyrights are claimed is stored in an external device i.e. in a medium of a digital versatile disk DVD RAM or a hard disk or in a case where the data is transferred externally via a network the decrypted data M is re encrypted using a second changeable key K at an encryption unite of the changeable key encryption decryption unit 

In a case where the double re encrypted data C is used again the re encrypted data C read from the storage medium of the external device or transferred from the network is re decrypted by a decryption unit of the unchangeable key encryption decryption unit using the unchangeable key K 

In this case in order to ensure the security it may be arranged in such a manner that when the re encrypted data C is read from the storage medium via a route shown by a broken line in the figure the re encrypted data C in the storage medium is deleted and the data re encrypted by using the changeable key K and the unchangeable key K is re stored.

As described above because the re encryption using the second changeable key K is performed before the re encryption using the unchangeable key even when the unchangeable key K is discovered by others since the data is also encrypted by using the second changeable key K it is very difficult to cryptanalyze the encrypted data without further finding out the second changeable key K.

Also the second changeable key K is first used for re encryption and it is again used for re decryption after the unchangeable key K is used for double re encryption and re decryption. Accordingly the security of the second changeable key K is highly ensured and because it is used first it strongly governs the encrypted data in the most effective manner.

In the description of the above embodiment the encryption unit and the decryption unit are contained in the changeable key encryption decryption unit and the encryption unit and the decryption unit are contained in the unchangeable key encryption decryption unit . Of course it goes without saying that these units and may also be separately provided.

The operations as described above can be easily implemented by providing a computer arrangement having a CPU and a system bus in the set top box .

Now referring to description will be given on another arrangement of the set top box which is a second embodiment of the present invention and also on a method for protecting the digital data carried out in this set top box.

In this second embodiment set top box as with the conventional set top box example shown in description is not given on peripheral circuits not directly related to encryption decryption e.g. an amplifier unit and a compression expansion unit.

The difference of the second embodiment set top box from the first embodiment set top box shown in is that the positions are switched between the unchangeable key encryption decryption unit for encryption decryption using the unchangeable key K and the changeable key encryption decryption unit for encryption decryption using the second changeable key K.

An unchangeable key encryption decryption unit for encryption decryption using the unchangeable key K is connected to a decryption unit and a display and an external changeable key encryption decryption unit for encryption decryption using the second changeable key K is connected to an external device . The second changeable key K may be supplied from the outside or may be generated in the set top box.

In reference numeral represents digital data supplied by broadcasting means such as digital terrestrial wave broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by a digital storage medium such as a DVD a CD etc. The data is encrypted by using a first changeable key K to prevent illegitimate use 1 1 and is supplied to a set top box .

When the encrypted digital data C is supplied to the set top box the encrypted digital data C is decrypted by the decryption unit using the first changeable key K obtained via the same route as or via a route different from that of the encrypted digital data C 1 1 and the decrypted data M is outputted to a display unit or the like.

In a case where the decrypted data M for which copyrights are claimed is stored in an external device i.e. in a medium such as a digital versatile disk DVD RAM or a hard disk etc. or is transferred externally via a network the decrypted data M is re encrypted using the unchangeable key K at the encryption unit of the unchangeable key encryption decryption unit 

In a case where the double re encrypted data C is used again the re encrypted data C read from the storage medium of the external device or transferred from the network is re decrypted using the external changeable key K by the re decryption unit of the external changeable key encryption decryption unit 

In this case in order to ensure the security it may be arranged in such a manner that when the re encrypted data C is read from the storage medium via a route shown by a broken line in the figure the double re encrypted data C in the storage medium is erased and the data re encrypted by using the unchangeable key K and the external changeable key K is re stored.

As described above because the re encryption is performed using the unchangeable key K before the re encryption using the second changeable key K even when the unchangeable key K is discovered by others since the data is also encrypted by using the second changeable key K it is very difficult to cryptanalyze the encrypted data without further finding out the second changeable key K.

In this arrangement the changeable key encryption decryption unit is simply added to the unchangeable encryption decryption unit of the conventionally proposed set top box shown in and accordingly a set top box employing the present invention can be easily achieved.

In the description of this embodiment the encryption unit and the decryption unit are contained in the unchangeable key encryption decryption unit and the encryption unit and the decryption unit are contained in the changeable key encryption decryption unit . Of course it goes without saying that these units and may also be separately provided.

The operation as described above can be easily implemented by providing a computer arrangement having a CPU and a system bus in the set top box .

Digital data content is handled not only in the set top box but also in a computer such as a personal computer.

Referring to through description will be given on embodiments of the present invention applied to an apparatus using a personal computer.

Unlike the set top box where all components are constituted of hardware and are operated only by the hardware a personal computer is an apparatus which is operated by controlling the hardware incorporated in the apparatus using software.

In order to efficiently operate the computer a operating system OS is used which manages the overall operation of the computer.

A conventional operating system used in the personal computer comprises a kernel for providing basic services such as memory management task management interrupt handling and communication between processes and an operating system service providing other services.

However with the advances in computer developments for example the functional improvements of a microprocesor and the price decrease of RAM used as main memory and also the user s demand for an increase of the performance ability of computers improvements in the functions of the operation system to manage the overall computer operation has been required. Accordingly the scale of the operating systems has become comparatively larger than before.

Since such an enlarged operating system itself occupies a large amount of space in the hard disk where it is to be stored the space to store application programs or data needed by the user is liable to be rather limited and that may lead to inconvenience for the user in using the computer.

To cope with such situations newer operating systems are of designed with user dependent subsystem parts such as an environmental subsystem for performing emulation of the other operating systems and graphics and a core subsystem such as a security subsystem removed from a kernel. Basic parts of an operating system consist of a HAL hardware abstraction layer to absorb differences of hardware micro kernels to provide a scheduling function an interrupt function an I O management function etc. and a system service API application programming interface interposed between the subsystem and the micro kernel.

With the above arrangement expandability of the operating system needing changes or additions of function is improved and portabilty of the operating system corresponding to the intended purpose can be made much easier.

By the distributed arrangement of elements of the micro kernel to a plurality of network computers it is now possible to easily realize a distributed operating system.

Computers are used in computer peripheral units various types of control units communication devices etc. in addition to personal computers typically represented by the desk top type or notebook type personal computers. In such cases unlike the operating system for a general purpose personal computer in which importance is put on the man machine interface a real time operating system is adopted in which importance is placed on speedy execution. An operating system especially one for embedding is suitable for each of these units and devices.

Of course the cost for development is increased when developing an operating system specially tailored for different embedded devices. For this reason it is recently proposed to use a general purpose operating system in the personal computer also for the embedded type real time operating system. By arranging a program specific for the embedded type in a subsystem combined with a micro kernel it is now practical to obtain an embedded type real time operating system.

Major functions of the operating system include task management such a scheduling or interrupt processing.

The task management has mainly two different types in the operating system single task type which only performs one task processing at the same time and multi task type for performing a plurality of task processings at the same time. The multi task type is divided into a multi task type where changeover of the task depends upon the task to be processed and a multi task type not dependent upon the task to be processed.

Among these the single task type allocates one process to an MPU so that the MPU is not free until the process is completed. A non preemptive multi task type allows the MPU to be allocated a plurality of processes by time division so that process is not executed unless the process in execution gives the control back to the operating system. A preemptive multi task type interrupts the process in execution at a certain time interval so that the control is forcibly transferred to the other process.

The task management in the computer is carried out according to the process which is a unit having system resources such as a memory a file etc. and the process is managed according to a thread which is a unit to allocate CPU time with divided processes. In this case the system resources are shared by all threads in the same process. This means that there are more than one thread to share system resources in one process.

Each task to be processed by the multi task type has a priority spectrum which is generally divided into steps. The normal task performing no interrupt is classified into dynamic classes which are divided into 0 15 steps and the task performing interrupt is classified to real time classes to be divided into steps.

Interrupt processing is executed using an interrupt enable time normally 10 milliseconds called a time slice unit. Ordinary interrupt is executed at 10 millisecond time slices.

Under such circumstances a time slice has been recently proposed in which an interrupt enable time called a real tine slice is 100 microseconds. If this real time slice is used it is possible to execute an interrupt with priority over the conventional interrupt of 10 milliseconds.

In a third embodiment shown in changeable key encryption decryption processing by software and the management of a crypt key in the computer are carried out by a real time OS provided in the HAL.

In reference numeral represents an operating system in a computer a display unit for displaying output from the computer an unchangeable key encryption decryption unit and a data storage medium such as a digital versatile disk DVD RAM or a hard disk or a data transfer system such as a network.

The operating system comprises an operating system service and a system service API which are user regions and a kernel and a HAL which are non user regions. The system service API is arranged between the operating system service and the kernel and serves to mediate between the operating system service and the kernel . The HAL is arranged at the lowermost layer of the operating system and serves to absorb differences in the hardware for the software.

The operating system service comprises an application a subsystem and a security subsystem . The kernel comprises a plurality of micro kernels and and a kernel . The micro kernel has task management functions such as scheduling interrupt etc. and the micro kernel has an I O management function.

The micro kernel having the I O management function comprises an I O management device drivers such as a disk driver and a network driver which are managed by the I O manager and a filter driver which is inserted when necessary between the I O manager and the device drivers such as the disk driver and the network driver .

The changeable key encryption decryption processing in the computer is executed by software. In case of the third embodiment the changeable key encryption decryption processing is carried out by the aforementioned real time OS RTOS with priority over other tasks in the HAL in the operating system .

Similar to the first embodiment shown in digital data supplied by broadcasting means such as digital terrestrial wave broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by a digital storage medium such as a DVD a CD etc. is encrypted using a first changeable key K to prevent illegitimate use 1 1 and is supplied. The supplied encrypted digital data C is decrypted by the operating system service using the first changeable key K provided from the key center via the same route as or via a route different from that of the encrypted digital date C 1 1 and the decrypted data M is outputted to the display unit or the like.

In a case where the decrypted data M for which copyrights are claimed is stored in a medium such as a digital versatile disk DVD RAM or a hard disk or where it is transferred externally via a network the decrypted data M is mandatory re crypted by HAL using a second changeable key K 

When the double re encrypted data C is utilized the double re encrypted data C read from the storage medium or transferred via the network is re decrypted using the unchangeable key K at the unchangeable key encryption decryption unit 

The real time OS is executed in priority over every other task. In the third embodiment the real time OS is implemented by the HAL being a contact point with the hardware in the operating system. Accordingly the re encryption of the digital data is performed in a reliable manner and it is impossible for decrypted data M as it is to be stored into the external device or to be transferred. Also re encryption is performed using the second changeable key K before the re encryption using the unchangeable key K. As a result even if the unchangeable key K is known it is very difficult to cryptanalyze the encrypted data by finding out the second changeable key K as the data is also encrypted by the second changeable key K.

Because the second changeable key K is used first and is then used after the unchangeable key K has been used key security can be ensured. Because the second changeable key K has been used first it strongly governs the encrypted data.

The above operations can be easily implemented by arranging the unchangeable key encryption decryption unit as a sub computer structure having a CPU and a system bus.

In a fourth embodiment shown in the changeable key encryption decryption is provided by software carried out at a filter driver placed in the I O management micro kernel in the kernel .

In an I O management micro kernel with no filter driver placed in it a file system driver an intermediate driver and a device driver are arranged from an upper hierarchy to a lower hierarchy. When necessary a filter driver A or a filter driver B is placed above the file system driver or between the intermediate driver and the device driver .

Because the I O management micro kernel can be designed to have these filter drivers A and B perform re encryption re decryption and management of the key the filter drivers A or B is designed to carry out the re encryption re decryption processing and the key management in this embodiment.

The filter driver is arranged not in the operating system service unit which can be handled by the user but in the kernel which cannot be handled by the user. On the other hand it is generally practiced to make the specification change to fit the particular computer using the operating system. In particular it is not very rare to change the I O manager therein.

Utilizing the above the modules having the function of re encryption re decryption processing and the key management are placed in the I O manager as the filter driver A or the filter driver B in the fourth embodiment.

Similar to the first embodiment shown in digital data supplied by broadcasting means such as digital terrestrial wave broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by digital storage medium such as a DVD a CD etc. is encrypted using a first changeable key K to prevent illegitimate use 1 1 and it is supplied. The encrypted and supplied digital data C is decrypted by the operating system service unit using the first changeable key K provided from the key center via the same route as or via a route different from that of the encrypted digital data C 1 1 and the decrypted data M is outputted to the display unit and the like.

In a case where the decrypted data M for which copyrights are claimed is stored in a medium such as a digital versatile disk DVD RAM or a hard disk or in a case where it is transferred externally via a network the decrypted data M is mandatorily re encrypted by the filter driver A or B using the external changeable key K 22 2 1 1 2 . Further the re encrypted data C is double re encrypted at the internal unchangeable key encryption decryption unit using an unchangeable key K 

When the double re encrypted data C is utilized again the double re encrypted data C read from the storage medium or transferred via the network is re decrypted using the unchangeable key K at the internal unchangeable key encryption decryption unit 

The filter driver can be easily placed into the kernel of the operation system in a part of the A O manager. In so doing the function of the re encryption re decryption processing and the key management can be easily incorporated into the operation system. Also since re encryption is performed using the second changeable key K before the re encryption using the unchangeable key K even if the unchangeable key K is discovered by others it is very difficult to cryptanalyze the encrypted data without finding out the second changeable key K because the data is also encrypted by the second changeable key K.

Further because the second changeable key K is used first and is then used after the unchangeable key K is used the key security can be highly ensured. Also because the second changeable key K is used first it strongly governs the encrypted data.

The above operations can be easily implemented by arranging the unchangeable key encryption decryption unit as a sub computer structure having a CPU and a system bus.

In a fifth embodiment shown in the changeable key encryption decryption and the key management is provided by software carried out at the disk driver and the network driver contained in the I O management micro kernel in the operating system .

As already explained in connection with the file system driver the intermediate driver and the device driver are arranged from an upper hierarchy to a lower hierarchy in the I O management micro kernel. The changeable key encryption decryption processing and the key management can be carried out also in the device driver positioned at the lowermost layer.

Similar to the first embodiment shown in the digital data supplied by broadcasting means such as digital terrestrial wave broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by digital storage medium such as a DVD a CD etc. is encrypted using the first changeable key K to prevent illegitimate use 1 1 and it is supplied. The encrypted and supplied digital data C is decrypted by the operating system service unit using the first changeable key K provided from the key center via the same route as or a route different from that of the encrypted digital data C 1 1 and the decrypted data M is outputted to the display unit or the like.

In a case where the decrypted data M for which copyrights are claimed is stored in a medium such as a digital versatile disk DVD RAM or a hard disk or in a case where it is transferred externally via a network the decrypted data M is mandatorily re encrypted by the device driver i.e. the disk driver and the network driver using the second changeable key K 

When the double re encrypted data C is utilized again the double re encrypted data C read from the storage medium or transferred via a network is re decrypted using the unchangeable key K by the internal unchangeable key encryption decryption unit 

For the device driver it is generally practiced to make the specification change to fit the particular computer using the operating system or when the corresponding device has been modified.

Since the function of the re encryption re decryption processing and the key management is incorporated into such a device driver it allows the easy incorporation of the function into the kernel of the operating system. Also since re encryption is performed using the second changeable key K before the re encryption using the unchangeable key K even if the unchangeable key K is discovered by others it is very difficult to cryptanalyze the encrypted data without finding out the second changeable key K because the data is also encrypted using the second changeable key K.

There is a possibility that the second changeable key K may be discovered by others when it is repeatedly used. In such a case it is preferably designed in such a manner that the second changeable key K used for encryption is abandoned and generated again when necessary for decryption as described in Japanese Patent Laid Open Publication 185448 1996 EP0704885A2 U.S. Ser. No. 08 536 749 . If it is necessary to have the key for decryption it should be obtained from the key center again.

These operations can be easily implemented by arranging the unchangeable key encryption decryption unit as a sub computer structure having a CPU and a system bus.

In the embodiments described above the second changeable key K and the unchangeable key K are used in addition to the first changeable key K. In the embodiments described below a third changeable key K is used additionally so that more reliable copyright management of digital content is provided.

Referring to description will be given on an arrangement of a set top box in a sixth embodiment of the present invention which is a variation of the first embodiment and also on a method for protecting digital data carried out in the set top box.

In the set top box of this embodiment similar to the set top box of the first embodiment no description is given on peripheral circuits not directly related to encryption decryption e.g. an amplifier unit and a compression decompression unit.

The set top box of the sixth embodiment has a difference from that of the first embodiment in distinguishing between a case where the decrypted data M is stored in a storage medium such as a hard disk which is incorporated in or dedicated to the set top box and another case where the decrypted data M is stored in a removable medium e.g. a DVD RAM in an external or is transferred externally via a network.

The internal unchangeable key encryption decryption unit and further a changeable key encryption unit are provided. In a case where the decrypted copyrighted data is stored for example in a hard disk as a storage medium which is incorporated in or dedicated to the set top box it is double re encrypted using an internal unchangeable key K. On the other hand in a case where it is stored in a removable medium i.e. a DVD RAM or is transferred externally via the network it is double re encrypted not by the internal unchangeable key K but by a third changeable key K.

In reference numeral represents digital data which is supplied by broadcasting means such as digital terrestrial wave broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by a digital storage medium such as a DVD a CD etc. The digital data is encrypted using a first changeable key K to prevent illegitimate use 1 1 and encrypted digital data C is supplied to a set top box .

When the encrypted digital data C is supplied to the set top box the encrypted digital data C is decrypted by a decryption unit using a first changeable key K obtained from a key center 1 1 and the decrypted data M is outputted to a display unit or the like.

In a case where the decrypted copyrighted data M is stored in a storage medium such as a hard disk which is incorporated in or is dedicated to the set top box or in a removable medium such as a DVD RAM or where it is transferred externally via a network the decrypted data M is re encrypted by an encryption unit of a changeable key encryption decryption unit using a second changeable key K which is obtained from the key center or generated in the set top box 

In a case where the re encrypted data C is stored in a hard disk of the storage medium incorporated into or dedicated to the set top box the re encrypted data C is double re encrypted by an encryption unit of an internal unchangeable key encryption decryption unit using an unchangeable crypt key K placed in the internal unchangeable key encryption decryption unit 

When the re encryption data C stored in the storage medium is utilized the double re encryption data C read from the storage medium is decrypted using the unchangeable crypt key K placed in a decryption unit of the internal unchangeable key encryption decryption unit 

In this case in order to ensure security when the double re encrypted data C is read from the storage medium via a path shown by a broken line in the figure it may be designed in a manner that the double re encrypted data C in the storage medium is erased at that time and that the data re encrypted using the changeable key K and the internal unchangeable key K is stored again.

In a case where the re encrypted data C is stored in a DVD RAM of a removable medium or it is transferred externally via a network at the externals the re encrypted data C is double re encrypted using a third changeable key K which is obtained from the key center or generated in the set top box by a changeable key encryption unit 

When the double re encrypted data C sent to the externals is utilized the double re encrypted data C is decrypted using the third changeable key K stored at a decryption unit of a changeable key encryption decryption unit 

These operations can be easily achieved by providing a sub computer arrangement having a CPU and a system bus in the set top box .

Referring to description will be given on an arrangement of a set top box of a seventh embodiment which is a variation of the sixth embodiment and also on a method for protecting digital data carried out in the set top box.

In the set top box of this embodiment again similar to the set top box of the sixth embodiment no description is given on peripheral circuits not directly related to encryption decryption e.g. an amplifier unit and a compression decompression unit.

The seventh embodiment set top box is different from that of the sixth embodiment in that the inserted positions are exchanged between the unchangeable key encryption decryption unit for performing encryption decryption using the the unchangeable key K and the changeable key encryption decryption unit for performing encryption decryption using the second changeable key K and in that there is further provided a changeable key encryption unit for performing encryption decryption using the second changeable key K for the case where the data is stored in a DVD RAM of a removable medium or is transferred externally via a network at the external .

The digital data which is supplied by broadcasting means such as digital terrestrial wave broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by a digital storage medium such as a DVD a CD etc. in encrypted using a first changeable key K in order to prevent illegitimate use 1 1 and encrypted digital data C is supplied to the set top box .

When the encrypted digital data C is supplied to the set top box the encrypted digital data C is decrypted by the decryption unit using the first changeable key K obtained from the key center 1 1 and the decrypted data M thus obtained is outputted to the display unit or the like.

In a case where the copyrighted and decrypted date M is stored in the storage medium such as a hard disk incorporated in or dedicated to the set top box the decrypted data M is re encrypted to re encrypted data C using the unchangeable crypt key K by the internal unchangeable key encryption decryption unit 

The re encrypted data C is double re encrypted by the encryption unit of the changeable key encryption decryption unit using the second changeable key K obtained from the key center or generated in the set top box 

When the double re encrypted data C stored in the storage medium is utilized the double re encrypted data C read from the storage medium is re decrypted by the decryption unit of the changeable key encryption decryption unit using the second changeable key K 

In this case in order to ensure security when the double re encrypted data C is read from the storage medium via a route shown by a broken line in the figure it may be designed in a manner that the double re encrypted data C in the storage medium is erased at that time and that the data re encrypted using the second changeable key K and the unchangeable key K is stored again.

In a case where the decrypted data M is stored in a DVD RAM of a removable medium or is transferred outside via a network at the external the decrypted data M is re encrypted to re encrypted data C using a third changeable key K obtained from the key center or generated in the set top box by the changeable key encryption unit 

The re encrypted data C is encrypted to double re encrypted data C by the changeable key encryption unit using the second changeable key K obtained from the key center or generated at the set top box 

When the double re encrypted data C sent to the externals is utilized the double re encrypted data C is decrypted using the second changeable key K by the decryption unit of the changeable key encryption decryption unit 

In the above embodiment the third changeable key K is used by the changeable key encryption unit and the second changeable key K is used by the changeable key encryption unit while this may be performed in reverse order.

Also it may be designed in a manner that the encryption unit of the changeable key encryption decryption unit serves the function of the changeable key encryption unit .

While description has been given on the above in the case where the encryption unit and the decryption unit are contained in the unchangeable key encryption decryption unit and the encryption unit and the decryption unit are contained in the changeable key encryption decryption unit it goes without saying that these units and may be separately provide.

These operation s can be easily achieved by providing a sub computer arrangement having a CPU and a system bus in the set top box .

Description will be given on a variation which is applied to an embodiment using a personal computer.

The eighth embodiment shown in is a variation of the fourth embodiment shown in . In the embodiment detailed description common to the fourth embodiment arrangement is not given here.

The eighth embodiment is different from the fourth embodiment in distinguishing between the cases where the decrypted data M is stored in a storage medium such as a hard disk incorporated in or dedicated to the computer and where it is stored in a removeable medium such as a DVD RAM or is transferred externally via a network .

For this purpose changeable key encryption units and are provided as hardware in addition to the unchangeable key encryption decryption unit . In a case where the copyrighted and decrypted data is stored in the hard disk of the storage medium incorporated in or dedicated to the computer it is double re encrypted and decrypted using the unchangeable key K by the encryption decryption unit via a disk driver . In a case where the data is stored in the DVD RAM of the removable medium it is double re encrypted and decrypted using the third changeable key K by the encryption decryption unit via the disk driver . In a case where the data is transferred externally via the network it is double re encrypted and decrypted using the third changeable key K by the changeable key encryption decryption unit via a network driver .

Similar to the first embodiment shown in the digital data supplied by broadcasting means such as digital terrestrial broadcasting digital CATV broadcasting digital satellite broadcasting etc. by network means such as Internet or by a digital storage medium such as a DVD a CD etc. is encrypted using a first changeable key K to prevent illegitimate use 1 1 and is supplied. The encrypted data C that supplied is decrypted by the operating system service using the first changeable key K provided from the key center via the same route as or a route different from that of the encrypted digital data C 1 1 and the decrypted data M is outputted to the display unit or the like.

In cases where the decrypted data M is stored in the storage medium incorporated in or dedicated to the computer such as a hard disk where it is stored in a medium such as the DVD RAM and where it is transferred externally via a network the decrypted data M is re encrypted by a filter driver using the second changeable key K obtained from the key center or generated in the operating system service 

Further when the re encrypted data C is stored in a storage medium incorporated in or dedicated to a computer the re encrypted data C is double re encrypted using an unchangeable key K by the encryption decryption unit in the hardware 2 0 2 0 2 0 1 1 2 0 and re encrypted data C is stored in the hard disk or the like.

In the case where the double re encrypted data C stored in the storage medium is utilized the double re encrypted data C read from the storage medium is re decrypted using the unchangeable key K by the encryption decryption unit in the hardware 2 2 2 0 0 1 1 2 0 further the re decrypted data C is decrypted using the second changeable key K by the filter driver having encryption decryption function 2 2 1 1 2 and the decrypted data M is outputted by the operating system of the computer to the display unit or the like to be utilized.

When the re encrypted data C is stored in a DVD RAM of the removable medium the re encrypted data C is double re encrypted using the third changeable key K by the changeable key encryption decryption unit of the hardware. 2 32 3 2 3 1 1 2 3 and double re encrypted data C is stored in the removable medium the DVD RAM.

In a case where the double re encrypted data C stored in the removable medium is utilized the double re encrypted data C read from the removable medium is re decrypted using the third changeable key K obtained from the key center or generated in the operating system service by the encryption decryption unit in the hardware 2 2 2 3 3 1 1 2 3 further the re decrypted data C is decrypted using the second changeable key K by the filter driver having encryption decryption function 2 2 1 1 2 and the decrypted data M is outputted by the operating system of the computer to the display unit or the like to be utilized.

When the re encrypted data C is transferred externally via the network the re encrypted data C is double re encrypted using the second changeable key K by the encryption decryption unit 2 3 2 3 2 3 1 1 2 3 and double re encrypted data C is transferred externally via the network .

In a case where the double re encrypted data C transferred from the outside via the network is utilized the encrypted re encrypted data C is re decrypted using the third changeable key K by the encryption decryption unit 2 2 2 3 3 1 1 2 3 further the re decrypted data C is decrypted using the second changeable key K by the filter driver having encryption decryption function 2 2 1 1 2 and the decrypted data M is outputted by the operating system of the computer to the display unit or the like to be utilized.

When the re encrypted data C is transferred outside via the network the re encrypted data C is double re encrypted using the second changeable key K at the encryption decryption unit 2 3 2 3 2 3 1 1 2 3 and double re encrypted data C is transferred outside via the network .

In a case where the double re encrypted data C transferred from the outside via the network is utilized the encrypted data C is re decrypted using the third changeable key K at the encryption decryption unit 2 2 2 3 3 1 1 2 3 further the re decrypted data C is decrypted using the second changeable key K at the filter driver having encryption decryption function 2 2 1 1 2 and the decrypted data M is outputted by the operating system of the computer to the display unit or the like to be utilized.

In the above embodiment in order to facilitate the explanation it has been described that the encryption decryption unit and are separate but it goes without saying that these units may be a single unit.

The encryption decryption as described above is managed by real time OS RTOS as already explained with priority over other tasks in the HAL in the operating system .

These operations can be easily achieved by designing the hardware as the sub computer arrangement having a CPU and a system bus.

In the I O management micro kernel a file system driver an intermediate driver and device drivers i.e. a disk driver and a network driver are arranged from an upper hierarchy to a lower hierarchy. When necessary a filter driver A or a filter driver B for performing changeable key encryption decryption is inserted above the file system driver or between the intermediate driver and the device driver.

Because these filter drivers A and B can perform re encryption de decryption it is designed to have the filter driver A or B carry out the re encryption re decryption processing and the management of crypt keys in this embodiment.

In cases where the copyrighted and decrypted data M is stored in a storage medium such as a hard disk incorporated therein or dedicated thereto where it is stored in a removable medium such as a DVD RAM or where it is transferred outside via a network the decrypted data M is re encrypted by the filter driver A or B using the second changeable key K obtained from the key center or generated in the I O management micro kernel 22 2 1 1 2 .

Further in a case where the re encrypted data C is stored in a computer incorporated or dedicated storage medium the re encrypted data C is double re encrypted using the unchangeable key K by the encryption decryption unit in the hardware 2 02 0 2 0 1 1 2 0 and double re encrypted data C is stored in the hard disk or the like.

When the double re encrypted data C stored in the storage medium is utilized the double re encrypted data C read from the storage medium is re decrypted using the unchangeable key K by the encryption decrypted unit in the hardware 22 2 0 0 C1 1 2 0 further the re decrypted data C is decrypted using the second changeable key K by the filter driver having the encryption decryption function 2 2 1 1 2 and the decrypted data M is outputted by the operating system of the computer to the display unit or the like to be utilized.

Also in a case where the re encrypted data C is stored in the removable medium such as a DVD RAM the re encrypted data C is double re encrypted using the third changeable key K obtained from the key center or generated in the I O management micro kernel by the encryption decryption unit in the hardware 2 32 3 2 3 1 1 2 3 and double re encrypted data C is stored in a removeable medium such as the DVD RAM.

When the double re encrypted data C stored in the removable medium is utilized the re encrypted data C read from the removeable medium is re decrypted using the third changeable key K by the encryption decryption unit in the hardware 22 2 3 3 1 1 2 3 further the re decrypted data C is decrypted using the second changeable key K by the filter driver having encryption decryption function 2 2 1 1 2 and the decrypted data M is outputted by the operating system of the computer to the display unit or the like to be utilized.

Also in a case where the re encrypted data C is transferred externally via the network the re encrypted data C is double re encrypted using the second changeable key K by the encryption decryption unit 2 32 3 2 3 1 1 2 3 and double re encrypted data C is transferred externally via the network .

When the double re encrypted data C transferred from the outside via the network is utilized the re encryption data C is re decrypted using the third changeable key K by the encryption decryption unit 22 2 3 3 1 1 2 3 further the re decrypted data C is decrypted using the second changeable key K by the filter driver having encryption decryption function 2 2 1 1 2 and the decrypted data M is outputted by the operating system of the computer to the display unit or the like to be utilized.

It is generally practiced that the specification of the device driver is changed to fit the particular computer using the operating system or according to the corresponding device modified.

By providing the device driver with the function for the re encryption decryption processing and the management of a key it allows the easy incorporation of the function into the kernel of the operating system. Also by re encryption the data using the second changeable key K before it is re encrypted using the unchangeable key K it is very difficult to cryptanalyze the encrypted data even if the unchangeable key is discovered by others without finding out the second changeable key K because the data is also encrypted using the second changeable key K.

Further because the second changeable key K is used first and then is used after the unchangeable key K is used high security of the key is ensured. Because the second changeable key K is used first it also strongly governs the encrypted data.

However when the second changeable key K is repeatedly used there is a possibility it may be discovered by others. In such a case it is preferably designed in such a manner that the second changeable key K used for encryption is abandoned and it is again obtained from the key center or generated when necessary for decryption a described in Japanese Patent Laid Open Publication 185448 1996 EP0704885A2 U.S. Ser. No 08 536 749 .

In order to perform re encryption re decryption of digital data as above it is necessary to add to the digital data information to indicate that storage or transfer of the digital data is restricted. In a case where the digital data is stored or transferred without being edited illegitimate use of the digital data can be prevented by the method and the apparatus for re encryption re decryption as described above.

However when the digital data is edited there is a possibility that the information to identify the restriction of storage or transfer may be lost.

In such the case it may be designed in a manner that all of the data are re encrypted re decrypted using a key specific to the device a master key .

In so doing even the digital data which has been edited for example by the cut paste method can be prevented from illegitimate use by re encryption re decryption.

Also it may be designed in a manner that the digital data without the information to identify the restriction of storage or transfer only is re encrypted re decrypted using the master key and that the digital data provided with the information to identify the restriction of storage or transfer is re encrypted re decrypted using the method and the apparatus as explained in the above embodiments.

In a case where the copyrighted and encrypted digital data is utilized in a specific device such as a set top box illegitimate storing copying or transferring can be relatively easily prevented. Also in a case where the copyrighted and encrypted digital data is utilized on a computer the management of storing copying or transferring the decrypted digital data can be executed by using the decryption re encryption apparatus described in Japanese Patent Laid Open Publication 287014 1996 U.S. Pat. No. 5 867 579 EP0713241A2 or by using the decryption re encryption apparatus described in U.S. Pat. No. 5 805 706.

However the digital data decrypted for the purpose of displaying or printing is present on the bus of the computer and it is possible to store copy or transfer the decrypted digital data via a device connected to the bus. In the following description will be given on a copyright management apparatus which solves this problem.

Also this copyright management apparatus can be realized in a configuration such as a sub board a PCMCIA card and IC card or an IC package for the purpose of security.

In reference numeral represents a CPU A ROM a RAM a hard disk drive a flexible disk drive a CD ROM drive a modem etc. are connected to a system bus connected to the CPU .

Reference numeral represents a copyright management apparatus which comprises a decryption encryption unit a video interface an audio interface and a printer interface .

A display unit a speaker and a printer are connected to the video interface the audio interface and the printer interface respectively on the outer side of the computer.

The decryption unit and the encryption unit of the decryption encryption unit are connected to the system bus of the computer. The video interface the audio interface and the printer interface are connected to the decryption unit .

This arrangement can be easily achieved by designing the copyright management apparatus as a sub computer arrangement having a CPU and a system bus.

In cases where the decrypted digital data M is stored in the hard disk drive where it is copied at the flexible disk drive or where it is transferred via the modem the decrypted digital data is re encrypted using the second changeable key K by the encryption unit 

The encrypted digital data C encrypted using the first changeable key K is supplied to the decryption unit from the system bus and is decrypted using the first changeable key K 1 1 .

In a case where the decrypted digital data M is outputted to the display unit or the speaker it is turned to analog at the video interface and the audio interface in the copyright management apparatus and is outputted in a predetermined signal form.

When the decrypted digital data M is outputted to the printer print data is outputted via the printer interface .

When this copyright management apparatus is used the decrypted digital data other than the data outputted to the printer is not present outside the copyright management apparatus . Because the data outputted to the printer is still data digital data of a moving picture or of audio data is not present outside the copyright management apparatus .

In the computer non encrypted digital data is also present in addition to the decrypted digital data.

In order to process the non encrypted digital data and the decrypted data by distinguishing between them it is necessary to provide a video interface an audio interface and a printer interface and this would make the system more complicated and costly. To avoid such situation it may be designed in a manner that non encrypted digital data is processed at the video interface and the audio interface in the copyright management system .

This copyright management apparatus can be realized in a configuration such as a sub board a PCMCIA card an IC card or an IC package for security purpose.

In reference numeral represents a CPU A ROM a RAM a hard disk drive a flexible disk drive a CD ROM drive a modem etc. are connected to a system bus connected to the CPU .

Reference numeral represents a copyright management apparatus. The copyright management apparatus has in addition to the decryption encryption unit an unchangeable key encryption unit a crypt video interface a crypt audio interface and a crypt printer interface .

Also an encrypted digital video display unit an encrypted digital audio player and an encrypted digital data printer which arranged outside of the computer are connected to the crypt video interface the crypt audio interface and the crypt printer interface .

The decryption unit and the encryption unit of the decryption encryption unit are both connected to the computer system bus . The unchangeable key encryption unit is further connected to the decryption unit .

The crypt video interface the crypt audio interface and the crypt printer interface are connected to the unchangeable key encryption unit .

The encrypted data display unit is connected to the crypt video interface the encrypted audio data player is connected to the crypt audio interface and the encrypted data printer is connected to the crypt printer interface .

The above arrangement can be easily realized by designing the copyright management apparatus as a sub computer arrangement having a CPU and a system bus.

The encrypted data display unit has an unchangeable key decryption unit connected to the crypt video interface a D A converter connected to the unchangeable key decryption unit and a display unit connected to the D A converter .

The encrypted audio data player has an unchangeable key decryption unit connected to the crypt audio interface a D A converter connected to the unchangeable key decryption unit and a speaker connected to the D A converter .

The encrypted data printer has an unchangeable key decryption unit connected to the crypt interface and a printer connected to the unchangeable key decryption unit .

Needless to say the encrypted data display unit the encrypted audio data player and the encrypted data printer have other components such as an amplifier.

The encrypted digital data C encrypted using the first changeable key K is supplied to the decryption unit from the system bus and it is decrypted using the first changeable key K 1 1 .

When the decrypted digital data M is stored at the hard disk drive or is copied at the flexible disk drive or is transferred via the modem it is re encrypted using the second changeable key K by the encryption unit 

When the decrypted digital data M is outputted to the encrypted data display unit the encrypted audio data player or the encrypted data printer it is re encrypted using the unchangeable key K by the unchangeable key encryption unit in the copyright management apparatus 

The re encrypted digital data C is arranged to be provided to the encrypted data display unit the encrypted audio data player and the encrypted data printer at the crypt video interface the crypt audio interface and the crypt printer interface respectively and an encrypted display signal Cd and encrypted audio signal Ca and an encrypted print signal Cp are respectively outputted.

When the encrypted display signal Cd is inputted to the encrypted data display unit from the crypt video interface it is decrypted using the unchangeable key K at the unchangeable key decryption unit 0 0 the decrypted display signal MA is converted to a displayable analog signal by the D A converter and it is displayed on the display unit .

If the display unit is a digital display unit which can display the digital data as it is the D A converter is unnecessary.

When the encrypted audio signal Ca is inputted to the encrypted audio data player from the crypt audio interface it is decrypted using the unchangeable key K by the unchangeable key decryption unit 0 0 the decrypted audio signal Ma is converted to a playable analog signal by the D A converter and it is played by the speaker .

The encrypted print signal Cp inputted to the encrypted data printer from the crypt printer interface is decrypted using the unchangeable key K by the unchangeable key decryption unit 0 0 and the decrypted print signal Mp is printed by the printer .

When this copyright management apparatus is used no decrypted data is present outside the copyright management apparatus .

As aforementioned non encrypted digital data is also present in addition to the decrypted digital data in the computer.

In order to process the non encrypted digital data and the decrypted digital data by distinguishing between them it is necessary to provide a video interface an audio interface and a printer interface and this would make the system more complicated and costly. To avoid such situation it may be designed in a manner that the non encrypted digital data is processed by the unchangeable key re encryption unit of the copyright management apparatus .

The copyright management apparatus can be realized in a configuration such as a sub board a PCMCIA card and IC card or an IC package for security purpose.

In reference numeral represents a CPU. A ROM a RAM a hard disk drive a flexible disk drive a CD ROM drive a modem etc. are connected to a system bus connected to the CPU .

The copyright management apparatus can be realized in a configuration such as a sub board a PCMCIA card an IC card or an IC package for security purpose.

In reference numeral represents a CPU. A ROM a RAM a hard disk drive a flexible disk drive a CD ROM drive a modem etc. are connected to a system bus connected to the CPU .

Reference numeral represents a copyright management apparatus which comprises a decryption encryption unit a video interface an audio interface a printer interface and an unchangeable key encryption unit .

The unchangeable key encryption unit has an unchangeable key encryption unit for video an unchangeable key encryption unit for audio and an unchangeable key encryption unit for print . The unchangeable key encryption units for video audio and print may be arranged in a single unit if it is available for sufficient encryption capacity.

The decryption unit and the re encryption unit of the decryption encryption unit are connected to the system bus of the computer. Further the video interface the audio interface and the printer interface are connected to the decryption unit and the unchangeable key encryption unit for video the unchangeable key encryption unit for audio and the unchangeable key encryption unit for print are connected to these interfaces.

An encrypted digital video display unit an encrypted digital audio player and an encrypted digital data printer arranged outside the computer are connected respectively to the unchangeable key encryption unit for video the unchangeable key encryption unit for audio and the unchangeable key encryption unit for print .

The above arrangement can be easily realized by designing the copyright management apparatus as a sub computer arrangement having a CPU and a system bus.

The encrypted data display unit has an unchangeable key decryption unit connected to the unchangeable key encryption unit for video a D A converter connected to the unchangeable key decryption unit and a display unit connected to the D A converter .

The encrypted audio data player has an unchangeable key decryption unit connected to the unchangeable key encryption unit for audio a D A converter connected to the unchangeable key decryption unit and a speaker connected to the D A converter .

The encrypted data printer has an unchangeable key decryption unit connected to the unchangeable key encryption unit for print and a printer connected to the unchangeable key decryption unit .

Needless to say the encrypted data display unit the encrypted audio data player and the encrypted data printer have other components such as an amplifier.

The encrypted digital data C encrypted using the first changeable key K is supplied to the decryption unit from the system bus and it is decrypted using the first changeable key K 1 1 .

When the decrypted digital data M is stored at the hard disk drive or copied at the flexible disk drive or transferred via the modem it is re encrypted using the second changeable key K by the encryption unit 

When the decrypted digital data M is outputted to the encrypted data display unit the encrypted audio data player or the encrypted data printer the decrypted digital data M is arranged to digital data Md Ma and Mp to be provided to the display unit the speaker and the printer respectively at the video interface the audio interface and the printer interface in the copyright management apparatus . Then these digital data are encrypted using the unchangeable key K by the unchangeable key encryption unit for video the unchangeable key encryption unit for audio and the unchangeable key encryption unit for print 0 0 0 0 0 0 and the encrypted display signal Cd the encrypted audio signal Ca and the encrypted print signal Cp are outputted.

The encrypted display signal Cd is imputted to the encrypted data display unit from the unchangeable key encryption unit for video and it is decrypted using the unchangeable key K at the unchangeable key decryption unit 0 0 . The decrypted display signal Md is converted to a displayable analog signal at the D A converter and is displayed on the display unit .

If the display unit is a digital display unit which can display the digital data as it is the D A converter is unnecessary.

The encrypted audio signal Ca is inputted to the encrypted audio data player from the unchangeable key encryption unit and it is decrypted using the unchangeable key K by the unchangeable key decryption unit 0 0 . The decrypted audio signal Ma is converted to a playable analog signal at the D A converter and is played at the speaker .

The encrypted print signal Cp is inputted to the encrypted data printer from the unchangeable key encryption unit and it is decrypted using the unchangeable key K 0 0 . The decrypted print signal Mp is printed by the printer .

When this copyright management apparatus is used no decrypted data is present outside the copyright management apparatus .

As aformentioned non encrypted digital data is also present in addition to the decrypted digital data in the computer.

In order to process the non encrypted digital data and the decryption data by distinguishing between them it is necessary to provide a video interface an audio interface and a printer interface and this would make the system more complicated and costly. To avoid such situation it may be disigned in a manner that the non encrypted digital data is processed at the video interface the audio interface and the printer interface of the copyright management apparatus .

A secret key cryptosystem is often used as a cryptosystem for encrypting digital data. The most popular DES Data Encryption Standard in the secret key cryptosystem carries out encryption decryption per 64 bit block unit of data. It is a typical block cipher method in the secret key cryptosystem and has been widely adopted. Using this encryption decryption per block processing allows the realization of a more high speed encryption decryption processing.

In doing so a plurality of encryption units and decryption units are provided in the encryption decryption unit. It allows these plurality of encryption units and decryption units to be in order allocated the encryption decryption processings of data blocks to be carried out. And then encryption decryption processing results thus obtained are synthesized.

Further it brings a supplemental effect that it is possible to use a respective crypt key for each data block and also to adopt a respective cryptosystem for each data block. Then more high security for digital data is possible.

