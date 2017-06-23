---

title: Using tags to modify program behavior
abstract: A first electronic device () can gather information about itself or another electronic device (), which is preferably situated within a same room of a user premises. This information can come from an RF-ID tag () or other transmitter. The information can relate to a state or identity of the other device. The first electronic device can alter program behavior () in response to the state or identity. The program might be an entertainment type program or a software type program. The information can be used to select brand specific program code () for execution.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08564414&OS=08564414&RS=08564414
owner: Koninklijke Philips N.V.
number: 08564414
owner_city: Eindhoven
owner_country: NL
publication_date: 20060302
---
The invention relates to the field of controlling electronic devices and to modifying their behavior responsive to the environment.

US 2002 0174025 shows a method and system for providing targeted advertising and personalized customer services. This system envisions a shopping cart with RFID tagged products. The RFID tags trigger a wireless communication device such as a PDA mobile phone pager or special shopping cart attachment device to deliver customized advertising based on what products are in the shopping cart.

It would be desirable to use transmitters attached to devices to influence behavior of devices in other ways.

For instance a group of electronic devices premises might communicate with each other in order to affect application behavior especially devices co located within a user premises. Such communication might result in changes in program behavior or changes in state of the devices or changes in program content.

One option for wireless communication is to use passive or active RF tags on the consumer devices . Preferably the type of tag used is readable within the common dimensions of a large room or an apartment. Such tags are preferably affixed by the manufacturer of a device such as a consumer device and programmed to contain an identification of the device. Manufacturers may do this for their own reasons. Alternatively the tags may be affixed at the request of someone who wishes to implement the invention. This identification preferably includes brand name type of product and a serial or model number. The processor could then access some sort of database whether local or remote to get other information about the device. This database might be as simple as a table within the receiving device or as complex as a remote server.

Purchase date color shape and value can all be regarded as examples of states of the device. If privacy of the owner of the device is desired the tags could omit any personal identifying information relating to the owner.

For example if the application see discussed below is running inside a television and detects both that one of the devices is a telephone and that the state of the telephone is ringing the application might issue a control command to lower the volume of the television so that the user can hear the ringing. This is an example of an audio output device changing its audio output in response to a state of another device.

Similarly if the application is running within a television and detects that a microwave oven is on in the user premises the application might signal the television to tune to a cooking program. This is an example of a consumer device choosing a transmitted signal in response to a state of anther device.

In still another example if a video game player is detected in the room the application could make its skin or other visual attribute to look like the video game that is currently playing. More about skin can be found at http en.wikipedia.org wiki Skin 28computing 29 Similarly suppose the application has several skins and wants to select one for every specific user. For this it scans the status of all tags around the receiver. Suppose it finds two black phones a metallic microwave and a silver game console. It could use this color information to select a skin that has a metallic look. This might be expected to be aesthetically pleasing to the user since the user has other devices with metallic looks. Analogously if several oval devices are in the room a skin with oval theme can be selected. These are examples of a device changing a visual attribute in response to a state of another device.

If a transmitted program has selectable plot or character options those might also be selected responsive to devices in the room. For instance if children s toys are detected plot or character options more suitable to children might be presented.

The antenna receives RF signals from all three tags and i.e. including from the tag of its own device. Accordingly the RF reader can act on all of this data.

The receiver will need to distinguish its own tag from the tags of the other devices. There are several ways in which this might be accomplished.

One is a Multimedia Home Platform MHP or OpenCable Applications Platform OCAP . More information about MHP can be found at http en.wikipedia.org wiki MHP OCAP is a similar system to MHP but intended for the US market.

A third module is the RF extension to the MHP OCAP which obtains an identification number ID from the RF tags associated with the various devices. If an application can know on which brand it is running on it can execute the program code that works for this specific brand. The module is an Application Program Interface API . More information about API s can be found at http en.wikipedia.org wiki API. The API interacts with a vendor data base . Code associated with the API and used to gather information as part of the invention is illustrated with respect to . is useful for MHP interoperability in other words making sure that MHP applications can run on any brand hardware. is useful for finding out characteristics of the environment of the user premises. gives a more detailed picture of the environment by retrieving more details from the devices in the neighborhood.

The invention could also be used in the context of an ordinary application not based on MHP or OCAP middleware. In that case instead of the RF extension to MHP OCAP there would be a software library.

MHP is an application execution environment that is independent of the underlying vendor specific hardware. This means that MHP applications shown at theoretically should be able to run on any MHP hardware of any brand. This is the theory but in practice it is very hard to write applications that work on all brands. Some program code needs to be different for different brands.

An example of this is to be found in . At the receiver decides that in order to draw something on a display screen it must hide the current video display of a television. How this is to be done will depend on the brand of the television. The MHP application is designed to be general purpose therefore it has code for several brands to allow it to hide video in different ways dependent on the design of the various brands. At the receiver scans its own device tag or what it believes to be its own device tag to determine what brand of television it finds itself in. If it determines that it is in a Brand A television then at it will issue a command to scale the video to . If a Brand B television is detected than at the MHP will issue a command to hide the video layer. If a Brand C television is detected than at the MHP will issue commands to pause the video and blank the screen. After the appropriate command is issued control proceeds to where other application tasks are continued.

The embodiments described above relate to an MHP application. The invention could also be applied to a PC environment with a PC application running under an operating system such as Windows rather than an MHP application. The Windows environment would have to be extended with the RF extension API. Other intelligent appliances such as mobile phones and PDAs might implement the invention as well. Other types of middleware software could be used instead of MHP OCAP such as the standards devised by the Multimedia and Hypermedia information coding Expert Group MHEG as described in http. en.wikipedia.org wiki Mheg OpenTV as described in http en.wikipedia.org wiki OpenTV MediaHighway http www.nds.com middleware middleware.html Liberate available from http www.liberate.com or JavaTV described at http java.sun.com products javatv overview.html.

From reading the present disclosure other modifications will be apparent to persons skilled in the art. Such modifications may involve other features which are already known in the design manufacture and use of control of electronic devices and methods for altering program behavior in response to outside data and which may be used instead of or in addition to features already described herein. Although claims have been formulated in this application to particular combinations of features it should be understood that the scope of the disclosure of the present application also includes any novel feature or novel combination of features disclosed herein either explicitly or implicitly or any generalization thereof whether or not it mitigates any or all of the same technical problems as does the present invention. The applicants hereby give notice that new claims may be formulated to such features during the prosecution of the present application or any further application derived therefrom.

The word comprising comprise or comprises as used herein should not be viewed as excluding additional elements. The singular article a or an as used herein should not be viewed as excluding a plurality of elements. The word or should be construed as an inclusive or in other words as and or .

