---

title: Variable precision computation
abstract: The present invention provides a method and system for describing variable precision computations without needing explicit conversion functions in case operands have different formats or sizes of fields, having the capability to modify at run time the sizes of the fields of any variable precision data object, as well as having access to special condition signals associated to each object in which results are stored.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07930690&OS=07930690&RS=07930690
owner: 
number: 07930690
owner_city: 
owner_country: 
publication_date: 20061016
---
1. Process description code written in a language that can be processed by a computer which sets the values of objects referred to in general as signals and more specifically as wires registers variables or nets and which is executed whenever there is a change in the value of one of the objects listed in the sensitivity list of the given process.

2. Hardware Description Language or HDL language that can be processed by a computer and that supports the description of electronic circuits for the purpose of predicting its behavior or for the purpose of creating the actual circuit from such a description. An HDL must have the capability of describing processes.

3. Digital simulation simulation of a hardware description provided in an HDL where values of the individual bits are being modeled as having two states 0 1 three states 0 1 x or four states 0 1 x or Z and possibly having strength associated to such states.

4. Front end program that reads the HDL description provided by the user and produces code that when executed simulates the HDL description.

5. Back End program comprising the code generated by the front end and code that is common to all simulations also known as kernel.

6. Run time or runtime the period of time during which the back end simulates the circuit. At run time means during the execution of the back end.

7. Abstraction level HDL descriptions are said to be at certain abstraction levels transistor level gate level rtl level behavioral level. Rtl level and behavioral level are said to be above gate level.

8. Arithmetic operators operators which include addition subtraction multiplication division power modulo .

10. Value rational number represented by various bits whose meaning is indicated by the associated information of format and sizes.

11. Floating Point representation or format manner in which a value is represented as exponent sign and mantissa as described by Standard IEEE 854.

12. Fixed Point representation or format the meaning of the corresponding bits is two s complement sign magnitude or fixed bcd.

13. Two s complement representation comprising two concatenated series of bits i.e. the integer part and the fractional part with the most significant bits being the integer part. The sign of a value is given by the most significant bit of the integer part with the value 1 corresponding to negative and 0 to positive. Positive numbers have as value the integer part viewed as an integer plus the sum of products between the value of the i th bit of the fractional part counting from the most significant and 2 i with the first bit being counted as 1. Negative values are obtained from their positive counter parts by taking the two s complement of the entire concatenation of the integer and fractional parts.

15. Right Hand Side or RHS expression occurring on the right hand side of an assignment e.g. of the sign.

16. Left Hand Side or LHS expression occurring on the left of an assignment i.e. the target of the assignment.

17. Variable Precision Descriptor data container able to contain all the information necessary to process the data to which the descriptor is associated. Information stored in the descriptor includes format of the data sizes of the fields of the format rounding options overflow options miscellaneous data regarding level of warnings etc.

18. Variable Precision Data Object data container that contains a handle to the associated descriptor and a number of bits that represent a value and which must be interpreted according to the information in the descriptor.

20. sensitivity list list of HDL supported objects whose change in value triggers the execution of the process that is sensitive to this sensitivity list.

21. Implicit info object HDL object i.e. of one of the types supported by the HDL that is associated by the front end to a Variable Precision Data Object and that the user can reference in reading it writing to it and using it in sensitivity lists without having to declare it.

Digital simulation at an abstraction level above gate level may use arithmetic or logic operators as well as system functions to model computations that are performed by the given circuit. The results of such computations depend on the representation of the values within the operands i.e. the format used e.g. floating point or fixed point and the number of bits of the fields of the given format.

In general it is best to use the appropriate number of bits for the representation of operands involved in computations. More bits than necessary will use too much power and fewer bits than necessary will introduce quantization errors that may be unacceptable for the correct behavior of the circuit.

Prior to this invention designers could insert in their hardware description language calls to pre defined functions that would perform the required computation using the appropriate format and precision and then perform simulations using this predefined functions. In case one operand does not have the appropriate format or size a conversion function could be called that would transform the given operand into an operand of the appropriate format and size.

Therefore prior to this invention the task of finding out the best formats and sizes for each operand was very time consuming since either explicit code for each kind of format and size needed to be inserted in the HDL simulation or numerous simulation performed each with a different format or size for some operands.

For example based on this invention the designer can write in Verilog HDL expressions involving operands of various formats having sizes which can be modified during the execution of the simulation. Also there is no need for using explicit conversion functions or system functions for operations such as addition subtraction multiplication division power remainder modulo for which there are operators in Verilog HDL.

Having the capability of modifying the format or number of bits used during the simulation makes it possible to find out the ideal format and number of bits for each operand without human intervention in the optimization loop. Also this capability allows to model hardware that is designed to change the formats and the number of bits of the operands during the execution of their functionality.

1. MatLab the program being sold by MathWorks supports the description of expressions and their evaluation where the operands have a given number of bits. Such expressions can be simulated within a Verilog simulator using Simulink. However the sizes of the operand representation may not be modified to a specific value nor the format of the representation changed at run time without human intervention see reference 2 .

2. The companion of MatLab the Symbolic Math Tool Box see reference 1 contains a function named vpa for variable precision arithmetic which accepts as inputs an expression e and a number d and returns a value r that contains the value of the expression with d correct digits of fractional part.

First we must notice that the number of correct digits produced by the function vpa does not guarantee the use of a certain number of bits for mantissa exponent or integer fractional part of the operands of the expression e even for simple two operand expressions. Evidently the number of bits used in order to produce d correct digits of fractional part depends on the value of the operands of expression e. Therefore using this approach one cannot evaluate an expression where the operands have sizes of their fields modified to exact values during the execution of the program without human intervention. It follows that the use of the vpa function in the Symbolic Math Tool Box does not provide any of the solutions claimed by this invention.

3. U.S. Pat. No. 6 857 118 assigned to Mathworks teaches how function calls containing other function calls as arguments can be processed more efficiently. This patent does not teach how to implement any of the features claimed by this invention. Specifically it does not teach how to change sizes of operands at runtime without human intervention how to associate implicit info objects to variable precision data objects how to support operators that accept operands of different formats and sizes and how to support overloading of assignments.

4. SystemC supports a library providing fixed point arithmetic computations for various sizes of operands see reference 3 . However this library does not support any of the features claimed by this invention.

5. Mentor Graphics made an announcement see reference 4 in June 2006 regarding the release of a C C library supporting computations with desired precision. However that announcement does not make any of the claims made by this invention.

6. Fintronic USA Inc. made an announcement on Jul. 21 2006 see reference 5 regarding support by Super FinSim of Variable Precision Fixed Point and Floating Point Computations. The announcement by Fintronic USA Inc. tells what Super FinSim Fintronic s Verilog simulator can achieve by using the present invention. However neither the announcement nor the documentation teaches anything about the embodiment supporting the claims made by this invention.

The present invention provides a method and system for describing variable precision computations without needing explicit conversion functions and supporting access to special condition signals associated to each object where results will be stored.

This is achieved by 1 allowing the user to a mark some objects as variable precision data objects b mark some objects as descriptors c associate descriptors to each of the data objects d set the fields of the descriptors to appropriate values e use supported operators and functions that accept variable precision data objects and 2 by having the front end i convert literals into variable precision data objects ii insert conversion functions between variable precision data objects and other data types and 3 by having in the simulator functions that can accept variable precision data objects of any of the supported formats e.g. floating point floating point with no denormals two s complement sign magnitude two s complement with negative sizes floating point bcd etc.

The present invention is directed to a method and apparatus supporting variable precision computations in Hardware Description Languages. The following description is presented to enable one of ordinary skill in the art to make and use the invention and is provided in the context of a patent application and its requirements. Various modifications to the preferred embodiment and the generic principles and features described herein will be readily apparent to those skilled in the art. Thus the present invention is not intended to be limited to the embodiment shown but is to be accorded the widest scope consistent with the principles and features described herein.

According to the present invention variable precision computation is made possible by having the user specify variable precision data objects and descriptors and associate descriptors to data objects. In doing so enough information is available at run time when computations are performed on the data objects and their associated descriptors so that the computations can be carried on as specified. Also the capability of accessing implicit info objects permits to access overflow or underflow information as well as to maintain the cumulative error associated to each data object which in turn leads to the capability to distinguish between correct special conditions e.g. overflow and underflow which would occur irrespective of the number of bits used during the computation and erroneous special conditions e.g. underflow or overflow which may occur due to quantization errors.

One skilled in the relevant art however will readily recognize that the invention can be practiced in slightly different way without one or more of the specific details or with other methods etc. In other instances well known structures or operations are not shown in detail to avoid obscuring the invention.

Original Verilog Code with Variable Precision Computation Showing an Initial Statement in the Context of Example 1.

a way to inform the function evaluating the expression in the back end of the specific type of the data corresponding to the literal. To show both solutions in detail in this embodiment real literals are assigned to temporaries and integer literals are converted to integers in an fstBundleT type with at least on of two arguments relating to the sizes of the main argument being non zero. In other words the main argument of a function contains a vp value only if at least one of the related two arguments has a non zero value. The related arguments are named ini SizeOfInt ini SizeOfDec for argument ml and similarly in2 SizeOfInt in2 SizeOfDec for argument in2 and the related code can be found in the back end functions such as fstVpAdd. Each temporary registers is allocated a descriptor for it is allocated as well and calls to VpAssocDescrToData are inserted in the special initial statement mentioned above in order to associate descriptors to the temporary registers.

 i temporary registers are allocated descriptors are allocated for each temporary register calls to VpAssocDescrToData are inserted in the special initial statement mentioned above in order to associate descriptors to the temporary registers 

 ii the expression is transformed into a sequence of assignments to temporary registers each one having as right hand side a simple expression consisting of either system function call or an operator applied to one or two operands and as lhs a temporary register or a user defined vp data object. If the lhs is a temporary register a call to a system task fstVpSetDescrFromN is inserted in front of the given assignment where N can be 0 1 or 2. The fstVpSetDescrFromN system tasks set the descriptor of the lhs of the next assignment to the appropriate values with N signifying the number of arguments having descriptors which participate in the value of the lhs. The system task fstVpSetDescrFromN accepts as argument in addition of the lhs and of the operand containing a descriptor if N 0 also an argument indicating the kind of expression of the rhs. The descriptor of the lhs is going to be set to different value in case the expression on the rhs is an addition or a multiplication although both may accept two vp data objects. The insertion of fstVpSetDescrFromN is exemplified in Example 2 and 15 the actual fstVpSetDescrFrom0 fstVpSetDescrFrom1 and fstVpSetDescrFrom2 are shown in the code of the back end.

Both i and ii are exemplified in example 2 and the front end code that performs the transformations described in i and ii can be found in functions smcTopFlattenExpr and smcVpFlattenExpr with the function smcVPProcessAssignment representing the general environment in which this transformation is performed.

The exact choice made by the preferred embodiment with respect to the values to be written in the descriptors of the temporary registers are only for the purpose of giving a complete description and other choices can be also acceptable and useful.

FE5 for each assignment encountered where the lhs is a vp data the appropriate conversion function is inserted if necessary on the rhs 

 i if the rhs is Verilog register its content is considered an integer value no conversion function is inserted and the arguments SizeOfInt SizeOfDec mentioned in FE3 are set accordingly 

 ii if the rhs is a Verilog real the conversion function fstVpF12Vp is inserted and the appropriate arguments are passed to it iii if the rhs is a vp data then the fstVpCopy is inserted and the appropriate arguments are passed to it. Both ii and iii are exemplified in example 1 and the code performing this transformation is shown in the front end function called smcVPProcessAssignment.

FE6 for each assignment encountered where the lhs is a Verilog real if the rhs is a vp data the conversion function fstVp2FI is inserted and the appropriate arguments are provided to the conversion. If the rhs is not a vp data no conversion function needs to be inserted since literals are converted by the front end into the appropriate format. The function fstVp2FI can be found in the back end. It converts the value of any vp data object into a double which is the format supported for the Verilog type real in this particular implementation of Verilog. Other formats for the Verilog type real are possible and a different choice would just lead to minor modifications of the function fstVp2FI.

FE7 each assignment statement is accompanied by the setting of the implicit registers associated to the left hand side of the assignment be it user defined vp data object or temporary register. This is done by passing as input arguments of the evaluation functions along with the obvious input data also the implicit input registers associated to the obvious input data. For example fstVpAdd will have as arguments not only ml and in2 the two vp data objects to be added and in3 the vp data object into which the result shall be placed but also 

 ii CummulativeError for each of ml and in2 and iii overflow underflow nrOfBitsLost cummulativeError and PeakNrOfBitsUsed for in3. Also when new values are assigned to implicit registers associated to vp data objects all processes that are sensitive to these implicit registers must be executed. There are many ways in which this can be implemented. In the present preferred embodiment the choice is made to compute the values of the implicit registers in some temporary variables and then assign these temporary values to the actual implicit registers via a standard mechanism in the simulator which will ensure that all processes sensitive to these implicit registers will be executed. Some implicit registers such as in l cummulativeError and in2 cummulativeError are inputs to fstVpAdd. Other implicit registers such as in3 overflow and in3 underflow are outputs of fstVpAdd. The implicit register in3 PeakNrOfBitsUSed is both an input and an output as it keeps the maximum number of bits used that was encountered throughout the simulation.

In order to support arithmetic operations between vp data objects having different formats and sizes the back end provides appropriate functions for each supported operator that first perform appropriate conversion bringing the operands to the same size and 20 format and then performs the operation using functions which are available outside the scope of this invention. There are several possible choices for finding a common format and sizes into which to transform both operands. In this preferred embodiment the choice was made to choose the format and sizes such that during the conversions and internal operation i.e. before performing the assignment of the internal value to the result the highest priority shall be given to not getting an overflow which would not have been obtained anyways second to not getting an underflow which would not have been obtained anyway then to getting a result which after rounding would be as close to the ideal result having infinite number of bits available as possible. Actual complete implementations of these functions are exemplified in the back end in functions fstVpAdd fstVpMult fstVpDiv. Note that fstVpSub is very similar to fstVpAdd and has therefore been omitted for the sake of clarity.

In order to support comparison operations between vp data objects having different formats and sizes the back end provides appropriate functions for each supported operator that first perform appropriate conversion bringing the operands to the same size and format and then performs the comparison operation using functions which are available outside the scope of this invention. There are several possible choices for finding a common format and sizes into which to transform both operands. In this preferred embodiment the choice was made to choose the format and sizes such that during the conversion made there should be no overflow or underflow. As a second priority the choice was made whenever possible to not to loose any bits of information of the value of the value to be converted. Actual complete implementations of these functions are exemplified in the back end in functions fstVpGE fstVpLE fstVpGT fstVpLT fstVpNE fstVpEQ.

The present invention has been described in accordance with the embodiments shown and one of ordinary skill in the art will readily recognize that there could be variations to the embodiments and any variations would be within the spirit and scope of the present invention. Accordingly many modifications may be made by one of ordinary skill in the art without departing from the spirit and scope of the appended claims.

