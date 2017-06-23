---

title: Software/hardware partitioning program and method
abstract: A software/hardware (SW/HW) partitioning and evaluating program allows a computer to perform a procedure of compiling a source code in which a mark is added to a portion to be executed by hardware, a procedure of generating an executable program for a simulator of CPU on a system-on-chip (SoC), a procedure of storing in memory an execution result of the executable program, and a procedure of evaluating an SW/HW partition based on the execution result.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07908592&OS=07908592&RS=07908592
owner: Fujitsu Semiconductor Limited
number: 07908592
owner_city: Yokohama
owner_country: JP
publication_date: 20061004
---
This application is based upon and claiming the benefit of priority from the prior Japanese Patent Application No. 2006 109848 filed in Apr. 12 2006 the entire contents of which are incorporated herein by reference.

The present invention relates to a development system for a large scale integrated circuit for performing an application and more specifically to a software hardware partitioning program and method for determining the partition between software and hardware in developing a system on chip SoC for realizing the application.

Recently a system on chip SoC having a CPU and user hardware loaded on one chip has been widely used as an LSI for realizing an application for example the image processing in the H.264 system.

Generally when the image processing is realized there is the problem of outstanding arithmetic complexity for data and it is efficient to allow hardware to process large amount of data and the CPU to perform a controlling operation such as the management of processing time etc. to enhance the processing speed. Thus it is very important to improve the performance to appropriately determine the partition between hardware and software by determining which process is to be assigned to the hardware and which process is to be the software.

That is when one application is shared by a CPU and user hardware the CPU performs a part of the application as a program while the user hardware has a part of software mounted as a hardware engine thereby performing the application by the cooperation of the CPU and the user hardware. The design for partitioning an application between a CPU and hardware depends on the application and the architecture of the CPU.

Conventionally to determine the partition between software and hardware an operator manually partitions the source code of an application program between a portion to be processed by software and a portion to be processed by hardware performs calculation on executable data by a visual C program using for example a computer and evaluates the partition between software and hardware SW HW . However there has been the problem with the method that the SW HW partition cannot be appropriately evaluated between a built in CPU practically loaded into the SoC and a user hardware.

The patent document 1 as a conventional technology relating to the simulation of a system description the cooperative design between software and hardware etc. discloses a method for simulating a description of a system specification capable of correcting measuring the runtime of candidates for software and hardware.

The patent document 2 discloses the technique of evaluating the capability of the software by determining the estimated value of the runtime of software based on a set of benchmark program and evaluating a model developed from the benchmark program.

The patent document 3 discloses a technology of integrating a simulation of hardware with a simulation of software into one application in such a way that each of them can be debugged thereby realizing a high speed cooperative simulation.

However the above mentioned conventional technology cannot solve the problem that the SW HW partition between a built in CPU and user hardware cannot be appropriate evaluated.

 Patent Document 1 Japanese Published Patent Application No. H11 259552 Method For Simulating A Description Of System Specification 

 Patent Document 2 National Publication of International patent Application No. 2004 530193 Method And Apparatus For Statistical Evaluation Of Runtime Of Built In Software 

The present invention has been developed to solve the above mentioned problem and aims at determining the partition between software and hardware such that the partition can be optimum for the application to be performed in the system corresponding to a practical built in CPU and the hardware partitioned by a source code using for example a simulator exclusive for a built in CPU loaded into a system on chip.

A feature of the present invention resides in a software hardware partitioning evaluating program used to direct a computer to partition a source code into a software unit and a hardware unit to realize an application. The program includes 

a procedure of compiling a source code in which a mark is added to a hardware unit to be executed by hardware in the source code corresponding to the application and generating an executable program for a simulator of a central processing unit used to realize an application 

a procedure of storing in memory an execution result of the executable program using the simulator and

a procedure of evaluating a partition between a software unit and a hardware unit corresponding to a mark added to the hardware unit based on the execution result stored in the memory.

In in step S in the source code corresponding to the application the procedure of compiling the code in which a mark is added to the hardware unit to be executed on the hardware side and generating an executable program for a simulator of the central processing unit for use in realizing an application is performed. In step S the procedure of storing in memory an execution result of the executable program by the simulator is executed. In step S the procedure of evaluating the partition between the software corresponding to the mark added to the hardware unit and the hardware is performed.

In as described above the code in which a mark is added to the hardware unit is compiled a model of the hardware unit as a process portion to be realized by the hardware an executable program for a simulator of the central processing unit for use in realizing an application and an interface for calling the model of the hardware unit from the executable program side are generated in step S. In step S an execution result of an executable program by a simulator is stored in the memory including the result of execution performed by calling a hardware unit model by a simulator. In step S the partition between the software corresponding to a mark of the hardware unit and the hardware is evaluated using the stored contents of the memory.

As described above according to the present invention the source code in which a mark is added to the hardware unit is compiled and a generated executable program is executed by for example a simulator of the central processing unit used for realizing an application and the partition between the software and the hardware is evaluated corresponding to the execution result.

According to the present invention a partition between software and hardware can be appropriately evaluated by an execution result of the program by a simulator of the central processing unit used in realizing an application and the evaluation of a partitioning plan between software and hardware can be easily performed at the initial designing stage of the SoC.

In the virtual partitioning process in step S the mark indicating the start point and the end point of the HW unit hard block which is considered efficient when it is executed by hardware in the source code of an application is embedded. That is the coding process is performed such that the mark indicating the start point and the end point of the HW unit can be identified on the tool as a software development environment for the development of a built in software.

When an application for example an LSI specialized for H.264 is developed it is necessary to have an application to be implemented that is software operated by a simulator of a built in CPU. In the built in software development environment with the above mentioned purpose for example an instruction set simulator ISS is incorporated as a CPU simulator to be developed or another simulator executable by a CPU architecture is incorporated instead of an ISS. In the present invention the following configuration including an ISS is explained. An ISS is a simulator capable of executing a program at an instruction level.

In the virtual partitioning in step S the SW HW partition is virtually performed and the partition is evaluated based on the simulation result using for example the ISS. When the evaluation result is not satisfactory control is returned to the virtual SW HW partition again and a different partition is evaluated again. When an evaluation result is accepted the SW HW partition terminates and various models are developed in step S. Various models can be a C C model of ISS HW a SystemC model of ISS HW an RTL model etc. Since the model itself is not directly related to the present invention the detailed explanation is omitted here.

In step S for example the executable program on the ISS that is a load module is generated and a simulation executing process is performed on a CPU model in step S using the load module . In the simulation the HW unit in which the HW mark is embedded as shown in is identified from other SW units but is processed as in the normal process on the ISS like the SW unit. The simulation execution result is associated with the SW unit and the HW unit and separately stored in memory .

On the other hand in step S a result of the simulation is referenced even during the simulation executing process in step S and a debugging process is performed on the load module as necessary.

In step S the simulation result corresponding to the virtual partitioning of the SW HW stored in the memory is evaluated. If the evaluation result is accepted the partition between software and hardware terminates. If the evaluation is not accepted control is returned to step S a different software hardware partitioning process is performed and the processes in and after step S is repeated.

In the first embodiment the executing process is performed on the HW unit as with the SW unit by the ISS as described above. However since the ISS is an LSI specialized for a certain application that is a simulator of the CPU incorporated into a system on chip SoC a more appropriate evaluation can be made on the SW HW partition on the practical SoC as compared with the case where the SW HW partition is evaluated using a common personal computer independent of a built in CPU as in the conventional technology. The ISS has the function of executing a user C function as a Hard function and the virtual partitioning of the SW HW can be evaluated using only the ISS.

When the process is started in it is determined in step S whether or not there is an instruction to be executed. If there is the instruction the instruction is fetched and decoded in step S. In step S it is determined whether or not the instruction is an HW unit mark as a special instruction. If it is the mark then in step S an HW unit execution flag is placed in the ON position for the HW unit start mark and then the instruction executing process is performed in step S. If it is not the HW mark the instruction executing process is immediately performed in step S. If the HW unit mark indicates the endpoint of the HW unit in step S the HW unit execution flag is placed in the OFF place.

In step S the type of the information to be executed is grasped the number of cycles is determined by an instruction and the execution information as a result of the execution of the instruction is accumulated in step S. The execution information is stored in memory as the instruction execution information of the HW unit if the HW unit flag is in the ON position. If the HW unit flag is in the OFF position the information is stored in memory as the execution information about the SW unit.

Then interrupt processing is performed in step S control is returned to step S and the processes in and after step S are repeated if there are instructions to be executed. If there is no instruction to be executed control exits the Exe loop as an execution function and is returned to the process in step S shown in . The interrupt processing in step S is a common process on for example timer interrupt etc. has nothing directly to do with the present invention and the process in step S is not performed if it is not necessary.

In the multiprocessor system the communication frequency and the amount of communication data for the control and information transmission among processors the parallelism of programs among processors that is the confirmation information dependent on data etc. can be obtained and the information is stored in the memory and shown in separately for the result of the HW unit and the result of the SW unit.

Then the insertion of the HW unit mark into a source code is further explained using . In the pragma unit as a special instruction is inserted into a source code thereby indicating the start point and the end point of the HW unit. That is pragma inserts the special instruction indicating the start point of the HW unit and end inserts the special instruction indicating the end point of the HW unit into the C C source code and the start and end of the HW unit are recognized by for example the ISS.

The special instruction inserted into a source code is originally an instruction completely independent of a source code of an application but an instruction recognized only by for example an ISS as a CPU simulator. The instruction code in the HW unit enclosed by the start point and the end point can include the data that can identify the HW block as a part of the HW unit for example an address.

The explanation of the first embodiment is finished and the second embodiment is described below. In the first embodiment the SW HW partition is performed by inserting an HW unit mark into a source code but actual instruction execution is performed by for example an ISS on the SW unit and the HW unit and the execution information as an execution result of a simulation is accumulated separately as the execution information for the SW unit and the execution information for the HW unit. On the other hand in the second embodiment a model different from the CPU model exists for the HW unit as for example the HW unit of the C model. When a mark of a start point of he HW unit is recognized on the source code control is passed to the HW unit through the application program interface API and when the mark indicating the end point of the HW unit is recognized control is returned to the ISS as a CPU model again thereby performing a simulation.

That is in the compiling process an HW unit is separated as an independent object corresponding to a result of the SW HW partition. For example a load module as an executable program provided for the ISS can be only the SW unit but as described later to allow the ISS to execute an instruction of the HW unit assume that both SW unit and HW unit can be included.

In step S a simulation is performed using a CPU model for example an ISS and a result is stored in the memory as in . However when the start point of the HW unit is recognized the HW unit is called by the addressing by an API application programming interface and the HW unit is processed. The debugging process in step S and the partition evaluation determining process in step S are the same as those shown in .

When it is detected for example the HW block is called as a C model using the API in the second embodiment the HW function is executed and a result is returned to the ISS side through the API .

After the process on the ISS side is restarted and the HW unit execution flag is placed in the ON position for the start point of the HW unit mark and in the OFF position for the end point in step S it is determined in step S whether or not an instruction is to be executed. The determination is made as to whether or not the instruction with which the HW function is executed by the HW block is also to be executed on the ISS side. The determination is performed such that the determination result can be the same on one HW unit enclosed by the start point and the end point as marks.

Then an instruction is performed in step S. In this example an instruction not recognized as an HW unit mark in step S that is the instruction of the SW unit is obviously executed and when an instruction of the HW unit is executed in step S the instruction is also executed. When the instruction of the HW unit is not executed on the ISS side the instruction execution in step S is not executed and control is passed to step S.

In step S as in the first embodiment the information about a result of the instruction execution on the HW unit is stored in the memory and the execution information on the SW unit is stored in the memory . The execution information obtained when the instruction execution is executed by the ISS is also accumulated in the memory . The interrupt processing in step S etc. is the same as what is shown in showing the first embodiment and the explanation is omitted here.

The SW development environment of the CPU simulation is provided with the ISS and an API unit object and an HW unit corresponding to the software development environment for the computer OS are generated. An ISS is connected through the HW unit and the API unit . The connection is controlled by the contents of the address specification file . The addressing can be performed also by another file such as the address specification file etc. as shown here and also can be performed by embedding the contents of the file in the API unit . Thus according to the second embodiment the process of the HW unit can be performed as an object function of the same level as the ISS instead of performing the process of the HW unit by the ISS thereby performing the process at a higher speed than the first embodiment.

According to the second embodiment various information shown in as a result of the simulation after the virtual SW HW partition is obtained. The insertion of the HW unit mark into a source code and specification using a GUI are the same as those shown in according to the first embodiment and explanation is omitted here.

The SoC system on chip model including a CPU model constituted by the ISS and the virtual HW unit as a core model is explained by referring to . The system model can be constituted without discriminating the first embodiment from the second embodiment.

In the system model as a SoC model is constituted such that a plurality of peripheral I O input output units through and a plurality of CPU models through are connected to a bus . One or more ISS s are provided in each CPU model. For example the CPU model is constituted by one core model that is an ISS and a virtual HW unit . The CPU model is constituted by two core models that is the ISS and two virtual HW units .

In the result of the virtual SW HW partitioning can be evaluated by a simulation of a partition using a multiple CPU model with the same type or different type configuration. In the simulation of a partition for example the process of the flowchart shown in is performed in parallel. Therefore the parallelism of a program can be extracted. Furthermore for example in the SystemC or the C C SoC model the SW HW partition can be redesigned of the partition between software and hardware can be optimized in the CPU core ISS .

In the description above the SW HW partition evaluating program and partition evaluating method are explained but the designing system which uses the program as a tool can be constituted using a common computer system as a base. is a block diagram of the configuration of the computer system that is a hardware environment.

In the computer system comprises a central processing unit CPU read only memory ROM random access memory RAM a communication interface a storage device an input output device a portable storage medium read device and a bus connecting all these components.

The storage device can be used any type of storage device such as a hard disk a magnetic disk etc. The storage device or ROM stores a program shown in the flowchart in and a program according to claims through of the present invention. The program is executed by the CPU thereby evaluating the SW HW partition and developing various models corresponding to an appropriate partition result etc.

The program can be stored by for example the storage device from a program provider through a network and the communication interface or marketed and stored in a distributed portable storage medium set in the read device and executed by the CPU . The portable storage medium can be used any of various types of storage medium such as CD ROM a flexible disk an optical disk a magneto optical disk a DVD etc. The program stored in the storage medium is read by the read device thereby evaluating the SW HW partition according to the mode for embodying the present invention.

