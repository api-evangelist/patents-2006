---

title: Signal processing apparatus, signal processing method, and recording medium
abstract: A signal processing apparatus includes the following elements. A plurality of signal processing software modules perform unit signal-processing steps of signal processing by means of software processing. An instruction input receiving unit receives an instruction. A virtual connecting unit sets up a virtual connection between inputs and outputs of the signal processing software modules in response to the received instruction. A circuit structure information storing and managing unit stores and manages the virtually connected signal processing software modules. A path routing unit routes a signal processing path to determine the order in which the stored signal processing software modules perform the signal processing. A signal processing executing unit performs the signal processing by sequentially executing the signal processing software modules in the determined order. The path routing unit determines whether a feedback loop including no delay element is generated in a circuit composed of the signal processing software modules.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07954113&OS=07954113&RS=07954113
owner: Sony Corporation
number: 07954113
owner_city: Tokyo
owner_country: JP
publication_date: 20060120
---
The present invention contains subject matter related to Japanese Patent Application JP 2005 012256 filed in the Japanese Patent Office on Jan. 20 2005 the entire contents of which are incorporated herein by reference.

The present invention relates to a signal processing apparatus and method for performing signal processing including a plurality of unit signal processing steps by means of software processing and to a recording medium storing a program for signal processing.

Recently increasingly high performance computers have been commercially available and moving pictures and music have been reproducible on the computers which was difficult in the past. Particularly there have been available video and audio signal processing applications capable of easily performing real time signal processing by means of software processing without using traditional dedicated signal processing devices such as digital signal processors DSPs or dedicated hardware.

Such signal processing applications are supported by various types of signal processing middleware such as DirectShow which is a product of Microsoft Corporation MATLAB which is a product of The MathWorks Inc. and Max MSP which is a product of Cycling 74.

With the use of such middleware signal processing applications can comparatively easily implement sophisticated features. For example audio features such as recording and reproduction input and output mixing and special effects are implemented by means of signal processing applications. Video signal processing applications having sophisticated editing features such as non linear editing have also been available.

Middleware systems with a plugin configuration are disclosed in Japanese Unexamined Patent Application Publications No. 2001 109628 and No. 7 302195. A plugin is a software application that carries out a modularized feature. This document deals with signal processing. Thus a plugin is a software application implementing a signal processing software module.

A plugin allows a user to add on and use a desired signal processing software module as needed. While plugins are generally used individually novel systems that allow multiple features with a combination of plugins have recently been developed. In the future such multiple plugin systems will become the mainstream of new added value systems.

 a As plugins are connected in multiple stages the processing delay latency proportionally increases.

 e It is difficult to implement the sample accuracy for synchronization between audio and video or changing parameters.

Several existing middleware systems partially overcome the foregoing drawbacks however there no middleware system that simultaneously overcomes all the drawbacks mentioned above because some of them are in conflict with each other that is a problem is overcome which then adversely affects another problem . For example it is difficult to concurrently overcome the drawbacks b and d .

Such drawbacks may sometimes cause a critical bottleneck for incorporation of the systems into traditional middleware products.

The present inventors have proposed a signal processing apparatus that overcomes the foregoing drawbacks. This signal processing apparatus allows a feedback loop to be closed without limitations in the connection between plugins.

However this signal processing apparatus still has an inevitable issue that is a general principle of digital signal processing namely a requirement of at least one or more delay elements being included in a feedback loop in a signal flow graph.

This is necessary to satisfy the causality constraint for signal processing. For example when a user is to create a feedback loop circuit including no delay element using the above described signal processing apparatus or the like it is desirable that this signal processing operation immediately be canceled or ceased because the user will not obtain correct signal processing results. The circuit could output an unnecessary signal such as noise because of the inability of the circuit to perform correct signal processing.

Such a user operation is common and there arises a problem that the process of producing a signal processing circuit on a signal processing apparatus is cumbersome and unfamiliar to particularly users who do not have the knowledge of the requirement of a delay element being included in a feedback loop.

It is therefore desirable to provide a signal processing apparatus that overcomes the foregoing drawbacks in light of this problem.

According to an embodiment of the present invention a signal processing apparatus for performing signal processing including a plurality of unit signal processing steps by means of software processing includes the following elements. A plurality of signal processing software modules perform the unit signal processing steps by means of software processing. Instruction input receiving means receives an instruction to generate or delete a signal processing software module and an instruction to connect inputs and outputs of the signal processing software modules. Virtual connecting means sets up a virtual connection between the inputs and the outputs of the plurality of signal processing software modules in response to the instruction received by the instruction input receiving means. Circuit structure information storing and managing means stores and manages the set up virtual connection between the inputs and the outputs of the plurality of signal processing software modules. Path routing means routes a signal processing path to determine the signal processing order in which the plurality of the signal processing software modules stored in the circuit structure information storing and managing means perform the signal processing. Signal processing executing means performs the signal processing by sequentially executing the plurality of signal processing software modules in the signal processing order determined by the path routing means based on the signal processing path. The path routing means determines whether or not a feedback loop including no delay element is generated in a circuit composed of the plurality of signal processing software modules.

The signal processing apparatus may further include warning means for sending a warning to a user when the path routing means determines that a feedback loop including no delay element is generated in the circuit composed of the plurality of signal processing software modules.

Accordingly when a feedback loop including no delay element is generated in a circuit composed of signal processing software modules a warning is sent to the user. Thus a user who does not have the knowledge of the requirement of a delay element being included in the feedback loop can take an appropriate action.

When the path routing means determines that a feedback loop including no delay element is generated in the circuit composed of the plurality of signal processing software modules the path routing means may insert an additional delay element in the feedback loop.

Accordingly when a feedback loop including no delay element is generated in a circuit composed of signal processing software modules an additional delay element is automatically inserted in the feedback loop. Thus a user who does not have the knowledge of the requirement of a delay element being included in the feedback loop can easily set up a circuit including a feedback loop.

A signal processing apparatus according to an embodiment of the present invention will be described hereinafter with reference to the drawings.

A signal processing apparatus according to an embodiment of the present invention is implemented as general purpose signal processing middleware. The middleware is hereinafter referred to as a software signal processor SSP . In the following embodiments signal processing will be discussed in the context of audio signal processing.

The SSP as shown in resides between a general purpose operating system OS and application software. With the use of the SSP the application software easily implements sophisticated signal processing features. The SSP is middleware that needs no graphical user interface GUI and is thus useful for signal processing engines used for embedded equipment having no display device.

The SSP which is an implementation of a signal processing apparatus according to an embodiment of the present invention is middleware with a graph structure and is basically implemented on a single computer. However as discussed below the SSP may be implemented on a plurality of computers connected via a network.

A signal processing apparatus according to an embodiment of the present invention which is implemented as SSP is composed of two parts a graph module implemented by software hereinafter referred to simply as a graph and a plugin module implemented by software hereinafter referred to simply as a plugin .

The plugin module is a signal processing software module for executing a unit signal processing step such as filter equalizer or gain control.

In this example the plugin may have a plurality of input ports and a plurality of output ports. The plugin performs signal processing unique to the plugin on audio signals input from the input ports and outputs the resulting signals from the output ports.

An output port of a plugin is connected to an input port of another plugin this connection is a virtual connection which means that an output signal from a plugin is input to another plugin rather than a hardware connection. This virtual connection is hereinafter referred to as a connection . A plurality of plugins can be connected to implement multiple signal processing features. The plugins are connected only by connecting an input port of a plugin to an output port of another plugin. The connection of input ports of plugins or output ports of plugins is not permitted.

The graph plays a roll of an SSP system and is adapted to include a plurality of plugins. The graph holds various signal processing functions. In response to an operation input from a user the graph generates or deletes a plugin or connects ports of plugins and holds resulting circuit structure information. The signal processing functions stored in the graph include a plugin generating and deleting function. Inside the graph therefore an arbitrary circuit composed of a plurality of plugins can be set up.

The graph when a signal processing function of this graph is called sequentially transfers received audio data with time information to the plugins included in the graph. The graph also plays a role of inputting and outputting audio data and attached information to the plugins.

Further the graph includes the properties of a plugin. Thus like plugins the graph has input and output ports so that the graph can be interconnected with another plugin. With the ability of a graph to include a plurality of plugins by creating a graph a circuit block graph composed of a plurality of plugins can be handled as a single plugin. The graph handled as a single plugin has a function for handling a collection of circuits as a single component.

In the example shown in a user first creates a basic root graph and then creates a circuit composed of a plurality of plugins to in the graph . The plugins to may be selected from plugins pre stored in the PC. The pre stored plugins are stored in the form of templates called object oriented classes before objects are actually generated.

For example the user selects the plugins to from plugins stored in a storage unit of the PC and dynamically generates or maps the selected plugins to in the graph . Object oriented objects are thus generated. The user instructs that output ports and input ports of the plugins to be connected and that the graph and the plugins and be connected thereby setting up a circuit shown in .

The graph holds circuit structure information of the internal plugins to . Once the user calls a signal processing function of the root graph signal processing functions of the internal plugins to are sequentially called recursively from within the signal processing function of the root graph and calculations associated with the signal processing are successively performed. The propagation of the recursive signal processing function calls is an implementation of the SSP system itself.

In a parent graph holds a graph which is a child graph and a plugin . The child graph holds plugins and . The plugins and insides the child graph are hidden from the parent graph and the child graph is viewed as a single plugin.

First the user creates a root graph i.e. the parent graph which is a root. Once the user calls a plugin generating and deleting function of the root graph the child graph and the plugin is generated inside the root graph.

When the user calls a plugin generating and deleting function of the child graph the plugins and are generated in a similar manner.

In order to perform signal processing first the user calls a signal processing function of the root graph . Then signal processing functions of the child graph handled as a plugin and the plugin inside the root graph are sequentially called recursively from within the signal processing function of the root graph and calculations are successively performed. The order of the recursive signal processing function calls is also determined by the graph.

In the child graph the signal processing function of the child graph is first called. Then the signal processing functions of the plugins and inside the child graph are sequentially called recursively from within the signal processing function of the child graph and calculations are successively performed.

An implementation of the SSP system is the above described graph operation itself. The graph or the plugin itself deals with the functions needed for the system such as the generation and deletion of a plugin the connection between plugins the transfer of data between the plugins the application of synchronization between time information and audio and video information to a plugin sequential calls of signal processing functions of the plugins and the determination of the order of the function calls.

A plugin class CPlugin inherits a plugin interface IPlugin and implements a plugin unique interface. The plugin class holds a plurality of input port classes CInputPort and output port classes COutputPort .

There are multiple types of plugin classes depending on their functions. For example an adder plugin class is a plugin class for performing addition and a multiplier plugin is a plugin class for performing multiplication. These classes are classified as user s own plugin CMyPlugin class. The user s own plugin class inherits the plugin class. In this example the middleware user uses a plugin template to easily create his her own plugin.

Next a graph class will be described. A graph class CGraph includes a plurality of plugin classes. Like the plugin class the graph class also inherits the plugin interface IPlugin and is also a plugin class.

The graph class thus has a recursive hierarchical structure in which a graph includes another graph and a plugin. This structure corresponds to a structure called a composite pattern in general object oriented design patterns.

Further the graph also includes the properties of a plugin. Thus like other plugins the graph has input and output ports so that the graph can be interconnected with another plugin. Once a graph object is created a circuit block composed of a plurality of plugin objects is handled as a single component object.

The interfaces APIs of the graph class and the plugin class are defined. By calling the APIs from an SSP middleware client application the objects are controllable. The operation performed by the user for the SSP system is performed on these two types of objects.

As shown in the plugin can include a signal processor zero or more input ports and zero or more output ports . That is the plugin may include no input ports or no output ports or may include one or a plurality of input ports and one or a plurality of output ports .

The plugin can exchange signals e.g. audio data with another plugin or other plugins via the input port or ports and the output port or ports . In this example audio signals of one channel per port are input and output.

The user instructs the plugin to add or delete the input port and the output port thus dynamically changing the number of input ports and output ports of the plugin even during signal processing. The input ports and the output ports are assigned identification numbers 0 to N where N is any natural number and 0 to M where M is any natural number respectively according to the order in which the ports are added. The user selects identification numbers to specify one of the input ports and one of the output ports .

The plugin further includes zero or more parameter holding sections parameter buffers for storing zero or more parameters. The parameters are variable values for setting the amount of effects in signal processing and so forth and are entered by the user. For example when the plugin is implemented as an amplifier the parameters include an amplification gain value. The user of the plugin changes the parameter values of the plugin to change the effects of signal processing.

In this example the parameters are assigned identification numbers 0 to K where K is any natural number. The user specifies the identification number of any parameter to change the content of the buffered parameter at an arbitrary timing. In the mechanism of the plugin a parameter given by the user is stored in the parameter buffer inside the plugin . A parameter is read according to the time information synchronized with sample data provided from the system i.e. the graph and is then transmitted to the signal processor for its signal processing.

The plugin further includes a time information register that constantly receives time information from the SSP system i.e. the graph . The time information represents the number of accumulated counts of audio input or output data samples starting at the start time of the SSP system that is the start time of the signal processing function of the graph . The number of accumulated counts is the most basic time information in the SSP system.

In the SSP system of this embodiment the time information and the audio input or output data are completely synchronized with each other. The SSP system supplies the time information to the plugin together with the audio data. The time information therefore serves as a time stamp of the data samples of the audio data input to the plugin for allowing the plugin itself to know detailed time information such as what sample in the absolute time domain the input data to be subjected to signal processing corresponds to. All plugins present inside the SSP system are synchronized with one another while referring to the absolute time and the entire circuit in the SSP system can realize synchronous signal processing with the sample accuracy.

The plugin includes the signal processor . Audio data input from another plugin is transmitted to the signal processor via the input port . The signal processor performs signal processing unique to the plugin on the audio data obtained from the input port while referring to the time information or the parameter value sent to the signal processor . The audio data processed by the signal processor is transmitted to another plugin via the output port .

In synchronization with the time information the processing in the plugin can be performed not only on a sample by sample basis but also on a unit by unit basis wherein each unit consists of a plurality of samples e.g. on a packet by packet basis. In plugins signal processing functions are called on a unit by unit basis. Thus in a case of performing signal processing on a packet by packet basis signal processing functions are called one time per packet and the number of function calls is reduced while increasing the signal processing speed.

As discussed above the graph also includes the properties of a plugin and includes a signal processor an input port an output port a parameter buffer and a time information register . The signal processor reads a plugin included in the graph . The functions of the input port the output port the parameter buffer and the time information register are similar to those of the corresponding components in the plugin described above with reference to and a description thereof is thus omitted. It is to be understood that the parameters stored in the parameter buffer are parameters with respect to the graph .

The graph includes an internal plugin generating and holding unit . The graph can include zero or more plugins. The user instructs the graph to add or delete a plugin thus dynamically generating or deleting a plugin even during signal processing. The dynamic generation or deletion of a plugin during signal processing is described in detail below.

In the graph the generated plugins are assigned identification numbers 0 to J where J is any natural number according to the order in which the plugins are added. The user identifies the plugins using the identification numbers. The plugins are not necessarily stored in the order of the identification numbers in the plugin generating and holding unit of the graph . In graph the plugins are sorted in the order of the successive calculations described below and are stored in the plugin generating and holding unit .

The user can also instruct the graph to connect the plugins included in the graph . The connection between an output port of a given plugin and an input port of another given plugin can dynamically be changed even during signal processing. The dynamic change can be performed by the user specifying to the graph the identification numbers of the plugins and the identification numbers of the ports. In response to an instruction from the user to change the connection the graph changes the connection state of the plugins.

The user instructs the graph to initiate signal processing. When the user calls a signal processing function of the graph signal processing functions of the plugins included in the graph are sequentially called recursively from within the signal processing function of the graph . When the signal processing function is called the signal processors of the graph and plugins included in the graph are sequentially executed according to the order of successive calculations. The graph and plugins are sorted in the order of the successive calculations and are stored in the plugin generating and holding unit .

Calculations are successively performed in the graph and plugins included in the graph whereby the overall circuit set up in the graph achieves multiple signal processing operations. The order of the successive calculations is determined by the system i.e. the graph depending on the connection between the plugins.

In a case of modifying the circuit design according to a user instruction such as adding or deleting a plugin or changing the connection between an input port and an output port the graph performs path routing discussed below to automatically determine the optimum order of successive calculations for the plugins and child graph included in the graph . The optimum order of successive calculations for the plugins included in the child graph is automatically determined by the child graph performing path routing.

As a result of the path routing performed by the graph the plugin group including the child graph as a plugin is stored in the plugin generating and holding unit in the manner that the plugins are sorted in the optimum order of successive calculations. A path routing algorithm of the graph is described in detail below.

The instruction input receiving function unit receives a user instruction to generate or delete a plugin to connect an input port of a plugin and an output port of another plugin to input a parameter and so on. The instruction input receiving function unit transfers the plugin generation or deletion instruction to the plugin generating and deleting function unit and the input and output port connection instruction to the plugin interconnection processing function unit . In response to the plugin generation or deletion instruction or the input and output port connection instruction the instruction input receiving function unit activates the path routing function unit to perform path routing. The instruction input receiving function unit is also adapted to hold an input parameter in a parameter buffer in response to the parameter input instruction.

The plugin generating and deleting function unit generates or deletes a plugin in response to the plugin generation or deletion instruction from the instruction input receiving function unit . When a plugin is generated the generated plugin is assigned an identification number and information of the generated plugin including the identification number is transferred to the circuit structure information storing and managing function unit . When a plugin is deleted deletion information including the identification number of the deleted plugin and the deletion request is transferred to the circuit structure information storing and managing function unit .

In response to the plugin interconnection instruction from the instruction input receiving function unit the plugin interconnection processing function unit transfers the connection information between the output port and the input port of the plugins specified by the connection instruction to the circuit structure information storing and managing function unit .

The circuit structure information storing and managing function unit stores and manages information relating to the circuit set up in the graph from the plugin generation information deletion information or connection information from the plugin generating and deleting function unit or the plugin interconnection processing function unit .

The path routing function unit activates and executes a path routing algorithm described below in response to the plugin generation or deletion instruction or an activation instruction based on the input and output port connecting instruction from the instruction input receiving function unit . As a result of the path routing algorithm the path routing function unit determines the order in which the plugins sequentially perform calculations hereinafter referred to as signal processing order and sends information relating to the signal processing order to the signal processing order managing function unit . The signal processing order managing function unit arranges the identification information on the plugins in the signal processing order and holds the plugins in the plugin generating and holding unit shown in .

As shown in the signal processing executing function unit includes a data transfer processor a signal processing function caller a signal processing time manager and a signal processing synchronization manager .

The signal processing executing function unit initiates signal processing using the circuit set up in the graph in response to a signal processing initiation instruction input via the instruction input receiving function unit . When the user instructs that a signal processing function of the graph be called the signal processing function caller reads the instructed signal processing function of the graph from the signal processing function storage unit . While the signal processing function caller reads the signal processing function of the graph in response to a user instruction signal processing functions of the plugins in the graph are sequentially called recursively from within the signal processing function of the graph.

The data transfer processor of the signal processing executing function unit refers to the circuit information stored in the circuit structure information storing and managing function unit and sequentially transfers audio data to the plugins according to the circuit structure.

The signal processing time manager manages time in units of data samples transferred from the data transfer processor . The signal processing synchronization manager manages packet synchronization e.g. a packet header during signal processing on a packet by packet basis or AV synchronization for allowing the processing timing of audio data to be synchronized with frames of video data.

Even during signal processing by the signal processing executing function unit the path routing function unit performs path routing on the circuit structure that is changed in response to a request to change the circuit structure in the graph from the instruction input receiving unit and transmits the routed path to the circuit structure information storing and managing function unit and the signal processing order managing function . The signal processing executing function unit then performs signal processing on the changed circuit structure according to the signal processing order determined based on the routed path obtained from the changed circuit structure.

As discussed above it is necessary to create a signal processing circuit in the graph so as to satisfy the general principle of digital signal processing namely the requirement of at least one or more delay elements being included in a feedback loop in a signal processing flow graph.

However a user who does not have the knowledge of the requirement of a delay element being included in a feedback loop can create a circuit not satisfying this requirement in the graph. When such a circuit including no delay element in a feedback loop is set up in the graph in an initial path routing algorithm discussed below the path routing function unit detects the circuit as an error. The path routing function unit when detecting such an error notifies the error warning function unit of the detected error.

When it is determined that a circuit including no delay element in a feedback loop is set up in the graph in response to the notification of the detected error from the path routing function unit the error warning function unit warns the user with an audio and or visual error message such as closed loop without delay cannot be created .

In response to the warning the user checks the feedback loop of the circuit created by the user and modifies the circuit so that an additional delay element is inserted at an appropriate position.

A process for creating a signal processing circuit according to the first embodiment will now be described in the context of a case where a circuit with a structure shown in is created in the graph. In the following description graphs and plugins are referred to as objects . In object oriented terminology an object is an instance which is an entity of a graph or a plugin.

In generating objects the number of input and output ports of each of the graphs and plugins is set as default initial values as below. The user may add or delete an input port and or an output port after generating the objects.

In the following description the numbers following the input ports and the output ports represent port numbers using 0 1 and 2.

A procedure for creating the circuit shown in will now be described with reference to a flowchart shown in . In for ease of understanding user instructions are illustrated in association with the operation of the signal processing apparatus according to the embodiment. Although not shown the signal processing apparatus according to the embodiment displays a view in accordance with an instruction input by the user on a display screen thus allowing the user to perform an input operation while viewing the display screen.

First the user instructs the signal processing apparatus to create an object of the graph parent graph user instruction 1 . Then the signal processing apparatus generates the parent graph as a root object and registers it step S .

The user instructs the object of the graph to create an object of the plugin user instruction 2 . Then in the signal processing apparatus the plugin generating and deleting function of the created graph is exercised to generate the plugin inside the graph and to register it step S . In response to the plugin generation instruction the path routing function unit in the graph performs path routing step S .

The user instructs the object of the graph to create an object of the plugin user instruction 3 . Then in the signal processing apparatus the plugin generating and deleting function of the graph is exercised to generate the plugin inside the graph and to register it step S . In response to the plugin generation instruction the path routing function unit in the graph performs path routing step S .

The user instructs the object of the graph to create an object of the graph child graph user instruction 4 . Then the graph exercises the plugin generating and deleting function to generate the child graph inside the graph as a plugin and to register it step S . In response to the plugin generation instruction the path routing function unit in the graph executes path routing step S .

The user instructs the object of the graph to create input port external user instruction 5 . Then in the signal processing apparatus as a function of the generated child graph the input port external is generated and registered in the child graph step S . In the child graph internal output port internal corresponding to the input port external is automatically generated step S . In response to the port creation instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the child graph to create output port external user instruction 6 . Then in the signal processing apparatus as a function of the generated child graph output port external is generated and registered in the child graph step S . In the child graph internal input port internal corresponding to the output port external is automatically generated step S . In response to the port creation instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the child graph to create an object of the plugin user instruction 7 . Then the plugin generating and deleting function of the child graph is exercised to generate the plugin inside the child graph and to register it step S . In response to the plugin generation instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the child graph to create an object of the plugin user instruction 8 . Then the plugin generating and deleting function of the child graph is exercised to generate the plugin inside the child graph and to register it step S . In response to the plugin generation instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the child graph to create an object of the plugin user instruction 9 . Then the plugin generating and deleting function of the child graph is exercised to generate the plugin inside the child graph and to register it step S . In response to the plugin generation instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the graph to connect output port of the plugin and the input port external of the child graph user instruction 10 . Then the graph exercises the plugin interconnection processing function unit to connect the output port of the plugin and the input port external of the child graph and to register the connection in the graph step S . In response to the port connection instruction the path routing function unit in the graph performs path routing step S .

The user instructs the object of the graph to connect the output port external of the child graph and input port of the plugin user instruction 11 . Then the graph exercises the plugin interconnection processing function unit to connect the output port external of the child graph and the input port of the plugin and to register the connection in the graph step S . In response to the port connection instruction the path routing function unit in the graph performs path routing step S .

The user instructs the object of the child graph to connect the internal output port internal of the child graph and input port of the plugin user instruction 12 . Then the child graph exercises the plugin interconnection processing function unit to connect the internal output port internal of the child graph and the input port of the plugin and to register the connection in the child graph step S . In response to the port connection instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the child graph to connect output port of the plugin and input port of the plugin user instruction 13 . Then the child graph exercises the plugin interconnection processing function unit to connect the output port of the plugin and the input port of the plugin and to register the connection in the child graph step S . In response to the port connection instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the child graph to connect output port of the plugin and input port of the plugin user instruction 14 . Then the child graph exercises the plugin interconnection processing function unit to connect the output port of the plugin and the input port of the plugin and to register the connection in the child graph step S . In response to the port connection instruction the path routing function unit in the child graph performs path routing step S .

The user instructs the object of the child graph to connect output port of the plugin and input port of the plugin user instruction 15 . Then the child graph exercises the plugin interconnection processing function unit to connect the output port of the plugin and the input port of the plugin and to register the connection in the child graph step S . In response to the port connection instruction the path routing function unit in the child graph performs path routing step S .

When the plugin is a plugin including no delay as discussed above an error is detected and the detected error is notified as a result of the path routing by the path routing function unit and the error warning function unit warns the user with an error message. In response to the warning the user inserts a delay element in front of or behind the plugin in the feedback loop to resolve the error.

When the plugin is a plugin including a delay on the other hand it is to be anticipated that no error is notified or no error warning is issued.

Finally the user instructs the object of the child graph to connect output port of the plugin and the internal input port internal of the child graph user instruction 16 . Then the child graph exercises the plugin interconnection processing function unit to connect the output port of the plugin and the internal input port internal of the child graph and to register the connection in the child graph step S . In response to the port connection instruction the path routing function unit in the child graph performs path routing step S .

The circuit shown in is thus set up in the graph according to the above described procedure. When the user instructs the graph to initiate signal processing as discussed above the plugins sequentially perform the signal processing according to the signal processing order determined by path routing.

As discussed above in the signal processing apparatus according to the embodiment since the total of 16 user steps in the procedure described above are performed on the graph objects the graph structure of the circuit is changed each time the steps are performed. Therefore the path routing algorithm is automatically performed by the system graph for each step. When the process for creating a circuit ends the path routing also ends and the signal processing order is determined.

The plugin generating and holding unit in the graph holds plugins that are sorted in the optimum successive calculation order determined by the path routing algorithm. While assuming that plugins are stored in the graph shown in in the optimum order the flow of performing signal processing will now be described.

 3 Then the signal processing function of the plugin is executed from within the signal processing function of the graph .

 4 Then the signal processing function of the child graph is executed from within the signal processing function of the graph .

 4 1 Then the signal processing function of the plugin is executed from within the signal processing function of the child graph .

 4 2 Then the signal processing function of the plugin is executed from within the signal processing function of the child graph .

 4 3 Then the signal processing function of the plugin is executed from within the signal processing function of the child graph .

 5 Then the signal processing function of the plugin is executed from within the signal processing function of the graph .

In the flow of the process described above only the processing of step for instructing the graph to initiate signal processing is performed in response to a user instruction and the processing of steps to is automatically performed by the graph and the child graph .

The path routing algorithm that is executed by the processing function of the graph according to this embodiment will now be described.

The following path routing algorithm builds the main part of the system according to the embodiment. The path routing algorithm allows the plugins included in the graph to be sorted in the optimum order. During signal processing the unique signal processing functions of the plugins are called and executed in the order in which the plugins are sorted.

In general when signal processing is performed using a signal processing device such as a digital signal processor DSP an arithmetic circuit unit in the DSP such as an arithmetic logical unit ALU successively performs calculations to achieve the desired signal processing. This successive processing approach with the use of the DSP or the like is also applied to the arithmetic operation performed by a central processing unit CPU of the middleware according to this embodiment.

In this embodiment a given circuit is regarded as a signal flow graph the order of successive calculations is determined from the graph and calculations are successively performed in the determined order. The SSP which is an implementation of the middleware according to this embodiment is also characterized by having a unique path routing algorithm.

The path routing algorithm allows any digital circuit including a feedback loop to be completely emulated. The path routing algorithm also allows the circuit structure to be dynamically changed which is difficult in real world hardware circuit environments.

The path routing algorithm according to this embodiment is an algorithm for determining the successive calculation order from which plugin to start signal processing in order to carry out the signal processing on a circuit composed of plugins joined to define a graph. The circuit to be subjected to path routing which is set up in the graph may include a feedback loop circuit.

This path routing algorithm is contained in the graph and the plugin generating and holding unit in the graph executes the path routing algorithm.

When the user instructs the graph to change the graph structure the graph itself automatically performs path routing and determines the new successive calculation order. When a plurality of graphs are present inside a circuit paths for the individual graphs are routed independently and the path routing is performed only on the changed graph. This path routing is very simple and is completed in a short time.

The details of the path routing algorithm according to this embodiment will be described hereinbelow.

In the path routing algorithm according to this embodiment plugins which are circuit elements constituting a graph are regarded as nodes. A node is an element constituting a node in graph theory. In this embodiment a circuit can be represented by a directed edge graph including nodes joined by directional arrowed links. An arrow directed to a node is defined as an input to the node and an arrow directed to the outside from a node is defined as an output from the node. In the path routing algorithm according to this embodiment the nodes joined to define a graph are traced forward to determine the signal order. The path routing algorithm according to this embodiment is hereinafter referred to as a node scan algorithm .

The node scan algorithm is made up of an initial path routing algorithm primary node scan algorithm as a basic path routing algorithm and a loop search algorithm for routing a path further according to loop information.

In this embodiment as shown in in the node scan algorithm first an initial path routing algorithm is executed step S . Then it is determined whether or not the initial path routing algorithm has ended step S . If it is determined that the initial path routing algorithm has normally ended a loop search algorithm is executed step S . Then the path routing algorithm ends.

If it is determined in step S that the initial path routing algorithm has not ended as discussed above and discussed in detail below it is determined whether or not the initial path routing algorithm has been interrupted and terminated due to an error caused by inserting a plugin including no delay in the feedback loop step S .

If it is determined in step S that the initial path routing algorithm has not been terminated the flow returns to step S and the initial path routing algorithm continues. If it is determined in step S that the initial path routing algorithm has been terminated the path routing algorithm ends.

The initial path routing algorithm is executed under the search conditions described below after setting the following propositional problem to be solved 

Assume that the nodes joined to define a graph are traced forward. Pass through all nodes at one time in one cycle under the conditions below. Determine the cyclic order that satisfies this requirement where the nodes to be traced are not necessarily directly joined by graph edges and the nodes may be skipped and traced.

 d An input of a node A is defined once an output of a preceding node B connected to the input of the node A is defined.

The nodes are assigned in advance unique numbers as identifiers in order. These numbers are hereinafter referred to as node numbers node Nos. . The node numbers may be arbitrary numbers and for example node numbers may be assigned in the order in which the objects of the plugins are generated. There are two types of plugins i.e. latency type plugins LTPs and non latency type plugins NLTPs . LTPs are plugins constituting delay elements that cause a delay of one or more samples. NLTPs are plugins constituting gate elements that do not cause a delay.

The initial path routing algorithm is repeatedly performed in the second cycle the third cycle and so on to check the nodes until the solution of the propositional problem is found. In a cycle of routing a path at least one node through which the path can pass hereinafter referred to as a passable node is found.

However there is an exception. That is in a cycle of routing a path no passable node is found if an LTP constituting a delay element is not included in a feedback loop. This is abnormal in the circuit structure.

In the general principle of digital signal processing it is necessary to include at least one or more delay elements in a feedback loop to satisfy the causality constraint. The initial path routing algorithm according to this embodiment is characterized in that the exception occurs when a user creates a circuit that does not satisfy this basic principle.

In the initial path routing algorithm according to this embodiment the occurrence of the exception is used to warn the user of an error. When a user creates a feedback circuit including no delay element the above described exception of routing occurs in the initial path routing algorithm. When this exception is detected the system warns the user so that he she can reconfigure a circuit.

The initial path routing algorithm described above can be executed according to a flowchart shown in .

First the first node is checked step S and it is determined whether or not the current node has been assigned a node sequence number hereinafter referred to as a node index step S . If the node index has been assigned it is determined whether or not all nodes have been assigned node indexes step S . If it is determined that all nodes have been assigned node indexes this processing routine ends.

If it is determined in step S that all nodes have not been assigned node indexes the next node is checked step S . Then the flow returns to step S and the processing after step S is repeatedly performed.

If it is determined in step S that the current node has not been assigned a node index it is determined whether or not the current node is a node through which the path can unconditionally pass i.e. whether or not the current node is an LTP step S .

If it is determined in step S that the current node is not a node through which the path can unconditionally pass it is determined whether or not all inputs of the current node are defined step S . If it is determined in step S that all inputs are not defined it is determined whether or not a cycle of path routing is completed step S .

If it is determined in step S that a cycle of path routing is not completed the next node is checked step S . Then the flow returns to step S and the processing after step S is repeatedly performed.

If it is determined in step S that a cycle of path routing is completed it is determined whether or not a passable node is found step S . If it is determined in step S that there is found any passable node it is determined whether or not all nodes have been assigned node indexes step S . If it is determined that there is any node that has not been assigned a node index the next node is checked step S . Then the flow returns to step S and the processing after step S is repeatedly performed. If it is determined in step S that all nodes have been assigned node indexes this processing routine ends.

If it is determined in step S that there is found no passable node an error due to no delay element included in the feedback loop is detected and an error notification is generated and issued step S . Then the path routing using the initial path routing algorithm is terminated step S and this processing routine ends.

If it is determined in step S that the current node is a node through which the path can unconditionally pass or if it is determined in step S that all inputs of the current node are defined the path passes through the current node and the output of the current node is defined step S . Then the input of the node to which the current node is connected is defined step S . The current node is then assigned a node index step S .

It is determined whether or not all nodes have been assigned node indexes step S . If it is determined that there is any node that has not been assigned a node index the next node is checked step S . Then the flow returns to step S and the processing after step S is repeatedly performed. If it is determined in step S that all nodes have been assigned node indexes this processing routine ends.

In this way an error due to no delay element included in the feedback loop is detected and an error notification is sent to the error warning function unit as described above. In response to the error notification the error warning function unit warns the user with the error message described above.

For example as shown in if a plugin constituting a non delay element NLTP is accidentally connected as the plugin as indicated by broken lines to create a feedback loop a warning message shown in is displayed on the screen.

In response to the warning message the user modifies the feedback loop so as to insert a delay element in the feedback loop or replace one of the NLTPs in the feedback loop with an LTP. In the next step of executing the path routing algorithm the error message does not appear.

A specific example assignment of node indexes based on the initial path routing algorithm will be described with reference to a circuit structure of a flag shown in . In seven nodes i.e. nodes No. to No. are target nodes. The nodes No. and No. are LTPs. In the initial path routing algorithm the nodes No. to No. are checked in turn as below. This check is repeatedly performed in multiple cycles of the nodes No. to No. until all nodes become passable nodes.

 1 The node No. has no input and is therefore a passable node. The output of the node No. is thus defined.

 3 The node No. has no input and is therefore a passable node. The output of the node No. is thus defined.

 5 The node No. is an LTP and is therefore a passable node. The output of the node No. is thus defined.

 7 The node No. is an LTP and is therefore a passable node. The output of the node No. is thus defined.

The first cycle of path routing is completed. Then the second cycle of path routing is performed as below on the nodes through which the path does not pass and of which outputs are undefined.

 1 The node No. becomes a passable node because all inputs and are defined. The output of the node No. is thus defined.

 2 The node No. becomes a passable node because all inputs and are defined. The outputs and of the node No. are thus defined.

Since the path passes through all nodes and the output is defined the path routing operation is completed. In this case routing is completed in the second cycle.

In the routing steps of the initial path routing algorithm the nodes are numbered in the order in which the outputs are defined and a routing result is determined. These new sequence numbers of the nodes are node indexes. shows a routing result for the example circuit structure of the graph shown in .

In the graph the plugins are stored in the order of the node indexes in the plugin creating and holding unit. Each time the path routing algorithm is executed the order of the plugins stored in the plugin creating and holding unit is updated. During signal processing the graph calls the signal processing functions of the plugins in the order of the node indexes thereby achieving the desired signal processing.

In the foregoing description an error notification is issued in the initial path routing algorithm. However an error notification may not be issued in the initial path routing algorithm and may be issued as a portion of the path routing algorithm shown in when the termination of the initial path routing algorithm is detected in the path routing algorithm shown in the flowchart of .

Next the loop search algorithm will be described. The loop search algorithm provides an improvement of a load on the CPU during signal processing. This technique is important to maintain high real time signal processing.

A desired signal processing circuit is achievable by using a routing result determined in the initial path routing algorithm. However the routing result determined in the initial path routing algorithm is not necessarily advantageous for a circuit structure including a feedback loop in view of the speed and performance.

A circuit structure including a feedback loop needs to satisfy the causality constraint in the principle of digital signal processing that outputs cannot be defined unless inputs are defined. In a circuit including a feedback loop therefore it is necessary to successively perform signal processing on the plugins on a sample by sample basis. That is it is necessary to input and output audio data with respect to the plugins and perform signal processing on the audio data on a sample by sample basis.

A problem is the number of function calls needed each time the signal processing is performed. In general in software processing function calling leads to increases the load on the CPU and is thus costly . In software based real time signal processing the fewer the function calls the higher the processing speed and performance. A method for reducing the number of function calls is needed to increase the processing speed and performance.

A typical method for reducing the number of function calls is to perform processing on a unit by unit basis wherein each unit consists of a plurality of data samples e.g. on a packet by packet basis. Instead of processing on a sample by sample basis a block consisting of a predetermined number of data samples is processed in a batch. For example when the packet size is 1 024 samples a block of 1 024 samples of audio data is processed by a single function call. By doing so the number of function calls can be reduced.

However if a circuit includes a feedback loop as discussed above function calling is needed on a sample by sample basis. In this case packet based processing is not carried out.

In the path routing algorithm according to this embodiment this problem is overcome by performing the loop search algorithm described below after performing the initial path routing algorithm.

In a circuit including a feedback loop nodes forming the loop are generally parts of the circuit. The loop search algorithm according to this embodiment uses this fact to separate a group of nodes forming the loop hereinafter referred to as loop nodes and a group of nodes not forming the loop hereinafter referred to as non loop nodes with respect to the signal processing order and enables packet based processing on the group of non loop nodes thereby entirely increasing the signal processing speed.

For example in the circuit structure shown in three nodes i.e. the nodes No. No. and No. form a loop and are less than half of the total of seven nodes.

Only the loop nodes are processed on a sample by sample basis while the remaining nodes are processed on a packet by packet basis to thereby prevent the deterioration in speed. In the overall circuit structure the smaller the ratio of the loop nodes the more efficiently the deterioration in speed can be prevented.

It is determined whether or not a non loop node is located between loop nodes in the signal processing order determined in the initial path routing algorithm step S .

If it is determined that a non loop node is located between loop nodes in the signal processing order step S the signal processing order is rearranged so that the non loop node is placed before the loop nodes step S . That is the node indexes are renumbered.

If it is determined in step S that no non loop node is located between loop nodes in the signal processing order this loop search algorithm ends.

The loop search algorithm will be described hereinafter in detail in the context of the application to the circuit structure shown in .

A result of the initial path routing algorithm executed for the circuit structure shown in is shown in . A table viewed in the left portion of shows that the loop nodes determined by the closed path routing algorithm i.e. the nodes No. No. and No. are shaded in the routing result shown in .

As is apparent from the table viewed in the left portion of the node No. which is a non loop node is located between loop nodes in the signal processing order in the routing result of the initial path routing algorithm. In this case the node No. in the signal processing order is also to be processed on a sample by sample basis although the processing on a sample by sample basis is not needed.

When applying the loop search algorithm in step S the signal processing order is changed so that the non loop node is placed before the loop nodes.

When the signal processing order is changed it is still necessary to satisfy the propositional problem to be solved in the initial path routing algorithm. In the loop search algorithm it may be determined whether or not the propositional problem to be solved in the initial path routing algorithm is satisfied for the changed signal processing order when the signal processing order is changed. In this example however the signal processing order is changed so that the non loop node is placed before the first loop node and the above described determination is not needed. This changing approach is advantageous in that the sequence of the signal processing is correctly maintained.

In the context of the example shown in since the nodes No. and No. are LTPs inherently the outputs are defined if the inputs are undefined. With this inherent feature the nodes No. and No. may be processed after the node No. .

In this example the loop search algorithm allows as viewed in the right portion of the signal processing order to be changed so that the node No. which is a non loop node is moved to the third position in the signal processing order before the node No. which is the first loop node.

As indicated by shading in the right portion of the loop nodes are grouped. That is the group of loop nodes is localized in the signal processing order.

Signal processing is performed in the signal processing order viewed in the right portion of according to the following procedure to minimize the number of function calls 

 1 The nodes with node indexes to are outside the loop and are therefore processed on a packet by packet basis.

 2 The nodes with node indexes to reside in the loop and are therefore processed on a sample by sample basis.

 3 The node with node index is outside the loop and is therefore processed on a packet by packet basis.

By performing signal processing in this way the number of function calls is reduced to prevent the deterioration in signal processing speed. Next the number of function calls in a case where the packet size is 1 024 samples will be described.

In the signal processing steps 1 to 5 described above a total of 3 076 function calls are needed to perform signal processing on 1 024 samples.

In this example if all nodes are processed on a sample by sample basis a total of 7 168 function calls are needed. The node scan algorithm according to the embodiment is executed to localize a group of loop nodes and function calling per sample is performed for the group of loop nodes while performing function calling one time for the remaining non loop nodes on a packet by packet basis. Thus the number of function calls can be reduced by about 57 .

The system according to this embodiment may not fix the packet size but may dynamically change the packet size.

As discussed above the signal processing apparatus according to this embodiment can dynamically change the graph structure even during signal processing in response to a graph change instruction from a user. Even during signal processing the path routing algorithm node scan algorithm according to this embodiment is re executed to support the change of the circuit structure.

This arrangement allows a user to change the signal processing apparatus according to this embodiment to a new circuit structure while for example listening to the sound processed and output from the signal processing apparatus according to this embodiment. Thus advantageously the signal processing apparatus according to this embodiment can be applied to equipment for live performance applications.

First signal processing is performed at time t step S . Then it is determined whether or not a graph change request such as an instruction to generate or delete a plugin or an instruction to generate or connect an input port and an output port has been received during the signal processing step S .

If it is determined in step S that a graph change request has been received the graph re executes path routing and reconfigures the circuit structure of the graph step S . Then signal processing at next time t 1 is performed step S . If it is determined in step S that no graph change request has been received then signal processing at next time t 1 is performed step S .

After step S processing similar to the processing of steps S to S is repeatedly performed e.g. steps S to S .

In this dynamic changing process the path routing algorithm using the flowcharts shown in is also executed in the path routing processing in steps S S and so forth. Like the example described above if a feedback loop including no delay is accidentally added an error warning is given to the user.

In response to the error warning the user can easily create a correct circuit by inserting a delay element in the feedback loop or changing a plugin from an NLTP to an LTP.

The above described signal processing apparatus according to the embodiment is normally implemented by a single computer and signal processing is performed on the single computer. This processing is extensively performed on a plurality of computers connected via a network thereby distributing the CPU load in real time.

This distribution processing is achievable by utilizing a distributed object technology which is a general computing technology such as COM DCOM Component Object Model Distributed Component Object Model or CORBA Common Object Request Broker Architecture .

A distribution processing will be described hereinbelow in the context of the COM DCOM technology which is mainly used in Windows OSs. First all plugin objects in the middleware of this embodiment are implemented as COM objects. A COM object is an object oriented component model and is characterized by location transparency. The location transparency is a feature that allows a COM object to be generated on a remove computer as if the COM object were generated on for example a local computer.

With the location transparency objects are generated on either a local computer or a remote computer by performing the same operation. That is plugin objects which are COM objects are uniformly generated on a plurality of computers without paying attention to networks. Operations other than the generation of plugins are also achievable with uniform operability on either a local computer or a remote computer.

For example audio input and output plugin objects may be placed on a local computer and echo plugin objects may be placed on a remote computer. As a whole a single circuit can be set up.

The flow of creating a circuit will now be described with reference to . A user creates a circuit in a similar manner to that for creating a circuit using only the local computer . The user draws attention to the remote computer only in a portion of the processing.

 1 The user creates an object of the graph . The object of the graph is created on the local computer .

 4 The user instructs the object of the graph to create an object of a plugin . In this case the plugin generation functions are assigned an identifier of the remote computer .

 6 The user instructs the object of the graph to connect output port of the plugin and input port of the plugin .

 7 The user instructs the object of the graph to connect output port of the plugin to input port of the plugin .

 8 The user instructs the object of the graph to connect output port of the plugin and input port of the plugin .

 9 The user instructs the object of the graph to connect output port of the plugin and input port of the plugin .

Thus the circuit is completed. The user draws attention to the remote computer only in the step 4 . Further the user can perform the signal processing in a similar manner to that with the use of only the local computer .

A signal processing apparatus according to a second embodiment of the present invention is basically similar in structure to that according to the first embodiment. The difference is that when a feedback loop including no delay is generated in the first embodiment an error warning is issued to the user whereas in the second embodiment a necessary delay element is automatically inserted in the feedback loop without issuing an error warning or after issuing an error warning.

In the second embodiment it may be preset whether or not an additional delay element is automatically inserted and if an additional delay element is automatically inserted the amount of delay of the additional delay element and the additional insertion position of the delay element may be preset.

As shown in the path routing function unit in the second embodiment includes an automatic delay element adding processor as functional means.

The preset function unit receives from the user a preset setting as to whether or not an additional delay element is automatically inserted a preset amount of delay of an additional delay element to be automatically inserted and a preset additional insertion position of the delay element and holds these preset settings.

When the path routing function unit detects a created feedback loop including no delay the automatic delay element adding processor of the path routing function unit adds the delay element having the amount of delay that is preset and stored in the preset function unit in the feedback loop at the additional insertion position that is preset and stored in the preset function unit .

First the preset function unit sends a query message to the user as to whether or not an additional delay element is automatically inserted when a feedback loop including no delay is generated step S . In response to the query message the user sets a preset as to whether or not an additional delay element is automatically inserted.

The preset function unit receives the preset input from the user step S and determines whether or not the preset specifies that an additional delay element is automatically inserted step S . If it is determined in step S that the preset does not specify that an additional delay element is automatically inserted the preset function unit ends this preset processing routine.

If it is determined in step S that the preset specifies that an additional delay element is automatically inserted a message prompting to set the amount of delay of the delay element to be inserted is sent step S . Then the flow waits for the user to set the amount of delay step S . If it is determined that the amount of delay is not set and the operation of terminating this presetting flow is performed step S this preset processing routine ends.

If it is determined in step S that the amount of delay is set the preset function unit holds the set amount of delay as the amount of delay of the delay element to be additionally inserted step S .

Then the preset function unit sends a message prompting to select an insertion position of the delay element to be additionally inserted step S . Two insertion position options e.g. positions in front of output side and behind input side a plugin NLTP in the feedback loop are presented to the user.

In response to the prompt the user selects either position in front of or behind the plugin in the feedback loop as an additional insertion position at which to insert the delay element. The preset function unit monitors the selection input of the user step S .

Then it is determined whether or not the operation of terminating this presetting flow is performed without receiving the selection input of the additional insertion position of the delay element step S . If it is determined that the operation of terminating the presetting flow is performed this preset processing routine ends. If it is determined that the operation of terminating the presetting flow is not performed the flow returns to step S and waits for the selection input of the additional insertion position of the delay element.

If the selection input of the additional insertion position of the delay element is received in step S the preset function unit holds the additional insertion position of the delay element set by the user step S . Then the preset processing routine ends.

First the path routing function unit executes an initial path routing algorithm step S . Then it is determined whether or not the initial path routing algorithm has ended step S . If it is determined that the initial path routing algorithm has normally ended a loop search algorithm is executed step S . Then the path routing algorithm ends.

If it is determined in step S that the initial path routing algorithm has not ended as discussed above it is determined whether or not an error caused by generating a feedback loop including no delay has occurred step S .

If it is determined in step S that a feedback loop including no delay is not generated the flow returns to step S and continues the initial path routing algorithm. If it is determined in step S that a feedback loop including no delay is generated it is determined whether or not it is preset that an additional delay element is automatically inserted step S .

If it is determined in step S that it is not preset that an additional delay element is automatically inserted the addition dynamic change of a plugin is cancelled and an error message is sent to the user step S . Then the path routing processing routine ends.

If it is determined in step S that it is preset that an additional delay element is automatically inserted the preset setting information stored in the preset function unit is referred to and it is determined whether or not the additional delay element to be automatically inserted is to be inserted in front of an added plugin NLTP including no delay step S .

If it is determined in step S that the insertion position is the front side position the delay element having the preset amount of delay is inserted in front of the plugin added by the user to generate a feedback loop step S . If it is determined in step S that the insertion position is not the front side position but the rear side position the delay element having the preset amount of delay is inserted behind the plugin added by the user to generate a feedback loop step S .

After the processing of step S or S the flow returns to step S and the initial path routing algorithm is re executed. Since the additional delay element is automatically inserted in the feedback loop the initial path routing algorithm normally ends.

The insertion of an additional delay element will now be specifically described. For example as shown in or in a circuit composed of four plugins to connected in cascade a user performs the dynamic changing process to connect an additional plugin between the plugins and to create a feedback loop.

In this case when the additional plugin inserted in the feedback loop is an NLTP plugin which is non delay element as discussed above if it is preset that an additional delay element is automatically inserted and the insertion position of the delay element is the front side position as shown in a plugin which is a delay element is inserted on the output side of the plugin . The amount of delay of the plugin which is a delay element is preset as discussed above.

If it is preset that the insertion position of the delay element is the rear side position as shown in a plugin which is a delay element is inserted on the input side of the plugin .

When a feedback loop is set up without connecting an additional plugin for example as shown in a plugin which is a delay element is also automatically inserted in the manner illustrated in .

According to the second embodiment when a user aims to rapidly change the circuit design during audio signal processing if the user accidentally create a feedback loop including no delay a delay element is automatically inserted thus achieving the initial aim of the user.

For example the signal processing tool according to the second embodiment is used for live performance applications a user sometimes desires to rapidly change the circuit design in synchronization with music while producing sound. In such a case if the user accidentally creates a feedback circuit including no delay element it is often difficult to change the circuit design at a desired timing leading to a problem with live performance. This problem is overcome by the second embodiment.

Particularly feedback loop circuits are frequently used for sound effectors sound filters and so forth. In live performances users are eager to create a closed loop circuit by performing a single additional operation. For example a user desires to change the circuit design on the first attempt in synchronization with music bar break. In such a case the user can rapidly change the circuit design in tune with the music according to the second embodiment.

While the second embodiment is applied to dynamic circuit change like the first embodiment the second embodiment may also be applied to a case where a circuit is initially created.

According to the above described embodiments in software digital signal processing it is possible to create a circuit without increased processing delay if signal processing circuits are connected in multiple stages. It is further possible to create any desired digital signal processing circuit including a feedback structure. It is still further possible to dynamically change the circuit structure of the digital signal processing circuit. Dynamically updatable circuit elements are 

parameters relating to signal processing such as the packet size and sampling frequencies in signal processing.

By implementing the middleware of the signal processing apparatus according to the foregoing embodiments in products the products whose circuit structure is dynamically changeable can be manufactured.

Further the thus created signal processing circuit is stored in a file thus allowing the signal processing circuit to be recovered later. This file is exchanged to facilitate replacement or reuse of the circuit.

If the signal processing circuit has a circuit structure including a feedback loop the number of calls of signal processing functions can be minimized resulting in low CPU load needed to perform real time signal processing.

A network allows real time distribution processing. A plurality of circuits on the network can synchronously be operated in real time.

While the foregoing embodiments have been described in the context of a case where a feedback loop including no delay is created when a plugin or a connection is added an embodiment of the present invention may also be applied to a case where an existing circuit is somewhat added deleted or modified and a feedback loop circuit including no delay element is finally created.

While the foregoing embodiments have been discussed in the context of audio signal processing signals other than audio signals may also be processed.

It should be understood by those skilled in the art that various modifications combinations sub combinations and alterations may occur depending on design requirements and other factors insofar as they are within the scope of the appended claims or the equivalents thereof.

