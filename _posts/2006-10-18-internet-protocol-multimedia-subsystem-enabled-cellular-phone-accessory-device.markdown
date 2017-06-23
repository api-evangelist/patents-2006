---

title: Internet protocol multimedia subsystem enabled cellular phone accessory device
abstract: A cellular phone accessory device () combined with an IMS client () is implemented to provide real time interactive multimedia applications to low end phones () and middle range phones () without having to re-engineer said phones. Said device behaves as a cellular phone accessory and IMS client that is implemented using client control, protocol components () and IMS client media components (). Said device comprises of general purpose processor () and digital signal processor () connected using a DSP bridge ().
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07606595&OS=07606595&RS=07606595
owner: 
number: 07606595
owner_city: 
owner_country: 
publication_date: 20061018
---
This is the utility patent of provisional Patent Application U.S. 60 728 884 with a priority date of Oct. 20 2005.

The present invention generally relates to internet protocol IP cellular phone accessory devices and specifically to IP multimedia subsystem IMS enabled cellular phone accessory device to enable mass deployment of IP multimedia services in a cellular network.

Cellular phone accessory market is a well established market with several kinds of accessories available to enhance user experience. Accessories can be wired or wireless or available as attachments. Some examples of commonly available accessories are headset keyboard speakerphone camera and display. A cellular phone accessory is defined to be a device that is controlled by the cellular phone and either extends or partitions existing functionality into an easy to use device. This implies that there exist a master slave relationship between a cellular phone and an accessory wherein cellular phone is master and accessory is slave.

In some situations a cellular phone gets used as a slave and other devices such as a personal computer PC control the cellular phone. In these cases the master slave relationship is reversed and a cellular phone gets used as a slave and serves as a data modem. In this setup where a cellular phone is used as a data modem cellular phone is termed as mobile termination equipment MT and personal computer that controls cellular phone is termed as terminal equipment TE .

This MT TE relation enables any data oriented service to be available to a user using a cellular network since a cellular phone acts as a cellular gateway to internet protocol network. In particular real time interactive applications using internet protocol multimedia subsystem IMS can also be supported.

Thus it is to be noted that a cellular phone accessory extends existing cellular phone functionality in hardware whereas a cellular phone used as a data modem extends functionality in software with new IMS applications that can be executed on terminal equipment. A software functionality extension using MT TE relation serves cellular phones that do not have ability to run new software whereas a cellular phone accessory device serves cellular phones with limited hardware features. So both relations serve a useful purpose but each is offered as a different device combination. That is to have extended hardware functionality and extended software functionality a person would have to carry a cellular phone a cellular phone accessory device and terminal equipment resulting in a total of three devices.

Hence a user would have to carry three devices if there is a need for both hardware and software functionality extension which is not a preferable solution by most users.

To alleviate this problem that a user would have to carry three devices a cellular phone that is programmable could be used instead of a non programmable cellular phone. Such programmable phones exist in market but are available in very low volume and very expensive compared to low end and middle range phones. This is due to the fact that low end and middle range phones use application specific integrated circuits to reduce power usage and bill of materials whereas completely programmable phones have to offer sophisticated operating systems and corresponding extended set of bill of materials.

Cellular phones are categorized into low end middle range and high end phones also called smart phones. Only high end phones support general purpose programmability. General purpose programmability provides a programmable platform to support both real time interactive and non interactive multimedia applications. There are several design challenges to provide complete general purpose programmability even in high end programmable smart phones. A list of challenges is given below.

Hence it can be seen that offering new functionality through smart phones although technically feasible is not a viable business solution due to its low volume and fragmented programming environment.

For high volume it is necessary that a solution that offers both hardware and software extension work with low and middle range phones.

Low end phones are not programmable and middle range phones offer minimal programmability with downloadable software using Sun Microsystems Java 2 Micro Edition J2ME or Qualcomm BREW environments. In particular IMS applications require interfaces to digital signal processing unit to get access to encoded multimedia bits. This is not provided in either low end or middle range phones.

Thus neither smart phone solutions nor a low end or middle range phone solutions can offer extended set of hardware and software functionality without compromising the business case of leveraging high volumes of low end and middle range phones.

Hence it can be seen that a device that can offer hardware extension as a cellular phone accessory device and software extension for real time interactive multimedia programmability will solve the above mentioned three device problem while leveraging mass market penetration of low and middle range phones.

This device of present invention is a combination of a cellular phone accessory functionality and terminal equipment programmability to support real time interactive multimedia applications. A device that is a cellular phone accessory provides hardware extension and a device that behaves as a TE is also programmable. Hence such a combination of a cellular phone accessory and terminal equipment would solve both problems including lack of real time interactive multimedia programmability of low to middle range phones and limited market penetration of smart phones.

The combination device is achieved by incorporating real time interactive multimedia functionality as described in internet IMS specifications from standards body third generation partnership project 3GPP into a cellular phone accessory device. IMS specifications prescribe an IMS client and an IMS server that interoperate to provide real time interactive multimedia applications. Hence a device that is both a cellular phone accessory and an IMS client will enable new real time interactive multimedia applications while working with low end and middle range phones. This device shall be referred to as IMS accessory device henceforth.

IMS accessory device is unique and is not known to exist in prior art. This will become very evident by the following description about prior art.

The prior art description is structured as follows first functional description of prior art IMS client is covered second functional description of cellular phones and challenges in enabling real time interactive multimedia services in cellular phones are described finally the inadequacy of existing solutions for enabling real time interactive multimedia services on low end and middle range phones is described.

One way to overcome the limitations described for low end phones and middle range phones is to build new features and functionality into cellular phone accessory that can interoperate with low end phones and middle range phones . These accessories themselves can add features requiring no changes to major changes to software and or hardware components in the cellular phones. Hence an ideal IMS accessory should provide IMS client functionality without calling for any changes to software and hardware components in the cellular phones in order to interoperate with widest range of low end phones and middle range phones .

US Doc 20020068600 proposes a mobile video phone system comprising a mobile telephone device wearable radio communication device with display and an optional radio headset. It primarily addresses the ease of use issue of video telephony. The mobile telephone device co ordinates the exchange of images video between remote user and wearable radio communication device with display. Also the mobile telephone device co ordinates the exchange of voice between remote user and radio headset. This system does not provide IMS client functionality and hence does not support real time interactive IP multimedia services and additionally this system calls for moderate to significant software changes in the mobile telephone device.

U.S. Pat. No. 6 768 911 proposes a mobile communication terminal device consisting of mobile communication device with detachable display and ear phone component. The communication device and the components communicate using short distance radio technology bluetooth. This prior art primarily addresses the size and portability of the device while maintaining rich functionality. This system does not provide IMS client functionality and hence does not support real time interactive multimedia services and additionally does not provide interoperability with existing low end and middle range phones.

U.S. Pat. No. 6 731 951 shows a cellular device having two parts one having cellular communication support and bluetooth link that can be stored away or used as a modem with PC or can work with the second component which is having input and output device display keyboard camera and a bluetooth link. Obvious advantage being that the second device is small easy to carry small size battery and first unit being not close to the body better signal strength for cellular connection and hence better battery life. This system does not provide IMS client functionality and hence does not support real time interactive multimedia services. Also the system calls for significant hardware and software changes to existing phones to interoperate.

U.S. Pat. No. 5 590 417 proposes a detachable headset device as an accessory to a cellular phone. The detachable headset when attached to phone can function as a speaker and microphone. The headset can also be detached and placed on the head of the user. In this mode of operation the headset and the cellular phone communicate using low power RF transceivers. This system does not provide IMS client functionality and hence does not support real time interactive multimedia services.

U.S. Pat. No. 6 788 332 introduces a digital camera with wireless link that can operate with Personal digital assistant PDA or cellular phone to communicate with images or facsimiles to a remote user by setting by data call. This system does not offer real time interactive multimedia services.

Some prior art systems provide additional features and services by using PC and PDA as TE programmed with new functionality and simply treating the cellular phone as modem or MT. These systems implement IMS client functionality by splitting the implementation between cellular phone or MT and PC and PDA or TE. For interoperability with widest range of low end and middle range phones the functional split should call for no changes in cellular phone or MT. Additionally the ideal solution will implement IMS client functionality as a TE and also function as an accessory such as hands free phone or headset or viewer to the cellular phone for at most convenience to the end user.

US Doc 20030210678 proposes a method for connecting TE to IMS server using a cellular phone as MT. This method calls for functional split in implementing IMS client functionality between TE and MT. As per the method proposed in this prior art terminal equipment performs protocol stream functions including real time transport protocol RTP and real time transport control protocol RTCP functions. The MT performs IMS proxy functions such as identification or authentication functions as well as call control functions. Implementing IMS proxy function in mobile terminal limits the terminal equipment interoperability to selected mobile terminals that support IMS proxy function. Additionally this solution does not combine terminal equipment function with cellular phone accessory function for end user convenience.

U.S. Pat. No. 6 788 676 proposes user equipment that includes a MT coupled to a TE. The TE includes IMS proxy adjunct which implements extensions needed in session initiation protocol SIP and session description protocol SDP for connectivity to IMS server. The user agent UA running on TE uses IMS proxy adjunct for accessing IMS services. Additionally IMS proxy adjunct also implements support for quality of service QoS between TE and MT and also between TE and IMS server. This prior art primarily addresses the need of terminal equipment with regular SIP UA to communicate with IMS server through IMS proxy adjunct and this scheme is more suited for IMS enabling existing PC or PDA based regular SIP applications. Hence this prior art does not address a solution that implements IMS client functions as a cellular phone accessory. Also this prior art does not address the issue of enabling IMS services to work with low end and middle range cellular phones.

As can be seen from above no known prior art shows a device that is both a cellular phone accessory and an IMS client to deliver new real time interactive multimedia applications to mass market without said re engineering efforts.

In accordance with present invention a cellular phone accessory device combined with an IMS client is implemented to address said issues that prevent delivery of new real time interactive multimedia applications to low end and middle range phones.

Real time interactive multimedia applications require special chipset architectures and access to digital signal processing unit. These are usually not available in low end and middle range cellular phones since cellular phone designs are aligned with chipset configurations. Chipset configurations for cellular phones are cost optimized for low middle and high end phones. Currently real time interactive multimedia applications can only be supported on high end chipsets and corresponding high end phones.

But high end phone market is fragmented and low in volume shipments as compared with low end and middle range phones. This brings out a serious challenge of delivering new real time interactive multimedia applications to low end and middle range phones.

Real time interactive multimedia applications platform is standardized by 3GPP as IMS client and server. In order to deliver real time interactive multimedia applications an IMS client has to be either implemented in the cellular phone or has to be provided as an external functionality. Implementing IMS client in a low end or middle range cellular phone suffers from the same issues of portability chipset architecture differences and DSP access problems. Implementing IMS client as terminal equipment such as a PC or a PDA to provide real time interactive multimedia applications is impractical in terms of size usability and cost.

On the other hand a cellular phone accessory is comparatively smaller in size and cost effective to enable a user to carry it along with cellular phone. But all current known cellular phone accessories are limited in functionality and provide minimal programmability and hence cannot support full fledged real time interactive multimedia applications.

Hence it can be seen that there is a need for a system that strikes a balance between real time interactive multimedia programmability portability usability cost and mass market appeal to enable new real time interactive multimedia applications to be deployed with low and middle range phones.

Such a system is achieved by a unique new device that is a combination of an IMS client with supporting chipset architecture DSP access and form factor and functionality of a cellular phone accessory. This device is referred to as IMS accessory device.

IMS accessory device provides an unobvious result of enabling new real time interactive multimedia applications to mass market low end and middle range phones striking a fine balance between real time interactive multimedia programmability portability usability cost and mass market appeal.

This section first covers an overview of the invention as shown in . It is then followed by description of how this invention fits in with various cellular phone accessory configurations as shown in and . Finally the invention as shown in is described in detail.

IMS accessory can be used uniquely in two different ways with cellular phones to provide enhanced services and end user convenience.

Following paragraphs describe the invention IMS accessory as shown in the in detail. First operational aspects of IMS accessory as IMS client are described and then operational aspects as cellular phone accessory are described.

As shown in prior art IMS client consists mainly of two software components namely IMS control protocol components referred as IMS control and IMS media components referred as IMS media . In accordance with preferred embodiment as shown in IMS accessory hosts IMS control in GPP and IMS media in DSP . IMS accessory addresses all the shortcomings of prior art low end phones and middle range phones for supporting IMS client .

c DSP has sufficient processing and memory resources to support IMS media . This is because unlike prior art low end phones and middle range phones DSP is not burdened with 2.5 G cellular packet switching protocol stack such as GPRS.

Thus as far as supporting IMS services IMS accessory is comparable to high end phones but this is achieved without the associated limitations such as high cost bulkiness and limited market penetration.

As shown in bluetooth transceiver hosts short range radio interface and its baseband whereas bluetooth host is hosted by GPP . Bluetooth host consists of host side stack layers as specified by bluetooth special interest group SIG such as logical link control and adaptation L2CAP link manager protocol LMP service discovery protocol SDP radio frequency communication RFCOMM layers. Additionally bluetooth host also includes various profiles to enable IMS accessory to be used as phone accessory namely Hands free profile headset profile subscriber information module SIM and personal area network PAN profiles.

In accordance with its preferred embodiment IMS accessory can be packaged and made available in various user friendly packages such as wearable over the ear headset wearable pen shaped device and wearable as a badge or a clip.

Alternative short range radio technology such as wireless local area network IEEE 802.11 can be used instead of bluetooth in IMS accessory to produce alternate embodiment.

IMS accessory can be packaged in various form factors based on prevailing market needs and customer taste.

IMS accessory can also be built without DSP and instead GPP can be built with sufficient processing and memory resources to host IMS media . This decision is primarily driven by type of multimedia applications types of general purpose processor availability and associated cost factors.

Accordingly the reader will see that combining an IMS client with a cellular phone accessory device provides real time interactive multimedia programmability portability usability cost effectiveness and mass market appeal to deliver new real time interactive multimedia applications to end user.

Although the description above contains much specificity these should not be construed as limiting the scope of invention but merely as providing illustrations of some of the presently preferred embodiments of this invention. Thus the scope of this invention should be determined by appended claims and their legal equivalents rather than by example given.

