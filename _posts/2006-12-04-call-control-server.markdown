---

title: Call control server
abstract: In a communication system that includes a communication terminal that originates and receives a call through a call control server, the call control server receives destination information from the communication terminal as a call request. The call control server checks an address of the communication terminal and determines based on the destination information whether transmission to a destination terminal is permitted for the communication terminal. Only when the transmission is permitted, the call control server originates a call to an address corresponding to the destination information to connect the communication terminal to the destination terminal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09473622&OS=09473622&RS=09473622
owner: RICOH COMPANY, LIMITED
number: 09473622
owner_city: Tokyo
owner_country: JP
publication_date: 20061204
---
The present document incorporates by reference the entire contents of Japanese priority document 2005 352784 filed in Japan on Dec. 7 2005.

The present invention relates to a call control server that connects a communication terminal to another terminal.

With the implementation of the Act on the Protection of Personal Information leakage of personal information has become a social problem. In particular there has been a case where personal information is erroneously transmitted to a wrong destination through communication by for example facsimile.

As a countermeasure against this problem some banks have introduced a system to prevent leakage of client information due to facsimile erroneous transmission. Reference may be had to the site http www.kyotobank.co.jp news pdf 2005 07 21.pdf accessible as of Oct. 6 2005 . In this system data is transmitted from a facsimile machine via a local area network LAN in the bank to a facsimile server where the data is automatically checked with destination information destination name facsimile machine number etc. registered in advance.

If they match and the destination is a place outside the bank transmission is temporarily halted and an executive in a transmitting section checks the destination and contents to be transmitted on a personal computer PC screen and then originates a call to a public line.

In this system however although the destination information of a place outside the bank is double checked through an automatic check on the facsimile server and a visual check by human the source information is checked only through a visual check by human this operation is not explicitly explained but it is assumed that the source information is checked through a check of transmission contents by human absence of a source check is not certain . That is the transmission source and the transmission destination are checked by human.

In this case human check may suffice if the number of transmission sources and transmission destinations is relatively small. However if the number is increased reliability of human check is decreased causing problems such that personal information is transmitted to an unintended destination leading to leakage of the personal information to third parties. Moreover in this case there is also a problem that such a human check takes time thereby impairing a real time feature of facsimile communication to interfere with business.

Meanwhile even among sections using a closed corporate network there is a risk in which a document is erroneously transmitted to a destination section not pertinent to personal information written on the document leading to erroneous leakage of the personal information to third parties without an appropriate process at the section receiving the document image.

Japanese Patent Application Laid Open Publication No. 2004 289782 discloses a method in which at the time of IP packet transfer over a network a source address and a destination address in an IPv6 header of an IP packet are identified and when interface IDs in the source address and the destination address match with a preset condition a transfer over the network is permitted or prohibited correspondingly. This interface ID contains information such as apparatus type and a manufacture name and apparatus model can be used as filter conditions.

However this operation can be applied only to a gateway and cannot be directly applied to a call control server for call connection.

Therefore other than communication via this gateway erroneous facsimile transmission cannot be prevented resulting in a problem that personal information is leaked to third parties.

Normally when personal information is leaked to third parties through erroneous facsimile transmission it is desirable that the transmitting operator can be specified.

However in the conventional technologies explained above a check to see who is a transmitting operator cannot be performed. Therefore when a problem of leakage of personal information occurs it is difficult to specify a transmitting operator thereby causing the ultimate location of responsibility to be blurred and posing a problem such that a risk of repeating the same error remains.

The problems explained above may occur not only in personal information but also in corporate confidential information.

On the other hand in recent years equipment and systems for transmitting and receiving voice data over a Voice over IP VoIP network have started to become widespread. Also needs for performing facsimile communication over this VoIP network is being increased and facsimile communication systems have been used such as the one conforming to International Telecommunication Union Telecommunication Standardization Sector ITU T Recommendations T.38 optimal to an IP network and the one in a G.711 PassThrough scheme in which a facsimile signal is regarded as a voice signal and is packetized to flow through an IP network.

In an in company VoIP network in place of Private Branch Exchange PBX used in a conventional analog circuit a call control server is often used in which a call is switched on an IP packet base. In this case a call to be switched is usually an IP phone call and there are not so many facsimile calls compared to IP phone calls. For this reason when an additional operation is performed only for controlling facsimile calls it is desired that whether to perform this additional operation be determined based on information from the calling source.

It is an object of the present invention to at least partially solve the problems in the conventional technology.

According to an aspect of the present invention a call control server in a communication system that includes a communication terminal that originates and receives a call through the call control server includes a receiving unit that receives destination information from the communication terminal as a call request a determining unit that checks an address of the communication terminal and determines based on the destination information whether transmission to a destination terminal is permitted for the communication terminal and a call connecting unit that originates a call to an address corresponding to the destination information only when the transmission is permitted to connect the communication terminal to the destination terminal.

According to another aspect of the present invention a call control server is used in a communication system that includes a communication terminal that originates and receives a call through the call control server and a monitor that issues to the call control server a command including information on whether to permit transmission from the communication terminal to a destination terminal based on destination information and an address of the communication terminal extracted from a call connection message received from the call control server. The call control server includes a receiving unit that receives the call connection message including the destination information from the communication terminal an inquiring unit that transmits the call connection message to the monitor and receives the command from the monitor and a call connecting unit that originates a call to an address corresponding to the destination information only when the transmission is permitted by the command to connect the communication terminal to the destination terminal.

According to still another aspect of the present invention a call control server is used in a communication system that includes a communication terminal that originates and receives a call through the call control server and transmits identification information that identifies a user of the communication terminal when originating a call. The call control server includes a receiving unit that receives destination information together with the identification information from the communication terminal as a call request a determining unit that determines based on the destination information and the identification information whether transmission to a destination terminal is permitted for the communication terminal and a call connecting unit that originates a call to an address corresponding to the destination information only when the transmission is permitted to connect the communication terminal to the destination terminal.

The above and other objects features advantages and technical and industrial significance of this invention will be better understood by reading the following detailed description of presently preferred embodiments of the invention when considered in connection with the accompanying drawings.

Exemplary embodiments of the present invention are described in detail below with reference to the accompanying drawings.

This communication system is a system in which voice data image data of facsimile machines and others are transmitted and received on a VoIP network NT. The communication system includes a call control server SV local networks forming areas ARa ARb and ARc connected to the VoIP network NT a VoIP gateway GW for interconnection with the VoIP network NT and an analog public network PSTN and group 3 facsimile machines FFa and FFb accommodated in the analog public network PSTN.

In the LAN sub network forming the area ARa a facsimile machine hereinafter IP facsimile machine FXa conforming to ITU T Recommendations T.38 and many for example on the order of 100 IP telephone terminals TA to TAn are connected to one another.

In the LAN sub network forming the area ARb an IP facsimile machine FXb and many for example on the order of 100 IP telephone terminals TB to TBAn are connected to one another.

In the LAN sub network forming the area ARc an IP facsimile machine FXc and many for example on the order of 100 IP telephone terminals TC to TCn are connected to one another.

Also the VoIP gateway GW has functions of converting a protocol for use on the VoIP network NT to a protocol for use on the analog public network PSTN and vice visa and also converting packetized digital data to an analog signal and vice versa.

Therefore the IP facsimile machines FXa FXb and FXc connected to the VoIP network NT can communicate with the group 3 facsimile machines FFa and FFb connected to the analog public network PSTN via the VoIP gateway GW. Also the IP telephone terminals TA to TAn TB to TBn and TC to TCn connected to the VoIP network NT can connect to subscriber telephones not shown connected to the analog public network PSTN via the VoIP gateway GW.

Here the call control server SV the IP facsimile machines FXa FXb and FXc the IP telephone terminals TA to TAn TB to TBn and TC to TCn and the VoIP gateway GW use ITU T Recommendations H.323 as a protocol for call control on the VoIP network.

In a gateway and a router for causing data to flow among different networks sub networks are not depicted.

The IP facsimile machine FX includes for example a central processing unit CPU a main memory a Read Only Memory ROM a clock generating circuit a bus controlling unit a Peripheral Component Interconnect PCI bridge circuit a cache memory a scanner controlling unit a scanner a print controlling unit a printer engine a hard disk HD an HD controlling unit a liquid crystal display LCD controlling unit an LCD a LAN controlling unit a LAN interface circuit a group 3 facsimile controlling unit a Public Switched Telephone Network PSTN analog public network interface circuit a key input controlling unit a hard key unit a Real Time Clock RTC a CPU bus a PCI bus and an X bus internal bus .

The CPU executes and processes a control processing program stored in the ROM and an Operation System OS . The main memory includes a Dynamic Random Access Memory DRAM and is used as a work area of the CPU or the like. The ROM has written in advance therein various programs for starting up the system at the time of power on and achieving functions of the IP facsimile machine FX.

The clock generating circuit includes a crystal oscillator and a dividing circuit and generates a clock for controlling the operation timing of the CPU and the bus controlling unit . The bus controlling unit controls data transfer on the CPU bus and the X bus . The PCI bridge circuit performs data transfer between the PCI bus and the CPU by using the cache memory . The cache memory includes a DRAM and is used by the PCI bridge circuit .

The scanner controlling unit controls a document reading operation of the scanner . The scanner reads an image on paper by a charge coupled device CCD line sensor. The print controlling unit controls the operation of the printer engine . The printer engine uses toner to generate a monochrome image on paper.

The HD stores image data received through communication when the IP facsimile machine runs out of print recording paper. The HD controlling unit has for example an Integrated Device Electronics IDE interface as an interface with the HD for high speed data transmission with the HD .

The LCD controlling unit performs Digital to Analog D A conversion on character data graphic data and others and also performs control for displaying such data on the LCD . The LAN controlling unit executes a communication protocol complying with for example Institute of Electrical and Electronics Engineers IEEE 802.3 standard and controls communication with another device connected to the Ethernet via the LAN interface circuit .

The group 3 facsimile controlling unit transmits and receives a group 3 facsimile modem signal by a modem incorporated therein and also performs compression and decompression of facsimile image data.

The key input controlling unit converts serial data input from the hard key unit to parallel data. The RTC is a daily clock and is backed up by a battery not shown.

Here regarding processes for which any hardware component is not explicitly explained the CPU executes a control process program stored in the ROM using the main memory as a work area.

The call control server SV includes for example a CPU a main memory a ROM a clock generating circuit a bus controlling unit a PCI bridge circuit a cache memory an HD an HD controlling unit a cathode ray tube CRT controlling unit a CRT display a LAN controlling unit a LAN interface circuit a key input controlling unit a keyboard an RTC a CPU bus a PCI bus and an X bus .

The CPU executes and processes a control processing program stored in the ROM and an OS. The main memory includes a DRAM and is used as a work area of the CPU or the like. The ROM has written in advance therein various programs for starting up the system at the time of power on and achieving functions of the call control server SV.

The clock generating circuit includes a crystal oscillator and a dividing circuit and generates a clock for controlling the operation timing of the CPU and the bus controlling unit . The bus controlling unit controls data transfer on the CPU bus and the X bus . The PCI bridge circuit performs data transfer between the PCI bus and the CPU by using the cache memory . The cache memory includes a DRAM and is used by the PCI bridge circuit .

The HD stores various data such as program data address data for call connection various setting data and work data . The HD controlling unit has for example an Integrated Device Electronics IDE interface as an interface with the HD for high speed data transmission with the HD .

The CRT controlling unit performs D A conversion on character data graphic data and others and also performs control for displaying such data on the CRT display . The LAN controlling unit executes a communication protocol complying with for example IEEE 802.3 standard and controls communication with another device connected to the Ethernet via the LAN interface circuit .

The key input controlling unit converts serial data input from the keyboard to parallel data. The RTC is a daily clock and is backed up by a battery not shown.

Here regarding processes for which any hardware component is not explicitly explained the CPU executes a control process program stored in the ROM using the main memory as a work area.

Also the call control server SV has stored therein a association table depicting a relation between telephone numbers number sequences of 0 to 9 following a known telephone number providing system which are referred to as alias numbers and IP addresses of the IP facsimile machines FXa FXb and FXc and the IP telephone terminals TA to TAn TB to TBn and TC to TCn such a table is referred to as an alias IP address association table refer to and a combination table depicting combinations of a source IP address and a destination alias number among any of the IP facsimile machines FXa FXb and FXc for which communication is permitted such a table is referred to as a communication permitted address table refer to . A system administrator can change and add new data to the data in these tables as appropriate.

The IP facsimile machines FXa FXb and FXc and the IP telephone terminals TA to TAn TB to TBn and TC to TCn are each provided with an alias number starting with a number other than 0. The telephone number of a subscriber telephone connected to the analog public network PSTN 0AB to J number a telephone number starting with 0 is used as it is as an alias number.

It is assumed that in this case communication from the IP facsimile machine FXa to the IP facsimile machine FXc and the group 3 facsimile machine FFa is set as being permitted whilst communication from the IP facsimile machine FXa to the IP facsimile machine FXb and the group 3 facsimile machine FFb is set as being not permitted.

First the case is explained in which a connection is established from the IP facsimile machine FXa to the IP facsimile machine FXc for communication.

The IP facsimile machine FXa sets the alias number of the IP facsimile machine FXc in destinationAddress which is a parameter of Setup UUIE to be included in a user user information element of a Setup message and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV acquires the alias number which is a value of destinationAddress included in this message and also acquires the IP address of the IP facsimile machine FXa which is the transmission source from the header of a Transmission Control Protocol TCP packet with which this Setup message is sent thereby checking whether a combination of this IP address and the destination alias number is in the communication permitted address table.

When confirming that this address combination is in the communication permitted address table the call control server SV acquires a destination IP address by referring to the alias IP address association table.

Then the call control server SV calls the IP address to connect the IP facsimile machine FXc and then returns a Connect message which is a normal response to the IP facsimile machine FXa to connect a channel for facsimile communication between the IP facsimile machine FXa and the IP facsimile machine FXc thereby performing facsimile communication complying with ITU T Recommendations T.38.

Next the case is explained in which a connection is established from the IP facsimile machine FXa to the group 3 facsimile machine FFa for communication.

The IP facsimile machine FXa as with the above sets the alias number of the group 3 facsimile machine FFa which is identical to a subscriber telephone number of the group 3 facsimile machine FFa in destinationAddress which is a parameter of the Setup message and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV acquires the alias number which is a value of destinationAddress included in this message and also acquires the IP address of the IP facsimile machine FXa which is the transmission source from the header of a TCP packet with which this Setup message is sent thereby checking whether a combination of this IP address and the destination alias number is in the communication permitted address table.

When confirming that this address combination is in the communication permitted address table the call control server SV checks to see whether the alias number starts with 0. Since the alias number starts with 0 the call control server SV sets the alias number of the group 3 facsimile machine FFa in destinationAddress which is a parameter of the Setup message and then transmits the result to the VoIP gateway GW.

When the alias number starts with 0 the call control server SV always issues a call request to the VoIP gateway GW.

When calling the alias number included in the Setup message to connect to the group 3 facsimile machine FFa the VoIP gateway GW returns a Connect message which is a normal response to the call control server SV.

Then the call control server SV returns a Connect message to the IP facsimile machine FXa. The IP facsimile machine FXa then performs facsimile communication with the group 3 facsimile machine FFa via the VoIP gateway GW.

Next the case is explained in which a connection is tried to be established from the IP facsimile machine FXa to the IP facsimile machine FXb.

The IP facsimile machine FXa as with the above sets the alias number of the IP facsimile machine FXb in destinationAddress which is a parameter of the Setup message and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV acquires the alias number which is a value of destinationAddress included in this message and also acquires the IP address of the IP facsimile machine FXa which is the transmission source from the header of a TCP packet with which this Setup message is sent thereby checking whether a combination of this IP address and the destination alias number is in the communication permitted address table.

Since this combination is not in the communication permitted address table the call control server SV returns a Release Complete message meaning connection rejection to the IP facsimile machine FXa and does not establish a connection with the IP facsimile machine FXb.

Upon receiving a Setup message YES at step S it is checked whether a combination of the source IP address and the destination alias number is in the communication permitted address table step S .

If this combination is not in the table NO at step S a Release Complete message is returned to the IP facsimile machine FX which is the call requester step and then the process ends at this time.

On the other hand if this combination is in the table YES at step S it is checked whether the alias number starts with 0 step S . If the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FX and then a Connect message is returned to the call requester IP facsimile machine FX step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FX and the destination IP facsimile machine FX step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand when the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FX step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FX and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S the connection for call control is disconnected and the operation ends at this time.

In the above description the case has been explained in which the IP address of the source terminal is acquired from the header of the TCP packet. Alternatively at the source terminal its IP address can be put in sourceCallSignalAddress which is a parameter of Setup UUIE to be included in a user user information element of a Setup message for transmission and from this parameter the call control server SV can acquire the IP address of the source terminal.

In this manner in the embodiment since a check on a transmission source and a transmission destination is automatically performed at the call control server human error that might occur when the transmission source and the transmission destination are visually checked as has been conventionally performed can be prevented. Also erroneous leakage of personal information or corporate secret to third parties due to erroneous transmission can be prevented.

Meanwhile the call control server SV receives a connection request not only from the IP facsimile machine FX but also from an IP telephone terminal. In the communication system of if permission or denial of connection with only any IP facsimile machine FX is desired a determination of whether the connection is permitted is made only when the source IP address is an IP address of an IP facsimile machine FX.

In a second embodiment as depicted in the call control server SV manages an alias IP address association table for IP telephone terminals and that for IP facsimile machines FX separately.

The case is explained in which a connection is established from the IP facsimile machine FXa to the IP facsimile machine FXc for communication.

The IP facsimile machine FXa sets the alias number of the IP facsimile machine FXc in destinationAddress which is a parameter of a Setup message and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV acquires the IP address of the source IP facsimile machine FXa from the header of the TCP packet with which this Setup message is sent. Then it is checked which alias IP address association table this IP address is in that is the one for IP telephone terminals or the one for IP facsimile machines FX.

If it is determined that this IP address is in the one for IP facsimile machines FX the alias number which is a value of destinationAddress included in the Setup message previously received is acquired and then it is checked whether a combination of this alias number and the IP address previously acquired is in the communication permitted address table.

When confirming that this address combination is in the communication permitted address table the call control server SV acquires a destination IP address by referring to the alias IP address association table for IP facsimile machines FX.

Then the call control server SV calls the IP address to connect to the IP facsimile machine FXc and then returns a Connect message which is a normal response to the IP facsimile machine FXa to connect a channel for facsimile communication between the IP facsimile machine FXa and the IP facsimile machine FXc thereby performing facsimile communication complying with ITU T Recommendations T.38.

On the other hand if the IP address of transmission source of the Setup message received by the call control server SV is for IP telephone terminals an alias number which is a value of destinationAddress included in the Setup message is acquired and then the destination IP address is acquired by referring to the alias IP address association table for IP telephone terminals.

Then the call control server SV calls the IP address to connect to the IP telephone terminal and then returns a Connect message which is a normal response to the source IP telephone terminal. Then a channel for voice is connected between IP telephone terminals for transmission and reception of voice data.

Upon receiving a Setup message YES at step S it is checked whether the source IP address is in the alias IP address association table for IP facsimile machines FX step S .

If the result of step S is YES it is checked whether a combination of the source IP address and the destination alias number is in the communication permitted address table step S .

If this combination is not in the table NO at step S a Release Complete message is returned to the call requester IP facsimile machine FX step S and then the process ends at this time.

On the other hand if this combination is in the table YES at step S a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FX and then a Connect message is returned to the call requester IP facsimile machine FX step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FX and the destination IP facsimile machine FX step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand if the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table for IP telephone terminals step S . Next the IP address is called to connect to the IP telephone terminal and then a Connect message is returned to the call requester IP telephone terminal step S .

With this voice data is transmitted between IP telephone terminals step S and a call end operation is waited NO at step S . When a call end operation is performed YES at step S the connection for call control is disconnected step S and the operation ends at this time.

In this manner in the embodiment an additional operation is performed only when the calling terminal is a facsimile machine. With this the load on an operation process of the call control server can be reduced.

In the embodiment the VoIP network NT is provided with a monitor CV. In place of the call control server SV this monitor CV determines whether to permit connection. Also the monitor CV has a configuration similar to that of the call control server SV depicted in and a connection monitoring application is implemented. The operation of the monitor CV explained below is operated and performed by this connection monitoring application.

In this case the call control server SV has implemented therein a Hypertext Transfer Protocol HTTP server function and a Java Telephony Application Programming Interface JTAPI refer to http java.sun.com products jtapi index.jsp . The connection monitoring application of the monitor CV uses an HTTP command and JTAPI to perform an operation in conjunction with the call control server SV.

The monitor CV first uses a JtapiPeerFactory class provided by JTAPI to generate JtapiPeer object and with a getProvider method performs registration on the call control server SV. With this the monitor CV can receive various events from the call control server SV.

The monitor CV has stored therein a combination table depicting combinations of a source IP address and a destination alias number among any of the IP facsimile machines FXa FXb and FXc for which communication is permitted communication permitted address table refer to . A system administrator can change and add new data to the data in these tables as appropriate.

The case is explained in which a connection is established from the IP facsimile machine FXa to the IP facsimile machine FXc for communication.

The IP facsimile machine FXa sets the alias number of the IP facsimile machine FXc in destinationAddress which is a parameter of a Setup message and also sets the IP address of its own in SourceCallSignalAddress and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV issues an incoming call notification to the monitor CV. Upon receiving this notification the monitor CV issues to the call control server SV a command of requesting acquisition of Setup message data. This command is transmitted by using a GET method in HTTP.

Upon receiving this command the call control server SV passes the Setup message data to the monitor CV as being included in a HTTP 200 OK response. Upon receiving this Setup message the monitor CV acquires the alias number which is a value of destinationAddress included in this message and the IP address included in sourceCallSignalAddress and checks whether a combination of these IP address and destination alias number is in the communication permitted address table. When confirming that this address combination is in the communication permitted address table a command for permitting connection is transmitted to the call control server SV. This command is transmitted by using a POST method in HTTP.

Upon receiving this command the call control server SV acquires the alias number which is a value of destinationAddress included in the Setup message previously received and then acquires a destination IP address by referring to the alias IP address association table. Then the IP address is called to connect to the IP facsimile machine FXc and then a Connect message which is a normal response is returned to the IP facsimile machine FXa to connect a channel for facsimile communication between the IP facsimile machine FXa and the IP facsimile machine FXc thereby performing facsimile communication complying with ITU T Recommendations T.38.

Next the case is explained in which a connection is tried to be established from the IP facsimile machine FXa to the IP facsimile machine FXb for which connection is not permitted.

The IP facsimile machine FXa as with the above sets the alias number of the IP facsimile machine FXb in destinationAddress which is a parameter of a Setup message and also sets the IP address of its own in SourceCallSignalAddress and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV passes the data of this message to the monitor CV in a manner similar to the above. Upon receiving this Setup message the monitor CV acquires the alias number which is a value of destinationAddress included in this message and the IP address included in sourceCallSignalAddress and checks whether a combination of these IP address and destination alias number is in the communication permitted address table. Here since such a combination is not in the communication permitted address table a command for not permitting connection is transmitted to the call control server SV.

Upon receiving this command the call control server SV returns a Release Complete message meaning connection rejection to the IP facsimile machine FXa and does not establish a connection with the IP facsimile machine FXb.

An operation flow of the call control server SV in this case is depicted in whilst an operation flow of the monitor CV is depicted in .

In upon receiving this Setup message YES at step S the call control server SV issues an incoming call notification to the monitor CV step S and waits until a Setup data acquisition request command is received from the monitor CV NO at step S . When the result of step S is YES the call control server SV passes the Setup message data to the monitor CV step S and then waits until a connection permit information command is received from the monitor CV NO at step S .

When the result of step S becomes YES the connection permit information command is examined to check whether connection has been permitted step S . If the result of step S is NO Release Complete message is returned to the IP facsimile machine FX which is the call requester step S and then the process ends at this time.

If connection has been permitted YES at step S the alias number is acquired from the Setup message previously received step S and it is checked whether the alias number starts with 0 step S .

When the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FX and then a Connect message is returned to the call requester IP facsimile machine FX step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FX and the destination IP facsimile machine FX step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand when the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FX step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FX and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S where the connection for call control is disconnected and the operation ends at this time.

Also in upon receiving an incoming call notification from the call control server SV YES at step S the monitor CV issues to the call control server SV a Setup data acquisition request command step S .

Then the monitor CV waits until the Setup message data is received from the call control server SV NO at step S . When the result of step S is YES the data of the received Setup message is examined to check whether a combination of the source IP address and the destination alias number is in the communication permitted address table step S .

If this combination is in the table YES at step S a connection permit command is issued to the call control server SV step S and then the operation ends at this time. Also if this combination is not in the table and the result of step S is NO a connection deny command is issued to the call control server SV step S and then the operation ends at this time.

In this manner in the embodiment a check on the transmission source and the transmission destination is performed at the monitor which is outside of the call control server. With this the load on an operation process of the call control server can be reduced.

Meanwhile in the communication system of if permission or denial of connection with only any IP facsimile machine FX is desired a determination of whether the connection is permitted is made only when the source IP address is an IP address of an IP facsimile machine FX.

In this case as explained in the second embodiment the call control server SV manages an alias IP address association table for IP telephone terminals and that for IP facsimile machine FX separately.

The IP facsimile machine FXa sets the alias number of the IP facsimile machine FXc in destinationAddress which is a parameter of a Setup message and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV acquires the IP address of the source IP facsimile machine FXa from the header of the TCP packet with which this Setup message is sent. Then it is checked which alias IP address association table this IP address is in that is the one for IP telephone terminals or the one for IP facsimile machines FX. If it is determined that this IP address is in the one for IP facsimile machines FX an incoming call notification is issued to the monitor CV.

Upon receiving this notification the monitor CV issues to the call control server SV a command of requesting acquisition of Setup message data. This command is transmitted by using a GET method in HTTP.

Upon receiving this command the call control server SV passes the Setup message data to the monitor CV as being included in a HTTP 200 OK response. The operation of the call control server SV and the operation of the monitor CV are similar to those explained in the third embodiment and therefore details are not explained herein.

On the other hand if the source IP address is for IP telephone terminals the call control server SV does not issue an incoming call notification to the monitor CV but acquires the alias number which is a value of destinationAddress included in the Setup message and acquires a destination IP address by referring to the alias IP address association table for IP telephone terminals.

Then the call control server SV calls the IP address to connect to the IP telephone terminal and then returns a Connect message which is a normal response to the source IP telephone terminal. Then a channel for voice is connected between IP telephone terminals for transmission and reception of voice data.

Meanwhile a determination of whether the connection is permitted is made for each operator user performing a transmitting operation of the IP facsimile machine FX. Such a case is explained next as a fifth embodiment.

The IP facsimile machine FZ includes for example a CPU a main memory a ROM a clock generating circuit a bus controlling unit a PCI bridge circuit a cache memory a scanner controlling unit a scanner a print controlling unit a printer engine an HD an HD controlling unit an LCD controlling unit an LCD a LAN controlling unit a LAN interface circuit a group 3 facsimile controlling unit a PSTN interface circuit an integrated circuit IC card reader a key input controlling unit a hard key unit an RTC a CPU bus a PCI bus and an X bus .

The CPU executes and processes a control processing program stored in the ROM and an OS. The main memory includes a DRAM and is used as a work area of the CPU or the like. The ROM has written in advance therein various programs for starting up the system at the time of power on and achieving functions of the IP facsimile machine FZ.

The clock generating circuit includes a crystal oscillator and a dividing circuit and generates a clock for controlling the operation timing of the CPU and the bus controlling unit . The bus controlling unit controls data transfer on the CPU bus and the X bus . The PCI bridge circuit performs data transfer between the PCI bus and the CPU by using the cache memory . The cache memory includes a DRAM and is used by the PCI bridge circuit .

The scanner controlling unit controls a document reading operation of the scanner . The scanner reads an image on paper by a charge coupled device CCD line sensor. The print controlling unit controls the operation of the printer engine . The printer engine uses toner to generate a monochrome image on paper.

The HD stores image data received through communication when the IP facsimile machine runs out of print recording paper. The HD controlling unit has for example an IDE interface as an interface with the HD for high speed data transmission with the HD .

The LCD controlling unit performs D A conversion on character data graphic data and others and also performs control for displaying such data on the LCD . The LAN controlling unit executes a communication protocol complying with for example IEEE 802.3 standard and controls communication with another device connected to the Ethernet via the LAN interface circuit .

The group 3 facsimile controlling unit transmits and receives a group 3 facsimile modem signal by a modem incorporated therein and also performs compression and decompression of facsimile image data.

The key input controlling unit converts serial data input from the hard key unit to parallel data. The RTC is a daily clock and is backed up by a battery not shown.

An IC card is a contactless IC card having incorporated therein a non volatile memory and a wireless communication chip and meets for example FeliCa Sony s registered trademark specifications. In this case communication between the IC card and the IC card reader is performed via a radio wave of 13.56 megahertz and they can be separated up to approximately 10 centimeters apart from each other.

Here regarding processes for which any hardware component is not explicitly explained the CPU executes a control process program stored in the ROM using the main memory as a work area.

In the embodiment the operator user of the IP facsimile machine FZ has the IC card having recorded thereon a user code which is an identification number of each user and uses this IC card to perform various operations of the IP facsimile machine FZ.

That is in a wait state without any operation from the operator the IP facsimile machine FZ is in a non active mode of not accepting any operation of the operator. When the user code is read from the IC card this mode is removed and an operation of the operator is accepted.

The call control server SV has stored therein a association table depicting a relation between alias numbers and IP addresses of all IP telephone terminals and IP facsimile machines FZ such a table is referred to as an alias IP address association table refer to and a combination table depicting combinations of a source IP address a sender s user code and a destination alias number among any of the IP facsimile machines FZa FZb and FZc for which communication is permitted for each operator such a table is referred to as a user level communication permitted address table refer to .

In only one destination alias number is provided for a sender s user code. Alternatively a plurality of destination alias numbers can be registered for each user code. A system administrator can change and add new data to the data in these tables as appropriate.

Next the case is explained in which a connection is established from the IP facsimile machine FZa to the IP facsimile machine FZc for communication.

When the operator holds the IC card over the vicinity of the IC card reader of the IP facsimile machine FZa the IC card reader wirelessly reads the user code recorded on the IC card .

The IP facsimile machine FZa stores this user code in the main memory and also removes the non active mode. Then when the operator performs an operation of transmission to the IP facsimile machine FZc the IP facsimile machine FZa sets the alias number of the IP facsimile machine FZc in destinationAddress which is a parameter of Setup UUIE to be included in a user user information element of a Setup message and also sets the user code in conferenceID which is a parameter of Setup UUIE and then transmits the result to the call control server SV.

Here conferenceID is originally a conference ID for use in teleconference but since no teleconference is performed on the IP facsimile machine FZ this parameter is used for a user code.

Upon receiving this Setup message the call control server SV acquires the alias number which is a value of destinationAddress and the user code which is a value of conferenceID included in this message and also acquires the IP address of the IP facsimile machine FZa which is the transmission source from the header of a TCP packet with which this Setup message is sent thereby checking whether a combination of this IP address the user code identification information for identifying the operator and the destination alias number is in the user level communication permitted address table.

When confirming that this combination is in the user level communication permitted address table the call control server SV acquires a destination IP address by referring to the alias IP address association table.

Then the call control server SV calls the IP address to connect to the IP facsimile machine FZc and then returns a Connect message which is a normal response to the IP facsimile machine FZa to connect a channel for facsimile communication between the IP facsimile machine FZa and the IP facsimile machine FZc thereby performing facsimile communication complying with ITU T Recommendations T.38.

Upon receiving a Setup message YES at step S it is checked whether a combination of the source IP address the user code and the destination alias number is in the user level communication permitted address table step S .

If the combination is not in the table NO at step S a Release Complete message is returned to the call requester IP facsimile machine FZ step S and then the process ends at this time.

On the other hand if this combination is in the table YES at step S it is checked whether the alias number starts with 0 step S . If the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FZ and then a Connect message is returned to the call requester IP facsimile machine FZ step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FZ and the destination IP facsimile machine FZ step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand if the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FZ step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FZ and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S where the connection for call control is disconnected and the operation ends at this time.

Meanwhile in the user level communication permitted address table depicted in the case is depicted in which the sender s user code is set for each IP facsimile machine FZ. When a user code identification information for identifying the operator unique to the operator user of all IP facsimile machines FZ communicating with the call control server SV is provided as shown in the user level communication permitted address table contains only combinations of a sender s user code and a destination alias number and the source IP addresses are not required. That is the identification information for identifying the operator includes combinations of the IP address of the IP facsimile machine FZ and the user code in whilst the identification information includes only user codes in .

Upon receipt of a Setup message YES at step S it is checked whether a combination of the user code and the destination alias number is in the user level communication permitted address table step S .

If the combination is not in the table NO at step S a Release Complete message is returned to the call requester IP facsimile machine FZ step S and then the process ends at this time.

On the other hand if this combination is in the table YES at step S it is checked whether the alias number starts with 0 step S . If the result of step is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FZ and then a Connect message is returned to the call requester IP facsimile machine FZ step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FZ and the destination IP facsimile machine FZ step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand if the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FZ step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FZ and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S where the connection for call control is disconnected and the operation ends at this time.

Meanwhile in the fifth embodiment described above a determination of whether the connection is permitted is made for each operator user performing a transmitting operation of the IP facsimile FZ. In a sixth embodiment this determination is made for each group code shared among a plurality of operators.

In each of the IP facsimile machines FZa FZb and FZc user codes recorded on the IC cards are classified into groups and a group code provided to each group is associated with the user codes in that group and is stored in the HD .

The call control server SV has stored therein a combination table depicting combinations of a source IP address a source group code and a destination alias number among any of the IP facsimile machines FZa FZb and FZc for which communication is permitted for each group such a table is referred to as a group level communication permitted address table .

An example of this group level communication permitted address table is depicted in . In only one destination alias number is provided for a source group code. Alternatively a plurality of destination alias numbers can be registered for each group code. A system administrator can change and add new data to the data in this table as appropriate.

When the operator user holds the IC card over the vicinity of the IC card reader of the IP facsimile machine FZa the IC card reader wirelessly reads the user code recorded on the IC card .

The IP facsimile machine FZa stores this user code in the main memory and also removes the non active mode. Then when the operator performs an operation of transmission to the IP facsimile machine FZc the IP facsimile machine FZa sets the alias number of the IP facsimile machine FZc in destinationAddress which is a parameter of Setup UUIE to be included in a user user information element of a Setup message and also sets the group code corresponding to the user code stored in advance in conferenceID which is a parameter of Setup UUIE and then transmits the result to the call control server SV.

Here conferenceID is originally a conference ID for use in teleconference but since no teleconference is performed on the IP facsimile machine FZ this parameter is used for a group code.

Upon receiving this Setup message the call control server SV acquires the alias number which is a value of destinationAddress and the group code which is a value of conferenceID included in this message and also acquires the IP address of the IP facsimile machine FZa which is the transmission source from the header of a TCP packet with which this Setup message is sent thereby checking whether a combination of this IP address the group code and the destination alias number is in the group level communication permitted address table.

When confirming that this combination is in the group level communication permitted address table the call control server SV acquires a destination IP address by referring to the alias IP address association table. Then the call control server SV calls the IP address to connect to the IP facsimile machine FZc and then returns a Connect message which is a normal response to the IP facsimile machine FZa to connect a channel for facsimile communication between the IP facsimile machine FZa and the IP facsimile machine FZc thereby performing facsimile communication complying with ITU T Recommendations T.38.

Upon receiving a Setup message YES at step S it is checked whether a combination of the source IP address the group code and the destination alias number is in the group level communication permitted address table step S .

If the combination is not in the table NO at step S a Release Complete message is returned to the call requester IP facsimile machine FZ step S and then the process ends at this time.

On the other hand if this combination is in the table YES at step S it is checked whether the alias number starts with 0 step S . If the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FZ and then a Connect message is returned to the call requester IP facsimile machine FZ step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FZ and the destination IP facsimile machine FZ step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand if the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FZ step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FZ and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S where the connection for call control is disconnected and the operation ends at this time.

Meanwhile in the system of if permission or denial of connection with only any IP facsimile machine FZ is desired a determination of whether the connection is permitted is made only when the source IP address is an IP address of an IP facsimile machine FZ. Such a case is explained next as a seventh embodiment.

In this case as with the second embodiment the call control server SV manages an alias IP address association table for IP telephone terminals and that for IP facsimile machines FZ separately refer to .

In this case as with the fifth embodiment the IP facsimile machine FZa sets the alias number of the IP facsimile machine FZc in destinationAddress which is a parameter of the Setup message the IP address thereof in sourceCallSignalAddress and the user code in conferenceID which is a parameter of Setup UUIE and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV acquires the IP address of the IP facsimile machine FZa which is the transmission source from the header of a TCP packet with which this Setup message is sent. Then it is determined which alias IP address association table this IP address is in that is the one for IP telephone terminals or the one for IP facsimile machines FZ.

If it is determined that this IP address is in the one for IP facsimile machines FZ the alias number which is a value of destinationAddress included in the Setup message previously received and the user code which is a value of conferenceID are acquired and then it is checked whether a combination of these IP address user code and alias number is in the user level communication permitted address table.

When confirming that this address combination is in the user level communication permitted address table the call control server SV acquires a destination IP address by referring to the alias IP address association table. Then the call control server SV calls the IP address to connect to the IP facsimile machine FZc and then returns a Connect message which is a normal response to the IP facsimile machine FZa to connect a channel for facsimile communication between the IP facsimile machine FZa and the IP facsimile machine FZc thereby performing facsimile communication complying with ITU T Recommendations T.38.

Upon receiving a Setup message YES at step S it is checked whether the source IP address is in the alias IP address association table for IP facsimile machines FZ step S .

If the result of step S is YES it is checked whether a combination of the source IP address the user code and the destination alias number is in the user level communication permitted address table step S .

If this combination is not in the table NO at step S a Release Complete message is returned to the call requester IP facsimile machine FZ step S and then the process ends at this time.

On the other hand if this combination is in the table YES at step S a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FZ and then a Connect message is returned to the call requester IP facsimile machine FZ step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FZ and the destination IP facsimile machine FZ step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand if the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table for IP telephone terminals step S . Next the IP address is called to connect to the IP telephone terminal and then a Connect message is returned to the call requester IP telephone terminal step S .

With this voice data is transmitted between IP telephone terminals step S and a call end operation is waited NO at step S . When a call end operation is performed and the result of step S is YES the connection for call control is disconnected step S and the operation ends at this time.

In the embodiment the VoIP network NT is provided with a monitor CV. In place of the call control server SV this monitor CV determines whether to permit connection. Here the monitor CV has a configuration similar to that of and the configuration is not explained in detail herein.

In this case as with the fifth embodiment described above the IP facsimile machine FZa sets the alias number of the IP facsimile machine FZc in destinationAddress which is a parameter of the Setup message the IP address thereof in SourceCallSignalAddress and the user code in conferenceID which is a parameter of Setup UUIE and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV issues an incoming call notification to the monitor CV. Upon receiving this notification the monitor CV issues to the call control server SV a command of requesting acquisition of Setup message data. This command is transmitted by using a GET method in HTTP.

Upon receiving this command the call control server SV passes the Setup message data to the monitor CV as being included in a HTTP 200 OK response. Upon receiving this Setup message the monitor CV acquires the alias number which is a value of destinationAddress included in this message the IP address included in sourceCallSignalAddress and the user code which is a value of conferenceID and checks whether a combination of these is in the user level communication permitted address table. When confirming that this address combination is in the user level communication permitted address table a command for permitting connection is transmitted to the call control server SV. This command is transmitted by using a POST method in HTTP.

Upon receiving this command the call control server SV acquires the alias number which is a value of destinationAddress included in the Setup message previously received and then acquires a destination IP address by referring to the alias IP address association table. Then the IP address is called to connect to the IP facsimile machine FZc and then a Connect message which is a normal response is returned to the IP facsimile machine FZa to connect a channel for facsimile communication between the IP facsimile machine FZa and the IP facsimile machine FZc thereby performing facsimile communication complying with ITU T Recommendations T.38.

An example of operation of the call control server SV in this case is depicted in whilst an example of operation of the monitor CV is depicted in .

In upon receiving this Setup message YES at step S the call control server SV issues an incoming call notification to the monitor CV step S and waits until a Setup data acquisition request command is received from the monitor CV NO at step S . When the result of step S is YES the call control server SV passes the Setup message data including the user code to the monitor CV step S and then waits until a connection permit information command is received from the monitor CV NO at step S .

When the result of step S becomes YES the connection permit information command is examined to check whether connection has been permitted step S . If the result of step S is NO Release Complete message is returned to the IP facsimile machine FZ which is the call requester step S and then the process ends at this time.

If connection has been permitted YES at step S the alias number is acquired from the Setup message previously received step S and it is checked whether the alias number starts with 0 step S .

When the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FZ and then a Connect message is returned to the call requester IP facsimile machine FZ step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FZ and the destination IP facsimile machine FZ step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand when the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FZ step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FZ and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S where the connection for call control is disconnected and the operation ends at this time.

Also in upon receiving an incoming call notification from the call control server SV YES at step S the monitor CV issues to the call control server SV a Setup data acquisition request command step S .

Then the monitor CV waits until the Setup message data is received from the call control server SV NO at step S . When the result of step S is YES the data of the received Setup message is examined to check whether a combination of the source IP address the user code and the destination alias number is in the user level communication permitted address table step S .

If this combination is in the table YES at step S a connection permit command is issued to the call control server SV step S and then the operation ends at this time. Also if this combination is not in the table and the result of step S is NO a connection deny command is issued to the call control server SV step S and then the operation ends at this time.

Meanwhile in the embodiment explained above the user codes are managed independently for each IP facsimile machine FZ for each area . The case is explained where a user code identification information for identifying an operator unique to the operator user of the all IP facsimile machines FZ communicating with the call control server SV is provided. In this case the user level communication permitted address table contains only combinations of a sender s user code and a destination alias number and the source IP addresses are not required refer to . That is the identification information for identifying the operator includes combinations of the IP address of the IP facsimile machine FZ and the user code in whilst the identification information includes only user codes in .

Operations of the IP facsimile machines FZa FZb and FZc and the call control server SV in this case are similar to those in the eighth embodiment described above and therefore are not explained herein.

Upon receiving an incoming call notification from the call control server SV YES at step S the monitor CV issues to the call control server SV a Setup data acquisition request command step S .

Then the monitor CV waits until the Setup message data is received from the call control server SV NO at step S . When the result of step S is YES the data of the received Setup message is examined to check whether a combination of the user code and the destination alias number is in the user level communication permitted address table step S .

If this combination is in the table YES at step S a connection permit command is issued to the call control server SV step S and then the operation ends at this time. Also if this combination is not in the table and the result of step S is NO a connection deny command is issued to the call control server SV step S and then the operation ends at this time.

Meanwhile in the eighth embodiment described above a determination of whether the connection is permitted is made for each operator user performing a transmitting operation of the IP facsimile FZ. In a ninth embodiment this determination is made for each group code shared among a plurality of operators. Also in this case the call control server SV has stored therein the group level communication permitted address table as depicted in .

An example of operation of the call control server SV in this case is depicted in whilst an example of operation of the monitor CV is depicted in .

In upon receiving this Setup message YES at step S the call control server SV issues an incoming call notification to the monitor CV step S and waits until a Setup data acquisition request command is received from the monitor CV NO at step S . When the result of step S is YES the call control server SV passes the Setup message data including the group code to the monitor CV step S and then waits until a connection permit information command is received from the monitor CV NO at step S .

When the result of step S becomes YES the connection permit information command is examined to check whether connection has been permitted step S . If the result of step S is NO Release Complete message is returned to the IP facsimile machine FZ which is the call requester step S and then the process ends at this time.

If connection has been permitted YES at step S the alias number is acquired from the Setup message previously received step S and it is checked whether the alias number starts with 0 step S .

When the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FZ and then a Connect message is returned to the call requester IP facsimile machine FZ step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FZ and the destination IP facsimile machine FZ step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand when the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FZ step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FZ and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S where the connection for call control is disconnected and the operation ends at this time.

Also in upon receiving an incoming call notification from the call control server SV YES at step S the monitor CV issues to the call control server SV a Setup data acquisition request command step S .

Then the monitor CV waits until the Setup message data is received from the call control server SV NO at step S . When the result of step S is YES the data of the received Setup message is examined to check whether a combination of the source IP address the group code and the destination alias number is in the group level communication permitted address table step S .

If this combination is in the table YES at step S a connection permit command is issued to the call control server SV step S and then the operation ends at this time. Also if this combination is not in the table and the result of step S is NO a connection deny command is issued to the call control server SV step S and then the operation ends at this time.

In a tenth embodiment as with the second embodiment the call control server SV manages an alias IP address association table for IP telephone terminals and that for IP facsimile machines FZ separately.

Also as with the fifth embodiment described above the IP facsimile machine FZa sets the alias number of the IP facsimile machine FZc in destinationAddress which is a parameter of the Setup message the IP address thereof in SourceCallSignalAddress and the user code in conferenceID which is a parameter of Setup UUIE and then transmits the result to the call control server SV.

Upon receiving this Setup message the call control server SV acquires the IP address of the IP facsimile machine FZa which is the transmission source from the header of a TCP packet with which this Setup message is sent. Then it is determined which alias IP address association table this IP address is in that is the one for IP telephone terminals or the one for IP facsimile machines FZ. If it is determined that this IP address is in the one for IP facsimile machines FZ an incoming call notification is issued to the monitor CV.

Upon receiving this notification the monitor CV issues to the call control server SV a command of requesting acquisition of Setup message data. This command is transmitted by using a GET method in HTTP.

Upon receiving this command the call control server SV passes the Setup message data to the monitor CV as being included in a HTTP 200 OK response. Upon receiving this Setup message the monitor CV acquires the alias number which is a value of destinationAddress included in this message the IP address included in sourceCallSignalAddress and the user code which is a value of conferenceID and checks whether a combination of these is in the user level communication permitted address table. When confirming that this address combination is in the user level communication permitted address table a command for permitting connection is transmitted to the call control server SV. This command is transmitted by using a POST method in HTTP.

Upon receiving this command the call control server SV acquires the alias number which is a value of destinationAddress included in the Setup message previously received and then acquires a destination IP address by referring to the alias IP address association table. Then the IP address is called to connect to the IP facsimile machine FZc and then a Connect message which is a normal response is returned to the IP facsimile machine FZa to connect a channel for facsimile communication between the IP facsimile machine FZa and the IP facsimile machine FZc thereby performing facsimile communication complying with ITU T Recommendations T.38.

On the other hand if the source IP address is for IP telephone terminals the call control server SV does not issue an incoming call notification to the monitor CV but acquires the alias number which is a value of destinationAddress included in the Setup message and acquires a destination IP address by referring to the alias IP address association table for IP telephone terminals. Then the call control server SV calls the IP address to connect to the IP telephone terminal and then returns a Connect message which is a normal response to the source IP telephone terminal. Then a channel for voice is connected between IP telephone terminals for transmission and reception of voice data.

An operation flow of the call control server SV is depicted in . Here an operation flow of the monitor CV in this case is similar to that in and is not explained herein.

Upon receiving this Setup message YES at step S the call control server SV checks whether the source IP address is in the alias IP address association table for IP facsimile machines step S . If the result of step S is YES the call control server SV issues an incoming call notification to the monitor CV step S and waits until a Setup data acquisition request command is received from the monitor CV NO at step S . When the result of step S is YES the call control server SV passes the Setup message data including the user code to the monitor CV step S and then waits until a connection permit information command is received from the monitor CV NO at step S .

When the result of step S becomes YES the connection permit information command is examined to check whether connection has been permitted step S . If the result of step S is NO Release Complete message is returned to the IP facsimile machine FZ which is the call requester step S and then the process ends at this time.

If connection has been permitted YES at step S the alias number is acquired from the Setup message previously received step S and it is checked whether the alias number starts with 0 step S .

When the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table step S .

Then the IP address is called to connect to the IP facsimile machine FZ and then a Connect message is returned to the call requester IP facsimile machine FZ step S . With this an operation of transmitting predetermined image data is performed between the call requester IP facsimile machine FZ and the destination IP facsimile machine FZ step S .

Then when the image data transmitting operation ends the connection for call control is disconnected step S and the operation ends at this time.

On the other hand when the result of step S is YES the VoIP gateway GW is determined as a connection destination step S . Then the IP address of the VoIP gateway GW is called to connect to a group 3 facsimile machine ahead thereof and then a Connect message is returned to the call requester IP facsimile machine FZ step S .

With this an operation of transmitting predetermined image data is performed via the VoIP gateway GW between the call requester IP facsimile machine FZ and the destination group 3 facsimile machine step S .

Then when the image data transmitting operation ends the procedure goes to step S where the connection for call control is disconnected and the operation ends at this time.

On the other hand if the result of step S is NO a destination IP address is acquired by referring to the alias IP address association table for IP telephone terminals step S . Next the IP address is called to connect to the IP telephone terminal and then a Connect message is returned to the call requester IP telephone terminal step S .

With this voice data is transmitted between IP telephone terminals step S and a call end operation is waited NO at step S . When a call end operation is performed and the result of step S is YES the connection for call control is disconnected step S and the operation ends at this time.

Meanwhile in the embodiments explained above the connection monitoring application implemented in the monitor CV can be downloaded from a server or the like for use.

In the embodiments explained above the case has been explained in which ITU T Recommendations H. 323 is used as a protocol for call control. However another protocol can be used such as Session Initiation Protocol SIP refer to RFC 3261 of Internet Engineering Task Force IETF . Furthermore Hypertext Transfer Protocol HTTP is a communication protocol for information exchange between a Web server and a Web client in a Web service on the Internet IP network and was established by a standardizing organization called World Wide Web Consortium W3C .

In the embodiments explained above when a determination of permitting communication between a transmission source and a destination source is made a table containing combinations for which communication is permitted is referred to. Alternatively a table containing combinations for which communication is not permitted can be created in advance and referred to.

In the embodiments explained above the operation of the call control server SV and the operation of the monitor are controlled by a program executed on them. Also the program can be stored in an appropriate storage medium or the like or can be distributed over a network. Furthermore in each of the embodiments explained above the identification information for identifying the operator includes the user code or a combination of the user code and the address of the source communication terminal. Alternatively the identification information for identifying the operator can include a combination of arbitrary pieces of information other than the above.

As set forth hereinabove according to an embodiment of the present invention effects can be achieved in which since a check on a transmission source and a transmission destination is automatically performed at a call control server human error that might occur when the transmission source and the transmission destination are visually checked is prevented and erroneous leakage of personal information or corporate secret to third parties due to erroneous transmission is prevented.

Although the invention has been described with respect to a specific embodiment for a complete and clear disclosure the appended claims are not to be thus limited but are to be construed as embodying all modifications and alternative constructions that may occur to one skilled in the art that fairly fall within the basic teaching herein set forth.

