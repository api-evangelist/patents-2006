---

title: Translation management system
abstract: A translation management system in a computer environment. A preferred embodiment of the invention automatically detects when a document, data stream, or non-text file in the master language has been updated and notifies the user which corresponding documents, data streams, or non-text files in the other languages require translation which are then staged and dynamically routed and sequenced to individual translation resources where the actual translation is performed. Management status, reporting, scheduling, and accounting information is sent to the user as the translation process ensues. The user is notified of the completion of translation and the invention coordinates the delivery of the translated documents, data streams, or non-text files back to the user's site for installation and optional review. The invention makes a variety of translation resources instantly available to the user which include both automated translation tools as well as human translators. The translation resources are connected to the invention using a flexible architecture that can be deployed on intranets as well as the Internet.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08489980&OS=08489980&RS=08489980
owner: TransPerfect Global, Inc.
number: 08489980
owner_city: New York
owner_country: US
publication_date: 20060518
---
This application is a Continuation Application of U.S. patent application Ser. No. 10 313 518 filed Dec. 5 2002 now U.S. Pat. No. 7 207 005 which is a Continuation Application of U.S. patent application Ser. No. 09 239 495 filed on Jan. 28 1999 now U.S. Pat. No. 6 526 426 which claims priority from Provisional Application No. 60 075 740 filed on Feb. 23 1998 which are each incorporated herein in their entirety by this reference made thereto.

The invention relates to the multilingual translation of documents in a computer environment. More particularly the invention relates to the management of monolingual documents data streams non text files and databases to enable their translation into target languages in a computer environment.

The surge of growth in Internet access across the world has created the need for multilingual Web sites. The majority of Web sites are created in English which creates a problem for non English speaking Internet users. This also creates a problem for Web site managers that maintain Web sites that are or attempt to be multilingual. The Web site content must be constantly maintained to be up to date and synchronized in all of the languages supported by the Web site.

One approach is shown in PCT International Publication Number WO97 18516 of Flanagan et al. published on 22 May 1997. This application integrates a machine translator in the end user s Web browser. The user selects the desired target language and the Web document retrieved by the browser is then translated by the machine translator. Unfortunately errors occur in the translation and the appropriate content is not consistently displayed to the user.

An alternative implementation in the above application places pre translated Web pages on a Web server. The Web server stores all of the translated Web pages locally. The Web site visitor sends a request to the Web server for a page in a specific language. The Web server searches for the pre translated page that has been stored locally and sends it to the Web visitor s Web browser. This creates a storage and file management problem on the Web server because of the duplication of each entire page of the Web site.

Some search engines on the Internet offer an option to translate the hits that come back from a search query into different languages. The user initiates the translation through a menu selection. The translation is performed automatically by machine.

Japanese Pat. No. 9 114852 is a method for a search unit which takes a search string in a second foreign language and translates it into a first foreign language. The translated search string is used to search the original document which is in the first foreign language.

Japanese Pat. No. 9 44502 is a method wherein a document in a first foreign language is translated into a second foreign language. The two documents are then displayed separately or together through a user interface.

European Pat. No. 0376741B1 issued to Francisco on 18 Oct. 1995 is a method for displaying error messages on a document collating and envelope stuffing machine. Said error messages exist simultaneously in a plurality of languages and are displayed in the language specified by the user. This approach has storage and maintenance problems because each error message must be duplicated in its entirety for each language.

European Pat. Appl. No. EP0774722A2 of Microsoft Corporation published on 21 May 1997 is a method for an information retrieval system that separates the design and content components of a document page. Pages are created with controls that define areas for content to be inserted into said pages.

It would be advantageous to provide a translation management system that gives the user local control of the multilingual translation of electronic content. It would further be advantageous to provide a translation management system that allows the user to easily manage schedule and track translation resources and the content that are sent to the translation resources thereby enhancing the maintainability of the system as a whole.

The invention provides a translation management system. The invention utilizes an intuitive user interface for managing document translation for multilingual Internet Web sites documents data streams and non text files enabling the user to incrementally update the language content of a Web site or document and enhancing the maintainability and storage of multilingual electronic content.

A preferred embodiment of the invention automatically detects when a document data stream or non text file in the master language has been updated and notifies the user which corresponding documents data streams or non text files in the other languages require translation. The documents data streams or non text files requiring translation are staged and dynamically routed and sequenced to individual translation resources where the actual translation is performed.

Management status reporting scheduling and accounting information is sent to the user as the translation process ensues. The user is notified of the completion of translation and the invention coordinates the delivery of the translated documents data streams or non text files back to the user s site for installation and optional review.

The invention makes a variety of translation resources instantly available to the user. These translation resources include both automated translation tools as well as human translators. The translation resources are connected to the invention using a flexible architecture that can be deployed on intranets as well as the Internet.

Other aspects and advantages of the invention will become apparent from the following detailed description in combination with the accompanying drawings illustrating by way of example the principles of the invention.

The invention is embodied in a translation management system for computer applications. A system according to the invention provides an intuitive user interface for managing document content translation for multilingual Internet Web sites documents data streams and non text files enabling the user to incrementally update the language content of a Web site or document and automatically initiate the translation of the content into the corresponding target languages keeping the multilingual content synchronized and enhancing its maintainability and storage. Many existing application programs use approaches that make it difficult for the user to manage the translation and synchronization of multilingual content.

A preferred embodiment of the invention provides a comprehensive suite of three modules that allow a user to build operate and maintain a multilingual Web site easily and efficiently. The invention enhances an existing Web site by adding advanced multilingual content management and process control capabilities to the customer s Web server. It also uses standard and open interfaces thus enabling the invention to work with all Web servers on supported platforms.

Each module is easy to set up and does not require special modifications to the Web site. The invention provides an easy migration path from early stage customers who are only interested in measuring overseas visitor traffic to more sophisticated customers who need to manage the rapid translation of changing content on large distributed multilingual Web sites.

Referring to the invention provides three components. The Visitor module the Developer module and the Workflow Manager module . Each module accesses one or more language and country databases and file systems . The Visitor Developer and Workflow Manager modules can operate in the same environment or in a standalone mode.

The Visitor module greatly enhances the multilingual Web site visitor s experience by providing an automated and seamless way to serve content in the correct language. Web site publishers can serve all their multilingual content through a single point of entry using the Visitor module. Web site visitors will immediately understand the information they see when they enter a site because it will be instantly presented in their language and for their country.

With respect to the Visitor module works in tandem with a customer s existing Web server . It automatically determines the language and country of a Web site visitor and directs the Web server to deliver the appropriate localized content contained in one or more country language databases and or file based content in a file system to the visitor s browser . Recently accessed localized content is placed into a Cache . The content is placed in the Cache so that if a similar request comes in for a document in that language and for that country then the cached version will be pushed out to the browser . This saves time and processor overhead for accessing the database and file system to rebuild the requested content. In addition Visitor informs the browser of the proper font and content encoding needed to display the selected language and enables the browser to download the font using for example Bitstream s TrueDoc technology if required.

The Visitor module intercepts input text that is submitted using an HTML form e.g. a customer feedback form and writes it into a form database in a manner so that it is easily translated later via the Workflow Manager. Most Web sites have forms that allow site visitors to submit comments or request more information from the site host. This feedback might not be in English and would otherwise be incomprehensible to the recipient in a multilingual environment.

The form database includes sufficient information to identify the country language and encoding of the text to properly interpret it for subsequent translation. Furthermore the invention includes a novel database viewer which allows the translated content to be viewed in the context of the form in which it was originally entered.

Referring to the Visitor module determines the Web site visitor s language and country from one or more of the following criteria 

The Visitor module supports content in all languages and encodings including Unicode. Manual language selection is easily implemented through the use of a special command set described later in this document thus eliminating the need for complex CGI scripts or interlinked pages. The required content for the Web site visitor s language and country is checked to see if has been previously requested and resident in the cache . If the content is in the cache then it is delivered from the cache .

If the required content is not in the cache then the Web server is notified of the appropriate localized content required . The appropriate content is then placed into the cache for future reference . The Web site visitor s country and language preferences are recorded in the server log . The enhanced Web server log gives the site manager a detailed breakdown of country and language for visitors to the Web site. Finally the browser is notified of the proper display font and allowed to download the font .

Input text that is submitted using an HTML form is intercepted . The text is converted to an internal format and is placed in the forms database for later translation.

The Developer module enables the Web site developer to build a single master site which is subsequently displayed in any number of languages compared with conventional methods whereby the site is re engineered for each language.

Referring to the Developer module contains all of the features of the Visitor module which records the Web site visitor s country and language preferences in the server log .

A toolkit is provided which allows a master site to be built that is language and country independent. The actual language content is placed in a language and country database and or file system where it is easily managed and maintained. When a visitor enters the site the requested document is automatically served in the visitor s language and for the visitor s country by filling in a document template from the master site with the correct language and country content from one or more databases.

This structure makes the site more compact reduces site resource requirements and lowers the cost of operating the site.

The cost of making a design change is also reduced as only the master site needs to be updated. This is in contrast to the more time consuming and expensive approach of propagating a single change throughout all language versions of the site which is unnecessary with the invention.

Keeping the translated content in a database also makes it extremely easy and cost effective to add additional languages to the site. Adding a language simply involves translating the appropriate content and creating new entries in the database . The Developer module makes it unnecessary to replicate the entire site for each new language and country as would typically be the case.

The toolkit offers the multilingual Web designer a great deal of flexibility. It allows a site to be built which combines content common to all languages with content that is specific to a particular language and country. For example company wide information which needs to be served in all languages is easily combined with regional specific information that may only be required in a single language.

The invention provides special tags that are used to insert language or country specific content into an HTML document. The tags are Multi country server side includes MCSSI and Multi language server side includes MLSSI . MCSSI allows locale specific elements of an HTML document to be dynamically included as a function of the current region or country while MLSSI allows localized elements of an HTML document to be included as a function of the current language.

The Developer module also supports the incremental construction of a multilingual Web site through a feature that makes it unnecessary to fully populate the site s language matrix completely with documents. If a requested document does not exist i.e. it has not been translated into the requested language the invention automatically retrieves the document in the next most appropriate language for the visitor or the default language of the document as specified by the Web site manager. Documents can exist on separate servers and or databases.

The invention walks down a priority list of languages for a designated country. If a document in the language that is first on the priority list is not present on the server it then looks for the next most appropriate language. The list is sorted according to the most prevalent language or dialect for a particular country. For example the languages entries for Egypt are arabic french english berber. A visitor from Egypt will be presented with a requested document in Arabic if it is available. If it is not the system will look for one in French and so on.

When a visitor is presented with content in an alternate language an informational text message can be included telling the visitor that the preferred language was not available. The informational text is supplied in the most recently valid language for the visitor s country and language and is embedded within Javascript code. The Javascript code is embedded within the HTML stream that is sent back to the server. The HTML body tag has an optional attribute where Javascript code can be inserted after the tag. The informational text contained within the Javascript code is in english and enclosed within the appropriate system tags described below enabling it to be replaced with its translation in the most recently valid language of the visitor. The informational text has been pretranslated into all of the languages in the system database for the customer. This allows easy access to the appropriate translation for the informational text based on the most recently valid language for the visitor s country and language.

This allows a multilingual Web site to be built incrementally such that only a portion of the documents on the site need be translated and documents not available in a requested language will be served in the next most appropriate language for a Web site visitor.

This also gives the customer the option of translating only a subset of the total content on the site. The Developer module controls all aspects of content navigation and delivery for the entire site so that a visitor will always be served in the most appropriate language based on what language content is actually available on the server. The visitor will never see an error message i.e. a 404 document not found because the requested content is not available in the visitor s language.

Regions are mapped and organized according to the Web site s needs. For example a mutli user server can have a separate region definition for each user s site. The regions file organizes the regions countries and languages that the user is concerned with and is configured by the user. The user sets up a mapping for example one user can have information specific to Italy and another user can have information that is just concerned with the European region and is not concerned with Italy. This approach allows a hierarchical region based lookup scheme. Content is hierarchically stored as country and language independent elements such that a one to many and many to one mapping exists between country and language. The advantage to this approach is that there is no content duplication the user has only as many files in the system as he has unique content.

With respect to the toolkit also features a novel mechanism to create localized content for specific geographic regions or countries by using a template based approach to dynamically create documents tailored for a specific language or country. This feature makes it easy to create a true global site localized for each area of the world with the smallest achievable site footprint on the Web server .

A template contains placeholders for country and language specific information that has been removed from a document. This information is dynamically inserted from a TermDB an external glossary another template or document located in a database or file system or provided automatically by the Developer module when the composite document is presented to the browser .

The basic approach to creating a template has two steps. First remove as much country and language specific information as possible from a document. Then replace this information with appropriate tags and commands specific to the invention and described later in this document.

The advantage to using templates is that a single document can easily support many languages and countries. For example a single form or CGI generated document can be constructed so that it will be automatically localized for different languages and locales. This significantly reduces the number of documents that have to be maintained on the site and makes it very easy to add new languages. It also allows a single update to a document to be immediately propagated to all languages and countries.

This technique allows country or regional content to be conveniently separated from the structure of the document thereby making it easy to change a design often by updating a single file. This in turn eliminates the ripple effect often seen when a single change must propagate through all of the localized documents on the site. This allows the Web Server to control the locale independent templates language specific elements country specific elements and static HTML content .

Visitors to a multilingual Web site may wish to enter information and feedback into a fill out form in their local language to send back to the Web site manager. A mechanism is provided and described above which facilitates the acquisition and translation of this information. The Developer module captures and tags all such information in a sufficient manner so it can be subsequently translated and analyzed by the customer.

This approach allows a site to be built with minimal effort and cost and allows the site to grow over time to meet the exact needs of the customer.

Referring to the Workflow Manager module enables the Web site manager to orchestrate the creation of foreign language versions of the site and to automatically keep them synchronized and up to date cost effectively and with minimal effort. The Workflow Manager module provides a Manager s Console access to a Workflow Pipeline and customizable Translation Resources . Translation queues hold the incoming translated documents and outgoing documents to be translated. Documents data streams and non text content are stored in one or more language and country databases and or file systems . Data streams and non text content are considered documents in the following text.

The Workflow Manager module is the core component of the invention. The module allows the Web site manager with no prior linguistic experience to effortlessly manage the traditionally complex process of translating and updating a multilingual Web site.

The Workflow Manager module provides a natural migration path beyond the Visitor and Developer modules. The Visitor and Developer modules provide a solution to efficiently serve and organize content on a multilingual Web site. The Workflow Manager completes the product family by enabling the language content on the site to be kept up to date efficiently and cost effectively.

The Web s very nature is dynamic. A monolingual Web site must be updated frequently to remain current. A multilingual Web site has an even more demanding problem of requiring all languages to be updated and synchronized simultaneously. Using traditional techniques the cost and time required to perform this update and synchronization exceed the benefit and lifetime of the newly updated information to be served effectively rendering the Web site useless. The Workflow Manager provides a solution to this paradox by reducing the cost and time requirement for language update and synchronization dramatically thereby ensuring that information on the Web site is always current regardless of language.

The Manager s Console is the user interface for the Workflow Manager and is the primary point of interaction for the Web site manager.

Referring to the Manager s Console detects when a document in the master language has been updated . It then notifies the Web site manager which corresponding documents in the other languages require translation . The Manager s Console provides one touch translation whereby at the click of a button documents from any source requiring translation are converted to the internal format staged down the Workflow Pipeline then dynamically routed and sequenced to the individual Translation Resources where the actual translation is performed. Documents may be Web based and non Web based and may also contain non text elements. The documents may contain or refer to additional dependent components such as graphics audio video and other multi media elements.

When the Web site manager initiates the translation process the newly updated master language document and its constituent elements together with associated control information will be converted by the Console to an internal format one which is more suitable for information transport over the Workflow Pipeline .

The Manager s Console automatically controls the sequencing and selection of Translation Resources during workflow processing according to subject matter of the document to be processed target language of the translation quality level whether draft only or high quality is required and other variables. The Web site manager can also individually specify the use of a specific set of Translation Resources.

The Manager s Console provides management status and reporting as the translation process ensues . It then automatically notifies the Web site manager of the document translation completion and coordinates the delivery of the translated documents back to the Web site for installation and optional review . The Web site manager can directly install the translated documents back onto the active area of the Web site at the click of a button or can make them available for internal review within the organization.

Status information is presented through a highly usable interface that facilitates interaction and improves the productivity of the Web site manager. The Console interface is designed to allow translation and update of the multilingual Web site to be performed cost effectively and with minimal effort by a non specialist.

New languages are easily added to the site as well. The Web site manager simply selects the new language from a pulldown list and the Manager s Console automatically initiates the translation of documents into the desired language under the control of the Web site manager . The documents are converted to the internal format used by the invention and staged down the Workflow Pipeline .

The Manager s Console also has a built in access and version control system which allows it to be easily integrated with a third party authoring or document management system on the Web site.

With respect to a task view of the Manager s Console is shown. The Update Status module updates the Web site manager of the document translation status. The Complete Document module retrieves the translated document and its constituent or dependent components from the Translation queues and updates the associated document status information. The document delivery to the Web site manager is then coordinated by the Coordinate Document Delivery module .

Documents that need to be translated are extracted from the language and country databases and file systems and are sent to Translation Queues . The Project Analyzer module receives project components in the form of documents and other electronic content from the Translation Queues and analyzes the project in sufficient detail to determine project cost and resource requirements.

The Project Analyzer module waits until all elements of a project have been received. It then sends the Scheduler module a description of the project and instructs the Scheduler module to begin the project. Typically the Project Analyzer module works with the Accounting Manager module to generate a project cost estimate prior to beginning the project.

Once the Scheduler module receives the project information from the Project Analyzer module it creates Work Packets Job Tickets and a Project Schedule. A single project consists of a set of Work Packets and associated Job Tickets. Each Job Ticket contains a reference to a Translation Resource. A set of Job Tickets is associated with a single Work Packet and describes the activities to be performed by that Work Packet. The Scheduler module generates a Schedule that is sent to the Manager s Console for review and validation. The documents and their constituent or dependent components are then scheduled and sent down to the Workflow Pipeline.

The Scheduler module updates the Project Schedule and notifies the Accounting Manager module during the course of the project. This permits the Project Schedule to be adjusted when there are changes in the availability of Translation Resources or when manual changes are made to the project by an operator via the Manager s Console.

The Accounting Manager module updates customer and Translation Resource accounting in the Accounting Database as jobs complete. The Accounting Manager module generates project cost estimates based on input from the Project Analyzer module handles customer billing and is responsible for generating purchase orders for Translation Resources when needed.

Completed documents and their constituent or dependent components that have been checked by the Web site manager are then installed in one or more language and country databases and or file systems by the Monitor Database Documents module .

The Workflow Pipeline is a transport layer that delivers documents and their constituent or dependent components requiring translation to the Translation Resources where the actual work is performed. The Workflow Pipeline is heavily instrumented so that status and tracking of ongoing work is instantly conveyed to the Web site manager on the Manager s Console.

The Workflow Pipeline uses a highly configurable architecture allowing a variety of Translation Resources to be instantly available to the Web site manager. These Translation Resources include both automated translation tools as well as human translators.

Translation Resources are connected to the Pipeline using an open Application Programming Interface API known as an Adaptor. Adaptors allow a variety of Translation Resources to be connected to the Pipeline making it easy to tailor the Workflow Manager to meet a customer s requirements. The flexible Pipeline architecture can be deployed on intranets as well as the Internet.

Referring to Generators are provided that convert the internal format document that is used within the Pipeline to the appropriate format required by the Translation Resource. The Adaptors invoke the specific generator for the appropriate Translation Resource . Each Adaptor accepts the internal format document sends the document to the appropriate Generator which converts the format to one that is acceptable to the Translation Resource attached to the Adaptor . The Generator sends the newly formatted document to the Adaptor which in turn sends it to the Translation Resource . When the document has been translated by the Translation Resource the Adaptor accepts the document and its associated information and invokes a Parser which converts the document back into the internal format. The Parser distributes the packet back up the Pipeline.

Parsers are also invoked whenever a document is extracted from the Translation queues and sent down the Pipeline. The Parser converts the document into the internal format. Generators are in a similar manner invoked whenever a translated document is posted back onto the Translation queues after completion of translation. The Generator converts the internal format document back to the document s original format e.g. HTML . The document is then sent to the final destination.

With respect to the Adaptor converts work packets to the appropriate Translation Resource format . The packets are then routed to the appropriate Translation Resource .

The Adaptor also receives packets from Translation resources . The packet is converted back to the work packet format and the status and control information in the work packet is updated . The Manager s Console is then notified of the work packet s availability in the translation queue.

This degree of flexibility allows new translation technologies and translation service providers to be quickly integrated into the workflow process. Additional resources are easily allocated to accommodate sites which require frequent update and synchronization.

Referring to a task view of the Adaptor is shown. The Convert to Translation Resource module converts work packets to the appropriate Translation Resource format that is understood by the resource. The packets are then routed to the Translation Resource by the Route Packet module .

Packets are received by the Receive Packet module . The Convert Update Packet module performs the packet conversion back to the work packet format and updates the packet s status and control information. It then notifies the Manager s Console that the work packet is available in the translation queue.

The Workflow Pipeline together with the Translation Resources allow the translation process to proceed rapidly and efficiently.

Translation Resources are centralized or distributed functional blocks which are connected to the Workflow Pipeline where the actual work including translation is performed. A typical workflow process will use one or more Translation Resources in a specified sequence to complete the required work.

A Translation Resource performs translation or other linguistic functions on a set of input documents and their constituent or dependent components and produces a set of output documents that have been transformed linguistically.

Translation memory systems provide a database of source target translation pairs for a particular document. When an updated version of a document needs to be translated the translation memory can be used to pre translate the document with translations from the previous version of the document.

Human translators are linked to the Workflow Pipeline through a special Adaptor that connects to the Internet or a customer s intranet. This allows any translator anywhere in the world to join a virtual translation team and provide translation services to multilingual Web sites or any other translation application serviced by the invention.

Terminology management systems provide functions that are necessary to support the entire translation process such as automated generation and retrieval of client specific glossaries and lexicons. Both human based as well as technology based Translation Resources require access to appropriate glossaries and lexicons to ensure that linguistic transformations are performed in the correct terminological domain.

Technology based Translation Resources are easily upgraded as their technology improves. For example older machine translation or translation memory systems are replaced with newer systems simply by unplugging the old systems and plugging in the new ones through the Adaptors on the Workflow Pipeline.

The Manager s Console provides the Web site manager with fully automated management of the entire translation process. The following is a description of how the Web site manager interacts with the Manager s Console in the process of keeping a site up to date.

With respect to when the site is current and all language content is up to date the Manager s Console reports to the Web site manager that no action is required.

If a document in the master language is subsequently updated perhaps out of date product information on the Web site is being updated the Console will immediately alert the Web site manager that the corresponding foreign language versions of the document are out of date and need to be re translated.

From this point the Web site manager simply clicks on a button using the Console s one touch translation feature to automatically initiate the re translation and update of each document. No additional action is required from the Web site manager until the documents have been translated and are ready to be mounted back onto the site.

When the Web site manager initiates the translation process the newly updated master language document together with associated control information will be converted by the Console to an internal format one which is more suitable for information transport over the Workflow Pipeline . The converted document together with relevant control and status information is known as a work packet. The Workflow Pipeline is responsible for sending and receiving work packets to an appropriate set of Translation Resources where they are processed.

The sequence in which the Translation Resources are engaged by the Pipeline is pre determined according to 

When a work packet is dispatched to a Translation Resource for processing the packet first flows from the translation queues through the Pipeline Adaptor for that Resource where it is converted from the Workflow s internal format into one that can be processed by that Resource.

Once the Translation Resource has finished its processing the packet which contains the work completed by the Translation Resource flows back through the Adaptor where it is re converted back into the Pipeline s internal format. The Adaptor is also responsible for analyzing the completion status of the Translation Resource and updating the packet s control and status information accordingly.

Since the Pipeline is heavily instrumented the Console gives the Web Site manager continuous updates on the progress of the translation. The Console also uses status information to automatically provide dynamic dispatch and control decisions to achieve the fastest and most cost effective turnaround time.

After completion of the workflow sequence the translated documents are routed back to the Console where the Web site manager is notified of their completion. From there the Web site manager can directly install the translated documents back onto the active area of the Web site file system local or remote or database local or remote at the click of a button or can make them available for internal review within the organization. For example when the translated documents are installed onto the active area of the Web site they are referenced by the appropriate language HTML commands inserted into the Web site pages and the translated content is removed from the translated documents and stored back in the database.

New languages are easily added to the Web site. The Web site manager simply needs to select the new language from a pulldown list along with the desired documents on the Manager s Console and the necessary steps will be automatically invoked to initiate the translation.

One skilled in the art will readily appreciate that although the invention has been described in the context of Web sites the same concept applies to other applications. For example in a fax application documents are scanned and sent through the invention for translation into selected languages. The translated documents are then automatically faxed to selected locations. Another example would be a universal translator where spoken words are converted into a data stream and sent through the invention for translation into designated languages. The translated data stream is converted back into audible speech and sent to the designated audiences.

The invention is scalable to provide multilingual presentation and management functions across multiple servers in a distributed environment. For example some sites might have English content on one server Japanese on another and so on. Each server will have installed on its respective site an instance of the invention communicating with other instances of the invention throughout the system. One server is designated the master and the others are slaves for the purpose of managing content. The servers communicate over a dedicated interface allowing content to be managed in a distributed fashion. This configuration also supports mirrored sites across multiple servers.

One skilled in the art will readily appreciate that although a single user system is specifically mentioned the same concept applies to multi user systems for example a multi user configuration would be appropriate for an Internet Service Provider ISP that serves multiple customers with and without multilingual sites from a single instance of the invention.

The following is an excerpt of a user manual describing the Visitor and Developer modules for a preferred embodiment of the invention called WebPlexer 

The following sections are ordered beginning with basic functions and gradually progressing to those that are more advanced. Similar functions have been grouped together logically for easy reading.

WebPlexer has 3 network ports. These ports are used to communicate with the client the Web server and the console. The ports can be assigned to any available port number on your system and are specified in WebPlexer s WP Config file.

Port numbers are assigned starting at 1. Lower numbers are reserved for dedicated processes like ftp http and telnet . The lower numbered ports are also privileged in that they require root level authority to use.

WebPlexer s InternetPort and ServerPort are configured to support two modes of operation test mode and production mode .

In test mode a separate access path is created for clients to send requests to WebPlexer. Normal http requests to port and the existing Web server are not affected. This permits off line testing of WebPlexer functionality until the site has been validated.

You can make WebPlexer available to ordinary port users even in test mode by including a special link on a page to send a request to WebPlexer s port.

In production mode WebPlexer is configured to process all http requests before they reach the Web server. This would normally be done once off line testing was completed and the site was ready to go into production.

This setting can also be overridden by a command line flag. Please see Section 3.11 Runtime Options for more information.

This setting can also be overridden by a command line flag. Please see Section 3.11 Runtime Options for more information.

This setting can also be overridden by a command line flag. Please see Section 3.11 Runtime Options for more information.

The filenames of these logs are defined in the WP Config file. Additional information on how to define the log files can be found in Chapter 4 Contents of WebPlexer Files. 

NOTE A fourth log the Usage Log is generated by the updtusage tool that analyzes the Information Log. This tool will be included in a future release.

The function of each log is described below. A detailed specification can be found in Section 4.4 Log Specifications. 

The AccessLog records information about each request received by WebPlexer such as date time and request type. WebPlexer command requests WPCommands are also logged.

NOTE When WebPlexer is configured for production mode see Section 3.1.1.2 Production Mode WebPlexer s Access Log should be used in place of the Web server s access log for analysis and auditing purposes the Web server s access log will show all requests originating from WebPlexer .

The InformationLog contains detailed information about WebPlexer s language selection processing for each request.

The ErrorLog shows any errors that occurred during WebPlexer operation or during the processing of a request.

The UsageLog contains a summary of country and language statistics. It is generated from the InformationLog using the usage log analysis tool. The UsageLog can be further processed using the visits log analysis tool. Please see section x.xx for a description of WebPlexer s log analysis tools.

WebPlexer s Language Selection feature allows the most appropriate language of a requested document to be served to a Web browser.

These three language selection modes all work together seamlessly. They do not require the addition of any special CGI scripts or links to be added to your Web site.

The language selection algorithm requires that each language be assigned a unique directory in the document tree. All documents in that language are placed in the corresponding directory. The entire document tree then becomes a collection of parallel language directories.

For example if user joe has english french and spanish documents on your site the directory structure might look like this 

WebPlexer s language selection algorithm works by inserting the correct language directory in the URL before sending the request on to the Web server.

A group of language directories and the documents they contain can be likened to a matrix. This matrix has one row for each language and one column for each document in the collection. When expressed in this form the collection is known as a document matrix.

WebPlexer s exclusive document management feature known as SPAMM Sparse Matrix Manager does not require each document to be translated in every language and therefore does not require every cell of the document matrix to be filled in.

In addition SPAMM also permits templates to be placed only in the default language directory see Section 3.3.2.3 Specifying the Local Default Languages and eliminates the need for them to be instantiated in every directory.

SPAMM offers an incremental approach to building a multilingual Web site. Please see Section 3.9.2 SPAMM Sparse Matrix Manager for more information on this feature.

WebPlexer s Language Selection feature is enabled by editing a few lines in the WP Map file located in the main WebPlexer directory. Once the file has been set up any of the language selection modes browser specified automatic manual are available.

Often a single server will serve multiple sites. You can easily have WebPlexer support multiple sites by creating a separate URL group for each site.

The next sections explain each component of the URL group declaration. Please refer to the example WP Map file supplied with this release while reading the following sections.

NOTE In the current implementation when a directory is specified it is also necessary to specify the corresponding top level file as well usually index.html .

Note that this file joe index.html does not actually exist in the document hierarchy but should match the URL the user will type when entering the site.

The language to directory map and charset document encoding are specified by adding lines of the form 

is the name of the language. Please see Appendix B. List of Available Languages for a list of which languages are available for this release.

The local default languages tell WebPlexer which language to use in case the requested language is not available on the server.

There are two local default languages that need to be specified. The first is called others and the second is simply called default .

For example if English French and Spanish documents exist on the server but the requested language is Russian WebPlexer will use the language defined as others .

The default language is chosen when WebPlexer cannot determine the language of a request and none has been specified by the browser. This can happen when the country of origin cannot be determined because the hostname is unavailable for example when the requester is behind a firewall.

In browser specified language selection the browser sends its language preference along with the http request. The language is set through a preference or option setting in the browser. The preference is sent to WebPlexer in the Accept Language header within the request message.

The Accept Language header is described in the http specification. The specification allows the browser to send more than one language in the header. The group of languages is ordered with the most desirable language first.

WebPlexer uses the Accept Language header to select the correct language. The header is only used when the request is to a URL that matches the top level URL given in the WP Map file see Section 4.2.1 Specifying the Top Level URL .

For example if the top level URL were joe and the browser preference were set to Spanish a request to 

If the browser has specified more than one language WebPlexer goes through the languages in order and stop when it finds the first one that is present on the server if none of the languages are found WebPlexer uses the others language specified in the WP Map file see Section 4.2.2.1 others 

Once the language has been determined WebPlexer redirects the browser to the directory for that language. All accesses to relative links within the requested document stay within that directory.

Changing the browser s language preference does not have any effect until the top level URL is again requested and the browser re enters the site. The recommended way to change language within a language directory is by manual selection see Section 3.3.5 Manual Language Selection .

In automatic language selection WebPlexer determines the language by first determining the country from the requester s domain then looking up the language for that country in a database.

NOTE If the browser has specified a language preference it overrides any automatic language selection.

This list of languages is processed in the same way as preferred languages are handled when received from a browser see Section 3.3.3 Browser Specified Language Selection . This means that the languages are examined until the first one present on the server is found.

For example the languages of Switzerland are german french italian romansch and will be searched in that order. The rules for selecting the local default languages are the same as for browser specified languages if the language cannot be found.

Manual language selection is effective at any time. Manual language selection overrides any automatic or browser specified language.

Manual language selection is performed by issuing a WPCommand whose type is language . WPCommands are more fully described in Section

NOTE language plus country means that the language directory is appended with the currently selected country e.g. english United States 

Note that even with manual language selection the languages and directories in the WP Map file still need to be set up as in automatic language selection.

WPCommands are normally issued through hypertext links embedded in an HTML document. This statement illustrates a simple example 

If the user is currently looking at an English document clicking on the word French will cause the browser to send WebPlexer a request for the URL

The manual language selection feature is performed completely by WebPlexer without the need for CGI scripts or complex interlinking of HTML documents. It merely requires the addition of a link in the HTML to send the WPCommand to WebPlexer for each desired language.

The WPCommand hypertext link can be used like any other HTML link that is it can be placed within a table connected to a graphic or icon or built into an imagemap.

The method described above works well when the number of languages is small. However as the number of languages on the server increases there may not be enough space to have the links for all the languages appear on each page.

In this case a generic mechanism exists for handling WPCommands that will move all of the language selection links off to a separate page. Once the links are moved a hypertext link that points to this special language selection page is placed on each page of your site.

Because of the need to return to the originating page when the language is changed WebPlexer requires that a special WPCommand be used to invoke the link to the change language page.

This WPCommand is of type link and takes the name of the page to link to as an argument. Its external behavior is the same as if a direct HTML link were used except it notifies WebPlexer that a change language or change country WPCommand is about to be issued.

WebPlexer provides a method of optionally forcing the selection of specific language s for certain hostnames or ip addresses.

This feature overrides automatic language selection when the top level URL specified in the WP Map file is requested. A browser specified language preference will still be used if specified.

There are two files used to specify automatic language selection overrides HostNameMap and IPAddrMap both of which are in WebPlexer s language subdirectory.

The global default language is used as the default for the console and for some WebPlexer initialization.

Content tagging allows WebPlexer to inform the browser of the language and charset used to encode a document when the document is accessed. Some browsers like Netscape Navigator use this information to automatically switch to the correct font and encoding for a particular language.

Content tagging is always active whenever a document is fetched from a language directory that is specified in the WP Map file.

When a document is content tagged the http Content Language and Content Type response headers are returned with the document to indicate the language and charset in use.

These fields are automatically updated by WebPlexer even when the language is changed by manual selection.

With automatic country selection WebPlexer determines the country from the requester s domain. If the domain cannot be determined usually because the requester is behind a firewall the country is set to the global default country see Section 3.4.5 Setting the Global Default Country .

Automatic country selection is only active when the browser request is to the top level URL specified in the WP Map file. See Section 3.3.2.1 Specifying the Top Level URL for a detailed description of how to set the top level URL. Once the country has been determined its value is saved by appending it to the language directory in the mapped URL.

By embedding the country name in the URL WebPlexer can retain the country setting for the lifetime of this session.

Manual country selection is performed by issuing a WPCommand of type country . WPCommands are more fully described in Section 3.6.3.3 WPCommands. They result in the browser sending a request to WebPlexer of the form 

For example if the current country is France and the current language is French and the current document being viewed is info.html to request that the country be changed to German this request should be sent to WebPlexer 

Regions are defined in the WP Regions file. Regions allow groups of countries to be combined into geographical areas that are meaningful for the type of content that is on the site.

For example if a company had one sales office in Europe and another in Asia and had developed Web site content that was specific to these markets it might want to create two regions like this 

Regions can be either user defined or pre defined default . User defined regions are specified in the WP Regions file see Section 4.9 WP Regions .

Pre defined default regions are established by WebPlexer. Please see Appendix D. List of WebPlexer Default Regions for more information.

Regions are used by the multi country server side include feature see Multi Country Server Side Includes MCSSI . They allow specific content to be presented to users from countries in those regions when they enter the Web site.

The global default country is used as the default for the console and for some additional WebPlexer functions.

WebPlexer has the unique ability to independently maintain both the country and the language associated with each request. This provides a great deal of flexibility in selectively targeting content to specific regions or countries of the world and at the same time making that content available in multiple languages.

It is important to understand how WebPlexer s country management and language management are different and how they are similar.

In the following description the term session refers to a logical grouping of requests between browser and WebPlexer. A session begins with the browser making a request for the top level URL. It ends with the final response being sent from WebPlexer to the browser. A session can have any number of request response pairs between these two endpoints.

A session has a state associated with it. Included in this state are the country and language of the requester.

Once the country and language state have been determined from the initial request they remain unchanged until the browser initiates an action like manually changing the country or language.

Unfortunately the http protocol used for data transport on the Web is a stateless protocol. This means that the protocol does not allow state to be maintained from one request to another.

WebPlexer uses a unique persistence mechanism for retaining session state across multiple requests. This mechanism allows country and language information to be saved throughout the lifetime of a session.

WebPlexer uses a simple 4 step algorithm for managing country and language when processing a request 

Once the country and language for a request have been established they are available as state variables within the HTML and can be used for 

WebPlexer will first determine the country of the requester if it is not known on an initial request or when it is manually selected through a WebPlexer change country command see Section 3.4.2 Manual Country Selection .

WebPlexer uses the country from the previous step to determine the slanguage of the requester. A list of languages for the selected country is obtained from a database and the first one that matches a language present on the server is selected.

For example if the requestor s country were Switzerland the requestor s language could be set to either german french italian or romansch depending on which one was found first on the server.

WebPlexer uses the country to dynamically select content specific to that country. This allows the content to change based on the geographic location of the requester. The actual selection mechanism is controlled by the multi country server side include feature. This feature is more fully described in Multi Country Server Side Includes MCSSI . Additional information can be found in Section 3.6.1 Template Model which describes WebPlexer s template model.

The Multilingual ToolKit is a set of HTML extensions and templates that simplifies the design and construction of multi language and multi country Web pages.

WebPlexer s Multilingual ToolKit uses a template based approach to dynamically create documents tailored for a specific language or country.

A template contains placeholders for country and language specific information that has been removed from a document. This information is dynamically inserted from a TermDB another template or document or provided automatically by WebPlexer when the composite document is presented to the browser.

The basic approach to creating a template has two steps. First remove as much country and language specific information as possible from a document. Then replace this information with appropriate WebPlexer tags and commands.

The advantage to using templates is that a single document can easily support many languages and countries.

For example a single form or CGI generated document can be constructed so that it will be automatically localized for different languages and locales.

This significantly reduces the number of documents that have to be maintained on the site and makes it very easy to add new languages. It also allows a single update to a document to be immediately propagated to all languages and countries.

This technique also allows country or regional content to be conveniently separated from the structure of the document making it easy to change a design often by updating a single file. This eliminates the ripple effect often seen when a single change must propagate through all of the localized documents on the site.

One document may contain all three template types. We call such a document a composite document since it is made up of multiple elements.

Most documents will have a mixture of these three basic types. In the sample included with this release the file info.html is a combination of static and tag based templates whereas the template of contact.html is completely tag based.

Please look through the sample files in the htdocs directory of this release for examples showing the use of templates.

File based templates require the server side include feature. This feature is not available in the current release.

Tag based templates are the most generic and allow a single document to be used across all languages and countries.

In general the smaller the amount of static content in a template the more generic the template is and the fewer the number of times it needs to be instantiated.

File based templates allow external files containing localized content such as country regional or language specific information to be inserted dynamically into a document. File based templates are provided using the server side include feature described in Section 3.6.3.5 Server Side Includes. 

Tag based templates allow replacement of marked up text with translations from an external TermDB according to the selected country or language. Tag based templates are provided using the WebPlexer HTML extensions described in Section 3.6.3.1 WPReplace. 

A TermDB is an HTML representation of a multilingual glossary. The glossary is built in the form of an HTML table. Rows in the table correspond to entries in the glossary be they words phrases or arbitrary strings. Columns in the table correspond to individual languages in the glossary such as English French or German.

One language in the TermDB is designated the primary language and is assigned to column 1 of the table. This primary language is used as the language of the key when looking up entries in the TermDB.

The TermDB is used together with the WPReplaceBegin and WPReplaceEnd tags. See Section 3.6.3.1 WPReplace . The tags enclose text that will be replaced by a TermDB entry. The text must be in the primary language.

When WebPlexer accesses the TermDB it first finds the word hello by looking in row 1 the primary language row of the TermDB and finding the column that contains the desired term. Then it retrieves the term from the row of the table corresponding to the current language row 2 in the case of French in the column it identified as containing the desired term.

This release of WebPlexer comes with a standard TermDB that includes the names of all languages and countries translated into 25 languages.

WebPlexer supports the use of multiple TermDBs. Each top level URL declared in the WP Map file can be associated with a different TermDB and multiple TermDBs can be defined for a given URL. This makes it possible to maintain several small TermDBs rather than one large one.

TermDBs together with WebPlexer s WPReplace tag allow multilingual terminology to be centralized. This has several advantages 

TermDBs and the other resources of the Multilingual ToolKit can be used most effectively if you plan appropriately before you design your site. If you need assistance in building your multilingual site please contact Language Automation and one of our site support engineers will be happy to assist you.

User defined TermDBs can be created and updated using the tpbuilder utility that comes with WebPlexer.

The first form is used when creating a new TermDB. The second form is used for updating an existing TermDB.

Note that these strings are for informational and readability purposes only and are not used by WebPlexer.

In this case english is defined to be the master language of the TermDB and the list of index terms will be taken from the file laieng.txt. The corresponding translations into arabic and french will be read from the files laiarah.txt and laifre.txt respectively.

NOTE The controlFile must contain all of the languages that were specified when the TermDB was initially created.

These operations are controlled through the contents of the individual input files specified in the controlFile and are described in more detail below.

To add a new entry simply add a new TermString to the master language input file and optionally corresponding TermStrings in the target language input files. If a matching translation is not found in a target language input file an empty entry will be created and will be filled in later when the translation is available through the WebPlexer console s translation management feature. Please see section x.xx for further information on console operation.

If an empty TermDB entry is accessed during a lookup the TermDB will return the value of the original master language string i.e. the index .

NOTE Prior to updating a TermDB it is recommended that TermStrings that will not change be removed from the input files i.e. input files should only specify actions to be performed during the update .

To replace an entry simply replace old translation s in the target language input files with new translations of the TermString. The original TermString must be specified in the master language input file.

If new translations are not available simply put a blank line in the target language input file s with a number that matches the original TermString in the master language input file. The translations will be updated later through the WebPlexer console s translation management feature.

To delete an entry simply put a minus sign in front of the line in the master language input file corresponding to the entry to be deleted. The master language entry for that TermString along with all translations will be removed from the TermDB.

HTML tags can be included in TermStrings to allow complete HTML constructs to be embedded between WPReplace tags. This provides a great deal of freedom in content organization.

The backslash character can also be used as a valid character in the TermString but it must be preceded by another backslash.

The Multilingual ToolKit s HTML extensions are a set of special purpose commands and comment embedded HTML tags. They enable WebPlexer to provide special country and language processing when serving a document.

The string to be replaced and the currently selected language are used as search keys within a TermDB. The TermDB is accessed and returns the translation of the string in the specified language.

Please see Section 4.2.3 outbound Enabling the Output Manager for information on how to specify TermDBs.

NOTE this is restricted in the current release. Please see Section 1.3 Known Bugs and Limitations of This Release. 

This code will allow the list items to be sorted in the correct order according to the current language.

In the above example the WPReplace tags are processed first replacing the words English French and German with their translations. The translations will then be used as the sort keys.

WPCommands are special WebPlexer commands included in a document s HTML. They allow WebPlexer to manage country and language selection within a document.

WPCommands are coded as hypertext links in a document. When a link is clicked the WPCommand is sent to WebPlexer in the request URL.

When WebPlexer receives the WPCommand it performs some function and returns the result to the browser.

Each of these commands is described in more detail in the following sections. See also Section 3.3.5 Manual Language Selection for a discussion of how WPCommands are used within the HTML.

This command has the side effect of notifying WebPlexer that a hypertext link was executed. This information is used to save the location where the browser came from so it can return after country or language selection.

When WebPlexer receives a link notification it saves the current value of the referer URL in the http request for this session. After a change country or change language command is executed see next sections the saved referer URL is restored and the browser returns to the page from where the link was issued.

The link command is used when the change country or change language function is implemented on a separate page. This allows the browser to return to the originating page once the new country or language is selected. Please see Section 3.3.6.2 Using WPCommand link for additional information.

An example of the link command is included in the sample documents included with this release. The change country and change language functions are implemented in the files countsel.html and langsel.html respectively. These pages are reached by issuing a WPCommand link from the index and form pages.

The current language may also change depending on the session state. See Section 3.5.2 Determine Language from Country .

WebPlexer s custom variables are special placeholders that can be included in HTML code. They are automatically replaced by current country and language information when the document is served to the browser.

The next sections describe the custom variables supported in this release. Please see the sample files e.g. contact.html for examples of their use.

For example if the current country were United States and the current language were Spanish this sequence

 flag is a placeholder for the name of the gif file containing the flag of the currently selected country. The name is automatically prepended with flag . The WebPlexer release includes gif images of flags from the countries of the world.

An ordinary server side include is an HTML tag which causes an external file to be included within an HTML document. The file is included when the document is served to the browser.

WebPlexer s server side include extends this capability by making the decision of what file to include based on the current country region or language. This enables a document to be built dynamically out of country and language specific components.

MCSSI permits locale specific elements of a document to be included as a function of the current region or country.

The MCSSI feature provides the ability to dynamically insert country and regional specific content into the HTML stream.

head of mcssi directory is the top level directory of the MCSSI area on the server and is defined in the WP Config file see Section 4.1 WP Config for more information and country or region is determined dynamically according to the algorithm described in Determining the country or region directory. 

The file which is included by MCSSI can itself contain additional WebPlexer tags such as WPReplace and Custom Variables see Section 3.6.3.1 WPReplace and Section 3.6.3.4 Custom Variables . It can also contain additional MCSSI and MLSSI includes see Multi Language Server Side Includes MLSSI .

By supporting WebPlexer tags such as WPReplace within the included MCSSI file regional specific content can be further localized according to language. This feature allows considerable flexibility in serving specific content for a region or country where more than one language is spoken.

Please note that language dependent content is normally not included in MCSSI files and that template tags see Section 3.6.1.1 Template Types such as WPReplace see Section 3.6.3.1 WPReplace or MLSSI see Multi Language Server Side Includes MLSSI should be used instead.

Language dependent content means any static text that is present in the file. Including language dependent content within an MCSSI file is not recommended since an MCSSI file is included based on the setting of the current country. In other words MCSSI files should contain only country or regional specific content and be independent of language.

For example if the current country of the browser is Switzerland the user might be viewing the site in either French or German. If an MCSSI file for Switzerland is included that contains static text in French the language will be wrong if the browser is requesting German.

This problem can be easily solved by replacing the static text in the MCSSI file with template tags either by

The country or region directory is determined dynamically from a combination of the following parameters 

The specific algorithm for determining the country or region directory from the above information is as follows.

These directories are consulted in order one at a time until the requested file is found. The directories are defined below.

MLSSI allows the Web site designer to further customize an HTML document according to language more generically than what can be provided by the WPReplace tags see Section 3.6.3.1 WPReplace .

Like MCSSI MLSSI allows a file to be included in line by referencing it within an HTML document. However the path to the file is determined by the currently active language rather than by country or region.

The referenced file is pre translated and placed in each of the language directories referenced in the WP Map file see Section 4.2 WP Map for a description of the WP Map file . When the HTML document is presented to the browser the file included by MLSSI is retrieved from the directory corresponding to the currently active language and inserted in line into the HTML stream. This allows a single HTML document to be easily customized by including components that are specific to the selected language of the browser.

language directory is the directory specified in the WP Map file and language is determined according to the rules outlined in Section 3.5 Country and Language Management. 

The file which is included by MLSSI can itself contain additional WebPlexer tags and commands such as WPReplace see Section 3.6.3.1 WPReplace . It can also contain additional MLSSI and MCSSI includes.

If the MLSSI file name is not found on the server the following message will be injected into the HTML stream in place of the MLSSI directive 

The Multilingual Navigator is a collection of WebPlexer enhanced HTML code which can be used to easily provide language and country selection for any document on the Web site. It provides complete language and country selection without the need for CGI scripts or complex interlinked pages.

The Multilingual Navigator is easily customizable to meet the specific navigation needs of your site.

The Multilingual Navigator is included with this release in a file called mlnav.html . It is also included on the index.html and contact.html pages in the sample directory.

WebPlexer s input manager allows forms handling CGI scripts to be intercepted and user input extracted for later translation. It can be used to support the translation of customer feedback forms in a multilingual environment.

To use the input manager the name of the CGI script to be intercepted is specified in WebPlexer s WP Map file along with the location of a template file and an output .prt pre translated file.

There is one line at the end of the WP Map file for each CGI script to be intercepted. The format of this line is 

The template file tells the input manager which fields of the form should be extracted. When the CGI script is invoked the input data from those fields is saved and appended to the output or .prt pre translated file. This file also contains the time stamp current country and language and domain of the requester.

Please see the files contact.html and contact.tmpl included in the sample directory of this release for additional examples.

The .prt file is the output file that contains data from the extracted fields specified in the template file.

The .prt files can be queued by the console for later translation. Please see Section 3.10.10 Maintaining Input Manager Database Files for more information.

WebPlexer s document manager manages the selection of documents to serve based on the current country and language. It requires that documents be placed in parallel language directories off of the Web server s htdoc root. It also requires that the location of language directories be specified in the WP Map file.

The document manager requires that translated documents be arranged in parallel language directories off of the Web server s htdoc root. Please see Section 3.3 Language Selection for detailed information on how to arrange the document hierarchy for the document manager.

WebPlexer s exclusive document management feature known as SPAMM Sparse Matrix Manager provides an incremental approach to building a multilingual Web site.

SPAMM allows the site administrator to translate only a portion of documents on the site and into only those languages that are most relevant.

SPAMM is a feature that makes it unnecessary to fully populate the site s language matrix completely with documents.

If the set of documents on a multilingual Web site is visualized as a matrix with each row representing a language and each column representing a document SPAMM eliminates the need to populate every cell of the matrix. When a document is requested in a particular language WebPlexer will go to that cell of the matrix and try to retrieve the corresponding document.

If the document is not there i.e. it has not been translated into the requested language WebPlexer will automatically retrieve it from the default language directory specified by the default declaration in the WP Map file for this top level URL see Section 4.2 WP Map for an explanation of how to set up the default language directory .

SPAMM is completely transparent in operation. It does not require any special set up or configuration. It also works with MLSSI so that if an included file cannot be found in the current language directory it will look in the default directory instead.

Please note that even when SPAMM fetches a document from the default directory WebPlexer still maintains the correct settings of country and language. This means that if a browser clicks on a link from within a document that was fetched from the default language directory through SPAMM WebPlexer will look for the new document in the currently active language directory not in the default language directory.

The mapping of language to directory must be specified in the WP Map file so the document manager can locate documents in the correct language.

Please see Section 3.3.2.2 Specifying the Language to Directory Map and Charset for detailed information on how to specify this mapping.

Please see Section 3.3.2.2 Specifying the Language to Directory Map and Charset for detailed information on how to specify the charset used to encode a document. This information is used by the document manager.

MCSSI allows an HTML document to be easily customized with country and regional specific content using a highly modular building block approach. This reduces the number of individual files that need to be kept on the server lowering the cost and time required to maintain the site.

One application of MCSSI is to insert a targeted country specific banner at the top of an HTML page. It can also be used to easily tailor a marketing message for a specific country or region. For example a travel company could use this feature to publish different airfares to various countries or regions. Or tour packages or travel information could be presented only to those countries or regions where it is relevant.

When this document is processed WebPlexer will first determine the current language and replace the string Welcome to the ABC Travel Site with its translation out of the TermDB. Please see Section 3.6.3.1 WPReplace for a description of WPReplace tags and how the replacement is done. Note that this is not part of the MCSSI operation but is included to make the example a bit more realistic.

Note that the included MCSSI file can contain additional WebPlexer tags including MLSSI and WPReplace tags. This allows the MCSSI file to be further customized for the current language by replacing strings with their translations using the TermDB.

Please note that language dependent content is normally not included in MCSSI files and that template tags see Section 3.6.1.1 Template Types such as WPReplace see Section 3.6.3.1 WPReplace or MLSSI see Multi Language Server Side Includes MLSSI should be used instead.

Language dependent content means any static text that is present in the file. Including language dependent content within an MCSSI file is not recommended since an MCSSI file is included based on the setting of the current country. In other words MCSSI files should contain only country or regional specific content and be independent of language.

For example if the current country of the browser is Switzerland the user might be viewing the site in either French or German. If an MCSSI file for Switzerland is included that contains static text in French the language will be wrong if the browser is requesting German.

This problem can be easily solved by replacing the static text in the MCSSI file with template tags either by

MLSSI is typically used to customize an HTML document by including HTML that might be too complex to be managed by WPReplace tags. For example MLSSI can be used to include a language specific heading at the top of a form constructed out of WPReplace tags.

MLSSI also helps to separate the form of a Web site the structure and layout of the site from its content the actual message to be displayed on the browser .

The design and layout of a multi language site is usually very similar and often invariant across languages. MLSSI allows the language dependent parts of the content to be isolated from the structural design making it easy to update the design of the site and have changes reflected automatically across all of the languages. Likewise MLSSI allows language content to be easily updated and maintained without affecting the overall site design.

Another application of MLSSI is to include language specific graphics or image maps within a template file.

For example a form based HTML document that is a pure template can be customized with a language specific banner and graphic at the top of the file as follows 

When this file is processed the file banner.html will be fetched from the language directory specified in the WP Map file i.e. french banner.html german banner.html etc. 

Of course the WPReplace strings name address will also be replaced by their translations from the TermDB during processing of the file. See Section 3.6.3.1 WPReplace for a description of how this is done.

As can be seen MLSSI can be used to separate out the language specific components of an HTML document making it easier to maintain the collection. In the previous example if the structure of the HTML form needed to change it would only require changing the template file and not any of the language specific files on the site.

CGI scripts producing HTML output should be written to be as independent of language and country as possible. This means these scripts should use the HTML extensions provided by the Multilingual ToolKit. They should write out templates that do not contain language specific or country specific information. Having only one script to maintain means that changes can be made easily and efficiently.

When the HTML output of such a CGI script is presented to the browser WebPlexer will fill in the template dynamically with current language and country information. Text that is marked up with WPReplace tags will also be translated.

In order for WebPlexer to correctly process a CGI script the filename of the script must be changed when it is referenced in an HTML document. The filename must not include the path to the cgi root even though the script is actually located in that directory.

WebPlexer accepts a number of command line flags used for configuration and debugging. These are described below.

These flags cause WebPlexer to send debugging and informational messages to stderr. They should not be used in normal operation as they will cause some amount of performance degradation. Type . webplexer h for more information.

This flag uses the specified file to activate WebPlexer s test mode. The test file contains a list of up to 64 domain suffixes that will be consecutively spoofed for each access.

This disables WebPlexer s exception handling. Normally WebPlexer notifies the client when an exception occurs if possible .

The WP Config file is similar in format to a httpd.conf file and consists of a series of key value pairs one per line.

A key is a non blank string ending with one or more white spaces. Examples of keys are InternetPort and ServerPort.

A value is a parameter string and varies depending upon the key. Examples of values are the strings 80 and logs WPErrorLog .

Keys are separated from values by one or more column delimiters spaces or tabs . Any text on a line after a comment symbol is ignored.

Specifies the language to be used as the master or reference language for the console i.e. documents in that language will be used as a reference when determining which languages are out of date .

NOTE The language must be one of those supported by WebPlexer see Appendix B. List of Available Languages .

The extensions specified as extN indicate what filetypes will be under console maintenance functions.

Specifies individual files to be included under console maintenance functions beyond those included using the ConsoleTextExtensions directive.

Specifies individual files to be excluded from console maintenance among the set that was included using the ConsoleTextExtensions directive.

PlugIns use the WebPlexer API. Information on PlugIns is not available in this release. However the WP Config file should contain the following two lines 

The WP Map file contains a list of top level URLs that are subject to language selection. URLs are organized in URL groups and as many groups as necessary can be specified. Each group contains the following information 

There are two reserved names that have special meaning. One is default and the other is others . Both of these must be specified in the directory map of each URL group definition. They are described in more detail below.

For example if English French and Spanish documents exist on the server but the requested language is Russian WebPlexer will use the language defined as others .

The default language is used when WebPlexer cannot determine the language of a request and none has been specified by the browser. This can happen when the country of origin cannot be determined because the hostname is unavailable or when the requester is behind a firewall.

The output manager i.e. Multilingual ToolKit is enabled by specifying TermDB s in the WP Map file for a given top level URL.

All documents containing templates tags or other resources of the Multilingual ToolKit which require dynamic processing will be processed through the listed TermDBs for this URL group.

To use the input manager the name of the CGI script to be intercepted is specified in the WP Map file along with the location of a template file and an output .prt file for this URL group.

The template file tells the input manager which fields of the form should be extracted. When the CGI script is invoked the input data from those fields is saved and appended to the output or .prt pre translated file. This file also contains the time stamp current country and language and domain of the requester.

WebPlexer provides two files that can optionally force the selection of specific language s for certain hostnames or IP addresses when the top level URL is accessed.

The filenames corresponding to these log file types except for the UsageLog are defined in the WP Config file See Section 4.1.4 AccessLog Section 4.1.6 InformationLog and Section 4.1.5 ErrorLog for additional information . The UsageLog is created and maintained by the usage script described in Section 3.10.11.1 Usage utility. 

The AccessLog records information about each request received by WebPlexer such as date time and request type.

NOTE When WebPlexer is configured for production mode see Section 3.1.1.2 Production Mode WebPlexer s AccessLog should be used in place of the Web server s access log for auditing purposes. The Web server s access log will show all requests originating from WebPlexer.

The ErrorLog logs any errors that occurred during WebPlexer operation or during the processing of a request.

The InformationLog records information about WebPlexer language and country selection. An entry is written whenever language or country changes whether automatically or by manual selection.

The UsageLog contains a summary of country and language statistics. It is generated from the InformationLog using the usage log analysis tool. The UsageLog can be further processed using the visits log analysis tool. Please see Section 3.10.11 Log Analysis for a description of WebPlexer s log analysis tools.

New language of this request i.e. an entry is created when a visitor enters the site or changes language once on the site .

New country of this request i.e. an entry is created when a visitor enters the site or changes country once on the site .

The country.list file contains a list of available countries. It is identical to the list included in Appendix C. List of Available Countries. 

The WP Languages file contains a list of available languages and dialects. It is identical to the list included in Appendix B. List of Available Languages. 

Countries must be chosen from the list of valid countries for WebPlexer. See Appendix C. List of Available Countries. 

The WP Regions file contains only user defined regions. WebPlexer also maintains a set of pre defined default regions. These are listed in Appendix D. List of WebPlexer Default Regions. 

 Determining the country or region directory further describes the interaction and relationship between pre defined default and user defined regions.

The Master termdb is included with the product and contains translations of the names of the world s countries and languages in the following languages and encodings 

Although the invention is described herein with reference to the preferred embodiment one skilled in the art will readily appreciate that other applications may be substituted for those set forth herein without departing from the spirit and scope of the present invention. Accordingly the invention should only be limited by the Claims included below.

