---

title: Image forming apparatus, control method for image forming apparatus, image forming system, and storage medium
abstract: An image forming apparatus which communicates with an information processing apparatus includes a display unit which is used to input an instruction to cause the information processing apparatus to execute a dynamic layout function of dynamically determining a layout on the basis of template data so as to form an image by using template data including insertion data and layout information, a transmission unit which transmits, to the information processing apparatus, specifying information to be used when processing is performed by using the dynamic layout function, a reception unit which receives dynamically laid out data, and an output unit which outputs the received data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07924452&OS=07924452&RS=07924452
owner: Canon Kabushiki Kaisha
number: 07924452
owner_city: Tokyo
owner_country: JP
publication_date: 20060817
---
The present invention relates to a technique of constructing a user interface UI window in accordance with a user s purpose and forming an image by using a function unique to a multi function peripheral MFP and the function of a server application in accordance with an instruction from the UI.

Recently an application execution environment typified by a Java registered trademark has been provided for a multi function peripheral MFP to be also simply referred to as an image forming apparatus hereinafter . Developing programs which operate in the Java registered trademark environment makes it possible to create applications using the functions of an MFP. In general most of these applications are those called package applications in which window configurations and functions provided by MFPs are fixed.

When a solution linked with a server application which operates on a server capable of communicating with an MFP is to be provided for a user company it is difficult to flexibly satisfy the specifications required by the user by using a package application which provides fixed window configurations and functions.

Japanese Patent Laid Open No. 2000 298561 discloses a technique of downloading an application program for an MFP from a server and executing it. However the contents disclosed in Japanese Patent Laid Open No. 2000 298561 do not refer to the customization of an MFP application itself and hence it is difficult to provide an individual solution for a user s request.

A case of a solution obtained by linking an MFP with an application on a server is a pull type printing system in which an MFP acquires a file stored in a document management server or content server through a network and prints the file. Another case is a system in which a scanned document file created by scanning operation using an MFP is registered in a document management server or content server.

Assume that a brochure printing system to which pull type printing is applied is to be used. In this case an electric appliance distributor and travel agency which belong to different categories of business require brochure printing with different specifications. For example the electric appliance distributor is assumed to require specifications for printing brochures for each of products such as digital cameras whereas the travel agency is assumed to require specifications for brochures for each of destinations of travel. In such a case the UI of an MFP issues instructions to the MFP and a server application in accordance with operations which users want to directly see touch and process and hence it is difficult to satisfy a wide variety of specifications which are assumed to be required by the users with fixed window configurations.

Japanese Patent Laid Open No. 2000 196698 discloses a technique of registering the correspondence relationship between a printer and a scanner as a transfer pass protocol in a server in advance and distributing the protocol by downloading it into a multi function apparatus and the like. This reference also discloses a technique of displaying on an operation panel an icon for virtual copy corresponding to the combination of the printer and the scanner by using the transfer pass protocol.

According to the conventional technique an icon indicating a combination of an input device and an output device is designated to make a plurality of devices cooperate with each other thereby executing one service. In the above conventional technique however the functions of a plurality of designated devices are simply executed sequentially. That is the technique does not allow the user to make full use of various functions of external devices with which the image forming apparatus communicates and flexibly change or enhance the function of the image forming apparatus.

In addition conventionally it is necessary to design the layout of a form in accordance with a combination of insertion data and a template for every execution of a service. For this reason a desired output cannot be obtained by only simple instructions from the user through the image forming apparatus.

According to one aspect of the present invention it is an object to provide a mechanism of enhancing or customizing the function of an image forming apparatus by making full use of various functions of an external information processing apparatus with which the image forming apparatus communicates.

According to another aspect of the present invention it is another object to provide a mechanism of obtaining a desired output by only issuing simple instructions through the display screen of an image forming apparatus in cooperation with an external device having a dynamic layout function.

In order to achieve the above objects an image forming apparatus according to the present invention is characterized by mainly comprising the following arrangement.

In order to achieve the above described object according to an aspect of the present invention there is provided an image forming apparatus which communicates with an information processing apparatus comprising 

a display unit adapted to display on an operation unit a window for inputting an instruction to cause the information processing apparatus to execute a dynamic layout function of dynamically determining a layout on the basis of template data so as to form an image by using template data including insertion data and layout information 

a transmission unit adapted to transmit to the information processing apparatus specifying information to be used when processing is performed by using the dynamic layout function of the information processing apparatus in accordance with an instruction input through a window displayed by the display unit 

a reception unit adapted to receive data dynamically laid out in the information processing apparatus by using the specifying information transmitted by the transmission unit and

Moreover according to another aspect of the present invention there is provided an image forming apparatus which communicates with an information processing apparatus comprising 

an acquisition unit adapted to acquire configuration data in which information for the construction of a user interface is set 

a display unit adapted to display a window for inputting an instruction to execute image processing in which data processed by using a function of the image forming apparatus is processed by using a function of the information processing apparatus by processing the configuration data acquired by the acquisition unit 

an execution unit adapted to execute a function of the image forming apparatus in accordance with an instruction input through the window displayed by the display unit and

a transmission unit adapted to transmit to the information processing apparatus data acquired when the execution unit executes the function of the image forming apparatus and processing information to be used when the data is processed by using a function of the information processing apparatus.

A control method for an image forming apparatus according to the present invention is characterized by mainly comprising the following arrangement.

According to another aspect of the present invention there is provided a control method for an image forming apparatus which communicates with an information processing apparatus comprising steps of 

displaying on an operation unit a window for inputting an instruction to cause the information processing apparatus to execute a dynamic layout function of dynamically determining a layout on the basis of template data so as to form an image by using template data including insertion data and layout information 

transmitting to the information processing apparatus specifying information to be used when processing is performed by using the dynamic layout function of the information processing apparatus in accordance with an instruction input through a window displayed in the step of displaying 

receiving data dynamically laid out in the information processing apparatus by using the specifying information transmitted in the step of transmitting and

Moreover according to another aspect of the present invention there is provided a control method for an image forming apparatus which communicates with an information processing apparatus characterized by comprising steps of 

displaying a window for inputting an instruction to execute image processing in which data processed by using a function of the image forming apparatus is processed by using a function of the information processing apparatus by processing the configuration data acquired in the step of acquiring 

executing a function of the image forming apparatus in accordance with an instruction input through the window display in the step of displaying and

transmitting to the information processing apparatus data acquired in the step of executing by executing the function of the image forming apparatus and processing information to be used when the data is processed by using a function of the information processing apparatus.

An image forming system according to the present invention is characterized by mainly comprising the following arrangement.

According to another aspect of the present invention there is provided an image forming system including an information processing apparatus and an image forming apparatus which communicates with the information processing apparatus and can perform processing using a function of the information processing apparatus 

a display unit adapted to display on an operation unit a window for inputting an instruction to cause the information processing apparatus to execute a dynamic layout function of dynamically determining a layout on the basis of template data so as to form an image by using template data including insertion data and layout information and

a transmission unit adapted to transmit to the information processing apparatus specifying information to be used when processing is performed by using the dynamic layout function of the information processing apparatus in accordance with an instruction input through a window displayed by the display unit 

a specifying information reception unit adapted to receive the specifying information transmitted by the transmission unit 

a dynamic layout execution unit adapted to execute dynamic layout by using the specifying information and

a dynamic layout data transmission unit adapted to transmit data dynamically laid out by the dynamic layout execution unit to the image forming apparatus and

a reception unit adapted to receive the data transmitted from the dynamic layout data transmission unit and

Moreover according to another aspect of the present invention there is provided an image forming system including an information processing apparatus and an image forming apparatus which communicates with the information processing apparatus and can perform processing using a function of the information processing apparatus 

an acquisition unit adapted to acquire configuration data in which information for the construction of a user interface is set 

a display unit adapted to display a window for inputting an instruction to execute image processing in which data processed by using a function of the image forming apparatus is processed by using a function of the information processing apparatus by processing the configuration data acquired by the acquisition unit 

an execution unit adapted to execute a function of the image forming apparatus in accordance with an instruction input through the window displayed by the display unit and

a transmission unit adapted to transmit to the information processing apparatus data acquired when the execution unit executes the function of the image forming apparatus and processing information to be used when the data is processed by using a function of the information processing apparatus 

a reception unit adapted to receive the data transmitted from the transmission unit and the processing information and

an information processing function execution unit adapted to execute a function of the information processing apparatus on the basis of the data and processing information received by the reception unit and

the information processing function executing unit registers the transmitted data in a storage unit when the processing information includes control information for registration of data input by a scanner function of the image forming apparatus.

According to the present invention a user interface window corresponding to a user s purpose is constructed and an image can be formed by using a function unique to a multi function peripheral and the function of a server application in accordance with settings from a user interface window.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings .

Preferred embodiments of the present invention will now be described in detail in accordance with the accompanying drawings.

The first preferred embodiment of the present invention will be described below with reference to the accompanying drawings. This embodiment will exemplify pull type printing which is realized by making an information processing apparatus server computer cooperate with an image forming apparatus MFP Multi Function Peripheral .

Reference numeral denotes a client PC which is connected to the server computer and is used by an operator to perform processing. For example the operator can designate items e.g. a product designation box a spot advertisement box a print quality box and a document type box for constructing a UI to be provided for the MFP in advance through the client PC . A server application on the server computer can create a UI configuration setting file based on the items designated by the client PC and register the file in an HDD of the server computer .

Note that designation of items for constructing a UI and creation and registration of a UI configuration setting file can be performed by using the server computer .

In step S the server computer assigns the UI configuration setting file registered in step S to the MFP .

In step S the server computer registers the server address of the server computer itself in the MFP in which the application operates.

In step S the application in the MFP transmits a UI configuration setting file acquisition request to the server computer for the server address registered in step S.

In step S the server computer reads out the UI configuration file assigned to the MFP and the application in the MFP downloads the UI configuration setting file from the server computer .

In step S the application stores the downloaded UI configurations setting file in the HDD and analyzes the contents of the UI configuration setting file. A UI is then constructed on the basis of the analysis result S .

In accordance with the same sequence the server computer can register an arbitrary UI configuration setting file in another MFP and assign it thereto. In addition another MFP can construct a user interface window corresponding to a user purpose in accordance with the individually assigned UI configuration setting file S .

Reference numeral denotes a control button for designating a print output based on the designation information file created by the server computer . When the control button is pressed data corresponding to a product or the like designated by each designation box or is sent as an argument to the server computer . In this case each data sent to the server computer is catalog creation information for creating a catalog. The catalog created by the server computer is downloaded into the MFP and printing processing is executed under the control of the CPU . The details of pull type printing processing executed by the server computer and the MFP in cooperation with each other will be described later with reference to .

UI configuration information in the Components node is for example identification information which identifies a panel element Panel forming a UI display in . Reference numeral denotes attribute information for concretely specifying the display position size and the like of the panel. The application can construct a UI by controlling the display of UI configuration elements on the basis of the identification information and the attribute information corresponding to the identification information under the control of the CPU .

In the XML identification information List is described as a constituent element for the formation of a UI for a product designation box and the display position size and the like of a product designation box are specified by corresponding attribute information . The application can construct a UI by controlling the display of the product designation box in the UI under the CPU on the basis of the identification information List and the attribute information .

In addition in the XML identification information List is described as a constituent element for the formation of a UI for a spot advertisement designation box and the display position size and the like of a spot advertisement designation box are specified by corresponding attribute information . The application can construct a UI by controlling the display of the spot advertisement designation box in the UI under the CPU on the basis of the identification information List and the attribute information .

Furthermore identification information Choice is described as a constituent element for the formation of a UI for a print quality designation box and the display position size and the like of a print quality designation box are specified by corresponding attribute information . The application can construct a UI by controlling the display of the print quality designation box in the UI under the CPU on the basis of the identification information Choice and the attribute information .

Identification information Button is described as a constituent element of a UI which is a button element for designating the start of printing and the display position size and the like of a button element are specified by corresponding attribute information . In label information information to be displayed in addition to the button element is described. The application can construct a UI by controlling the display of the button element in the UI under the CPU on the basis of the identification information Button attribute information and label information .

Note that in the display of each constituent element reference information such as a text to be displayed is described as a DataRef element. Assume that the application can construct a UI by using reference information such as a text to be displayed in addition to the above identification information and attribute information.

An XML in describes the contents of reference information DataRef element in the XML in . A root node DataSource includes a DataSet element and Data elements and . The Data elements and described in the DataSet element are referred to as display data for the construction of a UI on the basis of the reference data in the XML .

In the XML in reference numeral denotes a line on which an operation Target Action to be executed when the control button is pressed when a control event occurs is described. As an operation to be executed at the occurrence of a control event act001 is described on the line . When the control button is pressed and a control event occurs the attribute id act001 of an action element Action in an ActionMapping node is referred to. The attribute id act001 defines a call action name name and the attribute type of the action . In this case information which can be used as the attribute type of an action includes for example the function name of a program module and a URI.

An action element Action further includes an Arguments node and allows data selected or input by the user through the display of each designation box to be provided as an argument and .

When for example the user designates the item of DIGITAL C55 in the product designation box data 0622A001 corresponding to DIGITAL C55 is provided as an argument in the XML in . The application reads in this argument. When a transmission instruction is issued the corresponding data is then transmitted to the dynamic layout engine of the server computer.

In addition the UI configuration setting file is not limited to an XML form and may be described in the form of for example a text file binary file or data stream.

When the UI is operated by the user data necessary to call a function which corresponds to the operation and is unique to the MFP is transferred between the Components node and the ActionMapping node in the UI configuration setting file. The data necessary to call the function of the server application which corresponds to the operation of the UI is transferred between the MFP and the server computer . This makes it possible to control the function of the MFP and the function cooperated with the server application.

In step S a UI configuration setting file reception analysis unit receives the UI configuration setting file downloaded from the server computer and analyzes its contents.

In step S the UI configuration setting file reception analysis unit stores the data of the analyzed UI configuration setting file in storage areas and . The cache data of a set value attribute information or the like associated with each constituent element control for the construction of a UI is stored in the storage area . The mapping data of an action designated from the UI is stored in the storage area .

In step S a UI construction unit refers to the data identification information attribute information and the like in the file storage system and generates each constituent element each control for the construction of a UI thereby constructing a UI S . In this case each control is generated as for example a constituent element or shown in . Referring to n controls Control . . . are generated as constituent elements of the UI .

When each constituent element controls Control . . . of the constructed UI is operated and set S an event a command corresponding to the operation and setting is generated from the operated and set control element. This event is then notified to an event handling unit S .

The event handling unit refers to the mapping data in the storage area and calls an action assigned to the corresponding control operation setting . Assume that the event handling unit can select a function for executing an action corresponding to a generated event and call for example function modules and in the application .

For example the function module can be configured to use a function of the MFP through an API or a function provided by a server application.

In this case the functions of the MFP include a printing function a facsimile function a scanning function and the like. Assigning the respective functions to the function modules and makes it possible to selectively use the functions of the MFP .

The functions of a server application cooperated with the MFP include for example a function of searching for data designated through the UI creating a data layout and a file of laid out data as a print target and downloading the file. The functions of a server application cooperated with the scanning function of the MFP includes a function associated with registration processing of data input by the scanning unit .

An example of pull type printing using the printing function of the MFP and the data search layout file creation function of the server application starting from action calling will be described with reference to the sequence chart of by taking the UI in as an example.

In step S the user designates the model name of a digital camera a spot advertisement and a print quality by controls the product designation box spot advertisement designation box and print quality designation box using the UI . When the start of printing is designated from the control button an event is generated and a corresponding action is selected from the function modules and by referring to the mapping data of the action.

In step S the selected function module is called and processing is started. Reference numeral in denotes an example of a request which is notified to the function module and is expressed in XML. A root node Action includes a name Name node and an argument Arguments node . A function module can be called by assigning argument data to each argument element to following the argument node . The content of each argument element to can be identified by an attribute key in the argument element. This makes it possible to process data associated with a plurality of argument elements at once. The function module analyzes a call request for an action generates a content file creation request function request information and transmits the request to the server application S . The content of the content file creation request is based on the content of the request notified to the function module

Reference numeral in denotes an example of a content file creation request expressed in XML. A root node Request includes a name Name node and an argument Arguments node . Argument data is assigned to each argument in the argument node .

Argument data is data selected by a customized UI. This data is transferred to the server application. The server application executes data retrieval layout file creation function by using the transferred argument data. Consider a case wherein for example the model name DIGITAL C55 is selected and recommended printer is selected as the designation of a spot advertisement in . As described above argument 0622A001 and spot advertisement type AdvPrinter are prepared as specific information in accordance with the above designation through the operation panel. When the transmission button on the operation panel is pressed the application transmits a prepared argument to the server computer to transfer it to the layout engine.

On the basis of these data the server computer calls the layout engine and automatically creates a file in which character data image data and the like are laid out S . The details of step S will be described with reference to .

This file can also use PDF Portable Document Format as a format for electronic documents. In addition as an electronic document format a page description language PDL or the like can be used. The application transmits a file acquisition request to the server application S and downloads the file created by the server application S . The application calls the function of the MFP through the API or the like and performs PDL rasterization processing and printing processing S and S . In this case a print quality print quality dpi provided as argument data of an XML is used and the printing function of the MFP is controlled. In the case shown in since 600 dpi is set as a print quality the printing function is controlled on the basis of this designation. When all the processing starting from action calling is complete the completion of the processing is displayed in the UI. At this time the log of the processing may be recorded instead of display S . Upon completion of the display or recording of the result the series of action processing is complete S .

The above description has exemplified the creation of a dynamic insertion document comprising product data and advertisement data using the layout engine. However the application range of the present invention includes the use of the arbitrary providing function of the server computer from the MFP and is not limited to this example.

In steps S S and S described above the security of information can be protected by encrypting communication between the MFP and the server computer using an encryption means unit .

Each application of the MFP can construct a user interface window suitable for the specifications required by the user on the basis of the contents of a UI configuration setting file corresponding to a user s purpose. An example of a UI in a display form different from that of the UI shown in will be described with reference to .

When the button control next in the UI is clicked an event a command corresponding to the clicking operation is generated. The attribute id act001 of an action element Action in the ActionMapping node described in a Target Action is referred to. In this case the attribute and transition destination of the action element are respectively described as forward window transition and panel02 next UI panel . The identification information of panel02 is searched from the UI configuration information and the UI in is constructed on the basis of the attribute information of a corresponding product list and reference information .

An XML in is designed to describe the contents of reference information DataRef element in the XML in . A root node DataSource includes a DataSet element and Data elements and . Data to described in a data set are based on reference data in the XML and are referred to as display data for the construction of a UI.

In addition the application retrieves data to of a product category matching the item designated by the user from the reference information application retrieves data to associated with panel02 and displays the retrieved data in a product designation box .

As shown in a user interface window can be constructed in a display form suitable for the specifications required by the user by changing the contents of the UI configuration setting file. When the button print in is clicked an event is generated. The flow of processing then shifts to printing processing similar to that in the case of the print in described above.

According to this embodiment a user interface window can be constructed in accordance with a user s purpose and an image can be formed by using a function unique to the MFP and the function of a server application upon setting through the user interface window.

The second embodiment of the present invention will be described next with reference to . In this embodiment a server application registers a scanned document file obtained by using the scanning function of an MFP in a file storage system functioning as a storage means unit . A description of contents which are associated with system configurations the logical configuration of an application and the like and are redundant to those in the first embodiment will be omitted.

The server computer then performs the registration processing designated by a UI to register the file as the data of a designated document type in the file storage system functioning as a storage means unit .

In the UI in reference numeral denotes a display section unit capable of displaying an application name and selecting an application. When the display section unit is selected for example applications which can be selected are displayed in a pull down menu. Applications can be switched with each other by operating the display section unit . Reference numeral denotes a frame of the UI which is displayed on the display touch panel unit .

Reference numeral denotes a document type designation box a server registration processing designation box a scanning resolution designation box a designation box for determining whether to perform confirmation in a previous window and a control button for the registration of a scanned input document file in the server computer.

Obviously the gist of the present invention is not limited to these display contents. Assume that each application in the MFP can construct a user interface window suitable for the specifications required by a user on the basis of the contents of a UI configuration setting file corresponding to a user s purpose.

The application in the MFP can construct a UI by controlling the display of the constituent elements of the UI on the basis of identification information which identifies each constituent element and attribute information corresponding to the identification information.

In an XML in reference information in the XML in a root note DataSource as a DataRef element includes a DataSet element and Data elements and .

Buttons are defined as elements. Elements include element names and attributes. Each element can be accompanied by a sub element. First of all DataSet is an element name. DataSet has the attribute id . A value can be assigned to the attribute. In id id ds001 means that the attribute id defined as additional information of the element name DataSet takes the value id ds001 . In addition Data is defined as a sub element. Data further has a Label element and a Value element as sub elements. The character string set in the Label element as a result of analysis of XML data is used as the display name of a button. The Value element has a key as an attribute. The Key attribute is used to designate a document type. If for example a receipt button is pressed the character string Receipt is acquired as a Key attribute by the MFP . The MFP may transmit this acquired character string to the server computer in accordance with a transmission instruction.

An element having the attribute id ds0102 of the Dataset element will be further described. This is associated with the server registration processing designation box for designating how data read in by the scanner is processed by the server computer. When for example an electronic signature element of Label is analyzed a button including the character string of the electronic signature is displayed. The value save option is set for the attribute key of the value element. In addition eSignature is set as the content of the value element. When the transmission button is pressed while the electronic signature button is pressed once the character string eSignature is transmitted as the value of save option to the server computer. If the value of save option added to the data is eSignature the server computer performs electronic signature processing. If the value of save option is Time Stamp the server computer performs time stamp processing.

The third DataSet id attribute is id0203 will be described next. As in the above case a Label element is displayed as a button. The content of selected Value numeral information selected from 600 and 200 is acquired as a selected resolution by the MFP . If for example the 300 dpi button is pressed the MFP performs scanning processing for a document at a resolution of 300 dpi.

A concrete explanation of a UI configuration setting file will be omitted because it is redundant with the explanation made with reference to .

An example of using the scanning function of the MFP and the content registration function of the server application starting from a call for an action will be described with reference to the sequence chart of by taking the UI in as an example.

In step S the user designates the document type the server registration processing designation box the scanning resolution designation box and the designation box of the confirmation on a preview image by using the UI . When the scanning registration is designated with the control button an event is generated and a corresponding action is selected from function modules and by referring to the mapping data of the action.

In step S the selected function module the function module corresponding to the scanning function in this case is called and the processing is started. Reference numeral in denotes an example of a request which is notified to the function module and expressed in XML. A root node Action includes a name Name node and an argument Arguments node . A function module can be called by assigning argument data to each argument element to following the argument node . The content of each argument element to can be identified by an attribute key in the argument element. This makes it possible to process data associated with a plurality of argument elements at once. The function module analyzes a call request for an action and controls the function of the MFP through an API or the like so as to scan input an original at a designated resolution. The function module creates a scanned document file on the basis of the scanned input data S .

In step S if confirmation in a preview window is designated the application displays the preview window on the display touch panel unit . In addition the application displays a confirmation dialog on the display touch panel unit as needed.

In step S the function module analyzes a call request for an action generates a scanned document registration request function request information and transmits the request to the server application S . The content of the scanned document registration request is based on the content of the request notified to the function module

The function module transmits the scanned document registration request to the server application on the server computer and uploads the scanned document file. In this case reference numeral denotes an example of a scanned document registration request expressed in XML. A root node Request includes a name Name node and an argument Arguments node . Argument data is assigned to each argument in the argument node .

Argument data is data selected through a customized UI. This data is transferred to the server application. The server application executes a function associated with the registration of contents by using the transferred argument data.

The server application analyzes a scanned document registration request and detects whether registration processing save option an electronic signature eSignature and a time stamp TimeStamp are designated. Since registration processing an electronic signature and a time stamp are designated in the scanned document registration request the server application executes electronic signal processing time stamp processing and registration processing for the scanned document file in accordance with the designation.

That is the server application executes the electronic signature processing in step S time stamp processing in step S and registration processing with respect to a document DB in step S. When the file is to be registered in the document DB the server application registers it as a receipt Receipt as a document type document type designated by argument data.

In step S when the registration processing by the server application is complete the processing result is notified to the application of the MFP .

In step S when all the processing starting from action calling is complete the application displays the processing result in the UI. In this case the application can leave a record of the processing result so as to allow the user to check the log as well as displaying the result in the UI.

In steps S and S described above the security of information can be protected by encrypting communication between the MFP and the server computer using an encryption means unit .

According to this embodiment a user interface window can be constructed in accordance with a user s purpose and an image can be formed by using a function unique to a multi function peripheral and the function of a server application in accordance with settings from the user interface window.

The MFP which communicates with the server computer displays on the operation unit a window for allowing the user to input an instruction to cause the information processing apparatus to execute a dynamic layout function. In this case the dynamic layout function is for example a function of dynamically determining a layout based on document template data including insertion data and layout information for laying out the insertion data so as to form an image by merging the document template.

In accordance with an instruction input through a window displayed on the operation unit display touch panel unit specifying information to be used when processing is performed by using the dynamic layout function of the server computer is transmitted to the server computer . As specifying information a product code and a spot advertisement type have been described.

The server computer receives the data dynamically laid out by using the specifying information. The MFP outputs the received data by using the print engine.

The MFP acquires configuration data in which information for the construction of a user interface is set. The MFP then analyzes the configuration data. The operation unit of the MFP displays a window for inputting an instruction to execute dynamic layout processing.

The MFP is an apparatus which can input specifying information for specifying insertion data and template data. The MFP then transmits the input specifying information.

The MFP receives the data dynamically laid out by the server computer on the basis of the insertion data and template data specified by the transmitted specifying information. The MFP prints out the received data through the print engine.

The MFP which communicates with the server computer may be configured as follows. The MFP may comprise a network interface unit which acquires configuration data in which information for the construction of a user interface is set. The configuration data e.g. the data shown in A and B acquired through the network interface unit is processed to display on an operation unit display touch panel unit a window for inputting an instruction to execute image processing in which the data processed by using the scanner function of the MFP is processed by using the function of the server computer . A CPU executes scanning processing in accordance with the instruction input through the window displayed on the operation unit. The MFP also comprises a network interface unit which transmits to the server computer the data obtained when the CPU executes the scanner function of the MFP and processing information a scanned document registration request which is used to process the data by using the function of the server computer .

The display touch panel unit analyzes the configuration data acquired by the MFP using the network interface unit and displays a window for inputting an instruction to execute image processing for the data input by using the scanner of the MFP by executing a program installed in the server computer .

In addition the scanner function of the MFP is executed under the control of the CPU in accordance with an instruction input through the window displayed by the display touch panel unit .

The data input when the CPU executes the scanner function and a parameter or command scanned document registration request used to perform image processing for the data by using a program installed in the server computer are transmitted through the network interface unit . The server computer receives the transmitted scanned document registration request .

The server computer may provide time stamp processing for adding information indicating the time. In addition an instruction window for issuing an instruction to execute time stamp processing in the server computer may be displayed on the operation unit of the MFP .

The processing of the scanner function of the image forming apparatus may be executed under the control of the CPU in accordance with an instruction to operate the scanner which is issued through the display touch panel unit .

The transmission means unit transmits to the server computer processing information the scanned document registration request including the time stamp instruction including control information set by the operation of the user interface displayed on the display touch panel unit . The server computer may be caused to perform time stamp processing for the image data input by the scanner function of the MFP and register the resultant data.

The object of the present invention is achieved even by supplying a storage medium storing software program codes for implementing the functions of the above first and second embodiments to a system or apparatus and causing the computer or a CPU or an MPU of the system or apparatus to read out and execute the program codes stored in the storage medium.

In this case the program codes read out from the storage medium implement the functions of the above embodiments by themselves and the storage medium storing the program codes constitutes the present invention.

As a storage medium for supplying the program codes a flexible disk a hard disk an optical disk a magneto optical disk a CD ROM a CD R a magnetic tape a nonvolatile memory card a ROM or the like can be used.

The functions of the described embodiments are implemented not only when the readout program codes are executed by the computer but also when the operating system running on the computer performs part or all of actual processing on the basis of the instructions of the program codes.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2005 246431 filed on Aug. 26 2005 which is hereby incorporated by reference herein in its entirety.

