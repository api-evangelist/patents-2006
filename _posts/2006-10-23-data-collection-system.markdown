---

title: Data collection system
abstract: A data collection system includes: a contact information acquisition unit, for obtaining contact information; a state recognition unit, for obtaining, based on contact information acquired by the contact information acquisition unit, state information concerning the state of a equipment; a state coding unit, for transforming into coded contact associated information the state information obtained by the state recognition unit; and an output unit, for transmitting to an output apparatus contact information obtained by the contact information acquisition unit and for transmitting to a network apparatus contact associated information obtained by the state coding unit. With this arrangement, information concerning the operation of a equipment can be easily obtained, without requiring the reconstruction of a equipment or a great change in a sequence program, such as a programmable controller, mounted in the equipment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07854377&OS=07854377&RS=07854377
owner: Omron Corporation
number: 07854377
owner_city: Kyoto
owner_country: JP
publication_date: 20061023
---
This application claims priority from Japanese patent applications 2005 306811 filed on Oct. 21 2005 2005 306812 filed Oct. 21 2005 and 2006 152359 filed May 31 2006. The entire content of the aforementioned applications are incorporated herein by reference.

The present disclosure relates to a data collection system for collecting data concerning the operation of equipment such as production machines that constitute a production line.

A first related art data collection system is one that simplifies the acquisition of the latest information concerning equipment abnormalities see for example patent document 1 .

A second related art data collection system is one comprising an interface for at least transforming the output of a lamp a buzzer or a sensor used to indicate an operating state for a production equipment to obtain an ON OFF signal indicating a start a standby a fault or a halted state and a equipment operating state recording apparatus which is connected to the interface for at least recording the start standby fault or halted state data indicating the cause of a fault or a halt and the start and end times for the individual states of the equipment. According to the characteristic of this system a plurality of keys provided for the equipment operating state recording apparatus are allocated for a display unit and multiple choices for the cause of a fault at the production equipment or the halting thereof are allocated to these keys. In accordance with a signal pattern received from the interface an entry made with a key representing a pertinent choice is enabled for the display unit of the equipment operating recording apparatus and since an operator selectively used the key to enter data cause data allocated to the key are recorded as data representing the cause of the fault at the production equipment or the halting thereof. After an operator has entered an end key to counter the cause of the fault or the halting the entry of another cause input key is enabled and the time at which the end key was entered is recorded as the start of the new cause or of the standby state see patent document 2 .

A third related art data collection system is a production management system for managing a plurality of apparatuses connected to a network in a specific area. According to the characteristic of this system a communication port is provided for controllers of units that belong to the apparatuses in order that they may be connected to a network independent of the network in the specific area. The controllers perform at least one of the data collection data statistics data processing and data storage tasks associated with the units and transmit to a maintenance management computer connected to the independent network various types of information produced by employing data that are thus obtained. Then the maintenance management computer records and displays the received information for the performance of at least one of the overall control monitoring management and maintenance operations for the units see patent document 3 .

A fourth related art data collection system comprises a first LAN and a second LAN and a separation unit and a storage unit connected between the first LAN and the second LAN. According to the characteristic of this system the separation unit separates the first and the second LANs so that the two do not adversely affect each other and so that the control unit is accessible via both the first and the second LANs see for example patent document 4 .

A fifth related art data collection system is a system for a equipment that can appropriately evaluate a measurement for reducing a period for a stop due to a fault in accordance with the cause of the stop see for example patent document 5 .

According to a sixth related art data collection system a dedicated monitoring PLC is located between a PC and a programmable controller for a plurality of facilities. PLCs for the individual facilities transform signals indicating operating states cycle times and production quantities and the cause of an abnormality that caused an equipment to be halted into code and output this code as BCD binarized decimal signals to the dedicated monitoring PLC. The dedicated monitoring PLC sequentially monitors the equipment PLCs and uses data thus collected to calculate an operating rate for each equipment. Then the dedicated monitoring PLC adds this operating rate or the number of halt times to a halt history provided for each cause or for each equipment and stores the data in a register and also transmits them to the PC. The PC fetches the thus received data to table calculation software while constantly monitoring the operating state of the equipment and prepares a daily report or a monthly report or performs a data analysis see patent document 6 .

However it is not easy for these related art first to sixth data collection systems to be installed in a related art production equipment such as a equipment. Specifically when one of the related art first to sixth data collection systems is used to collect information for the operation of a production equipment the production equipment must be customized or a sequence program such as a programmable controller mounted in the production equipment must be greatly modified.

Furthermore for the transmission and reception of data the related art first to the sixth data collection systems can not represent using a small number of bits state information concerning various types of equipment states. Thus for a system that includes very large production facilities such as plants the free flow of network traffic would be threatened to collect state information for equipments.

Furthermore for the related art first to the sixth data collection system the operating state of the equipment cannot be satisfactorily analyzed. Specifically since information upon the occurrence of an abnormality such as operator moving time information and restoration time information cannot be obtained a counterplan required for a production job site cannot be performed. Furthermore since the occurrence rates for the individual states including the abnormal state and the durations and frequencies of these states cannot be obtained measures for the improvement of productivity and the improvement of quality at the production job site cannot be performed.

a divergence apparatus located between a equipment and an output apparatus for outputting contact information concerning an operation performed by the equipment 

With this arrangement information concerning the operation of a equipment can be easily obtained without having to customize a equipment or greatly change a sequence program such as a programmable controller mounted in the equipment.

According to a second aspect of the invention the data collection system of the first aspect further comprises 

With this arrangement a collected operating data log can be analyzed. Through this analysis for example solutions such as the need to increase the number of operators or the need to establish restoration procedures can be found.

Further with this arrangement information concerning the operation of a equipment can be easily obtained without having to customize a equipment or greatly change a sequence program such as a programmable controller mounted in the equipment.

According to a third aspect of the invention in addition to the data collection system of the first or the second aspect the divergence apparatus further includes 

a state recognition unit for employing contact information acquired by the contact information acquisition unit to obtain state information which is information concerning a state of the equipment and

a state coding unit for transforming the state information obtained by the state recognition unit into coded contact associated information and

the output unit transmits to the output apparatus the contact information obtained by the contact information acquisition unit and also transmits to the network apparatus the contact associated information obtained through a transform performed by the state coding unit.

With this arrangement data can be coded before being output to a network so that the network traffic can be reduced. Further the data collection system is extremely effective especially when introduced into a large production system such as a plant.

According to a fourth aspect of the invention in addition to the data collection system of the third aspect the state coding unit further includes 

a coding map storage unit for storing a coding map representing a correlation between state information which indicates state patterns for n contacts n is an integer of two or greater and contact associated information which is code in n 1 bits or smaller and

a contact associated information acquisition unit for obtaining from the coding map contact associated information that is correlated with state information obtained by the state recognition unit.

With this arrangement multiple state types can be handled by using a small number of bits and network traffic can be reduced. Furthermore the data collection system is extremely effective especially when introduced into a large production system such as a plant.

According to a fifth aspect of the invention in addition to the data collection system of the third aspect the state coding unit includes 

a coding map storage unit for storing a coding map according to which contact associated information correlated with state information that indicates a set of two or more states is regarded as the sum of contact associated information sets that are correlated with the two or more states and

a contact associated information acquisition unit for obtaining from the coding map contact associated information correlated with state information obtained by the state recognition unit.

With this arrangement the operating states generated simultaneously can be sorted and as a result a production management department can obtain the state of the equipment more quickly.

According to a sixth aspect of the invention in addition to the data collection system of the fourth or fifth aspect the contact outputs the state of a buzzer that is to be set either to the ON or to the OFF state or the state of a signal light that is to be turned on or off or to blink. The state information includes asynchronous information that is generated asynchronously with a change in the state of the buzzer and a change in the state of the signal light. When state information obtained by the state recognition unit includes asynchronous information the state coding unit transforms the state information into contact associated information which is code having a predetermined value regardless of whether information other than the asynchronous information is included in the state information obtained by the state recognition unit. And according to a seventh aspect of the invention in addition to the data collection system of the sixth aspect the asynchronous information is production count information indicating a production count for the equipment.

According to an eighth aspect of the invention in addition to the data collection system of the second aspect the analysis unit employs two or more sets of contact associated information to obtain operator moving time information which concerns moving time for a operator and restoration time information which concerns a restoration time. According to a ninth aspect of the invention in addition to the data collection system of the eighth aspect the analysis unit includes 

a operator moving time information acquisition unit for obtaining based on two or more sets of contact associated information information concerning a period extending from the start of the ON state of a buzzer to the OFF state and defining the information as operator moving time information and

a restoration time information acquisition unit for employing after the buzzer has been changed from on to off two or more sets of contact associated information to obtain information concerning a period required before the equipment is normal operation and defining the information as restoration time information.

With this arrangement information concerning the operation of the equipment can be easily obtained without changing the related art procedures followed by operators at a job site. That is in the related art when a fault has occurred at a common equipment a operator is notified by a buzzer. Then the operator moves to the reequipment and halts the buzzer sound by pressing for example a buzzer stop button. This is normally done to notify other operators that someone who can handle the fault has arrived at the pertinent apparatus. In other words should the buzzer sound continue two or more operators may move to the equipment to remove a fault. This is an inefficient situation. According to the arrangement of the invention information concerning the operation of the equipment can be obtained without having to change the normal process described above.

According to a tenth aspect of the invention in addition to the data collection system of the ninth aspect the analysis results output unit includes 

a moving time histogram output unit for preparing based on operator moving time information obtained by the operator moving time information acquisition unit a histogram that employs as respective axes operator moving time which is represented by the operator moving time information and a frequency at which movement during the pertinent moving time occurred and or a total time for one or more movements during the moving time and for outputting the histogram and

a restoration time histogram output unit for based on restoration time information obtained by the restoration time information acquisition unit preparing a histogram that employs as respective axes a restoration time which is represented by the restoration time information and a frequency of an occurrence of a restoration requiring the restoration time and or a total time for one or more restorations each of which require the restoration time and for outputting the histogram.

With this arrangement a countermeasure at a production job site can be easily effected. Specifically when the moving time is displayed using a histogram it is possible to determine whether the frequency at which the equipment was halted is higher when the moving time was long or when the moving time was short. When the frequency at which the equipment was halted during a long moving time is high it is apparent that the arrangement of operators is a problem. When the restoration time is displayed using a histogram it is possible to determine whether the frequency at which the equipment was halted was higher when the restoration time was long or when the restoration time was short. When the restoration time was long it can be assumed that trouble halts occurred frequently and that countermeasures for trouble halts are required. When the restoration time was short it can be assumed that short time halts occurred frequently and that countermeasures for short time halts are required. By displaying the histogram in this manner a counterplan for a equipment can be determined and supported. It should be noted that a short time halt is a short equipment stop event such as a clogged conveying line and that the equipment operation can be quickly restored by performing a comparatively easy process. A trouble halt however is a comparatively long equipment stop event that occurs as a result of a fault for which practical countermeasures have not yet been commonly employed e.g. either operators other than those having special skills can not handle the fault or to determine the required corrective action a manual or manuals must be referred to.

According to an eleventh aspect of the invention in addition to the data collection system of one of the eighth to the tenth aspects the contact associated information includes time information which is time related information and the analysis apparatus includes 

a correction unit for correcting based on a period that the state recognition unit requires to acquire state information correcting the operator moving time information and the restoration time information.

With this arrangement accurate timing of a state change such as the occurrence of a fault or a recovery operation for the equipment can be obtained. As a result the cause of a fault can be found easily.

According to a twelfth aspect of the invention in addition to the data collection system of one of the second to the eleventh aspects the data collection apparatus employs different network interfaces to connect to the divergence apparatus and to connect to the analysis apparatus.

With this arrangement a data collection network can be built that is independent of a general network installed in an office and without constituting a threat to the network traffic in the office information concerning the operation can be collected. A system configuration for which network traffic is taken into account is especially important in a plant where for a production system an extremely large number of equipments have been provided.

According to a thirteenth aspect of the invention in addition to the data collection system of the second aspect the analysis unit employs two or more sets of contact associated information to obtain operator moving time information which concerns the moving time for a operator and restoration time information which concerns a restoration time.

With this arrangement a collected operating data log can be analyzed. Through this analysis for example solutions such as the need to increase the number of operators or the need to establish restoration procedures can be found.

According to a fourteenth aspect of the invention in addition to the data collection system of the thirteenth aspect the analysis unit includes 

a operator moving time information acquisition unit for obtaining based on two or more sets of contact associated information information concerning a period extending from the start of the ON state of a buzzer to the OFF state and defining the information as operator moving time information and

a restoration time information acquisition unit for employing after the buzzer has been switched from on to off two or more sets of contact associated information to obtain information concerning a period required before the equipment is normal operation and defining the information as restoration time information.

With this arrangement information concerning the operation of the equipment can be easily obtained without changing the related art procedures followed by operators at a job site. That is in the related art when a fault has occurred at a common equipment a operator is notified by a buzzer. Then the operator moves to the reequipment and halts the sound of the buzzer by pressing for example a buzzer stop button. This is normally done to notify other operators that someone who can handle the fault has arrived at the pertinent apparatus. In other words should the buzzer sound continue two or more operators may move to the equipment to remove a fault. This is an inefficient situation. According to the arrangement of the invention information concerning the operation of the equipment can be obtained without having to change the normal process described above.

According to a fifteenth aspect of the invention in addition to the data collection system of the fourteenth aspect the analysis results output unit includes 

a moving time histogram output unit for preparing based on operator moving time information obtained by the operator moving time information acquisition unit a histogram that employs as respective axes operator moving time which is represented by the operator moving time information and a frequency at which movement during the pertinent moving time occurred and or a total time for one or more movements during the moving time and for outputting the histogram and

a restoration time histogram output unit for based on restoration time information obtained by the restoration time information acquisition unit preparing a histogram that employs as respective axes a restoration time which is represented by the restoration time information and a frequency for an occurrence of a restoration requiring the restoration time and or a total time for one or more restorations each of which require the restoration time and for outputting the histogram.

With this arrangement a countermeasure at a production job site can be easily effected. Specifically when the moving time is displayed using a histogram it is possible to determine whether the frequency at which the equipment was halted is higher when the moving time was long or when the moving time was short. When the frequency at which the equipment was halted during a long moving time is high it is apparent that the arrangement of operators is a problem. When the restoration time is displayed using a histogram it is possible to determine whether the frequency at which the equipment was halted was higher when the restoration time was long or when the restoration time was short. When the restoration time was long it can be assumed that trouble halts occurred frequently and that countermeasures for trouble halts are required. When the restoration time was short it can be assumed that short time halts occurred frequently and that countermeasures for short time halts are required. By displaying the histogram in this manner a counterplan for a equipment can be determined and supported. It should be noted that a short time halt is a short equipment stop event such as a clogged conveying line and that the equipment operation can be quickly restored by performing a comparatively easy process. A trouble halt however is a comparatively long equipment stop event that occurs as a result of a fault for which practical countermeasures have not yet been commonly employed e.g. either operators other than those having special skills can not handle the fault or to determine the required corrective action a manual or manuals must be referred to.

According to a sixteenth aspect of the invention in addition to the data collection system of one of the thirteenth to the fifteenth aspects the contact associated information includes time information which is time related information and the analysis apparatus includes 

a correction unit for correcting based on a period that the state recognition unit requires to acquire state information correcting the operator moving time information and the restoration time information.

With this arrangement accurate timing of a state change such as the occurrence of a fault or a recovery operation for the equipment can be obtained. As a result the cause of a fault can be found easily.

According to a seventeenth aspect of the invention in addition to the data collection system of the second aspect the analysis unit further includes 

an operating data statistical processor for calculating the total of durations of the individual states indicated by the state information for the equipment 

wherein the analysis results output unit outputs a graph showing occurrence rates for the states based on the total obtained by the operating data statistical processor of durations for the states that are indicated by the state information.

With this arrangement the occurrence rate of each state can be easily obtained for each equipment and a measure for a production job site such as an increase in productivity or an improvement in quality can be easily performed.

According to an eighteenth aspect of the invention in addition to the data collection system of the second aspect the analysis unit includes 

an operating data statistical processor for calculating durations or and frequencies of individual states indicated by state information for the equipment. Further based on the durations or and frequencies obtained by the operating data statistical processor the analysis results output unit outputs histograms for frequencies of the states.

With this arrangement the durations or and frequencies of the individual states can be easily obtained for each equipment and a measure for a production job site such as an increase in productivity or an improvement in quality can be easily performed.

According to a nineteenth aspect of the invention in addition to the data collection system of the second aspect the analysis unit includes 

an operating data statistical processor for calculating ON durations and frequencies for the individual states indicated by state information for the equipment and for also calculating OFF durations and frequencies for the states. Furthermore based on the ON durations and frequencies and the OFF durations and frequencies for the individual states that have been obtained by the operating data statistical processor the analysis output unit outputs ON histograms and OFF histograms that represent ON and OFF frequencies for the states.

According to a twentieth aspect of the present invention in addition to the data collection system of the nineteenth aspect the operating data statistical processor employs the ON duration and the frequency of a state and or the OFF duration and the frequency of a state to determine an occurrence type that is a type of an occurrence of a state and the analysis results output unit outputs the occurrence type.

With this arrangement the trend in the occurrence of an operating state can be more clearly categorized.

According to a twenty first aspect of the invention in addition to the data collection system of the nineteenth aspect the analysis unit includes 

a state identification information storage unit for storing state identification information that is used to identify a state and one or more occurrence types correlated with each other. Further the operating data statistical processor employs the ON duration and a frequency of a state and or the OFF duration and a frequency of a state to determine an occurrence type that is a type of an occurrence of a state and employs the occurrence type to search the state identification information storage unit and find state identification information. Furthermore the analysis results output unit outputs the state identification information.

With this arrangement the trend in the occurrence of an operating state can be clearly categorized and the state can be easily identified.

According to an twenty second aspect of the present invention in addition to the data collection system of the twentieth or twenty first aspect the occurrence type is either a long and frequent occurrence type a short and frequent occurrence type a long and sporadic occurrence type or a short and sporadic occurrence type .

According to a twenty third aspect of the present invention in addition to the data collection system of the second aspect the analysis unit includes 

an operating data statistical processor for calculating OFF durations and frequencies of individual states indicated by state information for the equipment. Further the analysis results output unit employs the OFF durations and frequencies of the states obtained by the operating data statistical processor to output OFF histograms that represent OFF frequencies of the states.

According to the data collection system of this invention operating data concerning existing production facilities can be collected without greatly affecting the production facilities.

A data collection system and other systems according to the preferred embodiments of the present invention will now be described while referring to the accompanying drawings. In the following embodiments since components denoted by the same reference numerals have the same functions explanations given for such components may not be repeated.

The equipments are those for producing electric apparatuses machines or other products and parts and the goods produced are not especially limited.

The programmable controllers are special controllers computers that turn output devices on or off in accordance with command signals e.g. ON OFF signals received from input devices and perform sequence control. In this embodiment the programmable controllers receive contact information concerning the operation of the equipments and transmit the information to the output apparatuses to control the these apparatuses . Further the programmable controllers include controllers and computers such as a programmable controller PC a sequence controller and a programmable logic controller PLC for performing monitoring sequences for the equipments . The contact information indicates for example the ON OFF state of a buzzer the light ON OFF state or the blinking state for a red yellow or green signal light such as an LED or a fluorescent lamp or the quantity of products produced by a equipment . The data structure of the contact information is not specifically designated.

The data collection systems are systems that obtain contact information concerning the operation of the equipments . The contact information is acquired from one or more contacts and information at individual contacts consisting of contact information is ON or OFF pulse information. The data collection systems are respectively located between the equipments and the output apparatuses that output contact information for the operation of corresponding equipments . Here between does not mean a spatial gap but represents a situation wherein at least one apparatus in this embodiment a divergence apparatus that will be described later of a data collection apparatus receives a signal from a equipment and transmits it to an output apparatus . For this transmission the received signal may be transferred either unchanged or after having been processed. Furthermore the data collection systems receive contact information from the programmable controllers . It should be noted that the data collection systems may also receive contact information directly from the equipments and in such a case the programmable controllers would not be required.

The output apparatuses output contact information by using for example a signal light such as an LED or generating buzzer sounds. The form of the output apparatus for outputting the contact information is not especially limited. The output in this case is a concept that includes transmission to another apparatus such as an apparatus having display means and storage on a recording medium.

Each data collection system includes one or more divergence apparatuses one or more network apparatuses a data collection apparatus and an analysis apparatus . In the data collection system the divergence apparatus and the network apparatus are provided as a set and the data collection system generally includes two or more sets of divergence apparatuses and network apparatuses one data collection apparatus and one analysis apparatus .

The divergence apparatuses obtain contact information concerning the operation of the equipment transmit the contact information to the output apparatuses and also to the network apparatuses . In this embodiment based on the contact information the divergence apparatuses obtain state information concerning the states of the equipments transform the state information into code and transmit the coded contact associated information to the network apparatuses Normally the divergence apparatuses transfer contact information to the output apparatuses unchanged however may process the contact information to change the data structure and transmit the resultant information to the output apparatuses . Preferably contact associated information includes time information concerning time. This time information indicates the time at which a state indicated by state information corresponding to the time information has occurred.

Further it is preferable that contact associated information include a equipment ID which is information for identifying a equipment that is a source for the generation of contact information.

The network apparatuses receive contact associated information from the divergence apparatuses and transmit this information to the data collection apparatus The same data structure need not be employed for received contact associated information and contact associated information to be transmitted.

The data collection apparatus receives the contact associated information from the network apparatuses and stores it.

The analysis apparatus obtains contact associated information stored in the data collection apparatus and analyzes the information.

The state coding unit includes a coding map storage unit and a contact associated information acquisition unit .

The contact information acquisition unit obtains contact information from the equipment directly or indirectly for example via programmable controller . In this embodiment the contact information acquisition unit obtains through the programmable controller contact information concerning the equipment . The contact information acquisition unit may receive contact information from the programmable controller or read contact information stored in the reequipment i.e. the contact information acquisition method employed by the contact information acquisition unit is not specifically designated. The contact information acquisition unit separates a transfer line for contact information received from the programmable controller into two branches one branch is to the output unit so as to output the contact information directly to the output apparatus and the other branch is to the state recognition so as to perform state recognition. The contact information acquisition unit can be for example an MPU or a memory or may be a wireless or a wired reception unit. The processing performed by the contact information acquisition unit is generally provided by software that is recorded on a recording medium such as a ROM but may also be provided by hardware a special circuit .

The state recognition unit obtains state information concerning the state of the equipment based on the contact information acquired by the contact information acquisition unit . The state of the equipment includes one of the two states for a buzzer either ON or OFF and one of the three states for three types of signal lights e.g. red yellow and green lamps that are lighted off or blinking. This state can be regarded as a pair of states for a plurality of media such as a buzzer and a signal light. There are ten state patterns that are paired for all states and a specific state example will be described later. The state information is information concerning the state of the equipment that is to be obtained based on the contact information that the contact information acquisition unit has obtained. In this embodiment the state information includes asynchronous information that is generated asynchronously with the change in the state of a buzzer and a signal light change. The asynchronous information is production count information concerning the production count for the equipment e.g. information concerning the exchange of dies installed in the equipment information concerning the exchange of a resin employed by the equipment re insertion information used when a product that was inspected as defective and was corrected is to be inserted or setup change information used when a setup change is performed. Normally the state recognition unit is for example an MPU or a memory and the processing performed by the state recognition unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

The state coding unit transforms state information obtained by the state recognition unit into contact associated information which is coded information. When state information obtained by the state recognition unit includes asynchronous information the state coding unit transforms contact associated information which is code having a predetermined value regardless of the state information other than the asynchronous information. The state coding unit employs only asynchronous information and omits the other state information to prepare contact associated information which is coded information. In this case the analysis apparatus regards the state information other than the asynchronous information as being unchanged from the previous state. An explanation will be specifically given later for a method whereby the state coding unit transforms state information into contact associated information. Normally the state coding unit is for example an MPU or a memory and the processing performed by the state coding unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

The coding map storage unit is used to store a coding map which is information indicating a correlation between state information that indicates the ON OFF states of n n is an integer of two or greater types and contact associated information which is code consisting of n 1 bits or fewer. The data structure of the coding map is not especially limited so long as the state information and the contact associated information can be correlated with each other. The state information is an ON OFF pattern for n types of information i.e. an ON OFF pattern for five types of information information indicating that production of a predetermined number of products has been completed the ON OFF state of a buzzer the ON OFF state of a red LED the ON OFF state of a yellow LED and the ON OFF state of a green LED. The contact associated information is information consisting of four bits. The coding map storage unit is preferably a nonvolatile storage medium such as a hard disk or a ROM however a volatile recording medium such as a RAM may be used.

The contact associated information acquisition unit obtains from the coding map storage unit contact associated information that corresponds to one or more sets of state information the state recognition unit has obtained. The contact associated information acquisition unit may search an externally available coding map using state information as a key and obtain contact associated information. In this case the divergence apparatus does not include a coding map storage unit . Normally the contact associated information acquisition unit is for example an MPU or a memory and the processing performed by the contact associated information acquisition unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

The output unit transmits to the output apparatus contact information obtained by the contact information acquisition unit and transmits to the network apparatus contact associated information concerning the contact information that is obtained by the state coding unit through transform. Generally the output unit is provided as a wireless or a wired communication unit or broadcasting unit.

The coding map setting unit stores a coding map in the coding map storage unit . The coding map setting unit receives a coding map entered using an input unit such as a keyboard or a mouse and stores the coding map in the coding map storage unit . An input unit such as a keyboard or a mouse may be included in the coding map setting unit .

The network apparatus includes a first contact associated information receiver and a second contact associated information transmitter .

The first contact associated information receiver receives contact associated information from the divergence apparatus . A wireless communication unit is appropriate for the first contact associated information receiver however a broadcasting reception unit or a wired communication unit may also be employed.

The first contact associated information transmitter transmits to the data collection apparatus contact associated information received by the contact associated information receiver . Generally the first contact associated information transmitter is provided by a wireless or a wired communication unit however a broadcasting unit may also be employed. The same data structure is employed for the contact associated information received by the first contact associated information receiver and the contact associated information to be transmitted by the first contact associated information transmitter . However the network apparatus may change a data structure.

The operating data storage unit is used to store contact associated information. A nonvolatile recording medium such as a hard disk is appropriate for the operating data storage unit however a volatile recording medium such as a RAM can also be employed.

The second contact associated information receiver receives contact associated information from the network apparatus . Generally the second contact associated information receiver can be provided by a wireless or a wired communication unit and may also be provided by a broadcast reception unit.

The operating data log accumulation unit stores in the operating data storage unit contact associated information received by the second contact associated information receiver . Normally the operating data log accumulation unit is for example an MPU or a memory and the processing performed by the operating data log accumulation unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

The analysis unit includes a coding map storage unit a state decoder a operator moving time information acquisition unit and a restoration time information acquisition unit .

The analysis results output unit includes a moving time histogram output unit and a restoration time histogram output unit .

The command acceptance unit accepts a command to start an analysis process. Arbitrary command input means can be employed such as a ten key pad a keyboard a mouse or a menu screen and the command acceptance unit can be provided by a device driver for an input device such as a ten key pad or a keyboard or control software for a screen menu. The analysis apparatus may start the analysis process by employing as a trigger an event that the command acceptance unit has accepted as a start command for the analysis process or may automatically start the analysis process when a predetermined time is reached.

The contact associated information acquisition unit obtains one or more sets of contact associated information hereinafter referred to as operating data logs from the operating data storage unit . Although a trigger or a timing at which the contact associated information acquisition unit obtains contact associated information is not especially limited generally when the command acceptance unit has received an command from a user the contact associated information acquisition unit obtains contact associated information. Further the contact associated information acquisition unit obtains via a communication an operating data log from the data collection apparatus . Normally the contact associated information acquisition unit is provided by a wireless or a wired communication unit however it may also be provided by a broadcast reception unit.

The correction unit corrects time information included in contact associated information based on a period that the state recognition unit requires for the acquisition of state information. In this case the correction unit stores in advance a period that the state recognition unit requires for the acquisition of state information. Further for the correction of time information the correction unit may employ a period that the state recognition unit requires for the acquisition of state information that has been transmitted by the divergence apparatus and is stored in the data collection apparatus . By delaying the execution time by a value equivalent to the period that the state recognition unit requires for the acquisition of the state information the correction unit can correct the time at which an abnormality occurred in the equipment a time at which a operator pressed a buzzer stop button a time at which the restoration job was started or a time at which the job was ended. Since the correction unit performs a time correction an accurate time can be obtained when the operator transit information and the restoration time information include time information. Normally the correction unit is for example an MPU or a memory and the processing performed by the correction unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit . Further correction unit may correct one or more sets of state information obtained by the state decoder .

The analysis unit processes one or more sets of contact associated information obtained by the contact associated information acquisition unit and obtains predetermined information. Specifically based on two or more sets of contact associated information operating data logs the analysis unit obtains operator moving time information which is information concerning the movement time for a operator and restoration time information which is information concerning a period required for a restoration job. A specific example for the processing performed by the analysis unit will be described later. Normally the analysis unit is for example an MPU or a memory and the processing performed by the analysis unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

The state decoder obtains from the coding map storage unit one or more sets of state information which are correlated with one or more sets of contact associated information obtained by the contact associated information acquisition unit . Normally the state decoder is for example an MPU or a memory and the processing performed by the state decoder is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

Based on one or more sets of state information obtained by the state decoder the operator moving time information acquisition unit obtains information concerning a period extending from the time a buzzer is turned on until it is switched off and defines the obtained information as operator moving time information. Normally the operator moving time information acquisition unit is for example an MPU or a memory and the processing performed by the operator moving time information acquisition unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

Based on two or more sets of contact associated information acquired by the restoration time information acquisition unit information is obtained concerning the period required for the reequipment to resume normal operation after the buzzer was switched from on to off and defines the obtained information as restoration time information. Generally a operator in charge of a restoration job switches a buzzer from on to off and an operating unit e.g. a button or a switch for turning the buzzer off is usually included in the equipment or is positioned somewhere around the periphery of the equipment . When the operator in charge manipulates the operating unit to turn off the buzzer the programmable controller for example detects the manipulation of the operating unit to turn off the buzzer and transmits a notification of this event to the divergence apparatus . Normally the restoration time information acquisition unit is for example an MPU or a memory and the processing performed by the restoration time information acquisition unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

The analysis results output unit outputs predetermined information that includes analysis results obtained by the analysis unit . Here output is a concept that includes presentation of data on a display unit printing of data performed by a printer transmission of data to an external apparatus and storage of data on a recording medium. Specifically in this embodiment the analysis results output unit outputs the operating state of the equipment using a graph a specific example will be described later or outputs histograms for a moving time and a restoration time. Further the analysis results output unit may or may not include an output device such as a display device. Driver software for an output device or driver software for an output device and an output device may be employed to provide the analysis results output unit .

Based on the operator moving time information obtained by the operator moving time information acquisition unit the moving time histogram output unit prepares and outputs a histogram that employs as two axes a moving time for a operator indicated by the operator moving time information and a frequency at which movement during the moving time occurred and or a total time for one or more movement occurrences during the moving time.

Based on the restoration time information obtained by the restoration time information acquisition unit the restoration time histogram output unit prepares and outputs a histogram that employs as two axes a restoration time indicated by the restoration time information and a frequency at which a restoration requiring the restoration time occurred and or a total time for one or more restorations that required the restoration time.

The histogram output process is a well known process and an example output histogram will be explained later.

The operation of the data collection system will now be described. First the operation of the divergence apparatus will be explained while referring to the flowchart in .

 step S The contact information acquisition unit determines whether the i th contact is present. It should be noted that a contact is a medium that outputs a signal for the operating state of the equipment . In this flowchart assume that n n is an integer of two or greater types of contacts are present.

In this flowchart assume that n n is an integer of two or greater types of contacts are present. When the i th contact is present program control advances to step S or when the i th contact is not present program control is shifted to step S.

 step S The contact information acquisition unit determines whether the contact information for the i th contact has been obtained. When contact information for the i th contact has been obtained program control advances to step S. When contact information for the i th contact has not been obtained program control returns to step S.

 step S The contact information acquisition unit transmits to the output unit the contact information obtained at step S.

 step S The contact information acquisition unit transmits to the state recognition unit the contact information obtained at step S.

 step S Based on one or more sets of contact information accepted at step S the state recognition unit identifies the state and obtains state information. In this case for the acquisition of state information the state recognition unit employs one or more sets of state information obtained during a predetermined period of time. The state recognition process performed by the state recognition unit will be described later while referring to the flowchart in .

 step S The contact associated information acquisition unit determines whether the state information has been output at step S. When the state information has been output at step S program control advances to step S. When the state information has not been not output at step S the process at step S is repeated.

 step S The contact associated information acquisition unit searches the coding map storage unit by employing one or more sets of state information as a key and obtains state code contact associated information that is paired with one or more sets of state information. When the state information includes asynchronous information the state code obtained by the contact associated information acquisition unit is code such that state information other than the asynchronous information can not be identified. An example of this state code will be explained later.

 step S The output unit transmits to the network apparatus the state code obtained at step S. It should be noted that the appropriate data size of the state code is equal to or smaller than n 1 bits.

 step S The output unit outputs to the output apparatus contact information for n types of contacts obtained by the contact information acquisition unit . Upon receiving the contact information the output apparatus outputs displays the received information unchanged. Thereafter program control returns to step S.

In the flowchart in the contact information acquisition unit may obtain information for n contacts by performing parallel processing.

The state recognition process performed by the divergence apparatus will now be described while referring to the flowchart in .

 step S The state recognition unit determines whether the state indicated by contact information is the ON state. When the state is the ON state program control advances to step S. When the state is not the ON state program control is shifted to step S.

 step S The state recognition unit determines whether the ON state is continued for at least a predetermined period T. When the ON state is continued program control advances to step S. When the ON state is not continued program control is shifted to step S.

 step S The state recognition unit identifies the state as a light on state or as a buzzer ON state and prepares state information corresponding to this state.

 step S The state recognition unit outputs the prepared state information and program control returns to a higher function.

 step S The state recognition unit identifies the state as a light off state and prepares state information corresponding to this state. Program control then advances to step S.

 step S The state recognition unit determines whether the OFF state is continued for at least the predetermined period T. When the OFF state is continued program control advances to step S. When the OFF state is not continued program control is shifted to step S.

 step S The state recognition unit identifies the state as a light off state or a buzzer OFF state and prepares state information corresponding to this state. Then program control is shifted to step S.

 step S The state recognition unit identifies the state as a light off state and prepares state information corresponding to this state. Thereafter program control is shifted to step S.

The operation of the network apparatus will now be described. The first contact associated information receiver of the network apparatus receives contact associated information from the divergence apparatus while the first contact associated information transmitter transmits the contact associated information to the data collection apparatus .

Next the operation of the data collection apparatus will be explained. The second contact associated information receiver of the data collection apparatus receives contact associated information from the network apparatus and the operating data log accumulation unit stores the contact associated information in the operating data storage unit . Upon receiving a request from the analysis apparatus the data collection apparatus transmits to the analysis apparatus a movement information log that includes one or more sets of contact associated information. The analysis apparatus does not need to obtain a movement information log directly from the data collection apparatus . The analysis apparatus may read a movement information log from a recording medium on which movement information logs are stored and perform an analysis process.

 step S The command acceptance unit determines whether an command to start an analysis process has been accepted. When an command for the start of an analysis process has been accepted program control advances to step S. When an command for the start of an analysis process has not yet been accepted program control returns to step S. The command includes for example information for a time period for an analysis target may also include information for a date or may be simply a start command. In this case the analysis apparatus employs as an analysis target all contact associated information for the data collection apparatus .

 step S The contact associated information acquisition unit obtains from the operating data storage unit of the data collection apparatus an operating data log for a target designated at step S.

 step S The correction unit obtains a period t which has been stored in advance that the state recognition unit requires for the acquisition of state information.

 step S The correction unit employs the period t obtained at step S to correct time information that is included in all contact associated information entered in the operating data log acquired at step S. That is the correction unit delays by the period t the time indicated by time information included in all the contact associated information entered in the operating data log. For example when time information included in the contact associated information indicates T the correction information regards T t as accurate time information.

 step S The analysis unit processes one or more sets of contact associated information obtained by the contact associated information acquisition unit and obtains predetermined information operator moving time and restoration time information . It should be noted that the contact associated information in this case is the information corrected by the correction unit . The analysis process performed by the analysis unit will be described later in detail while referring to the flowchart in .

 step S Based on operator moving time information the analysis results at step S obtained by the operator moving time information acquisition unit the moving time histogram output unit prepares a histogram that employs as two axes operator moving time indicated by the operator moving time information and a frequency at which movement during the moving time occurred and or a total time for one or more movements during the moving time.

 step S Based on the restoration time information the analysis results at step S obtained by the restoration time information acquisition unit the restoration time histogram output unit employs as two axes a restoration time indicated by the restoration time information and a frequency at which a restoration requiring the restoration time occurred and or a total time for one or more restorations requiring the restoration time.

 step S The restoration time histogram output unit outputs the histogram prepared at step S. The processing is thereafter terminated.

 step S The analysis unit determines whether the i th contact associated information is present in contact associated information obtained by the contact associated information acquisition unit . When the i th contact associated information is present program control advances to step S. When the i th contact associated information is not present program control returns to a higher function.

 step S The state decoder obtains from the coding map storage unit state information corresponding to the i th contact associated information.

 step S The operator moving time information acquisition unit determines whether state information obtained at step S indicates that an abnormality signal light is ON and a buzzer is ON . When the abnormality signal light is ON and the buzzer is ON program control advances to step S or when neither the abnormality signal light nor the buzzer is ON program control advances to step S.

 step S The operator moving time information acquisition unit substitutes 1 into a moving time variable m which is a variable for measuring moving time.

 step S The operator moving time information acquisition unit substitutes i 1 into a counter value j.

 step S The analysis unit determines whether the j th contact associated information is present. When the j th contact associated information is present program control advances to step S or when the j th contact associated information is not present program control returns to a higher function.

 step S The state decoder obtains from the coding map storage unit state information corresponding to the j th contact associated information.

 step S The operator moving time information acquisition unit determines whether the state information obtained at step S indicates that the abnormality signal light is ON and the buzzer is ON . When the abnormality signal light is ON and the buzzer is ON program control advances to step S or when neither the abnormality signal light nor the buzzer is ON program control is shifted to step S.

 step S The operator moving time information acquisition unit increments the counter value j by one. Program control thereafter returns to step S.

 step S The analysis unit increments the counter value i by one. Program control then returns to step S.

 step S The operator moving time information acquisition unit determines whether the obtained state information indicates that the abnormality signal light is ON and the buzzer is OFF . When the abnormality signal light is ON and the buzzer is OFF program control advances to step S. When the abnormality signal light is not ON and the buzzer is not OFF program control is shifted to step S.

 step S The operator moving time information acquisition unit calculates moving time based on the moving time variable m. Since m is proportional to the number of contact information sets that are output in a period during which a operator is moving generally the operator moving time information acquisition unit defines m time interval at which contact information is output as moving time.

 step S The restoration time information acquisition unit substitutes 1 into a restoration time variable r which is a variable for measuring a restoration time. Program control thereafter advances to step S.

 step S The analysis unit substitutes j 1 into the counter value i. Program control thereafter returns to step S.

 step S The restoration time information acquisition unit increments the counter value j by one. Program control thereafter advances to step S.

 step S The restoration time information acquisition unit determines whether the j th contact associated information is present. When the j th contact associated information is present program control advances to step S or when the j th contact associated information is not present program control returns to a higher function.

 step S The state decoder obtains from the coding map storage unit state information corresponding to the j th contact associated information.

 step S The restoration time information acquisition unit determines whether the obtained state information indicates that the abnormality signal light is ON and the buzzer is OFF . When the abnormality signal light is ON and the buzzer is OFF program control advances to step S. When the abnormality signal light is not ON and the buzzer is not OFF program control is shifted to step S.

 step S The restoration time information acquisition unit increments the restoration time variable r by one.

 step S The restoration time information acquisition unit increments the counter value j by one. Then program control returns to step S.

 step S The restoration time information acquisition unit determines whether the obtained state information indicates the abnormality signal light is OFF . When the abnormality signal light is OFF program control advances to step S or when the abnormality signal light is not OFF program control is shifted to step S.

 step S The restoration time information acquisition unit calculates a restoration time based on the restoration time variable r. Since r is proportional to the number of contact information sets that are output in a period during which a operator is performing a restoration job generally the restoration time information acquisition unit regards r time interval at which contact information is output as a restoration time.

 step S The analysis unit prepares analysis results information. The analysis results information includes for example time information indicating time of the occurrence of an abnormality moving time and a period required for a restoration job. Time information for the abnormality is held in contact associated information.

 step S The analysis unit substitutes j 1 into the counter value i. Program control thereafter returns to step S.

An explanation will now be given for specific operations performed by the production system of this embodiment and the data collection system that constitutes this production system. The basic configuration for the production system including the data collection system is shown in .

Assume that a programmable computer the programmable controller installed in the equipment outputs the following patterns as the contact is changed to the ON OFF state.

Three types of signal lights i.e. red yellow and green lamps are present. Each of the red yellow and green signal lights has three states light on blinking and light off.

The programmable controller outputs production count information concerning a production count. Specifically each time a finished work e.g. a product has passed along the production line the equipment a pulse signal is transmitted to the programmable controller . For each 100 pulses received the programmable controller outputs a pulse. This pulse is asynchronous information that is generated asynchronously.

Further the individual patterns maybe parallel for information indicating five states i.e. the states of the three signal lights and the buzzer and the production count information. The parallel patterns are specifically red off yellow blinking green on and buzzer ON patterns.

In the data collection system of the production system of this embodiment the divergence apparatus changes these patterns into bit codes and the data collection apparatus stores the bit codes. The analysis apparatus decodes state code stored in the data collection apparatus and transforms the state information into for example a graph display format so that a operator can visually understand the time and the period within which each pattern occurred.

The state information indicates the states of five types of contacts. In the following values can be provided for the attribute values of state information. Production quantity is information indicating that 100 works from the programmable controller were passed along one production line equipment . When there is no entry in the production count column it is assumed that 100 works have not yet passed along one production line equipment . Buzzer indicates that the buzzer is in the ON state and X indicates that the buzzer is in the OFF state. Red yellow and green represent the colors of the signal lights and for the individual signal lights indicates light on indicates blinking and X indicates light off . The divergence apparatus correlates for example with 0 with 1 and X with 2 . In the contact associated information is provided by four bits of code for which the bit values 0 or 1 individually indicate state state state and state .

First the divergence apparatus of the data collection system branches the path for a signal output by the programmable controller to the output apparatus and to the network apparatus . That is the divergence apparatus outputs this output signal directly to the output unit while the divergence apparatus recognizes the pattern of the output signal contact information and outputs to the network apparatus state code contact associated information that matches the pattern. Among these processes the process for preparing contact associated information based on contact information will now be specifically explained.

Based on contact information obtained by the contact information acquisition unit the state recognition unit identifies a state and obtains state information. Specifically the state recognition unit identifies patterns for the signal lights the buzzer and the production count.

The state recognition unit performs pattern recognition for the signal lights in the following manner. When for example one second contact information indicates the ON state or the OFF state the state recognition unit determines that the signal light is on or the signal light is off. When one second contact information indicates either the light on pattern or the light off pattern the state recognition unit determines that the warning light is blinking.

Further when the buzzer contact is turned on the state recognition unit identifies the ON state or when the buzzer contact is turned off identifies the OFF state.

In this embodiment when one work is passed along a production line a pulse signal is transmitted to the programmable controller and the state recognition unit determines that a counter has counted 100 pulses.

Following this the contact associated information acquisition unit obtains from the coding map storage unit contact associated information that is correlated with state information that has been identified and obtained by the state recognition unit . In this embodiment state information is information for five channels and when this state information is coded by the contact associated information acquisition unit four bits of data are obtained. Therefore by performing pattern recognition for state information the amount of state information stored is reduced compared with the amount of information that is directly branched and stored as operating data logs. Further the network traffic is also reduced.

The state recognition unit outputs a one second pulse hereinafter referred to as a count up pulse as needed as a signal indicating that 100 pulses have been reached relative to the production count. The count up pulse is to be very rarely output while taking into account the pattern changes for the signal lights and buzzer and also to be generated asynchronously with these changes. By considering this property it is assumed that the code for the count up pulse is independent of the codes for the signal lights and the buzzer. That is when the count up pulse is generated the code 1111 in is to be written to the operating data log by an interrupt. As shown in the independent code 1111 in is provided for the production count count up pulse and when the state information indicates the ON state the state recognition unit overwrites and outputs the code. Then so long as the production count count up pulse is being output the analysis apparatus regards the state as having been continued. That is when contact associated information is 1111 the analysis apparatus employs the preceding or succeeding contact associated information to obtain the states of the three signal lights red yellow and green and the state of the buzzer. Through this process the number of contact channels required for data collection can be reduced. Further network traffic can be reduced.

The contact associated information acquisition unit codes the contact information. The advantage of obtaining bit code for the contact information is as follows. When a pattern is to be identified without bit coding five channels for contacts red yellow green a buzzer and a production count are required for pattern recognition. However when bit coding is employed for contact information all the patterns ten in this embodiment can be represented by four bits i.e. four channels so that the number of channels is reduced to represent patterns.

Further since an independent code is allocated for information such as a count up pulse it is very rarely generated and log description can be performed by an interrupt. Thus the number of channels is not unnecessarily increased.

After the state information has been coded by the contact associated information acquisition unit the output unit outputs the obtained state code to the network apparatus .

Generally the output unit outputs to the output apparatus contact information for n types of contacts obtained by the contact information acquisition unit without being especially processed. Since the output process performed by the output apparatus is a well known process no detailed explanation for it will be given.

Sequentially the network apparatus receives coded contact associated information also called state code as needed from the divergence apparatus and transmits this information to the data collection apparatus .

The data collection apparatus receives contact associated information from the network apparatus and stores the received contact associated information in the operating data storage unit . Information stored in the operating data storage unit is an operating data log consisting of one or more sets of contact associated information. Generally the contact associated information includes time information the date and time information shown in .

Through the above processing a large amount of contact associated information shown in is accumulated in the data collection apparatus .

Assume that the command acceptance unit of the analysis apparatus accepts an analysis start command from a user.

Then the contact associated information acquisition unit obtains an operating data log having the data structure shown in from the operating data storage unit of the data collection apparatus .

The correction unit obtains a period t one second in this embodiment which is stored in advance that the state recognition unit requires for the acquisition of state information.

Sequentially the correction unit employs the obtained period t one second to correct a time that is included in all the contact associated information for the obtained operating data log.

A time correction process performed by the correction unit will now be described while referring to . Assume that the state indicated by contact associated information is the state of a signal light shown in . While referring to the signal light at time T is blinking however in order to obtain the blinking state at T T t the correction unit changes time information included in the contact associated information from T to T. Through this process the analysis apparatus can perform an analysis process based on the state at the exact time while taking into account the period t that the state recognition unit requires for the acquisition of state information.

Specifically for example as shown in through time correction performed by the correction unit contact associated information before correction is changed to contact associated information after correction. Using this correction process the time at which the pattern was changed can be accurately obtained.

Next the analysis unit performs the analysis process in the following manner and obtains operator moving time information and restoration time information based on one or more sets of contact associated information.

The state decoder of the analysis unit decodes the contact associated information to state information. As a result the analysis unit can obtain information with which a timing chart in can be prepared.

Following this moving time and a restoration time are calculated based on the ON OFF states of an abnormality signal light and a buzzer operator paging buzzer . The operator moving time information acquisition unit and the restoration time information acquisition unit may calculate moving time and a restoration time by employing as a trigger the depression of a buzzer halt button instead of employing the state of the buzzer.

Specifically assume that a table in is obtained by decoding and patterning the operating data log one or more sets of contact associated information . In since red blinking i.e. the lighting start time for an abnormality signal light is 12 52 46 and buzzer the stop time is 12 53 01 the operator moving time information acquisition unit calculates moving time buzzer stop time lighting start time for the abnormality signal light 15 s . In this case red blinking indicates an abnormal halt and green lighting indicates the normal operating state see state definition information in .

The restoration time information acquisition unit calculates a restoration time resume time buzzer stop time 12 m 4 s . It should be noted that in the resume time is 13 05 05 .

The results obtained by the operator moving time information acquisition unit and the restoration time information acquisition unit are at least temporarily stored by using an analysis results management table shown in . The analysis results management table in includes at least one record consisting of time information indicating an abnormality start time moving time and a restoration time.

Next based on the operator moving time information analysis results in obtained by the operator moving time information acquisition unit the moving time histogram output unit prepares and outputs a histogram that employs as two axes the moving time for a operator indicated by the operator moving time information and a frequency at which a movement in the moving time occurred and or a total time for one or more movements during the moving time.

Furthermore based on the restoration time information analysis results in obtained by the restoration time information acquisition unit the restoration time histogram output unit prepares and outputs a histogram that employs as two axes a restoration time indicated by the restoration time information and a frequency at which a restoration requiring the restoration time occurred and or a total time for one or more restorations that required restoration times.

Also restoration time histograms are shown in . While referring to since the median for the restoration time is smaller than a threshold value it can be determined that a countermeasure for a short time halt is required. A short time halt is a short equipment stop event such as clogged conveying line from which the equipment can be restored by performing a comparatively easy process. While referring to since the median for the restoration time is greater than the threshold value it can be determined that a countermeasure for a trouble halt is required. A trouble halt is a comparatively long equipment stop event that occurs in the case wherein a practical countermeasure not yet been commonly employed e.g. either operators other than those having special skills can not handle the fault or to determine the required corrective action a manual or manuals must be referred to. The countermeasure for a trouble halt is for example the establishment of procedures for a restoration job. It should be noted that the analysis unit holds in advance information for the threshold value. The analysis unit may determine whether the median is greater or smaller than the threshold value and the analysis results output unit may output information in accordance with the determination results.

The moving time histogram output unit and the restoration time histogram output unit specifically perform the following processing and output the histograms shown in .

Based on records acquired in the past the moving time histogram output unit divides the moving time in accordance with suitable levels to form the horizontal axis. The moving time histogram output unit provides for the vertical axis the frequency the number of times for the moving time at each level or the total number of time periods. As a result it can be ascertained at a glance which moving time adversely affected a period of time halted. When the frequency of short moving times is high this is not especially a problem because it is assumed that when a equipment halt occurs a operator can immediately respond and cope with the problem. On the other hand when the frequency of long moving times is high it is assumed that when a equipment halt occurs it takes time for a operator to arrive at the site and a problem in the distribution of operators exists. Thus it is ascertained that the operator distribution planning should be reviewed.

Based on records acquired in the past the restoration time histogram output unit divides the restoration time in accordance with suitable levels to form the horizontal axis. The restoration time histogram output unit provides for the vertical axis the frequency the number of times at which restoration times were required at each level or the total time. As a result it can be ascertained at a glance which restoration time adversely affected conditions during a halt period. When the frequency of short restoration times is high it is assumed that short time halts occurred frequently and determination of the reasons and the countermeasures required for short time halts are required. On the other hand when the frequency of long restoration times is high it is assumed that trouble halts have occurred frequently and determination of the reasons and the countermeasures required for trouble halts are required.

In this manner halt periods are displayed using histograms for moving times and for restoration times so as to provide for support for the determination of methods for improving the operating rate for the equipment.

The analysis results output unit may output a graph of the operating information shown in . In this case the analysis apparatus should also hold the state definition information shown in . Then state definition information e.g. power off data correlated with state information is output using a timing chart. Since the process for outputting the timing chart is well known no detailed explanation for this will be given. It should be noted that the definition for the timing chart is the same as that for a time chart.

According to this embodiment information concerning the operation of a equipment can be easily obtained without having to reconstruct a equipment such as a equipment or having to greatly change a sequence program such as a programmable controller mounted in the equipment. The data collection system of this embodiment is extremely effective especially when introduced into a large production system such as a plant.

Further according to this embodiment when the analysis apparatus analyzes an operating data log corrective measures to be taken such as the need to increase the number of operators or the need to establish procedures for restoration jobs can be adopted.

Furthermore according to this embodiment data to be transmitted to the network apparatus is coded and network traffic can be reduced. Additionally only a small amount of data is required for the storage of operating data logs.

Moreover according to the embodiment when state information includes asynchronous information that is generated asynchronously with a change in the state of a buzzer and changes in the states of signal lights regardless of whether state information other than the asynchronous information is obtained the information can be transformed into contact associated information which is code having a predetermined value. Therefore the network traffic can be reduced even more.

Further according to this embodiment information operator moving times and restoration times concerning the operation of a equipment can be easily obtained without changing related art procedures for the tasks assigned a operator at a job site e.g. performance of a duty such that when an abnormality occurs at a equipment a operator can move to the equipment and press a buzzer stop button . Thus countermeasures to be taken at a production site can be easily performed.

Furthermore since moving times are displayed using histograms it can readily be ascertained whether long moving times or short moving times occurred more frequently when a equipment was halted. And when long moving times were most frequent it can be assumed that the planning for the disposition of operators should be reviewed. Further since the restoration time is displayed using histograms it can be ascertained whether long restoration times or short restoration times occurred most frequently when the equipment was halted. When long restoration times were most frequent it can be assumed that trouble halts occurred most frequently and that appropriate countermeasures for trouble halts are required. And when short restoration times were not frequent it can be assumed that short time halts occurred most frequently and that appropriate countermeasures for short time halts are required. Since the histograms are displayed in this manner the process for determining what measures to take for a equipment can be supported.

Since the analysis apparatus includes the correction unit for correcting time the exact time at which the state of a equipment is changed e.g. the occurrence of a fault restoration can be obtained and as a result the cause for a fault for example can be easily determined.

In this embodiment the coding map is not limited to the map shown in and a map shown in or may be employed. In or means don t care i.e. can be either 0 or 1 .

When the coding map in is employed for attribute value no work for a preprocess work full for post process state information indicates that a yellow signal light is ON and a green signal light is blinking see the seventh record in . For work full for post process state information indicates the green signal light is blinking see the third record in . For no work for preprocess state information indicates that the yellow signal light is ON and the green signal light is also ON see the fifth record in . And while referring to the operating state no work for preprocess work full for post process which is generated at the same time is sorted. In other words in the coding map in three types of state information can be represented by contact associated information provide using two bits state and state in . Further according to the coding map in contact associated information for state information that indicates two or more states no work for preprocess and work full for post process in this case is regarded as the sum 110 of correlated contact associated information sets 100 and 010 . That is don t care is regarded as not affecting addition. This is because at a production site many states for a equipment must be transmitted by using a small number of signal lights hardware . On the other hand in a production management department it is preferable that operating states generated at the same time be separated and that three states no works for a preprocess work full for post process and no works for a preprocess work full for post process must be determined based on two output waveforms instead of three. That is as shown in a waveform for no works for a preprocess work full for post process shown at the bottom in is put together with no works for a preprocess and work full for post process . As a result the production management department can ascertain the state of a equipment at a glance. And when a different coding map is employed the same processes can be employed for example for the state code unit the coding map setting unit the contact associated information acquisition unit the analysis unit and the state decoder .

It should be noted that a circular portion and elliptical portions indicated by broken lines should be referred to for the above described processing.

The functions of the individual apparatuses in this embodiment may be provided using software. This software may be distributed by being downloaded or by being recorded on a recording medium such as a CD ROM. This can be applied for another embodiment for this invention. The software that provides the divergence apparatus in this embodiment is the following program. The program permits a computer to perform 

an output step of transmitting to the output apparatus contact information obtained at the contact information acquisition step and transmitting to the network apparatus contact associated information which is information concerning the contact information.

a state recognition step of employing contact information acquired at the contact information acquisition step to obtain state information which is information concerning a state of the equipment and

a state coding step of transforming the state information obtained by the state recognition unit into coded contact associated information and

whereby at the output step the contact information obtained at the contact information acquisition step is transmitted to the output apparatus and the contact associated information obtained through a transform performed at the state coding step is transmitted to the network apparatus.

a coding map storage unit a coding map is stored that represents a correlation between state information which indicates state patterns for n contacts n is an integer of two or greater and contact associated information which is code in n 1 bits or smaller. And the state coding step includes 

a contact associated information acquisition step of obtaining from the coding map contact associated information that is correlated with state information obtained at the state recognition step.

Further preferably for the program the contact outputs the state of a buzzer that is to be set either to the ON or to the OFF state or the state of a signal light that is to be turned on or off or to blink. The state information includes asynchronous information that is generated asynchronously with a change in the state of the buzzer and a change in the state of the signal light. When state information obtained at the state recognition step includes asynchronous information at the state coding step the state information is transformed into contact associated information which is code having a predetermined value regardless of whether information other than the asynchronous information is included in the state information obtained at the state recognition step.

Further the software used to provide the analysis apparatus of this embodiment is the following program. The program permits a computer to perform 

a contact associated information acquisition step of reading one or more sets of contact associated information from a data collection apparatus 

an analysis step of processing the one or more sets of contact associated information read at the contact associated information acquisition step and obtaining predetermined information and

an analysis results output step of outputting the predetermined information obtained at the analysis.

Further for the program at the analysis step two or more sets of contact associated information may be employed to obtain operator moving time information which concerns moving time for a operator and restoration time information which concerns a restoration time.

a operator moving time information acquisition step of obtaining based on two or more sets of contact associated information information concerning a period extending from the start of the ON state of a buzzer to the OFF state and defining the information as operator moving time information and

a restoration time information acquisition step of employing after the buzzer has been changed from on to off two or more sets of contact associated information to obtain information concerning a period required before the equipment is normal operation and defining the information as restoration time information.

a moving time histogram output step of preparing based on operator moving time information obtained at the operator moving time information acquisition step a histogram that employs as respective axes operator moving time which is represented by the operator moving time information and a frequency at which movement during the pertinent moving time occurred and or a total time for one or more movements during the moving time and outputting the histogram and

a restoration time histogram output step of based on restoration time information obtained at the restoration time information acquisition step preparing a histogram that employs as respective axes a restoration time which is represented by the restoration time information and a frequency of an occurrence of a restoration requiring the restoration time and or a total time for one or more restorations each of which require the restoration time and outputting the histogram.

Moreover for the program the contact associated information includes time information which is time related information. And the program permits the computer to further perform 

a correction step of correcting based on a period that acquisition of state information is required at the state recognition step correcting the operator moving time information and the restoration time information.

According to a second embodiment of this invention an explanation will now be given for an analysis apparatus that performs a statistical process for two or more sets of state information and obtains statistical data to ascertain the operation situation of one or more equipments.

A production system for this embodiment is the same as that for the first embodiment except only for an analysis apparatus. The equipment includes one or more equipments one or more programmable controllers one or more data collection systems and one or more output apparatuses .

The data collection system includes one or more divergence apparatuses one or more network apparatuses a data collection apparatus and an analysis apparatus .

The analysis apparatus includes an command acceptance unit a contact associated information acquisition unit a correction unit an analysis unit and an analysis results output unit .

The analysis unit includes a coding map storage unit a state decoder a operator moving time information acquisition unit a restoration time information acquisition unit an operating data statistical processor and a category information storage unit .

The analysis results output unit includes a moving time histogram output unit a restoration time histogram output unit and a statistical results output unit .

The analysis unit processes one or more sets of contact associated information obtained by the contact associated information acquisition unit and obtains predetermined information. Specifically based on two or more sets of contact associated information operating data logs the analysis unit obtains operator moving time information which is information concerning the movement time for a operator and restoration time information which is information concerning a period required for a restoration job. Specifically in order for example to ascertain the operating situations for one or more equipments the analysis unit performs the statistical process for one or more sets of contact associated information and obtains statistical data. A specific example for the processing performed by the analysis unit will be described later. Normally the analysis unit is for example an MPU or a memory and the processing performed by the analysis unit is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

The operating data statistical processor performs a statistical process for two or more sets of state information obtained by the state decoder and obtains statistical data to ascertain the operation situation of one or more equipments . The operating data statistical processor calculates for each equipment a total time of the durations of individual states indicated by the state information. That is the operating data statistical processor calculates for each equipment the durations and the frequencies of individual states indicated by state information and based on category information that will be described later divides the obtained durations and frequencies of the states into categories groups indicated by the category information.

The category information storage unit stores category information which is information for categories for which the operating data statistical processor performs a statistical process. The category information is information used for categorizing a fault in accordance with a duration that indicates a period during which a specific state e.g. state no supply of works from preprocess is continued and is completed for example within 1 min. to within 10 min or every 1 min .

The analysis results output unit outputs predetermined information that includes analysis results obtained by the analysis unit . Here output is a concept that includes presentation of data on a display unit printing of data performed by a printer transmission of data to an external apparatus and storage of data on a recording medium. Specifically in this embodiment the analysis results output unit outputs the operating state of the equipment using a graph a specific example will be described later or outputs histograms for a moving time and a restoration time. Specifically the analysis results output unit outputs a graph showing for example statistical data obtained by the operating data statistical processor . More specifically for each equipment the analysis results output unit employs a total time for the durations of the individual states indicated by state information and outputs for example a pie chart that represents the occurrence rates temporal rates of the individual states indicated by state information. Further specifically for each state duration indicated by state information the analysis results output unit outputs a histogram indicating a frequency. While referring to this histogram a user can understand the operating situation of the equipment . The analysis results output unit may or may not include an output device such as a display device. Driver software for an output device or driver software for an output device and the output device may be employed to provide the analysis results output unit .

The statistical results output unit employs a predetermined graph such as a pie chart or a histogram to output statistical data obtained by the operating data statistical processor . The process for outputting a pie chart or a histogram is a well known process and an example output pie chart or histogram will be described later.

The operation of the analysis apparatus will now be described while referring to the flowchart in . In the flowchart in only those steps will be described that differ from those in the flowchart in . In step S although the analysis process is indicated as analysis process in order to distinguish from analysis process and analysis process the analysis process is the same process of analysis process in and thus its explanation will be omitted.

 step S The operating data statistical processor performs the statistical process for two or more sets of state information obtained by the state decoder and obtains statistical data in order to ascertain the operating situations for one or more equipments . The obtained statistical data pertains to each equipment and represents a total time for the occurrence of state information. This process is referred to as an analysis process . The analysis process will be described in detail later while referring to the flowchart in .

 step S Based on the data that represent the total time obtained at step S for the occurrences of the states indicated by the state information the statistical results output unit outputs a graph such as a pie chart in which the temporal rate of each state is indicated.

 step S The operating data statistical processor performs the statistical process for two or more sets of state information obtained by the state decoder and obtains statistical data in order to ascertain the operating situations for one or more equipments . The obtained statistical data is frequency data for each category that is indicated by category information pertaining to the state indicated state information. This process is referred to as an analysis process . The analysis process will be described in detail later while referring to the flowchart in .

 step S The statistical results output unit outputs a histogram based on frequency data for each category obtained at step S. It should be noted that the histogram is output for each equipment and or each state. The processing is thereafter terminated.

In the flowchart in the analysis results output unit may employ a form other than a histogram or a pie graph as the output. Further in the flowchart in instead of performing the analysis processes and independently overlapping process may be performed only once.

 step S The operating data statistical processor performs the initialization process. The initialization process includes a process for substituting 1 into a counter value i and a process for substituting 0 into a variable corresponding to each set of state information. The variable corresponding to each set of state information is a variable used for calculating a duration for each state indicated by the state information. This variable is referred to as a state time variable as needed.

 step S The operating data statistical processor determines whether i th state information is present among state information data obtained at step S. When the i th state information is present program control advances to step S or when the i th state information is not present program control is shifted to a higher function.

 step S The operating information statistical processor increments by one the state time variable that corresponds to the i th state information.

 step S The operating data statistical processor increments the counter value i by one and program control returns to step S.

In the flowchart in a period corresponding to the value 1 of a state time variable is a time interval required for the acquisition of constant associated information. Further a period corresponding to the value 1 for the state time variable is not always 1 second.

 step S The operating data statistical processor performs the initialization process. The initialization process includes a process for substituting 1 into the counter value i and a process for substituting 0 into each state time variable.

 step S The operating data statistical processor determines whether the i th state information is present. When the i th state information is present program control advances to step S or when the i th state information is not present program control is shifted to step S.

 step S The operating data statistical processor determines whether the i th state information differs from the previously obtained state information the i th th state information the state is changed . When the state is changed program control advances to step S or when the state is not changed program control is shifted to step S.

 step S The operating data statistical processor stores as a set information that describes a category indicated by the value of the state time variable for the preceding state and information indicating the preceding state and the value duration of a state time variable. When the categories are 1 in one minute 2 in two minutes . . . 10 in ten minutes and 11 longer than ten minutes category information for example is ID 2 for each category. For category 1 in one minute the ID is 1 which means that the pertinent state will be continued in one minute. Information indicating the preceding state may be state information or the ID provided for the state information. The operating information statistical processor registers for example 2 normal operation 1870 . In 2 normal operation 1870 2 represents the ID of a category normal operation represents information indicating the preceding state and 1870 represents the duration seconds .

 step S The operating data statistical processor increments by one the state time variable that corresponds to the i th state information.

 step S The operating data statistical processor increments by one the counter value i and program control thereafter returns to step S.

 step S The operating data statistical processor calculates a total time for each state based on information registered at step S. Then program control returns to a higher function.

Assume that the command acceptance unit of the analysis apparatus accepts an analysis start command from a user.

Then the contact associated information acquisition unit obtains an operating data log having the data structure shown in from the operating data storage unit of the data collection apparatus .

The correction unit obtains a period t one second in this embodiment which is stored in advance that the state recognition unit requires for the acquisition of state information.

Sequentially the correction unit employs the obtained period t one second to correct a time that is included in all the contact associated information for the obtained operating data log.

Next the analysis unit performs the analysis process in the following manner and obtains operator moving time information and restoration time information based on one or more sets of contact associated information.

The state decoder of the analysis unit decodes the contact associated information to state information. As a result the analysis unit can obtain information with which a timing chart in can be prepared.

Next the operating data statistical processor performs the analysis process described above. That is the operating data statistical processor substitutes 0 into a variable a state time variable that corresponds to each set of state information. Following this the operating data statistical processor examines a coding map see and sequentially obtains state information based on contact associated information shown in . Then upon each acquisition of state information the operating data statistical processor increments by one the state time variable that is consonant with the state information. Through this process the total number of periods can be obtained wherein the individual states indicated by the state information occurred.

The operating information statistical processor obtains a state duration management table in . The state duration management table includes one or more records each of which includes a state information ID state information a state time variable s a rate and state definition information . The state information ID is an ID for identifying state information. The state time variable is information indicating the total length of the periods wherein the individual states indicated by state information occurred. The rate is the rate at which a state indicated by state information occurred. That is the operating data statistical processor calculates an attribute value rate based on the state time variable corresponding to all the state information. In the rate is a value obtained by rounding off to the first decimal place.

Next the statistical results output unit outputs a pie chart shown in by employing the rate and the state definition information in the state duration management table in . The pie chart in this embodiment is a graph showing the temporal rate of each state. By referring to the pie chart in FIG. a user on a production job site can examine a total ON period for the normal operating state and can obtain a rate that corresponds to the operation rate. Further the user on the production job site can examine other operating information to determine whether the cause of a halt is present in the local equipment in the preprocess or in the post process.

Following this the operating information statistical processor performs the analysis process . Specifically the operating information statistical processor substitutes 0 into a variable a state time variable that corresponds to each set of state information and obtains state information. Then the operating data statistical processor compares the latest obtained state information i th state information with the previously obtained state information i 1 th state information and increments by one the state time variable that corresponds to the pertinent state information before the state is changed. When the state is changed information designating a category indicated by the value of the state time variable for the preceding state information that indicates the preceding state and a total time of time are stored as a set. Through this process frequencies at which the individual states indicated by state information occurred continuously can be obtained as categories. Specifically the operating data statistical processor obtains for example a state information duration frequency management table shown in . The state information duration frequency management table includes one or more records each of which includes as attributes a category a frequency and a total time . The category is information used for grouping durations when specific states are continued. The frequency is the number of times a specific state was continued for a period indicated in a category. And the total time is the total number of the durations equivalent to the frequencies for the state in the category.

The operating data statistical processor obtains for each state a state information duration frequency management table. is a state information duration frequency management table of the state no work for preprocess for example.

Sequentially the statistical results output unit outputs a histogram based on the obtained state information duration frequency management table. It should be noted that the histogram is output for each equipment and for each state.

Furthermore when the statistical results output unit has output the histograms shown in a user uses them to ascertain the following. Assume that the histograms in represent the results obtained by measuring the duration and the frequency of the state no supply of works from preprocess . When the statistical results output unit outputs the histogram in the user determines that a tact balance relative to the preprocess is disturbed. When histogram in is output the user determines that a short time halt frequently occurred in the preprocess. When the histogram in is output the user determines that trouble halts occurred frequently during the preprocess. And when the histogram in is output the user determines that a plurality of factors are present for a production line defect. These determinations can be arrived at while referring to circular portions indicated by broken lines in the histograms in .

Further according to this embodiment in addition to the effects of first embodiment since statistical data indicating the duration of a specific state or indicating the occurrence frequency for a specific state is output the cause of a defect for example on a production line can be readily identified.

Furthermore according to this embodiment since the analysis apparatus includes the correction unit for correcting the time the times at which the state of the equipment changed e.g. upon the occurrence of a fault and the restoration can be accurately determined and as a result the cause of a fault can be easily found.

In this embodiment as with the first embodiment the coding map is not limited to the map shown in and a map shown in or may be employed. In or means don t care i.e. can be either 0 or 1 .

Further the functions of the individual apparatuses in this embodiment may be provided using software. This software may be distributed by being downloaded or by being recorded on a recording medium such as a CD ROM. This can be applied for another embodiment for this invention. The software that provides the divergence apparatus in this embodiment is the program as mentioned above in the first embodiment.

Additionally for the above program the contact associated information includes time information and the program permits a computer to further execute a correction step of 

employing a period required for the acquisition of state information to correct the operator moving time information and the restoration time information.

calculating the durations of the individual states indicated by state information for one or more equipments. Further it is preferable at the analysis results output step that a graph of the occurrence rate for a state be output based on the total time obtained at the operating data statistical processing step for the durations of the states indicated by state information.

Further for the program the analysis step includes an operating information statistical processing step of 

calculating the durations or and the frequencies of individual states indicated by state information for one or more equipment. Further it is preferable that at the analysis results output step histograms showing the frequencies of the individual states be output based on the durations and or the frequencies obtained at the operating data statistical processing step.

An explanation will now be given for a third embodiment of the present invention wherein a data collection apparatus includes two network interfaces and separates a network by which information is obtained that indicates the operation of a equipment from a network by which data is provided for an analysis apparatus so that network traffic is reduced and congestion is avoided.

The data collection apparatuses each include one or more divergence apparatuses one or more network apparatuses a data collection apparatus and an analysis apparatus .

The arrangement and the operation of the data collection apparatus are the same as those for the first embodiment except that different network interfaces are employed for connection to the divergence apparatus and connection to the analysis apparatus .

The data collection apparatus includes an operating data storage unit a second contact associated information receiver an operating data log accumulation unit and a second contact associated information transmitter .

The second contact associated information transmitter transmits to the analysis apparatus contact associated information stored in the operating data storage unit . The second contact associated information transmitter is provided by a wireless or a wired communication means.

Further two different networks a network N and a network N are provided for the production system. The network N is a local network provided between production facilities and the network N is an office network.

According to this embodiment while the load imposed on a network is increased as the operating state of a equipment is attained the data analysis process is not hindered by an increase in the load.

According to a fourth embodiment of this invention an explanation will now be given for an analysis apparatus that measures and outputs frequency operating information at each occurrence interval in order to determine whether a specific operating state occurred frequently or rarely. Further for this embodiment an explanation will also be given for an analysis apparatus that can more accurately analyze occurrence trends for an operating state by employing together the occurrence frequency for a direction in the operating state and the occurrence frequency for an interval. Furthermore the analysis apparatus of this embodiment categorizes a duration by length as a long time type or a short time type based on the duration frequency or categorizes an occurrence interval by length as being a frequent occurrence type or a sporadic occurrence type based on the frequency for the occurrence interval. As a result the trend is for there to be four types of operating information occurrence categories.

A production system for this embodiment is the same as that for the second embodiment except only for an analysis apparatus. The equipment includes one or more equipments one or more programmable controllers one or more data collection systems and one or more output apparatuses .

The data collection system includes one or more divergence apparatuses one or more network apparatuses a data collection apparatus and an analysis apparatus .

The analysis unit includes a coding map storage unit a state decoder a operator moving time information acquisition unit a restoration time information acquisition unit an operating data statistical processor a category information storage unit and a state identification information storage unit .

The analysis results output unit includes a moving time histogram output unit a restoration time histogram output unit and a statistical results output unit .

The operating data statistical processor performs the statistical process for two or more sets of state information obtained by the state decoder and obtains statistical data for ascertaining the operation situations of one or more equipments . Specifically for example the operating data statistical processor calculates for each equipment a total number of ON durations for individual states indicated by state information as well as a total number of OFF durations for the states. Then the operating data statistical processor calculates an ON duration and an OFF duration and a frequency for each state indicated by state information. Sequentially based on category information that will be described later the operating data statistical processor sorts into categories groups indicated by the category information the ON durations and their frequencies and the OFF durations and their frequencies for the individual states for each equipment . Following this the operating data statistical processor determines an occurrence type which is a type for the occurrence of a state based on information concerning the ON duration and its frequency for a specific state and or information concerning the OFF duration and its frequency for the specific state. Thereafter the operating data statistical processor obtains from the state occurrence type state identification information that designates a state. Further the operating data statistical processor may obtain state identification information from two or more state occurrence types in the same time slot. It should be noted that there are for example four occurrence types a long and frequent occurrence type a short and frequent occurrence type a long and sporadic occurrence type and a short and sporadic occurrence type . For each state the trend for the length of a duration is categorized as either a long type or a short type based on the frequency for the duration of a specific state the frequency for the ON duration of a specific state . Further the trend for an occurrence frequency is categorized as a frequent occurrence type or a sporadic occurrence type based on the frequency of the occurrence interval for a specific state the frequency for the OFF duration of a specific state . Each of the four occurrence types consist of a trend for the length of a direction and a trend for the occurrence frequency. Normally the operating data statistical processor for example is an MPU or a memory and the processing performed by the operating data statistical processor is provided by software that is recorded on a recording medium such as a ROM. However the processing may also be provided by hardware a special circuit .

State identification information and one or more occurrence types are stored in the state identification information storage unit in correlation with each other. A nonvolatile recording medium such as a hard disk or a ROM is appropriate for the state identification information storage unit however a volatile recording medium such as a RAM can also be employed.

The statistical results output unit employs a predetermined graph such as a pie chart or a histogram to output statistical data obtained by the operating data statistical processor . In this embodiment an ON histogram is defined for a histogram output by the statistical results output unit wherein the ON durations and their frequencies for the individual states are sorted into categories groups indicated by category information. Further an OFF histogram is defined for a histogram output by the statistical results output unit wherein the OFF durations and their frequencies for the individual states are sorted into categories groups indicated by category information. Additionally the statistical results output unit outputs the occurrence type determined by the operating data statistical processor and also outputs state identification information obtained by the operating data statistical processor . The processes for the output of a pie chart and a histogram are well known and an example output of the statistical results output unit will be explained later. In this case the output is a concept that include a display on a display device printing by a printer transmission to an external apparatus and storage on a recording medium. Driver software for an output device or driver software for an output device and an output device may be employed to provide the statistical results output unit .

The operation of the analysis apparatus will now be described while referring to the flowchart in . In the flowchart in only those steps will be described that differ from those in the flowchart in .

 step S The operating data statistical processor performs the statistical process for two or more sets of state information obtained by the state decoder and obtains statistical data in order to ascertain the operating situation for one or more equipments . Further the operating data statistical processor employs two or more state occurrence types in the same time slot to obtain state identification information for designating a state. This process is called an analysis process . The analysis process will be explained in detail later while referring to the flowcharts in .

 step S The statistical results output unit outputs a histogram based on frequency data obtained for a category at step S. The histogram is output for example for each equipment and for the ON OFF state. That is the statistical results output unit outputs an ON histogram and an OFF histogram for each state.

 step S The statistical results output unit outputs the state identification information obtained at step S. The processing is thereafter terminated.

The analysis process at step S will now be explained while referring to the flowcharts in . In the flowchart in only those steps will be described that differ different from those in the flowchart in .

 step S The operating data statistical processor stores as a pair information that indicates the preceding state is ON and the value duration of a state time variable. The information indicating the preceding state can be either state information or the ID of state information. The operating data statistical processor registers for example normal operation ON 1870 . In normal operation ON 1870 normal operation ON is information that the preceding state is ON and 1870 is a duration in seconds .

 step S The operating data statistical processor stores one or more sets each consisting of information that one or more states other than the preceding state are OFF and the values of state time variables durations . When information registered at step S is normal operation ON 1870 at step S the operating data statistical processor registers three sets of information indicating for example self halted OFF 1870 post process works full OFF 1870 and no work for preprocess OFF 1870 . Three sets of information provide the OFF duration for a specific state and the frequency for the OFF duration. Then program control advances to step S. It should be noted that one more state other than the preceding state is not always one of the three states described above. One of the other states can for example be manually halted OFF .

 step S The operating data statistical processor determines the state occurrence type based on the ON duration and its frequency form a specific state and or the OFF duration and its frequency for the specific state. The operation for determining the occurrence type will be described in detail later while referring to the flowchart in .

 step S The operating data statistical processor searches the state identification information storage unit and finds state identification information consonant with the occurrence type determined at step S. When two or more occurrence types are determined at step S the operating data statistical processor may find two or more sets of state identification information. Program control thereafter returns to a higher function.

The operation at step S for determining the occurrence type will now be explained while referring to the flowchart in .

 step S The operating data statistical processor performs an initialization process. The initialization process includes a process for substituting 1 into a counter value i and a process for example for calculating the total number of OFF durations for a specific contiguous state.

 step S The operating data statistical processor determines whether the i th state is present. When the i th state is present program control advances to step S or when the i th state is not present returns to a higher function.

 step S The operating data statistical processor obtains the long period occurrence count for the ON sub state of the i th state. The long period occurrence count is the total of the occurrence frequencies in categories that indicate periods longer or equal to or longer than a period allocated for a predesignated category.

 step S The operating data statistical processor obtains the short period occurrence count for the ON sub state in the i th state. The long period occurrence count is a total of the occurrence frequencies in categories that indicate periods shorter or equal to or shorter than a period allocated to a predesignated category.

 step S The operating data statistical processor determines whether the long period occurrence count obtained at step S the short period occurrence count obtained at step S . When this condition is established program control advances to step S or when this condition is not established program control is shifted to step S.

 step S The operating data statistical processor determines the i th state to be a long period type and writes an information pair that indicates the i th state and information that indicates a long period type. Program control thereafter advances to step S.

 step S The operating data statistical processor determines the i th state to be a short period type and writes an information pair for information that indicates the i th state and information that indicates a short period type.

 step S The operating data statistical processor obtains a long period occurrence count for the OFF sub state of the i th state.

 step S The operating data statistical processor obtains a short period occurrence count for the OFF sub state of the i th state.

 step S The operating data statistical processor determines whether the long period occurrence count obtained at step S the short period occurrence count obtained at step S is established. When this condition is established program control advances to step S or when this condition is not established program control is shifted to step S.

 step S The operating data statistical processor determines the i th state to be a sporadic occurrence type and writes an information pair that indicates the i th state and information that indicates a sporadic occurrence type. Program control advances to step S.

 step S The operating data statistical processor determines the i th state to be a frequent occurrence type and writes a pair of information that indicates the i th state and information that indicates a frequent occurrence type.

 step S The operating data statistical processor registers the occurrence type for the i th state. For registration of the occurrence type for example information for identifying the i th state and information of either a long period type or a short period type and either a sporadic occurrence type or a frequent occurrence type are entered as a pair.

 step S The operating data statistical processor increments the counter value i by one and program control returns to step S.

In the flowchart in the method for determining the long period type or the short period type and the sporadic occurrence type or the frequent occurrence type is not limited to the above described algorithm. For example the operating data statistical processor may obtain a category for a period in which the ON occurrence count for a state is the maximum and when this category is for a long period may determine that the occurrence type is a long period type or when the category is for a short period may determine the occurrence type is a short period type. In this case the operating data statistical processor also obtains the for a period in which the OFF occurrence count for a state is maximum and when this category is for a long period determines that the occurrence type is a sporadic occurrence type or when this category is for a short period determines that the occurrence type is a frequent occurrence type.

Further a long period type or a short period type and a sporadic occurrence type or a frequent occurrence type need not always be determined for all the states and it is appropriate that this occurrence type is determined only for a state that shows a noticeable trend.

In this situation assume that the analysis apparatus obtained for example contact associated information shown in and has corrected this information in the manner as described in the second embodiment and obtained contact associated information shown in . In state to state are for example normal operation and abnormally halted .

Sequentially the analysis apparatus outputs a moving time histogram and a restoration time histogram through the process performed as in the second embodiment.

Next an explanation will be given for the function for calculating the interval and frequency for generation of operation interval which is the feature of this embodiment. This function is the analysis process described above.

First the operating data statistical processor sequentially obtains state information and compares the latest obtained state information i 1 th state information with the previously obtained state information i th state information . Until the state is changed the operating data statistical processor increments by one the state time variable that corresponds to the state information. When the state is changed information that indicates a category indicated by the value of the state time variable for the preceding state information indicating that the preceding state is ON and a total time of time are stored as a set. This set of information is for example normal operation ON 60 minutes .

Furthermore the operating data statistical processor stores one or more sets of information indicating that states other than the preceding state are OFF and the value duration of the state time variable. For acquisition of states other than the preceding state the operating data statistical processor employs the state type management table in and prepares and registers information state identifier OFF above obtained total time for all the other states. Specifically the operating data statistical processor stores abnormally halted OFF 60 minutes no work for preprocess OFF 60 minutes works for work full for post process OFF 60 minutes .

The operating data statistical processor performs the above described processing for all the state information and obtains for example a state duration management table in . The state duration management table includes one or more records each of which consists of attributes ID sub state identifier and duration . The sub state identifier is information indicating ON OFF and represents one state together with the state identifier .

Next the operating data statistical processor adds the durations for the OFF time for a specific state that is timewise contiguous. In this case timewise contiguous is a timewise contiguous record having the same state identifier. That is while referring to record ID 3 record ID 7 and record ID 11 are contiguous records that should be added together. Further record ID 4 record ID 8 and record ID 12 in are also contiguous. Thus the operating data statistical processor adds the attribute values of the durations in record ID 3 record ID 7 and record ID 11 in and obtains a new record. Similarly the operating data statistical processor adds the attribute values of the durations in record ID 4 record ID 8 and record ID 12 in and obtains a new record. As a result the operating data statistical processor creates a new state duration management table in .

Following this the operating data statistical processor obtains for each state e.g. normal operation abnormally halted the occurrence frequency for each category e.g. in one minute in nine minutes or longer than ten minutes . This occurrence frequency represents the number of records in the table in that includes a duration to be entered in the time length allocated to each category.

Then the operating data statistical processor obtains a state frequency management table in The state frequency management table includes one or more records each of which includes attributes ID state identifier sub state identifier category and frequency . While referring to a phenomenon that the normal operation ON state was continued longer than ten minutes occurred 48 times. Further a phenomenon that the normal operation OFF state was continued in one minute occurred 18 times.

Sequentially the operating data statistical processor obtains occurrence count 48 of the long e.g. longer than ten minutes normal operation ON state. Sequentially the operating data statistical processor obtains occurrence count 0 total of in one minute to in six minutes of the short e.g. in six minutes normal operation ON state. Then the operating data statistical processor determines that occurrence count 48 for a long period state occurrence count 0 for a short period state and registers information indicating a long period type as the normal operation state.

Next the operating data statistical processor obtains occurrence count 1 of the long e.g. longer than ten minutes normal operation OFF state. Sequentially the operating data statistical processor obtains occurrence count 25 total of in one minute to in six minutes and frequency 18 for in one minute is included of the short e.g. in six minutes normal operation OFF state. Since occurrence count 1 for a long period state

Similarly the operating data statistical processor performs the processing for the abnormally halted state and writes short period sporadic occurrence type for the abnormally halted state.

Then the operating data statistical processor searches the state identification information management table in by employing as a key the normal operation state and long period frequent occurrence type and finds state identification information normally operating . Furthermore the operating data statistical processor searches the state identification information management table in also by employing as a key the abnormally halted state and short period sporadic occurrence type and finds state identification information normally operating .

Next the statistical results output unit outputs histograms in . The histogram in is a histogram showing the sub state for the normal operation ON state ON histogram and the histogram in is a histogram showing the sub state for the normal operation OFF state OFF histogram .

Sequentially the statistical results output unit outputs the obtained state specification information normally operating as shown in . In the above processing two sets of state identification information normally operating are found however since these two sets of information have the same contents only one information is output.

As shown in the statistical results output unit may output histograms and state identification information on one screen. The histograms in are prepared by focusing on state works full for post process and in the upper portion is an ON histogram and the lower portion is an OFF histogram. While referring to a halt trend appears in the histograms. Specifically it is apparent that in losing of a tact balance and a short time halt and a trouble halt occurred only in specific time slots.

As described above according to the embodiment since the histograms showing the ON state and OFF state are prepared and output the occurrence trend for the operating state can be clearly categorized. Specifically when for example a state wherein a equipment was halted for ten minutes or longer is frequent by referring to the ON histogram the occurrence trend of the state can be categorized as long period type and it is understood that a trouble halt occurred. A state wherein a equipment is halted for five to six minutes or less is frequent the occurrence trend of the state can be categorized as short period type and it is understood that a short time halt or losing of a tact balance occurred. Further a state wherein a equipment is halted longer than for example five minutes is frequent by referring to the OFF histogram the occurrence trend of the state can be categorized as sporadic occurrence type and it is understood that the state only rarely occurred. A state wherein a equipment is halted shorter than five minutes is frequent the occurrence trend of the state can be categorized as frequent occurrence type and it is understood that the state frequently occurred. That is according to the ON OFF state histograms the occurrence trend of the state can be categorized into four types long period frequent occurrence type long period sporadic occurrence type short period frequent occurrence type and short period sporadic occurrence type .

Furthermore when operating data collected and stored for an extended period of time is displayed simply using a time chart it is not easily identified whether the individual operating states were maintained ON for an extended period of time or frequently switched between ON and OFF. However when these states are displayed by using the ON OFF histograms and categorized as four occurrence types the occurrence trends of the operating states can be easily obtained.

In the above embodiment the operating data statistical processor may prepare only an ON histogram or an OFF histogram. That is the operating data statistical processor does not need to determine an occurrence type and obtain state identification information. In this case a user should examine the ON histogram and the OFF histogram output by the statistical results output unit and should manually determine an occurrence type and obtain state identification information.

Further in the embodiment the state identification information management table in has been employed to search one state identification information based on one identifier and an occurrence type. However a state identification information management table in may be employed. In this table in two or more state identifiers and occurrence types are employed to identify one set of state identification information. In the state identification information management table in when state identifier normal operation of record ID 1 is a short period frequent occurrence type and state identifier no work for preprocess is also a short period frequent occurrence type this represents state tact balance is disturbed for preprocess . In this case the operating data statistical processor employs a plurality of state occurrence types to obtain state identification information.

Further when the state identification information management table in is stored wherein are entered state identifier normal operation occurrence type short period frequent occurrence type state identifier works for work full for post process and occurrence type short period frequent occurrence type the operating data statistical processor searches the state identification management table in and obtains state identification information tact balance is disturbed in the post process .

Then the statistical results output unit outputs the obtained state identification information tact balance is disturbed in the post process in the manner shown in .

Furthermore when the state identification information management table in is employed and when the state identifier abnormally halted is a long period sporadic occurrence type the operating data statistical processor obtains state identification information a trouble halt occurs occasionally . The statistical results output unit outputs the obtained state identification information a bit halt occurs occasionally . That is the state identification information to be output can be various types.

Further in this embodiment the ON histogram and the OFF histogram is output at the same time however either the ON histogram or the OFF histogram may be output. Based on the ON histogram the occurrence type of a state can be determined to be either a short period type or a long period type . Further based on the OFF histogram the occurrence type of a state can be determined to be either a frequent occurrence type or a sporadic occurrence type .

Further software that provides the analysis apparatus for this embodiment is the following program. The program permits a computer to perform 

a contact associated information acquisition step of obtaining one or more sets of contact associated information from a data collection apparatus 

an analysis step of processing the one or more sets of contact associated information obtained at the contact associated information acquisition step and obtaining predetermined information and

an analysis results output step of outputting the predetermined information obtained at the analysis step.

an operating data statistical processing step of calculating ON durations and frequencies for the individual states indicated by state information for the equipment and also calculating OFF durations and frequencies for the states. Furthermore preferably based on the ON durations and frequencies and the OFF durations and frequencies for the individual states that have been obtained at the operating data statistical processing step ON histograms and OFF histograms that represent ON and OFF frequencies for the states are output at the analysis output step.

Further at the operating data statistical processing step of the program an occurrence type that is a type of an occurrence of a state is determined by employing the ON duration and the frequency of a state and or the OFF duration and the frequency of a state and the occurrence type is output at the analysis results output step.

Further at the operating data statistical processing step of the program the ON duration and a frequency of a state and or the OFF duration and a frequency of a state are employed to determine an occurrence type that is a type of an occurrence of a state and the occurrence type is employed to find state identification information. Furthermore the state identification information is output at the analysis results output step.

In the individual embodiments the individual processes functions may be centralized and performed by a single apparatus system or they may be distributed to a plurality of apparatuses.

The information transmission step and the information reception step of the program do not include processes performed by hardware such as processes performed using a modem or an interface card processes performed only by hardware .

A single computer or multiple computers may be employed to perform the program of the invention. That is centralized processing or distributed processing may be performed.

Further in the embodiments two or more communication units information transmitter or output unit such as data transmitters present in one apparatus may be physically provided by a single medium.

The present invention is not limited to the above described embodiments and can be variously modified and these modifications are also included within the technical scope of the present invention.

As described above the data collection system of the invention is effective and useful because this system can collect operating data for existing production facilities without affecting the performance of these production facilities.

