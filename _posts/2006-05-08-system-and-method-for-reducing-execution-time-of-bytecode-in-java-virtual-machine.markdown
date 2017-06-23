---

title: System and method for reducing execution time of bytecode in java virtual machine
abstract: A system and method for reducing the bytecode execution time in the Java virtual machine are disclosed. The system includes a DB cache to store old machine code converted from a bytecode, a machine code change unit to change the old machine code to new machine code by removing a predetermined instruction included therein, a register management unit to manage stack data necessary for operations of the new machine code and a register file to provide a register region to conduct the operations, and a machine code information storage unit to store basic block information on the new machine code and spill and fill execution information in the stack of the register file.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08561042&OS=08561042&RS=08561042
owner: Samsung Electronics Co., Ltd.
number: 08561042
owner_city: Suwon-Si
owner_country: KR
publication_date: 20060508
---
This application claims priority from Korean Patent Application No. 10 2005 0042082 filed on May 19 2005 in the Korean Intellectual Property Office the disclosure of which is incorporated herein in its entirety by reference.

Systems and methods consistent with the present invention relate to reduction of the execution time of bytecode in a Java virtual machine JVM . More particularly the present invention relates to a system and a method for reducing the bytecode execution time in the JVM whereby the entire bytecode execution time can be reduced by keeping the number of accesses of a stack memory to a minimum when carrying out machine code operations.

Java is an object oriented programming language which has become the de facto standard in network programming. These days Java is used in embedded systems and in systems including a microprocessor or a microcontroller. Characteristics of Java environments include object orientation automatic garbage collection and runtime security and a part thereof can be successfully used in embedded applications.

However the performance of the runtime environment has been poor because of the resource overhead required to execute Java code in the virtual machine of an interpreter or a just in time JIT compiler.

Java binary code called bytecode is distributed in one or more class files. Bytecode is instructions of a hypothetical computer that was specially designed for the execution of Java programs.

Since the conventional CPU cannot execute bytecode the bytecode is executed in a software layer called the Java virtual machine JVM . The JVM is an abstract machine specification that was published by Sun Microsystems Inc.

Execution of a Java program will now be described. A Java program which has the .java extension is compiled by a compiler and converted into a java executable file having the .class extension. The class file is interpreted by an interpreter and is executed. Interpreting is done in three stages class loading to load all the classes necessary for execution of the program verification to check the formats of the class files licenses to access and format changes of data and actual execution of the program.

The hierarchical structure of Java comprises a Java program written in the Java language the Java platform including the JVM and the Java application programming interface API and a hardware dependent platform. Under this structure a Java executable file is composed of bytecode which is platform independent and thus it can run on any platform that has the Java runtime environment JRE independent of the hardware of the system.

Java technology has a number of advantages including platform independence that is secure Write Once Run Anywhere WORA capability and dynamic extensibility and therefore it is used in a variety of fields. Most web servers are based on Java technology since it has been actively used as a server technology for web services. Java technology is also being employed in embedded devices as an environment to provide user services or execute control applications.

As illustrated machine code having a start address op A of a basic block executes an instruction to transfer data stored in the 4 position to a register r at the current local point lp and executes an instruction to store the data stored in the register r in the 4 position at the current position of the stack pointer sp and then changes the address of the stack pointer to the address by 4.

Machine code having op A of the basic block address executes an instruction to transfer data stored in the 8 position to a register at the current local point and executes an instruction to store the data stored in register in the 4 position of the stack pointer and then changes the address of the stack pointer by 4.

Machine code having the basic block address of op A executes an instruction to transfer data stored in the 4 position to a register r at the current stack point and conducts an instruction to transfer the data stored in the 4 position to the register at the current stack point A . In addition it executes an instruction to add the values in register and register and store the result in register B and executes an instruction to store data stored in the register at the current position of the stack pointer 4 and then changes the address of the stack pointer by 4 position C .

Three types of machine instructions are present in the machine code a pop A a push C and a core instruction B . The pop instruction is to transfer data in an upper part of the stack to a register the push instruction is to transfer data stored in the register to the stack and the core instruction refers to all the other instructions. In the basic block the instructions are in the sequence of pop push and core. The pop instruction uses successive registers in descending order i.e. Reg k Reg  k 1 . . . Reg . The push instruction uses successive registers in ascending order i.e. Reg  . . . Reg p. The core instructions use the same registers that the pop and push instructions use.

The machine code having the basic block address of op A executes an instruction to transfer data stored at the current position of the stack pointer 4 to register and executes an instruction to store the data stored in register at the current position of the stack pointer 12.

Accordingly in order to execute blocks A to A ten instructions to load store from to the stack six times and an instruction to load store from the the local point three times must be executed.

To reduce memory accesses in the Java environment bytecode folding database DB cache and stack registers have been used.

Bytecode folding refers to a method that patterns in advance three or four successive instructions that are frequently used when executing the bytecode and when these patterns are detected optimized machine code corresponding to the whole pattern is executed in lieu of executing every instruction. According to bytecode folding an operation result belonging to a pattern is stored in a register and it can be directly utilized when another instruction belonging to the same pattern uses it thereby being capable of reducing the number of stack accesses.

Typical operations of bytecode folding will now be described. Among bytecode to be executed three or four successive instructions are searched and it is checked whether they are identical to the limited number of predetermined patterns. When identical patterns are searched for provided machine code is executed in lieu of executing the instructions and the positions of the instructions are changed. However if the instructions to be executed are not identical to the predetermined patterns each instruction is executed.

The bytecode folding may produce an improvement in performance because fewer instructions have to be executed and the number of memory accesses is reduced. However only predetermined patterns can be applied and thus the application scope is limited. Also it is very effective in an application having bytecode use patterns that cannot be processed in a folding unit.

A DB cache is embodied within the Pico Java processor. A DB cache is a kind of instruction cache and is a region to store bytecode to be executed in the pipeline stage and machine code generated as a result of bytecode folding both of which are input by the folding unit. The DB cache can reduce memory accesses as it acts as an instruction cache and in particular further folding may not be executed when the already folded bytecode is stored thereby being capable of further improving the performance

Operations of the DB cache will now be described. In a fetch stage it is checked whether a corresponding instruction address is present in the DB cache. As a result if no corresponding address is present the process proceeds to the general pipeline execution and at the same time the bytecode is sent to an instruction folding unit.

Then the instructions folding unit executes bytecode folding and sends the folding result or the instruction to the DB cache so it can be stored therein. If a corresponding instruction address is present in the patch stage an instruction selected from the DB cache is executed.

When the bytecode is fetched from the DB cache in this way memory accesses are reduced. When the folded machine code is fetched memory accesses are reduced and the folding time is shortened.

The DB cache stores the bytecode and the machine code as the folding result in an additional cache in order to reduce memory accesses and make further folding operations unnecessary. However the process still retains the disadvantages described above.

A stack register realizes a stack by combining a round shaped register and a memory with the limited number for a stack machine such as Java. In order to allow an execution unit to access the register when it needs to use the stack the top region of the stack is filled and used in the register. When the register becomes filled the bottom portion of the stack which has been scarcely used is dumped into the memory.

Typical operations of the stack register will now be described. The execution unit requests pop and push operations on the stack.

In case of a push operation a value is added to the register. In case of a pop operation a value is removed from the register thereby creating an empty space in the register.

When the entire top of the stack is allocated by successive pushes the bottom portion of the stack is not dumped into the memory whereas the content dumped to the memory is transferred to the register when the top space of the stack is empty due to successive pops.

However the stack register composes a stack using limited registers and memory and it is assured that the execution unit can always use the registers but not the memory thereby improving push and pop performance. However it cannot remove push and pop instructions for an ineffective stack already present in the code.

Accordingly the present invention has been proposed to solve the problems described above. An object of the present invention is to minimize accesses to a stack memory and reduce bytecode execution time by storing the upper portion of the stack memory required for carrying out operations of a machine code in a stack register and securing the register regions to conduct the operations.

Another object of the present invention is to provide a new machine code from which top type and push type instructions are removed by storing stack data in the stack register.

The present invention shall not be limited to the objects described above. Any other objects not described herein shall be clearly understood by those skilled in the art from the descriptions stated below.

According to an aspect of the present invention there is provided a system for reducing the bytecode execution time in the JVM the system comprising a DB cache to store a plurality of machine code converted from a bytecode a machine code change unit to change the machine code to new machine code by removing a predetermined instruction included therein a register management unit to manage stack data necessary for operations of the machine code and a register file to provide a register region to conduct the operations and a machine code information storage unit to store basic block information on the machine code and spill and fill execution information in the stack of the register file.

According to another aspect of the present invention there is provided a method of reducing the bytecode execution time in the Java virtual machine the method comprising converting bytecode into machine code and storing the bytecode providing a register file that secures stack data necessary for conducting operations of the machine code and a register to conduct the operations changing the machine code into new machine code by removing a predetermined instruction from the machine code and conducting operations of the changed machine code.

Hereinafter exemplary embodiments of the present invention will be described in detail with reference to the accompanying drawings.

Aspects of the present invention and methods of accomplishing the same may be understood more readily by reference to the following detailed description of exemplary embodiments and the accompanying drawings. The present invention may however be embodied in many different forms and should not be construed as being limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the concept of the invention to those skilled in the art and the present invention will only be defined by the appended claims. Like reference numerals refer to like elements throughout the specification.

As illustrated the system comprises a memory an instruction buffer a bytecode conversion unit a DB cache a machine code change unit a machine code information storage unit a register management unit and a register file . It should be noted that devices that can include the Java virtual machine include wired and wireless terminals home appliances embedded devices and others.

The memory stores a stack region i.e. stack memory that is used in the Java virtual machine and predetermined instructions.

The instruction buffer temporarily stores instructions e.g. bytecode fetched from the memory . When an instruction to be executed is not stored in the DB cache the instruction buffer fetches it from the memory . At this time the instruction buffer also fetches the next instruction to be executed from the memory and stores it.

When the instruction fetched by the instruction buffer is bytecode the bytecode conversion unit converts the instruction into machine code. Here a single bytecode is converted into a plurality of machine code. The bytecode conversion unit also analyzes the bytecode. When the converted machine codes constitute a start address and an end address of a basic block the bytecode conversion unit sends the address of a concerned machine code to the machine code information storage unit .

When a machine code to carry out operations stored in the DB cache corresponds to the start address of the basic block the machine code change unit changes the machine code included in the basic block to new machine code. That is original machine code to carry out operations is changed to new machine code to reduce read write instructions on the stack.

Change of machine code is executed on a basic block address basis. To change the machine code the register file should satisfy a condition for changing the machine code. As the machine code change condition a register to carry out operations and stack data required for the operations must be present in the register file . The register management unit executes spill or fill at the time of carrying out operations in order that the register file satisfies the machine code change condition.

The machine code change unit checks the status of the register file i.e. the machine code change condition before changing the machine code and sends information as to whether to execute spill or fill to the machine code information storage unit in order to satisfy the machine code change condition. Based on the information stored in the machine code information storage unit e.g. information as to whether to execute spill or fill the register management unit executes spill or fill.

The machine code information storage unit stores information on the basic block start address and end address for machine code converted by the bytecode conversion unit and information as to whether to execute spill or fill of the register file sent from the machine code change unit . When the stack information e.g. Stack Top ST Stack Bottom SB and Stack Height SH is changed due to a change in the stack the machine code information storage unit also stores the new stack information. The ST refers to a pointer to a register where the top of the stack is stored the SB refers to a pointer to a register where the bottom of the stack is stored and the SH refers to the number of registers used as stack registers. The machine code information storage unit stores in a table form information on machine code to carry out operations. The information table will be described in detail with reference to .

The register file temporarily stores data in which information sufficiently lengthy to carry out arithmetic logic operations information interpretation and transmission and others are stored. For example the stack register to store the top of the stack memory is included in the register file . In the exemplary embodiment of the present invention the stack data stored in the stack register is spilled to the memory in order for the register file to satisfy the machine code change condition or the stack data stored in the memory is filled. The stack register of the register file will be described in detail with reference to .

The register management unit manages the stack register of the register file . That is spill or fill of the stack register is executed in order to make it possible to change the machine code. Spill or fill execution information needed by the stack register is stored in the machine code information storage unit .

When there is no register in the stack register to execute operations i.e. a push when the machine code information change unit intends to change predetermined machine code a predetermined amount of stack data stored in the stack register is sent to the stack memory i.e. a spill to thereby create a register region to execute the operations. When stack data used in operations is not present in the stack register i.e. a pop concerned stack data may be filled from the stack memory .

The register management unit stores stack information e.g. the ST SB and SH to manage the stack register . The stack information is changed by executing spill and fill for the stack register and the stack management unit stores and manages the new stack information.

As illustrated the information table stores machine code addresses basic block first BBF addresses basic block end BBE addresses the number of necessary registers information on whether to spill or fill and new stack information .

For example machine code having an address of 0 3400 has the basic block first address and one register. To carry out operations in the stack register a spill must be executed. As a result of the spill it can be seen that there is no change in the stack.

Accordingly based on the information stored in the machine code storage unit the register management unit decides to conduct a spill and fill for the stack register . When the stack register meets the machine code change condition the machine code change unit conducts code change directed to the original machine code.

As illustrated a plurality of stack data is stored in the stack memory and five sets of data are registered in the stack register . The stack register has a circular shape and the ST and SB are indicated.

If the register management unit executes a fill based on the information stored in the machine code information storage unit the stack data at the top of the stack memory is spilled and then filled in the bottom portion of the stack register in order to store the stack data necessary for operations in the stack register .

When the register management unit executes the fill by 3 the SB position is moved to R from R and data values of 4 5 and 6 are filled in R to R from the stack.

When the register management unit executes the spill based on the information stored in the machine code information storage unit a predetermined amount of stack data is spilled to the stack memory in order to form a register region to carry out operations. Accordingly the register region to carry out operations is secured in the stack register and the pointer value of the SB decreases by the number sets of stack data spilled to the stack memory .

As illustrated the machine code having the basic block start address op A performs an instruction to spill the data stored at the current position of the stack pointer 4 to register .

The machine code having the basic block address of op A performs an instruction to spill the data stored at position to the register .

The machine code having the basic block address of op A performs an instruction to spill the result of carrying out operations for register and register to register .

The machine code having the basic block address of op A conducts instructions to fill the data stored at the position 12 in register .

Since the new machine code does not conduct pop instructions and push instructions a smaller number of instructions than those for conducting operations of the conventional machine code are carried out. Accordingly in order to conduct the instructions in blocks A to A it is sufficient to conduct an instruction to load store three times.

When the top of the stack is allocated to the stack register unnecessary instructions are removed thereby reducing stack accesses as much as possible.

As illustrated when an instruction fetched from the memory is bytecode the bytecode conversion unit converts the concerned bytecode into the original machine code in operation S and stores the machine code in the DB cache .

Then the machine code change unit determines whether the original machine code to conduct an instruction stored in the DB cache corresponds to the basic block start address in operation S. As a result of the determination the original machine code to be conducted is the basic block start address and the stack information on the concerned original machine code ST SB and SH and basic block information start address and end address are stored in the machine code information storage unit in operation S.

The register management unit checks the status of the stack register based on the information on the machine code stored in the machine code information storage unit in operation S. It should be noted that the status of the stack register may refer to the pop instructions to spill data stored in the stack register to the stack memory or the push instructions to fill data stored in the stack memory in the stack register .

As a result of checking the status of the stack register since the status of the stack register is the push instructions that is the stack data necessary for operations is not included in the stack register the register management unit fills the stack data in the stack memory into the stack register in operation S.

Then the machine code change unit changes the original machine code to new machine code that can conduct operations using the stack data stored in the stack register without accessing the stack memory in operation S.

When the code change up to the basic block end address is completed the machine code conversion is finished in operation S. When the code change up to the basic block end address of the machine code is not completed operations S and S are continuously conducted until the code is completed.

Accordingly the top of the stack is allocated to the stack register thereby forming a register region to carry out operations and the total bytecode execution time can be reduced by reducing stack accesses.

As described above the system and the method for reducing the bytecode execution time in the Java virtual machine according to the exemplary embodiments of the present invention may produce one or more of the effects described below.

First the top portion of the stack which is necessary for conducting machine code operations is stored in the stack register to thereby secure a register region to conduct operations whereby the entire bytecode execution time is reduced owing to minimized stack accesses.

Second by storing the stack data in the stack register the entire bytecode execution time can be reduced by providing new machine code from which pop and push instructions have been removed.

Exemplary embodiments of the present invention have been described with respect to the accompanying drawings. However it should be understood by those of ordinary skill in the art that various replacements modifications and changes in the form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims. Therefore it is to be appreciated that the above described exemplary embodiments are for purposes of illustration only and are not to be construed as a limitation of the invention.

