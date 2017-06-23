---

title: Ultrasonic imaging system having computer coupled to receive and process raw data
abstract: An ultrasound machine is configured for developing new modes for obtaining images or other useful information from ultrasound signals. The machine has a data processor configured to control a transmit circuit to generate ultrasound signals. Echo signals are received and digitized to yield RF data that is stored in a memory accessible to the data processor. A user can operate design mode application software to change the manner in which the RF data is processed to yield images or other useful information. New modes can be developed rapidly. The data processor may comprise a conventional personal computer equipped with suitable interfaces. An ultrasound machine may include and use a floating point processor for processing ultrasound signals.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08491479&OS=08491479&RS=08491479
owner: Ultrasonix Medical Corporation
number: 08491479
owner_city: Richond, BC
owner_country: CA
publication_date: 20061227
---
This application claims the benefit under 35 U.S.C. 119 of U.S. application Ser. No. 60 744 193 filed 3 Apr. 2006 which is hereby incorporated herein by reference.

This invention relates to ultrasonic imaging methods and apparatus. The invention may be applied to medical ultrasonic imaging.

Ultrasound imaging devices as used for example in medical ultrasound imaging comprise a transducer an electronic controller and a user interface. The transducer typically comprises an array of piezoelectric transducer elements. Different transducers have different arrangements of elements. The electronic controller drives the transducer and collects and processes data from the transducer to generate store display and manipulate images. The user interface may include various input output devices which allow a user to control the operation of the ultrasound system.

The nature and quality of ultrasound images depends upon both the signals that drive individual transducer elements and the way in which reflected signals detected by the transducer elements are processed. A typical ultrasound machine may be configured to permit a user to select one of a few predefined imaging modes.

There remains a need for tools that are useful in the development of new ultrasound imaging modalities. There is also a need for sophisticated and yet cost effective ultrasound machines.

The following embodiments and aspects thereof are described and illustrated in conjunction with systems tools and methods which are meant to be exemplary and illustrative not limiting in scope.

One aspect of this invention provides ultrasound machines that are configured in a manner that facilitates the development of new ultrasound imaging modalities. Another aspect of the invention provides ultrasound machines that take advantage of powerful processing capabilities of a general purpose computer to enable sophisticated modes of operation. Another aspect of the invention provides ultrasound machines that utilize a floating point processor of a general purpose computer to perform signal processing functions which may include digital filtering and or computing Doppler signals.

Further aspects of the invention and features of specific embodiments of the invention are described below.

Throughout the following description specific details are set forth in order to provide a more thorough understanding to persons skilled in the art. However well known elements may not have been shown or described in detail to avoid unnecessarily obscuring the disclosure. Accordingly the description and drawings are to be regarded in an illustrative rather than a restrictive sense.

The ultrasound signals propagate from the transducer and interact with the material of a body being examined. As a result ultrasound is reflected back toward transducer . The reflected ultrasound is received at elements and converted into electrical signals. The electrical signals are delivered to receive circuits .

Receive circuits condition the electrical signals for example the receive circuits may include suitable filters to remove various noise components from the signals and amplifiers to increase the amplitude of the signals. Receive circuits include analog to digital converters ADCs that convert the signals into digital values. The ADCs sample the signals at a rate sufficient to obtain both phase and amplitude information for each signal. The resulting digital data which may comprise raw samples of waveforms received at each element may be termed RF data .

RF data is delivered to a data processor which may comprise a suitably programmed computer workstation such as a personal computer by way of a suitable hardware software interface . The volume of RF data will depend upon factors such as the rate at which data is sampled the sampling resolution the number of elements in transducer and the like. In a typical case RF data is generated in 16 bit samples at a rate of 40 MHz and delivered to data processor in real time. RF data is delivered over a data bus capable of carrying the RF data in real time. Any suitable high speed bus technology may be used to implement the transfer of RF data to data processor . Once received in data processor RF data is stored in a RF data memory area by a direct memory access DMA controller . RF data memory area may be a portion of a main memory of data processor .

Data processor comprises one or more microprocessors . The microprocessors may be for example Intel Pentium or AMD Athlon microprocessors. Data processor also includes one or more floating point processors . Floating point processors are conveniently integrated with microprocessor s . For example the microprocessors referred to above have integral floating point processors.

Data processor controls the operation of transmit circuit by way of an interface . Data processor includes a parameter store that contains parameters that control the timing and or waveforms of the driving signals to be delivered to elements of transducer . The number and precise nature of the parameters in parameter store will depend on the structure of transmit circuit and upon how many different ways transmit circuit can be adjusted to vary the driving signals to be delivered to elements .

Data processor is also configured to process RF data from RF data memory area to yield images that can be displayed on a display . Display may be a high resolution computer monitor driven by data processor by way of a suitable graphics interface. The graphics interface may comprise for example a graphics card and compatible software drivers.

Data processor processes RF data received from transducer to yield computed information and or images. One example of computed information is a maximum blood flow velocity obtained by processing the RF data to yield information regarding the Doppler shift of reflected ultrasound signals.

Processor processes the RF data according to one or more data processing functions . Data processing parameters are provided for some or all of the data processing functions. The data processing parameters control the operation of the functions as described in more detail below.

Design mode application software can be executed by processor and permits users to control transmit parameters select data processing functions and select data processing parameters for the selected data processing function . A user can interact with design mode application software by way of a suitable user interface which may comprise a keyboard graphical user interface some combination thereof or any other suitable user interface.

Design mode application software permits users to efficiently develop new ultrasound imaging modalities. A user can first set transmit parameters to provide a desired set of driving signals for elements of transducer . The user may specify a sequence of driving signals to be applied to each element to yield a sequence of ultrasonic signals as desired for an ultrasound modality that the user is developing.

The driving signals applied to different ones of elements may differ in various ways to achieve transmitted ultrasound signals that have desired characteristics. There are a wide variety of ways in which it is possible to vary the driving signals. Different driving signals may be applied to different elements of transducer . For example 

A user designing a new ultrasound mode may select transmit parameters to generate a set of driving signals that cause transducer to emit ultrasound signals that appear to be appropriate for the selected mode. The user may also select an existing data processing function or design a new data processing function to extract desired information whether an image or some other information from the RF data that represents the ultrasound signals that are reflected from a body upon application of the driving signals to transducer . The data processing function may have many forms. Typical data processing functions involve operations such as beamforming summing and filtering to obtain preprocessed data that comprises echo amplitude information and or other information useful for some diagnostic purpose.

The user can readily test and modify the ultrasound mode until the user is satisfied with the results obtained. The user can then save information that specifies the mode of operation for future use.

At block the user causes system to emit ultrasound signals according to the selected transmit parameters and to acquire and store corresponding RF data . Method continues at block by applying the selected data processing function to RF data using the selected data processing parameters to obtain a result.

In block the result is displayed and checked. If the check indicates that the result is acceptable YES result at block then information specifying the mode is saved at block and method ends. If the check indicates that the result is not acceptable NO result at block then the user has the option of modifying the data processing function at block A or modifying the data processing parameters at block B or modifying transmit parameters at block C.

If the user elects to modify data processing function or data processing parameters then it is not necessary to acquire fresh RF data . The user can rapidly try the effect of different data processing functions and or different data processing parameters on the results obtained without acquiring new RF data . In the alternative apparatus may be configured to acquire new RF data each time block A or B is executed or a function may be provided to allow the user to cause apparatus to acquire fresh RF data as indicated for example by block D .

If the user elects to execute block C then method acquires fresh RF data using the transmit parameters as modified by the user in block C.

It can be appreciated that method provides a very efficient way to develop and fine tune new ultrasound operating modes. The operating modes may be any of 

Where data processor comprises a personal computer running a common operating system then developing new data processing functions is facilitated. The full range of computer programming tools that have been developed for programming such computers can be applied to write new data processing functions as desired. For example new data processing functions may be built developed and run using an environment such as Microsoft Visual Studio or Matlab . Data processor may execute software that provides an application programming interface API that permits user software such as software written in a language such as C to access RF data and or to control ultrasound machine . The data processing functions may perform customized signal processing carry out special echo acquisition sequences or the like.

It is not necessary for data processing functions to be entirely self contained. Data processor may contain software or software and hardware that provides certain standard processing of raw data . A data processing function may take advantage of such standard processing and further process the data as required for the ultrasound mode being developed.

As shown in data processor may comprise a beamforming module that processes RF data to yield pre scan converted data a module that produces post scan converted data comprising both a Doppler data stream and an echo data stream . Data processing functions may access any of these sets of data as required. Data processing parameters may affect the operation of these standard processing modules.

In some embodiments apparatus can be selectively operated either as a research platform as described above or as a diagnostic ultrasound machine. When apparatus is being operated as a diagnostic ultrasound machine only preconfigured standard operating modes are available for selection. The user can select an operational mode and may be able to adjust the operation of the selected mode by setting values for a limited predetermined set of parameters.

When apparatus is switched to operate as a research platform as described above apparatus preferably displays a noticeable warning that the apparatus is being operated in research mode so that users will not accidentally attempt to use the apparatus to perform a standard ultrasound test with possible unintended consequences. The warning may comprise a symbol or other indicia displayed on display and or a warning lamp or the like on user interface .

In some embodiments of the invention data processing functions for a preconfigured operational mode or for a mode under development include floating point computations that are performed by floating point processor s . Implementing filters using floating point arithmetic can yield a significant noise reduction and increased signal to noise ratio as compared to equivalent filters implemented using integer arithmetic. Implementing the processing for Doppler imaging using floating point arithmetic permits a large increase in dynamic range especially when digital filtering is performed using floating point arithmetic using the floating point processor . Using a fast floating point processor can provide dramatic and surprising improvements in the quality of ultrasound images and or other information derived from processing ultrasound signals. Where data processor is a computer workstation such as a personal computer the floating point processor s are included in the processor of data processor thus rendering expensive separate processors unnecessary.

While a number of exemplary aspects and embodiments have been discussed above those of skill in the art will recognize certain modifications permutations additions and sub combinations thereof. For example signals may be processed at receive circuit in a way which preserves phase and amplitude information of reflected signals. The inventions disclosed herein include all such modifications permutations additions and sub combinations as are within their true spirit and scope.

