---

title: Method for copying images
abstract: An apparatus for copying image data between computer applications running under at least one operating system, the apparatus comprising: a selector, operable by a user, for selecting an object from a computer application, and an image data importer, associated with the selector, and configured to automatically import image data of the selected object into a predetermined target computer application, upon the selecting.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08935624&OS=08935624&RS=08935624
owner: Voyant Health Ltd.
number: 08935624
owner_city: Petach-Tikva
owner_country: IL
publication_date: 20061218
---
The present invention relates to computer user interfaces and more particularly but not exclusively to a system and apparatus for copying images between computer applications.

In human computer interaction cut and paste or copy and paste is a user interface paradigm for transferring text data files or objects from a source to a destination. Most ubiquitous is the ability to cut and paste sections of plain text.

The term cut and paste derives from the traditional practice in manuscript editing in which paragraphs were literally cut from a page with scissors and physically pasted onto another page.

This traditional practice was standard practice as late as the 1980s. Editing scissors with blades long enough to cut an 8 wide page were available at stationery stores. The advent of photocopiers made the practice easier and more flexible.

The cut and paste paradigm was widely popularized by Apple in the Lisa and Macintosh operating systems and applications. It was mapped to a key combination consisting of a special control key held down while typing the letters X for cut C for copy and V for paste .

The above key combinations were later adopted by Microsoft in Windows . Common User Access in Windows and OS 2 also uses combinations of the Insert Del Shift and Control keys.

The first multiple clipboard utility Copy Paste appeared on the Macintosh in 1989 and extended the keyboard concept for each clipboard so that holding down the command key c any number 0 9 would copy to a separate clipboard. CopyPaste later displayed and allowed editing hundreds of clipboards and added a clipboard recorder or stack of the most recently made cuts or copies.

Copy and paste refers to the popular simple method of reproducing data from a source application to a destination application which is only different from cut and paste in that the original source data is not deleted or removed as it is with the latter process.

Copying can be performed on most graphical user interface systems using the key combinations such as Ctrl C or Ctrl Ins or by using some other method such as a context menu or a toolbar button.

Once data have been copied into the area of memory referred to as the clipboard they can be pasted into a destination using the key combinations Ctrl V or Shift Insert or methods dependent on the system.

Macintosh computers use the key combinations Command C and Command V. In the X Window System selecting text copies it to a clipboard while middle clicking pastes.

The popularity of this method stems from its simplicity and the ease with which data can be moved between various applications without resorting to permanent storage.

By now the cut and paste paradigm or copy and paste is a universal paradigm used on a daily basis by most computer users.

Currently there are many computer applications which implement the cut and paste or copy and paste paradigm as described in further detail hereinabove.

For example TechSmith Inc. offers the Snag It product. The Snag It product allows a computer user to capture screen images of objects or entire screens and copy the images from one computer document to another.

However with current products the copy and paste operation is a multi step semiautomatic process. The user has to select the image in an application as well as a target application that the image data is copied to.

Furthermore the image data is temporarily stored in a file or a clipboard before the image is copied to the target application and the access to the file or a clipboard has to be appropriately managed.

On most systems there is only one location in the clipboard hence another cut operation overwrites the previously stored information. Multiple clipboard entries are provided by many UNIX text editors and some Windows clipboard manager programs that are available over the Internet.

With current systems only when the user selects the target application for the specific copy and paste operation is the image data copied to the target application.

For example U.S. Pat. No. 6 269 389 to Ashe filed on May 5 1995 entitled Method and system for controlling the copying and insertion of contents of documents describes a clipboard manager. The clipboard manager employs preemptive scheduling for access to contents of a clipboard region of memory in a computer.

There is thus a widely recognized need for and it would be highly advantageous to have a system devoid of the above limitations.

According to one aspect of the present invention there is provided an apparatus for copying image data between computer applications running under at least one operating system the apparatus comprising a a selector operable by a user for selecting an object from a computer application and b an image data importer associated with the selector and configured to automatically import image data of the selected object into a predetermined target computer application upon the selecting.

According to a second aspect of the present invention there is provided a method for copying image data between computer a applications running under at least one operating system the method comprising allowing a user to select an object from a computer application and upon the selecting automatically importing image data of the selected object into a predetermined target computer application.

Unless otherwise defined all technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. The materials methods and examples provided herein are illustrative only and not intended to be limiting.

Implementation of the method and system of the present invention involves performing or completing certain selected tasks or steps manually automatically or a combination thereof.

Moreover according to actual instrumentation and equipment of preferred embodiments of the method and system of the present invention several selected steps could be implemented by hardware or by software on any operating system of any firmware or a combination thereof.

For example as hardware selected steps of the invention could be implemented as a chip or a circuit. As software selected steps of the invention could be implemented as a plurality of software instructions being executed by a computer using any suitable operating system. In any case selected steps of the method and system of the invention could be described as being performed by a data processor such as a computing platform for executing a plurality of instructions.

The present embodiments comprise a method and apparatus for importing image data from one computer application to a target computer application.

A computer application is a defined subclass of computer software that employs the capabilities of a computer directly to a task that the user wishes to perform. This should be contrasted with operating systems which are involved in integrating a computer s various capabilities but typically does not directly apply them in the performance of tasks that benefit the user. An application generally runs within or under an operating system.

Typical computer applications used on a daily basis include a word processor such as Word a spreadsheet editor such as Excel etc.

For example in medical imaging Picture Archiving and Communication Systems PACS are computer applications dedicated to storage retrieval distribution and presentation of medical images.

With a method according to a preferred embodiment of the present invention a user may select an object appearing in a window of a computer application say a PACS application and the image data of the selected object is automatically imported to a predefined target computer application.

The predefined target computer application may be predefined by an administrator of a system predefined by the user or simply be an application the method is implemented by say a medical image calibration software installed with a functionality for implementing the method as described in further detail hereinbelow .

That is to say according to a preferred embodiment of the present invention the user merely has to choose the object for having the image data of the object automatically imported to the target application.

Unlike current methods the user does not have to engage in a multi step process where the user selects an object say by performing a Copy or Cut operation the image data of the object as held by the operating system is temporarily placed in a file or in a clipboard the user chooses the target application and the image is pasted on the target application s window.

For example a user uses propriety PACS software to examine a radiographic image of a human organ or bone. The user also uses a computer application for calibrating the radiographic image.

In accordance with a preferred embodiment of the present invention the user chooses the radiographic image in the PACS software. Consequently the image data of the radiographic image is automatically imported from the operating system to the target computer application used for calibrating the image.

The radiographic image may be presented edited and calibrated by the targeted computer application used for calibrating the image.

The principles and operation of an apparatus and method according to the present invention may be better understood with reference to the drawings and accompanying description.

Before explaining at least one embodiment of the invention in detail it is to be understood that the invention is not limited in its application to the details of construction and the arrangement of the components set forth in the following description or illustrated in the drawings.

The invention is capable of other embodiments or of being practiced or carried out in various ways. Also it is to be understood that the phraseology and terminology employed herein is for the purpose of description and should not be regarded as limiting.

Reference is now made to which is a block diagram illustrating an apparatus for copying image data between computer applications according to a preferred embodiment of the present invention.

The selector may be used by a user to select an object in a computer application say a radiographic image in a Picture Archiving and Communication Systems PACS .

Preferably the selector presents a marker to the user and allows the user to drag the marker onto an image of the object thereby to select the object as described in further detail hereinbelow.

An operating system such as Windows has access to image data of each object presented to a user in a computer screen by the operating system.

The image data importer automatically imports image data of the selected object from the operating system into a predetermined target computer application upon the selection of the object by the user.

That is to say once the user selects the object from the PACS or other computer application the image data of the selected object is imported from the operating system to a target application as described in further detail hereinbelow.

Preferably the target application is an application preinstalled with an apparatus such as a word processor spreadsheet software software for calibrating medical digital images etc.

Optionally the target application is a target application chosen by an administrator of the apparatus or a target application chosen by the user. Once the user or administrator selects the target application image data of any object selected by the user is automatically imported from the operating system to the selected target application.

Preferably the image data importer finds if the selected object belongs to the target application and thereby avoids importing the image data of an object belonging to the target application.

The image capturer captures the image data of the object selected by the user from an operating system prior to the importing of the image data of the object to the target application.

For example the image capturer may be implemented using a window spy. A window spy is software that is used for capturing the handle of the window where the image of the object is displayed and the handle is used to import the graphic object data from the operating system as described in further detail hereinbelow. An example of a window spy is Windows Spy.

One problem with the Windows operating system is that the Windows operating system does not provide for capturing of image data from a window which is not topmost of the windows presented to the user as explained in further detail hereinbelow.

That is to say when a user of a target application selects an object while using the target application the window of the target application is topmost. However the Windows operating system does not provide for capturing image data of the selected object s window as the object s window is not topmost among windows managed by the operating system.

In order to allow the capturing the image data of the object selected by the user the selected object s window is made topmost.

The topmost maker makes the selected object topmost. Consequently the image data of the selected object may be captured from the operating system. For example the image capturer may capture the image data from the Windows operating system as described in further detail hereinbelow.

The target application may be used to present the image data process the image data edit the image data etc as known in the art.

The image presenter presents an image of the selected object in a window of the target application using the imported image data.

Preferably the image presenter presents an image of the selected object in a window of the target application using the imported image data according to a policy predefined by a user or an administrator of the apparatus .

For example an administrator of the apparatus may define a policy that all images are to be aligned with the upper border of a window presented in a certain position in the window presented in a certain size etc.

Preferably the apparatus also comprises an image data processor connected to the image data importer .

The image data processor may process the image data according to a predefined policy. The policy may be defined by a user an administrator of the apparatus etc.

An example of such a policy would be that the image data processor may process the color images to a grey scale improve the quality of the image etc as known in the art.

Reference is now made to which is a flowchart illustrating a method for copying image data between computer applications according to a preferred embodiment of the present invention.

According to method a user is allowed to select an object from a computer application say using a selector as described in further detail hereinabove.

For example a user may select a radiographic image in a Picture Archiving and Communication Systems PACS .

Reference is now made to which shows an exemplary marker for selecting an object according to a preferred embodiment of the present invention.

Preferably the user is presented a marker and allowed to drag the marker onto an image of the object thereby to select the object .

Upon the selection of the object by the user say by dragging the marker into the image of the object as described hereinabove the image data of the selected object is automatically imported from the operating system into a predetermined target computer application.

That is to say once the user selects the object from the PACS or other computer application the image data of the selected object is imported into a target application say using an image data importer as described in further detail hereinbelow.

Preferably the method is implemented by an application preinstalled within an apparatus such as a word processor spreadsheet software software for calibrating medical digital images etc.

Optionally the target application is a target application chosen by an administrator of the apparatus or a target application chosen by the user in advance.

Once the user or administrator selects the target application image data of any object selected by the user is automatically imported to the selected target application.

Preferably there is verified that the object selected by the user does not belong to the target application itself say using the image data importer . If the selected object belongs to the target application the image data of the object which belongs to the target application is not imported to the target application.

Optionally the image data of the object is retrieved from the operating system prior to the importing of the image data of the object to the target application say using the image capturer described hereinabove.

One problem with the Windows operating system is that the Windows operating system does not allow capturing of image data from a window which is not topmost of the windows presented to the user.

For example when a user of a target application selects an object while using the target application the window of the target application is topmost. However the Windows operating system does not provide for capturing image data of the selected object s window as the object s window is not topmost among windows managed by the operating system.

In order to allow the capturing the image data of the object selected by the user the selected object s window is made topmost.

In order to overcome the problem with the Windows operating system the selected object is made topmost say using the methods described in further detail hereinbelow. Consequently the image data of an object may be captured from the Window operating system.

The target application may be used to present the image data process the image data edit the image data etc as known in the art.

Preferably the image data is used to present the image in a window already used by the target application in a new window etc.

Preferably the image of the selected object is presented in the window of the target application using the imported image data according to a policy predefined by a user or an administrator of the apparatus as described in further detail hereinabove.

Reference is now made to which shows an exemplary image of the object selected in after import to a target application according to a preferred embodiment of the present invention.

An administrator of the apparatus may define a policy that all images are to be aligned with the upper border of a window presented in a certain position in the window presented in a certain size etc.

Preferably the image data imported to the target application is processed according to a predefined policy. The policy may be defined by a user an administrator of the apparatus etc.

For example the image data processor may present color images in grey scale improve the quality of the image etc as known in the art.

Reference is now made to which is a flowchart illustrating a second method for copying image data between computer applications according to a preferred embodiment of the present invention.

Method may be implemented in the Windows operating system environment. In the method the user is presented a grabber window with a marker as illustrated in .

The grabber window presents the user with instructions for selecting the object and with a marker usable for selecting the object by dragging the marker onto the object as described in further detail hereinabove.

The user is allowed to drag the marker onto an image of an object that the user wishes to import into a predefined target application as described in further detail hereinabove.

Next there is found the handle of the window of the object selected by the user say by the image data imported . The handle is a unique number assigned by the Windows Operating system to each window.

If the handle belongs to the window of the target application the selection is disabled and no image data of the object which appears to be mistakenly selected by the user is imported to the target application.

If the handle does not belong to a window of the target application the object is made topmost say by making the window of the selected object topmost as described in further detail hereinbelow and the image data of the selected object is fetched from the Operating System say as a bitmap file as known in the art.

The target application may be an application such as a word processor or a spreadsheet editor selected in advance by the user or administrator of the apparatus a target application implementing the method etc as described in further detail hereinabove.

Reference is now made to which shows an exemplary image of an object in one application imported to a target application according to a preferred embodiment of the present invention.

The target application may process the image data of an object presented in an application present an image of the object to the user in minimized or maximized form using the image data of the object etc as described in further detail hereinabove.

Reference is now made to which is a flowchart illustrating a method for making an object topmost according to a preferred embodiment of the present invention.

As explained hereinabove one problem with the Windows operating system is that Windows operating system does not allow capturing of image data of a window which is not topmost of the windows presented to the user from the operating system as explained in further detail hereinbelow.

Optionally the user manually switches to the window of the object the user wishes to select say using the Windows Alt Tab functionality as known in the art thus making the window of the object selected by the user topmost

Preferably the object selected by the user in a Windows operating system application is made topmost say using method .

In method the handle of an object s window which needs to be made topmost is received say by the topmost maker described in further detail hereinabove.

Next there is used the GetParent Windows Application Programming Interface API Function to retrieve the handle of a window which contains the object selected by the user and the handle is stored .

Next there is checked if the window which contains the object selected by the user is minimized. If the window which contains the object selected by the user is minimized the window is restored to normal size using the ShowWindow API command as known in the art.

Next the handle of the foreground window is retrieved from the operating system using the GetForwardWindow API command as known in the art.

If the handle of the foreground window is different than the handle of the window hosting the object then there are performed the following steps 

The API GetWindowThreadProcessID is used to get the handle of the window which contains the object selected by the user.

The API method GetWindowThreadProcessID is also used to get the handle of the foreground window and the two handles are stored.

Next the Win32 AttachThreadInput method is used in order to attach the thread of the window of the object to the thread of the foreground window using the stored handles. By attaching the threads the thread of the window of the objects is successfully disguised as the thread of the foreground window which is usually the window of the target application . Consequently the BringToFront and SetForegroundWindow which are usually restricted to the foreground window may be used with respect to the window of the selected object.

If the Win32 AttachThreadInput method succeeds in attaching the threads the BringToFront and SetForegroundWindow methods are used in order to bring the window of the object to the front. Subsequently the AttachThreadInput is used again to disable the attachment of the window threads.

For example the Windows Operating System may block the AttachThreadInput method for a timeout period of a number of milliseconds from the last when a user uses the mouse or keyboard.

In order to overcome the blocking of the AttachThreadInput method If the Win32 AttachThreadInput method fails or the Win32 GetForegroundWindow indicates that the window of the object is not topmost there are carried out the following steps 

It is expected that during the life of this patent many relevant devices and systems will be developed and the scope of the terms herein particularly of the terms PACS Window Object Image Data Thread and Handle is intended to include all such new technologies a priori.

It is appreciated that certain features of the invention which are for clarity described in the context of separate embodiments may also be provided in combination in a single embodiment.

Conversely various features of the invention which are for brevity described in the context of a single embodiment may also be provided separately or in any suitable sub combination.

Although the invention has been described in conjunction with specific embodiments thereof it is evident that many alternatives modifications and variations will be apparent to those skilled in the art. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the spirit and broad scope of the appended claims.

All publications patents and patent applications mentioned in this specification are herein incorporated in their entirety by reference into the specification to the same extent as if each individual publication patent or patent application was specifically and individually indicated to be incorporated herein by reference. In addition citation or identification of any reference in this application shall not be construed as an admission that such reference is available as prior art to the present invention.

