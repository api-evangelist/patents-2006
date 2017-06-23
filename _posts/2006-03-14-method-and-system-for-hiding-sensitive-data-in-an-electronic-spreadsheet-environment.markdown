---

title: Method and system for hiding sensitive data in an electronic spreadsheet environment
abstract: A method and system for hiding sensitive data in an electronic spreadsheet. A first output equation expresses output data as a function of at least one first input data and at least one first intermediary result. The at least one first and second intermediary result are assigned as content of intermediary cells of the spreadsheet. A second output equation is generated and expresses the output data as a function of a subset of the at least one first and second input data with no functional dependence on the plurality of intermediary results. Generation of the second output equation utilizes the first output equation and the plurality of first intermediary equations. The output data of the second output equation is assigned as content of an output cell of the spreadsheet. The content of the intermediary cells is removed, resulting in the plurality of intermediary results not being identifiable in the spreadsheet.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07743316&OS=07743316&RS=07743316
owner: International Business Machines Corporation
number: 07743316
owner_city: Armonk
owner_country: US
publication_date: 20060314
---
The present invention is directed to the field of electronic spreadsheets and more particularly to a method system and computer program for hiding sensitive data within models in an electronic spreadsheet environment.

Before computers numerical analyses particularly financial ones were usually prepared on an accountant s columnar pad or spreadsheet with pencil and calculator in hand. By organizing data into columns and rows spreadsheets afford the rapid assimilation of information by a reader. The task of preparing a spreadsheet on paper however is not quite so fast. Instead the process tends to be very slow as each entry must be tediously calculated and entered into the spreadsheet. Manually prepared spreadsheets are also prone to errors. Hence preparation of spreadsheets by hand is slow tedious and unreliable.

With the advent of microcomputers a solution was forthcoming in the form of electronic spreadsheets. Better known simply as spreadsheets these software programs provide a computerized replacement for the traditional financial modeling tools the accountant s columnar pad pencil and calculator. In some regards spreadsheet programs are to those tools what word processors are to typewriters. Spreadsheets offer dramatic improvements in ease of creating editing and using financial models.

A typical spreadsheet program configures the memory of a computer to resemble the column row or grid format of an accountant s columnar pad thus providing a visible calculator for a user. Because this pad exists dynamically in the computer s memory however it differs from paper pads in several important ways. Locations in the electronic spreadsheet for example must be communicated to the computer in a format which it can understand. A common scheme for accomplishing this is to assign a number to each row in a spreadsheet and a letter to each column. To reference a location at column A and row 1 i.e. the upper left hand corner the user types in A1 . In this manner the spreadsheet defines an addressable storage location or cell at each intersection of a row with a column.

Data entry into an electronic spreadsheet occurs in much the same manner that information would be entered on an accountant s pad. After a screen cursor is positioned at a desired location the user can enter alphanumeric information. Besides holding text and numeric information however spreadsheet cells can store special instructions or formulas specifying calculations to be performed on the numbers stored in spreadsheet cells. In this fashion cell references can serve as variables in an equation thereby allowing precise mathematical relationships to be defined between cells. The structure and operation of a spreadsheet program including advanced functions such as functions and macros are documented in the technical trade and patent literature. For an overview see e.g. Cobb S. 2 Borland OsborneIMcGraw Mll 1990 and LeBlond G. and Cobb D. 1 2 3 Que corp. 1985. The disclosures of each of the foregoing are hereby incorporated by reference.

Electronic spreadsheets offer many advantages over their paper counterparts. For one electronic spreadsheets are much larger i.e. hold more information than their paper counterparts electronic spreadsheets having thousands or even millions of cells are not uncommon. Spreadsheet programs also allow users to perform what if scenarios. After a set of computational relationships has been entered into a worksheet thanks to imbedded formulas for instance the spread of information can be recalculated using different sets of assumptions with the results of each recalculation appearing almost instantaneously. Performing this operation manually with paper and pencil would require the recalculation of every relationship in the model with each change made. Electronic spreadsheet systems are well suited to solve what if problems that is changing an input and seeing what happens to an output.

Electronic spreadsheets are commonly used for implementing costing and pricing tools typically for service oriented offerings. Such tools are simply an implementation of a model either a costing model or a pricing model featuring a set of output data based on a set of input data.

Costing pricing models can be quite complex and the resulting spreadsheet tool can also be complex involving a large number of formulas spreading across different sheets. Such formulas involve intermediary results themselves involving either input data or other intermediary data. If a costing pricing tool spreadsheet is disclosed to a person this person can easily reverse engineer this tool to determine all the different intermediary results which are part of the model. Such intermediary results can contain confidential information that the costing pricing tool spreadsheet author does not want to share with third parties. Nevertheless the costing pricing tool spreadsheet author may want to share a tool which produces the output data when fed with the input data.

A typical example corresponding to this case is the following. Assume that a company X is currently delivering an offering through direct sales channel and wants to rely on indirect channels like business partners to reach a wider opportunity base. If an internal cost price model is disclosed to a business partner then this business partner will easily access information that this company X refuses to disclose. On the contrary every effort must be done by the company X to give to this business partner all the relevant tools streamlining the sales cycle such as a costing pricing tool.

This dilemma cannot be solved with conventional spreadsheet tools since spreadsheet protection can easily be broken by cracks available on the Internet.

The present invention provides a computer implemented method for hiding sensitive data in an electronic spreadsheet wherein a first output equation expresses an output data as a function of at least one first input data and at least one first intermediary result wherein a plurality of first intermediary equations relates the at least one first intermediary result to at least one second intermediary result and at least one second input data wherein a plurality of input data denotes the at least one first input data and the at least one second input data collectively wherein a plurality of intermediary results denote the at least one first intermediary result and the at least one second intermediary result collectively said method comprising 

generating a second output equation that expresses the output data as a function of a subset of the plurality of input data with no functional dependence on the plurality of intermediary results said generating the second output equation utilizing the first output equation and the plurality of first intermediary equations 

assigning the output data of the second output equation as content of an output cell of the spreadsheet and

after said assigning the output data removing the content of the intermediary cells resulting in the plurality of intermediary results not being identifiable in the spreadsheet.

The present invention provides a computer program stored in a memory of a computer system said computer program comprising instructions that when executed by a processor of a computer system implement a method for hiding sensitive data in an electronic spreadsheet wherein a first output equation expresses an output data as a function of at least one first input data and at least one first intermediary result wherein a plurality of first intermediary equations relates the at least one first intermediary result to at least one second intermediary result and at least one second input data wherein a plurality of input data denotes the at least one first input data and the at least one second input data collectively wherein a plurality of intermediary results denote the at least one first intermediary result and the at least one second intermediary result collectively said method comprising 

generating a second output equation that expresses the output data as a function of a subset of the plurality of input data with no functional dependence on the plurality of intermediary results said generating the second output equation utilizing the first output equation and the plurality of first intermediary equations 

assigning the output data of the second output equation as content of an output cell of the spreadsheet and

after said assigning the output data removing the content of the intermediary cells resulting in the plurality of intermediary results not being identifiable in the spreadsheet.

The present invention provides a computer system comprising a processor and a memory coupled to the processor said memory containing instructions that when executed by the processor implement a method for hiding sensitive data in an electronic spreadsheet wherein a first output equation expresses an output data as a function of at least one first input data and at least one first intermediary result wherein a plurality of first intermediary equations relates the at least one first intermediary result to at least one second intermediary result and at least one second input data wherein a plurality of input data denotes the at least one first input data and the at least one second input data collectively wherein a plurality of intermediary results denote the at least one first intermediary result and the at least one second intermediary result collectively said method comprising 

generating a second output equation that expresses the output data as a function of a subset of the plurality of input data with no functional dependence on the plurality of intermediary results said generating the second output equation utilizing the first output equation and the plurality of first intermediary equations 

assigning the output data of the second output equation as content of an output cell of the spreadsheet and

after said assigning the output data removing the content of the intermediary cells resulting in the plurality of intermediary results not being identifiable in the spreadsheet.

The following description is presented to enable one or ordinary skill in the art to make and use the invention and is provided in the context of a patent application and its requirements. Various modifications to the preferred embodiment and the generic principles and features described herein will be readily apparent to those skilled in the art. Thus the present invention is not intended to be limited to the embodiment shown but is to be accorded the widest scope consistent with the principles and features described herein.

The method and system of the present invention provides within an electronic spreadsheet a tool implementing a costing pricing model giving to the tool user a limited visibility on the model internals while maintaining full control of all the parameters including the model data for the tool author.

The method and system of the present invention specifies within an electronic spreadsheet the cells containing either an output data or a scope data or a model data.

The method and system of the present invention builds an internal table representing a sequence of intermediary results establishing a set of hierarchical relationships between the output data and both the scope and model data.

The method and system of the present invention establishes a relationship tying directly the output data from the scope and model data.

The method and system of the present invention establishes a relationship tying directly the output data from the scope data and from the not hidden model data.

The method and system of the present invention removes cells referencing either intermediary results or hidden model data so that the resulting electronic spreadsheet file only comprises the output data the scope data and the not hidden model data.

As shown in the present invention may be embodied on a computer system comprising a central processor a main memory an input output controller a keyboard a pointing device e.g. mouse track ball pen device or the like a display device and a mass storage e.g. hard disk . Additional input output devices such as a printing device may be included in the system as desired. As illustrated the various components of the system communicate through a system bus or similar architecture.

Illustrated in a computer software system is provided for directing the operation of the computer system . Software system which is stored in system memory and on disk memory includes a kernel or operating system and a shell or interface . One or more application programs such as application software may be loaded i.e. transferred from storage into memory for execution by the system . The system receives user commands and data through user interface these inputs may then be acted upon by the system in accordance with instructions from operating module and or application module . The interface which may be a graphical user interface GUI also serves to display results whereupon the user may supply additional inputs or terminate the session. In one embodiment operating system and interface are Microsoft Win95 available from Microsoft Corporation of Redmond Wash. Application module on the other hand includes a spreadsheet notebook of the present invention as described in further detail herein below.

The following description will focus on the embodiments of the present invention which are embodied in spreadsheet applications operative in the Microsoft Windows environment. The present invention however is not limited to any particular application or any particular environment. Instead those skilled in the art will find that the system and methods of the present invention may be advantageously applied to a variety of system and application software including database management systems word processors and the like. Moreover the present invention may be embodied on a variety of different platforms including Macintosh UNIX NextStep and the like. Therefore the description of the exemplary embodiments which follows is for purposes of illustration and not limitation.

Referring now to the system includes a windowing interface or workspace . Window is a rectangular graphical user interface GUI for display on screen additional windowing elements may be displayed in various sizes and formats e.g. tiled or cascaded as desired. At the top of window is a menu bar with a plurality of user command choices each of which may invoke additional submenus and software tools for use with application objects. Window includes a client area for displaying and manipulating screen objects such as graphic object and text object . In essence the client area is a workspace or view port for the user to interact with data objects which reside within the computer system .

Windowing interface includes a screen cursor or pointer for selecting and otherwise invoking screen objects of interest. In response to user movement signals from the pointing device the cursor floats i.e. freely moves across the screen to a desired screen location. During or after cursor movement the user may generate user event signals e.g. mouse button clicks and drags for selecting and manipulating objects as is known in the art. For example Window may be closed resized or scrolled by clicking selecting screen components and respectively.

In one embodiment screen cursor is controlled with a mouse device. Single button double button or triple button mouse devices are available from a variety of vendors including Apple Computer of Cupertino Calif. Microsoft Corporation of Redmond Wash. and Logitech Corporation of Fremont Calif. respectively. The screen cursor control device may be a two button mouse device including both right and left mouse buttons. 

Programming techniques and operations for mouse devices are well documented in the programming and hardware literature see e.g. Microsoft Press 1989. The general construction and operation of a GUI event driven system such as Windows is also known in the art see e.g. Petzold C. Second Edition Microsoft Press 1990. The disclosures of each are hereby incorporated by reference.

Shown in a spreadsheet notebook interface of the present invention will now be described The spreadsheet notebook or workbook of the present invention includes a notebook workspace for receiving processing and presenting information including alphanumeric as well as graphic information. Notebook workspace includes a menu bar a toolbar a current cell indicator an input line a status line and a notebook window . The menu bar displays and invokes in response to user inputs a main level of user commands. Menu also invokes additional pull down menus as is known in windowing applications. Input line accepts user commands and information for the entry and editing of cell contents which may include data formulas macros and the like. Indicator displays an address for the current cursor i.e. active cell position. At the status line system displays information about the current state of the workbook for example a READY indicator means that the system is ready for the user to select another task to be performed.

The toolbar shown in further detail in comprises a row or palette of tools which provide a quick way for the user to choose commonly used menu commands or properties. In an exemplary embodiment toolbar includes file manipulation buttons printing buttons an undo button cut copy and paste buttons information pop up window buttons tool a range selection button a style copy button a column resizing button and a sum button . The functions of these buttons are suggested by their names. For instance buttons cut copy and paste data and objects to and from Windows clipboard. The same actions are also available as corresponding commands in the Edit menu available from menu bar .

The notebook which provides an interface for entering and displaying information of interest includes a plurality of spreadsheet pages. Each page may include conventional windowing features and operations such as moving resizing and deleting. In a preferred embodiment the notebook includes 256 spreadsheet pages all of which are saved as a single disk file on the mass storage . Workspace may display one or more notebooks each sized and positioned e.g. tiled overlapping and the like according to user specified constraints.

Each spreadsheet page of a notebook includes a 2 D spread. Page A from the notebook for example includes a grid in row and column format such as row 3 and column F. At each row column intersection a box or cell e.g. cell C4 is provided for entering processing and displaying information in a conventional manner. Each cell is addressable with a selector being provided for indicating a currently active one i.e. the cell that is currently selected .

As shown in individual notebook pages are identified by page identifiers preferably located along one edge of a notebook. In one embodiment each page identifier is in the form of a tab member e.g. members situated along a top edge of the notebook. Each tab member may include representative indicia such as textual or graphic labels including user selected titles representing the contents of a corresponding page. In the tab members are set to their respective default names. For example the first three tab members members are respectively set to A B and C. Tab members are typically given descriptive names provided by the user however. As shown in for example the first three tab members have now been set to Contents tab member Summary tab member and Jan tab member . In a similar manner the remaining tabs are set to subsequent months of the year. In this manner the user associates the page identifiers with familiar tabs from an ordinary paper notebook. Thus the user already knows how to select a page or spread of interest simply select the tab corresponding to the page as one would do when selecting a page from a paper notebook .

In addition to aiding in the selection of an appropriate page of information the user customizable page identifiers serve aid in the entry of spreadsheet formulas. For example when entering a formula referring to cells on another page the user may simply use the descriptive page name in the formula itself as described herein infra thus making it easier for the user to understand the relationship of the cell s or information being referenced.

A general description of the features and operation of the spreadsheet notebook interface may be found in Quattro Pro for Windows available from Borland International.

In embodiments described infra a single output data is provided by the model under study. For real cases where several output data are featured the model can be considered as a collection of different models where each of them specifies a single output data.

The input data comprises scope data and model data. Scope data is specific to a quotation and quantifies the scope of service to be delivered e.g. the number of objects to be managed for a remote management offering . Model data specifies parameters which are not scope dependent but rather are model dependent e.g. a labour rate giving the hourly cost for a person with a given skill level .

SD corresponds to the set of scope data. Here it is assumed that several of these scope data are part of the model under study. Scope data is identified by an index i.

MD corresponds to the set of model data. Here it is assumed that several of these model data are part of the model under study. Model data is identified by an index j.

IR corresponds to the set of intermediary results. Here it is assumed that several of these intermediary results are part of the model under study. Intermediary results are identified by an index k.

The different relationships defined between the above data correspond to the different formulas found within the electronic spreadsheet cells hosting these data. These relationships are also formally represented by mathematical functions as follows 1 

All the available input data SD and MD are not necessarily present in the above formula. The same remark also applies for the formula translating the relationship defining the intermediary data see infra . 2 

It is assumed that there is no circular reference that is a data which is a function of itself in the electronic spreadsheet thus some intermediary results are such that 3 

Thus the intermediary results in equation 3 rely only on the input data. Equations 1 2 and 3 will be referred to as equations of category 1 2 and 3 respectively.

Accordingly the set of relationships can be formalized through a tree structure as shown in . The tree structure in defines a hierarchy between a lowest level corresponding to the output data OD and arbitrarily set to 1 and a highest level corresponding to an intermediary result which is the deeper in the sequence of antecedents. Within the case illustrated by the a first intermediary result IR is at level 2 while the level 3 corresponds to a second intermediary result IR to a scope data SD and to a model data MD. Conventional techniques not described herein are available to assign such levels.

This can be done by recursively replacing in each equation of category 2 IR F SD MD IR each argument IRby the corresponding equation of either category 2 IR F SD MD IR or category 3 IR F SD MD . For instance if each argument IRis replaced by an equation of category 2 IR F SD MD IR the step will comprise building the following relationships IR F SD MD F SD MD IR . In the present case all the resulting equations are of category 2 . The next step comprises replacing each argument IRof each equation of category 2 by an equation either of category 2 or 3 . This iterative process ends when each argument can be defined by an equation of category 3 and when the output data can be represented in an equation of category 4 .

If each argument IRis replaced by an equation of category 3 IR F SD MD the step comprises building the following relationships IR F SD MD F SD MD which are equations of category 3 . The next step comprises replacing in equation of category 1 all the arguments IRby the corresponding equations of category 3 to obtain an equation of category 4 .

If at least one argument IRis replaced by an equation of category 2 IR F SD MD IR at least one of the resulting equations will be of category 2 . The next step comprises replacing each argument IRof each equation of category 2 by an equation either of category 2 or 3 . This iterative process ends when each argument can be defined by an equation of category 3 and when the output data can be represented in an equation of category 4 .

The resulting new formula 5 OD F SD supersedes the set of formulas corresponding to the equations 1 2 and 3 . These equations 1 2 and 3 can be simply removed from the electronic spreadsheet file by deleting the content of the corresponding cells. Obviously the resulting data needs to be recorded in a new file to avoid the loss of the root information made by the equations 1 2 and 3 .

Computer algebra is today a well known technique available either within commercial product such as Maple Mathematica MatLab and MuPad or as sharewares like Yacas . Such techniques are available in tools that can be easily interfaced by office applications such as electronic spreadsheets due to industry standard Application Programming Interfaces which can be invoked by macros. The present invention does not assume one particular tool related to formula simplification e.g. through factorization techniques or formula evaluation since most of the available tools share a wide range of similar functions which fit the needs of the present invention.

The scope data of corresponds to the duration of the service contract scope data year the number of managed network devices scope data dev and the number of customer locations scope data loc .

The model data of corresponds to multiple variables specifying different cost drivers such as hourly labor rates model data hrmon hrpb and hrrep hardware charges model data srvcost and software license charges model data sfwfee .

The output data of corresponds to a single output data giving the total contract value output data tcv .

The intermediary results are represented by . comprises intermediary results corresponding to either monthly charges or one time charges. comprises intermediary results corresponding to yearly dependent cost drivers.

The tree in specifies the levels defining the hierarchy between the different intermediary results. For instance the highest hierarchical level 1 corresponds to the output data tcv . The second level corresponds to the intermediary results mlc and otc and so on up to the last hierarchical level 12 corresponding to the intermediary result coef1 which is listed as a leaf node of equation type 3 in .

For instance the first equation tcv mlc year 12 otc rank equal to 1 in translates the relationship used to determine the output data tcv from the scope data year and from the intermediary results mlc and otc . This first equation for tcv is of type 1 because the first equation is a root node at level 1.

In the present example the first two steps A and B as previously described are performed as follows starting with the equation of highest level 12 that is coef 1 1 followed down to level 7 1 1 2 1 1 3 2 4 3 5 4 6 5 Note that in the previous equalities steps A and B have been nested to allow the computer algebra algorithm to perform the simplification of the form a a a.

Then going on with the equations of level 6 starting with rank 31 to 36 and using the variable i as an integer between values 1 and 6 

Let assume now that the objective is to hide all the model data except the trv one which specifies the average cost for travelling to the customer premises. The step C substitutes every model data but trv in the former formula by its corresponding value as follows 

The last step consists in feeding the computer algebra engine with the above formula in order to perform the simplification of the expressions between brackets. This results into the following formula 

It is clear that nobody can reverse engineer this kind of formula to sketch the underlying model and cost drivers. So if a spreadsheet cell is filled with this formula and if all the cells hosting intermediary results are removed then the present problem is solved. Spreadsheet file according to the present invention comprises a faithful and working version of the original model without disclosing any of its internal sensitive information.

At step the spreadsheet user is prompted to specify the cell which comprises the Output Data OD. If a single output data is produced by the model then a single cell must be specified within the electronic spreadsheet file. For a model producing a plurality of output data the present method can be repeated for each individual output data.

At step an Intermediary Result Table IRT is created to record the set of intermediary results IR in the spreadsheet and to link the output data with both the Scope Data and the Model Data. This IRT is made of a collection of records each record comprising the following fields a Cell Address CA field but if the cell is named then the cell name can replaces the cell address a Cell Type CT field a Cell Level CL field Cell Content CC field.

The IRT is built by starting with the first record corresponding to the output data where the Cell Level defaults to 1. The creation of the following records comprises the steps of parsing the formulas of the CC Cell Content field of already existing records and identifying in the parsed formulas variables which are neither a SD Scope Data nor a MD Model Data . Such variables correspond to Intermediary Results IR . For each created record corresponding to a given IR the value given to the CL Cell Level field is equal to the highest value of the CL field of the parent IR incremented by 1. This process completes when for all the created records the formula points to variables which are either SD or MD or recorded IR.

At step the computer algebra engine is fed with the formulas comprised in the CC fields of the IRT in order to build a formula of type 4 OD F SD MD . This is also done iteratively by starting feeding the computer algebra engine with the formulas CC of highest CL and simplifying the last fed CC. This sequence of steps is illustrated in the previous example.

At step the resulting formula built by the computer algebra engine is recorded in a cell of the spreadsheet file for instance within a cell previously void or as a new version of the cell previously containing OD Output Data .

At step the electronic spreadsheet user is prompted to specify which are the MD Model Data which need to be hidden. This can be done through conventional user interface techniques such as pop up windows and dialog box or this can even be reduced to a void step assuming by default that all the MD must be hidden if it is not the case then an input data is specified as Scope data in step .

At step the computer algebra engine is fed with this formula where hidden MD are replaced by their values for simplification.

At step the simplified formula returned by the computer algebra engine is recorded in a cell of the spreadsheet file with the same approach as for step .

At step all the IR intermediary result cells including obviously the original OD cell and all the hidden MD cells are removed from the electronic spreadsheet file.

In a conventional costing pricing tool end users can easily determine all the different intermediary results which are part of the model. Such intermediary results can contain confidential information typically the model data that the costing pricing tool spreadsheet author does not want to share with third parties. Nevertheless the author may want to share a tool which produces the output data when fed with the scope data.

The present invention can be advantageously used to share a costing pricing model with third parties without disclosing intermediary results can contain confidential information typically the model data .

For instance a company X is currently delivering an offering through direct sales channel and wants to rely on indirect channels like business partners to reach a wider opportunity base. With the present invention it is possible to share with one or a plurality of business partners an internal cost price model while preserving the confidentiality of sensible information.

The method of the present invention is next discussed in a formulation as illustrated by the detailed worked out example discussed supra.

A first output equation tcv mlc year 12 otc expresses an output data tcv as a function of at least one first input data year and at least one first intermediary result mlc otc . A plurality of first intermediary equations nodes in levels 2 12 of relates the at least one first intermediary result mlc otc to at least one second intermediary result mlcm mlch . . . coef2 coef1 and at least one second input data dev loc srvcap . . . hiny . A plurality of input data year dev loc srvcap . . . hiny denotes the at least one first input data year and the at least one second input data dev loc srvcap . . . hiny collectively. A plurality of intermediary results mlc otc mlcm mlch . . . coef2 coef denotes the at least one first intermediary result mlc otc and the at least one second intermediary result mlcm mlch . . . coef2 coef collectively.

The plurality of intermediary results are assigned as content of intermediary cells of the spreadsheet Intermediate Result Table in step of .

A second output equation tcv dev 12 . . . year 12 . . . namely the level equation for tcv resulting from execution of steps A and B is generated wherein the second output equation expresses the output data tcv as a function of a subset of the plurality of input data with no functional dependence on the plurality of intermediary results. See second output equation of tcv 1.5 75 trv year trv . . . in step D wherein the subset of the plurality of input data includes the scope data year dev loc and excludes all model data except trv and wherein the second output equation has no functional dependence on the plurality of intermediary results mlc otc mlcm mlch . . . coef2 coef . Generation of the second output equation utilizes the first output equation tcv mlc year 12 otc and the plurality of first intermediary equations nodes in levels 2 12 of .

The output data tcv of the second output equation is assigned as content of an output cell of the spreadsheet see step of .

After the output data is assigned the content of the intermediary cells is removed resulting in the plurality of intermediary results not being identifiable in the spreadsheet see step of .

Generating the second output equation may comprise recursively eliminating the at least one second intermediary result mlcm mlch . . . coef2 coef1 from the plurality of first intermediary equations nodes in levels 2 12 of to transform the plurality of first intermediary equations into at least one second intermediary equation level 2 equation for otc and mlc resulting from execution of steps A and B that expresses the at least one first intermediary result mlc otc in terms of the at least one second input data dev loc srvcap hiny with no dependence on the at least one second intermediary result mlcm mlch . . . coef2 coef . The at least one first intermediary result from the at least one second intermediary equation is substituted into the first output equation tcv mlc year 12 otc to generate the second output equation tcv dev 12 . . . year 12 . . . namely the level 1 equation for tcv resulting from execution of steps A and B .

The subset of the plurality of input data may not include at least one selected input data of the plurality of input data. Generation of the second output equation may comprise replacing each selected input data by its value such that the second output equation in the output cell does not indicate a functional dependence on the at least one selected input data. In the detailed example the at least one selected input data replaced by its values was all of the model data except trv.

While the invention has been particularly shown and described with reference to a preferred embodiment it will be understood that various changes in form and detail may be made therein without departing from the spirit and scope of the invention.

