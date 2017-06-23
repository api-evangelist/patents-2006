---

title: Tax deduction revaluation system
abstract: A method and system for calculating a tax credit obtains a tax function T(A), a value for deduction (D), and a value for an income amount (A) at which a computation is based. The method and system computes a tax credit C=k(T(A)−T(A−(D−C))). The calculation may be done non-recursively or recursively by calculating values C=k(T(A)−T(A−(D−C))).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07769662&OS=07769662&RS=07769662
owner: 
number: 07769662
owner_city: 
owner_country: 
publication_date: 20060814
---
The present patent application is based on Provisional Application No. 60 708 358 filed Aug. 15 2005 the entire contents of which are hereby incorporated by reference in their entirety.

The invention is useful in the field of data processing and more particularly to computation of certain recursive values such as tax deductions.

In the tax payment processes used by governments and other tax imposing agencies for taxes such as income taxes taxpayers are typically allowed to deduct certain expenses as the taxable amount is being calculated. One deduction commonly allowed is payment of other taxes.

Allowing a deduction creates a tax credit for the taxpayer namely the difference between the amount of tax that would have been paid if that deduction had not been allowed and the amount of tax paid if that deduction is allowed.

A tax credit reduces the expense that formed the deduction so that the tax imposing body is allowing the amount of deduction to be too large if the amount of the deduction allowed is the amount of the claimed expense. In this case the valuation of the deduction is too high.

An object of the invention is to avoid over valuation of a tax credit and correctly reduce the amount that the tax imposing body returns to the taxpayer. In order to do this the actual value of the tax credit created should satisfy the following 

This is because the actual expense being incurred by the taxpayer is being reduced by the tax credit. This is the Tax Credit Definition on which the preferred embodiment of this invention is based. However working with alternate tax credit definitions is within the scope of the invention.

The Dampening Factor is a factor inserted for flexibility to enable the tax imposing body to reduce the tax credit granted depending upon the Tax Amount and the Deduction. For example if the Tax Amount becomes large relative to other tax amounts in the taxable population the tax imposing body may wish to reduce the percentage of the Deduction that is allowed to be used to reduce the tax paid.

Another function of the Dampening Factor is to enable the tax imposing body to maintain pre existing or desired levels of tax revenues. Prior to implementation of this tax credit methodology various techniques may have been used by the tax imposing body for example minimum tax models such as the Alternative Minimum Tax and Corporate Minimum Tax models used in the United States to disable the use of deductions by taxpayers to reduce taxes paid. For example by setting the Dampening Factor to be very large relative to the Tax Amount and the Deduction the left hand side of the above equation becomes nearly 0 that is smaller than the smallest unit of currency used so that the Deduction is disallowed. Because the Dampening Factor can be varied according to the values of the Tax Amount and the Deduction this provides great flexibility in managing the valuation of the tax credit and so the revaluation of the Deduction.

The true valuation of a deduction that should be allowed by the tax imposing body is the expense amount that generates the deduction reduced by the tax credit calculated to solve the above equation.

This invention enables incorporation of tax deduction revaluation into general tax systems the host systems that include and support all tax processing and calculation methods and includes a system that performs the computations needed for the revaluation of claimed tax deductions. The invention is applicable to all tax systems including the U.S. Individual Income Tax all filing statuses and the U.S. Corporation Income Tax but is not limited to these tax systems. The invention checks to be certain that the calculations for the tax credit and revaluation of the deduction can be carried out successfully in the tax system to which it is being applied.

The credit may be an approximation of the value expressed by equation such as when a recursive calculation converges to within a specified limit.

Other exemplary embodiments and advantages of the present invention may be ascertained by reviewing the present disclosure and the accompanying drawings.

The particulars shown herein are by way of example and for purposes of illustrative discussion of the embodiments of the present invention only and are presented in the cause of providing what is believed to be the most useful and readily understood description of the principles and conceptual aspects of the present invention. In this regard no attempt is made to show structural details of the present invention in more detail than is necessary for the fundamental understanding of the present invention the description taken with the drawings making apparent to those skilled in the art how the several forms of the present invention may be embodied in practice.

Referring to the system is comprised of several different modules. The modules may be software or hardware. The primary modules are identified described and interact with each other as follows.

A Data Access Module interfaces with data sources to obtain information that includes but is not limited to 

 i description of the tax function including a definition of the tax function itself tax brackets and marginal tax rates brackets and marginal rates can be derived from the definition of the tax function if not provided separately 

 ii value of the income amount referred to in the following as the base income or the taxable income at which computations are based e.g. adjusted gross income 

 iv value of the dampening factor or definition of a dampening factor function which can be applied to the income amount ii and the deduction s iii 

 v sensitivity coefficients how much of an approximation is required of the system usually to a certain fraction or of the currency unit used in the tax processing and

 vi numerical processing bound s which if provided can override the default values set in a Recursion Processing Module discussed below .

A Data Conversion Verification Module converts the information provided via the Data Access Module into forms used by the system. For example if the tax function is specified by a table of values it may be converted into a piecewise linear function whose coefficients are obtained by processing the values of the table.

If the information provided via the Data Access Module is provided in forms that may be used by the system such as a piecewise linear function including necessary coefficients then this module may simply verify those forms and pass the information to a Consistency Solvability Check Module discussed below . In this case no conversion of data is performed.

Once the data provided via the Data Access Module is in forms used by the system this data is passed to a Consistency Solvability Check Module . All data passed to the Consistency Solvability Check Module comes from this Data Conversion Verification Module even if no conversion of the data from the Data Access Module occurs.

A Consistency Solvability Check Module checks the consistency of the data provided through the Data Conversion Verification Module . These consistency checks may include but are not limited to verification of correct overlap of the taxable income intervals and associated coefficients for which the tax function is linear. These checks may also include confirmation that the tax function coefficients corresponding to marginal tax rates are monotonically increasing or if they are not and if linear interpolation is required for computation that the associated sensitivity parameters are sufficiently fine.

Using these checks the system also verifies that the tax function provided can be successfully processed within the range of the data values provided by the Data Conversion Verification Module such as base income amount values of claimed deductions dampening factor and sensitivity parameters .

If the module determines that the tax function cannot be successfully processed the system sends an Error Message to the host system and terminates.

The Consistency Solvability Check Module may set a Non Recursion Processing Flag and pass the data obtained from the Data Conversion Verification Module including but not necessarily restricted to the base income amount the values of claimed deductions and the dampening factor to the Forced Solution Module discussed below .

A Recursion Processing Module processes the tax function and the data provided running an iterative recursion defined by the Tax Credit Equation 

Note that although the natural definition of and processing of the Tax Credit Equation are recursive it may be computationally optimal to use a non recursive processing technique as described below Forcing a Solution When Second Forced Solution Flag Is Set .

Although there may be other methods or processes for computing the tax credit to be allowed by the tax imposing body the Tax Credit Equation is consistent with and reflects the Tax Credit Definition. Any change in the Tax Credit Definition automatically changes the Tax Credit Equation and vice versa. The system can handle different Tax Credit Definitions by applying the corresponding different Tax Credit Equations.

The Recursion Processing Module terminates when either i two consecutive values of tax credits fall within the sensitivity parameter set in the Data Access Module or using a default value for sensitivity or ii a numerical processing bound is reached.

The sensitivity of a computation in the system is the precision required by or defined for that computation. A sensitivity parameter is the parameter within the system that represents and is assigned the value for a sensitivity of a computation.

A numerical processing bound for a computation which can be either a single calculation or a set of calculations is a limit or bound imposed on one or more particular numerical characteristics of that computation. Such characteristics may include without limitation number of iterations total execution time for the computation and size of a result of the computation. All numerical processing bounds for the system preferably have default values that can be overridden by values set in the Data Access Module .

The system preferably contains default values for all its sensitivities. These can be overridden by values obtained in the Data Access Module . The system also carries sensitivity flags. When a sensitivity flag is turned off this indicates that the corresponding computation must yield exact value s . By default all sensitivity flags are preferably on. If a sensitivity flag is turned off two values of the corresponding computation fall within the sensitivity parameter if and only if they are identical. If a sensitivity flag is turned on two values of the corresponding computation fall within the sensitivity parameter if and only if the distance between them is less than the value of the sensitivity parameter.

If two consecutive values of tax credits fall within the sensitivity parameter then the last value processed is returned as the Final Tax Credit.

If a numerical processing bound is reached without consecutive values of tax credits falling within the sensitivity parameter the system sets a Forced Solution Flag the effect of which is discussed below.

A Forced Solution Module executes if the Forced Solution Flag is set. The Forced Solution Flag is set only when a computation has not obtained results that fall within the sensitivity parameter but when a numerical processing bound has been hit or exceeded.

There are two primary reasons why a Forced Solution Flag would be set. The first reason is that a computation that is being iterated will not converge to within the sensitivity parameter. The second reason is that the computation will converge but the value of the numerical processing bound disallows a sufficient number of iterations of the computation for the results to fall within the sensitivity parameter. The first situation is described as true non convergence while the second is not true non convergence.

If a Second Forced Solution Flag is not set as discussed below the Forced Solution Module checks for true non convergence of the tax credit sequence. True non convergence for the tax functions under consideration functions T x that are continuous increasing T x T x whenever x100 Max for two 2 consecutive values of n. The value 100 used here is illustrative and can be adjusted as a system parameter. Similarly the number 2 of consecutive values for the sequential index n used here is simply illustrative and can also be adjusted as a system parameter. If true non convergence is detected then i a Second Forced Solution Flag is set ii a message is sent to the host system advising of occurrence of true non convergence and including the computational parameters when such non convergence occurred and iii Forced Solution Module is called again.

If there is no true non convergence or if true non convergence is not detected then the Forced Solution Module continues execution of the iterative recursion of the Tax Credit Equation. If two consecutive values of tax credits thus obtained fall within the sensitivity parameter then the last value processed is returned as the Final Tax Credit and this module sends a message to the host system advising of a bad setting for a numerical processing bound for the system because the Forced Solution Flag was set prematurely .

If after continued execution a numerical processing bound again is reached before two consecutive values of tax credits fall within the sensitivity parameter then i a message is sent to the host system advising of failure of iterative execution and including the relevant computational parameters ii a Second Forced Solution Flag is set and iii the Forced Solution Module is called again.

If a Second Forced Solution Flag is set then the Forced Solution Module takes the last two values of tax credits that had been obtained and determines a solution to the Tax Credit Equation lying between these two values of tax credits. In this case the module may turn one or more sensitivity flags on if they had been off depending upon factors for optimizing system processing speed . This solution is returned as the Final Tax Credit and the Second Forced Solution Flag is cleared.

If the last two values of tax credits obtained were Cand C then a brute force technique for forcing a solution may be to have the Forced Solution Module examine each possible currency value between these two values.

However a different approach is usually more efficient and also can be used to provide confirmation that the iterative solution converges to the correct solution for the tax credit when the recursive processing converges . This approach can be used in addition to or instead of the iterative solution approach. Like the iterative solution it originates from the Tax Credit Equation. If a Non Recursion Processing Flag is set this non recursive approach is taken as described in the following. A non recursive method is implemented in a Non Recursion Processing Module a sub module of the Forced Solution Module .

The non recursive method uses the fact that tax functions are typically piecewise linear being linear or affine meaning that the tax function can be written in a form T x rx b for the taxable income values x in an individual tax bracket. The value r is referred to as the marginal tax rate for this bracket.

Suppose that the tax bracket boundaries are listed as the m values A 0 A . . . A where the first tax bracket is the taxable income A such that A 0 A

Write the tax function for the jtax bracket as T x rx b as obtained from the Data Conversion Verification Module . If Forced Solution Module is given the values A for taxable amount D for original deduction amount and k for the dampening factor the Non Recursion Processing Module will identify a value i so that A lies in the itax bracket and will form the i values

A Deduction Revaluation Module takes the value of the Final Tax Credit obtained. If the Forced Solution Flag is not set this module takes the value of the Final Tax Credit from the Recursion Processing Module . If the Forced Solution Flag is set or if the Non Recursion Processing Flag is set this module takes the value of the Final Tax Credit from the Forced Solution Module and clears the Forced Solution Flag or the Non Recursion Processing Flag.

The Deduction Revaluation Module checks that the Final Tax Credit is a solution to the Tax Credit Equation to within sensitivity set for this solution and verified by the Consistency Solvability Check Module . If it is not a solution the Deduction Revaluation Module sends an Error Message to the host system and the system terminates. If it is a solution then the Deduction Revaluation Module reduces the value of the deduction obtained from the Data Access Module by the value of the Final Tax Credit and returns this reduced value as the Revaluated Deduction. This Revaluated Deduction is the value of the deduction to be allowed by the taxing entity.

The Deduction Revaluation Module then checks if further runs of the system are required for multiple deduction amounts obtained by the Data Access Module . If so this module calls the Consistency Solvability Check Module .

Under Schedule X in Tax Year 2005 there were six 6 tax brackets with the boundaries being 0 7 300 29 700 71 950 150 150 326 450. The marginal tax rates for those brackets were 10 15 25 28 33 35 .

The programming in the spreadsheets uses only Excel spreadsheet functions. Cell formulas are shown at heads of columns . For example in cell F calculates the tax T on 75 000 A D C the value in cell E by using the formula VLOOKUP E A 2 F 7 5 TRUE E VLOOKUP E A 2 F 7 6 TRUE . Here the array A 2 F 7 is the table of tax brackets in the upper left corner of the spreadsheet.

In the example represented in A 250 000 D 175 000 and k 1. Using a sensitivity of 1 0.01 the smallest unit of currency in this example the recursion converges in 13 iterations and shows that C 42 181.64. This means that the deduction should be reduced from 175 000 to 132 818.36 increasing the tax paid from 15 506.50 if the full deduction were allowed to 27 317.00 rounding to the nearest dollar .

From and it is clear that as the Dampening Factor increases the amount of the revaluated deduction decreases because the tax credit increases . It is also clear that as the Dampening Factor increases the recursion converges more slowly. For example for k 3 not illustrated more than 1 000 iterations would be required to push consecutive values of the tax credit sequence C to within 0.01 of each other.

Slow convergence is not an issue when the non recursive processing technique of E.2 is used. As is illustrated in and the algorithm settles in the same number of iterations. Indeed it will always be the case regardless of the value of the Dampening Factor that the maximum number of computations to be made using this non recursive processing technique will be the number of tax brackets in the tax function. For this example the tax function has six 6 brackets but because the taxable amount A lies in the 5bracket at most 5 computations are required.

The system described herein can be implemented as a standalone system e.g. using a computer program such as Microsoft Excel as demonstrated in the previous example in section G . In such an implementation some of the functionality associated with the Data Access Module the Data Conversion Verification Module the Consistency Solvability Check Module and the Deduction Revaluation Module may be performed manually by the user in conjunction with functionality provided by the computer operating system and application programs. This was demonstrated in the example in section G.

Because the preferred embodiment is designed to be usable as an alternate method to existing methods for evaluating and managing tax deductions in tax processing systems the preferred embodiment can be implemented as a system of software modules with interface s to the host system defined by the Application Programming Interfaces APIs of the host system so long as the host system can provide the data required by this Tax Deduction Revaluation system via Data Access Module . The preferred embodiment is designed so that the processing load on the host system induced by inclusion of this system of software modules can be controlled monitored and optimized. The recursive and or non recursive algorithmic processing required for this system is minimal. The incremental processing memory and data storage requirements imposed on the host system are minimal to the point that no hardware modifications or enhancements may be necessary.

The source code of the software implementing the preferred embodiment can be written in any standard programming language including but not restricted to C C Java and Perl. Pre programmed scripts spreadsheets and other files may be distributed by transportable storage media such as CD Rom or by electronic transmission such as over the Internet.

It is noted that the foregoing examples have been provided merely for the purpose of explanation and are in no way to be construed as limiting of the present invention. While the present invention has been described with reference to certain embodiments it is understood that the words which have been used herein are words of description and illustration rather than words of limitation. Changes may be made within the purview of the appended claims as presently stated and as amended without departing from the scope and spirit of the present invention in its aspects. Although the present invention has been described herein with reference to particular means materials and embodiments the present invention is not intended to be limited to the particulars disclosed herein rather the present invention extends to all functionally equivalent structures methods and uses such as are within the scope of the appended claims.

