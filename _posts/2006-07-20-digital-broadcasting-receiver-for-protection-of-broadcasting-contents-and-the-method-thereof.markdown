---

title: Digital broadcasting receiver for protection of broadcasting contents and the method thereof
abstract: Provided are a digital broadcasting receiver and method of broadcast content protection. The digital broadcasting receiver comprises a platform which stores received broadcast data, middleware which comprises an application manager managing various applications so that broadcast content corresponding to the received broadcast data is used according to a consumption policy, a platform interface unit which acts as an interface between the platform and the middleware, and a middleware interface unit which acts as an interface between the various applications and the middleware. According to the method, various broadcast content protection and management policies can be accepted in various digital broadcasting receivers, each having different hardware and software structures.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08677500&OS=08677500&RS=08677500
owner: Electronics and Telecommunications Research Institute
number: 08677500
owner_city: Daejeon
owner_country: KR
publication_date: 20060720
---
The present invention relates to a digital broadcasting receiver and method of broadcast content protection and more particularly to a digital broadcasting receiver and method which apply a middleware interface for broadcast content protection.

Digital Broadcasting receivers are apparatuses which enable a user to receive broadcast data through a broadcasting network and use the broadcast data according to consumption policy. Here the broadcast data includes broadcast content such as video audio or data and protection management information which enables the broadcast data to be used according to the consumption policy. The consumption policy is a policy that allows an authorized user to normally use the broadcast content. That is the consumption policy is a policy about access to enable the use of the broadcast content.

Meanwhile the digital broadcasting receivers have a hardware structure and software structure different from each other. Also the consumption policy differs based on broadcast content. Accordingly to support these various environments middleware is required which supports various applications and a middleware interface for the middleware should be defined.

The present invention provides a digital broadcasting receiver and method which enable a user to safely and rightfully access broadcast content using a broadcast content protection management interface which is a middleware interface while accepting various broadcast content protection and management policies in various digital broadcasting receivers having different hardware and software structures.

According to an aspect of the present invention there is provided a digital broadcasting receiver for broadcast content protection the digital broadcasting receiver including a platform which stores received broadcast data middleware which comprises an application manager managing various applications so that broadcast content corresponding to the received broadcast data is used according to a consumption policy a platform interface unit which acts as an interface between the platform and the middleware and a middleware interface unit which acts as an interface between the various applications and the middleware.

The application manager may include a tool detector which detects tool information related to protection management of the broadcast content included in the received broadcast data based on the received broadcast data and a tool operator which operates a protection management tool that corresponds to the detected tool information.

The application manager may further include a tool remover which removes information on the protection management tool which has finished operating from an operation tool list containing information on the operating protection management tool.

The tool detector may include a data obtainer which is provided with the broadcast data from the platform a protection management information searcher which searches for protection management information related to the protection management of the broadcast content from the obtained broadcast data and a tool information detector which detects tool information related to the protection management of the broadcast content by analyzing the protection management information.

The tool operator may include a registration determiner which determines whether a protection management tool corresponding to the detected tool information is registered an initiating unit which initiates the registered protection management tool and an operator which operates the initiated protection management tool.

The tool operator may further include a tool obtainer which obtains a protection management tool corresponding to the detected tool information through the platform when the protection management tool corresponding to the detected tool information is not registered and registers the obtained protection management tool by installing the obtained protection management tool.

According to another aspect of the present invention there is provided a method of broadcast content protection in a digital broadcasting receiver comprising a platform middleware and various applications the method including the platform storing received broadcast data and the middleware managing the various applications so that broadcast content corresponding to the received broadcast data is used according to a consumption policy through a platform interface which acts as an interface between the middleware and the platform and a middleware interface which acts as an interface between the middleware and the various applications.

The managing of the various applications may include detecting tool information related to protection management of broadcast content contained in the broadcast data based on the received broadcast data and operating a protection management tool that corresponds to the detected tool information.

The managing of the various applications may further include removing information on the protection management tool which has finished operating from an operation tool list containing information on the operating protection management tool.

The detecting of the tool information may include being provided with the broadcast data from the platform searching for protection management information related to the protection management of the broadcast content from the obtained broadcast data and detecting tool information related to the protection management of the broadcast content by analyzing the protection management information.

The operating of the protection management tool may include determining whether a protection management tool corresponding to the detected tool information is registered initiating the registered protection management tool and operating the initiated protection management tool.

The operating of the protection management tool may further include obtaining a protection management tool corresponding to the detected tool information through the platform when the protection management tool corresponding to the detected tool information is not registered and registering the obtained protection management tool by installing the obtained protection management tool.

Hereinafter the present invention will be described more fully with reference to the accompanying drawings in which exemplary embodiments of the invention are shown.

Referring to a demodulating unit receives broadcast data provides multiplexed audio video data transmission streams to a DEMUX demultiplexer unit and provides access control information on the multiplexed audio video data transmission streams to an access controlling unit .

The DEMUX unit separates the multiplexed audio video data transmission streams into separate element streams and provides each element stream to a decoding unit and a storing unit .

The access control unit generates a first control signal which can control each element stream and a second control signal related to the storing of the element streams according to a consumption policy corresponding to the current transmission stream based on the access control information. Accordingly the access control unit provides the first control signal to the DEMUX unit and the second control signal to the storing unit .

The decoder unit decodes the element streams provided by the storing unit or the DEMUX unit and provides audio video data which is the result of the decoding to an A V D expressing unit .

Meanwhile broadcast service providers who provide various broadcast services each apply a specific consumption policy on protecting and managing broadcast content. Accordingly it is impossible for a current digital broadcasting receiver to receive all of these various protection and management policies. Subsequently ISO ITU JTG 1 SC29 WG11 MPEG prepared a framework to apply various multimedia content protection management policies by providing a standard called MPEG Intellectual Property Management and Protection IPMP .

Using the IPMP technique distribution of content between various content providers and users can be done safely and easily based on a digital right management DRM structure.

In sections connected to an IPMP terminal are sections where a consumption policy can be applied before a user uses multimedia content. In other words each connected section is where the IPMP terminal can access and control multiplexed MPEG 2 transmission streams video audio streams and video audio data.

For example in the case of a MPEG 2 transmission stream a consumption policy can be specified on header information of the MPEG 2 transmission stream. In the case of a video audio stream a policy which can decode each encoded stream can be applied. Also in the case of video audio data which passed through a decoder the IPMP terminal can apply a policy which can detect transformation reproduction or the like of the video audio data using signature information watermark information etc. contained in the video audio data.

That is the digital broadcasting receiver includes an application manager in order to control a protection management policy for application and broadcast content through a middleware API layer.

The platform of the digital broadcasting receiver includes an audio video data processor a media protection manager and an operation organizer .

The audio video data processor embodies an audio decoding function a video decoding function and a graphic processing function in hardware.

The operation organizer manages the entire operation of the digital broadcasting receiver using support from a central processor a network processor and a storing unit .

The platform stores received broadcast data for example in the storing unit but it is not limited thereto. Hereinafter a structure providing the received broadcast data shall be called an initiator for convenience.

The media protection manager protects and manages broadcast content from among the broadcast data stored in the platform .

The application includes a resident application a plugin application and other applications . The IPMP terminal exists in a form of the resident application . Also various protection management tools exist in a form of the resident application or the plugin application and are supported by the middleware by using a middleware application programming interface API .

The middleware exists to ensure compatibility between various platforms and various applications and supports detailed operation of the various applications through the middleware interface unit . The middleware interface unit acts as an interface between the resident application the plugin application and the middleware in the middleware API form.

The IPMP terminal is installed in the resident application form and performs a protection management function corresponding to a consumption policy of broadcast content based on support from the middleware .

Referring to the middleware specifically includes the application manager to support consumption according to a consumption policy of the broadcast content.

The tool detector detects tool information related to protection management of the current broadcast content based on received broadcast data. Referring to the tool detector includes a data obtainer a protection management information searcher and a tool information detector .

The data obtainer is provided with all or part of the received broadcast data from the platform through the platform interface unit .

The protection management information searcher searches for protection management information related to the protection management of the current broadcast content from among the broadcast data.

The tool information detector analyzes the protection management information and detects tool information related to the protection management of the current broadcast content.

The tool operator operates a protection management tool corresponding to the detected tool information. Referring to the tool operator includes a registration determiner an initiating unit an operator and a tool obtainer . The registration determiner determines whether a protection management tool corresponding to the detected tool information is registered.

The tool obtainer obtains a protection management tool corresponding to the detected tool information through the platform when the protection management tool corresponding to the detected tool information is not registered and registers the obtained protection management tool by installing the obtained protection management tool. The initiating unit initiates the protection management tool corresponding to the detected tool information. The operator operates the initiated protection management tool.

The tool remover receives completion information of the operating protection management tool and removes the operating protection management tool from an operating operation tool list.

Meanwhile the protection management tool is installed in the resident application form or the plugin application form and operates according to a command from the operator . In detail the protection management tool performs a corresponding tool processing function an authentication function an encrypt function a decrypt function a watermark embedding function a watermark detecting function or the like by receiving support from the middleware by using middleware API such as toolprocessing authentication encyript decrypt embedWatermark or detectWatermark . When the protection management tool finishes operating information on tool operation termination is provided to the application manager using terminateTool which is middleware API. Accordingly the tool remover of the application manager receives the information on tool operation termination and removes the operating tool from the operating operation tool list.

In other words illustrates how the application manager operates by using the middleware API layer. As shown in middleware API of the application manager defines an interface between an initiator an IPMP terminal and a protection management tool . Various protection management tools operate through the interface according to a consumption policy of broadcasting content.

Referring to in operations S and S the IPMP terminal ensures that the data obtainer is provided with all or part of the broadcasting data received from the initiator through the platform interface unit using middleware API named getStreamData and return .

In operation S the IPMP terminal makes the tool information detector analyze the protection management information and detect tool information related to protection management of the current broadcasting content using middleware API named retrievelPMPInfo .

In operation S the IPMP terminal makes the protection management information searcher search for protection management information related to protection management of the current broadcast content from the broadcast data using middleware API named parselPMPInfo .

In operations S and S the IPMP terminal makes the registration determiner determine whether a protection management tool corresponding to the detected tool information is registered using middleware API named getTools and return .

In operations S and S the IPMP terminal makes the tool obtainer obtain a protection management tool corresponding to the detected tool information through the platform and then register the obtained protection management tool by installing the obtained protection management tool using middleware API named retrieveMissingTool and return when it is determined that a tool corresponding to the detected tool information is not registered.

In operations S and S the IPMP terminal makes the initiating unit perform initiation so that the protection management tool can properly operate using middleware API named initTool .

In operation S the IPMP terminal makes the operator operate the initiated protection management tool using middleware API named operateTool . At this time the application manager includes the currently operating protection management tool in the operation tool list.

In operation S the protection management tool performs the corresponding work by receiving support from the application manager using middleware API named toolProcessing . In operation S termination information of the operating protection management tool is transmitted to the application manager and the IPMP terminal using middleware API named terminateTool .

In operation S the IPMP terminal makes the tool remover receive termination information of the operating protection management tool and remove the operating protection management from the operating operation tool list using middleware API named revokeTool .

The protection management tool above is a tool application for detecting a watermark contained in broadcast content and is terminated when the watermark is detected. The protection management tool is generally used in order to use the detected watermark according to a consumption policy before broadcast content is used.

The invention can also be embodied as computer readable codes on a computer readable recording medium. The computer readable recording medium is any data storage device that can store data which can be thereafter read by a computer system. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy discs optical data storage devices and carrier waves such as data transmission through the Internet . The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. Also functional programs codes and code segments for accomplishing the present invention can be easily construed by programmers skilled in the art to which the present invention pertains.

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims.

According to the present invention various broadcast content protection management policies can be easily applied to various digital broadcasting receivers each having different hardware and software structures. Accordingly broadcast service providers can provide stable and various broadcast services by deciding on a protection management policy suitable for the broadcast content itself and not by deciding on a protection management policy considering a digital broadcasting receiver.

