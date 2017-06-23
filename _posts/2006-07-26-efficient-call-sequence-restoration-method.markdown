---

title: Efficient call sequence restoration method
abstract: Embodiments of the present invention provide for minimizing the number of procedure frame unwinding operations to be performed when restoring the program control flow information. A first data structure may be constructed to contain procedure linkage information along with references to the conventional memory area where each procedure linkage information element (procedure return address or a procedure frame pointer) was originally found. The first data structure may be initialized upon the initial request for program control flow information. Upon each subsequent request, the contents of the conventional memory area as referenced by the first data structure may be compared with the corresponding elements of the first data structure. As a result of said comparison, changed and unchanged regions within the conventional memory area may be determined. Then, procedure frame unwinding operations may be performed for the changed regions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07926048&OS=07926048&RS=07926048
owner: Intel Corporation
number: 07926048
owner_city: Santa Clara
owner_country: US
publication_date: 20060726
---
This application is a National Phase application of and claims priority to International Application No. PCT RU2006 000400 filed Jul. 26 2006 entitled AN EFFICIENT CALL SEQUENCE RESTORATION METHOD.

A portion of the disclosure of this patent document contains material that is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

The present invention relates generally to the program performance monitoring and analysis domain and more specifically to low intrusive methods of program logic restoration such as constructing statistical control flow graphs and revealing information on procedure call sequences.

The ability to reconstruct program flow logic and correlate it with performance characteristics while employing low overhead statistical data collection methods is essential for modern performance monitoring systems. One of the most popular solutions is to build a statistical call graph to restore call sequences for each statistically determined performance hotspot in a program code.

Various techniques may be employed to restore call sequences some of them are precise and rely on information provided by compilers e.g. stack unwinding some are imprecise and employ a heuristic stack search for return addresses and instruction decoding but all of them are inappropriately intrusive and cannot be directly applicable to real time profiling of highly nested code.

The importance of real time profiling and hence the requirement of low intrusiveness can be explained by the inability to correlate performance characteristics with program states since information on the actual program states is absent at the post processing stage and the obtained performance results become distorted in case the monitoring system is too intrusive.

Therefore a need exists for the capability to enable real time control flow restoration by minimizing the number of stack unwinding operations or equivalent thereof and removing the dependency of stack unwinding methods on the number of nesting levels in any given program.

An embodiment of the present invention is a method that provides for efficient program control flow restoration by minimizing the number of procedure frame unwinding operations to be performed. The efficiency in control flow restoration may be achieved by mapping the procedure linkage information to its original locations on the stack. By further checking for the differences between such mapping and the actual stack contents upon subsequent requests for control flow information the changed regions of the stack may be determined and the procedure frame unwinding operations may be performed over the changed regions only.

Any reference in the specification to stack procedure stack frame or frame pointer should not be construed in a limiting sense with regard to computer architectures that have no explicit support for stack memory and stack manipulation instructions since the terms in question relate more to software convention rather than a particular computer system implementation and denote a memory area to contain procedure linkage information procedure local execution context and a reference to the local execution context respectively. A reference to the above terms should be interpreted as referring to any type of memory being static or dynamic random access memory register files or similar logic that is conventionally used to store procedure linkage information and procedure local execution contexts.

Reference in the specification to one embodiment or an embodiment of the present invention means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention. Thus the appearances of the phrase in one embodiment appearing in various places throughout the specification are not necessarily all referring to the same embodiment.

The following definitions may be useful for understanding embodiments of the present invention described herein.

A Statistical Call Graph is a partial program control flow graph reconstructed for statistically discernible code elements e.g. functions with performance information assigned to each node it is typically implemented as a combination of time or event based sampling and call sequence restoration upon each sample.

Call Sequence Restoration is a process of determination of the actual sequence of function calls that led to any given code element address function it is typically implemented as stack unwinding.

A Stack for purposes of the present specification is a conventional memory area dedicated to contain procedure linkage information.

Procedure linkage information PLI is a partial execution context necessary to establish correct execution transfer between nested procedures the PLI includes at least a procedure return link address it may also include a frame pointer that provides information on the correct stack frame size allocated for the procedure .

A Procedure Stack Frame is a stack area allocated for each function to store function local execution context preserved execution context of upper level functions a procedure return link address and input parameters.

Stack Frame or Procedure Frame Unwinding is a process of restoring a function s local execution context interpreting its contents determining the size of the function s stack frame and locating the return link address to the function s caller. The process may be repeated for each function along the call chain.

It has to be noted here that the presence of a common part in program execution paths is typical for most software applications since 90 of the work in an efficient program is usually performed at the same nesting level. Otherwise in case too much work is distributed over different nesting levels the efficiency of the program diminishes as a greater part of computational resources is spent on procedure invocation rather than on useful computations. Besides almost every program built using modern compiler and linker environments has a common unchanging part comprising nested runtime functions.

Embodiments of the present invention may prove efficient for profiling any program the actual efficiency level depending on the size of the common part in a sequence of nested functions.

The reference to a location of a procedure linkage information element should unambiguously identify the location and may comprise an offset to a stack base or a stack pointer or as depicted in a memory address within the stack limits.

Once map is formed it may be used as a reference map previous map while processing a subsequent request for program control flow restoration. The reference map may then be compared with the contents of a new stack frame block elements of map may be respectively compared with the contents of the stack frame at the address associated with each element. The difference between any element of map and the stack contents at the corresponding stack location indicates invocation of a different procedure and consequently a different call sequence. The unchanged stack regions do not necessarily imply there has been no change to the regions since the last sample point in fact there is no difference with respect to program control flow restoration if the actual changes occurred as long as the sequence of calls identical to one from the previous sample point is restored.

The borders of changed regions may be determined as follows the lower border of a changed region may be set to the value of the stack reference from the preceding unchanged element of the map. The higher border of the changed region may be set to the stack reference from the next unchanged element of the map.

Once the changed and unchanged regions of the stack are determined the actual stack unwinding or equivalent means to determine procedure linkage information may be applied to the lowest changed region first. Then an additional check of whether the newly unwound procedure frames intersect the unchanged regions may be performed.

In case of intersection the adjacent unchanged region may be marked as changed and concatenated with an upper adjacent changed region if any . The unwinding operation may be performed upon such a combined formerly unchanged region in accordance with the above specification.

The procedure linkage information collected for all changed regions may then be stored in map along with references to corresponding stack locations and portions of map describing unchanged regions may be copied to map so that the latter describes the entire stack and may be used as the reference map upon further requests for program control flow restoration.

The process of determining changed regions may be extended if imprecise procedure frame unwinding algorithms are employed heuristic return address search for instance which does not guarantee the collected procedure linkage information to be correct and correspond to actual procedure invocations . In this case each unchanged region may be assigned a confidence level. The confidence level should indicate the probability of error in the determination of unchanged regions.

For example lower deeper nested unchanged regions may be considered of less confidence than upper regions or an unchanged region surrounded by changed regions may be viewed to be of the least confidence.

A confidence threshold may be established to leverage the precision computational complexity ratio and either minimize the number of unwinding operations to be performed or increase the precision by double checking the presumably unchanged regions.

At block a procedure frame may be unwound or an equivalent operation to determine procedure linkage information may be employed.

The current PLI map may be updated with a new procedure linkage information element and a reference to the corresponding stack location at block .

The check whether the obtained PLI element is located within the current changed region being analyzed may be performed at block . If the PLI element is still within the current stack region the control may be transferred to block and the procedure frame unwinding may be continued.

Otherwise the list of changed and unchanged regions may be updated at block in case the last PLI element was obtained beyond the current stack region s boundary only applicable to precise procedure frame unwinding methods .

Then in case there are more changed regions left as checked at block the control may be transferred to block for the selection of the next changed region to process.

After all changed regions have been processed the current PLI map may be combined with the portions of the previous PLI map describing unchanged stack regions at block .

Finally the current PLI map may be substituted for the previous map at block to be used as a reference map upon a next request for program control flow restoration.

One skilled in the art will recognize that the invention described herein does not depend on any particular method employed to unwind the stack or determine procedure linkage information. Embodiments of the present invention may rather be used to raise the efficiency of such a method and minimize the number of operations it would otherwise require to restore information on program control flow. Thus a method wherein procedure linkage information is gathered as a result of specific compiler support adherence to a software convention or automatically reported by the processor or dedicated logic may be combined with the present invention to constitute an efficient profiling system.

For a C language example of an embodiment of the present invention refer to Appendix A. The goal of this code is to illustrate how the number of stack unwinding operations can be minimized by means of mapping pre unwound procedure return addresses to their original stack locations and checking the actual stack contents against the mapped values upon each subsequent request for call sequence restoration. One skilled in the art will recognize the option of implementing different mapping algorithms without deviating from the scope of the present invention as long as such algorithms establish unambiguous correspondence between procedure linkage information and its stack locations and provide for detection of changes to the stack in accordance with the method introduced by the present invention.

Furthermore one skilled in the art will recognize that embodiments of the present invention may be implemented in other ways and using other programming languages.

The techniques described herein are not limited to any particular hardware or software configuration they may find applicability in any computing or processing environment. The techniques may be implemented in logic embodied in hardware software or firmware components or a combination of the above. The techniques may be implemented in programs executing on programmable machines such as mobile or stationary computers personal digital assistants set top boxes cellular telephones and pagers and other electronic devices that each include a processor a storage medium readable by the processor including volatile and non volatile memory and or storage elements at least one input device and one or more output devices. Program code is applied to the data entered using the input device to perform the functions described and to generate output information. The output information may be applied to one or more output devices. One of ordinary skill in the art may appreciate that the invention can be practiced with various computer system configurations including multiprocessor systems minicomputers mainframe computers and the like. The invention can also be practiced in distributed computing environments where tasks may be performed by remote processing devices that are linked through a communications network.

Each program may be implemented in a high level procedural or object oriented programming language to communicate with a processing system. However programs may be implemented in assembly or machine language if desired. In any case the language may be compiled or interpreted.

Program instructions may be used to cause a general purpose or special purpose processing system that is programmed with the instructions to perform the operations described herein. Alternatively the operations may be performed by specific hardware components that contain hardwired logic for performing the operations or by any combination of programmed computer components and custom hardware components. The methods described herein may be provided as a computer program product that may include a machine readable medium having stored thereon instructions that may be used to program a processing system or other electronic device to perform the methods. The term machine readable medium used herein shall include any medium that is capable of storing or encoding a sequence of instructions for execution by the machine and that cause the machine to perform any one of the methods described herein. The term machine readable medium shall accordingly include but not be limited to solid state memories optical and magnetic disks and a carrier wave that encodes a data signal. Furthermore it is common in the art to speak of software in one form or another e.g. program procedure process application module logic and so on as taking an action or causing a result. Such expressions are merely a shorthand way of stating the execution of the software by a processing system to cause the processor to perform an action or produce a result.

While this invention has been described with reference to illustrative embodiments this description is not intended to be construed in a limiting sense. Various modifications of the illustrative embodiments as well as other embodiments of the invention which are apparent to persons skilled in the art to which the invention pertains are deemed to lie within the spirit and scope of the invention.

The present example shows a possible implementation of the algorithm that minimizes the number of procedure frame unwinding operations. The code sample is provided for illustrative purposes only and does not constitute a complete solution for a program logic restoration system. The furnished sample may have dependencies on third party stack unwinding interfaces which may impose extra restrictions on the compilation process.

The goal of the code is to maintain a map of procedure return addresses and upon each request for procedure call chain restoration compare the actual stack data with the contents of the map. As the result of the comparison the stack is divided into the changed and unchanged regions. The stack unwinding procedure is performed for the changed region first then the position of the last procedure return address in the stack is compared with the region border. If the return address is obtained from a location beyond the changed region the unchanged region is assumed to be changed and the unwinding procedure is repeated until the end of stack is reached.

A new map of procedure return addresses is constructed by concatenating information of the newly unwound procedure frames and the contents of the previous map portion that correspond to the unchanged stack region.

