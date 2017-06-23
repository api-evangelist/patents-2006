---

title: Method and system for presenting events associated with recorded data exchanged between a server and a user
abstract: Events associated with recorded data exchanged between at least one user and at least one server are presented to a user. A set of events associated with the recorded data is defined, and each event within the set is represented by an event identifier, e.g., a time stamp. Each event identifier is associated with portions of the recorded data that correspond to the event represented by the event identifier. An event is selected for presentation by selecting the event identifier associated with a portion of the data that corresponds to that event.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07424718&OS=07424718&RS=07424718
owner: Verint Americas Inc.
number: 07424718
owner_city: Roswell
owner_country: US
publication_date: 20060323
---
This application is a continuation of and claims priority to U.S. application Ser. No. 10 136 705 filed on Apr. 30 2002 which is a continuation in part of commonly assigned U.S. patent application Ser. No. 10 061 469 filed Jan. 31 2002 now U.S. Pat. No. 7 219 138 a continuation in part of U.S. patent application Ser. No. 10 061 489 filed Jan. 31 2002 now abandoned and a continuation in part of U.S. patent application Ser. No. 10 061 491 filed Jan. 31 2002 all of which are hereby incorporated by reference. This application is also a continuation in part of commonly assigned U.S. patent application Ser. No. 10 058 911 now abandoned filed Jan. 28 2002 and hereby incorporated by reference. Also this application is related to copending U.S. application Ser. No. 11 388 944 entitled Methods and Systems for Categorizing and Cataloguing Recorded Interactions filed Mar. 23 2006 U.S. application Ser. No. 11 388 854 entitled Method and System for Selectively Dedicating Resources for Recording Data Exchanged Between Entities Attached to a Network filed Mar. 23 2006 and U.S. application Ser. No. 10 136 718 now U.S. Pat. No. 7 149 788 entitled Method and System for Providing Access to Captured Multimedia Data from a Multimedia Player filed on Apr. 30 2002 and hereby incorporated by reference.

The present invention is directed to a method and system for presenting recorded data. More particularly the present invention is directed to a method and system for presenting events associated with recorded data exchanged between a server and a user.

For systems employing interactions between a user and server it is often desirable to be able to view the interactions ideally in a manner that is transparent to the user. This is particularly desirable in a context such as sales customer service and e commerce where interactions between customers and a service provider are important indicators of customer satisfaction.

Attempts have been made to recreate interactions between a user and a server. For example click stream analysis procedures have been used to recreate interactions between a web user and a web service provider. This type of procedure is analogous to reviewing and analyzing the script to a movie. While this procedure reveals some information about the interaction between the server and the user it does not provide a clear tangible picture of special effects the environment chemistry between the user and the server etc.

Other attempts have been made to replay recorded interactions between a server and a user. However these attempts are typically implemented at the server and are thus suitable only for a particular type of server. The format into which the data is recorded is typically not accessible by a large number of users using conventional servers. Also the recorded exchanges often contain multimedia data e.g. text and audio which needs to be synchronized.

In addition these approaches typically do not distinguish between interactions that are considered important and interactions that are not important. Thus a lot of time and resources are wasted on replaying unimportant recorded interactions.

Also it may be important for users to be notified when certain events occur e.g. when certain data is recorded and to be able to search for recorded data associated with the events.

There is thus a need for a technique for providing access to multimedia data captured during exchanges between and a web server and a user. There is also a need for providing for notification to users of event occurrence and for enabling users to locate recorded data associated with the events.

It is an object of the present invention to enable a user to locate recorded data associated with events.

According to exemplary embodiments these and other objects are met by a method and system for presenting events associated with recorded data exchanged between at least one user and at least one server. A set of events associated with the recorded data is defined and each event within the set is represented by an event identifier e.g. a time stamp. Each event identifier is associated with portions of the recorded data that correspond to the event represented by the event identifier. An event is selected for presentation by selecting the event identifier associated with a portion of the data that corresponds to that event.

Further objects advantages and features of the present invention will become more apparent when reference is made to the following description taken in conjunction with the accompanying drawings.

According to exemplary embodiments access is provided to a multimedia player of data exchanged between a server and a user. In the following description the server is referred to as a web server and the user is referred to as a web browser. It will be appreciated however that the invention may be applicable to other types of servers and users.

Although only one web server page capture module and web browser are depicted in it will be appreciated that the invention is applicable to any number of servers data capturing modules and users.

The web browser may be implemented in a personal computer a telephone etc. The web server may be implemented as a server supporting any operating system e.g. Unix Linux NT or Windows 2000.

The page capture module is arranged between the web server and the web browser . For security purposes a firewall may separate the web browser and the page capture module .

The page capture module operates independently from the web server and the web browser . Thus the page capture module does not need to be customized for each type of web server but may be used with any web server supporting any operating system.

Although the page capture module operates independently from the web server and the web browser it may be implemented in the same device as the web server or the web browser .

The page capture module captures pages and other data exchanged between the web server and the browser . Pages and other data may be captured continually or at designated intervals or time windows. The page capture module may also record these pages and other data or recording may be performed in a separate recorder server connected to the page capture module.

Each web browser is assigned a unique machine identity ID by the web server . A persistent machine ID cookie may be created by the web server and stored at the web browser for this purpose. All pages served to a particular web browser are identified and grouped by the machine ID.

Although the module is described as a page capture module according to exemplary embodiments other types of data may also be captured. For example events and attributes may be captured. Attributes may be captured in a manner similar to that in which pages are captured as described above.

For event capturing according to an exemplary embodiment an event capture module captures user side events and delivers these to the page capture module . The event capture module may be implemented as an applet that is downloaded to the web browser . Although shown as a separate component the event capture applet is stored at the browser with parameters such as the web browser machine ID the host Internet Protocol IP address and the current page name. The event capture applet may be notified for example by JavaScript embedded in the current page whenever an event needs to be recorded. The event capture applet records events such as page load page unload page scroll page resize and browser exit. The event capture applet sends captured events to the page capturing module via for example a Transmission Control Protocol Internet Protocol TCP IP socket connection on port or port for secure exchanges .

Pages and other data captured during exchanges between the web server and the web browser at the page capture module are sent from the page capturing module to a page preprocessor via e.g. a TCP IP socket.

According to an exemplary embodiment each captured page is assigned a unique page ID and is associated with a specific browser user machine ID. Each page may also contain the date and time that the page was captured and the page status recording processing playback etc. After pages are captured this information is extracted from the captured page and a new record is inserted into a database .

The page preprocessor acts as a recorder server and stores the captured data in a device such as a database . The pages are then passed on to the page post processor . Alternatively the page capturing module may perform this recording. To reduce the amount of storage necessary only predetermined portions of data may be stored e.g. the request portion or the response portion. Also only data satisfying predetermined rules e.g. rules indicating timing may be stored. When the captured pages are recorded identifying information may also be recorded e.g. a session record ID a date time of recording a machine ID etc.

The page capturing module and page preprocessor are described in more detail in the afore mentioned U.S. patent application Ser. No. 10 061 469 filed Jan. 31 2002 now U.S. Pat. No. 7 219 138.

A post processing module determines which captured data satisfies predefined rules e.g. business rules and records this data in a playback database such as a JAR file. The database is updated to indicate what captured data has been selected and recorded for playback. The post processing module is described in further retail below with reference to .

A playback tool selects recorded data from the database using the information in the database . The playback module controls playback of the data. The data may be displayed for example in a search frame for the web server or the browser.

Although not shown in the interest of simplifying the illustrations it will be appreciated that the system in may also include other components e.g. configuration files used for processing and log files use for storing information for debugging etc.

According to an exemplary embodiment a user is allowed to search for select and playback a recorded browser session using the playback module . The playback module assembles a session of recordings selected by the user and plays back the session. The playback module may be implemented using e.g. Netscape 4.5x and above browser or an Internet Explorer 4.x and above browser. More details are provided for searching selecting and playing of a recorded browser session in the afore mentioned U.S. patent application Ser. No. 10 061 491.

According to exemplary embodiments business rules are applied to the recorded data in the business rule engine to determine whether a page should be saved for playback. A business rule may be defined as a statement that defines or constrains some aspect of a business. The business rule asserts business structure or controls or influences the behavior of the business.

Data from a page table database and a page rule table database may be used in the evaluation by the business rule engine . Pages that satisfy the business rules are recorded for future playback. The page table and page rule database are updated after post processing.

An example of a comparison of business rule with captured data may be determining whether the captured data is an interaction resulting in a sale greater than a predetermined number of dollars determining whether an interaction was longer than a predetermined number of minutes etc. As another example a business rule may state that the current page is to be recorded and all previous pages for that machine ID in that session. Also a business rule comparison may be in the form of voice recognition.

Page post processing is described in more detail in the afore mentioned U.S. patent application Ser. No. 10 061 489 filed Jan. 31 2002 now abandoned.

According to an exemplary embodiment the server includes a business rules engine such as the engine shown in an editor a scheduled rules processor a business object layer BOL a data abstraction layer DAL and and a repository or database . Alternatively the database may included as a separate entity e.g. if a large load is expected.

Data exchanged between the user and the server may include one or more contacts. According to an exemplary embodiment a contact may be considered an interaction between e.g. an agent within the same enterprise as the server and a user outside the enterprise. In addition to playing back data in sessions as described above captured data may be played back as one or more contacts.

A contact may include one or more events and some content representing contacts in a machine readable form. The events may include occurrences associated with entities external to the enterprise such as occurrences associated with Computer Telephony Integration CTI telephony or speech recognition. Also the events may include occurrences within the enterprise and occurrences associated with user initiated annotations.

Attributes of contacts and metadata may be stored in the database as well as business rule data populated and manipulated by the editor. The server communicates with the database to obtain the business rules. The engine applies the business rules to the captured data and communicates with a recorder server for recording the captured data that satisfies predetermined business rules. The BOL interfaces with both the business rule editor applet and the DAL and to manage traffic to and from the database .

According to an exemplary embodiment business rules may be added deleted copied pasted and or modified by a user such as a supervisor using the business rules editor implemented in the server shown . The server communicates with a client computer such as the computer . The client computer may be implemented as a browser based application utilizing Java applets and HTML and interfacing with some COM Java bridging tool Jintegra or R JAX to allow the Java based client to communicate with the COM based server. The business rules editor may be a Java applet running in a browser MSIE or NN on the client machine such as the computer shown in .

According to an exemplary embodiment contacts are organized and grouped into a contact folder. The contact s may be played back under the control of a contact manager as shown in .

Referring to a contact manager is in communication with the business rules engine for mapping business rules to folders. The business rules engine in turn is in communication with a BOL that communicates with the database e.g. through the DAL .

As shown in the contact manager may communicate with the business rules engine via an internal event notification service . The internal event notification service controls notification of event occurrences through e.g. an email notification service for e mail notification and a pager notification service for page notification. Notification is described in more detail below.

As shown in the contact manager is also in communication with the recorder via a content manager that manages how the content in a contact is recorded. Also the contact manager is in communication with the client via a call or session manager that manages session playback a DCOM interface and a CTI adapter . The contact manager also communicates with the event persistence e.g. through the internal event notification service . The contact manager also communicates with the event persistence e.g. through the internal event notification service . The event persistence maintains events and permits a user to jump to a point in a contact at which an event occurred. The event persistence in turn communicates with the database .

Also shown in are a scheduler and a live monitoring and playback service . The scheduler coordinates scheduling of event occurrence. The live monitoring and playback service controls playback of recorded data and live monitoring of data and is connected via a playback socket to a user desiring to playback or monitor the data.

Recorded and or live contacts may be replayed to a user under the control of the contact manager and the live monitor playback server connected to the user via a playback socket. The live monitor playback server may be considered as part of the playback module shown in .

The components to the right of the dashed dotted lines in may be implemented e.g. in an application server . Alternatively some of the components shown to the right of the dashed dotted lines in may be implemented as separate entities.

A contact may include voice graphical user interface desktop data an e mail message or a web transaction. A list of contacts may be displayed to a user for playback as shown e.g. in described below and in more detail in the afore mentioned U.S. patent application Ser. No. 11 388 944 entitled Methods and Systems for Categorizing and Cataloguing Recorded Interactions and filed Mar. 23 2006.

When a user selects a contact from the contact list page in the contact module a new browser window may be displayed as shown in . The browser contains an applet that displays all the events for the contact. The applet may also contain a player.

According to an exemplary embodiment each event recorded in a contact may be assigned an event identifier. This may be in the form of a time code or a timestamp. For example voice data may be given a time stamp and text data may be given a time code.

For playback of events a list of events may be displayed via a player in sequence on an event list e.g. top to bottom in the order in which the event time stamp occurs. This is illustrated e.g. in which show an event list of e mail events and in which show an event list of call events.

The screens shown in may be divided into two parts e.g. a right pane and a left pane. According to an exemplary embodiment the left pane contains the contact name and the event list. The event list may be scrollable. The right pane contains one or more tabs. One tab may labeled content and the other tab may be labeled attributes.

When the event list screen is first opened the user may be presented with the contact name at the top of the left pane and a list of events below the contact name on the left pane. The first event may be preselcted automatically and its content table may be visible in the right pane.

The interface allows all events associated with a contact to be displayed. If the user does not have security privileges to the events they may not be displayed.

Referring again to when a user selects an event name in the left pane the right pane displays the content tab open and the attributes tab behind it. Upon selection of the content tab the screen shown in for e mail events or for call events is displayed. Upon selection of the attributes tab the screen shown in for e mail events or for call events is displayed. On the attributes tab all the attributes of the event are displayed including the attribute name and value. Also right mouse clicking on an event may cause the attributes of the event to be displayed.

For example if the contact is an e mail message the player has the ability to show information for each event in the contact in text format. The e mail contact may be stored in the event as an attribute. There is no content to display for e mails.

An e mail event in most cases contains the text of an e mail message. However this is not always the case. For example if an e mail does not reach its destination then this would correspond to some event but there would not necessarily be an e mail message associated with the event. Some text may be displayed describing the event. The text of an e mail message may be obtained from the corresponding attribute.

If the event is an e mail event and the address and text attributes are present the re constructed email may be displayed in the content tab as shown e.g. in . The content includes the re constructed email including addressing information and the e mail text with some icon representation of any attachments. The applet shows a list contains all the events emails in a chain. An e mail may be displayed by selecting it from the events email list. If the e mail cannot be reconstructed the message there is no available content for this event may displayed instead.

In the content tab shown in the event attributes may include anything. It the attributes contain the email address an text attribute the e mail may be reconstructed to include to information which may include many names separated by semicolon a sender the date time sent a cc recipient string a bcc recipient string the subject line the email text which may be scrollable and any attachments. If it is not possible to reconstruct the email from the attributes present for the event a message such as no viewable content exists for this event may be displayed in the content window.

If the contact is a voice graphics user interface contact e.g. a call content and attribute data may be displayed as shown in respectively. The these types of contacts the player has the ability to play the voice graphical user interface data for all events in the contact. This includes all annotations and bookmarks. The content of the agent desktop if any may be displayed on the screen C.

In addition to the content screen shown in controls for play pause stop fast forward and rewind may be displayed along a progress bar as shown e.g. in . The user may use any of the controls to navigate through playback. Any action requested applies to both voice and graphical user interface data. A pointer representing the relative position of the listener in the contact may be displayed on the timeline bar. Also by selecting an event in the list the user may jump to a specific location in playback.

Once a contact has been played back an indicator may be set that the contact session has been reviewed. This indicator may be stored as a value in the database. An icon representing the reviewed unreviewed status may appear on the contact list of contacts.

There may be a limit to the number of contacts that may be recorded without having been reviewed. To keep track of unreviewed contacts in addition to setting an indicator the count of unreviewed sessions may be decremented by one. This prevents contacts continually being saved without the events being reviewed. The unreviewed contact counter may be stored in the database.

For contact events in the left pane the event name may be preceded by one or more icons which indicate the type of media involved in the event whether the media is voice and GUI voice only or e mail. An example may be business rule triggered events or annotations. Annotations may include voice and or text. Business rule trigger events have no icons.

If one or more business rules have been triggered on this contact the name s of the business rule s triggered may be displayed. If the user selects a business rule name from the left pane the content tab in the right pane displays the content of the event which triggered the business rules. If no content is available e.g. because the business rules was triggered after a call a message no viewable content for this event may be displayed. If the event was a voice event play may begin at the point where the business rule was triggered e.g. at the time stamp in the contact content.

In addition to playing back recorded contacts between a server and a user agent initiated monitoring AIM recorded contacts may be played back. Also live monitoring may be provided in which a data exchange is played back as it occurs.

If AIM recordings have been stored for an event a caption agent initiated monitor agent name may be listed in the event list one for each occurrence. If live monitor recordings have been stored for an event a caption live monitor record by name of person may be listed in the event list one for each occurrence.

In addition to playing back recorded events and live monitor playback a user may annotate contacts upon playback. Contact annotation is the process of adding text or voice to a contact during playback.

According to an exemplary embodiment to annotate a contact a user selects a contact in a contact folder using e.g. a screen such as that shown in . This causes the event viewer such as that shown in to be displayed. The user may make voice and text annotations to the contact.

The name of each annotation created for a contact may be displayed unless the annotation is marked private. If the annotation is marked private it may only appear in the list if the user is also the annotation owner. To the left of the annotation name an icon may appear to indicate if the annotation is voice or text.

At any point in the replay the user may add an annotation by selecting pause on a player controller such as that shown in and then pressing tools annotation create voice text annotation. Alternatively the system may automatically pause if the user attempts to create an annotation during play.

If text annotation is requested an interface such as that shown in for providing text data may be presented to the user. Once the user requests to save the information the text data is sent to a contact annotation service. The annotation service creates an event and sends it to the event notification server.

Voice annotation may be implemented as follows. If s user is listens to playback on a soundcard then the voice annotation may be done performed via soundcard. If the user is listening to playback via a phone then the voice annotation may be performed via phone.

If voice annotation is requested through a phone a request is made to an annotation service implemented e.g. in the applications server to record for the agent extension. For example the annotation service may use e.g. the voice card shown in for receiving requests for annotation. The annotation service passes the agent extension to the content routing service and requests that recording begin. In an exemplary embodiment the telephony data manager and the n data manager shown in may act as the content routing service. The annotation data may be stored in a database. The content routing service returns a globally unique content identity that may be used to refer to the recorded information.

The user indicates that recording is complete via a user interface control. At this point the user makes a request to the annotation service that records stop for the particular agent extension. The annotation service forwards this request to the content routing service to stop the recording.

If voice annotation is requested through a soundcard microphone the recorded data and its length are passed to the annotation service. This data is forwarded to the content routing service. The content routing service returns a globally unique identifier that may be used to reference the recorded information.

According to an exemplary embodiment the annotation may be given the date time stamp of its relative location in the contact. When the annotation is complete the play may be resumed by clicking the pause control again.

As annotations are added saved the event list may be dynamically updated to include the new annotations.

A user with appropriate access may view an annotation. To view an annotation the user selects the annotation in the event list. The annotation may then be displayed if it is text or played back if voice . An example of an annotation to an e mail message is shown in .

In addition to viewing annotations by selecting annotations in the event list annotations may be viewed using e.g. a player control including annotation names as shown in . When a mouse is moved over the inverted triangle representing an annotation the name of the annotation appears. The triangle under the timeline bar represents the relative position of the listener in the contact.

In addition to annotation the ability to notify parties is included. Notification may be implemented using a system such as that shown in using the internal event notification service .

For notification property screens such as those shown in may be displayed. Referring to if notification is desired the send notification checkbox may be checked or the notification tab may be selected activating the notification tab on the property sheet.

According to an exemplary embodiment there may be different types of notifications e.g. e mail notification page notification PDA device notification WAP device notification 3G wireless cellular phone notification etc. For simplicity of illustration only e mail notification and page notification are described below.

The notification pages shown in correspond to e mail notification and pager notification respectively. In the exemplary implementation shown in e mail notification is controlled by the e mail notification service and pager notification is controlled by the pager notification service .

According to an exemplary embodiment notification follows a similar routine whether it occurs via e mail pager PDA WAP 3G or any other suitable device. First the users who will receive the notification must be assigned. For setting notifications it is assumed that the notification recipient s information is defined within the user profile and that this information is requested when necessary. For example for e mail notification it is assumed that the recipient s e mail address is defined in the user profile.

User names may be multi selected from the left hand user list in the screen shown in and the users may be assigned to the notification list by clicking the top button. For advanced users simply double clicking on the user name in the left hand list may add the name to the right hand list. The opposite also holds true. User names may be multi selected in the right hand list and the bottom button clicked to remove them from the notify list or the name may be double clicked.

For e mail notification there may be two options for the subject line the rule s name may be used or some user specified text may be used. The body of the e mail may be entered into the text box labeled for e mail text. A notification frequency may be set to indicate how often the user s should be sent an e mail message when the rule is fired. This may be tracked by the business rule engine.

As shown in the configuration for notification via pager is very similar to that for e mail. The assignment of users follows the same method. Where the e mail definition dealt with a subject line the pager setup requires the actual text to be sent to the pager. The options are to either use the rule name or to use some user defined text. The paging time constraint restricts the time that users may be paged to a specific time range. Again as with e mail notification a notification frequency may be set.

Notifications are particularly useful when interactions are played to an entity outside of the enterprise. For example an entity outside of the enterprise using e.g. Windows media player may desire to access the data. This entity may be e.g. a supervisor interested in viewing or personnel in other parts of the company. This outside entity may not have equipment necessary to playback the recorded interactions in the format in which they are stored in the enterprise e.g. VOX format for voice data and proprietary DAT format for text data. Also since the data may contain media of different types the data needs to be synchronized before being presented to the media player.

Thus according to an exemplary embodiment voice and data e.g. desktop content of a contact may be converted to any audio video format easily accessible without requiring special hardware. Examples of such an audio video format into which the contact may be converted include an audio video interleaved AVI format a Moving Pictures Expert Group MPEG format etc.

The converted file may be saved in an HTML format and associated with a hyperlink or Uniform Resource Locator URL that is accessible by launching a media player. This is described in more detail below. Alternatively the user may choose to email the converted file and the converted file may be provided as an attachment to an email.

For exporting a contact the contact folder that contains the contact to be exported may be selected via a contact tab such as that shown in . Once the contact is selected the export feature may be selected using a contact editing pop up menu such as that shown in .

Rather than selecting a contact to export using the contact tab the playback event viewer may also include a button for export contact . This may only be visible if a user has permission. The playback event viewer may also contain validation to allow this on CTI contacts only not e mail or web contacts. An error message may be generated if validation fails.

If the export contact button is selected while the contact is being replayed the replay may be paused until the conversion is complete and the user has specified the file name and path for the converted file. Then replay may resume.

Using the dialog box shown in a user may decide whether to export audio data only video data only or audio and video. The selected contact is then converted into a format compatible with the multimedia player. While the conversion occurs a window may display the progress as shown in . If conversion of the contact fails a message may be generated.

When the conversion is complete the converted contact may be saved and a hyperlink may be created for the contact using the screen shown e.g. in . The file type may be passed back to the browser which may then display a file SaveAs box. The user selects the path and name. For an AVI file the extension is forced to avi .

If the save is not successful an error message may be displayed. If successful the file Save As box is closed and replay resumes if the contact was paused in replay. Otherwise direction from the user is awaited.

A user may decide to view the contact or e mail the link to the contact using a dialog box such as that shown in . To e mail the contact link the user may be presented with a default mail client set to composed and the unique contact name may be displayed in the subject line as shown in . The user completes the to field in the e mail window and any other information in the body of the message and selects send . The hyperlink link for the contact may then be sent to the e mail addresses.

A multimedia player may then be launched from a machine to view the contact by linking to that URL. The media player may be launched from a control panel screen such as that shown in . The converted contact may be replayed by commercially available media player which may be chosen by the customer and obtained at the customer s option.

Contacts may be retrieved from an archives and converted to an audio video format in a similar fashion.

An audit trail data of converted contact may be available for reporting at customer s option. The audit trail may include information indicating what entity converted the file the contact name and the date. The audit trail may be handled similarly to reporting.

As shown in a recording interface receives signals from a recorder server . Also the recorder interface is connected to voice card drivers via a telephone network connection manager for receiving control data. The recorder interface outputs control signals to the central unit which in turn outputs control signals to the LAN data managers and the telephony data manager and the n data manager .

A node manager starts various processes performed by the components and monitors their progress. A time synchronization unit provides a synchronization signal to all components so that the playback of the recorded contacts is synchronized.

The LAN data manager receives captured screen data e.g. from an agent s desktop from screen data record units and . This data may be stored in a local storage and then transferred to a database via the data store manager .

The telephony data manager receives captured voice data via a voice card driver . This data may also be stored in the local storage and transferred to a database via the data store manager . Also this data may be provided e.g. back to the agent for live monitoring.

Screen data in the local storage may be provided to the LAN data manager for playback e.g. to an agent or a supervisor via the playback module . The playback module synchronizes data of different media types e.g. voice data and text data. This may be performed by matching e.g. the time codes of the voice data and the time stamps of the text data.

The playback module also converts the multimedia data into an audio video format suitable for a multimedia player e.g. an AVI format or an MPEG format. The playback module then exports the data to local storage . When a media player is launched from e.g. a browser outside the enterprise the converted audio video format file may be retrieved from the local storage and played back.

A n data manager receives data from the local storage and outputs data to other applications as desired.

According to exemplary embodiments captured multimedia data may be recorded and stored annotated and exported for playback to any media player. Also users may be notified upon recording and storing.

It should be understood that the foregoing description and accompanying drawings are by example only. A variety of modifications are envisioned that do not depart from the scope and spirit of the invention. The above description is intended by way of example only and is not intended to limit the present invention in any way.

