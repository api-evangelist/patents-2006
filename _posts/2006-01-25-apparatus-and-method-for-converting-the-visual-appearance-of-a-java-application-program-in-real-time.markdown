---

title: Apparatus and method for converting the visual appearance of a Java application program in real time
abstract: A method and an apparatus for converting the visual appearance) of a program in real time, and more particularly, to a method and an apparatus for converting the visual appearance of a program in real time, by allowing an interface-based program convert a color combination, font, icon and a text position of a component, and an external appearance of the component in real time by adding a new interface to the application programming interface (API) that defines the visual appearance of the program.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08332759&OS=08332759&RS=08332759
owner: Samsung Electronics Co., Ltd.
number: 08332759
owner_city: Suwon-si
owner_country: KR
publication_date: 20060125
---
This application claims priority of Korean Patent Application No. 10 2005 0006800 filed on Jan. 25 2005 in the Korean Intellectual Property Office the disclosure of which is incorporated herein in its entirety by reference.

Apparatuses and methods consistent with the present invention relate to converting the visual appearance of a Java application program in real time and more particularly to a method and an apparatus for converting a visual appearance of the Java application program in real time that allows an interface based Java application program to convert a color combination font icon text position and external appearance of a component in real time by adding a new interface that defines the visual appearance of the Java application program to a Java application programming interface API .

Java is an object oriented programming language that is platform independent. Here the platform refers to hardware environment in which a program is executed or a software environment such as an operating system. Java code is compiled to Java byte code by a Java compiler and the Java byte code is executed by a Java virtual machine which has been ported to a variety of platforms .

The system comprises a Java application program a Java application programming interface API a Java virtual machine and a hardware based platform .

The Java application program refers to a program written in the Java language which is compiled into Java byte code using a Java compiler and the Java byte code is interpreted by the Java virtual machine and then executed. At this time the Java virtual machine operates as an interpreter with respect to the Java byte codes.

The Java API as aggregated libraries or classes for developing a Java program they are provided in packaged units where interrelated classes are bundled.

The Java application program uses the Java API in order to provide a graphic user interface hereinafter referred to as a GUI wherein the Java API outputs a graphic on a screen by using a GUI of the platform .

The Java API used for providing a GUI is classified into a heavy weight API and a light weight API according to drawing modes. The heavy weight API is platform dependent because it writes a GUI in the format supplied by a platform based GUI. The light weight API can provide a GUI in the same format in other platforms as it writes the GUI in the format desired by the developer and transmits it to the platform based GUI.

Here the Java Abstract Window Toolkit is the heavy weight API and the Java Swing is the light weight API.

The Label component is an extension of a Component class of the Abstract Window Toolkit which is connected to a LabelPeer class for connection with a platform based GUI . The LabelPeer class plays a role in connecting the platform based GUI and the Label component . Owing to this construction the Abstract Window Toolkit provides a platform dependent GUI.

The Label component of Swing is JLabel and a JLabel component is an extension of the JComponent class . The JComponent class finally inherits the Component class . The JLabel component has an object called a LabelUI which draws the JLabel component and which is not connected with a platform based GUI. The portions that draw a component are all realized in Java and they are output on a screen through the Java virtual machine .

The visual appearance is a visual property of a component output on a screen it indicates a color combination a font and an icon of a component and the location and external appearance of text.

As mentioned above the external appearance of the component changes according to the platform and real time conversion is not impossible because the Abstract Window Toolkit is platform dependent.

However with Swing the external appearance of the component does not change according to a platform because Swing is platform independent. However applying Swing to a program written based on the Abstract Window Toolkit may produce problems.

The visual appearance of a component is only applicable in the application program unit due to a structural limitation of the light weight API and it can not be applied to all the application programs in operation on a platform.

An aspect of the present invention is to allow an interface based Java application program to change looks in real time by adding a new interface with the defined looks of the Java application program to a Java API.

This aspect as well as other aspects features and advantages of the present invention will become clear to those skilled in the art upon review of the following description.

According to an aspect of the present invention there is provided an apparatus for converting a visual appearance of a Java application program in real time comprises a command reception unit which receives a command to convert the visual appearance of the Java application program currently in operation produced based upon the Abstract Window Toolkit an interface management unit which refers to a stored visual appearance package according to the received command and converts the visual appearance by notifying a component of the Java application program of the visual appearance conversion and a display unit which outputs the Java application program to which the converted visual appearance is applied on a screen.

A method for converting a visual appearance of a Java application program in real time comprises receiving a command to convert the visual appearance of the Java application program currently in operation produced based upon the Abstract Window Toolkit referring to a stored visual appearance package according to the received command and converting the visual appearance by notifying a component of the Java application program of the visual appearance conversion and outputting the Java application program to which the converted visual appearance is applied on a screen.

Advantages and features of the present invention and methods of accomplishing the same may be understood more readily by reference to the following detailed description of exemplary embodiments and the accompanying drawings. The present invention may however be embodied in many different forms and should not be constructed as being limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be through and complete and will fully convey the concept of the invention to those skilled in the art and the present invention will only be defined by the appended claims.

Exemplary embodiments of the subject application will be described in detail with reference to the accompanying drawings.

Although Swing provides more robust graphic functions than the Abstract Window Toolkit such devices as electric home appliances having limited memory mainly have a graphic user interface written based on the Abstract Window Toolkit since Swing libraries have to be stored in an apparatus.

An apparatus according to an exemplary embodiment of the present invention refers to one in which a graphic user s interface of a Java application program is written using the Abstract Window Toolkit. One of ordinary skill in the art would recognize however that the present invention is not limited to a Java application program written using the Abstract Window Toolkit.

An apparatus according to an embodiment of the present invention comprises an interface management unit a command reception unit and a display unit .

The command reception unit receives a command to convert the visual appearance of an Abstract Window Toolkit based Java application program currently in operation.

A visual appearance is a visual property of a Java application program such as a color combination a font and an icon of a component the location and an external appearance of text for example a window and a button.

A visual appearance conversion command input by a user is transmitted to the control unit and the control unit directs the interface management unit to notify a component included in the Java application program of the visual appearance conversion by referring to the stored visual appearance package according to the received command and then performs the visual appearance conversion.

The stored visual appearance package refers to a bundle of classes relating to a theme and a skin which includes a skin package which details an external appearance of a component and a theme package to form a theme by reading out property information relative to a color combination a font and an icon of a component and the location of text.

A Java application program in operation applies the stored visual appearance package to its visual appearance and then converts the visual appearance using a newly stored visual appearance package.

The display unit outputs the Java application program to which the converted visual appearance is applied and the control unit generally controls the command reception unit the interface management unit and the display unit .

The interface management unit comprises an interface control unit a theme management unit and a skin management unit .

The theme management unit manages properties of a component according to properties such as a color combination a font and an icon of a component and a location of text included in a Java application program using property information of a theme read out from a file. More specifically theme property information is loaded and stored when the apparatus is initialized and this information is modified according to a command of the interface control unit in real time and is then re loaded.

The skin management unit manages skin properties of a component according to properties of an external appearance of a component included in a Java application program by use of the stored skin package. More specifically the content of a skin package is loaded and stored when the apparatus is initialized and the content of a newly registered skin package is loaded in real time according to a command from the interface control unit .

The skin management unit confirms the presence of the skin requested by the interface control unit and delivers the skin to the component if the requested skin exists if not the skin management unit creates a new skin and delivers it to the component.

The interface control unit manages the conversion status of the theme and the skin through general control of the theme management unit and the skin management unit according to a command from the control unit . When a change has occurred the interface control unit notifies each component of the Java application program of the change in the theme or the skin and allows them to convert their look.

When an apparatus is initialized the theme management unit and the skin management unit load and store the property information of a theme and the content of a skin package. If the command reception unit receives a command to convert the skin of the Java application program currently in operation from a user S the received skin conversion command is transmitted to the control unit and the control unit makes the interface management unit convert the skin of the component.

The interface control unit of the interface management unit notifies a component of the skin conversion S and each component requests the new skin from the skin management unit . Accordingly the skin management unit checks if the skin exists S. If the requested skin exists the skin management unit applies it to the component S. If not the skin management unit creates a new skin S and applies it to the component S.

The Java application program registers its top level window in the interface control unit when it is initialized. When a command to convert the skin is issued while the Java application program is in operation the interface control unit notifies each component of the application program of the skin conversion using the registered top level window. Each component that has been notified of the skin conversion requests the converted skin from the skin management unit and converts the skin using the transmitted skin.

When an apparatus is initialized the theme management unit and the skin management unit load and store the property information of a theme and the content of a skin package. When the command reception unit receives a command to convert the theme of a Java application program in operation from a user S the received command is transmitted to the control unit and the control unit makes the interface management unit convert the theme of a component.

The interface control unit of the interface management unit notifies a component of the theme conversion S and checks a skin using the theme property exists S. If the skin exists the interface control unit notifies a theme conversion of the concerned skin S. The skin management unit converts a theme of a skin using the new theme according to the content of the theme stored in the theme management unit S. When the converted theme is applied to a component the visual appearance of the component is converted S.

The Java application program registers its top level window in the interface control unit when it is initialized. The interface management unit notifies each component of the application program of a theme conversion by using the registered top level window when a command to convert the theme is issued while the Java application program is in operation S. Each component that has been notified of the theme conversion converts its theme using the theme transmitted from the theme management unit S.

An apparatus and a method for changing the visual appearance of a Java application in real time according to the present invention produce at least one of the following effects.

First a new interface whereby the visual appearance of a Java application program is defined is added to the Java API and the Java application program using this interface can convert the visual appearance in real time.

Second since the new interface has a simplified construction it can be added to an apparatus having limited resources.

Third since the theme reads out information from an external property file the Java application program can change the theme property in real time without changing the code.

While the present invention has been illustrated and described with respect to exemplary embodiments thereof it will be understood by those skilled in the art that the foregoing and other changes in form and details may be made therein without departing from the spirit and scope of the invention which should be limited only by the scope of the appended claims. Thus exemplary embodiments of the invention disclosed above are used in a generic and descriptive sense only and not for purposes of limitation.

