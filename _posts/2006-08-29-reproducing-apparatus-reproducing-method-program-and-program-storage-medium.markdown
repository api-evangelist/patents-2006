---

title: Reproducing apparatus, reproducing method, program, and program storage medium
abstract: A reproducing apparatus includes an acquisition unit for acquiring playback management information containing first information containing a main playback path indicating a location of a main stream, a read out unit for reading the main stream to be reproduced and video data that is to be reproduced in synchronization with the main stream, based on the playback management information, a first storage unit for storing the video data read by the read out unit, a decode unit for decoding the video data stored on the first storage unit, a second storage unit for storing the video data decoded by the decode unit, a playback unit for reproducing the main stream read by the read out unit by referencing a predetermined counter based on the playback management information, and a video data output unit for outputting the decoded video data stored on the second storage unit in synchronization with playback of the main stream.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08208794&OS=08208794&RS=08208794
owner: Sony Corporation
number: 08208794
owner_city: Tokyo
owner_country: JP
publication_date: 20060829
---
The present invention contains subject matter related to Japanese Patent Application JP 2005 263970 filed in the Japanese Patent Office on Sep. 12 2005 the entire contents of which are incorporated herein by reference.

The present invention relates to a reproducing apparatus a reproducing method a program and a program storage medium and in particular to a reproducing apparatus a reproducing method a program and a program storage medium for displaying an MPEG 2 transport stream and animation data different in data format from the MPEG2 transport stream in synchronization.

Japanese Unexamined Patent Application Publication No. 7 306954 discloses an animation technique. According to the disclosure to achieve strict synchronization in the display of a plurality animation characters action generation modules of characters to be displayed on screen are arranged and registered in a module list. Display of the animation characters is then controlled by referencing the module list.

In another known technique graphics objects multiplexed into a transport stream based on an HDMV graphics stream are used to display graphics in synchronization with a video frame of an MPEG 2 transport stream format.

To generate graphics data in synchronization with a video frame using an HDMV graphics stream the knowledge of MPEG 2 transport stream and development skills related thereto are required. The technique disclosed in Japanese Unexamined Patent Application Publication No. 7 306954 synchronizes a plurality of units of animation data generated in the same data format. Even with this technique video data and animation data in different data formats cannot be displayed in synchronization.

It is thus desirable to display in synchronization an MPEG 2 transport stream and animation data in a data format different from that of the MPEG 2 transport stream.

In one embodiment of the present invention a reproducing apparatus includes an acquisition unit configured to acquire playback management information containing first information containing a main playback path indicating along time axis a location of a main stream containing at least one stream a read out unit configured to read the main stream to be reproduced and video data that is to be reproduced in synchronization with the main stream based on the playback management information acquired by the acquisition unit a first storage unit configured to store the video data read by the read out unit a decode unit configured to decode the video data stored on the first storage unit a second storage unit configured to store the video data decoded by the decode unit a playback unit configured to reproduce the main stream read by the read out unit by referencing a predetermined counter based on the playback management information acquired by the acquisition unit and a video data output unit configured to output the decoded video data stored on the second storage unit in synchronization with playback of the main stream by the playback unit.

The reproducing apparatus may further include a control unit configured to control process of the first storage unit the decode unit the second storage unit and the video data output unit by referencing the counter referenced by the playback unit.

The acquisition unit may acquire control information containing a command for calling an API corresponding to a process performed by the control unit and when the API is called by executing the command the control unit controls the process of the first storage unit the decode unit the second storage unit and the video data output unit by referencing the counter referenced by the playback unit.

The video data may be in a JPEG data format and include animation data reproducible on a Java application.

The reproducing apparatus may further include a mixture video data generation unit configured to generate mixture video data to be mixed with the main stream reproduced by the playback unit and a playback output unit configured to output the video data that is to be reproduced in response to the supply of the mixture video data to be mixed and generated by the mixture video data generation unit and the supply of the main stream reproduced by the playback unit wherein the video data output unit outputs the decoded video data to the mixture video data generation unit.

The video data output unit may acquire the mixture video data immediately prior to when the video data output unit outputs the decoded video data to the mixture video data generation unit mix the decoded video data with the acquired mixture video data and output the resulting data to the mixture video data generation unit.

The reproducing apparatus may include at least two mixture video data generation units. While a first mixture video data generation unit generates the mixture video data a second mixture video data generation unit supplies the generated mixture video data to the playback output unit. While the second mixture video data generation unit generates the mixture video data the first mixture video data generation unit supplies the generated mixture video data to the playback output unit.

The reproducing apparatus may further include a recording medium playback unit configured to reproduce and read information from a removable recording medium wherein the acquisition unit acquires the playback management information read from the recording medium by the recording medium playback unit.

The reproducing apparatus may further include a storage unit configured to store a variety of units of data wherein the acquisition unit acquires the playback management information stored on the storage unit.

The reproducing apparatus may further include a recording medium playback unit configured to reproduce and read information from a removable recording medium wherein the read out unit reads the main stream and the video data read from the recording medium by the recording medium playback unit.

The reproducing apparatus may further include a storage unit configured to store a variety of units of data wherein the read out unit reads the main stream and the video data stored on the storage unit.

The playback management information acquired by the acquisition unit may contain second information containing a sub playback path of a sub stream file different from a file of the main stream.

In another embodiment of the present invention one of a reproducing method and a computer program of a reproducing apparatus for reproducing stream data includes the steps of reading a main stream to be reproduced based on playback management information containing first information containing a playback path indicating along time axis a location of a main stream containing at least one stream storing video data that is to be reproduced in synchronization with the main stream based on the playback management information decoding the stored video data storing the decoded video data reproducing the read main stream by referencing a predetermined counter based on the playback management information and outputting the stored decoded video data in synchronization with playback of the main stream.

In accordance with embodiments of the present invention the main stream to be reproduced is read based on the playback management information containing the first information containing the playback path indicating along time axis the location of the main stream containing at least one stream the video data that is to be reproduced in synchronization with the main stream is read for storage based on the playback management information the stored video data is decoded the decoded video data is stored the read main stream is reproduced by referencing the predetermined counter based on the playback management information and the stored decoded video data is output in synchronization with playback of the main stream.

Network refers to a mechanism that allows at least two apparatuses interconnected to each other to convey information from one to the other apparatus. The apparatuses communicating via the network may be independent apparatuses or may be internal blocks forming one apparatus.

Communication refers to wireless communication wired communication or a combination of wireless communication and wired communication. In the case of the combination of wireless communication and wired communication wireless communication may be performed in one area and wired communication may be performed in the other area. Furthermore wired communication is performed from a first apparatus to a second apparatus and then wireless communication is performed from the second apparatus to a third apparatus.

The reproducing apparatus may be an independent apparatus or a block performing a playback process in a recording and reproducing apparatus.

In accordance with embodiments of the present invention stream data is reproduced. In particular stream data and video data are reproduced in synchronization.

Before describing an embodiment of the present invention the correspondence between the features of the claims and the specific elements disclosed in an embodiment of the present invention is discussed below. This description is intended to assure that embodiments supporting the claimed invention are described in this specification. Thus even if an element in the following embodiments is not described as relating to a certain feature of the present invention that does not necessarily mean that the element does not relate to that feature of the claims. Conversely even if an element is described herein as relating to a certain feature of the claims that does not necessarily mean that the element does not relate to other features of the claims.

In accordance with one embodiment of the present invention a reproducing apparatus for example reproducing apparatus of includes an acquisition unit for example controller of or configured to acquire playback management information for example playlist containing first information containing a main playback path for example main path indicating along time axis a location of a main stream for example a primary stream containing at least one stream a read out unit for example switch configured to read the main stream to be reproduced and video data for example animation data that is to be reproduced in synchronization with the main stream based on the playback management information acquired by the acquisition unit a first storage unit for example pre load buffer of configured to store the video data read by the read out unit a decode unit for example animation decoder of configured to decode the video data stored on the first storage unit a second storage unit for example decoded object buffer of configured to store the video data decoded by the decode unit a playback unit for example first video decoder and video plane generator of configured to reproduce the main stream read by the read out unit by referencing a predetermined counter for example STC counter based on the playback management information acquired by the acquisition unit and a video data output unit for example composition buffer of configured to output the decoded video data stored on the second storage unit in synchronization with playback of the main stream by the playback unit.

The reproducing apparatus may further include a control unit for example animation scheduler of configured to control process of the first storage unit the decode unit the second storage unit and the video data output unit by referencing the counter referenced by the playback unit.

The acquisition unit may further acquire control information for example a MovieObject file containing a command for calling an API corresponding to a process performed by the control unit and when the API is called by executing the command the control unit controls the process of the first storage unit the decode unit the second storage unit and the video data output unit by referencing the counter referenced by the playback unit.

The reproducing apparatus may further include a mixture video data generation unit for example interactive graphics plane generator of configured to generate mixture video data to be mixed with the main stream reproduced by the playback unit and a playback output unit for example video data processor configured to output the video data that is to be reproduced in response to the supply of the mixture video data to be mixed and generated by the mixture video data generation unit and the supply of the main stream reproduced by the playback unit wherein the video data output unit outputs the decoded video data to the mixture video data generation unit.

The reproducing apparatus may further include at least two mixture video data generation units for example back graphics plane and front graphics plane of wherein while a first mixture video data generation unit generates the mixture video data a second mixture video data generation unit supplies the generated mixture video data to the playback output unit and wherein while the second mixture video data generation unit generates the mixture video data the first mixture video data generation unit supplies the generated mixture video data to the playback output unit.

The reproducing apparatus may further include a recording medium playback unit for example optical disk drive of or configured to reproduce and read information from a removable recording medium wherein the acquisition unit acquires the playback management information read from the recording medium by the recording medium playback unit.

The reproducing apparatus may further include a storage unit for example local storage of or configured to store a variety of units of data wherein the acquisition unit acquires the playback management information stored on the storage unit.

The reproducing apparatus may further include a recording medium playback unit for example optical disk drive of or configured to reproduce and read information from a removable recording medium wherein the read out unit reads the main stream and the video data read from the recording medium by the recording medium playback unit.

The reproducing apparatus may further include a storage unit for example local storage of or configured to store a variety of units of data wherein the read out unit reads the main stream and the video data stored on the storage unit.

One of a reproducing method of a reproducing apparatus for reproducing stream data and a computer program for causing a computer to perform a playback process includes the steps of reading for example in a process of step S of a main stream for example a primary stream to be reproduced based on playback management information for example playlist containing first information containing a playback path for example a main path indicating along time axis a location of a main stream containing at least one stream reading for example in a process of step S of for storage video data for example animation data that is to be reproduced in synchronization with the main stream based on the playback management information decoding for example in a process of step S of the stored video data storing for example in a process in step S of the decoded video data reproducing for example in a playback process of a primary video stream of the read main stream by referencing a predetermined counter for example STC counter based on the playback management information and outputting for example in a process of step S of the stored decoded video data in synchronization with playback of the main stream.

A controller executes a prepared control program. The controller also reads a navigation program to be discussed later recorded on an optical disk by controlling an optical disk drive and expands the navigation program on a memory to execute the navigation program. The controller thus generally controls the reproducing apparatus . When the optical disk is loaded the controller causes a predetermined menu screen to be displayed on an external display device.

Under the control of the controller the optical disk drive reads data from the optical disk and outputs the read data to one of the controller the memory and a decoder . If information read from the optical disk by the optical disk drive is one of a navigation program and PlayList the read information is supplied to one of the controller and the memory . If the information read from the optical disk by the optical disk drive is one of an AV stream and text data the read information is output to the decoder .

The application format contains two layers of PlayList and Clip for managing an AV audio visual stream. A pair of one AV stream or text data and clip information accompanying the AV stream or the text data is handled as one object and referred to as a clip. A data file of the AV stream is referred to as an AV stream file. A data file of the clip information is referred to as a clip information file.

Files used by computers are generally handled as byte strings. A content of an AV stream file is expanded along time axis and an access point of the clip is typically specified by a timestamp in PlayList.

When the access point in the clip is specified by a timestamp in the PlayList the clip information file is used to find from the timestamp address information at which decoding of the AV stream file is to be started.

The PlayList is a set of information indicating a playback period of the AV stream. Information indicating one playback period in the AV stream is referred to as PlayItem. PlayItem is represented by a pair of an IN point playback start point and an OUT point playback end point of the playback period along time axis. PlayList is composed at least one PlayItem as shown in .

As shown in a first PlayList shown on the leftmost portion is composed of two PlayItems. The two PlayItems reference a first portion and a second portion of the AV stream contained in a first clip on the leftmost portion. A second PlayList from the left is composed of a single PlayItem. The PlayItem references the entire second clip shown on the right side. A third PlayList shown on a third position from the left is composed of two PlayItems. The two PlayItems reference a predetermined portion of the AV stream contained in the first clip and a predetermined portion of the AV stream contained in the second clip shown on the right side.

Navigation program is a program for causing the controller to control the order of playback of PlayList and interactive playback of the PlayList. The navigation program has also a function to display a menus screen on which a user enters a command to execute playback. The navigation program is described in programming language such as Java registered trademark and recorded on a recording medium such as the optical disk . The controller now executes the navigation program. If the first PlayItem contained in the first PlayList shown on the leftmost portion of is specified as information indicating a playback position the first portion of the AV stream contained in the first clip shown on the leftmost portion referenced by the first PlayItem is reproduced.

In addition to a main path specified by the PlayItem sub path information specified by a sub play item of can be contained in the PlayList of . With the SubPlayItem defined a separate data stream not multiplexed with a clip such as an MPEG 2 transport stream specified by PlayItem can be reproduced in synchronization with the AV stream.

Caption related information including a caption text file and a font file required for rendering and SubPlayItem specifying a playback period of the caption related information are prepared in association with a clip AV stream of the main path specified by PlayItem. The clip AV stream is reproduced while a caption corresponding to data described in the caption text file is displayed on a display device in a display font based on the font data written in the font file. For example dubbed in voice data of a different language and SubPlayItem corresponding to the dubbed in voice data are prepared in association with the clip AV stream of the main path specified by PlayItem. The clip AV stream is thus reproduced while the dubbed in voice data of the different language is reproduced and output at the same time.

The SubPlayItem and the corresponding data clip may be recorded on the optical disk or may be downloaded from the server via the network as additional data update data or may be acquired in a removable medium such as a removable medium to be discussed later . A method of downloading the additional data from the server will be described in detail later with reference to .

The memory stores data the controller requires to execute a variety of processes. A local storage is an HDD hard disk drive for example.

An Internet interface is connected to the network in a wired fashion or a wireless fashion. Under the control of the controller the Internet interface communicates with the server via the network and supplies data downloaded from the server to the local storage . The server downloads a content that updates the data discussed with reference to and recorded on the optical disk loaded on the reproducing apparatus . The local storage records the content downloaded from the server via the network .

The decoder decodes the AV stream or text data supplied from one of the optical disk drive and the local storage and outputs the resulting video signal and audio signal to the external display device. In response to the decoded signals from the decoder the display device outputs the content of the optical disk i.e. displaying a video and outputting an audio .

The operation input unit includes an input device including buttons keys touchpanel jogdial and the like and a receiver receiving an infrared signal transmitted from a predetermined remote commander. The operation input unit receives an operation input from a user and supplies the operation input to the controller .

The controller is connected to the drive as necessary. A removable medium is loaded on the drive . The removable medium may include one of a magnetic disk including a floppy disk an optical disk such as compact disk read only memory CD ROM or DVD a magneto optical disk such as Mini Disk MD registered trademark and a semiconductor memory.

Data recorded on the optical disk loaded on the reproducing apparatus and data stored on the local storage are reproduced as described below.

The reproducing apparatus includes the local storage such as HDD Hard Disk Drive . The reproducing apparatus connected to the network in a wired fashion or a wireless fashion stores on the local storage the content downloaded from the server via the network . The server downloads the data that updates the content such as a movie recorded on the optical disk loaded on the reproducing apparatus .

When the operation input unit is commanded to reproduce the content recorded on the optical disk with the downloaded content recorded on the local storage the controller associates the content recorded on the optical disk with the content recorded on the local storage and performs a playback process of the content.

The content on the optical disk and the content on the local storage are reproduced in association with each other as described with reference to .

For example the optical disk of may be a medium sold in package and record a movie content. Only an English caption text file for example may be recorded on the optical disk as a caption data file that can be displayed superimposed on the video of the movie content.

The AV stream of clip recorded on the optical disk and referenced by the PlayItem of the PlayList as shown in is a stream for displaying the video of the movie content and reproducing the corresponding audio. Caption related information of Clip referenced by the SubPlayItem of the PlayList is a caption text file for displaying an English caption to be superimposed on the video.

A user for example might want to view the movie content recorded on the optical disk with a caption of a language different from English. The optical disk has no recorded caption of the language different from English. In this condition the user cannot view the movie with the caption data of the language different from English.

The user then downloads a caption text file of the desired language of the movie recorded on the optical disk from the server via the network or retrieves the caption text file from the removable medium . The caption text file of Arabic for example might be downloaded or copied from the removable medium to the local storage .

When the user issues an instruction to download the caption text file of Arabic corresponding to the PlayList pre recorded on the optical disk the reproducing apparatus accesses the server and then downloads a file prepared on the server for updating the content recorded on the optical disk .

With reference to there are shown clip composed of an Arabic caption text file caption related information and a clip information file attached thereto a PlayList file updated PlayList file enabled to control playback and displaying of caption data of clip in addition to the video clip and the audio clip AV stream data and the English caption text file pre recorded on the optical disk and a new navigation program file updated from the navigation program file stored on the optical disk . These pieces of information are downloaded and stored on the local storage .

The updated PlayList includes SubPlayItem and SubPlayItem each representing a sub path in addition to PlayItem representing a main path. The PlayItem of the updated PlayList is used to reference clip containing the AV stream recorded on the optical disk . SubPlayItem is used to reference clip containing caption related information recorded on the optical disk . SubPlayItem is used to reference clip downloaded from the server together with the updated PlayList containing caption related information as the Arabic caption text file.

The new navigation program file of specifies one of SubPlayItem and SubPlayItem together with PlayItem of the updated PlayList as a playback period. A desired video is associated with audio data. With this arrangement the user can display one of the English caption defined by the English caption text file pre recorded on the optical disk and the Arabic caption defined by the Arabic caption text file not pre recoded on the optical disk whichever is desired.

When downloading from the server copying from the removable medium is performed the reproducing apparatus can reproduce and display any of clip as the English caption text file and clip as the Arabic caption text file not pre recoded on the optical disk . More specifically the user selects a desired language from caption languages displayable on a menu screen presented on the display device. The user can thus view the movie on any of English caption and Arabic caption.

The AV stream recorded on the optical disk includes a moving picture experts group MPEG 2 transport stream as shown in . Each MPEG 2 transport stream contains an integer number of aligned units. The aligned unit has a size of 6144 bytes 2048x3 bytes and starts with a first byte of a source packet. The source packet is 192 bytes long. One source packet contains TP extra header and a transport packet. TP extra header is 4 bytes long and the transport packet is 188 bytes long. One aligned unit is composed of 32 source packets. Data of a video stream or an audio stream is packetized into MPEG 2 PES packetized elementary stream and a PES packet is packetized into transport packets.

The functions of are executed when the controller performs a prepared control program or when the controller performs a navigation program recorded on the optical disk .

A menu screen display controller causes the external display device to display a menu screen. The menu screen shows buttons operated for the user to select the audio of the content recorded on the optical disk the language of the caption the angle of the video and buttons operated for the user to select an update file to be downloaded and a file to be deleted.

An operation input acquisition unit acquires a signal indicating a operation input entered by the user via the operation input unit and outputs the signal indicating the user operation input to any corresponding one of the menu screen display controller a data acquisition unit a local storage directory manager and a playback controller .

The data acquisition unit controls communications performed on the Internet interface of and information exchange with the removable medium on the drive . For example the data acquisition unit downloads the update file indicated by the user from the server and outputs the acquired file to the local storage directory manager . Upon receiving information indicating a required file from a file system merge processor to be discussed later the data acquisition unit acquires the required file from the server through downloading and outputs the acquired file to the local storage directory manager .

The local storage directory manager manages directories on the local storage controls writing of data onto the local storage reading of data from the local storage and deleting of data from the local storage . The PlayList read from the local storage under the control of the local storage directory manager is output to the memory . The audio data and the video data of the AV stream and text data of the caption text file read from the local storage are output to the decoder . When the file system merge processor merges a file system on the optical disk with a file system on the local storage the local storage directory manager outputs information relating to the file system on the local storage to the file system merge processor .

The optical disk directory manager manages directories of the optical disk and controls reading of data from the optical disk . The optical disk has author id and disc id as identification information set thereon. The identification information author id and disc id read from the optical disk under the control of the optical disk directory manager are supplied to the data acquisition unit and the local storage directory manager . The PlayList read from the optical disk under the control of the optical disk directory manager is output to the memory . The audio data and the video data of the AV stream and the text data of the caption text file read from the optical disk are output to the decoder . When the file system merge processor merges the file system on the optical disk with the file system on the local storage the optical disk directory manager outputs information relating to the file system on the optical disk to the file system merge processor . The identification information author id and disc id will be described later.

The file system merge processor merges the file system on the optical disk supplied from the optical disk directory manager and the file system on the local storage supplied from the local storage directory manager thereby creating a single virtual file system. The file system merge processor outputs the created virtual file system to the playback controller .

In a process to be discussed later the file system merge processor determines whether a deletion of several files recorded on the local storage can cause a malfunction in a link structure of files in the virtual file system in the link structure data is linked to reproduce the clip in accordance with the PlayList based on an application format of the optical disk as discussed with reference to . If the file system merge processor determines that a malfunction can take place in the link structure of the files in the virtual file system a file required to correct the malfunction is extracted. Information regarding the required file is supplied to the data acquisition unit . The required file can be downloaded as necessary.

When several files are deleted from the local storage a file that cannot be reproduced in accordance with any PlayList in the virtual file system i.e. cannot be specified by any of PlayLists occurs. In the process to be discussed later the file system merge processor commands the local storage directory manager to delete such an unnecessary file.

Whether or not to delete the unnecessary file caused in response to the deletion of files may be set by the user.

The playback controller executes the navigation program specified by the virtual file system supplied from the file system merge processor and controls playback of content. More specifically the playback controller references the PlayList supplied to and stored on the memory and controls the local storage directory manager and the optical disk directory manager to read the audio data and the video data of the AV stream and as necessary the text data of the caption text file from the optical disk and the local storage based on the virtual file system. The playback controller controls the decoder of to decode reproduce the audio data and the video data of the AV stream and as necessary the text data of the caption text file stored on one of the optical disk and the local storage .

The file system merge processor merges the file system on the optical disk with the file system for managing a data group that is downloaded from the server and recorded on the local storage . The merging operation is performed when the optical disk is loaded on the reproducing apparatus when the playback of a content recorded on the reproducing apparatus is requested when inputting or outputting of any data recorded on one of the optical disk and the local storage is requested or when the user issues a command to perform the merging operation.

A virtual file system is defined as an upper layer of a native file system of the system of the reproducing apparatus i.e. the file system of the data actually recorded on one of the optical disk and the local storage . More specifically as shown in an application program and a user handling the application program can recognize only the virtual file system as an upper layer. The application program causes the local storage to record new data by downloading the new data from the server and reproduces the data actually stored on one of the optical disk and the local storage . The virtual file system abstracts the native file system thereby hiding a native structure such as a physical device and an operating system in the reproducing apparatus .

The main functions of the virtual file system include mounting a file directory on a physical device such as the optical disk or the local storage to create a file system of a virtual disk recognized by the user and supplying a file access application programming interface API to the created virtual disk.

When the user enters an operation input requesting an access to any file recorded on one of the optical disk and the local storage the application program of can recognize only the virtual file system. A local file system and a local file system recorded on one of the optical disk and the local storage and the structure of the file system of the optical disk are hidden from the application program and the user handling the application program and can be accessed via the virtual file system.

To perform a file access request of the application program of the reproducing apparatus calls an API Application Programming Interface for file input and output provided by the virtual file system and then accesses the data stored on one of the optical disk and the local storage without being aware of the physical structure of the disk drive and the software structure of the file system. More specifically the API of the virtual file system calls in practice API of the native file system within the reproducing apparatus .

The virtual file system provides a variety of types of APIs. For example the virtual file system provides an open API for opening a specified file a close API for closing a specified file a seek API for setting a reading position or writing position of a specified file a stat API for acquiring status of a specified file a read API for reading a specified file a write API for writing a specified file etc. The application program executed by the playback controller manipulates the files stored on one of the optical disk and the local storage using these APIs.

The virtual file system has a function of dividing and managing a disk area of the local storage . As shown in the disk area of the local storage has a directory structure in which the disk area is divided into divisions for suppliers of contents content authors on a per supplier basis. Directories disc id immediately under author id are flexibly configured in a file directory structure by a content author. A description of metadata manifest data to be discussed later contained in the downloaded data defines where to place data on the local storage i.e. defines the file directory structure of the downloaded file.

In the file directory structure of the local storage author id dividing the directory is an identifier uniquely identifying an entity managing the metadata manifest data to be discussed later contained in the downloaded data. More specifically the author id identifier uniquely identifies an entity including a content producer a motion picture company or a group including a plurality of content producers and motion picture companies. An identifier disc id uniquely identifies the optical disk provided by the content producer identified by the author id identifier. These identifiers are contained in the metadata of the downloaded data. The metadata manifest data and the author id and disc id identifiers will be described later.

The file directory structure of the virtual disk accessible by the application is compatible with the file directory structure of the optical disk . More specifically the data file structure under the author id and disc id identifiers is merged with the data file structure of the optical disk . The virtual file system of the virtual disk having file directory structure compatible with the file directory structure of the optical disk is thus configured.

The virtual file system also has a function of managing manifest files to be discussed later in addition to the directory and file management function. The purpose of the virtual file system of defining fields of the metadata to a file model of a native file system is three fold i.e. to display a name representing a content rather than displaying a path or a name of a file of the local storage to prevent double updating of the same file in a download process and to define a path name in the virtual file system namely a path name during playback of the optical disk .

The virtual file system provides two functions in metadata management namely operation of a manifest file and operation of metadata. The manifest file is metadata representing a variety of attributes of the downloaded files. Manifest may be stored in a corresponding file or may be merged with one file with a manifest id identifier to be discussed later with reference to of a manifest section used as a key for identification. In either case the file is referred to as a manifest file. The reproducing apparatus storing the file downloaded to the local storage must also store a manifest file. The manifest file may be described in mark up language text such as XML.

An author id field specifies an entity managing the manifest file. More specifically the author id field specifies an identifier uniquely identifies a content producer a motion picture company or a group including a plurality of content producers and motion picture companies. The identifier is determined by referencing the author id field of a content distribution file to be discussed later with reference to . The application program or the user can freely set any value to this field.

A disc id field is used to specify an identifier uniquely identifying the optical disk to the content producer identified by the author id identifier. The identifier is determined by referencing the disc id field of the content distribution file to be discussed later with reference to . The application program or the user can freely set any value to this field.

A version field is used by a content author to manage history. History number is within an integer range from 1 to 255 and the larger the number the newer the content is. The identifier is determined by referencing the version field of the content distribution file to be discussed with reference to . Neither the application program nor the user can set freely a value to this field.

In a display name field a name easily recognizable to the user is defined here. More specifically a character string such as Japanese caption of title XXX which could be difficult to imagine from a file name alone is set in the display name field. The character string is coded in accordance with ISO IEC 10646 1 Standard.

In a source field information indicating a source of a file is described. The value in this field is coded in accordance with ISO IEC 646 Standard. In the case of network downloading a URL of a download source is described.

A permission field is used for the content author to specify whether to set approval information as a visible attribute or an invisible attribute. If 0x00 is written in an eight bit permission field the attribute of a file of metadata is invisible to the user. If 0x01 is written in the eight bit permission field the attribute of a file of metadata is visible to the user. If 0x02 is written in the eight bit permission field the attribute of a file of metadata is overwrite inhibited.

A src file name field contains information that uniquely identifies where the corresponding file is recorded in the directory structure of the file system of the local storage . More specifically this field specifies a path name representing a path identifying a file with a file location in the hierarchical layer structure of the file system of the local storage . Names of the file and directory representing the path name are coded in accordance with ISO IEC 646 Standard.

A dst file name field contains information that uniquely identifies where the corresponding file is recorded in the directory structure at a bind destination in a virtual disk of the file actually recorded on the local storage . More specifically this field specifies a path name representing a path identifying a file with a file location in the hierarchical layer structure of the virtual file system. Names of the file and directory representing the path name are coded in accordance with ISO IEC 646 Standard.

The virtual file system defines API for reading the content of the manifest file without disclosing the file name the file location or the physical structure of the manifest file to the application program or the user.

More specifically the application program or a resident program to be executed by the reproducing apparatus can indirectly access the manifest file by calling the following APIs 

In practice detailed definition of API such as type information needs to be modified depending on programming language specifications of software execution environment of the reproducing apparatus .

A directory named BDMV is arranged under the root directory of the optical disk . Under the directory BDMV a file named Index.bdmv and a file named MoveObject.bdmv are stored. Hereinafter these files are referred to as an Index file and a MoveObject file respectively as appropriate. Each file is referred to as a file name followed by file and each directory is referred to as a directory name followed by directory .

The Index file contains information relating to a menu for the playback of the optical disk . The reproducing apparatus causes a display device to display a playback menu screen based on the Index file. The playback menu screen shows items for reproducing all contents on the optical disk reproducing a particular chapter only reproducing repeatedly a particular chapter and displaying an initial menu. MovieObject that is executed with any item selected is set in the Index file. When a user selects one item from the playback menu screen the reproducing apparatus executes a MoveObject command set in the Index file.

The MovieObject file includes MovieObject. MovieObject includes a command controlling the playback of the PlayList recorded on the optical disk . The reproducing apparatus selects and executes one of MovieObjects recorded on the reproducing apparatus thereby reproducing the content recorded on the optical disk .

An application program interface API for reproducing animation data to be discussed later is defined. The MovieObject includes a command to invoke an API for reproducing the animation data. For example when an animation is displayed in synchronization with AV data reproduced by a given PlayList the MovieObject containing the command for invoking the API application based on the provided API for reproducing the animation data is executed. In this way the API application based on the provided API is invoked and executed and the animation is reproduced and displayed in synchronization with the AV data.

Arranged further under the BDMV directory are a directory named BACKUP BACKUP directory a directory named PLAYLIST PLAYLIST directory a directory named CLIPINF CLIPINF directory a directory named STREAM STREAM directory and a directory named AUXDATA AUXDATA directory .

The PLAYLIST directory stores a PlayList file. Each PlayList file name is composed of a file name of a five digit number with an extension .mpls attached thereto as shown in .

The CLIPINF directory stores a clip information file. Each clip information file is composed of a file name of a five digit number with an extension .clpi attached thereto as shown in .

The STREAM directory stores a clip AV stream file and a substream file. Each stream file has a file name of a five digit number with an extension .m2ts attached thereto as shown in .

The AUXDATA directory stores files of data not contained in but referenced from the clip AV stream file and the substream file and data used separately from the clip AV stream and the substream file. As shown in the AUXDATA directory stores a caption font file named 11111.otf and an effect sound file named sound.bdmv. 

A graphical animation data file in JPEG format is also stored in the AUXDATA directory. The graphical animation data is reproduced by initiating Java application based on the API for reproducing the animation data.

By defining the API for reproducing the animation data the reproducing apparatus sets an animation frame for displaying animations in a format different from the format of the stream file such as video stream. For example the reproducing apparatus can thus display graphical animations based on Java application in synchronization with the AV content data.

Since the data in a coding scheme different from that of an AV content is handled as video data that can be mixed with the AV content the freedom of authoring is increased.

The animation is described in a format such as Java different from that of the stream file of the video stream. Buffer capacity required by the reproducing apparatus is smaller than when an animation frame is prepared in the same data file structure as the video. Cost reduction and compact design are thus easily implemented in the reproducing apparatus .

The optical disk stores the author id and disc id identifiers in the form of secure electronic data that cannot be rewritten by the user or in the form of physical pits. The author id identifier identifies a content author also referred to as title author of a content manufacturer of the optical disk such as a production company or a distributing agency of a movie. The disc id identifier identifies the type of the optical disk manufactured by the title author identified by the author id identifier.

At least one directory named author id is arranged under the root directory of the local storage . At least one directory named disc id is arranged under the author id directory. The disc id directory includes a set of manifest sections or a manifest file composed of one manifest section. The structure of the other directories and files is freely set by the content author. The other directories and files may have the same file directory structure as the one of the optical disk discussed with reference to or may have the one as discussed with reference to which is quite different from the file directory structure discussed with reference to .

As shown in the disc id directory includes in addition to the manifest file a plurality of directories including a MainMovie directory a SubTitle directory and an AUXDATA directory. Those directories may further contain folders and files.

The file directory structure of the local storage of is invisible to the application program executed by the reproducing apparatus or the user.

For example in the manifest section of MainMovie movie01 main.r1.jp.mp2 as the path name thereof might be specified in the src file name field and STREAM 01002 m2ts as the path name thereof might be specified in the dst file name field. As shown in the downloaded data is recorded in a file name of main.r1.jp.mp2 in a movie01 directory within the MainMovie directory under the author id and disc id identifiers in the local storage . In the virtual file system of the virtual disk the downloaded data is handled as a file named 01002.m2ts in the STREAM directory.

In this way the content author can specify the path name of the local storage in the src file name field and the path name in the virtual file system of the virtual disk in the dst file name field of the manifest section of the downloaded package. If the path name adapted to the virtual file system in the virtual disk is set in the dst file name field the content author can freely set a file directory structure under disc id of the data actually recorded on the local storage and newly add directories and files under areas identified by the disc id identifier in the reproducing apparatus .

If the dst file name field in the manifest section remains blank at the downloading of an actual file that file cannot be referenced from the application program being executed by the reproducing apparatus in other words the application program being executed by the reproducing apparatus and the user cannot recognize the presence of that file . The actual file is stored on the local storage and the actual file is correctly recognized in the file system of the local storage . With the dst file name field left blank the file is considered as being absent from the virtual file system. That file is thus hidden from the application program of the reproducing apparatus and the user.

This feature is taken advantage of. An actual file is downloaded with the dst file name field blanked in the manifest section. Later in the future a manifest section having the same manifest id and a predetermined path name written in the dst file name field is downloaded again to overwrite the manifest section. The application program to be executed by the reproducing apparatus thus operates in the same way as the actual file is downloaded at the same timing as the downloading of the new manifest section.

For example a plurality of bonus tracks was downloaded at a time or delivered in a predetermined recording medium and later only the manifest section containing the dst file name field is downloaded for overwriting periodically so that the application program recognizes different bonus tracks. In this arrangement the user enjoys services in which different bonus tracks are added from time to time without the need for downloading frequently a vast amount of data.

In the synchronization binding between the actual file system of the optical disk and the local storage and the file system of the virtual disk regardless of whether it is a so called static binding system or a dynamic binding system a new API for updating the virtual file system for example a update may be defined. When that API is called in response to a user operation or explicitly by the application program the virtual file system is updated.

In the static binding the actual file systems in the optical disk and the local storage are referenced at the moment the optical disk is loaded on the reproducing apparatus or at the timing of the switching of reproduction title in order to map the file directory structure in the virtual file system. In the dynamic binding required files are searched for at the moment a file input and output request is issued.

The file directory structure of the virtual disk preferably matches the file directory structure of the optical disk . The file directory structure of the optical disk is formulated by standards and typically cannot be modified. Preferably the structure of actual directories and files in the local storage is freely set by the content author. If the file directory structure of the virtual disk is set based on the fixed file directory structure of the optical disk a playback process is performed in compliance with standards such as the application format of the optical disk while maintaining the freedom of data distributed by the content author at the same time.

A directory named BDMV is arranged under the root directory in the file directory structure of the virtual disk of . Under that directory there are arranged a file named Index.bdmv and a file named Movieobject.bdmv .

The Index file contains information relating to a menu for reproducing a content that is stored on the optical disk and the local storage and handled by the application program as the one being recorded on the virtual disk. The reproducing apparatus causes the display device to display the playback menu screen in accordance with the Index file. The playback menu screen may show items for reproducing all contents on the optical disk reproducing a particular chapter only reproducing repeatedly a particular chapter and displaying an initial menu. MovieObject that is executed with any item selected is set in the Index file. When a user selects one item from the playback menu screen the reproducing apparatus executes a MoveObject command set in the Index file.

The MovieObject file includes MovieObject. MovieObject includes a command controlling the playback of PlayList that is handled as being recorded on the virtual disk. The reproducing apparatus selects and executes one of MovieObjects that are handled as being recorded on the virtual disk thereby reproducing the content that is handled as being recorded on the virtual disk.

Arranged under the BDMV directory are a directory named BACKUP BACKUP directory a directory named PLAYLIST PLAYLIST directory a directory named CLIPINF CLIPINF directory a directory named STREAM STREAM directory and a directory named AUXDATA AUXDATA directory .

The BACKUP directory stores files and data to back up files and data to be handled as being recorded on the virtual disk.

The PLAYLIST directory stores a PlayList file. Each PlayList file name is composed of a file name of a five digit number with an extension .mpls attached thereto in the same way as in the optical disk .

The CLIPINF directory stores a clip information file. Each clip information file is composed of a file name of a five digit number with an extension .clpi attached thereto in the same way as in the optical disk .

The STREAM directory stores a clip AV stream file and a substream file. Each stream file has a file name of a five digit number with an extension .m2ts attached thereto in the same way as in the optical disk .

The AUXDATA directory stores files of data not contained in the clip AV stream file and the substream file handled as being recoded on the virtual disk but referenced from the clip AV stream file and the substream file and files of data used separately from the clip AV stream file and the substream file. As in the above described optical disk a caption font file a sound effect file and graphical animation data animation frame are recorded in the AUXDATA directory.

As previously discussed the reproducing apparatus accepts the animation frame for displaying animation having a format different from that of the video stream file and a graphical animation described on a Java application is displayed in synchronization with the AV content data.

Since the data in a coding scheme different from that of an AV content is handled as video data that can be mixed with the AV content the freedom of authoring is increased.

The animation is described in a format such as Java different from that of the stream file of the video stream. Buffer capacity required by the reproducing apparatus is smaller than when an animation frame is prepared in the same data file structure as the video. Cost reduction and compact design are easily implemented in the reproducing apparatus .

Information indicating a file on the menu screen displayed to the user has a name typically specified in a display name field. The file directory structure of the virtual disk discussed with reference to is not hidden in nature from the application program and the user. Depending on the application program executed by the reproducing apparatus the file directory structure of the virtual disk may be displayed to the user.

The definition of the content distribution file format the content author uses to distribute the content is described with reference to . The file format for content distribution may be individually determined on a per content file unit basis. Alternatively the file format may be an archive type containing metadata manifest as shown in .

A package header section and a package body section in archive may take text expression of mark up language such as XML.

When the content author distributes contents on a per file unit basis metadata manifest is handled as an independent binary file or text file. In other words an appropriate state needs to be described in the manifest associated with a content distributed on a per file unit basis in view of a directory structure expected subsequent to file addition.

A compression type field is used to specify a compression method of data within the package body . If zero is specified in this field data within the package body is non compressive type.

An encryption type field is used to specify a scramble encryption method of data within the package body . If zero is specified in this field the data within the package body is non scrambled type clear text .

As for the order of scrambling and compression of the data in the package body a compression process is performed first followed by a scrambling process.

After archive data is downloaded the manifest section may be stored on a per file unit basis on a per archive data unit basis on the local storage . Alternatively the manifest section may be merged with a file with the manifest id identifier of a manifest section used as a key for identification.

An author id field is a field in which the content author specifies an identifier uniquely identifying a content producer.

A disc id field is a field in which the content author specifies an identifier uniquely identifying the optical disk of a particular content producer. This archive is update data for the optical disk specified by the disc id identifier.

A version field is a field the content author uses to manage history. History number is represented by a number from 1 to 255 and the larger the number the newer the content is.

In a source field a source URL of a file associated with the manifest is described. The value in this field is coded in accordance with ISO IEC 10646 1 Standard.

In a display name field a name easily recognizable to the user is defined here. More specifically a character string such as Japanese caption of title XXX which could be difficult to imagine from a file name alone is set in the display name field. The character string is coded in accordance with ISO IEC 10646 1 Standard.

A permission field is used for the content author to specify whether to set approval information as a visible attribute or an invisible attribute. The values specifiable for the permission field remain unchanged from the values discussed with reference to .

An src file name field is used to specify a path name of a file to be recorded on the local storage as previously discussed with reference to . The file directory name is encoded in accordance with ISO IEC 646 standard.

A dst file name field is used to specify a path name of a file at a binding destination in the virtual disk virtual file system as previously discussed with reference to . The file directory name is encoded in accordance with ISO IEC 646 Standard.

The data of having the described content distribution file format is downloaded and the reproducing apparatus merges the downloaded data with the data recorded on the loaded optical disk to construct a virtual file system in the virtual disk. The user who reproduces a content recorded on the optical disk using the reproducing apparatus feels that the optical disk is updated with bonus tracks and sounds or captions of different language sounds added to the contents recorded on the optical disk .

If the contents having the above described format are updated new data files are downloaded for binding in the virtual file system discussed with reference to . For example at least one of an Index file Index.bdmv a MovieObject file Movieobjects.bdmv a PlayList file .mpls a ClipInformation file .clpi and a STREAM file and AUXDATA file .m2ts .bdmv and .otf is added or updated. The various types of additions defined by above referenced operation type such as the addition of MainPath and SubPath are executed so that the above described files are downloaded and reproduced in association with the contents recorded on the optical disk .

As shown in the controller reads a PlayList file from the optical disk a recording medium such as a Blu ray disk or DVD via the optical disk drive or from the local storage and reads an AV stream or AV data from the optical disk a recording medium such as a Blu ray disk or DVD via the optical disk drive or from the local storage in accordance with the information of the PlayList file. Using the operation input unit the user issues a command to switch audio or caption to the controller . The controller is supplied with information of initial language setting of the reproducing apparatus by a storage unit not shown .

The PlayList file contains a variety of pieces of playback information in addition to information regarding Main Path and Sub Path. The controller reads from the optical disk via the optical disk drive or from the local storage a main Clip AV stream file hereinafter referred to as main Clip referenced by a PlayItem contained in the PlayList file a sub Clip AV stream file hereinafter referred to as sub Clip referenced by a SubPlayItem and text sub title data and animation data each referenced by the SubPlayItem. The main Clip referenced by the PlayItem and the sub Clip referenced by the SubPlayItem may be stored on different recording media. For example the main Clip may be recorded on a recording medium while the corresponding sub Clip may be stored on the local storage after being supplied via a network not shown . The controller may select and reproduce an elementary stream corresponding to a playback function thereof or may select and reproduce an elementary stream corresponding to the information about the initial language setting of the reproducing apparatus .

The AV decoder includes buffers PID filter PID filter switches PID filter pre load buffer animation decoder decoded object buffer composition buffer animation scheduler background decoder first video decoder second video decoder presentation graphics decoder interactive graphics decoder first audio decoder second audio decoder text sub title composition decoder switch switch background plane generator video plane generator presentation graphics plane generator interactive graphics plane generator buffer video data processor mixing processor and mixing processor .

The first video decoder decodes a primary video stream while the second video decoder decodes a secondary video stream. The first audio decoder decodes an audio stream primary audio stream while the second audio decoder decodes an audio stream secondary audio stream .

The reproducing apparatus includes the two video decoders the first video decoder and the second video decoder to decode the two video streams and the two audio decoders the first audio decoder and the second audio decoder to decode the two audio streams. If there is no need to distinguish between the first video decoder and the second video decoder each video decoder is referred as a video decoder . If there is no need to distinguish between the first audio decoder and the second audio decoder each audio decoder is referred to as an audio decoder .

File data read by the controller is decoded and error corrected by an error correcting code ECC decoder not shown into a multiplexed stream. Under the control of the controller the switch selects the decoded and error corrected data by stream type and then supplies the selected data to corresponding buffers .

The main Clip AV stream is a stream such as a transport stream into which video and at least one of audio bit map caption presentation graphics stream and interactive graphics are multiplexed. The sub Clip AV stream is a stream into which at least one of audio bit map caption presentation graphics stream and interactive graphics is multiplexed. The animation data may be data described in a data format such as Java different from a multiplexed data stream like a transport stream. In other words the knowledge and development skill of MPEG 2 transport stream are not required to generate animation data to be reproduced in synchronization with main video data on the reproducing apparatus . The data text sub title data file Text ST may or may not be in a multiplexed stream form such as a transport stream.

The reproducing apparatus reads the file data from the optical disk or other recording medium via the optical disk drive or from the local storage and reproduces video bit map caption interactive graphics animation and audio.

From among data animation data is read from the optical disk drive recording medium or the local storage and then subjected to a decode process. When the main Clip the sub Clip and the text sub tilt data are read from the optical disk drive recording medium or the local storage respective files may be read in a time division manner or the sub Clip and the text sub tilt data may be pre loaded to all buffers buffers and before the sub Clip and the text sub tilt data are read from the main Clip.

More specifically the switch is controlled by the controller so that the animation data that is read first in response to a command from a user is supplied to the pre load buffer .

Under the control of the animation scheduler the pre load buffer buffers the animation data supplied from the switch and then supplies the animation data to the animation decoder . The animation decoder under the control of the animation scheduler decodes the supplied animation data and then supplies a decoded object to the decoded object buffer .

In order to synchronize the playback of the video data of the main Clip primary stream with the playback of the animation the animation scheduler references an STC counter not shown that is referenced by the video decoder and controls the operation of the pre load buffer the animation decoder the decoded object buffer and the composition buffer .

As shown in supplied animation frames include at least one picture frame and are not necessarily prepared for all time domains of video frames. As shown the animation frames are displayed during a predetermined animation playback time and not displayed during an animation interval. The animation frame is then displayed again during the next animation playback time.

Timing of the decode process for the playback of the main Clip video data primary video stream cannot be predicted because the timing depends on an image of each frame. The animation frames are buffered and decoded beforehand and then stored on the decoded object buffer . In accordance with IN time and OUT time of the main Clip video data primary video stream the animation scheduler transfers the decoded animation data on the decoded object buffer to the composition buffer .

When playback of the animation frame starts the composition buffer under the control of the animation scheduler acquires a graphics plane that has been just generated by the interactive graphics plane generator and stores for backup the graphics plane as data to be mixed extracts an image of a target portion of the animation frame supplied from the decoded object buffer alpha blends the extracted image and the stored graphic object and transfers the blended image to the interactive graphics plane generator .

Referring to T represents a pre load time during which all animation frames are pre loaded at a time to the pre load buffer . T represents a decode time during which all animation frames are decoded in the process of the animation decoder . T represents a transfer time during which the content of graphics plane is transferred from the interactive graphics plane generator to the composition buffer immediately prior to animation start. T represents the sum of a time for alpha blending of one animation frame by the composition buffer and a transfer time of the blending result to the interactive graphics plane generator . T represents a presence time of one animation frame in the interactive graphics plane generator .

Times T through T take different parameters depending on the hardware structure of the reproducing apparatus . Furthermore times T through T are parameters specified by applications.

The animation frame is pre loaded onto the pre load buffer and then copied to the animation decoder rather than being transferred to the animation decoder the data of the animation frame remains on the pre load buffer . The pre load buffer may store the pre loaded animation frame until a next animation frame is supplied. The supply of the decoded animation frame from the decoded object buffer to the composition buffer is performed as a copying operation rather than a transfer operation the decoded animation frame remains on the decoded object buffer . The decoded object buffer may store the decoded animation frame until a next decoded frame is supplied. Furthermore the supply of the alpha blended frame data from the composition buffer to the interactive graphics plane generator may be performed as a copying operation rather than a transfer operation with the original blended frame data remaining on the composition buffer .

The application can specify parameters such as an image to be displayed as an animation frame an animation start time indicated by PTS presentation time stamp of a video stream an animation end time indicated by the PTS of the video stream and a parameter of a frame rate of animation.

The size of the animation frame to be processed with respect to the animation frame rate is determined by a data transfer rate copying speed of data from the composition buffer to the interactive graphics plane generator and a processing speed of alpha blending per pixel unit in the composition buffer .

The animation frame rate and the total number of usable frames with respect to the size of the animation frame corresponding to the animation frame rate are determined by the buffer capacity of the decoded object buffer .

More specifically the following equation 1 must be satisfied 1 where T n is described by equation 2 and satisfies equation 3 N n is the total number of graphics objects used in an n th animation and f n is a frame rate s of the n th animation animation end time animation start time 2 0 3 where nimation start time n is the start time of the n th animation and animation end time n is the end time of the n th animation.

The animation interval must satisfy the following equation 4 animation end time 1 2 3 4 animation start time 1 4 

The following equation 5 namely equation 6 also must be satisfied. 2 8 and 2 8 max 5 2 8 max 6 where Rd is a data transfer rate data copying speed bits s of the reproducing apparatus Rp is an alpha blending process rate per pixel pixels s of the reproducing apparatus and BPP is a color depth bits pixel of the graphics object. S n is the sum of sizes of the all animation graphics objects namely represented by SIZE object 1 SIZE object 2 . . . SIZE object N n where SIZE gfx is a function that provides the size of graphics object gfx in bytes. Smax n is represented by MAXSIZE object 1 SIZE object 2 . . . SIZE object N n wherein MAX is a function that provides the maximum value of the object trains in bytes.

If DEC TIME gfx is a function that provides a decode time of animation graphics object gfx in seconds the following equation 7 must also be satisfied  TIME object 1  TIME object 2 . . .  TIME object 2 7 

Furthermore the following equation 8 must also be satisfied SIZE Decoded Object Buffer 8 where SIZE Decoded Object Buffer represents the buffer capacity of the decoded object buffer .

With reference to timing at which the animation frame is pre loaded to the pre load buffer is described below.

In the playback of the sequential movie shown in image data of an animation frame to be reproduced in synchronization with the primary video streams of PlayItem and PlayItem is pre loaded prior to the start of the playback of the PlayItem . Animation is then reproduced at a predetermined playback position in synchronization with the primary video streams of the PlayItem and the PlayItem . If different PlayItem is concatenated with the PlayItem and the PlayItem in a non seamless fashion image data of the an animation frame to be reproduced in synchronization with the primary video stream of the PlayItem is pre loaded prior to the playback of the primary video stream of the PlayItem .

If the PlayItem is concatenated with the PlayItem and the PlayItem in a seamless fashion the animation frame to be reproduced in synchronization with the primary video stream of the PlayItem is also pro loaded prior to playback of the first PlayItem.

When PlayItems are concatenated in a non seamless fashion in the playback of the interactive movie branching type as shown in image data of the animation frames can be pre loaded on a per PlayItem basis prior to playback. However if the PlayItems are concatenated in a seamless fashion the image data of the animation frame can be pre loaded only prior to the playback of the first PlayItem.

When an animation frame is expanded in size only with the top left origin thereof fixed as shown in re rendering process is not activated. To alpha blend with a background image the composition buffer stores for backup the graphics plane immediately prior to the start of animation display in an overlay area maximum overlay area in the expansion of the animation frame from the interactive graphics plane generator .

As shown in the re rendering process is not activated when an animation frame is contracted in size only with the top left origin thereof fixed as shown in . To alpha blend with a background image the composition buffer stores for backup the graphics plane immediately prior to the start of animation display in an overlay area maximum overlay area in the expansion of the animation frame from the interactive graphics plane generator .

When the animation frame is shifted as shown in the re rendering process is activated on an overlay area. To alpha blend with a background image the composition buffer stores for backup the graphics plane immediately prior to the start of animation display of a rectangular area as a passing zone all overlay areas from the interactive graphics plane generator .

Returning to the switch controlled by the controller supplies background image data to the buffer main Clip data to the buffer sub Clip data to the buffer and text sub title data to the buffer . The buffer buffers the background image data the buffer buffers the main Clip data the buffer buffers the sub Clip data and the buffer buffers the text sub title data.

The data read from the buffer for buffering the background image data is supplied to the background decoder at a predetermined timing. The background decoder decodes the background image data and supplies the decoded background image data to the background plane generator .

The stream data read from the buffer as a main Clip AV stream read buffer is output to the subsequent stage PID packet ID filter at a predetermined timing. The PID filter sorts the input main Clip AV stream into streams by PID packet ID and outputs the sorted streams to respective decoders for elementary streams. More specifically the PID filter supplies a video stream to the PID filter serving as a supply source to one of the first video decoder and the second video decoder a presentation graphics stream to the switch serving as a supply source to the presentation graphics decoder an interactive graphics stream to the switch serving as a supply source to the interactive graphics decoder and an audio stream to the switch serving as a supply source to one of the first audio decoder and the second audio decoder .

The stream data read from the buffer serving as a sub Clip AV stream read buffer is output to the subsequent stage PID packet ID filter . The PID filter sorts the input sub Clip AV stream by PID and outputs the sorted streams to the respective decoders of the elementary streams. More specifically the PID filter supplies a video stream to the PID filter serving as a supply source to one of the first video decoder and the second video decoder a presentation graphics stream to the switch serving as a supply source to the presentation graphics decoder an interactive graphics stream to the switch serving as a supply source to the interactive graphics decoder and an audio stream to the switch serving as a supply source to one of the first audio decoder and the second audio decoder .

The PID filter receives one of the video stream contained in the main Clip supplied from the PID filter and the video stream contained in the sub Clip supplied from the PID filter . Under the control of the controller the PID filter determines whether the input is a primary video stream or a secondary video stream and then supplies the primary video stream to the first video decoder and the second video stream to the second video decoder .

The video streams sorted by the PID filter are then supplied to the subsequent first video decoder and second video decoder . Each of the first video decoder and the second video decoder decodes the supplied video stream and then supplies decoded video data to the video plane generator .

The first video decoder is a decoder for decoding the primary video stream and the second video decoder is a decoder for decoding the secondary video stream. The first audio decoder is a decoder for decoding the audio stream primary audio stream and the second audio decoder is a decoder for decoding the audio stream secondary audio stream .

The reproducing apparatus includes the two video decoders the first video decoder and the second video decoder to decode the two video streams and the two audio decoders the first audio decoder and the second audio decoder to decode the two audio streams. If there is no need to discriminate between the first video decoder and the second video decoder each video decoder is simply referred to as video decoder . If there is no need to discriminate between the first audio decoder and the second audio decoder each audio decoder is referred to as audio decoder .

The switch selects one from the presentation graphics stream contained in the main Clip supplied from the PID filter and the presentation graphics stream contained in the sub Clip supplied from the PID filter and supplies the selected presentation graphics stream to the subsequent presentation graphics decoder . The presentation graphics decoder decodes the presentation graphics stream and supplies the data of the decoded presentation graphics stream to the switch serving as a supply source to the presentation graphics plane generator .

The switch selects one from the interactive graphics stream contained in the main Clip supplied from the PID filter and the interactive graphics stream contained in the sub Clip supplied from the PID filter and supplies the selected interactive graphics stream to the subsequent interactive graphics decoder . The interactive graphics stream supplied to the interactive graphics decoder is a stream separated from the main Clip AV stream or the sub Clip AV stream.

The interactive graphics decoder decodes the interactive graphics stream and supplies data of the decoded interactive graphics stream to the switch serving as a supply source of the interactive graphics plane generator .

The switch selects one from the audio stream contained in the main Clip supplied from the PID filter and the audio stream contained in the sub Clip supplied from the PID filter and supplies the selected audio stream to one of the first audio decoder and the second audio decoder . The audio stream supplied to the first audio decoder is a stream separated from one of the main Clip and the sub Clip. The audio stream supplied to the second audio decoder is also a stream separated from one of the main Clip and the sub Clip. If the audio stream and the audio stream are contained in the main Clip the PID filter filters the audio stream and the audio stream in accordance with PID of the audio stream and then supplies the filtered audio stream to the switch .

For example the switch operates to supply the audio stream supplied from the PID filter to the first audio decoder and the audio stream supplied from the PID filter to the second audio decoder .

The first audio decoder decodes the audio stream and supplies data of the decoded audio stream to the mixing processor . The second audio decoder decodes the audio stream and supplies the decoded data of the decoded audio stream to the mixing processor .

If the audio stream and the audio stream are reproduced in an overlay mode if two audio streams are selected as audio stream to be reproduced by the user the audio stream decoded by the first audio decoder and the audio stream decoded by the second audio decoder are supplied to the mixing processor .

The mixing processor mixes superimposes the audio data from the first audio decoder and the audio data from the second audio decoder and supplies the mixed audio data to the subsequent mixing processor . In this embodiment of the present invention mixing superimposition of the audio data from the first audio decoder and the audio data from the second audio decoder is also referred to as synthesis. Synthesis thus means mixing of two pieces of audio data.

The sound data selected by the switch is supplied to the buffer . The buffer supplies the sound data to the mixing processor at a predetermined timing. The mixing processor mixes superimposes or synthesizes the audio data mixed by the mixing processor i.e. the audio data that is obtained by mixing the audio data output from the first audio decoder and the audio data output from the second audio decoder with the sound data supplied from the buffer and then outputs the mixed audio data as an audio signal.

Data read from the buffer serving as the text sub title read buffer is output to the subsequent text sub title composition decoder at a predetermined timing. The text sub title composition decoder decodes the Text ST data and supplies the decoded Text ST data to the switch .

The switch selects between the presentation graphics stream decoded by the presentation graphics decoder and the text sub title data decoded by the text sub title composition decoder and then supplies the selected data to the presentation graphics plane generator . Caption image supplied to the presentation graphics plane generator is one of the output of the presentation graphics decoder and the output of the text sub title composition decoder .

The switch selects one of the data of the interactive graphics stream decoded by the interactive graphics decoder and animation data supplied from the composition buffer and then supplies the selected data to the interactive graphics plane generator . The animation data is composed by the composition buffer at a playback timing. Upon receiving the animation data from the composition buffer the switch supplies the animation data to the interactive graphics plane generator .

The presentation graphics stream input to the presentation graphics decoder is a stream separated from the main Clip and the sub Clip as selected by the switch .

When a video image is displayed in a contracted scale based on the background image data supplied from the background decoder the background plane generator generates a background plane serving as a wall paper image and then supplies the background plane to the video data processor .

When the video data is supplied from the first video decoder and the second video decoder the video plane generator under the control of the controller generates a video plane by synthesizing the supplied video data and supplies the video plane to the video data processor . When the video data is supplied by the first video decoder only the video plane generator generates a video plane based on the supplied video data and then supplies the video plane to the video data processor . Synthesizing two pieces of video data is also referred to as superimposing or mixing two pieces of video data.

In response to the data selected and supplied by the switch one of the presentation graphics stream and the text sub title data the presentation graphics plane generator generates a presentation graphics plane as a rendering image and then supplies the presentation graphics plane to the video data processor .

In response to data selected and supplied by the switch one of the data of the interactive graphics stream supplied from the interactive graphics decoder and the animation frame supplied from the composition buffer the interactive graphics plane generator generates an interactive graphics plane and supplies the generated interactive graphics plane to the video data processor .

The video data processor mixes the background plane from the background plane generator the video plane from the video plane generator the presentation graphics plane from the presentation graphics plane generator and the interactive graphics plane from the interactive graphics plane generator and outputs the mixed planes as a video signal. The mixing processor mixes synthesizes or superimposes the audio data from the mixing processor the audio data that is obtained by mixing the audio data decoded by the first audio decoder and the audio data decoded by the second audio decoder and the sound data from the buffer and outputs the mixed data as an audio signal.

The switches and switches and operate in response to the selection input on the operation input unit by the user or a file containing data to be processed. For example if an audio stream is contained in the sub Clip AV stream file only the switch is set to a sub side.

The decoder discussed with reference to performs a playback process under the control of the controller .

As discussed above the decoder in the reproducing apparatus includes the pre load buffer the animation decoder the decoded object buffer the composition buffer and the animation scheduler . The decoder thus reproduces a graphic animation in synchronization with the video frame.

In typical applications an AV content such as a movie of a main path is accompanied by a comment of a director or a director explains an individual scene while pointing to the individual scene on a screen or a real time gaming is performed with a main AV reproduced as background.

Data required to reproduce animation animation frame is buffered and then decoded beforehand. An animation frame of the data buffered on the decoded object buffer is randomly accessed when the animation scheduler references a count at an STC counter used by the video decoder. However a jump playback to a different PlayList or a different PlayItem cannot be performed.

As previously discussed the reproducing apparatus the animation frame required for animation playback is pre loaded on the pre load buffer and decoded beforehand. When the animation scheduler references the STC counter not shown the animation frame displayed in synchronization with a specified video frame is transferred to the interactive graphics plane generator .

In actual design a technique of double buffering or triple buffering may be introduced in the interactive graphics plane generator to prevent flickering in animation display.

As shown in the interactive graphics plane generator contains a back graphics plane and a front graphics plane . A buffering controller controls data inputting to and data outputting from each of the back graphics plane and the front graphics plane . More specifically after a mixing process is completed in the front graphics plane the mixed data is output from the front graphics plane . While the mixed data is being output from the front graphics plane data is supplied to the back graphics plane for the mixing process. Data input and data output are then reversed between the two planes when the output of the mixed data from the front graphics plane and the mixing process in the back graphics plane are completed.

The interactive graphics plane generator thus constructed prevents the animation display from being flickered.

The process for the above referenced animation display namely the process of the controller performed on the pre load buffer the animation decoder the decoded object buffer the composition buffer and the animation scheduler is initiated by animation as API for initiating video synchronized animation.

The specific syntax of the API is different depending on the language specifications of the platform of the reproducing apparatus . An application program or a resident program executed by the reproducing apparatus can thus control animation display by calling the following APIs.

Mode This argument specifies one of normal mode and sprite mode. When the normal mode is specified by the argument Mode one image file corresponds to one animation frame. When the sprite mode is specified by the argument Mode a plurality of animation frames are extracted from a single image file.

filenames This argument is a character string type argument. An image file specified by filenames and required for animation is pre loaded and expanded. Using filenames a plurality of file names can be specified.

PlayList id This argument specifies a string of PlayList When a plurality of PlayLists are specified PlayLists need to be specified in the order of playback.

PlayItem id This argument specifies a string of PlayItems. When a plurality of PlayItems are specified PlayItems need to be specified in the order of playback. If a plurality of PlayList id are specified the argument PlayItem id cannot specify value.

start PTS This argument specifies PTS of a video frame at the start time of animation. The value of start PTS falls within presentation time of video as previously discussed.

end PTS This argument specifies PTS of the video frame at the end time of animation. As the value of start PTS the value of end PTS falls within the range of presentation time of video.

frame rate This argument specifies a frame rate of animation and is an integer multiple of a video frame rate of synchronized video.

width This argument specifies a width of the animation frame a width of the image frame of original data rather than a width of display .

height This argument specifies a height of the animation frame a height of the image frame of the original data rather than a height of display .

X This argument represents a display position of animation for example X coordinate or X coordinate string of the top left corner of the animation in the generated presentation graphics plane or in the display screen .

Y This argument represents a display position of animation for example Y coordinate or Y coordinate string of the top left corner of the animation in the generated presentation graphics plane or in the display screen .

scaling factor This argument represents a string of a measure of the size of animation data scaling factor shown in the generated presentation graphics plane or in the display screen with respect to the size of the animation frame.

With these API arguments authoring process is performed by simply calling the API in the application program.

With this arrangement the animation frame described using Java can be reproduced in synchronization with the video data reproduced as stream data on the reproducing apparatus .

In comparison with the known HDMV graphics stream used to display graphics in synchronization with a video frame in the MPEG 2 transport stream format the reproducing apparatus is free from video format limitation and compression format limitation. The format of the image to be reproduced in synchronization is flexibly introduced. The authoring process is so simple as to call the API in the application program.

Frame synchronized animation is thus developed with low development cost and provided based on general graphics objects such as JPEG images and the definition of the control API. With API driven animation a content producer and a content provider can produce and distribute video synchronized animation without expert knowledge about MPEG 2 transport stream.

On a later date animation data may be easily supplied over the network such as the Internet to be reproduced in accordance with an already distributed content. The development of the data to be supplied on a later date requires no expert knowledge about MPEG 2 transport stream for example.

When the HDMV graphics stream is used as a data format of an image to be reproduced in synchronization with a video stream on the reproducing apparatus of one embodiment of the present invention all data can be read at a time or on a per source packet basis. Reading is thus flexibly performed.

In step S the operational input acquisition unit in the controller determines based on a signal supplied from the operation input unit whether a command for a file based addition process i.e. a command to start an addition process of adding a file contained in a directory identified by a predetermined disc id has been received from a user. If it is determined in step S that the command to start the file addition process has not been received step S is repeated until it is determined that the command to start the file addition process has been received.

If it is determined in step S that the command to start the file addition process has been received the local storage directory manager in the controller controls the data acquisition unit in step S thereby accessing the server via the Internet interface and the network to transmit information indicating the status of the current virtual file system such as the manifest id identifier of the manifest section to the server .

In step S the data acquisition unit controls the Internet interface thereby determining whether information corresponding to the list of downloadable files has been received from the server via the network .

If it is determined in step S that the information corresponding to the list of downloadable files has not been received the menu screen display controller controls in step S displaying of an error message notifying the user that the file addition process is disabled and then ends the process.

If it is determined in step S that the information corresponding to the list of downloadable files has been received the data acquisition unit supplies in step S the menu screen display controller with information regarding the list of downloadable files transmitted from the server and received via the Internet interface . The menu screen display controller causes a display device to display a menu screen of the list of downloadable files from which the user is allowed to select one.

In step S the operation input acquisition unit determines whether the user has selected an item to be added using one of buttons and icons on the menu screen displayed under the control of the menu screen display controller . If it is determined in step S that any item the user may want to add has not been selected step S is repeated until it is determined that any item has been selected.

If it is determined in step S that the item the user may want to add has been selected the operation input acquisition unit supplies in step S to the data acquisition unit information indicating the content of updating selected by the user. The data acquisition unit controls the Internet interface and transmits information indicating a requested file to the server to request the server to send back the file selected by the user.

In step S the data acquisition unit controls the Internet interface thereby causing the server to download one of a PlayList file a ClipInformation file a clip AV stream file an audio file a caption text stream file an animation data file and a font file prepared as download files. The data acquisition unit then notifies the local storage directory manager that these files have been downloaded.

In step S the local storage directory manager determines whether the local storage has already stored directories identified by the author id and disc id identifiers contained in the manifest of the downloaded files. If the corresponding directory is present on the local storage the downloaded data file is expanded on that directory. If no corresponding directory is present a new directory specified by the author id and disc id identifiers is created and the downloaded data file is then expanded thereon.

Through this process the update file is downloaded from the server stored on the local storage and handled as an update file of the content recorded on the optical disk .

For example a user purchases an optical disk having a content such as a movie recorded thereon. The user then acquires a file required to display a caption of a language unrecorded on the optical disk or a file required to display an new animation in synchronization with the video data and then stores those files on the local storage . The application program for performing the playback process can thus handle the data recorded on the optical disk and the data recorded on the local storage without any difference. As a result a virtual file system that hides the storage of physical data from the user and the application program is produced.

In step S the local storage directory manager extracts a directory of a corresponding disc id from a downloaded data group stored on the local storage and then supplies the directory to the file system merge processor .

In step S the file system merge processor references the src file name and dst file name fields in the manifest file.

In step S the file system merge processor binds a native file system to a virtual file system based on the src file name and dst file name referenced in step S.

More specifically the src file name presents a path name representing a path i.e. information uniquely identifying where the corresponding file is recorded in the directory structure in the file system of the local storage . The dst file name field presents a path name representing a path i.e. information uniquely identifying where the corresponding file is recorded in the directory structure at a binding destination in the virtual disk of the file stored on the local storage .

For example in the manifest section described with reference to MainMovie movie01 main.r1.jp.mp2 as a path name might be specified in the src file name field and STREAM 01002.m2ts as a path name might be specified in the dst file name field. As previously discussed with reference to the downloaded data is stored under a file name of main.r1.jp.mp2 in a movie01 folder in MainMovie folder on the local storage in accordance with the author id and disc id identifiers. In the virtual file system on the virtual disk the file system merge processor performs the binding process so that the downloaded data is handled as a file having a file name of 01002.m2ts in a STREAM directory.

The content author can specify the path name in the local storage in the src file name field of the manifest section of the downloaded file package and the path name of the virtual file system on the virtual disk in the dst file name field. If the path name adapted to the virtual file system on the virtual disk i.e. adapted to the file system of the optical disk is set in the dst file name field the content author can freely set the file directory structure under the disc id identifier and add newly a directory and a file in an area under the disc id identifier of the data actually recorded on the local storage in the reproducing apparatus .

The playback process executed by the reproducing apparatus is described below with reference to the flowchart of .

When the user enters an instruction to reproduce a predetermined content the controller reads from the optical disk via the optical disk drive or from the local storage the PlayList file corresponding to the content that is to be reproduced in response to the instruction. In step S the controller determines whether the API for displaying animation is initiated. If it is determined in step S that the API has not been initiated processing proceeds to step S.

If it is determined in step S that the API has been initiated an animation display preparation process to be discussed later with reference to is executed in step S. With the animation display preparation process executed the decoded object buffer accumulates decoded animation data.

If it is determined in step S that the API has not been initiated the controller reads the main Clip the sub Clip and the text sub title data Text ST data in step S subsequent to step S. More specifically the controller reads the main Clip based on the PlayItem contained in the PlayList. The controller reads the sub Clip and the text sub title data based on SubPlayItem referenced by a SubPath contained in the PlayList.

In step S the controller controls the switch in order to supply the read data including the main Clip the sub Clip and the text sub title data to respective buffers . More specifically the controller controls the switch to supply the background image data to the buffer the main Clip data to the buffer the sub Clip data to the buffer and the text sub title data to the buffer .

In step S the switch is thus controlled by the controller . The background data is supplied to the buffer the main Clip data is supplied to the buffer the sub Clip data is supplied to the buffer and the text sub title data is supplied to the buffer .

In step S the buffers buffer respective supplied data. More specifically the buffer buffers the supplied background image data the buffer buffers the main Clip data the buffer buffers the sub Clip data and the buffer buffers the text sub title data.

In step S the PID filter sorts the stream data in accordance with PID accompanying the TS packet forming the main Clip AV stream file and then distributes the sorted stream to the decoders of elementary streams. More specifically the PID filter supplies the video stream to the PID filter the presentation graphics stream to the switch serving as a supply source to the presentation graphics decoder the interactive graphics stream to the switch serving as a supply source to the interactive graphics decoder and the audio stream to the switch serving as a supply source to the first audio decoder . The video stream the presentation graphics stream the interactive graphics stream and the audio stream are assigned different PIDs. The PID filter under the control of the controller supplies the primary video stream to the first video decoder and the secondary video stream to the second video decoder .

In step S the PID filter sorts the stream data in accordance with PID and distributes the sorted data to respective decoders of elementary streams. More specifically the PID filter supplies the video stream to the PID filter the presentation graphics stream to the switch serving as a supply source to the presentation graphics decoder the interactive graphics stream to the switch serving as a supply source to the interactive graphics decoder and the audio stream to the switch serving as a supply source to one of the first audio decoder and the second audio decoder . The PID filter under the control of the controller supplies the primary video stream to the first video decoder and the secondary video stream to the second video decoder .

In step S the PID filters under the control of the controller selects between the main Clip and the sub Clip. More specifically the switch selects the presentation graphics stream of one of the main Clip supplied from the PID filter and the sub Clip supplied from the PID filter and supplies the presentation graphics stream to the subsequent presentation graphics decoder . The switch selects the interactive graphics stream of one of the main Clip supplied from the PID filter and the sub Clip supplied from the PID filter and supplies the selected interactive graphics stream to the interactive graphics decoder . The switch selects the audio stream of one of the main Clip supplied from the PID filter and the sub Clip supplied from the PID filter and supplies the selected audio stream to the first audio decoder . If the user issues an instruction to switch audio the switch may supply the audio stream of the main Clip to the second audio decoder or the audio stream of the sub Clip to one of the first audio decoder and the second audio decoder . The discussion of this process is skipped because the playback process prior to the audio switching is discussed herein.

In step S the background decoder decodes the background image data and outputs the decoded background image data to the background plane generator .

In step S the first video decoder decodes the supplied primary video stream and then outputs the decoded primary video stream to the video plane generator .

In step S the second video decoder decodes the supplied secondary video stream and then outputs the decoded secondary video stream to the video plane generator .

In step S the presentation graphics decoder decodes the presentation graphics stream selected and supplied by the switch and then outputs decoded presentation graphics stream to the subsequent switch .

In step S the interactive graphics decoder decodes the interactive graphics stream selected and supplied by the switch and then outputs the decoded interactive graphics stream to the subsequent switch .

In step S the first audio decoder decodes the primary audio stream selected and supplied by the switch and then outputs the decoded primary audio stream to the subsequent mixing processor .

In step S the second audio decoder decodes the secondary audio stream selected and supplied by the switch and then outputs the decoded secondary audio stream to the subsequent mixing processor .

In step S the text sub title composition decoder decodes the primary or secondary text sub title data to be displayed and then outputs the decoded text sub title data to the switch .

In step S the composition buffer under the control of the animation scheduler determines whether animation is to be displayed.

If it is determined in step S that animation is to be displayed an animation generation process to be discussed later with reference to the flowchart of is executed in step S.

If it is determined in step S that animation is not to be displayed or subsequent to step S the switch selects one of the data output from the presentation graphics decoder and the data output from the text sub title composition decoder in step S. More specifically the switch selects one of the presentation graphics stream decoded by the presentation graphics decoder and the text sub title data from the text sub title composition decoder to be displayed and then supplies the selected data to the presentation graphics plane generator .

In step S the switch selects one of the data output from the interactive graphics decoder and the data output from the composition buffer . More specifically the switch selects one of the interactive graphics stream decoded by the interactive graphics decoder and the animation data generated by the composition buffer to be displayed and then supplies the selected data to the interactive graphics plane generator . The moment the animation data is supplied to the composition buffer is animation timing and the switch thus supplies the animation data from the composition buffer to the interactive graphics plane generator .

In step S the background plane generator generates a background plane based on the background image data supplied from the background decoder .

In step S the video plane generator mixes the video data from the first video decoder and the video data from the second video decoder to generates a video plane and then outputs the video plane to the video data processor .

In step S the presentation graphics plane generator generates a presentation graphics plane based on one of the data from the presentation graphics decoder and selected and supplied by the switch in step S and the data from the text sub title composition decoder .

In step S the interactive graphics plane generator generates an interactive graphics plane based on one of the data of the interactive graphics stream supplied from the interactive graphics decoder and then selected by the switch in step S and the animation data supplied from the composition buffer .

In step S the buffer buffers the sound data selected and supplied in step S and then supplies the buffered sound data to the mixing processor at a predetermined timing.

In step S the video data processor mixes and then output data of the planes. More specifically the video data processor mixes the data from the background plane generator the video plane generator the presentation graphics plane generator and the interactive graphics plane generator and then outputs the mixed data as video data.

In step S the mixing processor mixes the primary audio data output from the first audio decoder and the secondary audio data output from the second audio decoder and outputs the mixed data to the mixing processor .

In step S the mixing processor mixes synthesizes the mixed audio data output from the mixing processor and the sound data and outputs the mixed data.

In step S the controller references the read PlayList thereby determining whether to end the playback process. If it is determined in step S that the playback process is not to end processing returns to step S to repeat step S of and subsequent steps. If it is determined in step S that the playback process is to end processing ends.

Through the above process the audio data and the video data recorded in the form of the AV stream on one of the optical disk and the local storage and as necessary the text data in the text caption file the audio data of sound effect and the image data for displaying animation animation frame data are decoded and reproduced.

The animation display preparation process executed in step S of is described below with reference to the flowchart of .

In step S the animation decoder decodes the animation frame read and buffered on the pre load buffer and then supplies the decoded animation frame to the decoded object buffer .

In step S the decoded object buffer retains the decoded animation frame. Processing returns to step S of to proceed to step S.

Through this process the animation frame is buffered and decoded beforehand and then stored on the decoded object buffer in order to reproduce the animation in synchronization with the video data of the main Clip the decode timing of which is difficult to predict.

The animation generation process executed in step S of is described below with reference to the flowchart of .

In step S the animation scheduler references the STC counter not shown to check a video synchronization signal.

In step S the animation scheduler determines whether the current time is earlier than the animation start time by T T more specifically determines whether the current time is earlier than the start of the transfer of the animation frame from the decoded object buffer to the composition buffer discussed with reference to by time required to back up the image data before the start of the animation display.

If it is determined in step S that the current time is earlier than the animation start time by T T the composition buffer backs up in step S the image data immediately prior to the start of the animation display from the interactive graphics plane generator as the background image of the animation display.

If it is determined in step S that the current time is not earlier than the animation start time by T T or subsequent to step S the animation scheduler determines in step S whether it is it is now between the time earlier than the animation display start time by T and the animation display end time i.e. whether it is time to output the animation frame in synchronization with the video frame.

If it is determined in step S that the current time is between the time earlier than the animation display start time by T and the animation display end time the animation scheduler determines in step S whether an animation to be displayed is present in the decoded object buffer .

If it is determined in step S that an animation is present the decoded object buffer extracts a target image of the animation frame under the control of the animation scheduler in step S.

In step S the decoded object buffer transfers or copies the target image of the animation frame to the composition buffer under the control of the animation scheduler that references the same STC counter as the video buffer.

In step S the composition buffer alpha blends the background image backed up in step S and the target image of the animation frame transferred or copied in step S.

In step S the composition buffer supplies the mixed image to the switch to output the mixed image to the interactive graphics plane generator . Processing returns to step S of to proceed to step S.

If it is determined in step S that the current time is not between the time earlier than the animation display start time by T and the animation display end time or if it is determined in step S that no animation frame is present processing returns to step S of to proceed to step S.

Through this process the animation frame buffered and decoded beforehand is displayed in synchronization with the video data.

The repeated playback process or the playback start point specifying process is described below with reference to the flowchart of .

In step S the controller determines based on a signal from the operation input unit whether a command to start one of the repeated playback process and the playback start point specifying process has been received from the user. If it is determined in step S that a command to start one of the repeated playback process and the playback start point specifying process has been not been received from the user step S is repeated until it is determined that a command to start one of the repeated playback process and the playback start point specifying process has been received from the user.

If it is determined in step S that a command to start one of the repeated playback process and the playback start point specifying process has been received from the user the controller references the PlayList corresponding to a playback portion to determine whether the animation display is to be performed.

If it is determined in step S that no animation display is to be performed the controller controls the decoder in step S thereby performing the playback process without displaying animation. More specifically the controller performs a portion of the playback process discussed with reference to unrelated to animation.

If it is determined in step S that the animation display is to be performed the controller determines in step S whether the animation display preparation process has been completed.

If it is determined in step S that the animation display preparation process has not been completed the controller performs in step S the animation display preparation process discussed with reference to .

If it is determined in step S that the animation display preparation process has been completed or subsequent to step S the controller acquires in step S a playback start point based on a signal supplied from the operation input unit .

In step S the controller performs the playback process using the decoded animation data. More specifically the controller performs the same process as step S and subsequent steps of the process discussed with reference to .

When a portion that has undergone the animation display preparation process is reproduced through this process the decoded and buffered animation data of the corresponding portion may be used. The repeated playback process and the playback start point specifying process may be quickly and easily performed.

In the repeated playback process or the playback start point specifying process discussed with reference to when the portion that has undergone the animation display preparation process is reproduced the decoded and buffered animation data of the corresponding portion is used as described above. If the alpha blended frame data is stored on the composition buffer i.e. the data is not transferred but copied from the composition buffer to the switch the alpha blended frame data stored on the composition buffer may be reused to perform the one of the repeated playback process and the playback start point specifying process.

For example an animation frame described using Java can be reproduced in synchronization with video to be reproduced as stream data on the reproducing apparatus .

In comparison with the known HDMV graphics stream used to display graphics in synchronization with a video frame in the MPEG 2 transport stream format the reproducing apparatus of the embodiments of the present invention is free from video format limitation and compression format limitation. The format of the image to be reproduced in synchronization is flexibly introduced. The authoring process is so simple as to call the API in the application program.

In the reproducing apparatus of the embodiment of the present invention frame synchronized animation is thus developed with low development cost based on general graphics objects such as JPEG images and the definition of the control API. With API driven animation a content producer and a content provider can produce and distribute video synchronized animation without expert knowledge about MPEG 2 transport stream.

On a later date animation data may be easily supplied over the network such as the Internet to be reproduced in accordance with an already distributed content. The development of the data to be supplied on a later date requires no expert knowledge about MPEG 2 transport stream for example.

A manufacturing method of the recording medium storing data replayable on the reproducing apparatus is described below with reference to . As shown the recording medium is the optical disk .

As shown in a master disk made of glass is prepared. A recording material made of photoresist or the like is applied on the master disk. The recording master disk thus results.

As shown in video data in a format replayable on the reproducing apparatus encoded by a video encoder in a software production section is stored temporarily on a buffer. Audio data encoded by an audio encoder is temporarily stored on a buffer. Data other than streams for example Indexes Playlist PlayItem etc. encoded by a data encoder is temporarily stored on a buffer. The video data the audio data and the data other than the stream stored on the respective buffers are multiplexed by a multiplexer MPX in synchronization with a synchronization signal and an error correction code ECC circuit attaches an error correction code to the multiplexed signal. The resulting signal is modulated by a modulator MOD circuit and then stored on a magnetic tape in accordance with a predetermined format. Thus a software program is manufactured to be recorded onto one of the optical disk and the removable medium replayable on the reproducing apparatus .

The software program is edited pre mastered as necessary and a signal having a format to be recorded on the optical is thus produced. A laser beam is modulated In accordance with the recording signal and then directed to the photoresist on the master disk. The photoresist on the master disk is thus exposed to the laser beam modulated with the recording signal.

The master disk is then developed and pits are arranged on the master disk. The master disk is then subjected to electroforming to manufacture a metal master disk into which the pits of the glass master disk are transferred. From the metal master disk a metal stamper is produced and used as a mold.

A material such as PMMA acryl or PC polycarbonate is injected into the mold and solidified. Alternatively after applying 2P ultraviolet curing resin on the metal stamper ultraviolet light is directed to the metal stamper for curing. In this way the pits on the metal stamper are transferred to a replica made of the resin.

A reflective film is formed on thus constructed replica using deposition or sputtering technique. Alternatively a reflective film is formed on the replica using spin coating technique.

The inner circular edge and the outer circular edge of the disk is then neatly shaped and a process required to bond two disks together is also performed. Further a label is glued on the disk and a hub is attached to the disk and the resulting disk is inserted into a cartridge. The optical disk or the removable medium having data replayable on the reproducing apparatus are thus manufactured.

The above referenced series of process steps may be performed using software. A program of the software may be installed from a recording medium onto a computer built in dedicated hardware or a general purpose personal computer enabled to perform a variety of functions with a variety of programs installed thereon.

As shown in the recording medium includes the removable medium distributed to a user separate from a computer to provide the user with the program. The recording media include the removable medium such as one of a magnetic disk including a flexible disk an optical disk such as compact disk read only memory CD ROM or digital versatile disk DVD a magneto optical disk such as mini disk MD and a semiconductor memory. The recording media also include the memory such a ROM or a RAM or the local storage such as a hard disk each storing the program and supplied in the apparatus to the user.

The process steps describing the program stored on the recording medium may be performed in the time series order sequence as previously stated. Alternatively the process steps may be performed in parallel or separately.

It should be understood by those skilled in the art that various modifications combinations sub combinations and alterations may occur depending on design requirements and other factors insofar as they are within the scope of the appended claims or the equivalents thereof.

