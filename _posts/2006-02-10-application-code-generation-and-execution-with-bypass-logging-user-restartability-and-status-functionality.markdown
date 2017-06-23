---

title: Application code generation and execution with bypass, logging, user restartability and status functionality
abstract: A Value Analyzer system is a data-driven computer-facilitated financial model that provides accurate and consistent profitability calculations using account, product and event attributes stored in a relational database managed by a relational database management system (RDBMS). Profitability calculations are performed in the computer by applying one or more rules to the account, product and event attributes accessed from the database, wherein the profitability calculations include setup, generation and execution of structured query language (SQL) statements by the RDBMS. The present invention also monitors the profitability calculations by monitoring the setup, generation and execution of the SQL statements by the RDBMS, in order to provide bypass, logging, user restartability, or status (BLURS) functions for the profitability calculations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08374997&OS=08374997&RS=08374997
owner: Teradota US, Inc.
number: 08374997
owner_city: Dayton
owner_country: US
publication_date: 20060210
---
This application claims priority under 35 U.S.C. 119 e to co pending and commonly assigned Provisional Application Ser. No. 60 683 392 entitled APPLICATION CODE GENERATION AND EXECUTION WITH BYPASS LOGGING USER RESTARTABILITY AND STATUS FEATURES filed on May 20 2005 by Paul H. Phibbs Jr. and Thomas K. Ryan which application is incorporated by reference herein.

Utility application Ser. No. 11 251 667 filed on Oct. 17 2005 by Paul H. Phibbs Jr. and Thomas K. Ryan entitled PROCESSING FORMULAE IN RULES FOR PROFITABILITY CALCULATIONS FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM which applications claims priority under 35 U.S.C. 119 e to Provisional Application Ser. No. 60 714 648 filed on Sep. 7 2005 by Paul H. Phibbs Jr. and Thomas K. Ryan entitled PROCESSING FORMULAE IN RULES FOR PROFITABILITY CALCULATIONS FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 227 909 filed on Aug. 26 2002 by Brian J. Wasserman and Thomas K. Ryan entitled PLATFORM INDEPENDENT ARCHITECTURE FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 227 783 filed on Aug. 26 2002 by George R. Hood Brian J. Wasserman Thomas K. Ryan and Sang Y. Yum entitled SELECTION PROCESSING FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 227 726 filed on Aug. 26 2002 by Richard C. Schwarz Brian J. Wasserman Sang Y. Yum and Thomas K. Ryan entitled DRIVER AMOUNT COUNT SELECTION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 227 976 filed on Aug. 26 2002 by Brian J. Wasserman George R. Hood and Thomas K. Ryan entitled DISCRETE PROFITABILITY CALCULATIONS FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 228 022 filed on Aug. 26 2002 by Brian J. Wasserman George R. Hood and Thomas K. Ryan entitled RULES BASED DATA DRIVEN PROFITABILITY CALCULATIONS FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 228 031 filed on Aug. 26 2002 by Brian J. Wasserman entitled OBJECT ORIENTED REPRESENTATION OF A GENERIC PROFITABILITY RULE FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 016 779 filed on Dec. 10 2001 by Brian J. Wasserman entitled PARALLEL SELECTION PROCESSING FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 013 422 filed on Dec. 10 2001 by Brian J. Wasserman entitled ACCOUNT SELECTION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 013 434 filed on Dec. 10 2001 by Brian J. Wasserman entitled DRIVER AMOUNT AND COUNT SELECTION PROCESSING FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 10 016 452 filed on Dec. 10 2001 by Brian J. Wasserman George R. Hood and Thomas K. Ryan entitled DYNAMIC EVENT SELECTION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 943 060 filed on Aug. 30 2001 by Paul H. Phibbs Jr. entitled CAPITAL ALLOCATION IN A NET INTEREST REVENUE IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 943 059 filed on Aug. 30 2001 by Paul H. Phibbs Jr. entitled ALLOCATED BALANCES IN A NET INTEREST REVENUE IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 845 461 filed on Apr. 30 2001 by George R. Hood entitled TAX ADJUSTMENT FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 845 924 filed on Apr. 30 2001 by George R. Hood entitled AMORTIZATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 845 851 filed on Apr. 30 2001 by George R. Hood entitled SHAREHOLDER VALUE ADD FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 608 355 filed on Jun. 29 2000 by George R. Hood and Paul H. Phibbs Jr. entitled ADVANCED AND BREAKTHROUGH NET INTEREST REVENUE IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 610 646 filed on Jun. 29 2000 by George R. Hood and Paul H. Phibbs Jr. entitled BASIC AND INTERMEDIATE NET INTEREST REVENUE IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 608 681 filed on Jun. 29 2000 by George R. Hood entitled OTHER REVENUE IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 608 675 filed on Jun. 29 2000 by George R. Hood entitled DIRECT EXPENSE IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

Utility application Ser. No. 09 608 342 filed on Jun. 29 2000 by George R. Hood entitled INDIRECT EXPENSE IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM and

Utility application Ser. No. 09 608 682 filed on Jun. 29 2000 by George R. Hood entitled RISK PROVISION IMPLEMENTATION FOR FINANCIAL PROCESSING IN A RELATIONAL DATABASE MANAGEMENT SYSTEM 

This invention relates in general to financial processing systems performed by computers and in particular to application code generation and execution with bypass logging user restartability and status features using a relational database management system.

Financial processing systems provide tools for financial analysis of accounting data. Typically each financial processing system operates in a unique way and approaches financial analysis differently. Some financial processing systems are advanced in their approach to profitability calculations in that they are based on complex relational database management systems RDBMS s .

In such systems the financial processing includes the generation and execution of SQL statements by the RDBMS. However such systems due to their complexity may be prone to errors and difficult to monitor. For example previously users would start a job comprised of one or more SQL statements and have little control as to when and how the statements completed. When an error occurred the user would have a substantial effort to find the location and cause of the error. In addition the user would have to reset and restart the job from the beginning resulting in a substantial loss of time.

There is a need then for an improved approach for performing financial processing using a relational database management system especially in the area of application code generation and execution. The present invention satisfies that need.

A Value Analyzer system is a data driven computer facilitated financial model that provides accurate and consistent profitability calculations using account product and event attributes stored in a relational database managed by a relational database management system RDBMS .

The present invention performs one or more profitability calculations by applying one or more rules to account product and event attributes accessed from a relational database management system RDBMS wherein the profitability calculations include setup generation and execution of structured query language SQL statements by the RDBMS. The present invention also monitors the profitability calculations by monitoring the setup generation and execution of the SQL statements by the RDBMS in order to provide bypass logging user restartability or status BLURS functions for the profitability calculations.

In the following description of the preferred embodiment reference is made to the accompanying drawings which form a part hereof and in which is shown by way of illustration a specific embodiment in which the invention may be practiced. It is to be understood that other embodiments may be utilized and structural changes may be made without departing from the scope of the present invention.

A Value Analyzer system is a data driven computer facilitated financial model that provides accurate and consistent profitability calculations using account product and event attributes stored in a relational database managed by a relational database management system RDBMS .

In the preferred embodiment the RDBMS includes at least one Parsing Engine PE and one or more Access Module Processors AMPs A E storing the relational database in one or more data storage devices A E. The Parsing Engine and Access Module Processors may be implemented in separate machines or may be implemented as separate or related processes in a single machine. The RDBMS used in the preferred embodiment comprises the Teradata RDBMS sold by NCR Corporation the assignee of the present invention although other DBMS s could be used.

Generally the Value Analyzer Client includes a graphical user interface GUI for operators of the system wherein requests are transmitted to the Value Analyzer Calculation Engine and or the RDBMS and responses are received therefrom. In response to the requests the Value Analyzer Calculation Engine performs the functions described below including formulating queries for the RDBMS and processing data retrieved from the RDBMS . Moreover the results from the functions performed by the Value Analyzer Calculation Engine may be provided directly to the Value Analyzer Client or may be provided to the RDBMS for storing into the relational database. Once stored in the relational database the results from the functions performed by the Value Analyzer Calculation Engine may be independently retrieved from the RDBMS by the Value Analyzer Client .

Note that the Value Analyzer Client the Value Analyzer Calculation Engine and the RDBMS may be implemented in separate machines or may be implemented as separate or related processes in a single machine. Moreover in the preferred embodiment the system may use any number of different parallelism mechanisms to take advantage of the parallelism offered by the multiple tier architecture the client server structure of the Value Analyzer Client Value Analyzer Calculation Engine and RDBMS and the multiple Access Module Processors of the RDBMS . Further data within the relational database may be partitioned across multiple data storage devices to provide additional parallelism.

Generally the Value Analyzer Client Value Analyzer Calculation Engine RDBMS Parsing Engine and or Access Module Processors A E comprise logic and or data tangibly embodied in and or accessible from a device media carrier or signal such as RAM ROM one or more of the data storage devices A E and or a remote system or device communicating with the computer system via one or more data communications devices.

However those skilled in the art will recognize that the exemplary environment illustrated in is not intended to limit the present invention. Indeed those skilled in the art will recognize that other alternative environments may be used without departing from the scope of the present invention. In addition it should be understood that the present invention may also apply to components other than those disclosed herein.

The Value Analyzer system is a data driven computer facilitated financial model that provides accurate and consistent profitability calculations using account event and Product data stored in the RDBMS wherein 1 the account attributes comprise data about accounts being measured 2 the event attributes comprise data about account related transactions and 3 product attributes comprise data about products being purchased. The profitability calculations performed by the Value Analyzer system rely on a Five Factor Atomic Profit Metric FFAPM 

In the above equation it is assumed that the sign of elements that reduce profit are negative and those that contribute are positive.

Each of these five factors can be measured for a desired period daily weekly monthly quarterly etc. . Moreover each factor is essentially discrete and independent with fundamentally different characteristics which strengthens the user s ability to fully utilize the output to determine relationships between account event and Product data and enable consistent multiple dimensional aggregation.

The FFAPM is atomic in that profitability is computed using data stored in the RDBMS . There are three aspects to this 

The Value Analyzer generally defines indirect components of profitability to be those which must be apportioned to accounts and direct components to be those which are either computed at the account level or are rolled up to the account level from lower level events.

Account Attributes comprise data about the accounts being measured. This data includes balance rate or interest accrued product identification limits expected default frequency and various dates e.g. open rate reset last payment next payment maturity etc. .

Event Attributes comprise data about account related events or transactions. This data includes account identification event or transaction amounts event or transaction location event or transaction time counter party identification event or transaction type e.g. loan payment interest paid loan draw down amount etc. .

Product Attributes comprise data about products being purchased. This data includes product identification unit price amounts etc.

Profit Factors include parameter values necessary to perform the Profitability Calculations . The major classifications of this data include 

The Profitability Calculations use one or more Rules applied to data retrieved from the RDBMS . These Rules include inter alia the following 

Treatments. Every account with cash flows affecting a organization s balance sheet requires a method of valuing the account s use of internal funds. One approach is matched maturity funds transfer pricing which uses a canonical representation of an account s funding characteristics and then determines a value based on adjusted market yields for each instance that requires an interest rate transfer price to calculate an account s marginal Net Interest Revenue.

Equity Allocation. In order to provide precise Net Interest Revenue calculations the amount of equity funds required at an account must be determined. This rule allows for equity allocation using any of the following methods simple ratios regulatory definitions economic allocations or user defined allocations.

Apportionment. Other Revenue Risk Provision and Indirect Expense calculations are applied at the account level using Product Attributes that are not related directly to account activity. These profit adjustments are made so that the sum of all account level Profitability Calculations comprises the overall profit. One approach is to pool indirect costs and revenues and then apportion them. Apportionment rules specify how the pooled indirect costs and revenues is completely allocated to appropriate accounts wherein the preferred embodiment uses closed form allocation rules which require only information known in the current period and not iterative computation.

Amortization. Some types of income or expense are deferred or accrued over multiple periods including and subsequent to the current accounting period. This is common to accrual accounting methods used in profit presentations of financial statements and gives rise to timing differences between cash flows and their related profit as presented in a financial statement in any accounting period. Since the Value Analyzer system is designed to reconcile to the financial statement s profit values it supports deferral and accrual accounting principles. Amortization methods that account for these timing differences are interest amortization used for interest income and expense accruals and for deferral of fees that are in lieu of interest and straight line or declining balance amortizations used for cost deferrals and investment depreciation .

Other Revenue Pricing. In situations where account and event activity can be used to derive account level income or fees the Value Analyzer system calculates these drivers of the profitability in the Other Revenue calculations. These calculations comprise linear combinations of event or account values and modeled coefficients.

Direct Expense. The calculation of account profit adjustments due to account related activity requires rules that take the form of linear combinations of event or account values and modeled coefficients.

Indirect Expense. In situations where expense apportionment or amortization amounts are aggregated the user may want different rules applied depending on the path or dimension of aggregation. These rules allow for multiple Profitability Calculations rules to be applied to derive multiple account level Indirect Expense amounts.

Risk Provision. Adjusting current profit for expected future losses is known as actuarial profit provisioning. The Value Analyzer system applies actuarial based methods in its account level Profitability Calculations where the actuarial reserve that the provisions maintain represents the expected loss associated with all accounts.

Taxable Equivalent Gross up. Profit is an after tax measure and thus some events or portions of some accounts profits may be excluded from normal taxation. The Value Analyzer system adjusts these pre tax values so that a singular tax rate can be used to convert pre tax profit into after tax values which are also known as taxable equivalent adjustment. These rules use account and event attributes to adjust each of the five factors of the FFAPM to a taxable equivalent basis.

Interest Yield Adjustments. Since the Value Analyzer system can calculate profits for any number of periods the adjustment of cash interest payments and the financial statement s accrual or smoothed representation of interest related Profit the Value Analyzer system provides a method for converting cash interest amounts to accrual amounts for financial statements. The Value Analyzer system implements an effective interest rate conversion to accomplish this type of calculation.

Shareholder Value Add. Shareholder Value Add SVA is used to calculate Earnings and is a method that Financial Institutions use to adjust Profit for risk. The idea is to subtract the cost of the equity required to support the profit measure from the profit measure. Financial Institutions use this risk adjustment measure to penalize the profit for risk.

Allocated Balances. The Value Analyzer system uses Allocated Balances AB functionality as a Cost of Funds for the NIR calculation. Specifically the Cost of Funds include Allocated Balances that are used to assign balance sheet amounts that are not actual account balances and the Allocated Balances are selected from a group comprising Float Fixed Assets Payables and Receivables balances.

The Profitability Calculations may include performing a Rule ordering process for at least one of the Rules applied in the Profitability Calculations . The Rule ordering process is based on the concept that at least one of the Rules may have dependencies on other Rules which may thus require multiple levels of a Profitability Calculation to be generated. Rules without dependencies are processed first followed by Rules that have dependencies on Rules processed previously. The Rule ordering process further comprises iteratively processing the Rules until all of the Rules have been processed.

This ensures that during execution Rules are run after Rules on which they are dependent for results. The Value Analyzer Calculation Engine controls the Rule ordering process through execution of the Profitability Calculations by selecting each set of Rules and generating SQL statements in response thereto.

In the Rules ordering process example of the Value Analyzer Calculation Engine initially determines that this is the first run through a Profitability Calculation and selects the set of Rules with no dependencies in the figure rules and for processing. Upon completion of these Rules the Value Analyzer Calculation Engine determines that more Rules need to be processed and selects Rules that are dependent on the Rules already processed in the figure rules and which are then be processed by the Value Analyzer Calculation Engine . These steps continue any number of times until no more Rules are left to be processed and the Value Analyzer Calculation Engine proceeds on to the next Profitability Calculation to be processed. Generally Rules without dependencies are processed first followed by Rules that have dependencies on the Rules processed previously. This iterative process continues until all Rules have been processed. Moreover this methodology can support any number of levels of Rules .

Note that steps 2 through 6 perform account level calculations. Steps 2 3 4 5 and 6 can be performed independently and in parallel while step 7 requires values derived in steps 2 3 4 5 and 6 and therefore must be performed after steps 2 3 4 5 and 6 are completed.

The Profitability Calculations generate one or more values for the five factors of the FFAPM and specifically the NIR OR DE IE RP and Profit values. These values are used to generate the Database which comprises one or more tables stored by the RDBMS in the relational database.

The Value Analyzer system includes an application code generation and execution methodology known as BLURS Bypass Logging User Restartability and Status functions that allows for n level Profitability Calculations execution management bypass user restartability execution logging and real time status capabilities. Specifically the BLURS functions manage the setup generation of SQL statements and the subsequent execution of SQL statements.

In the Value Analyzer system the Value Analyzer Calculation Engine oversees the execution of Profitability Calculations including the generation and execution of SQL statements by the RDBMS . Previously users would start a job comprised of one or more Profitability Calculations and including one or more SQL statements and have little control as to when and how it completed. When an error occurred the user would have a substantial effort to find the location and cause of the error. In addition the user would have to reset and restart the job from the beginning resulting in a substantial loss of time.

In the preferred embodiment the Value Analyzer system performs financial processing by performing Profitability Calculations by applying Rules to account product and event attributes accessed from the RDBMS wherein the Profitability Calculations include setup generation and execution of SQL statements by the RDBMS . Using the BLURS functions the Value Analyzer system monitors the Profitability Calculations by monitoring the setup generation and execution of the SQL statements by the RDBMS in order to provide bypass logging user restartability or status BLURS functions for the Profitability Calculations .

The BLURS functions use stored procedures tables and coding concepts to provide a job management and execution facility for the Value Analyzer system . Processing preferably occurs within the Value Analyzer Calculation Engine and the RDBMS although processing may be performed by other modules as well.

In the preferred embodiment the RDBMS stores a table known as the Calc Engine SQL table which is the main repository for BLURS information. This table is used by the BLURS functionality to store generated SQL statements current status of jobs timings activity counts or error codes for each SQL statement in real time. This table is also selected or queried by a user in order to view what SQL statement the RDBMS is currently processing what SQL statements that have generated errors in the RDBMS the current status of the job the timings the activity counts or the error codes for each SQL statement in real time.

The Calc Engine SQL table is used by the BLURS functions to hold generated SQL statements status timings activity counts and error codes for each SQL statement in real time. The user can select or query from this table in order to view the current status of a job what SQL statement the RDBMS is currently processing and what SQL statements that have generated errors.

The SQL Generation Phase generates the SQL statements and the SQL Execution Phase executes the SQL statements in the identified order. The specifics of the BLURS functions in both of these phases are described below 

Before each statement is processed in the execution phase the Calc Engine SQL table is checked for a prior statement that has generated a fatal error. If an Error is found a SQL Stmt Status Cd 5 the current statement is bypassed which is to say it will not run. The net effect of this processing is that after a fatal error status has been generated for a statement all statements following sequentially are bypassed essentially aborting the job. A user monitoring the status of a job via the Calc Engine SQL table upon witnessing a statement status being updated with an Error status should see the job quickly come to an end.

Logging occurs before and after each statement is processed and after the restart and bypass checks. The before logging updates the Calc Engine SQL table with information indicating that the SQL is Working a SQL Stmt Status Cd 2 and sets the start time for execution of the statement. The after logging occurs immediately following execution of the statement and updates the status with either a Success Error or Warning code as well as the stop time calculated elapsed time and the activity count. This information may be used for Bypass and User Restartability as well as debugging and run analysis. When a job is finished a copy of the job is archived to the archive table.

User Restartability uses the Logging data to determine if a job is being newly run or restarted from an existing run. The SQL Generation phase loads each statement with a Pending status a SQL Stmt Status Cd 1 . Before each statement is processed the Calc Engine SQL table is checked for the status of the statement. If the statement has a Success or Warning status a SQL Stmt Status Cd 3 or 4 the statement is considered as already having been run and is skipped. If the status is Error a SQL Stmt Status Cd 5 the statement is considered as a statement that failed in a previous run and is attempted again it is assumed that some corrective measure has been taken by the user in order for the statement to be re tried . A Pending status for a statement indicates that the statement has not been previously attempted and it is executed.

The Status function is an extension of the Logging capability in that the Value Analyzer Calculation Engine and or RDBMS updates the Calc Engine SQL table as events occur. This allows the user to query the Calc Engine SQL table and obtain specific information on the job in real time while the job is being processed.

The Engine Monitor Window provides a convenient way for the user to Start Monitor Break or Stop execution of a job.

Field allows a user to specify the Selector SQL statement and Gen button begins the generation of the Selector SQL statement. Field allows the user to specify the run type either ALL generate and execute the SQL statements GEN generate the SQL statements or RUN execute the SQL statements .

Field allows a user to select the FFAPM metrics of the Profitability Calculation to generate i.e. AB Allocated Balances NIR Net Interest Revenue CA SVA Shareholder Value Add OR Other Revenue IE Indirect Expense DE Direct Expense RP Risk Provision and ALL .

Field allows a user to specify a starting procedure and its parameters if any and the Start button initiates execution of the starting procedure.

Stop button and Clear button are used to set and clear breaks in the execution of the SQL statements for the Profitability Calculations .

The bottom half of the Window provides a glimpse into the execution of the job as it is proceeding. Depending on the refresh rate selected at the user can watch the job proceed in real time. All of the rows in the Calc Engine SQL table are presented in the bottom half of the Window . The user can review status elapsed times etc.

If the user sees anything that suggests the job should be stopped the Window provides the user with the opportunity to abort the job immediately the Start button turns to an Abort button while the job is running or insert or remove breaks using and at any point in the execution processing using the Debug section.

Block represents the Value Analyzer Client accepting commands from a user to invoke or perform one or more Profitability Calculations .

Block represents the Value Analyzer Calculation Engine invoking one or more SQL macros in the RDBMS to select accounts events and products from the relational database based on the specified Profitability Calculations .

Block represents the Parsing Engine of the RDBMS accessing the SQL macros and the SQL statements therein and transforming the statements into an operator tree.

Block represents the Parsing Engine of the RDBMS generating one or more access plans from the operator tree.

Block represents the Parsing Engine of the RDBMS parallelizing the access plans and then transmitting the access plans to their assigned Access Module Processors A E of the RDBMS .

Block represents the Access Module Processors A E of the RDBMS executing the access plans and thereby performing the required data manipulation associated with the access plans received from the Parsing Engine wherein the required data manipulation associated with the access plans are performed in parallel by the Access Module Processors A E.

Block represents the Value Analyzer system performing the BLURS functions which are described in more detail below.

Block represents the Parsing Engine of the RDBMS standardizing the results received from the Access Module Processors A E and storing the standardized results in the intermediate tables in the relational database.

Block represents the Value Analyzer Calculation Engine invoking one or more SQL macros in the RDBMS to perform the calculation steps of the Profitability Calculations by applying the Rules to the results stored in the intermediate tables in the database.

Block represents the Parsing Engine of the RDBMS accessing the SQL macros and the SQL statements therein and transforming the statements into an operator tree.

Block represents the Parsing Engine of the RDBMS generating one or more access plans from the operator tree.

Block represents the Parsing Engine of the RDBMS parallelizing the access plans and then transmitting the access plans to their assigned Access Module Processors A E of the RDBMS .

Block represents the Access Module Processors A E of the RDBMS executing the access plans and thereby performing the required data manipulation associated with the access plans received from the Parsing Engine wherein the required data manipulation associated with the access plans are performed in parallel by the Access Module Processors A E.

Block represents the Value Analyzer system performing the BLURS functions which are described in more detail below.

Block represents the Parsing Engine of the RDBMS standardizing the results received from the Access Module Processors A E and providing the standardized results to the Value Analyzer Calculation Engine .

Block represents the Value Analyzer Calculation Engine delivering the output or results from the Profitability Calculations to the Value Analyzer Client and or the RDBMS . With regard to the Value Analyzer Client the results may be presented to the user printed or used by various other computer programs as desired. With regard to the RDBMS the results may be stored for later use by the Value Analyzer Client the Value Analyzer Calculation Engine or other computer programs as desired.

With regard to Blocks and although they are shown in a specific sequence the BLURS functions may be performed before during or after any of the other Blocks of the . Specifically the Value Analyzer system performs financial processing which includes performing one or more Profitability Calculations by applying one or more rules to account product and event attributes accessed from the RDBMS . These Profitability Calculations include the setup generation and execution of SQL statements by the RDBMS . The Value Analyzer system via Blocks and monitoring the Profitability Calculations by monitoring the setup generation and execution of the SQL statements by the RDBMS in order to provide the BLURS functions for the Profitability Calculations . As noted earlier the BLURS functions allow for n level profitability calculations execution management bypass user restartability execution logging and real time status capabilities.

This concludes the description of the preferred embodiment of the invention. The following paragraphs describe some alternative embodiments for accomplishing the same invention.

In one alternative embodiment any type of computer or configuration of computers could be used to implement the present invention. In addition any database management system decision support system on line analytic processing system or other computer program that performs similar functions could be used with the present invention.

In summary the present invention discloses a Value Analyzer system which is a data driven computer facilitated financial model that provides accurate and consistent profitability calculations using account product and event attributes stored in a relational database managed by a relational database management system RDBMS . Profitability calculations are performed in the computer by applying one or more rules to the account product and event attributes accessed from the database wherein the profitability calculations include setup generation and execution of structured query language SQL statements by the RDBMS. The present invention also monitors the profitability calculations by monitoring the setup generation and execution of the SQL statements by the RDBMS in order to provide bypass logging user restartability or status BLURS functions for the profitability calculations.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

