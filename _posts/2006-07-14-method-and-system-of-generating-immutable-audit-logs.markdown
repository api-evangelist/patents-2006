---

title: Method and system of generating immutable audit logs
abstract: A method to generate Immutable Audit logs (IAL) using related computer means and/or computer programs. This method and system processes audit information by cryptographic means generating one immutable digital chains that will contain at least the audit information split among the links and optionally encrypted, and this immutable digital chain is stored in a massive storage media. Each immutable digital chain is generated by including at every link at least the data resulting to apply a MAC function using a secret session key K over the result of information at current link concatenated with a previous link MAC value. The method proposes adding specific links to said immutable digital chain at regular defined intervals (‘Metronome Entry’) that contain at least a timestamp and the data resulting to apply a digital signature using a private key that is always kept secret over the metronome timestamp concatenated with previous link results.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08422682&OS=08422682&RS=08422682
owner: Kinamik Data Integrity, S.L.
number: 08422682
owner_city: Barcelona
owner_country: ES
publication_date: 20060714
---
This application is a U.S. National Phase Application of PCT International Application No. PCT IB2006 001948 filed Jul. 14 2006.

The present invention relates to the art of centralized auditing of any kind of information received from heterogeneous sources maintaining tamper resistant logs by use of cryptographic techniques and hardware implementing them.

The vast majority of today s audit logs are mutable. This means that the information recorded can be changed or deleted by both authorized users typically database administrators within the system and by unauthorized users hacking into the system from inside or outside.

Specially on those well regulated environments operating with large volumes of sensitive information it is needed to guarantee the integrity of their data with a system that eliminates the risk of data manipulation.

In today s world it is a fact that most administrations and private companies dealing with sensitive information lack of robust and cost efficient independent secure logs solutions. Typically audit logs are maintained in the custody of one or more highly privileged system user system administrators and these privileged users have rights to access and modify the logs they can add change delete log entries. It also means that logs are also vulnerable to be tampered by a malicious party that gains administrator privileges.

The industry has been addressing these deficiencies by several means including the use of WORMs Write Once Read Many devices the use of digital signatures redundant off site storage managed by different people etc. but all of them have aspects to demand a more efficient solution WORMs are slower than any other storage device and one risk is that a drive can be replaced by another one tampered digital signatures have a high computational cost that makes impossible to use standalone in systems with significant transaction volume and do not prevent the change of order and duplicating the storage systems and administration have cost issues and difficult the further audit process.

The state of art is based today in the use of digital signatures Public Key Infrastructure based accompanied by an accurate date and time stamp to provide authenticity to the data susceptible of further audit but the following issues are not addressed 

The present invention addresses both issues providing a cost efficient method and system even with significant transaction volumes guarantying immutability. The use of both symmetric message authentication hash functions to create the links and digitally signatures for chunks of links make possible to generate immutable digital chains in a cost efficient way by using standard industry hardware and software.

With the proposed invention the audit information that is recorded cannot be altered by anyone regardless of access privilege without creating clear evidence of what happened and when it happened this is logs become true immutable.

The invention proposes a centralized scalable immutable audit log server that can receive the audit information from multiple sources in an information sharing environment. The immutable audit log server processes such audit information and stores it in a way that assures the integrity of stamped record. The information could also be encrypted to assure confidentiality.

This invention uses digital signatures to provide authenticity to the audit logs and keyed hash functions to create a digital chain where all audit records are links. The algorithm proposed creates multiple parallel chains and digitally signs chunks of links instead of every single one to achieve high volume of transactions.

Symmetric session keys used at hash functions to create the digital chain are stored encrypted using the public key of the authorized auditor. An audit tool is presented to allow auditors to verify data integrity decrypt the information and generate required audit reports. The use of PKI Public Key Infrastructure assures that only authorized auditors can get access.

In with a timer it is indicated the regular intervals at which metronomes entries are added to the digital chain. The audit information M added to the link i is concatenated to the authentication tag obtained at previous link i 1 and the type and a digital signature DS function is applied using a private key to obtain the authentication tag h.

The present invention proposes to generate immutable audit logs from audit information provided by one or more information sources. It is proposed an independent unit the Immutable Audit Log server IAL server involving the following steps 

The system described herein is preferably implemented as a software program platform independent Java implementation running in a standard hardware independent server. However the system may be implemented in various embodiments using other well known implementations such as for example Microsoft s .net technology or C . The executable applications as described herein are computer programs software stored within the main memory or a secondary memory on any suitable computer running preferably Linux or Windows. Such computer programs when executed enable a processor to perform the features of the present invention. The system as disclosed herein can be implemented by a programmer using commercially available development tools. Obviously as technology changes other computers and or operating systems may be preferable in the future. In a preferred embodiment the use of an industry standard Hardware Security Module HSM to run at least the software routines in charge to generate the immutable digital chains provides even a higher degree of security.

The system is proposed in a 3 tier software architecture 1 the client or communications tier which is in charge of the connection with audit data sources 2 the business or cryptographic tier which is in charge to generate the immutable digital chains 3 and the persistent data storage tier in charge to store the data in a persistent storage mainly a database but it could also be server side files or any other legacy data stores.

Designing the application in layers or tiers is useful for many different reasons. In a multiple tier design each tier can be run a separate machine or machines allowing for improved processing performance. Depending on the design multiprocessor machines or many different independent computers can be used to improve performance. Efficient layering can give structure to the application promote scalability and ease long term maintenance requirements for the code.

To receive the audit information to store the IAL server provides an Application Programming Interface. At least two levels of communication standards are defined 

The immutable digital chains according to this invention are generated following the cryptographic protocol defined below 

In a system using encryption all entries messages mto m are encrypted using a symmetric encryption algorithm with key K the message mwill never be encrypted because mis the key already encrypted with the Auditor s public key . In a preferred embodiment AES is the encryption algorithm but others can also be used such as DES 3DES IDEA etc.

When the Auditor receives a register to audit he can check its integrity and validate it using the session keys and verifying the digital signatures using the public key of IAL server. The authorized Auditor can obtain the session keys used by decrypting them using his private key and thus verify the whole audit register.

All session keys for symmetric encryption have been encrypted under the Auditor s public key and digitally signed using the IAL server private key see section 3.1 . The Auditor can obtain the session keys by processing sequentially the register. Every time the Auditor finds an entry of type New Key Entry it can obtain the session key and check its integrity by verifying its digital signature.

The Auditor verifies each entry according to its type and its position in the chain recreating the same process followed during its generation and verifying MACs and digital signatures. The entries are verified preserving the sequence order.

If the system is compromised the attacker has no way to recreate the MACs the only way is to know the session key so he can t modify it without detection. Later the authorized Auditor will use the session keys to recreate the digital chain and check whether the entries are or aren t still intact.

Consider what happens if an attacker chooses to simply delete or truncate a register rather than attempting to modify existing entries without detection. Of course no new valid entries can be added once a register has been truncated since intermediate links will have been lost and this will be detected during verification.

Consider now an attacker that deletes entries from the end of the register in this scenario the lack of new entries could suggest the authorized Auditor that the system is still secure and what is happening is that no data have been received recently. The use of metronome entries prevents this kind of attacks metronome entries are special register entries which are made at regular intervals. If an attacker deletes entries from the end he will also delete the metronome entries or if he leaves the metronome entries their digital signatures will not match and the authorized Auditor will be able to detect the situation where the last valid entry indicates the earliest time at which the register could have been truncated .

In the case of a dishonest Auditor the session key gives the ability to falsify register entries but as there are periodic digital signatures of the records this kind of attack will also be detected because even though the MACs verification won t show errors the verification of the digital signature will.

An optional improvement considers same method but securing multiple concurrently maintained digital chains to reduce latency and take a better advantage of computational load. The IAL sever will establish as many concurrent different session keys as registers. Each register is independent of the other ones and works in an independent way. But in order to detect the removal of a whole register all registers are securely linked in a chain at creation time. In this way a register cannot be entirely deleted without detection. Additionally metronome entries are added to all current registers at the same time so all registers should have the same number of metronome entries. Metronome entries added at the same time have the same identifier value it simplifies detecting truncation . Later the authorized Auditor can validate that these metronome entries are present at verification time.

The use of an industry standard Hardware Security Module HSM where at least the pair of private public keys for digital signatures are generated guarantees the immutability of the digital chain because nobody can access the private key used to sign even those privileged users such as the system administrators.

The IAL server public key can be certified by a trusted 3party or even by the Auditor s organization to guarantee nobody will supplant the IAL server and generate fake audit logs

An industry standard Hardware Security Module HSM or a smart card or a USB token is used to generate at least one private key kept it always secret and use it to calculate and add digital signatures at least to one of said one or more immutable digital chains.

The persistent data tier is in charge to store the immutable digital chain s that are being generated. In a simple implementation the immutable digital chain s will be stored in files at server s hard drive but in a preferred implementation the immutable digital chain s will be stored in a database that could use same server s hard drives but also external storage such as Network Attached Storage NAS typically a cabinet with hard drives directly attached to the server or by fiber channel . Files and database can moreover be stored on a WORM device optionally.

The present invention may be embodied in other specific forms without departing from its basic characteristics and the described embodiments are to be considered in all respects only as illustrative and not restrictive. The scope of the invention is therefore indicated by the appended claims.

