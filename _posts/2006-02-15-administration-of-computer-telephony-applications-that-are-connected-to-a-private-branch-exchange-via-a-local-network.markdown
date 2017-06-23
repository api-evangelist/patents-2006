---

title: Administration of computer telephony applications that are connected to a private branch exchange via a local network
abstract: An administration of telephony applications conventionally using domain controller-based access authorization methods is provided such to eliminate the need for these methods. In a network where terminal devices are connected to time division multiplexed or packet-oriented network components, a terminal device establishes a communication link to a terminal device-specific adaptation for telephony applications via an interface for telephony applications, and the authorization for importing data is verified. Data is imported via the communication link to affected applications or affected services of the network. Any terminal device can be used to import the data and that no special authorizations are required for access as the proprietary/license keys that are exchanged between the terminal device and the exchange and the domain controller provide protection from unauthorized access to the exchange and to the local network connected thereto. For accessing the exchange and the domain controller, only one authorization check method is required.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08595795&OS=08595795&RS=08595795
owner: Siemens Enterprise Communications GmbH & Co. KG
number: 08595795
owner_city: Munich
owner_country: DE
publication_date: 20060215
---
This application is the US National Stage of International Application No. PCT EP2006 050938 filed Feb. 15 2006 and claims the benefit thereof. The International Application claims the benefits of German application No. 102005014522.1 DE filed Mar. 30 2005 both of the applications are incorporated by reference herein in their entirety.

The present invention relates to a method and communication system for importing data into communication networks.

In addition to analog and digital telephones computers especially personal computers with a telephone function or IP phones are increasingly being connected via a local network LAN to exchanges for example private branch exchanges. Different access procedures are usually provided in each case for importing data or information into the private branch exchanges or into the local network especially a local IP network in the sense of administering these networks.

Qualified access is provided for accessing a local network in which with the aid of a domain controller both the authentication and also the import of the data are handled. The authentication is required since only authenticated users are allowed to use the network especially to administer it. Further protection measures are for example firewalls and SSL Secure Socket Layer SS is a protocol for encrypted transmission of data.

To import data or information into a private branch exchange in order to administer said data for example special interfaces are provided which are likewise equipped with specific protection mechanisms. In this case the authentication procedures for example Hipath Licensing especially ensure that only authorized users specifically administrators import data into the private branch exchange and can administer the components concerned.

The local network LAN and the private branch exchange are administered and configured via different interfaces and using different associated protection mechanisms for example authentication and data transmission procedures. This means having to enter and reconcile the data to be imported several times.

The underlying object of the invention is to be seen as improving the importing of data into exchange systems with a local network. The object is achieved by the features of claims.

The significant aspect of the inventive method or communication system lies in the establishment from a terminal via an interface for telephone applications TAPI of a communication link to a terminal specific adaptation for telephone applications TAPI Service Provider in which case the authorization for importing the data is verified. Subsequently the data is imported via the communication link to the relevant applications or services of the network. One advantage of the invention can be seen in the fact that the importation of data into a Windows domain of a local network can be undertaken by any terminal of the exchange. A further advantage lies in the fact that no specific authorizations are required in this case since the protection license authorizations which are exchanged between the terminal and the exchange guarantee a preventive protection against unauthorized access to the exchange system and to the local network connected to it. Advantageously only one authorization method namely that of the private branch exchange PBX is needed for access to the exchange and Domain Controller DC .

TAPI involves an Application Programming Interface API for telephone applications T especially for Windows based personal computers and LANs. A TSP adapts the Application Programming Interface TAPI to the respective terminal specific characteristics. The underlying telephone functions for connection signaling and further telephone specific service features are controlled with the aid of the TSP.

A Domain Controller DC administers the terminals EG of the network N. The Domain Controller DC can be used to determine which terminals EG may log on with which password the files or network facilities to which they have access etc.

Inventively a connection to the TSP is established from a terminal EG of the PBX via the PBX. To this end a predetermined telephone number is dialed by the terminal which is identified by the TSP. As part of the connections setup an exchange of license keys is undertaken between the terminal and the PBX in accordance with Hipath Licensing. This exchange of the license keys ensures that only authorized users can obtain access to the PBX. Because of this authentication of the terminal EG or of the user a further authentication procedure for access to the TSP can be dispensed with. Usually this type of access to a Windows domain would only be possible with further extensive access authorization procedures.

After the authentication of the terminal EG or of the user the data d to be imported into the TSP is determined and stored via the terminal EG.

The method or communication system in accordance with the invention is not restricted to the exemplary embodiment but can be used in all networks for which packet oriented network components such as local network interoperate with time division multiplexing oriented network components such as telephone exchanges. Of importance here is that a communication link is established from a terminal of the network to a TSP with the available authentication procedure between terminal and PBX advantageously being used as the authentication procedure for access to the TSP. This enables the usual authorization procedures in the Windows domain TSP to be dispensed with and thus enables both the programming effort and also the operating efforts for access to the TSP to be reduced.

