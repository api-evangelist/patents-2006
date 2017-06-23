---

title: System and method for securely storing and organizing SDARS content with DRM and non-DRM protected media content, and for facilitating obtaining purchased or subscription-based media based on received SDARS content
abstract: Disclosed are a device and method for securely storing and organizing SDARS content on a portable player. SDARS audio content is stored on a private partition of the device not available to a client PC. Shadow files are stored on a public partition of the device. The shadow files contain metadata related to the corresponding SDARS audio and a reference to the SDARS audio on the private partition. Playlists can be organized on the device intermixing stored SDARS content with DRM and non-DRM protected media content. Downloading of purchased or subscription-based media files based on observed or received SDARS content is facilitated. Digital Rights Management features are included to control authorized actions with respect to SDARS content. Firmware updates are performed using encrypted firmware unique to the particular device to thwart firmware hacking.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08005419&OS=08005419&RS=08005419
owner: XM Satellite Radio Inc.
number: 08005419
owner_city: Washington
owner_country: US
publication_date: 20061229
---
The present invention relates generally to satellite digital audio broadcast radio service SDARS and portable music players. In particular the present invention relates to a system and method for storing protected SDARS content on a portable player and organizing the same in playlists along with digital nights management DRM protected media and non DRM protected media.

Recently there has been increased interest in delivering media content such as music to consumers in new ways. For example online music stores have enabled consumers to purchase music tracks one song or one album at a time. A Digital Rights Management DRM digital version of the song is transferred to the consumer typically over a broadband internet connection for playback on the consumer s computer or another authorized device such as a portable playback device. One problem with this business model is that consumers are typically only able to sample 30 second sound bites of songs before purchasing. Also consumers are typically required to know what music they are interested in before they can search for and purchase the music. In other words this business model is a pull system where the consumer requests the particular song or media file that they want. Client software may make recommendations to consumers to introduce them to new content but these features are typically rather limited. Furthermore spontaneously generated broadcast content such as terrestrial or satellite radio broadcasts is often more effective at introducing consumers to new music and or reminding consumers of music they would like to purchase. However in most cases the consumer is required to remember what they heard on the radio and search for the desired content the next time they are at a computer.

Another business model works on a subscription basis. Consumers typically pay a monthly subscription and are entitled to download an unlimited number of DRM protected songs from a particular vendor s library of media content. These subscription based songs however are typically only playable on the consumer s PC or other authorized device so long as the consumer maintains their subscription. Also the consumer is typically more limited in what they can do with media content obtained via their subscription. For example while the subscription holder can normally download an unlimited number of songs if they want to burn music to a standard CD they are required to separately purchase the songs they want to burn. Also the subscription model is a pull model and is subject to the same problems described above with respect to inadequate means to identify new content for download.

More recently satellite digital audio radio service SDARS systems have been introduced to provide consumers with a new way of enjoying music. In an SDARS system over 100 channels of music news and other content are streamed via satellite or terrestrial repeater to consumer receivers. The consumers are typically required to maintain a subscription to the SDARS service to receive the SDARS broadcast. Due to the number of channels and the variety of genres available on SDARS systems consumers have rapidly adopted these services. More recently personal portable players have been introduced that allow the consumer to use their SDARS receiver in their car in their home or even to carry the receiver with them.

There are some known limitations with existing SDARS systems and for purchase and subscription based download music services. SDARS portable players have had some capacity to buffer SDARS content in a first in first out FIFO manner and to remember names of artists and or song titles to assist with later purchase from an online music service. However by design such devices have limited the ability of the consumer to permanently save and organize SDARS content. The portable players have a limited capacity for storing SDARS content such as for example five hours of content . The content is typically overwritten in a FIFO manner unless a particular portion is locked. However locked content reduces the amount of memory remaining for new content to be stored. The FIFO buffer of existing players is mainly intended to be used as a time shifting device rather than a permanent storage for music owned by the consumer. SDARS devices by design do not permit the consumer to transfer stored SDARS content from the portable player to another device. In addition the stored SDARS content only remains playable while the consumer maintains their subscription with the SDARS service.

Furthermore if the consumer desires to use both an SDARS system and a digital media player to enjoy their purchased or subscription based downloaded music two separate devices are required.

Accordingly there is a need for a portable SDARS receiver that facilitates the identification and download of purchased or subscription based media files. Furthermore there is a need for a more sophisticated manner of interacting with stored SDARS content on a portable player while still preventing the consumer from removing the SDARS content from the device or otherwise using the stored SDARS content in an unauthorized manner. There is a need for a single portable device which allows the consumer to store both SDARS content and downloaded purchased or subscription based music and to organize playlists comprising both SDARS content and DRM or non DRM protected media files.

The above and other problems are overcome and additional advantages are realized by exemplary embodiments of the present invention. A system according to an exemplary embodiment of the present invention comprises a portable SDARS player that is connectable to a personal computer PC having client software that is adapted to interact with the portable SDARS player and an online media service such as a music purchase service or a subscription download service. The portable SDARS player is capable of storing SDARS content in private memory that is not accessible outside the portable SDARS receiver and makes the stored SDARS content available to the client software via shadow files that represent individual segments of the stored SDARS content and that reside in a public memory in the player that is accessible by the PC via the client software. The shadow files preferably contain metadata representing the content of the stored SDARS segments to which they pertain as well as a reference to the particular SDARS segment stored in the private memory.

The client software is preferably capable of matching stored SDARS content to media files available from the online media service in order to facilitate obtaining authorized purchased or subscription based versions of media files corresponding to the stored SDARS content. The matching preferably occurs via the metadata contained in shadow files. The metadata preferably includes artist name album name and song title information and also can include program ID data and time of transmission among other things.

The client software is preferably capable of arranging playlists on the portable SDARS player comprising references to DRM and or non DRM protected media files stored in the public memory as well as references to stored SDARS segments via shadow files. In this manner the portable SDARS player can play back a playlist comprising DRM and or non DRM protected media files intermixed with stored SDARS segments so long as the user remains authorized to access the SDARS content and any DRM protected media files in the playlist.

Throughout the drawing figures like reference numbers will be understood to refer to like elements features and structures.

Exemplary embodiments of the invention will now be described with reference to the attached drawing figures. shows a system according to an exemplary embodiment of the present invention. The system comprises a portable SDARS player connected to a client personal computer PC that hosts client software for interacting with the SDARS player . The SDARS player receives SDARS service provided via a broadcast station that can transmit SDARS via a wired network and wirelessly e.g. from satellites or terrestrial repeaters . For illustrative purposes the SDARS service is represented as broadcast via a satellite or via as wired network from an SDARS broadcast station in . The PC with client software also connects to an online media store via the internet to obtain desired media content for the user.

The interface operations of SDARS capable audio players hereinafter Devices will now be described which enable such Devices to be supported by the client PC software. Devices that support these interface operations and therefore gain compatibility with the client software advantageously provide all the users of the Device benefits associated with the capabilities of the client PC software which include the following functions among others 

In accordance with an exemplary embodiment of the present invention the following components and specifications are involved in PC24 Device connectivity 

For convenience the entire suite of PC software and specifications covered by these interface specifications is hereinafter called NXM. 

Generation Devices supported by NXM incorporate MSC Mass Storage Class for device connectivity and PDDRM for digital rights management of files transferred from the PC to the Device. Generation Devices preferably use MTP for device connectivity and Janus for digital rights management.

An exemplary embodiment described herein covers devices using MSC for PC connectivity and PDDRM. However it should be understood that exemplary embodiments can also use MTP for PC connectivity and Janus for DRM or any other suitable protocols and DRM methods known to those of ordinary skill in the art.

Bookmark Refers to the action and result of the user flagging a track heard or recorded on the Device for further exploration in the Online Music Service . Bookmarks are stored on the Device as metadata only database records separate from content metadata so they can persist if the content and associated metadata is deleted.

PDDRM Microsoft DRM version 9 as implemented on a portable device. Does not support subscription based DRM.

Event ID a 64 bit number generated by the SDARS service from a Program ID a 32 bit number received over the air with most aired SDARS tracks and the date the track was aired. The Event ID is used by the online music store SDARS service back end systems to manage matches between content received over the air and content in the online music store library.

Lock The action and result of flagging an SDARS track on the Device to prevent the track from being overwritten during a subsequent SDARS recording session. The user locks tracks she wishes to keep tracks that remain unlocked are subject to being replaced during recording sessions.

MSC Mass Storage Class. A technique for connecting a flash based or microdrive storage device over USB to a PC wherein the device s storage appears as a simple external hard drive.

MTP Media Transfer Protocol. A technique for connecting a flash based or microdrive storage device over USB to a PC wherein data is transferred between the device and PC as objects and control information over a communication session.

Partition MSC based Device storage is preferably allocated into two partitions although more partitions can be employed 

Session A continuous recording of a single channel of SDARS content. A track recorded during a Session can be uniquely attributed to the session through a combination of the Device ID on which the session was recorded date the session recording started a Session ID unique for that day on that device and a Session Sequence Number indicating the order the track was recorded relative to other tracks recorded in the Session.

Track Minimum individually identifiable audio element. Usually corresponds to a song but can also correspond to an excerpt from a news program or even a brief comment from a DJ in between songs. For SDARS content track boundaries typically correspond to any title artist change.

WMP 10 Windows Media Player version 10 most recent version as of mid 2005 supported by Windows XP only.

SDARS Content Audio content captured by the Device through the SDARS service effectively SDARS Media Files and the audio content they represent.

SDARS Media File A file representing a single track of SDARS Content. SDARS Media Files contain metadata attributes title artist channel etc. for the SDARS audio files they represent as well as a reference to the actual stored SDARS audio content they represent.

XMPDlib Software component that exposes the SDARS Device API to the Client and communicates with the Device abstracting the details of the Device interface to the PC Client.

In accordance with an exemplary embodiment of the present invention the player is configured to orient the display and assign functions to the user interface buttons on the player depending on the orientation of the player while in use. For example the player can be used with a cradle when docked for use with the PC or when charging. The player has a display for indicating among other things channel information for a received SDARS signal or titles of songs or other tracks being received or retrieved from memory for playback. The player comprises one or more buttons e.g. buttons and to facilitate user operation of the player including track channel or menu option selections that can be provided on the display .

When the player is being used as a portable hand held device as shown in the player controller operates the display to orient the information being displayed thereon so that it is parallel to the longitudinal axis of the player thereby facilitating viewing by a user carrying the device. Further the buttons are assigned certain operations. For example buttons and can be for scrolling among items listed on the display buttons and can be used for navigating forward and backward among a plurality of screens generated on the display and the button can be used for selecting an item on the display e.g. a song channel or menu option highlighted on the display .

When the player is connected to the cradle as shown in the player controller operates the display to orient the information being displayed thereon so that it is parallel to the horizontal axis of the player thereby facilitating viewing by a user of a docked device. Further the buttons can be assigned different operations than when the player is not docked. For example buttons and can be for scrolling among items listed on the display and buttons and can be used for navigating forward and backward among a plurality of screens generated on the display . The player preferably connects to the cradle via an electrical interface or connector and therefore can be configured to receive an input when a player port is connected to the cradle to facilitate determining when the player is docked.

In accordance with exemplary embodiments of the present invention other player operations and screens for the display will now be described with reference to D and E.

As shown in the player display can indicate when a user is listening to live SDARS content i.e. SDARS content that is currently being broadcast by the SDARS system and received by the player by generating XM or Live message on the display and when the user is listening to recorded SDARS content or MP3 WMA tracks by instead generating My Music or similar label.

As shown in the controller is programmed to assign one of the buttons e.g. left arrow button the functionality of when pressed providing a virtual keypad e.g. a numeric keypad on the display e.g. for channel tuning .

As shown in the controller is programmed to provide a TuneSelect operation to allow a user to locate a channel on which a favorite artist or song is currently playing in the broadcast. For example the controller is programmed to provide a Bookmark menu on the display when the button is pressed while a track is being broadcast. The Bookmark menu allows a user to select an artist or song for addition to a TuneSelect list maintained by the controller as indicated at or to merely bookmark the song as indicated at . When a song or artist from the list is being broadcast and received via the player the controller causes an indication e.g. flash Artist Song Found or similar message on the display or beep to notify the user that a list item is being broadcast on a particular channel. The user need only press the button to switch to that channel. Similarly the player is programmed to allow a user to select a particular sport or team or stock. The controller can generate virtual keypad e.g. an alphanumeric character keypad on the display to facilitate selection. When a selected button pressed or a menu item is selected the current news for the selected sport team or stock is provided on at least part of the display .

As with the PC client the player is programmed to provide key operations and display menu options to record SDARS content schedule a recording session select and listen to recorded content and to organize stored content e.g. organize stored content by genre or artist generate playlists bookmark content add and delete tracks from memory . In addition the player is configured to generate display screens and menus to allow a user to lock or unlock stored content. Individual tracks can be selectively locked and unlocked and groups of tracks can be selectively locked and unlocked by artist category or channel. Since the player is configured to record content over older tracks first locking a track prevents it from being automatically recorded over. High quality versions of these tracks can also be purchased for storage in another memory that is not automatically recorded over.

The following sections define the logical contents and format of the files exchanged between a Device and PC according to an exemplary embodiment of the present invention. A description of the files as they relate to the different memory partitions then follows.

The SDARS Media File represents SDARS content recorded on the Device . For first generation devices based on HCMOS9 receiver technology this file does not include actual content. However the file format is designed to accommodate inclusion of encrypted content when used for future products based on CMOS90 receiver technology.

The SDARS Media File is created and maintained by the Device but a few fields noted below are created and or can be modified by the PC .

The following are exemplary features of the SDARS Media File format and contents in accordance with an exemplary embodiment of the present invention.

SDARS Media Files preferably use the extension .xmm There are preferably no other restrictions on the file name.

ID3v2 tagging can be used to encode most of the data elements in the SDARS Media File. Since ID3 is a form of tag length value encoding this allows new data elements to be added to the SDARS Media File in the future without affecting legacy parsers. Also existing ID3 parsing software components can be easily re used to handle much of the SDARS Media File parsing. Specifications for the ID3v2 standard can be found online for example http www.id3.org develop.html and so are not included in this document except for a general overview in describing how ID3 is used in the SDARS Media File.

The SDARS Media File preferably begins with an 8 byte header containing the Fingerprint and the Major and Minor SDARS Media File Format Versions 

The ID3v2 flags are zero to indicate no unsynchronization no extended header non experimental and no footer. The ID3v2 tag size indicates the total length of the tag which includes the ID3 header and the following ID3 Frames plus padding. The ID3v2 tag size is encoded with four bytes where the most significant bit bit is set to zero in every byte making a total of 28 bits. The zeroed bits are ignored so a 257 bytes long tag is represented as 00 00 02 01.

Multiple ID3 frames follow the ID3v2 header. Each frame begins with a 10 byte header preceding the data element value 

For SDARS Media File data elements with no clear equivalent in ID3 declared Frame IDs Frame IDs beginning with X are used to avoid collision with future IDs. Frame Size excludes the 10 byte Frame header. Frame Flags are 0x00 for the data elements within the SDARS Media File.

Unless otherwise noted all string values are preferably encoded as ISO 8859 1. Terminated strings are terminated with 0x00. Where compliance with ID3v2 declared Frame IDs is useful numeric values are sometimes encoded as numeric strings. Unsigned integer UINT UINT32 Date values are time t UTC based.

After all ID3 frames the SDARS Media File is preferably padded out to the next 128 byte boundary with 0x00 counting from the start of the Fingerprint sequence in the SDARS Media File header .

The following are data elements that preferably appear in the SDARS Media File their assigned ID3v2 Frame IDs and value information. The previous section entitled Data Elements in SDARS Media File provides information on the logical meaning of element values.

An SDARS Bookmark File is a metadata only file essentially identical in format to the SDARS Media File but preferably with a different file extension .xmb in accordance with an exemplary embodiment of the present invention.

In general an SDARS Bookmark File for a recorded track preferably includes all of the same field values as the corresponding SDARS Media File except that Content Inclusion and Content Reference fields indicate that no content is included.

For SDARS Bookmark Files for tracks that have not been recorded that is no corresponding SDARS Media File has been written to the Data Exchange Partition the following field value considerations can be observed 

With the exception of the SDARS Media File the PC Device Data Exchange files are preferably encoded using the following tag length value TLV encoding method 

The SDARS Channel Lineup File captures the list of authorized channels determined during the most recent connection of the Device to a live SDARS radio signal e.g. reception of SDARS live content broadcast via satellite terrestrial repeater wired network and so on . It is primarily intended for use by the PC Client in displaying available channel information for the recording session user interface.

Native Playlist Files created by the Device or by NXM can use the m3u format consisting of simple references to MP3 WMA and SDARS Media Files by filename.

Playlist Files support playback of MP3 and WMA files that are located in subdirectories in the Public Content Partition.

References to SDARS Media File filenames in the Playlist Files are preferably denoted by an extension of .xmm.

The PC Directive File in the Data Exchange Partition is used by the PC application NXM to indicate that there have been certain updates or commands from the PC that need to be processed on the next Device boot cycle. The PC Directive File is preferably implemented as a primitive script created by the NXM for execution by the Device upon boot.

The PC Directive File is preferably transparent to the Client and used only by XMPDlib and an MSC based Device

The following data elements are preferably provided in an Identification Header for integrity purposes. To deter malicious reformatting the Device preferably verifies that they match the Device s equivalent fields before proceeding with any re partitioning. NXM retrieves these fields for example from the SDARS Device Profile File when constructing the PC Directive File.

The Identification Header is preferably followed by one or more Directive Commands with corresponding parameters.

The SDARS Device Firmware Update File is referenced by an Update Firmware command in the SDARS PC Directive File and contains a firmware update for the Device .

Devices can provide alternative methods of installing firmware updates that do not involve the SDARS Device Firmware Update File or SDARS PC Directive File. In such cases the manufacturer preferably employs techniques that prevent theft of SDARS services and content through installation of a hacked firmware update file. For example a method of providing encrypted firmware to the SDARS player can be used.

Exemplary supplemental specifications and implementation guidelines will now be described for any MSC PDDRM based Device intended for compatibility with the client software related to management of the PC Device Data Exchange files.

The Public Content Partition is important even for nominal 100 SDARS partitioning to essentially always provide a partition that is visible to the PC to allow synchronization of SDARS Media Files playlists profile and so on. Minimum MSC partition size for each 1 GB of SDARS partition is preferably 12 MB.

The Device preferably maintains the following files on the Public Content and Data Exchange Data Partition see PC Device Data Files described above regarding file contents 

The Device s master copy of the following data files are maintained in the Data Exchange Partition no other copy is maintained on another partition of these files 

The Device provides recovery from accidental erasure of all contents of the Data Exchange Partition so that such an event does not result in loss of Locked SDARS tracks accumulated by the user in the Private Content Partition see Data Exchange Partition Recovery below .

Upon completion of all commands in the PC Directive File the Device can delete the PC Directive File.

The partition exposed by MSC devices to a PC is subject to corruption or data loss due to 1 improper disconnect of the Device from the PC or 2 a user accidentally erasing the contents of the partition using Windows Explorer or other OS tools. For the overall Public Content and Data Exchange Partition recovery by the user is usually possible since a copy of the MP3 and WMA files in that partition are typically also on the user s PC. However the Data Exchange Data is preferably only created by the Device and moreover preferably provides the only window into the SDARS audio content on the Private Content Partition. Should the Device interpret missing SDARS Media Files on the Public Content and Data Exchange Partition as a signal to delete corresponding files in the Private Content Partition the result could be the permanent loss of locked SDARS content. The Data Exchange Partition Recovery procedures are intended to prevent this from occurring and to ensure synchronization between the SDARS Media Files in the Data Exchange Partition with the corresponding files in the Private Content Partition. Also the procedures described herein can be followed during normal creation of the default Data Exchange Partition such as initial factory reset or after repartitioning the Device flash storage.

The Device preferably performs the following steps when recovering the contents of the Data Exchange Partition.

During the Data Exchange Data Recovery process the Device can display a message to the user such as Please wait Preparing Data .

In a preferred implementation each time a track is recorded the Device creates an SDARS Media File on the SDARS partition and when recording is complete makes a copy of the SDARS Media File in the Data Exchange Partition.

In a preferred implementation the Device updates the Storage Status in the SDARS Device Profile File upon changes that affect storage capacity such as lock status changes recording of a new SDARS track or user deletion of a new SDARS track. These updates are preferably made concurrent with the precipitating event to ensure the Storage Status parameters are correct upon next connection to the PC.

Upon creation editing and deletion of a playlist the Device edits the playlist on the Data Exchange Partition.

Upon capturing a full channel lineup from the SDARS receiver the Device preferably writes the SDARS Channel Lineup File. This can be performed at least once during each power up session with live SDARS reception. In a preferred implementation the Device preferably also monitors the channel lineup for changes and rewrite the SDARS Channel Lineup File upon detected change.

Various run time policies are implemented by the Device and PC and client in accordance with exemplary embodiments of the present invention.

The Device enforces SDARS DRM policies in accordance with an exemplary embodiment of the present invention. In particular if the PC Client inadvertently or maliciously attempts to perform SDARS content management functions that are not allowed due to elapsed SDARS subscription or locking organizing authorization the Device ignores such attempts.

When playing a Playlist and the SDARS subscription and or locking organizing authorization is lapsed any references to SDARS tracks in the Playlist are skipped.

To support Plays4Sure capabilities the Device can play Playlists with supported Playlist formats detected on the Public Content Partition through one of the following methods 

Furthermore in scenario 3 the track that was being recorded before the channel change can be stored with the Truncation flag asserted indicating end of track truncation .

In accordance with an exemplary embodiment of the present invention a user can Bookmark a track intended for exploration with the Online Music Service . Bookmarking a track causes the Device to create an SDARS Bookmark File in the Data Exchange Partition and effectively copies the corresponding SDARS Media File for the track. Since an SDARS Bookmark File is separate from an SDARS Media File it survives even if the corresponding SDARS Media File is deleted by overwrite during a subsequent recording session or intentionally by the user.

If the user deletes a track tagged as Bookmarked the audio data associated with the track is preferably deleted as usual but the SDARS Bookmark File corresponding to the Bookmarked and overwritten file is preferably not removed from the Data Exchange Partition.

The Device preferably limits the number of Bookmarked files to 500. In a preferred implementation a new Bookmark after the limit is exceeded will replace the oldest Bookmark.

The user preferably has the ability to Bookmark a playing track regardless of when the action occurs during track playback and regardless of whether the track is being recorded. If the track is Bookmarked but not recorded then only the SDARS Bookmark File on the Data Exchange Partition need be written. This further requires the Device to buffer all metadata necessary to create an SDARS Bookmark File for the currently playing track even if the track is not being recorded in case the user decides to Bookmark the track near the end of the track.

In a preferred implementation the Device preferably provides a user interface for viewing and deleting all Bookmarks.

SDARS transmits a 32 bit Program ID for each track transmitted over the air. A new Program ID is provided with each significant artist title change. The Device preferably must capture the Program ID and track start time based on the SDARS system time to populate the Program ID and Program Date fields in SDARS Media Files and SDARS Bookmark Files. Program IDs can be used by the PC Client and Online Music Services to manage matching of SDARS tracks received over the air by the Device with corresponding content in the Napster online library. The Device issues the CbmLabelBICMonReq CBM command to enable reception of the Program ID through the CbmSngTimelnd CBM indication. The Program ID is then available to the Device when a new track starts and title artist labels change or if the Device is tuned to a new channel during ongoing track transmission that is CbmSngTimelnd with Program ID can be received during mid track .

The Device updates the Diagnostics fields in the SDARS Device Profile File with data and selected circumstances. This is intended primarily to augment Type Approval testing of SDARS DRM compliance from a PC based test application.

The client PC application interacts with the SDARS Device to provide additional functions in accordance with an exemplary embodiment of the present invention. The client application will now be described in further detail.

When a compatible SDARS Device is connected to a PC running the client application the Device is detected during device discovery and additional options are enabled in the client application that are related to interaction with the SDARS Device . During the discovery process the model and capabilities of the SDARS Device are preferably determined by the client . The client user interface UI preferably provides for 

An SDARS online service e.g. XM Radio Online or XMRO can be provided that employs commerce application servers and a PAD Event database . The SDARS online service can receive data e.g. PAD date and Program ID via a link. An embedded SDARS online service player e.g. XMRO player can be provided in the client to communicate with XMRO infrastructure e.g. SDARS online service to obtain PAD and rights to currently playing music. To reconcile the rights for the handheld device the client communicates with the Napster infrastructure indicated generally at . The Napster infrastructure matches the PAD information to a unique Napster track ID. They store the matched unique Napster track ID with the unique event ID in memory e.g. a quick lookup cache . The unique event ID can be generated from the ProgramID and date.

The next bookmark shown in does not have an exact track match at the online music service but there are artist and album matches. The next two bookmarks have artist matches but no album or track matches. The last two bookmarks shown in have no matches.

An SDARS Device according to an exemplary embodiment of the present invention preferably enables the creation of mixed playlists comprising both recorded SDARS tracks indicated generally at and DRM or non DRM protected media files indicated generally at . illustrates an exemplary screenshot of the client interface for reviewing a mixed playlist. As shown SDARS tracks are intermixed with subscription based downloads and DRM and non DRM protected media files such as MP3 WMA AAC AAC OGG among others . The SDARS tracks are made available through SDARS Media files e.g. shadow files that represent the corresponding SDARS audio content on the private SDARS Device memory partition that preferably remains invisible to the client PC . So long as the user s SDARS subscription remains valid the SDARS tracks can be organized and played back along with other media files .

As described above the SDARS PC and portable player system of the present invention employs a client application at a PC that communicates with a preferably portable user device or player . The SDARS capable user device or player is provided with a device API for communicating with the client application.

The player preferably employs an antenna with a low noise amplifier LNA for receiving an SDARS signal. The SDARS receiver comprises a tuner and a baseband processor . The SDARS receiver preferably comprises three receiver arms for processing the SDARS broadcast stream received from two satellites and a terrestrial repeater as indicated by the demodulators and that are demodulated combined decoded and demultiplexed to recover channels from the SDARS broadcast stream as indicated by the controller and TDM combine and service demultiplexer module . Demultiplexed data from the SDARS broadcast stream is provided to a data port and the data bus . Demultiplexed audio speech and the like are provided to audio and speech decoders and having outputs to the digital audio bus . Processing of a received SDARS broadcast stream is described in further detail in commonly owned U.S. Pat. Nos. 6 154 452 and 6 229 824 the entire contents of which are hereby incorporated herein by reference.

With continued reference to a digital audio bus preferably transports uncompressed audio. The digital audio bus can transport for example an I2S formatted signal which is known in the industry. The data bus can be used for the output of non audio or compressed audio signals. The player is configured to decode signals employing various types of encoding. By way of an example the speech decoder can provide AMBE speech decoding. The audio decoder or the system controller can provide AAC AAC WMA MP3 and XMA decoding among other types.

The player can be connected to a personal computer PC via a USB as indicated at . As described above the system controller is provided with a device API that communicates with the client application described above. The player can therefore be operated with the PC to manage playlists of content stored from the received SDARS stream as well as other content files and to otherwise search and navigate among stored content.

The player can comprise an optional bus multiplexer or digital transceiver integrated circuit DTIC or other interface from the player to a corresponding interface in another device. The DTIC is described in U.S. patent application Ser. No. 11 239 642 filed Sep. 30 2005 and incorporated in its entirety herein by reference. Briefly a DTIC is provided in each of at least two devices that are connected via a link to control communications on the link. Thus the DTIC provides a cost effective means for an electronics equipment manufacturer to be SDARS compatible since the manufacturer can provide a DTIC in a media player or other consumer electronic device and another DTIC in a corresponding SDARS receiver module e.g. a cartridge that is preferably detachable from the media player to allow the media player and the SDARS receiver module to communicate with each other via the link.

The manufacturer preferably configures the DTIC in the media player to operate as a master device with respect to the DTIC in the corresponding SDARS receiver module e.g. consumer electronic device since the media player typically has a user interface and controller . Accordingly the DTIC in the SDARS receiver module is preferably configured to operate as a slave device. The two DTICs each multiplex data and audio streams e.g. from an SDARS content stream that are transported between the media player and the SDARS receiver module into a time division duplex TDD high frequency serial link that is preferably implemented as an EIA 422 484 physical interface. By way of an example the DTIC can implement a TDM TDD bus multiplexer in a cartridge as shown in .

A communications cable connecting the DTICs preferably comprises four wires with preferably two wires for supplying power such as DC power and ground and two wires providing bidirectional differential communication between two devices.

With reference to and a docking system with SDARS subscription cartridge is provided in accordance with an exemplary embodiment of the present invention. The docking station can be connected to a standard SDARS antenna as opposed to a digital antenna or an integrated antenna comprising an SDARS receiver and antenna in a single unit as described in the above referenced U.S. patent application Ser. No. 11 239 642. The docking station can be connected to an SDARS compatible device via a cable and connector as described in connection with of the above referenced U.S. patent application Ser. No. 11 239 642. The docking station comprises an interface or connector for detachably connecting to a cartridge . As shown in the cartridge comprises similar components to those described in connection with . As stated above the audio decoder or system controller of the cartridge can implement one or more decoders for decoding different content formats such as WMA AAC AAC XMA and MP3 among others. The speech decoder can be or can comprise an AMBE decoder. The system controller is preferably provided with a software module for interfacing with the client application in the PC that provides the SDARS digital jukebox functionality described above. The description of the remaining components is therefore omitted here for conciseness.

As stated above an interface such as a time division multiplexing time division duplexing TDM TDD bus multiplexer can be provided to facilitate interfacing the baseband processor of the cartridge to various external devices such as a player or consumer equipment . As stated above the cable connecting devices having respective DTICs e.g. which can be configured to implement bus multiplexers in corresponding ones of two devices in communication with each other preferably comprises two wires for power such as line power and ground wires and two wires for supporting two wire differential communications. Baseband processor is illustrated as being connected to a TDM TDD bus multiplexer via a data bus and a digital audio bus . It is to be understood however that separate or discrete lines can be used to connect the baseband processor to the docking station via a cable.

The docking station for the configuration depicted in preferably operates as a wire pass through to a device such as a consumer equipment e.g. a stereo receiver shown in . The docking station has a cartridge interface or connector for electrically coupling the cartridge when it is inserted in slot to a connect and play interface . A four wire cable extends from the connect and play interface to the consumer equipment which preferably has a 4 prong or 4 socket connector to provide a DC voltage and ground to the cartridge when inserted in slot on two of the cable wires and to exchange communication signals with and receive SDARS content from the cartridge on the other two cable wires. An RF connector is provided for providing signals from an external antenna to the cartridge .

SDARS Digital Rights Management SDARS DRM for player devices will now be described in accordance with an exemplary embodiment of the present invention. SDARS DRM is preferably implemented via a management system which has been developed to control the recording and playback of SDARS content. The SDARS DRM system of the present invention preferably serves four main purposes as follows 

1. All recorded XM content is preferably protected from being able to be removed from the device . For example file control attributes are transmitted over the air or on line with the SDARS signal that control the device to disregard user attempts to remove recorded SDARS content.

2. Parameters such as restriction parameters can be transmitted with the SDARS content e.g. over the air or on line that can restrict recordings of channels programs or individual songs.

3. The device is programmed to verify that the user subscription is valid in order for recorded content to continue to play e.g. by receiving activation bits from the SDARS receiver or Connect and Play Antenna that were provided to the SDARS receiver or Connect and Play Antenna during activation .

4. Properties of the XM recorded content including the playback lifetime and content organization capabilities can be changed by additional over the air parameters.

Player devices do not enable unencrypted SDARS content to be stored on a removable storage media or to be transferred from the embedded storage media in accordance with an exemplary embodiment of the present invention. Preferably only SDARS Program Associated Data PAD such as the artist name song program ID and category may be transferred from the embedded storage media.

If the player provides visibility of stored metadata media PAD data and other attributes to external devices such as a connected PC in the form of an attribute file associated with each stored media file the attribute file preferably conforms to the SDARS Media File format described above. The SDARS Media Files exposed by the player do not include the actual recorded audio content in accordance with an exemplary embodiment of the present invention.

In accordance with an exemplary embodiment of the present invention upon detection of the Update Firmware command in the SDARS Directive File during power up the Device can locate the referenced SDARS Device Firmware Update File in the xmsys folder of the Public Content and Data Exchange Data Partition and if present verify the CRC of the file. If the firmware version is greater than or equal to the installed firmware version the Device installs the firmware deletes the SDARS Device Firmware Update File and reboots.

As shown in the PID can be used to identify the beginning of a new track in a sporting event. For example in a baseball telecast it may be beneficial to record each inning as a separate track. In the meanwhile PAD data changes to reflect changes in the score. In one embodiment when the score changes and PAD data correspondingly changes and internal PID of 0 is used. The PID 0 is recast as the previous PID so that the SDARS Device never sees a change in the PID. In this manner the SDARS Device separates tracks when it sees a PID change that is at breaks between innings of the baseball game. Alternately PID 0 could be transmitted to the SDARS Device but ignored by the SDARS Device until a PID change to a non zero value is recognized.

Exemplary embodiments of the present invention have been described with reference to a player PC controller e.g. player controller web server online music infrastructure and so one. It is to be understood however that the present invention can also be embodied as computer readable codes on a computer readable recording medium. The computer readable recording medium is any data storage device that can store data which can thereafter be read by a computer system. Examples of the computer readable recording medium include but are not limited to read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks optical data storage devices and carrier waves such as data transmission through the Internet via wired or wireless transmission paths . The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. Also functional programs codes and code segments for accomplishing the present invention can be easily construed as within the scope of the invention by programmers skilled in the art to which the present invention pertains.

While the invention herein disclosed has been described by means of specific embodiments and applications thereof numerous modifications and variations can be made thereto by those skilled in the art without departing from the scope of the invention.

