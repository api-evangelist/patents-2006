---

title: Fault tolerant system for execution of parallel jobs
abstract: The present invention provides a fault tolerant system and method for parallel job execution. In the proposed solution the job state and the state transition control are decoupled. The job execution infrastructure maintains the state information for all the executing jobs, and the job control units, one per-job, control the state transitions of their jobs. Due to the stateless nature of the control units, the system and method allow jobs to continue uninterrupted execution even when the corresponding control units fail.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08291419&OS=08291419&RS=08291419
owner: International Business Machines Corporation
number: 08291419
owner_city: Armonk
owner_country: US
publication_date: 20060926
---
The present invention relates to the field of parallel computing. More particularly the invention relates to a parallel computing architecture using Message Passing Interface MPI .

Since the past few decades the computational power of computing devices has increased exponentially. The advancement in hardware whether in terms of faster stronger processors or bigger memory is equally matched by the amount of data to be processed. The amount of data to be processed is so huge at times that a single computer may take days or even years to finish a task.

One of the methods employed to overcome the aforementioned problem is to use parallel computers. Parallel computers are two or more serial computers connected to each other in a particular configuration which communicate with each other for input and output requirements of data to be exchanged between the processes running on them. Using parallel programming a problem is divided into one or more tasks that can run concurrently. Thereafter these tasks are distributed over a cluster of parallel computers for execution. Once all the tasks have been executed the results are collated and presented. The use of parallel computing with parallel computers provides a greater memory and Central Processing Unit CPU resources to execute a job thereby reducing the turnaround time for its completion.

Parallel computers broadly follow two types of architectures i.e. distributed memory and shared memory. In distributed memory architecture the serial computers have access to their own memory and communicate with other nodes through a communication network.

In shared memory architecture multiple processing units share a common memory space using a high speed memory bus.

For a job i.e. a problem to run on a parallel computing architecture it must first be broken down into smaller problems that can run on different processors simultaneously. The smaller problems are referred to as job units. Thus a job consists of two or more job units. A single job unit is a process which executes concurrently with other job units.

The shared memory architecture does not scale up well for large jobs i.e. those which comprise of a few tens of job units. On the other hand the distributed memory architecture on the other hand does scale well to allow similar large jobs to execute with good performance.

Distributed memory parallel computers use the message passing programming paradigm in which the programmer has to explicitly divide data and work across the processors as well as manage the communication between them.

Message Passing Interface MPI implements the message passing model of parallel computing. The message passing model comprises of 

The processes may or may not run on different processing machines. The advantage of the above process is that it provides more control over the flow of data and can be implemented across a variety of platforms. MPI is usually implemented as a library of functions or subroutines that are inserted in the source code to perform data communication between the processes.

Once a job has been divided into two or more units and allocated some hardware resource from the job execution infrastructure it changes several states till the time of its completion These states may include for example initial loaded running stopped terminated etc. The transition between states is handled by Mpirun. Mpirun is a job control program which the user uses to launch their jobs on the execution platform. Each job has a corresponding Mpirun program that controls the state transitions of the job. As stated above a job has two or more job units that run parallel to each other. At any given time a job i.e. all the job units belonging to the job have the same state. All the job units for a particular job change the state together when instructed by the job control program.

The advantage of using Mpirun to control parallel jobs is that the mpirun can run and control the job from a remote location. It is possible for Mpirun and a parallel job to run on a physically different hardware. The parallel job usually runs on a much more robust hardware than the Mpirun. For instance one can run a parallel job on the servers in a supercomputing facility but the Mpirun that controls this job may run on a standard office computer. Not only is the office computer built of much less robust hardware and is sensitive to various aspect of problems such as power interruption but one is also exposed to the network hiccups between the office and the servers on which the job is running on.

As stated before Mpirun is responsible for the state transitions of its respective job. Consequently Mpirun also holds the present state of the job it controls.

If for some reason the connection to the Mpirun program is lost for example if Mpirun is killed there is no way to reconnect to the job and the infrastructure takes immediate action to terminate the job. This can be a problem for long executing jobs that are terminated after running for a significant amount of time losing all their work and wasting resources and time just because their connection to Mpirun is lost.

In addition Mpirun needs to closely interact with the job execution infrastructure in order to perform job state transitions which means that different infrastructures use different Mpirun programs customized for their own specific implementation. This tight coupling between Mpirun and the infrastructure does not allow Mpirun to be easily ported and used on other execution infrastructures.

The aforementioned problems make the parallel job execution architecture prone to faults as an early terminated job needs to be executed again from start. Various approaches have been taken in the past in order to stabilize parallel job execution architecture.

It is known in the art of parallel job processing to store information related to the job execution state in a table. Before terminating a job information regarding its state is stored. The information is used at a later stage to restart the job. However this approach relates to the problem of saving the running state of jobs when the jobs are in the middle of execution. The approach does not take care of the logical state of the job.

Re executing an early terminated job results in wastage of all the computing resources that it had used until it was terminated. Periodic Checkpointing is one solution to reduce such resource wastage. In periodic checkpointing an image of the job i.e. snapshot of all job units is saved to a disk at periodic intervals of time. These images can be later restored in case the job gets terminated because Mpirun is killed to restore its state to the last checkpoint and allow it to continue executing from that point reducing the waste of resources.

The problem with periodic checkpointing is that with the current capacity of today s parallel computers a parallel job may be composed of a huge number of processes job units . In such a scale the time and amount or storage required to periodically checkpoint such a job makes periodic checkpointing a practically infeasible option.

Therefore there is a need for a system for fault tolerant execution of parallel jobs that allows the jobs to continue uninterrupted execution even if their control program i.e. Mpirun gets killed or the connection to Mpirun is lost in order to minimize the waste of resources and time caused by the early termination of the jobs.

The present invention provides for a system for executing one or more jobs in parallel in a job execution infrastructure. The system comprises of a job distribution unit for allocating at least a portion of the job execution infrastructure to the job and job control units one per job for controlling the state transitions of their jobs.

The present invention also provides for a method for executing one or more jobs in parallel in a job execution infrastructure by allocating at least a portion of the job execution infrastructure to each job unit and controlling an execution state of each job unit. The state of each job is maintained by the job execution infrastructure and a state transition for each job is communicated to the job execution infrastructure as and when required.

The invention will now be described with reference to the accompanying figures. The figures and the description is meant for explanatory purposes only and is in no way intended to limit the inventive features of the invention.

The present invention describes a system and a method for running one or more jobs in parallel on a common job execution infrastructure. The jobs state is maintained with the job execution infrastructure thereby decoupling the control units from the actual execution of their jobs. Should the connection to the control unit be lost for any reason the execution infrastructure allows the jobs to continue uninterrupted execution since the state of the jobs is maintained with the infrastructure and not with the control units.

The control units have a similar role as the Mpirun programs in that control units are programs used to launch the jobs on the execution infrastructure. Control units differ from Mpirun in that control units are stateless with respect to the jobs they control. This allows jobs to continue uninterrupted execution even if their corresponding control units are killed.

The actual state of all jobs is maintained by the job execution infrastructure which exports an interface for jobs state query and control. The control units query the state of their jobs and communicate state transitions to the execution infrastructure using that interface.

In parallel computing a typical job is divided by a programmer into two or more units each of which has hardware resources allocated to it. One or more job units may share the hardware resources or hardware resources maybe dedicated to each job unit. The jobs are executed using the hardware resources. Each complete job that is run in parallel is referred to as job and each division as a job unit . Each job unit is equivalent to a process.

During a typical execution cycle a job may go through various job states. shows the various states that a job may undergo during its lifecycle. At first when a new job is created it is in the initiated state . Thereafter in order to start the execution of the job it is loaded . Once the job is loaded it is given the run command to get it into the running state . While a job is running its process may be stopped to be resumed later and restore it back to running state . A job may also be put in a debugging mode and then be resumed to the running state . A running job may be naturally terminated or it may terminate because of some error . All the job units i.e. the sub processes of a job have the same state at any given point of time.

Mpirun is the program used by the user to launch his job in a typical parallel computing environment. Mpirun controls the state transitions of the job until the job is completed. A system that implements such a parallel computing environment is shown in .

As shown in jobs A and B may be decomposed into two or more job units and . The job units are allocated hardware resources on the job execution infrastructure and are executed in parallel. The state of a particular job is maintained by its corresponding Mpirun program and which also controls the job s state transitions. These Mpirun programs communicate state transitions for the jobs to the execution infrastructure . The job execution infrastructure is stateless with regard to the state of jobs whereas the Mpirun programs are state full.

If the connection to Mpirun is lost for some reason in the aforementioned setup the job execution infrastructure takes immediate action to terminate the corresponding job. This results in waste of all resources consumed by the job until its early termination. Furthermore in such a setup the Mpirun is closely coupled with the job execution infrastructure. Since the Mpirun is actually responsible for performing the state transitions it is difficult to achieve the portability of Mpirun to different platforms.

The present invention proposes to overcome the aforementioned drawback by decoupling the control and the state maintenance of jobs. shows an embodiment according to the present invention. Once a job is received that has been divided into two or more job units a job allocation unit not shown allocates the job units and hardware resource on the job execution infrastructure . Apart from executing the jobs the job execution infrastructure also maintains the information on the present state of the different jobs and . For example job may be in state running while job may be in state stopped . In this setup stateless Mpirun also called control unit is responsible only for controlling state transitions for jobs and . The actual low level transition of state is carried out by the job execution infrastructure which exports an interface for state transitions control and monitoring. Any control unit implementation that conforms to the interface even one on a different platform may control parallel jobs on that execution infrastructure.

In the above setup the job execution infrastructure would maintain the job in its current state instead of terminating it even if the connection to the control unit is lost for some reason. If the job is in state of running when it terminates the infrastructure moves the job to a terminated state. At a later time a subsequent control unit can reconnect to the job by polling its current state from the infrastructure. This subsequent control unit can then continue to control the job s state transitions. In this manner the work performed by long executing jobs is not lost and resources are not wasted.

In yet another embodiment of the aforementioned concept in particular for the Blue Gene L supercomputer system as shown in the jobs state information is maintained in a DB2 database and the execution infrastructure uses a DB2 client to connect to the database update jobs state and answer job state queries from the job control units. The job execution infrastructure exports a set of Application Programming Interfaces APIs for adding and removing jobs querying jobs states and performing state transitions.

The Mpirun programs and interact with the job execution infrastructure using these APIs. To perform a state transition the Mpirun calls the corresponding API and the BlueGene L execution infrastructure handles the rest. To check if the state transition completes successfully the control units use the query API . The execution infrastructure will answer the query from the database .

There is no need to maintain a permanent connection between the control units and the infrastructure. This allows flexibility to an extent that the control units can be killed re restarted suspended and resumed and the job will still remain in its current state. The job will continue uninterrupted execution or moved to a terminated state by the infrastructure on its termination.

The basis for maintaining a connection between the infrastructure and the control units is for streaming input and output. However by buffering input and output and later streaming it to a subsequent control unit the infrastructure can maintain a continuity in execution of jobs even if the connection is lost.

In the aforesaid description specific embodiments of the present invention have been described by way of examples with reference to the accompanying figures and drawings. One of ordinary skill in the art will appreciate that various modifications and changes can be made to the embodiments without departing from the scope of the present invention as set forth in the claims below. Accordingly the specification and figures are to be regarded in an illustrative rather than a restrictive sense and all such modifications are intended to be included within the scope of present invention.

