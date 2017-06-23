---

title: System and method to resolve an identity interactively
abstract: A system and method for resolving an identity includes a security console, which displays security information regarding a secure network. The security information includes at least a first identity used to access the secure network. An operator selects the first identity, and the security console sends it to a resolver. The resolver connects with an identity server to find an access session record with an identity matching the first identity. A second identity is extracted from this record, and the resolver returns a result that includes the second identity. The security console displays the second identity; The first identity can be a user identity of a user, where the second identity is corresponding host identity, or vise versa. In this manner, an efficient interface to security information is provided to an operator, where the operator may resolve a user/host identity to a host/user identity interactively.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07647635&OS=07647635&RS=07647635
owner: A10 Networks, Inc.
number: 07647635
owner_city: San Jose
owner_country: US
publication_date: 20061102
---
This invention relates generally to data networking and more specifically to a system and method to interactively resolve an identity.

The secure data network of a company is a critical component for day to day functioning of company business activities. A company employee uses a host device such as a desktop personal computer a laptop personal computer a personal data assistant PDA a workstation or a smartphone to access the secure data network for communication within the company and with the outside world. An employee typically accesses the secure data network after a successful log on process using an employee name or an employee identity.

Information about an employee s access to the secure data network is recorded in the secure data network such as in an identity server an authentication server or an identity management system. The information associates an employee identity with an identity of the host device used for the secure data network access such as an Internet Protocol IP address or a Media Access Control MAC address.

Security data network also records network activities of the host device in the form of event logs security alerts network performance reports or security monitor records. Information technologies IT staff supporting the security data network often have to plow through a large volume of such information to troubleshoot security instances such as security breaches suspicious network activities or employee complaints. Oftentimes IT staff has to discover the owner of a host device or the employee who is using the host device at the time of the security instance in order to troubleshoot a security instance.

In one example IT support engineer Eddie receives a security alert flagging a suspected malicious attack to the secure data network from a host device. The security alert includes an Internet Protocol IP address of the host device. In order to contact the employee using the host device for remedial action Eddie first queries a Dynamic Host Control Protocol DHCP server to find a device identity such as a Media Access Control MAC address of the host device. In one scenario Eddie queries a directory server or an identity server to find the employee who is using the host device. In another scenario Eddie checks an inventory record such as an inventory database a spreadsheet or a hard copy list to find the employee or the department who owns the host device. This largely manual process unfortunately takes minutes if not hours to complete. This not only hampers Eddie s ability to solve other security issues but may also spell lost opportunity to come up with a timely remedial solution for the security instance.

In another example while monitoring the secure data network Eddie notices unusual confidential document retrieval activities associated with an employee name Maria Vista . Eddie manually queries an identity server for security network access information and finds that Maria Vista has accessed secure data network using three different devices in the past 2 hours. Alarmed Eddie manually looks up inventory database and other network configuration information to locate the devices. This slow process causes unacceptable delay and by the time Eddie sends a security guard to investigate the alleged perpetrator is nowhere to be found.

Accordingly there is a need for a system and method to allow an IT personnel to interactively resolve a host device identity to an employee identity and vice versa. This invention addresses such a need.

A system and method for resolving an identity includes a security console which displays security information regarding a secure network. The security information includes at least a first identity used to access the secure network. An operator selects the first identity and the security console sends it to a resolver. The resolver connects with an identity server to find an access session record with an identity matching the first identity. A second identity is extracted from this record and the resolver returns a result that includes the second identity. The security console displays the second identity. The first identity can be a user identity of a user where the second identity is corresponding host identity or vise versa. In this manner an efficient interface to security information is provided to an operator where the operator may resolve a user host identity to a host user identity interactively.

In one embodiment secure network includes a data network based on an Internet Protocol IP . In one embodiment secure network includes a wired Local Area Network LAN such as an Ethernet. In one embodiment secure network includes a Wireless Local Area Network WLAN . In one embodiment secure network includes a Wide Area Network WAN . In one embodiment secure network includes a public data network such as a WiFi hotspot network or a cellular data network such as General Packet Radio Service GPRS network. In one embodiment secure network includes a private data network such as a home network a corporate network a regional corporate network or a corporate Virtual Private Network VPN . In one embodiment secure network includes a service provider network.

Host is a computing device with network access capabilities. In one embodiment host is a desktop personal computer or a laptop personal computer. In one embodiment host is a Personal Data Assistant PDA a smartphone or a cellular phone.

Typically user uses host to access secure network over an access session for some duration. During access session user assumes a user identity and host assumes a host identity . User identity corresponds to host identity for the access session .

In one embodiment user identity includes a user name a subscriber name or an employee number. In one embodiment user identity includes a telephone number an extension number or an email address.

In one embodiment host identity includes an Internet Protocol IP address. In one embodiment host identity includes a Media Access Control MAC address. In one embodiment host identity includes a host name. In one embodiment host identity includes an International Mobile Subscriber Identity IMSI a Temporary Mobile Subscriber Identity TMSI or an International Mobile Equipment Identity IMEI or a Mobile Equipment Identifier MEID .

Access session record records information about access session . Access session record includes user identity and host identity . In one embodiment access session record includes access time . Access time records the time of the access session . In one embodiment access time includes a time stamp of the starting time of access session . In one embodiment access time includes a time stamp of the ending time of access session .

Identity server stores access session record . In one embodiment identity server creates access session record at the starting time of access session . In another embodiment identity server creates access session record after the ending time of access session . In an embodiment identity server creates access session record during access session . Identity server may record access time during or after access session .

Security console is a software application presenting security information about secure network . Resolver is a software program associated with security console .

Security console runs on a computing device with a display screen. The computing device can be a server a workstation a desktop personal computer a laptop personal computer a Personal Data Assistant PDA or a smartphone. Security console presents security information about secure network on the display screen.

In one embodiment security information is an event log a security alert a network report a result of a security query a network performance summary a security monitoring record or a historical network usage report. In one embodiment security console includes a browser.

An operator uses security console to interactively monitor secure network . In one embodiment the computing device provides input module such as a mouse a pointing device a stylus or a touchscreen for operator to interact with security console .

In one embodiment security console presents user identity . Operator uses input module to select user identity and invokes resolver to resolve user identity . In one embodiment resolver I resolves user identity to host identity . In one embodiment resolver resolves user identity to access session record .

In one embodiment operator selects user identity by using the mouse to highlight user identity . In one embodiment operator selects user identity by placing the mouse over user identity .

In another embodiment security console presents host identity . Operator uses input module to select host identity and invokes resolver to resolve host identity to user identity . In one embodiment resolver resolves host identity to access session record .

In one embodiment operator highlights character sequence using input module . In one embodiment operator highlights by indicating the first character and the last character of character sequence . In one embodiment operator indicates the first character by clicking a mouse button of input module at a location before the first character. Likewise operator indicates the last character by clicking a mouse button of input module at a location after the last character. In one embodiment character sequence is a word or a sequence of words. In one embodiment operator highlights the word by double clicking a mouse button of input module .

In one embodiment security console includes identity recognizer . Identity recognizer analyzes character sequence to determine identity . In one embodiment identity recognizer recognizes a string of four numbers separated by periods such as 172.168.0.105 in character sequence . Identity recognizer determines identity to be a host identity as an IP address. In one embodiment identity recognizer recognizes a string of six two digit hexadecimal numbers separated by hyphens or colons such as 00 08 74 4C 7F 1D or 01 23 45 6C 89 AB in character sequence . Identity recognizer determines identity to be a host identity as an Ethernet MAC address.

In one embodiment identity recognizer recognizes character sequence as one or more words such as John Smith . Identity recognizer determines identity to be a user identity as a user name. In one embodiment identity recognizer recognizes character sequence as one or more digits such as 0239581 . Identity recognizer determines identity to be a user identity as an employee number. In one more embodiment identity recognizer recognizes character sequence as one word that includes an character such as johnsmith goldenbank.com . Identity recognizer determines identity to be a user identity as an email address.

In one embodiment security console includes a browser such as INTERNET EXPLORER FIREFOX NETSCAPE SAFARI or OPERA. In one embodiment security console includes a text editor. In one embodiment security console includes a network management application a network monitor application a network security management application a network performance monitor application.

In one embodiment plug in interface is an ActiveX Control Application Programming Interface API . In one embodiment plug in interface is based on Component Object Model COM or Distributed Component Object Model DCOM . In one embodiment plug in interface is based on Object Linking and Embedding OLE technology. In one embodiment plug in interface is based on Firefox extension system. In one embodiment plug in interface is based on Java applets technology.

Security console receives result from resolver over plug in interface . In one embodiment identity is a first host identity. In one embodiment result includes a first user identity that corresponds to the first host identity. In one embodiment result includes a first access session record. In another embodiment identity is a second user identity. In one embodiment result includes a second host identity that corresponds to the second user identity. In one embodiment result includes a second access session record.

In one embodiment security console formats and displays result on the display screen. In one embodiment security console displays result in a dialog box next to identity in the displayed security information . In one embodiment security console reformats and displays security information by including result as part of security information .

Resolver receives identity from security console as illustrated in . Resolver resolves identity in conjunction with an identity server .

Identity server stores a plurality of access session records. The plurality of access session records includes access session record .

Resolver connects to identity server . In one embodiment resolver connects to identity server over a data network. In one embodiment the data network is an IP network. In one embodiment the data network is secure network.

In one embodiment resolver connects to identity server using Hypertext Transfer Protocol HTTP . In one embodiment resolver connects to identity server using Simple Object Access Protocol SOAP Simple Network Management Protocol SNMP Remote Method Invocation RMI Remote Procedure Call RPC or Light Weight Directory Access Protocol LDAP . In one embodiment resolver connects to identity server using a database connectivity API such as Open Database Connectivity ODBC API or Java Database Connectivity JDBC API. In one embodiment resolver connects to identity server using a proprietary protocol.

Resolver sends identity to identity server . In one embodiment identity is host identity . Identity server selects access session record with matching host identity . Identity server extracts user identity from access session record and includes user identity in response . In one embodiment identity server includes access session record in response .

In another embodiment identity is user identity . Identity server selects access session record with matching user identity . Identity server extracts host identity from access session record and includes host identity in response . In one embodiment identity server includes access session record in response .

In one embodiment security console recognizes that identity is a user identity. Security console presents to operator a plurality of user identity resolution choices . In one embodiment user identity resolution choices include host identity access session record or access history. In one embodiment security console presents user identity resolution choices in a drop down selection menu on the display screen.

Operator uses input module to select from user identity resolution choices . In one embodiment operator selects the access session record choice. Security console sends identity to resolver over plug in interface requesting resolution from user identity to access session record.

In a similar fashion security console recognizes that security is a host identity. Security console presents to operator a plurality of host identity resolution choices . In one embodiment host identity resolution choices include user identity access session record or access history.

In one embodiment operator uses input module to point to a character in security information displayed on security console . In one embodiment operator uses the mouse to point to the character. In one embodiment operator uses a stylus to point to the character. Identity recognizer recognizes an identity in a sequence of characters that includes the character. In one embodiment the sequence of characters is delimited by a pair of white space characters such as character return line feed or space characters. In one embodiment the sequence of characters includes multiple words. In one embodiment the sequence of characters is delimited by a pair of matching tags such as Extended Markup Language XML tags or Hypertext Markup Language HTTP tags.

In one embodiment security console automatically recognizes an identity in security information . In one embodiment identity recognizer automatically scans security information to recognize identity . Security console sends the identity to resolver . In one embodiment identity recognizer matched the recognized identity against a list of identities. Security console sends the matched identity to resolver .

In one embodiment identity recognizer automatically recognizes a plurality of identities. Security console sends the plurality of identities to resolver .

In one embodiment resolver includes identity recognizer . Security console sends character sequence to resolver over plug in interface . Resolver invokes identity recognizer to recognize identity in character sequence . In one embodiment resolver indicates to security console the recognition of a user identity in character sequence security console presents user identity resolution choices to operator. In a similar fashion resolver indicates to security console the recognition of a host identity in character sequence security console presents host identity resolution choices to operator .

In one embodiment the resolution is based on time. Resolver sends time information to identity server together with identity . Identity server selects an access session record with access time matching the time information.

In one embodiment after operator selects identity security console prompts operator to enter time information. Security console obtains time information from operator . In one embodiment security console obtains time information from a clock that indicates time of day. Security console sends time information together with identity to resolver .

In one embodiment access session record includes additional user information such as office or cubicle number or location building number or location telephone number department name or email address. In one embodiment host identity resolution choices include additional user information choice. In one embodiment access session record includes additional host information such as host device type host device location network access point identity or device owner information. In one embodiment user identity resolution choices include additional host information choice.

In one embodiment security console stores result in a document. In one embodiment security console stores result in response to operator input.

Foregoing described embodiments of the invention are provided as illustrations and descriptions. They are not intended to limit the invention to precise form described. In particular it is contemplated that functional implementation of invention described herein may be implemented equivalently in hardware software firmware and or other available functional components or building blocks and that networks may be wired wireless or a combination of wired and wireless. Other variations and embodiments are possible in light of above teachings and it is thus intended that the scope of invention not be limited by this Detailed Description but rather by Claims following.

