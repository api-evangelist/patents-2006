---

title: System for portion of a day out of office notification
abstract: A system for generating an electronic notice programmed to display a portion of a day out of the office notice. The system including an application server node configured to execute a personal information management application. An application programming interface is programmatically associated with the personal information management application for allowing requests for services to be transmitted to the personal information management application. At least one of a rich client delegate and a remote EJB housing the API, the rich client delegate and the remote EJB being programmatically associated with the application server node and the personal information management application. The rich client delegate being configured to receive and transmit data to the API via a network. At least one client node is operably associated with the application server node via the network. Each client node having a user interface (UI) that is programmatically associated with the personal information management application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08095941&OS=08095941&RS=08095941
owner: International Business Machines Corporation
number: 08095941
owner_city: Armonk
owner_country: US
publication_date: 20060907
---
IBM is a registered trademark of International Business Machines Corporation Armonk N.Y. U.S.A. Other names used herein may be registered trademarks trademarks or product names of International Business Machines Corporation or other companies.

This invention relates in general to personal information management applications and more particularly to a system that generates an electronic notice that displays a portion of a day out of office notice.

Out of office features in existing applications such as Lotus Notes IBM Workplace and Microsoft Outlook all implement a way to take a number of days off from one day to many days. Yet none of these applications contain the feature of letting a person take a half day or in more general terms x days and x hours off.

When creating an out of office notification in Lotus Notes and the user wishes to take a half day off the user enters the start date and the return date. Then the user manipulates around the existing implementation by setting the notification to out for a half a day in the subject line or the body of the notification in order to attempt to notify others of their partial absence day. The only way the user can get the notifications for out of office to fire off during a fraction of a day with current implementations is to physically turn off disable the application after half a day or turn it on enable the application part way through the day.

Thus there is a need to allow a user the ability to be able to generate an out of office notification that will distribute out of office notification to senders for only a limited number of hours a partial day .

The shortcomings of the prior art are overcome and additional advantages are provided through the provision of a system for generating an electronic notification containing a portion of a day out of office notice. The system includes an application server node operably associated with a database server having an application data supporting PIM system the application server node configured to execute a personal information management application the application server node further configured to store the personal information management application. An application programming interface API being programmatically associated with the personal information management application for allowing requests for services to be transmitted to the personal information management application. The system further includes a rich client delegate and a remote EJB housing the API the rich client delegate and the remote EJB are programmatically associated with the application server node and the personal information management application the rich client delegate being configured to transmit and receive data to the API via a network. At least one client node is operably associated with the application server node via the network each client node having a user interface UI that is programmatically associated with the personal information management application and the API such that the user may input date with timestamp to the minute data into the UI and transmit the data from the client node to the API. One rich client delegate per client application is programmatically supported by a business logic member. The business logic member being configured to receive the date with timestamp to the minute data entered by the user via the UI via the supporting business logic. The rich client delegate is further configured to transmit the data to the API of the remote EJB.

Additional features and advantages are realized through the techniques of the present invention. Other embodiments and aspects of the invention are described in detail herein and are considered a part of the claimed invention. For a better understanding of the invention with advantages and features refer to the description and to the drawings.

As a result of the summarized invention technically we have achieved a solution for a system for generating an electronic notification containing a portion of a da out of office notice.

The detailed description explains an exemplary embodiment of the invention together with advantages and features by way of example with reference to the drawings.

Referring to a system for generating an electronic notification containing a portion of a day out of office notice is shown. The system includes an application server node being operably associated with a database server having an application data supporting PIM system . The application server node is configured to execute a personal information management application . The application server node is further configured to store the personal information management application .

Referring to the application server node further includes a mail transfer agent MTA . The mail transfer agent is programmatically associated with the personal information management application and an application programming interface API . The mail transfer agent includes three phases i a receiving phase for the SMTP server ii a handling phase for handling name resolution group expansion and content analysis and iii a delivering phase for performing local and external mail delivery. The MTA includes an out of office filter member . The out of office filter member is programmatically configured to be a plug in to a delivery extension member and is operably associated with an out of office service .

The delivery phase includes the delivery extension member for allowing plug ins to add new functionalities. The delivery extension member is programmatically associated with the personal information management application and the API .

The API is programmatically associated with the personal information management application . The API allows request for services to be transmitted to the personal information management application .

At least one of a rich client delegate or a remote EJB housing the API is programmatically associated with the application server node and the personal information management application . The rich client delegate is configured to transmit data to the API . The rich client delegate and the remote EJB are configured to receive the transmitted data from a client node via a business logic member and forward the data to the API . The API is further configured to forward the transferred data to the MTA . At least one client node is operably associated with the application server node via the network .

Referring to where an exemplary user interface UI is shown. Each client node includes the user interface UI which is programmatically associated with the personal information management application and the API . The user may input date with timestamp to the minute data into the UI and transmit the data from the rich client delegate to the API of the remote EJB .

One rich client delegate is programmatically supported by the business logic member . The business logic member is configured to receive the data with timestamp to the minute data entered by the user via the UI by way of the supporting business logic member . The rich client delegate is further configured to transmit the date to the API of the remote EJB .

While the preferred embodiment to the invention has been described it will be understood that those skilled in the art both now and in the future may make various improvements and enhancements which fall within the scope of the claims which follow. These claims should be construed to maintain the proper protection for the invention first described.

