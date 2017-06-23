---

title: Method and device for managing images stored in a plurality of storage media included in or connected to image forming apparatus
abstract: A method and device for managing images stored in a plurality of storage media by using a display unit included in an image forming apparatus to prints the images are provided. The method includes: displaying identification names of a plurality of storage media included in or connected to the image forming apparatus; and linking information on images stored in the plurality of storage media with the identification names of the plurality of storage media and displaying the information on images stored in the plurality of storage media. Accordingly, the identification names of the plurality of storage media included in or connected to the image forming apparatus are displayed by linking information on images with the identification names in order to manage the images stored in the storage media. Therefore, a user can conveniently and promptly recognize and manage the storage media and the images stored in the storage media. In addition, since the plurality of storage media are controlled concurrently, image data can be promptly read from or written to the storage media, and data transfer speed between the storage media can be increased.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07701607&OS=07701607&RS=07701607
owner: Samsung Electronics Co., Ltd.
number: 07701607
owner_city: Suwon-Si
owner_country: KR
publication_date: 20060928
---
This application claims the benefit under 35 U.S.C. 119 a of Korean Patent Application No. 10 2005 0099330 filed Oct. 20 2005 and Korean Patent Application No. 10 2005 0103271 filed Oct. 31 2005 in the Korean Intellectual Property Office the entire disclosures of which are hereby incorporated by reference.

The present invention relates to an image forming apparatus for printing images stored in a plurality of storage media. More particularly the present invention relates to a method and device for managing images stored in the plurality of storage media by using a display unit included in the image forming apparatus.

In image forming apparatuses documents to be printed are converted into encoded data through application programs and the encoded data is then printed on paper in a readable format.

Recently developed image formatting apparatuses use a memory card or a universal serial bus USB memory stick storing image data to facilitate the printing the image data directly from the external storage media or to include a big capacity hard disk.

To print image data from a memory card the image forming apparatus includes a display unit such as a liquid crystal display LCD to display images stored in the memory card. The LCD permits a user to select an image to be printed after verifying the images. The display unit included in the image forming apparatus has an N up function to display a plurality of images stored in the memory card on one screen.

However even when a plurality of storage media are connected to the image forming apparatus the user only obtain information on images stored in the storage medium selected by the user. Therefore images cannot be transferred between storage media resulting in ineffective management of the images stored in the plurality of storage media.

Accordingly there is a need for an improved system and method for effectively managing images stored in a plurality of storage media included in or connected to an image forming apparatus.

An aspect of exemplary embodiments of the present invention is to address at least the above problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of exemplary embodiments of the present invention is to provide a method and device for effectively managing images stored in a plurality of storage media included in or connected to an image forming apparatus.

An exemplary embodiment of the present invention also provides a method and device for controlling a plurality of storage media connected to an image forming apparatus to conveniently and promptly manage stored images.

According to an aspect of an exemplary embodiment of the present invention a method of managing images to be printed by an image forming apparatus is provided. Identification names of a plurality of storage media included in or connected to the image forming apparatus are displayed. Information on images stored in the plurality of storage media is linked with the identification names of the plurality of storage media and the information on images stored in the plurality of storage media is displayed.

According to an exemplary embodiment of the present invention the plurality of storage media may comprise a hard disk a memory card a universal serial bus USB memory stick or a card reader.

The information on images may also be displayed in an enlarged or reduced form so that the images are adjusted to the size of an image display area.

Also the identification names of the storage media may be displayed in a first alignment manner in which the identification names of the storage media are horizontally displayed and the information on the images stored in the storage media is displayed vertically in a column of the corresponding identification names of the storage media. Alternatively the identification names of the storage media may be displayed in a second alignment manner in which the identification names of the storage media are vertically displayed and the information on the images stored in the storage media is horizontally displayed in a row of the corresponding identification names of the storage media.

In addition the identification names of the storage media may be horizontally or vertically displayed and the information on the images stored in the storage media may be horizontally or vertically displayed in the same row or column of the corresponding storage media in which the images are stored.

When two and more images are stored in the storage media information on images is displayed by determining a display order of the images according to an image date a file format a file name or exchangeable image file Exif information and by displaying the information on the images according to the determined display order.

Any one of the displayed identification names of the storage media may be input by a user and images stored in a storage medium corresponding to the input identification name may be displayed.

Directory names of the storage media may be displayed and information on images stored in each directory may be linked with the displayed directory names. Also the information on images stored in each directory may be displayed.

Any one of the images may be selected by a user using the displayed image information. The selected image may be read from the storage media where the image is stored and the selected image may be printed using read image data.

According to an exemplary implementation a storage medium s connection to or disconnection from the image forming apparatus is verified. The size of a display area for displaying information of one image is arranged according to the number of storage media included in or connected to the image forming apparatus when the result of the verification indicates that a storage medium has been connected to or disconnected from the image forming apparatus.

Further the identification names of the storage media and the information on the images may be respectively linked by heads and tails connected to the heads and may be stored in and managed by the image forming apparatus.

According to anther aspect of an exemplary embodiment of the present invention a device for managing images is provided. The device is included in an image forming apparatus and comprises a storage medium managing unit a control unit and a display unit. The storage medium managing unit reads information on images stored in a plurality of storage media included in or connected to the image forming apparatus. The control unit determines identification names of the plurality of storage media and respectively links the images stored in the storage media with the identification names of the storage media. The display unit displays the identification names of the plurality of storage media and the image information.

According to an exemplary implementation the plurality of storage media may comprise a hard disk a memory card a universal serial bus USB memory stick or a card reader.

The information on images may also be displayed in enlarged or reduced form so that the images are adjusted to the size of an image display area.

Also the display unit may horizontally display the identification names of the storage media in a first alignment manner in which the identification names of the storage media are horizontally displayed and the information on the images stored in the storage media is displayed vertically in a column of the corresponding identification names of the storage media. Alternatively the identification names of the storage media may be displayed in a second alignment manner in which the identification names of the storage media are vertically displayed and the information on the images stored in the storage media is horizontally in a row of the corresponding identification names of the storage media.

When two and more images are stored in the storage media the control unit may determine a display order of the images according to an image date a file format a file name or exchangeable image file Exif information and may display the information on the images according to the determined display order.

The storage medium managing unit may verify a storage medium s connection to or disconnection from the image forming apparatus. The control unit may arrange the size of a display area for displaying information of one image according to the number of storage media included in or connected to the image forming apparatus when the result of the verification indicates that a storage medium has been connected to or disconnected from the image forming apparatus.

According to another aspect of an exemplary embodiment of the present invention a method of controlling a plurality of storage media included in or connected to an image forming apparatus is provided Each controller controlling the plurality of storage media is independently configured and the plurality of storage media is concurrently accessed using the configured controllers to read data stored in the storage media or write the data to the storage media.

According to an exemplary implementation the plurality of storage media may comprise a hard disk a memory card a universal serial bus USB memory stick or a card reader.

According to anther aspect of an exemplary embodiment of the present invention a device for controlling a plurality of storage media included in or connected to an image forming apparatus is provided. A file system for the storage media stores information required for controlling the storage media. A driver for the storage media generates signals for controlling the storage media. A controller for the storage media controls the storage media using the generated signals wherein the plurality of storage media is controlled concurrently.

According to an exemplary implementation the information required for controlling the storage media may include location information of files stored in the storage media capacity of the storage media or sector size.

The file systems the drivers and the controllers for the storage media may be independent from one other.

An exemplary embodiment of the present invention also provides a computer readable medium comprising a computer program for executing the method of managing images and the method of controlling storage media.

Other objects advantages and salient features of the invention will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses exemplary embodiments of the invention.

Throughout the drawings the same drawing reference numerals will be understood to refer to the same elements features and structures.

The matters defined in the description such as a detailed construction and elements are provided to assist in a comprehensive understanding of the embodiments of the invention. Accordingly those of ordinary skill in the art will recognize that various changes and modifications of the embodiments described herein can be made without departing from the scope and spirit of the invention. Also descriptions of well known functions and constructions are omitted for clarity and conciseness.

Hereinafter a method and device for managing images stored in a plurality of storage media included in or connected to an image forming apparatus and a method and device for concurrently controlling the plurality of storage media according to an exemplary embodiment of the present invention will be described in detail by explaining exemplary embodiments of the invention with reference to the attached drawings.

The storage medium managing unit accesses storage media included in an image forming apparatus connected to the image forming apparatus to read information of images stored in the plurality of storage media. For example the storage medium managing unit accesses first second and third external storage media and to read information of images stored in the plurality of storage media. Examples of the plurality of storage media include a hard disk included in the image forming apparatus a memory card connected to the image forming apparatus a universal serial bus USB memory stick and a card reader. The memory card may be a compact flash CF memory card a smart media SM memory card an extreme digital XD memory card a memory stick MS a secure digital SD memory card and a multimedia card MMC .

Image information read from the storage media may include information on an image file and an image attribute. The image attribute information may include an image file name a file format an image date an image size or exchangeable image file Exif information.

The control unit respectively determines identification names of the plurality of storage media. For example the control unit determines identification names of the first second and third storage media and and displays the determined identification names on the display unit step . The identification names for identifying the plurality of storage media may be a letter or a name.

The control unit links the image information which is read from the respective storage media with the identification names of the storage media and displays the image information on the display unit step . The displayed image information corresponding to the identification names may be a thumbnail image or a reduced image.

When a USB memory stick and a memory card are connected to the image forming apparatus the storage medium managing unit initializes the USB memory stick and the memory card under the control of the control unit and initializes the file system of the USB memory stick and the memory card using information on the storage media. The initializing operations may be performed concurrently.

The control unit determines the identification names of the hard disk the USB memory stick and the memory card which are included in or connected to the image forming apparatus step . The identification names may be determined using a manufacturer s name a product name or other information on the storage media.

The storage medium managing unit searches the hard disk to read image files stored in the hard disk step searches the USB memory stick to read image files stored in the USB memory stick step and searches the memory card to read image files stored in the memory card step . As illustrated in the steps and may be concurrently performed.

The control unit determines a display order of the image files read from the storage media step . The display order may be determined according to an image date a file format a file name or Exif information. For example if ten image files are read from the hard disk the display order of the ten image files may be displayed in the order of the image date. Image attribute information determining the display order may be included in the image files or may be read from each storage medium along with the image files.

Under the control of the control unit the display unit displays identification names of storage media and step links images read from the storage media and with the displayed identification names of each storage medium and displays the images in the order determined as described above step . The displayed images may be thumbnail images included in image files read from the storage media. Also image data read form the storage media may be reduced or enlarged according to the size of an image display area. The size of the image display area varies according to the number of images which are concurrently displayed on the display unit . Thus the control unit may estimate the size of a display area for one image and then enlarge or reduce the thumbnail images or the images read from the storage media according to the estimated size of the display area.

When the user selects any one of images displayed on the display unit through the user input unit the selected image is displayed on the whole screen of the display unit . For example as illustrated in if the user selects an image A the image A is displayed on the whole screen of the display unit .

The storage medium managing unit reads the selected image file from the storage media and the print unit prints the selected image using the read image file if printing is requested after any one of the displayed images is selected as described above.

When a new storage medium is connected to the image forming apparatus the storage medium managing unit initializes the new storage medium under the control of the control unit and initializes a file system of the storage medium using information on the storage medium. When the initializing operation is completed the control unit determines an identification name of the new storage medium and reads stored image files from the new storage medium through the storage medium managing unit . The control unit determines a display order of the read image files using the image attribute information. To update a display the control unit controls the display unit so the identification name of the new storage medium and the images stored in the new storage medium are displayed along with the identification names of the displayed storage media and the images stored in the storage media.

When the storage medium connected to the image forming apparatus is disconnected the storage medium managing unit deletes a file system of the removed storage medium and all stored information on the storage medium under the control of the control unit . To update the display the control unit controls the display unit so the identification name of the removed storage medium and the corresponding images are removed from the identification names of the displayed storage media.

The identification names of the displayed storage medium and information on the images corresponding to the storage medium may be stored in and managed by a temporary storage medium not shown included in the image forming apparatus . illustrates a data structure for managing identification names and image information of a plurality of storage media in the temporary storage medium not shown . According to an exemplary implementation the identification names of the storage media are linked using heads and the information on the images corresponding to the identification names are linked using tails connected to the heads. As illustrated in the storage media included in or connected to the image forming apparatus has its head at the same location. In each head information on the images stored in the corresponding storage media is linked using tails. In addition adjacent tails linked to different heads may be linked with each other. A link between image information stored in the same storage media is indicated by a solid line and a link between image information stored in the different storage media is indicated by a dotted line.

The image information stored in the different storage medium may be promptly transferred via the link between the image information stored in the different storage media. For example when information tail on the image A is accessed while information tail on the image B is accessed the information tail on the image A can be accessed via the tail through the dotted lined link without accessing the tail via a head and a head .

Although the identification names of the storage media are horizontally displayed and the information on the images stored in the storage media are vertically displayed in the aforementioned description the identification names of the storage media and the information on the images may be displayed in an opposite way. The user may choose whether the identification names of the storage media will be horizontally or vertically displayed.

In order to manage the images stored in the plurality of storage media included in or connected to the image forming apparatus through one display screen the plurality of storage media may be concurrently controlled. Namely the image data of the plurality of storage media may perform read write operations at the same time.

The central processing unit which controls overall operations of the image forming apparatus controls the USB control unit the user interface unit the DSP the print unit the first and second memory card control units and and the hard disk control unit . The user interface unit receives an input of a specific function or value and displays a screen for providing information through a display unit such as a liquid crystal display LCD . The DSP performs image processing for image data read from a storage medium and coverts the image data into a desired format of printable image data. The print unit prints the converted image data.

The USB control unit controls external storage media which use the USB memory stick connected to the image forming apparatus so that a USB storage medium is powered and initiated and data read write operations are then performed with respect to the USB storage medium.

The first and second memory card control units and verify whether a memory card is inserted into the first and second card slots and . This facilitates the initialization of the memory card and the performance of the data read write operations with respect to the memory card. The memory card connected to the image forming apparatus through the first and second card slots and may be a compact flash CF memory card a smart media SM memory card an extreme digital XD memory card a memory stick MS a secure digital SD memory card and a multimedia card MMC .

The hard disk control unit controls the hard disk included in the image forming apparatus so that the hard disk is initialized and data read write operations are then performed with respect to the hard disk .

As described above the plurality of storage media included in or connected to the image forming apparatus are respectively controlled by independent control units. The control units controlling the storage media are also operated in response to independent control signals without interference. The plurality of storage media included in or connected to the image forming apparatus may be concurrently controlled due to these independent control units.

Referring to the USB storage medium connected to the image forming apparatus a first memory card connected to the first card slot a second memory card connected to the second card slot and the hard disk are respectively controlled by independent control units including the USB control unit the first memory card control unit the second memory card control unit and the hard disk control unit . Control signals for controlling the control units and are independently generated by the central processing unit .

The control units and and the file systems the drivers and the controllers included in the control units are independently operated.

When the USB storage medium is connected to the image forming apparatus the first driver verifies device information of the connected USB storage medium through the first controller . The first driver then initializes the USB storage medium. In the initiating process the driver analyses attribute information on the USB storage medium such as capacity write protect sector size manufacturer and serial number. When read write operations are facilitated in the USB storage medium the driver provides an application programming interface API through which the USB storage medium is controlled and which has the attribute information on the storage medium.

An application initiates the first file system through the API. In the initiating process the first file system stores a file system configuration. For example the first file system stores necessary information such as file location memory card capacity and sector size for controlling the storage media.

When the initializing process is completed for the USB storage medium and the first file system a desired operation of the application is performed with respect to the USB storage medium. Specifically the first driver generates instruction signals for performing operations requested from the application according to a control sequence or a protocol of the connected USB storage medium. The first controller also performs the requested operations such as power supplying initializing and data read write operations in response to the generated instruction signals.

When a memory card is inserted into the first card slot the second driver supplies power to the inserted memory card and performs the initializing process so that the card can be accessed as in the case of the aforementioned USB storage medium. The second file system is initialized by the application . When the initializing process is completed the desired operation of the application can be performed with respect to the inserted memory card through the second driver and the second controller as in the case of the USB storage medium.

When the memory card is inserted into the second card slot power is supplied the memory card and the third file system are initialized and then the read write operations are performed with respect to the memory card.

The fourth driver supplies power to the hard disk and performs the initializing process. The application initializes the fourth file system . When the initializing process is completed the hard disk can be controlled.

Initializing operations and instruction signal generating operations for each of the first second third and fourth drivers and are independently performed without interference. Also initializing operations and instruction signal generating operations of the application for each of the first second third and fourth file systems and are independently performed without interference. Also data read write operations of the first second third and fourth controller and for the storage media are independently performed without interference.

The plurality of storage media included in or connected to the image forming apparatus may be concurrently controlled due to the independent file systems drivers and controllers for the storage media.

According to an exemplary embodiment of the present invention identification names of a plurality of storage media included in or connected to an image forming apparatus are displayed by linking information on images with the identification names. This facilitates the management of the images stored in the storage media. Therefore a user can conveniently and promptly recognize and manage the storage media and the images stored in the storage media.

The invention may also be embodied as computer readable codes on a computer readable recording medium. The computer readable recording medium is any data storage device that can store data which may be subsequently read by a computer system. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks optical data storage devices and carrier waves such as data transmission through the Internet . The computer readable recording medium can also be distributed over network coupled computer systems to facilitate the storage and execution in a distributed fashion of the computer readable code. Also functional programs codes and code segments for accomplishing exemplary embodiments of the present invention can be easily construed by programmers skilled in the art to which the present invention pertains.

While the present invention has been particularly shown and described with reference to certain exemplary embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the appended claims and their equivalents.

