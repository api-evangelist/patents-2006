---

title: Producing a ranking for pages using distances in a web-link graph
abstract: Methods, systems, and apparatus, including computer programs encoded on a computer storage medium, for producing a ranking for pages on the web. In one aspect, a system receives a set of pages to be ranked, wherein the set of pages are interconnected with links. The system also receives a set of seed pages which include outgoing links to the set of pages. The system then assigns lengths to the links based on properties of the links and properties of the pages attached to the links. The system next computes shortest distances from the set of seed pages to each page in the set of pages based on the lengths of the links between the pages. Next, the system determines a ranking score for each page in the set of pages based on the computed shortest distances. The system then produces a ranking for the set of pages based on the ranking scores for the set of pages.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09165040&OS=09165040&RS=09165040
owner: Google Inc.
number: 09165040
owner_city: Mountain View
owner_country: US
publication_date: 20061012
---
The present invention generally relates to techniques for ranking pages on the web. More specifically the present invention relates to a method for producing a ranking for pages on the web by computing shortest distances from a set of seed pages to each of the pages to be ranked wherein the seed pages and the pages to be ranked are interconnected with links.

The relentless growth of the Internet has been largely fueled by the development of sophisticated search engines which enable users to comb through billions of web pages looking for specific pages of interest. Because a given query can return millions of search results it is important to be able to rank these search results to present high quality results to the user.

A popular search engine developed by Google Inc. of Mountain View Calif. uses PageRank as a page quality metric for efficiently guiding the processes of web crawling index selection and web page ranking. Generally the PageRank technique computes and assigns a PageRank score to each web page it encounters on the web wherein the PageRank score serves as a measure of the relative quality of a given web page with respect to other web pages. PageRank generally ensures that important and high quality web pages receive high PageRank scores which enables a search engine to efficiently rank the search results based on their associated PageRank scores.

PageRank scores are computed based on the web link graph structure wherein the web pages are the nodes of the link graph which are interconnected with hyperlinks. In this model PageRank R for a given web page p can be computed as 

However the simple formulation of Equation 1 for computing the PageRank is vulnerable to manipulations. Some web pages called spam pages can be designed to use various techniques to obtain artificially inflated PageRanks for example by forming link farms or creating loops. 

One possible variation of PageRank that would reduce the effect of these techniques is to select a few trusted pages also referred to as the seed pages and discovers other pages which are likely to be good by following the links from the trusted pages. For example the technique can use a set of high quality seed pages s s s and for each seed page i 1 2 . . . n the system can iteratively compute the PageRank scores for the set of the web pages P using the formulae 

Generally it is desirable to use large number of seed pages to accommodate the different languages and a wide range of fields which are contained in the fast growing web contents. Unfortunately this variation of PageRank requires solving the entire system for each seed separately. Hence as the number of seed pages increases the complexity of computation increases linearly thereby limiting the number of seeds that can be practically used.

Hence what is needed is a method and an apparatus for producing a ranking for pages on the web using a large number of diversified seed pages without the problems of the above described techniques.

One embodiment of the present invention provides a system that produces a ranking for pages on the web. During operation the system receives a set of pages to be ranked wherein the set of pages are interconnected with links. The system also receives a set of seed pages which include outgoing links to the set of pages. The system then assigns lengths to the links based on properties of the links and properties of the pages attached to the links. The system next computes shortest distances from the set of seed pages to each page in the set of pages based on the lengths of the links between the pages. Next the system determines a ranking score for each page in the set of pages based on the computed shortest distances. The system then produces a ranking for the set of pages based on the ranking scores for the set of pages.

In a variation on this embodiment the system assigns a length to a link by computing a function of the number of outgoing links from the source page of the link.

In a further variation on this embodiment the function is a monotonic non decreasing function of the number of outgoing links from the source page so that the length of the link increases as the number of outgoing links from the source page increases.

In a variation on this embodiment the system computes a shortest distance from a seed page to a given page by summing lengths of individual links along a shortest path from the seed page to the given page.

In a further variation on this embodiment the system computes the length of a link q p by adding a term log q to the length of the link wherein is a non negative value and wherein q is the number of outgoing links from the source page q.

In a variation on this embodiment a seed page sin the set of seed pages is associated with a predetermined weight wherein 0

In a further variation on this embodiment the computed shortest distance from the seed page sto a given page includes the initial distance d.

In a variation on this embodiment the system determines the ranking score for a given page based on the computed shortest distances by using k shortest distances from the k nearest seed pages to each page wherein k is a predetermined positive integer.

In a further variation on this embodiment the system determines the ranking score for a given page based on the computed shortest distances by using the kth shortest distance among the computed shortest distances.

In a further variation on this embodiment the ranking score for the given page can be proportional to e wherein D p is the kth shortest distance.

In a further variation on this embodiment the function for the length of the link includes a weight of the link.

In a variation on this embodiment the links associated with the computed shortest distances constitute a reduced link graph.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the claims.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or any device capable of storing data usable by a computer system.

One embodiment of the present invention provides a system that ranks pages on the web based on distances between the pages wherein the pages are interconnected with links to form a link graph. More specifically a set of high quality seed pages are chosen as references for ranking the pages in the link graph and shortest distances from the set of seed pages to each given page in the link graph are computed. Each of the shortest distances is obtained by summing lengths of a set of links which follows the shortest path from a seed page to a given page wherein the length of a given link is assigned to the link based on properties of the link and properties of the page attached to the link. The computed shortest distances are then used to determine the ranking scores of the associated pages.

As illustrated in the collection of pages is classified into two subsets of pages a set of seed pages and a set of non seed pages . Seed pages hereinafter referred to as seeds form the root nodes of link graph which comprise seed seed and seed . Although for simplicity is described in the context of three seeds generally the present invention can use much more than three seeds. Note that seeds are interconnected with link and link .

Non seed pages include pages wherein each page is either directly or indirectly connected to one or more seeds through the links in the link graph. In one embodiment of the present invention seeds are specially selected high quality pages which provide good web connectivity to other non seed pages.

More specifically to ensure that other high quality pages are easily reachable from seeds seeds in seeds need to be reliable diverse to cover a wide range of fields of public interests as well as well connected with other pages i.e. having a large number of outgoing links . For example Google Directory and The New York Times are both good seeds which possess such properties. It is typically assumed that these seeds are also closer to other high quality pages on the web. In addition seeds with large number of useful outgoing links facilitate identifying other useful and high quality pages thereby acting as hubs on the web.

One approach for choosing seeds involves selecting a diverse set of trusted seeds. Choosing a more diverse set of seeds can shorten the paths from the seeds to a given page. Hence it would be desirable to have a largest possible set of seeds that include as many different types of seeds as possible. However because selecting the seeds involves a human manually identifying these high quality pages the total number of the seeds is typically limited. Moreover having too many seeds can make the selected seeds vulnerable to manipulation. Consequently the actual number of the selected set of seeds is limited.

As illustrated in a link from a seed to a page is represented by an arrow pointing from the seed to the page. For example seed links to page and page through links and respectively. Such links assert a support from the seed to the linked pages.

The set of non seed pages are also interconnected with links. For example page has three outgoing links and which target at pages and respectively. Furthermore page has two outgoing links and which connect to pages and respectively. Additionally page links to page through link as shown.

Note that pages and form a loop wherein these pages point to each other in a circular manner though links and . Furthermore page and page also form a loop in which they point to each other through links and .

Note that even though there is no direct link from seed to page page is reachable from seed via three distinct paths which are highlighted 1 seed page page 2 seed page page and 3 seed page page page . We are interested in determining a shortest path from seed to page among all of these possible paths wherein the shortest path will be subsequently used to determine a ranking score for page . Note however that the illustrated lengths of the links in are not related to the metric which is used to determine the lengths of the links in computing the shortest path. We will discuss how to compute the lengths of the links below.

In one embodiment of the present invention a large number of reliable international seed pages s s . . . sare used to compute the PageRank scores. For each i 1 2 . . . n we would like to calculate PageRank Rbased on Equation 2 and set the final PageRank for a page p in the set of pages P to be  max 3 where k is a positive integer between 1 and n and k max represents the klargest value.

With a large set of seeds one may want to promote some seeds and demote others. This can be done by assigning each seed san optional positive weight w which has a default value of 1 and modifying 3 by  max 4 

Note that using the klargest ranking score facilitates suppressing unfairly high scores due to lack of proportionality at the vicinity of the seeds. In practice it is sufficient to choose k to be a small integer for example 3 4 5 or 6.

So far we have ignored the complexity issues from using the large set of seeds. Next we will discuss how to reduce the complexity of Equation 3 or 4 .

To compute distances between pages in link graph we need to assign a length to every link. The length of a link can be a function of any set of properties of the link and the source of the link. These properties can include but are not limited to the link s position the link s font and the source page s out degree.

Referring to Equation 2 for each link q p the contribution of page q to page p with respect to seed scan be expressed as 

Let s s . . . sbe a set of seed pages and for every 1 i n let wbe an optional positive weight with default value of 1 we can approximate the PageRank of page p in the set of pages P with respect to the set of seeds s as 1 7 

Note that the length equation 10 includes a term log q so that the length of the link increases as the number of outgoing links from the source page q increases. More generally the length is a monotonic non decreasing function of the number of outgoing links from the source. This definition is related to the PageRank computation in a sense that a higher ranking score is corresponding to a smaller out degree q wherein the smaller out degree results in a shorter length of the link. We will provide other length models for computing the length of a given link below.

For any given pair of pages u and v let D u v be the distance of the shortest path from u to v if no such path exists D u v . We define a distance system including the shortest distances D p from the set of seeds s to page p according to 1 11 

Note that similar to assigning the klargest value of R p as the final PageRank R p we have set the final shortest distance for page p as the kshortest distance among the set of shortest distances D p for the same reason as mentioned above.

The relation R p edefines a transformation from Equations 7 8 and 9 to Equations 11 12 and 13 such that 

From observing Equation 15 one would appreciate that a larger PageRank score for page p is corresponding to a shorter distance from seed sto page p. The meaning of Equation 16 is that instead of calculating the PageRank score R p one can alternatively calculate D p which is the distance from the knearest seed top where the distance from seed scan include an optional initial distance d . Hence the goal of the ranking computation is translated into findings the shortest distances to any given page from the nearest k seeds. This computation can be preformed together for all the pages and seeds.

Referring back to Equation 10 if we ignore the weights that can be assigned to a link we can rewrite the length of the link to be 

We then examine the conditions where a monotonic non decreasing function 0 N R can be used for defining the lengths of the links given the out degrees of the source pages L q p q .

As expected d log d satisfies this condition and so does 1. More generally every function x g log x where g is a concave non negative real function on 0 will satisfy condition 19 because for every 0 n n log log log log log log 0 log . 20 General Process of Ranking Based on a Shortest Distance

Next the system computes shortest distances from the set of seeds to each page in the set of pages based on the lengths of the links between the pages step . More specifically for each given page in the set of pages the system identifies k nearest seeds among the set of seeds wherein k

Note that it is possible for a selected seed to comprise more than one page. In such cases the shortest path from the seed to any target page will be defined as the shortest path from any of the seed s pages to the target page.

The system next determines a ranking score for each page in the set of pages based on the computed shortest distances step . In one embodiment of the present invention for each given page the system first identifies the kth nearest seed in the computed shorted distances for the give page and subsequently computes a ranking score for the given page based on Equation 16 . Finally the system produces a ranking for the set of pages based on the ranking scores for the set of pages step . Note that however not all the pages in the set of pages receive ranking scores through this process. For example a page that cannot be reached by any of the seed pages will not be ranked.

Note that the results from above ranking process can be used for seed tuning. Specifically the ranking process produces lists of the nearest seeds and the lengths of the shortest paths for all the ranked pages. The system can process these results to extract information for each of the seeds with respect to the ranked pages. Next the system can use this information to evaluate the quality and the contribution of the seeds and then modify the list of seeds and or the weights of the seeds based on this information.

Note that the links participating in the k shortest paths from the seeds to the pages constitute a sub graph that includes all the links that are flow ranked from the seeds. Although this sub graph includes much less links than the original link graph the k shortest paths from the seeds to each page in this sub graph have the same lengths as the paths in the original graph. For each page p the maximum number of links to page p in this sub graph is at most k. Furthermore the rank flow to each page can be backtracked to the nearest k seeds through the paths in this sub graph.

During a subsequent search process a search engine receives a query from a user through a web browser . This query specifies a number of terms to be searched for in the set of documents. In response to query search engine uses the ranking information to identify highly ranked documents that satisfy the query. Search engine then returns a response through web browser wherein the response contains matching pages along with ranking information and references to the identified documents.

Note that the application of the present invention is not limited to the web and web pages. The general technique of producing ranking scores can be expanded to any hyperlinked database which can include but is not limited to hyperlinked documents of an enterprise.

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description.

They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

