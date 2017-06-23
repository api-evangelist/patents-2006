---

title: Information processing apparatus for setting a printing attribute to a hot folder
abstract: According to an information processing method of generating print data to be processed by a printing apparatus, when data is stored in a storage area, the data is transmitted to the printing apparatus by applying a printing attribute corresponding to the storage area. The printing attribute corresponding to the storage area is set, and status information representing the status of the printing apparatus is obtained. The printing attribute is changed to adapt the printing attribute to the obtained status information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08681354&OS=08681354&RS=08681354
owner: Canon Kabushiki Kaisha
number: 08681354
owner_city: Tokyo
owner_country: JP
publication_date: 20061006
---
A printer driver and a hot folder are used for inputting a print job to a printing apparatus. In the use of the hot folder the user creates a hot folder on the desktop of a host computer or the like. At this time the user sets desired printing attributes. When the user drags and drops a file to be printed into the folder the hot folder executes print processing in accordance with the printing attributes set in advance. The hot folder can permanently use printing attributes set once and thus can repeat printing at the same settings e.g. Japanese Patent Laid Open No. 2005 115568 .

Even the printer driver can perform processing similar to that using the hot folder. For example the user sets printing attributes on the printer driver and saves the printing attribute settings as favorite settings . In printing the printer driver reads out the printing attributes and can print with the printing attributes set by the user.

Inputting a print job using the printer driver or hot folder allows saving printing attributes set once and repetitively executing jobs at the same settings.

However the above mentioned prior art cannot cope with a change of the device status because printing attributes are fixed. Compared to a case of setting printing attributes for a hot folder or the like the prior art cannot flexibly cope with a change of the paper type prepared in the paper feed cassette replacement demounting of a finisher or a change of resources in the ICC profile or the like.

The present invention has been made to overcome the conventional drawbacks and has as its object to provide an information processing technique capable of flexibly coping with a change of the device status addition change of settings demounting of a device or the like which is impossible by the conventional hot folder technique and driver technique.

In order to achieve the above object an information processing apparatus and information processing method according to the present invention mainly have the following arrangements.

According to the present invention the foregoing object is attained by providing an information processing apparatus which generates print data to be processed by a printing apparatus from input data in accordance with a set printing attribute comprising 

a first transmission unit which when storing data in a storage area transmits the data to the printing apparatus by applying a printing attribute corresponding to the storage area 

an obtaining unit which obtains status information representing a status of the printing apparatus and

a change unit which changes the printing attribute so as to adapt the printing attribute corresponding to the storage area to the status information obtained by the obtaining unit.

According to another aspect of the present invention the foregoing object is attained by providing an information processing method of generating print data to be processed by a printing apparatus from input data in accordance with a set printing attribute comprising 

a first transmission step of when storing data in a storage area transmitting the data to the printing apparatus by applying a printing attribute corresponding to the storage area 

an obtaining step of obtaining status information representing a status of the printing apparatus and

a change step of changing the printing attribute so as to adapt the printing attribute corresponding to the storage area to the status information obtained in the obtaining step.

The present invention can dynamically treat a change of the device status and a change of resources prevent an output result not intended by the user and achieve information processing for efficient printing.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings .

An example of a printing system using a hot folder will be explained. is a block diagram schematically showing the configuration of a system which prints using a hot folder. Reference numeral denotes an information processing apparatus host computer and and network printers to be simply referred to as printers hereinafter connectable to a network . The printers and can receive a print job from the host computer and print. The printers and connect to post processing apparatuses finishers and respectively. An operating system is installed in the host computer and an application for creating a hot folder is installed on the operating system.

The information processing apparatus host computer having an arrangement as shown in generates a device status list and executes information processing for a device status list management table and the like which will be described later. In an application runs in the host computer . The host computer comprises a CPU which executes an operating system OS printer driver application program hot folder application and the like. A ROM or hard disk HD stores these programs or a flexible disk FD supplies them.

The CPU comprehensively controls devices connected to a system bus . A RAM functions as a main memory work area and the like for the CPU . A keyboard controller KBC controls an instruction input from a keyboard KB a pointing device not shown or the like. A CRT controller CRTC controls display of a CRT display CRT . A disk controller DKC controls access to the hard disk HD and flexible disk FD . These disk media store a boot program operating system edit file user file application program network control program and the like.

A network interface I F bidirectionally exchanges data with a network device and the like via the network . As the network a communication medium such as the LAN or Internet is available. In the following description the hardware entity which executes processing is the CPU and the software entity is an application program installed in the hard disk HD unless otherwise specified.

An operation when the user prints out the document file by bookbinding printing will be explained with reference to .

The user drags the document file to be printed with the mouse and superposes it on the hot folder having the bookbinding printing attribute. After superposition the user releases the mouse button to drop the document file in the hot folder . At this time the hot folder application transmits the dropped file to the network printers and together with printing attribute information. The network printers and print at preset printing attributes on the basis of the transmitted printing attribute information and document file .

Note that the hot folder is an executable application but may be a service to be registered in an operating system. The hot folder described below saves printing attributes set by the user as a job ticket of the XML format.

The network printers and can also interpret a job ticket as a printing attribute. The hot folder application comprises a UI controller which controls settings such as printing attributes and a job ticket controller which generates and saves a job ticket of printing attributes set by the user through the UI controller . The hot folder application comprises a job ticket management table which associates a job ticket hot folder and printer with each other. The hot folder application further comprises a job generation transmission controller which generates a job on the basis of a file dropped in a hot folder and a job ticket associated with the folder and transmits the job to the printer.

A job ticket save area of the operating system saves via the API Application Programming Interface of the operating system a job ticket generated by the job ticket controller .

Reference numeral denotes a network interface of the host computer that connects to a network interface of the printer via a communication medium. For example the network interface transmits a print job and exchanges information representing a printer status. The printer saves profile information used for color conversion processing screen data for performing halftone processing information on paper currently set in the cassette and the like. The printer connects to the finisher and can perform processing such as stapling in discharge.

Procedures to create a hot folder by the user will be explained with reference to . Note that the user changes the page layout setting to 4UP the single double sided setting to double sided and the copy count setting to 10 copies from default settings of printing attributes thereby setting printing attributes.

In step S the user creates a folder at an arbitrary location and gives an easy to understand name to the folder. In general a hot folder conveniently exists on the desktop of a host computer and is created on it. To recognize printing attributes changed from defaults the folder is given a folder name 4UP10copies double sided printing . Needless to say the name is arbitrary. By this procedure a folder 4UP10copies double sided printing is generated on the desktop like the hot folder shown in .

A button is used to open a reference dialog in order to designate a printer in the reference dialog instead of directly inputting a printer to be referred to as a target printer hereinafter designated as the output destination of a file data dropped in a hot folder. Note that a target printer is designated by its IP address 192.168.0.100 but the designation method is arbitrary as far as a printer can be specified.

Reference numeral denotes a setting button for opening a dialog to set the printing attributes of a hot folder and a hot folder setting button for setting the printing attributes of a target hot folder and its target printer in the current status.

Referring back to the created folder is designated as a target folder in step S. Since the folder having the folder name 4UP10copies double sided printing is created on the desktop in step S the user inputs to the input field used for the target folder designation control a path to the desktop for designating the folder. Note that a folder path precedent to the folder name depends on the operating system.

In step S the user sets the printing attributes of the target hot folder. The user presses the printing attribute setting button in order to set the printing attributes. When the user presses the button printing attribute setting dialogs shown in appear.

Printing attributes except for ones shown in will be omitted. In this case the default settings of printing attributes are the output paper size A4 the paper type plain paper the number of copies 10 copies the page layout 4 pages sheet double sided printing and the discharge method staple .

The user presses an OK button to finalize set printing attributes. To discard contents and return to the hot folder dialog in the user presses a cancel button .

The user may refer to the paper information saved in the printer when displaying the pull down menus of the output paper size and paper type . Similarly when setting the discharge method information representing whether the finisher is connected may be obtained from the printer to change the pull down menu of the discharge method in accordance with the information.

When the user clicks the print quality tab a UI as shown in appears. Reference numerals to denote the same parts as those of reference numerals to in . In the print quality tab is selected. Reference numerals to allow various settings associated with the print quality. Reference numeral denotes a scroll control identical to the scroll control in .

The user finalizes settings on the UI window with an OK button . When the user presses a cancel button the UI returns to the hot folder dialog .

The setting items of the setting fields to in the UI window are associated with color conversion and actual print work uses the profile information in the printer . The color mode setting is relevant to the screen data of the printer which is used in printing. In setting from the setting fields to and their pull down menu may be changed by referring to the profile information and screen data .

The user presses the hot folder setting button in the hot folder dialog of to generate a job ticket in the target folder in step S of . Then the job ticket management table is updated together with the target printer information.

The job ticket management table describes a full path as the folder path of a target hot folder a designated IP address as a target printer and only a file name as a job ticket because the directory which stores a job ticket is defined in advance. When the user drops a file into a given folder the hot folder application can use the folder name as a key to know a target printer and corresponding job ticket from the management table.

In step S the hot folder application monitors drop of a file into a hot folder by the user. If the user does not drop any file the process returns to step S to repeat monitoring. If the user drops a file the process advances to step S to search the job ticket management table for a job ticket set for the hot folder and obtain the job ticket. At this time the hot folder application also obtains target printer information. In step S the hot folder application transmits the job to the printer and the process ends. The user can drop arbitrary application data into a hot folder as far as the hot folder application can interpret the data. Unlike processing by the driver no print event need be activated via an application corresponding to a file format.

The first embodiment of the present invention will be described with reference to the accompanying drawings. The configuration of a system having an information processing apparatus and printer and the display and operation of a hot folder are the same as those in .

The hot folder application comprises a job ticket management table UI controller job ticket controller job generation transmission controller device status list management table and device status list controller .

The host computer can communicate with a printer and the printer connects to a finisher post processing apparatus . The host computer to finisher can perform the same processes as those of the host computer and the hot folder application to finisher in .

As an arrangement different from the device status list management table device status list controller and device status list save area are added in . In setting by the UI controller the device status list controller generates a device status list and the device status list management table manages the device status list by making the folder path of a hot folder and a designated target printer correspond to each other. The device status list controller saves the device status list in the device status list save area of the OS via the API of the OS .

The host computer which generates print data to be processed by the printer from input data in accordance with set printing attributes job ticket comprises the following arrangement. The host computer comprises a transmission unit which when storing data in a predetermined storage area transmits data to the printer by applying printing attributes corresponding to the predetermined storage area.

The host computer comprises a setting unit which sets printing attributes corresponding to a predetermined storage area and an obtaining unit which obtains status information information containing at least one of pieces of information on addition change of settings in the printer and demounting of a device representing the status of the printer .

The host computer comprises a change unit which changes printing attributes so as to adapt printing attributes corresponding to a predetermined storage area to status information obtained by the obtaining unit.

Under the control of a CPU the respective controllers of the hot folder application can execute the processes of the transmission unit setting unit obtaining unit and change unit which form the host computer .

Procedures to create a hot folder in the first embodiment of the present invention will be explained with reference to . Steps S to S are the same as the above described steps S to S in and a description thereof will be omitted.

After a hot folder is set in step S the process advances to step S in parallel with step S. The hot folder application obtains status information of a device printer in which connects to the host computer. The obtained device status information is relevant to all printing attributes settable by the user via the hot folder application . Hence the device information contains not only profile information and screen data held in the device printer but also finisher information on the finisher connected to the device printer . When the information processing apparatus holds profile information the device information also contains this information.

In step S the hot folder application generates a device status list and device status list management table.

The user designates the folder path of a target folder a target printer print settings and the like in a dialog displayed when the hot folder application starts up . A job ticket generated by setting printing attributes has the same structure as that in . Similar to the job ticket management table manages the job ticket the folder path of the designated target folder and the target printer.

A device status list based on device status information obtained in step S of will be explained. Print settings of the hot folder application in will be exemplified. Device information is relevant to an output paper size paper type and discharge method on a page setup tab and print quality tab in . Device information is relevant to an RGB source profile CMYK simulation profile output profile and halftone on a page setup tab and print quality tab in .

The discharge method setting represents that the printer has two cassettes cassette storing A4 plain paper A4 normal and cassette storing A3 glossy paper A3 photo paper . A finisher post processing apparatus connected to the device printer has a name Finisher A .

In the first embodiment the device status list describes device information of the printer and connected finisher together. Alternatively the device status list may describe the printer and finisher discriminately as independent devices.

The device status list controller generates the device status list management table which makes a generated device status list the folder path of a target hot folder and a target printer correspond to each other. The hot folder application holds the device status list management table. is a table illustrating the structure of a device status list management table . The device status list management table makes a folder path of a target hot folder address information e.g. IP address for specifying a target printer as an output destination and a device status list correspond to each other.

In the device status list management table describes a full path as the folder path of a target hot folder a designated IP address as a target printer and only a file name as a device status list because the directory which stores a device status list is defined in advance.

When the user drops a file into a given folder the hot folder application can use the folder name as a key to know a target printer and corresponding device status list from the device status list management table.

Hot folder processing procedures according to the first embodiment of the present invention will be explained with reference to the flowchart of . The job ticket controller device status list controller and UI controller execute this flowchart under comprehensive control of the hot folder application .

In step S the hot folder application determines whether the user inputs a file data into a hot folder.

If the user does not input any file data in step S NO in S the process waits for input of a file data .

If the user inputs a file data YES in S the process advances to step S to search the job ticket management table see and obtain a job ticket set for a corresponding hot folder. For example when a hot folder is designated as represented by the job ticket management table in FIG. a corresponding job ticket can be specified.

In step S the hot folder application obtains status information set for the current device as described with reference to B and .

In step S the hot folder application searches the device status list management table to obtain the device status list of a corresponding hot folder. When the device status list management table is not updated the obtained device status list is one in creating a hot folder. When the device status list management table is updated the latest updated device status list is obtained.

In step S the device status list controller compares the current device status information S with the device status list of the corresponding hot folder S .

If the device status list obtained in step S matches the current device status information in step S the hot folder application determines that the device status has not changed. If the device status has not changed NO in S the process advances to step S to transmit the file data input to the hot folder to the designated target printer in .

If the hot folder application determines in step S that the device status list obtained in step S does not match the current device status information it determines that the device status has changed.

If the device status has changed YES in S the process advances to step S and the hot folder application displays on a CRT a user interface UI which prompts the user to change printing attributes.

If the user does not change the printing attributes from the UI NO in S the process advances to step S to transmit the job without changing the printing attributes S .

If the user changes the printing attributes from the UI in step S the process advances to steps S and S.

In step S the job ticket controller creates a job ticket again on the basis of information on the printing attributes changed by the user. In step S the hot folder application transmits the job to the designated target printer.

In step S the job ticket controller saves the re created job ticket in the job ticket management table to update the job ticket management table S . In the next job input the job ticket management table provides the updated job ticket.

In step S the device status list controller creates a device status list again on the basis of information on the printing attributes changed by the user to update information in the device status list management table S . The updated device status list management table is based on the printing attributes changed in step S and corresponds to the re created job ticket.

For example when the user subsequently inputs a file data into the hot folder the current device status information and device status list information match each other. The hot folder application can successively transmit jobs to a printer designated as a target printer.

Display of the UI which prompts the user to change printing attributes in step S will be described. shows a UI for inputting page settings when creating a hot folder. shows a UI for setting the print quality when creating a hot folder. Printing attributes are set on the basis of information input to these UIs. In an initial state device information shown in is set as information representing a device status in creating a hot folder. After that the device status changes into one as shown in .

The device status list controller compares items between and determines whether items of the device status have changed. Changed items between are three denoted by reference numerals to . More specifically compared to items in creating a hot folder the simulation profile additionally contains EuroScale . Cassette changes from A3 glossy paper to A3 plain paper A3 normal . Since the finisher is demounted the finisher changes to none deleted .

In an output paper size is set to A3 and a paper type is set to glossy paper . A discharge method designates staple . In a simulation profile is JapanColor .

The UI controller performs display control to display on the CRT a UI for setting the output paper size paper type discharge method and simulation profile in accordance with the determination result by the device status list controller .

Even when the printing attributes of a hot folder become inconsistent with the current device status information upon a change of the current device status information the first embodiment can make the printing attributes consistent with the current device status information by updating the printing attributes in accordance with the change of the status information and creating a device status list again.

The first embodiment can provide an information processing technique capable of dynamically coping with a change of the device status addition change of settings demounting of a device or the like .

The first embodiment can dynamically cope with a change of the device status and a change of resources prevent an output result not intended by the user and achieve information processing for efficient printing.

The second embodiment will describe processing to create a hot folder not by a hot folder application but by a printer driver.

In step S the printer driver in a host computer starts up. In response to the startup of the printer driver a CRT displays a UI for creating a hot folder.

In step S the printer driver determines whether the user presses a hot folder creation button not shown from the UI displayed in response to the startup of the printer driver.

If the user does not press the hot folder creation button NO in S the process advances to step S to print in accordance with the settings of the printer driver S .

If the printer driver determines in step S that the user presses the hot folder creation button YES in S the process advances to step S and the printer driver activates a hot folder setting window S . The activated hot folder setting window is e.g. the dialog shown in . This window allows the user to designate the folder path of a target folder set as a hot folder and a target printer.

In step S the printer driver creates a hot folder in accordance with contents set from the hot folder setting window. A created hot folder and hot folder processing after inputting a job are the same as the contents described in the first embodiment. The printer driver creates a job ticket and a device status list . If the device status has changed a job ticket management table and device status list management table are updated under the control of the printer driver in accordance with the flowchart of .

The printer driver includes a user I F UI driver which displays a user I F UI and saves settings. The printer driver includes a graphic driver which converts a print drawing instruction issued from the application program via the OS into a code interpretable by a printer. The UI driver displays a print setting dialog and property sheet when the application program designates print settings via the OS . Examples of the print setting dialog and property sheet will be omitted.

A printer driver setting save area exists in a save area managed by the OS and saves printing attributes set by the user via the UI driver . The UI driver graphic driver and application program can access the printer driver setting save area via the OS and read printing attributes set by the user.

A communication I F of the host computer and a communication I F of a printer connect to each other via a communication medium such as a network. The graphic driver can transmit print data to the printer via the OS and obtain status information of the printer via the OS .

To communicate with a hot folder the printer driver comprises an external communication controller and export function . Similarly the hot folder comprises an external communication controller and export function and can communicate with the printer driver via them. This arrangement allows the printer driver and hot folder to exchange instructions and information in accordance with specified procedures and data structures.

Processing for a file data input to a hot folder generated by the printer driver is the same as the flowchart of described in the first embodiment and a detailed description thereof will be omitted.

Note that the printer driver may incorporate a job ticket management table and device status list management table to be looked up in the processing of . Alternatively the job ticket management table and device status list management table may be set on the OS as shown in . When the job ticket management table and device status list management table are set on the OS the printer driver can look up these tables via the OS .

If the device status changes the printer driver creates a job ticket and device status list again on the basis of a change of printing attributes corresponding to the change of the device status. The printer driver updates the job ticket management table and device status list management table on the basis of the re created job ticket and device status list.

The second embodiment can provide an information processing technique capable of dynamically coping with a change of the device status addition change of settings demounting of a device or the like using the printer driver as a processing entity.

The second embodiment can dynamically cope with a change of the device status and a change of resources prevent an output result not intended by the user and achieve information processing for efficient printing.

The third embodiment will describe a case of applying the present invention to favorite settings saved as printing attributes designated by the user.

Similar to the arrangement in the printer driver includes a user I F UI driver which displays a user I F UI and saves settings. The printer driver includes a graphic driver which converts a print drawing instruction issued from an application program via an OS into a code interpretable by a printer. Further the printer driver includes a device status list management table . The device status list management table can manage a device status list based on device status information obtained from a printer .

A device status list save area is set on the OS in addition to a printer driver setting save area . The device status list save area saves via the OS a device status list e.g. based on device status information obtained by the printer driver .

The printer driver setting save area saves printing attributes set as favorites by the user from the printer driver . The printer driver can manage to save and update the set printing attributes favorite information via the OS .

The printer driver manages printing attributes favorite information set by the user as attribute information different from information obtained from a device.

In step S the printer driver activates its dialog window. In step S the user sets printing attributes. The printing attributes serve as favorite information set by the user.

In step S the printer driver determines whether the user designates to save the printing attributes favorite information set in step S. If the printer driver determines in step S that the user does not designate to save the printing attributes favorite information NO in S the process advances to step S. If printing is to be executed YES in S the process advances to step S to print.

If the printer driver determines in step S that the user designates to save the printing attributes favorite information YES in S the process advances to step S. The printer driver saves the printing attributes favorite information in the printer driver setting save area via the OS .

In step S the printer driver obtains device information of a device printer . Assume that a communication I F of the host computer and a communication I F of the printer connect to each other via a communication medium such as a network. The printer driver can transmit print data to the printer via the OS . The printer driver can also obtain status information of the printer via the OS .

Referring back to the printer driver generates a device status list and device status list management table in step S. These processes correspond to step S of .

In step S the printer driver determines whether to print. If no printing is to be executed NO in S the process ends. If printing is to be executed YES in S the process advances to step S to print S and then ends.

In step S the printer driver reads out printing attributes favorite information saved in the printer driver setting save area .

In step S the printer driver searches the device status list management table on the basis of the readout printing attributes obtaining a device status list in saving the printing attributes favorite information set by the user. For example when the printing attribute A is read out in the printer driver obtains the corresponding device status list device A  .

In step S the printer driver compares the current device status information with the device status information in saving the favorite information.

If the two pieces of status information match each other in step S the printer driver determines that the device status has not changed. If the device status has not changed NO in S the process advances to step S to print S .

If the printer driver determines in step S that the device status information in saving the favorite information does not match the current device status information it determines that the device status has changed.

If the device status has changed YES in S the process advances to step S. Under display control of the printer driver the CRT displays a user interface UI which prompts the user to change printing attributes

The user sets printing attributes from the printing attribute changing portion using the printing attribute addition to printing attribute deletion and presses an execution button finalizing the set printing attributes.

If the user changes printing attributes favorite information from the printing attribute changing portion YES in S the process advances to step S. The printer driver updates the printing attributes favorite information saved in the printer driver setting save area S . The printer driver reflects the update results in printing attributes saved in the printer driver setting save area . In the next read the updated printing attributes are read out.

If the printer driver determines in step S that the user does not change the printing attributes NO in S the process advances to step S to print S .

If the printer driver updates the printing attributes favorite information saved in the printer driver setting save area in step S the process advances to step S. The printer driver creates again a device status list corresponding to the change of the printing attributes. The printer driver updates the device status list management table on the basis of the re created device status list S .

After the end of processing in step S the process advances to step S to execute print processing which reflects the changed printing attributes S and then ends.

The third embodiment has exemplified favorite information as an example of printing attributes set by the user but the gist of the present invention is not limited to this example. For example the present invention may target information on printing attributes settable by the user separately from status information obtained from a device.

Even when saved printing attributes become inconsistent with the current device status information upon a change of the current device status information the third embodiment can make the printing attributes consistent with the current device status information by updating the printing attributes in accordance with the change of the status information and creating a device status list again.

The third embodiment can provide an information processing technique capable of dynamically coping with a change of the device status e.g. a change of information containing at least one of pieces of information on addition change of settings in the printer and demounting of a device .

The third embodiment can flexibly cope with a change of the device status and a change of resources e.g. a device configuration typified by the image forming program or image forming circuit of a device or an option such as a finisher for a device . The third embodiment can prevent an output result not intended by the user and implement information processing for efficient printing.

The fourth embodiment will describe a case of switching whether or not to compare device statuses when a hot folder receives a job. The fourth embodiment defines dynamic configuration which is processing to compare the current device status with a device status in creating a hot folder by using a device status list described in the first embodiment and when the device status has changed display a UI which prompts the user to change printing attributes.

Processing procedures according to the fourth embodiment will be explained with reference to . S to S are the same processes as those in S to S S and S of and a description thereof will be omitted. After a job ticket set in a hot folder is obtained in S it is determined in S whether dynamic configuration is set. If no dynamic configuration is set the job is transmitted in S. If dynamic configuration is set the current device status information is obtained in S and a device status list in creating a hot folder is obtained in S to perform subsequent processing.

The procedures described in the fourth embodiment are merely an example and the processing can take any form as far as the processing switches whether or not to execute dynamic configuration.

Even when saved printing attributes become inconsistent with the current device status information upon a change of the current device status information the fourth embodiment can make the printing attributes consistent with the current device status information by updating the printing attributes in accordance with the change of the status information and creating a device status list again.

The fourth embodiment can provide an information processing technique capable of dynamically coping with a change of the device status e.g. a change of information containing at least one of pieces of information on addition change of settings in the printer and demounting of a device .

The fourth embodiment can flexibly cope with a change of the device status and a change of resources e.g. a device configuration typified by the image forming program or image forming circuit of a device an option such as a finisher for the device or the like . The fourth embodiment can prevent an output result not intended by the user and implement information processing for efficient printing.

The objects of the present invention are also achieved by supplying a storage medium which records software program codes that implement the functions of the above described embodiments to a system or apparatus. The objects of the present invention are also achieved by reading out and executing the program codes stored in the storage medium by the computer CPU or MPU of the system or apparatus.

In this case the program codes read out from the storage medium implement the functions of the above described embodiments and the storage medium which stores the program codes constitutes the present invention.

The storage medium for supplying the program codes includes e.g. a flexible disk hard disk optical disk magnetooptical disk CD ROM CD R nonvolatile memory card and ROM.

The functions of the above described embodiments are implemented by executing the readout program codes by the computer. Also the functions of the above described embodiments are implemented by performing some or all of actual processes by an OS Operating System or the like running on the computer on the basis of the instructions of the program codes.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2005 299322 filed on Oct. 13 2005 which is hereby incorporated by reference herein in its entirety.

