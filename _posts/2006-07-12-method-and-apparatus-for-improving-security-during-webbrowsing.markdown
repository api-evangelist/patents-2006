---

title: Method and apparatus for improving security during web-browsing
abstract: One embodiment of the present invention provides a system that improves security during web-browsing. During operation, the system can receive a URL from a user. Next, the system can determine an IP address for the URL by querying a DNS server. The system can then determine a public-key associated with the URL. Next, the system can encrypt a string using the public-key to obtain an encrypted-string. The system can then send the encrypted-string to a remote-system which is associated with the IP address. Next, the system can receive a response from the remote-system. The system can then determine whether the DNS server has been compromised using the string and the response. If the system determines that the DNS server has been compromised, the system can alert the user, and in doing so, improve security during web-browsing.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09154472&OS=09154472&RS=09154472
owner: INTUIT INC.
number: 09154472
owner_city: Mountain View
owner_country: US
publication_date: 20060712
---
The World Wide Web WWW has permeated almost all aspects of our lives from buying cameras to buying real estate and from reading a newspaper to watching a movie. Unfortunately the WWW can also be a very dangerous place where even savvy users can compromise highly sensitive information or suffer substantial financial loss.

A common security problem on the Internet involves a malicious website posing as a legitimate one. For example a user may receive a malicious email which contains a link that seems legitimate however when the user clicks on the link it navigates the user s web browser to a malicious website which is specifically designed to extract private information from the unsuspecting user. For example the malicious website may prompt the user to enter his or her login name and or password bank account number credit card number etc.

If the user is careful he or she may be able to detect some security problems. For example after clicking on a link in the email the user can verify that the URL Universal Resource Locator that appears in the web browser s address bar is for a legitimate website. Some prior art techniques automate this process and restrict the user to only a list of legitimate websites to ensure that the user does not visit a malicious website. However this technique can prevent the user from visiting legitimate websites that are not on the list.

Unfortunately prior art techniques usually do not detect security threats which exploit a compromised DNS Domain Name System server. DNS is a distributed network of name servers which enables computer systems to resolve domain names to IP Internet Protocol addresses. However when a user queries a compromised DNS server the DNS server may return the IP address of a malicious website instead of the IP address of the legitimate website. Note that prior art techniques usually cannot detect such DNS based security threats because the address bar in the web browser displays the URL of a legitimate website.

One embodiment of the present invention provides a system that improves security during web browsing. During operation the system can receive a URL from a user. Next the system can determine an IP address for the URL by querying a DNS server. The system can then determine a public key associated with the URL. Next the system can encrypt a string using the public key to obtain an encrypted string. The system can then send the encrypted string to a remote system which is associated with the IP address. Next the system can receive a response from the remote system. The system can then determine whether the DNS server has been compromised using the string and the response. If the system determines that the DNS server has been compromised the system can alert the user and in doing so improve security during web browsing.

In a variation on this embodiment the string can contain the IP address for the URL a second IP address which is associated with the user s computer a timestamp which can specify the date and time when the string was encrypted or a random string.

In a variation on this embodiment the system can alert the user by displaying a watermark to the user using a web browser.

In a variation on this embodiment the system can determine the IP address by sending a query message with the URL s domain name to the DNS server and receiving a response message from the DNS server which contains the IP address.

In a variation on this embodiment the system can determine the public key by sending a query message with the URL to a trusted system which stores public keys and receiving a response message from the trusted system which contains the public key associated with the URL.

In a variation on this embodiment the system can determine whether the DNS server has been compromised by comparing the string with the response.

One embodiment of the present invention provides a system that determines whether a network has been compromised. During operation the system can determine a public key which is associated with a URL which contains a domain name. Next the system can query a DNS server to determine an IP address for the domain name. The system can then send an encrypted string to the IP address wherein the encrypted string is determined using a string and the public key. Next the system can receive a response from a remote system which is associated with the IP address. The system can then determine whether the network has been compromised using the string and the response. Note that the DNS server can be located within the network. Specifically in one embodiment the system determines that the network has been compromised by determining that the DNS server has been compromised.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing computer readable media now known or later developed.

Network is coupled with computer malicious web server legitimate web server trusted system compromised DNS server and DNS server .

Network can generally comprise any type of wire or wireless communication channel capable of coupling together network nodes. This includes but is not limited to a local area network a wide area network or a combination of networks or other network enabling communication between two or more computing systems. In one embodiment of the present invention network comprises the Internet.

A network node such as a computer can generally include any type of communication device capable of communicating with other network nodes via a network. This includes but is not limited to a computer system based on a microprocessor a mainframe computer a server a printer a video camera an external disk drive a router a switch a personal organizer a mobile phone or other computing system capable of processing data.

Network allows a network node such as computer to communicate with another network node such as legitimate web server . However in order to communicate computer needs to know the IP address of web server . Typically computer queries a DNS server such as DNS server to determine web server s IP address.

The Domain Name System DNS is a distributed network of name servers that provides a global naming service. DNS makes it possible to associate domain names to IP addresses.

DNS packet contains a number of fields that can be used by a network node such as a computer to exchange information with DNS server .

DNS query packets and DNS response packets can use the same DNS packet format. Specifically DNS packet can contain an identification field which allows a network node such as a computer to match queries to the corresponding responses. DNS packet can also contain a flags field which can indicate whether the DNS packet is a query or a response.

DNS packet can also contain four variable length fields namely queries response resource records authority response records and additional information response records . These variable length fields can be used for exchanging information between computer and DNS server . Additionally DNS packet can contain four other fields namely number of queries field number of response resource records field number of authority resource records field and number of additional information resource records field which can specify the number of entries in the four variable length fields.

During normal operation computer can send a DNS query packet to DNS server with legitimate web server s domain name. DNS server can then send a DNS response packet to computer with legitimate web server s IP address. Computer can then use the IP address to communicate with legitimate web server .

However if the DNS server is hijacked the DNS response packet may contain the IP address of a malicious web server instead of a legitimate web server s IP address. For example suppose computer sends a DNS query packet to compromised DNS server with legitimate web server s domain name. Compromised DNS server may respond by sending the IP address of malicious web server instead of sending legitimate web server s IP address.

Note that prior art techniques usually cannot detect a DNS hijack because these techniques typically use the URL to detect security problems. However during a DNS hijack since the URL points to a legitimate website prior art techniques are unable to detect the security problem.

Even if a security problem is detected prior art techniques typically do not properly alert an average user. Note that there are a number of users who are not technically savvy. Although most users pay attention to the content within a web browser s main window they many not know or pay attention to an icon or indicator on the web browser s toolbar which may alert them to security problems. Furthermore it may not be preferable to prevent the user from navigating to a website simply because the web browser was unable to ascertain the legitimacy of the website.

To summarize prior art techniques typically do not detect serious security problems such as a DNS hijack. Further even when prior art techniques detect a security problem they do not alert the user using an approach which is conspicuous yet non invasive.

The process can begin by receiving a URL from a user step . For example computer may receive the URL when user enters the URL in the address bar of a web browser or when user clicks on a link in an email or on a website.

Specifically the system can send a query message with the URL s domain name to the DNS server. The system can then receive a response message from the DNS server which contains the IP address.

For example computer can send a query message with the URL s domain name to compromised DNS server or to DNS server which can send a response message back to computer with an IP address.

Note that the system can determine the public key using a number of techniques. For example the system e.g. computer can send a query message with the URL to a trusted system e.g. trusted system which stores public keys. Computer can then receive a response message from trusted system which contains the public key associated with the URL.

Alternatively the system may lookup the public key in a local keystore which contains the public keys for a number of URLs and or trusted systems. Further one or more public keys may be hard coded in the web browser software. For example a public key for trusted system may be hard coded in the web browser software. In yet another embodiment the system can receive a signed public key which proves that the public key is associated with the URL.

The string can be any string that can help the system to verify the identity of the URL. Specifically the string can contain the IP address for the URL a second IP address which is associated with the user s computer a timestamp which can specify the date and time when the string was encrypted or a random string. Note that the string can be a concatenation of a number of sub strings which can contain the above described information.

The system can then send the encrypted string to a remote system which is associated with the IP address step .

For example if computer queries DNS server it may receive legitimate web server s IP address. On the other hand if computer queries compromised DNS server it may receive malicious web server s IP address. Hence in the first scenario computer can send the encrypted string to the legitimate web server and in the second scenario computer can send the encrypted string to the malicious web server .

Note that the encrypted string can be sent using a networking protocol such as TCP Transport Control Protocol SSL Secure Socket Layer TLS Transport Layer Security HTTP HyperText Transfer Protocol or a combination thereof. In one embodiment the encrypted string is sent to the remote system using HTTP s POST method.

The remote system can generally be any system capable of communicating with the user s computer. For example the remote system can be a web server. In one embodiment the remote system can generate the response using a server script such as a PHP script PHP is a scripting language commonly used in server side applications or an ASP.NET script ASP.NET is a set of web development technologies from Microsoft Corporation . In another embodiment the remote system can generate the response using an ASAPI Apache Server Application Programming Interface module.

Recall that the system encrypted the string using the public key that was associated with the URL. Hence if the remote system is a legitimate web server for the URL it should be able to decrypt the encrypted string using the matching private key. On the other hand if the remote system is a malicious web server that is posing as a legitimate web server then it won t be able to decrypt the encrypted string because it won t have the matching private key.

For example legitimate web server may be able to decrypt the encrypted string however malicious web server will not be able to decrypt the encrypted string.

The response received from the remote system can comprise any string which enables the user s client to verify that the remote system is a legitimate web server for the URL.

In one embodiment the remote system can return the decrypted string in the response which demonstrates that the remote system has the matching private key thereby proving that it is a legitimate web server for the URL. In another embodiment the remote system can first decrypt the encrypted string to obtain the string. Next the remote system can encrypt the string using the user s public key and send it to the user s computer.

The system can then determine whether the DNS server has been compromised using the string and the response step .

Specifically the system can compare the string with the response. If they match the system can conclude that the DNS server has not been compromised. On the other hand if they do not match the system can conclude that the DNS server has been compromised. If the remote system encrypted the response using the user s public key the system can first decrypt the response using the user s private key. Next the system can compare the decrypted response with the string.

For example since malicious web server was unable to decrypt the encrypted string it may either send no response which may result in a timeout or send a response which would clearly demonstrate that malicious web server does not have the matching private key. In either case computer can conclude that DNS server has been hijacked. On the other hand legitimate web server may be able to decrypt the encrypted message and send a valid response. In this case computer can correctly conclude that DNS server has not been compromised.

In another embodiment the system can determine that a DNS server has been compromised by first sending query messages with the URL s domain name to a number of DNS servers. The system can then receive response messages from the DNS servers that contain IP addresses. Next the system can use these IP addresses to determine whether a DNS server has been compromised. For example if a particular DNS server returns the IP address of malicious web server whereas all other DNS servers return the IP address of legitimate web server the system can determine that the DNS server has been compromised. Note that this technique assumes that it is highly unlikely that multiple DNS servers would be compromised at the same time. Hence this technique may not be able to detect the security problem if multiple DNS servers are compromised. In contrast the technique that uses a URL s public key does not suffer from this drawback. Specifically even if a number of DNS servers are compromised the public key based technique can still determine whether a particular DNS server has been compromised or not.

If the system determines that the DNS server has been compromised the system can alert the user step .

Note that the system can use a number of techniques to alert the user. For example the computer can display an icon within the web browser s screen or within the web browser s toolbar. Alternatively the computer can generate an audio signal e.g. a beeping sound to alert user . In another embodiment the computer can replace the served webpage with a warning webpage which alerts the user that the website has been compromised. In addition to a warning message the warning webpage can comprise an explanation on what has happened how to fix it and a link to the originally requested webpage.

Prior art techniques typically use small icons or pop up windows to alert users about security issues. Unfortunately many users do not know the meaning of the various buttons and or icons on a web browser. Further many users turn off pop ups because they can interfere with web browsing. Additionally many users turn off the sound because they may be in a meeting or at the library. Hence it may be preferable to alert the user in a conspicuous manner albeit using a non invasive technique.

In one embodiment the system can alert the user by displaying a watermark using a web browser. The watermark can be integrated with the webpage s content. In one embodiment the system can embed a conspicuous watermark with the webpage content received from the remote system and display the modified webpage to the user. Note that users typically pay attention to the information in the web browser s main window which is used to display content from websites. Hence displaying a watermark can substantially increase the probability that the user will be alerted about the security problem. The user s web browsing experience may not be affected because the system may not display a watermark during normal web browsing rather the system may display the watermark only when the user visits a malicious website. Furthermore since the watermark is typically in the background of the webpage it is not invasive.

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art.

For example the techniques and systems described in the above disclosure can be used to detect a number of network security problems. Specifically although the invention has been described in the context of detecting a compromised DNS server the invention can generally be used to detect any compromised component of IP translation and routing. For example the invention can detect a compromised router which has been configured to send all packets destined for legitimate web server to malicious web server .

The above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

