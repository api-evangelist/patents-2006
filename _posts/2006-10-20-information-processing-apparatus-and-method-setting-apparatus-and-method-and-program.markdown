---

title: Information processing apparatus and method, setting apparatus and method, and program
abstract: An information processing apparatus for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip. The information processing apparatus includes: among a plurality of calculation modules for calculating the key information being individually different in accordance with predetermined algorithms, control means for causing the calculation module identified by identification information input from the outside to calculate the key information; and encryption means for encrypting data by the key information calculated.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08423771&OS=08423771&RS=08423771
owner: Sony Corporation
number: 08423771
owner_city: Tokyo
owner_country: JP
publication_date: 20061020
---
The present invention contains subject matter related to Japanese Patent Application JP 2005 310675 filed in the Japanese Patent Office on Oct. 26 2005 the entire contents of which are incorporated herein by reference.

The present invention relates to an information processing apparatus and method a setting apparatus and method and a program. More particularly the present invention relates to an information processing apparatus and method a setting apparatus and method and a program capable of specifying a module for calculating key information corresponding to a service from the outside.

In recent years various services using an IC card in which an IC chip is embedded such as FeliCa registered trademark etc. have become widespread. Such services include for example an electronic money service which enables a user to pay for goods at purchase time using an IC card a service which enables a user to use an IC card as a ticket for transportation facilities such as a train etc. a service which enables a user to take care of reward points issued by stores and the like.

In the example shown in an application server and a client terminal are connected through the Internet . A SAM Secure Application Module is connected to the application server and a reader writer is connected to the client terminal . The reader writer may be provided as being contained in the client terminal . The SAM the application server the client terminal and the reader writer are provided by a service provider for example.

Also in the example in an IC card in which a contactless IC chip is embedded is in close vicinity of the reader writer and thus the IC card can perform short distance communication with the reader writer using electromagnetic induction. The IC card is carried around by a user of the services.

The SAM is a tamper resistant apparatus and performs encryption processing and management of a key used in the encryption processing. The SAM encrypts a command supplied from the application server and outputs the encrypted command to the application server . The SAM and the IC chip individually have a common key and encryption communication is performed between the SAM and the IC chip by the transmission and receiving of the information encrypted by that key through each of the apparatuses.

The application server outputs the command command to be executed by the IC chip created in response to a request from the client terminal to the SAM . Also when the encrypted command is supplied from the SAM the application server transmits it to the client terminal . An HTTP Hyper Text Transfer Protocol server and an HTTP client are implemented in the application server and the client terminal respectively. Such data transmission and receiving are performed by the HTTP communication.

Also the application server transmits screen information to the client terminal and displays it on the display of the client terminal .

The client terminal transmits a predetermined request to the application server . At the same time when a command is transmitted from the application server the client terminal supplies the command to the IC chip through the reader writer to execute it.

The IC chip decrypts the encrypted command that has been transmitted from the SAM through the reader writer etc. and executes the command. When the content of the command is for example to instruct to rewrite electronic money the command also includes amount of money information to rewrite etc.

In a system having such a configuration for example when a user of the IC card who is a user of an electronic money service pays for goods using electronic money stored in the IC chip a payment request of the goods is transmitted from the client terminal to the application server in response to the user holding the IC card above the reader writer . The application server which has received the request creates the command Read command for requesting the IC chip to read the balance of the electronic money.

The Read command created by the application server is encrypted by the SAM and then is transmitted to the IC chip through the application server the Internet the client terminal and the reader writer . After the Read command is decrypted in the IC chip the Read command is executed.

The balance which has been read by the execution of the Read command is encrypted by the IC chip and then is transmitted to the SAM through the reader writer the client terminal the Internet and the application server as a response to the application server . The SAM decrypts the encrypted balance transmitted from the IC chip and the decrypted balance is transmitted to the application server .

Thus it is possible for the application server to check the current balance of the electronic money stored in the IC chip .

When the application server checked the balance the application server creates the command Write command for requesting the IC chip to rewrite the balance replace the previous balance with the difference when the price of the goods is subtracted from the previous balance of the electronic money.

In the same manner as the Read command transmitted before the Write command created by the application server is encrypted by the SAM and then is transmitted to the IC chip through the application server the Internet the client terminal and the reader writer . After the Write command is decrypted in the IC chip the Write command is executed. The Write command also includes information indicating the new balance. Thus the balance of the electronic money stored in the IC chip becomes the difference when the price of the goods is subtracted from the previous balance.

For example after the processing is performed such as a message notifying the completion of the subtraction from the previous balance is transmitted from the IC chip to the application server a series of processing is terminated. The payment of the price of the goods is carried out by such processing.

In this regard at the time of starting a series of processing the identification information of the IC chip the information stored in the area allocated to an electronic money service out of the memory disposed in the IC chip etc. are transmitted from the IC chip to the SAM . Mutual authentication using the key calculated by the SAM is performed between the SAM and the IC chip on the basis of the transmitted information etc. When the mutual authentication has been successful the encryption of the above described data command the decryption of the encrypted data etc. are performed using the key information calculated at the time of the mutual authentication. Japanese Unexamined Patent Application Publication No. 2004 274211 has disclosed a system in which mutual authentication is performed and the processing is performed between the SAM and IC chip that have succeeded in the mutual authentication.

The common portion is a software module provided in common for SAMs achieving any services. The common portion includes the descriptions of the algorithms for performing for example the mutual authentication with the IC chip which is performed using the key information calculated by the logic the encryption of the command created by the application server the decryption of the encrypted data by the IC chip etc.

The logic is a software module provided differently for each service for each memory area area for reading and writing data of the IC chip to be an access destination . The logic includes for example the description of the algorithm for calculating the key information used for the mutual authentication the data encryption the decryption of the encrypted data on the basis of the information obtained from the IC chip to be the communication party on the other end at the start time of the communication.

The common portion performs the encryption processing the mutual authentication the data encryption the decryption of the encrypted data using the key information calculated by the logic appropriately.

In this regard the software configuration shown in may be not included in the SAM and may be included in the application server . In this case the encryption processing is performed by the application server itself.

Now a different area is allocated to each service in the memory of an IC chip and different key information is necessary for reading and writing data stored in each area. That is to say it is necessary that logic for calculating different key information is provided for an SAM or an application server application server having a configuration of performing encryption processing by itself . When a new service different from the services provided previously is provided it is necessary for a service provider to newly provide logic for calculating the key information used for the new service to the SAM or the application server.

Accordingly in this case it is necessary for the service provider to request a manufacturer who is a supplier of the SAM or the application server to prepare for the logic for calculating the key information corresponding to the new service and thus it takes time and effort.

Also in particular when a logic included in an application server is renewed it is difficult to keep a logic algorithm for calculating the key information corresponding to a new service secret and to provide that logic because an application server is not a tamper resistant apparatus and it is easier to know the content of the software provided for the apparatus compared with a tamper resistant apparatus.

As shown in these things are caused by the fact that only one piece of logic is provided for one SAM or application server and the fact that the type of the algorithm key information calculation algorithm used in one SAM or application server is limited and the like.

Furthermore some service providers desire to determine the parameters necessary for the calculation of key information and desire a programmer of a manufacturer to set them in the SAM etc. That is to say they desire to separate a person who determines the parameters from a person who sets the parameters. However as described above it has been difficult because a manufacturer prepares the logic.

The present invention has been made in view of these situations. It is desirable for example to make it possible to specify a module for calculating the key information corresponding to a service from the outside.

According to an embodiment of the present invention there is provided an information processing apparatus for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip the information processing apparatus including among a plurality of calculation modules for calculating the key information being individually different in accordance with predetermined algorithms control means for causing the calculation module identified by identification information input from the outside to calculate the key information and encryption means for encrypting data by the key information calculated.

The control means may cause the calculation module to calculate the key information on the basis of a parameter input by an administration unit in addition to the information obtained from the IC chip as a communication party on the other end.

According to another embodiment of the present invention there is provided a method of information processing of an information processing apparatus for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip the method including the steps of among a plurality of calculation modules for calculating the key information being individually different in accordance with predetermined algorithms controlling for causing the calculation module identified by identification information input from the outside to calculate the key information and encrypting for encrypting data by the key information calculated.

According to another embodiment of the present invention there is provided a program for causing a computer to perform information processing in an information processing apparatus for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip the program including the steps of among a plurality of calculation modules for calculating the key information being individually different in accordance with predetermined algorithms controlling for causing the calculation module identified by identification information input from the outside to calculate the key information and encrypting for encrypting data by the key information calculated.

According to another embodiment of the present invention there is provided for an information processing apparatus for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip a setting apparatus for setting part of information among the predetermined information the setting apparatus including first encryption means for encrypting part of information input by an administration unit among the predetermined information second encryption means for encrypting an entire file describing information encrypted by the first encryption means generation means for generating a predetermined format file enabling the information processing apparatus to capture information on the basis of a file obtained by being subjected to encryption by the second encryption means and setting means for outputting the predetermined format file generated by the generation means to the information processing apparatus and setting part of information among the predetermined information.

According to another embodiment of the present invention there is provided for an information processing apparatus for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip a method of setting part of information among the predetermined information the method including the steps of encrypting part of information input by an administration unit among the predetermined information encrypting an entire file describing the encrypted information generating a predetermined format file enabling the information processing apparatus to capture information on the basis of a file obtained by being subjected to the encryption and outputting the generated predetermined format file to the information processing apparatus and setting part of information among the predetermined information.

According to another embodiment of the present invention there is provided for an information processing apparatus for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip a program for causing a computer to perform setting part of information among the predetermined information the method including the steps of encrypting part of information input by an administration unit among the predetermined information encrypting an entire file describing the encrypted information generating a predetermined format file enabling the information processing apparatus to capture information on the basis of a file obtained by being subjected to the encryption and outputting the generated predetermined format file to the information processing apparatus and setting part of information among the predetermined information.

In an embodiment of the present invention control is performed such that the key information is calculated by the calculation module identified by identification information input from the outside among a plurality of calculation modules for calculating the key information being individually different in accordance with predetermined algorithms.

In another embodiment of the present invention encryption processing is performed on part of information input by an administration unit among the predetermined information and then encryption processing is performed on the entire file describing the encrypted information. On the basis of the file obtained by being subjected to the encryption a predetermined format file enabling the information processing apparatus to capture information is generated. Also the generated predetermined format file is output to the information processing apparatus and part of information among the predetermined information is set in the information processing apparatus.

According to an embodiment of the present invention it is possible to specify the module for calculating the key information corresponding to a service from the outside.

According to another embodiment of the present invention it is possible to set information necessary for calculating key information while keeping the information secret.

In the following a description will be given of an embodiment of the present invention. The relationship between the constituent features of the present invention and the embodiment described in the specification or the drawings is exemplified as follows. This description is for confirming that an embodiment supporting the present invention is included in the specification or the drawings. Accordingly if there is an embodiment included in the specification or the drawings but not included here as an embodiment corresponding to the constituent features the fact does not mean that the embodiment does not corresponds to the constituent features. On the contrary if an embodiment is included here as constituent features corresponding to the present invention the fact does not mean the embodiment does not correspond to the features other than the constituent features.

According to an embodiment of the present invention there is provided an information processing apparatus for example the SAM in for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip the information processing apparatus including among a plurality of calculation modules for example logic to for calculating the key information being individually different in accordance with predetermined algorithms control means for example a control section in for causing the calculation module identified by identification information for example logic identification information input from the outside to calculate the key information and encryption means for encrypting data by the key information calculated.

The control means may cause the calculation module to calculate the key information on the basis of a parameter for example logic processing section specific information input by an administration unit in addition to the information obtained from the IC chip as a communication party on the other end.

According to another embodiment of the present invention there is provided for an information processing apparatus for example the SAM in for using key information calculated on the basis of predetermined information including information obtained from an IC chip as a communication party on the other end in order to perform encryption processing with the IC chip a setting apparatus for example the setting apparatus in for setting part of information for example logic processing section specific information among the predetermined information the setting apparatus including first encryption means for example an encryption tool in for encrypting part of information input by an administration unit among the predetermined information second encryption means for example an encryption tool in for encrypting an entire file for example the setting input file in describing information encrypted by the first encryption means generation means for example a setting support tool in for generating a predetermined format file for example the setting package file in enabling the information processing apparatus to capture information on the basis of a file obtained by being subjected to encryption by the second encryption means and setting means for example a management tool in for outputting the predetermined format file generated by the generation means to the information processing apparatus and setting part of information among the predetermined information.

In the following a description will be given of an embodiment of the present invention with reference to the drawings.

In the example in an application server and a client terminal are connected through the Internet . A SAM is connected to the application server through a SCSI Small Computer System Interface interface or Ethernet registered trademark . A reader writer dumb type is connected to the client terminal through USB Universal Serial Bus etc. Radio communication corresponding to a physical level with an IC chip a chip contained in an IC card in close vicinity is achieved by the reader writer . The SAM the application server the client terminal and the reader writer are provided by a service provider for example.

In this regard only one client terminal is shown in . However a plurality of client terminals are connected to the application server through the Internet . Also the function of the reader writer may be contained in the client terminal . The function of the SAM may be contained in the application server .

Also in the example of an IC card including an IC chip is in close vicinity to the reader writer so that it is possible to perform short distance communication with the reader writer using electromagnetic induction. The IC card is carried around by a user of the service.

As described above the SAM is a tamper resistant apparatus and performs encryption processing and management of a key to be used in the encryption processing. The SAM encrypts a command supplied from the application server and outputs the encrypted command to the application server . The SAM and the IC chip individually have a common key and encryption communication is performed between the SAM and the IC chip by the information encrypted by the key being transmitted and received through each apparatus.

The application server outputs the command created in response to a request from the client terminal to the SAM . Also when the encrypted command is supplied from the SAM the application server transmits it to the client terminal . An HTTP Hyper Text Transfer Protocol server and an HTTP client are implemented in the application server and the client terminal respectively. Such data transmission and receiving are performed by the HTTP communication.

Also the application server transmits screen information to the client terminal and displays it on the display of the client terminal .

The client terminal transmits a predetermined request to the application server . At the same time when a command is transmitted from the application server the client terminal supplies the command to the IC chip through the reader writer to execute it. The client terminal is provided with a Web browser A. Operations using the client terminal are appropriately performed on the screen displayed by the Web browser A on the display of the client terminal when accessing to the application server .

The IC chip decrypts the encrypted command that has been transmitted from the SAM through the reader writer etc. and executes the command. When the content of the command is to rewrite electronic money the command also includes amount of money information to rewrite etc.

In this manner the application server the client terminal and the reader writer that lie between the SAM and the IC chip play only a role of storing a command and a response content in a data payload portion and relaying them and are not involved with data encryption and decryption mutual authentication etc. Accordingly in the following a description will be appropriately given on the assumption that information transmitted from the apparatuses of the service provider side that is to say the application server the client terminal and the reader writer to the IC chip is information transmitted from the SAM . Also a description will be given on the assumption that information transmitted from the IC chip to the apparatuses of the service provider side is information transmitted to the SAM .

As shown in the SAM has as a portion the hardware configuration in which a CPU Central Processing Unit a peripheral including an encryption processing processor etc. and a memory are connected through an internal bus. The CPU is provided with an internal ROM Read Only Memory and an internal RAM Random Access Memory . An RTOS Real Time Operating system code a system stack a key for managing a safe area formed in an external RAM etc. which should be kept secret at a maximum are allocated to the internal ROM and the internal RAM.

The SAM has a bus scramble function capable of encrypting data and code and decrypting them when communication is performed between the CPU and the external RAM. Also the SAM has a firewall function capable of setting application programs accessible to individual areas in the external RAM.

Next a description will be given of the software configuration of the SAM . is a diagram illustrating an example of the software configuration of the SAM .

As shown in drivers including the RTOS kernel RTOS corresponding to peripheral hardware reside in the lowest layer the layer which is one layer above the hardware level . Handlers which perform processing logically integrated as a unit reside in the upper layer of the driver layer. An upper handler Privilege Module which has integrated application specific libraries etc. reside in the upper layer of the handler layer. Furthermore general applications reside in the upper layer of the upper handler layer with a firewall therebetween. In the example of user AP to user AP n are shown as general applications.

As described above the SAM has a software module provided in common for SAMs achieving any services. The common portion in is a software module provided in common. The common portion in corresponds to for example the RTOS kernel the drivers the handlers the upper handler and the firewall in .

Also referring to the logic and are shown as software modules corresponding to the user AP the user AP and the user AP n in respectively.

The logic is a piece of logic identified by a logic category 1. The logic processing key information calculation processing of a content A is performed in accordance with the algorithm described by the logic .

The logic and the logic are also pieces of logic identified by a logic category 1. The logic processing of a content B is performed by the logic among them and the logic processing of a content C is performed by the logic 

The logic for performing processing of a predetermined content identified by the logic category 2 is also provided in the SAM as for example logic etc.

That is to say the memory of an IC chip carried with a user who is a service user includes an area service area formed in order to manage necessary data for achieving each service. The SAM is provided in advance with a plurality of pieces of logic for calculating key information used for accessing reading data stored in a service area and writing data to the service area different service areas of different IC chips.

Specifically the logic and in which are identified by the logical category 1 are pieces of logic for calculating key information to be used for example for accessing a first service area in which an amount of money that is necessary data for achieving a first electronic money service etc. are managed out of the service areas formed in the memory of the IC chip.

Also the logic not shown which is identified by the logical category 2 is a piece of logic for calculating key information to be used for example for accessing a second service area of the IC chip in which an amount of money that is necessary data for achieving a second electronic money service etc. are managed out of the service areas formed in the memory of the IC chip.

In this manner a logic category is set in the SAM for each service area of the IC chip to be accessed. A service provider itself can select logic for calculating key information by specifying a logic category corresponding to a service area to be accessed that is to say a provided service.

In this regard the logic and in are pieces of logic pieces of logic for calculating different key information by different content processing for performing the logic processing of the contents A B and C respectively. Even if the access destination is the same for example if it is the first service area in which necessary data for achieving the first electronic money service is managed when an IC card to be processed is different different key information becomes necessary for accessing. Thus a plurality of pieces of logic are provided for performing individually different contents and calculating key information corresponding to one access destination area.

On the right side in logic processing section specific information and logic identification information are shown as information to be provided to the software including the common portion and the logic to 

The logic processing section specific information is a parameter to be used for calculating key information and the logic identification information is information for specifying a logic category and a logic pattern. The logic pattern is information indicating the sequence of information in which a plurality of pieces of original information for calculation of the key information are arranged to be used for operation. This information is set for example by a service provider before starting the supply of a service.

The logic identification information including the sequence 00010001 shown in is the information specifying the logic category 1 and the logic pattern 1 and is given to the common portion etc. in accordance with the operation by a service provider A.

Also the logic identification information including the sequence 00010002 is the information specifying the logic category 1 and the logic pattern 2 and is given to the common portion etc. in accordance with the operation by a service provider B. The logic identification information including the sequence 00020001 is the information specifying the logic category 2 and the logic pattern 1 and is given to the common portion etc. in accordance with the operation by a service provider C.

In this manner it is possible to constitute the logic identification information as 4 byte information including the upper 2 bytes which represent a logic category and the lower 2 bytes which represent a logic pattern.

The logic to be actually operated when the encryption processing is performed is selected from a plurality of pieces of logic provided for the SAM by the logic identification information having such a structure.

Here a description will be given of the processing for setting information to the SAM with reference to the flowchart in .

In step S the service provider system administration unit operates the controller to set the service area of the IC chip used for the service to be provided in the SAM . The controller may be implemented for example in the SAM or may be implemented in the outside apparatus of the SAM such as the application server .

The setting of the service area by the controller is accepted by the SAM in step S. In the SAM the information indicating a logic category which is the upper 2 byte information out of the logic identification information in accordance with the accepted service area is selected.

In step S the service provider operates the controller to set the logic pattern indicating the content of the processing for calculating the key information in the SAM .

The setting of the logic pattern by the controller is accepted by the SAM in step S. In the SAM the lower 2 byte information of the logic identification information is selected in accordance with the accepted logic pattern.

In step S the SAM selects logic to be used for providing the service out of a plurality of pieces of the logic provided in advance on the basis of the logic identification information.

In step S the service provider operates the controller to set the logic processing section specific information the logic selected in step S in the SAM . Thus it becomes possible for the SAM to calculate the key information in accordance with the service area of the IC chip to be processed and to perform the encryption processing. For example the above processing is performed before providing the service. The logic processing section specific information and the logic pattern set before are set in the same manner as for example storing the key information etc. in the SAM . The way of the setting of the logic processing section specific information etc. will be described later.

In step S the SAM the SAM and the reader writer connected through each apparatus performs polling for searching an IC chip being held above the reader writer .

The IC chip which has received the command transmitted by the polling from the reader writer in step S proceeds to step S and respond to the command. The response from the IC chip to the polling includes specific information set in the IC chip. Specific identification information is allocated to each of the IC chips embedded in the IC card that has been issued to a service user.

The SAM which has received the response from the IC chip in step S proceeds to step S and transmits a Request Service command requesting the notification of a list of service areas formed in the memory to the IC chip.

The IC chip which has received the Request Service command transmitted from the SAM in step S proceeds to step S and responds to it.

The SAM which has received the response from the IC chip in step S proceeds to step S and transmits a Read Without Encryption command requesting the transmission of additional information stored in the service area to be an access destination to the IC chip.

The IC chip which has received the Read Without Encryption command transmitted from the SAM in step S proceeds to step S and responds to it. The response from the IC chip to the Read Without Encryption command includes information other than the key information which is stored in the service area as additional information.

The SAM which has received the response from the IC chip in step S proceeds to step S and calculates the key information by the logic selected in advance on the basis of the specific information of the IC chip obtained in step S and the additional information obtained in step S.

In step S the SAM performs mutual authentication with the IC chip using the calculated key information. For example the SAM encrypts predetermined information using the calculated key information and transmits the obtained data to the IC chip.

In step S the IC chip decrypts the data transmitted from the SAM encrypts the data obtained by the decryption and the other data using the key information allocated to the service area to be accessed now proceeds to step S and transmits the obtained data to the SAM . The key information corresponding to the key information calculated in the SAM is allocated to the service area of the IC chip and thus it is possible for the IC chip to decrypt the data encrypted by the key information calculated in the SAM . On the contrary the SAM can decrypt the data encrypted by the IC chip using the information allocated to the service area to be accessed.

The data transmitted from the IC chip is received by the SAM in step S and the subsequent encryption processing is continued.

In this manner it becomes possible to provide a plurality of types of logic having different processing contents by one SAM by introducing the configuration enabling the selection of logic by the logic identification information logic category and logic pattern .

Also the service provider can save time and effort for requesting a manufacturer to implement new logic every time a new service is provided.

Furthermore it has become possible to set the logic specific information etc. in a data format capable of being set externally by the service provider. Thus it becomes possible to increase the freedom of the setting and to manage information at the same level of safety as the key information stored in the SAM.

In the example of IC cards A to C are shown as IC cards IC chips to be processed. The IC cards A to C are individually connected to the SAM through an IC card communication path for example a path including the application server the Internet the client terminal and the reader writer in .

Data I is stored in the service area formed in the IC card A and a key A is allocated to this area. Information a is allocated to the IC card A as card specific information. Also data I is stored in the service area formed in the IC card B and a key B is allocated to this area. Information b is allocated to the IC card B as card specific information. Similarly data I is stored in the service area formed in the IC card C and a key C is allocated to this area. Information c is allocated to the IC card C as card specific information.

Individual service areas of the IC card A to C are all the areas for storing the same service information such as the first electronic money service as described above.

Also in the example of the common processing section and the logic processing section are implemented in the SAM . The common processing section is carried out by the CPU executing the common portion out of the software configuration of the SAM .

The common processing section selects one piece of logic by the logic identification information indicating the logic category and the logic pattern corresponding to the service area specified by the control section in accordance with the operation by the service provider administration unit . The common processing section supplies the logic processing section specific information set in accordance with the operation by the service provider similarly to the selected logic to the logic processing section carried out by the logic .

The logic processing section is performed by the CPU executing one piece of logic selected by the logic identification information supplied from the control section in accordance with the operation by the service provider. As described with reference to the logic processing section calculates the keys A B and C necessary for accessing the data I in the IC cards A B and C respectively and performs the encryption processing with the IC cards A B and C respectively using the calculated keys A B and C.

That is to say the control section is performed in the controller implemented in the SAM or in the application server . The specification of the service area the logic pattern and the logic processing section specific information in accordance with the operation of the service provider is input from the control section to the SAM through the control communication path.

In the example in the key the key allocated to the service area in which the data I is stored of the data I in the IC card A is represented by 12345678h in hexadecimal and the key of the data I in the IC card B is represented by 81234567h in hexadecimal. Also the key of the data I in the IC card C is represented by 78123456h in hexadecimal.

In the example in the specific information a of the IC card A is represented by 1h in hexadecimal and the specific information b of the IC card B is represented by 2h in hexadecimal. Also the specific information c of the IC card C is represented by 3h in hexadecimal.

In the example in all the pieces of the additional information of the data I stored in the service area of the IC cards A to C are represented by 1h in hexadecimal. Here the additional information is the information other than the key information for identifying the data I. The number of the pieces of the additional information used for generation of the key information is not limited to one.

In the example in the logic processing section specific information to be given to the logic processing section is represented by 34567812h in hexadecimal. The logic processing section specific information is the information directly referenced by the logic processing section as an input parameter at the time of the calculation of the key information. The number of the pieces of the information is not limited to one.

The logic processing section inputs the specific information of the IC card the additional information I of the data I and the logic processing section specific information to generate the key for accessing the data I. For example when the IC card A is to be processed the logic processing section assumes the specific information a to be the specific information of the IC card A and assumes the key A to be the key for accessing the data I.

A service provider usually defines the logic processing section determines the value of the key the key information allocated to the service area of the data I of the IC cards A to C based on that definition and issues an IC card having the key represented by the value allocated to the service area. Thus the key information corresponding to the key information managed by the SAM becomes allocated to the service area of the IC chip. In this regard the calculation algorithm of the key information receives the specific information of the IC card the additional information I of the data I and the logic processing section specific information as input and uses arithmetic operators encryption operators etc.

Here it is assumed that there area two types of key information calculation algorithm one is a key information calculation algorithm when the service area to be processed is identified by the logic category 1 and the other is a key information calculation algorithm when the service area is identified by the logic category 2.

The key information calculation algorithm shown in is for the service area identified by the logic category 1. The key information is calculated by individually inserting the specific information of the IC card to be processed the additional information and the logic processing section specific information into the fields A B and C of in a predetermined sequence. Which of the information is inserted into which of the fields A B and C is identified for example by the logic pattern. In the example of one sequence out of six types of sequence is identified by the logic pattern.

For example as shown in when the specific information a of the IC card A is inserted into the field A the additional information I is inserted into the field B and the logic processing section specific information is inserted into the field C the key A 12345678h is calculated by operators A and B as the key information for performing the encryption processing on the IC card A.

The key information calculation algorithm shown in is for the service area identified by the logic category 2. The key information is calculated by individually inserting the specific information of the IC card to be processed the additional information and the logic processing section specific information into the fields A B and C of in a predetermined sequence.

In the example of the specific information of the IC card A is inserted into the field A the logic processing section specific information is inserted into the field B and the additional information is inserted into the field C and a predetermined key value is calculated by the operators A and B.

First a logic category and a logic pattern are set by the logic identification information and the logic logic processing section is determined. This determination is made before the execution of the processing on the IC card.

The parameters passed from the common processing section to the logic processing section when performing processing on the IC card are divided by the APIs Application Programming Interfaces included in the common processing section into the following three types.

The API of the common processing section passes the additional information I to the logic processing section . The key information calculated by the logic processing section is returned supplied to the common processing section by the return value of the API or by a value written into the buffer address passed as an input parameter. The encryption processing is performed between the common processing section and the IC card using the supplied key information.

The additional information I is supplied from the IC card to the SAM in a state of being not encrypted. Thus it is easy for the person who has not implemented the logic to know the additional information I exceptionally compared with the information provided with being encrypted. However only the additional information can be known and it is difficult to identify the other important information the logic processing section specific information etc. provided by the service provider etc. and used for the processing by the logic processing section .

The API of the common processing section passes the specific information of the IC card to the logic processing section in response to the request from the logic processing section . The specific information of the IC card is returned to the logic processing section by the return value of the API .

 3 The API of the Common Processing Section Passes the Logic processing Section Specific Information to the Logic Processing Section

The logic processing section specific information is returned to the logic processing section by the return value of the API or by a value written into the buffer address passed as an input parameter.

Finally a description will be given of a mechanism capable of setting the logic processing section specific information etc. while ensuring secrecy.

The setting apparatus having the configuration as shown in is implemented in the SAM or the controller in which includes a personal computer etc. connected to the SAM .

As shown at the upper left in the logic processing section specific information entered by the service provider is input into the encryption tool . In the encryption tool encryption is performed on the input logic processing section specific information. Thus the encryption is performed on the logic processing section specific information once.

The logic processing section specific information encrypted by the encryption tool is described as a statement of an input file provided for the service provider DB and the obtained setting input file is supplied to the encryption tool . A file including a description of the information for decrypting the encryption performed on the logic processing section specific information is supplied from the encryption tool to the setting support tool as a seed file.

In the encryption tool the encryption using the seed file for input file generated by the seed generator as a key is performed on the entire setting input file and thus the second time encryption is performed on the logic processing section specific information. The setting input file encrypted by the encryption tool is output to the setting support tool .

In the setting support tool the encryption performed on the setting input file that is to say the second time encryption on the logic processing section specific information is decrypted on the basis of the seed file generated by the seed generator . Also in the setting support tool the first time encryption performed on the logic processing section specific information described as a statement of the setting input file is decrypted on the basis of the seed file supplied from the encryption tool .

In the setting support tool a setting package file is generated on the basis of the logic processing section specific information plain text data obtained by the decryption. The setting package file is appropriately encrypted using a package key in the setting support tool .

The setting package file obtained by the setting support tool is output to the management tool and is output to the SAM by the management tool . The setting package file has a format enabling the SAM to capture various information described in that file.

The setting input file which has been generated by the encrypted logic processing section specific information being described as a statement is input into a decryption processing section . In the decryption processing section the encryption performed on the setting input file using the seed file generated by the seed generator is decrypted as described above. Also the encryption performed on the logic processing section specific information is decrypted using the seed file supplied from the encryption tool .

The setting input file which has been subjected to the decryption and has entirely become plain text data is output to a packaging section . In the packaging section a package file having a format enabling the SAM to capture the logic processing section specific information is generated the package file is appropriately encrypted using a package key and then the package file is output to the management tool .

For example the first time encryption on the logic processing section specific information using the encryption tool is performed by the service provider itself and the subsequent processing is performed by a programmer who sets information in the SAM . Thus it is possible for the service provider to set the logic processing section specific information determined by the service provider itself in the SAM without the programmer knowing the information. That is to say it becomes possible to separate the person who determines the logic processing section specific information which becomes a parameter necessary for calculating the key information and the person who sets information in the SAM .

In this regard the setting may be carried out by such a mechanism not only when setting the logic processing section specific information but also when setting the other information such as key information etc. which becomes necessary for the SAM to perform processing.

The above described series of processing can be executed by hardware or can be executed by software. When the series of processing is executed by software the programs constituting the software are built in a dedicated hardware of a computer. Alternatively the various programs are installed in for example a general purpose personal computer capable of executing various functions from a recording medium.

An input output interface is connected to the CPU through the bus . An input section including a keyboard a mouse a microphone etc. and an output section including a display a speaker etc. are connected to the input output interface . The CPU executes various kinds of processing in accordance with instructions input from the input section . The CPU outputs the result of the processing to the output section .

The storage section connected to the input output interface includes for example a hard disk and stores the programs executed by the CPU and various kinds of data. A communication section communicates with external apparatuses through a network such as the Internet a local area network etc.

Also the programs may be obtained through the communication section and may be stored in the storage section .

When a removable medium such as a magnetic disk an optical disc a magneto optical disc or a semiconductor memory etc. is attached a drive connected to the input output interface drives the medium and obtains the program and the data recorded there. The obtained program and data are transferred to the storage section as necessary and is stored there.

The program recording medium for storing the programs which are installed in a computer and is executable by the computer includes as shown in a removable medium which is a package medium including such as a magnetic disk including a flexible disk an optical disc including a CD ROM Compact Disc Read Only Memory and a DVD Digital Versatile Disc a magneto optical disc or a semiconductor memory etc. Alternatively the program recording medium includes a ROM for storing the programs temporarily or permanently a hard disk constituting the storage section etc. The storage of the programs into the program recording medium is carried out through the communication section which is a router a modem etc. as necessary or using a wired or wireless communication medium such as a local area network the Internet a digital satellite broadcasting etc.

In this regard in this specification the steps describing the programs to be stored in the program recording medium include the processing to be performed in time series in accordance with the described sequence as a matter of course. Also the steps include the processing which is not necessarily executed in time series but is executed in parallel or individually.

Also in this specification a system represents the entire apparatus including a plurality of apparatuses.

It should be understood by those skilled in the art that various modifications combinations sub combinations and alterations may occur depending on design requirements and other factors insofar as they are within the scope of the appended claims or the equivalents thereof.

