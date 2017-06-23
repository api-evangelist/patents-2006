---

title: Maltweb multi-axis viewing interface and higher level scoping
abstract: A method, apparatus and computer program product for navigating in a multi-dimensional space containing an electronic publication formed from predefined portions of text-based data encoded using a markup language are disclosed. A selected predefined portion is displayed in a first display region. A point on a primary axis of the multi-dimensional space corresponding to the displayed pre-defined portion is also displayed. Also, a method, apparatus and computer program product for publishing an electronic publication formed from predefined portions of text-based data encoded using a markup language are also disclosed. Predefined portions are stored in terminal nodes. Higher level nodes are provided for organising the terminal nodes into an hierarchical structure embodied in said electronic publication. Each higher level node contains the identity of a parent node, a position indicator for the higher level node and an associated identifier.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08386484&OS=08386484&RS=08386484
owner: TimeBase Pty Limited
number: 08386484
owner_city: Sydney, New South Wales
owner_country: AU
publication_date: 20061117
---
This application is a continuation of U.S. application Ser. No. 09 689 927 filed on Oct. 12 2000 now allowed which is a continuation in part of U.S. application Ser. No. 09 108 999 filed on Jul. 1 1998 now U.S. Pat. No. 6 233 592 which is a continuation of International Application No. PCT AU1998 000050 filed Jan. 30 1998 which designated the United States and was published in English and which claimed priority to Australian Application No. PO4892 filed on Jan. 31 1997. Each of these applications in their entirety are incorporated herein by reference.

The present invention relates to an electronic publishing system and in particular to an electronic publishing system for the delivery of information which is not limited as to storage space and is not governed by predetermined pathways.

The present invention relates generally to an electronic publishing system and in particular to aids for navigating in an electronic publishing system and a method of organising data in an electronic publishing system.

Conventionally information is published in document form as a printed publication or in electronic form but again using the document or book metaphor. In the past the concept of a multidimensional space in electronic publishing has been intuitively understood that is instinctively desired . However a comprehensive display discussion or treatment has been rejected by publishers and information providers as too difficult to develop and manage. Instead publishers and information providers have managed large amounts of data 

The effect of this is clearest when the dimension of time is considered. The conventional approach to information storage and publishing is centred on the notion that information is either current information ie present day or historical information ie the day before the present day and all days prior to that . Thus information is traditionally retained stored and or published sold as either current or historical information.

The effect of this has been to leave the end user with a collection of non integrated repositories and many additional tasks to do before the information is useful to them. For example the end user is required to 

To illustrate the disadvantages of conventional publishing systems an example of using such conventional techniques and publishing systems to research information is provided. If a person were interested in information regarding the powers of the Secretary under Australian legislation with respect to couples in a family relationship when and how the Secretary is restricted and what did the relevant legislation provide prior to that the person would refer to relevant legal information which is the Social Security legislation of the Commonwealth of Australia. The relevant provisions are set forth in Appendix A under the heading Example Research . This would be determined by the end user s own knowledge of the broad subject and or reference to secondary material.

The relevant legislative provision is Section 4 which in conventional electronic legal publishing systems might be found by looking for words or phrases such as family family relationships and family relationships AND social security where AND is a logical operator.

Once the above is established it can be seen from the information found that Section 4 of the Social Security Act as at Sep. 8 1996 has been amended ten times see Appendix A A1. AMENDMENTS TO SECTION AT Sep. 8 1996 .

There is however nothing in the current Commonwealth Government Reprint in either the electronic or print versions see heading EXAMPLE RESEARCH of Appendix A that allows the end user to see the text of those amendments or what part s of Section 4 were changed by them.

Thus unless the end user is prepared to refer to many statute books reading each piece of text against another the end user is not able to see easily or reliably what section 4 looked like before it was amended by any one of a number of prior amending Acts. However if the end user has a library complete enough to provide access to the prior amending Acts the person would eventually determine that Act No 105 of 1995 is the relevant amending Act.

Further it should be noted that while the Commonwealth Government Reprint indicates that the Social Security Act was amended by Act No 105 of 1995 it does not indicate what section or schedule in Act No 105 of 1995 actually amended Section 4. This again requires the end user to have access to the amending Acts themselves and renders the information provided by the Reprint as to commencement see Appendix A B. COMMENCEMENT INFORMATION FOR ACT NO 105 OF 1995 CONTAINED IN REPRINT of little utility without a copy of the amending Act No 105 of 1995 from which it can be established that Section 14 of Act No 105 amended Section 4 of the Social Security Act with respect to powers of the Commissioner see Appendix A D. AMENDING ACT 1995 NO 105 AMENDING SECTION 14 .

Eventually the required information can be found but several pieces of information need to be searched by the end user. This is an arduous time consuming tedious and complex task that must be manually repeated for each research topic and if the same search is to be carried out again.

Conventional publishing systems including electronic publishing systems that typically are speeded up paper based publishing systems are based on a book metaphor. The smallest piece of information used by such conventional publishing systems is either I an Act or Regulation in the case of reprints a whole Act or Regulation is printed again or II a word. Typically conventional publishing systems choose a word as the smallest piece when legislation is amended. To track such amendments a lawyer or their assistant may actually use scissors to cut and paste pieces of legislation or the publisher cuts and pastes each word electronically. If a whole Act or Regulation is tracked as in I above it is necessary to store each new version of an Act or Regulation in its entirety.

c it is very difficult to know which particular section or schedule has changed to track how that particular section or schedule has changed to find the relevant section of the Amending Act or Regulation that effected the section or schedule as shown in the reprint 

d if multiple changes have occurred on a particular section or schedule between reprints the latest version of the section or schedule can only be seen in the reprint 

e issues like commencement of the latest version of a particular section or schedule and so called Application Saving or Transitional Provisions are difficult to recreate and

If every single word is tracked as in II above a level of complexity results that is difficult to administer and maintain without a large number of errors. For example some legislative sections and schedules are amended several times annually.

Table 1 provides an example where Section 6 of the Income Tax Assessment Act has been amended 70 times 

It is both difficult and impractical to store the complete amendment history of every word and phrase within section 6. Trying to track all changes on such a detailed level leads to unmanageable complexity.

Largely the split between historical and present information has come about because of the publishing and information industry s own development and not because such is the desired or best way to manage information. Thus a need clearly exists for an electronic publishing system that can overcome one or more of the disadvantages of conventional techniques and systems.

International Publication No. WO 98 34179 PCT AU98 00050 corresponding to U.S. patent application Ser. No. 09 108 999 is incorporated herein by cross reference and discloses an electronic publishing system that provides a sparse multidimensional matrix of data using a set of flat file records. In particular the computer implemented system publishes an electronic publication using text based data. Predefined portions of the text based data are stored and used for the publication. At least one of the predefined portions is modified and the modified version is stored as well. The predefined portion is typically a block of text greater in size than a single word but less than an entire document. Thus for example in the case of legislation the predefined portion may be a section of the Act. Each predefined portion and the modified portion s are marked up with one or more links using a markup language preferably SGML or XML. The system also has attributes each being a point on an axis of a multidimensional space for organising the predefined portions and the modified portion s of the text based data. This system is simply referred to as the Multi Access Layer Technology or MALT system hereinafter.

Existing methods of navigating electronic publications have been derived from traditional methods used to navigate printed publications. Typical of these methods is the use of a bookmark which is merely an indicator which identifies a page or section of interest. Bookmarks are typically limited in the information provided to users. Bookmarks follow a single axis perhaps indicating the current page chapter and title of the publication. However bookmarks do not necessarily provide the user with adequate context pertaining to how the user arrived at the current page. If a user knows the exact publication desired and then navigates through the same publication a bookmark is probably adequate for the user s needs. In the event that the user has conducted a number of searches and trawled through various versions of different documents to arrive at the current page of a publication it is impossible for a bookmark to capture all the relevant information and provide the user with an adequate reading context. The book metaphor fails to address the abilities and complexities of electronic publications.

Existing methods of navigating compact disc based publications and Internet sites are typically ill suited to displaying the complex data provided by MALT. Known web solutions for example typically handle two axes sequential and hierarchical using either embedded links such as Previous Next and Contents or expandable content frames as provided in Windows Explorer. Further axes may be handled by incorporating embedded links in the body of the text. Such embedded links are point to point and provide limited navigational value to the user.

Object databases are capable of providing the required functionality but search queries employed by these databases are too complicated for untrained users both in terms of the complexity and amount of information required.

Thus a need clearly exists for a detailed context to be provided to users of electronic publishing overcoming one or more disadvantages of existing systems.

In accordance with a first aspect of the invention there is provided a system for publishing electronic information comprising 

a plurality of predefined portions of data with each predefined portion being encoded with at least one linking means and for each predefined portion the each predefined portion is stored and where such predefined portion has been modified each such modified predefined portion is stored and

a plurality of attributes each attribute being a point on an axis of a multidimensional space for organising the data.

In accordance with a second aspect of the invention there is provided a recording medium for publishing electronic information comprising 

a plurality of predefined portions of data with each predefined portion being encoded with at least one linking means and for each predefirmed portion the each predefined portion is stored and where such predefined portion has been modified each such modified predefined portion is stored and

a plurality of attributes each attribute being a point on an axis of a multidimensional space for organising the data.

In accordance with a third aspect of the invention there is provided a method for publishing electronic information comprising 

providing a plurality of predefined portions of data with each predefined portion being encoded with at least one linking means and for each predefined portion the each predefined portion is stored and where such predefined portion has been modified each such modified predefined portion is stored and

providing a plurality of attributes each attribute being a point on an axis of a multidimensional space for organising the data.

According to a first aspect of the invention there is provided a method of navigating in a multidimensional space having three or more dimensions. The method includes the steps of 

displaying in a first display region a selected predefined portion of an electronic publication formed from predefined portions of text based data encoded using a markup language each predefined portion having at least one attribute being a coordinate of an axis of the multidimensional space wherein logical connections among the predefined portions and any logical connections between the predefined portions and predefined portions of any further electronic publication data in the multidimensional space correspond to one or more axes of the multidimensional space 

displaying a point on a primary axis of the multidimensional space dependent upon an attribute of the displayed predefined portion 

displaying a second point on a second viewing axis orthogonal to the first axis the second point being derived from the first point dependent upon a logical connection between the displayed predefined portion and a predefined portion associated with the second point and

displaying information regarding the second point of the second axis in a second display region the first and second points being displayed in two display regions.

According to a second aspect of the invention there is provided a method of navigating in a multidimensional space having three or more dimensions the multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language. The method includes the steps of 

According to a third aspect of the invention there is provided an apparatus for navigating in a multidimensional space having three or more dimensions. The apparatus includes 

a device for displaying in a first display region a selected predefined portion of an electronic publication formed from predefined portions of text based data encoded using a markup language each predefined portion having at least one attribute being a coordinate of an axis of the multidimensional space wherein logical connections among the predefined portions and any logical connections between the predefined portions and predefined portions of any further electronic publication data in the multidimensional space correspond to one or more axes of the multidimensional space 

a device for displaying a point on a selected axis of the multidimensional space dependent upon an attribute of the displayed predefined portion 

a device for displaying a second point on a second viewing axis orthogonal to the selected axis the second point being derived from the first axis at the first point dependent upon a logical connection between the displayed predefined portion and a predefined portion associated with the second point and

a device for displaying information regarding the second point of the second axis in a second display region the first and second points being displayed in two display regions.

According to a fourth aspect of the invention there is provided an apparatus for navigating in a multidimensional space having three or more dimensions the multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language. The apparatus includes 

a device for displaying at least one base point and at least a first axis depending from said base point 

According to a fifth aspect of the invention there is provided a computer program product having a computer readable medium having a computer program recorded therein for navigating in a multidimensional space having three or more dimensions. The computer program product includes 

a computer program code module for displaying in a first display region a selected predefined portion of an electronic publication formed from predefined portions of text based data encoded using a markup language each predefined portion having at least one attribute being a coordinate of an axis of the multidimensional space wherein logical connections among the predefined portions and any logical connections between the predefined portions and predefined portions of any further electronic publication data in the multidimensional space correspond to one or more axes of the multidimensional space 

a computer program code module for displaying a point on a primary axis of the multidimensional space dependent upon an attribute of the displayed predefined portion 

a computer program module for displaying a second point on a second viewing axis orthogonal to the first axis the second point being derived from the first point dependent upon a logical connection between the displayed predefined portion and a predefined portion associated with the second point and

a computer program code module for displaying information regarding the second point of the second axis in a second display region the first and second points being displayed in two display regions.

According to a sixth aspect of the invention there is provided a computer program product having a computer readable medium having a computer program recorded therein for navigating in a multidimensional space having three or more dimensions the multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language. The computer program product includes 

a computer program code module for displaying at least one base point and at least a first axis depending from said base point 

a computer program code module for displaying other points axes or both derived from said base point 

a computer program code module for navigating a multidimensional space formed by said points and axes 

a computer program code module for adjusting the view so a current view point becomes a new base point.

According to a seventh aspect of the invention there is provided a method of publishing an electronic publication formed from predefined portions of text based data encoded using a markup language. The method includes the steps of 

providing one or more higher level nodes for organising the terminal nodes to correspond with a hierarchical structure embodied in the electronic publication wherein each higher level node consists of the identity of a parent node a position indicator for the higher level node and an identifier 

wherein one of the higher level nodes has a null parent identity and the position indicator indicates a position of the higher level node relative to a sibling node.

According to an eighth aspect of the invention there is provided an apparatus for publishing an electronic publication formed from predefined portions of text based data encoded using a markup language. The apparatus includes 

a device for providing one or more higher level nodes for organising the terminal nodes to correspond with a hierarchical structure embodied in the electronic publication wherein each higher level node consists of the identity of a parent node a position indicator for the higher level node and an identifier 

wherein one of the higher level nodes has a null parent identity and the position indicator indicates a position of the higher level node relative to a sibling node.

According to a ninth aspect of the invention there is provided a computer program product having a computer readable medium having a computer program recorded therein for publishing an electronic publication formed from predefined portions of text based data encoded using a markup language. The computer program product includes 

a computer program code module for providing one or more higher level nodes for organising the terminal nodes to correspond with a hierarchical structure embodied in the electronic publication wherein each higher level node consists of the identity of a parent node a position indicator for said higher level node and an identifier 

wherein one of the higher level nodes has a null parent identity and the position indicator indicates a position of the higher level node relative to a sibling node.

According to a tenth aspect of the invention there is provided a method of publishing an electronic publication formed from predefined portions of text based data encoded using a markup language. The method includes the steps of 

providing one or more higher level nodes for organising the terminal nodes to correspond with a hierarchical structure embodied in the electronic publication wherein each higher level node consists of the identity of a parent node a position indicator for the higher level node and an identifier the predefined portion includes text associated with a commentary and a scope including a start date an end date and an update date the update date being later than the start date and earlier than the end date 

further wherein one of the higher level nodes has a null parent identity and the position indicator indicates a position of the higher level node relative to a sibling node.

The present invention is directed towards a system of electronic publishing that can overcome the disadvantages of conventional information publishing both in print and electronic form. The present invention reduces if not eliminates end user problems with conventional information publishing including 

The embodiments of the invention provide an entirely new way of delivering storing and publishing information. The embodiments allow publishers to add an arbitrary number of logical connections to a set of data and even permit the publisher to display the precise evolution of that data set over time. This can be done without getting bogged down in the complexity of the logical connections and without limit as to storage space.

Frequently people desire to have more information available. However with the advent of the Internet and new technology many people suffer from information overload. The embodiments of the invention provide an easy and effective way to navigate large complex volumes of information.

Conventionally information may only contain very rudimentary i.e. haphazard hyperlinks or non existent logical connections. Thus conventional techniques of investigating how a set of data has evolved and changed over time can only be done for small data sets and are very expensive.

However with the embodiments of the invention it is possible to list all logical connections within a data set no matter how complex those connections may be. The embodiments of the invention and the principles of those embodiments described hereinafter can be applied to many different types of information such as medical scientific pharmaceutical etc. For ease of description however the embodiments are set forth in relation to legal information.

Conventionally legislation is often purchased in two ways 1 The individual Numbered Acts and Regulations that give each piece of legislation as it is passed and 2 Consolidated legislation that provides the latest consolidated version.

In the embodiments of the invention legislation is stored using every version of each Act or Regulation. The end user can search every version of any section schedule or provision. For example the required version of a section is immediately available as is the opportunity to view every preceeding and subsequent version of the same section. Also links are available to any relevant amending legislation commencing that change as well as the one that repealed it. Relevant Application Saving or Transitional Provisions can also be easily accessed.

In this manner it is possible to come to a full understanding of the legislation just by looking at the data provided through the embodiments of the invention. In contrast using conventional techniques it would have been impossible or very hard expensive and time consuming to do so.

Using conventional means a person wishing to view a particular section of a particular Act e.g. the Income Tax Assessment Act as of a particular date e.g. 30 Jun. 1996 a significant amount of work would be required to do so. The end user would need to track all Amendments since the last reprint of the legislation which may take a long time and involve referring to many volumes. This may even possibly involve using scissors and paste to actually cut and replace words. Even to figure out which Acts amended a particular section and to trace those commencement dates can be difficult time consuming and trying. However a piece of research that may have taken an experienced researcher days or even weeks can be accomplished in minutes using the embodiments of the invention.

The ability to move through information in time is outlined above. The embodiments of the invention also give additional flexibility and SCOPE to the end user. Further dimensions and interconnections may include type jurisdiction subject depth. Some examples are 

The ability to associate the relevance and interconnection contained within the information is highly advantageous to the end user.

A key aspect of the embodiments of the invention in successfully providing a multi dimensional repository of information has been in deciding the optimum storage unit . In the past publishers have chosen to either store new versions of the entire Act too big or new versions of each and every change in a method similar to red lining too complex . The first aspect of the invention was to analysis the data and choose to store every version of every section or provision level of legislation.

Structured Generalised Markup Language SGML is a recognised way to mark up data. SGML allows logical structure to be added to a document unlike HTML and word processors which only allow the addition of visual content . SGML alone is not enough to deal with text based data that contains a highly complex logical structure. The complexity increases exponentially until the complexity cannot be managed any more. Large legal publishers have stored their data in SGML but those legal publishers that are successful in dealing with their SGML based data have purposely kept their markup as simple as possible. When such publishers have tried to encode a complex structure on text based data their costs of creating the data set and maintaining the data set simply went through the roof and it became impossible to maintain the integrity of the data set.

In contrast the embodiments of the invention allow SGML data to be encoded with a much more complex structure whilst remaining manageable. Alternatively Extensible Markup Language XML may be used. For example with SGML it is possible to encode all 71 versions of Section 6 of the Australian Federal Income Tax Assessment Act in a single file that Act has about 6 000 sections but this would be utterly unmanageable when applied to the 6 000 other sections of the Income Tax Assessment Act. It becomes even more unmanageable if anybody would try to use the above method on all the sections within all other Acts and Regulations of the Commonwealth. A significant problem with using SGML even well executed SGML is that it is possible to quickly get bogged down in unmanageable levels of complexity. The embodiments of the invention have overcome these problems.

Another key aspect of the invention is the use of database technologies in the management of the SGML encoded techniques. Database technology provides a large number of ready tools to deal with complex structured data. The embodiments combine these technologies SGML XML and database technologies in an advantageous manner.

In the past traditional publishers have been limited by the size and speed of available storage systems. Only a limited amount can be reproduced in paper and until recently hard disk costs prohibited the storing of multiple gigabytes of data for both publishers and clients alike.

The embodiments of the invention have the ability to look at situations from a new and up to date view point and therefore come up with innovative conclusions that can be radically different to processes employed in the past.

Thus the embodiments of the invention provide a new computer publishing system that changes the availability of electronic information from being merely speeded up paper to being electronic information taking advantage of new electronic media by providing users with enhanced functionality of data retrieval and manipulation. The information included in the electronic format is of a publishable standard meets cost constraints and is able to be accessed under any combination of dimensions from the multi dimensional space Acts cases time jurisdiction subject . The publishing system facilitates continual updates to the data contained in the databases without any adverse effects on the operating capabilities that make the publishing system unique. Due to the extra functionality the publishing system is also designed in such a way that it can still be made available in as many different electronic media as possible and all search functions are able to operate in a time efficient manner.

The embodiments of the invention organize process and present information in a way that is significantly different than conventional structures processes and presentation. They provide an information storage and publishing system and in particular an information storage and publishing system that stores and manages large and comprehensive amounts of information eg legal information .

Publication data being preferably legal information is encoded using Standard Generalized Markup Language SGML or Extensible Markup Language XML which adds codes to the publication data and provides functionality to the data. The publication data is processed as a plurality of predefined portions which in the case of legislation is preferably at the section schedule level or provision level. A hierarchy of divisions of the legislation may be implemented. For each of the predefined portions the system stores a copy of the predefined portion and a modified predefined portion in the first database whenever it is changed. A second relational database is preferably provided that comprises plural attributes for managing the information of the first database with each attribute being a point on an axis of a multidimensional space for organising the data for publication. Alternatively a single repository of information may be practised as described with reference to the second embodiment.

The system enables the first database to be searched for one of the predefined portions of the publication data using attributes of the second database by following one or more pathways through the multidimensional space. The plurality of attributes are connected to by the plurality of links. Once the desired predefined portion is located the predefined portions can be retrieved using the attributes to define a point in the multidimensional space.

Preferably the system implements inter alia time based legislation in which sections of legislation that have been amended are not discarded and replaced with the current provision only as of the publication date. Instead each version of an amended section is retained in the first database. Thus the systems according to the embodiments of the invention are particularly advantageous in that legal information is published so that a user can obtain such sections or provisions at a particular time point.

The embodiments advantageously divide information into suitably small pieces or blocks of text each of which is a predefined portion of data and add to each piece of text either expressly or implicitly a number of attributes characteristics or descriptors . The suitability as to size of text pieces is determined by an analysis of the information and its naturally occurring structure based on knowledge of how the information is used and consumed by the end user.

This makes it possible to locate each piece or block of text at a particular point in a multidimensional space using as coordinates the attributes added to the piece or block of text. Multidimensional space refers to an area not having boundaries and that is capable of or involves more than three dimensions.

Referring to the ability to locate assign or map each node or key intersection point of the various axes or pathways is a significant functional aspect of the embodiments of the invention. This mapping is explained further hereinafter. With such coordinates known located or mapped it is possible to move easily between points in the multidimensional space .

The effect of mapping nodes as shown in is that a course through the information represented in the three dimensional space can be easily plotted. The user begins the course at node and progresses vertically downward to the fourth node . Further the plotted course is flexible to the extent of the relationships a user chooses to follow or seek out.

A first embodiment of the invention provides information management in the multidimensional space and allows movement along different axes or pathways 

In the first embodiment coding of information or data for publication is based on SGML or XML and one or more specifically developed Document Type Definitions DTD which preferably is specifically designed for legal information. Alternatively in the case of XML a Style Sheet Mechanism SSM may be used. This coding can then be related back to information retained in a specifically developed database that enables the code information to be managed and updated. For a detailed description of this aspect of the invention reference is made to Appendix C. The DTDs according to the first embodiment are set forth in detail in Appendix B. A DTD is used to define the structure of publication data preferably being legislation down to a comprehensive level. This is done by using information coded in conjunction with any one of a number of off the shelf free text retrieval software packages eg Folio Views or Dynatext to deliver the information to the end user.

A DTD describes the markup for the SGML publication data or repository which may contain legislation case law journal articles and other types of material that are stored in computer files. The files contain publication data in text form and the markup which is extra information about the text included with the text. An example of a markup is which indicates that the data from this point on is bold . A further example is

 . This markup indicates that the data from this point on is part of a section of legislation the section has an identifier of CWACT 19950104 SEC 1 and the section has a label of 1 .

There are a number of different ways to add markup to data. The first embodiment adds markup to data using SGML. Alternatively XML may be used. Still further in the case of XML being used an SSM may be used. Even within SGML there are many ways to add markup to text. Each particular way of adding markup within SGML is described by using a DTD. In the first embodiment the data for publication is marked up using a number of different DTDs. In particular the DTDs are used to mark up the logical structure of the legislation case law or journal articles. Significant amounts of information about the data for publication is stored in the markup. For example the markup provides the following information the data is a piece of Commonwealth of Australia legislation indicated by CW at the beginning of the string the section is part of an Act ACT after CW and not a regulation the act is Act No. 104 of 1995 19950104 in the middle of the string the data is a Section SEC within the Act and it is Section 1 1 at the end .

The preparation of such DTDs necessitates that the author has a sound knowledge of the data that will be marked up using the DTD. It is especially important that the underlying structure of the data to be marked up using the DTD be understood. The process of becoming acquainted with the structure of the data to be marked up is referred to hereinafter as content analysis .

In particular the section level or schedule level portion of legislation is used in the first embodiment. That is the section level portion is preferably the predefined portion of the publication data which is the smallest piece of information to be tracked. This is unlike conventional publishing systems. For example with reference to Table 1 the first embodiment stores every version of Section 6. In this manner complexity tracking every word is reduced by increasing storage. However unlike example I of conventional publishing systems the first embodiment does not lose any pertinent information 

A further advantage of tracking every version of each section or schedule is that it is possible to store some of the information not in the markup but in a database as noted hereinbefore. This simplifies the updating process.

While SGML is a powerful way of storing information it is not a retrieval medium. Therefore the stored information needs to be converted into a format that the end user of the information can access. The first embodiment uses an electronic format for retrieval. For this electronic retrieval a software application called high end text retrieval software is used. Examples of high end text retrieval software applications include Folio Views and Dynatext. In the first embodiment Folio Views is used.

Folio Views has its own proprietary markup language which is not part of the SGML family. A complete guide to the Folio Views markup language is provided in the text Folio Views Infobase Production Kit Utilities Manual Version 3.1 Provo Utah Folio Corporation 1 Jun. 1994 . Storing the data for publication in SGML allows other retrieval software applications besides Folio Views to be used.

In the first embodiment a process is implemented to convert the SGML marked up data into the format used by the retrieval software application. The example given for Folio Views hereinafter is but one example of the process involved. The conversion program basically maps the SGML markup to Folio Views markup. For example for the SGML markup the conversion process marks all ID s substantively unchanged as Jump Destinations JD s .

A Keying Guide for Australian Legislation Documents with instructions for the conversion process to Folio Views added is provided in Appendix D.

Movement through legal information can be as follows the flexibility and scope is largely up to the end user 

The application of legal information to mapped nodes is shown in . However this is only one of numerous possible applications. Information from medical technical and scientific areas are all open to the application of this invention. This diagram substitutes the technical terminology of with legal terms to show the way information appears according to the first embodiment. Further provides an example of how legal information is navigated by an end user. The user may be seeking information on the following matters 

Some general assumptions are made about legal information for the purposes of this example. Broadly legal information has two main primary sources statute law including subordinate legislation and case law. There is also secondary information such as commentary which can be added to aid interpretation. Each of these sources is interconnected and relevant to the other in terms of both past and present information. This may also apply to future information in terms of bills or other forms of uncommenced legislation. It is the association of this relevance and interconnection that is advantageous to the end user.

In the X Y and Z axes indicate time Time the legislative provision location and type eg legislation L cases C and journal articles J . To simplify the diagram only three axes are illustrated however other axes may be included dependent upon the number of dimensions of the space. In the first embodiment the multidimensional space also includes another three axes jurisdiction U subject V and depth W. Thus the space according to the first embodiment has six dimensions. In the six dimensional case it is possible to move along each axis and at the points of intersection change direction as well as find and or follow new or additional information.

The end user begins at legislation L along the Z axis where the Fences and Boundaries Act is located and then selects Section 1 of legislation indicated by L allowing the Z axis at node as of 1 Jan. 1996. The user then follows a path in the legislation through nodes and for Sections 2 3 and 4 respectively as of that same date ie the Y axis to find a definition of the term fences . Node contains Section 4 at 1 Jan. 1996 which contains the current definition of fences . This would provide information in response to above query 1 .

The user then selects Section 4 of the legislation as of 1 Jan. 1995 which in this case is an earlier version of the section prior to amendment by moving to node along the X axis . This provides information about the prior law for above query 2 . The user can then move to other information on Section 4 as of 1 Jan. 1995 by going to nodes and for case and journal article information respectively along the Z axis. For example a case on the earlier Section 4 might be identified at node and articles on interpretation of Section 4 at node . The foregoing is only one possible route through the multidimensional space of information. Other more complicated and interrelated pathways involving axes U V and W are possible. For example the user can move to axis U jurisdiction and compare the definition in Section 4 of New South Wales with that in another jurisdiction eg Victoria .

A data management database is provided to step . The database is based on a master table and a textblock table see Appendix C for further detail . The output of step is also provided to step . In step the data is consolidated the data is stored as multiple versions if applicable and uses the predefined portions of data ie textblocks . In step a filter program s is applied to the consolidated data to convert the data from SGML to the relevant format for the retrieval software application including Folio Views DynaText Topic HTML and the like. Steps item to comprise the second data management stage.

The filtered data output by step can then be provided to step . In step the filter consolidated data is imported to the text retrieval software. In step the data is provided to the delivery medium which may include CD ROM DVD magnetic tape electronic online services and other media. The output of this is the end user product . Steps item to comprise the third product manufacture stage.

The first embodiment is preferably practiced using a conventional general purpose computer such as the one shown in wherein processes for providing and managing the information are carried out using software executing on the computer. In particular the legislation database the database and the DTD s may be stored after a filtering process on a CD ROM used by the computer system and the computer system is operated using Folio View. The computer system includes a computer a video display and input devices . A number of output devices including line printers laser printers plotters and other reproduction devices can be connected to the computer . Further the computer system can be connected to one or more other computers using an appropriate communication channel such as a modem communications path a computer network or the like.

The computer consists of a central processing unit simply processor hereinafter an input output interface a video interface a memory which can include random access memory RAM and read only memory ROM and one or more storage devices generally represented by a block in . The storage device s can consist of one or more of the following a floppy disc a hard disc drive a magneto optical disc drive CD ROM or any other of a number of non volatile storage devices well known to those skilled in the art. Each of the components to is typically connected to one or more of the other devices via a bus that in turn can consist of data address and control buses.

The video interface is connected to the video display and provides video signals from the computer for display on the video display . User input to operate the computer can be provided by one or more input devices. For example a operator can use the keyboard and or a pointing device such as the mouse to provide input to time computer . Exemplary computers on which the embodiment can be practiced include Macintosh personal computers Sun SparcStations and IBM PC ATs and compatibles.

In an alternate embodiment of the invention the computer system can be connected in a networked environment by means of an appropriate communications channel. For example a local area network could be accessed by means of an appropriate network adaptor not shown connected to the computer or the Internet or an Intranet could be accessed by means of a modem connected to the I O interface or an ISDN card connected to the computer by the bus . In such a networked configuration the electronic publishing system can be implemented partially on the user s computer and a remote computer not shown coupled over the network. The legislation database the database and the DTD s can be implemented on the remote computer and the computer system can be operated using Folio View.

The operation of the first embodiment is described with reference to the screen shots shown in . All screen shots are derived from the first embodiment which uses Folio Views as the retrieval software. Broadly are screen shots illustrating navigation or movement around the information. are screen shots that show search capacities.

The title screen is presented when the process is commenced and is the first screen. A customisable toolbar is provided for searching functions. Also drop menus are provided above the toolbar . In the lower portion of the screen contains a status bar showing information relevant to searching. The Start and Main menu buttons in are both navigational tools. The Start button takes a new user to information providing help on how to use the invention. The Main Menu button takes the end user to the menu shown in the second screen shot of .

Assuming the appropriate jump link is selected in shows how the beginning of the Social Security Act appears in screen and the buttons that link the user to the provisions of the Act. This is the start of the most current version of the Social Security Act preferably. From this screen provisions of the Act can be accessed. By accessing the Table of Provisions box the Table of Provisions menu can be accessed. shows the Table of Provisions screen and illustrates how a specific provision say Section 4 can be accessed again using links . Different sections of the Act e.g. ss 3 4 and 6A may be accessed as well using corresponding jump links. Again location information is provided in the upper portion of the screen. A return button is also provided that provides access back to the beginning of the Act.

The screen shots in display a step through or navigation based way of locating information. There is also the more direct approach of searching for terms using text retrieval. The screen shots in illustrate such searching provided by the first embodiment. Screen shown in provides a customised search template that includes a time base option allowing a user to search for versions of a section for example. Screen shown in illustrates a customised search template for case law which includes a time base option connecting cases to legislation at a particular date for example. Again the ability to relate such to time and then to mix and match types of information from different sources jurisdictions is a feature provided by the coding technique used for the data and not the Folio Views software used to deliver the data to the end user.

The second embodiment stores all the information in a single repository which is marked up in SGML or XML. The information is divided in that repository into suitable pieces or blocks of text as described in the first embodiment and any relevant markup marks up a whole suitable piece or block of text by a choosing suitable pieces or blocks of text and b demanding that relevant markup belongs to a whole suitable piece or block of text the following becomes possible. A relational database consisting of records consisting of fields can be created with one and only one record per suitable piece or block of text where the actual text of each suitable piece or block of text is the content of one filed of the above record and where each item of the markup is assigned its own field in the above record.

For example a version of Section 6 of the Income Tax Assessment Act ITAA 1936 may be stored as a record in the above relational database The first field of that record contains the actual text of that version of Section 6. The next field identifies it as Section 6 of the ITAA the next field gives the date this version came into being the next field contains the section of the amending act that created this particular version the next field contains the day this version became superseded another field contains the subject s this version addresses another field contains the case s that have addressed this version of section 6 and so on. Storing the data in this way allows multidimensional database techniques to be applied to the data.

An XML DTD for implementing the second embodiment is set forth in Appendix E. It will be apparent to one skilled in the art that the second embodiment may be readily implemented in view of the foregoing description of the first embodiment which is not repeated here for the purpose of brevity and in view of the accompanying DTD set out in Appendix E.

The foregoing only describes a small number of embodiments of the invention and modifications and changes apparent to those skilled in the art can be made thereto without departing from the scope and spirit of the invention. For example the embodiments of the invention have been described with reference to SGML. The embodiments may alternatively be practiced with the extensible markup language XML as well. Also the embodiments may alternatively be practiced with a Style Sheet Mechanism SSM instead of or in addition to one or more DTDs.

A method apparatus and computer program product for navigating in a multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language are disclosed. In the following description numerous specific details are set forth. However it will be apparent to those skilled in the art in view of this disclosure that changes may be made without departing from the scope and spirit of the invention. In other instances well known features have not been described in detail so as not to obscure the invention. Whilst the invention may be preferably practised on flat files it will be apparent to a person skilled in the art that the invention may also be practised on databases. A database may be constructed from sets of flat file records. A relational database is a collection of related tables each table being a set of flat files having the same structure. The method includes the step of displaying a selected one of the predefined portions in a first display region. The display region preferably takes the form of an area of real estate on a computer screen henceforth referred to as the content frame . The method also includes the step of displaying a view into a primary axis of the multidimensional space in which the displayed preferred portion is clearly marked. This second area of the computer screen shall be referred to as the reference frame . Each frame has an associated anchor which is a title bar clearly indicating the nature of the view currently displayed in the frame. The reference anchor also contains tools for navigating the displayed axis. The method also includes the step of displaying a point on a primary axis of the multidimensional space for the displayed predefined portion.

The method may be enhanced by displaying a second point on a second axis which relates to the first axis at the first point. The second axis represents time based versions of the selected one of the predefined portions. Alternatively the second axis represents amending legislation that was applied to the selected one of the predefined portions. In another example the second axis represents case law that applied the selected one of the predefined portions. In further example the second axis represents annotations to the selected one of the predefined portions. In a yet further example the second axis represents entries of a subject index that are covered in the selected one of the predefined portions.

The embodiment of the present invention allows for a primary axis the combined hierarchical sequential or normal axis . A base node may be selected by navigating the primary axis. The method then allows for one of a number of potential axes associated with the base node to be selected and subsequently navigated. The selection is accomplished by means of activating links in the displayed base node. The reference frame is redrawn to give a view of the members of the selected axis and one member of that axis is displayed. At any point it is possible to return to the primary axis and select a new base node. Alternatively the currently displayed base node may be chosen as a new base node from which subsequent axes are derived. In this manner any number of axes may be displayed and navigated without increasing the complexity of the screen view i.e. only two frames are ever required . It is this quality which allows a complex dataset to be navigated by a non specialist end user.

By way of example a user may select a first node corresponding to a provision in the multidimensional space. The first node s locator is displayed in a first anchor to provide the user with a first point of reference. If the user is interested in different versions of the provision the user may then move to second node on an orthogonal axis being the Versions axis. The first anchor is updated and displays the locator of the second node. A second anchor displays the locator of the first node. The second anchor also displays the relationship between the first node and the second node. The user is provided with information which indicates the original provision that was being studied the provision currently being studied and the current provision s relationship to the original provision. Thus the first and second anchors and the information provided therein enable the user to navigate the multidimensional space.

Where reference is made in any one or more of the accompanying drawings to steps and or features which have the same reference numerals those steps and or features have for the purposes of this description the same function s or operation s unless the contrary intention appears.

The principles of the preferred method described herein have general applicability to electronic publishing. However for ease of explanation the steps of the preferred method are described with reference to navigating in a MALT publication. However it is not intended that the present invention be limited to the described method. It will be appreciated by those skilled in the art that a publication could include a document or a database. The invention may apply to any hierarchical XML data where any of the nodes may change independently of other nodes in the hierarchy. Typical examples might include manuals and newspapers. For example the invention may have application to the production and display of aircraft manuals. In this case each node would be a set of maintenance instructions for a part or assembly. The axes might be part number category electrical structural etc. location Boeing 737 wing wingtip assembly eddy baffle securing flange AX 703 airline United QANTAS language English French . Since each commercial aircraft is in effect a one off construct the basic information needs to be reconfigured for each plane each airline etc.

Before proceeding with a description of the embodiments a brief review of terminology is discussed hereinafter. A dataset refers to the complete set of data that is to be navigated. A dataset has a complete set of discrete objects called nodes. The dataset may be viewed as a sparse multidimensional matrix as is produced using the MALT publishing method. In the example of this specification the dataset preferably refers to a body of legislation designed for point in time searching.

A node preferably corresponds to a particular legislative provision at a particular date. A base node is a particular node from which one or more viewing axes may be derived.

A viewing axis is an ordered set of nodes derived from a single base node. The base node itself may or may not constitute part of the axis. For example given a particular provision in time three possible viewing axes are the set of all provisions in force on the same date as the base node the set of versions of the base provision in time and the set of amending provisions most recently applied to the base provision. Further viewing axes may be practised and may include case law that applied the provision annotations to the provision and entries of a subject index that are covered in the provision.

A provision for the purposes of this system is a unit of legislation having a heading and or content but not including text belonging to any sub provision that is a predefined portion of text. A provision may be an Act a schedule a chapter a section or other legislative unit. A provision has a scope in time such that when a provision is amended a new provision is created. A provision corresponds to a set of nodes each node corresponding to a range of dates in the scope of the provision.

Scope refers to a period of time during which a provision is in force. Thus a given scope is usually expressed as start and end dates. A provision s scope is determined by the dates on which the provision commenced was amended and or was repealed.

A locator is an identifier that is used to locate a particular node. For example a locator may be a date or a position such as the name of an Act and a section number.

Using the publication of legislation as an example a provision is defined as being an amendable unit of legislation. At any given moment the body of active legislation can be divided into provisions. Provisions also have a scope in time so that when a provision is amended the current provision goes out of scope and a new provision is created. The nodes of the dataset in this example are provisions with an associated date. Two locators are required to specify a particular node uniquely a position such as act and section number and a date.

There are a number of viewing axes associated with each node. As indicated in the explanation of terminology above a viewing axis is defined as an ordered set of nodes that can be derived from the current node. When XML data is converted to a series of flat files viewing axes are derived from the current node as a result of an intersection between two flat files. Two flat files intersect if common entries are contained in the fields of the respective flat files. For example a legislation flat file may contain a field Identifiers of cases that apply this provision . The legislation flat file shares a common entry with a case law flat file. Alternatively the legislation flat file may contain a field subjects covered in the provision . In this example the legislation flat file shares a common entry with a subject index flat file. Alternatively an amending legislation flat file may have a field Identifiers of provisions amended by this provision and share a common entry with the legislation flat file.

Having utilised MALT to construct a set of data encapsulating the above relationships the problem is how to access this data in a meaningful way. To provide an untrained user with full multi axis access to MALT type data whilst maintaining a consistent look and feel throughout a view consisting of a two frame screen is provided.

Situated above the content anchor is a reference frame which contains a set of links corresponding to the members of a viewing axis associated with the current base node. Reference markers indicate which of the links is currently selected. In the Normal view the content node shown in the content frame is always the same as the base node for the reference frame. In the Version view the content node and base node are initially the same but deviate when a different version is selected. In the Source view the base node is being amended and the content node is one of the amending provisions.

The reference frame has a corresponding reference anchor which describes the current viewing axis and provides buttons for navigating the sequential axis and button for accessing higher levels of the hierarchy. These levels can also be accessed via the links in the reference frame. In the example the reference anchor indicates that the user is being shown a normal view of s59 as in force on 20 Jul. 2000. This view also shows the search mode in which the text exercise of jurisdiction has been located. The buttons allow access to the next or previous occurrence of this text whilst button cancels the search. The hits links in the reference frame allow rapid access to occurrences of the search text in other parts of the document. In this respect the search mode acts very much like a separate viewing axis. The highlighting indicates the selected text. Finally the links allow access to the other viewing axes in this case Versions and Amendments .

Where appropriate the reference anchor may indicate the base node of the viewing axis. The base node is the node from which the viewing axis is derived. For example the reference anchor of which shows a Source axis view of the same provision depicted in displays the following information 

This indicates that the Source axis being viewed by the user is derived from the base provision Corporations Act s59 16 Oct. 1995 onwards . The content anchor details the amending provision which in this example is Corporations Legislation Amdt Act 1994 Cth Sch 1.

The relationship of the base node and the content node depends on the view. In the Normal axis view consisting of the sequential and hierarchical axes the base node and the content node are always the same. In the Versions axis view the base node and the content node may or may not be the same.

A view is therefore defined as the display of a particular content node in relation to a specified axis. Each view may be uniquely identified from the following the current content node the current viewing axis and the base node of the viewing axis. To further help the user in distinguishing the different viewing axes the reference frame links may optionally vary in colour content and indenting style among the views.

The reference frame of indicates that there are two versions of the provision a first version with a scope of 1 Jan. 1994 to 15 Oct. 1995 and a second version with a scope of 16 Oct. 1995 to 31 Dec. 2001. Each version of the provision is a distinct node on the Version axis. The reference anchor indicates that the user is navigating along the Versions axis view of section .

Thus the multi access viewing interface provides a user with content and reference components. Anchors uniquely identify the content node by position and date and the viewing axis by base node and axis type. Furthermore the reference frame is capable of displaying multiple viewing axes for a given base node as illustrated in .

The MALT concept encapsulates the ability to store the contents of a sparse multidimensional matrix in a set of flat file records. As previously defined the scope of a provision is a time period during which the given provision is in force. A problem arises relating to scoping a record which encompasses a number of lower level records.

Consider as an example legislation marked up for point in time searching. The body of the legislation consists of provisions or nodes where each provision is an amendable unit of legislation. For the purposes of this example each provision possesses the following four properties 

The scope of a terminal node is the period of time between the terminal node s start date and end date inclusive. The root node is deemed to be always in scope. The scope of a node which is neither a terminal node nor a root node is problematic.

For example a chapter may encompass many sections but the chapter s actual content viewed in isolation as a record is simply the chapter s title including locator if present and any notes or other attachments that apply to the chapter as a whole. All other content is contained indirectly via the chapter s descendant provisions such as parts sections and the like.

Difficulty arises in determining the scope of the chapter node. In one sense the scope of the chapter node is the sum of the scopes of the chapter node s descendants. A question then arises if for example the chapter s title is altered. The same applies to the case in which the abovementioned notes or other attachments are altered.

One solution is to create a duplicate chapter with the altered title. While effective this method has some major drawbacks. Firstly it involves a great deal of unnecessary duplication of material. Since each child provision can have only one parent new copies of every sub level have to be made. The scope of both the original and duplicate sublevels then have to be split at the date of the chapter s title change. This in turn requires each sub level to behave as though amended even though the amendment only applies to the title of an ancestor level.

A better solution is to create a new terminal sub level of the chapter which contains just the title and associated text. This sub level can then be scoped independently of the main level and other sub levels are unaffected. The sub levels retain the same parent as the chapter level itself was not affected by the amendment.

However this still leaves open the question of what to do with the scope of the chapter level. Clearly a chapter like any other provision can be created or repealed. Thus an amendment such as repeal Chapter 2A should end the scope of the chapter level as well as all of the chapter s descendants.

The scope of the stub clearly lies outside the scope of the chapter. There are three possible solutions 

Having delegated the title and other general notes to their own sublevels all content has effectively been removed from the chapter. However a chapter level is still required as removing higher levels makes all terminal nodes direct children of the root. This in turn severely impacts on the usefulness of the data when mapped to a hierarchical form such as XML.

In addition a higher level does contain one property namely one or more locators Chapter 2A in the example . While this property can theoretically be delegated to yet another sub level the practical implications are significant. In particular the locator reflects the ordering of the chapter amongst its siblings. If for example an amendment renumbers chapter 2A to chapter 4 this gives rise to the issue of whether the chapter comes before or after chapter 3 in either a flat file or in XML. For this reason the locator is the sole property preserved by a higher level node throughout the higher level node s scope. If the position is changed then a new level and sub levels is created.

This still leaves the problem of the scope of a higher level. For example if Chapter 2A is repealed and a new unrelated chapter 2A immediately takes the place of the repealed Chapter 2A a problem is potentially presented as to two overlapping scopes for the same provision. The scope of the original node has to be terminated otherwise there are two Chapter 2As in scope contemporaneously. The co existence of two Chapter 2As poses a detrimental impact on the ability to navigate and search the legislation under consideration. In the situation in which the original Chapter 2A has a repeal stub the original Chapter 2A s scope may overlap the new Chapter 2A since the stub may continue indefinitely in time. Among many possibilities a repeal stub may be provided while Chapter 2A does not exist.

Other problems include repeal or substitution of a higher level node renumbering relocation of a higher level node renaming without renumbering relocation of a higher level node elevation or demotion of a higher level node within the hierarchy e.g. changing a part to a chapter or a division to a subdivision and insertion removal of an intermediate level heading node requiring that nodes which follow and are were according to their type inferior to that heading node become cease to be children of that node.

In order to resolve these problems the following design rule is applied Higher level nodes may have neither scope nor content. In other words a non terminal node must be a container only. A non terminal node s only properties are a parent indicator a position within the parent and optionally a locator. Any content notionally belonging to such a node such as a chapter title is assigned to a new terminal child node. A terminal child node may contain a label which is preferably a title but can be or include other data related to the parent node. The new child node preserves the scope of the title so for example a single chapter may possess a number of temporally disjoint title nodes.

Higher level scoping has a number of surprising but useful consequences. In particular a higher level provision is in itself not subject to amendment. Thus an instruction such as Repeal Chapter 2A actually terminates the scope of all of Chapter 2A s constituent terminal nodes. The chapter node having no scope of its own is unaffected.

Additionally the previously described problem pertaining to the overlapping scope of the 2A repeal stub disappears. Embodiments of the invention utilise the following approaches. When Chapter 2A is repealed the associated scope of all terminal nodes within Chapter 2A is terminated. In a first embodiment a new Chapter 2A is enacted immediately after the original chapter is terminated. The new Chapter 2A has an associated scope commencing on the day after which the original Chapter 2A was repealed. In a second embodiment a repeal stub is introduced. A repeal stub in the preferred embodiment is a title with an attribute marking this title as being of the type repeal stub . The repeal stub has an associated scope with a start date corresponding to the date after which Chapter 2A was repealed. The repeal stub has the Chapter 2A node as a parent. If a new Chapter 2A is later enacted the scope of the repeal stub is terminated and the scope of the terminal nodes of the new Chapter 2A will begin on the day after the end date of the repeal stub s scope.

Thus a request for Chapter 2A on date X returns a description of Chapter 2A that was valid on that date. In the event that the request is for a date on which the chapter is repealed the fact that the chapter is not in force having been repealed on or before that date will be returned.

A portion of Document Type Definition DTD code which is used to enable higher level scoping appears in Tables 2 to 8 below 

Consider an example consisting of an Act with two chapters the second chapter containing two sections as shown by the system of . A root node represents the Act. The root node has no parent and all other nodes descend from the root node . The first chapter of the Act is represented by a higher level node . As a higher level node node has neither scope nor content. Node has the following properties a parent being the Act node a position within the parent node being 1 and an optional locator being Chapter 1 . Node has two descendant nodes . Node has the following properties a parent being the node identified by its locator Chapter 1 a position within the parent node being 1 an optional locator being Chapter 1 Description scope being 1 Jan. 1998 onwards and content relating to the title or textual description of the first chapter of the Act under consideration. Node has the following properties a parent being the node identified by its locator Chapter 1 a position within the parent node being 2 an optional locator being Chapter 1 Note scope being 1 Jan. 1998 onwards and content providing general notes or comments pertaining to the first chapter of the Act under consideration.

A second higher level node represents the second chapter of the Act. Node has two sections. Node has the following properties parent being the Act node a position within the parent node being 2 and an optional locator being Chapter 2A . Node has five child nodes and each of which is a terminal node in this example. Node has the properties parent being Chapter 2A a position within the parent being 1 an optional locator being Chapter 2A description scope being 1 Jan. 1998 30 Jun. 1998 and content being Company Registration . Node has the properties parent being Chapter 2A a position within the parent being 2 an optional locator being Chapter 2A description scope being 1 Jul. 1998 onwards and content being Registering a Company . Node has the properties parent being Chapter 2A a position within the parent being 3 an optional locator being Chapter 2A note scope and content. Node has the properties parent being Chapter 2A a position within the parent being 4 an optional locator being Section 11 scope and content. Node has the properties parent being Chapter 2A a position within the parent being 5 an optional locator being Section 12 scope and content.

The different scopes of nodes and allow nodes to co exist without overlapping. Nodes may share the same locator but the combination of locator and scope uniquely identifies the nodes. Nodes reflect the amendment of the title of Chapter 2A from Company Registration to Registering a Company . The scopes of nodes indicate that the amendment came into effect on 1 Jul. 1998.

In accordance with a further embodiment higher level scoping is extended to facilitate commentaries subject indices and similar material. When considering legislation any amendment results in the production of a modified portion. However when considering commentaries two types of amendment to the commentary are possible. In the first scenario corresponding to the legislation example the scope of the current predefined portion of commentary is terminated and a new predefined portion is provided. The new predefined portion has a scope commencing on the day after the expiration of the current predefined portion. In the second possible scenario the current predefined portion of the commentary is amended without a second predefined portion being created.

The scope of commentary portions is extended to include three dates a start date an update date and an end date. Referring to a screen shot shows a commentary. The commentary was created on 1 Jul. 2000 as seen from the amendment bar . The commentary has the following scope properties start date of 1 Jul. 2000 no update date and no end date. shows a screen shot of the commentary of at a later date. The amendment bar indicates that the commentary was last updated on 1 Sep. 2000. Thus the scope of the commentary now has a start date of 1 Jul. 2000 an update date of 1 Sep. 2000 and no end date. shows a further screen shot of the commentary of at a yet later date. The amendment bar indicates that at least one further amendment has been applied to the commentary since the update of 1 Sep. 2000 indicated at in . The amendment bar of shows that the last update date of the commentary is 1 Oct. 2000. Therefore the scope properties of the commentary now read First portion start date of 1 Jul. 2000 end date of 30 Sep. 2000 Second portion start date of 1 Oct. 2000 and no end date.

In a further embodiment XML data may be divided into predefined portions and stored as a collection of flat files. In an example the flat files take the form of a relational database. There is a one to one correspondence between the XML data and the relational database. The hierarchy of the XML data is expressed via the implementation of higher level scoping. A single record is provided with an identifier and other terminal nodes are provided in which to store the remainder of the information.

The process for navigating in a multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language can be implemented using a computer program product in conjunction with a computer system as shown in . In particular the process for navigating in a multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language can be implemented as software or computer readable program code executing on the computer system .

Similarly the process for publishing an electronic publication formed from predefined portions of text based data encoded using a markup language may also be implemented using a computer program product in conjunction with the computer system shown in .

The computer system includes a computer a video display and input devices . In addition the computer system can have any of a number of other output devices including line printers laser printers plotters and other reproduction devices connected to the computer . The computer system can be connected to one or more other computers via a communication input output I O interface using an appropriate communication channel such as a modem communications path an electronic network or the like. The network may include a local area network LAN a wide area network WAN an Intranet and or the Internet .

The computer includes the control module a memory that may include random access memory RAM and read only memory ROM input output I O interfaces a video interface and one or more storage devices generally represented by the storage device . The control module is implemented using a central processing unit CPU that executes or runs a computer readable program code that performs a particular function or related set of functions.

The video interface is connected to the video display and provides video signals from the computer for display on the video display . User input to operate the computer can be provided by one or more of the input devices via the I O interface . For example a user of the computer can use a keyboard as I O interface and or a pointing device such as a mouse as I O interface . The keyboard and the mouse provide input to the computer . The storage device can consist of one or more of the following a floppy disk a hard disk drive a magneto optical disk drive CD ROM magnetic tape or any other of a number of non volatile storage devices well known to those skilled in the art. Each of the elements in the computer system is typically connected to other devices via a bus that in turn can consist of data address and control buses.

The method steps for navigating in a multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language are effected by instructions in the software that are carried out by the computer system . Again the software may be implemented as one or more modules for implementing the method steps.

In particular the software may be stored in a computer readable medium including the storage device or that is downloaded from a remote location via the interface and communications channel from the Internet or another network location or site. The computer system includes the computer readable medium having such software or program code recorded such that instructions of the software or the program code can be carried out. The use of the computer system preferably effects advantageous apparatuses for navigating a multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language and for publishing an electronic publication formed from predefined portions of text based data encoded using a markup language in accordance with the embodiments of the invention.

The computer system is provided for illustrative purposes and other configurations can be employed without departing from the scope and spirit of the invention. The foregoing is merely an example of the types of computers or computer systems with which the embodiments of the invention may be practised. Typically the processes of the embodiments are resident as software or a computer readable program code recorded on a hard disk drive as the computer readable medium and read and controlled using the control module . Intermediate storage of the program code and any data including entities tickets and the like may be accomplished using the memory possibly in concert with the storage device .

In some instances the program may be supplied to the user encoded on a CD ROM or a floppy disk both generally depicted by the storage device or alternatively could be read by the user from the network via a modem device connected to the computer . Still further the computer system can load the software from other computer readable media. This may include magnetic tape a ROM or integrated circuit a magneto optical disk a radio or infra red transmission channel between the computer and another device a computer readable card such as a PC card and the Internet and Intranets including email transmissions and information recorded on Internet sites and the like. The foregoing are merely examples of relevant computer readable media. Other computer readable media may be practised without departing from the scope and spirit of the invention.

The process for navigating in a multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language can be realised in a centralised fashion in one computer system or in a distributed fashion where different elements are spread across several interconnected computer systems.

The process for publishing an electronic publication formed from predefined portions of text based data encoded using a markup language may also be implemented using a computer program product in conjunction with the computer system of in a manner similar to that which has just been described.

Computer program modules or computer program in the present context mean any expression in any language code or notation of a set of instructions intended to cause a system having an information processing capability to perform a particular function either directly or after either or both of the following a conversion to another language code or notation or b reproduction in a different material form.

In the foregoing manner a method an apparatus and a computer program product for navigating in a multidimensional space containing an electronic publication formed from predefined portions of text based data encoded using a markup language are disclosed. Further a method an apparatus and a computer program product for publishing an electronic publication formed from predefined portions of text based data encoded using a markup language are disclosed. While only a small number of embodiments are described it will be apparent to those skilled in the art in view of this disclosure that numerous changes and or modifications can be made without departing from the scope and spirit of the invention.

Note a prohibited relationship for the purposes of section 23B of the Marriage Act 1961 is a relationship between a person and 

Note Fields are out of database structure order in the examples because they appear at different places in the legislation to the structure used in the database tables.

This is the most important field in the database as it ties all the remaining fields and their information together.

For the example used here that is the Social Security Act this will be Act 19910046. This is arrived at by combining 

All three parts of the ID are important. Inputting the right type that is Act for ACTS and Reg for REGULATION etc. and the right year and number is critical as only the correct combination of all three will give the required accuracy.

In the ID field the year and number are separated by a hyphen. Also four digits must be used for the year number thus 0046 and not 46 is used for the ACT S number in this example.

An important point to note is that it is possible for an ACT or REGULATION to be known as say the Federal Law Act 1996 but to be Act No 2 of 1997 so that its ID then will be Act 19970002

For ACTS use the Table of Acts at the column Date of Assent. The entry for Act No 46 1991 being the entry for the principal ACT that is the Social Security Act is the place to look and the second column shows the date of assent as 23 Apr. 1991 see d below .

For REGULATIONS use the Table of Statutory Rules at the column Date of Notification. The entry for REGULATION No 36 1990 being the entry for the principal REGULATIONS that is the Cash Transactions Reports Regulations is the place to look and the second column shows the date of notification as 27 Feb. 1990 see e below .

 1 The Cash Transaction Reports Regulations in force under the Cash Transaction Reports Act 1988 as shown in this reprint comprise Statutory Rules 1990 No. 36 amended as indicated in the Tables below.

This usually appears in Section 1 of an ACT or regulation 1 of a REGULATION. This is the best place to take the name from as it is the legislated official way that the ACT REGULATION etc. is to be referred to etc. See f below.

You should include the year even though it is part of the ID and also the words ACT or REGULATION. This will firstly provide a cross check as normally these should match. It will also indicate those ACTS or REGULATIONS where the Short Title Year is different to the Year and Number in the ID field.

This is the best place to take the date of commencement from as here it is part of the legislation the law and therefore always correct even if its wrong . If taken from the Table of Acts or Table of Regulations an error would not be correct even if not made by us because technically Tables Title Pages and even side margin notes are not considered part of legislation.

The example given at g above is a simple form of commencement in that one date is stated in Section 2.

Note With respect to the calculation of time as for example in the case of commencement 28 days after assent Section 36 of the Acts Interpretation Act affects how this is done. Section 36 provides 

The above will be handled in Australia with respect ot those ACTS or REGULATIONS to which this applies.

This is the opposite of commencement that is it indicates when the whole of an ACT or REGULATION or some Part Section or regulation in an ACT or REGULATION ceases to have effect.

Note because the expiry is provided for in the ACT or REGULATION itself this is different to a repeal. The effect is however the same.

Sections or Regulations relevant to this field are headed Sunset clause or Sunset provision see h below.

Note the use of the words unless sooner repealed in the examples below. This means entries will need to be checked or reviewed to ensure that ACT or REGULATION has not been sooner repealed.

The date or timing of expiry is indicated expressed in a few different ways by a specific date see i below.

Note the example above uses the words cease to be in force and the one below the words ceases to have effect . The result is still the same for our purpose.

This Field provides more specific information about the type of legislation. It is different to the ID Field described above which gives the legislation a unique ID. This Field uses three single character codes to describe the legislation.

There is nothing specifically unique or different in a principal ACT or REGULATION that makes it easy to identify. By elimination it is however possible to say what is not a Principal ACT or REGULATION. This is done by looking at the ACT or REGULATION S title information. Amending Acts or Regulations which are dealt with next usually contain the word s Amending Amendment Repeal or Statute Law Revision in their Short Title. Another indicator in the case of ACTS is that the Long Title will also contain the word s Amending Amendment Repeal or Statute Law Revision REGULATIONS however do not have a Long Title .

The example marked K and J below shows the Long and Short Titles for a Principal Act known as the Trade Practices Act. Compare these examples with the ones marked L and 20 M below .

Note A principal ACT or REGULATION can contain amendments to other ACTS or REGULATIONS. It therefore still needs to be considered for its effect on other ACTS.

Amending ACTS or REGULATIONS will not generally exist in their own right in the consolidated information for which we are creating the data base. The changes they effect will nearly always become part of the Principal ACT or REGULATION.

There are some rare exceptions to the above point however which will need to be identified the way to do this most effectively will be to identify them in Australia and provide a list or table of what these ACTS and REGULATIONS are .

Amending ACTS or REGULATIONS will nearly always contain the word s Amending Amendment Repeal or Statute Law Revision in their Short Title.

For Acts but not Regulations there is also a Long Title at the very beginning of the Act usually before Section 1 which will also contain the word s Amending Amendment Repeal or Statute Law Revision .

The example marked L and M below shows the Long and Short Titles for the Amending ACT known as the Trade Practices Secondary Boycotts Amendment Act 1979.

Below are two examples of these. Usually this is clean up legislation which makes many changes and often effects a larger number of ACTS. They can be specific as in the case of the Decimal Currency example or they can be general as in the case of the 1973 example.

They can both change amend Parts Divisions and Sections of ACTS and REGULATIONS and or delete repeal whole ACTS and REGULATION or Parts Divisions and Sections.

The above can usually be spotted by the use of words such as Consequential Provisions Laws Amendment Legislation Amendment Miscellaneous Provisions in their Short Titles.

Below are two examples of these. One where the term Legislation is used in the title indicating that more many ACTS are being repealed. Again this is often clean up legislation which repeals many ACTS whose purpose or reason for being has lapsed. Alternatively as the second example indicates Repeal ACTS can be specific effecting the repeal of only one ACT.

Indicates that the type of the ACT or REGULATION is not known or cannot be determined. These records will the be handled in Australia.

The information required for this field does not appear in the Commonwealth Data as presently supplied to held by us. It will need initially to be obtained in the form of a list of existing reprints and their numbers and be added to both the Commonwealth data and the data base as a once only job. It will then need to be maintained on a monthly basis using the two AGPS Pamphlet Publications known as ACTS TABLES for Acts and STATUTORY RULES TABLES for Regulations the last page in each contains this information for the current year. Note where the Pamphlets are not available or the reprint number is not known or unavailable then the number 999 should be used to indicate this.

Each of the two tables from the Pamphlets contains the name of the Reprinted ACT or REGULATION in alphabetical order but see Statutory Rules example below followed by the date of reprint then followed by the words Reprint No. and a number. It is this last number that needs to be entered.

Note Statutory Rules are listed by their parent Act the Act under which the are made appearing in Italic as shown in the example below .

Like the Reprint Number discussed in B 07 above the information required for this field does not appear in the Commonwealth Data as presently supplied to held by us. It too will need initially to be obtained in the form of a list of existing reprints and be added to both the Commonwealth data and the data base as a once only job. It will then need to be maintained on a monthly basis using the two AGPS Pamphlet Publications known as ACTS TABLES for ACTS and STATUTORY RULES TABLES for Regulations the last page in each contains this information for the current year.

Each of the two tables contains the name of the Reprinted ACT or REGULATION in alphabetical order but see Statutory Rules example below followed by the date of reprint then followed by the words Reprint No. and a number.

For this field it is the Date preceding the Reprint Number that needs to be entered. For examples see the examples at B 07 above.

Note Again where the Pamphlets are not available or the reprint date is not known or unavailable then the date 00 00 00 should be used to indicate this.

TEXTBLOCK entries will not normally be required for ACTS or REGULATIONS which are either Principal or Reprinted ACTS or REGULATIONS. But note that in the case of Principal ACTS there are exceptions namely where the Principal ACT or REGULATION also amends or repeals other ACTS or REGULATIONS.

This field simply repeats the information obtained in B 01 above. Its purpose is to link this Table with the MASTER TABLE by way of the same ID. For the example in B 01 for the Social Security Act the ID was Act 19910046. This ID would be repeated in this field.

This field is for the ID of the specific Part Section or regulation in an Amending ACT or REGULATION that causes a change amendment to happen.

Textblock ID2 see C 04 below on the other hand records the ID of the specific Part Section or regulation in an Amending Act or Regulation that is changed amended .

Following is an example of an amendment to the Social Security Act which shows how the information required for this field is obtained.

Please note there are several ways in which Amending ACTS and REGULATIONS are presented. However the information required for this ID field is present in all cases. This first example shows the things to look for and the next example show some of the variations possible.

This field is for the ID of the specific Part Section or regulation in an Amending ACT or REGULATION that is changed amended .

Textblock ID1 see C 03 above on the other hand records the ID of the specific Part Section or regulation in an Amending ACT or REGULATION that causes a change amendment to happen.

Following is an example of an amendment to the Social Security Act which shows how the information required for this field is obtained.

Please note as with Textblock ID1 there are several ways in which Amending ACTS and REGULATIONS are presented. However the information required for this ID field is present in all cases. This first example shows the things to look for and the next example shows some of the variations possible.

This field is for the date an amendment or repeal of a specific Part Section or regulation commenced. See also B 04 for information on commencement.

Below is an example of a commencement provision from an amending ACT. Note how various sections of the amending ACT are allocated a date of commencement. Using the Section identified in TEXTBLOCK ID1 the date of commencement can be identified and entered in this field.

Thus if the TEXTBLOCK ID1 field were ACT 19950105 SEC 8 then the date information required for this field would be 1 Jul. 1995. See DD below.

This field provides for amendments that are enacted for a period of time for example during a special event such as the Olympics.

Note Expiry provisions are rare and should only be added if clearly specified in the data as in the example below.

All files produced must be parsed against the relevant DTD and each table should be viewed using a suitable Table renderer to make sure that they have been coded correctly.

No local modifications must be made to the supplied DTD s. If there are any situations in which it is thought that a change to a DTD is required then the requested change and the reasons for it must be submitted to SGMLSE. If a change is deemed necessary then the DTD will be changed in the UK and resupplied. This is necessary to maintain consistency in the DTD s being used at both ends in the process.

The SGML files that will be supplied have already been partially processed but will be invalid according to the DTD especially the tables .

Carriage return characters must not appear in any element which has PCDATA within its content model. If it is wished to use carriage return characters to shorten line lengths then they must be placed in position s where they will be ignored by an SGML parser e.g. in places where PCDATA is not allowed or within start and end tags in places where separator characters are allowed.

Element and attribute names are case insensitive. They may be entered in either uppercase lowercase or a mixture.

Attribute values are usually case insensitive. The only time that they are case sensitive is when they have a declared type of CDATA in which case the string values should be entered directly as they appear in the text.

No non empty elements have omissible start or end tags but the empty end tag can be used to end the currently open element. A carriage return character can not occur within an empty end tag.

There are four DTDs and a common element declaration that are used to define the structure of the legislation.

This DTD has the public identifier SGMLSE DTD 1.0 Regulations EN and contains the declaration for the regulations. It has two parameter entity references which include SGMLSE DTD 1.0 Act EN and SGMLSE DTD 1.0 Regulation EN . The file regs.sgm produced by the Perl script regs.p conforms to regs.dtd and calls in all acts as parameter entities.

This DTD has the public identifier SGMLSE DTD 1.0 Acts EN and contains the declaration for the acts. It has a parameter entity references which includes SGMLSE DTD 1.0 Act EN . The file acts.sgm produced by the Perl script acts.pl conforms to acts.dtd and calls in all acts as parameter entities.

This DTD has the public identifier SGMLSE DTD 1.0 Regulation EN and contains the declaration of a regulation.

This list of elements has the public identifier SGMLSE ELEMENTS 1.0 Common Elements EN and includes element and entity definitions common to all document types.

The character entities allowed have been selected from the ISO public sets isogrk1 isogrk3 isolat1 isonum isopub and isotech.

These characters are translated one to one to the equivalent character in the Times New Roman True Type font.

all have a required label attribute Ibl . Unique identifiers should be generated for these elements. The label for these elements is the preceding number or letter WITHOUT any punctuation or parentheses. For example 

All cross references point directly to a target by providing the id of the target as the value of an attribute of the xref element. For details of the format of cross reference identifier strings see the description of the xref element below.

That is it contains a required title element followed by an optional header element followed by 1 or more act element.

The insert date attribute should be used to insert the date YYYYMMDD that the REG was inserted. The insert leg should be used to insert the ID of the legislation that inserted the REG. The repeal date attribute should be used to insert the date YYYYMMDD that the REG was repealed. The repeal leg should be used to insert the ID of the legislation that repealed the REG. The amend date attribute should be used to insert the date YYYYMMDD that the REG was amended. The amend leg should be used to insert the ID of the legislation that amended the REG.

The title gets marked up as Level Heading Level 1 . The period between the insert date and the repeal date or amend date that is the period during which the above element was in force gets marked up as follows 

The Folio Views markup used is Groups. See the manual for explanations. We will use three kinds of groups Inforce yyyy Inforce yyyy mm and Inforce yyyy mm dd yyyy can be any year mm can be any month from 1 12 and dd can be any day from 1 31 . If the element was valid throughout a year yyyy the element becomes a member of the Inforce yyyy group. If the element was valid only for some months within a year it becomes a member of the relevant Inforce yyyy mm groups. If the element was only valid for some days within a month the element becomes a member of the relevant Inforce yyyy mm dd groups. Example 

If the element was valid from Jan. 7 1994 to Jul. 4 1996 then the element belongs to the following groups Inforce 94 07 Inforce 94 08 Inforce 94 09 Inforce 94 10 Inforce 94 11 Inforce 94 12 Inforce 95 Inforce 96 01 Inforce 96 02 Inforce 96 03 Inforce 96 04 01 Inforce 96 04 02 Inforce 96 04 03 Inforce 96 04 04 Inforce 96 04 05 Inforce 96 04 06 and Inforce 96 04 07.

Note that the element is not part of the Inforce 94 group because the element wasn t in force throughout of 1994. Nor is the element part of the Inforce 96 04 group because the element wasn t in force throughout April 1996.

If the enduser wants to search for all elements that are valid as of a particular date then the enduser can enter that date in a Query Template in the form DD MM YYYY. The Query Template then searches the Folio Views infobase for all elements that belong to the groups Inforce yyyy Inforce yyyy mm and Inforce yyyy mm dd.

The noteref gets marked up as a popup link. The text of the note becomes the text within the popup link.

The title gets marked up as Level Heading Level 2 . Dates get treated the same way as in Regs DTD Elements. See there for details.

The insert date attribute should be used to insert the date YYYYMMDD that the ORDER was inserted. The insert leg should be used to insert the ID of the legislation that inserted the ORDER.

The repeal date attribute should be used to insert the date YYYYMMDD that the ORDER was repealed. The repeal leg should be used to insert the ID of the legislation that repealed the ORDER.

The amend date attribute should be used to insert the date YYYYMMDD that the ORDER was amended. The amend leg should be used to insert the ID of the legislation that amended the ORDER.

The title gets marked up as Level Heading Level 3 . Dates get treated the same way as in Regs DTD Elements. See there for details.

Provisions get ignored The Table of Provisions gets generated by the conversion program from the following Elements Part Chapter Order Division Subdivision and Section. The generated Table of Provisions is stored just before the first Part Chapter Order Division Subdivision and Section.

The title gets marked up as Level Heading Level 4 . Dates gets treated the same way as in Regs DTD Elements. See there for details.

The title gets marked up as Level Heading Level 2 . Dates get treated the same way as in Regs DTD Elements. See there for details.

Each form has a title regulation a front and an optional back. Each has a required Ibl attribute and a required ID.

1. Where there is insufficient space on this form to furnish the required information the information is to be shown on separate sheets numbered consecutively and signed by or on behalf of the applicant.

Forms get marked up with a Paragraph Style Forms . The markup of Front and Back gets inserted as hidden text hidden text is visible on the screen but doesn t show when the Form gets printed.

Forms get marked up with a Paragraph Style Forms . The markup of Front and Back gets inserted as hidden text hidden text is visible on the screen but doesn t show when the Form gets printed.

Used to mark any inline text which is set in a bold face other than a title or a label. It may contain text or any inline elements other than .

An inline equation. This is a mathematical equation which is embedded in a line of text characters or other inline elements. See the attached description of equations for further details.

Used to mark any inline text which is set in a italic face other than a title or a label. It may contain text or any inline elements other than .

A sequence of text characters or inline elements surrounded by single or double paired quotation marks. The quotation mark characters must not be entered as text characters or entity references as they will be generated automatically.

A reference to a piece of legislation where the ID is not known. The tempref element will converted to an XREF element at a later date when the ID is known .

It has two required attributes startref and endref. Startref is the id of the first of the targets referenced and endref is the id of the last target referenced. For a description of id strings see the description of the xref element.

A cross reference to a single target. It has a single attribute ref which must contain the id string of the target of the reference. Ids are not being entered on elements during keying but will be generated automatically from the Ibl attribute of elements.

Cross references to sections of Acts and Act Schedules should be marked up using the xref element as described above.

It has a single attribute marker which has allowed values of bullet dash or none with a default of none. If a marker character precedes the list item then the relevant value should be entered for the attribute. The marker character should not be entered as text. If any marker character other than a bullet or dash is found contact SGMLSE for a change to the DTD.

A non inline quote. The quotation mark characters must not be entered as text characters or entity references as they will be generated automatically

A container element for a table which has a title. It contains a required title element followed by a single table.

The tag has three required attributes. They must be specified correctly or the table will not be handled properly.

A four column table which is the full width of the page. The second and third columns are twice the width of the first column and the fourth column is three times the width of the first 

Empty element. Specifies a vertical rule. It has a single attribute rty which specifies the type of rule. Valid values for rty are 

Empty element. Specifies a sequence of horizontal rules one per cell in the row. It has a single attribute rtl which is a colon delimited list of rule type specifiers. There must be one rule type specifier for each cell in the row. The valid specifiers are as for cellrule above.

Specifies a row in the table. It has a single attribute hdr which specifies whether or not the row is a header row in a table which will be repeated over page breaks. The only valid value is 1 one which indicates that the row is a header row. An omitted value for hdr indicates that the row is not a header row. A value is only valid on the first in the table.

indicates that the row is a header row iff the is the first in the table else it will generate an error .

spn INTEGER For horizontally spanned columns. VAL is a whole number representing how many columns are spanned. Note that for horizontal spans the text appears in the LEFTMOST cell in the span and all other cells in the span should be void of text.

vspn INTEGER For vertically spanned rows. VAL is a whole number representing how many rows are spanned. Note that for vertical spans the text appears in the LOWEST cell in the span and all other cells in the span should be void of text.

This maths DTD is a subset of the Arbortext maths DTD which itself is derived from the AAP maths DTD.

In maths mode all spaces are ignored except in a element as described below . Correct spacing is handled automatically.

Fence. A pair of bracketed delimiters. The attribute lp left post defines the type of the left delimiter as below and the following element rp right post defines the type of the right delimiter.

Phrase. In a phrase all characters are set in roman face and keyed space characters are preserved. A phrase is essentially a temporary escape out of maths mode back into normal text mode.

Radical or root. Contains a radicand which is the constructs which appear beneath the top horizontal bar and an optional radix rdx which is the power of the root e.g. square cube 4 etc. .

Roman Function. A function name set in roman face such as log sin cos lim arg etc. It differs from the element in that preceding and following space characters are generated to separate it from surrounding characters.

Roman face. Used to force an alpha character to be displayed in normal face rather than be treated as a variable and displayed in italic face.

Right delimiter of a fence. It has a single attribute post which defines the type of the delimiter. Valid values are the same as for the lp attribute of the element except that they specify the right hand match for the relevant left post.

Equations get converted to Microsoft Word equations and then converted into Folio Views. Alternatively equations get converted to images and added to Folio Views as images.

It is apparent from the above that the arrangements described are applicable to the electronic publishing industry.

The foregoing describes only some embodiments of the present invention and modifications and or changes can be made thereto without departing from the scope and spirit of the invention the embodiments being illustrative and not restrictive.

