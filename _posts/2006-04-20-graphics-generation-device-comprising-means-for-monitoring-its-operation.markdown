---

title: Graphics generation device comprising means for monitoring its operation
abstract: A device for the graphical generation of symbologies intended for a display screen, the device having functions for the generation of symbology elements and means for monitoring its correct operation. The monitoring of correct operation allowing the use of certain of the functions for the generation of symbology elements to be prohibited and micro-images dedicated to the monitoring of the functions to be generated and controlled.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08009163&OS=08009163&RS=08009163
owner: Thales
number: 08009163
owner_city: 
owner_country: FR
publication_date: 20060420
---
The present Application is based on International Application No. PCT EP2006 061720 filed Apr. 20 2006 which in turn corresponds to France Application No. 05 04195 filed Apr. 26 2005 and priority is hereby claimed under 35 USC 119 based on these applications. Each of these applications are hereby incorporated by reference in their entirety into the present application.

The field of the invention relates to the operational security safety and reliability of Man Machine Interface systems displaying information in the form of graphics or symbology.

The field of application is more particularly that of cockpit display systems on board aircraft. This type of system is designed to display critical information for the piloting or the navigation of the aircraft. The erroneous display of certain parameters may lead to catastrophic situations for the operational safety of the aircraft. Since the basic integrity or the reliability of the display system is not sufficient to guarantee the demands on safety and security dedicated monitoring mechanisms designed to detect possible display errors need to be implemented.

Clearly in view of the safety and security constraints specific to this field the main target field for this type of application is aeronautics. The invention may however be applied to any Man Machine Interface system requiring a high degree of security or reliability and comprising graphical displays such as the systems employed for rail transport or the centralized control and command systems for civil or military applications.

There exist several solutions for ensuring the operational safety and reliability of a display system.

Historically the operational reliability of an onboard display system is principally ensured by a feedback mechanism.

The principle is illustrated in . A display system is disposed between one or more sensors and a display screen . It essentially comprises 3 sub systems which are 

Another solution consists in implementing two dissimilar Graphics Generation channels denoted channel 1 and channel 2 

The objective of the monitoring is to verify that the two channels really have generated the same image for the critical symbols. Two solutions are implemented 

The goal of the invention is to guarantee the display integrity of an onboard display system while at the same time avoiding the previous drawbacks. Furthermore with respect to the current solutions described hereinabove this new monitoring mechanism provides a generic solution independent of the type of application and of the images that are displayed. In addition this new monitoring technique allows the integrity of the new display technologies to be guaranteed whether they are based on solutions referred to as proprietary in other words developed specifically for a given application or whether they are based on commercially available solutions referred to as COTS Component Off The Shelf the monitoring mechanism that forms the subject of the invention being sufficiently generic and portable with respect to the graphics generation implemented. Generally speaking components of the COTS type have a relatively short lifetime. It is therefore important to develop a monitoring device that is not linked to the component.

The monitoring principles according to the prior art are all based on the monitoring of graphical information coming from the display system and the verification that this information really does correspond to the input parameters. The heart of the invention is to essentially monitor the correct operation of the graphics generation functions independently of the data that they are processing.

The invention is more specifically designed to be implemented for graphics generation devices implanted within computer reception structures comprising a CPU acronym for Central Processing Unit. In this type of architecture the graphics generation no longer belongs to a particular application but forms an integral part of the reception structure. Thus a monitoring mechanism for the graphics generation is implemented within the reception structure itself. The definition of the applications therefore becomes independent of the graphics generation. In order that the applications may if necessary implement their own monitoring process each reception structure offers the possibility of dialogue with another reception structure which dialogue is also referred to as cross talk.

More precisely the invention relates to a device for the graphical generation of symbologies intended for a display screen the said device comprising functions for the generation of symbology elements and means for monitoring its correct operation characterized in that the said monitoring means comprise at least 

Advantageously the prohibited functions are functions that are capable of generating recurrent symbol elements or macro functions comprising a plurality of elementary functions for generating symbology elements.

Advantageously the device comprises a memory comprising a first region intended for the storage of the symbology and a second region the micro images being generated in this second region.

Advantageously the device comprises a memory comprising a first region intended for the storage of the symbology the second monitoring means allowing micro images to be generated in this first region during a short period of time compared with the refresh time of the symbology on the display screen.

Furthermore the device additionally comprises third monitoring means allowing certain state variables internal to the graphics generation device to be monitored the said third means comprising means for computing the said internal state variables independent of those of the graphics generation device.

The invention also relates to a method for monitoring the correct operation of a graphics generation device comprising a memory comprising a first region intended for storing the symbology the micro images being generated within this first region the said method comprising at least the following steps 

Furthermore the device can be of the GPU type acronym for Graphics Processing Unit the graphics generation functions and the monitoring means are integrated with a reception structure comprising a CPU acronym for Central Processing Unit and the functions for generation of symbology elements are written in an OpenGL language acronym for Open Graphics Language.

Advantageously the display screen is of the LCD type acronym for Liquid Crystal Display and the symbology is of the aeronautics type and represents symbols useful at least for the piloting and navigation of aircraft.

The invention is more specifically designed to be implemented for graphics generation devices implanted within computer reception structures. In this type of architecture illustrated in the graphics generation no longer belongs to a particular application but forms an integral part of the reception structure . Thus a monitoring mechanism for the graphics generation is implemented within the reception structure itself. The graphics generation offers a generic interface called API acronym for Application Programming Interface with the graphics applications by means of a graphics language. For example the graphics language can be the standard called OpenGL developed by the company Silicon Graphics or a standard derived from this language.

As was stated in order to avoid the dependency on the type of graphics solution the monitoring of the graphics generation is carried out within the functions implemented by the graphics language.

In the following part of the description these various means will also be referred to as security barriers.

By way of non limiting example a dysfunctional analysis of the functional machine OpenGL has allowed the critical functions to be identified that can generate a non integrity of the displayed parameters. is a table representing these critical functions in the case of a 2D application where the images are traced in 2 dimensions. The right hand column gives the OpenGL terminology of the critical functions identified and the left hand column the programming rules allowing the said functions to be disabled.

With regard to the second means the principle of the monitoring implemented consists in subjecting micro images to graphics generation. These micro images are characteristic of the correct operation of the critical functions. This principle is shown in .

In a first variant in order not to interfere with the display of the operational image these micro images are calculated by the monitoring device then drawn in a region of memory corresponding to an invisible part of the color buffers . The reception structure reads these color buffers in order to generate the video sent to the screen . When the reception structure reads the invisible part it does not send these pixels onto the screen but calculates a mathematical signature over the whole of the pixels of the micro image. It then suffices to verify by means of the comparison device that this signature conforms to that expected by the monitoring device in order to detect any possible malfunctioning of the graphics generation. The mathematical function that allows the signature to be determined is chosen such that any interference in the micro image leads to a modification of the signature. This type of function is known by those skilled in the art.

These micro images consist of a sub assembly of tests performed during the validation of the graphics generation function.

The main advantage of this solution is that the micro images generated do not interfere with the final image. However for certain applications it may be advantageous to verify the state of the final image. Accordingly in a second variant the micro images are traced within the visible part of the color buffers. In order that the micro image does not appear on the screen the following sequence is executed 

In the two cases the monitoring mechanism is executed on a processing core that of the application different from the graphics generation core. This guarantees the principle of segregation between a function and its monitoring.

To these main security barriers may also be added other safety and security mechanisms. In particular it is possible to monitor certain state variables of the graphics language generation system. The idea is then to re read in the graphics component certain state variables liable to have a critical effect on the operational integrity. For example in the case of the OpenGL language the state variables to be monitored are called Model View matrix Projection matrix Current color.

In this case the monitoring function of the graphics generation performs a dissimilar computation of these state variables allowing the coherence with the values implemented in the graphics component to be verified. Each time that the application modifies one of these state variables it performs the following operations 

In order that this monitoring be generic with regard to the applications a code generator must be used that automatically adds the above processing operations into the application.

By way of non limiting example the table in shows an exemplary implementation of the whole of the means according to the invention in the case where the programming language is OpenGL.

The main functions of the OpenGL programmable controller are grouped by type and disposed in columns. The terminology used is the OpenGL terminology. For example the first 3 functions of the table denoted as Process commands Evaluator GLUT are implemented in the Driver part and are grouped in the first three columns of the table. GLUT is the acronym for Graphics Language Utility Toolkit.

The security barriers are grouped in rows. The first 10 rows relate to the micro images rows 11 and 12 relate to the monitoring of the state variables and the last row relates to the programming rules.

When a security barrier can be applied to a given function a cross appears in the table at the intersection of the corresponding row and column.

Thus it is possible to guarantee the reliability of around forty OpenGL functions with a reduced number of security barriers. In addition certain functions are rendered secure in a redundant manner.

Thus the monitoring devices according to the invention allow a display system for critical parameters to be implemented with a high level of integrity. These devices are generic with regard to the type of application and portable with regard to the graphics generation technology employed.

With respect to the current solutions these monitoring devices limit the exchanges of data within the system and reduce the computational loading.

Moreover by limiting the asynchronism and tolerance problems between systems as far as possible these devices allow the detection of errors to be substantially improved.

