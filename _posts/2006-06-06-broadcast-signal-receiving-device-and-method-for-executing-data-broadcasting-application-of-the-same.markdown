---

title: Broadcast signal receiving device and method for executing data broadcasting application of the same
abstract: A broadcast signal receiving device includes a profile management module that manages user profile information indicating whether to execute a data broadcasting application received via a channel, an application filtering module that filters data composing a data broadcasting application from data signals of broadcast signals, and an application management module that executes a data broadcasting application composed of the filtered data and according to the user profile information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08904461&OS=08904461&RS=08904461
owner: Samsung Electronics Co., Ltd.
number: 08904461
owner_city: Suwon-Si
owner_country: KR
publication_date: 20060606
---
This application claims priority from Korean Patent Application No. 10 2005 0066863 filed on Jul. 22 2005 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference in its entirety.

Apparatuses and methods consistent with the present invention relate to data broadcasting and more particularly to a broadcast signal receiving device that receives data broadcasting and a method for executing a data broadcasting application of the same.

Conventional television TV broadcasts contain audio and video. Digital TV broadcasts however contain text in addition to audio and video.

Some technologies that broadcast text information have been established and broadcast signal receiving devices such as TV sets and set top boxes are commercially available.

Accordingly broadcasting stations can transmit content such as information on weather medicine performances games books as well as additional information on each channel or program using hypertext mark up language HTML which is the standard language of the Internet.

Referring to when a digital broadcast signal of a channel among broadcast signals received via an antenna or cable is received via channel tuning by user a tuner tunes and demodulates the digital broadcast signal and the obtained digital broadcast signal stream is output to a demultiplexer .

The demultiplexer demultiplexes the input digital broadcast signal stream to thereby divide it into audio video and text. Because the demodulated digital audio and video signals and text are multiplexed in the form of a transport packet the demultiplexer can separate them into audio and video signals and text respectively by demultiplexing.

The audio signal is output to an audio decoder which restores the compressed audio signal to an original audio signal and then outputs it to a speaker. Also the video signal is output to a video decoder which restores the compressed video signal to an original video signal and then displays it via a display control unit .

A system control unit controls a text capture engine in order to capture the text and output the captured text to the display control unit . The text is a data stream format consisting of a header and a payload. As an example the header includes information to signify start of signals a packet identification number to identify information included in the payload following it. After data is extracted from the payload fragments of the data are combined to constitute a single file which is in a specific format.

The display control unit displays on the screen the text based content transmitted from the text capture engine along with a video signal output via the video decoder . The system control unit controls the data flow between the demultiplexer and the text capture engine .

The user input denoted by numeral in implies that a predetermined data broadcasting application is executed when a user selects it using a remote control.

The data broadcasting application received by the broadcast signal receiving device is displayed on a TV screen in one of two possible ways.

In the first way when a data broadcast is received a data broadcasting application for the data broadcast is automatically displayed on a screen regardless of whether the user selects it. In the other way when a data broadcast is received the user is given an opportunity to select an application for viewing the data broadcasting and the application is displayed only when the user selects it.

Several data broadcasting applications for one channel may be transmitted according to the current text broadcasting specification and a user can select one of them to view.

As the user views the audio video A V broadcasts of a predetermined channel data broadcasts corresponding to the channel are received by the broadcast signal receiving device. When the data broadcasts are completely received they can be displayed on the current A V broadcasting screen as illustrated in .

Referring to a mark A is displayed in the top left of the screen . If a user wants to view various data broadcasting applications corresponding to the received data broadcasts the user makes the mark A active using a remote control.

With development in communication technologies and content industries it is expected that a number of data broadcasting applications will be transmitted to broadcast signal receiving devices such as TV sets or set top boxes. Here automatic display of data broadcasting applications regardless of the user s preference is liable to cause inconvenience to the user.

If a number of data broadcasting applications associated with an advertisement are continuously displayed on a screen while a user is watching TV program the user may become annoyed and cease viewing.

Accordingly it is necessary to provide a device and method that allows the user to control the execution of data broadcasting applications received for each channel.

The present invention provides a broadcast signal receiving device that controls data broadcasting applications according to execution information of the data broadcasting applications preset by a user and a method of the broadcast signal receiving device for executing the data broadcasting applications.

According to an aspect of the present invention there is provided a broadcast signal receiving device including a profile management module to manage user profile information showing whether to execute a text broadcasting application received via a channel an application filtering module to filter data that composes a text broadcasting application from a broadcast signal and an application management module to execute a text broadcasting application composed of the filtered data and according to the user profile information.

According to another aspect of the present invention there is provided a method of the broadcast signal receiving device for executing a text broadcasting application including filtering data that composes a text broadcasting application from a broadcast signal extracting user profile information showing whether to execute the text broadcasting application and executing a text broadcasting application composed of the filtered data and according to the extracted user profile information.

Advantages and features of the present invention and methods of accomplishing the same may be understood more readily by reference to the following detailed description of the exemplary embodiments and the accompanying drawings. The present invention may however be embodied in many different forms and should not be construed as being limited to the exemplary embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the concept of the invention to those skilled in the art and the present invention will only be defined by the appended claims. Like reference numerals refer to like elements throughout the specification.

The present invention is described hereinafter with reference to flowchart illustrations of user interfaces methods and computer program products according to embodiments of the invention. It will be understood that each block of the flowchart illustrations and combinations of blocks in the flowchart illustrations can be implemented by computer program instructions. These computer program instructions can be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which are executed via the processor of the computer or other programmable data processing apparatus create means for implementing the functions specified in the flowchart block or blocks. These computer program instructions may also be stored in a computer usable or computer readable memory that can direct a computer or other programmable data processing apparatus to function in a particular manner such that the instructions stored in the computer usable or computer readable memory produce an article of manufacture including instruction means that implement the functions specified in the flowchart block or blocks. The computer program instructions may also be loaded into a computer or other programmable data processing apparatus to cause a series of operational steps to be executed in the computer or other programmable apparatus to produce a computer implemented process such that the instructions that execute in the computer or other programmable apparatus provide steps for implementing the functions specified in the flowchart block or blocks.

And each block of the flowchart illustrations may represent a module segment or portion of code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some alternative implementations the functions noted in the blocks may occur out of order. For example two blocks shown in succession may in fact be executed substantially concurrently or the blocks may sometimes be executed in reverse order depending upon the functionality involved.

A broadcast signal receiving device includes a device that provides user audio video and text extracted from a broadcasts signal after receiving broadcasts signals via terrestrial wave satellite or cable.

Referring to a data broadcasting system according to the present invention includes a network a broadcasting station s transmitter a broadcasting station s computer a content server and a user s TV . Here the content is text and a data broadcasting application.

The network may be the Internet. Because software and hardware for connecting to the Internet are built in to the broadcasting station s computer and the content provider s computer and the user s TV are connected to the network two way communication is possible.

The broadcasting station transmitter station adds text to the content produced by a broadcasting station advertisements and content developed by a provider who manages online commerce for program content and then transmits them.

The broadcasting station s computer classifies additional information using a database and then stores it. Hardware and software that manage data transmitted from a user via the network are built in to the broadcasting station s computer .

The content provider s computer produces advertisements that will be added to broadcast programs under a contract with a broadcasting station and content associated with on line commerce and sends them to the broadcasting station. Hardware and software that manage online commerce information transmitted via the network are built in to the content provider s computer .

The user s TV has built in hardware and software that extracts text from broadcast signals transmitted by the broadcasting station s transmitter and manages it. Also the user s TV has built in hardware and software to transceive information on the text by connecting with the broadcasting station s computer and the content provider s computer via the network .

Viewers may select and use text in the broadcasting program transmitted by the broadcasting station s transmitter . The broadcast signal receiving device using text obtained from the user s TV will be described in detail in the following.

The broadcast signal receiving device comprises hardware an operating system OS to control the hardware and middleware .

An execution engine able to execute a data broadcasting application and a native application are operated based on the operating system and the middleware . The native application is an application loaded when the broadcast signal receiving device is produced or upgraded for example an electronic program guide EPG which is loaded when a user purchases the broadcast signal receiving device and applications with various menus.

Also various data broadcasting applications may be executed via an Xlet application programming interface API . The Xlet API may be defined by standards such as the Digital Video Broadcast Multimedia Home Platform DVB MHP the Open Cable Application Platform OCAP and the Advanced Common Application Platform ACAP .

The data broadcasting applications comprise Xlet applications such as an electronic program guide EPG or video on demand VOD and a bound or unbound Xlet application. The bound application is bound to services or channels or programs. For example the bound application automatically disappears when changing to another channel because the bound application is bound to a specific channel or after ending specific broadcasting because the bound application is bound to specific broadcasting e.g. TV drama or news .

The unbound application refers to a service channel unbound application and a program unbound application.

If a broadcasting station A operates an A 1 channel and an A 2 channel the service channel unbound application shows all the programs of broadcasting station A.

If a specific broadcasting station operates only one channel the program unbound application refers to provided applications e.g. a weather application and a news application regardless of programs.

Referring to a broadcast signal receiving device may include an antenna a tuner a channel decoding unit a demultiplexer an audio signal processing unit a speaker a video signal processing unit a video editing unit a display unit a user input unit a control unit a network communication unit and an application processing unit .

When a user selects a desired broadcast channel after turning on the TV using key input means of the user input unit the tuner outputs only the broadcast signal of the channel set by the user among broadcast signals received via the antenna or input terminal not shown . The user input unit may be a remote control.

Then the channel decoding unit separates the digital signal found in broadcast signal of the selected channel by packet and then outputs it to the demultiplexer . The demultiplexer classifies the audio video and data signals extracted from the signal independent series of bits and then outputs them.

The separated audio signal is output to the speaker after demodulation and error correction is performed by the audio signal processing unit .

The separated video signal is output to the video editing unit after demodulation and error correction is performed by the video signal processing unit . Data and a data broadcasting application are input to the video editing unit after the separated data signals are processed.

The video editing unit edits information received from the video signal processing unit and the application processing unit and composes one screen showing the information in order to send the screen to the displaying unit .

The displaying unit outputs the screen composed by the video editing unit to a display unit such as a TV .

The control unit allows the application processing unit to execute a user interface that a user may set via the user input unit. Then the application processing unit displays the user interface to the TV via the video editing unit and the displaying unit . The information on whether to execute a data broadcasting application received will be referred to as a user profile .

The user profile A in is set to channel . If a user selects channel all received data broadcasting applications can be executed. The user profile B in is set to channel . If the user selects channel an unbound data broadcasting application of received data broadcasting applications can be executed.

A menu that allows a user to select a user profile is activated in channel and a user may select a desired profile among four profiles using a direction button of the user input unit .

If channel is selected by the user the control unit allows the application processing unit to execute only an unbound broadcasting application among broadcasting applications received from channel . Accordingly the video editing unit receives the text provided by the unbound broadcasting application and edits it with information received from the video signal processing unit .

User profile information in and the user interface in may be managed by the application processing unit .

The network communication unit has built in network communication software and hardware and may produce a return channel synchronized with the data broadcasting applications.

The profile management module provides the user interface in according to a user s request and stores the result in the profile storage module . The profile management module also extracts a user profile from the profile storage module according to a request of the application management module and provides it to the application module .

The application filtering module filters data that composes a data broadcasting application and stores the result in the profile storage module . The application management module stores data filtered by the application filtering module in the application storage module .

Various data broadcasting applications received from the channel selected by a user are stored in the application storage module .

The application management module executes the data broadcasting application stored in the application storage module by requesting user profile information from the profile management module and applying the user profile.

The term module as used herein means but is not limited to a software or hardware component such as a Field Programmable Gate Array FPGA or Application Specific Integrated Circuit ASIC which executes certain tasks. A module may advantageously be configured to reside in the addressable storage medium and configured to be executed on one or more processors. Thus a module may include by way of example components such as software components object oriented software components class components and task components processes functions attributes procedures subroutines segments of program code drivers firmware microcode circuitry data databases data structures tables arrays and variables. The functionality provided for in the components and modules may be combined into fewer components and modules or further separated into additional components and modules.

When the control unit receives an application information table AIT that includes numeral and functional information of the application program application control codes and the application program s name and position from the demultiplexer which sent to the application management module of the application processing unit S . The above is referred to as a signal .

If the application management module receives the signal the application management module allows the application filtering module to filter data that composes a data broadcasting application S .

In S the application management module stores the data filtered by the application filtering module in the application storage module . That is various data broadcasting applications being received from channel are stored in the application storage module .

If the application management module requests a user profile from the profile management module the profile management module extracts the user profile from the profile storage module and provides it to the application management module S .

The application management module tests whether a data broadcasting application stored in the application storage module is an application that has an auto executing attribute S . If the application has an auto executing attribute the application management module determines whether to execute the application using a user profile provided from the profile management module S .

In this case the application management module determines whether to execute the application using the new user profile provided from the profile management module .

According to the broadcast signal receiving device and the method for executing data broadcasting application using the broadcast signal receiving device a user can control the data broadcasting applications that are auto executed by defining a user profile about executing data broadcasting applications and applying the user profile.

Although the apparatus and method for managing a file system according to the present invention has been described in connection with the exemplary embodiments of the present invention it will be apparent to those skilled in the art that various modifications and changes may be made thereto without departing from the scope and spirit of the invention. Therefore it should be understood that the above embodiments are not limitative but illustrative in all aspects.

