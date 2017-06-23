---

title: Division program, combination program and information processing method
abstract: The present invention provides an information processing method converting a format of a structured document, comprising: a first step copying, a first storage unit, information of a pre-converted first structured document sequentially by a predetermined amount beginning from the head; a second step adding start tags and/or end tags, and an identifier tag for identifying the aforementioned start and/or end tags so that the information copied to the first storage unit becomes one complete second structured document; a third step converting the second structured document built up in the first storage unit to a target format and outputting it to a second storage as a third structured document; and a fourth step removing the start tags and/or end tags and the identifier tag added to in the second step from the third structured document retained by the second storage unit and merging with a fourth structured document.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08418053&OS=08418053&RS=08418053
owner: Fujitsu Limited
number: 08418053
owner_city: Kawasaki
owner_country: JP
publication_date: 20060331
---
The present invention relates to a division program combination program information processing technique and to a technique effectively applicable to a processing technique used for a structured document e.g. an XML extensible Markup Language document.

In recent years diverse systems such as those of individuals enterprises government offices are connected through the Internet to carry out Web services an EDI electronic data interchange and an EC electronic commerce by the collaboration of systems.

This requires a wide range of information to be exchanged for which the XML extensible Markup Language has been in the spotlight as a common platform format used for information exchange because the XML has a flexible expression capability for structuring data and is suited to computer processing for data exchange and data processing.

The XML originating from an SGML Standard Generalized Markup Language standardized by the ISO International Organization for Standardization in 1986 has been established by the W3C World Wide Web Consortium as its basic specification XML 1.0 in February 1998 for the purpose of easy utilization on the Internet. The HTML Hyper Text Markup Language which is a Web page creation language has fixed tags which are specialized for a display being faced with a problem of not responding to the requirement of information processing by a computer based on the tag information. The XML allows a user to define a tag freely has a language structure for giving meaning to a character string within a document and allows information processing by a computer.

In the case of applying a handling such as search update and delete to an XML document it is handled by expanding it into to a tree structure Document Object Model DOM by standard API Application Programming Interface software. Expansion into a DOM tree however requires an operating memory volume of up to five to ten times that of the original data and moreover develops unused items thus having the shortcoming of being time consuming.

The following is a description of problems of the conventional technique concerning the above described XML.

Here the following is how the terminology is used based on the XML standard. A character string enclosed by a pair of is called a tag a is called a start tag a is called an end tag an entire character string from a start tag to an end tag is called an element a character string sandwiched between a start tag and an end tag is called an element content a name of an element described within a tag is called an element name or a tag name and additional information for an element is called an attribute.

A structured document describes a data structure in the form of embedding a tag within the document itself. Having a structure of embedding a data structure in the document as a tag keeps a flexibility and extensibility against an addition deletion and modification of data items. And naming with a meaningful name makes data possess a visibility when a person reads it.

Two standard interfaces API Application Programming Interface specifications i.e. DOM Document Object Model and SAX Simple API for XML are established for the purpose of handling an XML document as a representative structured document.

SAX has the characteristics of small memory consumption generally high speed being a time series output and is thus suitable for simple processing for referencing.

DOM on the other hand has the characteristics of large memory consumption generally low speed and easy of programming even for a complex processing content because elements of a document are expanded a hierarchical tree. DOM is usually used for updating an XML document.

The XSLT conversion equipped as standard in an XML environment is used for a form conversion of an XML document. The XSLT conversion however consumes a large amount of memory of about ten times a file size and therefore it is hard to convert a large capacity XML document of the scale of 50 MB or larger. Accordingly the below described countermeasures i ii and iii have conventionally been taken. While the countermeasure i is the least cumbersome it has been difficult for a document having a complex structure.

 i Division and conversion of a file a conceivable method is to divide a file into a plurality thereof to convert them followed by combing the converted files for converting a large capacity XML document. It is however necessary to divide an XML document having a complex data structure at the most convenient dividing position hence necessary to rely on a manual work.

 ii Conversion by streaming processing a a conversion program is written for a standard API SAX Simple API for XML . This requires an individual new program b use STX Steaming Transformations for XML e.g. refer to a non patent document 1 . The b method is non standard requiring a standard style sheet to be rewritten for matching with a special specification. Since it is a single pass stream processing it has a shortcoming of data handling for conversion being constrained.

 iii Use of an RDB a large capacity XML document is once stored in an RDB Relational Data Base and processed in the RDB followed by extracting it as a converted XML document. This method requires an RDB handling a new program to be created and is hence cumbersome.

A flexible data expression form though it is XML has a shortcoming of data processing consuming a large volume of memory.

As a countermeasure to the above problem a patent document 1 has disclosed a technique for developing a partial tree with analyzed elements as nodes and also deleting unnecessary nodes when a prescribed stopping condition as a trigger occurs thereby making analysis processing continue without falling short of memory in the case of processing an XML document by DOM.

The case of the patent document 1 however requires a change of an operating specification of DOM per se and also a determination of individual stopping conditions according to a processing content hence lacking versatility.

A purpose of the present invention is to provide a technique for enabling a reduction of resources necessary for a data processing of a structured document such as an XML document without requiring a user intervention.

Another purpose of the present invention is to provide a technique for enabling an automatic conversion processing of a structured document such as a large capacity XML document having a complex data structure without requiring unnecessarily large memory resources.

Yet another purpose of the present invention is to provide a technique for enabling a conversion processing of a structured document such as a large capacity XML document having a complex data structure by using a general purpose conversion technique without requiring unnecessarily large memory resources.

A first aspect of the present invention is to provide a signal for carrying a division program for dividing information contained in a first structured document into a plurality of second structured documents wherein the division program makes a computer execute first processing for copying the information of the first structured document in each of the second structured documents which has a proper name corresponding to a sequence of division sequentially by a predetermined amount beginning from the head and second processing for adding a start tag and or an end tag to the second structured documents so that each of the second structured documents has the same hierarchical structure as the first structured document.

A second aspect of the present invention is to provide the signal for carrying a division program noted in the first aspect wherein the division program further makes a computer execute third processing for adding an identifier tag in order to identify said start and or end tags which are added to each of said second structured documents.

A third aspect of the present invention is to provide the signal for carrying a division program noted in the first aspect wherein said first and second structured documents are XML documents described by the extensible markup language XML .

A fourth aspect of the present invention is to provide a signal for carrying a combination program wherein the program makes a computer execute first processing for reading information in a sequence based on a proper name given to each of first structured documents in a manner to indicate a combination sequence from each of a plurality of the aforementioned first structured documents having a common hierarchical structure and second processing for merging with the second structured document having the same hierarchical structure as the first structured document following removal of a redundant start tag and or end tag which are included in the information.

A fifth aspect of the present invention is to provide the signal for carrying a combination program noted in the fourth aspect wherein said second processing is for identifying and removing a redundant said start tag and or end tag based on an identifier tag added to each of said first structured documents in order to identify the aforementioned redundant start tag and or end tag.

A sixth aspect of the present invention is to provide the signal for carrying a combination program noted in the fourth aspect wherein said first and second structured documents are XML documents described by the extensible markup language XML .

A seventh aspect of the present invention is to provide an information processing method for converting a format of a structured document comprising a first step for copying in a first storage unit information of a pre converted first structured document sequentially by a predetermined amount beginning from the head a second step for adding a start tag and or an end tag and an identifier tag for identifying the aforementioned start and or end tags so that the information copied to the first storage unit becomes one complete second structured document a third step for converting the second structured document built up in the first storage unit to a target format and outputting it to a second storage as a third structured document and a fourth step for removing the start tag and or end tag and the identifier tag added to in the second step from the third structured document retained by the second storage unit and merging with a fourth structured document.

An eighth aspect of the present invention is to provide the information processing method noted in the seventh aspect wherein said third step is for carrying out a CSV compaction conversion which assembles a plurality of elements contained in said second structured document by lining them up in a CSV Comma Separated Values style.

A ninth aspect of the present invention is to provide the information processing method noted in the seventh aspect wherein said structured document is an XML document described by the extensible markup language XML .

The present invention is comprised to read an XML document by using a stream type API divide it into a plurality of documents of a specified size and assign serial numbers to file names of the divided files so that a division sequence may be comprehended at the time of combining them when dividing and converting a large capacity XML document for instance.

Also comprised is to memorize the current hierarchical level at the time of a division processing so as to make each divided file an XML document add a start tag and an end tag of matched level depth at a discretionary division position and also insert an identifier tag for identifying the addition of start and end tags.

This comprisal makes it possible to combine and write the divided file in a sequence of file names by using the streaming type API after the division delete the start and end tags added for the convenience of the division and reproduce a converted document in the original XML format. Since the divided files are of the same as a pre divided file they allow a handling without changing an XSLT style sheet.

Conventionally a conversion of a large capacity XML document uses the above noted countermeasure iii in many cases because the aforementioned document is stored in an RDB and processed. As a future trend a method of data processing in a main memory is predicted to become popular as prices of memory become inexpensive in order to take advantage of the merits of XML. In such a case the possibility of being able to convert a large capacity XML document based on the standard specification is desirable.

The present invention provides a benefit of enabling an automatic conversion of a complex structured XML document regardless of its size by using a standard XSLT conversion since an input XML document is divided and then subjected to a conversion processing. Reading and writing a large capacity XML document at the time of dividing and combining by using a stream type API makes this possible without requiring a large amount of main storage.

That is the present invention enables an automatic division processing and conversion processing of a complex structured XML document. Also enabled is conversion processing of a large capacity XML document in a main storage which is predicted to become increasingly popular in the future by using a standard XML conversion.

One is called a data centric XML document such as a form or schedule chart which is characterized as having a number of tags and short element content.

The other one is called a document centric XML document such as magazine manual or dictionary which is characterized as having long element content a sentence.

The present invention enables a simplification of an API with the data type XML document for example as a target.

The present invention enables a handling of a data centric XML documents for example particularly an XML document being expressed by a record form is handled as a data base.

This comprisal enables a conversion of a large capacity XML documents in the unit of records for example by using a standard XSLT style sheet without requiring a volume increase of main storage.

The following is a detailed description of the preferred embodiment of the present invention in reference to the accompanying drawings.

The first description is of a configuration example of an information processing apparatus according to the embodiment of the present invention by referring to .

The information processing apparatus according to the present embodiment includes a central processing apparatus a main storage an external storage apparatus a display an information input apparatus and a network interface .

The central processing apparatus being comprised by a microprocessor et cetera executes a program installed in the main storage thereby carrying out a desired information processing.

The main storage being comprised by a semiconductor memory for example stores software executed by the central processing apparatus and data.

The present embodiment is configured to let the main storage install software including an operating system a streaming type parser program a division program an XSLT conversion processor a combination program et cetera.

The central processing apparatus executes the operating system thereby controlling an entire operation of the information processing apparatus .

The streaming type parser program division program XSLT conversion processor and combination program are application programs operating under the control of the operating system .

The external storage apparatus is made up of a storage apparatus comprising a nonvolatile storage medium.

The present embodiment is configured to make the external storage apparatus store a system folder a large capacity XML document a combined XML document a folder and a XSLT style sheet

The system folder stores software including the above noted operating system streaming type parser program division program XSLT conversion processor combination program and sequential division conversion program et cetera which are executed by being read in the main storage on an as required basis.

The streaming type parser program is an event driven type XML parser such as SAX Simple API for XML .

The division program while performing a structural analysis byway of the streaming type parser program carries out the processing of reading a large capacity XML document and dividing it into a plurality of small capacity XML documents

The division program has a stack area for temporarily storing tag information of an input large capacity XML document in a pushdown pop up system.

The XSLT conversion processor carries out a conversion processing defined in a XSLT style sheet by the XSLT extensible Stylesheet Language Transformations for each of the plurality of small capacity XML documents and outputs the conversion result to each of the plurality of small capacity XML documents respectively.

The combination program carries out the processing of generating a combined XML document by combining a plurality of small capacity XML documents

The information input apparatus comprising information input equipment such as a keyboard mouse etcetera provides an information input interface between a user and information processing apparatus . The present embodiment is configured to use it for an input of later described division control information .

The network interface provides a telecommunication interface for carrying out a telecommunication between the information processing apparatus and the outside.

The above described pieces of information stored by the external storage apparatus may be placed in an external server apparatus or storage apparatus neither of which are shown herein by way of the network interface and accessed by the information processing apparatus .

Next small capacity XML documents are taken out one by one from the folder and an XSLT conversion is carried out at the XSLT conversion processor by using the XSLT extensible Stylesheet Language Transformations . The converted plurality of small capacity XML documents are stored in the folder with the same serially numbered file names as the pre converted small capacity XML documents to which they correspond.

Next the XML documents in the folder are taken out one by one combined by using the combination program and the resultant combined XML document is obtained.

The large capacity XML document i.e. list.xml as the subject of processing shown by is a list of employee names having a list of record elements employee of respective employees as a record under the root element employee name list which has a simple data structure.

Specifying a record name and the number of records per file for the division program divides the large capacity XML document into the small capacity XML documents . In this case the division is carried out just by taking out the number of record elements specified by the user by the division control information and attaching an additional start tag and an additional end tag of the root element employee name list to the small capacity XML documents

That is the first small capacity XML document is attached only with an additional end tag of the root element employee name list at the end.

The last small capacity XML document is attached only with an additional start tag of the root element employee name list at the head of the document.

The small capacity XML document in the middle is attached with an additional start tag and an additional end tag of the root element employee name list at the start and at the end respectively.

Meanwhile the combination program enables a combination into one combined XML document by removing a redundant additional start tag and additional end tag within each of the small capacity XML documents based on the number of records specified by the division control information in a method reversal of that described above.

This makes each of the small capacity XML documents become part of one complete combined XML document allowing a processing by the XSLT conversion processor .

Although the XSLT conversion processor expands the entirety of input small capacity XML documents in a work area of the main storage a memory volume of the work area is small because the small capacity XML documents are only of small capacity and hence it is unnecessary to make the main storage large.

In the conversion example of the XSLT conversion processor shown by the case of carrying out a CSV compaction conversion is shown. That is enumerating data of each element i.e. extension fax and contact address contained in the level of the element employee by commas as separation and consolidating in the newly set contact address thereby reducing the data volume as a result of omitting a start and end tags for each element.

The next description is of a modified example of the present embodiment in which the case of applying to an XML document having more complex hierarchical level structure. Note that shown here is a CSV compaction processing for a part of record elements i.e. customer product and matter as individual record for example although a conversion processing is not particularly shown by a figure herein.

Referring to a large capacity XML document lists.xml as the subject is data of a sales performance. This has elements master and sales under the root element sales performance and further levels customer master and product master under the master .

And three kinds of record elements i.e. customer within customer master product within product master and matter within sales and the number of records of the unit of division are externally specified as the division control information .

A large capacity XML document actually has tens of thousand to hundred of thousand of records and a small capacity document is divided into units of hundreds to thousands of records. The small capacity XML document shown on the right side of examplifies the case of the records being divided into two per document.

A division into small capacity XML documents is carried out by specifying customer product and matter as the record names and 2 for the number of records both by the division control information for the division program .

The first small capacity XML document 001.xml is copied down to the point where two of the specified records appear when looking at the large capacity document from the head. This is followed by attaching additional end tags i.e. and corresponding to the original start tags i.e. and down to the level relevant to the aforementioned point and also attaching an identifier end tag i.e. at the head of these additional end tags thereby making one complete XML document having the same hierarchical structure as the original large capacity XML document .

To the second small capacity XML document 002.xml is added a tag of the level of the former XML document as start tags i.e. an additional start tag followed by adding an identifier start tag i.e. to the additional start tags .

Next is to copy from the point of interruption to a point of the specified number of records of the large capacity XML document followed by adding an identifier end tag and end tags i.e. an additional end tag down to the relevant level thereby making a complete XML document.

From the third small capacity XML document to one document prior to the last small capacity XML document the same operation as that applied to the second document is repeated.

To the last small capacity XML documents is added start tags of the level i.e. an additional start tags and an identifier start tag for beginning a generation processing to copy less than the number of specified records in the same way as the start of the second small capacity XML documents and therefore an end tag of the level i.e. an end tag is also copied as is to finish the processing.

The above described division operation operates so that each of the divided small capacity XML documents has the same hierarchy as the original large capacity XML document and the specified number of records . This allows each of the small capacity XML documents to be converted without any change to the XSLT style sheet

For a combination operation copying while searching for an identifier start tag and an identifier end tag from the divided document i.e. the post conversion small capacity XML documents in this case and if there is an identifier end tag then additional end tags of levels thereafter down to the end of the document are discarded. In this case a specifying by the division control information is not required for the combination processing.

For the next document an operation is repeated in which additional start tags of the levels from the head to the identifier start tag are discarded and contents between the next and just before the identifier end tag i.e. are copied. By so doing the redundant tags i.e. an additional start tag and an additional end tag attached at the time of division are all deleted and the hierarchy of the original large capacity XML document is restored.

The next description is of a greater detail of a division processing by the division program according to the present embodiment by referring to the flow chart shown by .

First the step S is to input from the information input apparatus or a file the element name and the number of records of the unit of file division of a subject record as division control information .

Then the step S is to open an input XML file i.e. a large capacity XML document and also the first output file i.e. a small capacity XML document of serially numbered files to be divided.

Then the step Sreads the root tag of the input large capacity XML document and store the root element name.

If the read content is a start tag and is not the subject record of the steps S and S then the step S the tag name is accumulated on the stack i.e. the stack area by a pushdown followed by copying the start tag in the small capacity XML document and going back to the step S.

If the read content is a start tag and is the subject record in the steps S and S the step S is to copy all the record elements and elements within the record.

Then the step S is to count the number of records and if the counted value is judged to have reached the number of records inputted as the division control information in the step S then the step S attaches an identifier end tag i.e. for identification followed by writing out tags of stacked levels down to the root element as an end tag and closing the small capacity XML document as the output file.

Then the step S opens a new serially numbered output file i.e. a small capacity XML document and writes out tags down to the current stacked level from the root element as the start tag i.e. an additional start tag followed by attaching an identifier start tag i.e. . Then returns to the step S. If the number of counted records is judged not to have reached the input number of records returns to the step S as is.

If the read content is judged not to be a start tag in the step S and if an end tag is detected in the step S then the step S is to remove one tag name from the stacked level tags by a pop up followed by copying the end tag into the output file.

Then if the end tag is judged as a root tag in the step S the step S is to close the output file to end the processing. If the end tag is judged not to be a root tag return to the step S.

If the read content is judged to be neither a start tag nor an end tag in the step S and rather is an element content the step S copies the content directly to the output file followed by returning to the step S.

Thus a plurality of divided small capacity XML documents have the same hierarchical structure as the original large capacity XML document and therefore allow conversion processing without changing the XSLT style sheet described based on the hierarchical structure of the original large capacity XML document in the conversion processing such as a CSV compaction et cetera by the XSLT conversion processor by using the XSLT style sheet for instance.

Note that the identifier start tag and identifier end tag are inherited from the pre converted small capacity XML documents to the post conversion small capacity XML document in the above described conversion processing.

First the step S opens a divided file i.e. a post conversion small capacity XML document of the smallest serial numbered file name and also an output file i.e. a combined XML document of a combination output destination.

The step S reads one of the contents of the input file i.e. a small capacity XML document . In the step S if the judgment is that it is the first input file jump to the S to copy the read contents to the output file in the step S until an identifier end tag appears as per a judgment of S .

When an identifier end tag appears in the step S then the step S closes the input file and the step S opens the next input file followed by returning to the step S.

Next if it is an input file of the second in sequence or thereafter the step S examines whether an identifier start tag has appeared. If an identifier start tag has not appeared the step S examines whether the read content is an identifier start tag and if it is so the step S stores the fact that the identifier start tag appeared followed by returning to the step S.

If it is judged that an identifier start tag has not yet appeared in the step S and if the read content is not an identifier start tag then the step S skips the read content followed by returning to the step S.

If an identifier start tag is judged to have already appeared in the step S and if the read content is not an identifier start tag then the step S copies the read content to the output file followed by judging whether an end of file of the input file is detected in the step S.

If an end of file of the input file is judged as not being detected in the step S return to the step S.

If an end of file of the input file is judged as being detected in the step S then the step S closes the input file and ends the processing.

If an identifier start tag is judged as being detected in the step S then the processing is the same as that of the first file.

As described above the modified example shown by and attaches an additional start tag and or additional end tag by matching with a depth of tag levels before and after the dividing position when dividing a large capacity XML document into a plurality of small capacity XML documents . This configuration enables a division into small capacity XML documents accurately and automatically even in the case of a large capacity XML document having a relatively complex structure.

Conversely combining small capacity XML documents obtained by a conversion processing of a plurality of small capacity XML documents into a combined XML document enables an accurate and complete construction of the combined XML document as a result of removing the redundant additional start tags and or additional end tags by referring to an identifier start tag and or an identifier end tag as a mark.

And the storage resources of the main storage consumed by the XSLT conversion processor at the time of generating small capacity XML documents by applying conversion processing to a plurality of small capacity XML documents requires only a small capacity corresponding to each thereof. This eliminates a necessity to increase a capacity of the main storage by matching that of the large capacity XML document .

That is to an arbitrarily sized large capacity XML document can be applied automatically and confidently a conversion processing without a concern over a shortage of the main storage capacity.

The above described embodiment is configured to divide a large capacity XML document into a plurality of small capacity XML documents in a lump output to each of a plurality of small capacity XML documents by converting in a lump and output small capacity XML documents to a combined XML document in a lump. This makes it a division and conversion in a lump also called a lumped division and conversion hereinafter .

Comparably with the above described a sequential division and conversion can be carried out in the same way as shown in . In the case of the sequential division and conversion small capacity documents i.e. sequential division XML documents of a predetermined number of records are cut out of a large capacity XML document to a division buffer in the main storage and the divided documents are converted and output to sequential conversion XML document . And the conversion result is added to the combined XML document .

Carrying out the operation sequentially from the head of the large capacity XML document to the end makes it possible to generate a combined XML document in a state of a post conversion plurality of small capacity XML documents being combined together just by securing storage areas i.e. a division buffer and a combination buffer in the main storage for one divided document of small capacity XML documents and one converted divided document of each of post conversion small capacity XML documents without furnishing the external storage apparatus with storage memory areas for a plurality of small capacity XML documents or small capacity XML documents

A sequential division conversion program includes a division unit an XSLT conversion unit a combination unit a division buffer and a combination buffer .

The division unit while carrying out the same processing as the above described division program differs in its output part.

That is the case of the division unit comprises the function of instructing the XSLT conversion unit for a conversion start at the time of one sequential division XML document being built in the division buffer and that of building the next sequential division XML document in the division buffer at the notification of a conversion completion from the XSLT conversion unit as a trigger.

Also the combination unit is a little different from the combination program for the function of the input side. That is the combination unit comprises the function of inputting a sequential conversion XML document in the combination buffer and additionally outputting to the combined XML document .

The XSLT conversion unit carries out a conversion processing which is defined by a style sheet described by the XSLT eXtensible Stylesheet Language Transformations for a sequential division XML documents read out from the division buffer and output to the combination buffer as a sequential conversion XML document . The conversion processing by the style sheet conceptually includes a CSV compaction for example.

Note that the sequential division conversion program can be accomplished by a shell script if the above described division program XSLT conversion processor and combination program comprise a standard input output function and if the operating system is a multitasking operating system.

That is to allocate a large capacity XML document by way of a streaming type parser program as standard input of the division program i.e. the division unit and connect the standard output to the standard input of the XSLT conversion processor i.e. XSLT conversion unit at the next stage.

And to connect the standard output of the XSLT conversion processor to the standard input of the combination program i.e. the combination unit at the next stage and allocate the standard output of the combination program to the combined XML document by way of the streaming type parser program .

In this case to allocate sizes according to the number of input records to the division buffer and combination buffer .

The next description is an operation of the above described sequential division and conversion. is a flow chart examplifying an operation of a sequential division and conversion processing according to the present embodiment.

First the step S inputs the element name of a target record and the number of records of the unit of file division as the division control information from the information input apparatus or a file.

Then the step S opens an input XML file i.e. a large capacity XML document and also the first output file i.e. a combined XML document of the dividing serially numbered file names.

Then the step S secures a storage area for a sequential division XML document in the division buffer and also reads the root tag of the input large capacity XML document to store the root element name.

If the read content is judged to be a start tag and a subject record in the steps S and S respectively the step S copies all the record elements and elements within the record.

Then the step S counts the number of records and if the counted value is judged to have reached the number of records input as the division control information in the step S the step S attaches an identifier end tag i.e. followed by writing out tags of stacked levels down to the root element as an end tag and closing the sequential division XML document that is the output file.

Then the step S converts the generated sequential division XML documents by the XSLT conversion unit and generating a sequential conversion XML document in the combination buffer .

If the number of counted records is judged as not reaching the number of input records in the step S return to the step S as is.

In the above described step S if the read content is judged as a start tag and not a subject record the step S stores the tag name in the stack by a pushdown followed by copying the start tag in the sequential division XML documents and returning to the step S.

If the judgment in the step S is that it is not a start tag and if an end tag is detected in the step S then the step S removes one tag of the stacked tag names by a pop up and copies the end tag to the output file.

Then if the end tag is judged as the root tag in the step S the step S closes the input file i.e. the large capacity XML document and the sequential division XML documents to execute the step S. If the end tag is judged not to be the root tag return to the step S.

If the read content is neither a start tag nor an end tag and is an element content in the step S S the step S copies the read content directly to the output file followed by going back to the step S.

Following the above described step S the step S reads one of contents of the input file i.e. the sequential conversion XML document . If it is judged to be the first input file in the step S jump to the step S and copy the read contents at the step S to the output file until an identifier end tag appears.

If an identifier end tag appears in the step S then the step S deletes the sequential division XML documents and sequential conversion XML documents and if the input file i.e. the large capacity XML document is closed in the step S then the step S closes the combined XML document and ends the processing.

If the input file i.e. the large capacity XML document is judged not to be closed in the step S the step S opens a new sequential conversion XML document and writes out tags of the root element down to the current stacked level as additional start tags followed by attaching an identifier start tag i.e. for identification and returning to the step S.

Then if it is judged as the second i.e. not the first sequential conversion XML document or thereafter in the above described step S then the step S examines whether an identifier start tag has already appeared. If an identifier start tag has not appeared the step S examines whether the read content is an identifier start tag and if it is as such the step S is to store the fact that the identifier start tag appeared and return to the step S.

If an identifier start tag is judged not to have appeared in the step S and if the read content is not an identifier start tag in the step S then in the step S skip the read content and return to the step S.

If an identifier start tag is judged to have already appeared in the step S and if the read content is not an identifier start tag in the step S then the step S copies the read content to the output file followed by returning to the step S.

As such the case of a sequential division and conversion by using the sequential division conversion program does not necessarily require outputting a sequential division XML document or sequential conversion XML document as a file to the external storage apparatus enabling a data processing in the main storage hence making it possible to carry out a high speed division and conversion of a large capacity XML document although the structure of the sequential division conversion program becomes relatively complex.

That is the case of a sequential division and conversion of a large capacity XML document can carry out conversion processing at a high speed and output to a combined XML document without being conscious of the storage capacities of the external storage apparatus or main storage .

The following is a comparison of the advantages of the lumped division and conversion and the sequential division and conversion.

The lumped division and conversion makes the structure of software such as the division program folder et cetera simple.

The divided files such as the small capacity XML documents and the small capacity XML documents are once retained in the folders and hence enabling the processing such as update addition delete et cetera in the folders and respectively.

Each divided file such as the small capacity XML document and the small capacity XML document is of a small capacity making data updating processing easy.

Although a sorting processing with a record being a unit requires an execution in a large capacity XML document a combination of an XML CSV compaction refer to laid open Japanese patent application publication Nos. 2003 203067 and 2005 267531 which are inventions filed with the relevant patent offices by the inventor of the present invention and the division and conversion according to the present embodiment makes it possible to carry out a sort processing while saving resources.

On the other hand the case of the sequential division and conversion does not necessarily require outputting a sequential division XML document or a sequential conversion XML document as a file to the external storage apparatus enabling a data processing in the main storage hence making it possible to carry out a high speed division and conversion of a large capacity XML document although the structure of the sequential division conversion program becomes relatively complex as described above.

The above described present embodiment examplifies the case of having one CSV element within a record when carrying out a CSV compaction as a conversion processing as exemplified by the element contact address within the record of employee in the small capacity XML documents . Also in the case of making a CSV element plural this can be managed in an API by describing element names stored in the plurality of CSV elements in the header of a CSV compaction document i.e. a combined XML document and by reading in the same way as the described above and using a for two data associative array.

Note that it goes without saying that the present invention can be changed in various ways within the scope thereof and is not limited by the configurations exemplified by the above described embodiment.

The present invention provides a technique for enabling a reduction of necessary resources for a data processing of a structured document such as an XML document without requiring a user intervention.

Also enabled is an automatic conversion processing of a structured document such as a large capacity XML document having a complex data structure without requiring unnecessarily large memory resources.

Also enabled is a conversion processing of a structured document such as a large capacity XML document having a complex data structure by using a general purpose conversion technique without requiring unnecessarily large memory resources.

