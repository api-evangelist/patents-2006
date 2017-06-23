---

title: De-blurring in a digital image system
abstract: A camera system deblurrs an image by detecting a velocity of a camera as an image is captured by an image sensor. A processor interconnected to the image sensor and the velocity detector processes the sensed image so as to deblurr the image and output the deblurred image to a printer means.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07646403&OS=07646403&RS=07646403
owner: Kia Silverbrook
number: 07646403
owner_city: Balmain, New South Wales
owner_country: AU
publication_date: 20060807
---
The present application is a continuation of U.S. application Ser. No. 09 113 090 filed on Jul. 10 1998 now issued U.S. Pat. No. 7 110 024 all of which is herein incorporated by reference.

The following Australian provisional patent applications are hereby incorporated by cross reference. For the purposes of location and identification U.S. patent applications identified by their U.S. patent application serial numbers USSN are listed alongside the Australian applications from which the U.S. patent applications claim the right of priority.

A large number of new forms of ink jet printers have been developed to facilitate alternative ink jet technologies for the image processing and data distribution system. Various combinations of ink jet devices can be included in printer devices incorporated as part of the present invention. Australian Provisional Patent Applications relating to these ink jets which are specifically incorporated by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

Further the present application may utilize advanced semiconductor fabrication techniques in the construction of large arrays of ink jet printers. Suitable manufacturing techniques are described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

Further the present application may utilize an ink delivery system to the ink jet head. Delivery systems relating to the supply of ink to a series of ink jet nozzles are described in the following Australian provisional patent specifications the disclosure of which are hereby incorporated by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

Further the present application may utilize advanced semiconductor microelectromechanical techniques in the construction of large arrays of ink jet printers. Suitable microelectromechanical techniques are described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

Further the present application may include the utilization of a disposable camera system such as those described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

Further the present application may include the utilization of a data distribution system such as that described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

Further the present application may include the utilization of camera and data processing techniques such as an Artcam type device as described in the following Australian provisional patent specifications incorporated here by cross reference. The serial numbers of respective corresponding U.S. patent applications are also provided for the sake of convenience.

The present invention relates to digital image processing and in particular discloses A Camera System Having Motion Deblurring Means.

Further the present invention relates to the field of digital image cameras and in particular discloses a camera system having motion blur compensating means.

Motion blur in the taking of images is a common significant problem. The motion blur normally occurs as a result of movement of the camera while taking the picture or otherwise as a result of movement of objects within an image.

It is an object of the present invention to provide a camera system having the ability to overcome the effects of motion blur.

In accordance with the first aspect of the present invention there is provided a camera system for outputting deblurred images said system comprising 

Preferably the camera system is connected to a printer means for immediate output of said deblurred image and is a portable handheld unit. The velocity detection means can comprise an accelerometer such as a micro electro mechanical MEMS device.

As described in Australian Provisional Patent Application No. PO7991 the camera system incorporates an Artcard linear sensor which converts the Artcard data image to electrical signals which are communicated to the ACP. The linear image sensor is illustrated in which is a reproduction of of Australian Provisional Patent Application No. PO7991. The linear image sensor can be fabricated using either CCD or APS CMOS technology. The active length of the linear image sensor is 50 mm equal to the width of the data array on the Artcard. To satisfy Nyquist s sampling theorem the resolution of the linear image sensor must be at least twice the highest spatial frequency of the Artcard optical image reaching the linear image sensor. In practice data detection is easier if the linear image sensor resolution is substantially above this. A resolution of 4800 dpi 189 dpmm is chosen giving a total of 9 450 pixels. This resolution requires a pixel sensor pitch of 5.3 mu m. This can readily be achieved by using four staggered rows of 20 mu m pixel sensors.

The linear image sensor is mounted in a special package which includes an LED to illuminate the Artcard via a light pipe.

1. It diffuses the light from the LED over the width of the card using total internal reflection facets.

2. It focuses the light onto a 16 mu m wide strip of the Artcard using an integrated cylindrical lens.

3. It focuses light reflected from the Artcard onto the linear image sensor pixels using a molded array of microlenses.

The preferred embodiment is preferably implemented through suitable programming of a hand held camera device such as that described in Australian Provisional Patent Application No. PO7991 filed 15 Jul. 1997 entitled Image Processing Method and Apparatus ART01 in addition to Australian Provisional Patent Application entitled Image Processing Method and Apparatus ART01a filed concurrently herewith by the present applicant the content of which is hereby specifically incorporated by cross reference.

The aforementioned patent specifications disclose a camera system hereinafter known as an Artcam type camera wherein sensed images can be directly printed out by an internal Artcam portable camera unit. Further the aforementioned specification discloses means and methods for performing various manipulations on images captured by the camera sensing device leading to the production of various effects in any output image. The manipulations are disclosed to be highly flexible in nature and can be implemented through the insertion into the Artcam of cards having encoded thereon various instructions for the manipulation of images the cards hereinafter being known as Artcards . The Artcam further has significant onboard processing power by an Artcam Central Processor unit ACP which is interconnected to a memory device for the storage of important data and images.

In the preferred embodiment the Artcam device is modified so as to include a two dimensional motion sensor. The motion sensor can comprise a small micro electro mechanical system MEMS device or other suitable device able to detect motion in two axes. The motion sensor can be mounted on the camera device and its output monitored by the Artcam central processor device which is disclosed in the afore mentioned patent specifications.

Turning now to there is illustrated a schematic of the preferred arrangement of the preferred embodiment. The accelerometer outputs to the Artcard processor which also receives the blurred sensed image from the CCD device. The Artcard processor utilises the accelerometer readings so as to determine a likely angular velocity of the camera when the picture was taken. This velocity factor is then utilised by a suitably programmed Artcard processor to apply a deblurring function to the blurred sensed image thereby outputting a deblurred output image . The programming of the Artcard processor so as to perform the deblurring can utilise standard algorithms known to those skilled in the art of computer programming and digital image restoration. For example reference is made to the Selected Papers on Digital Image Restoration M. Ibrahim Sezan Editor SPIE Milestone series volume 74 and in particular the reprinted paper at pages 167 175 thereof. Further simplified techniques are shown in the Image Processing Handbook second edition by John C. Russ published by CRC Press at pages 336 341 thereof.

It would be therefore obvious to the person skilled in the art that many different techniques for motion blur removal can be utilised in the preferred embodiment. Additionally other forms of motion sensors may be provided. Once the input image has been deblurred the image is then able to be printed out by the Artcam device in accordance with the techniques as discussed in the afore mentioned patent specification.

It would be appreciated by a person skilled in the art that numerous variations and or modifications may be made to the present invention as shown in the specific embodiment without departing from the spirit or scope of the invention as broadly described. The present embodiment is therefore to be considered in all respects to be illustrative and not restrictive.

The embodiments of the invention use an ink jet printer type device. Of course many different devices could be used. However presently popular ink jet printing technologies are unlikely to be suitable.

The most significant problem with thermal inkjet is power consumption. This is approximately 100 times that required for high speed and stems from the energy inefficient means of drop ejection. This involves the rapid boiling of water to produce a vapor bubble which expels the ink. Water has a very high heat capacity and must be superheated in thermal inkjet applications. This leads to an efficiency of around 0.02 from electricity input to drop momentum and increased surface area out.

The most significant problem with piezoelectric inkjet is size and cost. Piezoelectric crystals have a very small deflection at reasonable drive voltages and therefore require a large area for each nozzle. Also each piezoelectric actuator must be connected to its drive circuit on a separate substrate. This is not a significant problem at the current limit of around 300 nozzles per print head but is a major impediment to the fabrication of pagewidth print heads with 19 200 nozzles.

Ideally the inkjet technologies used meet the stringent requirements of in camera digital color printing and other high quality high speed low cost printing applications. To meet the requirements of digital photography new inkjet technologies have been created. The target features include 

All of these features can be met or exceeded by the inkjet systems described below with differing levels of difficulty. Forty five different inkjet technologies have been developed by the Assignee to give a wide range of choices for high volume manufacture. These technologies form part of separate applications assigned to the present Assignee as set out in the table under the heading Cross References to Related Applications .

The inkjet designs shown here are suitable for a wide range of digital printing systems from battery powered one time use digital cameras through to desktop and network printers and through to commercial printing systems.

For ease of manufacture using standard process equipment the printhead is designed to be a monolithic 0.5 micron CMOS chip with MEMS post processing. For color photographic applications the printhead is 100 mm long with a width which depends upon the inkjet type. The smallest printhead designed is IJ38 which is 0.35 mm wide giving a chip area of 35 square mm. The printheads each contain 19 200 nozzles plus data and control circuitry.

Ink is supplied to the back of the printhead by injection molded plastic ink channels. The molding requires 50 micron features which can be created using a lithographically micromachined insert in a standard injection molding tool. Ink flows through holes etched through the wafer to the nozzle chambers fabricated on the front surface of the wafer. The printhead is connected to the camera circuitry by tape automated bonding.

Eleven important characteristics of the fundamental operation of individual inkjet nozzles have been identified. These characteristics are largely orthogonal and so can be elucidated as an eleven dimensional matrix. Most of the eleven axes of this matrix include entries developed by the present assignee.

The complete eleven dimensional table represented by these axes contains 36.9 billion possible configurations of inkjet nozzle. While not all of the possible combinations result in a viable inkjet technology many million configurations are viable. It is clearly impractical to elucidate all of the possible configurations. Instead certain inkjet types have been investigated in detail. These are designated IJ01 to IJ45 which match the docket numbers in the table under the heading Cross References to Related Applications.

Other inkjet configurations can readily be derived from these forty five examples by substituting alternative configurations along one or more of the 11 axes. Most of the IJ01 to IJ45 examples can be made into inkjet printheads with characteristics superior to any currently available inkjet technology.

Where there are prior art examples known to the inventor one or more of these examples are listed in the examples column of the tables below. The IJ01 to IJ45 series are also listed in the examples column. In some cases print technology may be listed more than once in a table where it shares characteristics with more than one entry.

Suitable applications include Home printers Office network printers Short run digital printers Commercial print systems Fabric printers Pocket printers Internet WWW printers Video printers Medical imaging Wide format printers Notebook PC printers Fax machines Industrial printing systems Photocopiers Photographic minilabs etc.

The information associated with the aforementioned 11 dimensional matrix are set out in the following tables.

