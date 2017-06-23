---

title: Method and system for protecting the security of an open file in a computing environment
abstract: A file security protection method and system. The method is performed by an operating system of a computer system. A metadata token is received from a software application executing on the computer system. The metadata token denotes that the application has opened a file. The metadata token includes the name of the file. An initial time is set to about a time at which the metadata token was received. A loop is executed. Each iteration of the loop includes determining whether a first or second condition has been satisfied. The loop is exited if it is determined that the first or second condition has been satisfied. The first condition is that an elapsed time relative the initial time exceeds a specified threshold. The second condition is that a closeout token denoting that the file has been closed has been received from the application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07845013&OS=07845013&RS=07845013
owner: International Business Machines Corporation
number: 07845013
owner_city: Armonk
owner_country: US
publication_date: 20060530
---
The present invention discloses a method and system for protecting the security of an open file in a computing environment.

Many different software applications have within them the ability to mark files as private sensitive protected or otherwise make such files hidden from unintended viewing. Examples of such implementations range from the ubiquitous password protection given to Microsoft Word documents through the gamut of other analogous password protected graphical and spreadsheet files down to the complete masking of protected files e.g. with Palm OS Memo functionality . A security gap exists however as despite the password protections provided by the relevant applications human error or casualness about his her environment may offer unplanned eyes the opportunity to view such files.

Current means of protecting documents as implied assume that the file user will save and close the sensitive document rather than permit the document to be inadvertently viewed by others. However in practice this dependence upon human consistency falls short as users walk away from their computers attend to phone calls and other such interruptions or in the case of handheld devices smart phones and personal digital assistants i.e. highly portable devices forget to re mask records for conceivably days at a time. When the user walks away from the computer the opportunity arises for others to view the screen contents. When a user forgets to re mask records on a highly portable device its sensitive contents may be viewed by anyone who finds the device. In any of these cases secrecy is compromised. Whether the information is of a business or personal nature human inattentiveness has revealed information previously deemed to be of a confidential nature.

receiving a metadata token from a software application executing on a computer system said metadata token denoting that the application has opened a file having a name said metadata token comprising the name of the file 

responsive to receiving the metadata token setting an initial time to about a time at which said receiving the metadata token occurred and

after setting the initial time executing iterations of a loop each iteration of said iterations comprising determining whether a first condition has been satisfied determining whether a second condition has been satisfied and exiting the loop in response to having determined that the first condition or the second condition has been satisfied 

wherein the first condition is that an elapsed time relative the initial time exceeds a specified threshold 

wherein the second condition is that a closeout token denoting that the file has been closed has been received from the application such that the closeout token comprises the name of the file and

wherein said receiving the metadata said setting the initial time and said executing the iterations of the loop are performed by an operating system executing on the computer system.

The present invention provides a process for supporting computer infrastructure said process comprising providing at least one support service for at least one of creating integrating hosting maintaining and deploying computer readable code in a computing system wherein the code in combination with the computing system is capable of performing a file security protection method said method comprising 

receiving a metadata token from a software application executing on a computer system said metadata token denoting that the application has opened a file having a name said metadata token comprising the name of the file 

responsive to receiving the metadata token setting an initial time to about a time at which said receiving the metadata token occurred and

after setting the initial time executing iterations of a loop each iteration of said iterations comprising determining whether a first condition has been satisfied determining whether a second condition has been satisfied and exiting the loop in response to having determined that the first condition or the second condition has been satisfied 

wherein the first condition is that an elapsed time relative the initial time exceeds a specified threshold 

wherein the second condition is that a closeout token denoting that the file has been closed has been received from the application such that the closeout token comprises the name of the file and

wherein said receiving the metadata said setting the initial time and said executing the iterations of the loop are performed by an operating system executing on the computer system.

The present invention provides a computer program product comprising a computer usable medium having a computer readable program code embodied therein said computer readable program code containing instructions that when executed by a processor of a computer system implement a file security protection method said method comprising 

receiving a metadata token from a software application executing on a computer system said metadata token denoting that the application has opened a file having a name said metadata token comprising the name of the file 

responsive to receiving the metadata token setting an initial time to about a time at which said receiving the metadata token occurred and

after setting the initial time executing iterations of a loop each iteration of said iterations comprising determining whether a first condition has been satisfied determining whether a second condition has been satisfied and exiting the loop in response to having determined that the first condition or the second condition has been satisfied 

wherein the first condition is that an elapsed time relative the initial time exceeds a specified threshold 

wherein the second condition is that a closeout token denoting that the file has been closed has been received from the application such that the closeout token comprises the name of the file and

wherein said receiving the metadata said setting the initial time and said executing the iterations of the loop are performed by an operating system executing on the computer system.

The present invention provides a computer system comprising a processor and a computer readable memory unit coupled to the processor said memory unit containing instructions that when executed by the processor implement a file security protection method said method comprising 

receiving a metadata token from a software application executing on a computer system said metadata token denoting that the application has opened a file having a name said metadata token comprising the name of the file 

responsive to receiving the metadata token setting an initial time to about a time at which said receiving the metadata token occurred and

after setting the initial time executing iterations of a loop each iteration of said iterations comprising determining whether a first condition has been satisfied determining whether a second condition has been satisfied and exiting the loop in response to having determined that the first condition or the second condition has been satisfied 

wherein the first condition is that an elapsed time relative the initial time exceeds a specified threshold 

wherein the second condition is that a closeout token denoting that the file has been closed has been received from the application such that the closeout token comprises the name of the file and

wherein said receiving the metadata said setting the initial time and said executing the iterations of the loop are performed by an operating system executing on the computer system.

The memory device includes a software application input data and a file . The software application is a computer program that comprises computer executable instructions and utilizes the file . The input data includes input required by the software application . The operating system includes software for implementing a method that protects the security of the file after the file has been opened by the software application . A user is a user of the software application . The user has access to the file the input device and the output device .

The processor is one or more processors. The processor executes the software application and the operating system runs on the processor . The output device displays output from the software application and or any other data e.g. the input data . Either or both memory devices and or one or more additional memory devices not shown may be used as a computer readable storage medium or program storage device for storing data and program code therein e.g. having a computer readable program stored therein and or having other data stored therein wherein the computer readable program comprises the software application . Generally a computer program product or alternatively an article of manufacture of the computer system may comprise said computer usable medium or said program storage device .

Any of the components of the present invention could be deployed managed serviced etc. by a service provider who offers to deploy or integrate computing infrastructure with respect to an operating system that is enhanced by the file security protection method of the present invention. Thus the present invention discloses a process for supporting computer infrastructure comprising integrating hosting maintaining and deploying computer readable code into the computer system wherein the code in combination with the computer system is capable of performing a method for protecting the security of an open file.

In another embodiment the invention provides a business method that performs the process steps of the invention on a subscription advertising and or fee basis. That is a service provider such as a Solution Integrator could offer to create maintain support etc. an operating system that is enhanced by the file security protection method of the present invention. In this case the service provider can create maintain support etc. a computer infrastructure that performs the process steps of the invention for one or more customers. In return the service provider can receive payment from the customer s under a subscription and or fee agreement and or the service provider can receive payment from the sale of advertising content to one or more third parties.

While shows the computer system as a particular configuration of hardware and software any configuration of hardware and software as would be known to a person of ordinary skill in the art may be utilized for the purposes stated supra in conjunction with the particular computer system of . For example the memory devices and may be portions of a single memory device rather than separate memory devices. As another example the software application and the operating system could be stored on either a same memory device or different memory devices.

The present invention discloses a method and system for protecting the security of an open file e.g. file in a computing environment. The present invention enhances file security by enabling application calls or connections to the operating system so that the operating system may change certain default behaviors during the time that a file containing sensitive or private records has been opened. The present invention provides for an application programming interface API call or other such invocation between the application and the operating system . The content of this call invocation informs the operating system that a sensitive file has been opened and that the operating system should take certain actions accordingly.

In step the software application opens the file . The file may have been assigned a security level with respect to a security classification system and may accordingly be in need of security protection. The security level may be expressed numerically e.g. 1 2 3 4 . . . or textually e.g. sensitive confidential secret etc. . Even if the file has not been assigned a security level the file may nonetheless contain sensitive material and thus be in need of security protection. The sensitive nature of the file may be deemed by use of a password or other masking mechanism.

In step the operating system receives a metadata token from the application . The metadata token denotes that the application has opened the file . The metadata token comprises the name of the file . The metadata token may further comprise at least one of an identification of the application a specified threshold T against which time elapsed is measured as described infra in conjunction with step and the level of security that has been assigned to the file if applicable .

In one embodiment the metadata token comprises a security level of the file but not the threshold. Instead the operating system determines the threshold by using the security level in the metadata token in conjunction with a specification of threshold as a function of security level. For example the operating system may utilize a table such as Table 1.

In step responsive to receiving the metadata token the operating system may perform an onset action. Performing the onset action may comprise modifying a screen saver screen lock time out value triggering a visual indicator on a screen or hardware of the user to remind the user of that file is open or combinations thereof. The screen or hardware may be comprised by the output device . The visual indicator may be inter alia an attention provoking icon or message e.g. Your File STRATEGIC BUYOUT is Open in red color .

In step responsive to receiving the metadata token the operating system sets an initial time T to about a time at which the metadata token was received by the operating system from the software application . For example the operating system may determine the initial time from a system clock of the computer system . The initial time serves as a reference against which subsequent elapsed time T is measured wherein the elapsed time is indicative of how much time elapsed since the initial time was set. Note that the elapsed time T is T T wherein T is the dynamically changing current time which may be determined by inter alia invoking a timer function at the operating system level. The elapsed time T may be viewed as a staleness indicator indicative of how long it has been since interaction with the file has occurred.

In step the operating system determines whether the elapsed time exceeds the threshold i.e. whether T T. If it is determined in step that the elapsed time exceeds the threshold then forgotten document actions are executed in step followed by exiting execution of the algorithm of otherwise step is next executed.

In step the executed forgotten document actions may be at least one of masking an application window on a screen output device of the user auto saving and closing the file and sending a remote indicator e.g. email page SMS IM to a contact device of an owner of the file to indicate that the file remains open.

In step the operating system determines whether the file has been closed. The application communicates that the file has been closed by sending a closeout token see to the operating system . The closeout token comprises the name of the file . Thus the operating system implements step by determining whether the operating system has received the closeout token from the application . If it is determined in step that the file has been closed i.e. the closeout token has been received by the operating system then closeout actions are executed in step followed by exiting execution of the algorithm of otherwise the algorithm loops back to step to perform the next iteration of the loop of steps and .

In step the executed closeout actions may be at least one of modifying a screen saver screen lock time out value and turning off a visual indicator on a screen output device of the user .

The looping through steps and is repeated iteratively until one of the aforementioned condition for executing step or step is satisfied.

If it is determined in step that the file has been closed then closeout actions are executed in step as described supra followed by exiting execution of the algorithm of otherwise step is next executed.

In step the operating system determines whether an action on the file has been undertaken. The application communicates that an action on the file has been undertaken by sending an update token see to the operating system . The update token comprises the name of the file . Thus the operating system implements step by determining whether the operating system has received the update token from the application . If it is determined in step that an action on the file has not been undertaken i.e. the update token has not been received by the operating system then the algorithm loops back to step to perform the next iteration of the inner loop of steps and otherwise the the algorithm loops back to step to reset the initial time to the current time e.g. as determined from the system clock to perform the next iteration of the outer loop of steps and .

The update token may be passed to the operating system each time or via a defined interval the file is changed. In this event the operating system is tracking time between file changes to indicate a potentially forgotten file. Note that the update token may be passed in implementation specific options via an explicit action in which the file is changed saved or unsaved through deletion of content from the file addition of new content to the file and or change of content of the file or via an action in which the file is unchanged and a non intrusive action has occurred with respect to the file e.g. page down page up scrolling etc. Either of these actions explicit action or non intrusive action indicates that the user is still actively engaged with the application and the file itself.

The inner looping through steps and is repeated iteratively until one of the aforementioned condition for executing step or step is satisfied. The outer looping through steps and is repeated iteratively until an action on the file has been undertaken as determined in step .

Note that if multiple sensitive files were open simultaneously the algorithms of would extrapolate without complication. The onset and closeout actions changing operating system behavior would correspond to the first sensitive file opened and the last sensitive file closed and chronologically based actions would be unique to each application and or file as described supra.

While embodiments of the present invention have been described herein for purposes of illustration many modifications and changes will become apparent to those skilled in the art. Accordingly the appended claims are intended to encompass all such modifications and changes as fall within the true spirit and scope of this invention.

