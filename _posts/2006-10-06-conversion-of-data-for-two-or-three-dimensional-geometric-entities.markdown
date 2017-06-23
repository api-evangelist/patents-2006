---

title: Conversion of data for two or three dimensional geometric entities
abstract: A method for transmission of data for two or three dimensional geometrical entities uses a computer system, for modeling and/or manipulation of geometrical entities. The computer system comprises at least one program for modeling and/or manipulation and at least one display program, the at least one modeling and/or manipulation program transmits the data associated with the geometrical entities for display to the at least one display program, by calling up display functions located within the at least one display program. An exporting program for data associated with geometrical entities is substituted in at least one of the at least one display programs, the exporting program having the same display functions as the at least one display program.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07747570&OS=07747570&RS=07747570
owner: Adobe Systems Incorporated
number: 07747570
owner_city: San Jose
owner_country: US
publication_date: 20061006
---
This application is a continuation application of and claims priority to pending U.S. patent application Ser. No. 10 482 742 entitled CONVERSION OF DATA FOR TWO OR THREE DIMENSIONAL GEOMETRIC ENTITIES to inventor Francois le Masne de Chermont which was filed on May 13 2004 which claims the benefit of priority to International Application PCT FR01 02136 filed Jul. 4 2001. The disclosures of the above applications are incorporated herein by reference in their entirety.

This invention generally concerns the exportation of computer data and more specifically the exportation of data associated with geometric entities from a computer program such as a computer assisted design CAD program or a videogame.

The technique and systems for modeling and or manipulation of geometric entities such as CAD and videogames are now quite widespread in all fields of the industry from computer assisted design of products such as automobiles or aircraft to 3D virtual reality action games and including simulation programs such as flight simulators.

In particular although the CAD technique is relatively young under twenty years old the need for upward compatibility by the prior CAD systems led to the retention of existing data structures that only partially used the possibilities of the modern computer systems despite the rapid evolution of information technologies.

Additionally whether in the field of CAD or videogames the format of these data structures used is universally proprietary meaning it is specific to the software involved or as a minimum to the software publisher involved. However at least in the CAD field these graphic programs generally have the functionalities to import various data formats associated with geometric entities.

On the other hand clearly for customer retention purposes the publishers of these programs whoever they may be are not inclined to publish the specifications for the data formats they use and in the same vein they are generally rather reticent to offer utilities making it possible to export all of the data from their programs to a competitor s program.

This situation means that it is very difficult to transfer all of the data used by these programs from a computer system for modeling and or manipulation of geometric entities to a similar computer system. However this transfer is frequently made necessary for example to transfer data among different CAD systems as they exist at the various subcontractors of a single customer even within one company as happens in particular for reasons that generally relate to backward compatibility in the major companies having used CAD for a long time.

It can be expected that the evolution of videogame technology will ultimately make it possible to import characters or objects into a videogame which will then raise the problem again of exporting this type of entity from another videogame.

This need to transfer data between different systems for modeling and or manipulation of data associated with geometric entities means that there are quite significant development costs on the conversion utilities for these data due to the absence of precise specifications concerning the format of the databases involved and it also means that these utilities should be rewritten partially or in full at the time of upgrades or modifications made to the structure of the databases of the systems involved. Also this conversion is generally incomplete due to the absence of precise specifications for the format of the data to be converted.

Furthermore there is a need in companies using CAD systems for an open data structure and format widespread and well defined as a means of exchange among different CAD systems as well as to ensure minimal independence regarding the publishers of the CAD programs they use to allow CAD data capture from one program to another in the event the publisher of the CAD program used goes out of business.

In view of the foregoing it is clear there is a need for a process and a system to make it possible in an affordable and reliable manner to export data associated with geometric entities from any program for modeling and or manipulation of data associated with geometric entities with no knowledge of the data structures used by this program without any modification of this program in any way and without development of a specific interface to the program involved.

There are known utilities such as glTrace or glAnalysePro that make it possible to intercept and store the graphic primitives or function calls made by a graphic application. However the function of these utilities is only to debug the graphic application involved and not to allow the exportation of data associated with geometric entities to other systems of the same kind.

The object of this invention is therefore to propose a process for exporting data associated with geometric entities using a computer system for modeling and or manipulation of geometric entities said computer system for modeling and or manipulation of geometric entities including at least one central processing unit that can execute computer programs a memory that can store said computer programs and data associated with geometric entities throughout the course of execution of said computer programs and at least one storage unit allowing permanent storage of the data associated with geometric entities said computer system including at least one program and modeling and or manipulation of geometric entities and at least one program to display data associated with geometric entities said at least one program for modeling and or manipulation transmitting the data associated with geometric entities to be displayed said at least one display program calling the display functions located in said at least one display program said data to be displayed by said display program being transmitted by said at least one program for modeling and or manipulation of said at least one display program in the form of call parameters said display functions called by said at least one program for modeling and or manipulation of said display functions called by said at least one program for modeling and or manipulation of geometric entities said display functions making it possible to display a certain number of data associated with geometric entities and characterized in that a program for exportation of data associated with geometric entities is replaced by at least one of same at least one display programs said exportation program having the same function of displaying data associated with geometric entities as that of at least one display programs said functions of displaying data associated with geometric entities of said exportation program having the same parameters as the corresponding functions of said at least one display program said at least one program for modeling and or manipulation of geometric entities transparently calling the functions of said exportation program instead of the corresponding functions of said at least one display program.

In the process of the invention at least one of said at least one programs for modeling and or manipulation can be for example a computer assisted design or CAD program or even a videogame program.

Additionally during a call of said at least one program for modeling and or manipulation to one of said display functions of said exportation program said exportation program can store in an appropriate format within said at least one storage unit data from processing by said exportation program of the calls to said at least one program for modeling and or manipulation to said display functions of said exportation program.

Further during a call of said at least one program for modeling and or manipulation to one of said display functions of said exportation program said exportation program may call the display function of said display program corresponding to said display function called in said exportation program with the same call parameters as those present in the call to said function of said exportation program.

In this case said called display program can be said display program for which said exportation program was replaced or a different display program from that for which said exportation program was replaced.

Said computer system can also include at least one graphic display device said at least one display device including at least one refresh and or display memory said at least one display memory ordering said at least one display device to digitize in the form of points said calls for display functions received by said display program said display device storing in said refresh and or display memory said points coming from said digitization of said calls for display functions received by said at least one display program.

In this case said computer system can also include at least one graphic screen in which said refresh and or display memory is reread by said at least one display device said at least one display device displaying on said at least one graphic screen said points reread from said refresh and or display memory.

Said exportation of data by said exportation program can then be triggered by at least one specific graphic instruction transmitted by said at least one program for modeling and or manipulation of said exportation program said at least one specific graphic instruction triggering said data exportation being for example an instruction causing completion of said digitization of said graphic function calls received in said points in said refresh and or display memory.

As a variation said at least one display device includes at least two refresh and or display memories in which said instruction causing said exportation can then be an instruction causing the switch from one of the said at least two refresh and or display memories to another of said at least two refresh and or display memories.

Furthermore during a call of said program for modeling and or manipulation to one of said display functions of said exportation program said exportation program can store in said memory in an appropriate format data from processing by said exportation program of calls to said display functions of said exportation program. In this case said computer system can also execute a utility program reading in said memory said data from processing by said exportation program. Furthermore said utility program rereading said memory can then store in an appropriate format in said at least one storage unit said data from processing by said exportation program reread from said memory.

Additionally said utility program can also display said data reread from said memory with the held of appropriate calls to the display function of said at least one display program.

The one of said at least one display program for which said exportation program is substituted may be for example compliant with the Silicon Graphics Inc. OpenGL specification. In this case said at least one instruction causing said exportation could be the OpenGL instruction wglSwapBuffers and or the OpenGL instruction glFlush. 

Also the one of said at least one display program for which said exportation program is replaced may also be compliant with the Microsoft DirectX specification.

Generally in the process of the invention said data associated with geometric entities would include geometric data. In this case said geometric data could be bidimensional and or tridimensional. Said geometric data could then include data on points and or data on two point segments and or data on triangles and or data on quadrangles and or data on polygons.

Likewise said geometric data could be associated with line and or surface and or volume geometric entities. Said geometric data associated with geometric entities could then also include geometric data associated with at least one normal vector with at least one of said line and or surface and or volume entities.

The invention also proposes a system for exporting data associated with geometric entities using a computer system for modeling and or manipulation of geometric entities said computer system for modeling and or manipulation of geometric entities including at least one central processing unit that can execute computer programs a memory that can store said computer programs and data associated with geometric entities throughout the course of execution of said computer programs and at least one storage unit that can permanently store data associated with geometric entities said computer system including at least one program for modeling and or manipulation of geometric entities and at least one display program for data associated with geometric entities said at least one modeling and or manipulation program transmitting the data associated with geometric entities to be displayed to said at least one display program by calling the display functions located in said at least one display program said data to be displayed by said display program being transmitted by said at least one program for modeling and or manipulation to said at least one display program in the form of call parameters of said display functions called by said at least one program for modeling and or manipulation of geometric entities said display functions allowing display of a certain number of data associated with geometric entities and characterized in that it implements the process according to any of the preceding claims.

The process of the invention functions in a computer system for modeling and or manipulation of data associated with geometric entities.

This computer system allows implementation by a user not shown of a program for modeling and or manipulation of data associated with geometric entities regardless of whether the process of the invention is implemented on the computer system . The computer system also allows display on a graphic screen of graphic signals from a graphic interface card driven by a library of graphic functions .

In the continuation of this description the program for modeling and or manipulation of data associated with geometric entities could also be referenced as the graphic application for greater simplicity.

In the referred embodiments of the invention the computer system used to make the process of the invention function is a computer running the Microsoft Windows operating system and in this operating system the program for displaying geometric data is a graphic API Advanced Programming Interface implemented via a dynamic link or DLL library compliant for example with the Silicon Graphics Inc. OpenGL specification. This DLL is generally located in the Windows system directory and it is called opengl32.dll. 

As the OpenGL library includes hundreds of functions all of the OpenGL functions used as examples in this description whether with or without implementation of the process of the invention were voluntarily limited to a very reduced subset of OpenGL functions to allow this description to be of a reasonable size. However it should be understood as of now that the principle of the invention is not limited to the OpenGL functions stated in this description but it likewise applies to all functions existing in the OpenGL specification.

Referring to we will now describe the operating principle for the display of a geometric model on the graphic screen without using the process of the invention for exporting data.

When the graphic application wishes to display a geometric model on the graphic screen it calls the graphic functions located in the DLL of the graphic interface . This graphic interface sends vector commands to the graphic interface card via its associated software driver.

As the computer screens themselves are made of cathode ray tubes or similar devices making the display by video scanning this means it is necessary to store a binary image of the graphic data displayed so that a visual persistence of the graphic data displayed can be maintained for the user . This binary image formed of a certain number of bits for each of the displayable points on the graphic screen is stored in an internal memory on the graphic interface card called refresh memory. The visual persistence of the data for the user is obtained by the graphic interface card by rereading this binary image dozens of times a second and generating video signals from the information reread representing the stored image in the refresh memory of the graphic interface card . These video signals are sent by the graphic interface card to the graphic screen on which they cause the display of the image stored in binary form in the refresh memory of the graphic interface card .

A graphic application wishing to display a geometric model on the screen of the computer will thus execute a sequence of calls to the graphic functions present in the OpenGL DLL. In the OpenGL specification this sequence of graphic function calls is terminated by a call to a specific function that will cause completion of the conversion of instructions sent to the graphic interface card on binary points displayed on the graphic screen .

For example to display a geometric model formed of a strip of two triangles T and T go respectively through points ABC and BCD of the respective coordinates 

In this sequence of calls the call glBegin GL TRIANGLE STRIP indicates the beginning of the strip of triangles and the call glEnd indicates its end. The function glVertex3fv allows definition of one of the vertices of the triangles by its three x y and z coordinates.

When all the preceding components were sent by the graphic application to the graphic interface via the above function calls the graphic application causes completion of display of the components previously sent using an appropriate function of the graphic interface such as the function glFlush or the function wglSwapBuffers appearing in the above example. These functions both cause completion of the conversion of the graphic instructions previously received in bit images in the current refresh memory of the graphic interface card terminating the display of the graphic instructions received previously on the graphic screen .

The instruction wglSwapBuffers also causes the swapping of the two frame memories of the graphic interface card in the event this graphic interface card has two.

In the case of the example of display described the reception of the instruction wglSwapBuffers causes the display on the graphic screen of graphic instructions transmitted by the graphic application to the graphic interface card via the graphic interface . In this case this completes the display of the geometric model formed of the two triangles T and T on this graphic screen .

Referring now to we will now describe the exportation of a geometric model implementing the process of exportation of the invention.

During installation of the program for exportation of graphic data implementing the process of the invention the original DLL opengl32.dll present in the Windows system directory is named for example as opengl32bis.dll and it is replaced by a DLL implementing the process of the invention and named identically to the original meaning opengl32.dll. This DLL according to the invention has the same functions in compliance with the OpenGL specification as the original DLL meaning it has the same interface functions with the same names and same parameters as the original OpenGL DLL.

When an operator not shown wishes to export the data from a geometric model created and or manipulated by the graphic application it first executes the DLL according to the invention as described above. He then has the desired geometric model displayed by the graphic application . In the same way as described previously in using the computer system without implementing the process of the invention when the graphic application wishes to display a geometric model on the screen it uses the DLL named opengl32.dll found in the Windows system directory meaning it makes calls to the functions and to the primitives in accordance with the OpenGL specification contained in this DLL .

Considering that at the time of installation of the exportation program for data associated with the geometric entities according to the invention the DLL was replaced by the DLL implementing the process of the invention the graphic application then transparently calls the functions and primitives present in the DLL implementing the process of the invention instead and in place of the functions and primitives present in the original DLL.

As a variation the DLL called opengl32.dll could be installed only by a specific graphic application for geometric entities modeling or manipulation by installing the DLL only in the directory of the specific graphic application . In fact when the Windows operating system searches for a DLL referenced by graphic application it first searches for this DLL in the same directory as the one where the graphic application is found. As a default the Windows operating system then searches for this DLL in the predefined directories of the system which include among others the system directory where the Windows operating system is installed.

Thus when the process of the invention is implemented and using the above example the DLL of the process of the invention receives instead and in place of the original OpenGL DLL the graphic function calls intended for the latter. In the current embodiments of the invention the DLL of the invention then transmits to the original DLL the function calls received meaning it calls the corresponding functions of the DLL with the same parameters as those received in the calls from the graphic application .

To export data associated with geometric entities the program contained in the DLL according to the invention stores and manages in its memory a certain number of tables of data associated with geometric entities such as but not limited to a Points table of points and a Triangles table of triangles. Initially these two tables are empty meaning the number of NPoints components in the Points table and the number of NTriangles components in the Triangles table are all zero.

The DLL program starts at step where it initializes the number of points NPoints and the number of triangles NTriangles at value 0 then it awaits reception of a graphic instruction from the graphic application . At the time of reception of the instruction glBegin GL TRIANGLE STRIP the process according to the invention moves to step where it tests whether the value of the parameter of the instruction GL BEGIN is the predefined value GL TRIANGLE STRIP indicating the beginning of a sequence of graphic instructions defining a strip of triangles by their vertices. If the response is negative the process returns to step . If the response to step is positive meaning if the value of the parameter is GL TRIANGLE STRIP the process moves to step where it awaits a graphic instruction.

At the time of reception of a graphic instruction the process of the invention tests in step whether the instruction received is a glVertex3fv instruction in the case of the example given the response is positive and at the time of reception of the call glVertex3fv 0.000 10.000 0.000 the process of the invention then moves to step . In step the DLL then increases by one unit the number of points received NPoints meaning it moves the NPoints number of points from its initial value zero to value 1. It then stores the point received in the Points table meaning that still in step it also stores respectively the first second and third parameter of the instruction glVertex3fv received in this case the values 0.000 10.000 and 0.000 in the spaces for the x y and z coordinates of the first point in the Points table. The process of the invention then moves to step .

In step the process of the invention tests whether the number NPoints of points received is lower than 3. If the response is positive the process of the invention returns to step or else the process of the invention moves to step .

When in step the response is negative this means that at least three points were transmitted by the previous glVertex3fv instructions. According to the OpenGL specification for the triangle strip GL TRIANGLE STRIP this means that a triangle in the strip formed by the three last points received was defined.

Consequently in step the DLL program implementing the process of the invention thus increases the number of triangles received from a unit meaning it increases the number NTriangles of triangles received from a unit. It then stores the numbers n nand nof the points forming the triangle thus received meaning according to the OpenGL specification the last three points received in the corresponding spaces of the triangles table meaning it stores the numbers NPoints 2 NPoints 1 and NPoints of the last three points received in spaces n nand nof the space for number NTriangles in the Triangles table.

The DLL then returns to step to await other possible points from the strip of triangles transmitted by the graphic application .

In the example described after having four points via the four glVertex3fv instructions the DLL receives no other glVertex3fv instructions but it receives instead a glEnd instruction. Consequently in step the response is negative and the DLL then moves to step .

In the OpenGL specification the instruction glEnd means that the sequence of graphic instructions begun by the previous instruction glBegin in this case the strip of triangles GL TRIANGLE STRIP is terminated.

In step the DLL tests whether the last function call received was a call to the function glEnd. If the response is negative the program contained in the DLL returns to step . When the response of the test in step is positive the program of the DLL moves to step . In the example described this happens when the graphic application sends the instruction glEnd after the four glVertex3fv instructions.

In step the program contained in the DLL of the invention is waiting for an instruction from the graphic application then when such an instruction is received it moves to step .

In step the DLL program tests whether the graphic instruction received is an OpenGL wglSwapBuffers or glFlush instruction. If the response is negative meaning if the instruction received is neither a wglSwapBuffers instruction nor a glBuffers instruction the DLL program according to the process of the invention is terminated. If the response to step is positive the DLL program moves to step .

In the example described after the glEnd instruction is sent the graphic application sends the instruction wglSwapBuffers to the program but the glFlush instruction could also have been used.

As indicated previously in implementation of the computer system without using the process of the invention these instructions cause the completion of the conversion of the graphic instructions and their display on the graphic screen and they thus implicitly include the meaning that the previously transmitted instructions form a consistent whole since they should be displayed on the graphic screen without waiting for graphic instructions.

Consequently in the embodiments of the invention these instructions are used to determine that the graphic instructions previously received form a consistent whole and to then cause their exportation to the storage unit .

Therefore when in step the response to the test is positive meaning when a wglSwapBuffers or glFlush instruction was received the instructions previously received by the DLL form a consistent whole and the DLL implementing the process of the invention then moves to step where a module named Raider 3D does the exporting to the storage unit of the Points and Triangles tables stored in the memory .

In the process of the invention the memory in which the Points and Triangles tables are stored is a shared memory in the computer implementing the process of the invention which means that it can be written by DLL and reread simultaneously by the Raider 3D module .

In a first embodiment of the invention the Points and Triangles tables are exported to the storage unit in the form of simple text files in which the points and the triangles are recorded in files of the same name in the storage unit .

Referring further to we will now describe the operation of the Raider 3D module according to a first embodiment of the process of this invention.

In this first embodiment at step the Raider 3D module creates and opens a point exportation file named Points in the example described in the storage unit it initializes the number i of points recorded in the file Points at value 0 then it moves to step .

In step the Raider 3D module tests whether the number i of points recorded in the Points file is lower than the number of NPoints points present in the shared memory. If the response to step is positive the Raider 3D module moves to step . In step the Raider 3D module increases by one unit the value of number i then it writes in the Points file the new value of the number i followed on the same line by the three x y and z coordinates of the corresponding number i point copied from input i of the Points file stored in the shared memory . The Raider 3D module then moves to the line in the Points file then it returns to step .

If the response to step is negative the Raider 3D module moves to step . In step the Raider 3D module closes the Points file then moves to step . In step the Raider 3D module creates and opens in the storage unit a triangle exportation file called Triangles in the example described then it initializes at zero the value of the number i of triangles written in the Triangles file. It then moves to step .

In step the Raider 3D module tests whether the number i of triangles recorded in the Triangles file is lower than the number of NTriangles triangles present in the shared memory. If the response to step is positive the Raider 3D module moves to step . In step the Raider 3D module increases the number i of a unit then it writes in the Triangle files the number i of the current triangle and on the same line of the Triangle file it copies the numbers n nand nof the three points forming the triangle of number i from the input i of the Triangle tables stored in the shared memory. The module then returns to step .

If in step the response is negative the Raider 3D module then moves to step where it closes the Triangles exportation file.

The Points and Triangles text files obtained in the previous example will then have the form presented in tables 1 and 2 below respectively.

The process of exporting data linked to geometric entities according to the first embodiment of the invention is then terminated and as we have just seen it would have made it possible to export the geometric model created and or manipulated by the graphic application with no knowledge of the format of the data of this graphic application and with no development of the program specific to this graphic application .

In a second embodiment of the invention the exportation format used is the DXF Drawing eXchange Format of the AutoDesk company which is the reference format for the market of exportation materials of data associated with geometric entities.

The DXF format is a text format at the rate of one piece of information per line. The lines are grouped in pairs with the first line of the pair containing a whole number datum indicating the type of data appearing in the following line. Thus when the numerical type data is a whole number between 0 and 9 the data appearing in the following line will be a chain of characters and when the numerical type data is a whole number between 10 and 59 the data appearing on the following line will be a tridimensional double precision floating points coordinate.

Additionally a DXF file is organized in sections. A section is introduced by a pair of lines one line formed of the introducing a chain of characters and one line formed of the keyword SECTION and it is terminated by a pair of lines the first of which is formed of the and the second of the keyword ENDSEC.

A DXF file includes a certain number of different section types in particular the section ENTITIES describing the geometric entities as well as a certain number of other sections such as the sections defining parameters or classes which are not in this description.

The ENTITIES section is formed of the various geometric entities of the geometric model with each entity being introduced by a chain of characters indicating the type of entity followed by the parameters needed to define the entity in question.

For example the definition of a facet in the space is introduced by a pair of lines the first of which is formed of the introducing a chain of characters followed by a line formed of the keyword 3DFACE.

A facet in the space is formed of three or four points respectively forming a triangle or a quadrangle with the fourth point being specified as identical to the third to indicate by convention a triangle rather than a quadrangle. Each of the four points of a facet is defined by its three x y and z coordinates and each of the coordinates is defined as previously indicated by a pair of lines the first of which is a whole number indicator between 10 and 59 and the second of which is the coordinate.

In the DXF format specification the indicators for the x yand z coordinates of the first point of the facet are 10 20 and 30 respectively the indicators for the x yand zcoordinates of the second point of the facet are 11 21 and 31 respectively indicators for the x yand zcoordinates of the third point of the facet are 12 22 and 32 respectively and the indicators for the x yand zcoordinates of the first point of the facet are 13 23 and 33 respectively.

In other words for the point of number j with j varying from 1 to 4 on a facet the numerical indicator of the x coordinate of point j is 9 j the numerical indicator of the y coordinate of point j is 19 j and the numerical indicator of the z coordinate of point j is 29 j.

More specifically referring now to the Raider 3D module according to the second embodiment of this invention creates and opens in step an exportation file named in the example given DXF then it moves to step . In step the Raider 3D module writes the header lines of the file in the DXF format meaning the following four lines 

Then it initializes at 0 the number i of facets described in the DXF file. The Raider 3D module then moves to step . In step the Raider 3D module tests whether the number i of facets written is lower than the number of triangles stored in the shared memory.

If the response to step is positive meaning if the number i of triangles previously written in the DXF file is lower than the number NTriangles of triangles stored in the shared memory the Raider 3D module moves to step . In step the Raider 3D module increases by one unit the number i of triangles previously written in the file then it writes the header lines in DXF format for a facet meaning the following two lines 

In addition still in step the Raider 3D module initializes at 0 the number j of points of the triangle i described in the DXF file then it moves to step . In step the Raider 3D module tests whether the number j of points of the triangle i written in the DXF file is lower than 3. If the response is positive the Raider 3D module moves to step .

In step the Raider 3D module increases by one unit the number j of points of the triangle i written in the DXF file and calculates a number n as being equal to Triangles.n meaning n becomes equal to the number nof point j of triangle i. It then successively writes the indicator of the x coordinate for point j of the facet in the DXF format meaning value 9 j on a first line then the x coordinate itself on a second line for the point whose number n was previously calculated.

Likewise still in step and still for the point of number n the Raider 3D module respectively writes the indicator j on a third line and the y coordinate on a fourth line then the indicator j on a fifth line and the z coordinate on a sixth line. The Raider 3D module then returns to step .

The process of steps and is repeated until in step the response becomes negative meaning the number j of points of the triangle written in the DXF file is equal to 3. At this point in the operations the Raider 3D module will then have written the three points of the triangle i.

When i equals 1 meaning for the first triangle the Raider 3D module will then have written successively the following lines in the DXF file 

When in step the number j of points written in the DXF file is equal to 3 the Raider 3D module moves to step . At the beginning of step the Raider 3D module will then have written in the DXF file the three points of the triangle i in the form indicated above. However as the DXF specification requires four points for a facet as previously mentioned the third point of number nis repeated which means per DXF convention that the facet described is a triangle.

To that end in step the Raider 3D module writes in the file the x coordinate indicator for the fourth point of the facet or on a first line then the x coordinate on a second line. Likewise it successively writes the y coordinate indicator or on a third line and the y coordinate on a fourth line and the z coordinate indicator or on a fifth line and the z coordinate on a sixth line.

When i equals 1 meaning for the first triangle this is reflected in the fact that in step the Raider 3D module writes the following lines in the DXF file 

At the end of step the Raider 3D module then returns to step to export the following triangle using the same process as that described above for the first triangle until in step the response is positive.

When the response is positive in step meaning that all of the triangles previously stored in the shared memory were written in the DXF file then the Raider 3D module moves to step . In step the Raider 3D module writes the end of section lines meaning the following two lines 

Then still in step the Raider 3D module closes the DXF file which will then have the form presented in Table 3 below 

The process of exporting data linked to geometric entities according to the second embodiment of this invention is then terminated and as we have just seen it will have made it possible to export the geometric model created and or manipulated by the graphic application with no knowledge of the data format of this application with no modification of this graphic application and with no development of the program specific to this graphic application .

Obviously the process of the invention is not limited to the interception and exportation of the graphic functions of points and triangles described above. In particular in the example described previously the function used for generating points was the glVertex3fv function but it will be clear to anyone competent in the technology that the preceding description applies with basic adaptations to any instruction from the glVertex group.

In addition it should be perfectly clear from the preceding description that the process of the invention allows exportation of any desired OpenGL function including but not limited to the functions defining quadrangular components those defining surface orientation information such as the normal of a point those defining color information surface texture transparency etc.

Also the process is not limited to the exportation of geometric structures as simple as those in the example described but it will be obvious to experts that the process of the invention makes it possible to export any geometric model due to the fact that any modeled structure as complex as it may be will be displayed with the help of point primitives triangles quadrangles etc. and may thus be exported using the process described above.

Likewise for obvious reasons of simplicity in the description it was assumed that all of the geometric structures used the points in particular were distinct and that consequently there was no need to seek to eliminate duplications or to optimize the tables used in any manner. In practice the duplicated components would clearly be deleted by an appropriate process either during their recording in the Points and Triangles tables by the DLL program or during their exportation to the storage unit by the Raider 3D module .

Also the process is not limited to the described embodiments using the OpenGL graphic library and it will be obvious to anyone competent in the technology that the process described above also applies to any other library of display functions likely to be used by the modeling or geometric modeling application such as including but not limited to the Microsoft DirectX display library.

Additionally the process of the invention can be implemented only for a desired specific application rather than for all of the graphic applications present in the modeling and or manipulation system installing the DLL implementing the process of the invention only in the directory of the desired application rather than in the Windows operating system directory.

According to the foregoing it is clear that the process of the invention made it possible to export the geometry information from the example modeled by the application with no modification of this application with no program development specific to this application and with no knowledge of the data format used by the latter only by intercepting the graphic primitives and functions that this application uses to display its geometric models.

Considering that the data format used to store the data associated with the geometric entities exported into the storage unit will be either a known open format such as that presented in the first embodiment or a standard market format such as the DXF format or any other format needed for a specific application it will be very easy to import these data into any other desired geometric modeling and or manipulation system.

The process of the invention is thus likely to be applied in a very wide variety of fields in particular in all of the fields in which data associated with geometric entities need to be exchanged among different systems as occurs in all of the industries and services using data associated with geometric entities such as the automobile construction or aeronautic industrial design building and or architecture videogame etc. services or industries.

