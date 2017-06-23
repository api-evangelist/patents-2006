---

title: Collaborative web page authoring
abstract: Collaborative web pages are enabled which allow every page on a website to be editable by an author and by others the author lets access the site. Web pages can send and receive email messages. Users can attach files to pages. Structure queries and page-building are enabled by use of various forms and form elements.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07584268&OS=07584268&RS=07584268
owner: Google Inc.
number: 07584268
owner_city: Mountain View
owner_country: US
publication_date: 20060131
---
This patent application claims priority from U.S. Provisional Patent Application Ser. No. 60 649 364 for Collaborative Web Page Authoring filed Feb. 1 2005 the disclosure of which is incorporated herein by reference.

The present invention relates generally to various techniques for improving authoring of collaborative applications including collaborative web page authoring.

A wiki is a website designed for collaboration. Unlike a traditional website where pages can only be read in a wiki everyone can edit update and append pages with new information and without knowing HTML.

Wikis are useful for many types of collaboration from writing documents and managing projects to creating intranets or extranets.

The present invention provides various techniques for improving collaborative web page authoring and editing. These techniques can be implemented singly or in any combination.

The present invention makes every page editable directly by an author and the people the author lets access the site.

In one embodiment every page in a wiki has an email box or some other control for sending email. Users can send email to and from any page in the wiki. Users can attach any type of file to any page. All pages in the wiki are full text indexed and searchable.

In one embodiment the present invention is able to composite data from multiple web sources into a wiki.

In one embodiment the present invention provides an easy to use application platform that facilitates the creation of multi user web applications in a very short period of time.

One skilled in the art will recognize that these Figures are merely examples of the operation of the invention according to various embodiments and that other architectures and modes of operation can be used without departing from the essential characteristics of the invention.

In the context of the present invention the term wiki refers to a piece of server software that allows users to freely create and edit Web page content using any Web browser. Wiki also refers to a set of web pages that is generated and maintained using wiki software. As is known in the art the wiki protocol supports hyperlinks and has a simple text syntax for creating new pages and crosslinks between internal pages on the fly.

A wiki page is a web page that can be edited by potentially anybody who views it. This enables quick collaboration in work groups. Every page has a name usually a WikiWord and a path that determines where exactly it is located in the wiki.

A wiki page also has any number of arbitrary properties which apply structure to an otherwise unstructured wiki page. Properties are usually applied by and are made visible by wiki forms.

The present invention makes every page editable directly by an author and the people the author lets access the site.

Every page the user creates has a title. To link to that page a user need only write that page s title on any other page in the wiki. A link is automatically created without the need to type any HTML code.

The author gives a page a title. To link to that page a user writes that page s title on any other page in a wiki and a link will be automatically created no HTML required. Users can edit every page in a wiki using familiar tools for graphical editing.

In one embodiment every page in a wiki has an email box or some other control for sending email. Users can send email to and from any page in the wiki. To send email to a page a user types the page title and an authentication code assigned by an administrator and the email contents automatically get attached to the page indexed and archived. Users can send email out of the wiki as well.

Some files such as MS Word and MS Excel files are automatically indexed for search. In one embodiment all attachments have the same revision control as any other page in the wiki. In one embodiment binary attachment data is stored as another property of a page.

In one embodiment all pages in the wiki are full text indexed and searchable. In addition to or instead of editing pages users can add comments if they wish. In one embodiment the structured properties of each page can be searched in a structured way in addition to full text for example with XPath or SQL.

In one embodiment the present invention also provides revision control. A user can roll back to any previous version or compare two versions. is a screen shot depicting an example of a user interface for revision control within a user editable website according to one embodiment of the present invention. Revision history shows various revisions links to compare each revision with a previous revision and edit dates .

In one embodiment the present invention also provides permissions to allow a user to specify who can read and write certain pages. is a screen shot depicting an example of a user interface for viewing permissions within a user editable website according to one embodiment of the present invention. In the example list shows individuals who have permission to read the page list shows individuals who have permission to edit the page.

In one embodiment the present invention allows a user to add structure to wiki pages using forms. Using forms the user can define fields to collect structured data like dates or numbers or create pull down menus to consolidate choices.

Forms need not be specified in advance. A user can start with a free text wiki and then add structure later. Fields and forms can be added modified or deleted at any time.

Individual elements can appear in both the table and calendar so that the viewer can clearly see the relationship between the two portions of the display.

In one embodiment the present invention is able to composite data from multiple web sources into a wiki.

For example is a screen shot depicting an example of search results composited into web page within a user editable website according to one embodiment of the present invention. Google search results can be embedded right into a page. Page dynamically looks up information on data items every time it is opened.

In one embodiment the present invention provides an easy to use application platform that facilitates the creation of multi user web applications in a very short period of time.

The present invention can be used to build highly customized collaborative applications. Such applications can easily be edited and modified. Applications can evolve over time and grow to perfectly fit a specific need.

The present invention uses a page as a fundamental unit of a wiki. Everything is stored as a wiki page. Themes look and feel of the site Forms toolbars user records error pages everything is stored using a single consistent model. Every page can be edited by anyone with permission. This means that practically everything can be customized and modified easily. The advantage of having a simple consistent model for everything in the wiki is that a developer or user need only learn a few verbs view create edit delete. Once he or she knows how to use those verbs he or she can apply them to all of the artifacts of the system.

Pages have properties. A property is a value attached to a particular page. Each property has a name and a value. Furthermore the value of a property has a specific type. For example almost every page in the wiki has a property whose name is main text and whose value is the text of the page. The type of main text is usually wiki which means that it is formatted wiki text.

Using the techniques of the present invention a developer can create whatever properties are desired. For example in a contact management application a developer could create a contact lastName property a contact firstName property or the like. Property names look like path structures but that is mostly for convenience in grouping similar properties together.

A page can have any number of arbitrary properties. Each property has a name e.g. contact firstName a type e.g. text and an optional value e.g. John .

A property can be read set searched for and reported on. Forms define groups of properties that get applied to all pages that the form is applied to.

In one embodiment every page has a certain set of default properties with a defined meaning. For example 

A WikiForm is used to display and edit a subset of these properties. For example the default WikiForm simply shows the main text property this is what users normally view and edit.

Most of the sys variables are inherited a child will take on the value specified by their parent if the child doesn t explicitly specify a value itself.

In one embodiment property names consist of at least two parts. Each part is separated by a . Usually if the property is associated with a form the first part of the name is the name of the form. For example if there is a form named contact which contains a property called firstName the full name of the property will be contact firstName when the form is applied to another page.

In one embodiment a page has a default theme and a default form. is a screen shot depicting an example of a user interface for a theme a form a page and a toolbar for a user editable website according to one embodiment of the present invention.

Theme defines the look and feel of page the WikiHome title the Edit Page button and the like. Form determines which properties to show in this case only the main text property is displayed. The content inside page section is value of the main text property. Toolbar section this is another wiki page included by the theme.

In one embodiment forms allow users to enter structured data into the wiki and can easily be created with a few lines of script.

Forms are applied to a page. A particular form can be applied at different times to multiple pages and the same page can have multiple forms applied to it. A form is best thought of as a mask that chooses certain properties from the page it is applied to. In addition to choosing properties it also determines how to show them on the page. Thus a form is a way to structure the properties of a page.

There are several ways to search sort and filter data that has been entered into forms. Using the SearchTag and TableTag a user can easily search and display form data in a tabular format.

A theme is a set of pages in the wiki that define the look and feel of the page. A theme page can contain any combination of HTML or wiki script. The view theme page is used when viewing a page the edit theme page is used when editing a page and the preview theme page is used when previewing.

Because a theme consists of a set of pages a theme is typically defined by a prefix . For example the prefix System Templates single tab defines a theme such that the view page is located at System Templates single tab view the edit page is located at System Templates single tab edit etc. A user can create and apply his or her own themes to a page.

A theme is usually specified by a path prefix. Given this prefix the system looks for a particular template e.g. the view template by simply prepending the prefix. For example given the prefix Templates plain the system looks for the view template at Templates plain view.

In one embodiment the prefix does not represent a directory for example if the prefix were MyTemplates my then the view template would be found at MyTemplates myview. Therefore a trailing character is included if the prefix specifies a directory.

PageProperties can be used to change the template type for example if sys templateAlternateView is set to foo and the prefix is Templates plain then the view template will be Templates plain foo. This additional bit of complexity is useful for certain special cases for example style sheets that should not have chrome.

In one embodiment the present invention allows a developer to easily integrate data from external sites. The developer can include RSS feeds as well as use the functions pre built in a library to integrate data from other sites.

Every editable page in the wiki can be displayed in one of these modes create view edit or preview. The current mode can be obtained from the variable action mode .

View Mode Used to display a page for instance if a user clicks a normal link. A wiki link will per default show a page in view mode.

Edit Mode A page is displayed in Edit Mode if the user clicks the Edit Page button or if the link to a page contains the query parameter edit with value 1 e.g. http mywiki.jot.com TestPage edit 1 .

Create Mode Whenever the user hits the Create Page button and types in the name for a new page that new page will be displayed in Create Mode.

Preview Mode A page is displayed in Preview Mode whenever the user edits or creates a page and then hits the Preview button.

Files inside  Admin Users contain authentication information. For example the authentication information for user foo is stored in  Admin Users foo. In one embodiment these pages are expected to set a single PageProperty user password which contains the encrypted password.

In one embodiment the present invention provides a scripting language for the application wiki. The scripting language enables the writing of situated lightweight wiki application making use of XML markup and XPath expressions. Script tags live in the wiki namespace. In one embodiment the present invention uses a language neutral API called JotLib JotLib is embedded in different scripting languages such as server side Javascript XML template processing XPath and others. It is also exposed to web services protocols such as XML RPC SOAP and the pseudo protocol REST.

This example assumes that there is a WikiForm called contact which is used for a simple contact database application. The line above simply generates a table of all contacts. Each row will show a contact and each column will show a property of the form.

This assumes that the wanted state has been assigned already to a variable called wantedState this could come from a pull down menu for instance . A SearchTag is used in order to find all contacts residing in the wanted state. The results are ordered by last name.

Often the expression will simply be a variable reference e.g. req path or page editTime. However the contents of can actually be any valid XPath expression.

XPath variables can have structure for example the req variable has a path child and an args child the args child has its own children which represent the query string arguments.

XPath variables can also represent lists for example if page is bound to a node with attachments using the NodeInfoTag then page attachments will represent an array 

Usually an attribute will take an expression as its value. This expression can be anything pure text e.g. abc a variable reference e.g. req path or something more complicated e.g. count page attachments .

However sometimes an attribute specifies the name of a variable. In this case the attribute should only be the variable s name e.g. req path not an expression containing the variable e.g. req path . This is the case for the over attribute of the LoopTag for example.

Several custom functions are defined for XPath expressions in addition to the functions defined by XPath.

These variables will typically be used with syntax e.g. req path is usually referenced in a template as req path.

The current wiki page plus any query string arguments constitute the request and that data is stored in the variable req. Req has the following subvariables 

Examples assuming the following query string http www.wikipad.com webspace Bugs SomeBug foo FOO bar BAR

The nodeinfo tag binds a variable to a specific node so that the user can then access specific properties of that node. The user can bind any node to a variable not just the node that the user is currently visiting.

The result of the attachments property is another list of nodes. For each element in attachments the above properties are valid for example name is the name of the attached file.

Then to display the values of any of the sub variables associated the node specified the following syntax can be used 

There is a set of default attributes that are used by several tags e.g. NodeInfoTag IncludeTag ShowTag . These attributes provide different ways to access a node.

In one embodiment one of path href or node must be specified. The only difference between path and href is that href expects the link to have a wiki prefix. In other words the following two invocations are the same 

A package is a bundle of wiki pages described by a manifest. It can be downloaded distributed and installed in any wiki as a ZIP file.

Packages can be used for several purposes. Mostly they will be used to bundle up wiki applications. Packages can also be used to define themes skins for the wiki. Packages can be used to bundle up system pages that will get deployed to new wikis.

A package is composed of a number of pages that are described by a manifest. The manifest contains information about the paths and types of pages that are included in the package. It also contains information about the name of the package its author version etc. In one embodiment the manifest itself is another wiki page having the following properties 

The main text property of the package manifest describes which pages are part of the package in the form of a normal HTML table. The table has a structure as shown in this example 

The system package PackageUserInterface which is installed in the wiki supports the developer in creating new manifests and packages. System Packages is the home page of this package.

Date objects can be displayed as is e.g. date to display their value. The following date objects are also available 

The date type of wiki input can be used to create a new year month day date in other words no time of day or datetime can be used to create a full date time pair.

The default time zone used for showing and editing dates is stored in the variable sys env timeZone. The value can be changed to a string e.g. EST and all future dates will be shown using that time zone.

The user can also modify sys env formatTime sys env formatDate and sys env formatTimeDate to control the display of times and dates.

Forms are a great way to be able to create structured data in a Wiki. In this example a simple contact management database is created that allows a user to enter new contacts via a form with custom fields at the push of a button. This contact manager works best when the user enter new contacts as WikiWords.

The developer creates a page in a wiki that will be the home for the contact management app. For the purposes of this example that page is referred to as MyContacts . The developer hits the Create Page button and on the next screen he or she titles the page MyContacts .

On the MyContacts page the developer creates a createPage control that will allows him or her to easily add new contacts to the contact database. In one embodiment every new contact that the developer creates is essentially its own page in the Wiki.

The createPage control allows the developer to enter new contacts. On the MyContacts page the developer enters the code below 

The developer creates the ContactForm page by hitting the Create Page button entering ContactForm in the box and then entering the following code on the new page 

In the code above a form is started and titled contacts . The bars separating the text are wiki tables that allow the developer to display his or her form fields in organized rows and cells.

A user can now enter new contacts into the Contact Management database by going to the MyContacts page and entering a new contact.

After entering a new contact as a WikiWord the form asks the user to enter a first name and last name. The following change avoids the need for duplicative entry of this information. By changing

The developer makes use of a utility called util wikiwords to split a WikiWord into two pieces and then setting the default values of the firstName and lastName fields to be first and second pieces of the WikiWord respectively.

For example suppose it is desired to create a Daily Calls Log. The purpose of this log is to have a page where a user can hit a button and fill in a simple form with some basic information about a call that has been received. Each logged new call creates a page in the user s wiki and the title of the page will be automatically created which will be its unique ID. The user will be able to choose how pages are named and every new call he or she enters will have that name with a number added to the end of it. In this example new pages are named DailyCall. The user has the ability to set the page title. An incremented number will automatically be added to the end of each page title when a new call is added example DailyCall0 DailyCall1 DailyCall2 and so on . . . .

The developer uses the createPage control to create button that will allows a user to enter new calls. The developer changes his or her Default Edit Style setting by clicking on a Preferences link clicking Edit Page and then changing the Default Edit Style setting to Script Markup. The developer saves the page and goes back to the WikiHome page by clicking the WikiHome link at the top left hand corner of the page inside the tab. Now the developer hits the Create Page button and on the next screen titles the page DailyCallsLog .

This tells the table tag to look up all the pages created using the DailyCallsLogForm and display them in a table . So the actual search for the pages is implicit.

Now the developer creates the DailyCallsLogForm to specify what fields he or she wants to capture when entering a new call. Since it doesn t exist yet the developer creates it now by hitting the Create Page button entering DailyCallsLogForm as the title of the page and then entering the following code on the new page 

The code above starts a form and titles it CaIlLog . The bars separating the text are wiki tables that allow the developer to display form fields in organized rows and cells.

This is where the developer defines the naming scheme for each new page that is created. The unique name pattern DailyCall U is used where the U means add a uniquely incrementing number . So the result is DailyCall0 DailyCall1 DailyCall2 etc. To see what other types of patterns the developer can use see the PageNameField documentation page.

The user can now enter new calls into the Daily Calls Log by hitting the Enter New Call button as shown in which causes form to appear. As the user enters calls the calls will appear in the table on the DailyCallsLog page. Each call has a new number at the end of its name.

The developer can also add a calendar to go along with the log so that the user can automatically chart the calls that are received in a convenient monthly calendar view. The following line is added to the DailyCallsLog page 

The developer can create a calendar and feed into it all the pages that were created through the DailyCallsLogForm page. It will use the first date field type that it comes across in the form that is defined to determine where to place each call on the calendar.

The developer creates a page calls it CalendarForm. The developer sets the event date field shown below to type date and gives it a name of event date 

Now that the developer has created a CalendarForm he or she creates a new page called MyCalendar. This is the page to be used to display the calendar as well as the Create new event button. The developer enters this line in the Mycalendar page 

The next step is to do a search to collect all the pages that were created by using the form before feeding them into the calendar. Remember that we named the wiki form event in an earlier step 

Now the developer creates a new page called Mycalendar. This is the page that will be used to display the calendar as well as the Create new event button. The developer enters this line below in the MyCalendar page 

The developer can specify the date as well as the time of the event when he or she creates a new event.

The next step is to do a search to collect all the pages that were created by using the CalendarForm before feeding them into the calendar. The wiki form has been named event in an earlier step 

Using the wiki item tags in between the wiki calendar tags gives the developer fine grain control of what to display on calendar . The developer can use XPathExpressions to display specific fields of the event. In the example above the code displays various bits of information about the event including title location and time.

In order to enter events that span multiple dates or events that recur on a periodic basis e.g. Monthly team meeting the developer can use the event type field.

Searches and Tables go hand in hand. Searches are used to group or collect a set of wiki pages based on certain criteria. Tables display the data collected in the search.

forChildren is used to search for all the sub pages or children of a parent page. This is what s called a parent child relationship. For example 

In this example NHLHockey and NBABasketball are both parent pages with sub pages or children beneath them. Let s say we only want to search for the Hockey teams. We know that they are sub pages of the parent page called NHLHockey . This is how the search would look 

Those two lines do the following first search for all sub pages of NHLHockey and then throw the results in a table to display them. Notice that in this example we simply used with no other arguments.

Here s the way that search tags and table tags know how to work with each other In the search tag example above notice that we have not set any kind of variable to store the results of the search in. The search above is just the search tag with only forChildren specified. In the case where the developer does not specify set anyVariableName in the search tag the results of the search will be stored in an internal variable that is hidden to the user. Any table tags that are used after the search will seamlessly use that hidden variable. Alternatively the developer can also manually choose a variable name. Here s an example of explicitly setting a variable for the results of the search 

This means that the results of the search are now stored in a container called nhlResults . In the table tag that follows the developer specifies what container of search results the user wants to display like so 

forFormName is used to retrieve all the pages that were created by using a specific form. Three contacts have been entered using a form.

When the developer specifies the form page in the table tag it displays all of the form fields in the generated table. Suppose the developer only wants to show the name of the page and the phone number associated with it but would like to suppress the other fields. The search tag stays the same but the table tag is modified 

forName is used to specify a search pattern for matching the names of pages in a wiki. The symbol can be used as a wildcard. If no wildcards are specified the match implicitly adds wildcards to the beginning and end so that the pattern foo will match afoob .

The following example shows a technique for refining search results by using filters. A search filter is an instruction given to the search tag telling it to match the results against specific criteria. For example use the same contact list created above a regular search and table shows all the contacts currently in the database 

Now suppose we only want to display the contacts that live in California. A filter can be applied as follows 

The filter it contact state California was added to the search. The it stands for iterator namely an object or routine for accessing items from a list or array one at a time. The iterator loops over a number of items.

Another example is now shown in which the desired result is to retrieve all of the contacts that are NOT from Indiana.

Another example is now shown in which the desired result is to retrieve all of the contacts with the last name of Flint that live in California.

In one embodiment the invention can also function in connection with XPath functions that allow greater flexibility when creating filters. For example to filter for contacts that have an area code of an XPath function starts with can be used 

The developer also has the option of specifying the order in which the results will appear. To show contacts alphabetically by last name 

The default ordering style is in ascending order. The developer can also specify descending order by simply adding a after the order 

In one embodiment XML mode can be used to combine raw XHTML with a script to create a Search box that displays the results of the search in a collapsible window.

In one embodiment an IncludeTag can be used to allow easy inclusion of the contents of one wiki page into another wiki page.

Step 1 Create a MyCandidates page that has a createPage control for the CandidateForm. Switch the Default Edit Style setting to Script Markup by clicking on the Preferences link present on the bottom right hand corner of your page.

Step 2 Next step is to create a page that displays a table of all candidates. Create a page called CandidateSearchTable and enter the following code.

In the MyCandidates page enter the following code to include the CandidatesSearchTable into your MyCandidates page.

The result is shown in which is an example of a job candidate table within a user editable website according to one embodiment of the present invention.

In the code above the CandidateSearchTable has been specified in a separate wiki page and included on the MyCandidates page. Alternatively the code from the CandidateSearchTable page could be directly included into the MyCandidates page but by creating a separate page for the candidates table the developer can potentially include the table in any number of wiki pages giving plug n play style functionality.

Step 3 The developer can further modify the CandidateSearchTable to take in arguments and filter candidates based on their status. Edit your CandidateSearchTable page and replace the line

The code above specifies that candidates should be filtered on their status. The args variable has the list of arguments passed to the wiki page. The args variable is a PredefinedVariable. The expression args status specifies the value of the status variable that is passed as an argument to the CandidateSearchTable page.

will show all candidates who have been rejected. The developer can set the status variable to any of the different values to show candidates in the different stages of the interview process.

In one embodiment the present invention can facilitate the inclusion of maps and other data from multiple sources on the resultant wiki page. The following example illustrates the creation of a lead management application that tracks potential client companies and aggregates information about the client company from various websites.

Step 1 Switch Default Edit Style setting to Script Markup mode by clicking on the Preferences link at the bottom of the right hand corner. Create a wiki form called ClientForm and add the following fields to the client form.

Save the ClientForm and create a page called MyClients that has the createPage control to add new clients and a wiki table to display existing clients.

Step 2 The next step is to pass the address information to the MapDisplay app already created in the JotSpotLibrary to display the map. Edit the ClientForm and add the following code to the bottom of the page 

This piece of code includes the MapDisplay app available in the JotSpotLibrary using the IncludeTag and passes the address information in a variable called address to the app. The developer can reference variables in the wiki page using XPathExpressions.

Step 3 Search results for the client company on the client page can be included by adding the following two lines to the ClientForm.

The Yahoo and Hoovers applications are similar to the MapDisplay application and take a search term as the input argument. Save the ClientForm and return to your MyClients page. Enter some new clients from the MyClients page. Yahoo Hoovers and MapQuest data about each client company can then be viewed on the client s wiki page.

With the ReportTag the developer can write reports over a collection of wiki pages. The following example illustrates how to use the ReportTag in the simple recruiting application discussed above and generate reports on the number of candidates and recruiters.

Add additional fields to the CandidateForm created in the Include Tag Cookbook by including the following lines between the tags

The createPage control in the MyCandidates page created in the earlier example allows entry of new candidates. The following code creates a createPage control for the CandidateForm

After some sample data has been added the ReportTag can be used to generate reports. The SearchTag can be used to collect all the wiki pages of the CandidateForm. The ReportTag can then be used along with the group tag to group data. Typically the SearchTag is used to collect all the wiki page into a set before using a ReportTag to generate the report

So for example if 5 candidates were entered assigned 2 to one recruiter and 3 to another the above piece of code would result in 

To report the number of open and rejected candidates per recruiter another line of Script could be added in between the report tags.

The application can be taken one step further so as to report on the average rank per recruiter. The average rank could be one of the metrics by which a company could track the quality of candidates a specific recruiter qualifies. In order to do this we use an aggregate tag that allows aggregation of ranks of the different candidates and application of the average function.

The code above specifies that we want to display the number of candidates per recruiter as well as compute the average rank of all the candidates assigned to a specific recruiter. The ReportTag reference documentation has a comprehensive list of functions that you can use in the aggregate and group reporting tags.

In one embodiment the present invention facilitates modification of standardized applications. the following example illustrates modification of a project management application by adding custom fields adding options to a pull down menu and changing the information displayed.

The form fields are defined between the two form tags. The developer can add to the select options on the status pull down menu by changing the selectOptions string. For example to add the option Abandoned Change the line

To add a new field to the form simply add another line in between the tags and specify the form field name. For example the line below adds a field of type date and name start date to the ToDo form.

To add some code on the project management home page so that the new form field start date can be viewed from the home page the developer can edit the project management home page.

In one embodiment every object in the system is represented by a page. Each unit of user content is a page but pages are also used for 

In one embodiment every page has a unique address and every page can be edited by a user with the appropriate permissions. Because in one embodiment every object is represented by a page this means that every object in the system users themes code libraries etc. is URL addressable and editable from within the system. This provides uniformity of access and modification.

In one embodiment all information contained in the page is stored in one or more properties which are typed name value pairs. A property name is an alpha numeric sequence possibly with a path separator character. A property value is a data object with a specific type. Types include 

The binary data property is used to store arbitrary web resources such as JPEGs CSS stylesheets Word or Excel documents etc.

The XML data property is used to store structured data. The property can contain XHTML for showing web content RSS for weblog content or user defined XML as needed. An expression language is used to extract specific pieces of an XML data structure.

However any user can create new properties at any time. In one embodiment there is no distinction between system defined properties and user defined properties.

The system stores a full log of changes to each page. Every time a property is modified a new version of the page is saved to disk. Users can revert to previous versions of a page at any time.

A page is typically viewed through one or more transformations. Pages have a raw XML representation which is always accessible. But typically a transformation is applied before viewing or editing a page. Transformations come in several types 

In the current implementation most pages are passed through two transformations an evaluating form transformation that selects the main text property and an evaluating theme transformation that surrounds the content of the main text property with navigation chrome.

The data store manages the physical storage of pages and properties including their revisions. There are multiple implementations of the data store API 

The auth layer manages both authentication and authorization. Authentication is handled by matching a user against a particular page in the wiki. Authorization is handled by accessing specific properties e.g. sys readUsers for the ACL of users who are allowed to read the page .

The transformation layer access specific page properties evaluates them according to certain rules JotScript XSLT etc. and returns the result.

The network manager converts incoming protocols HTTP RESTful XML SBAP SMTP etc. into wiki pages and converts wiki pages back into outgoing protocols HTML HTTP RESTful XML RSS Atom SMTP etc. .

The system processes incoming email messages by testing the To address. In one embodiment the following address format is used 

The message is routed to the wiki named mywiki. That wiki has a user settable authentication code. If secretcode matches the mywiki s authentication code then the mail is accepted. The mail is assigned to a page in the wiki as follows if DestinationPage exists then the mail is created as a sub page of DestinationPage with the mail s subject line as the name of the sub page if DestinationPage does not exist then a new page called DestinationPage is created. In either case the content of the email becomes the main text property of the page. In addition mail related properties such as mail subject and mail from are set based on the email s header. Any attachments in the email message are stripped out and inserted into the wiki as separate pages.

One feature of the system is that mail messages become pages just like everything else so they can be modified deleted indexed searched etc.

An example Assume there is a wiki named foo.jot.com. The wiki has pages named Page1 and Page2. The wiki s authentication code is magic.

