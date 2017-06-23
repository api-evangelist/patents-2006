---

title: Method for processing a data tree structure
abstract: A method of processing a tree data structure organized into interconnected elements. The method comprises the steps of: defining processing units as subsets of interconnected elements and allocating each processing unit a processing time on which the data of the allocated processing unit is to be used by a unit that is the destination for the data. The processing method can be applied to streaming metadata, in particular for adaptation of scalable multimedia content.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09081755&OS=09081755&RS=09081755
owner: France Telecom
number: 09081755
owner_city: Paris
owner_country: FR
publication_date: 20060407
---
This application claims the priority of French patent application no. 05 03642 filed Apr. 12 2005 the content of both of which is hereby incorporated by reference.

The present invention relates a method of processing a tree data structure organized into interconnected elements.

The invention applies generally to the field of telecommunications in particular telecommunications via the Internet. However one more particularly advantageous application of the invention relates to transmitting metadata progressively streaming in particular for adapting scalable multimedia contents.

The contribution MPEG SC29 WG11 M11611 71st MPEG Meeting Hong Kong China 17 21 01 2005 defines a method of streaming a digital item conforming to the concept defined by the MPEG 21 standard ISO IEC TR 2100 1 2004 Part 1 Vision Technologies and Strategy and represents the fundamental transaction and distribution unit in the MPEG 21 context. A digital item is an abstraction of one or more semantically linked multimedia contents for example videos images audio and any metadata linked to those contents the whole constituting a transaction and end use unit.

The metadata linked to the digital item is frequently written in the widely used data tree structuring language known as XML eXtensible Mark Up Language . Since the digital item is intended to be communicated where applicable via Internet type networks the problem arises of transmitting metadata contained therein and more generally of transmitting XML documents.

In particular it is beneficial to stream transmit progressively an XML document so that the destination entity can use the fragment it has received without having to wait to receive the entire document. Moreover the use of an XML document is some times linked to the use of other data that is sent continuously such as a video stream. It is then necessary to synchronize the various data streams mutually and for this purpose to assign timing information to the fragments of the XML document.

The above mentioned MPEG contribution proposes a solution for fragmenting a digital item and for assigning timing information to the fragments obtained. It applies to XML documents in particular although it is not limited to them. That solution indicates the fragments to be transmitted by means of Xpath expressions Xpath XML Path Language version 1.0 W3C Recommendation 16 Nov. 1999 being an expression language for identifying a node or a set of nodes in an XML document. Moreover a parameter is used to define a transmission time for those fragments.

Against that background a technical problem to be solved by the present invention is to propose a method of processing a tree data structure organized into interconnected elements that makes it possible to select a set of fragments in particular in an XML type document and to assign them timing information flexibly.

Also apart from the fact that it should require limited memory resources regardless of the size of the document to be streamed this method should also be applicable to a document that is generated on the fly.

According to an embodiment of the present invention the solution to the stated technical problem consists in that said method comprises the operations of 

An embodiment of the invention provides more particularly for each processing unit to be defined on the basis of a given element called the anchor element as a set of elements linked to said anchor element in accordance with a given attachment mode.

According to an embodiment of the invention said attachment mode is chosen from the following modes simple ancestors descendants ancestors and descendants ancestors descendants and preceding siblings . These various attachment modes are defined below.

The invention further provides for said processing time to be defined by a time addressing mode and a time specification mode.

In a first implementation of the invention said time addressing mode is an absolute addressing mode and the processing time of a processing unit is defined absolutely in time. Said processing time specification mode is then the processing time in a given specification format.

In a second implementation of the invention said time addressing mode is a relative addressing mode and the processing time of a processing unit is defined relative to the preceding processing unit. The processing time specification mode consisting of a time interval can then be envisaged and likewise said time interval being expressed as a number of units on a time scale.

More precisely when implemented statically the method of the invention implemented by means of a document that structures data in the form of a tree is noteworthy in that the modes assigned to said elements are specified in said document.

Moreover when implemented dynamically the method of the invention implemented by means of a document that structures data in the form of a tree is noteworthy in that said document is associated with a template document in which the modes assigned to the elements concerned of said document are specified.

In particular there is provision for said template document to contain a set of templates each template being defined by a template pattern and by a set of attributes to be specified for the element or elements satisfying said template pattern.

Finally another embodiment of the invention also relates to a server for implementing the method discussed above to a computer program comprising program code instructions for executing the method when said program is executed in a computer and to a signal representing a document that structures data in the form of a tree specifying a processing unit and an associated processing time by means of an attribute.

The XML document is associated with the tree structure. Of course the invention is not limited to XML documents alone and can be applied to any tree data structure.

It is assumed that the destination application can use this document progressively. In this context a processing unit is a fragment of the document that can be used independently of the rest of the document.

However this solution would introduce a risk of inconsistency caused by the redundancy of the data and unnecessary consumption of storage space and bandwidth.

It is to avoid these drawbacks that an embodiment of the invention proposes the processing method that is described below with reference to .

Broadly speaking this processing method provides a method of defining said processing units and assigns each processing unit a processing time at which the data of the associated processing unit is to be used by the entity that constitutes the destination of said data.

The processing units are defined on the basis of a given element called the anchor element as a set of elements linked to said anchor element in accordance with a given attachment mode. In and the anchor elements of the processing units UT UT and UT are el el and el respectively represented by a white circle in the tree.

Various attachment modes can be envisaged namely the simple ancestors descendants ancestors and descendants and ancestors descendants and preceding siblings attachment modes.

In the ancestors attachment mode the processing unit contains the anchor element and all its ancestors.

In the descendants attachment mode the processing unit contains the anchor element and all its descendants.

In the ancestors and descendants attachment mode the processing unit contains the anchor element all its descendants and all its ancestors.

In the ancestors descendants and preceding siblings attachment mode the processing unit contains the anchor element its descendants its ancestors the elements preceding its ancestors and their descendants.

In and the processing units UT UT and UT are defined by applying the ancestors and descendants attachment mode to their respective anchor elements.

The anchor element and attachment mode concepts are used to define properties that apply to the elements of the tree structure to be streamed to the destination entity.

The anchor element concept corresponds to the property whereby an element is or is not an anchor element. Similarly the attachment mode concept corresponds to the property whereby an element is attached to the anchor element according to a given attachment mode.

According to the anchor element property an anchor element defines one and only one processing unit. In contrast it can belong to other processing units. Reciprocally a processing unit is identified by one and only one anchor element. In contrast it can contain other anchor elements.

When the processing method of the invention is implemented by an XML document for example a property of an element is either defined by an XML attribute or inherited from its parent element.

The anchor element property is reflected in the anchorElement attribute assigned to the elements el el and el. The value of the anchor element attribute is Boolean an element is an anchor element if and only if it contains the anchor element attribute with the value true .

There exists a relationship of order defined for the elements of an XML document that corresponds to the following navigation paths with the document scanned from left to right and from top to bottom the order of the elements is the order of occurrence of the opening tags. For example in the document the elements are ordered as follows el el el el el el el el el. The order of the processing units is the order of the anchor elements that define them. That order is used below in particular for relative time addressing defining the processing time of a processing unit relative to the preceding processing unit.

Note that the anchor element property cannot be inherited in the sense that an element cannot inherit this property from a parent element.

The second property linked to the attachment mode is reflected in a puMode attribute that is used to select a processing unit on the basis of the anchor element. This property is either defined directly by the puMode attribute or inherited from the parent element. Its value is one of the following 

In the document shown in the puMode attribute is used in the root element el to define the property puMode with the value ancestorsDescendants for example. Here this property is inherited by all the elements of the document. The anchor elements el el and el therefore inherit this property. Each therefore defines a processing unit as a function of that property as explained above. The processor unit UT UT and UT defined in this way correspond to the three documents represented in and and represented graphically in and

In this example the puMode property is defined once for the root element by the puMode attribute and then inherited by the other elements. It is equally possible to define this property separately for other elements. If the processor unit UT from is replaced by the processor unit UT from for which the anchor element is still the element el but for which the puMode property is defined by the descendants attachment mode then the descendants value of the puMode attribute must be specified in the anchor element el.

The mechanism proposed by the invention for defining properties by way of attributes and inheritance therefore defines properties with a fine granularity i.e. for each element independently if necessary and efficiently if the elements of a subtree of the document share the same property it is not necessary to add the attribute to each element to define that property. It suffices to add an attribute to the root element of the subtree and the property defined in this way is then inherited by all its descendants.

A first property timeMode defines the time addressing mode. It is either defined by a timeMode attribute or inherited from the parent element. The values of the timeMode attribute are as follows 

A second property timeScale defines the time scale for relative time addressing. It is either defined by a timeScale attribute or inherited from the parent element. Its value is an integer defining the time scale i.e. the number of units per second.

A third property timeInterval defines the time interval between two consecutive processing units for relative time addressing. It is either defined by a timeInterval attribute or inherited from the parent element. Its value is an integer defining the number of time units relative to the preceding processing unit the time unit being defined by the timeScale property defined above.

A fourth property absTimeScheme defines the addressing format for absolute time addressing. It is either defined by an absTimeScheme attribute or inherited from the parent element. Its value is a character stream defining the time addressing format. For example the stream mp7t denotes the time addressing format defined by MPEG 7 MDS MediaTimePointType .

Finally a fifth property absTime defines the processing time for absolute time addressing. It is not inherited and is defined by an absTime attribute. It value is a character stream defining the time according to the time addressing format defined by the absTimeScheme property. One example of this value for the MPEG 7 addressing format is T17 30 45 2F10 .

For example in the document shown in the timeMode timeScale and timeInterval attributes applied to the root element el indicate that time addressing for that element is relative the time scale is 22050 units per second and the interval between two processing units is 1024 units. Here these properties are inherited by the elements of the document and in particular by the anchor elements. The processing units inherit these properties from their respective anchor elements. The processing unit UT will therefore be presented to the destination application at the time t 0 the processing unit UT at the time t 1024 22050 seconds and the processing unit UT at the time t 2048 22050 seconds.

It has been shown above how the properties defining the processing units and their associated processing time can be specified by means of attributes added statically to the original document as illustrated by the document.

In this dynamic implementation the original XML document like that from is associated with a template document in which each template is defined by a template pattern. This pattern defines the XML elements to which this template will be applied and a set of attributes that will then be added to those elements. The syntax of all of the attributes and the templates is defined in .

The template pattern is written with a syntax derived from the expression language STXPath defined in STX Streaming Transformations for XML STX Version 1.0 Working Draft 1 Jul. 2004 . STX is an XML transformation language for transforming an XML document on the fly i.e. without having to load all of the document into memory first. This enables transformation of large XML documents and documents that are generated on the fly and consequently cannot be made available in their entirety. STXPath is therefore particularly suitable for the context of the present invention.

The STXPath syntax is close to XPath. In contrast its semantics are different. In XPath as in STXPath an expression is resolved relative to a context element. To evaluate the expression XPath must take into account a context that consists in the whole of the document. In contrast STXPath considers only the context element and the stack of its ancestors. The context necessary for resolution in STXPath is therefore limited and thus is particularly suitable for the context of the present invention. STXPath is used in particular to express constraints on the names of the elements of the context their ordinal number and the names and the values of their potential attributes.

For example the XPath expression el el selects all the elements named el whose parent element is named el and is the root of the document. The same expression in STXPath selects at most one element the element in the stack of the ancestors of the context element whose parent element is named el and its parent is named el.

A given implementation can use a subset of STXPath to provide a filtering process that is both flexible and fast.

The processing of the elements of the XML document from in accordance with the method of the invention is explained below with reference to a in static mode and b in dynamic mode.

The original XML document is read by a software module called a syntax analyzer parser . Several sorts of parser are widely used. These modules enable an application to access information contained in an XML document via a given application programming interface API . All the information contained in a XML document is modeled by an abstract model called Infoset standardized by the Web Consortium XML Information Set Second Edition W3C Recommendation 4 Feb. 2004 .

Embodiments of the invention can be used with several types of parser such as DOM Document Object Model Document Object System Level 2 Core Specification Version 1.0 W3C Recommendation 13 Nov. 2004 or SAX Simple API for XML . The invention is described here using SAX an implementation that is efficient in terms of memory consumption.

A SAX type parser reads an XML document and outputs a sequence of events describing the content. For example reading the general document represented in gives rise in substance to the following sequence of events 

Embodiments of the invention enriches the Infoset of the XML document with information defining the processing units.

In the static mode a attributes are added to the original document as shown in . The SAX parser thus generates a SAX event sequence containing the enriched information.

In the dynamic mode b events generated by analyzing the original document are processed by a bank of templates to add attributes on the fly. A module called the streaming instructions processor receives as input the SAX events output by the parser reading the original document applies the templates specified in the document called Dynamic Streaming Instructions and outputs a SAX event sequence containing the enriched information. The encoder therefore receives an Infoset enriched with streaming instructions just as if the instructions had been added statically to the original XML document. The remainder of the process is therefore identical to the situation of static instructions.

The encoder then uses the information defining the processing units to encode them. The output of the encoder consists in a sequence of access units UA which are data entities encoded for transport so that decoding the successive access units reconstructs the processing units as defined by the streaming instructions.

Several encoding methods can be used such as MPEG 7 Systems ISO IEC 15938 1 2002 Part 1 Systems TeM text encoding or BiM binary encoding . Several encoding strategies are possible for each encoding method.

The access units can then be sent via a network for example the Internet or concatenated in a memory to be sent later. shows both these cases. In each case each access unit is associated with a processing time that specifies the time at which the processing unit must be available to the destination entity in order to be used where applicable after being decoded. The right hand part of shows the use of the access units by the destination entity.

