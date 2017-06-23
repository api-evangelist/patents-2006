---

title: Ahead-of-time scheduling of commands in RFID reader systems
abstract: RFID reader systems, software and methods precompute one or more reader commands, before a tag actually responds to an earlier transmitted command. This way a system can result at a high data rate, while meeting specification requirements of responding within a preset time.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08427315&OS=08427315&RS=08427315
owner: Impinj, Inc.
number: 08427315
owner_city: Seattle
owner_country: US
publication_date: 20060823
---
This utility patent application claims priority from U.S.A. Provisional Patent Application No. 60 786 875 filed 2006 Mar. 29 the disclosure of which is hereby incorporated by reference for all purposes.

The present description is related to the field of Radio Frequency IDentification RFID and more specifically to devices systems software and methods for RFID readers.

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers the latter are also known as RFID reader writers or RFID interrogators . RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a power management section a radio section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

RFID readers and tags typically communicate with each other in accordance with an air interface protocol. An air interface protocol may be described as a precise and detailed written description and set of rules defining the way in which a reader and tags operate while communicating via radio waves. An air interface protocol may define the types of commands and responses that may be communicated as well as the timing requirements for such communications.

Meeting the timing requirements sometimes is a challenge. For example when a reader receives a response from a tag it may have a short time to respond. This is a problem particularly in environments that have high data rates. The reader may have a challenge if it tries to do further operations such as error checking and respond also as it is determined from the error checking.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

The present description gives instances of RFID reader systems software and methods the use of which may help overcome these problems and limitations of the prior art. Briefly a next reader command starts being planned before it is needed.

In some embodiments a first reader command is transmitted. Before a first tag response is actually received interim processing can begin for generating a second command. When a first tag response is actually received this second reader command can be transmitted responsive to the received first tag response.

An advantage of the invention is that the second reader command is generated and sent more quickly because its generation began before the actual first tag response is received. And this can be critical for responding within the time allotted by the protocol if processing is to be performed additional to the received actual first tag response.

Another advantage over the prior art is that the time saved can be relatively so large that additional processing can be performed. When this additional processing is error checking it increases the performance of the RFID reader system even in the face of interference.

This and other features and advantages of the invention will be better understood in view of the Detailed Description and the Drawings in which 

As has been mentioned the present description is about RFID reader systems software and methods for RFID readers to start computing their next command before even receiving a response from a tag. Such implementations are sometimes referred to as Ahead Of Time Scheduling AOTS . The subject is now described in more detail.

Reader and tag exchange data via wave and wave . In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and decoded from RF waveforms.

Encoding the data in waveforms can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a delimiter a calibration symbol and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired. In turn when the waveforms are processed internally by reader and tag they can be equivalently considered and treated as numbers having corresponding values and so on.

Tag can be a passive tag or an active tag i.e. having its own power source. Where tag is a passive tag it is powered from wave .

Tag is formed on a substantially planar inlay which can be made in many ways known in the art. Tag also includes two antenna segments which are usually flat and attached to inlay . Antenna segments are shown here forming a dipole but many other embodiments using any number of antenna segments are possible.

Tag also includes an electrical circuit which is preferably implemented in an integrated circuit IC . IC is also arranged on inlay and electrically coupled to antenna segments . Only one method of coupling is shown while many are possible.

In operation a signal is received by antenna segments and communicated to IC . IC both harvests power and responds if appropriate based on the incoming signal and its internal state. In order to respond by replying IC modulates the reflectance of antenna segments which generates the backscatter from a wave transmitted by the reader. Coupling together and uncoupling antenna segments can modulate the reflectance as can a variety of other means.

In the embodiment of antenna segments are separate from IC . In other embodiments antenna segments may alternately be formed on IC and so on.

The components of the RFID system of may communicate with each other in any number of modes. One such mode is called full duplex. Another such mode is called half duplex and is described below.

RFID reader and RFID tag talk and listen to each other by taking turns. As seen on axis TIME when reader talks to tag the communication session is designated as R T and when tag talks to reader the communication session is designated as T R . Along the TIME axis a sample R T communication session occurs during a time interval and a following sample T R communication session occurs during a time interval . Of course interval is typically of a different duration than interval here the durations are shown approximately equal only for purposes of illustration.

According to blocks and RFID reader talks during interval and listens during interval . According to blocks and RFID tag listens while reader talks during interval and talks while reader listens during interval .

In terms of actual technical behavior during interval reader talks to tag as follows. According to block reader transmits wave which was first described in . At the same time according to block tag receives wave and processes it. Meanwhile according to block tag does not backscatter with its antenna and according to block reader has no wave to receive from tag .

During interval tag talks to reader as follows. According to block reader transmits a Continuous Wave CW which can be thought of as a carrier signal that ideally encodes no information. As discussed before this carrier signal serves both to be harvested by tag for its own internal power needs and also as a wave that tag can backscatter. Indeed during interval according to block tag does not receive a signal for processing. Instead according to block tag modulates the CW emitted according to block so as to generate backscatter wave . Concurrently according to block reader receives backscatter wave and processes it.

In the above an RFID reader interrogator may communicate with one or more RFID tags in any number of ways. Some such ways are called protocols. A protocol is a specification that calls for specific manners of signaling between the reader and the tags.

As discussed above in the Background section one such protocol is called the Specification for RFID Air interface EPC Radio Frequency Identity Protocols Class 1 Generation 2 UHF RFID Protocol for Communications at 860 MHz 960 MHz which is also colloquially known as the Gen2 Spec . The Gen2 Spec has been ratified by EPCglobal which is an organization that maintains a website at at the time this document is initially filed with the USPTO.

It was described above how reader and tag communicate in terms of time. In addition communications between reader and tag may be restricted according to frequency. One such restriction is that the available frequency spectrum may be partitioned into divisions that are called channels. Different partitioning manners may be specified by different regulatory jurisdictions and authorities e.g. FCC in North America CEPT in Europe etc. .

The reader typically transmits with a transmission spectrum that lies within one channel. In some regulatory jurisdictions the authorities permit aggregating multiple channels into one or more larger channels but for all practical purposes an aggregate channel can again be considered a single albeit larger individual channel.

Tag can respond with a backscatter that is modulated directly onto the frequency of the reader s emitted CW also called baseband backscatter. Alternatively Tag can respond with a backscatter that is modulated onto a frequency developed by Tag that is different from the reader s emitter CW and this modulated tag frequency is then impressed upon the reader s emitted CW. This second type of backscatter is called subcarrier backscatter. The subcarrier frequency can be within the reader s channel can straddle the boundaries with the adjacent channel or can be wholly outside the reader s channel.

A number of jurisdictions require a reader to hop to a new channel on a regular basis. When a reader hops to a new channel it may encounter RF energy there that could interfere with communications.

Embodiments of the present disclosure can be useful in different RFID environments for example in the deployment of RFID readers in sparse or dense reader environments in environments with networked and disconnected readers such as where a hand held reader may enter the field of networked readers in environments with mobile readers or in environments with other interference sources. It will be understood that the present embodiments are not limited to operation in the above environments but may provide improved operation in such environments.

Circuit includes at least two antenna connections which are suitable for coupling to one or more antenna segments not shown in . Antenna connections may be made in any suitable way such as pads and so on. In a number of embodiments more than two antenna connections are used especially in embodiments where more antenna segments are used.

Circuit includes a section . Section may be implemented as shown for example as a group of nodes for proper routing of signals. In some embodiments section may be implemented otherwise for example to include a receive transmit switch that can route a signal and so on.

Circuit also includes a Power Management Unit PMU . PMU may be implemented in any way known in the art for harvesting raw RF power received via antenna connections . In some embodiments PMU includes at least one rectifier and so on.

In operation an RF wave received via antenna connections is received by PMU which in turn generates power for components of circuit . This is true for either or both of R T sessions when the received RF wave carries a signal and T R sessions when the received RF wave carries no signal .

Circuit additionally includes a demodulator . Demodulator demodulates an RF signal received via antenna connections . Demodulator may be implemented in any way known in the art for example including an attenuator stage amplifier stage and so on.

Circuit further includes a processing block . Processing block receives the demodulated signal from demodulator and may perform operations. In addition it may generate an output signal for transmission.

Processing block may be implemented in any way known in the art. For example processing block may include a number of components such as a processor a memory a decoder an encoder and so on.

Circuit additionally includes a modulator . Modulator modulates an output signal generated by processing block . The modulated signal is transmitted by driving antenna connections and therefore driving the load presented by the coupled antenna segment or segments. Modulator may be implemented in any way known in the art for example including a driver stage amplifier stage and so on.

In one embodiment demodulator and modulator may be combined in a single transceiver circuit. In another embodiment modulator may include a backscatter transmitter or an active transmitter. In yet other embodiments demodulator and modulator are part of processing block .

It will be recognized at this juncture that circuit can also be the circuit of an RFID reader according to the invention without needing PMU . Indeed an RFID reader can typically be powered differently such as from a wall outlet a battery and so on. Additionally when circuit is configured as a reader processing block may have additional Inputs Outputs I O to a terminal network or other such devices or connections.

In terms of processing a signal circuit operates differently during a R T session and a T R session in treating a signal. The different operations are described below.

Version A shows as relatively obscured those components that do not play a part in processing a signal during a R T session. Indeed PMU may be active but only in converting raw RF power. And modulator generally does not transmit during a R T session. Modulator typically does not interact with the received RF wave significantly either because switching action in section of decouples the modulator from the RF wave or by designing modulator to have a suitable impedance and so on.

While modulator is typically inactive during a R T session it need not be always the case. For example during a R T session modulator could be active in other ways. For example it could be adjusting its own parameters for operation in a future session.

Version B shows as relatively obscured those components that do not play a part in processing a signal during a T R session. Indeed PMU may be active but only in converting raw RF power. And demodulator generally does not receive during a T R session. Demodulator typically does not interact with the transmitted RF wave either because switching action in section decouples the demodulator from the RF wave or by designing demodulator to have a suitable impedance and so on.

While demodulator is typically inactive during a T R session it need not be always the case. For example during a T R session demodulator could be active in other ways. For example it could be adjusting its own parameters for operation in a future session.

Local block is responsible for communicating with the tags. Local block includes a block of an antenna and a driver of the antenna for communicating with the tags. Some readers like that shown in local block contain a single antenna and driver. Some readers contain multiple antennas and drivers and a method to switch signals among them including sometimes using different antennas for transmitting and for receiving. And some readers contain multiple antennas and drivers that can operate simultaneously. A demodulator decoder block demodulates and decodes backscattered waves received from the tags via antenna block . Modulator encoder block encodes and modulates an RF wave that is to be transmitted to the tags via antenna block .

Local block additionally includes an optional local processor . Processor may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation digital and or analog processors such as microprocessors and digital signal processors DSPs controllers such as microcontrollers software running in a machine such as a general purpose computer programmable circuits such as Field Programmable Gate Arrays FPGAs Field Programmable Analog Arrays FPAAs Programmable Logic Devices PLDs Application Specific Integrated Circuits ASIC any combination of one or more of these and so on. In some cases some or all of the decoding function in block the encoding function in block or both may be performed instead by processor .

Local block additionally includes an optional local memory . Memory may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation nonvolatile memories NVM read only memories ROM random access memories RAM any combination of one or more of these and so on. Memory if provided can include programs for processor to run if provided.

In some embodiments memory stores data read from tags or data to be written to tags such as Electronic Product Codes EPCs Tag Identifiers TIDs and other data. Memory can also include reference data that is to be compared to the EPC codes instructions and or rules for how to encode commands for the tags modes for controlling antenna and so on. In some of these embodiments local memory is provided as a database.

Some components of local block typically treat the data as analog such as the antenna driver block . Other components such as memory typically treat the data as digital. At some point there is a conversion between analog and digital. Based on where this conversion occurs a whole reader may be characterized as analog or digital but most readers contain a mix of analog and digital functionality.

If remote components are indeed provided they are coupled to local block via an electronic communications network . Network can be a Local Area Network LAN a Metropolitan Area Network MAN a Wide Area Network WAN a network of networks such as the internet and so on. In turn local block then includes a local network connection for communicating with network .

There can be one or more remote component s . If more than one they can be located at the same place with each other or in different places. They can access each other and local block via network or via other similar networks and so on. Accordingly remote component s can use respective remote network connections. Only one such remote network connection is shown which is similar to local network connection etc.

Remote component s can also include a remote processor . Processor can be made in any way known in the art such as was described with reference to local processor .

Remote component s can also include a remote memory . Memory can be made in any way known in the art such as was described with reference to local memory . Memory may include a local database and a different database of a Standards Organization such as one that can reference EPCs.

Of the above described elements it is advantageous to consider a combination of these components designated as operational processing block . Block includes those that are provided of the following local processor remote processor local network connection remote network connection and by extension an applicable portion of network that links connection with connection . The portion can be dynamically changeable etc. In addition block can receive and decode RF waves received via antenna and cause antenna to transmit RF waves according to what it has processed.

Block includes either local processor or remote processor or both. If both are provided remote processor can be made such that it operates in a way complementary with that of local processor . In fact the two can cooperate. It will be appreciated that block as defined this way is in communication with both local memory and remote memory if both are present.

Accordingly block is location agnostic in that its functions can be implemented either by local processor or by remote processor or by a combination of both. Some of these functions are preferably implemented by local processor and some by remote processor . Block accesses local memory or remote memory or both for storing and or retrieving data.

Reader system operates by block generating communications for RFID tags. These communications are ultimately transmitted by antenna block with modulator encoder block encoding and modulating the information on an RF wave. Then data is received from the tags via antenna block demodulated and decoded by demodulator decoder block and processed by processing block .

The invention also includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system.

These methods can be implemented in any number of ways including the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the program.

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

Embodiments of an RFID reader system can be implemented as a combination of hardware and software. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination. An example of such a subdivision is now described.

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor.

System moreover includes an Application Programming Interface module which is also known as API Modem API and MAPI. In some embodiments module is itself an interface for a user.

System further includes a host processor . Processor exchanges signals with MAC layer via module . In some embodiments host processor is not considered as a separate module but one that includes some of the above mentioned modules of system . A user interface is coupled to processor and it can be manual automatic or both.

Host processor can include applications for system . In some embodiments elements of module may be distributed between processor and MAC layer .

It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. That which is to be transmitted becomes ultimately signals for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

An economy is achieved in the present document in that a single set of flowcharts is used to describe methods in and of themselves along with operations of hardware and or software. This is regardless of how each element is implemented.

The challenges of the prior art are now described. Description is by using as an example the above mentioned Gen2 Spec which is also known as the Gen2 protocol.

This document defines physical and logical requirements for a passive backscatter interrogator talks first ITF RFID system operating in the 860 MHz 960 MHz frequency range. The Gen2 Spec defines an industry standard designed to promote interoperability between RFID readers and tags manufactured by different vendors. It should be kept in mind however that the present invention is by no means limited to systems designed to operate in accordance with the Gen2 air interface protocol nor to any other specific protocol.

Link timing examples are now described. They are the type that might occur when a reader inventories a population of tags by presenting slots and one or more tags reply per slot.

Part A of depicts a first link timing example which is generally denoted with reference numeral . This example represents a single tag transaction such as might occur when a single tag replies in a slot. As shown shortly after the interrogator or reader starts its continuous wave CW transmission the reader transmits a Select command and following a time period denoted T the reader transmits a Query command . Within the time period denoted T the tag transmits or backscatters an RN16 response .

Then within the T timeout period the reader is required to make another transmission. In this example the reader transmits an Acknowledge ACK command .

As noted in the Gen2 protocol time delay T can be as small as 31.25 microseconds at fast enough data rates. This time period in which the reader is required to transmit a next command to prevent timeout of the tag could become even smaller in future versions of the Gen2 Spec or in new industry standards or de facto standards that may be adopted.

The tag then responds to the ACK command by backscattering its PC EPC and CRC16 which are generally denoted with reference numeral . The reader then transmits within the time period T a QueryRep or QueryAdj command if the EPC is valid or a NAK if the EPC is invalid.

In part B of reference numeral generally refers to a linked timing example in which multiple tags reply in a slot. In this case the replies are said to be collided. In this example the reader issues a Query command and multiple tags reply with their respective RN16 responses . In this case a collision is detected and so the reader issues a QueryRep command . When no reply is detected within the time periods denoted by T T the reader issues a second QueryRep command . Following this a single tag response is detected in this case an RN16 response . Then within the time period denoted T the reader transmits an ACK command and then another QueryRep command . The second QueryRep command is transmitted by the reader since no reply was received within the time period T T. In the Gen2 Spec T is defined as the time from interrogator reader transmission to a tag response and T is defined as the time an interrogator reader waits after T before it issues another command.

According to a next operation the reader processes the tag response received at operation . Processing is for generating a next reader command that is appropriate according to the protocol in use for the received tag response.

According to a next operation the reader transmits the next reader command generated by the processing of operation . Execution then returns to operation .

The challenge of the prior art is illustrated by comment . The processing of operation has to be performed within the time period specified by the applicable air interface protocol. For example in a Gen2 environment this time period is T which is measured from the end of the tag response and substantially concurrent receipt of it by the reader to the start of the next reader command being transmitted. As noted above T can be as small as 31.25 microseconds. It will be appreciated that in terms of how long various operations take operation is by far the most time consuming one.

Methods are now described more particularly according to embodiments. In the below the order of operations is not constrained to what is shown and different orders may be possible. In addition actions within each operation can be modified deleted or new ones added without departing from the scope and spirit of the invention.

In addition a first tag response to the first reader command can be anticipated according to the protocol. This anticipating can be programmed in or executed as an operation. The first anticipated tag response can be any such response such as a RN16 a tag code a collision of responses from multiple tags or even no response at all. The first anticipated tag response can further depend on different possible scenarios. For example in the face of interference it can be a response that is not recognized.

In some embodiments a reader system performs a process for inventorying a group of tags such as by using a slotted aloha process. In these the transmitted first reader command can be part of this inventorying process and the generated second reader command can continue the inventorying process. Depending on the tag responses actual and anticipated the inventorying process can be continued as is or the generated second reader command can adjust one of its parameters. Examples of a description of such an inventorying process can be seen in U.S. patent application Ser. No. 11 210 384 published as US 2005 0280505A1 the disclosure of which is hereby incorporated by reference.

For specific implementations of the Gen 2 Spec an inventorying process can be set up with the reader system transmitting a Query command. One of the first anticipated tag responses is a Random Number and the generated second reader command includes an Acknowledge command.

When the inventorying process is going the first reader command can be a QueryRep command for examining the contents of a next slot. The first anticipated tag response can be a Null response in which case the generated second reader command can be another QueryRep command. Or the first anticipated tag response can be a collision in which the generated second reader command can be a QueryAdj command for adjusting a Q parameter. In addition a new Q parameter can be computed and communicated with this generated second reader command. A particular example will be described with reference to .

In flowchart according to an optional next operation the anticipated first tag response is determined. In fact one or more of such responses can be determined. These can be determined in any number of ways as will be evident to a person skilled in the art. One such way is by looking up stored tag responses that are legitimate according to the protocol for the first reader command. They can be stored in a storage medium such as a memory buffer etc. either by themselves or upon having decided on which is the first reader command.

According to a next operation a second reader command is generated. In fact one or more such second reader commands are generated which are desirable and legitimate according to the protocol in use for responding to the first anticipated tag response.

Importantly computation for generating the second reader command commences before completely receiving a first tag response as is later described for operation of flowchart . Considering the intended use of the second reader command this computation is really a precomputation because the first tag response is not yet known. In some embodiments this precomputation commences before even transmitting even the first reader command at operation . In some embodiments this whole precomputation is completed before that time.

Generating the second reader command can be performed in a number of ways. For example it can include looking up stored reader commands that are legitimate according to the protocol for responding to the first anticipated tag response. Or it can assemble them e.g. by checking individually their legitimacy and desirability. According to an optional next operation the one or more generated second reader commands are stored in a buffer. Along with the commands the one or more first anticipated tag responses can also be stored e.g. for indexing. Various implementations are possible.

In some embodiments the second reader command is generated by processing at a first layer of the RFID reader system and the buffer is in a second layer of the RFID reader system. For example this buffer may be in the data link or physical layer of the reader whereas the interim processing in this example is performed in the MAC layer. In other embodiments the buffer is in a first layer of the RFID reader system where the second reader command is generated. The second reader command can be transferred to a second layer of the RFID reader system for being transmitted.

According to next operation there is received an actual backscattered first tag response to the first reader command in accordance with the protocol. This is performed as described above for flowchart . A difference however is that by now some computation has already taken place.

According to an optional next operation the actual first tag response received at operation is error checked. This can be performed in any number of ways such as is described for example in co pending U.S. patent application Ser. No. 11 388 235 filed 2006 Mar. 22 entitled Error Recovery in RFID Reader Systems . The disclosure of that application is hereby incorporated by reference. A more robust reader system can thus result especially in environments of high interference.

According to an optional operation it is determined whether the generated second reader command is to be transmitted. The determination takes place from the actual first tag response received at operation and can take place in a number of ways. In some embodiments the determination is made depending on whether the received actual first tag response corresponds to the first anticipated tag response. In some embodiments the actual first tag response corresponds to the first anticipated tag response if they match. If it is determined to not transmit the generated second reader command the process ends.

If at operation it is determined to transmit the generated second reader command then according to an optional next operation one or more stored parameters can be looked up for the generated second reader command whose transmission is impending. The parameter depends on the operation. A related example is described later in this document with reference to in an inventorying operation. The parameter can be stored in a memory buffer such as described above.

According to a next operation the generated second reader command is transmitted responsive to the first tag response received at operation . If operation has taken place then the generated second reader command is transmitted only if it is so determined. Else another command can be transmitted or no command can be transmitted.

Execution then can either stop there or iterate such as right after box . This way these operations can be repeated for one or more second anticipated tag responses to the second reader command which was transmitted at operation . In addition one or more third reader responses can be generated for the one or more second anticipated tag responses and so on.

In these embodiments more than one first tag responses can be anticipated and for each such tag response one or even more second reader commands can be generated. In fact all possible tag responses can be anticipated this way with second reader responses. Then the transmitted second reader command is the one of those whose anticipated first tag response corresponds to the actual received first tag response. In these embodiments where multiple ones of these are determined the desirable second reader command can be identified from its corresponding anticipated tag response. So at operation the transmitted second reader command is the appropriate one for the actual first tag response.

According to a comment operations should be performed in some embodiments within a limited time. And as before only operations require appreciable amounts of time. More time is available however because interim processing has already started at operation instead of waiting for the actual tag response at operation . In fact the time savings can be so much that additional operation of error checking can also be accommodated within this time.

The operations described herein may take place by appropriate design of components and distribution of tasks among the components as will be apparent to a person skilled in the art. For example buffers can be implemented in the various modules of which can store commands and communicate commands in an advantageous manner. In some embodiments pre computed commands can be stored in a buffer and then transmitted. In some embodiments they can be stored in the buffer of one component e.g. the MAC layer and transmitted to another e.g. the Physical layer . For purposes of programming commands can be given suitable names and so on.

The example of diagram can be one of an inventorying operation. After the reader system transmits a Query command it receives a tag response of an RN16. For this example there was no collision and the tag responded immediately without needing any QueryRep commands from the initial Query command .

At an operation tag response is error checked. In this instance error checking involves checking thresholds of tag response and in particular checking whether its waveform segments are high and low by appropriate margins. If they are then an Acknowledge command can be transmitted.

According to an operation a calculation can start taking place for when it is needed next. It can be anticipated that the tag will respond to Acknowledge command with an EPC Electronic Product Code that will pass some criteria and therefore inventorying will continue without accessing the tag. Operation can determine whether the next inventorying command will be a Query QueryRep or QueryAdj. For example if the Q only is to change then a QueryAdj may be called for. Note that Q is the slot count parameter as defined in the Gen2 Specification. 

It should be noted that operation starts taking place before a response is actually received to Acknowledge command . In fact it can start taking place before Acknowledge command is even transmitted. Although not shown computed results are preferably stored.

Then at an operation A tag response is error checked. In this instance error checking again involves checking thresholds of tag response . Then at an operation B tag response is error checked for whether the CRC checks out with the EPC. Then at an operation an additional internal check is made.

Then at operation a determination is made as to whether to use the commands computed at operation . The determination is made based on the received tag response and in this case it is more particularly as to whether the tag is to be accessed or inventorying will proceed with another tag. In this case inventorying is to proceed with another tag.

Then at operation a stored parameter is looked up such as a next slot number a Q value whether new or not and so on. Then the generated command is transmitted which can be another Query or a QueryRep or a QueryAdj command.

It will be appreciated that at various portions of diagram there are time limits for responding. These time limits are T and T relative to tag response and T relative to tag responses and . The precomputing at operation enabled responding with second generated command within time T from first actual received tag response even at high data rates.

The overall signal flow begins when the reader in MAC layer starts a CW transmission . This is propagated from MAC layer to Physical layer and then to Transmit Receive layer . MAC layer then generates a Select command and this is propagated to Physical layer and so on as shown. MAC layer then generates a Query command and propagates this to Physical layer .

During this interval Select command has been propagated to Transmit Receive layer as shown. At this point MAC layer knows that its last command was Select command and its next command which has yet to be propagated to the Transmit Receive layer is Query command . Thus MAC layer begins to schedule its next command. This is represented by reference numeral which points to a table or buffer in which a group of reader to tag commands are shown including ACK two instances of NONE and three instances of QueryRep. For example if the receiver status is OK then a suitable next command would be the ACK command. This table buffer is propagated to Physical layer within the time period denoted by T in . As mentioned T represents the minimum time period separating successive R T commands.

Following this time period T Query command is propagated from Physical layer to Transmit Receive layer as shown. Once the reader system also called a reader for short completes the transmission of Query command the signal flow moves back to MAC layer as shown.

During the next T time interval the reader detects an empty window denoted by reference numeral and therefore MAC layer determines that the appropriate next command is the QueryRep command corresponding to the empty window receiver status. This is represented by reference numeral . This QueryRep command is constructed in memory structure and is made accessible to or placed in Physical layer . Reference numeral denotes this QueryRep command being propagated to the Transmit Receive layer .

Subsequently the tag transmits an RN16 response which is first received in Transmit Receive layer and this is propagated back to MAC layer which uses this to begin construction of the next command which in this case would be ACK command .

Reference numeral denotes a first set of possible reader commands in this case comprising only a Select command. The anticipated response to the Select command is designated with reference numeral . In this case the Null or no response is appropriate to the Select command.

Reference numeral denotes the second set of possible R T commands. In this case only the Query command would be appropriate to the Null T R response .

As shown the two possible R T responses to the Query command include the Null response and an RN16 response . As also shown before the MAC layer may pre compute the next reader command s and pass these from the MAC layer to the Physical layer.

Moreover reference numeral shows a third set of possible reader commands including a second set of Query QueryRep and QueryAdj commands denoted Query QueryRep and QueryAdjust respectively as well as an Acknowledge ACK command.

Each of these possible reader commands can be further mapped to an anticipated T R response. As shown these include the Null None response an RN16 response and a response including a PC EPC and CRC and another Null None response .

These possible T R responses can similarly be mapped to a fourth set of possible reader commands denoted generally by reference numeral . Again these pre computed reader commands can be initially formulated by the MAC layer and propagated to the Physical layer.

As noted in the a Null T R response may indicate a collided response or an empty slot or an unresolvable EPC or CRC16 error from the tag.

In this description numerous details have been set forth in order to provide a thorough understanding. In other instances well known features have not been described in detail in order to not obscure unnecessarily the description.

A person skilled in the art will be able to practice the present invention in view of this description which is to be taken as a whole. The specific embodiments as disclosed and illustrated herein are not to be considered in a limiting sense. Indeed it should be readily apparent to those skilled in the art that what is described herein may be modified in numerous ways. Such ways can include equivalents to what is described herein.

The following claims define certain combinations and subcombinations of elements features steps and or functions which are regarded as novel and non obvious.

Additional claims for other combinations and subcombinations may be presented in this or a related document. These claims apply to systems software and methods etc. above and beyond those merely compliant with the Gen2 Spec except where specifically written so.

