---

title: Window positioner/sizer
abstract: Methods and apparatus, including computer program products, for a window positioner/sizer. A computer-implemented method of displaying information on a computer display device includes displaying a first popup window on a primary window, the first popup window comprising controls enabling selective positioning and sizing of the first popup window relative to the primary window.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07836410&OS=07836410&RS=07836410
owner: SAP AG
number: 07836410
owner_city: Walldorf
owner_country: DE
publication_date: 20060106
---
The present invention relates to data processing by digital computer and more particularly to a window positioner sizer.

User interfaces UIs are an integral part of many business enterprise software applications. For example Web Dynpro from SAP AG enables companies to model and design UIs cost effectively and precisely. A Web Dynpro application includes a set of views navigation between the views concepts for managing the views and determining their sequence a context for keeping session data and the business logic of the application.

Within Web Dynpro application popup e.g. internal windows are frequently used to help a user to make decisions about one or more operations that can be preformed on data in a main or primary window. The popup window when open can hide data of interest in the main window. The popup window is not resizable and not movable so the user may have to close the popup window memorize the data of interest from the primary window and then reopen the popup window.

The present invention provides methods and apparatus including computer program products for a window positioner sizer.

In one aspect the invention features a method including displaying a first popup window on a primary window the first popup window including controls enabling selective positioning and sizing of the first popup window relative to the primary window.

In embodiments the controls can include an up position control a down position control a left position control a right position control and a center position control.

The controls can be positioned in a second popup window. The second popup window can be displayed in response to a user selection of a popup manager.

The window positioner sizer enables the movement and re sizing of a popup window that is originally created to be non resizable and non moveable.

The window positioner sizer enables a user to see all the data in the background e.g. main window primary window without having to close and re open the popup window.

The window positioner sizer enables sizing and positioning for a non resizable non movable internal window.

The window positioner sizer is easy to implement e.g. common DC or additional UI element and improves user friendliness of a popup window.

Other features and advantages of the invention are apparent from the following description and from the claims.

As shown in an exemplary computer system includes a processing unit one or more input devices and a display device upon which a user is presented displays. The display device has a video screen upon which displays appear.

The processing unit can include a processor random access memory RAM and read only memory ROM all interconnected by a data bus . Input device controllers also connected to the data bus receive command signals from input devices and forward the command signals in the appropriate format for processing. A video controller connected to the data bus receives video command signals from the data bus and generates the appropriate video signals that are forwarded to the display device so that the desired display is provided on the screen . The system is not limited to a personal computer PC but could include a personal digital assistant PDA a terminal a workstation or other such device.

ROM provides non volatile data storage for various application programs. In the example shown a number of different application programs are stored in ROM . Also stored in ROM is a user interface UI program designed to work in concert with each of the application programs . This is conceptually depicted by the UI program shown as a layer on top of the application programs . With such a design UI program modules common to several application programs need not be duplicated in each of the application programs . In addition such a design may enable a common look and feel to the UI for the different program applications . In other examples the UI program or module is not a common program or module for more than one program application. In still other examples the components described can be combined or separated in various manners and can be stored in various manners such as on various non volatile storage medium.

Programs have program instructions that can be loaded into RAM during operation. Processor then executes the program instructions as required to perform desired program functions.

Also stored in ROM are various data in database . Database includes data needed or generated during operation of the application programs . Although only a single database is shown that serves as a common database for all applications in other examples there can be separate databases for one or more of the applications .

System includes connection to a server and a network interface connected to its data bus . As such system can access server over network to run applications residing on the server . Network can be for example a Local Area Network LAN Wide Area Network WAN or the Internet.

The server includes a network interface a processor RAM and ROM all interconnected by a data bus . The server s network interface provides the connection to network so that client computer systems such as system can access the server . In similar fashion to computer system the server ROM includes various different application programs as well as a common user interface program for the application programs . ROM in this example includes data stored in database although in other implementations separate databases or a separate database server may be required.

A Web Dynpro Application Programming Interface API enables the creation of windows using an IWDWindowManager interface. The IWDWindowManager interface includes createExternalWindow a method that generates a window that contains displays a Web Dynpro Components window with its view hierarchy. An external window which is assigned an URL address opens a new widow that is re sizable and movable.

The IWDWindowManager interface includes createWindow a method that generates a window that contains displays a Web Dynpro Components window with its view hierarchy. Here the window type is internal meaning some clients can display it above the current view assembly and others will replace the view assembly. An internal window is an embedded window that is not re sizable and not movable.

As shown in an exemplary primary window includes an electronic mail email application . Pressing a To button causes generation of a popup window . In this particular example the popup window includes an address book used in conjunction with the To button i.e. address field . It should be noted that the popup window is not movable and not resizable causing it to partially hide information contained in the primary window . More particularly in this example the address book in the popup window is partially obstructing a previously entered address in the To address field of the primary window and the user cannot view that previously entered address. Accordingly the user may have to close the popup window in order to see what the entry in the address filed of primary window .

In other examples if the primary window is a large table there is almost no room to enable a popup window to be positioned that does not obstruct at least part of the large table. If the user has to make an operation using a popup and on the data of the tables the user may have to memorize table values or make a copy of them or close the popup window and reopen the popup window.

Memory includes a window positioner sizer process that overcomes the disadvantages of popup windows obstructing primary windows. Process enables a set of commands for positioning a popup window e.g. up down left right and center . Process enables a set of commands for resizing the popup window e.g. width height or both .

The commands can be implemented for example as an additional feature of Web Dynpro s WDWindow class a UI element for a popup window in the same way a table has a tool bar table that can contain a set of UI Elements such as buttons input fields and so forth. The commands can also be implemented as a common DC.

As shown in process can display controls that enable moving a popup window in an absolute or a relative manner. For example commands enable the user to move the popup window in the following positions top left top center top right or center left center center center right bottom left bottom center and bottom right.

As shown in if moving if the popup window is relative the user can enter the number of pixels desired to move the popup window from previous coordinates.

As shown in a sample of the effect of positioning a popup window top center center right and bottom right is illustrated.

As shown in sizing of the popup window can be done by increasing the width only the height only or both. The sizing can also be absolute relative or a predefined quantity. In one particular example a predefined quantity is 50 or 100 pixels at a time.

As shown in process enables a popup window size to be reduced to allow more visible data for the primary background window.

As shown in process enables a popup window to be enlarged to better see the data within the popup window.

Window positioning sizing controls can be directly incorporated in the popup window as shown in or incorporated within a popup window of the popup window as shown in .

Embodiments of the invention can be implemented in digital electronic circuitry or in computer hardware firmware software or in combinations of them. Embodiments of the invention can be implemented as a computer program product i.e. a computer program tangibly embodied in an information carrier e.g. in a machine readable storage device for execution by or to control the operation of data processing apparatus e.g. a programmable processor a computer or multiple computers. A computer program can be written in any form of programming language including compiled or interpreted languages and it can be deployed in any form including as a stand alone program or as a module component subroutine or other unit suitable for use in a computing environment. A computer program can be deployed to be executed on one computer or on multiple computers at one site or distributed across multiple sites and interconnected by a communication network.

Method steps of embodiments of the invention can be performed by one or more programmable processors executing a computer program to perform functions of the invention by operating on input data and generating output. Method steps can also be performed by and apparatus of the invention can be implemented as special purpose logic circuitry e.g. an FPGA field programmable gate array or an ASIC application specific integrated circuit .

Processors suitable for the execution of a computer program include by way of example both general and special purpose microprocessors and any one or more processors of any kind of digital computer. Generally a processor will receive instructions and data from a read only memory or a random access memory or both. The essential elements of a computer are a processor for executing instructions and one or more memory devices for storing instructions and data. Generally a computer will also include or be operatively coupled to receive data from or transfer data to or both one or more mass storage devices for storing data e.g. magnetic magneto optical disks or optical disks. Information carriers suitable for embodying computer program instructions and data include all forms of non volatile memory including by way of example semiconductor memory devices e.g. EPROM EEPROM and flash memory devices magnetic disks e.g. internal hard disks or removable disks magneto optical disks and CD ROM and DVD ROM disks. The processor and the memory can be supplemented by or incorporated in special purpose logic circuitry.

It is to be understood that the foregoing description is intended to illustrate and not to limit the scope of the invention which is defined by the scope of the appended claims. Other embodiments are within the scope of the following claims.

