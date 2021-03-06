---

title: Media content at the end of a communication
abstract: A method includes playing a video clip upon the end of a communication between two users. Another method includes playing an audio clip upon the end of a communication between two users. The audio clip may have been downloaded to a device of at least one of the users or it may be selected by a first user for playing on the device of a second user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08626830&OS=08626830&RS=08626830
owner: Vringo Inc.
number: 08626830
owner_city: New York
owner_country: US
publication_date: 20061016
---
This application claims benefit from the following U.S. Provisional Patent Applications 60 771 883 filed Feb. 10 2006 60 772 564 filed Feb. 13 2006 60 819 621 filed Jul. 11 2006 and 60 841 233 filed Aug. 31 2006 all of which are hereby incorporated in their entirety by reference.

The present invention relates to communication devices generally and to personalization content sharing on the communication devices by a community of users in particular.

Cellular telephones are known in the art. Such devices were originally developed to provide mobile telephony services to users who for reasons of preference convenience or circumstance required wireless connections to a public telephony network. The earliest cellular telephones were dedicated devices that lacked the capability to be used for other purposes.

Recent cellular telephones have more advanced operating systems that enable users to enrich and personalize their mobile telephony experience. For example users can display or play media content such as photos video clips and audio files.

One of the most popular ways to personalize a mobile user s telephony experience is to select a unique audio ringtone to be played for incoming calls. The ringtone selected by the user overrides the default ringing sound selected by the telephone manufacturer.

Some cellular telephones run software that supports the definition of unique ringtones for a specific contact or for groups of contacts.

Some of these cellular telephones support user definition of a photo or video clip to display when an incoming call is received from a specific contact or group of contacts.

The media files used for these personalization services are available from a variety of sources. A small selection of files is usually pre loaded on the devices prior to their distribution. The devices also often come equipped with cameras and audio recorders that may be used to create such media files on the devices themselves. Files may also be transferred from other devices in the user s possession via a physical connection or a short range wireless connection technology such as Bluetooth or infra red. Some media files are also typically downloaded over the air across an Internet connection via the connection supplied by the mobile network operator or other media content provider.

Some cellular network operators have introduced ringback personalization services which enable a mobile subscriber to define the audio clip that the network operator will play instead of the normal ring for someone calling the subscriber s phone number.

Ringtones and Ringback tones are available in other systems as well. SIP Session Initiation Protocol which may be used to connect devices for a voice over IP VoIP connection also provides an option for the selection of alternative tones. The alternative tone may be indicated by a URL universal resource locator that may be used to download the tone at the time the connection is made. The download may be performed using a different channel than the VoIP connection.

 Endtone personalization services may soon be offered by network operators. Endtones may include specialized disconnect tones to notify wireless device users that voice and data connections are terminated. Endtones have been announced by Endtone of the United States.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numerals may be repeated among the figures to indicate corresponding or analogous elements.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

Applicants have realized that there are several barriers to the introduction and success of systems that provide voice connections concurrent with the download and play of media files. Such barriers include for example the inability of many current mobile networks to provide concurrent voice and data connections to a single device. Certain variations of a relatively new mobile network technology known as 3G are capable of providing concurrent voice and data connections. However 3G networks may still suffer from latency that may affect the quality when attempting to synchronize the download and play of media files with a voice connection. Furthermore the repeated downloading of media files is often prohibitively expensive.

Applicants have realized that creating a community to define media files to be played when two friends or buddies communicate may provide the illusion of real time sharing of media content between the two buddies. Such media files may be downloaded to a buddy s device prior to the conversation.

Reference is now made to which illustrates a novel media content sharing system capable of providing the illusion of real time sharing of media content between a novel communication device owned by for example Jack and a telephone owned by for example Jill who are simultaneously setting up or using a voice connection for a telephone conversation.

In accordance with one preferred embodiment of the present invention Jack and Jill may both be members of a media content personalization sharing community organized through a community server . Community server may be a web server including for example a media file database .

Members of community such as Jack and Jill who elect to share personalization content i.e. media files such as photos audio clips and video clips with each other are said to be buddies. Typically the buddy sets of the members are not the same.

In a preferred embodiment of the present invention individual members of community may select arrow media content on community server that they wish some or all of their buddies to see and or hear. For example Jill may select a media file . At some other time each member may download arrow to their own devices the selected media content of his her buddies. Thus Jack may download a version of media file to his device where media file may be a version of the file suitable for presentation to Jack on his device. It will be appreciated that such a download may be performed as an occasional automated procedure initiated by Jack s device or as one initiated by Jack or as one initiated by server in response to new selection .

Novel device may be any suitable smart phone capable at least of providing telephony services downloading data and of presenting a variety of media content. Novel device may include a media player among its standard feature set and in accordance with a preferred embodiment of the present invention may also comprise a personalization content manager and a media file storage unit capable of receiving and storing media file . Telephone may be a novel communication device like device or it may be any suitable telephone such as a landline phone a mobile phone a digital phone a VoIP phone or an analog phone.

On the occasion of a telephone connection between Jack and Jill over voice connection personalization content manager may cause media file selected by Jill to be played on media player of device belonging to Jack. It will be appreciated that since media file may belong to Jill and may be downloaded to device without any intervention from Jack Jack may have the illusion that media file was provided from Jill across connection at the time of the telephone conversation without any latency.

It will further be appreciated that media file was not provided concurrently by the operators of voice connection even though Jack may have the illusion otherwise. It will still further be appreciated that media file may be played even on pre 3G devices as long as such devices can download and play media files.

Reference is now made to which illustrates the method performed by device to play media file when simultaneously involved in a voice connection operation with telephone .

Personalization content manager may remain step in a wait state until notification of an activating event is received. Activating event may be for example a call initiation a call ringing or an end of call . Call initiation may occur when device is used to initiate a call to telephone at the point of dialing or connecting. Call ringing may occur when device detects an incoming call from telephone . End of call may occur when a phone conversation between device and telephone ends and is determined by notification of a hang up or idle state.

After activating event may be received personalization content manager may retrieve step the telephone number of telephone and may use it to look up step the media file associated with Jill whose telephone number was retrieved.

Personalization content manager may then launch step the associated media file for play by media player . Media player may stop at the completion of media file or may continue to play media file in a continuous loop until personalization content manager may receive notification of an ending event . Ending event may be for example a call connection a call answering or a call hang up .

Call connection may occur when telephone answers a call initiated by device . Such a state may apply when activating event was for example call initiation . Call answering may occur when device answers an incoming call initiated by telephone . Such a state may apply when activating event was for example call ringing .

Call hang up may occur when the phone conversation between device and telephone ends such as when either device or telephone hangs up. Such a state may apply when activating event was for example either call initiation or call ringing and the connection may not have completed between device and telephone .

After personalization content manager receives notification of an ending event personalization content manager may stop step media player after which personalization content manager may return to wait state .

In accordance with a preferred embodiment of the present invention Jill may have selected a different media file for each activating event. Accordingly personalization media file database of device may include for example a personalization media file A to be played for call initiation event a second personalization media file B to be played for call ringing event and a third personalization media file C to be played for end of call event .

It will be appreciated that more than one activating event may occur during the course of a single connection between device and telephone . For example call initiation may occur when device calls device . Personalization content manager may play associated media file A until for example call connection occurs. Jack and Jill may then conduct a typical telephone conversation. When the telephone conversation ends personalization content manager may play the media file C associated with end of call .

Similarly for example call ringing may occur when device receives an incoming call from telephone . Personalization content manager may play associated media file B until for example call answering occurs. Jack and Jill may then conduct a typical phone conversation. When the telephone conversation ends personalization content manager may play the media file C associated with end of call .

It will be appreciated that additional examples of activating event may occur at any time during the set up execution or end of a telephone call between device and telephone .

In an alternative preferred embodiment of the present invention such additional examples of activating event may also be associated with unsuccessful attempts to complete a connection and conduct a typical phone conversation. For example activating event may be a busy signal network congestion fast busy signal or call waiting. In accordance with this embodiment Jill may select one or more media files for these activating events as well.

Reference is now made to which represents an exemplary user media table which may be stored on community server . For every user in table there may be one or more records indicating activating events and the associated media files to play for each activating event .

In accordance with the embodiment of Jill may have selected the media file VID1.3GP for playing on the device of her buddies whenever a buddy initiates a call i.e. call initiation to Jill. Jill may also have selected the media file VID2.3GP for playing on the device of her buddies whenever she calls a buddy i.e. call ringing . She may also have selected the media file VID3.3GP for playing on the devices of her buddies whenever a phone call between her and one of her buddies ends regardless of who initiated the connection.

Other information which may be stored in the user media table may include account information for the user the content source such as a universal resource locator URL for each media file and or a record of when the file was copied from the server to media file storage unit . It will be appreciated that the data in is exemplary in nature and does not represent an exhaustive listing of the possible events for which Jill may select media files to play. For example in accordance with an alternative preferred embodiment of the present invention user media table may also include selections of media files to be played when a caller receives a busy signal a fast busy signal or call waiting.

In accordance with an alternative preferred embodiment of the present invention user media table may also include selections of default media files to be played when Jill is called by someone that does not meet any of the criteria for her other selections. For example a caller may not be a member of community . It may also be possible that Jill s caller may be a member of community but may not be Jill s buddy. Another possibility may be that Jill s caller may be indeed be her buddy but that neither she nor such caller have previously selected a media file to be played in such a situation. Jill may select one or more default media files to be played in such situations.

Different versions of user media table may be located on device and on community server . Device may store a local version which may be a small portion of table having the records of only those buddies of the owner of device . Community server on the other hand may store the entire table for all the members of community .

Reference is now made to which illustrates a user buddy table that may be used to define relevant records to be stored in each local version of user media table . For every user in table there may be one or more records listing his buddies . In user is listed as having buddies user user user and user and user is listed as having user as his buddy.

Reference is now made to which shows an alternative format for user buddy table here labeled . Table records users and their buddies as before. In addition to enable users to share different media files with different buddies buddy table may record which media files are to be shared with which buddy for which type of activating event .

In accordance with a preferred embodiment of the present invention community server may update the local version of user media table from time to time as discussed hereinabove with data stored in the server version of user media table . The update process may refer to buddy table to determine which records to download to the local version as well as which files to download.

The update process may define a population of records in buddy table where user matches the name of the owner of device . The process may then download records from the server version of user media table for the relevant user .

It will be appreciated that tables and may be updated and stored in other ways and such other ways are included in the present invention. For example and not inclusive tables and may be stored locally. Additions and changes to them may be generated on community server and may be downloaded to device at the appropriate moment. They may be deleted thereafter from community server .

Reference is now made to which details one exemplary device with its personalization content manager here labeled implemented on a mobile telephone. Device may comprise as part of its feature set an operating system a media player and a phone application to which may be added personalization content manager and a personalization storage unit .

Operating system may provide connectivity between the elements of device typically via operating system application programming interfaces APIs . In accordance with a preferred embodiment of the present invention the operating system of device may be Symbian OS commercially available from Symbian Ltd. of the United Kingdom. Alternative embodiments may include for example BREW commercially available from QUALCOMM Incorporated of the United States or derivatives of Microsoft Windows for mobile devices such as Windows Mobile or MS SmartPhone commercially available from Microsoft Corporation of the United States.

Phone application may comprise for example all the functions necessary for device to operate as a cellular telephone and may interface directly with operating system . Phone application may pass phone number and caller id information to personalization content manager through standard operating system APIs. Similarly personalization content manager typically may launch the media files via operating system which may in turn start up media player .

Personalization content manager may be started as a resident application when device may be booted up. Manager may remain in a dormant wait state until the user initiates a call to another device or when an incoming call is detected.

Personalization content manager may comprise a main program a line status determiner and a phone number determiner . Line status determiner may make API calls to operating system to receive indications of when an activating event occurs. Line status determiner may forward the status to main program . Main program may activate phone number determiner whenever line status determiner may indicate that an activating event has happened and phone number determiner may determine the phone number associated with the activating event. In one embodiment phone number determiner may monitor changes in a phone log not shown to find the currently active phone number. In another embodiment phone number determiner may register to receive the phone number whenever operating system provides indications of a new event to line status determiner . Main program may then use this phone number to look up the associated media file in storage unit .

For some phones operating system may accord the highest processing priority to phone application to ensure that the telephony services take precedence over the execution of other operations such as the playing of media files. Similarly phone application will typically be in a window group with the highest z order priority which determines precedence for the display of application data on the device screen. Such z order priority may interfere with the display of media file . Therefore in accordance with a preferred embodiment of the present invention main program may raise the priority of the window group associated with media player in order to enable its display to take precedence over the displays of phone application . Alternatively main program may raise the process priority of the process associated with media player or with personalization content manager .

It will be appreciated that some cellular telephones may not gracefully handle such changes to priority of the window and or of the process. The behavior may vary greatly in response to even minor changes in the handset model or embedded firmware. However in accordance with a further preferred embodiment of the present invention the properties of newer cellular telephone handsets may be utilized. Some handsets such as the Sanyo MM 7500 allow the user to select video ringtones to be played in response to incoming calls. Certain of these handsets such as the Sanyo MM 7500 even allow the user to specify specific video ringtones to be played in response to incoming calls from particular users.

In accordance with a further preferred embodiment of the present invention such handsets may provide a programming API accessible to downloadable applications similar to personalization content manager that allows an upgraded manager to specify the video ringtone to be associated with a contact in the contact list. When such an API may exist the upgraded manager may operate as follows 

When a call comes from a buddy the built in phone software may react to the caller id and may play the associated media content properly.

Furthermore in accordance with a further preferred embodiment of the present invention such an API may also allow the registration of a video ringtone that would play at other activation events such as call initiation end of call or the various busy indications regular busy fast busy or call waiting such as described hereinabove. When such an API may exist the appropriate media content may be played for each activation event and not just for call ringing.

As detailed in the embodiments the media file played when a given member of community receives an incoming call may not have been selected by that same member. Indeed depending on the number of associated buddies it may be likely that a large number of constantly changing media files may be played for incoming calls such that a given member of community may not recognize the fact that an incoming call is on his her device . Accordingly in a preferred embodiment of the present invention members of community may also select a self ID media file to be played before media file for all incoming calls. With this members of community may recognize the incoming call as being on their devices even though they may not recognize the sounds which follow.

Reference is now made to which illustrates a preferred embodiment of the present invention in which the playing of media file may be occasioned by an event other than a voice connection between devices operated by Jack and Jill.

Playing device may be owned by Jack and may be any programmable device capable of storing and playing media files. Such a device may be for example a desktop computer running VoIP software such as Skype available from Skype Limited of Luxemburg a handheld device having communication capabilities or a soft phone. Jill s unit may be any device or method by which Jill may contact or be contacted by playing device . As in the embodiment of Jack and Jill the owners of playing device and unit respectively may be members of media content personalization sharing community using community server to select and download media files .

Activating event may be associated with any form of communication between playing device and Jill s unit including for example email SMS instant messages or VoIP. Activating event may also be associated with any detail of such communication including for example the timing length or contents of the communication as well as the identity or presence state of the initiating entity.

It will be appreciated that in addition to being a video file an image or an audio file as discussed hereinabove media file may also be a request to invoke or launch a previously installed program or application. In the latter case media file is not necessarily played by a media player.

In accordance with an alternative preferred embodiment of the present invention media file may be an audio file played at the end of a call. For such an embodiment audio file which may be much smaller than a video sequence may be downloaded from the other party to the conversation which may or may not be a buddy at any time including prior to the conversation or during the conversation for devices that can perform simultaneous voice and data transfer. For devices that cannot simultaneously transfer voice and data the download may occur just after the conversation ends. This download may occur from the community server or along the voice channel. In the latter embodiment the network operator may provide media file .

Reference is now made to which may describe a further alternative embodiment in which the communication channel may be an instant messaging IM channel between the users Jack and Jill. In this embodiment the communication channel may include an IM server . Jill s device may be an IM client and Jack s device may include an IM client in addition to media player personalization content manager and storage unit .

As is known in the art instant messaging also known as IM or chatting typically comprises the sending of textual messages emoticons and or animated emoticons between two users such as between Jack and Jill. In accordance with this embodiment of the present invention Jill may additionally send Jack a triggering event such as an identifier during their conversation. An exemplary identifier may be a file name a number or a URL of media file to be played.

Jack s IM client may recognize identifier and may transfer it to personalization content manager along with some indication of the source of event e.g. Jill . As in the previous embodiments manager may retrieve media file indicated by identifier and may play it on media player . Prior to playing media file manager may additionally check to see that the source e.g. Jill was authorized to send identifier .

As in the previous embodiments media file may have been previously downloaded to Jack s device from community server . Alternatively it may be downloaded the first time that Jill may send identifier and may be stored for later use when Jill may again send identifier .

It will be appreciated that IM server may be implemented separately from or as part of community server . If servers and are implemented together the combined server may perform part of the operation of IM client . Thus the combined server may check to see that the source e.g. Jill was authorized to send identifier and or may download the associated file if it was not previously downloaded to device .

It will be appreciated that as shown in to which reference is now briefly made personalization content manager may be implemented in many different types of devices of which four have been discussed above and three are shown in . In addition to smart phones cellular telephones programmable devices and devices that allow instant messaging manager may be implemented on any type of device and for any type of platform which has communication ability and media playing abilities. Such other types of devices include but are not limited to mobile handsets Skype IM sessions the new outside screen on laptops IP Internet Protocol phones with color screens caller id pop ups on televisions etc.

For example shows four exemplary devices a television with a caller id pop up a laptop computer with a secondary display on the back of the cover a video telephone with a screen and a personal computer with a IM session with their elements including a device processor to run the standard operation of the device.

The delivery mechanisms through which communication may occur are varied and may include but are not limited to IP SIP session initiation protocol SMS short message system IVR interactive voice response etc. It will be appreciated that the personalization content sharing may be managed through community server irrespective of the delivery mechanism.

Furthermore while the personalization content manager may be different for each type of device and or delivery mechanism and thus is labeled A B C and D in each manager may include at least main program not shown in which may manage the downloading and storage of media content files and may provide the media file associated with the current buddy to whatever media player labeled A B C and D the device may have. In some embodiments main program may provide media file in response to receiving an identification of the current buddy from a call handler or an identification handler of the device. Typically such identification is a caller ID type identification but other identifications such as customer number etc. may also be utilized. In other embodiments where the device has the ability to play different media files per identification main program may provide the media file for association with a given buddy prior to its use.

Alternatively if call handler or ID handler is not capable of providing the identification manager may determine it from other information available on the device.

While certain features of the invention have been illustrated and described herein many modifications substitutions changes and equivalents will now occur to those of ordinary skill in the art. It is therefore to be understood that the appended claims are intended to cover all such modifications and changes as fall within the true spirit of the invention.

