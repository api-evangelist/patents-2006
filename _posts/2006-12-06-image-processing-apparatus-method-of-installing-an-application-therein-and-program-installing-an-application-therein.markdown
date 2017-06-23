---

title: Image processing apparatus, method of installing an application therein, and program installing an application therein
abstract: Provided is an image processing apparatus, comprising a first function-judging unit of judging the function used by an installed application, a second function-judging unit of judging the functions available in the device, and a control unit of terminating and/or eliminating the function unused by the installed application, based on the results obtained in the first function-judging unit and the second function-judging unit when the application is installed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07952738&OS=07952738&RS=07952738
owner: Konica Minolta Business Technologies, Inc.
number: 07952738
owner_city: Chiyoda-Ku, Tokyo
owner_country: JP
publication_date: 20061206
---
This application claims priority under 35 U.S.C. 119 to Japanese Patent Application No. 2006 116371 filed on Apr. 20 2006 the entire disclosure of which is incorporated herein by reference in its entirety.

The present invention relates to an image processing apparatus operating by an application installed such as MFP Multi Function Peripheral a method of installing the application used in the image processing apparatus and an installing program stored on a computer readable medium to make a compute in the image processing apparatus execute the processing of installing an application.

The following description sets forth the inventor s knowledge of related art and problems therein and should not be construed as an admission of knowledge in the prior art.

For example when various applications such as image converting application are installed and operated in a multifunctional digital processing machine MFP it is often difficult to install the applications because of the shortage in storage region needed for installation and to operate the applications because of the shortage in the memory range needed for operation. In addition it is occasionally difficult to run the applications because of the shortage in processing capacity of MFP lower operational speed or lower efficiency in use.

When there is insufficiently resource available in MFP as described above the manager often replaces the applications seldom used or turns off or eliminates the applications not in use manually and reinstalls applications according to the condition of the apparatus.

On the other hand methods of obtaining information on the applications used judging the possibility of installing an application in the apparatus based on the application information displaying the information on the operational panel for selection of installable applications are conventionally known for such apparatuses for example Japanese Unexamined Laid open Patent Publication No. 2004 127281 .

However it is quite laborsome to exchange applications removing unused functions manually or removing and reinstalling application manually according to the condition of the device when there is restriction in the resource of the device such as memory capacity and processing capacity as in conventional devices. It is because it is necessary to eliminate and reinstall applications several times for installation if there is no information on the resource for storage of existing applications and the resource for storage and operation of the applications to be installed. Even if the resource is secured when operation of the functions is turned off or applications are eliminated the application to be installed may not be sufficiently used when installed if the application uses the functions or the applications above.

In addition by the method described in Japanese Unexamined Laid open Patent Publication No. 2004 127281 it is possible to select installable applications on the display panel but the usable functions are limited to the functions of installable applications and thus the efficiency in use is lower.

The description herein of advantages and disadvantages of various features embodiments methods and apparatus disclosed in other publications is in no way intended to limit the present invention. Indeed certain features of the invention may be capable of overcoming certain disadvantages while still retaining some or all of the features embodiments methods and apparatus disclosed therein.

The preferred embodiments of the present invention have been developed in view of the above mentioned and or other problems in the related art. The Preferred embodiments of the present invention can significantly improve upon existing methods and or apparatuses.

An object of the present invention is to provide an image processing apparatus allowing automatically installation of applications and favorable operation thereof and higher in the efficiency in use even if there is limitation in the resource of the device without need for additional applications or termination of some of the functions according to condition.

Another object of the present invention is to provide a method of installing an application executed in the image processing apparatus.

Yet another object of the present invention is to provide an installation program stored on a computer readable medium to make a compute in the image processing apparatus execute the processing of installing an application.

a control unit of terminating and or eliminating the function unused by the installed application based on the results obtained in the first function judging unit and the second function judging unit when the application is installed.

a control unit of terminating and or eliminating the functions of the API unused by the installed application based on the judgment results obtained in the API judging unit and the function judging unit when the application is installed.

A third aspect of the present invention is a method of installing an application in an image processing apparatus comprising

a control step of terminating and or eliminating the function unused by the installed application based on the judgment results in the respective judging steps after the application is installed.

A fourth aspect of the present invention is a method of installing an application in an image processing apparatus comprising

a control step of terminating and or eliminating the function of the API unused by the installed application based on the judgment results in the respective judging steps after the application is installed.

A fifth aspect of the present invention is a program stored on a computer readable medium for installing an application for making a compute in an image processing apparatus execute processing comprising

a control step of terminating and or eliminating the function unused by the installed application based on the judgment results in the respective judging steps after the application is installed.

A sixth aspect of the present invention is a program stored on a computer readable medium for making a compute in an image processing apparatus execute processing comprising

a control step of terminating and or eliminating the function of the API unused by the installed application based on the judgment results in the respective judging steps after the application is installed.

The above and or other aspects features and or advantages of various embodiments will be further appreciated in view of the following description in conjunction with the accompanying figures. Various embodiments can include and or exclude different aspects features and or advantages where applicable. In addition various embodiments can combine one or more aspect or feature of other embodiments where applicable. The descriptions of aspects features and or advantages of particular embodiments should not be construed as limiting other embodiments or the claims.

In the following paragraphs some preferred embodiments of the invention will be described by way of example and not limitation. It should be understood based on this disclosure that various other modifications can be made by those in the art based on these illustrated embodiments.

In the image processing system includes for example multiple image processing apparatuses MFP s to a server and multiple terminal devices to for example of personal computer PC wherein the multiple MFP s to the server and the terminal devices to are connected to each other via a network such as of LAN.

Each of MFP s to is a multifunctional digital processing machine having functions as copying machine printer facsimile scanner and others and having the same configuration and MFP will be described as an example in the description below.

In MFP has for example a CPU a ROM a RAM a hard disk an operational panel unit an image reading unit a printing unit and a network interface unit . The ROM RAM hard disk operational panel unit image reading unit printing unit and network interface are connected to the bus of CPU .

The CPU controls the entire operation of MFP and executes a particular installation processing when application software is installed in MFP . The specific processing will be described below.

The ROM is a memory storing the operational program of CPU and the RAM is a memory used as the operational area for CPU .

The hard disk HDD is a memory means storing image data and job data and also storing installed applications.

The operational panel unit has a key input unit and a liquid crystal display unit both not shown in Figure for input of various operations and mode selection.

The image reading unit has a function as scanner to read for example a document image. The printing unit prints image data on paper according to the job condition instructed.

The network interface functions as a communication unit for communicating data among other MFP s to server and terminal devices to on the network .

The program controlling unit consists of an application hereinafter referred to simply as APP acquiring unit an installed application recognizing unit an existing application controlling unit and an APP transferring unit .

The APP acquiring unit acquires an application program to be installed by the user from an external device supplying the APP e.g. terminal device .

The installed application recognizing unit has a functional type recognizing unit a function API recognizing unit and a needed resource recognizing unit .

The function API recognizing unit recognizes the function and the API Application Programming Interface to be used by the installed application.

The needed resource recognizing unit recognizes the resource the first resource needed for operation of the installed application. The resource is for example primary memory capacity secondary memory capacity or the processing capacity of CPU . The primary memory capacity is a memory capacity used for operation of the installed application and is a memory capacity desirable for the RAM shown in in the present embodiment. The secondary memory capacity is a memory capacity needed for installation of the application and is a memory capacity desirable for the hard disk shown in in the present embodiment.

In the present embodiment recognition of the functional type in the functional type recognizing unit recognition of the function and API in the function API recognizing unit and detection of the first resource in the needed resource recognizing unit are performed by reading the following information added to the installed application 

The existing application controlling unit has a functional type recognizing unit a function API recognizing unit a needed resource recognizing unit an application exchange controlling unit and an API controlling unit . The functional type recognizing unit recognizes the types of the functions available on the MFP.

The function API recognizing unit recognizes the functions available on the MFP and the API s responsible for the functions available on the MFP. The needed resource recognizing unit recognizes the resources consumed by the functions available on the MFP.

The application exchange controlling unit controls installation of an application when it is newly installed. It recognizes for example the current resource second resource available for a newly installed application in other words an open resource and compares the first resource with the second resource and when it is not possible to secure the first resource without eliminating and or terminating the preinstalled functions after comparison performs processing for elimination and or termination of the function and installs a new application.

The API controlling unit above enables the functions above by controlling the API responsible for operation of the instructed function in the terminal device. The APP transferring unit sends the data on the function decided to be eliminated by the application exchange controlling unit to an external device e.g. terminal device .

In the present embodiment recognition of the function in the functional type recognizing unit recognition of the function and API in the function API recognizing unit and detection of the resource in the needed resource recognizing unit are performed based on the information which MFP has about each functions about the used resource functional type and the API responsible for each function. Examples of the information include the followings 

The size of the second resource is determined by the application exchange controlling unit from the total of the resources for respective functions and the entire resources.

The processing unit which executes various processings in MFP has a memory controlling unit controlling RAM a nonvolatile memory controlling unit controlling ROM a touch panel controlling unit controlling a touch panel displaying unit not shown in the Figure a scanner controlling unit controlling the image reading unit an outside communication unit controlling the network interface and communicating with external devices an image controlling unit performing image processing and others an engine controlling unit controlling printing unit and a job controlling unit controlling jobs.

In the MFP having such a controlling unit A when an application to be installed is supplied from an external device e.g. terminal device the application is obtained in the APP acquiring unit . In the installed application recognizing unit based on the information attached to the obtained application the functional type of the application is determined in the functional type recognizing unit the function API to be used by the application is determined in the function API recognizing unit and the first resource needed for storing and operating the application is determined in the resource recognizing unit .

On the other hand the functional type of existing functions and the API responsible for the function are determined and the second resource a currently available open resource is determined in the existing application controlling unit . If the second resource is greater in capacity than the first resource when the first resource needed for operation of the installed application and the second resource usable in MFP is compared the second resource is regarded to be ready to accept the application and the application is installed as it is.

When the second resource is smaller than the first resource part of the functions of MFP are eliminated. Then the data on the functions eliminated may be sent to external devices such as terminal devices to . When an existing application is in operation consuming the memory capacity of the second resource and thus the second resource is smaller than the first resource operation of the existing application is terminated.

By this processing when an application is installed even when there is some restriction on the resources such as primary memory capacity secondary memory capacity and the processing capacity of CPU it is possible to install the application and allow it to operate suitably without installing an additional application compatible therewith or terminating the unused function manually.

 I The function corresponding to the API which the installed application uses is not eliminated or terminated. In the example above it corresponds to the raw data transmitting API and the secondary memory storing API.

 II Functions similar to the function of the installed application are eliminated or terminated preferentially. In this example the type of the installed application is image conversion and thus the image converting function which is similar thereto is eliminated preferentially.

Hereinafter the processing to install a new application in MFP will be described with reference to the flowchart of . The processing is performed by operation of the CPU in controlling unit A in accordance with the program stored in ROM .

In step S in data on the functional type the API used and the resource used by application first resource needed for storage and operation of application are acquired from the installed application and the open resource second resource usable for storage and operation of installed application and the used resource in MFP are compared in step S.

In step S it is judged whether the open resource in MFP is greater than the resource used by application. If the open resource in MFP is greater than the resource used by application YES in step S the application is installed in step S and the processing terminates. If the open resource in MFP is not greater than the resource used by the application NO in step S the processing advances to step S.

In step S the processing for judging whether there is a function in MFP that can be eliminated is performed. Then in step S it is judged whether there is a removable function and if there is a removable function YES in step S the processing advances to step S and if there is no removable function NO in step S the processing of an installation error is performed in step S and the processing terminates.

A removable function is selected in step S the open resource after elimination is calculated in step S and the processing advances to step S. It is judged whether the open resource after elimination of the function is greater than the resource used by application in step S if the open resource is greater than the resource used by application YES in step S the function is eliminated in step S securing the open resource and the application is installed in step S. If the open resource is not greater than the resource used by application NO in step S it is judged once again whether there is a removable function back in step S.

Then the subroutine of the processing for judging whether there is a removable function step S in will be described with reference to the flowchart in .

In the function to be eliminated is selected in step S it is judged whether there is a function to be eliminated in step S if there is a function to be eliminated YES in step S the API that becomes ineffective after elimination is obtained in step S and processing advances to step S. If there is no function to be eliminated NO in step S it is set that there is no removable function in step S and the processing goes back to the main routine.

It is judged whether the application to be installed uses the API to be invalidated in step S if the application to be installed uses the API to be invalidated YES in step S the function cannot be removed and the processing goes back to step S and the function to be eliminated is selected once again. If the application to be installed does not use the API to be invalidated NO in step S the function may be eliminated and thus it is set that there is a removable function in step S and the processing goes back to the main routine.

Hereinafter the subroutine of the processing for selecting a removable function step S in will be described with reference to the flowchart shown in .

In it is investigated whether there is a function similar to the application to be installed among the functions to be eliminated in step S and then it is judged whether there is a function similar to the application in step S. If there is a function similar to the application YES in step S it is set that the selected function is to be removed in step S and the processing goes back to the main routine.

Because a function similar to the installed application is eliminated in this way it is possible to prevent the inconvenience caused by elimination of a different and also to eliminate the duplicated functions to the minimal degree making a device higher in efficiency of use.

If there is no function similar to the application NO in step S the use frequency of the functions is determined from the use history in step S it is set that the function lowest in use frequency is to be eliminated in step S and the processing goes back to the main routine.

Hereinafter another process of installing an application in MFP will be described with reference to the flowchart shown in . The processing is also performed similarly to the processing in by operation of the CPU in controlling unit A according to the program stored in ROM .

The processing shown in is processing to transmit the data on a function to be removed to other external devices such as MFP s to when a needed open resource is secured by removing the function of MFP and steps S to S and steps S and S are the same as steps S to in .

In the functional type the API used and the resource used by application first resource are obtained from the installed application in step S and the open resource in MFP second resource and the used resource are compared in step S.

In step S it is judged whether the open resource in MFP is greater than the resource used by application. If the open resource in MFP is greater than the resource used by the application YES in step S the application is installed as it is in step S and the processing terminates. If the open resource in MFP is not greater than the resource used by the application NO in step S the processing advances to step S.

In step S the processing for judging whether there is a removable function in MFP is performed. Then in step S it is judged whether there is a removable function if there is a removable function YES in step S the processing advances to step S if there is no removable function NO in step S the processing of an installation error is performed in step S and the processing terminates.

A removable function is selected in step S the open resource after its removal is calculated in step S and the processing advances to step S.

It is judged whether the open resource obtained by removal of the function is greater than the resource used by application in step S if the open resource is greater than the resource used by the application YES in step S the function is transferred in step S and the processing advances to step S and terminates. If the open resource is not greater tan the resource used by the application NO in step S the processing goes back to step S and repeats the processing for judging whether there is a removable function.

The subroutine of the processing for judging whether there is a removable function step S is the same as that in and the subroutine of the processing for selecting the function to be removed step S is the same as that shown in . Then the subroutine of the processing for transferring function step S shown in will be described with reference to the flowchart shown in .

In needed information is obtained from an external device in step S and an installable external device is selected in step S and the processing advances to step S.

It is judged whether there is an installable external device in step S if there is no installable external device NO in step S the function to be removed is removed without transfer thereof to an external device in step S and the processing goes back to the main routine. If there is an installable external device YES in step S the processing advances to step S.

The application of the function to be removed is converted into data installable in the external device in step S and the converted data is transferred to and installed in the external device in step S. The data on the function to be removed is thus transferred into an external device and the function can be used any time after retrieval or be transferred back to the image processing apparatus if required.

Then in step S the API responsible for the function is changed from internal use mode to external reference mode the same function is removed in step S and the processing goes back to the main routine.

Hereinafter the subroutine of the processing for retrieving an installable external device step S in will be described with reference to the flowchart shown in .

In an installable external device is retrieved in step S it is judged whether there is an installable external device in step S if there is an installable external device YES in step S the processing advances to step S. If there is no installable external device NO in step S it is set that there is no installable external device in step S and the processing goes back to the main routine.

The open resource in the external device found is inquired in step S it is judged whether the open resource in the external device is greater than the resource needed for installing and executing the application of the function to be removed in step S if the open resource is greater than the needed resource YES in step S it is judged that it is installable it is set that there is an installable external device found in step S and the processing goes back to the main routine.

Hereinafter the subroutine of the processing for converting data into a format installable in an external device step S in will be described with reference to the flowchart shown in .

In the data format installable in the external device is inquired in step S the application of the function to be removed is converted into the data format obtained from the external device in step S and the processing goes back to the main routine. The information of installable data format is stored in ROM the application of the function to be removed is converted into the data format identical with the data format retrieved from the external device stored in ROM .

The installable data formats include executive formats .EXE .DLL object formats .OBJ .O library .LIB lava application Java applet Java Servlet and the like. Hereinafter the subroutine of the processing for changing the API from the internal use mode to external reference mode step S in will be described with reference to the flowchart in .

In a symbol table is retrieved in step S. The symbol table is stored in RAM . shows the contents in the symbol table. The symbol table contains the symbol name of API information about use mode internal or external simply inside outside in and the address when in the internal use mode or the IP address of the external device in the external reference mode.

Then it is judged whether there is a corresponding API symbol name in step S. If there is a symbol name YES in step S the processing advances to step S while if there is no symbol name NO in step S the processing goes back to the main routine.

The information about the internal use mode or external reference mode is converted into the external reference mode in step S the IP address of the external device in transfer destination is registered in the symbol table in step S and the processing goes back to the main routine.

Hereinafter another processing for installing an application in MFP will be described with reference to the flowchart shown in . The API used by the installed application is recognized and the function performed by the API unused by the installed application is eliminated in the processing shown in while the function used by the installed application is recognized and the function unused by the installed application is eliminated in the processing in . The processing in is also performed by operation of the CPU in controlling unit A according to the program stored in ROM in a similar manner to the processing in .

In the functional type function used and resource used by application first resource needed for storage and operation of application are obtained from the installed application in step S the open resource in MFP second resource usable for storage and operation of installed application and the resource used are compared in step S.

In step S it is judged whether the open resource in MFP is greater than the resource used by application. If the open resource in MFP is greater than the resource used by application YES in step S the application is installed as it is in step S and the processing terminates. If the open resource in MFP is not greater than the resource used by application NO in step S the processing advances to step S. In step S the processing for judging whether the MFP has a removable function is performed. Then it is judged whether there is a removable function in step S if there is a removable function YES in step S the processing advances to step S if there is no removable function NO in step S processing of an installation error is performed in step S and the processing terminates.

A removable function is selected in step S the open resource available after elimination is calculated in step S and the processing advances to step S.

It is judged whether the open resource available by elimination of the function is greater than the resource used by application in step S if the open resource is greater than the resource used by application YES in step S the function is eliminated securing the open resource in step S and the processing advances to step S and the application is installed. If the open resource is not greater than the resource used by application NO in step S the processing goes back to step S and the processing for judging whether there is a removable function is repeated.

Hereinafter the subroutine of the processing for judging whether there is a removable function step S in will be described with reference to the flowchart in .

In a function to be eliminated is selected in step S it is judged whether there is a function to be eliminated in step S and if there is a function to be eliminated YES in step S the processing advances to step S. If there is no function to be eliminated NO in step S it is set that there is no removable function in step S and the processing goes back to the main routine.

It is judged whether the application to be installed will use the function to be inactivated in step S if the application to be installed uses the function to be inactivated YES in step S the processing goes back to step S because it is not possible to eliminate the function and the processing for selecting the function to be eliminated is repeated. If the application to be installed does not use the function to be inactivated NO in step S it is set that there is a removable function in step S because there is no problem in eliminating the function and the processing goes back to the main routine.

The processing for selecting a removable function step S shown in is the same as the processing for selecting a removable function step S shown in and the description thereof is omitted.

Similarly to the processing shown in in the embodiments shown in the data on the function to be removed may be transferred to the other external devices such as MFP s to when the function in MFP is eliminated for providing a needed open resource.

Hereinafter yet another processing for installing an application in MFP will be described with reference to the flowchart shown . In the present embodiment in addition to the processing shown in an open resource for installation of an application is secured by terminating the function unused by the installed application.

The processing shown in is also performed by operation of the CPU in controlling unit A according to the program stored in ROM similarly to the processing in .

In the functional type API used and the resource used by application first resource needed for storage and operation of application are obtained from the installed application in step S. A function used may be obtained instead of the API used as shown in .

Then in step S the open resource in MFP second resource usable for storage and operation of installed application and the resource used are compared. In step S it is judged whether the open resource in MFP is greater than the resource used by application. If the open resource in MFP is greater than the resource used by application YES in step S the application is installed as it is in step S and the processing terminates. If the open resource in MFP is not greater than the resource used by application NO in step S the processing advances to step S.

In step S the processing for judging whether there is a function that may be inactivated in MFP is performed. Then it is judged whether there is an inactivatable function in step S if there is an inactivatable function YES in step S the processing advances to step S and if there is no inactivatable function NO in step S the processing advances to step S.

An open resource is secured by eliminating and inactivating the same function in step S and the processing advances to step S and the application is installed.

On the other hand in step S the processing for judging whether there is a removable function in MFP is performed. It is then judged whether there is a removable function in step S if there is a removable function YES in step S the processing advances to step S if there is no removable function NO in step S processing of an installation error is performed in step S and the processing terminates.

A removable function is selected in step S the open resource available after elimination is calculated in step S and the processing advances to step S.

It is judged whether the open resource available after elimination is greater than the resource used by application in step S if the open resource is greater than the resource used by application YES in step S the function is eliminated securing the open resource in step S and the processing advances to step S and the application is installed. If the open resource is not greater tan the resource used by application NO in step S the processing goes back to step S and the processing for judging whether there is a removable function is repeated.

Hereinafter the subroutine for the processing for judging whether there is a inactivatable function step S shown in will be described with reference to the flowchart shown in .

In the function to be terminated is selected in step S it is judged whether there is a function to be terminated in step S if there is a function to be terminated YES in step S the API to be invalidated by termination is obtained in step S and the processing advances to step S. If there is no function to be terminated NO in step S it is set that there is no function to be terminated in step S and the processing goes back to the main routine.

It is judged whether the API to be invalidated is used by the application to be installed in step S if the API to be invalidated is used by the application to be installed YES in step S the processing goes back to step S because the function cannot be terminated and the processing for selecting the function to be terminated is repeated. If the application to be installed does not use the API to be invalidated NO in step S it is set that there is a function to be terminated in step S because there is no problem in terminating the function and the processing goes back to the main routine.

The processings for judging whether there is a removable function step S and for selecting the removable function step S in are the same respectively as those shown in and the description thereof is omitted.

While the present invention may be embodied in many different forms a number of illustrative embodiments are described herein with the understanding that the present disclosure is to be considered as providing examples of the principles of the invention and such examples are not intended to limit the invention to preferred embodiments described herein and or illustrated herein.

While illustrative embodiments of the invention have been described herein the present invention is not limited to the various preferred embodiments described herein but includes any and all embodiments having equivalent elements modifications omissions combinations e.g. of aspects across various embodiments adaptations and or alterations as would be appreciated by those in the art based on the present disclosure. The limitations in the claims are to be interpreted broadly based on the language employed in the claims and not limited to examples described in the present specification or during the prosecution of the application which examples are to be construed as non exclusive. For example in the present disclosure the term preferably is non exclusive and means preferably but not limited to . In this disclosure and during the prosecution of this application means plus function or step plus function limitations will only be employed where for a specific claim limitation all of the following conditions present in that limitation a means for or step for is expressly recited b a corresponding function is expressly recited and c structure material or acts that support that structure are not recited. In this disclosure and during the prosecution of this application the terminology present invention or invention may be used as a reference to one or more aspect within the present disclosure. The language present invention or invention should not be improperly interpreted as an identification of criticality should not be improperly interpreted as applying across all aspects or embodiments i.e. it should be understood that the present invention has a number of aspects and embodiments and should not be improperly interpreted as limiting the scope of the application or claims. In this disclosure and during the prosecution of this application the terminology embodiment can be used to describe any aspect feature process or step any combination thereof and or any portion thereof etc. In some examples various embodiments may include overlapping features. In this disclosure and during the prosecution of this case the following abbreviated terminology may be employed e.g. which means for example and NB which means note well .

