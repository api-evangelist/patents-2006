---

title: Using readily available driver and application source code with a synthesized operating system
abstract: Software that modifies the source code for readily available software tasks—typically applications and hardware drivers—so that a small, fast, reliable operating system can be synthesized to control execution of these readily available software tasks.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07900187&OS=07900187&RS=07900187
owner: Robert Zeidman
number: 07900187
owner_city: Cupertino
owner_country: US
publication_date: 20060425
---
The present application is a continuation in part application of copending U.S. patent application entitled Software tool for synthesizing a real time operating system Ser. No. 10 688 573 filed on Oct. 20 2003 now U.S. Pat. No. 7 882 488.

The open source movement is having an increasing influence on the software industry and all software development. This movement consists of individual programmers and companies that create software and release the original source code to the public without charge. This source code is released to allow compilation for running on all kinds of computer systems. The software often includes common applications such as word processors and spreadsheets and drivers for use with specific hardware in a system.

The major driving force behind the open source movement is specifically the LINUX operating system LINUX . This open source operating system is growing in influence as it is being deployed by many different individuals and companies. Along with this growing acceptance in order to compete with commercial operating systems such as WINDOWS from MICROSOFT the complexity of LINUX is also growing to allow it to run on larger systems and to control complex multitasking systems. This increasing complexity inevitably results in decreasing reliability larger memory requirements and a slower response time to critical situations i.e. latency time .

While this growth in complexity is beneficial for desktop systems and web hosting systems it is detrimental for systems that require high reliability small memory and short latency. Critical systems such as medical equipment require high reliability. Systems on a chip SOCs require small memory footprints. Real time embedded systems require short latency. While a number of vendors are now offering versions of embedded LINUX these LINUX systems are all distinct semi proprietary operating systems that still have large memory requirements long latency times and inadequate reliability. Embedded system designers need the open source drivers and applications to run on an operating system that is smaller faster and more reliable than the existing off the shelf operating systems.

The present invention modifies the source code for readily available software tasks typically applications and hardware drivers so that a small fast reliable operating system can be synthesized to control execution of these readily available software tasks. The present invention provides a method and apparatus for searching the task source code for operating system application program interfaces APIs and replacing them with simple statements called primitives that are understood by a software synthesis program. The present invention provides a method and apparatus for also searching the task source code for data structures such as mutexes semaphores mailboxes and message queues and substituting primitives so that source code for declaring instantiating and accessing these data structures can be synthesized by a software synthesis tool.

The present invention is understood more fully from the detailed description given below and from the accompanying drawings of the preferred embodiments of the invention which however should not be taken to limit the invention to the specific embodiments but are provided for illustration explanation and understanding only.

One embodiment of the invention relies on a software synthesis program to perform the synthesis step i.e. generating system specific source code that can be directly compiled into an executable program that runs on a particular computer system . In this embodiment the present invention modifies task source code such that the modified source code can be used as input data for such a software synthesis program. One example of such a suitable synthesis program is the SynthOS program from ZEIDMAN TECHNOLOGIES. The principles of operation of the SynthOS program are disclosed for example in U.S. Pat. No. 6 934 947 entitled Visual Tool for Developing Real Time Task Management Code filed on May 10 1999 and U.S. patent application Ser. No. 10 688 573 entitled Software tool for synthesizing a real time operating system filed on Oct. 20 2003. Relevant features of SynthOS are described in the following sections.

SynthOS synthesizes source code to control tasks in a real time operating system RTOS . To specify the tasks to be synthesized SynthOS primitives are used to specify task management functions in a source input file. SynthOS recognizes several types of tasks that are discussed below. The specific parameters associated with each task are defined in a task section of a SynthOS Project SOP file which is an input configuration file used by the SynthOS program.

A Call task is a task that is not executed unless it is specifically started by an executing task calling task . A SynthOS call or SynthOS start primitive may be used to start execution of the Call task.

An Init task is executed once during the initialization of the software. It can also be started by an executing task just like a Call task i.e. using a SynthOS call or SynthOS start primitive to start execution of the Init task .

A Loop task is executed by the task management code using an algorithm defined by the scheduler as specified in the SOP file.

SynthOS primitives are placed in the source code to specify task management and communication between tasks. For example a SynthOS primitive is used in a first task to start execution of a second task while passing data to the second task and receiving data back from the second task. SynthOS primitives are styled after C language function calls and they are used in the code in a manner similar to operating system OS calls in a traditional RTOS. The next section explains the syntax for each of the following SynthOS primitives 

Note that SynthOS primitives can be inferred by SynthOS during synthesis i.e. the inferred SynthOS primitives are specified implicitly . In those cases the primitives are not needed but may be used for clarity within the code.

The SynthOS call primitive is a blocking primitive which means that execution of the current task is suspended until some later time when a condition is met. In the case of SynthOS call the condition is the completion of the called task.

The SynthOS call primitive begins execution of another task Taskname in the examples above while suspending execution of the calling task until the called task has completed. In the first example above where the return value is not specified the called task does not return a value. In the second and third examples the called task returns a value in variable Retval.

In the third example using the alternative syntax the SynthOS call primitive is inferred from the task identifier Taskname which is declared as a Call task in the SynthOS project file SOP file . Because the task returns a value the calling task cannot continue until the called task i.e. Taskname has completed execution and returned the value.

Note that if several tasks call the same Call task the call requests are queued in the order in which they occur only one instance or context of a given Call task may execute at a time. The SynthOS start primitive discussed below begins executing the called task without suspending the calling task.

The SynthOS check is a non blocking primitive that checks whether a Call task is currently executing. In executing a non blocking primitive the calling task continues execution and does not wait for the called task to complete. SynthOS check returns true if the task specified i.e. Taskname is executing false if all instances of the task have completed execution. If several different tasks call Taskname SynthOS check Taskname returns true if any instance of Taskname is scheduled for execution. If the user desires to know if a specific instance of a Call task is executing it is recommended that the user invoke that Call task only from one other task or create another mechanism such as using global variables to identify different instances of the Call task.

SynthOS sleep is a blocking primitive. SynthOS sleep blocks the calling task and returns execution control to the RTOS. The calling task may resume execution at a later time as determined by the RTOS. This primitive may be thought of as a voluntary preemption point that allows the scheduler to reschedule a higher priority task that is ready to run. Inserting SynthOS sleep primitives in long sections of code can increase the responsiveness of the system. At a suitable later time the RTOS restarts execution of the calling task from the point following the SynthOS sleep primitive. The time at which execution of the calling task resumes is determined by the operating system according to its scheduling algorithm the priority of the calling task and the priorities of other tasks waiting to execute.

The SynthOS start primitive is a non blocking primitive that begins execution of another task Taskname in the example without suspending execution of the calling task. In the alternative example the SynthOS start primitive is inferred from Taskname which is declared as a Call task in the SynthOS project file SOP file . Because the task does not return a value the calling task can immediately continue execution without suspension after the called task begins execution.

SynthOS terminate is a non blocking primitive. SynthOS terminate terminates execution of a task. If a task is specified such as Taskname that task is terminated. If no task is specified the calling task is terminated.

The SynthOS wait primitive is a blocking primitive that suspends execution of the calling task until Taskname is idle in the first example or when Condition becomes true in the second example . Condition can be any legal C expression using constants and global variables such as x i j 5 . Note that when waiting for a task to complete the SynthOS wait primitive does not begin execution of Taskname. If execution of Taskname needs to be started the SynthOS call primitive can be used to both start Taskname and wait for it to finish executing. If several different tasks call the same Call task the SynthOS wait primitive blocks until the last instance of that Call task completes. If the user desires to block until a specific instance of a Call task completes it is recommended that the user invoke that Call task from only one task or create another mechanism such as using global variables to identify different instances of the Call task.

When the SynthOS wait primitive is used to wait for a condition the calling task is suspended until the specified condition becomes true. Note that the condition may become false again immediately after the primitive is executed. This is because multiple tasks are effectively running simultaneously. For example one event in one task may cause the condition to become true causing the calling task to continue executing. However even before the calling task can execute the next line of its code another task may have already caused the condition to become false again.

The SynthOS project file is a user defined text file that has the name ProjectName.sop where ProjectName is the name of the project. The SynthOS project file is a listing of tasks and their properties expressed in a number of fields. Each field has a default value if the user does not specify an explicit value so the user need only specify those fields that are relevant to the application.

The code synthesized by SynthOS supports the task operations discussed in this section. At run time each task has an associated task context block TCB structure in memory. A TCB contains the current task state a pointer to the return value if the task returns a value an identifier ID that identifies the calling task i.e. a pointer to the queue TCBQ of TCBs associated with the calling task and the parameters that are passed to the task.

All TCBs associated with a task are queued in a TCB queue TCBQ specific to the task. Each time the task is called i.e. an instance of the task is executed a new TCB is loaded at the tail of the queue. An exemplary structure of a TCB Queue is shown in . As shown in at the head of the TCBQ is TCB which is the TCB for the currently executing instance of the task consisting of the task state the pointer to the value returned by the task if any the ID of the calling task and the parameters that are passed to the task. shows TCB which is the next TCB in the queue. TCB is the next instance of the task to be executed when TCB completes. TCB has the same structure as TCB and starts with the task state .

When operating system determines that task B can execute operating system checks whether the TCBQ of task B is empty. If not empty operating system transfers control to task B . Task B executes some code in the context of its current TCB as shown in element and updates the task state in its current TCB as shown in element . At element if execution of Task B in its current context is not yet complete control is returned to operating system . However at element if execution of task B in its current context is complete task B places the return value if any in its current TCB as shown in element places a DONE value in the task state field in the current TCB as shown in element and returns control to operating system .

When operating system determines that task A can execute operating system checks whether the TCBQ of task A is empty. If not empty operating system transfers control to task A using the TCB at the head of the TCBQ as its current context. When task A resumes execution it checks whether it is waiting for task B to complete due to execution of the previous blocking primitive as shown in element . If task A is waiting for task B to complete it checks whether task B has completed execution as shown in element by examining the current TCB of task B for a set DONE flag in the task state field. If task B has not completed task A returns control to the operating system . If task B has completed execution task A checks whether the ID field in the current TCB matches the ID of task A as shown in element . If the IDs do not match task A transfers control back to operating system as another task is waiting for task B to complete execution in its current context. If the ID in the current TCB of task B does match the ID of task A task A obtains the return value from the current TCB of task B as shown in element . Task A then writes a zero into the task state field in the current TCB of task B as shown in element and removes the current TCB from the TCBQ of task B as shown in element and continues executing code after the blocking primitive as shown in element .

If the TCBQ of task B is still not empty task B executes in the new context of the TCB that is now at the head of the TCBQ of task B . Note that task A and task B can return control to operating system many times during execution and operating system can return control to task A and task B many times before either task A or task B completes execution.

Before the source code of a program that includes hardware drivers and application programs can be used as input to a synthesis program such as SynthOS the source code must be modified to specify task management and task communication using synthesis primitives such as SynthOS primitives. According to one embodiment of the present invention a source code modification program follows the steps in to examine source code for various tasks that run on the operating system including hardware drivers and application programs. Beginning at step when the user specifies the files containing the source code for the tasks the source code modification program proceeds to step where it opens the first source code file for examination. The program opens a new source code file for writing the modified source code at step . At step the source code modification program examines the first function call from the file. Note that each programming statement may consist of none one or more function calls. At step the function call read is matched against a list of operating system APIs to determine whether the function call is to be substituted by one or more of the synthesis primitives. If a match is found at step the source code modification program performs the appropriate substitution at step as described later in this disclosure. The modified source code is written to the output file. If a match is found at step the source code modification program performs any necessary changes to the SOP file at step as described later in this disclosure. If no match is found at step the source code modification program copies the original source code to the output file at step . At step the source code modification program determines whether the end of file EOF for the input file has been reached. If not control returns to step . At step if the EOF has been reached both the input and the output files are closed at step . If there are still more source code files to be examined at step the process repeats for the next input file at step . If not at step the source code modification program halts.

Note that in certain cases it may be necessary to make multiple passes through the process for certain source code files in order for the source code modification program to modify code and insert code into the source code files.

One common standard set of APIs which may be used in the program discussed above in conjunction with is embodied in the POSIX standard that is used by Linux and other UNIX type operating systems. In this embodiment the source code modification program looks specifically for POSIX APIs and substitutes software synthesis primitives and other source code and in some cases makes modifications to the SOP file.

When determining how to make the appropriate substitution the source code modification program divides the APIs into categories. The first category is thread manipulation APIs. Threads are programs or functions that run concurrently on top of an operating system and correspond to drivers and applications. The terms thread and task may be used interchangeably below. A table of thread manipulation APIs is shown in .

The pthread create API is the thread creation system call. For software synthesis threads are allocated statically at compile time but POSIX only allows one thread to be created statically namely the thread that executes main . Thus the source code modification program scans the source code looking for pthread create APIs. The function specified in the third parameter will then be assumed to be a Call task and replaced with a SynthOS call or SynthOS start primitive depending on whether the function returns a value or not. Also the SOP file will be modified to specify the function as a Call task. The thread implementing main will thus be the only Loop task in the system.

The pthread self API provides a way for a thread to access the data structure that represents itself. A field in the TCB points to the pthread t data structure enabling the source code modification program to substitute this system call with a macro that uses SynthOS tcb pthread.

The first four of these system APIs referred to as cancel system calls are the POSIX system calls to terminate threads. The pthread exit API also referred to as the exit system call allows a thread to terminate itself. The source code modification program substitutes the SynthOS terminate primitive for these APIs.

These cleanup APIs allow cleanup handlers to be attached to threads. The cleanup APIs are automatically called when the associated thread is terminated. Cleanup APIs are infrequently used and add complexity. In many applications synthesis for cleanup APIs is not necessary and the source code modification program eliminates these APIs and issues a warning to the user.

The pthread detach and pthread join APIs control whether or not a thread can wait for another to complete and are similar to the SynthOS wait primitive. The source code modification program substitutes a SynthOS wait primitive.

The pthread equal API checks for equality of two thread data structures and the source code modification program substitutes a simple macro.

The pthread getconcurrency and pthread setconcurrency APIs are not necessary in some environments. In those environments the source code modification program removes these system calls and issues a warning to the user.

The pthread getschedparam and pthread setschedparam APIs allow control of scheduling policies and priorities. Because SynthOS does not allow changing scheduling policies and priorities at run time the source code modification program removes these APIs and issues a warning to the user. In an alternate embodiment SynthOS allows changing scheduling policies and priorities at run time and the source code modification program substitutes code to set global variables representing scheduling policies and priorities for the operating system.

The pthread once API is similar to executing an Init task except that the initialization can take place at any time. The source code modification program implements the pthread once system call by specifying the called task as a Call task and creating code for a global Boolean flag that is initialized to 0 by the Call task and set to 1 when the Call task completes. The source code modification program substitutes a SynthOS call primitive and inserts source code in the Call task to check this Boolean flag and only execute if the flag is 0. The source code modification program also modifies the SOP file to declare the called task as a Call task.

The attributes manipulated by the APIs are not meaningful in a single stack environment like the RTOS synthesized by SynthOS. The source code modification program produces an error message to the user when it comes across these APIs.

In a single process environment i.e. a single scope environment like the RTOS generated by SynthOS these APIs simply return reasonable values. The source code modification program replaces these APIs with simple functions that get and set global variables.

The pthread attr init API simply initializes a pthread attr data structure to its default values. The pthread attr destroy API does nothing on Linux so the source code modification program removes these APIs.

These get and set APIs simply fetch or set fields in the thread data structure. The source code modification program implements them as macros.

The pthread mutex init and pthread mutex destroy APIs are used to allocate and free memory used by mutexes. The source code modification program removes these APIs because the mutex implementation used by SynthOS requires very little memory.

These mutex APIs are the core functions of the mutex. The source code modification program substitutes them with the SynthOS wait primitive.

The pthread mutexattr init API simply initializes a pthread mutexattr t data structure to its default values. The pthread mutexattr destroy API does nothing on Linux so the source code modification program removes these APIs.

These eight mutex attribute APIs simply fetch or set fields in the mutexattr data structure. The source code modification program substitutes macros.

The pthread cond init API simply initializes a pthread cond t data structure to its default values. The pthread cond destroy API does nothing on Linux so the source code modification program removes these APIs.

These four condition APIs are the core functions of condition variables. The source code modification program substitutes the SynthOS wait primitive.

The pthread condattr init API simply initializes a pthread condattr t data structure to its default values. The pthread condattr destroy API does nothing on Linux so the source code modification program removes these APIs.

These two condition attribute APIs simply fetch or set fields in the condattr data structure. The source code modification program substitutes macros.

The pthread key create and pthread key delete APIs are used with the pthread setspecific and pthread getspecific APIs to provide a mini database for threads. The source code modification program substitutes macros.

The pthread rwlock init API simply initializes a pthread rwlock t data structure to its default values. The pthread rwlock destroy API does nothing on Linux so the source code modification program removes these APIs.

These five lock functions are the core functions of read write lock variables. The source code modification program substitutes the SynthOS wait primitive.

Another API category is read write lock attribute APIs. A table of read write lock attribute APIs is shown in .

The pthread rwlockattr init API simply initializes a pthread rwlock t data structure to its default values. The pthread rwlockattr destroy API does nothing on Linux so the source code modification program removes these APIs.

These two read write lock attribute functions simply fetch or set fields in the rwlockattr data structure and the source code modification program substitutes macros.

Using the substitutions and modifications described above hardware drivers and application programs may be converted for use with SynthOS or a SynthOS like synthesis program. The modified source code may then be provided to a synthesis tool to synthesize code for compilation into an RTOS.

Various modifications and adaptations to the embodiments described here are apparent to those skilled in the art based on the discussion in the above detailed disclosure. Many variations and modifications within the scope of the invention are therefore possible. The present invention is set forth in the following claims.

