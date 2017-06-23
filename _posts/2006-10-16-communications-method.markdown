---

title: Communications method
abstract: A computer-implemented method for establishing a communications link between a source and a target comprises:


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08837507&OS=08837507&RS=08837507
owner: Oracle International Corporation
number: 08837507
owner_city: Redwood Shores
owner_country: US
publication_date: 20061016
---
This invention relates to a computer implemented method for establishing a communications link between a source and a target and to a server adapted to perform the method.

Electronic mail e mail is extremely prolific. It represents one of the principal forms of communication between individuals both in commercial and personal arenas.

E mail is a passive mode of communication in which the clients and servers of an e mail system do not perform any processing on the content of the e mail message but simply make it available for opening and reading by the addressee. As such all e mail communication requires the addressee to open the e mail read it and if necessary act upon the message accordingly. Thus the addressee will not be aware of the existence of an e mail and hence cannot act on it if they do not have access to e mail when it is received. In some cases an e mail message may remain unopened and ignored for a long length of time for example because the addressee is on holiday.

In accordance with one aspect of the present invention there is provided a computer implemented method for establishing a communications link between a source and a target the method comprising 

In accordance with a second aspect of the present invention a server is adapted to receive data identifying a source and target wherein the server comprises a processor adapted to 

Hence the invention provides a method and server by which communications may be established between a source and a target in the event that the target cannot be reached by e mail. For example a telephone call may be initiated between the source and target. This overcomes the disadvantages with the prior art in that it is now possible to increase the accessibility of individuals by enabling various communications channels to be opened for example simply by sending an e mail.

In a preferred embodiment the data identifying the source and target are embedded in an electronic mail received by the server.

The communications profiles may identify one or more of the following communications systems electronic mail instant messaging and telephony.

The communication profiles may include data indicating the priority of a communication system with respect to other communication systems.

The communication profiles may include data indicating whether use of each communication system is inhibited in order to establish a communications link with a particular source or target.

In accordance with a third aspect of the invention a computer program comprising computer program code means is adapted to perform the steps of the first aspect of the invention when said program is run on a computer.

In accordance with a fourth aspect of the invention a computer program product comprising program code means stored on a computer readable medium performs the method of the first aspect of the invention when said program product is run on a computer.

The operation of the system shown in is best explained by way of example with reference to the flow charts of . In this example a salesman visits a potential customer and after the visit enters the customer s details into the client computer at which he is working. These details are captured as user input in step and may include the following items a unique identification number for the customer customer s ID a unique identification number for the salesman salesman s ID one or more unique identification numbers for other agents of the salesman s organisation who may be associated with this customer agent s ID s and one or more communication channels via which the customer may be contacted e.g. land and mobile phone numbers and or one or more e mail addresses .

An e mail message is then automatically composed in step . The message comprises a header a command section a data section and a footer section. The header indicates the type of message for example whether it is extensible mark up language XML based PHP Hypertext Preprocessor PHP based or Python based. The command section indicates the action to be performed by the IRP in this case to add the customer s details i.e. the user input of step which form the data section of the message. Finally the footer indicates a second action to be performed on completion of the action indicated in the command section. For example in this case it may indicate that a confirmation message should be sent to the originator of this e mail message indicating that the customer s details have been stored on the database.

This e mail message is sent in step to the server . The e mail message has an address that will cause it to be directed to the server which is adapted to receive the e mail. For example the e mail may have an address of irp domain.com and the server may be adapted to receive all e mail messages with an address that resolves to the domain.com domain. As shown in the e mail message is received from the client by the server in step . The server redirects all e mail messages such as this one with the address irp domain.com to the IRP .

The detailed structure of the IRP is shown in . The IRP comprises an e mail interface module a format analyser a PHP interpreter an XML processor a Structured Query Language SQL processor an application programming interface API processor a database discovery service a discovery data cache and an action agent .

The IRP receives the redirected e mail message via the e mail interface module . This passes the message to the format analyser which confirms that the message has the correct format that is that it has a header command and data sections and a footer. The format analyser will examine the header to determine whether the e mail is PHP or XML based and then pass the message to the PHP interpreter or XML processor respectively.

In step of the PHP interpreter or XML processor in conjunction with the SQL processor or API processor as appropriate then generates an SQL statement or an API request as appropriate and passes the resulting SQL statement or API request to the action agent respectively. For example if the e mail is PHP based and the source data required to execute the required command are stored on the database then the PHP interpreter and SQL processor will generate a SQL query from the command and data sections of the message. Alternatively if the e mail is XML based and the source data required to execute the required command are not on the database then the XML processor and API processor will generate a suitable API request from the command and data sections of the message. In either case the action agent will execute the SQL query or API request in step .

In this case the action agent proceeds by executing an SQL statement on database to create the new customer record including the details sent in the e mail message in step . The action agent may be configured to access a variety of data sources through various mechanisms. For example it may access an Oracle database using the Oracle Call Interface. Alternatively it may access a remote database via a network connection. In step the action agent composes a simple e mail in accordance with the e mail s footer to confirm that the new customer record has been created and this is sent to the salesman s client computer via the e mail interface module in step .

The API processor is capable of executing batch jobs on the server when an e mail is received with a suitable set of commands. The IRP can extract these commands from the e mail and run them on the server. Also the API processor may be used for example to respond to a command by retrieving a specified file from the server and e mailing it to a specified e mail address.

The communication channel specified in the e mail footer takes precedence over that specified for a user in the user s profile accessible by the IRP . It may be used to specify that the response should be sent to someone other than the originating user.

The above e mail format can be in the XML or PHP format. From the Type field of the e mail header the format analyser can identify whether the e mail is based on XML or PHP. If it is based on XML the format analyser will redirect the e mail to the XML processor whilst if it is based on PHP the format analyser will redirect the e mail to the PHP interpreter . The XML processor or PHP interpreter as the case may be parses the e mail based on commonly accepted XML parsing techniques or in a line by line fashion in the case of PHP.

The embedded query or command is extracted from the e mail as a result of this parsing process and passed to the SQL processor or API processor as appropriate which frames the SQL query or API request and passes it to the action agent .

The action agent uses data from a discovery data cache for establishing connections with the database . A database discovery service discover the different database installations and tables schema descriptions of the table which will be used by the action agent for executing SQL statements.

If an alternative e mail address for the response to be sent to is not specified in the e mail then an e mail address for the originating user is retrieved from the profile manager .

The data retrieved from the database or as a result of executing the API request are embedded in a return e mail which is sent to the e mail interface module for transmission to the specified e mail address or that retrieved from the profile manager .

In step an e mail would be composed by the action agent that comprises the relevant retrieved details and this e mail would be sent to the client computer via the e mail interface in step . Since the details indicate which communication channels the customer can be reached via the agent may now contact the client.

It will be apparent that using the same mechanism the customer may send an e mail with an embedded command to the IRP to update his contact details amongst other things.

Furthermore it should be clear that these enhancements to e mail have a multiplicity of uses not limited to this particular embodiment. For example a customer of a bank may wish to obtain his account balance and he may do this simply by sending an e mail with an appropriate command section and data section to the bank s server. The bank s server will then respond by interpreting the command and data sections retrieving the account balance and including this in a return e mail to the customer.

In addition the IRP is provided with functionality that can establish a communications link between a source and a target for example the agent and the customer. For example the IRP may be able to set up a telephone call using a voice over IP link between the customer and the agent using the agent s telephone number extracted from the e mail message and the customer s telephone number extracted from the profile manager .

This scenario will be explained further with reference to and . This shows a sample data structure for the profile manager and a flow chart for the operation of the invention in this scenario.

There is also shown a priority column which indicates the priority or order of preference which each user has assigned to each of their chosen communication channels. For example the agent has specified that his highest priority i.e. level 1 communication channel is his landline telephone and his lowest priority channel is instant messaging i.e. level 3 .

In addition there is an Inhibit column which allows a user to inhibit the use of a specified communication channel for a particular user. For example the agent has inhibited use of the landline telephone for establishing communication with user and the customer has specified that the agent may not establish communication using his mobile telephone.

In the customer sends an e mail to the agent at a time when the agent is not able to receive his e mail. The e mail contains an embedded command for establishing a communications link between the customer and agent. In step IRP intercepts the e mail either as a matter of routine or because it has been configured especially to do so due to the fact that the agent is unable to receive e mail at this time. The IRP parses the e mail and determines that the customer wishes to contact the agent and then retrieves in step their profiles from the profile manager.

In step the IRP subjects the retrieved profiles to a policy filter and to a preference filter. The policy filter identifies the communications channels that the agent and customer have in common in this case telephone landline and mobile and instant messaging. The preference filter then decides on the basis of the priority and inhibit data which compatible pairs of channels to try and in what order.

Thus in step an attempt is made to establish a communications link between the customer and agent. The agent s highest priority channel is his landline telephone and the customer s is his mobile telephone. However the use of the customer s mobile telephone for contact with the agent is inhibited and so the IRP first tries to establish communications between the agent s and the customer s landline telephone this being the highest priority pair of uninhibited common communication channels. If the agent is not available on his landline then his mobile telephone will be tried instead in an attempt to establish communication between the customer s landline and the agent s mobile. If both of these attempts fail then the lowest priority common communication channels i.e. instant messaging are tried. If this fails communication is not established.

It can be seen from this example that by common communication channels we mean two channels one for the source and one for the target that are compatible with each other. Thus the source s landline telephone system may be chosen as a common communication channel or system with the target s landline telephone or mobile telephone. Similarly mobile telephone is a common communication system with landline telephone or another mobile telephone. However a system such as instant messaging is incompatible with any voice telephone system and so is only considered a common communication channel with other instant messaging channels.

In establishing telephone communications the IRP is configured to use voice over IP as already described. Techniques for enabling this will be apparent to those skilled in the art but exemplary methods include use of the Dialogic D41 ESC or the H323 protocol. Effectively the IRP establishes a telephone call with each of the source and target e.g. the customer and agent and then joins the two calls together if successfully established in the same manner as a conference call.

This invention also allows for the user profiles to be easily and dynamically modified as explained above. Thus users can change the channels via which they may be contacted as necessary depending on the availability of those channels from time to time.

It is important to note that while the present invention has been described in a context of a fully functioning data processing system those of ordinary skill in the art will appreciate that the processes of the present invention are capable of being distributed in the form of a computer readable medium of instructions and a variety of forms and that the present invention applies equally regardless of a particular type of signal bearing media actually used to carry out distribution. Examples of computer readable media include recordable type media such as floppy disks a hard disk drive RAM and CD ROMs as well as transmission type media such as digital and analogue communications links.

