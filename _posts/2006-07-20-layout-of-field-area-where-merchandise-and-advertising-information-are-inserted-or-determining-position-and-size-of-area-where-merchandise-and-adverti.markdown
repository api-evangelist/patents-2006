---

title: Layout of field area where merchandise and advertising information are inserted or determining position and size of area where merchandise and advertising information flow
abstract: Association information representing the association between the first information and the second information is set in the first record belonging to the first information and the second record belonging to the second information that are stored in a storage medium. A field area where data of the designated first record is inserted and a field area where data of the second record associated with the first record is inserted in accordance with the association information are laid out in a page on the basis of the template.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08464151&OS=08464151&RS=08464151
owner: Canon Kabushiki Kaisha
number: 08464151
owner_city: Tokyo
owner_country: JP
publication_date: 20060720
---
The present invention relates to an information processing apparatus which lays out in a page on the basis of a template field areas for inserting data of data fields selected from a record made up of a plurality of types of data fields a control method therefor and a program.

As various kinds of merchandise are produced shortening of the merchandise life has recently received attention. The necessity for CRM Customer Relationship Management and one to one marketing has also received a great deal of attention due to factors such as customer s orientation to customized services as the use of the Internet spreads. These methods try to raise the customer satisfaction win new customers and keep customers.

One to one marketing is a kind of database marketing. According to this technique a database of individual attribute information including the age gender hobby preference and purchase log of a customer is created and the contents of the database are analyzed to make a proposal complying with customer s needs. A typical method of this marketing is variable printing. These days a variable printing system which customizes a document for each customer and outputs the document has been developed along with the development of the DTP Desk Top Publishing technique and the pervasion of digital printing apparatuses. The variable printing system needs to create a customized document in which contents of different amounts for respective customers are optimally laid out.

Generally when such a customized document is to be created by the variable printing system containers are laid out in a document. The container is a drawing area for drawing contents drawing contents e.g. an image and text and is also called a field area.

Containers are laid out in a document and a database is associated with the layout various contents in the database are associated with the containers . As a result a desired customized document called a document template can be created. The contents of the customized document can be changed made variable by properly switching contents in the containers in the customized document by changing the association . Such a document is called a variable data document and a printing system using the variable data document is a variable printing system.

In a conventional variable printing system the size of a container associated with a text or image serving as contents is fixed. When contents in the database are inserted flowed into a container and the data amount is larger than the container size the following problems arise. That is if the data is a text overlapping of the text occurs. If the data is its image clipping of the image occurs. When the data amount is smaller than the container size no proper display may be obtained such that a gap appears between the container and its internal contents.

As another technique of changing the layout in order to solve these problems a Layout Designing Apparatus in Japanese Patent Laid Open No. 7 129658 paragraph 0049 FIG. 8 discloses a technique of when the size of a given container becomes large decreasing the size of another container adjacent to the given container.

Japanese Patent Laid Open No. 2004 171395 paragraph 0051 FIG. 8 discloses another technique. That is the items of merchandise specifications such as price running cost and processing speed are rearranged in accordance with the priority order of customer s demands. Then data are input to field areas and a customized catalogue is saved and output.

In the prior arts however when an advertisement is dynamically inserted into a merchandise catalogue to output the merchandise catalogue a field area for the advertisement is fixed. If the image size or text length changes the layout is deformed resulting in a catalogue of poor appearance. In order to solve this problem the catalogue must be manually edited in advance decreasing the efficiency.

The present invention has been made to overcome the conventional drawbacks and has as its object to provide an information processing apparatus capable of suitably properly laying out pieces of associated information in a page a control method therefor and a program.

According to the present invention the foregoing object is attained by providing an information processing apparatus which lays out in a page on the basis of a template field areas for inserting data of data fields selected from a record made up of a plurality of types of data fields comprising 

first storage means for storing a first record belonging to first information and a second record belonging to second information 

second storage means for storing association information representing association between the first information and the second information and

layout means for laying out in a page on the basis of the template a field area where data of the designated first record is inserted and a field area where data of the second record associated with the first record is inserted in accordance with the association information.

In a preferred embodiment the layout means lays out in a page on the basis of the template a first record field area where the data of the designated first record is inserted and then lays out in the same page a second record field area where the data of the second record associated with the first record is inserted in accordance with the association information.

In a preferred embodiment the apparatus further comprises output means for outputting a layout result by the layout means.

In a preferred embodiment the apparatus further comprises setting means for setting the association information representing the association between the first information and the second information 

the setting means further comprising priority order setting means for setting priority order at which the data of the second record is inserted into the field area.

In a preferred embodiment the apparatus further comprises setting means for setting the association information representing the association between the first information and the second information 

the setting means further comprising frequency setting means for setting a frequency at which the data of the second record is inserted into the field area.

In a preferred embodiment the information processing apparatus is a server apparatus connected to a network.

In a preferred embodiment the apparatus further comprises transmission means for transmitting to a client apparatus connected to the network a preview window for previewing a layout result by the layout means.

In a preferred embodiment the apparatus further comprises transmission means for transmitting a layout result by the layout means to an image forming apparatus connected to the network.

According to the present invention the foregoing object is attained by providing a method of controlling an information processing apparatus which lays out in a page on the basis of a template field areas for inserting data of data fields selected from a record made up of a plurality of types of data fields comprising 

a setting step of setting association information representing association between first information and second information in a first record and second record which are stored in a storage medium the first record belonging to the first information and the second record belonging to the second information and

a layout step of laying out in a page on the basis of the template a field area where data of the designated first record is inserted and a field area where data of the second record associated with the first record is inserted in accordance with the association information.

According to the present invention the foregoing object is attained by providing a program for causing a computer to execute control of an information processing apparatus which lays out in a page on the basis of a template field areas for inserting data of data fields selected from a record made up of a plurality of types of data fields characterized by causing the computer to execute

a setting step of setting association information representing association between first information and second information in a first record and second record which are stored in a storage medium the first record belonging to the first information and the second record belonging to the second information and

a layout step of laying out in a page on the basis of the template a field area where data of the designated first record is inserted and a field area where data of the second record associated with the first record is inserted in accordance with the association information.

According to the present invention the foregoing object is attained by providing an information processing apparatus comprising 

acquisition means for acquiring second information on the basis of the first information selected by the selection means 

determination means for determining by using a template positions and sizes of respective areas where information on the first information selected by the selection means and information on the second information acquired by the acquisition means are flowed and

flowing means for flowing the information on the first information and the information on the second information into the areas of the positions and sizes determined by the determination means.

In a preferred embodiment the template is determined on the basis of the first information selected by the selection means and the second information acquired by the acquisition means.

In a preferred embodiment the template is determined on the basis of the number of pieces of second information acquired by the acquisition means.

According to the present invention the foregoing object is attained by providing a layout method comprising 

an acquisition step of acquiring second information on the basis of the first information selected in the selection step 

a determination step of determining by using a template positions and sizes of respective areas where information on the first information selected in the selection step and information on the second information acquired in the acquisition step are flowed and

a flowing step of flowing the information on the first information and the information on the second information into the areas of the positions and sizes determined in the determination step.

According to the present invention the foregoing object is attained by providing a program characterized by causing a computer to execute

an acquisition step of acquiring second information on the basis of the first information selected in the selection step 

a determination step of determining by using a template positions and sizes of respective areas where information on the first information selected in the selection step and information on the second information acquired in the acquisition step are flowed and

a flowing step of flowing the information on the first information and the information on the second information into the areas of the positions and sizes determined in the determination step.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings .

A preferred embodiment of the present invention will be described in detail in accordance with the accompanying drawings.

The hardware configuration of an information processing system and that of a host computer as a building component of the information processing system according to the embodiment will be described with reference to .

Various computers e.g. a database server and file server other than the host computer in also have the same hardware configuration as e.g. that in .

In an information processing system is built by connecting a host computer the database server the file server and an image forming apparatus e.g. printer via a network .

The database server comprises a database . The image forming apparatus can properly print print data received via the network .

The information processing system in especially shows an example of the configuration of a variable printing system which prints a variable data document. A variable printing process to be described in the embodiment is implemented by the host computer formed from a general purpose computer module which functions as a layout editing apparatus.

A layout editing application which can run in the variable printing system is executed completely or partially by the host computer . In particular a process associated with layout editing and a process associated with printing of a variable data document are implemented by software which is executed by the host computer .

Software and computer programs such as the layout editing application are stored in a computer readable medium. The software and computer programs are loaded from the computer readable medium into a memory of the host computer and executed. The computer readable medium which stores software and computer programs is a computer program product. When the computer program product is used in e.g. the host computer an apparatus suitable for layout editing and variable printing of a variable data document is provided.

As shown in a keyboard and a mouse serving as a pointing device are connected as input devices to the host computer via an I O Input Output interface . A display device is also connected as an output device via a video interface . The image forming apparatus can also be connected via an I O interface .

The I O interface also has a function of connecting the host computer to the network . With the I O interface the host computer can be connected via the network to another computer apparatus external device in the variable printing system . Typical examples of the network are a local area network LAN and wide area network WAN .

As shown in the host computer includes at least one processor and a memory which is formed from a semiconductor memory such as a random access memory RAM or read only memory ROM . A storage device includes a hard disk drive HDD capable of exchanging data with a computer readable medium which stores various data such as a program and a Floppy disk drive FDD .

Although not shown in various storage devices such as a magnetic tape drive and memory card can also be used as the storage device . A CD ROM drive is provided as a nonvolatile data source a computer program may also be provided by a CD ROM .

The host computer communicates with the building components to of the host computer via an interconnection bus . This communication is realized by an operating system such as GNU LINUX or Microsoft Windows or typically in accordance with an operating system. Alternatively this communication is done by a method in a conventional operation mode of a computer system which is formed by a well known related technique. That is the building components to are connected via the interconnection bus so that they can communicate with each other and are used by an operating system installed in the host computer .

Conceivable examples of the host computer shown in are an IBM compatible PC Personal Computer Sparcstation available from Sun and a computer system including them.

In the embodiment the layout editing application is resident in the hard disk drive and controls execution and loading by the processor . Data fetched from the intermediary storage device of the layout editing application and the network use the memory in response to the hard disk drive .

For example an encoded program of the layout editing application is stored in a CD ROM or Floppy disk. This program is loaded via the corresponding CD ROM drive or Floppy disk drive and installed in the hard disk drive .

As another example the layout editing application may be loaded from the network into the host computer and installed in the hard disk drive .

Various software programs including the layout editing application may be loaded into the host computer from a magnetic tape a ROM an integrated circuit or a magneto optical disk. These software programs may also be loaded into the host computer by radio communication e.g. infrared communication between the host computer and another device. These software programs may also be loaded into the host computer from a computer readable card e.g. a PCMCIA card or another proper computer including e mail communication an intranet or the Internet having recording information on a WEB site. They are examples of the computer readable medium and another computer readable medium is obviously used.

In the layout editing application causes the host computer to implement variable printing to be also referred to as variable data printing VDP . The layout editing application includes two software components a layout engine and user interface .

The layout engine is a software component for loading records one by one from variable data which are stored as records in the database under constraints in size and position on a container rectangular range serving as a field area partial area . Further the layout engine calculates from the loaded variable data and the container constraints the layout including the size and position of a container to which the loaded variable data is flowed.

In the embodiment the layout engine also performs a process of drawing variable data assigned to a container and generating an image of a variable data document. However the present invention is not limited to this and the layout engine operates as an application which determines the size and position of each partial area container and outputs drawing information to a printer driver not shown . The printer driver may perform a variable data document image drawing process and generate print data.

The user interface allows the user to set the layout and attribute of a container and create a document template to be also referred to as template information . The user interface provides a mechanism of associating each container in the document template with a data source variable data contents in the database . The user interface and layout engine communicate with each other via a communication channel .

An example of the data source for generating a variable data document is the typical database in the database server which generally executes a database application and is formed from another computer.

The host computer communicates with the database server via the network . The layout editing application generates a document template to be saved in the host computer or the file server which is generally formed from another computer.

The layout editing application generates a variable data document which is formed from a document template merged with variable data. The variable data document is saved in the local file system of the host computer or the file server or printed directly by the image forming apparatus .

Another example of the configuration of the variable printing system will be explained with reference to .

The engine server is formed from a typical computer similar to the remaining servers. A document template saved in the file server can be combined with data saved in the database in order to generate a document by the layout engine for printing or another purpose. Such operation is requested via the user interface or so requested as to print only a specific record.

In the layout editing application is implemented in a client in a server client system but is not limited to this. For example an application server in which the layout editing application is installed may be configured and the client may access the application server.

More specifically a configuration in which a Web server client system is constructed the layout editing application is installed in the Web server and the configurations in are implemented between the Web server and the Web client will be explained.

An outline of the configuration of the Web server client system will be explained with reference to .

In the client personal computers to be referred to as client PCs hereinafter to the server personal computer to be referred to as a server PC hereinafter and the image forming apparatus are connected to the network . These computers have the same hardware configuration as that in .

The server PC has a Web server function receives instructions from the client PCs to via their Web browsers and sends back process results to the Web browsers of the client PCs which have issued the instructions. Note that the present invention does not particularly limit the communication method between the server PC and the client PCs to . The single server PC may implement the configurations in .

The client PC has a Web browser function. In addition the client PC comprises an information registration module for registering contents such as catalogue information or image data in the server PC . The client PC comprises an output form registration module for registering a form document template for outputting merchandise information content data . The client PC further comprises an output result preview module for previewing the output result of merchandise information.

These modules are automatically distributed as plug ins of the Web browser from the server PC as needed and need not be installed in the client PC .

The server PC has an HTTP Web application server function. The server PC comprises a module set including various modules for processing requests from the client PC .

The module set includes the following modules for example a user authentication module search process module merchandise information registration module advertisement information registration module catalogue information registration module and association information registration module. In addition the module set includes a batch registration module for various data catalogue information and association information various maintenance modules and a merchandise information catalogue output module.

These modules are loaded into the memory in the server PC to execute processes in response to a request from the client PC .

Separately from these modules the server PC comprises an editing module including an image editing module for editing an image such as a PDF file by using a layout engine and a file editing module for performing editing such as merging division for a data file. The editing module is implemented by e.g. the layout editing application .

Further the server PC comprises a database shared library for exchanging data with a database corresponding to the database in in the server PC and a utility library for implementing various functions.

The image forming apparatus comprises a scanner unit a print engine a control unit which is controlled by a touch panel a fixing unit a sheet feed unit a delivery unit a finishing device and a bin at which delivered paper sheets are stocked. With these building components the image forming apparatus functions as an MFP Multi Function Peripheral which implements a plurality of types of functions such as a copying function printing function FAX function and data transfer function. Note that the scanner unit has an auto document feeder ADF .

In the image forming apparatus the scanner unit scans a document on the basis of an operation from the control unit and the print engine executes a printing process in a designated printing mode. A printed material as a result of printing on a printing sheet by the printing process is delivered from the delivery unit . If necessary the printed material undergoes a finishing process stapling punching or the like by the finishing device and is output to the delivery bin .

Note that the control unit has a CPU which controls the image forming apparatus a RAM which is used to store various data and functions as a data work area and a ROM which stores various programs including a control program for implementing processes of the embodiment.

Reference numeral denotes an execution environment of the present invention in which the overall image forming apparatus is controlled. The execution environment is implemented by e.g. each module of a real time OS capable of controlling various functions of the image forming apparatus in real time. The execution environment may also be implemented by libraries which can instruct the CPU to critically control functions including the optional device and expansion card of the image forming apparatus . Further the execution environment is implemented by modules which provide interface commands to an application running on an upper layer.

Reference numeral denotes a controller control unit which runs in the execution environment . Reference numeral denotes an application programming interface to be referred to as an API hereinafter . The API has a function of executing a process to access the controller control unit and transmitting a control command to the image forming apparatus in response to the instruction sequences of instruction inputs from applications to and the like.

Reference numeral denotes an execution environment optimal for executing a specific application which implements processes described in the embodiment. The execution environment is implemented by e.g. a Java virtual machine. The applications and run on the virtual machine and request various processes of the controller control unit by using the API . The applications and can also communicate with various information processing apparatuses and to via the network .

Reference numeral denotes a resource management unit which manages resources used by the virtual machine and runs in the execution environment . The resource management unit limits the use of more than predetermined resources when the virtual machine itself the API or all the applications to on the virtual machine use resources such as a memory.

A plurality of containers to are laid out on a page in accordance with an operation instruction from the user via the user interface of the layout editing application . Constraints on position and size are assigned to the containers via the user interface to generate a document template .

The user interface associates the document template with a data source e.g. the database and further associates each container with each data field in the data source . Association information representing the association between each container and each data field in the data source is described in the document template and the document template is stored in the HDD . The data source is a file which describes item data for each record and is stored in the HDD .

The layout engine loads data associated by association information from the data source into the containers to of the document template in accordance with a print instruction or preview instruction from the user. The layout engine flows the data of each record into the containers e.g. flows data fields A to C of data record into the containers to . The layout engine adjusts adjusts the layout the size of each container and the like in accordance with the flowed data.

For a preview instruction the layout engine generates a layout adjusted document image and outputs it on the screen of the display device so as to display the image as a preview. For a print instruction the layout engine outputs as print data to the image forming apparatus a document image generated using the layout engine or printer driver. By sequentially processing data records . . . variable data printing is implemented.

As shown in the user interface displays on the display device a user interface which is formed by an application window upon operation. The application window has a menu bar tool bar work area and optional palette .

The menu bar and tool bar can be hidden or moved to various locations in the window. The location of the work area can be moved by operation of the mouse . The palette is an option and can be controlled to be display hidden in accordance with a purpose. A cursor pointer indicates the hotspot of the mouse .

The tool bar has many tool buttons and widgets components which can be hidden or displayed in a special mode of the application.

A ruler is an option and is used to indicate the position of a pointer page line margin guide container or object in the work area .

A palette is used to access an additional function such as a variable data library. The palette has a window control button for moving resizing and closing the palette . The palette can be displayed on the front surface of the work area or on the back surface of an object. The palette can be displayed only within the application window or displayed partially or entirely outside the application window .

 1 Selection tool button The button is used to select move resize and lock unlock the edge of a container. A container is selected by dragging a selection box around the container. A plurality of containers can be selected by selecting and operating them while pressing the CTRL key of the keyboard .

 2 Text container tool button The button is used to create a container having a static or variable text.

 3 Image container tool button The button is used to create a container having a static or variable image.

 4 Link tool button The button is used to create a link for associating containers and also used to control the distance of a link.

As a known technique these buttons are implemented as tool tips of icons which change in accordance with an operation status.

The application window can determine a basic layout by laying out containers and links in a page. The basic layout is a layout serving as a base for variable data printing. When each container in the basic layout is a fixed layout the print results of all records have the same layout.

When each container in the basic layout is a flexible container to be described later the size and position of the container change in accordance with the amount and size of data loaded from each record under constraints to be described later .

Hence a document template created by the layout editing application determines only the basic layout. When the document template contains a dynamic container the layout of a finally printed material is adjusted in accordance with loaded data.

A container whose size and position are fixed will be called a static container in comparison with the dynamic layout.

In the work area is used to display and edit the design of the document template basic layout . The work area can present an outline of a document to be printed to the user while the user designs a document template. From the outline of the document the user can easily understand how a document merged with the data source changes depending on the amount and size of variable data.

When the data source is associated with the document template corresponding variable texts and images are displayed in laid out containers so as to preview a current document.

A document structure and visual clues e.g. frame anchor slider and link of a container for drawing a container in the document template are always displayed in creating the document template. In preview for flowing variable data visual clues are displayed when the cursor is moved onto a container or a container is selected.

The work area includes a scroll bar the optional ruler and a document template . The document template can show that a document has a plurality of pages. The document template corresponds to the document template in .

The page size of a given document template is designated by the user using a known technique. For example a dialog for setting a page size is displayed by selecting page setup from file on the menu and a page size designated by the user is reflected in the dialog.

The number of actual pages of each document may change depending on variable data in an associated data source. In this case a field which changes in size depending on the variable data amount like a dynamic table is set in the document template. That is in this case an additional page is automatically created upon loading variable data which cannot fit variable data in one page.

A boundary displayed in each page is an arbitrary page margin which represents the maximum width of a printable object on the page.

Such objects are containers and an arbitrarily applied anchor icon fixed edges and an unfixed edge a link and a slider .

The anchor icon can be set at a corner or edge of a rectangular container or at the center of a container. When the anchor icon is set the position of the set anchor icon is fixed. In the example of the anchor icon is set at the upper left corner of the container . The anchor icon shows that the container can be enlarged to the right or down when variable data is flowed into the container and the image size or text amount of variable data is large.

When the anchor icon is set at an edge the edge is fixed and the container can be enlarged along the three remaining edges. When the anchor icon is set at the center of a container the center position of the container is fixed and the container can be enlarged in four directions so as not to change the center position of the rectangular container. Although details of the link will be described later the link represents that the containers and are associated. The link also represents that the container can be moved to the right while maintaining a length range can be specified set for the link . The slider shows that it can be moved parallel to an edge at which the slider is set.

A container will be explained as a field area for inserting data of a plurality of types of data fields contained in each record in the database. The container is a field area to be referred to as a partial area where a fixed or flexible text and image data of a plurality of types of data fields are flowed from a variable data file into a document template and drawn. The container is laid out together with other containers and objects as shown in . The container is moved adjusted in size or created again by operation of the mouse in accordance with an operation instruction from the user via the user interface.

More precisely the container has a set of settings visual representation interaction and editing operation. The definition of the container in the embodiment will be described.

Flexible contents variable data can be said to be dynamic in a sense that data acquired from the data source may change for each document i.e. each record. Note that flexible contents in the embodiment are not intended to be animated contents or contents which change over time by another method because these contents are not suitable for printing.

Similarly fixed contents are displayed identically for all documents generated using containers. When however a link to flexible contents is set fixed contents may change in position in each document under the influence of the flexible contents.

 2 A container has decoration functions similar to text settings such as the background color border and font style which are applied to contents. These settings will be called container attributes. The container attributes can be set for each container and a container can also be given the same container attributes as those of a given container.

 3 A container is merged with data from the data source when a document is generated. The decoration function is visible on a printout for any fixed contents. Flexible contents provide display of specific data from the data source. This representation of the container can be for example printed and or also displayed on the screen of the display device .

 4 A container has a user interface as a visual clue as shown in . For example a container has an interactive graphical user interface GUI for editing a container and setting its display. GUI components are displayed on the screen of the display device but are not printed in a document. The user interface of the layout editing application displays some of the container decoration functions such as the background color and font and has a function of enabling editing and displaying container settings.

Examples of special purposes of the user interface function are a border or a corner icon for interactively changing and displaying the size and position of a container. Other examples are an overwrite count representing container operation when a container is merged with data from the data source a line an icon and a text.

The container has constrains on controlling how to link contents displayed in each document. These constraints including linking of fixed flexible contents to a container are a major method of controlling generation of many documents from one document template by the user.

An example of the constraints is the height of contents in this container is 4 inches at maximum . Another example of the constraints is the left edge of contents in the container must be displayed at the same horizontal position in respective documents . The descriptions of the constraints provide various methods for displaying and editing these constraints by using the GUI.

A content place holder which designates the layout of fixed contents like an image which has a defined place on a page is well known in the digital printing technique. A container has a position and size which are edited and displayed by a method known in a conventional technique. The following description is focused on display and editing by a method specialized in variable data printing.

By using a container the user can designate the size drawing size and position of contents in a document. Since a plurality of types of documents are generated from one document template many possibilities and constraints are set on a container. For these settings designation and display a predetermined user interface is exploited.

The edge of one container defines a virtual boundary within which associated contents are displayed in a document. Hence a discussion about the left edge of a container is a discussion about the leftmost edge in an area in which associated contents can be displayed in each document. Similarly a discussion about the height of a container is understood to be a discussion about constraints on the height of associated contents in a generated document. In this specification this distinction will become apparent when the edge or size of a container is discussed by referring to the user interface .

In the following description a term fixed which defines a given value used to constrain display of contents applies to all documents.

 1 When the width of a container is fixed a width assigned to associated contents is equal in all documents.

 2 When the height of a container is fixed a height assigned to associated contents is equal in all documents.

 3 When the distance length of a link is fixed a designated distance acts as a constraint in all documents.

 4 When the right and left edges of a container are fixed the horizontal positions of the edges of a page are identical in all documents. However the height or vertical position of a container may change. For example when the left edge of a container is fixed the display position of associated contents is defined such that the horizontal position of the left edge is identical in all documents. However the contents may be displayed at an upper portion on a page in a given document but at a lower portion on a page in another document.

 5 When the upper and lower edges of a container are fixed the vertical positions of the edges of a page are identical in all documents. However the width or horizontal position of a container may change in each document.

 6 The vertical axis of a container is a virtual vertical line which is parallel to the right and left edges of the container and positioned between them. If the vertical axis of a container is fixed the average i.e. center position between the right and left edges of the horizontal positions of the right and left edges of the container is identical in all documents. Under this constraint the width of a container may change. However the vertical axis is at the same horizontal position in all documents including a document whose right and left edges are the farthest from the vertical axis and a document whose right and left edges are the nearest to the vertical axis. The height and vertical position of a container are not influenced by this constraint.

 7 Similarly if the horizontal axis is fixed the average of the upper and lower edges of a container coincides with the same vertical position. However the width and horizontal position of a container are not influenced by this constraint.

 8 When both the horizontal and vertical axes are fixed this means that the center position of a container is fixed. However the width and height of a container are not influenced by this constraint.

 9 When the corner position of a container the intermediate position of the edge of the container or the center position of the container is fixed the fixed position is identical in all documents. For example if the upper left corner of a container is fixed the upper left position of a laid out container is identical in all documents.

 10 A vertical edge or axis can be fixed in association with the left or right edge of a page a left or right page margin or another horizontal position. Similarly a horizontal edge or axis can be fixed in association with the upper or lower edge of a page an upper or lower page margin or another vertical position.

A term opposite to fixed is flexible which means that the edge axis corner or intermediate position of a container or a document constraint may change between documents records . For example the layout in a page is expected to dynamically change depending on the size and amount of variable data. For a specific container its size and position may be desirably fixed or the four corners of a container at a corner of a page may be desirably fixed.

To meet these demands the layout editing application can properly set whether to fix or change make flexible an edge axis corner intermediate position or the like for each container partial area . The user can create a desired basic layout when he determines the basic layout of the document template .

A container is described as either of two text and image containers. The text container has a text and buried image. The image container has only an image.

As shown in a new text container or image container is created on the document template by clicking the text container tool or image container tool with the mouse and dragging a rectangle onto the document template .

Alternatively a container may be created by making a desired one of the text container tool and image container tool active and simply clicking on the document template . In this case a container of a default size is inserted into the template in accordance with clicking of the mouse and a dialog box or another prompt for setting the dimensions of the new container or the like is provided.

Note that the container size may be set by various methods so that the container size is automatically defined in advance or a container is created and laid out in accordance with a calculated schema. A generated container is selected with an input device such as a mouse and operation such as designation of properties with right clicking is performed. Then the property dialog of a container is displayed and constraints on the container can be set.

The layout editing application draws an edge by using a solid line item or dotted line in order to represent the state of the container edge. The layout editing application also uses anchors and lines shapes or icons drawn near the edge of a container . The layout editing application further uses a handle control point drawn on or near the edge of an area for movement and modification the slider short parallel lines drawn on the two sides of an edge see a scaling icon and the color.

 5 Scaling icons are drawn near edges which are not drawn by rules 1 to 3 and these edges are drawn in dotted lines.

 6 If a pair of vertical and horizontal edges or vertical and horizontal axes is fixed an anchor is drawn at the intersection.

 8 If neither anchor nor slider is drawn on a pair of vertical and horizontal edges or vertical and horizontal axes a handle is drawn at the intersection.

Lines defined by rules 1 2 and 3 are drawn in solid lines because these lines are fixed or restricted as described above. A flexible edge is drawn in a dotted line as defined by rule 5 . Anchors are displayed at fixed points defined by rules 6 7 and 8 sliders are displayed on several fixed edges and handles are displayed for other components.

The above rules give priority to a constraint set later by the user. More specifically when another constraint is set later and the rules influence an edge to be drawn the drawing contents of solid and dotted lines are changed. For example when a container is so small that icons overlap each other or another display function becomes obscure the icons may be changed or omitted to draw lines.

The place at which a flexible edge is drawn depends on the contents of a container. As will be described later a dynamic calibration process is employed which means that contents are merged into a document template and visualized on a user interface. Alternate execution can be achieved by another means for determining where a flexible edge is laid out in a user interface or in the content area of a container averaged in all documents.

These content representations provide a graphic function of displaying the state of each edge of a container. The representations are interpreted as follows.

 1 A dotted line means that the position of an edge in a document changes depending on the contents of a container like the edge in .

 2 The solid edge means a fixed edge or an edge restricted because the width or height of a container is fixed the four edges of the container are drawn in solid lines and both the width and height are fixed .

 3 An anchor means that a place where edges or axes cross each other is fixed. Anchor points appear at horizontal and vertical positions in all documents and anchors are naturally fixed. The icon in is an example of the anchor icon meaning that the position where the edges cross each other is fixed.

 4 A slider means that the length of an associated edge is fixed but may be translated. For example the slider in represents that the contents of the container may be displayed left or right to a position given by a specific diagram in a document.

For example when the image size or text amount of data flowed into the container associated with the container link is set between them is small the size of the container decreases. Thus the container is slid translated to the left laid out and displayed. When the size of the container increases the container is slid to the right and laid out.

Some or all of these icons and edges are drawn or are not drawn depending on which of tools and containers is selected highlighted or made active. Generally the edges and icons of a container are assistance to design a document template and are not drawn on a printed material.

As described above settings of a basic pattern such as the reference minimum and maximum values of the width and height of a container are displayed in a secondary dialog window.

In both the width and height of a container are not fixed are flexible . A fixed edge is represented in a solid line and a flexible edge is represented in a dotted line. A scaling icon exhibits that the adjacent edge is flexible. An indicator in another form may also be used instead or additionally.

In both the width and height of the container are flexible. An anchor icon is so added as to explicitly represent that the corner position between two crossing edges is fixed.

In an upper edge of the container is fixed but both the width and height are flexible. The anchor icon positioned at the center of the upper edge is fixed. The left and right edges of the container pass the anchor icon and move apart from or close to the vertical center axis vertical axis .

A link indicates association between containers. The association represents a distance between containers and containers associated by a link execute layout calculation upon a change in their layouts. For example the link in associates the containers and with each other as described above. The link setting method and the layout calculation method for containers associated by a link will be described later.

In step S the layout editing application displays a document template selected as an editing target in the work area of the user interface. In order to set a link at least two containers to which a link is to be set must be created on the document template. show an example of transition of the user interface when two containers are created and a link is set in step S.

In step S the layout editing application selects a link tool the link tool is selected by clicking the button in .

In containers and are made up of fixed edges. Reference numerals and denote anchors similar to in . Reference numeral denotes a mouse pointer.

While the link tool is selected the user clicks on and selects one e.g. the container of two containers to which a link is to be set. In accordance with this operation the user interface of the layout editing application recognizes that the first container has been selected step S and holds information which specifies the selected container.

A locus corresponding to subsequent movement of the mouse cursor is displayed on the screen. For example a line segment in exhibits a line which connects a click position in the state of and the current position of the mouse pointer . This UI can present the user with a position at which a link is set.

As shown in the user moves the mouse pointer to the other container container and clicks. In accordance with this operation the user interface recognizes that the second container has been selected step S and holds information which specifies the selected container.

The layout editing application sets a link between the first container selected in step S and the second container selected in step S.

After the link is set between the two containers and selected by the user a link is displayed step S . In response to the link setting the container display state changes to a state in step S .

That is the container UI is automatically changed upon setting the link. In this case edges associated by the link become flexible and are drawn in dotted lines. In reference numeral denotes an edge which is drawn in a dotted line and is a flexible edge as described above.

The state of the container edge as shown in is automatically changed when the need for making the container edge flexible arises upon setting a link. A purpose of this operation is to prevent a contradictory state in which all edges are fixed though a link is set. Reference numeral denotes a mark which similar to in visually presents the user with a direction in which a container can be changed upon setting a link. In the example of the right edge of the left container and the left edge of the right container change to a flexible state but this is merely an example. The right container may change to a setting having the slider in .

The layout editing application according to the embodiment has at least two operation modes. One is a layout mode in which containers are created using the user interface and associated link is set to create a layout. The other is a preview mode in which each record in the data source is inserted into a created layout by the layout engine and a layout result to which the record is actually inserted is previewed.

In the preview mode an actual record is inserted and the layout is calculated. In the preview mode layout calculation on the display is performed. In actual printing the layout engine inserts data into each container and calculates the layout and the calculation method at this time is the same as that in the preview mode.

The preview mode is selected step S . In the preview mode the layout editing application prompts the user to select a record to be previewed from the data source and inserts each field data of the selected record into each container step S .

After the field data is inserted into each container the layout editing application executes layout calculation for laying out the record and if necessary adjusts the layout step S . Details of layout calculation in step S will be described later.

The layout editing application displays previews the layout calculated in step S step S . The layout editing application determines on the basis of an instruction from the user whether to preview another record step S . If another record need not be previewed in step S NO in step S the preview mode ends step S .

If another record needs to be previewed YES in step S the layout editing application selects another record executes layout calculation again and previews the calculated layout step S .

In printing unlike the preview mode layout calculation is sequentially performed for all records to be printed. In printing therefore step S is omitted and whether all records to be printed have been processed is determined in step S. In step S the results of layout calculation are drawn output and generated as print data using the printer driver thereby outputting the print data to the printer. In this case the process ends when print data are output for all records all records to be printed .

The layout editing application sets a set of containers whose layout is to be calculated step S . Layout calculation is done for associated containers as one set.

For example referring to four containers are laid out on a page and association is set between the containers. In this case containers A and B are associated by a link whereas containers C and D are associated by a link.

Containers A and B are specified as set whereas containers C and D are specified as set . In other words containers connected by a link are specified as one set. As described above reference numeral denotes an anchor a fixed edge a controller an arrow indicating a direction in which a flexible edge changes a flexible edge a link and a slider.

The layout editing application selects one of the container sets obtained in step S in order to calculate a layout step S . The layout is calculated for the selected container set.

For two containers A and B as flexible elements contained in the selected container set a size when each container is free from any constraint is calculated from the image size or text amount of data to be flowed.

More specifically the layout editing application determines whether container A is an image data container or text container. This determination is made on the basis of an attribute set for the container as described above.

Then the layout editing application loads data flowed into container A. When container A is an image data container the size the numbers of pixels corresponding to the width and height and resolution of the image data is a size when container A is free from any constraint.

When container A is a text container the amount of text data to be flowed into container A can be calculated on the basis of the number of characters and character attributes designated by the container attributes of container A. The character attributes are e.g. the font type font size character pitch and line pitch.

For a text container constraints are imposed because the aspect ratio of container A cannot be decided unless constraints are taken into consideration. In the example of anchors are set at the upper and lower left corners of container A and its height longitudinal direction is fixed. The layout editing application determines whether characters of a calculated data amount text amount can be flowed into container A having a width lateral direction set as the basic pattern of container A.

If the layout editing application determines that all characters can be flowed the size width and height of container A that are set by the basic pattern is not changed. If the layout editing application determines that all characters cannot be flowed container A extends in the lateral direction because the height is fixed by anchor setting. The layout editing application calculates the width of container A at which characters of the calculated data amount can be flowed and thereby calculates the size of container A.

The layout editing application optimizes the layout so as to minimize the difference between the size of the laid out container and that of actual contents step S .

The layout is optimized so that the difference between the layout size and the size of contents to be inserted into a container is minimized in each of containers which are so associated as to dynamically change their sizes.

The layout editing application calculates the size of the container set that is calculated in step S i.e. the total size of containers A and B and link in this case fixed link . The layout editing application calculates the difference between the total size and the size in the example of corresponding to the distances of the anchor icons of containers A and B of the container set in the basic layout. If containers A and B become wider a difference value is generated after calculation in the previous step. The layout editing application adjusts the layout by equally distributing the difference value to respective elements of the container set.

The layout editing application optimizes the layout and determines whether the layout breaks the rules step S . If the layout does not break rules YES in step S the process advances to step S. If the layout breaks the rules NO in step S the process returns to step S to calculate the layout again so as not to break the rules.

The rules are constraints set by the user in creating a layout and include constraints on the flexible range of the size of a container and the position of the container and for a flexible link a constraint on a change of the length of the link. After the layout editing application calculates the layout so as not to break the rules the layout of the set is completed.

The process from steps S to S is performed for all sets on the page and the layout editing application determines whether the layout of the entire page has been calculated step S . If the calculation has not ended NO in step S the process returns to step S. If the calculation has ended YES in step S the process ends.

In similar to the application window and tool bar are configured. In the state of containers and exist on the document template . The container includes anchor icons and fixed edges whereas the container includes anchor icons and fixed edges .

A flexible size link is set between the containers and to link them. Since the link is set between the containers and a right edge of the container and a left edge of the container are represented in broken lines. Indicators and are displayed on the respective containers to represent that the edges and are flexible.

The dialog window has a link type field made up of radio buttons for alternatively selecting whether the link type is a link of a flexible length or that of a fixed length .

When the link type is a flexible length link a link distance field is formed from a minimum value field minimum distance maximum value field maximum distance and reference value field for the link length.

The dialog window in is displayed when a link is set between two containers by e.g. the link setting operation described with reference to to C and then the set link is selected by an operation such as clicking. Alternatively immediately after a link is set the dialog window relevant to the link may be automatically displayed. The reference value of the reference value field for the distance between containers is a link length used when the size of each container does not change upon flowing data into it.

For example when a link is set between two containers A and B in by the link setting operation described with reference to to C a link of a fixed size is set. By selecting this link and executing the process shown in the link can be changed from the fixed size link to the flexible size link .

First a desired link e.g. the link in is selected with the mouse step S . Then a predetermined operation to display link properties is performed. In response to this the user interface of the layout editing application displays the dialog window corresponding to the selected link to be referred to as a target link hereinafter step S .

Note that the link selection operation is an arbitrary one such as right clicking of the mouse or an operation to a specific key of the keyboard similar to the setting of the basic pattern of a container.

The displayed dialog window presents the current state of the selected link. In this example since the link is selected the link size is fixed in this stage and the distance representing a fixed length is selected in the link type field .

In order to change the link from a fixed size to a flexible one in the dialog window the flexible length button is selected in the link type field to set the link size flexible step S .

In response to this selection the maximum distance field minimum distance field and reference value field arranged in the link distance field are enabled to allow setting numerical values. In order to set a flexible size of the link the user sets the maximum value of the link length in the maximum distance field the minimum value in the minimum distance field and the current value in the reference value field step S .

After the end of the settings the user designates application of the settings with the general dialog window opening closing button . When the user interface detects this designation it reflects the setting state on the target link. As a result the link UI display changes to a state as represented by the link in step S .

The layout is calculated by the same method as that described above. For example assume that image data of different sizes are inserted into the containers and shown in . In this case the respective containers regard data sizes to be optimal. The container is to change its size to the right so as to move close to a frame optimal container size corresponding to the size of the inserted image. Similarly the container is to change its size to the left so as to move close to a frame optimal container size corresponding to the size of the inserted image.

However a left edge of the container and a right edge of the container cannot move owing to the anchors and . To change the sizes of the containers and the interval between them must be decreased. However a fixed size link is set between the containers and and the length of the fixed size link is maintained in layout calculation. Thus the sizes of the containers and are changed.

As a result the containers and cannot ensure sizes each optimal for the aspect ratio of data and finally become smaller than the optimal sizes frames and as shown in . In other words since the size of the link is fixed the containers and cannot achieve their optimal sizes in the range indicated by a chain line in each container exhibits the aspect ratio of data .

In this case as shown in a flexible size link is set between the containers and in the above example. In changing the sizes of the containers and the link size decreases to set the sizes of the containers and larger than those in the example of .

Hence a size optimal for the size of inserted data can be achieved or a container frame close to the size optimal size of inserted data can be set. shows the result of this layout. The flexible link in changes to a size represented by a flexible link as a result of layout calculation. In this case the containers and attain optimal sizes sizes corresponding to their data sizes .

A process when catalogue data having advertisement information field areas is output or previewed on a browser serving as a client will be explained.

The database DB comprises a content management table which manages access information for accessing content data master data formed from various contents such as merchandise information and advertisement information . The database also comprises a master data management table which manages master data formed from various contents such as merchandise information and advertisement information.

The database comprises an association management table which manages information of association between the content management table and the master data management table . The database further comprises a master data association management table which associates merchandise information and advertisement information managed by the master data management table .

The relationship between the database and a document document template having field areas according to the embodiment will be explained with reference to .

Reference numeral denotes an example of a document document template having at least a merchandise information field area and advertisement information field area as field areas. In this example three field areas are formed as merchandise information field areas. More specifically the merchandise information field areas are a field area for inserting merchandise name data as merchandise information a field area for inserting merchandise code data and a field area for inserting merchandise image data. The advertisement information field area is a field area advertisement area for inserting advertisement information.

The database shown in stores data for the field areas to . The database includes at least a merchandise information management table advertisement information management table and merchandise information advertisement information association management table .

The merchandise information management table and advertisement information management table are contained in the master data management table in . The merchandise information advertisement information association management table is contained in the master data association management table .

The merchandise information management table manages data to be inserted into the merchandise information field areas to . The merchandise information field area is associated with a key DATA A the merchandise information field area with a key DATA B and the merchandise information field area with a key DATA C .

The advertisement information management table manages data to be inserted into the advertisement information field area and is made up of keys to and the like.

The merchandise information advertisement information association management table associates the key of the advertisement information management table with the key or of the merchandise information management table . That is in the merchandise information advertisement information association management table associates an advertisement category key representing an advertisement category with a merchandise category key representing a merchandise category or a merchandise category key representing a merchandise code.

In the embodiment merchandise information and advertisement information serving as master data can be associated with each other via an operation window to be described later . Several examples of the associated state will be explained.

Assume that merchandise information and advertisement information in the following description contain merchandise master data representing information on a piece of merchandise and advertisement master data representing information on a single advertisement. Further merchandise information and advertisement information contain a merchandise category representing a plurality of merchandise master data belonging to the same category and an advertisement category representing a plurality of advertisement master data belonging to the same category.

An association process of associating merchandise information and advertisement information will be explained with reference to .

In step S it is determined whether to establish association from merchandise information to advertisement information. If association is to be established from merchandise information to advertisement information YES in step S the flow advances to step S to determine whether to establish association between categories. If association is to be established between categories YES in step S merchandise categories are searched for in step S. In step S a merchandise category is selected from the search results. In step S an advertisement category to be associated is selected.

If it is determined in step S that no association is to be established between categories NO in step S the flow advances to step S to search for merchandise master data. In step S merchandise master data is selected from the search results. In step S advertisement master data to be associated is selected.

If it is determined in step S that association is to be established from advertisement information to merchandise information NO in step S the flow advances to step S to determine whether to establish association between categories. If association is to be established between categories YES in step S the flow advances to step S to search for advertisement categories. In step S an advertisement category is selected from the search results. In step S a merchandise category to be associated is selected.

If it is determined in step S that no association is to be established between categories NO in step S the flow advances to step S to search for advertisement master data. In step S advertisement master data is selected from the search results. In step S merchandise master data to be associated is selected.

After the association between merchandise information and advertisement information is determined by the above process the priority order of advertisement information is set in step S. The priority order means e.g. an order to output advertisement information or the ratio at which an advertisement is output.

In step S the selected merchandise information and advertisement information are associated. The association information and priority order setting information are saved in the database . In step S the association information is transmitted to the image forming apparatus on the network.

Note that the association information and priority order setting information are set on the basis of an operation to an association window to be described later .

In step S merchandise information and advertisement information are acquired on the basis of association information.

In step S a document template is selected on the basis of the number of pieces of merchandise information and that of pieces of advertisement information acquired in step S. For example when two advertisement master data are associated with merchandise master data serving as merchandise information a document template having two advertisement information field areas is selected. This process may be performed by the server PC or available document templates may be displayed on the client PC to prompt the user to select one of them.

In step S the selected document template is opened. In steps Sand S a loop process of repeating the process of step S by the number of advertisement information field areas defined in the document template is executed. Details of the loop process will be explained with reference to .

In step S the server PC inserts the merchandise information and advertisement information into the document template and executes a dynamic layout according to the above described layout calculation method .

In this example a dynamic layout is executed simultaneously for both the merchandise information and advertisement information but execution of the dynamic layout is not limited to this. For example it is also possible to execute a dynamic layout for merchandise information and then execute a dynamic layout for advertisement information associated with the merchandise information in accordance with association information. When priority order is set for advertisement information a dynamic layout for the advertisement information is executed in accordance with the priority order.

In step S the document template is transmitted as a preview window to the client PC so that the document template catalogue data having advertisement information field areas after layout calculation can be previewed.

By the above process a document in which pieces of advertisement information are inserted into advertisement information field areas on the basis of merchandise information selected in the client PC is created in the server PC and previewed on the client PC .

In step S merchandise information is selected from the image forming apparatus . In step S the image forming apparatus acquires the merchandise information selected in step S and its association information and transmits them to the server PC . In step S the server PC acquires the merchandise information and association information which are transmitted from the image forming apparatus and acquires advertisement information associated with the merchandise information from the database .

In step S a document template is selected on the basis of the number of pieces of acquired merchandise information and that of pieces of acquired advertisement information. For example when two advertisement master data are associated with merchandise master data serving as merchandise information a document template having two advertisement information field areas is selected. This process may be performed by the server PC or available document templates may be displayed on the client PC to prompt the user to select one of them.

In step S the server PC opens the document template. In steps Sand S the server PC executes a loop process of repeating the process of step S by the number of advertisement information field areas defined in the document template. Details of the loop process will be explained with reference to .

In step S the server PC inserts the merchandise information and advertisement information into the document template and executes a dynamic layout according to the above described layout calculation method .

In this example a dynamic layout is executed simultaneously for both the merchandise information and advertisement information but execution of the dynamic layout is not limited to this. For example it is also possible to execute a dynamic layout for merchandise information and then execute a dynamic layout for advertisement information associated with the merchandise information in accordance with association information. When priority is set for advertisement information a dynamic layout for the advertisement information is executed in accordance with the priority order.

In step S the server PC transmits to the image forming apparatus a document template catalogue data having advertisement information field areas after layout calculation.

By the above process a document template catalogue data having advertisement areas is created in the server PC on the basis of the merchandise information selected from the image forming apparatus and output from the image forming apparatus .

An association window implemented by the user interface displays a menu title and guidance . Reference numeral denotes an image of merchandise master data to be associated. Reference numeral denotes information advertisement number advertisement title type and publisher representing the contents of advertisement master data to be associated. As the definitions of items representing these pieces of information the names of items and the number of items can be freely defined by setting the database.

Reference numeral denotes an area which displays a list of merchandise categories performance mid range PC entry level PC monitor and the like . A plurality of merchandise categories can be selected from the area . The item of a selected merchandise category i.e. an item in an area is inversely displayed. Reference numeral denotes a drop down list for setting priority order to insert advertisement information advertisement master data for a selected merchandise category.

As the priority order for example the order to insert advertisement information or the frequency at which advertisement information is inserted can be set. Display effects such as highlight and balloon can also be set in the drop down list . A button provides a function of associating advertisement master data and a merchandise category and saving priority order in the database . A button provides a function of restoring a previous window. A button provides a function of restoring a menu window.

Note that the association window is implemented on e.g. the client PC or server PC . The association window shown in is particularly a window for associating advertisement master data and a merchandise category. Needless to say an association window for associating merchandise information and advertisement information of another type e.g. associating an advertisement category and merchandise master data or associating advertisement master data and merchandise master data is similarly configured.

A merchandise category selection window displays a logotype and guidance . Buttons are used to select respective merchandise categories high end PC mid range PC low end PC monitor and the like . When an arbitrary one of the buttons is pressed the merchandise category selection window changes to a merchandise master data list selection window details will be described with reference to representing a list of merchandise master data in a corresponding merchandise category. A button provides a function of changing to a menu window.

Needless to say an advertisement category selection window similar to the merchandise category selection window is configured.

A merchandise master data list selection window displays the logotype and guidance . A list provides a function of displaying a list of merchandise master data belonging to a merchandise category selected in and allowing selection of a plurality of merchandise master data. A button provides a function of outputting catalogue data which is associated with merchandise master data selected from the list and has advertisement information field areas. A button provides a function of restoring a merchandise category selection window.

As a matter of course an advertisement master data selection window similar to the merchandise master data list selection window is configured.

A preview execution window displays a menu title to notify the user to confirm selection of merchandise information merchandise master data . Reference numeral denotes an image of selected merchandise master data. Reference numeral denotes an area representing the items and contents of the selected merchandise master data. In the area the names of items and the number of items can be changed by the configuration in .

A button provides a function of outputting as a preview catalogue data having advertisement information field areas for the selected merchandise master data. An area provides a function of restoring a previous window. An button provides a function of restoring a menu window.

The preview execution window shown in is especially a merchandise information window. Similar to this window an advertisement information window is configured.

An operation when data and images contents managed by various tables in the actual database are inserted into a document document template having merchandise information field areas and advertisement information field areas will be explained.

In an output result merchandise master data items and and content data are dynamically laid out. The items and and the content data are defined as containers field areas in the document template respectively. An optimal layout process is dynamically performed by the above described layout calculation method in accordance with the number of characters to be inserted into each container the size of contents and the settings of the document template.

Pieces of advertisement information and are inserted into an advertisement information field area . Also in the advertisement information field area items and are defined as containers field areas in the document template. An optimal layout process is dynamically performed by the above described layout calculation method in accordance with the number of characters to be inserted as advertisement information the size of contents and the settings of the document template.

In an output result merchandise master data items and and content data are dynamically laid out. The items and and the content data are defined as containers field areas in the document template respectively. An optimal layout process is dynamically performed by the above described layout calculation method in accordance with the number of characters to be inserted into each container the size of contents and the settings of the document template.

The output results in are different in the sizes of the containers and . In this example the containers and in are larger than the containers and in . This difference comes from the result of optimally dynamically laying out containers in accordance with the number of character data in the database and the size of contents.

Further pieces of advertisement information and are inserted into the advertisement information field area . Also in the advertisement information field area the items and are defined as containers field areas in the document template. An optimal layout process is dynamically performed by the above described layout calculation method in accordance with the number of characters to be inserted as advertisement information the size of contents and the settings of the document template.

In an output result merchandise master data items and and content data are dynamically laid out. The items and and the content data are defined as containers field areas in the document template respectively. An optimal layout process is dynamically performed by the above described layout calculation method in accordance with the number of characters to be inserted into each container the size of contents and the settings of the document template.

One advertisement information is defined in an advertisement information field area . Items and are defined as containers field areas . An optimal layout process is dynamically performed by the above described layout calculation method in accordance with the number of characters to be inserted as advertisement information the size of contents and the settings of the document template.

The output results in are different in the number of pieces of advertisement information in the advertisement information field area . More specifically in an optimal layout process is performed in order to insert the two pieces of advertisement information and . In an optimal layout process is performed in order to insert one advertisement information . The number of pieces of advertisement information in this case may be determined in accordance with the number of advertisement master data or advertisement categories associated with merchandise master data or merchandise categories.

In step S the number of pieces of advertisement information acquired in step S or S is recognized. In step S it is determined whether the number of pieces of advertisement information is one. If the number of pieces of advertisement information is one YES in step S the flow advances to step S to select a document template having one advertisement information field area.

If the number of pieces of advertisement information is not one NO in step S the flow advances to step S to determine whether the number of pieces of advertisement information is two. If the number of pieces of advertisement information is two YES in step S the flow advances to step S to select a document template having two advertisement information field areas.

If the number of pieces of advertisement information is not two NO in step S i.e. the number of pieces of advertisement information is three or more the flow advances to step S to select from the pieces of advertisement information two pieces of advertisement information which satisfy a predetermined condition. Then the flow advances to step S.

By the process in when one advertisement master data is associated with one merchandise master data a document template having one merchandise information field area and one advertisement information field area is selected.

This process can also cope with a case where there is only a document template having e.g. one or two advertisement information field areas smaller in number than e.g. three advertisement master data.

More specifically in the process of step S pieces of advertisement information by the maximum number e.g. two of advertisement information field areas of the document template are selected from three or more pieces of advertisement information which satisfy a predetermined condition. In step S a document template having the maximum number e.g. two of advertisement information field areas is selected for the pieces of selected advertisement information. After a document template is selected pieces of advertisement information by the maximum number of advertisement information field areas of the document template may be selected.

In the process of the number of pieces of advertisement information is one. When therefore one advertisement master data is associated with one merchandise master data a document template having one merchandise information field area and one advertisement information field area is selected.

However the present invention is not limited to this. For example the present invention can also be applied to a case where pieces of merchandise information exist. In this case the number of pieces of acquired merchandise information and that of pieces of advertisement information are recognized in step S. For example it is recognized that the number of pieces of merchandise information is two and that of pieces of advertisement information is two. In this case a document template having two merchandise information field areas and two advertisement information field areas is selected.

The predetermined condition for selecting advertisement information in step S includes various conditions. For example use log information of advertisement information may be separately managed and each advertisement information may be adaptively selected on the basis of the use log information so as to equally use each advertisement information. Alternatively for example priority order may be set for pieces of advertisement information and the advertisement information may be selected in accordance with the priority order.

As described above according to the embodiment merchandise information at least one of merchandise master data and a merchandise category and advertisement information at least one of advertisement master data and an advertisement category are associated with each other. A dynamic layout process for the merchandise information and its associated advertisement information is executed by e.g. the server PC.

As a result catalogue data having advertisement information field areas can be previewed on the client PC. By selecting merchandise information in the image forming apparatus a dynamic layout process for the merchandise information and its associated advertisement information can be executed by the server PC to output the process result.

Although the embodiment has described an example of dynamically laying out merchandise information and its associated advertisement information in a page the type of information is not limited to them. That is the gist of the present invention resides in that different types of information are associated with each other and dynamically laid out in the same page. Thus the present invention can be applied to pieces of information which are categorized into different types explicitly by the user and associated between the categories.

The present invention can be more generally expressed as a process of associating the first record belonging to the first information and the second record belonging to the second information and dynamically laying out the designated first record and its associated second record in the same page on the basis of the document template.

Note that the present invention can be applied to an apparatus comprising a single device or to system constituted by a plurality of devices.

Furthermore the invention can be implemented by supplying a software program which implements the functions of the foregoing embodiments directly or indirectly to a system or apparatus reading the supplied program code with a computer of the system or apparatus and then executing the program code. In this case so long as the system or apparatus has the functions of the program the mode of implementation need not rely upon a program.

Accordingly since the functions of the present invention are implemented by computer the program code installed in the computer also implements the present invention. In other words the claims of the present invention also cover a computer program for the purpose of implementing the functions of the present invention.

In this case so long as the system or apparatus has the functions of the program the program may be executed in any form such as an object code a program executed by an interpreter or scrip data supplied to an operating system.

Example of storage media that can be used for supplying the program are a floppy disk a hard disk an optical disk a magneto optical disk a CD ROM a CD R a CD RW a magnetic tape a non volatile type memory card a ROM and a DVD DVD ROM and a DVD R .

As for the method of supplying the program a client computer can be connected to a website on the Internet using a browser of the client computer and the computer program of the present invention or an automatically installable compressed file of the program can be downloaded to a recording medium such as a hard disk. Further the program of the present invention can be supplied by dividing the program code constituting the program into a plurality of files and downloading the files from different websites. In other words a WWW World Wide Web server that downloads to multiple users the program files that implement the functions of the present invention by computer is also covered by the claims of the present invention.

It is also possible to encrypt and store the program of the present invention on a storage medium such as a CD ROM distribute the storage medium to users allow users who meet certain requirements to download decryption key information from a website via the Internet and allow these users to decrypt the encrypted program by using the key information whereby the program is installed in the user computer.

Besides the cases where the aforementioned functions according to the embodiments are implemented by executing the read program by computer an operating system or the like running on the computer may perform all or a part of the actual processing so that the functions of the foregoing embodiments can be implemented by this processing.

Furthermore after the program read from the storage medium is written to a function expansion board inserted into the computer or to a memory provided in a function expansion unit connected to the computer a CPU or the like mounted on the function expansion board or function expansion unit performs all or a part of the actual processing so that the functions of the foregoing embodiments can be implemented by this processing.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2005 231172 filed Aug. 9 2005 which is hereby incorporated by reference herein in its entirety.

