---

title: Projected image display unit
abstract: A projection image display device including a display plane for displaying an image, a projection mechanism projecting an image on the display plane, and an imaging mechanism arranged on the same side of the display plane as the projection mechanism for imaging the display plane. The imaging mechanism is arranged at a position where a position symmetric with respect to the display plane of the projection mechanism is out of the range of the field angle of the imaging mechanism. By arranging the imaging mechanism at a position where no direct reflecting light of the light source of the projection mechanism comes, it is possible to prevent generation of a hot spot.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07959300&OS=07959300&RS=07959300
owner: Ricoh Company, Ltd.
number: 07959300
owner_city: Tokyo
owner_country: JP
publication_date: 20060629
---
The present invention relates to projected image display units. In particular the present invention relates to a drawn image data retention method a drawn image data retention apparatus and a projected image display unit that superpose drawn image data obtained by capturing the image of an object such as written information on the front surface of a screen on the image data of an image projected onto the screen and project them from the rear side of the screen and bind the drawn image data to the image data and store them.

Conventionally there have been used projected image display units of a rear projection type which project an image onto a transmission screen with a projector from the backside rear side of the screen opposite to the surface viewed by a viewer front surface .

Some of such projected image display units are capable of capturing the image of an object on the front surface of a screen with a camera from the rear side of the screen .

The image capturing is affected by the contrast ratio of a projector. The contrast ratio of the projector is expressed by the ratio of the brightness of an all white projection to the brightness of an all black projection. When the brightness of a lamp is constant low contrast means high brightness of black projection and the transmittance of the lamp at the time of black projection is also high.

Many recent DLP projectors enjoy high contrast in which the effect of a lamp center light is relatively small. However the effect of the lamp cannot be ignored even in black projection in conventional projectors with approximate contrast of 50 1 to 1000 1. See Patent Documents 1 through 6. 

Further in recent years this rear projection type display has been used in demonstrations in events conferences etc. and there is strong demand for the function of displaying a drawn image written onto the front surface side of a screen on the screen in combination with an image projected onto the screen and the function of manipulating an image projected onto the screen by directly touching the front surface of the screen with a hand.

One method that satisfies this demand is to capture the image of an object on the front surface of a screen from its rear surface side with a camera using a CCD solid state image sensing device and extract necessary information from the captured image.

In general screens conventionally used for rear projection type displays which give importance to visibility at the time of viewing from the front side are provided with a Fresnel lens for making uniform the amount of light at the time of viewing the projected light of a projector from the front side and a lenticular lens for improving visibility. However capturing an image on the screen using them from its rear side results in a distorted image. Further there is a problem in that while it is necessary for external light from the front side of the screen to be sufficiently transmitted to its rear surface side in order to have good image quality an increase in the scattering performance of light projected from the rear side decreases the transmission performance.

Therefore for example a mask is provided between a projector and a screen and the mask is caused to be in a transmission state during a projection display period and in a light interruption state or a light scattering state during an image capturing period. See Patent Document 7. 

Further a screen is formed by sandwiching liquid crystal between a lenticular lens and a Fresnel lens and an electric field is applied to the liquid crystal so that the liquid crystal matches the lenticular lens in refractive index so as to cause the screen to be in the light transmission state at the time of image capturing and the liquid crystal does not match the lenticular lens in refractive index so as to cause the screen to be in the light scattering state at the time of displaying. See Patent Document 8 .

However these techniques make it expensive to manufacture screens and make it necessary to control screen conditions a camera and projection with high accuracy at high speed in order to prevent a user viewing the surface of projection from the front side from feeling oddness thus complicating system configuration and control.

On the other hand a region that diffuses light and a region that transmits light from the front surface are provided like a lattice thereby improving the visibility of a projected image and the quality of an image captured by a camera on the rear side. See Patent Document 9. 

This technique has the advantage that external light is taken in with efficiency the visibility of a projected image is prevented from being degraded and there is no need to switch states during use of the apparatus. However there are the problems of high technical difficulty and high cost because the diffusion region and the transmission region of the screen should be placed with high accuracy considering displaying a projected image with good quality to a viewer on the front side of the screen and the quality of the image captured from the rear side.

Further image information and conference image information can be stored or transmitted to a remote place by using a screen selectively set to a scattering state or a transmission state electrically and projecting an image from the rear side of the screen and capturing the image of original material and participants disposed on the front side of the screen from the rear side of the screen. Patent Document 10. 

When black display is performed at the time of capturing an image the entire screen can be viewed as black from a viewer. However a hot spot of a projector enters the image captured by a camera as shown in . The hot spot is a phenomenon where the lamp of a projector appears like a spot. The hot spot refers to a phenomenon where only one point lightens brightly when viewed from an angle at which the light of the projector is directly reflected. This entrance of the hot spot is referred to as generation of the hot spot . This generation of the hot spot is caused because the screen also serves as a mirror surface at the same time as displaying projected light.

Further since image capturing is performed using external light it is difficult to capture the image of information on the screen surface in an environment with little illumination. In this case the color of the projected light of the projector is changed so as to serve as the stroboscope of a camera. For example in the case of capturing an image with all white display the degradation of image quality due to the hot spot is conspicuous as shown in .

Further according to each of the techniques disclosed in the cited documents 7 through 10 an image based on image data is projected onto a screen and for example information handwritten on the screen at the scene of a conference cannot be stored together with the data of a projected image or the stored information cannot be edited.

In view of these problems the present invention has an object of providing a projected image display unit that avoids generation of a hot spot.

In order to solve the above described problems the present invention is characterized by a display surface configured to display an image projection means for projecting the image onto the display surface and image capturing means for performing image capturing on the display surface the image capturing means being placed on the same side of the display surface as the projection means wherein the image capturing means is placed at a position so that the symmetrical position of the projection means with respect to the display surface is out of the range of an angle of view of the image capturing means.

In order to solve the above described problems the present invention is characterized by a display surface configured to display an image projection means for projecting the image onto the display surface and image capturing means for performing image capturing on the display surface the image capturing means being placed on the same side of the display surface as the projection means wherein the projection means is placed at a position so that the symmetrical position of the image capturing means with respect to the display surface is out of the range of the angle of view of the projection means.

The above described projected image display units may also be further characterized by means for changing the optical path of the projection means and the optical path of the image capturing means.

They may also be characterized in that the changing means changes the optical path of the projection means and the optical path of the image capturing means with a reflection plane reflecting light.

They may also be characterized in that the changing means changes the optical path of the projection means and the optical path of the image capturing means so that the optical paths pass through the display surface.

They may also be characterized in that the image capturing means is placed so that the optical path of the projection means and the optical path of the image capturing means are prevented from overlapping each other on the reflection plane of the changing means.

They may also be characterized in that the projection means is placed so that the optical path of the projection means and the optical path of the image capturing means are prevented from overlapping each other on the reflection plane of the reflection means.

They may also be characterized by changing means for projection for changing the optical path of the projection means so that the optical path of the projection means passes through the display surface and changing means for image capturing for changing the optical path of the image capturing means so that the optical path of the image capturing means passes through the display surface.

They may also be characterized in that the projection means displays an image captured by the image capturing means in which a distortion is corrected.

They may also be characterized in that the image capturing means is capable of shifting or tilting the lens of the image capturing means.

They may also be characterized in that the projection means is capable of shifting or tilting the lens of the projection means.

They may also be characterized in that the image capturing means captures the image of a writing formed on the display surface or an image in contact with the display surface.

They may also be characterized in that the projection area of the projection means on the display surface is substantially equal to the image capturing area of the image capturing means.

According to the present invention it is possible to provide a projected image display unit that avoids generation of a hot spot.

A description is given below with reference to the drawings of embodiments of the present invention. In this embodiment a description of already described reference numerals may be omitted. Further in this embodiment it is assumed that an angle of view indicates a range within which an image can be captured with the lens of a camera or a range within which a projector can perform projection.

In general the length and the width of the image capturing element of a camera are different. Accordingly the angle of view of the camera includes a horizontal angle of view and a vertical angle of view. Likewise the angle of view of a projector includes a horizontal angle of view and a vertical angle of view. In the description of this embodiment an angle of view means a horizontal angle of view and a vertical angle of view.

Letting the side of the screen viewed by the viewer be the front surface display surface the projector performs projection and the camera captures an image from the rear side of the screen .

The projector that is projection means is connected to the PC and projects an image from the PC . The PC may be contained in the unit or externally connected. The PC may be any information processor capable of image processing and is not limited to a PC.

The switch for processing commands is provided on the viewer side. This may be a mouse for operating the PC or the switch that generates a specific processing signal. In the case of the switch it may be one configured to include multiple buttons generating respective signals for corresponding operations such as numeric keys. Alternatively multiple unit specific buttons may be provided.

The screen which is a display surface is a rear projection type projector screen provided with a protection sheet or subjected to treatment so that writing can be performed thereon with a common whiteboard marker.

The camera that is image capturing means is contained in the projected image display unit. This camera is provided so that the angle of view of the camera matches an image projected onto the screen . The area of the display surface within which an image is captured by the camera may not be entirely equal to the area of the display surface onto which projection is performed by the projector . For example if a writing area may not be the entire display surface onto which projection is performed by the projector the writing area may be the area of the display surface within which an image is captured by the camera .

In addition to an image projected onto the screen the camera captures the image of writing formed on the screen by the viewer and an image in contact with the display surface. Further in this embodiment the camera is a CCD camera.

The above described overall configuration of the projected image display unit only shows configuration and the camera and the projector in this embodiment take various positions as described below.

The viewer writes additional matter onto this projected image display unit with a whiteboard marker while viewing a projected image on the screen . After the writing the viewer commands processing with the switch so that the camera performs image capturing. The purpose of this image capturing is to capture the image of characters or drawings written onto the screen. Therefore the projected light of the projector is temporarily blocked at the time of capturing the image in order to prevent the projected image from being captured. This light blocking condition is achieved by making the projected image all black for example by making the PC perform all black display.

A specific description is given using the flowchart of of the operation of capturing a still image in this projected image display unit. In step S a user presses down the switch . In step S all black display is performed. Next in step S the camera captures an image. In step S after the image capturing the projector reprojects a normal image. Thereafter in step S the image captured earlier is processed.

In this embodiment a description is given based on the assumption that the camera captures an image in accordance with a user s operation. Alternatively the camera may capture an image every time a predetermined period of time passes.

A description is given below of a configuration that avoids generation of a hot spot. First prior to this description a description is given of the cause of generation of a hot spot.

If the projector is thus within the angle of view of the symmetry camera in the position plane symmetric with respect to the screen as an axis of symmetry a hot spot is generated. Further a hot spot is also generated if the camera is within the angle of view of the symmetry projector not shown in the drawing which is in the position plane symmetric with respect to the screen as an axis of symmetry.

In the case of a configuration that has the same angle of view on the screen as the projected image display unit if one is not within the angle of view the other is not within the angle of view either. Accordingly it is possible to avoid generation of a hot spot by causing the projector not to be included in the range plane symmetric to the angle of view of the camera or causing the camera not to be included in the range plane symmetric to the angle of view of the symmetry projector.

Thus in this embodiment generation of a hot spot is avoided by placing the camera in a position that the direct reflected light of the light source of the projector does not enter. In this embodiment the effect of a hot spot is eliminated by determining the positional relationship between the camera and the projector so that the light source of the projector is not within the angle of view the range of image capturing of the camera so as to prevent a generated hot spot from entering an image captured by the camera in the case of taking the screen as a mirror.

As shown in generation of a hot spot is avoided in the image captured in this condition. However the placement of the camera or projector shown in or causes distortion in the captured image because the optical axis is inclined with respect to the screen surface. Specifically the rectangle of the screen surface is distorted into a trapezoid in the captured image. This trapezoidal distortion can be corrected using projective transformation.

Further this distortion is caused by an imaging plane and the screen subjected to image capturing through a lens being not parallel as shown in . Accordingly this trapezoidal distortion can be optically corrected by performing shift correction that offsets the optical axis of the lens from the optical axis of the imaging plane as shown in .

Further since the screen is inclined with respect to the lens the depth of field of the image capturing lens at each point on the screen surface may be less than a normal depth of field depending on the degree of inclination.

In this case it is possible to focus on a focal plane by inclining the lens that is tilting the lens with respect to the imaging plane .

Thus it is possible to optically correct image distortion caused in the case of determining placement of a camera so as to prevent a projector from being within the angle of view of the camera by combining the shift and tilt of the lens of the camera.

The tilt and shift of the lens are applicable not only to the camera but also to the projector. That is it is possible to optically correct image distortion caused in the case of determining placement of the projector by combining the shift and tilt of the lens of the projector. Needless to say in the case of the projector the keystone correction of the projector may also be used.

Next a description is given of avoidance of generation of a hot spot in the case of the projectors and shown in . is a configuration of the projector or . The angle of view of each of the camera and the projector is adjusted to the screen by way of a single mirror .

In the projectors and it is often difficult at the time of designing to ensure a sufficient optical path length for the projector or camera from a viewpoint of practical use such as the space saving characteristic of the unit. Therefore in general such a structure as to ensure optical path length through the mirror is adopted.

As shown in the projector is included in the angle of view of the camera . Accordingly a hot spot is generated in the projected image display unit shown in .

Therefore it is possible to avoid generation of a hot spot by arranging the camera and the projector as shown in . shows the camera and the projector in the positions plane symmetric with respect to the mirror as an axis of symmetry. Further the camera is shown in the position plane symmetric to the camera with respect to the screen as an axis of symmetry. Further there is a part where the optical path of the camera overlaps the optical path of the projector in .

As shown in the projector is not included in the angle of view of the camera . Accordingly it is possible to avoid generation of a hot spot in the projected image display unit shown in .

However because of the part diffuse reflection of projector light is caused by dust adhering to the mirror so that this reflected light enters a camera image. is one at the time of projecting a white image from a projector as auxiliary light at the time of image capturing. An area in the upper part of shows that diffuse reflection of projector light has been caused by dust adhering to a mirror.

This diffuse reflection of light causes degradation of image quality. Therefore in the case of forming a unit through a mirror it is desirable that the optical path of the projector does not overlap the optical path of the camera on the mirror. Accordingly it is possible to capture a high quality image as by such an arrangement as to avoid generation of the hot spot of the projector and to prevent the optical paths of the projector and the camera from overlapping each other on the mirror surface remove a highlight part due to diffuse reflection of light caused by foreign matter adhering to the mirror surface . Further such a configuration as to prevent the optical paths of both from overlapping each other reduces the frequency of maintenance of the mirror which is a merit in practical use.

Implementing a configuration where the projector is not within the angle of view of the camera and their optical paths do not overlap each other on the mirror surface with a single mirror in this manner increases the area of the mirror and may not be desirable in view of a practical space saving design.

Further the mirror itself may be distorted by its weight so as to cause distortion in a projected image. The distortion due to the distortion of the mirror surface cannot be corrected by the keystone correction of the projector or the like. Accordingly it is preferable that the mirror area be as small as possible.

Therefore it is desirable to use two mirrors as shown in . shows a configuration where two mirrors and are used. That is it is possible to eliminate the problem of highlight due to an optical system and the problem of highlight due to dust adhering to a mirror surface by the projector and the camera using the separate mirrors and that adjust their angles of view to the screen surface respectively. Since the mirror area is also reduced there is more latitude in designing such as practical space saving.

In the case of the table type projected image display unit shown in there is a limit to its height and an increase in the dead space due to a large mirror or an arrangement for preventing degradation of image quality is not preferable. Therefore using the two mirrors and as shown in is extremely advantageous in terms of designing.

In the configuration of the table type projected image display unit the possibility is extremely high that the optical axis of the camera may not be perpendicular to and may be tilted with respect to the screen surface due to its space limitation so that a trapezoidal distortion is caused in the configuration for preventing dust adhering to a mirror surface from degrading image quality.

As a measure against this the above described optical correction technique using the shift and tilt of a camera lens is effective. However since a special lens is used in such a case an arrangement that minimizes the tilt angle on the camera side is desirable in order to avoid the trapezoidal distortion. Therefore it is also possible to adopt a configuration where the tilt of the camera is reduced by increasing the latitude of arrangement using the mirrors and individually as shown in .

The base material of the above described screen should have a level surface for image capturing by the camera and possible embodiments of the screen are as follows. A description is given below of embodiments of a drawn image data retention method a drawn image data retention apparatus and a projected image display unit centering on embodiments of the screen .

A rear projection display unit of this embodiment an example of which is shown in includes a screen onto which an image is projected a projector that projects an image onto the screen a digital camera that captures the image of an object in the direction of the screen from behind a rear surface of the screen and obtains the captured image of the object a mirror placed at an angle to a display surface of the screen behind the rear surface of the screen an enclosure and a computer hereinafter referred to as PC not graphically illustrated.

Each of a lens surface of the projector through which an image is projected and a lens surface of the digital camera through which the image of an object is captured faces toward the mirror . Light projected from the projector is reflected by the mirror so that the optical path is directed to a direction perpendicular to the screen . A drawn image written onto the display surface of the screen or light reflected from or transmitted through the contact surface of an object in contact with the display surface of the screen is reflected by the mirror and condensed by the lens of the digital camera and is captured by the built in solid state image sensing device such as a CCD image sensing device of the digital camera so as to be converted into captured image data.

The PC has a display screen and displays an image on the display surface based on image data generated using predetermined software corresponding to image display means or image data externally input from a camera or scanner. Meanwhile the PC can send the image data representing the displayed image to the projector and cause an image analogous to the image displayed on the display surface to be projected from the projector onto the screen based on the image data. A description is given below of the image display means.

Here the enclosure does not always have to be a vertical type and may be a horizontal type with its side surfaces vertically positioned.

Further the rear projection display unit of this embodiment which has the digital camera that obtains drawn image data by capturing a drawn image written onto the display surface of the screen may replace the digital camera with for example a known digitizer capable of obtaining drawn image data electromagnetically or through infrared position detection from a drawn image written onto the screen .

The rear projection display unit of another example shown in is a table type where the screen is placed horizontally on the upper surface of a table and the projector and the digital camera are both placed in a bottom part of the enclosure with their respective lens surfaces and facing toward the screen . Accordingly the mirror is not provided in the rear projection display unit of .

As shown in the screen of this embodiment includes a diffusion particle layer formed of a transparent acrylic material and having diffusion treatment for diffusing light on the display surface displaying an image and an acryl layer without diffusion treatment. Diffusion treatment is performed by applying a transparent coating material containing fine particles that diffuse light on the surface of the acrylic material.

As shown in when the light of the projector is projected from the rear surface side of the screen of the embodiment with diffusion treatment the light passing through the acryl layer without diffusion treatment of the rear surface reaches the diffusion particle layer to be diffused by the diffusion particles of the diffusion particle layer as shown in that is an enlargement of the part of encircled with a broken line. Accordingly a viewer who views an image projected from the rear surface side of the screen from the display surface side can view the projected image without depending on the viewing position.

As shown in when the light entering the screen from the display surface side of the screen travels toward the rear surface side through the acryl layer via the diffusion particle layer the light that has entered from various angles scatters to be evenly distributed so that a high contrast image can be obtained by performing image capturing on the rear surface with the digital camera on the rear surface side.

Here a transparent thin film is applied on the diffusion particle layer of the display surface . Further this transparent thin film is coated with an antireflection film so as to increase the amount of light entering the camera. Preferably the antireflection film has a reflectance of 1 or less at an incident angle of 0 . Further a preferable film thickness including the thin film is less than or equal to 0.25 mm considering the transmittance of light projected from the projector and the contrast of written information.

Thus a transparent thin film is applied on the diffusion particle layer . Accordingly when characters or drawings are written on an image projected on the screen with a marker it is possible to erase the written characters or drawings with ease. Further the coating of an antireflection film suppresses reflection of light on the screen surface so as to prevent a surrounding background from being captured to improve the visibility of the projected image.

The rear projection display unit of this embodiment uses the screen of such a configuration. Accordingly an image can be captured of not only a drawn image characters or drawings written onto the display surface of the screen but also an object placed on the display surface side of the screen using illuminating external light. That is the image can be captured as a shadow if transmittivity is poor and as a colored pattern in the case of a marker with some transmittivity. Further the image of original material superposed on the display surface of the screen can be captured by performing monochromatic projection from the projector and using its light as illuminating light because external light cannot be used.

In this embodiment the diffusion particle layer is formed by applying diffusion particles on the surface of acryl thereby diffusing passing light. Such a method based on application of diffusion particles is advantageous in terms of productivity and cost. However there is no limitation to this method and the diffusion effect can also be obtained by directly processing acryl by cutting or grinding.

Further the transparent base material of the screen is preferably acryl in terms of processability and cost but is not necessarily limited thereto. It may be any material that has a refractive index approximate to air and is transparent.

Image display means an example of which is shown in includes an image extraction part that extracts of drawn image data obtained by the digital camera those of a drawn image written onto the screen an image obtaining part that determines the size and position in which the extracted drawn image data are pasted a data addition part that creates composite data by pasting the drawn image data having its pasting position etc. determined by the image obtaining part to image data based on a generated or externally input projection file and switch means that switches an image projected onto the screen by the projector to illuminating light depending on whether it is the case of capturing the image of a drawn image written onto the display surface of the screen with the digital camera the case of capturing the image of the shadow on an object appearing on the screen with the digital camera or the case of capturing the image of original material superposed on the display surface with the digital camera .

In the case of capturing the image of original material superposed on the screen with the digital camera the switch means stops projecting an image and emits illuminating light from the projector since external light does not reach the surface of the original material.

The image display means is a program that is installed in the PC connected to the projector and the digital camera and has the function of creating composite data by for example pasting drawn image data captured by the digital camera to the projection file generated using an application program of the PC. Based on the created composite data a composite image where a drawn image represented by the drawn image data is pasted to the image that has been projected is projected from the projector onto the screen as shown in .

An API Application Programming Interface is open to the public for the program used to create the projection file shown in . Accordingly the drawn image data captured by the digital camera can be pasted to the image data projected onto the screen based on the projection file using the program for which API is open to the public and can be stored as the internal data of the projection file of the projected image.

Thereby it is possible to paste drawn image data into the projection file that has been projected onto the screen and to check it on the screen . In addition it is possible to store the projection file to which the drawn image data are bound. Therefore later re editing and cutting the pasted drawn image data are possible.

What the digital camera captures does not always have to be a handwritten drawn image and may be printed original material. The contents of paper material may be captured as drawn image data and used with electronic material.

The image display means another example of which is shown in includes the image extraction part that extracts of drawn image data obtained by the digital camera those of a drawn image written onto the screen the image obtaining part that determines the size and position in which the extracted drawn image data are pasted the data addition part that creates composite data by pasting the drawn image data having its pasting position etc. determined by the image obtaining part to a projection file converted into bitmap data and the switch means that switches an image projected onto the screen by the projector to illuminating light depending on whether it is the case of capturing the image of a drawn image written onto the display surface of the screen with the digital camera the case of capturing the image of the shadow on an object appearing on the screen with the digital camera or the case of capturing the image of original material superposed on the display surface with the digital camera .

In the case of capturing the image of original material superposed on the screen with the digital camera the switch means stops projecting an image and emits illuminating light from the projector since external light does not reach the surface of the original material.

In this example the image document of a projection file created with a program for which no API is open to the public is projected. Accordingly the bitmap data converted into a file having a hierarchical structure by a virtual printer driver are input to the data addition part . It is the same as the image display means shown in except that the bitmap data converted by the virtual printer driver are input.

Here a printer driver is generally a program for printing the printing information of an application on paper while the virtual printer driver is a program for outputting printing information to other than actual printers as an image. Accordingly in the case of an application with a printing function the information of a file is output as image information by setting this virtual printer driver as the driver of an output destination.

As shown in by converting a document image of a projection file created with a program for which no API is open to the public with the virtual printer driver an image file having a hierarchical structure can be created.

The document image created with the program having no API open to the public is loaded into a hierarchically structured image file through the virtual printer driver by the printing function. Since any image data can be added to this image file it is possible to add information without being restricted by the application.

Accordingly in the case of a projection file created with a program for which no API is open to the public when writing is performed over a file projected onto the screen from the projector it is possible to capture the image of the written drawn image with the digital camera and extract the data of the written drawn image from obtained drawn image data top and to add the extracted drawn image data to the hierarchically structured image file loaded through the virtual printer driver and display them as a superposition of the document image and the drawn image on the screen of the PC bottom as shown in .

No API is open to the public for a program used to create a projection file shown in . Accordingly the drawn image data captured by the digital camera cannot be pasted as the internal data of the projection file projected onto the screen . On the other hand if the data are combined to display a composite image on the screen the data of the combined part disappear. Therefore in this example the projection file is converted into page by page image files by the virtual printer driver and the drawn image data are superposed on a page of the image files to which the drawn image data are to be pasted. Thereby it is possible to link the drawn image data with the image files and retain them in a bound state without losing the original projection file.

Thus by creating a hierarchically structured file through the virtual printer driver an application having a printing function can manage an application document and added information such as a written drawn image in a later editable manner.

Compared with the first embodiment the second embodiment is different in the structure of the screen where a transparent flat plate member is stuck with an adhesive agent to the back side of the display surface with diffusion treatment of the screen used for the rear projection display unit but the other points are common. Accordingly a description is given of the structure of the screen which structure is different.

First as a comparative example a description is given of a conventionally used structure of the screen where a Fresnel lens is provided on the rear surface side.

The screen shown in has a Fresnel lens a diffusion sheet and a reinforcement glass in a layered structure from the rear surface side to the display surface side. In order to eliminate unevenness in the amount of light projected onto the rear surface side from a light source the light that has entered at different angles is converted into a parallel optical path by the Fresnel lens so as to be projected onto the diffusion sheet so that a projected image can be visually recognized from the display surface side.

Thus the screen of this structure emphasizes the visibility of a projected image to a viewer on the display surface side. Accordingly in the case of capturing the image of the screen surface from the rear surface side of the screen of this structure an object on the display surface side of the screen is blurred by the effect of the Fresnel lens. Further in the case of performing image capturing with the digital camera with projection from the light source the reflected light of the projected light on the surface of the Fresnel lens interferes so that noise enters a captured image if monochrome display is performed to use the projected light as auxiliary light for the image capturing with the digital camera for example.

The appearance of a rear image projection unit is the same as illustrated using in the first embodiment. In particular in the case of the table type one shown in a user may put a hand or object on the screen surface at the time of having a meeting around it. Accordingly the screen surface needs enough strength to sustain it and it is often the case that that large screens naturally need strength to be used in presentations or conferences.

Accordingly it is necessary to provide a reinforcement plate on the side opposite to the display surface side. With the reinforcement plate simply attached there is an air layer between the acryl member forming the display surface and the reinforcement acryl member.

In the screen includes a display surface side transparent member that has the diffusion particle layer with diffusion treatment and the acryl layer and on which a projected image is displayed and a rear surface side transparent flat plate member to which the projected image is projected.

The display surface side transparent member has the diffusion particle layer formed by applying diffusion particles on the surface of a flat plate acrylic material.

Further transparent thin films and are applied on the display surface side transparent member and the rear surface side flat plate member respectively and the thin films and are coated with respective antireflection films.

The antireflection films are determined so as to have a reflectance of 1 or less at an incident angle of 0 .

According to the screen of the structure where the display surface side transparent member and the rear surface side flat plate member are stuck together with an adhesive agent materials are selected so that each of the display surface side transparent member and the rear surface side flat plate member is formed of an acrylic material having a refractive index of for example 1.4 and the adhesive agent has a refractive index more than or equal to the refractive index of the acrylic material.

For example an ultraviolet curing adhesive agent may be used as the adhesive agent. However the adhesive agent is not necessarily limited to this and may be any adhesive agent having a refractive index approximate to that of the flat plate member and having the quality of becoming transparent in color after curing.

In general total internal reflection occurs when light enters a substance of a lower refractive index from a substance of a higher refractive index. Because of this quality if there are two contact planes of the acryl member and air between the front surface and the rear surface of the screen as shown in total internal reflection may occur at two planes and . This reduces the rate at which external light that has entered from the front surface of the screen reaches the rear surface by half.

However by bonding the display surface side transparent member and the rear surface side flat plate member with a substance having a refractive index higher than and approximate to that of the acryl member the total internal reflection at the first plane boundary is eliminated and . As a result compared with the case where there is an air layer the light entering the rear surface increases so as to increase the amount of light on the rear surface of the screen so that when an image is captured with a camera from the rear surface side the contrast of the captured image increases.

Thereby it is possible to obtain drawn image data with higher lightness and higher resolution in the case of capturing the image of an object on the display surface side from the rear surface side of the screen with a camera.

Further the rear surface side transparent member is coated with the antireflection film . This suppresses reflection of light projected from a projector so that it is possible to suppress noise due to a projected image in the case of for example capturing the image of written characters with a camera.

In the horizontal axis represents an angle at which a viewer views the screen surface and the vertical axis represents gain.

Thus by performing various types of tinting of different angles it is possible to configure screens according to purposes that allow a good quality image captured from the rear surface to be obtained without reducing the quality of an image projected from a projector.

Since the screen of this embodiment has a reinforcement plate on the rear surface side it is possible to increase the size of the screen. Accordingly while it is used as a screen for a rear projection type display in conferences or presentations so as to display the electronic material of a PC on the screen it is possible to write directly over what is displayed on the screen using a water based marker as if it were a whiteboard if there is any change or addition to what is displayed on the screen.

The screen of this embodiment has a transparent thin film applied on the display surface. Accordingly it is possible to perform writing on the screen with ease using a marker as if it were a whiteboard and it is also possible to erase it later with ease. Further it is possible to capture the image of a drawn image which has been superposed and written over a projected image while viewing the projected image from the rear surface with a camera to extract the written information and paste it to the projected image and to project a composite image by the pasting onto the screen and view it. It is also possible to bind the written drawn image information to the data of the original projection file and store them and to edit them later.

A drawn image data retention method according to the present invention wherein drawn image data obtained from a drawn image superposed and written over an image projected onto a screen is retained being bound to image data representing the image may be characterized by projecting the image based on the image data input to image display means onto the screen from behind the rear surface of the screen on the side opposite to its display surface using a projector obtain the drawn image data by capturing the image of the drawn image written onto the display surface of the screen onto which the image is projected from behind the rear surface of the screen using a camera and pasting the obtained drawn image data to the image data input to the image display means projecting a composite image based on the composite data by the pasting onto the screen from behind the rear surface using the projector and binding the obtained drawn data to the image data and retaining them.

Thus drawn image data are obtained by capturing the image of a drawn image written onto a screen onto which an image is projected with a camera and composite data into which the obtained drawn image data are merged with image data representing the image are retained. Accordingly it is easy to manage the drawn image data.

Further a drawn image data retention apparatus according to the present invention wherein drawn image data obtained from a drawn image superposed and written over an image projected onto a screen is retained being bound to image data representing the image may be characterized by a projector projecting the image based on the predetermined image data onto the screen from behind the rear surface of the screen on the side opposite to its display surface a camera obtaining the drawn image data by capturing the image of an object on the display surface side of the screen onto which the image is projected from behind the rear surface of the screen and image display means for sending generated image data to the projector and if the drawn image data captured by the camera are input thereto from the camera sending composite data where all or part of the input drawn image data is pasted to the image data to the projector wherein the image display means may bound and retain the drawn image data and the image data.

Thus image display means for pasting all or part of drawn image data obtained by performing image capturing with a camera to image data projected from a projector is provided. Accordingly a composite image based on the composite data by the pasting can be viewed and retained.

A projected image display unit according to the present invention including a screen a projector projecting a projection image based on image data input from image display means onto a screen from behind the rear surface of the screen on the side opposite to its display surface and a camera obtaining captured image data by capturing the image of an object in the direction of the screen from behind the rear surface wherein the projector projects onto the screen a projection image based on composite data where the obtained captured image data are pasted to the image data may be characterized in that the screen is formed of a transparent member having a transparent thin film applied on the display surface subjected to light diffusion treatment and the camera obtains the captured image data by capturing the image of a drawn image erasably written onto the thin film of the screen or the image of the contact surface of an object in contact with the screen.

Thus the screen is subjected to diffusion treatment and has a transparent thin film applied thereon. Accordingly writing with a marker and erasure are easy.

According to the above described drawn image data retention method and drawn image data retention apparatus image data projected onto a screen and drawn image data related to a figure or written characters or drawings on the display surface of the screen can be bound together and retained in an editable state.

Further according to the above described projected image display unit it is possible to improve the visibility of a projected image on the display surface of a screen and it is also possible to ensure a necessary amount of light for capturing the image of an object on the display surface side of the screen from the rear surface of the screen and obtain high resolution data by capturing the image.

The present application is a national stage application of PCT JP2006 312970 filed Jun. 29 2006 and which claims priority based on Japanese Patent Application No. 2005 192511 filed on Jun. 30 2005 the entire contents of both of which are hereby incorporated by reference.

