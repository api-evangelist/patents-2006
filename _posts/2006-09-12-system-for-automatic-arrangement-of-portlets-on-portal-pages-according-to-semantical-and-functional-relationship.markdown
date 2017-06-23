---

title: System for automatic arrangement of portlets on portal pages according to semantical and functional relationship
abstract: The present invention relates to the field of network computing, and in particular to method and system for designing a Web Portal comprising a hierarchical structure of portal pages and portlets for accessing Web contents accessible via the Portal. A typical larger enterprise's portal contains large numbers, e.g., thousands of pages and portlets. Due to the complexity of an enterprise portal, manual administration is inefficient as it is time-consuming, error-prone and thus expensive. In order to overcome these disadvantages, it is proposed that a Portal according to the invention performs some mining of the portlet markup and/or that of the portlet description in order to autonomously compute and propose an enhanced portal content structure. This helps to provide a user-friendly content structure that reflects well the relationships between portlets.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07653659&OS=07653659&RS=07653659
owner: International Business Machines Corporation
number: 07653659
owner_city: Armonk
owner_country: US
publication_date: 20060912
---
The present application claims priority under 35 USC 119 to European Patent Application Number EP05111949.3 filed Dec. 12 2005.

The present invention relates to the field of network computing and in particular to a method and system for designing a Web Portal or Enterprise Portal including a hierarchical structure of portal pages and portlets for accessing Web contents or Enterprise contents accessible via the Portal.

In more detail a Portal engine of the Web server in implements an aggregation of Portlets based on the underlying Portal model and Portal information such as security settings user roles customization settings and device capabilities. Within the rendered page the Portal automatically generates the appropriate set of navigation elements based on the Portal model. The Portal engine invokes Portlets during the aggregation as required and when required and uses caching to reduce the number of requests made to Portlets. The prior art IBM WebSphere Portal employs open standards such as the Java Portlet API application programming interface . It also supports the use of a remote Portlet via the WSRP standard.

The Portlet container is a single control component competent for all Portlets which may control the execution of code residing in each of these Portlets. It provides the runtime environment for the Portlets and facilities for event handling inter Portlet messaging and access to Portlet instance and configuration data among others. The Portal resources are in particular the Portlets themselves and the pages on which they are aggregated in form of an aggregation of fragments. A Portal database stores the portlet description this is in detail the portlet description featuring some attributes like portlet name portlet description portlet title portlet short title and keywords the portlet interaction interface description which is often stored in form of WSDL documents. The Portal database also stores the Portal content structure i.e. the hierarchical structure of portal pages which may again contain nested pages and portlets. This data is stored in the database in an adequate representation based on prior art techniques like relational tables.

The before mentioned aggregation logic includes all steps that are required to assemble a page. Typically these steps are to load a content structure from storage to traverse it and to call the instances referenced in the structure in order to obtain their output which is assembled to a single page. The content structure may be defined through e.g. Portlet Customization by the administrators or users and saved in the database or by other ways e.g. scripting xml import etc.

A graphical user interface component is provided for manually controlling the layout of the plurality of rendered pages. By that interface a Portal administrator is enabled to control the visual appearance of the Web pages. In particular the Administrator can decide which Portal is rendered at which location next to which other Portlet at a given Web page.

With particular reference to the focus of the present invention the structure behind a Portal is illustrated by way of a tourist information Portal example in . Such prior art portal is made up of a hierarchical structure of portal pages see the circles to which may again contain nested pages see to and portlets to . Such structure is generally referred to herein as content structure . Of course the Portlets to are not restricted to be located at one and the same hierarchy level as depicted in instead they can be distributed over any level.

With reference to in more detail page is the homepage of the portal. The homepage comprises amongst other graphical elements three links leading to pages and . Page comprises again another link which leads to page which intern comprises links leading to pages and . A similar structure is repeated for page leading to pages and . A similar structure could be appended beneath page which is suppressed here in order to increase clarity of the drawing.

In this example page comprises two portlets . Portlet shows the train schedule and portlet is a portlet which guides the user when he wants to buy an online ticket. Under page a portlet related to rental cars is provided. Further under page a trip planning portlet is provided. Further under page a flight booking portlet and a news portlet is provided. Finally under page a further page comprising a telephone book portlet is provided.

In prior art the portal content structure as exemplarily depicted in in a simplified manner is manually defined by portal administrators and users using above interface in . An administrator edits page containing the TRAIN SCHEDULE portlet . In prior art there is generally no system support for configuring the content structure.

Although the content structure given in is kept deliberately simple a person skilled in the art will appreciate that the task of configuring the Portlets on the Web pages of a Portal is no more trivial when the number of Portlets and the depth of the tree increases.

A typical larger enterprise s portal however contains large numbers e.g. thousands of pages and portlets. Due to the complexity of an enterprise portal manual administration is inefficient as it is time consuming error prone and thus expensive. In addition in a complex portal it is not possible for a human administrator to capture the entire set of functional and semantic relationships between portlets thus an Administrator will very often not be able to arrange all portlets properly such that a user visiting the Portal may easily find all those Portlets which are closely related to each other.

An improper arrangement of portlets including complex arrangements of inter related Portlets when they are for example spread across different pages results in a complex content structure and in difficult navigation. This may degrade the usability of the Portal and a user s productivity as the user has to perform too many switches between pages in order to work with two or more functionally related portlets. Further a user risks to finish his visit on the portal uncompleted for example due to the fact that the user is not aware of some relevant Portlet waiting for him to be called two pages higher in the tree.

Thus it is basically foreseeable that additional helpdesk support and user training is required or at least recommended in such complex navigation structure.

It is an objective of the present invention to provide an improved method and system for designing a Web Portal including a hierarchical structure of portal pages and portlets for accessing Web contents accessible via the Portal. This objective of the invention is achieved by the features stated in enclosed independent claims. Further advantageous arrangements and embodiments of the invention are set forth in the respective subclaims. Reference should now be made to the appended claims.

Briefly a Portal according to the invention performs some mining of the portlet markup and or the portlet description in order to autonomously compute and propose an enhanced portal content structure. This helps to provide a user friendly content structure that reflects well the relationships between portlets. This includes arranging inter related portlets near by preferably on one and the same page and thus better integrates the portlets. This enhances user experience and productivity as it reduces the number of navigational actions in particular page changes and as it presents a more integrated view of related portlets.

The mining reveals semantic and functional similarities between the portlets. The result of the mining function is a more or less compressed form of grouped Portlets. A group is characterized by the feature that the Portlets comprised thereof have inter relations between. The degree of closeness of interrelation may be preset by one or more initialization parameters. Those groups can be taken now and manually improved and further edited in order to better organize the pre existing content structure.

According to the broadest aspect of the invention at the Portal Server a method for arranging Portlets in a Web Portal is disclosed comprising a hierarchical structure of portal pages and portlets which is characterized by the steps of 

a retrieving data mining input data relating to said Portlets from the Portlet markup and or from the Portlet description and or from the Portlet interaction description of Portlets residing on the Portal preferably from a database associated with the Portal or from a request to said Portlets b performing a data mining function on said data mining input data resulting in a data mining result revealing respective semantic and or respective functional similarities between said portlets c calculating a new content structure from said data mining result wherein said new content structure arranges semantically and functionally similar Portlets on said pages and d offering new pages with said new content structure.

Further advantageously the portlet arrangement software may implement the step of receiving an administrator feedback if the calculated arrangement of Portlets is accepted as a base version for a new Web Portal version.

Further advantageously the portlet arrangement software may implement the step of receiving an administrator feedback including manually performed corrections on the offered web page structure.

Further the step of calculating a new Portlet arrangement may be based on iterations and start with an existing Portlet arrangement.

Further the step of calculating a new Portlet arrangement is performed when a new Portlet is to be installed on a page.

First a portal user benefits from enhanced integration of portlets and simplified navigation. Second the portal administrator is relieved from manual configuration of the content structure.

With general reference to the figures and with special reference now to a preferred embodiment of the present invention will be described in more detail below.

In a first preparative block of steps which are depicted as block in the data mining input data is retrieved. A preferred data sources is the portal database . Preferably the following input data is collected the portlet description featuring some attributes like portlet name portlet description portlet title portlet short title and keywords the portlet interaction interface description which is often stored in form of WSDL documents or the portlet markup e.g. HTML fragments optionally HTML and JSP source files.

A further data source is the portlet itself the data can thus be requested also from the portlets for example when the before mentioned Portlet arrangement control requests markup from the portlet by invoking the portlet through the portlet container.

In block the data mining is done based on above mentioned input data collected in step . For this block basic prior art data mining technology can be applied. This data mining function includes a prior art clustering algorithm which is applied to the present data and that returns a hierarchy of clusters of related portlets. In a subsequent step the cluster hierarchy is mapped to the content structure.

Briefly the clustering returns a set of clusters i.e. the set of all clusters is a function of all portlets. As a person skilled in the art knows Clustering is the process of grouping a set of objects into classes of similar objects. Central to clustering is to determine the degree of similarity or dissimilarity between individual objects and between clusters which is expressed as a distance value.

The preferred algorithm of the invention uses agglomerative hierarchical clustering techniques which iteratively join together similar clusters. This is depicted in steps to in and will be described in more detail next below 

Step The disclosed algorithm starts by assigning each portlet to a cluster so that if there is a number of N N can be any realistic number 200 500 1000 etc. for example portlets initially there are N clusters each containing just one portlet. For each pair of clusters the distance described later below in more detail between the cluster pair is the same as the distance between the portlets they contain. Step here the closest most similar pair of clusters is determined. Then they are merged into a single cluster so that now there remains a reduced number N 1 of clusters. Step Then the distances between the new cluster and each of the old clusters is computed.

Then a loop condition Do the distance values exceed a pre defined distance threshold T is executed and steps and are repeated until the distance values exceed this pre defined distance threshold T i.e. the loop is continued and the cluster gets merged in order to contain more and more Portlets as group members until there are no more similar clusters according to the user defined distance T which could be merged in a further iteration of step . The value T is chosen by the user thereby allowing the user to specify at what similarity of two clusters no merging between these two clusters should be done.

Note that for didactical reasons the check to terminate the loop is done at the end of the loop after at least one iteration preferably in real applications this test should be done in the beginning of the loop allowing zero iterations as well i.e. allow the case where no merging happens at all .

The end result of the mining function is thus in general a reduced number of clusters wherein each cluster comprises a certain plurality of inter related Portlets.

Then a new content structure is calculated in step from the mining result. With reference to the illustration of the tree structure given in is redrafted. Based on this tree redraft a new Portal structure is calculated wherein an additional step is performed of arranging the most top interrelated Portlets on a single page. This new tree structure coupled to a new rough page layout is then displayed to the Administration User in a step and proposed as a basic offer how the Portal pages could function better.

Further optionally the Administrator may perform some personal re redraft by the interface in and may trigger the disclosed program to redraft according to these new priorities. By that a feedback is fed also to the disclosed program in step .

In the following the distance calculation applied in the present invention is described in more detail as follows 

The distance d A B between two portlets A B is based on the distance between the portlet attributes i.e. the portlet descriptions and portlet markups of the portlets A and B. Prior art text processing and text mining methods are used to compute the distance between attribute pairs as for example the so called TF IDF Weighting and Cosine Similarity Measure see for example in Ricardo A. Baeza Yates Berthier Ribeiro Neto Modern Information Retrieval Addison Wesley Longman Publishing Co. Inc. Boston Mass. 1999. The frequency of occurrence of a search term TF is discussed there in relation to term specific relevance which is measured as inverse document frequency IDF of a term. Applied to the present invention the before mentioned attributes are usable as such terms. The documents mentioned in this publication correspond to the totality of data sources relevant for the data mining used herein and mentioned already above.

On the basis of portlet distance an inter cluster distance is defined. The distance D X Y between two clusters X Y is computed by aggregating the distance values of pairs of portlets in X and Y for example in a complete linkage method wherein the aggregation is performed by calculating the maximum of all distances between pairs of portlets in two clusters max where portlet is in cluster and portlet is in cluster 

Alternatively an average distance can be calculated. Then the aggregation is performed by calculating the average of all distances between pairs of portlets in two clusters avg where portlet is in cluster and portlet is in cluster 

In addition the disclosed cluster distance value calculation preferably incorporates heuristics to prevent oversized clusters which would result in oversized pages. An example is to limit the number of Portlets on a single page to a predefined maximum number e.g. 6 or 8.

Furthermore the cluster distance calculation used in the above algorithm can be modified in order to increase the inter cluster distance if a check indicates that a union of two clusters would be oversized. The check is based on the definition of two parameters 

The parameter threshold limits the size of the page that corresponds to the cluster. Note that a page is aggregated from markup of the portlets contained in a given cluster.

A modified distance D calculation algorithm can thus be described as follows pseudocode is added in brackets where useful 

First the distance D between two Portlets one in cluster X the other in cluster Y is determined according to aggregation where portlet is in cluster and portlet is in cluster Then the portlets are determined which are assigned to cluster X Y the union of X and Y . Then a check is performed if the number of Portlets is larger than a pre defined threshold portlets threshold then the computed distance D is increased by a predefined increment increment Return Then the portlet preview markup of portlets in X Y is retrieved Then an aggregation of the portlet preview markup is performed which results in a page preview Then another check is performed if the required size of the page is too large to display the markup of all Portlets i.e. larger than a predefined threshold then the computed distance D is incremented as for example if size page preview threshold increment Return 

In order to completely prevent oversized pages the parameter increment is set at least to the predefined threshold T.

First the cluster hierarchy is mapped to the page hierarchy thus a bijective mapping between a page and one respective cluster is done. Thus a page ID corresponds to a cluster ID. This allows mapping each portlet to a page.

Finally the portal content structure is modified according to the resulting content structure model. This is realized by converting the content structure into a representation suited for being stored in a database e.g. relational tables and writing this representation to the Portal database. Subsequent Portal requests will be processed on basis of this new content structure.

Next an example of the automatic arrangement of Portlets is given with reference to wherein only portlet title and portlet keywords are used as data mining input.

For each portlet the disclosed program component indicates the size of the portlet window as percentage of a page i.e. screen size . Thus e.g. portlet Train Schedule requires 50 of the page leaving 50 for other portlets on the same page.

In order to prevent oversized pages the increment is set to increment max 1 6 i.e. higher than every portlet distance value.

The hierarchical disclosed clustering algorithm will start with the cluster structure given in . In a number of 7 start clusters exist they are identical with the portals to from . Reference is thus made back to . The keywords given in for each portal to are extracted from the above mentioned data mining data sources in this example the portlet description the interaction interface description of the portlets and the mark up of the portlets. Further an additional indication of the portlet size expressed in terms of a fraction of the page is made for each portlet. For example the train schedule portlet has a size of 50 of the screen.

For each iteration the sequence of steps to see FIG. is run through. Step in the starting run or first iteration yields a cluster structure as given in each portlet is associated with a single cluster i.e. the numbers of clusters and the number of portlets are identical. Then in step the closest clusters are found and merged. This step is performed by aid of the distance calculation as it was given above. This yields a cluster structure as given in . Here the portlets and are merged as their distance is 1 as calculated above because they have two common keywords namely trip and time .

Then step is performed wherein the distances between each cluster and the merged cluster is computed. Then in step it is checked if any similar clusters are present. Here the cluster cluster distance calculation is performed as given above. A respective decision in step yields that similar clusters exist. Thus it is branched back in the YES branch to step for entering iteration number 2. Iteration 2 finds out that the train tickets cluster and the rental cars cluster are similar and are just joined i.e. merged. Then the next iteration is entered according to the algorithm given in .

For iteration 3 is relevant the disclosed program component calculates the distances between cluster and portlet flight booking which reveals cluster 71 flight booking 1 increment 1 6 7.

This calculation is done under the assumption that a size restriction involves the increment in order to avoid that more than 100 of the screen must be used for displaying a complete page. This is true in here because the portlet and require 80 of the page which is too much to integrate additionally the flight booking portlet which has in turn a size of 30 of the screen. Thus a total size of 110 of the page would result which leads the increment to be added in the above distance calculation. This size restriction increases the effective distance between portlet and cluster .

Next the distance between cluster and portlet is calculated to be 1 i.e. D cluster portlet 1. Further the other distances are also calculated D portlet portlet 5 

D portlet portlet 5. As the portlet is merged with the cluster to which it has the closest distance portlet will be merged with cluster .

At this point no more clusters can be merged mainly because each merge operation would generate an overfull page consuming more than 100 of the screen . However one may consider the newly created clusters as automatically generated new portlets each one containing the set of links to the cluster members and each one inheriting the keywords from its cluster members. And now a program component can re run the algorithm again this time on the generated clusters. This time however the procedure would have finished after one step gaining the two level structure as shown in the new cluster having the clusters and as members.

The disclosed method can be varied broadly. For example a Portlet interaction factor can be introduced in order to reflect the inter relations and in particular the input out dependence of certain portlets. For that embodiment the clustering algorithm is modified to recognize the fact that certain portlets are able to interact. This is done by analysis of the portlet interaction interface description WSDL documents and that of the portlet markup. From this pre analysis one or more sets of interacting Portlets are extracted from the total pool of Portlets. Different sets generally will not share a common Portlet. When interaction is determined then this fact is input as a interaction parameter into the calculation when computing distance values for these portlets. This is accomplished by an algorithm that computes an interaction factor for two portlets. This algorithm starts with a neutral value and increments an interaction factor IFAC between Portlet x and Portlet y if portlet x can handle properties published by portlet y. This means the algorithm performs a matching of interaction between the interface description of portlet x and the markup of portlet y that contains JSP tags referring to interaction operations 

Yin y property y is referred as input property in interaction interface description or markup of portlet Y

Yout y property y is referred as output property in interaction interface description or markup of portlet Y

In a further embodiment the new content structure is stored separately in the Portal database i.e. the current content structure is not modified. The Aggregation component is modified to perform a check when a portal user logs on to the Portal or when a user requests a page. The check tests whether the new content structure of the requested page is modified in comparison to the current content structure. If this test yields modified the aggregation component computes the difference between the current content structure and the new content structure prepares actions to selectively adapt the current content structure according to the changes and inserts links for invoking the actions into the page markup. Thus the user is presented a link through which he can enhance the page structure for example add semantically or functionally related portlets to the page. The current content structure is changed when the user invokes the according link. In this embodiment the user fully controls any changes to the content structure.

During processing of a request issued by a client the first step is to get a page identification of the page requested by the client. The page is processed using prior art techniques.

Then the disclosed program component retrieves the current content structure of the page using prior art techniques.

For all portlets that are contained in the new content structure only the following procedure is run through 

first the disclosed program component creates an URL that includes identifications of the current page the new portlet and the type of action i.e. add portlet . Note that URL creation is performed through prior art techniques.

For all portlets that are contained in the current content structure only the following procedure is run 

first a URL is created that includes identifications of the current page the according portlet and the type of action i.e. remove portlet . Also here the URL creation is performed through prior art techniques.

The client may issue the above mentioned URLs to the Portal. The Portal will use prior art techniques to process the action contained in the URL i.e. to add the specified portlet or to remove the portlet.

The skilled reader will appreciate that the before mentioned embodiments showing certain procedures and proposed sequences of steps are primarily given for demonstrating the disclosed method by way of example. Thus it will be understood that those examples may be varied in various aspects like for example the ordering of steps the degree of parallelization between steps the implementation details of the single steps the form in which data is stored the way how the grouping of portlets is achieved etc. and respective further embodiments can be obtained.

The present invention can be realized in hardware software or a combination of hardware and software. A Portlet arrangement tool according to the present invention can be realized in a centralized fashion in one computer system or in a distributed fashion where different elements are spread across several interconnected computer systems. Any kind of computer system or other apparatus adapted for carrying out the methods described herein is suited. A typical combination of hardware and software could be a general purpose computer system with a computer program that when being loaded and executed controls the computer system such that it carries out the methods described herein.

The figures include block diagram and flowchart illustrations of methods apparatus s and computer program products according to an embodiment of the invention. It will be understood that each block in such figures and combinations of these blocks can be implemented by computer program instructions. These computer program instructions may be loaded onto a computer or other programmable data processing apparatus to produce a machine such that the instructions which execute on the computer or other programmable data processing apparatus create means for implementing the functions specified in the block or blocks. These computer program instructions may also be stored in a computer readable medium or memory that can direct a computer or other programmable data processing apparatus to function in a particular manner such that the instructions stored in the computer readable medium or memory produce an article of manufacture including instruction means which implement the function specified in the block or blocks. The computer program instructions may also be loaded onto a computer or other programmable data processing apparatus to cause a series of operational steps to be performed on the computer or other programmable apparatus to produce a computer implemented process such that the instructions which execute on the computer or other programmable apparatus provide steps for implementing the functions specified in the block or blocks.

Those skilled in the art should readily appreciate that programs defining the functions of the present invention can be delivered to a computer in many forms including but not limited to a information permanently stored on non writable storage media e.g. read only memory devices within a computer such as ROM or CD ROM disks readable by a computer I O attachment b information alterably stored on writable storage media e.g. floppy disks and hard drives or c information conveyed to a computer through communication media for example using wireless baseband signaling or broadband signaling techniques including carrier wave signaling techniques such as over computer or telephone networks via a modem.

While the invention is described through the above exemplary embodiments it will be understood by those of ordinary skill in the art that modification to and variation of the illustrated embodiments may be made without departing from the inventive concepts herein disclosed.

