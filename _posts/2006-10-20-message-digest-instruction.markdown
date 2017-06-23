---

title: Message digest instruction
abstract: A method, system and computer program product for digesting data in storage of a computing environment. The digesting computes a condensed representation of a message or data stored in the computer storage. A COMPUTE INTERMEDIATE MESSAGE DIGEST (KIMD) and a COMPUTE LAST MESSAGE DIGEST (KLMD) instruction are disclosed which specify a unit of storage to be digested by a secure hashing algorithm.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07725736&OS=07725736&RS=07725736
owner: International Business Machines Corporation
number: 07725736
owner_city: Armonk
owner_country: US
publication_date: 20061020
---
This is a divisional application of Ser. No. 10 436 230 MESSAGE DIGEST INSTRUCTIONS filed on May 12 2003 now U.S. Pat. No. 7 159 122 and assigned to IBM. The disclosure of the forgoing application is incorporated herein by reference.

This invention relates to computer system architecture and particularly to new instructions which augment the IBM z Architecture and can be emulated by other architectures.

Before our invention IBM has created through the work of many highly talented engineers beginning with machines known as the IBM System 360 in the 1960s to the present a special architecture which because of its essential nature to a computing system became known as the mainframe whose principles of operation state the architecture of the machine by describing the machine instructions which may be executed upon the mainframe implementation of the machine instructions which had been invented by IBM inventors and adopted because of their significant contribution to improving the state of the computing machine represented by the mainframe as significant contributions by inclusion in IBM s Principles of Operation as stated over the years. The First Edition of the which was published December 2000 has become the standard published reference as SA22 7832 00. We determined that further new instructions would assist the art and could be included in a z Architecture machine and also emulated by others in simpler machines as described herein.

We determined that further new instructions would assist the art and could be included in a z Architecture machine and also emulated by others in simpler machines as described herein.

It is a primary object of the present invention to disclose CPU synchronous problem state and sectioning instructions which digest data in computer storage wherein the instructions compute a condensed representation of messages or data.

It is another object of the invention to disclose instructions which specify a unit of storage to be digested and wherein a secure hashing algorithm digests the data in the specified unit of storage.

It is another object of the invention to disclose a COMPUTE INTERMEDIATE MESSAGE DIGEST instruction and a COMPUTE LAST MESSAGE DIGEST instruction.

It is a further object of the invention to disclose a digest instruction wherein complete blocks of data are processed and after processing all complete blocks a padding operation is performed to include the remaining portion of the specified storage.

It is another object of the invention to emulate the digest instruction in a computer architecture which is different than the computer architecture of the instruction.

The message digest instructions discussed herein are for computing a condensed representation of a message or data file. The compute intermediate message digest and the compute last message digest instructions will first be discussed followed by a discussion of the preferred computer system for executing these instructions. In the alternative a second preferred computer system which emulates another computer system for executing these instructions will be discussed.

Bit positions of general register contain the function code. show the assigned function codes for COMPUTE INTERMEDIATE MESSAGE DIGEST AND COMPUTE LAST MESSAGE DIGEST respectively. All other function codes are unassigned. Bit of general register must be zero otherwise a specification exception is recognized. All other bits of general register are ignored. General register contains the logical address of the leftmost byte of the parameter block in storage. In the 24 bit addressing mode the contents of bit positions of general register constitute the address and the contents of bit positions are ignored. In the 31 bit addressing mode the contents of bit positions of general register constitute the address and the contents of bit positions are ignored. In the 64 bit addressing mode the contents of bit positions of general register constitute the address.

The query function provides the means of indicating the availability of the other functions. The contents of general registers R and R 1 are ignored for the query function.

For all other functions the second operand is processed as specified by the function code using an initial chaining value in the parameter block and the result replaces the chaining value. For COMPUTE LAST MESSAGE DIGEST the operation also uses a message bit length in the parameter block. The operation proceeds until the end of the second operand location is reached or a CPU determined number of bytes have been processed whichever occurs first. The result is indicated in the condition code.

The R field designates an even odd pair of general registers and must designate an even numbered register otherwise a specification exception is recognized.

The location of the leftmost byte of the second operand is specified in the contents of the R general register. The number of bytes in the second operand location is specified in general register R 1.

As part of the operation the address in general register R is incremented by the number of bytes processed from the second operand and the length in general register R 1 is decremented by the same number. The formation and updating of the address and length is dependent on the addressing mode.

In the 24 bit addressing mode the contents of bit positions of general register R constitute the address of second operand and the contents of bit positions are ignored bits of the updates address replace the corresponding bits in general register R carries out of bit position of the updated address are ignored and the contents of bit positions of general register R are set to zeros. In the 31 bit addressing mode the contents of bit positions of general register R constitute the address of second operand and the contents of bit positions are ignored bits of the updated address replace the corresponding bits in general register R carries out of bit position of the updated address are ignored and the content of bit position of general register R is set to zero. In the 64 bit addressing mode the contents of bit positions of general register R constitute the address of second operand bits of the updated address replace the contents of general register R and carries out of bit position are ignored.

In both the 24 bit and the 31 bit addressing modes the contents of bit positions of general register R 1 form a 32 bit unsigned binary integer which specifies the number of bytes in the second operand and the updated value replaces the contents of bit positions of general register R 1. In the 64 bit addressing mode the contents of bit positions of general register R 1 form a 64 bit unsigned binary integer which specifies the number of bytes in the second operand and the updated value replaces the contents of general register R 1.

In the 24 bit or 31 bit addressing mode the contents of bit positions of general registers R and R 1 always remain unchanged.

In the access register mode access registers and R specify the address spaces containing the parameter block and second operand respectively.

The result is obtained as if processing starts at the left end of the second operand and proceeds to the right block by block. The operation is ended when all source bytes in the second operand have been processed called normal completion or when a CPU determined number of blocks that is less than the length of the second operand have been processed called partial completion . The CPU determined number of blocks depends on the model and may be a different number each time the instruction is executed. The CPU determined number of blocks is usually nonzero. In certain unusual situations this number may be zero and condition code 3 may be set with no progress. However the CPU protects against endless reoccurrence of this no progress case.

When the chaining value field overlaps any portion of the second operand the result in the chaining value field is unpredictable.

For COMPUTE INTERMEDIATE MESSAGE DIGEST normal completion occurs when the number of bytes in the second operand as specified in general register R 1 have been processed. For COMPUTE LAST MESSAGE DIGEST after all bytes in the second operand as specified in general register R 1 have been processed the padding operation is performed and then normal completion occurs.

When the operation ends due to normal completion condition code 0 is set and the resulting value in R 1 is zero. When the operation ends due to partial completion condition code 3 is set and the resulting value in R 1 is nonzero.

When the second operand length is initially zero the second operand is not accessed general registers R and R 1 are not changed and condition code 0 is set. For COMPUTE INTERMEDIATE MESSAGE DIGEST the parameter block is not accessed. However for COMPUTE LAST MESSAGE DIGEST the empty block L 0 case padding operation is performed and the result is stored into the parameter block.

As observed by other CPUs and channel programs references to the parameter block and storage operands may be multiple access references accesses to these storage locations are not necessarily block concurrent and the sequence of these accesses or references is undefined.

Access exceptions may be reported for a larger portion of the second operand than is processed in a single execution of the instruction however access exceptions are not recognized for locations beyond the length of the second operand nor for locations more than 4K bytes beyond the current location being processed.

The symbols of are used in the subsequent description of the COMPUTE INTERMEDIATE MESSAGE DIGEST and COMPUTE LAST MESSAGE DIGEST functions. Further description of the secure hash algorithm may be found in Federal Information Processing Standards publication 180 1 National Institute of Standards and Technology Washington D.C. Apr. 17 1995.

A 128 bit status word is stored in the parameter block. Bits of this field correspond to function codes respectively of the COMPUTE INTERMEDIATE MESSAGE DIGEST instruction. When a bit is one the corresponding function is installed otherwise the function is not installed.

Condition code 0 is set when execution of the KIMD Query function completes condition code 3 is not applicable to this function.

A 20 byte intermediate message digest is generated for the 64 byte message blocks in operand using the SHA 1 block digest algorithm with the 20 byte chaining value in the parameter block. The generated intermediate message digest also called the output chaining value OCV is stored in the chaining value field of the parameter block. The KIMD SHA 1 operation is shown in .

A 128 bit status word is stored in the parameter block. Bits of this field correspond to function codes respectively of the COMPUTE LAST MESSAGE DIGEST instruction. When a bit is one the corresponding function is installed otherwise the function is not installed.

Condition code 0 is set when execution of the KLMD Query function completes condition code 3 is not applicable to this function.

The message digest for the message M in operand is generated using the SHA 1 algorithm with the chaining value and message bit length information in the parameter block.

If the length of the message in operand is equal to or greater than 64 bytes an intermediate message digest is generated for each 64 byte message block using the SHA 1 block digest algorithm with the 20 byte chaining value in the parameter block and the generated intermediate message digest also called the output chaining value OCV is stored into the chaining value field of the parameter block. This operation is shown in and repeats until the remaining message is less than 64 bytes. If the length of the message or the remaining message is zero bytes then the operation in is performed.

If the length of the message or the remaining message is between one byte and 55 bytes inclusive then the operation in is performed if the length is between 56 bytes and 63 bytes inclusive then the operation in is performed The message digest also called the output chaining value OCV is stored in to the chaining value field of the parameter block.

The following additional symbols are used in the description of the COMPUTE LAST MESSAGE DIGEST functions.

2. When condition code 3 is set the second operand address and length in general registers R and R 1 respectively and the chaining value in the parameter block are usually updated such that the program can simply branch back to the instruction to continue the operation.

For unusual situations the CPU protects against endless reoccurrence for the no progress case. Thus the program can safely branch back to the instruction whenever condition code 3 is set with no exposure to an endless loop.

3. If the length of the second operand is nonzero initially and condition code 0 is set the registers are updated in the same manner as for condition code 3 the chaining value in this case is such that additional operands can be processed as if they were part of the same chain.

4. The instructions COMPUTE INTERMEDIATE MESSAGE DIGEST and COMPUTE LAST MESSAGE DIGEST are designed to be used by a security service application programming interface API . These APIs provide the program with means to compute the digest of messages of almost unlimited size including those too large to fit in storage all at once. This is accomplished by permitting the program to pass the message to the API in parts. The following programming notes are described in terms of these APIs.

5. Before processing the first part of a message the program must set the initial values for the chaining value field. For SHA 1 the initial chaining values are listed as follows 

6. When processing message parts other than the last the program must process message parts in multiples of 512 bits 64 bytes and use the COMPUTE INTERMEDIATE MESSAGE DIGEST instruction.

7. When processing the last message part the program must compute the length of the original message in bits and place this 64 bit value in the message bit length field of the parameter block and use the COMPUTE LAST MESSAGE DIGEST instruction.

8. The COMPUTE LAST MESSAGE DIGEST instruction does not require the second operand to be a multiple of the block size. It first processes complete blocks and may set condition code 3 before processing all blocks. After processing all complete blocks it then performs the padding operation including the remaining portion of the second operand. This may require one or two iterations of the SHA 1 block digest algorithm.

9. The COMPUTE LAST MESSAGE DIGEST instruction provides the SHA 1 padding for messages that are a multiple of eight bits in length. If SHA 1 is to be applied to a bit string which is not a multiple of eight bits the program must perform the padding and use the COMPUTE INTERMEDIATE MESSAGE DIGEST instruction.

The preferred embodiment provides a crypto coprocessor which can be used with the instructions described herein and to execute cipher messages and assist in a variety of chaining message tasks which can be employed for chained and cryptographic use with the appropriate instructions.

The cryptographic control unit provides a cryptographic coprocessor directly attached to a data path common to all internal execution units of the central processing unit on a general purpose microprocessor providing the available hardware E. . . E or from a combination thereof in the preferred embodiment having multiple execution pipelines for the central processing unit. When a cryptographic instruction is encountered in the command register the control unit invokes the appropriate algorithm from the available hardware. Operand data is delivered over the same internal microprocessor bus via an input FIFO register . When an operation is completed the a flag is set in a status register and the results are available to be read out from the output FIFO register .

The illustrated preferred embodiment of our invention is designed to be extensible to include as many hardware engines as required by a particular implementation depending on the performance goals of the system. The data paths to the input and output registers are common among all engines.

The preferred embodiment of the invention cryptographic functions are implemented in execution unit hardware on the CPU and this implementation enables a lower latency for calling and executing encryption operations and increases the efficiency.

This decreased latency greatly enhances the capability of general purpose processors in systems that frequently do many encryption operations particularly when only small amounts of data are involved. This allows implementation that can significantly accelerate the processes involved in doing secure online transactions. The most common methods of securing online transactions involve a set of three algorithms. The first algorithm is only used one time in a session and may be implemented in hardware or software while the other operations are invoked with every transaction of the session and the cost in latency of calling external hardware as well as the cost in time to execute the algorithm in software are both eliminated with this invention.

In we have shown conceptually how to implement what we have in a preferred embodiment implemented in a mainframe computer having the microprocessor described above which can effectively be used as we have experimentally proven within IBM in a commercial implementation of the long displacement facility computer architected instruction format the instructions are used by programmers usually today C programmers. These instruction formats stored in the storage medium may be executed natively in a z Architecture IBM Server or alternatively in machines executing other architecture. They can be emulated in the existing and in future IBM mainframe servers and on other machines of IBM e.g. pSeries Servers and xSeries Servers . They can be executed in machines running Linux on a wide variety of machines using hardware manufactured by IBM Intel AMD Sun Microsystems and others. Besides execution on that hardware under a z Architecture Linux can be used as well as machines which use emulation by Hercules UMX FXI or Platform Solutions where generally execution is in an emulation mode. In emulation mode the specific instruction being emulated is decoded and a subroutine built to implement the individual instruction as in a C subroutine or driver or some other method of providing a driver for the specific hardware as is within the skill of those in the art after understanding the description of the preferred embodiment. Various software and hardware emulation patents including but not limited to U.S. Pat. No. 5 551 013 for a Multiprocessor for hardware emulation of Beausoleil et al. and U.S. Pat. No. 6 009 261 Preprocessing of stored target routines for emulating incompatible instructions on a target processor of Scalzi et al and U.S. Pat. No. 5 574 873 Decoding guest instruction to directly access emulation routines that emulate the guest instructions of Davidian et al U.S. Pat. No. 6 308 255 Symmetrical multiprocessing bus and chipset used for coprocessor support allowing non native code to run in a system of Gorishek et al and U.S. Pat. No. 6 463 582 Dynamic optimizing object code translator for architecture emulation and dynamic optimizing object code translation method of Lethin et al and U.S. Pat. No. 5 790 825 Method for emulating guest instructions on a host computer through dynamic recompilation of host instructions of Eric Traut and many others illustrate the a variety of known ways to achieve emulation of an instruction format architected for a different machine for a target machine available to those skilled in the art as well as those commercial software techniques used by those referenced above.

As illustrated by these instructions are executed in hardware by a processor or by emulation of said instruction set by software executing on a computer having a different native instruction set.

In shows a computer memory storage containing instructions and data. The instructions described in this invention would initially stored in this computer. shows a mechanism for fetching instructions from a computer memory and may also contain local buffering of these instructions it has fetched. Then the raw instructions are transferred to an instruction decoder where it determines what type of instruction has been fetched. shows a mechanism for executing instructions. This may include loading data into a register from memory storing data back to memory from a register or performing some type of arithmetic or logical operation. This exact type of operation to be performed has been previously determined by the machine instruction decoder. The instructions described in this invention would be executed here. If the instructions are being executed natively on a computer system then this diagram is complete as described above. However if an instruction set architecture is being emulated on another computer the above process would be implemented in software on a host computer . In this case the above stated mechanisms would typically be implemented as one or more software subroutines within the emulator software. In both cases an instruction is fetched decoded and executed.

More particularly these architected instructions can be used with a computer architecture with existing instruction formats with a 12 bit unsigned displacement used to form the operand storage address and also one having additional instruction formats that provide a additional displacement bits preferably 20 bits which comprise an extended signed displacement used to form the operand storage address. These computer architected instructions comprise computer software stored in a computer storage medium for producing the code running of the processor utilizing the computer software and comprising the instruction code for use by a compiler or emulator interpreter which is stored in a computer storage medium and wherein the first part of the instruction code comprises an operation code which specified the operation to be performed and a second part which designates the operands for that participate. The long displacement instructions permit additional addresses to be directly addressed with the use of the long displacement facility instruction.

Furthermore the preferred computer architecture has an instruction format such that the opcode is in bit positions through .

While the preferred embodiment of the invention has been illustrated and described herein it is to be understood that the invention is not limited to the precise construction herein disclosed and the right is reserved to all changes and modifications coming within the scope of the invention as defined in the appended claims.

