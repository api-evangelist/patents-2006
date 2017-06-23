---

title: Managing multiple languages in a data language
abstract: Described are various methods and apparatuses that provide for variants for multiple resource types and efficiently managing these resources by use of common variables and an organized file structure. A file structure is organize by a common variables, such as the $lang variable, and includes resource references such that once the common variable is defined, similar resources can be referenced using the same instruction by the use of modifying the common variable. Multiple resource types, including text, images as well as other resource types may be managed using the file structure disclosed herein.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07797308&OS=07797308&RS=07797308
owner: QUALCOMM Incorporated
number: 07797308
owner_city: San Diego
owner_country: US
publication_date: 20060531
---
This application claims benefit of U.S. Provisional Application Ser. No. 60 686 180 filed May 31 2005 the entirety of which is hereby incorporated herein by this reference.

The present invention generally relates to variable processing of software applications. More particularly the invention relates to creating file structures and resource processing with common variables.

Data languages are becoming a more pervasive way to program. Data languages include markup languages such as those based on XML including HTML TRIGML owned by QUALCOMM Incorporated . Data driving languages are extensively used in programming web based applications but are not limited thereto. Examples of XML based languages also include billing and transaction processing applications.

Difficulties rise in a couple of instances when using data languages. For example in developing a user interface UI it is desireable to have the availability to multiple languages for an application depending on the language desired by the application running on the device. For example a wireless device used in France may want to access the term bonjour whereas a wireless device used in the United Kingdom may want to access the term Hello for the same purposes.

In addition to text however there may be other resource types that the application would like to vary based on the culture language or other variable. For example the application may wish to display the Eiffel Tower as a backdrop if the language is selected as French yet may wish to display Buckingham Palace for English. Similary more risque pictures may be desired for those languages cultures that the application developer believes are more appropriate versus more reserved images for those languages cultures the application developer believes is more reserved.

Current methods use to address this problem is the use of language packs. Microsoft Word for example can install a language pack. This language pack merely changes a pointer value for a defined term. For example a French language pack installed would substitute the menu option for edit the corresponding French word such as editer. Multiple language packs may be installed but they become hard to manage as the number of language dependent resources gets large. Further there is no solution to managing resources based on other variants.

Therefore what is needed in the art is a method apparatus and system for that allow the managing the language variants for multiple types of resources. Further what is need is a method apparatus and system for providing variants for multiple resource types and managing resources using multiple variants.

Systems and methods consistent with the present invention overcome the shortcomings of existing systems by creating systems methods and apparatuses that provide for variants for multiple resource types and efficiently managing these resources by use of common variables and an organized file structure.

In one embodiment a method for generating a structure for managing resources using a variable in a data language comprises receiving a plurality of resource references distinguished by a variable and building a structure using the variable and the plurality of resource references wherein the plurality of resource references may be accessed by modifying the variable value.

In another embodiment a method for generating a file structure to access similar resource reference distinguished by a common variable comprises dividing the file structure using the common variable type placing a value associated with each of the similar resource references in the same relative location within the file structure.

In yet another embodiment a device for storing a file structure to access similar resource references distinguished by a common variable comprises a memory the file structure stored in the memory wherein the file structure is organized via a common variable and the similar resource references are located within the file structure as the same locations within different common variable values and a processor to retrieve the resource references using the common variable value.

In yet another embodiment a computer readable medium containing computer executable instructions that when executed generates a file structure to access similar resource references distinguished by a common variable by performing the step of dividing the file structure using the common variable and placing a value associated with each of the similar resource references in the same relative location within the file structure referenced by the common variable.

In yet another embodiment a method of managing resources in a data language comprises receiving a request for a resource using a parameter modifying the parameter and receiving a request for a related resource modified using the parameter.

In yet another embodiment a method for receiving a request for a resource value contained within a file structure organized using a common variable comprises storing a value of the common variable receiving the request for a resource wherein the request contains the common variable and resource reference retrieving the value of the common variable and retrieving the resource value using the retrieved common value and the resource reference by looking up a location in the file structure associated with the common value and the resource reference. This method may further include modifying the value of common variable receiving a request for a second resource value contained within the file structure organized using the common variable and the resource reference retrieving the modified common variable retrieving a second resource value using the modified common variable and the resource reference.

Other objects advantages and features of the present invention will become apparent after review of the herein after set forth Brief Description of the Drawings Detailed Description of the Invention and the Claims.

Reference will now be made in detail to the presently exemplary and preferred embodiments of the invention as illustrated in the accompanying drawings in which like reference characters designate like or corresponding parts throughout the several drawings. The nature objectives and advantages of the present invention will become more apparent to those skilled in the art after considering the following detailed description in connection with the accompanying drawings.

Regarding use of terms in this description the terms wireless device wireless telephone and mobile device are used interchangeably. The term application as used herein is intended to encompass executable and nonexecutable software files raw data aggregated data patches content user interfaces and user interface components and other code segments. Further like numerals refer to like elements throughout the several views and the articles a and the includes plural references unless otherwise specified in the description.

The following description relates to a user interface resource management method apparatus and system using TrigML data language. TrigML is a data language useful in developing User Interfaces. TrigML is a product owned by QUALCOMM Corporation. Like data languages defined under XML TrigML code includes the use of tags. It will be recognized by those skilled in the art that while the forgoing description is in terms of a UI TrigML and managing languages that it is applicable to other applications than UI may be implemented in data languages other than TrigML including other XML based languages and may be use to manage other resource types using variants other than language.

Embodiments of the present invention include managing resources such as text and images by managing languages. These may be any resources including but not limited to text images page layout program fragments access to device components and functions.

In one example the wireless network may include a cellular telephone network. Several mobile devices are in communication with the wireless network such as a cellular phone a laptop computer a PDA and a mobile messaging device . These devices are only shown as illustrative of the many types of devices that may communicate over the wireless network .

Illustrated in are an application server and a user interface server . The user interface server is a computing device that serves user interface components described in more detail below . These user interface components may be downloaded to other devices connected to the wireless network . User interface components include code and or data to render a user interface such as function calls menus code for content calls skins etc. . Note many other servers may be used connect to the network to deliver information including content servers. The type of information that can be made available is limitless and very many different examples will be apparent to those skilled in the art. The user interface server includes server software that is configured to provide the user interface components to requesting devices over the wireless network .

The application server is a computing device or system coupled to the wireless network that makes software applications available for download by the mobile devices. Generally stated the applications are downloadable by the devices connected to the wireless network such as the cellular phone for execution on those devices. In this particular implementation at least one of the applications served by the application download server is a content based application configured for execution on at least one of the mobile devices. The content based application the client is configured to retrieve content from the content server not shown for presentation by the mobile device via a user interface.

The mobile device has a computer platform that can receive and execute software applications and display data. The computer platform includes a processor such as an application specific integrated circuit ASIC digital signal processor DSP microprocessor microcontroller logic circuit state machine or other data processing device. The processor executes the application programming interface API layer that interfaces with any resident programs in the memory of the mobile device. The memory can include random access or read only memory RAM or ROM EPROM EEPROM flash memory or any memory common to computer platforms. The computer platform also includes a local storage that can hold software applications files or data not actively used in memory such as software applications or user interface components downloaded from the user interface server . The local storage is typically comprised of one or more flash memory cells but can be any secondary or tertiary storage device as known in the art such as magnetic media EPROM EEPROM optical media tape or soft or hard disk.

The computer platform also includes a display that may be used by the software applications to display data using the user interface not shown .

The components shown in are typical of many types of mobile devices but it will be appreciated that other components may be added to the mobile device and in certain cases some components shown in may be omitted from the mobile device .

In this example the computing device includes a processor unit a memory a storage medium and an audio unit . The processor unit advantageously includes a microprocessor or a special purpose processor such as a digital signal processor DSP but may in the alternative be any conventional form of processor controller microcontroller or state machine. The processor unit is coupled to the memory which is advantageously implemented as RAM memory holding software instructions that are executed by the processor unit . In an alternate embodiment the memory could be composed of firmware or flash memory. In this embodiment the software instructions stored in the memory include an operating system and one or more other applications such as an application employing a user interface not shown .

The mobile device also includes a communications module that enables bidirectional communication between the computing device and one or more other computing devices such as the mobile device. The communications module may include components to enable RF or other wireless communications such as a cellular telephone network Bluetooth connection wireless local area network or perhaps a wireless wide area network. Alternatively the communications module may include components to enable land line or hard wired network communications such as an Ethernet connection RJ 11 connection universal serial bus connection IEEE 1394 Firewire connection or the like. These are intended as non exhaustive lists and many other alternatives are possible. The audio unit is a component of the mobile device that is configured to convert signals between analog and digital format. The audio unit is used by the mobile device to output sound using a speaker and to receive input signals from a microphone .

In one embodiment the application architecture of a wireless device includes Device APIs BREW APIs BREW Extensions a Trigplayer Actors and Trigs . The Device APIs may include those APIs used by a software platform to address functions associated specifically with that device such as specific processor or ASIC functions specific device hardware functionality etc.

The BREW APIs is a software platform developed by QUALCOMM Incorporated. The BREW APIs provide the ability for applications to call Device APIs and other functions without having to be written specifically for the device. In otherwords it abstracts the specific aspects of the hardware from the application thereby allowing an application to be written for many devices without having to tailor or requiring only slight tailoring for each specific device on which the application executes.

A BREW extension provides the ability to add additional capability to the BREW platform such as offering MP3 players Java Virtual Machines etc.

A TrigPlayer Trigs and Actors are components of the uiOne architecture developed by QUALCOMM Incorporated. These components typically refer to user interface aspects of the device . In one embodiment the Trigs are compiled TrigML code and other resources which may include metadata text files and images used by an application to render a user interface on the device . Multiple Trigs and updates to Trigs referred to as Triglets not shown may be used for the user interface.

TrigML code owned by QUALCOMM Incorporated is a data language based on XML and may be used for user interface presentation language for authoring Trigs and includes advantages of mobile targeted functionality an interactive user interface event model and pixel positioning among other advantages.

Actors include underlying C code to connect Trigs to underlying Device APIs and or BREW APIs . Actors may also serve as executables for input output. And because actors connect to the underlying Device and BREW APIs they have access to the computer platform functions.

The Trigplayer may be implemented as a BREW extension even though it is separated out in . The Trigplayer is used to render the user interface using the Trigs and actors.

It will be recognized that although the discussion of is in terms of the QUALCOMM Incorporated s uiOne architecture including compiled TrigML Trigplayer BREW APIs etc that this is for descriptive purposes and that the present invention include other data languages computer and software platforms and device architectures.

In building the system that allows managing multiple languages the developer creates a TrigML element such as 

The builder will also receive from the developer the languages the developer wishes to support. For example the developer may select English and French. In the example above the text resource a has been created and has an associated English and French value.

One embodiment creates a file structure based on the resource a and the languages selected by the developer. depicts an example of this file structure . In this example the text resource reference a in the English version has a value of hello and bonjour for the French version of the text resource a .

If lang is defined as English the above expression resolves to hello . If the lang is defined as French the above expression resolves to bonjour. Note that the same resource reference a is used to access two representations of a related text resources namely hello and bonjour .

In one embodiment a trigplayer may be used to resolve the lang variable in compiled code. However it will be recognized by those skilled in the art that any parser or other code analyzer may be used. Further the code is not required to be compiled.

The lang variable may be set or changed by the device the developer application or other entity that may access the variables. In one paradigm the lang has a default value for example English and may be changed by the device at a later point.

Should the lang value change the trigplayer will attempt to use that value when determining which resource to access. Should the language resource not exists the trigplayer may return to the last valid lang value. For example if the previous value of lang was English and then was changed to German and the following expression was encountered 

The trigplayer would attempt to find text German a . However if German does not exist the trigplayer would revert to the previous lang value that was valid. Therefore if the lang value of English was successfully used previously the trigplayer would then try to find text English a when the above expression was encountered.

Alternatively the trigplayer may have a default value for lang that it always reverts to. And yet another alternative may be returning a error such as resource not found error.

Embodiments were described in terms of language and a lang variable. However other variables may be used other than language in the same manner in order to control variable values. For example a variable may be used to manage multiple devices supported other device resources such as screen sizes functions etc. It will be recognized that any resource may be managed using the methods and apparatus described herein.

If the path of a resource in a Trig or Triglet a UI element contains lang and you compile for multiple languages then each resource data for each language will be included with the lang part of the path replaced with the two letter country code. Note throughout the document unless otherwise noted the use of Trig s refers to Trig s or Triglet s .

To reference the path in TrigML the lang variable is kept in the path and the Trigplayer looks up the language of the handset and selects the correct resource to include from the mulitple values present.

The default language is extra information used to carry in the Trig properties so that when the trig is compiled that the default language is the first language in the config supportedLangs data list of languages.

In one embodiment the compiler can assume that it is the first language in the array passed to the compiler.

The Trigplayer currently reads a text resource located at config supportedLangs which contains a new line separated list of languages which the Trig supports. The first language in the list is the default language which the player will fall back on should the language selected on the handset be unsupported.

In another embodiment the use of Parcelforce code abstracts the meaning of whether a resource is multi language or not by a method on the resource object is multilang. This method tests whether the string lang is present in the resource path for the resource object.

When the resource path of an object is a new argument of lang which if it is passed in will substitute the presence of lang with the passed in language. This code can then be called by the TrigCompiler when it is generating the resource paths to go into the bar file. All other use of get resource path will return the path without replacing the lang for use in TrigBuilder for example.

There is also a call to unify checking to see if a Trig is multi language or not. The method is multilang on the Trig object checks all the resources it contains are multi language. This common code is used in a number of places and follows good programming practice to put common code in one place.

By abstracting it in this way we can more easily move to a different implementation of multiple language handling in the future.

The above method and software design description may also be implemented in an apparatus stored as instructions in RAM or in other memory storage devices. Although the processes presented in this document have been illustrated and described sequentially in a particular order in other embodiments the steps of the processes may be performed in different orders multiple times and or in parallel. Further in some embodiments one or more steps described in the several processes may be performed as separate steps combined into fewer steps or possibly omitted entirely.

While the foregoing disclosure shows illustrative embodiments of the invention it should be noted that various changes and modifications could be made to the described embodiments without departing from the spirit and scope of the invention as defined by the appended claims. Furthermore although elements of the invention may be described or claimed in the singular the plural is contemplated unless limitation to the singular is explicitly stated.

