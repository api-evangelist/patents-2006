---

title: Image processing apparatus and image processing method
abstract: A rendering of objects described by description language into bitmap data is performed. As color space compression, the bitmap data in which the rendering has been performed is compressed in a color reproduction range.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07920308&OS=07920308&RS=07920308
owner: Canon Kabushiki Kaisha
number: 07920308
owner_city: Tokyo
owner_country: JP
publication_date: 20060602
---
The present invention relates to a technique for applying a gamut mapping processing to each inputted object and outputting it.

Though a user expects that a color reproduced on a monitor is perceptually identical to a color of an image outputted by a printer it is very difficult for a color reproduction technique to have a color image on the monitor perceptually identical to the image outputted by the printer. A main cause of this is that a color gamut of the monitor and a color gamut of the printer are different.

Therefore in order to contemplate the perceptual identity of displayed color images between such display media having different color gamuts a technique for having one color gamut correspond to another color gamut in a uniform color specification system is required. Actually in order to fit one color gamut into another color reproduction range its color space is compressed. This color space compression is referred to as Gamut Mapping and a gamut mapping method for realizing this is referred to as Gamut Mapping Algorithm GMA .

For GMA various methods have been designed such as a method for mapping of a color reproduction in a state where a chroma is maintained as shown in a method for mapping of the color reproduction with a lightness being maintained as shown in and the like.

For processes of the GMA there are three types of processes Perceptual generally for outputting a photo image in which maintaining a relationship of tones is prioritized over a precise color reproduction of the image Colorimetric for reproducing a logo and the like faithfully and Saturation intended to maintain a bright impression of the original color without a high regard for a hue precision for vibrantly outputting a pie chart or characters. For color matching data for implementing these three types of methods in an example of a printer profile as shown in a transformation LUT Look Up Table from Lab to printer CMYK is prepared for each method of these three types and the LUT corresponding to the GMA information which has been set is selected to be used for the color matching.

Moreover the printer engine is configured with a communication I F unit for exchanging the data with the front end server and an output unit for performing a print.

Next the PDL interpreter unit generates the intermediate data from the PDL data including the color data on which the GMA process has been performed at the color management processing unit and stores the intermediate data in the intermediate data storage unit S Next the rendering unit expands the intermediate data in the intermediate data storage unit into the bitmap image data and stores the bitmap image data in the bitmap storage unit S . Then the bitmap image data is transformed into the printer CMYK S . Finally the expanded bitmap image data is transferred to the printer engine via the communication I F unit and the print is performed by the output unit of the printer engine S .

In this way conventionally since the GMA process is performed prior to the rendering there has been a characteristic in which the color space of the rendering is the color space within the color reproduction of the device printer .

Here using details of the GMA process With respect to the color data of the object in the PDL data at S as shown in will be described. is a flowchart showing the details of the GMA process with respect to the color data of the object in the PDL data.

First it is determined whether the object attribute in the PDL data is an image or not S . If the object attribute is an image the GMA information selected for the image is set to a Flag S and the GMA process is performed S . Moreover if the object attribute is not an image but vector graphics YES at S the GMA information selected for vector graphics is set to the Flag S and the GMA process is performed S .

On the contrary if the object attribute is not an image or vector graphics but text YES at S the GMA information selected for the text is set to the Flag S and the GMA process is performed S . While the object exists YES at S the above described process is repeated and when there is not any object to be processed NO at S this process is terminated.

Here using the details of the GMA process at S S and S as shown in will be described. is a flowchart showing the details of the GMA process.

First the source profile selected now is extracted S and the destination profile is extracted S . Next the type of GMA selected now any one of the above described Perceptual Colorimetric and Saturation is set to a Rendering intent flag S . Then the source profile and the destination profile as well as the Rendering intent flag which has been set with the type of GMA are set to the CMM S and the color matching process of the CMM is performed S .

A conventional color management system of color image data for example U.S. Pat. No. 6 603 483 Japanese Patent Laid Open 2001 218079 will be briefly described.

Moreover the color transformation module also has three components the transformation parameter input image data and output image data with respect to the above described API. Here the transformation parameter indicates the storage location in which the color transformation sequence created by the transformation sequence creation module is arranged. The input image data is color image data transformed with the color transformation sequence corresponding to the transformation parameter by the user. The output image data is the color image data which has been transformed with the color transformation sequence based on the transformation parameter.

In this way the user utilizes the transformation sequence creation module to generate the color transformation sequence based on the profile list and the GMA list applies the color transformation sequence to the input image data and creates the output image data through the color transformation .

It should be noted that the color profile representatively relates to a particular image device such as the printer a scanner the monitor a digital camera and the like. Here the color profile corresponding to the particular device is referred to as device color profile .

As shown in the color profile is configured with a color appearance transformation a color gamut boundary descriptor and a linearization table . First the color appearance transformation is used to transform the color image data from a device color space corresponding to the device to which the color profile relates into a device independent color space. Also the color appearance transformation is used to inversely transform the color image data from the device independent color space into a device dependent color space.

Next the color gamut boundary descriptor is used to define a color gamut boundary of a color image device to which the color profile corresponds. Thereby it is possible to map the color image data so that the color image data after mapping does not go out of the reproducible color gamut boundary of the color image device providing the mapped color image data by the gamut mapping. As a result it is possible to render the color image data appropriately with the image device related to the color profile .

Next the linearization table includes one or more linearization tables which are utilized between the color appearance transformation and a gamut mapping transformation in order to access the color appearance transformation and the color gamut boundary descriptor respectively.

It should be noted that the color profile reference to the color profile reference N correspond to the individual color profile as shown in .

The GMA list has a plurality of reference entries including a GMA reference selected by the user such as a GMA reference to a GMA reference N .

The transformation sequence creation module acquires the color appearance transformation and the linearization table from the color profiles of the color profile references to . In order to create a color transformation sequence the transformation sequence creation module requires access to the color profiles and the GMAs . Moreover the GMAs correspond to the GMAs of respective types which are treated as references in the GMA references to .

Here the transformation sequence creation module generates the color transformation sequence based on the color profile list the GMA list the color profiles and the GMAs . The color transformation sequence includes a transformation step for transforming the color image data according to the color transformation procedure.

First a profile step corresponds to the color appearance transformation acquired from the color profile in an input device which has provided the color image data and thereby maps the color image data from the color space of the input device to the device independent color space. Next a gamut mapping step corresponds to the first GMA reference of the GMA list that is the GMA reference in this case. The transformation sequence creation module determines whether or not the transformation step should be created for each color profile reference of the color profile list and for each GMA reference of the GMA list .

Finally a profile step is created if the last color profile reference that is the color profile reference N corresponds to the device color profile.

As shown in the profile step includes a color appearance transformation and table . In this way when the profile step is applied to the color image data the profile step has data required for transforming the color image data appropriately and copies an appropriate color appearance transformation and a corresponding table from the appropriate color profile. Here the color appearance transformation and table is configured with the data acquired from the color appearance transformation and the linearization table as shown in .

Here the color appearance transformation and table includes a color space transformation a first pair of one dimensional look up tables a 3 3 matrix a second pair of one dimensional look up tables a multi dimensional look up table a third pair of one dimensional look up tables and a second color space transformation. In this way the profile step includes the data required for mapping the color image data into the device independent color space and for mapping the color image data from the device independent color space.

It should be noted that the profile step does not necessarily use all the above described transformations and tables. For example the input image data from the monitor is transformed from CIE XYZ space into CIE JCh space using the first pair of one dimensional look up tables followed by the 3 3 matrix and the color space transformation and other steps are not performed. On the contrary on outputting the color image data to the monitor the color space transformation for transforming from the JCh color space into the XYZ color space would be used subsequently the 3 3 matrix would be used and furthermore the second pair of one dimensional look up tables would be used.

A transformation step bit field configures a mechanism for indicating which is specified and required among the above described elements by the profile step .

It should be noted that the GMA pointer may identify a specific type of GMA by use of another appropriate means such as identifying the GMA with its name. It can be seen that other gamut mapping step may also include the GMA pointer for indicating another type of GMA which is indicated by the user at the GMA references to included in the GMA list . In this way the user can control which type of GMA should be applied at a predetermined point of time in the color transformation sequence .

The gamut mapping step further includes gamut mapping data including a data block which is required for the specific type of GMA indicated by the GMA pointer in order to execute the gamut mapping. The gamut mapping data is obtained from the color profiles and preferably includes both an input color gamut boundary descriptor and an output color gamut boundary descriptor corresponding to the input device and an output device for which the gamut mapping step maps the color image data.

For example one specific GMA has an initialization routine for setting up all information required by the specific GMA. This initialization data is preferably provided also for the gamut mapping data . Since the input color gamut boundary descriptor and the output color gamut boundary descriptor exist the efficiency of the gamut mapping step improves when the specific GMA is applied to the color image data.

Next the GMA step is applied to the input image data and the input image data is gamut mapped into the indicated color gamut boundary. The GMA step utilizes the GMAs provided from the color management module . The GMAs utilize the color gamut boundary descriptors of an input color space and an output color space in order to execute the gamut mapping correctly.

The profile step transforms the input image data from the device independent color space such as the JCh to the device dependent color space corresponding to the output device such as the RGB and generates the output image data .

Next the transformation step bit field is accessed from the profile step and decoded and it is determined which transformation and table should be utilized in this specific profile step such as a one dimensional table included in the color appearance transformation and table S . Next according to the determination an appropriate transformation is applied to the input image data S .

Moreover at step S if it is determined that the transformation step is the GMA step the GMA pointer as well as the input color gamut boundary descriptor and the output color gamut boundary descriptor are accessed from the GMA step S .

As described above the GMA pointer is utilized in order to access the appropriate GMA to be applied to the input image data. Conventionally in the appropriate GMA values which have been previously designated by the user are held in the intermediate data and attribute information.

Next the appropriate GMA is applied to the input image data using the color gamut boundary descriptor S . Then it is determined whether or not the transformation step to be processed remains in the color transformation sequence S Here if the transformation step to be processed remains the process returns to S. While the transformation step to be processed exists the process repeats S to S. If no transformation step exists this process is terminated.

In this way the user can control selection of available GMA through the color transformation sequence. And the user can perform a highly accurate color reproduction by performing a flexible gamut mapping which utilizes the color gamut boundary descriptors of the input color space and the output color space at the point of time when the gamut mapping is executed.

The above described print process is assumed to output to an existing PDL Page Description language such as PCL PostSCript and the like.

On the other hand a graphic format with a high regard for the display of a graphic design to the monitor such as SVG has been used. The SVG which is an abbreviation of Scalable Vector Graphic is a standard for describing a two dimensional graphic in an XML format. Moreover the SVG is a drawing method for dealing with graphics as numerical data for representing lines or curves instead of as a collection of dots and stores the image as coordinates of the lines and a collection of angles and directions. For that purpose the drawn graphics may be freely processed such as movement inversion enlargement reduction and the like and also have small data capacity.

In the SVG there are three types of objects an image a vector graphic and a text. The SVG is an advanced application and it is possible to use the SVG to utilize rich and graphical functions. As representative of the functions an blending and a gradation are cited.

The blending is a technique which is also known as a translucent copy. This process performs an operation by adding two color values in the color space in which the rendering is performed depending on an a value opacity . Assuming that a basic expression has the RGB as an blending result RGB1 as a transferring RGB RGB2 as a transferred RGB and an as the value 0.0 1.0 results in the following expression 12 1 .

On the other hand the gradation performs an operation in which a linear interpolation is discretely performed between the two color values in the color space in which the rendering is performed.

The following processes are performed in a case where a web designer performs a web design on the monitor using the blending function of the above described SVG. First the blending function is implemented in a rendering color space for example a RGB color space such as the sRGB specified in an operating system OS and then the RGB data of that rendering color space would be color matching transformed into monitor RGB to be displayed.

In other words after the process of blending is performed in a device independent rendering color space SRGB the data is transformed into a monitor RGB color space which is the device color space.

However in the color matching by means of the above described conventional ICC profile as described above since it is not possible to perform the matching based on color space information of the input device and the process is to be uniformly performed even if input color data comes from the device of whatever color gamut the input color data is transformed into Jch or L a b of CIE and the color matching is performed there has been a limit in improving color matching accuracy.

Moreover on applying the color matching by means of the ICC profile to the PDL data and outputting it to the printer as shown in rendering processing of the blending is generally performed by performing gamut mapping first processing to the color gamut of the output device and then by performing processing second processing for obtaining color after the blending. However it is not easy to replace blending data of application software by blending function of PDL because of data structure in comparison with SVG whether the PDL has blending function or not. It should be noted that it is easy to look for blending objects because the SVG is described by XML and is structured data tree structure and tag . Therefore utilizing the blending function of PDL was less than the SVG. Accordingly it does not become something of a problem because performing the first processing and the second processing is not the rule.

However in the case where the blending function is more commonly used for web design such as the above described SVG if the gamut mapping is performed before the rendering a problem occurs in which appearance would be different between the monitor display and the printer output at a portion of the blending.

The present invention is made in order to solve the above described problems and it is an object of the present invention to realize preferred color reproducibility when a rendering and color space compression gamut mapping are performed for objects described by a description language.

In order to attain the above described object according to an embodiment of the present invention an image processing apparatus comprising rendering means for performing a rendering of objects described by description language into bitmap data and color space compression means for performing in a color reproduction range color space compression of the bitmap data in which the rendering has been performed is provided.

Moreover according to an embodiment of the present invention an image processing method comprising a rendering step of performing a rendering of objects described by description language into bitmap data and a color space compression step of performing in a color reproduction range color space compression of the bitmap data in which the rendering has been performed is provided.

Other objects of the present invention will be apparent with the following drawings and a detailed description described below.

Hereinafter the best embodiment for practicing the present invention will be described in detail with reference to the drawings.

It should be noted that in the embodiment a new color matching process is incorporated in a print process instead of a color matching process by means of an ICC profile. As shown in a new print mechanism will be described in which a rendering of an blending is performed in a color gamut rendering color reproduction range broader than a color reproduction range of a printer and subsequently color gamut is compressed into a color gamut of an output device.

Moreover the printer engine is configured with a communication I F unit for exchanging the data with the front end server and an output unit for performing the print.

Next the rendering unit expands the stored intermediate data into the bitmap image data and stores the bitmap image data in the bitmap storage unit S . Here the color management processing unit performs a GMA process with respect to the stored bitmap image data S . Finally the expanded bitmap image data is transferred to the printer engine and the print is performed S .

In the mechanism shown in it is possible to introduce a mechanism for performing the GMA process after implementing an blending function in a rendering color space.

Next based on the color gamut boundary descriptors of the input and output color spaces a Colorimetric gamut mapping step is executed S . Next a color profile of the rendering color space is extracted S and the profile step is executed based on the color profile of the rendering color space S . Then other information in the object data is analyzed and transformed into the intermediate data S and the object attribute information is added to the attribute information of the intermediate data S .

Next color gamut boundary descriptor information of the input color space is added to the attribute information of the intermediate data S . Then the GMA information with respect to the object attribute which has been set at the color management setting unit is extracted S and the GMA information is added to the attribute information of the intermediate data S . Then the intermediate data is stored in the intermediate data storage unit together with the attribute information S and while the object to be processed exists YES at S the process of the above described S to S is repeated. Thereafter when there is not any object No at S this process is terminated.

In this way based on the color profile which has been set with respect to each object in a document and the color profile of the rendering color space it is possible to perform a color measuring color space transformation on color space data of the input into the rendering color space and to set the object attribute the color gamut boundary descriptor of the input color space and the GMA information as the attribute information in the intermediate data.

In this way it is possible to expand the intermediate data into the bitmap image data and to set the object attribute the color gamut boundary descriptor of the input color space and the GMA information as the attribute information with respect to each pixel configuring the bitmap image data.

Next a GMA pointer corresponding to the GMA information is extracted S and the gamut mapping step of the GMA information is executed based on the color gamut boundary descriptors of the input and output color spaces S . Finally the color profile of the printer is extracted S and the profile step is executed based on the color profile of the printer S . While the pixel data exists YES at S the process of the above described S to S is repeated. When there is not any pixel data No at S this process is terminated.

In this way using the object attribute the color gamut boundary descriptor of the input color space and the GMA information as the attribute information with respect to each pixel of the expanded bitmap image data it is possible to perform the gamut mapping processing from the rendering color space data into color space data of the printer with respect to the color profiles of the rendering color space and the printer.

According to this embodiment it is possible to approximate a monitor display and an appearance of a printer output at a portion of the blending compared to a conventional process by introducing the mechanism for performing the gamut mapping after implementing the blending function in the rendering color space.

Furthermore compared to the color matching using the ICC profile since it becomes possible to perform the color matching based on the color space information of the input and output devices a print output with an improved matching accuracy can be expected.

Next a modification example of this embodiment will be described in detail with reference to the drawings. In the above described embodiment the case has been described by way of example where the blending is performed with respect to two colors of the same a value in the color space in which the rendering is performed before data compression is performed in the color reproduction range. However in the modification example as shown in the case will be described by way of example where the blending is performed with respect to a color C having the value of A1 and a color C having the a value of A2. In this case a blending color at an overlapping portion can be represented with the following expression C1 A1 1 A2 C2 A2.

Here as shown in an object having the color C is raster image data shot by a digital camera and the raster image data is image data of Adobe RGB color space. A gamut mapping method is designated at GMA. An object having the color C is vector graphics data of sRGB and gamut mapping method of this object is designated at GMA. The case of the blending between the objects having colors and will be considered.

In the case of this modification example it becomes problematic which GMA and which color gamut can appropriately process a portion on which a pixel process of the blending is performed.

With respect to the GMA which can appropriately process the portion on which the pixel process of the blending is performed as shown in a user interface is provided in which the user can select an appropriate GMA among a plurality of GMAs and a mechanism is provided for applying the selected GMA with respect to the data after the rendering.

Moreover in order to appropriately process the blending of color and color in units of pixel the process in units of pixel is implemented in the rendering color space. Because if color spaces of two colors differ each other it is unclear whether or not a result of the blending surely enters the color gamut designated at each object. For example there is a case where a result of the blending does not enter the color gamut of sRGB when the color is Adobe RGB and the color is sRGB.

It should be noted that a configuration of the modification example is similar to the configuration described with in the above described embodiment and therefore the description of the configuration of the modification example is omitted.

The attachment information as shown in is configured with data for indicating the type of the object GMA information which has been set at the color management setting unit with the UI shown in and color gamut boundary descriptor information of the input color space .

Next the image output process using the front end server and the printer engine in the modification example will be described.

It should be noted that the image output process is similar to the process described with in the above described embodiment and thereby only points of difference will be described here.

On the contrary if the pixel process has not been performed the process of S and S is not performed and the process proceeds to the next process. Then the object attribute information the color gamut boundary descriptor information of the input color space and the GMA information are added to the attribute information corresponding to each pixel S . While the pixel to be processed exists the above described process of S to S is repeated S and when there is not any pixel the process proceeds to the next process. Here the bitmap image data is stored in the bitmap storage unit together with the attribute information S . Then while the object to be processed exists YES at S the above described process of S to S is repeated and when there is not any object NO at S this process is terminated.

In this way it is possible to expand the intermediate data into the bitmap image data and to set the object attribute the color gamut boundary descriptor of the input color space and the GMA information as the attribute information with respect to each pixel configuring the bitmap image data.

According to the modification example since it becomes possible to use the GMA and the color gamut which can appropriately process the portion on which the pixel process of the blending is performed it becomes possible to more approximate the monitor display and the appearance of the printer output at the portion of the blending.

It should be noted that the present invention may be applied to a system configured with a plurality of devices for example a host computer an interface device a reader the printer and the like or applied to an apparatus consisting of one device for example a copying machine a facsimile machine and the like .

Moreover of course the object of the present invention is also attained by supplying a recording medium having recorded thereon a program code of software for realizing the functions of the above described embodiment to the system or the apparatus and reading and executing the program code stored on the recording medium by the computer a CPU or an MPU of the system or the apparatus.

In this case the program code itself read from the recording medium would realize the functions of the above described embodiment and the recording medium having recorded thereon the program code would configure the present invention.

For the recording medium for supplying this program code for example it is possible to use a floppy disk a hard disk an optical disk a magneto optical disk a CD ROM a CD R a magnetic tape a non volatile memory card a ROM and the like.

Moreover of course not only the case where the functions of the above described embodiment are realized by executing the read program code by the computer but also the case is included where an operating system OS operating on the computer or the like performs some or all of actual processes based on instructions of the program code and the functions of the above described embodiment are realized by the processes.

Furthermore of course the case is also included where after the program code read from the recording medium is written into a function expansion board inserted into the computer or a memory provided on a function expansion unit connected to the computer the CPU or the like provided on the function expansion board or the function expansion unit performs some or all of actual processes based on the instructions of the program code and the functions of the above described embodiment are realized by the processes.

According to the present invention it is possible to match the color gamuts of the input and output devices with respect to the overlapping portion of the objects having different colors.

Although the present invention has been described above with preferred examples the present invention is not limited to the above described examples and various modifications are possible within the scope of the claims.

This application claims the benefit of Japanese Patent Application No. 2005 167349 filed on Jun. 7 2005 which is hereby incorporated by reference herein in its entirety.

