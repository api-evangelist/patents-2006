---

title: Document layout verification
abstract: A test document is parsed into components which may include bounding boxes, segments, and points. Test code makes calls to properties and methods of components in order to verify document layout. Rather than take absolute measurements of component placement, components are evaluated relative to each other. Layout verification logic may be part of a larger software test system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07756333&OS=07756333&RS=07756333
owner: Microsoft Corporation
number: 07756333
owner_city: Redmond
owner_country: US
publication_date: 20060426
---
In enterprises which design and implement computer software testing that software can be a tortuous process. As software applications increase in size and complexity an enterprise may automate the process of software testing ensuring that incremental software builds work the way they are intended. Using a computer to test software presents a challenge in determining whether application output was properly generated. In the case of applications which work with documents as data testing application output may involve verifying that the layout of an outputted document is proper.

Existing solutions for verifying the layout of a document created by a software application may include using methods which are inefficient and which may lead to unwanted false negative and or false positive test results. These methods may include having a person view a document in comparison to a model or master document. Other methods may involve a software module analyzing a test document against a master document perhaps by performing a pixel by pixel analysis. Other methods may involve the comparison of properties of components e.g. graphics text etc on a test document to the properties of objects on a master document.

This summary is provided to introduce a selection of concepts in a simplified form that are further described below in the detailed description. This summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended as an aid in determining the scope of the claimed subject matter.

Embodiments provide for verifying a test document produced by a software application. Objects on the test document are parsed into components which provide methods and properties used by test code. Methods perform relative comparisons between components in order to determine a preferred result.

These and other features and advantages will be apparent from a reading of the following detailed description and a review of the associated drawings. It is to be understood that both the foregoing general description and the following detailed description are explanatory only and are not restrictive of the invention as claimed.

A software test application may automate the test process utilizing aliases or indirect references to files in order to abstract their location and prevent problems associated with hard coded file locations. Additional functionality helps for testing by providing multiple prioritized locations where a file may be found.

With reference to an embodiment may include a computing device such as computing device . In a basic configuration computer device may include at least one processing unit and memory . Depending on the configuration of the computer device memory may be volatile e.g. Random Access Memory RAM non volatile e.g. Read Only Memory ROM Flash etc. or some combination thereof. Memory may serve as a storage location for operating system one or more applications and may include program data as well as other programs. In some embodiments applications may include test application and or software application . Test application may include layout verification logic .

Although the basic computing device configuration is contained within dashed line box computing device may include additional features and functionality. For example computing device may include additional data storage components including both removable storage e.g. floppy disks memory cards compact disc CD ROMs digital video discs DVDs external hard drives universal serial bus USB key drives etc. and non removable storage e.g. magnetic hard drives .

Computer storage media may include media implemented in any method or technology for storage of information including computer readable instructions data structures program modules or other data. Memory removable storage and non removable storage are all examples of computer storage media. Further examples of such media include RAM ROM electrically erasable programmable ROM EEPROM flash memory CD ROM DVD cassettes magnetic tape magnetic disks and so forth. Any such computer storage media may be accessed by components which are a part of computing device or which are external to computing device and connected via a communications link e.g. Bluetooth USB parallel serial infrared etc. . Computing device may also include input devices such as keyboards mice pens microphone touchpad touch display etc. Output devices may include displays speakers printers and so forth. Additional forms of storage input and output devices may be utilized.

Computing device may also include one or more communication connections which allow the computing device to communicate with other computing devices such as over a network e.g. a local area network LAN the Internet etc. . Communication media in the form of computer readable instructions data structures program modules or other data in a modulated data signal may be shared with and by device via communication connection . Modulated data signal may mean a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal and may include a modulated carrier wave or other transport mechanism. Communication connection may be comprised of hardware and or software enabling either a wired e.g. Ethernet USB Token Ring modem etc. or wireless e.g. WiFi WiMax cellular acoustic infrared radio frequency RF etc. communication conduit with other devices .

In some embodiments tests developed on tester machine may be managed and or transferred to test clients using test automation system . Test automation system may minimally include a tester interface a data store and a test controller . Tester interface may be operated as a local software client on tester machine . Tester interface may also be operated via a separate server not shown and accessed via a network connection. Tester interface may be accessed by a tester using a web browser. A tester may utilize tester interface to upload test files including test scripts or code helper files compiled code and so forth. A tester may only upload some or all of the files required for a test. The files may be stored in data store or in other locations. Tester interface may allow a tester to specify parameters for a test run including operating system processor build number number of test clients helper files expected results and so forth. Tester interface may further allow a tester and others to initiate a test run and to view and analyze results of a particular test run.

Data store may be composed of a database system including a relational database an object database or some other form of database e.g. text files spreadsheets etc. . Data store may reside on the same machine as tester interface including tester machine itself . Data store need not be composed of a single database but may encompass multiple databases files servers and locations. Data store may store the test run parameters as indicated above and may also store files and data required for a test run. Further data store may store information about test clients including platform specifications and information about past and future test runs. Data store may also store the results of tests including test data or files outputted by a test run or performance indicators such as successful completion and time to completion.

Test controller may reside on the same machine as data store including tester machine or may reside on separate machines in communication with data store and tester interface using a network connection. Other configurations may be available. In a given test environment more than one test controller may be utilized to dispatch test runs. For example a given test controller may be responsible for test runs on a particular subset of available test clients . Test controller may initiate and track test runs as provided by a tester via tester interface . Test controller may copy all information and files to test clients or may simply pass along a minimal amount of information and allow test clients to individually copy required files before initiating a test. During and upon completion of a test each test client may supply feedback and results to test controller which may in turn store feedback and results in data store . Likewise test controller may also communicate to tester interface that a test is running and or complete so that a tester can be notified of test status.

Although depicted as separate computers in it should be noted that tester machine test automation system and test clients may all be collocated on the same computer. In addition the test automation system described here is intended merely as an example. Other test schemes and test environments may also be utilized to implement the subject of the appended claims.

Layout verification logic may be located with test application in memory on test client where it may be used to verify the layout of a document produced or modified by software application . Layout verification logic may also be found on other computers including tester computer where it may be used in the course of designing a test script for use in conjunction with test application . The logic may be accessed through an application programming interface API . The API may be utilized through an object oriented programming environment or via other programming platforms.

Here document may be stored in volatile memory within test client or in non volatile storage such as a hard drive. Document may be formatted as a rasterized image e.g. bitmap a vector graphic e.g. scalable vector graphic SVG a markup language document e.g. Hypertext Markup Language HTML or another format which includes information sufficient to replicate the document. Prior to verifying the layout of document the document may be converted from one format to another. Examples of such conversions include converting a proprietary word processing document format to an extensible markup language XML format scanning a rasterized format e.g. a screen capture in order to recognize and store information about the components of document and loading a drawing file from non volatile memory and extracting information about the components which are found on document for storage in volatile memory.

Document components may include any distinct item appearing on document . The layout of components on document constitutes a structure similar to an organizational chart. Here each oval e.g. oval represents a distinct component. Connecting segments e.g. segment AB also represent distinct components. Although distinct in this representation components need not be whole objects as depicted here but may include portions of objects or collections of multiple objects.

Prior to utilizing layout verification logic document may be parsed into components including ovals and segments. In determining components data underlying a document representation may be examined in order to extract information about components e.g. name size position color etc . This underlying data may be in the form of XML formatted object descriptions or other types of object descriptions. Alternatively component information may be extracted by analyzing the pixels points or other graphical unit of a displayable or printable version of document . Optical recognition algorithms may be used to distinguish components from each other and reconstruct underlying data about objects.

Once components are distinguished each component may be evaluated to determine a set of common features for use by verification functions. These common features may include a bounding box segments and points of interest. A bounding box may be represented by a rectangle sized to the outermost points of a particular component. For example oval has a bounding box as shown. Segments associated with oval may include the four sides of bounding box . And points of interest associated with oval may include corner point as well as other points such as a center point associated with the component. Other features associated with components may include an object identifier or name object text e.g. A in the case of oval color fill pattern and so forth. Verification functions may work with bounding boxes segments and points along with other objects when determining whether the layout of document is proper. Verification functions may deal with all components generally and may also include component type specific functions which may be evaluated using for example shape specific geometry.

The document s determined components may be exposed to test application as a collection of programming objects for use by layout verification logic . Each programming object may include a series of methods for use by layout verification logic . These methods may be utilized to compare component properties relative to each other to ensure alignment position etc. are proper. Using relative property values enables layout verification to be self contained in that the use of a model document is not needed. This may prevent false negatives when absolute values are not required to be exact and rather relative positioning of components provides adequate test results. This may also enable one test script to be written which works across products builds versions operating systems hardware platforms screen and or print resolutions and so forth. Such methods may be used alone to verify document layout or may be used in conjunction with other verification methods.

In the context of document object methods associated with components may be utilized by layout verification logic to verify document layout. A test script author can utilize components and their associated object methods to write test code which verifies placement of objects relative to each other among other verification methods. Examples of object methods are provided below.

When parsing the components of document a collection of components may be created which are accessible by test code. These components may come in several classes or varieties including LayoutElements collection LayoutElement Boundingbox Segment and Point. The class names provided are used as examples and other names and class types may be utilized.

A LayoutElements collection serves as a collector class for the LayoutElement class. Instances of LayoutElements may provide properties and methods for searching and filtering LayoutElement instances. The listing below presents examples of class properties and or methods available via a LayoutElements collection. Unless otherwise stated methods return instances or arrays of instances of the classes preceding the method name. The listing presents only a partial list of methods and or properties available from the LayoutElements collection.

LayoutElement BottomMost get returns the bottommost element in the collection. Bottommost and other functions may be evaluated as against the position on the document independent of whether coordinate values increases or decreases top to bottom.

bool AreAbove LayoutElement elements returns true or false indicating whether the elements in the collection are above the array of elements passed in. This function may be evaluated by determining whether the bottommost points of each of the elements in the collection are above the topmost point of each of the array of elements passed in. Other similar functions may be evaluated in a similar fashion. In an alternative embodiment this function and similar functions may be evaluated using the relative location of center points only.

bool AreBelow LayoutElement elements returns true or false indicating whether the elements in the collection are below the array of elements passed in.

bool AreCenterAligned Slope slope double maxDeviation returns true or false indicating whether the centers of the elements in the collection are aligned within a specified deviation amount along a line parallel to the slope. The maxDeviation value may be a decimal or an integer and may vary depending on the unit being used by the hardware platform operating system or software application being tested.

bool AreLeftOf LayoutElement elements returns true or false indicating whether the elements in the collection are to the left of the array of elements passed in.

bool AreRightOf LayoutElement elements returns true or false indicating whether the elements in the collection are to the right of the array of elements passed in.

bool Contains LayoutElement value returns true or false indicating whether the passed in value is a member of this collection of elements.

LayoutElements ElementsCoincidentWith Boundingbox box returns a sub collection of elements from the collection which are completely or partially contained within the passed in bounding box.

LayoutElements ElementsContainedWithin Boundingbox box returns a sub collection of elements from the collection which are completely contained within the passed in bounding box.

LayoutElements ElementsWithAreaLargerThan LayoutElement subject returns a sub collection of elements from the collection which have areas larger than that of the subject. Area for this and other functions below may include the area of a component shape or the area of the component s bounding box.

LayoutElements ElementsWithAreaSmallerThan LayoutElement subject returns a sub collection of elements from the collection which have areas smaller than that of the subject.

LayoutElements ElementsWithHeightGreaterThan LayoutElement subject returns a sub collection of elements from the collection which have a height greater than that of the subject.

LayoutElements ElementsWithHeightLessThan LayoutElement subject returns a sub collection of elements from the collection which have a height less than that of the subject.

LayoutElements ElementsWithWidthGreaterThan LayoutElement subject returns a sub collection of elements from the collection which have a width greater than that of the subject.

LayoutElements ElementsWithWidthLessThan LayoutElement subject returns a sub collection of elements from the collection which have a width greater than that of the subject.

LayoutElements GetElementsNameContains string name returns a sub collection of elements from the collection which have a name containing the string. This function may or may not consider case sensitivity when determining string containment.

A LayoutElement may consist of a Boundingbox with the addition of a unique identifier and or a name. As such the LayoutElement class may extend the Boundingbox class. A name may be determined based on any labels or properties applied to the object in question. A Boundingbox may represent a boundary surrounding the object such as box . A Boundingbox may be composed of four Segments connected to form a quadrangle and the quadrangle may be aligned with coordinate axes such that each set of opposing sides are parallel to one of the axes. A Boundingbox class may provide properties and methods for accessing Segments Points and other Boundingboxes associated with the underlying object in addition to other relevant methods for comparing instances of Boundingbox and providing information such as height width area and so forth.

The listing below presents examples of class properties and or methods available via a Boundingbox instance. Unless otherwise stated methods return instances or arrays of instances of the classes preceding the method name. The listing presents only a partial list of methods and or properties available for a Boundingbox instance.

bool Contains Boundingbox boxes returns true or false indicating whether the box fully contains all of the boxes passed in.

Boundingbox Intersection Boundingbox box returns a box representing the new box created by the overlap of two boxes.

bool IsAbove Boundingbox boxes returns true or false indicating whether the box is above all of the boxes passed in.

bool IsBelow Boundingbox boxes returns true or false indicating whether the box is below all of the boxes passed in.

bool IsBottomAlignedWith double maxDeviation Boundingbox boxes returns true or false indicating whether the box is aligned along the bottom side with the bottom sides of all of the boxes passed in within a certain deviation.

bool IsCenterAlignedWith Slope slope double maxDeviation Boundingbox boxes returns true or false indicating whether the box s center point is aligned along a line parallel to slope with all of the center points of the boxes passed in within a certain deviation.

bool IsLeftAlignedWith double maxDeviation Boundingbox boxes returns true or false indicating whether the box is aligned along the left side with the left sides of all of the boxes passed in within a certain deviation.

bool IsLeftOf Boundingbox boxes returns true or false indicating whether the box is to the left of all of the boxes passed in.

bool IsRightAlignedWith double maxDeviation Boundingbox boxes returns true or false indicating whether the box is aligned along the right side with the right sides of all of the boxes passed in within a certain deviation.

bool IsRightOf Boundingbox boxes returns true or false indicating whether the box is to the right of all of the boxes passed in.

bool IsTopAlignedWith double maxDeviation Boundingbox boxes returns true or false indicating whether the box is aligned along the top side with the top sides of all of the boxes passed in within a certain deviation.

As noted above a Boundingbox may consist of four Segments each representing a side of the box. A Segment class may provide properties and methods for accessing Segments Points and other objects associated with the underlying object in addition to other relevant methods for comparing instances of Segment and providing information such as length orientation and so forth. The listing below presents examples of class properties and or methods available via a Segment instance. Unless otherwise stated methods return instances or arrays of instances of the classes preceding the method name. The listing presents only a partial list of methods and or properties available for a Segment instance.

bool Includes Point points returns true or false indicating whether all the points in the array are included in the segment.

bool IsAbove Segment segments returns true or false indicating whether the segment is above all of the segments passed in.

bool IsBelow Segment segments returns true or false indicating whether the segment is below all of the segments passed in.

bool IsColinearWith double maxDeviation Segment segments returns true or false indicating whether the segment is collinear with all of the segments passed in within a certain max deviation. Collinear generally means falling upon the same line or in a state of alignment.

bool IsLeftOf Segment segments returns true or false indicating whether the segment is to the left of all of the segments passed in.

bool IsRightOf Segment segments returns true or false indicating whether the segment is to the right of all of the segments passed in.

Point PointAtX double x returns the point along the segment having an x coordinate matching the x value passed in.

Point PointAtY double y returns the point along the segment having an y coordinate matching the y value passed in.

double ShortestDistanceTo Point point returns a number representing the shortest distance between the segment and a nearby point.

Segments Boundingboxes and other components consist of a set of Points. A Point class may provide properties and methods for accessing Segments Points and other objects associated with the underlying point in addition to other relevant methods for comparing instances of Point. The listing below presents examples of class properties and or methods available via a Point instance. Unless otherwise stated methods return instances or arrays of instances of the classes preceding the method name. The listing presents only a partial list of methods and or properties available for a Point instance.

double DistanceFrom Point point returns a number representing the distance from the point to the point passed in.

double DistanceXFrom Point point returns a number representing the distance in the direction of the x axis from the point to the point passed in.

double DistanceYFrom Point point returns a number representing the distance in the direction of the y axis from the point to the point passed in.

bool IsAbove Point points returns true or false indicating whether the point is above all of the points passed in.

bool IsBelow Point points returns true or false indicating whether the point is below all of the points passed in.

bool IsColinearWith double maxDeviation Point points returns true or false indicating whether the point is colinear with all of the points passed in within a certain max deviation.

bool IsColinearWith Slope slope double maxDeviation Point points returns true or false indicating whether the point is colinear along a slope with all of the points passed in within a certain max deviation.

bool IsHorizontallyAlignedWith double maxDeviation Point points returns true or false indicating whether the point is horizontally aligned with all of the points passed in within a certain max deviation.

bool IsLeftOf Point points returns true or false indicating whether the point is to the left of all the points passed in.

bool IsRightOf Point points returns true or false indicating whether the point is to the right of all the points passed in.

bool IsVerticallyAlignedWith double maxDeviation Point points returns true or false indicating whether the point is vertically aligned with all of the points passed in within a certain max deviation.

Other objects classes and elements may be used to describe and or encapsulate the contents of document . Those provided here are merely one example of classes methods and properties which may be used.

When a test script author has designed a test to have software application create or modify document the author may utilize methods exposed by the objects described above to confirm that document is properly laid out. Layout verification logic may be instantiated as an object and document may be processed as described above.

Document may include components similar to those displayed in . Layout verification logic may be used to confirm the relative location of each component. depicts a series of points which may appear on document . These points may represent merely points or may represent corners or center points of other objects. The points or corresponding objects may have been automatically drawn by software application under the direction of a test script. The test script may then analyze document as the product of software application and utilize the specified layout requirements to establish whether or not the application passes the test.

A test author may wish to determine whether points are colinear whether they fall along a line . In determining colinearity points may not be precisely in line as with point . Thus a deviation parameter in the test function may allow for points to be close enough to be considered colinear. Such a deviation parameter may account for the distance between and line . Code snippet 1 below is a sample line of code which may be used to log the results of the test for colinearity. The single letters correspond to instances of Point objects corresponding to each of the points. Log.Verify a.IsColinearWith 0.05 b c d e f 1 

Here point is used to determine whether points are colinear with with a max deviation of 0.05. The Log object or class may be used as a receptacle for verification results or may otherwise store or communicate verification results. The result of the verification in code snippet 1 may be placed in test results which may then be used by a test author or software developer to either confirm a build or rewrite the code to make it work properly.

Code snippet 3 below is an example of how test code can be compounded to find complex test results. Points and are determined based on the intersections of segments and with segments and respectively. Points and are then evaluated to determine whether they are vertically aligned with each other. Log.Verify g.Intersection i .IsVerticallyAlignedWith 0.05 j.Intersection k 3 

Code snippet 4 determines whether Boundingbox is bottom aligned with Boundingbox . Code snippet 5 determines whether the box formed by the intersection of boxes and has a center point aligned with the top left corner of box . Code snippet 6 determines whether box is center aligned with box

Placing calls to layout verification logic in code similar to the above samples provides a method for tracking the results of document manipulation. Because the verification is relative to internal objects and not to some model document some advantages may be realized including minimizing the maintenance of test code and master documents. Relative verification means that slight or unimportant changes in the manipulated document e.g. slight shifting of objects do not require a new revision of a model document. Moreover no absolute values are required to be exactly correct if all components on a document shift uniformly relative verification may produce the same outcome regardless. In addition by placing layout verification in test code it can easily be tracked as part of the source code and does not require separate verification documents and tools. Creation of test scripts can actually begin before an application progresses to a point where test documents can be created. By knowing the definition of how document components should be composed relative to each other a test script can be written in the absence of a master document. In addition testers do not need in depth knowledge of the workings of a product to be able to generate useful test cases.

At as the test code is executed components are compared to each other. This comparison may involve comparing locations of center Points bottom Segments overlapping Boundingboxes and so forth. Other comparisons may be used. At if the components of the test document produce favorable test results then at the layout of the test document may be deemed verified. If at some test fails then the failure may be logged.

While methods and systems embodying the present invention are shown by way of example it will be understood that the invention is not limited to these embodiments. The methods and systems described are merely examples of the invention the limits of which are set forth in the claims which follow. Those skilled in the art may make modifications particularly in light of the foregoing teachings.

