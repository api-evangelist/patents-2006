---

title: Automatic updating of variables in a data language
abstract: Described are various methods and apparatuses for automatic updating of variables in a data language. A dynamic variable is updated by parsing an instruction written in the data language containing the dynamic variable, creating the dynamic variable in memory, assigning a value for the dynamic variable, and updating the dynamic variable value without parsing the instruction written in the data language containing the dynamic variable. The dynamic variable may also be updated by creating an object associated with the dynamic value, wherein the object determines the value of the dynamic variable. Further, an observing a function value may be associated with the dynamic variable and then a notification is given to the object when the function value has changed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07908595&OS=07908595&RS=07908595
owner: QUALCOMM Incorporated
number: 07908595
owner_city: San Diego
owner_country: US
publication_date: 20060531
---
This application claims benefit of U.S. Provisional Application Ser. No. 60 686 271 filed on May 31 2005 the entirety of which is hereby incorporated herein by this reference.

The present invention generally relates to variable processing of software applications. More particularly the invention relates to processing dynamic variables in a data language.

Data languages are becoming a more pervasive way to program. Data languages include markup languages such as those based on XML including HTML and TRIGML owned by QUALCOMM Incorporated . Data languages are extensively used in programming web based applications but are not limited thereto. Examples of functions implemented using XML based languages include billing and transaction processing programs.

Data languages are interpretive by nature. A pass is made through the data language program and for example a web page is displayed using elements defined in the program. The program may define the elements used as well as characteristics of the element regarding how they may be displayed. These languages may also be used in the generation of user interfaces.

Difficulties arise in the use of data languages such as with the handling of variables. Because XML is interpretive by nature variables that are dynamic can t be changed once the variable has been set. Some attempts to solve this problem is with the use of java scripts. However java scripts don t modify the variable until the code is re executed and something must trigger the java script to be re executed. There is no automatic trigger. In otherwords the program code containing the java script must be executed again to determine the new variable value. If the variable is dynamic and changing the variable used in java script will not be updated until the code is re executed.

Another difficulty in using data languages is that they don t allow access to the underlying computer or processor platform functions. For example should you want to use a data language display a battery icon indicating the battery level there is no mechanism in the data language to access the battery level as known to the platform. Java scripts also suffer from this problem of not having the ability to access computer platform functions.

Consequently there is a need in the art to provide methods and apparatus allowing the evaluation of expressions containing dynamic variables. In addition there is need to have a method and apparatus provide access to the computer platform level functions.

Systems and methods consistent with the present invention overcome the shortcomings of existing systems by creating systems methods and apparatuses that evaluate dynamic variables and access underlying functions of the computer platform.

In one embodiment of the present invention an expression having a dynamic variable written in a data language is evaluated by receiving the dynamic variable determining a first value of the dynamic variable evaluating the expression using the first value and detecting a change associated with the dynamic variable. After receiving a second value associated with the dynamic variable and evaluating the expression using the second value associated with the dynamic variable the expression is evaluated using the second value without reinterpreting other program code containing the expression.

In another embodiment a dynamic variable is updated by parsing an instruction written in the data language containing the dynamic variable creating the dynamic variable in memory assigning a value for the dynamic variable and updating the dynamic variable value without parsing the instruction written in the data language containing the dynamic variable. The dynamic variable may also be updated by creating an object associated with the dynamic value wherein the object determines the value of the dynamic variable. Further an observing a function value may be associated with the dynamic variable and then a notification is given to the object when the function value has changed.

In yet another embodiment an apparatus for updating a dynamic variable in a data language comprises a memory location assigned to a dynamic variable wherein the dynamic variable was assigned the memory location in response to parsing an instruction in a data language and a processor to evaluate updates to the dynamic variable.

In yet another embodiment a computer readable medium containing computer executable instructions for updating a dynamic variable written in a data language that when executed performs the steps comprises parsing an instruction written in the data language containing the dynamic variable creating the dynamic variable in memory assigning a value for the dynamic variable and updating the dynamic variable value without parsing the instruction written in the data language containing the dynamic variable.

Other objects advantages and features of the present invention will become apparent after review of the herein after set forth Brief Description of the Drawings Detailed Description of the Invention and the Claims.

Reference will now be made in detail to the presently exemplary and preferred embodiments of the invention as illustrated in the accompanying drawings in which like reference characters designate like or corresponding parts throughout the several drawings. The nature objectives and advantages of the present invention will become more apparent to those skilled in the art after considering the following detailed description in connection with the accompanying drawings.

Regarding use of terms in this description the terms wireless device wireless telephone and mobile device are used interchangeably. The term application as used herein is intended to encompass executable and nonexecutable software files raw data aggregated data patches content user interfaces and user interface components and other code segments. Further like numerals refer to like elements throughout the several views and the articles a and the includes plural references unless otherwise specified in the description.

TrigML is a data driven language useful in developing User Interfaces. TrigML is a product owned by QUALCOMM Corporation. Like data languages defined under XML TrigML code includes the use of tags. While embodiments will be described in context of TrigML for a user interface on a wireless device it will be recognized that this is for descriptive purposes only and not a limitation on the invention. The apparatus and methods described herein are also applicable in non user interface environments and as stated above in those using environments using a different data language.

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

In one embodiment of the invention when the TrigML program code is parsed for execution objects associated with elements in the TrigML code. These objects may contain the representations of the element. For example element indicates a box having a length of 3. When this element is evaluated an object having the value of the box length 3 is created.

It may be desireable to include a dynamic variable in an expression in the program code. For example if an icon representing a battery level for a wireless device is desired assuming the width of box changes as the batter level changes it is desirable to update this box width to indicate the current battery level which is subject to change as the battery is charged and depleted.

In this case the element contains an expression batterylife 10 having a dynamic variable batterylife that may change depending the amount of charge left in the battery. It further is manipulated by the object by dividing the batterylife value by 10. Note the expression may contain a simple or complex operation including the use of numbers strings operators along with dynamic variables.

In one embodiment an object is created to determine the value of the expression of the element containing the dynamic variable. In addition an actor is created and used to receive the batterylife value. The object will use the value represented in the actor for the dynamic variable in evaluating the expression.

In the device a function e.g. an API monitors and determines the current batterylife . The function may include those functions that are at the computer or platform level to the computing device e.g. Device and or BREW APIs or may be other functions of other APIs functions or tasks executed locally or remotely and related to the local computer or a remote computer. It will be recognized by those skilled in the art that the batterylife function is used for descriptive purposes only and that any function API may be used.

Many paradigms may be used to indicate a change in the value of the batterylife function to the actor . For example an observe notify pattern may be implemented in which the batterylife function is told that the actor exists and when a change in value occurs to notify the actor . Using this paradigm the actor stands by and waits for an indication from the batterylife function that a change occurred. Once the actor receives the indication of a change it notifies the object so the object can fetch the value from the battery function . The object can then evaluate the expression containing the dynamic variable using the new function value.

Another paradigm includes polling where the actor periodically polls the batterylife function for an indication that a change has occurred. Processing proceeds as described above where the object fetches the value of the function and evaluates the expression. Other paradigms exist and known to those skilled in the art and included in the scope of this invention.

When the object representing the expression is reevaluated the new value can then be used for the purpose the TrigML code was written. Also notice that the dynamic variable can change often and with each change only the object associated with the expression needs to reevaluated to determine a new value. The TrigML code is not needed to be reparsed.

Also the dynamic variable is a variable that may change and any change to it may be desired after the initial parsing of the data language program code. It may also be related to function associated with the computer platform.

Next an object is created to evaluate the expression Step . The use of an object is not necessary and may only be necessary for some elements. The object may contain the value not necessarily a number or scalar value but the representation of the intention of the element.

An actor is then created Step which assists in providing a value of the dynamic variable. Alternatively the actor may have already existed and the existing actor is use for informing the object that the function value has changed. The actor is linked to the function associated with the dynamic variable. The actor may provide two functions these functions are not required to be assigned to the actor and it may perform additional functions . First it may allow a value to be queried fetched read etc and second it may server as the mechanism to indicate a change in the function to the object using one of the paradigms discussed herein .

The object then fetches the function value from the function Step . The object proceeds to evaluate the expression Step . Next it is determined if there is a change in the function value Step . This may be perform as described herein via the function indicating to the actor that a change has occurred and the actor indicating that a change occurred to the object.

If the function value changed in Step the yes path is followed and the object re fetches the function value from the function Step and evaluates the expression using the new function value associated with the dynamic variable Step .

If the value of the function does not change in step the no path is followed and the function is monitored for a change using one of the paradigms described herein or others known to those skilled in the art.

Here the animate animation tag is activated while the given boolean expression is true. If at any point in the future the expression resolves to false the animation will be deactivated.

Boolean expression may also be used for one off action tags by insisting that the tag is instantaneously activated each time the expression resolves to true i.e. when any sub element of the expression is changed and the whole expression resolves to true e.g. 

Here the doload action is performed each time the VFS node res errormsg is updated and the expression evaluated to true.

In this embodiment the resource path of three elements is constructed using a string literal for the first element and two expressions for the final elements. The resource path indicates the location of the image to be rendered. Should any of the sub expressions change the resource path will be automatically re evaluated and may result in a different image being displayed.

By embedding arbitrarily complex expressions directly in XML attributes it is possible to create dynamically updatable UIs with succinct and elegant markup without the need for events or embedded scripting languages.

The above method and software design description may also be implemented in an apparatus stored as instructions in RAM or in other memory storage devices. Although the processes presented in this document have been illustrated and described sequentially in a particular order in other embodiments the steps of the processes may be performed in different orders multiple times and or in parallel. Further in some embodiments one or more steps described in the several processes may be performed as separate steps combined into fewer steps or possibly omitted entirely.

While the foregoing disclosure shows illustrative embodiments of the invention it should be noted that various changes and modifications could be made to the described embodiments without departing from the spirit and scope of the invention as defined by the appended claims. Furthermore although elements of the invention may be described or claimed in the singular the plural is contemplated unless limitation to the singular is explicitly stated.

