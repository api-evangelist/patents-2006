---

title: System and method for keyword extraction and contextual advertisement generation
abstract: A computer-implemented system and method for keyword extraction and contextual advertisement generation are disclosed. The system in an example embodiment includes a keyword extraction service to obtain information related to user activity on a host site and to extract relevant keywords from content of a web page, the information related to user activity on the host site being used to determine relevancy of the extracted keywords, and a contextual advertiser to produce an advertisement placement on an affiliate web page, the produced advertisement placement being relevant to user activity on the host site.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08001105&OS=08001105&RS=08001105
owner: eBay Inc.
number: 08001105
owner_city: San Jose
owner_country: US
publication_date: 20061227
---
This patent application claims the benefit of the filing date of U.S. Provisional Patent Application Ser. No. 60 804 387 filed Jun. 9 2006 and entitled SYSTEM AND METHOD FOR KEYWORD EXTRACTION AND CONTEXTUAL ADVERTISEMENT GENERATION the content of which is incorporated by reference herein.

This disclosure relates to methods and systems supporting online advertising and online transactions by a user. More particularly the present disclosure relates to keyword extraction and contextual advertisement generation.

An increasingly popular way of delivering Internet advertisements is to tie the presentation of advertisements to particular user behaviors and or user profiles and or user demographics. Such user behaviors include user access to a particular web page user selection also called mouse clicking or clicking of a particular location on a web page user entry of a particular search string or keyword and the like. In order to target advertising accurately advertisers or vendors pay to have their advertisements presented in response to certain kinds of events that is their advertisements are presented when particular user behaviors warrant such presentation. If a particular advertisement ad leads to some user action an advertiser may receive remuneration for the ad.

Using other systems and processes on the Web users can search for goods and services via the Internet and shop or make purchases of goods or services over the Internet. Unfortunately conventional systems have not been able to create an effective way of extracting keywords from web pages and create contextual advertisements that may lead to a user purchase transaction.

Some conventional web based merchants use affiliate programs. In an affiliate program the merchant itself must track purchase transactions and reward 3party affiliates when purchase transactions are completed. This transaction tracking and rewarding process imposes a significant administrative burden on the merchant. Moreover the tracking reward functionality must be replicated for each merchant that chooses to use such a system. Current technology does not provide a solution for off loading this tracking reward functionality to a 3party without risking an increase in fraudulent transactions and a decrease in the time efficiency of processing purchase transactions.

U.S. Pat. No. 5 948 061 discloses methods and apparatuses for targeting the delivery of advertisements over a network such as the Internet. Statistics are compiled on individual users and networks and the use of the advertisements is tracked to permit targeting of the advertisements of individual users. In response to requests from affiliated sites an advertising server transmits to people accessing the page of a site an appropriate one of the advertisements based upon profiling of users and networks.

A computer implemented system and method for keyword extraction and contextual advertisement generation are disclosed. In the following description numerous specific details are set forth. However it is understood that embodiments may be practiced without these specific details. In other instances well known processes structures and techniques have not been shown in detail in order not to obscure the clarity of this description.

As described further below according to various example embodiments of the disclosed subject matter described and claimed herein there is provided a computer implemented system and method for keyword extraction and contextual advertisement generation. The system includes a keyword extraction engine operable to extract keywords from various sources based on user interaction with networked content. Further the system includes a contextual advertisement generator to produce advertising or information content correlated with content with which a user is or has interacted. Various embodiments are described below in connection with the figures provided herein.

Functionality for various embodiments includes components for 1 building the core components to analyze content and perform keyword extraction for a Host platform 2 building the additional components to enable the Editor Kit to integrate with the keyword extraction system and provide contextual advertisements 3 enabling contextual advertising capabilities for the Editor Kit by providing ranked and scored suggestions for searches keywords category constraint categories products and catalog properties 4 using the keyword extraction system in multiple system features both on and off the Host where unstructured text content is read by users.

The Host may lack the capability to analyze large volumes of unstructured text and determine if that text contains any keywords that would be of value to the user reading the text with relation to the Host. Creating this capability will enable several short term and long term product opportunities for on Host product features the Host related sites and off Host third party deals.

The first use case of this capability is contextual advertising with the use of the Editor Kit. This will help content oriented affiliates who publish diverse content frequently and across large numbers of pages and sites.

In various embodiments described herein functionality is included to analyze content from any URL via HTTP extract searches keyword category constraint categories products and catalog properties that are relevant to the content rank the relevant results according to measures of popularity supply and other performance measures obtained from tracking aggregate user behavior on the site and use feedback to improve the rankings and results over time.

The following use cases illustrate how the keyword extractor service of an example embodiment is used in different system features. The service is designed to make it extensible across all the use cases.

The Keyword Extraction KE service provides at least two levels of service in an example embodiment. One is a near real time capability for time critical applications. The second is a delayed analysis capability with a less stringent expectation for the return of results.

The Keyword Extractor is a system service that analyzes HTML content and extracts relevant keywords from that content by using a variety of information. This information includes frequency of user queries listings availability and catalog data. illustrates a high level architecture of the keyword extractor system in an example embodiment.

There will be many different types of consumer applications that will call the keyword extractor service. The main ways consumer applications interact with the service include submitting URLs to the service receiving data back from the service and emitting impression and clickthrough tracking events only the Host consumer applications .

The consumer application could either be an internal Host product feature or an API application programming interface call being used by affiliates to access the service. The following parameters can be provided by the consumer application when requesting results from the keyword extractor.

This component is the primary interface to the keyword extractor service. If the particular URL algorithm combination that the consumer application is requesting has already been processed and exists in the cache then the data is returned. If the URL algorithm combination has not been processed and cached yet then a check to determine whether it s still being processed or this URL algorithm combination has never been seen before. Depending on the result either a status code is returned to the consumer application or the URL algorithm required is published as a batch execution event in order to get the URL fetched and analyzed. illustrates the basic logic used in the Editor Kit front end of an example embodiment.

The interface is a method available for consumer applications to call the service and obtain results. Many different types of consumer applications will call the service and may generate a high load of requests. In order to invoke the service several parameters may be provided some are required while others are optional. Only internal Host applications will call the service directly through the interface. External consumer applications e.g. affiliate applications will have to use a Developer s Program API call in order to access the service. The parameters described below are fairly specific to the Contextual Editor Kit use case. In addition these can be extended in order to support keyword extraction for other sites e.g. Kijiji .

All of the input parameters should be validated to make sure they are properly formed and contain valid values. Any invalid parameter should cause the front end to return an error code to the consumer application.

If the URL is brand new actually if the URL Site ID Category ID Hint Algorithm Algorithm Version combination is new since this combination defines the primary key then the URL needs to be fetched and analyzed. If the same URL is submitted again but any of the other parameters in the combination is different then a new fetch and analyze is required since these parameters will influence the result. In addition various embodiments can initiate a re fetch of the content of a particular page based on the observed changes in the keywords extracted for that page. In this manner the keywords extracted for a page can act as a proxy for the content of the page. Thus as observed changes in the keywords extracted for a page occur changes to the content of the page can be inferred and a re fetch of the page can be automatically initiated.

If URLs are submitted with session specific parameters embedded in the query string i.e. session ID then the system will treat each of these URLs as unique even if they display essentially the same content . The system may not attempt to identify these types of URLs.

This database contains the information that is generated by the Extractor Service for each URL and returns the data to the Editor Kit Server FE Front End when a particular URL is requested again in order to eliminate the latency associated with the fetch and extraction process. The cache needs to be periodically flushed e.g. every 7 days of URLs that have not been accessed during the previous time period in order to save space. The time period for performing the check and flushing the cache should be made configurable. The cache needs to be extensible enough to hold different result data types in the future i.e. Listings Reviews Guides Kijiji postings or the system should be able to support multiple types of caches depending on the use case. The cache should support all languages including double byte ones.

This component contains queues for unfetched and fetched URLs as well as associated metadata for those URLs.

The Fetch Extract Consumer component is responsible for consuming URL.FETCH events via BES. For each event consumed the component will fetch the HTML content and any associated external CSS files from the target URL. Once the HTML and CSS have been fetched from a URL the information is passed to the Extractor Service for processing.

The fetcher will save content on only single pages identified by the URL in the URL.FETCH BES event. The fetcher will not identify additional URLs i.e. links on the page in order to crawl deeper into the site.

Any URL submitted needs to be periodically re fetched unless the re fetch time was set to zero in order to determine if the content on the page has changed and caused a different set of keywords to be created. Each page has an optimal re fetch time that is algorithmically determined by the system. The goal is to refresh the cache contents at or near the same frequency as the URLs publishing frequency.

The traditional method of determining whether to re fetch a page would be to schedule a periodic batch job that would check the re fetch times on all URLs to determine if any of them had expired. Those URLs whose re fetch times had expired would be queued up for fetching and re analysis.

Instead of having a batch job periodically examine all URLs for those whose re fetch times have expired the alternative is to examine re fetch times of those URLs that are requested as a result of an impression event. If a URL is served and its re fetch time has expired or is close to expiring i.e. within 30 minutes configurable without a train roll then an event to re fetch and analyze the URL is published.

All page source content should be fetched this includes everything unless there is a specific exception noted in the following table.

Each URL has a re fetch interval or time that is calculated after each time the page contents are fetched extracted and analyzed. The purpose of calculating the re fetch interval is to determine the optimal frequency at which a URL changes or updates its content on average so that the results that are cached for the URL are as up to date as possible. The system should continuously monitor and adjust as the publishing patterns of the URL change. To start with all URLs receive a default re fetch interval i.e. 24 hours . In order to determine if a URL s content has changed a fingerprint needs to be generated for each extract and analysis. In this case the fingerprint will be generated from the top n Searches keyword and category for a given URL. To determine if a fingerprint has changed a set comparison needs to be made between the Searches in the previous fingerprint and the current one. If any of the individual Searches has changed keyword or category or the sets have a different number of Searches in them then the fingerprint has changed ranking or scores are not relevant. If the sets are equivalent then the fingerprints and therefore the URL contents can be considered the same. Based on changes in a URL s fingerprint the following decisions need to be made 1 whether to increase decrease or not change the re fetch interval and 2 how much to increase decrease the re fetch interval. The general scheme for this is outlined below.

If the Keyword Store is refreshed with new data this may cause a certain set of pages to change their fingerprints the next time they are refreshed causing a decrease in their re fetch interval.

The fetcher will likely encounter many situations i.e. 4xx status codes where it cannot properly fetch a page. In general the fetcher should attempt to re fetch the page when it encounters problems. Appropriate error messaging should be provided to the consumer application i.e. EK Server FE so that the consumer application can take the appropriate action.

This component is responsible for taking the page data HTML and CSS from either the Fetch Extract Consumer or Editor Kit Preview FE components and extracting and ranking keywords from that data with the help of the HTML to Text Parser and the Text to Keyword Extractor Ranker components.

The results should be assembled into a dataset that is easily parsed i.e. XML by the consumer application EK Server FE or EK Preview FE . The dataset should be easily extended to hold new types of data i.e. Listings Reviews Guides Kijiji postings . Each data type should have its own section in the data. Each section should its results sorted by rank in ascending order.

In either situation when no results can be extracted or returned for the given URL i.e. not enough content or content that does not overlap well with the Host community then a default set of results should be provided. The default results will be the top n ranked keywords within one or more categories. If no category hints were provided then the category root will be used. In situation 2 when no keywords can be extracted from the content the system should remember this so that the page is not re fetched and a useless extraction performed each time the URL gets an impression.

This requirement is for taking the raw HTML and CSS if it exists and generate clean text for easier processing by the Keyword Extractor Ranker SIBE service. The parsing will also analyze the content and provide weightings for certain pieces of text that it thinks are more important. These weightings will influence the final weighting of the keywords.

The main goal of the parser is to extract the content and remove all the extraneous elements that are needed to format a page. In general all tags for structural and formatting should be removed unless specifically mentioned in the table below and all the content in the body of the document should be kept. Note that some of the tags and CSS directives will be used to generate weightings to influence keyword ranking. Additionally meta information tags can be used to determine keywords and context of a page.

The page being parsed may implement content indicator tags. These are the Host proprietary tags that indicate which ranges of text are actual content as opposed to UI user interface navigation elements . These will allow better accuracy on pages that contain a lot of irrelevant content on the pages. The tags are optional and may not be embedded in all of the pages that the system fetches. A page may have multiple pairs of content indicator tags embedded in it. If the one or more pairs of content indicator tags are present then only the text in those sections should be parsed. Any content outside of those tags will be thrown away unless there are no tags present at all then the entire page should be analyzed. The content indicator tags should not be nested or overlapping in any manner. The content indicator tags should be easily parsed and should not cause the page they are embedded in to render differently. Possible implementations are using a DIV tag with a custom class or using a comment tag with a specific string. Comments are probably preferred because they will not cause browsers to place a line break before and after the DIV element.

The weighting scheme will apply a set of rules that are based on the formatting and metadata of a page. The rules will assign a weighting to the areas of text and metadata that meet the requirements of a rule. Text that does not meet any of the rules will be classified as neutral weight zero . Note that this does not mean that neutral weighted text has zero weighting. Adding new rules and changing weightings for existing rules should be easily configured without a train roll. The weighting of the text should not destroy any of the context in the document i.e. phrases should not be broken up . This is because formatting boundaries are not guaranteed to coincide with token boundaries therefore weighting chunks of text should not create artificial token boundaries. There will be only one set of weighting rules for all sites having per site rules is too much of a maintenance problem .

Rules can apply to various elements on a page but will mostly apply to meta tags HTML tags and CSS rules.

The ability to configure a different set of rules for different languages or groups of sites should be supported by the system. Different languages use different text sizes but that doesn t mean words in one language are more important than words in another language. For instance compared to English words Chinese words must use a larger text size to be readable. Since other languages will be sized differently due to character set differences the default weightings may produce undesired results.

The text should be pre processed in order to normalize all variations and put the text into a consistent format. Some scrubbing procedures may not apply to all languages. The scrubbing process should be identical to the one used for scrubbing queries on the site in order to ensure that both processes are generating the same output.

The Text to Keyword Extractor Ranker component consumes the output derived from the actual content of the HTML to Text Parser and analyzes it with the aid of the data in the Keyword Store. The output is a set of assets that is contextually related to the analysis and metadata for each asset. An asset represents anything that could be surfaced to the user reading the original content. This document will only focus on specific assets that exist on the Host .com and country sites but the system should be designed to be extensible enough so that other assets could be added whether from the Host i.e. Reviews and Guides or come from affiliated sites such Kijiji i.e. postings .

All of the tokens should be run through three operations spell check stemming and transliteration. Each token should be spell checked and replaced with the top spell check suggestion if there is an error in the original token. Perform stemming and transliteration on all the tokens in order to normalize them. After these three processes are performed on the tokens then the metrics should be combined according to pre defined rules.

After spell check and stemming operations tokens that are identical should be combined into one metric along with their associated metrics. All the metrics should be added together.

The general framework of the ranking system in an example embodiment is to use multiple inputs in the form of histograms and combine the data from the histograms in an equation that will produce a numerical value for each token. The framework should be flexible enough to add additional algorithms in the future and also change the equation that combines the data from the histograms into producing a numerical value for each token. This is needed to support A B testing of different algorithms.

New algorithms can be created either by 1 configuring the weightings of various histogram inputs into an existing algorithm. This should be done by without requiring a new train roll. Different weightings for the same basic algorithm should be available simultaneously for A B testing or 2 creating a brand new algorithm that computes the ranking in a brand new manner. This can be done with a new train roll.

In an example embodiment rankings will be produced for the following Searches keyword category constraints and Categories. The ranking system should be extensible to allow the addition of other types of rankings i.e. reviews guides Kijiji postings etc. .

Ranking keywords will use both relevance data and financial data to rank each keyword category . Both sets of information may be combined in order to create a single value for each keyword category that indicates the relative value of the keyword category compared to the other keyword category items in the same result set.

The overall keyword ranking process in an example embodiment is illustrated in and explained as follows 

The step of categorization and tokenization of the content is based on site wide supply and demand data as well as URL specific data all of which are processed by the pseudocode set forth below. Note that site wide bid BIN data will not be used in this step.

Each keyword category will have a relevance score computed for it as part of the categorization and tokenization step.

The relevance score for each keyword category is transformed into a probability score based on the relative difference between keyword category elements for the page.

Given a set keyword category items from the relevance scoring steps the system should use the combination of Host ID URL keyword category to look up the historical financial performance of that combination recency weighted average of bid BIN and registration activity . If the historical financial performance is not available then an estimate should be used by looking up the alternate aggregate financial information for the keyword. The financial score will be in the currency of the Site ID used and represent the expected value of bid BIN and registration activity created per one thousand impressions of a given site ID URL keyword category combination.

The expected financial value for each keyword category is transformed into a probability similar to relevance probability in step 3 where the expected value of the keyword category combination is considered in relation to the combined expected value of all the other keyword category combinations for the page.

The relevance probability and financial probability for each keyword category item are mathematically combined to produce a single probability score for each keyword category item.

Once the single probability score is calculated for each of the keyword category items in the set the results can be stored in the URL to keyword cache for a front end application to access.

The Keyword Store contains the various histograms that act as inputs to the ranking algorithm. Each country site on the Host should have its own set of histogram data to provide accurate results for content driven ads that will be driving users to that specific site. This component should also be made extensible so we can add sets of metrics from additional platforms to the system i.e. Rent.com or Kijiji sites when we extend keyword extraction to those platforms and suggest assets from those systems. Different platforms will likely have different sets of histograms. The histograms in this section are those that will specifically run the keyword extractor system for the Host platform. The data for the following histograms do not necessarily need to be implemented as separate data structures. They are separated logically in the diagram for clarity. The histogram data should be refreshed on a regular basis in order to accurately track trends and provide accurate recommendations.

This histogram will associate with each search query the frequency with which users clicked through to a view item page on a per category basis. illustrates a graph showing association of category ID to query term in an example embodiment. For each listing that a user views after a search the category ID of the listing is associated with query term and the count of view item actions for that particular query term category ID combination is incremented by 1. If a user views multiple listings after a search i.e. repeatedly clicking back in their browser and clicking on different listings in the search results then all of those actions should be counted. View item counts at child categories should be aggregated up the category tree to parent categories.

This histogram will associate with each keyword i.e. search query the number of listings available on the site on a per category basis. This histogram should be built by determining the number of listings all formats whose listing title and description match the given keyword available across all categories i.e. execute a search . This data should be broken out on a per category basis and the number of listings at child categories should be aggregated up the category tree to parent categories.

This histogram will associate with each keyword the frequency with which users bid or BIN on listings related to those keywords on a per category basis. illustrates a graph showing association of bid amounts to query term. For each listing that a user bids on after performing a search then the category ID of the listing as well as the bid amounts absolute and differential are associated with the query term and the count of bid actions for that particular query term category ID combination is incremented by 1. The event should be tracked regardless of how it was generated i.e. manual bid or proxy bid . Bid counts and amounts at child categories should be aggregated up the category tree to parent categories.

This histogram will associate with each keyword the frequency with which users BIN through on those keywords on a per category basis. illustrates a graph showing association of BIN amount to query term. For each listing that a user BINs on after performing a search then the category ID of the listing as well as the BIN amount absolute are associated with the query term and the count of BIN actions for that particular query term category ID combination is incremented by 1. BIN counts and amounts at child categories should be aggregated up the category tree to parent categories.

This histogram will associate with each keyword the frequency with which users clickthrough to an item which is associated with specific product on a per category basis. illustrates a graph showing association of product reference ID to query term. For each listing that a user views after a search the product reference ID of the listing if available is associated with query term and the count of view item actions for that particular query term product ID combination is incremented by 1. If a user views multiple listings after a search i.e. repeatedly clicking back in their browser and clicking on different listings in the search results then all of those actions are counted if a product reference ID is available. If no product reference ID is associated with the listing then no event is registered and not stored in the histogram. Product reference ID counts at child categories should be aggregated up the category tree to parent categories. Only the top n products within each category need to be stored. The rest of the data accumulated by the query index does not need to be held in the Keyword Store since for Keyword Extractor purposes we will only be interested in suggesting the top few products associated with a keyword and or the products that show the greatest acceleration in search to view item clicks.

Based on the total number of impressions and clickthrough events the clickthrough rate CTR can be calculated for any asset that is made available in ads via the Contextual Editor Kit. By tracking the clickthrough rate CTR for Contextual Editor Kit ad placements the system can be influenced to rank assets with better CTRs higher and produce better results. Note that there can be multiple CTRs for a given keyword due to the various types of impressions and clickthrough events.

This histogram is similar to the one described above but differs in one key data point. The data should be attributed back to the keyword impression that was made in the ad placement on an affiliate site not any intermediate keywords a user searched on during their session while the category ID and dollar amounts are derived from the particular listing. In addition the various other feedback tracking dimensions described herein need to be captured as well. illustrates a graph showing association of Bid amounts to ad query term.

The data should be attributed back to the keyword impression not any intermediate keywords they searched on . This histogram is similar to the one described above but differs in one key data point. The data should be attributed back to the keyword impression that was made in the ad placement on an affiliate site not any intermediate keywords a user searched on during their session while the category ID and dollar amounts are derived from the particular listing. In addition the various other feedback tracking dimensions described herein need to be captured as well. illustrates a graph showing association of BIN amount to query term.

In order to refine keyword probabilities based on actual performance the system needs to analyze feedback events in aggregate. The financial value driven by a particular site ID URL keyword category combination will be tracked and aggregated on a regular basis. The aggregate data is then used to refine the financial expectation and probability score.

For each unique site ID URL keyword category the total financial value driven per thousand impressions should be calculated based on various financial events such as bids and registrations. The calculation needs to be statistically significant so an adequate number of impressions need to be shown to reach a desired confidence interval.

This component will periodically update the histograms stored in the Keyword Store from various data sources. The Keyword Store should be refreshed on a regular basis.

A blacklist should be used to filter keywords based on precise match prior to the keywords entering the Keyword Store. This will prevent these keywords from being recommended assuming the Keyword Store gets rebuilt and not incrementally updated . There will be an additional blacklist check in the Editor Kit Server Front End in order to catch keywords that are added to the blacklist between refreshes of the Keyword Store.

The query index will use data generated by various embodiments to find queries entered by users searching on the Host and aggregate metrics about the user s actions after they obtain their search results and associate those aggregate metrics to the query terms. The user s search and related activity must all occur within the same user session. The query index should support all languages used by on platform sites. The index should be refreshed periodically i.e. ideally daily refresh minimum weekly refresh in order to accurately track changes in aggregate user actions.

The system will be extensible to incorporate additional sources of data to be used in the keyword extracting and ranking algorithms.

Additional data will be sourced from the Keyword Data Mart KWDM . The metrics will be used in the token scoring algorithm to influence the final ranking of keywords towards those keywords that are expected to generate more revenue. If the Keyword RPC metric is not available for a keyword during the ranking process then the ranking algorithm should use the other keyword metrics available.

Two classes of events will be tracked in an example embodiment. The first class is feedback events. These events will allow the system to improve its performance over time by incorporating actual user activity into the system. The second class is performance tracking events. These are for internal reporting purposes in order to evaluate the system s performance. The tracking system should be extensible enough to add different events for different use cases or to track new performance measures in the future. The feedback events will be aggregated on a regular basis by a batch job in order for easier consumption by the Keyword Store Builder. The events should be tracked only for users that are shown an impression and clickthrough on one of those impressions and navigate the site. Events should be tracked at 100 . Note that some of the tracking information will only be available at impression time but will need to follow the user as downstream tracking events are generated. The following are the individual measures that should be tracked when events occur.

The following are the dimensions that the individual measures can be identified by. Not all dimensions may be applicable for particular type of event. Note that certain dimensions will follow a user throughout their session i.e. the affiliate URL where they initially viewed the impression .

The objective of the feedback tracking is to determine which assets i.e. searches listings products categories etc. are actually performing the best and to use that data to influence the ranking of various assets. In the Contextual Editor Kit use case we are interested in tracking user activity both on the affiliate site and on the Host to determine which searches keyword category categories and product suggestions actually produce the best clickthrough rate and activity on the Host site.

If ad unit is requested the system should register one or more of the following impression events the number and type of impressions is dependent upon what results are displayed . A user interface in an example embodiment is presented in as a generic mockup showing impressions generated from one ad unit.

Impressions may need to be differentiated from each other in some embodiments. For example there are multiple types of search on the Host core search product based search three variations of Stores search .

Whenever a user viewing an impression actually takes and action and either clicks through or executes a search then the clickthrough event should be registered. All clickthrough events should be counted. There will be no filtering of repeat clicks from the same user as there will be no issues with click fraud.

Once a user performs a clickthrough to a Host site via an ad unit impression certain events will be tracked as input to the feedback mechanism. Only the events that occur during the user s session will be registered.

Performance tracking events generate data that will allow us to analyze various aspects of system performance.

Performance tracking data should be accessible so that ad hoc queries can be run in order to determine how the Contextual Editor Kit ad placements are performing. Since the analysis will be mostly ad hoc the types of queries and aggregations will not well known in advance.

This batch job takes the detailed level tracking metrics for the feedback system and aggregates them into a useful form that can be used to complete the feedback loop. The batch job should aggregate data on a weekly basis. For the feedback data at the Editor Kit level the primary purpose is to separate the data out at a keyword URL level so when the aggregated data is folded back into the ranking algorithm that keywords on URLs that have higher clickthrough rates or higher onsite activity will have those keywords rank higher as time progresses. When ranking keywords for a given URL if specific URL Page Domain level aggregated feedback data exists then this should be used in the ranking algorithm to refine the final ranking of the keyword. The feedback data should only be used if a statistically adequate number of data points i.e. impressions for the given keyword URL Page Domain had been received. This should be set to 100 data points initially and be made configurable without a train roll. Otherwise the ranking algorithm should simply leverage the existing site wide tracking data for the keyword.

The feedback data should be aggregated according to the dimensions described herein. Each week of aggregate data should be maintained so that historical trends can be taken into account during the ranking of tokens.

The aggregated keyword level data should be made easily accessible. It may be advantageous to pull the entire dataset on occasion to analyze the data for various correlations to paid search performance.

Keyword Extractor KE currently suggests keyword category combinations only if the keyword appears on a page that it processes. KE cannot suggest keywords that do not appear on the page even if they are highly relevant to the context of the page. By leveraging the existing data that powers the Related Searches feature on a particular host KE can gain the capability to suggest new and relevant keywords that do not appear in the original content of a page.

The current Related Searches feature works by aggregating data about consecutive searches performed by users. This data allows the website to know that users who search for say harry potter are also likely to search for harry potter wand and harry potter dvd afterwards. These follow on searches are automatically suggested whenever a person types in a search on a particular host.

KE combines Related Searches data with the keyword data extracted from a page. This could be done in a variety of circumstances such as when page content is sparse the page content is of the type that does not yield an adequate number of keyword matches or when related searches may yield better relevance or have a higher expected return.

For instance the top ranked keyword category combination extracted from a page would be used to look up all the related searches for it. Then the related searches returned would be scored according to their relevance and expected return although since the related searches do not appear on the page they will not have any context data which will need to be compensated for during scoring this could involved the use of Related Searches clickthrough rate data . The keyword category combinations and related searches can then be combined and rank ordered as usual. The combined data can then be passed to various applications for use such as AdContext.

All standard tracking impression click and post click activity may be monitored for keywords that are surfaced through Related Searches data so that their performance is optimized over time.

1 Editor Kit EK the current EK will include the Keyword Extractor backend in addition to redesigning the ads and EK creation flow.

The Keyword Extractor service can be used to automatically generate contextual EK listings. The Editor Kit has been augmented to provide the Contextual Advertisement Generator.

Various embodiments have a direct dependency on the Keyword Extractor functionality described above. Refer to the Keyword Extractor description herein for details on the following issues.

When setting up a new EK ad an EK to KE interface interaction may occur. This interaction may include a real time preview as detailed in for an example embodiment. Performance requirements for the real time preview are noted in the KE description above. The dataset returned to the EK is then used to generate relevant listings as outlined above.

After an EK is created the Javascript code is then embedded into a web page s source code. The ad is then considered published. The ad will load once the web page is rendered and the EK to KE interface interaction as shown in may occur. The URL used for a published ad is the web page that the ad is placed. The URL submitted by the Affiliate at creation should not be used after the preview. Both the category ID s and site ID are the parameters specified by the Affiliate at creation. The KE service will return the top overall keywords if there is a Fetch error or if no keywords are found. The top keywords are described in the KE description section above.

A subset of the data tracked by various embodiments herein will be tracked by the Data Warehouse DW . This data will be used to evaluate the performance of the Contextual Advertiser. The events and dimensions listed below have been defined in the KE description above. The following events may be tracked in the DW.

Tracking pixels for both Commission Junction CJ and Mediaplex should be added to all ads. Commission Junction CJ and Mediaplex are well known advertising related services. These pixels will trigger CJ and Mediaplex to record an impression each time an ad is rendered.

In order to obtain more comparable impression counts between Mediaplex CJ and Host it is recommended to include cache busting. In the description below replace all occurrences of CACHEBUSTER in the ad tags below with a value using one of the following two Cache Buster types.

The Cache Buster value must be identical on all ad tag components for each ad placement. Proper cache busting ensures the correct clickthrough URLs are delivered and ensures correct banner weighting rotation.

This section describes how the dataset returned from the KE service will be used to generate ad content for the EK.

All data from the Keyword Extractor will be character encoded in UTF 8 in an example embodiment. The Editor Kit must do the necessary conversion to match the EK content with the character encoding of the Affiliate s URL.

The keywords used by the EK should be scrubbed of the blacklisted keywords from the sources listed below.

The most current keywords on the SIBE blacklist should be excluded from the keywords used for the EK.

Affiliates may specify a keyword exclusion list when creating their EK. This functionality exists today with the current EK. These keywords should also not appear in the keyword section of the newly designed ads.

This section details the criteria used to determine which search listings should be displayed in the EK ads.

The generated search listings should use the current Editor Kit functionality. Below are the current defaults used by the EK mirrors search front end default .

Only listings with time left greater than some time limit e.g. two hours should be included. Make this parameter configurable to a shorter time without the need for a train roll. The keywords and categories from the KE service will be used to populate the EK with relevant search listings. Use the slot selection process below to select which keywords generate each listing.

When the keyword set is retrieved from the URL to keyword cache the keywords must be assigned to the slots within the ad. The process to perform this assignment does so with a probabilistic selection process. Each keyword category combination has a value assigned to it. This value indicates the probability that this keyword can be selected for a given ad slot. For each ad slot starting with the first slot a game must be played to determine which keyword category from the entire set will win the ad slot. Once a keyword category combination wins a slot it is removed from consideration for the current instance of the ad and the game is played for the next slot and the remaining keyword category combinations left in the set. To play the game normalize the entire set of keyword category values and assign each on a range from zero to one proportional to their value. keyword category values that are relatively higher than other values in the set will be assigned a larger range. Then randomly generate a number from zero to one the random number generator should have an even distribution. The random number will fall into the range of one of the keyword category combinations and indicates that it has won the game for the specific ad slot. The winning keyword category combination should be removed from gameplay and then the range assignments should be re calculated for the next ad slot based on the remaining keyword category combinations. The game should be played until all the ad slots are filled or all the keyword category combinations are used. Note that each time an ad is played the game should be played which may result in a different keyword to slot assignment each time.

This section describes the formats colors sizes and components of the EK ads in an example embodiment.

Graphic and text ads are available with a fixed color scheme as pictured in in an example embodiment.

Graphic and text ads are also available as customizable ads. These ad designs do not include the horizontal stripe at the bottom. Examples of customizable ads are pictured in in an example embodiment.

Text only ads will not include any graphics including listing images logos or the horizontal stripe. The default color scheme for the text only ads may be as follows 

Conventional Flash 8 can be used to build the Flash ads. This version of Flash should allow .gifs to appear in the Flash ad.

There may only be one type of Flash ad created for a particular embodiment. It may be available in five different sizes. No other color options are available for this Flash ad. Flash ads will always use the Top Keywords as the fall back for null search results. Most watched items will not be an available fall back option for null search results. Below is a table of the behavior for the different sizes.

It should be determined if the user who is viewing the Flash ad has Macromedia Flash 8 installed on their machine. If a user does not have Flash 8 installed they will not be able to see the ad correctly. A contextual graphic and text ad should be displayed as the back up for the Flash ad. One embodiment may do a silent downgrade detailed below to a text and image ad when Flash isn t installed on the user s machine.

The size selection has expanded to accommodate the new sizes defined by the Interactive Advertising Bureau IAB .

The sizes available for each ad format are listed below. Each size has a fixed layout that is not configurable by the Affiliate.

Affiliates can customize the size of a graphic text or text only ad. Flash ads are only available at the fixed sizes. The custom size ad uses the existing functionality that the EK create page currently allows. The following parameters are configurable in an example embodiment.

Single listings are stacked vertically in the ad layout. The ad will flex to the specified width. Keywords and categories can t be added to the custom size layout.

Fixed and customizable color themes are available for graphic text and text only ads. There may be no color choices for the Flash ads.

The fixed color schemes available for each ad format are listed below. Fixed color schemes are not configurable by the Affiliate.

Below are examples of the fixed color schemes that may be available in the color scheme drop down. The Host Brand themes with the single color are also available with a white background. illustrates fixed color theme examples in an example embodiment.

Affiliates can customize the colors of a graphic text or text only ad. The configurable color options in an example embodiment include the following.

Each component within an ad is highlighted in the figure pictured in in an example embodiment. illustrates an Ad Components Legend in an example embodiment. All links should open up the landing page in a new window.

The product image for a listing should be resized according to the ad size specifications. No product images should appear in the text only ads. Product images should link to the View Item Page VIP for that featured listing.

The listing title should display at a maximum of 3 lines. Any titles that are longer than 3 lines will be truncated with an ellipses . . . at the end. Shorter listing titles can appear as just 1 or 2 lines. The title text should link to the View Item Page VIP for that featured listing.

For Buy It Now items the price should be shown as Price x.xx . For Auction listings the price should be shown as Current Bid x.xx .

Check ad specifications to see if Time Left is included. Not all ad sizes will include this component. Time Left should display according to the following specifications.

Searches made in the search box will use the same default parameters used for searches from the Host homepage. Parameters include the following.

The system includes Affiliate tracking for the EK search box. A search is initiated when the user clicks the Go button. A search can also be initiated by hitting the key. The search box may be pre populated with Search Host . When the user clicks on the search box this text should disappear and a blank box with a text cursor should remain.

Those ads that include a categories section should display categories in the following order of priority.

If no categories are returned by the KE service or specified by the Affiliate no categories should be shown. The keywords section will instead be extended into the categories section.

An example of a Create Your Own Ad page is illustrated in for an example embodiment. The user interface UI mock ups in this document are for a visual example only.

The Host Header as noted in the figures will remain as it does on the current page. Included elements Host logo site navigation search user greeting breadcrumb trail Sun logo.

As shown in Content selection determines if the new Editor Kit will use the Keyword Extractor backend Automated or the manually selected keywords Manual .

Automated is the default selection in the Content Selection drop down. The Website Address field is a required field. The Keyword Extractor will fetch keywords from this URL for the real time preview.

An Affiliate may choose to manually enter in keyword filters. The EK does not use the KE service under the Manual option.

The Editor Kits that use the current manual keyword method should still function correctly after the Contextual Advertiser launches.

For example a user types in harry potter eragon. The user then selects Books Children s Books and DVDs as two category filters. The backend processing will play the game with the following ranked keyword category combinations.

If Manual is selected Website Address is replaced with Keywords as a required text field. A checkbox for searching Title Description is added next to the Keywords text field. An example of choosing manual content is shown in for an example embodiment.

As shown in affiliates may choose categories to filter their ad content. These selected categories serve two functions.

A pop up layer may be used for Affiliates to select categories. This HTML pop up layer is similar to an AJAX pop up layer used to choose categories. Affiliates should not be required to choose the deepest subcategory possible. illustrate category selection in an example embodiment.

When the user clicks on the Remove link next to an item under Categories you have selected the behaviors below apply.

All selected categories may appear on the main page after the AJAX window has been saved and closed. These selected categories should include the breadcrumb paths. See the selected category display mock up illustrated in for an example embodiment.

A pop up layer is used for Affiliates to select advanced options. See the Tools in the Create Your Own Ad page section.

A filter can be added to allow for only charity listings to be displayed. This filter will be triggered when a checkbox is selected. The charity checkbox should not be selected by default. A charity ID can be specified to narrow the displayed listings to a specific charity. There is currently an API that allows for charity specific listings to be returned when a charity ID is supplied. http developer.ebay.com DevZone SOAP docs Reference Host io GetCharities.html . The charity ID filter will not be configurable in the Create Your Own Ad page. The default will be to include all charities.

The in the upper right hand corner or the Advanced Options pop up should link to the Contextual Ad Hub page.

All selected advanced options should appear on the main page after the AJAX window has been saved and closed. See the mock up illustrated in for an example embodiment.

The preview button triggers the generation of ads in the preview area. As stated earlier if Manual is selected the current EK functionality is used. The KE service is not called. The Refresh button must be clicked in order to update the preview ads with any user changes.

The reset button will clear all fields populated by the Affiliates. This includes any options selected in the Advanced Options and Category Selector pop up windows. All fields should revert back to their default state. The reset button should trigger a warning message pop up. An Affiliate must click on OK before the reset is completed.

The reloaded pages with error messaging should retain any selections and inputs the Affiliate has already made. See the mock up illustrated in for an example embodiment.

An animated loading graphic will appear when the backend call is initiated. The graphic will continuously run until one of the following occurs.

The preview area is where the ads are displayed with real time content. Affiliates can select color and size in this area. They can copy the code directly from this section into their source code. See the mock up illustrated in for an example embodiment.

A drop down of available color themes will display at the top of the Preview section. The color scheme drop down will not appear for Flash ads. The default selection will be the Host Stripe. Custom Color Font will be the last option in the drop down. This selection will extend the section to display color and font options. The ads displayed will change to the color scheme selected by the Affiliate in real time.

When a user chooses Custom Color Font under the Color Scheme drop down the default Custom template ads appear in the preview area. These default templates will have a dark gray border and white background as depicted in the ad specifications.

The color picker appears when a user is selecting a color in the custom color or custom ad sections. When choosing a specific color a user can perform the following actions.

When the custom color theme is chosen a Font drop down should also appear. The font options should appear in a drop down.

A drop down of all available sizes will display. The default size in the drop down will be All . The last listed size in the drop down will be Custom Ad . When a specific size is selected the page will scroll down to that specific size. Custom Ad will not appear in the size drop down for Flash ads.

When selected the preview section will expand to include custom color font logo size and these following options.

The table below outlines which show columns are available by size. The first column indicates the minimum width needed to fit the X d show columns on the right. For example if a user chooses the width of their ad to 340 or above but below 455 they are limited to 45 characters in their title a gallery image title and current price only. The checkboxes for the show columns are used to remove any show columns that the user does not want to appear in the ad. The remaining ad content will expand no empty columns should appear.

When Custom Ad is selected only an ad template will appear in the preview section. This template should reflect the real time changes that are being made in the custom fields above. This preview template is identical to the existing functionality of the current EK ad. None of the new ad formats can be used when the custom ad is chosen. The updated Javascript code should be displayed next to the ad template.

The custom ad title is user text that can be added to a custom ad. This is existing functionality that the EK currently offers. The title text is added below the Host logo in the ad see screenshot below . The default text color is black 000000 . 90 characters maximum are allowed. The title text may wrap depending on the size of the ad. Further customization is allowed. An example of custom ad title is shown in for an example embodiment.

For the custom size fields user inputs that fall outside of the valid range will receive the following errors.

The corresponding Javascript for each ad should appear next to the ad preview. The Copy Code button will serve as a hot key to automatically highlight the code and trigger the copy function ctrl c . The URL included in the JS should have the tracking information embedded. An example of the Create Your Own Ad page is shown in in an example embodiment.

The AJAX and dialogs sections should be referred to for the Category Selection and Advanced Options sections in this document.

Asynchronous JavaScript and XML or AJAX can be used to enable features to update the page without refreshing the entire page. Features can leverage AJAX and retrieve new data from the server asynchronously without stalling the Affiliate s interaction with the page. The result is a more responsive interface since the amount of data interchanged between the web browser and web server is vastly reduced.

Example application When the seller selects a meta category on the Browse Category page the system will post the seller s selection to the sever and fetch the list of L2 categories for that the selected meta without reloading the page. The information exchanged between the client and the server will be kept to the minimal to minimize load time.

The following is a general description of the Advanced Options and Category dialogs. Additional components will be specific for each individual dialog.

If a user has disabled Javascript the EK Create page should still be accessible. The real time preview ads and the AJAX layers will not be appear. All non JS features should still appear.

When a user lands on the Create Your CA page a sniffer should detect if the user has turned off JS on their machine. If the user does not have JS enabled a warning window should pop up directing the user to enable JS in their browser options.

There is an API call that will allow affiliates to access the Keyword Extractor service dataset. The keywords that the API returns should be scrubbed against the Host Blacklist. A configurable parameter should be added to limit the number of keywords returned. The default will be set at no limit. This limit should be configurable internally without a train roll. It should not be configurable by external developers using the API. The API will interface with the Keyword Extractor service. The real time preview should not be accessible via the API.

Various embodiments of the Contextual Advertiser Front end have revamped the Editor Kit by redesigning the ads simplifying the ad setup flow and integrating the Keyword Extractor backend. Various embodiments will further enhance the ad as follows.

Host AdContext may only display content from the site ID of the Host site in which the ad was created. The ad may not take into account the site ID of the user who is viewing the ad. For example if a German user views an American website the Host AdContext should display a DE intems and links.

The location of a user viewing a Host AdContext advertisement generator eAC created advertisement should be identified and used to generate more targeted content.

Geo targeting should be added to the Advanced Options section of the Create flow. Multiple site IDs can be supported for geo targeting. The default site ID will be set to the site ID of the create flow e.g. US create flow will have a default of 0 . The default should be configurable by the Affiliate. Geo targeting must be explicitly enabled by the Affiliate. Tracking geo targeted impressions clicks conversion metrics etc. should also be captured by site ID and by tracking provider.

The KE should use the viewer s location to determine which site ID to use for generating keyword category recommendations. For example if a viewer is identified as being in France the Keyword Extractor will use Host.fr s supply demand and conversion data to determine the most relevant keywords. The first time a viewer from a new site ID visits the Affiliate page top keywords from the new site ID are returned. The Affiliate page for the new site ID is added to the queue to be scanned for keywords. This is how the KE currently functions when a user visits an Affiliate URL for the first time. Geo targeting is only turned on for site IDs that have been set up by the Affiliate in the Create flow.

Affiliates can create ads featuring products with the Product Kit non contextual . This feature will add product data to the Host AdContext.

There should be different levels of how product data is displayed in the ads. The Affiliate should have the flexibility to choose which format they prefer such as the following.

2. Optimized automatically the ad will display product data item listings or a combination of both depending on how popular the product is.

Product content can be driven by contextual recommendations from the KE and also Affiliate search terms provided at set up.

A new product specific histogram can be added to the current KE functionality. A site product Reference ID histogram will associate with each keyword the frequency with which users clickthrough to an item which is associated with specific product on a per category basis. illustrates a graph showing association of product reference ID to query term in an example embodiment. For each listing that a user views after a search the product reference ID of the listing if available is associated with query term and the count of view item actions for that particular query term product ID combination is incremented by 1. If a user views multiple listings after a search i.e. repeatedly clicking back in their browser and clicking on different listings in the search results then all of those actions are counted if a product reference ID is available. If no product reference ID is associated with the listing then no event is registered and not stored in the histogram. Product reference ID counts at child categories should be aggregated up the category tree to parent categories. Note that the category ID may not be required pending further investigation by ERL. Only the top n products n 5 configurable parameter within each category need to be stored. The rest of the data accumulated by the query index does not need to be held in the Keyword Store since for Keyword Extractor purposes we will only be interested in suggesting the top few products associated with a keyword.

The Host AdContext may only allow an Affiliate to choose either Keyword Extractor recommendations or a static list of keywords provided by the Affiliate. This feature will allow a hybrid of both sources to drive ad content.

An Affiliate can use the automated Keyword Extractor to drive content in addition to providing keywords. These keywords can be used in the following ways.

If two or more eAC units are on the same webpage all could potentially show the same ad content. The system can detect if multiple eAC units are displaying on one page. The system can ensure that the items displayed across multiple ads are not duplicated. The system can allow the user to differentiate between different placements either on the same page or on different pages in their reporting.

There are two methods of adding Express links to eAC. The Express Front end feature only affects the items and URLs that are displayed in eAC. Magellan Integration adds Magellan data to the KE.

Currently Affiliate tools do not personalize ad content. RTM provides valuable data on user preferences and previous purchases. This information can further target Host ads to offer compelling recommendations to the user.

Various embodiments described herein add personalization to ads in order to increase click through and also personalizing Host landing pages to increase conversion. Host users visiting non Host sites can be identified e.g. cookie sniffing and matched with their Host user profile.

Host AdContext uses keyword and category recommendations from the Keyword Extractor KE to decide what ad content to display. These recommendations are contextual to the page that the ad is placed. When a user visits an Affiliate page with a Host AdContext ad we will check if there is a Host cookie on the user s machine.

Options on how to utilize user data to refine the ad content are described in the following sections.

KE recommendations can be enhanced using data to incorporate user data as an additional weighting factor when choosing ad content. This data can include the following 

The list of KE keyword and category combinations should be expanded for those combinations that are related to a user s history. Keywords can be expanded by related searches logic. Categories can be expanded by related categories logic.

Cluster profiles can be built for users with matching attributes segments. The purchase and interest activity of these users can be tracked. These cluster interests can be used to recommend products and categories for other users that match the same attributes as the cluster.

When a user clicks through an Internet Marketing link we do not personalize the Host page that they first land on. An embodiment can build a customized search results landing page with the following features.

Based on the various embodiments described above systems and methods are taught herein for supporting a variety of functions related to keyword extraction and contextual advertisement generation. Among these supported features are the following features.

Detection of an end user interaction with a Web page generating keywords based on the end user interaction with the Web page and performing a search using the keywords is described. For example a program running on a client computer may monitor the end user s browsing activities on the Internet. When the end user clicks on a link information associated with the link such as the link s label may be parsed and the Post Search Activity analysis used to generate one or more keywords. The keywords may be used to perform a search to generate search results which would be the feedback responsive to the keywords. The post search activity analysis maybe combined with inventory listing available on the site.

Detection of an end user interaction with a Web page generating keywords based on the end user interaction with the Web page and performing a search using the keywords is described. In one embodiment a program monitors a user s web browsing activity. The client program may be configured to trigger delivery of search results to the client computer when the user goes to a website in a category of websites. The search results may be responsive to one or more keywords derived from addressing information such as the uniform resource locator URL of a website visited by the user.

Detection of an end user interaction with a Web page generating keywords based on the end user interaction with the Web page and performing a search using the keywords is described. A keyword extracting device which extracts keywords by a monitoring the content change using frequency of spidering activity b using a pattern processing means and c creating a fingerprint of content to monitor frequency of change is described.

Detection of an end user interaction with a Web page generating keywords based on the end user interaction with the Web page and performing a search using the keywords is described. This is a system wherein said keyword extractor comprises plural and selectable extraction algorithms customized for different situations content. The keyword extractor can monitor events e.g. disaster vs. positive event and selectively determine when to contextualize.

Detection of an end user interaction with a Web page generating keywords based on the end user interaction with the Web page and performing a search using the keywords is described. The search results may be responsive to one or more keywords derived from addressing information as opposed to full text such as the uniform resource locator URL of a website visited by the user. In general there is no direct end user interaction with a web page URL. The API s described herein allows a 3rd party programmer to utilize the KE service directly and receive the unformatted data to use as s he sees fit. A URL is provided to the URL but there may or may not be an end user visiting that URL at that point in time the API is invoked.

Detection of an end user interaction with a Web page generating keywords based on the end user interaction with the Web page and performing a search using the keywords is described. The system wherein said keyword extractor leverages on an on site feature called related searches. The related searches may be search results presented by a program including content that relates to a keyword employed by the user in the request for information. Because the keyword represents the user s interest in a topic the chance of the user being interested in the related search content is increased.

A technique is described for delivering contextual information to end users using a keyword analyzing platform. Contextual information to be delivered to the end user is selected using the keyword information. According to a specific implementation the contextual information corresponds to ad information which is provided by a campaign provider. The contextual advertiser uses keyword recommendations and categories from keyword extractor to customize the ad unit to have new ads that are flash text and rich media advertisements. By using scores to statistically pick advertisement slots for keywords this invention gives them exposure builds traffic and uses them optimally.

A system and method for processing a request using a contextual product toolbar is described. The method comprises the steps of a sensing context on page and return keyword to be inserted into toolbar search box b indicating insertion to user such that a pre populated search box is arrived at c including call to action with highlighting e.g. . . . mouse over smart tag to highlight contextual keywords on page and d retrieving items and populating toolbar. This functionality would either utilize an API call or directly call the KE service.

A system and method for ad placements in different media and forums like blogs Emails RSS and Wikis is described where the contextual information corresponds to ad information provided by a campaign provider.

A system and method for generating cross asset site suggestions which can include a product review or a product guide for a keyword or a score for a keyword is described. An important feature of this invention is the ad which suggests items that are monetized best based on the feedback which is contextually sensitive and is not limited to listings.

A system comprising a plurality of Web pages a set of automatically generated suggested tags each of which is associated with an indication of either the content of a Web page or its relevance to certain search engine queries or both suggested tags associated with each of the plurality of Web pages wherein the tag has been associated with the Web page according to the preference of a user is described.

Detection of an end user interaction with a Web page generating keywords based on the end user interaction with the Web page and performing a search using the keywords is described. The systems and methods include a mechanism for providing interest and demographic data that may be applied to filter the Web page at the provider side resulting in personalization of keyword suggestions. The extracted keyword values are applied to filter content for delivery to a requesting Web client.

Referring now to a diagram illustrates a network environment in which various example embodiments may operate. In this conventional network architecture a server computer system is coupled to a wide area network . Wide area network includes the Internet or other proprietary networks which are well known to those of ordinary skill in the art. Wide area network may include conventional network backbones long haul telephone lines Internet service providers various levels of network routers and other conventional means for routing data between computers. Using conventional network protocols server may communicate through wide area network to a plurality of client computer systems connected through wide area network in various ways. For example client is connected directly to wide area network through direct or dial up telephone or other network transmission line. Alternatively clients may be connected through wide area network using a modem pool . A conventional modem pool allows a plurality of client systems to connect with a smaller set of modems in modem pool for connection through wide area network . In another alternative network topology wide area network is connected to a gateway computer . Gateway computer is used to route data to clients through a local area network LAN . In this manner clients can communicate with each other through local area network or with server through gateway and wide area network .

Using one of a variety of network connection means server computer can communicate with client computers using conventional means. In a particular implementation of this network configuration a server computer may operate as a web server if the Internet s World Wide Web WWW is used for wide area network . Using the HTTP protocol and the HTML coding language across wide area network web server may communicate across the World Wide Web with clients . In this configuration clients use a client application program known as a web browser such as the Internet Explorer published by Microsoft Corporation of Redmond Wash. the user interface of America On Line or the web browser or HTML renderer of any other supplier. Using such conventional browsers and the World Wide Web clients may access image graphical and textual data provided by web server or they may run Web application software. Conventional means exist by which clients may supply information to web server through the World Wide Web and the web server may return processed data to clients .

Having briefly described one embodiment of the network environment in which an example embodiment may operate show an example of a computer system illustrating an exemplary client or server computer system in which the features of an example embodiment may be implemented. Computer system is comprised of a bus or other communications means and for communicating information and a processing means such as processor coupled with bus for processing information. Computer system further comprises a random access memory RAM or other dynamic storage device commonly referred to as main memory coupled to bus for storing information and instructions to be executed by processor . Main memory also may be used for storing temporary variables or other intermediate information during execution of instructions by processor . Computer system also comprises a read only memory ROM and or other static storage device coupled to bus for storing static information and instructions for processor .

An optional data storage device such as a magnetic disk or optical disk and its corresponding drive may also be coupled to computer system for storing information and instructions. Computer system can also be coupled via bus to a display device such as a cathode ray tube CRT or a liquid crystal display LCD for displaying information to a computer user. For example image textual video or graphical depictions of information may be presented to the user on display device . Typically an alphanumeric input device including alphanumeric and other keys is coupled to bus for communicating information and or command selections to processor . Another type of user input device is cursor control device such as a conventional mouse trackball or other type of cursor direction keys for communicating direction information and command selection to processor and for controlling cursor movement on display .

Alternatively the client can be implemented as a network computer or thin client device. Client may also be a laptop or palm top computing device such as the Palm Pilot . Client could also be implemented in a robust cellular telephone where such devices are currently being used with Internet micro browsers. Such a network computer or thin client device does not necessarily include all of the devices and features of the above described exemplary computer system however the functionality of an example embodiment or a subset thereof may nevertheless be implemented with such devices.

A communication device is also coupled to bus for accessing remote computers or servers such as web server or other servers via the Internet for example. The communication device may include a modem a network interface card or other well known interface devices such as those used for interfacing with Ethernet Token ring or other types of networks. In any event in this manner the computer system may be coupled to a number of servers via a conventional network infrastructure such as the infrastructure illustrated in and described above.

The system of an example embodiment includes software information processing hardware and various processing steps which will be described below. The features and process steps of example embodiments may be embodied in articles of manufacture as machine or computer executable instructions. The instructions can be used to cause a general purpose or special purpose processor which is programmed with the instructions to perform the steps of an example embodiment. Alternatively the features or steps may be performed by specific hardware components that contain hard wired logic for performing the steps or by any combination of programmed computer components and custom hardware components. While embodiments are described with reference to the Internet the method and apparatus described herein is equally applicable to other network infrastructures or other data communications systems.

Various embodiments are described herein. In particular the use of embodiments with various types and formats of user interface presentations and or application programming interfaces may be described. It will be apparent to those of ordinary skill in the art that alternative embodiments of the implementations described herein can be employed and still fall within the scope of the claimed invention. In the detail herein various embodiments are described as implemented in computer implemented processing logic denoted sometimes herein as the Software . As described above however the claimed invention is not limited to a purely software implementation.

Thus a computer implemented system and method for keyword extraction and contextual advertisement generation are disclosed. While the present invention has been described in terms of several example embodiments those of ordinary skill in the art will recognize that the present invention is not limited to the embodiments described but can be practiced with modification and alteration within the spirit and scope of the appended claims. The description herein is thus to be regarded as illustrative instead of limiting.

