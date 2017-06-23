---

title: Method and apparatus for executing a long transaction
abstract: A system that executes a long transaction in a system with limited transactional hardware resources. During operation, the system executes the long transaction in a non transactional mode, which does not use transactional hardware resources. The system defers stores generated during the long transaction so that the stores are not committed to the architectural state of a processor until the transaction is successfully completed. If the long transaction successfully completes, the system commits the long transaction, which involves performing multiple hardware transactions to commit the deferred stores to the architectural state of the processor.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07669040&OS=07669040&RS=07669040
owner: Sun Microsystems, Inc.
number: 07669040
owner_city: Santa Clara
owner_country: US
publication_date: 20061215
---
The present invention relates to a method and an apparatus for executing a long transaction in a system with limited transactional hardware resources.

Synchronization mechanisms facilitate preventing avoiding or recovering from inopportune interleavings of concurrent operations which are referred to races. One such synchronization mechanism is mutual exclusion locking wherein at most one thread is permitted access to protected code or data e.g. critical sections .

In the Java programming language the Java Virtual Machine JVM provides monitors by which threads running application code can ensure that certain operations are performed atomically with respect to the execution of other threads. Note that Java is a trademark or registered trademark of Sun Microsystems Inc. in the United States and other countries. Typical JVMs implement monitors with mutual exclusion locking mechanisms wherein the monitor is either locked or unlocked and wherein only one thread can own the monitor at any given time. A thread can enter a critical section protected by a monitor only after acquiring ownership of the monitor. If a thread attempts to lock a monitor that is in an unlocked state the thread gains ownership of the monitor. However if a thread attempts to acquire ownership of a monitor that has been locked by another thread the thread is not permitted to enter into a critical section until the owner of the lock releases the lock and the thread gains exclusive ownership of the lock.

Unfortunately mutual exclusion can cause problems. For example under mutual exclusion threads can be vulnerable to deadlock and a thread that is stalled or preempted while executing a critical section can impede other threads trying to acquire the lock which can cause excessive latency in acquiring the lock priority inversion and excessive context switching.

One solution to this problem is to use a lock free synchronization mechanism. A synchronization mechanism is considered lock free if a system that is executing a group of threads that communicate with each other is guaranteed to make useful forward progress e.g. completing an atomic update in a finite number of processor cycles. Lock freedom does not guarantee that a specific thread makes progress in a finite number of program steps but rather that at least one of the threads being executed by the system is guaranteed to make progress after a finite number of program steps.

The Java synchronization mechanism is the synchronized construct. A JVM can implement the synchronized construct in a number of ways 

Processors that support hardware transactional memory typically have limited hardware resources. The number of tracked loads and conditionally deferred stores is finite in these processors. Some of these processors do not support large transactions that load from or store to a large number of disparate cache lines. Furthermore some of these processors do not allow SAVE and RESTORE instructions in transactional mode thereby precluding procedure calls to non leaf routines while in transactional mode.

For example the following operations although synchronizing on the same object and executed by different threads commuted to H transactions can proceed in parallel because the operands do not conflict 

The following example illustrates the process of commuting synchronized blocks to H Transactions. Consider the following Java code fragment 

The above code attempts to use an H Transaction. If the object is locked at the start of execution of the critical section mutual exclusion locking is used. Otherwise a hardware transaction is used. Note that islocked loads and tests a lockword for an object. If a second thread acquires the lock while a first thread is executing a transaction the lockword is modified and the first transaction aborts immediately because of the interference by the second thread.

Note that if hardware transactional memory is not available mutual exclusion locking is used not shown in the above code . In practice the CHKPT routine returns a specified non zero value which indicates whether hardware transactional memory is supported by the processor.

Also note that a more sophisticated transaction triage failure policy can be used. The code above checks the return value from CHKPT . If the transaction fails because of interference or contention as evidenced by the return code from CHKPT a more sophisticated failure policy can retry the operation using hardware transactions a specified number of times before attempting to acquire a mutual exclusion lock. Typically once mutual exclusion locking is used on an object the object tends to remain in mutual exclusion mode until the contention abates.

Furthermore note that some critical sections are not eligible to be commuted to H transactional form. For example a critical section is ineligible if any of the following occurs 

Hence what is needed is a method and an apparatus for executing a long transaction without the problems described above.

One embodiment of the present invention provides a system that executes a long transaction in a system with limited transactional hardware resources. During operation the system executes the long transaction in a non transactional mode which does not use transactional hardware resources. The system defers stores generated during the long transaction so that the stores are not committed to the architectural state of a processor until the transaction is successfully completed. If the long transaction successfully completes the system commits the long transaction which involves performing multiple hardware transactions to commit the deferred stores to the architectural state of the processor.

In a variation on this embodiment if a thread which is performing the multiple hardware transactions fails to complete the multiple hardware transactions the system may use other threads to complete the multiple hardware transactions.

In a variation on this embodiment while performing the multiple hardware transactions the system partitions the deferred stores into subsets and commits each subset of deferred stores to the architectural state of the processor.

In a further variation while committing a subset of deferred stores to the architectural state of the processor the system uses a single hardware transaction to commit the subset to the architectural state of the processor.

In a further variation while committing a subset of deferred stores to the architectural state of the processor the system uses a single multi word compare and swap CAS operation to commit the subset to the architectural state of the processor.

In a further variation while committing the subset of deferred stores to the architectural state of the processor the system uses a restartable critical section to commit the subset to the architectural state of the processor.

In a variation on this embodiment while deferring a store generated during the long transaction the system places the store into a thread specific speculative commit buffer.

In a further variation if the transaction fails the system discards the contents of the thread specific commit buffer.

In a further variation if a load operation is performed on a variable which is stored in the thread specific commit buffer the system retrieves a value for the variable from an entry associated with the load operation from the thread specific commit buffer.

In a variation on this embodiment the long transaction is used to speculatively execute a critical section of code within a program without first acquiring a lock associated with the critical section.

In a variation on this embodiment prior to committing the long transaction the system ensures that a version number maintained for the long transaction has not changed thereby ensuring that variables read by a thread while executing the long transaction remain coherent with each other.

In a variation on this embodiment prior to executing the long transaction the system determines a favored mode of execution for the transaction wherein the favored mode of transactional execution can involve 1 executing the transaction using mutual exclusion to ensure that the transaction completes without interference from other threads 2 executing the transaction as a single hardware transaction which uses the transactional hardware resources or 3 executing the transaction as a long transaction which does not use the transactional hardware resources and wherein stores are not committed to the architectural state of the processor until the transaction is successfully committed.

In a further variation while determining the favored mode of execution for the transaction the system analyzes statistics from previous runs of the long transaction to determine the favored mode of transactional execution.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing computer readable media now known or later developed. Computer System

One embodiment of the present invention provides a transactional execution mechanism which executes long transactions in a non transactional mode which saves conditional updates in a log. In one embodiment of the present invention the log is a thread specific commit buffer.

In one embodiment of the present invention the long transaction is used to speculatively execute a critical section of code within a program without first acquiring a lock associated with the critical section.

In one embodiment of the present invention the transactional execution mechanism uses transactional memory or multi word CAS to attempt to commit the long transaction. If the commit operation is successful the log of conditional updates is written memory. Note that hardware transactions are referred to as H Transactions and long transactions are referred to as L Transactions. 

In one embodiment of the present invention L Transactions are lock free if the underlying H Transactions on which the L Transactions are constructed are lock free.

In one embodiment of the present invention static analysis is used before execution of the critical section to determine whether a block is ineligible to be commuted to a hardware transaction. If so the block is not commuted to an H transaction.

In another embodiment of the present invention the critical section is optimistically assumed to be feasible. In this embodiment runtime checks are inserted to guard ineligible sections. If program execution reaches an ineligible section the current transaction is aborted and several remedial measures can be taken. In one embodiment of the present invention the critical section is re executed using mutual exclusion locking. In another embodiment of the present invention the critical section is recompiled to use mutual exclusion locking and the critical section is re executed. In another embodiment of the present invention a flag specific to either the object i.e. data or the synchronized block i.e. code is set. Threads entering the synchronized block check this flag and based on the value use either mutual exclusion locking or execute the block using H transactions. Similarly the runtime environment can maintain statistics for each block. If the cost of the transactions that aborted because they attempted to execute ineligible code exceeds the benefits derived from transactional execution the JVM can set flags in the lock to indicate that operation should be performed using mutual exclusion locking in the future.

In one embodiment of the present invention long synchronized blocks that are H transactionally infeasible are made lock free in software by decomposing the commit phase into a number of short fixed size always feasible hardware transactions. In one embodiment of the present invention an L transaction tracks the consistency of all loaded values and deferred stores.

In one embodiment of the present invention the L transaction aborts completely using software to roll back the thread state. In another embodiment of the present invention the L transaction commits atomically to the architectural state of the processor.

In one embodiment of the present invention the L Transaction explicitly records L transactional stores in a thread local commit buffer. During the commit phase a thread attempts to install the commit buffer into the object or the monitor. If the install operation is successful a commit operation is performed which publishes the commit buffer so that the contents of the commit buffer are made visible to other threads. Once installed the thread then attempts to write back the deferred stores from the buffer to the associated locations in the memory hierarchy. In one embodiment of the present invention if a thread stalls or aborts during the write back phase other threads that operate on the same object can use a helping function to complete the write back phase for the stalled or aborted thread.

The benefit of using an L transaction is that stalled threads do no impede other threads and pure readers can operate in parallel without conflict. A disadvantage is that a first transaction that commits causes a second transaction which is operating concurrently with the first transaction to abort even if the operands do not conflict.

The following example illustrates the process of commuting synchronized blocks to L transactions. Consider the Java code or the equivalent byte code 

After completing pending write backs the thread executes the instructions in the L transaction block step . In doing so the thread may encounter a number of stores. These stores are deferred and recorded in a thread specific commit buffer. If the thread is interrupted by another thread the thread aborts and can restart execution from the beginning of the process.

If the L transaction body successfully completes the thread attempts to commit i.e. publish the deferred stores so that other threads can view the contents of the commit buffer step . If the thread is interrupted by another thread the thread aborts and can restart execution from the beginning of the process.

After publishing the commit buffer the thread attempts to write back the deferred stores to the architectural state of the processor step . In one embodiment of the present invention the deferred stores are partitioned into subsets of deferred stores and each subset is committed atomically to the architectural state of the processor using a single hardware transaction. If the thread is interrupted by another thread the thread aborts but does not restart execution from the beginning. Instead other threads can finish writing back the changes to the architectural state of the processor.

Next the system defers stores generated during the long transaction into a thread specific commit buffer so that the stores are not committed to the architectural state of a processor until the transaction is successfully completed step . In one embodiment of the present invention if the transaction fails the system discards the contents of the thread specific commit buffer. In one embodiment of the present invention if a load operation is performed on a variable which is stored in the thread specific commit buffer the system retrieves a value for the variable from a corresponding entry associated with the load operation from the thread specific commit buffer.

Another embodiment of the present invention handles transactional stores to local variables by saving the original value of the variable and the address for the local variable into a thread specific undo log. The new value for the local variable is then stored to the local variable. If the transaction commits successfully the undo log is discarded. Otherwise the undo log is used to restore the original values of the local variables for the thread. In other words L transactions update local variables in place and roll back the changes if the transaction fails.

One embodiment of the present invention stores a new value for a local variable and an address for the local variable into a thread specific commit buffer. In this embodiment if a transactional load operation is performed the thread specific commit buffer is checked to determine whether the local variable being referenced is in the thread specific commit buffer. If so the most recently written value in the commit buffer is returned by the load operation. Otherwise the value for the local variable stored in memory is returned. If the operation commits successfully the contents of the commit buffer are flushed into their respective variables. Otherwise the commit buffer is discarded. The commit buffer is then marked empty. In other words L transactions save updates to thread local variables into a log e.g. commit buffer and then roll the log forward if the transaction succeeds.

Returning to if the long transaction successfully completes the system commits the long transaction which involves performing multiple hardware transactions to commit the deferred stores to the architectural state of the processor step . Note that step is described in more detail in reference to below.

In one embodiment of the present invention prior to committing the long transaction the system ensures that a version number maintained for the long transaction has not changed thereby ensuring that variables read by a thread while executing the long transaction remain coherent with each other.

In one embodiment of the present invention while committing a subset of deferred stores to the architectural state of the processor the system uses a single hardware transaction to commit the subset to the architectural state of the processor. In another embodiment of the present invention while committing a subset of deferred stores to the architectural state of the processor the system uses a single multi word compare and swap CAS operation to commit the subset to the architectural state of the processor.

In one embodiment of the present invention when accessing CPU specific data or when executing critical sections on a uniprocessor Restartable Critical Sections can be used instead of CAS or hardware transactional memory.

In one embodiment of the present invention prior to Garbage Collection GC operations pending write backs are completed.

In one embodiment of the present invention reference field values in a committed but not yet written back commit buffer or a thread local undo log is treated as heap roots for the purposes of garbage collection.

One embodiment of the present invention complies with the visibility rules defined by the Java Memory Model specification JSR133 see JLS3e Chapter 171 . For example consider the following code that is executed using L transactions 

The examples above assume that a strong memory model such as SPARC s TSO or IA32 s SPO is used. Weaker memory models can be supported by the proper insertion of barrier or fence instructions.

Note that for notational convenience a hardware transactional memory mechanism with a capacity to perform memory operations to at least n distinct memory locations is referred to as TM n . The code in WriteBack requires TM or TM . For the sake of clarity the code has been simplified by using more variables than needed in the transaction. In practice the transactional memory requirements can be reduced to TM or TM e.g. the Log Cursor and WritePos fields can be collapsed .

Note that in the example above the L transactional fetches from global values are followed by a txConsistent call. This ensures that the thread in the L transaction only sees or is presented with a consistent set of shared global values. It is possible to relax the protocol however and elide some of the txConsistent calls. If a transaction is fated to abort and retry the consequence of eliding txConsistenct checks is that the L transactional code sees an impossible set of values and throws an exception. If all possible exceptions are prevented from leaking out of a doomed L transaction the txConsistent calls can be elided and the L Transaction can be aborted and retried at the txTryCommit point. Critically no control flow or variable updates are allowed to leak from a moribund L transaction.

The address component in the address value lists in the above example is shown as a simple virtual address. In one embodiment of the present invention the address is represented as an object Field pair or an Object Fieldoffset Size tuple.

In one embodiment of the present invention the version field in the above example is 64 bits wide. Note that if the field were shorter and overflowed then L transactions can be exposed to a situation where the compare of the version values in txCommit results in a false equal condition theoretically permitting a moribund transaction to inadvertently commit. In another embodiment of the present invention the version field is 32 bits wide. In this embodiment corrective or preventative action is taken such as using a stop the world point to abort all L transactions in flight.

Note that although the present invention is described in terms of an implementation for a JVM it is equally applicable to Managed Runtime Environments such as Microsoft s CLR Common Language Runtime .

In one embodiment of the present invention the preferred mode of execution uses a single hardware transaction which uses the transactional hardware resources block . In another embodiment the preferred mode of execution uses a long transaction which does not use the transactional hardware resources and wherein stores are not committed to the architectural state of the processor until the transaction is successfully committed i.e. an L transaction block . In another embodiment the preferred mode of execution uses mutual exclusion to ensure that the transaction completes without interference from other threads block .

If the preferred mode of execution uses hardware transactional memory block or software transactional memory block the system determines whether mutual exclusion locking is being used on the object block . If so the system uses mutual exclusion locking to execute the transaction blocks and . Otherwise the system executes the transaction using hardware transactional memory block or software transactional memory block respectively.

In one embodiment of the present invention the system attempts to use hardware transactional memory to execute the transaction. If the hardware transactional memory fails the system then uses software transactional memory to execute the transaction. If software transactional memory fails the system then reverts to using mutual exclusion locking to execute the transaction.

One embodiment of the present invention makes the critical section ineligible if it contains a wait statement. The critical section is run non transactionally even if the wait is executed infrequently. Another embodiment of the present invention optimistically assumes that the critical section does not execute the wait statement. In this case the wait statement is replaced with 

Another embodiment of the present invention commits the operation up to the point of the wait statement and then proceeds non transactionally. In this case the wait statement is replaced with 

Another embodiment of the present invention commits the transactional operations prior to wait using a hardware transactional execution mode to enqueue the thread on the monitor s waitset. This effectively partitions a synchronized block into two or more sub transactions the pre wait transaction and the post wait transaction. In this case the wait statement is replaced with 

The present invention uses a transactional memory mechanism to free up processor resources when a processor encounters a halt sequence. Transactional memory is described in more detail in U.S. Pat. No. 6 862 664 entitled Method and Apparatus for Avoiding Locks by Speculatively Executing Critical Sections by inventors Shailender Chaudhry Marc Tremblay and Quinn Jacobson. The above listed application is hereby incorporated by reference to provide details on how transactional memory operates and is herein referred to as Chaudhry . 

Some modern processors provide a checkpoint CHKPT instruction that places the processor in transactional execution mode. Once in transactional execution mode load and store operations are performed transactionally. Transactional loads operate normally except that the operand address is added to a set of tracked memory locations. The checkpoint instruction sets the list of tracked load addresses to empty. Transactional stores are deferred and not made visible to other processors or threads .

For example consider a processor Pthat has executed a transactional load of address an address A. If processor Psubsequently stores to address A P s transaction aborts immediately all pending transactional store operations for Pare abandoned and control resumes at the instruction designated in the CHKPT instruction with the register state rolled back to the values at the time of the checkpoint was taken. Conceptually Pmonitors tracked load addresses for the duration of the transaction.

A COMMIT instruction exits a transactional execution mode and attempts to write back any deferred stores accumulated during the transaction. The COMMIT instruction either completely succeeds in which case the stores are made visible to other processors or threads or the COMMIT instruction fails and the transaction aborts and no store operations are made visible to other processors or threads .

A Checkpoint Status CPS register can be read after a transaction fails. Status bits indicate if the transaction failed because of interference lack of hardware resources or some other reason.

Note that a transactional execution mode can be highly constrained. For example CAS MEMBAR SAVE RESTORE may not be permitted and result in the transaction aborting. Any traps or exceptions including TLB missed not satisfied in hardware can cause a transaction to abort. The number of distinct tracked load addresses and deferred stores are limited. If a transaction is too long i.e. too many tracked loads or deferred stores the transaction aborts and the processor sets the CPS register accordingly.

Also note that some processors do not provide an explicit ABORT instruction. In this case an existing trap always TA instruction can be used to abort transactions. Executing a TA instruction in transactional execution mode causes the transaction to immediately abort rolling back the processor state and causing control to transfer to the label designated in the CHKPT instruction.

Furthermore note that some processors also allow for the possibility of mutual abort with no progress wherein transactions are not necessarily lock free.

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

