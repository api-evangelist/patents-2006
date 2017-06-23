---

title: Differential rendering and refreshing a portal page with a page delta
abstract: A method for differential rendering a portal page that includes a plurality of page elements () and refreshing the portal page. The method includes providing a complete portal page (). A request for the portal page is then sent and/or received (). The request can represent user events. In a next step, page elements () of the portal page to be updated are identified () on the basis of the user events. A page delta is then calculated (), wherein each page element () is associated with a refresh policy depending on the semantics of the respective page element (). The page delta can include the markup elements of the page elements to be updated. Next the page delta is transferred () to the existing portal page and merged () with the existing portal page.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07831556&OS=07831556&RS=07831556
owner: International Business Machines Corporation
number: 07831556
owner_city: Armonk
owner_country: US
publication_date: 20060317
---
This application claims the benefit of European Patent Application Serial Number 05102111.1 which was filed on Mar. 17 2005 and which is fully incorporated herein by reference.

The present invention relates to a method for the differential rendering of portal pages on the server and refreshing them on the client. In particular the inventive method relates to the interaction between a server and a browser of a client.

A conventional portal page aggregation system usually transfers the complete portal page. In particular the complete markup which corresponds with the visual representation of the portal page is sent as a markup document from the server to the browser of the client. The markup includes all portlets and navigation elements.

There are two main disadvantages with using this approach First the server side processing time for rendering the page is slow since the markup of each page element has to be requested. Second since the markup document is very large transfer of the markup from the server to the client results in a high data flow between server and browser.

According to an alternative conventional method the complete page is only downloaded from the server to the browser the first time the portal page is accessed. Subsequently the client sends separate requests for only those parts of the portal page that have changed via so called client side includes CSI . Accordingly the server sends the markup for each of these parts in a separate response to the browser.

However this approach also has a major drawback Refreshing individual page parts does not work well because the browser is not able to always determine those parts of the portal page correctly. This is a result of the browser not knowing the portal specific semantics of the received user events. This is especially problematic if several portlets are communicatively linked i.e. when a click into one portlet has an effect on another portlet.

It is an object of the present invention to provide a method for rendering a portal page on the server and refreshing it on the client which improves the transfer between the server and the client and reduces the request processing time on the server.

The above object is achieved by a method as laid out in the independent claims. Further advantageous embodiments of the present invention are described in the dependent claims and are taught in the description below.

An objective of the present invention is to calculate a minimal page delta based on the user event and the current state of the portal page after the complete portal page has been initially stored. Each page element is associated with a refresh policy depending on the semantics of the respective page element. The refresh policies may be completely adapted to the semantics of the resources of the page. For example in one arrangement the refresh of a portlet is only required if the portlet was a target of an action or if the portlet has received an event of another portlet.

The page delta can be calculated on a server and the portal page can be stored on a client. The page delta only contains markup elements of those page elements that need a refresh typically one portlet or a small set of portlets. Accordingly only these markup elements are sent to the client. Several markup elements can be connected to markup fragments. After receiving the page delta the client merges the contained markup fragments with the overall markup document stored on the client. In addition the markup fragments of connected page parts are grouped to larger fragments called partitions. Thus the number of merge operations on the client can be minimized.

The inventive method has the advantage that the overall performance of the portal application is significantly improved due to reduced data transfer between server and client as well as reduced request processing time on the server.

In the first two levels of the tree structure the portal page includes nested layout elements e.g. horizontal panels. In a third level the portal page comprises two layout elements and a portlet . In a forth level the portal page comprises one navigation element e.g. for page navigation one layout element and three portlets . The page elements of one level correspond with another page element in the next lower level.

In a next step the markup of the requested portal page is written to the response during the render phase. The rendering is performed by traversing the tree structure of the portal page in order to collect the markup of each visited page element. In addition to the rendering the portal application creates a cookie which contains information about the rendered page as a whole and the rendered elements making up that page.

In a step the response is sent to the client. The response contains the page markup the created cookie and a script which implements the merge algorithm required for subsequent requests. In a step the received markup document the cookie and the merge script are stored on the client. In a final step the received markup document is displayed on the client.

In a next step the portal application starts the request processing lifecycle beginning with the initialization phase followed by the action phase. The action phase is responsible for portlet action execution. After the action phase the state of the portal application is committed.

In a further step it is checked based on the cookie if the requested page is already on the client. If this page is on the client in a step the render phase calculates the page delta to that page by identifying all page elements of the requested page that require a refresh. Otherwise the complete page is rendered in the same way as in the scope of the initial request.

In a step only the markups for page elements which need a refresh are rendered i.e. only the markup of those page elements are written to the response. Finally the cookie is updated as the structure of the page might have changed.

In a step after the request processing has been finished the response is sent to the client. It contains the markup reflecting the page delta as well as the updated cookie. On the client a script function is called within the received delta markup document which loads the markup document representing the complete page from the store on the client.

In a step the merge script function is invoked which merges the markup document representing the page delta with the loaded document representing the complete page. The resulting markup document and the cookie are stored on the client in the step . In the step the browser displays the resulting markup document representing the refreshed page.

In the next step the rendering is performed by traversing the tree structure of the portal page and writing the markup for each visited page element to the response. In addition to the rendering the portal application creates a cookie which contains information about the rendered page as well as the rendered page elements making up that page. To be more precise the cookie contains a list of pages that have already been sent to the client as well as for each page a list of page parts whose markup fragments are included in the sent markup document of that page.

In the step the response is sent to the client. It contains the page markup the created cookie and a script e.g. JavaScript which implements the merge algorithm required for subsequent requests. The script is sent as a separate file e.g. a js file which may be cached by the browser of the client.

In the step the browser stores the received markup document in the storage . The cookie and the merge script are stored in the cache of the browser . In the final step the browser displays the received markup document.

In the step the portal application starts the request processing lifecycle beginning with the initialization phase followed by the action phase. The action phase is responsible for portlet action execution. After the action phase the state of the portal application is committed i.e. it is now possible to distinctly identify all those elements of the requested page which need a refresh.

In the step shown in of the render phase it is checked on the basis of the cookie whether the requested page is already on the client. If this is not the case the complete page is rendered in the same way as in the scope of the initial request.

If the requested page is already stored on the client the render phase in the step calculates the page delta to that page by identifying all page elements of the requested page that require a refresh. Accordingly it merely writes the markup of those page elements to the response. Finally the cookie is updated as the structure of the page might have changed. For example a page element representing a portlet might have been added to the page during the action phase.

In the step the response is sent to the client. It contains the markup reflecting the page delta as well as the updated cookie. A script function called within the received markup document of the page delta loads the markup document representing the complete page from the storage of the client step .

In the step the merge script function is invoked which merges the received markup document of the page delta with the document of the complete page loaded in step . The merge algorithm replaces the stale markup fragments in the overall markup document with the markup fragments contained in the received page delta. The resulting markup document is saved in the storage of the client. The cookie is stored in the cache of the browser in the step . In the final step the browser displays the resulting markup document.

In a first step the visited page element is asked whether it supports the dynamic refresh mechanism introduced in the scope of this invention or not. Note that not every type of page element must support this mechanism though it is strongly encouraged in order to maximize the benefits of the inventive method.

Assuming that dynamic refresh is supported in a further step the algorithm detects on the basis of the cookie whether the markup of the visited page element is already on the client as a part of the stored markup document representing the entire portal page. Note that the mere existence of the overall markup document for the requested page on the client does not imply that the markup of a particular visited page element is contained in this document as the structure of the page might have changed during the action phase. For example the current request might have caused the inclusion of an additional portlet into the page during the action phase.

If the markup of the page element is already on the client in a next step a refresh policy of this page element is requested and executed. As already mentioned the refresh policy of a particular page element depends on the semantics of the respective page element. The refresh policy of a portlet for example might check in a step whether the portlet executed an action in the scope of this request or if its markup was invalidated due to other reasons e.g. due to a configured timeout on the server.

If a refresh is required the page element delivers its entire markup in a step . If no refresh is required in a step a reference is returned which points to the markup fragment of the page element in the markup document stored on the client.

The tree of the portal page on the server represents a model of the page which abstracts from the visual representation of the page. This representation just contains those page elements which are relevant for the request processing on the server in the portal application.

The representation of the portal page on the client corresponds to a markup document which reflects the visual representation of the portal page . When using a browser of a personal computer the markup document is typically a HTML document consisting of HTML tags. As the document describes a hierarchy it can also be seen as a tree c.f. . The depicted sample tree might correspond to a HTML markup document with a structure shown in Table I.

The calculation of a page delta on the server that can be applied to the page or markup document respectively stored on the client requires a mapping between the two illustrated representations. This may be done by assigning each page element a unique identifier in the representation on the server. In these identifiers are illustrated as numbers within circles representing the server side page elements. During rendering a page element encodes its identifier into the root tag of its markup fragment of the page e.g. as a special tag attribute. All other tags which are depicted as empty squares being part of this markup fragment need not be flagged with this identifier. The identifiers in the markup document can be easily looked up by the merge script. In the root tags of the various markup fragments are depicted as squares with numbers in them representing the identifiers.

The existence of such unique identifiers within the markup document processed on the client is therefore a prerequisite for the inventive method.

The sample HTML delta markup document that corresponds with the delta tree of might have a structure shown in Table II.

In the depicted sample the creation of partitions is implicit. A partition is formed from each sub tree in the markup document consisting merely of nodes or tags respectively representing references. The merge algorithm detects these partitions. In the provided sample the sub tree of the page elements with the numbers R R and R forms a partition. The merge script on the client detects these partitions in order to minimize the merge operations. Note that implementations also are conceivable where partitions are explicitly mapped to a special tag in the markup document.

Note that deletions of markup fragments are implicit. Markup fragments which are part of the overall markup document that are neither referenced nor refreshed are not included into the result markup document e.g. the former page delta. The result of this merging is a refreshed portal page which should be stored in the client side store before displaying it.

A detailed description of an implementation of the inventive method and the integration into a portal application is described below.

The following paragraphs outline a possible implementation of the inventive method on a software design level. In addition the integration into an existing architecture of a portal application is discussed.

In the following the term component denotes a self contained coarse granular entity in a software architecture that offers its service via an interface. If a user interface component is meant e.g. a button a menu or a selection list the term user interface component is used explicitly.

An authentication component is responsible for verifying the identity of the user. Each incoming request should pass an authentication. The portal uses the user identity to determine the content the user is authorized to access as well as the commands to execute.

A command API application programming interface component provides an abstraction layer for portal specific commands. In particular it allows for executing commands via a unified interface. Commands may be used to perform administrative tasks such as creating and or deleting portal pages adding and or removing portlets to and or from portal pages arranging portlets on existing pages and so on.

A model API component provides a unified access e.g. read and write access to various models e.g. layout models representing the layouts of portal pages or navigation models representing the hierarchy of portal pages. The provided layout models correspond to the server side page representations as discussed above.

A state manager component is responsible for handling a portal resource state e.g. the portlet modes and or window states of the portlets or the identifier of the currently selected portal page. It provides an API which allows for reading as well as writing these state portions.

A portlet container provides unified access to the portlets. In particular it allows for gathering the markup of a certain portlet or executing a portlet action. The portlet container invokes portlets by means of the portlet API.

An aggregation component is invoked during the render phase of the request processing lifecycle. The aggregation component is responsible for transforming the model of the requested page into a presentation tree. The aggregation component also is responsible for writing for the response the markup that corresponds to this presentation tree.

The control flow during the action phase which is not illustrated explicitly can be outlined as follows.

First the front controller retrieves the user action from the given request. Next the controller maps the user action or an identifying string to a certain command. The controller passes in a set of parameters and executes the command via the command API component . The subsequent control flow depends on the semantics of the respective command.

An administrative command might load a layout model via the model API component and modify this model according to the parameters passed in for example it might add a portlet. Other kinds of commands involve the modification of a resource state via the state manager component or executing a portlet action by dispatching to the portlet container component .

The control flow during the render phase can be outlined as follows. The front controller delegates the rendering task to the aggregation component . The aggregation component first retrieves the identifier of the requested page from the state manager component . Second the aggregation component loads the corresponding layout model representing the requested portlet page via the model API component and transforms it into a presentation tree afterwards. Depending on the implementation of the aggregation component this transformation step may vary. In an implementation based on Java server faces JSF for example each resource in the loaded layout model is mapped to at least one JSF user interface component. As a final step the resulting JSF tree is traversed and the markup of each visited user interface component is written to the response.

The implementation of the inventive method requires the adaptation of the aggregation component as well as the state manager component . illustrates these changes and extensions. It presupposes a JSF based aggregation.

The main components in the JSF based aggregation are illustrated as inner components nested in the aggregation component . A view handler component controls the behavior in the render phase i.e. the view handler component is responsible for building the JSF component tree as well as invoking the renderers associated with the various user interface components. The renderers are responsible for writing the markup of a user interface component to the response.

The part of the user interface component tree representing the actual portal page in addition to the navigation components is the result of a layout model transformation. The abstraction layer modeling transformations corresponds with a model transformer component . The transformer of a layout model for example might traverse the given layout model and map each visited layout model resource to a JSF user interface component. As this mapping step is a complex step involving the instantiation as well as the initialization of the respective user interface component it is also encapsulated in a self contained component namely in a user interface mapper component . To summerize the model transformer component defines the transformation strategy and uses the associated user interface mapper component in order to transform one particular resource.

The main extension is a refresh policy model component which is actually a micro framework within the aggregation component . As depicted in this framework basically consists of a set of interfaces and generic classes implementing these interfaces which simplify the implementation of concrete user interface components and renderers which support the inventive method.

The required interfaces and classes are described below in detail. By means of a so called refresh policy holder interface user interface components indicate that they support the inventive refresh method. This interface offers a getRefreshPolicy method which enables renderers to get the refresh policy associated with the respective user interface component. Note that the user interface mapper component must initialize each user interface component supporting the refresh policy holder interface with the needed refresh policy by means of the setRefreshPolicy method. As the user interface mapper component is able to set generic properties of arbitrary user interface components no extensions of the user interface mapper component are required to support this step.

The class of base refresh user interface components is an abstract JSF user interface component which implements the refresh policy holder interface . It merely reads and or writes an instance variable representing the refresh policy. This abstract class is supposed to be extended by concrete specific user interface components which support the inventive method.

Specific refresh policies are modeled by means of a refresh policy interface . The refresh policy interface provides a RefreshRequired method and is to be implemented according to the semantics of the resource using this policy.

The class of base refresh renderers is an abstract implementation of specific JSF renderers e.g. JSF renderers which encapsulates the refresh algorithm as illustrated by the flow diagram of . This base refresh renderer is also supposed to be extended by concrete renderers which merely need to provide some methods to gather their markup in case that a refresh is required.

Required state manager component extensions depicted in are related to the generation of a uniform resource locator URL . In addition to providing access to the state information the state manager component is also responsible for encoding state information into the URLs in order to support browser bookmarks and back button usage. However as the concept of the inventive method involves the client side storing of markup which is likely to contain the URLs the state information encoded into the URLs must be invariant to specific user requests. This means that the URLs may only encode the delta state portion while the base state to which the delta state refers must be encoded into the delta markup document per request i.e. the base state must not be stored on the client. However the state manager component of the web sphere portal makes use of a flexible state handling and URL generation framework which can be easily customized to meet this requirement.

Another discussed requirement of the inventive method is the mapping between the server side portal page representation and the client side markup document via identifiers. This concept may be easily put into practice when using a JSF based aggregation as the JSF user interface model component already offers the concept of a so called client identifier.

The user interface mapper component which is responsible for the user interface component initialization sets the client identifier for each processed user interface component by deriving it from the unique identifier of the transformed resource in the model e.g. layout model. Thus each renderer is able to encode the client identifier of the associated user interface component into the markup of the user interface component. As the client side merge script must be able to detect these identifiers in the markup document i.e. in the overall markup document stored on the client as well as in the received delta markup document the encoding into the markup needs to be implemented in a unified way. Therefore the encoding of the client identifier of a user interface component is also performed in the class of the base refresh renderer .

The present invention can be realized in an entirely hardware embodiment or an embodiment combining hardware and software. The present invention can be realized in a centralized fashion in one processing system or in a distributed fashion where different elements are spread across several interconnected processing systems. Any kind of processing system or other apparatus adapted for carrying out the methods described herein is suited. A typical combination of hardware and software can be a general purpose processing system with an application that when being loaded and executed controls the processing system such that it carries out the methods described herein. The present invention also can be embedded in an application product which comprises all the features enabling the implementation of the methods described herein and which when loaded in a processing system is able to carry out these methods.

The terms computer program software application variants and or combinations thereof in the present context mean any expression in any language code or notation of a set of instructions intended to cause a system having an information processing capability to perform a particular function either directly or after either or both of the following a conversion to another language code or notation b reproduction in a different material form. For example an application can include but is not limited to a subroutine a function a procedure an object method an object implementation an executable application an applet a servlet a source code an object code a shared library dynamic load library and or other sequence of instructions designed for execution on a processing system.

The terms a and an as used herein are defined as one or more than one. The term plurality as used herein is defined as two or more than two. The term another as used herein is defined as at least a second or more. The terms including and or having as used herein are defined as comprising i.e. open language . The term coupled as used herein is defined as connected although not necessarily directly and not necessarily mechanically i.e. communicatively linked through a communication channel or pathway.

This invention can be embodied in other forms without departing from the spirit or essential attributes thereof. Accordingly reference should be made to the following claims rather than to the foregoing specification as indicating the scope of the invention.

