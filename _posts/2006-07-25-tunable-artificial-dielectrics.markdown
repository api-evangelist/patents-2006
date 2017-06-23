---

title: Tunable artificial dielectrics
abstract: Tuning devices and methods are disclosed. One of the devices comprises a metal structure connected with artificial dielectric elements, and variable capacitance devices. Each variable capacitance device is connected with a respective artificial dielectric element and with a control signal. Control of the variation of the capacitance allows the desired tuning. Another device comprises metallic structures connected with artificial dielectric elements and switches connected between the artificial dielectric elements. Turning ON and OFF the switches allows the capacitance between artificial dielectric elements to be varied and a signal guided by the metallic structures to be tuned.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07852176&OS=07852176&RS=07852176
owner: The Regents of the University of California
number: 07852176
owner_city: Oakland
owner_country: US
publication_date: 20060725
---
The present application claims the benefit of provisional application 60 705 870 for On Chip Tunable Artificial Dielectrics Based VCO filed on Aug. 4 2005 provisional application 60 705 871 for On chip Tunable Artificial Dielectrics filed on Aug. 4 2005 and provisional application 60 794 012 for On Chip Tunable Artificial Dielectrics filed on Apr. 21 2006 all of which are incorporated herein by reference in their entirety.

The invention was made with Government support of Grant No. N66001 04 1 8934 awarded by the U.S. Navy. The Government has certain rights in this invention.

The present disclosure relates to tunable circuits devices and methods. In particular it relates to tunable artificial dielectrics.

Artificial dielectrics are known in the art and are made for example by distributing small polarizable particles in a uniform background material and represent a macroscopic analogue of a natural dielectrics. The polarizable particles can be either metallics particles or dielectric particles. Reference can be made for example to R. E. Collin Field Theory of Guided Waves 2Edition pp. 749 786 IEEE Press New Jersey 1990 or W. E. Kock Metallic Delay Lenses Bell System Tech. J. Vol. 27 pp. 58 82 1948. Those two papers are incorporated herein by reference in their entirety.

Known artificial dielectric materials are for example discrete or floating metal spheres disks strips or rods etc. When embedding these materials into an electromagnetic field the artificial particles of these materials are polarized by the applied field with the positive and negative charges displaced from each other. Each particle then acts as a dipole contributing to the total charge displacement and thus to an effective dielectric constant.

A device based on the artificial dielectrics concept is shown for example in W. Andress and D. Ham Standing Wave Oscillators Utilizing Wave Adaptive Tapered Transmission Lines Symposium on VLSI Circuits Digest of Technology Papers pp. 50 53 2004 where an artificial dielectrics based standing wave oscillator is disclosed.

Further wavelength or frequency tunability is important for radio frequency RF microwave and millimeter wave components and circuits. It can be used to tune the working frequencies of components such as transmission lines resonant tanks antennas delay lines filters inductors transformers baluns duplexers and circuits such as amplifiers mixers filters VCOs PLLs and any other circuits that employ wavelength or frequency or tuning filtering.

According to a first aspect a device is disclosed comprising a plurality of artificial dielectric elements a metal structure coupled with the plurality of artificial dielectric elements and a plurality of variable capacitance devices each variable capacitance device having a first end connected with a respective artificial dielectric element of the plurality of artificial dielectric elements and a second end wherein each second end is adapted to be connected to a control signal the control signal controlling variation of the capacitance of the variable capacitance devices.

According to a second aspect a voltage controlled oscillator is disclosed comprising a metallic structure to guide an input wave a plurality of artificial dielectric elements connected with the metallic structure the input wave polarizing metal particles in the artificial dielectric elements and variable capacitance devices each having a first end connected with a respective artificial dielectric element and a second end adapted to be connected with a control signal the second ends of the variable capacitance devices forming a control input of the voltage controlled oscillator to control the frequency of the input wave.

According to a third aspect a method for tuning a signal is disclosed comprising coupling a metal structure with a plurality of artificial dielectric elements the metal structure adapted to guide the signal to be tuned providing a plurality of variable capacitance devices each variable capacitance device having a first end connected with a respective artificial dielectric element of the plurality of artificial dielectric elements and a second end connecting each second end to at least one control signal and tuning the signal by varying the capacitance of the variable capacitance devices through the at least one control signal.

According to a fourth aspect a device is disclosed comprising a first and a second plurality of artificial dielectric elements a first metallic structure coupled with the first plurality of artificial dielectric elements a second metallic structure coupled with the second plurality of artificial dielectric elements and a plurality of switches each switch connected with a respective artificial dielectric element of the first plurality of artificial dielectric elements and a respective artificial dielectric element of the second plurality of artificial dielectric elements each switch further connectable with a control signal the control signal tuning the frequency of a signal guided by the first and second metallic structures.

According to a fifth aspect a device is disclosed comprising a plurality of artificial dielectric elements a metallic structure coupled with the plurality of artificial dielectric elements a plurality of switches each switch having a first terminal connected with a respective artificial dielectric element of the plurality of artificial dielectric elements a second terminal connected with ground and a third terminal connectable with a control signal the control signal tuning the frequency of a signal guided by the metallic structure.

According to a sixth aspect a switch controlled oscillator SCO comprising the device of the fourth or fifth aspect is disclosed.

According to a seventh aspect a resonator comprising a plurality of devices according to the fourth or fifth aspect connected in a closed loop arrangement is disclosed.

According to an eighth aspect a transmission line comprising a device according to the fourth or fifth aspect is disclosed.

According to a ninth aspect a switch controlled reconfigurable filter comprising the device of the fourth or fifth aspect is disclosed.

According to a tenth aspect a synthesizer is disclosed comprising a voltage control oscillator VCO a transmission line connected to the VCO the transmission line having a transmission line input and a transmission line output a mixer adapted to mix a signal on the transmission line input with a signal on the transmission line output the mixer having a mixer output and a low pass filter connected with the mixer output the low pass filter having a low pass filter output connected with the VCO wherein the transmission line is a transmission line comprising a device in accordance with the fourth or fifth aspect.

According to an eleventh aspect a delay locked loop DLL device is disclosed comprising a voltage control oscillator VCO a transmission line connected to the VCO the transmission line having a transmission line input and a transmission line output a mixer adapted to mix a signal on the transmission line input with a signal on the transmission line output the mixer having a mixer output a low pass filter connected with the mixer output the low pass filter having a low pass filter output a control logic block connected with the low pass filter output the control logic block having a control logic block output wherein the transmission line is a transmission line comprising a device in accordance with the fourth or fifth aspect.

The teachings of the present disclosure can be used to tune working frequencies of components such as transmission lines resonant tanks antennas delay lines filters inductors transformers baluns duplexers and circuits such as amplifiers mixers filters VCOs PLLs and or any other circuits that employ wavelength or frequency tuning or filtering.

High effective dielectric constants can be achieved which is highly desirable in integrated circuits because of the small size of passive components.

The teachings of the present disclosure are compatible with main stream IC processes that comprise multiple metal layers such as CMOS BiCMOS bipolar and SiGe technologies.

A large linear dynamic tuning range can be obtained due to the large dielectric constant tuning range.

Variation of the parasitic capacitances modifies the artificial dipole distribution or the permittivity capacitance ratio as seen by the electromagnetic wave of the applied field which in turn changes the wavelength of the applied field accordingly.

The applicants have noted that variation of capacitance between the elements forming the allows the frequency of an applied signal to be tuned. In particular the present disclosure discloses a way of changing the permittivity that characterizes the effect of dipoles in artificial dielectrics.

According to a first embodiment of the present disclosure in order to tune the dielectric constant variable capacitance devices such as varactors and diodes are used such that one end of each variable capacitance device is connected to one of the artificial particles and the other ends of all capacitance devices or all in a group are tied together and connected to control signals.

The enlarged section of shows an artificial particle e.g. a floating metal sheet and a variable capacitance device . The device can be for example a variable capacitance diode varactor . A first end of the variable capacitance device is connected to the particle . A second end of the variable capacitance device is connected to a control signal. As shown in the embodiment of the second ends of a first group of variable capacitance devices are connected to a first control signal Control Signal while the second ends of a second group of variable capacitance devices are connected to a second control signal Control Signal . The person skilled in the art will devise alternative embodiments where a single group connection to a single control signal or multiple groups of variable capacitance devices connections to multiple control signals are provided. The enlarged section of also shows parasitic parameters such as a parasitic capacitance and parasitic resistances . The value of the total variable capacitance connected to every artificial particle is determined by the capacitive equivalent of a combination between the variable capacitance and all parasitic parameters.

Variation of the control signals e.g. Control Signal and Control Signal in changes the capacitance connected to each of the artificial particles and thus has an effect on the permittivity of the artificial medium due to capacitance changes in the variable capacitance devices . As a result the wavelength of the wave speed of the electromagnetic wave guided by the metal structures becomes tunable.

Differential topologies are preferred for the metal structures to guide the electromagnetic wave due to the presence of a virtual ground which provides a well defined signal return path for the two branches of differential structures and thus confines the electromagnetic field within the artificial dielectrics.

Tunable artificial dielectric tanks like the ones shown in usually have an open circuited end and a short circuited end. Therefore the external active circuits which sense the standing wave signal in the tank and compensate the loss of the tank may have either open circuited or short circuited interfaces. Standing wave tanks have the highest voltage signal at the open circuited end and the largest current signal at the short circuited end. It is preferable not to draw too much energy from the tank when connecting circuits to the tank. In order to do that voltage coupling should be used between open circuited ends between tanks and circuits and current coupling should be used between short circuited ends between tanks and circuits.

The teachings of the present disclosure allow to accomplish frequency tuning effects which result in much less noise when compared to conventional tunable resonant tanks such as LC tanks.

The teachings of the present disclosure allow the signal i.e. the electromagnetic wave to be isolated from the substrates which are very noisy and lossy in silicon processes. Additionally there is no loss in the artificial dielectrics because no current flows in the artificial particles. In view of the above advantages a high Q factor is obtained as shown in . Such Q factor can be very high even in commercial CMOS processes at frequencies as high as 60 GHz.

According to a further embodiment of the present disclosure an embedded artificial dielectric can be realized in MOS or CMOS technology with adaptive permittivity controlled by MOS or CMOS switches to achieve frequency synthesis tuning hopping phase shift delay dynamic impedance matching and bandpass filtering over broad frequency ranges in real time.

In particular the applicants have noted that variation of the effective capacitance or permittivity of an embedded artificial dielectric by using shunt CMOS variable capacitors varactors can be limited by the frequency tuning range which is inversely proportional to the dielectric boost factor defined in Eq. 1 .

To overcome the difficulty in reaching broadband frequency tuning in modern software radios a further embodiment to control the permittivity of the embedded artificial dielectric provides for insertion of MOS switches.

In both embodiments when all MOS switches are turned on the artificial dielectric reaches its highest permittivity and achieves boost factor given by

On the other hand when each CMOS switch is turned off it disconnects the metal strip pair and forbids the charge exchange between them. Effectively this renders the C to zero if neglecting the parasitic capacitance. Therefore by turning selective MOS switches on and off with a programmable digital controller the permittivity or the equivalent boost factor of the artificial dielectric can be varied to a very large range from 1 to k and with very fine resolution k of

This results in a digital controlled effective permittivity which enables variable transmission wavelength with i th switch turned on and j th switch turned off as 

The applicants have called the techniques of the present disclosure Digital Controlled Artificial Dielectric as DiCAD. DiCAD has many potential applications in modern multi band software radio systems including 

The circuit of comprises a shorted circuit end and an open circuit end . As already explained with reference to a tank embodiment the shorted circuit end forms a standing wave resonator while the open circuit end is connected to an excitation network which provides gain or negative resistance R to compensate for resonator loss.

In addition similar tuning range and resolution can be achieved from a traveling wave transmission line resonator as indicated in . The active negative resistor R shown in compensates for transmission losses. Traveling wave transmission line resonators are known as such. See for example J. Wood T. C. Edwards and S. Lipa Rotary Traveling Wave Oscillator Arrays A New Clock Technology IEEE JSSC Vol. 36 No. 11 November 2001. shows an embodiment with four artificial dielectrics devices. Further embodiments can also be provided with a different number of devices e.g. 2 3 5 etc. so long as a closed loop is obtained.

Fixed frequency bandwidth bandpass or bandstop filters were implemented in the past by using dual lattice constant spacing frequency selective distributed Bragg reflector on PCB. See for example T. H. Wang and T. Itoh Compact Grating Structure for Application to Filters and Resonators in Monolithic Microwave Integrated Circuits IEEE Trans on MTT Vol. MTT 35 No. 12 December 1987. By using DiCAD transmission lines on CMOS lattice constants dand dcan be reconfigured by digitally controlling DiCAD switches on or off to vary the bandpass or bandstop filter characteristics as shown in . This re configurable filtering structure has compact size low insertion loss and ultra widely tunable bandwidth and center frequency.

With reference to the PLL of a voltage controlled oscillator VCO is connected to a transmission line . The VCO can be a conventional VCO or a switch controlled oscillator SCO as described in . The transmission line is a 4 transmission line already described with reference to . The input and the output of the transmission line are mixed in a mixer the output of which is fed to a low pass filter and a charge pump connected to the VCO . The mixer low pass filter and charge pump form part of the feedback loop of the PLL. The output forms the phase locked output of the PLL.

With reference to the DLL of many elements are identical to the embodiment of . However the output of the low pass filter is sent to a control logic block and the output of block forms the digital control bits that control the switching of the MOS transistors of transmission line . The output forms the phase locked output of the DLL.

DiCAD based SCO SCPS SCVI SCRF and SCPLL DLL are key building blocks to build software radio with reconfigurable agile frequency hopping capability for multi band and multi mode communication systems. Advantages of the presently disclosed systems and methods include 

On chip DiCAD based SCOs phase shifters impedance matching network have been designed simulated and implemented in silicon.

Digital controlled artificial dielectrics with wide tuning range on frequency phase delay and impedance are important for software radio implementations. The DiCAD can be used to tune operating frequencies of components such as resonators antennas filters baluns duplexers to tune phase delay in transmission lines to shrink the size of inductors and transformers. It can be inserted to circuits such as amplifiers mixers filters oscillators PLLs DLLs and any other circuits with large frequency phase delay or impedance tuning requirements. The disclosed techniques and circuits are ideal for software radio building block circuits.

Two different structures have been shown in . shows a differential structure where a ground reference is not needed because of the virtual ground present in all differential structures. shows a non differential structure in combination with a ground reference. The following examples of A and B have been described with reference to the differential structure of . However the person skilled in the art will understand upon reading of the present disclosure that the two structures of are interchangeable therebetween and that the examples of A and B could also be implemented with the structure shown in .

Further with reference to the switch embodiments while the presence of MOS or CMOS switches is to be preferred other kind of switches having three terminals or more can be used.

Therefore in summary according to one of the embodiments of the present disclosure tuning devices and methods are disclosed. One of the devices comprises a metal structure connected with artificial dielectric elements and variable capacitance devices. Each variable capacitance device is connected with a respective artificial dielectric element and with a control signal. Control of the variation of the capacitance allows the desired tuning. Another device comprises metallic structures connected with artificial dielectric elements and switches connected between the artificial dielectric elements. Turning ON and OFF the switches allows the capacitance between artificial dielectric elements to be varied and a signal guided by the metallic structures to be tuned.

While several illustrative embodiments of the invention have been shown and described numerous variations and alternative embodiments will occur to those skilled in the art. Such variations and alternative embodiments are contemplated and can be made without departing from the spirit and scope of the invention as defined in the appended claims.

