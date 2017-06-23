---

title: Print control apparatus, print control method, and program for implementing the method
abstract: A print control apparatus that can improve the performance and quality of a printer driver and a Win32 application and can improve usability for users. A Win32 application that operates on the print control apparatus handles print settings as a print ticket in XML format, and a printer driver that operates on the apparatus manages print settings as a DEVMODE structure in binary format. A conversion process between the print ticket and the DEVMODE structure is carried out in a submodule. The submodule constructs a public portion of the DEVMODE structure based on the print ticket and incorporates the print ticket into a free space in a private portion of the DEVMODE structure. Further, the submodule extracts the print ticket incorporated in the DEVMODE private portion.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07884952&OS=07884952&RS=07884952
owner: Canon Kabushiki Kaisha
number: 07884952
owner_city: 
owner_country: JP
publication_date: 20060403
---
The present invention relates to a print control apparatus a print control method and a program for implementing the method and more particularly to a print control apparatus on which operate an application that handles print settings as a print ticket in XML format and a printer driver that manages the print settings as a print settings structure in binary format a print control method applied to the print control apparatus and a program for causing a computer to execute the print control method.

In a printing environment in the Microsoft Windows registered trademark OS operating system developed by Microsoft Inc. a memory block called a DEVMODE structure used by Win32 applications serves an important role as print settings designating data. DEVMODE is the structure of designation information used when actually instructing a printer to carry out printing. In the Windows OS DEVMODE provided by the OS stores the content of setting entered on the properties of a printer driver. DEVMODE is referred to by the printer driver that has been handed print data when generating print instructions to be transmitted to the printer.

The DEVMODE structure is composed of a memory region that stores information relating to device initialization and a printer environment and is characterized by being composed of two regions a public portion whose specification is made public and a private portion whose specification is not made public and can be accessed by the printer driver only. Normally only extremely basic information such as sheet type sheet orientation resolution and the like is written as members in the public portion of the DEVMODE structure with the remaining majority of the information being written as members in the private portion .

The dmSpecVersion member specifies the version number of the initialization data specification on which the DEVMODE structure is based.

The dmDriverVersion member specifies the printer driver version number assigned by the developer of the printer driver.

The dmSize member specifies the size in bytes of the DEVMODE structure not including a dmDriverData member device specific information .

The dmDriverExtra member contains the number of bytes of private driver data that follow the DEVMODE structure.

The dmFields member specifies members that have been initialized out of the remaining members of the DEVMODE structure.

The dmScale member specifies the factor by which the printed output is to be scaled when scaling is carried out.

The dmCopies member specifies the number of copies printed if the device supports multiple page copies.

The dmDuplex member specifies duplex or double sided printing for printers capable of double sided printing.

The dmCollate member specifies whether collation i.e. sorting into page order should be used when printing multiple copies.

The dmDisplayFrequency member specifies the frequency in hertz of the display device in a particular mode.

In this way the public portion of the DEVMODE structure is strictly defined by Microsoft as a header file written in C language. On the other hand the private portion of the DEVMODE structure that is independently defined by a printer driver developer continues immediately after the public portion in the DEVMODE structure and has a size designated by the dmDriverExtra member.

In 2004 the hardware engineering conference WinHEC 2004 was held by Microsoft in Seattle USA. At the conference it was announced that XML based print settings designating data called a print ticket also referred to in general terms as a job ticket would be used in Microsoft s next generation printing system.

DEVMODE which is comprised of conventional print settings designating data is written as a data structure. Since the specification of the private portion that occupies the majority of DEVMODE can be freely decided by respective printer vendors the content of the private portion differs between vendors and is not made public. Also since data of DEVMODE is binary data users cannot understand the settings even if they refer to the content of DEVMODE. The private portion of DEVMODE is characterized by being accessible only to a printer driver and in that a Win32 application including an API Application Programming Interface that is independent of the printer driver can use the data of DEVMODE for example data related to appliance specific settings that is normally written in the private portion of DEVMODE such a stapling position and a face up down setting for the discharged sheets by communicating with the printer driver using the independent API. A technique by which an application acquires the data of DEVMODE from a printer driver is disclosed in Japanese Laid Open Patent Publication Kokai No. 2003 091387 for example.

On the other hand a print ticket that is comprised of print settings designating data with the new format has the following five characteristics i the ticket is written in XML Extensible Markup Language ii the specification of the ticket is made public iii the ticket is written in text format i.e. readable by the user iv the ticket cannot be directly accessed by a printer driver and v the ticket can be used from a WinFX application with a new format API.

As described above although it is a large step forward for a WinFX application to be able to use a print ticket this only applies to an application layer and the situation is greatly different on a driver layer. This will now be described with reference to .

In a Win32 application on the application layer communicates using DEVMODE with a printer driver via a Win32 API on the OS layer.

On the other hand a process by which a WinFX application on the application layer communicates using print tickets with the printer driver on the driver layer via a WinFX API on the OS layer is quite complex. That is according to the Microsoft specification input and output for the printer driver are limited to DEVMODE. This means that to make the printer driver compatible with print tickets it is necessary to provide the driver layer with a submodule for converting between print tickets and DEVMODE. Due to the functioning of the submodule even though the printer driver is able to handle only DEVMODE it is possible to have communication carried out between the printer driver and the WinFX application using in effect print tickets.

As shown in to maintain compatibility with the specification of the conventional Win32 application as before the printer driver needs to handle DEVMODE comprised of the print settings designating data that is described in non public binary format. Since the exchanging of print settings with the Win32 application is carried out using conventional DEVMODE the printer driver can handle the settings without conversion. However to exchange print settings with the WinFX application a conversion process referred to hereinafter as a ticket cycle between a print ticket and DEVMODE has to be frequently carried out. The ticket cycle has a problem that will now be described with reference to .

For this reason if the ability of a print ticket to express print settings is lower than the ability of DEVMODE to express such settings there will be a problem in that part of the information in the DEVMODE print settings designating data will be lost when the DEVMODE of the print settings made via the printer driver UI is converted T in to a print ticket to be passed over to the WinFX application.

To prevent data from being lost in this way a method that incorporates DEVMODE into the print ticket is conceivable.

However preventing the loss of data by incorporating DEVMODE in the print ticket in this way is based on a premise of DEVMODE having a greater ability to express print setting designations than the print ticket. When the print ticket has a greater ability to express print setting designations than DEVMODE it is not possible to prevent data from being lost.

Also as described above it is still necessary for the printer driver to handle the DEVMODE structure in order to maintain compatibility with the specification of conventional Win32 applications. For this reason there have been a number of problems that inconvenience users such as i the ticket cycle is complex and the processing speed is slow ii there is an increased load for data management since it is necessary to manage both the print ticket and DEVMODE iii in spite of the print ticket being based on XML desired tags cannot be added easily and iv since the size of DEVMODE is decided at a fixed value during initialization content cannot be added later to DEVMODE.

Also conventional Win32 applications are not able to access and directly read and write the private portion of the DEVMODE structure. Thus as shown in a printer driver accesses a DEVMODE private portion via a driver expansion interface I F that is uniquely designed for the printer driver . shows the relationship between a Win32 application and the driver expansion interface of the printer driver and the relationship between the driver expansion interface and the DEVMODE private portion .

By using the driver expansion interface the Win32 application can access and read and write the DEVMODE private portion and as a result the Win32 application can set original functions supported by the printer driver for example a stapling function . The driver expansion interface used by the Win32 application is implemented in the printer driver according to different methods by respective developers and therefore does not have general purpose applicability in other words the interface is incompatible with other drivers . Since the method of using the driver expansion interface will differ if the type of printer driver changes components of the Win32 application become extremely complex thereby increasing the time and effort required by application development.

On the other hand as shown in a WinFX application can directly access a print ticket and read and write the print ticket directly without performing access via a print driver. is a diagram showing the relationship between the WinFX application and the print ticket .

In this way since the WinFX application can directly access the print ticket components of the WinFX application become extremely simple.

However the conventional Win32 application described above cannot handle the print ticket and can only use the DEVMODE private portion . In this case it is necessary to depend on the driver expansion interface that is uniquely designed for the printer driver which has increased the time and effort required to develop Win32 applications.

It is an object of the present invention to provide a print control apparatus a print control method and a program for implementing the method that can improve the performance and quality of a printer driver and a Win32 application and can thereby improve usability for users.

To attain the above object in a first aspect of the present invention there is provided a print control apparatus on which operate an application that handles print settings as a print ticket in XML format and a printer driver that manages print settings as a print settings structure in binary format the print control apparatus comprising a constructing device that constructs a public data portion of the print settings structure in binary format based on the print ticket in XML format an incorporating device that incorporates the print ticket in XML format into a non public data portion of the print settings structure in binary format and an extracting device that extracts the print ticket in XML format incorporated in the non public data portion of the print settings structure in binary format.

Preferably the incorporating device includes an acquiring device that acquires a size of a free space in a memory region for storing the non public data portion of the print settings structure in binary format a first comparing device that compares the size of the free space acquired by the acquiring device and a size of the print ticket in XML format and a compressing device operable when a comparison result of the first comparing device is that the size of the free space is smaller than the size of the print ticket in XML format to compress the print ticket in XML format.

More preferably the incorporating device includes a second comparing device that compares the size of the free space acquired by the acquiring device and a size of the print ticket in XML format compressed by the compressing device and a first storage device operable when a comparison result of the second comparing device is that the size of the compressed print ticket in XML format is not greater than the size of the free space to store the compressed print ticket in XML format in the free space in the memory region for storing the non public data portion of the print settings structure in binary format.

Alternatively the incorporating device includes a second storage device operable when a comparison result of the first comparing device is that the size of the free space is not less than the size of the print ticket in XML format to store the print ticket in XML format in the free space in the memory region for storing the non public data portion of the print settings structure in binary format.

Preferably the incorporating device includes a canceling device operable when a comparison result of the second comparing device is that the size of the compressed print ticket in XML format is larger than the size of the free space to cancel storage of the compressed print ticket in XML format in the free space in the memory region for storing the non public data portion of the print settings structure in binary format.

Preferably the extracting device includes a determining device that determines whether the print ticket in XML format incorporated in the free space in the memory region for storing the non public data portion of the print settings structure in binary format is compressed and a decompression device operable when the determining device has determined that the print ticket in XML format is compressed to decompress the compressed print ticket in XML format.

Preferably the print control apparatus further comprises a deciding device that decides which data is to be prioritized out of the print ticket in XML format and the public data portion of the print settings structure in binary format a determining device operable when the deciding device has decided that the print ticket in XML format is to be prioritized to determine whether a content of the print ticket in XML format differs to a content of the public data portion of the print settings structure in binary format and a correcting device operable when the determining device has determined that the content of the print ticket in XML format differs from the content of the public data portion of the print settings structure in binary format to correct the print ticket in XML format based on the content of the public data portion of the print settings structure in binary format.

To attain the above object in a second aspect of the present invention there is provided a print control method applied to a print control apparatus on which operate an application that handles print settings as a print ticket in XML format and a printer driver that manages print settings as a print settings structure in binary format the print control method comprising a constructing step of constructing a public data portion of the print settings structure in binary format based on the print ticket in XML format an incorporating step of incorporating the print ticket in XML format into a non public data portion of the print settings structure in binary format and an extracting step of extracting the print ticket in XML format incorporated in the non public data portion of the print settings structure in binary format.

Preferably the incorporating step includes an acquiring step of acquiring a size of a free space in a memory region for storing the non public data portion of the print settings structure in binary format a first comparing step of comparing the size of the free space acquired by the acquiring step and a size of the print ticket in XML format and a compressing step of compressing the print ticket in XML format when a comparison result of the first comparing step is that the size of the free space is smaller than the size of the print ticket in XML format.

More preferably the incorporating step includes a second comparing step of comparing the size of the free space acquired by the acquiring step and a size of the print ticket in XML format compressed by the compressing step and a first storage step of storing the compressed print ticket in XML format in the free space in the memory region for storing the non public data portion of the print settings structure in binary format when a comparison result of the second comparing step is that the size of the compressed print ticket in XML format is not greater than the size of the free space.

Alternatively the incorporating step includes a second storage step of storing the print ticket in XML format in the free space in the memory region for storing the non public data portion of the print settings structure in binary format when a comparison result of the first comparing step is that the size of the free space is not less than the size of the print ticket in XML format.

Preferably the incorporating step includes a canceling step of canceling storage of the compressed print ticket in XML format in the free space in the memory region for storing the non public data portion of the print settings structure in binary format when a comparison result of the second comparing step is that the size of the compressed print ticket in XML format is larger than the size of the free space.

Preferably the extracting step includes a determining step of determining whether the print ticket in XML format incorporated in the free space in the memory region for storing the non public data portion of the print settings structure in binary format is compressed and a decompression step of decompressing the compressed print ticket in XML format when the determining step has determined that the print ticket in XML format is compressed.

Preferably the print control method further comprises a deciding step of deciding which data is to be prioritized out of the print ticket in XML format and the public data portion of the print settings structure in binary format a determining step of determining whether a content of the print ticket in XML format differs to a content of the public data portion of the print settings structure in binary format when the deciding step has decided that the print ticket in XML format is to be prioritized and a correcting step of correcting the print ticket in XML format based on the content of public data portion of the print settings structure in binary format when the determining step has determined that the print ticket in XML format differs from the content of the public data portion of the print settings structure in binary format.

To attain the above object in a third aspect of the present invention there is provided a program for causing a computer to implement a print control method applied to a print control apparatus on which operate an application that handles print settings as a print ticket in XML format and a printer driver that manages print settings as a print settings structure in binary format the program comprising a constructing module for constructing a public data portion of the print settings structure in binary format based on the print ticket in XML format an incorporating module for incorporating the print ticket in XML format into a non public data portion of the print settings structure in binary format and an extracting module for extracting the print ticket in XML format incorporated in the non public data portion of the print settings structure in binary format.

According to the present invention there is no inclusive relationship between a print ticket in XML format and a print settings structure in binary format and therefore even if a conversion process ticket cycle is executed between the print ticket and the print settings structure no information is lost. Since the ticket cycle becomes extremely simple the processing speed is increased. As a result for example high speed printing becomes possible using a print ticket even for Win32 based applications.

Thus it is possible to improve the performance and quality of a printer driver and a Win32 application and thereby improve usability for users.

The above and other objects features and advantages of the invention will become more apparent from the following detailed description taken in conjunction with the accompanying with drawings.

The present invention will now be described in detail with reference to the drawings showing preferred embodiments thereof.

In reference numeral designates a host computer equipped with a CPU a ROM and an external memory . The CPU processes documents including ones containing graphics images text tables including spreadsheets in a mixed manner based on a document processing program or the like stored in a program ROM that constructs the ROM or in the external memory . The CPU also carries out overall control of various devices connected to a system bus .

An operating system program hereinafter simply OS or the like that is a control program of the CPU is stored in the program ROM of the ROM or in the external memory . Font data or the like used when carrying out the document processing mentioned above is stored in a font ROM that constructs the ROM or in the external memory . Various data used when carrying out the document processing is stored in a data ROM that constructs the ROM or in the external memory .

The host computer is also comprised of a RAM a keyboard controller KBC a CRT controller CRTC a disk controller DKC a printer controller PRTC a keyboard KB and a CRT display CRT .

The RAM functions as a main memory a work area and the like of the CPU . The keyboard controller controls signal inputs from the keyboard or a pointing device not shown. The CRT controller controls display of the CRT display . The disk controller controls access to the external memory . The external memory is a hard disk HD a floppy registered trademark disk FD or the like that stores a boot program various applications font data user files editing files a printer control command generating program hereinafter printer driver and the like.

The printer controller is connected to a printer via a predetermined two way interface and executes a communication control process to communicate with the printer .

It should be noted that the CPU rasterizes outline fonts onto a display information RAM provided e.g. on the RAM for example to enable WYSIWYG What You See Is What You Get on the CRT display .

The CPU opens a variety of registered windows in response to commands designated by a mouse cursor or the like displayed on the CRT display and executes various data processing. When the user carries out printing a window relating to print settings is opened so that settings of a print processing method including settings of the printer and a selection of print mode can be made to the printer driver.

The printer is comprised of a CPU a ROM and an external memory . Based on a print control program stored in a program ROM that constructs the ROM or the external memory the CPU outputs an image signal as output information to a print section printer engine connected to a system bus .

A control program and the like of the CPU are also stored in the program ROM of the ROM . Font data and the like used when generating the output information mentioned above are stored in a font ROM that constructs the ROM and information and the like used at the host computer when the printer has no external memory such as a hard disk HD are stored in a data ROM that constructs the ROM .

In addition the CPU of the printer is capable of executing a communication process for communication with the host computer via an input section so that the host computer can be notified of information and the like inside the printer .

A RAM functions as a main memory a work area and the like of the CPU and is constructed so that the memory capacity can be expanded by an option RAM connected to an expansion port not shown. Note that the RAM is used as an output information expanding region an environment data storage region an NVRAM non volatile RAM and the like.

The external memory is constructed of a hard disk HD an IC card or the like with access to the external memory being controlled by a memory controller MC . The external memory is connected as an option and stores font data an emulation program form data and the like. The printer may be provided with a plurality of external memories that store in addition to the font data optional font data and or programs for interpreting printer control languages of different language systems.

Next a typical example of print data generation by the host computer will be described with reference to .

An application a graphics engine a printer driver and a system spooler appearing in exist as files that are stored in the external memory and are loaded into the RAM and executed by the OS or a module. The application and the printer driver can be added to the HD of the external memory by an FD or a CD ROM or alternatively via a network.

Printing is carried out according to the application using the printer as follows The application and the graphic engine stored in the external memory are loaded into the RAM . The graphic engine is enabled by being loaded into the RAM and produces image output image drawing . The graphics engine loads the printer driver which is provided corresponding to the printer from the external memory into the RAM and the printer driver converts the image outputted from the graphics engine to control commands for the printer . The printer control commands obtained by the conversion are sent to the system spooler loaded into the RAM by the OS and are outputted from the spooler to the printer via the interface .

An application carries out a process that calls a variety of functions APIs provided by an operating system . To implement processing relating to printing the operating system carries out a process that calls a function DDI provided by a printer driver or of the selected printer. As a result printing to the selected printer can be carried out by the application .

At this time print settings designating data is exchanged between the printer driver or the operating system and the application . Such exchanging of the print settings designating data is shown in . Since has already been described description thereof is omitted here.

In the DEVMODE structure according to the present embodiment a print ticket in XML format a tagged format is incorporated in a DEVMODE private portion independently managed by the printer driver. That is although the DEVMODE structure according to the present embodiment has the appearance of a DEVMODE structure in reality a print ticket is itself included in the DEVMODE private portion .

In addition to the print ticket a signature showing a type of the DEVMODE a print ticket priority flag set at valid when a written content of the print ticket has priority over a written content of the DEVMODE public portion and a print ticket compression flag set at valid when the print ticket is compressed are inserted into the DEVMODE private portion .

In the present embodiment by using a DEVMODE structure of the above structure the ticket cycle that occurs in the submodule appearing in is efficiently carried out that is a process that generates the DEVMODE shown in . The detailed processing flow of the ticket cycle will now be described.

First in a step S the submodule receives a print ticket in XML format that has been inputted from a WinFX application via an API on the OS layer.

In a step S the submodule constructs a public portion of the DEVMODE structure hereinafter referred to as DEVMODE public portion based on various print settings in the XML print ticket. Typically since the print ticket has a greater ability to express the print settings than the DEVMODE public portion the processing in the step S is quite simple.

In a step S the submodule acquires a size S of a free space in a memory region used to store the DEVMODE private portion based on data contained in the dmDriverExtra member in the DEVMODE public portion .

In a step S the submodule compares the size S with a size of the print ticket. If the size S is equal to or larger than the size of the print ticket the process proceeds to a step S while if the size S is smaller than the size of the print ticket the process proceeds to a step S.

In the step S the submodule incorporates the print ticket into the free space in the DEVMODE private portion . At this time the submodule sets the signature sets the print ticket priority flag at valid and sets the print ticket compression flag at invalid .

In the step S since all of the data of the print ticket in its original state cannot be incorporated into the DEVMODE private portion the submodule compresses the data of the print ticket.

In a step S the submodule compares the size S with a size of the print ticket after compression in the step S. If the size S is equal to or larger than the size of the compressed print ticket the process proceeds to a step S while if the size S is smaller than the size of the compressed print ticket the process proceeds to a step S.

In the step S the submodule incorporates the compressed print ticket into the free space in the DEVMODE private portion . At this time the submodule sets the signature sets the print ticket priority flag at valid and sets the print ticket compression flag at valid .

In the step S the submodule cancels incorporation of the print ticket in the DEVMODE structure and carries out error handling.

In a step S the submodule refers to the print ticket compression flag and determines whether the print ticket compression flag is set at valid that is whether the print ticket is compressed. If the print ticket compression flag is set at valid the process proceeds to a step S while if the print ticket compression flag is not set at valid the process skips the step S and proceeds to a step S.

In the step S since the print ticket obtained in the step S is compressed the compressed print ticket is decompressed.

In the step S the submodule determines whether the print ticket priority flag is set at valid that is settings in the print ticket has priority over settings in the DEVMODE public portion . If the print ticket priority flag is set at valid the process proceeds to a step S while if the print ticket compression flag is not set at valid the present process is terminated.

In the step S the submodule compares the settings in the print ticket obtained in the step S or the step S with the settings in the DEVMODE public portion . If the print ticket includes information that differs to the settings in the DEVMODE public portion the processing proceeds to a step S while if there is no such information the present process is terminated.

In a step S the submodule corrects the content of the settings of the print ticket obtained in the step S or the step S so as to match the settings in the DEVMODE public portion .

It should be noted that the process shown in that incorporates the print ticket in the DEVMODE structure and the process shown in that extracts the print ticket from the DEVMODE structure which are executed by the printer driver and the submodule are extremely simple. Thus it is easy to have a Win32 application that supports an API for handling the DEVMODE structure an independent API for the private portion to carry out the incorporating process and the extracting process. This will now be described with reference to .

By executing the process shown in that incorporates the print ticket in the DEVMODE structure the Win32 application can incorporate a print ticket in a DEVMODE structure to produce the DEVMODE structure one example of which is shown in in which the print ticket is incorporated. In the same way by executing the process shown in that extracts the print ticket from the DEVMODE structure the Win32 application recognizes that the signature shown in is set in the DEVMODE structure and therefore determines that the DEVMODE structure is a DEVMODE structure in which a print ticket is incorporated. As a result the Win32 application can directly read and write the DEVMODE structure in the same way as the relationship between the WinFX application and the print ticket shown in .

It is to be understood that the object of the present invention may also be accomplished by supplying a system or an apparatus with a storage medium in which a program code of software which realizes the functions of the above described embodiment is stored and causing a computer or CPU or MPU of the system or apparatus to read out and execute the program code stored in the storage medium.

In this case the program code itself read out from the storage medium realizes the functions of the above described embodiment and hence the program code and the storage medium in which the program code is stored constitute the present invention.

Examples of the storage medium for supplying the program code include a floppy registered trademark disk a hard disk a magnetic optical disk an optical disk such as a CD ROM a CD R a CD RW a DVD ROM a DVD RAM a DVD RW and a DVD RW a magnetic tape a nonvolatile memory card and a ROM. Alternatively the program code may be downloaded via a network.

Further it is to be understood that the functions of the above described embodiment may be accomplished not only by executing a program code read out by a computer but also by causing an OS or the like which operates on the computer to perform a part or all of the actual operations based on instructions of the program code.

Further it is to be understood that the functions of the above described embodiment may be accomplished by writing a program code read out from the storage medium into a memory provided on an expansion board inserted into a computer or in an expansion unit connected to the computer and then causing a CPU or the like provided in the expansion board or the expansion unit to perform a part or all of the actual operations based on instructions of the program code.

This application claims the benefit of Japanese Application No. 2005 107919 filed Apr. 4 2005 which is hereby incorporated by reference herein in its entirety.

