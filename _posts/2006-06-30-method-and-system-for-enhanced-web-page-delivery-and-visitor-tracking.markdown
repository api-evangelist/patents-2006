---

title: Method and system for enhanced web page delivery and visitor tracking
abstract: A system for and method of enhancing web page delivery and visitor tracking. The invention provides the ability to control redirection of Web traffic of humans. It can identify visitors to a Web page, track their movements, log critical information, and analyze the Web traffic in order to judge the success in driving quality traffic to some known goal on a Web site, such as a sale. The system tracks visitors via use of redirection with an image tag. The invention can also use unique image marker references to prevent browsers from accessing cached images.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08701016&OS=08701016&RS=08701016
owner: SuperMedia LLC
number: 08701016
owner_city: DFW Airport
owner_country: US
publication_date: 20060630
---
This application is a divisional of U.S. patent application Ser. No. 09 845 575 filed Apr. 30 2001 now U.S. Pat. No. 7 260 774 which claims priority to U.S. provisional patent application Ser. No. 60 200 205 filed Apr. 28 2000 each of which is incorporated herein by reference.

A portion of the disclosure of this patent document contains material that is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever. Copyright 2006 Inceptor Inc.

The present invention relates generally to the enhancement of Web page delivery. More specifically the invention relates to techniques to increase visibility of Web sites control visitor redirections and analyze traffic. Thus the invention has application in the field of electronic commerce.

The ability to manage and control the typical Web site has become an increasingly demanding task. This is due to the complex nature of Web sites and their use of various technologies that provide dynamic content with the aid of complex content management systems utilizing database systems. These Web sites are designed to provide the optimal experience for the human user. This is often done by using sophisticated graphics and multimedia to provide a highly visual and personalized experience for visitors. For the online marketer all these factors provide a difficult environment for them to do their job of ensuring high visibility of their Web site analyzing customer behavior and then acting on that behavior in a timely and responsive fashion.

From the situation described above three primary factors for which help is required may be identified visibility control and analysis.

 Visibility involves all the points of presence that a Web site provider has on the Internet that allow visitors to find links to the provider s Web site. This could include 

In each case a Universal Resource Locator URL or Web address is provided that allows visitors to click on and find a page within the provider s Web site.

Search engine visibility is extremely difficult as search engines typically use programs called spiders to visit Web sites parse the text and then determine what terms known as a keyphrase best describes a provider s Web site. Such a process precludes search engines from seeing the bulk of most Web sites as they are only able to see the text on static Web pages and not the dynamic content held in databases nor the content held in graphics and multimedia. This situation leads search engines to often misrepresent or under represent Web sites and the content they hold. To compound the problem each search engine uses different criteria for ranking making it even more difficult to find a single page structure that appeals to them all. This also has an impact on the available number of pages that visitors doing searches could be directed to in order to find the content they are after. The visibility problem has been dealt with in the past by creating doorway pages for both people and search engines to enter through but while this is a refinement of the problem it does not solve the problem as a balance between what the search engines see and what people see must still be struck.

 Control relates to the ability when directing visitors to a provider s Web site to send them to the appropriate landing point . That is send them to the most appropriate page rather than just to the Home page of the Web site. This is often a difficult task especially when it is desired to change the page to which to direct visitors. In some cases this is just not possible. For example with search engines if a page is indexed the URL to which visitors will be directed cannot be changed at all. Similar cases with varying degrees of difficulty can be made for banner advertisements affiliate links and promotional emails.

 Analysis is most important to judge the success of the Visibility and Control aspects of the process with respect to driving quality traffic to some known goal in a provider s Web site such as a sale for example. Thus analysis in this case should provide the maximum amount of information between source and sale. While analysis of Web traffic is quite common it is limited in its ability to easily identify the source of the traffic and also in how well integrated it is with the Visibility and Control aspects. Having determined successes and deficiencies it is necessary to be able to easily and in real time make changes to the Visibility and Control aspects. If possible some situations should be handled automatically. Existing solutions track traffic once it comes to a provider s site but only determine its source with a great deal of work and often requiring changes to the Web site to do so. These solutions have no integration with the Visibility and Control aspects.

In one aspect the present invention is a method of enhancing web page delivery comprising the steps of receiving a request for a web page content from a requester identifying the requestor as either a human visitor or a search engine spider and redirecting identified human visitors to a web page in an existing web site. The system may for identified search engine spiders dynamically generate one or more web pages optimized for the particular search engine spiders and return generated web pages to the identified search engine spider.

Different web pages may be dynamically generated depending upon the particular search engine spider identified as the requestor. Updateable templates are merged with user entered data or information stored in a catalog database to dynamically generate the one or more web sites. In another aspect the present invention is an apparatus for practicing the methods described above.

In one aspect the invention is a system e.g. a method an apparatus and computer executable process steps for dynamically generating web pages for search engine spiders while redirecting human visitors to a web page in an existing web site.

Preferred embodiments of the system of the invention will now be described with reference to the accompanying drawings. The system is described below in terms of both overall methodology and a physical implementation in an actual working software application termed the Information Exposition and Control Engine or more briefly the IXC Engine . The system is intended to be integrated with technology that delivers Web pages and is invoked during the initial stages of the Web page delivery process.

The IXC Engine leverages the hypertext transfer protocols to control where a requested web page is held. Accessing a Web page typically is accomplished by the following steps 

During this interaction the Web server may perform other actions. This may include communicating to the Web browser that the desired page no longer exists at that Web site and indicating the new location for the page. This may be a permanent or a temporary relocation. In either case the Web browser will accept this new location and send another request for the desired page and the new location. In this scenario the steps of accessing the desired page could comprise 

The IXC Engine uses this ability to handle requests and issue relocation responses to not only control where requests are sent but also to generate Web page contents when needed. The remainder of this section discusses how this technique furthers the enhanced Web page delivery objective of the invention.

Note that search engine search results are obtained by presenting to search engines via their spider programs optimized virtual Web pages especially tailored for each of the search engines . The optimized virtual Web pages result in URLs that point back to IXC Engine via a network such as the Internet.

IXC Engine interacts via a browser not depicted with a customer or prospect when the customer or prospect clicks on a link that has been created through the IXC Engine and then distributed across the Internet via Banners Affiliate Links search engine results or E mails . Whenever a customer or prospect clicks on one of these links they are redirected to the appropriate page on an actual web site .

All actions taken whether the actions are visits by search engine spiders or redirections are logged and reported to an Online Marketer who configures the IXC Engine via graphical user interface . Customer or prospect navigation through Online Marketer s Web site can also be tracked and reported through image tags placed on each web page.

Below are described the primary processes of an embodiment of the invention a main process shown in a perform action process as shown in a redirect and track process as shown in a select redirect process as shown in and an optimized dynamically generated page process as shown in . Describing these as separate processes is for ease of explanation only and is meant by no means to be limiting. Indeed one skilled in the art should easily envision other program structures not organized into five processes that still fall within the scope of the present invention.

The individual steps which comprise the Perform Action Process are illustrated in detail . In this process the required actions are determined and performed. The steps which comprise this process are as follows 

In this process the appropriate redirection and tracking actions are determined and performed. depicts the steps in this process 

It should be noted that using a redirect for an image allows Web site providers to place image markers on their Web site that will redirect to an invisible image but produce traceable logs indicating which pages each visitor visits. A cookie redirect image pair can be used to identify a visitor and log the visitor s path through a Web site. The visitor is identified only by the information held in the cookie that is nothing other than a unique number.

In this process optimized web pages for search engines are generated. depicts the steps in this process.

To assist in operating IXC Engine it is necessary to have a user friendly graphical user interface GUI to configure the settings. For example GUI is employed in changing the redirect URL for simple redirects and the specifications for more complex redirections.

A reporting module operated through GUI may report all information captured throughout the previously described processes and access the real time state information mentioned for Active Routing. From the captured information it is possible to 

All of the information described above can be generated in simple report formats in real time to show the most up to date state information. Aggregation of all the data or select portions such as groupings of traffic channels data may be performed to provide this information on a daily weekly or monthly basis. Consequently a detailed media mix analysis can be performed to provide accurate cost benefit analysis across all traffic channels based on cost of acquisition e.g. cost of banner advertisements and their value e.g. value of each sale where a sale is marked as a conversion .

A real time tracking interface is also provided to allow selective tracking and monitoring of URLs. Monitoring allows a person such as an online marketer to see the number of visits to a particular page and if appropriate the value of the conversion.

This section includes a description of a preferred physical embodiment of the inventive system. Each of the process steps described in the previous section are not all described again but instead some specific examples are provided in order to demonstrate in specific terms how the invention might operate.

A plug in is required when IXC Engine is operating on the same Web server as the web site to which it is redirecting traffic. This plug in is needed to differentiate which requests are coming to IXC Engine and which should be passed onto the Web site . This is determined by the URL requested. If the URL requested is one used by IXC Engine then it is handled by IXC Engine otherwise it is handled by the Web server as it would have normally.

A preferred deployment is to operate IXC Engine on a separate dedicated Web server using a subdomain of the actual web site s domain name. That is if the domain name used by the web site was www.inceptor.com then the domain is inceptor.com and a subdomain could be www2.inceptor.com. Different Web servers may use subdomains of the same domain and still share cookies associated with the same domain. This is important when using cookies between web servers for the purpose of identification and ongoing tracking across those web servers.

The ability to differentiate agents and spiders and thus identify human visitors customers or prospects is accomplished by examining the User agent tag and the IP address of the HTTP request. Signature database stores both pieces of information and accepts frequent updates to keep this data fresh. An example of an extract from signature database is shown below 

Here an AltaVista spider is recognized by its user agent tag holding the phrases TV36 Mercator n2s7 A 1.0 or TV36 Mercator n2s7 B 1.0 or alternatively be recognizing it has an IP address between 128.177.243.1 and 128.177.243.255 or between 128.177.244 and 128.177.244.255. User agent tags and IP addresses may also be identified explicitly to identify visitors as human and respond accordingly.

It is also possible to take some traffic and assign it a username and password to allow it to access secure parts of a Web site. This occurs as part of the redirection process by providing the required user id and password as used in a HTTP authentication process.

A key feature in the process of generating optimized dynamic pages usually for search engine spiders is the use of templates. Templates dictate how information is presented and thus what information is needed either from a database or from the provider of Web site through GUI . Each template has placeholders for dynamic content placed in careful locations within an HTML Hyperlink Text Markup Language page. Some of the typical pieces of information required include 

When using templates to publish data from a database the hidden web it is also important that the database fields are mapped to the template s placeholders with any additional manipulation functions being made available. To enhance this capability IXC Engine may leverage the versatility of the Perl programming language. Perl scripts can be used in the templates to allow the greatest flexibility in adding features and manipulating data to generate the most appropriate HTML pages for each search engine.

It should also be noted that the flexible nature of the templates and their application allows for non HTML pages to also be generated from the data provided. This may include pages of the following format 

All pages created may also be presented to non spider traffic. For example a Web provider could generate a WAP version and make this available to human users browsing through their mobile phones. These can be identified by the user agent string used by WAP browsers.

A key feature of the IXC Engine is that the templates may be updated along with the spider signatures automatically and remotely and that the templates drive the data requirements from both the GUI and the database perspective.

As has been outlined in the preceding part of this application there are multiple ways that a redirection can be determined. Before covering these in detail the redirection process itself is covered as the same mechanism is used throughout the system.

IXC Engine leverages the HTML standards for Server Response Codes. To explain this process assume that the IXC Engine controls it may or may not generate a Web page depending on its use the URL http www2.example.com offer.htm and redirects human users who request this page to http www.example.com bargain.htm. To perform a redirection IXC Engine performs the following actions it is assumed that IXC Engine is operating on a Web server that handles the subdomain www2.example.com 

The definition of this particular response code in the working model falling within the category of Client Request Redirected further action necessary is as follows Moved Temporarily The requested URL has moved but only temporarily. The Location header points to the new location. Immediately after receiving this status code the client should use the new URL to resolve the request but the old URL should be used for all future requests.

The temporary nature of the redirection ensures that multiple accesses from the same source of traffic will always request the original URL and not cache the redirect URL. This is important as the IXC Engine allows for the redirect URL to be changed at any time with real time effect. As soon as this URL is changed the next person to request the original URL will be redirected to the newly entered redirect URL.

This same principle is used for all redirections. What will change is how this redirect URL is determined.

Additional information can be added to the redirection URLs which can identify the source of the redirected traffic e.g. which search engine or which email campaign . This information then enriches the weblogs stored in the web server rather than only having this information stored in the IXC Engine s logs. This enhances the information stored in the standard web logs used in all web servers.

Given the basic principle of redirection described above a number of mechanisms are available for determining the redirect URL. There are essentially two classes of redirect determination tasks static and active. Within each of these classes several approaches are available. Static approaches available include 

For Active Routing URLs a list of static URLs are made available entered by the administrator of the software . The available methods for determining which URL to use to redirect a visitor include 

For each URL provided by IXC Engine a static URL is assigned. This may easily be looked up as described in Step .

In both examples a URL is mapped to a redirect URL. The redirect URL exists on the actual website these could be static or dynamic pages . The IXC URLs can have any structure so long as the correct subdomain is used.

In smart redirects there is a database available this could be a text file with multiple fields for each record. One of the fields is a primary key unique identifying field for the database. The same database may be used multiple times and in different ways. Each use is called a campaign. The following extract of a database is used in the example only a portion of the Description fields are shown . Note that the field ISBN is the primary key it is a unique identifier for each record.

For each campaign a mechanism for generating the IXC URL from the data available is set. This is constructed by choosing which fields from the database to use in the URL structure. For example if we select the fields Title and Surname the IXC URLs would look as follows 

Next each of the records using a simple redirect must have a redirect URL generated dynamically for them. This is accomplished by specifying three components that will make up the redirect URL Stem Primary Key Tail. The following is an example of such a specification.

Using the Simple Redirect approach has wide use for systems that utilize the primary key to generate a dynamic page.

The advanced redirect mechanism uses the same process for generating the IXC URL but uses a much more sophisticated process to generate the redirect URL. It has two parts the Match Path and the Redirect Specification. The Match Path matches the incoming URL that is the IXC URL. This allows extensive use of the IXC URL as it can have additional information added to it and then incorporated into the redirect URL. Both use the Perl protocol for specifying a regular expression for the Match Path and the redirect specification.

Multiple Matching Paths may be specified. The first one that matches will then have its redirect specification enacted to generate the redirect URL. Should no Matching Path match the IXC URL a default URL will be used.

In the first example a match will occur whenever a URL has Wright in the midst of the IXC URL. This will then cause a Redirect URL to be generated using Author s surname that comes from the database entry for that record the correct record is chosen based on the primary key information held in the IXC URL .

In the second example the match is made with any IXC URL and the Redirect URL is generated by using the information held in the IXC URL. In this case the second matching component the part preceding the .htm is used to build up this URL.

These two examples show some simple uses of the database and matching components in building up a Redirect URL.

In selecting an Active Routing URL through Random selection a list of static URLs is specified as follows. The following static URLs are assigned for the defined active URL www2.example.com active offers.htm 

Whenever any visitor clicks on the URL http www2.example.com active offers.htm This URL may be embedded in a banner advertisement affiliate link email or a search engine result they will be taken to one of the three offer URLs within the www.example.com website chosen at random.

Using the example shown in the Random Example if Round Robin were used each visitor using the URL would be sent to the next URL in the list. The following table shows an example of redirections that would occur for the first 5 visitors to the URL http www2.example.com active offers.htm 

In this example a list of static URLs use the previous example s list is appended with a threshold value and a page marker described in a later section that indicates a successful conversion. A successful conversion therefore is a visitor clicking through this URL http www2.example.com active offers.htm and during the same online session arriving at the indicated page.

In this example a threshold of 3 is set and a selected page is marked. Since either Random or Round Robin may be used to select the next Redirect URL initially it is assumed that Round Robin has been selected. If the selected page is reached by any visitors a counter is updated for that redirect URL. The following table shows an example of some interactions. For ease of depiction the Redirect URLs are abbreviated as follows http www.example.com testoffers offer1.htm is depicted by offer1.htm . Also counter1 will signify the counter associated with offer1.htm counter2 will signify the counter associated with offer2.htm and so on.

Visitor 7 converting takes the counter for offer1.htm over the threshold 3 and hence all subsequent visitors are taken to offer1.htm.

In this example conversion works identically to conversion as in the previous example except that instead of tracking a threshold at a certain time the offer with the highest counter is selected for all subsequent redirects. Using the same example as above we set the artificial time for the decision to be 12 noon.

The only difference in this case is that the highest counter is chosen at a given time rather than a threshold value.

In this example each redirect URL has an associated threshold associated with it. As in the previous examples a counter is updated for each successful conversion. Once the threshold has been reached for a particular URL no further redirects are sent to it.

Using this test data and assuming Round Robin is used to select from available redirect URLs and similar schemes for counter maintenance these results follow 

As demonstrated in this example after visitor 7 offer1.htm is no longer used as it has reached its threshold value and is no longer valid.

This example demonstrates how date or time restrictions can influence which Redirect URLs are selected. For each redirect URL a valid date range must be used. This shown in the following table 

This example demonstrates that only offers valid for the visitor s visit date are selected. For dates outside of all the valid date ranges a default Redirect URL offers.htm is used for all Redirect URLs.

Tracking uses Redirection and cookies to track visitors through a Web site. This is accomplished by placing an image on a page that needs to be tracked. The image is placed using a standard HTML image reference and could look as follows 

The URL used is an IXC URL that will require a Simple Redirection to a real GIF file that is in fact invisible. The IXC URL is classified internally as a tracking URL and thus requires a cookie to be associated with the IMG request. If no cookie is supplied then one is allocated. Note the following with respect to cookies 

The cookies are also allocated whenever any visitor uses any of the IXC URLs. This allows the identification of the initial source of a visitor assuming that an IXC URL is used for each of the sources of visitor traffic Search Results Banner Advertisements Affiliate Links Email campaigns. Visitor traffic that arrives directly at the actual website will have a source identification of the first tracking IXC URL that it comes across this identifies where the visitor was first noticed.

Reporting on the above statistics and metrics using these facts are created. Additional information can be gathered and reported on and is covered in a later section.

To speed up downloads many Internet Service Providers ISPs and businesses use caching. Caching stores pages accessed by persons connected via their Internet services so that persons accessing the same page may use a local copy rather than getting a new copy of the page directly from the issuing Web site. This can cause problems with the image markers used in tracking as cached image references will not access the IXC Engine to access the marker and hence will not update the IXC logs.

To circumvent this problem advanced markers are employed which use Java script to generate what appears to be a unique marker reference for each access of the markers. This is done by appending a timestamp which is ignored by the IXC Engine but seen by the caching software as a unique URL. An example of the Java script code is shown below 

This script ensures that any browsers that can t handle Java script will run the normal image reference with a reference saying Javascript was not available otherwise it generates a unique image reference using a timestamp and thus cache busting .

As was shown in the previous section additional information may be passed with the image references. In the previous case it was either a timestamp or simply a note to indicate that Java script was not available js no . This information is logged and if needed reported.

Information that is useful to gather includes the value of conversions mentioned in previous sections. This is done by including a reference to the value variable stored in the IXC Engine for reference and then the value of the conversion.

A simpler image reference example the more complex Java script code is amended in a similar way could appear 

In this example the variable stored within the IXC Engine value and the variable found on the tagged web page is ordervalue . This ordervalue variable is part of the web page that has been marked and will be replaced by the value it holds when the marked web page is generated.

As well as the content provided via the markers other information is also sent along in the logging process. Most importantly the referring URL is logged. This is the URL used to generate the web page that the marker has been placed on. The following is an example of such a URL 

This information can be processed in reports to enhance the data being shown in the clickpath. If merged with external data e.g. product descriptions it could add much more meaning to reports and allow different reporting views.

For web traffic generated through retention email it is possible to track with more detail. An email campaign is the result of creating an email template that has several URLs embedded in the message. The objective is to get existing customers who have supplied their email address and given their consent to be sent email offers to click on these URLs and perform some action e.g. purchase signup etc .

To allow more detailed tracking each email that is sent can have an identifier built into its URLs that identifies the recipient of the email. With this information the source of the traffic can be identified to the recipient of the email allowing reporting to not only show whether the email campaign was successful for each recipient but also allowing more detailed tracking of what each recipient does on the web site.

This information can then be used to refine subsequent email campaigns by taking into account recipients actions to previous email campaigns.

Other embodiments of the invention will be apparent to those skilled in the art from a consideration of the specification or practice of the invention disclosed herein. It is intended that the specification and examples be considered as exemplary only with the true scope and spirit of the invention being indicated by the following claims.

