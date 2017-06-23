---

title: Semiconductor integrated circuit device and power consumption control device
abstract: To perform execution scheduling of function blocks so as to control the total required power of the function blocks within a supplyable power budget value, and thereby realize stable operations at low power consumption. Function block identifiers are allotted to all the function blocks, and to a RAM area that a power consumption control device can read and write, a list to store identifiers and task priority, power mode value showing power states, and power mode time showing the holding time of power states can be linked. A single or plural link lists for controlling the schedules of tasks operating on the function blocks, a link list for controlling the function block in execution currently in high power mode, a link list for controlling the function block in stop currently in stop mode, and a link list for controlling the function block in execution currently in low power mode are allotted, and thereby the power source and the operation clock are controlled by the power consumption control device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07646197&OS=07646197&RS=07646197
owner: Renesas Technology Corp.
number: 07646197
owner_city: Tokyo
owner_country: JP
publication_date: 20061004
---
The present application claims priority from Japanese Patent Application No. JP 2005 294757 filed on Oct. 7 2005 the content of which is hereby incorporated by reference into this application.

The present invention relates to a low power consumption technology in a semiconductor integrated circuit device more specifically to a technology effective for power consumption control in the functional block in the semiconductor integrated circuit device.

In recent years digital household electric appliances including battery driven types such as cell phones digital cameras portable audio players and the like and stationary types such as digital TV sets digital video disk players digital hard disk recorders and the like have become compact thin and light weight and semiconductor integrated circuit devices such as digital LSI Large Scale Integration and the like have been used widely.

Semiconductor microfabrication technologies to manufacture digital LSI have been developed more year after year and for example by making the gate width and oxide file thickness and the like of a CMOS Complementary Metal Oxide Semiconductor circuit thinner it has been possible to manufacture the digital LSI itself thinner and smaller. The compact and thin and light weight structure of the digital LSI is regarded as the value of semiconductor.

Further in order to make the gate width and the oxide film thickness thin it is necessary to make the power source voltage to be applied to the digital LSI low at the same time. As a result in order to secure the same processing capacity or more than that of digital LSI produced by the one generation prior microfabrication technology that is to produce digital LSI that can be driven at the same operation frequency or more from the relation between withstand voltage and the oxide film thickness it is necessary to make the power source voltage low and at the same time to make the threshold value voltage lower than that of the digital LSI.

However when the threshold voltage is made low whether the digital LSI is driven or not that is whether the CMOS circuit is switched or not the increase of leakage current which has the characteristic that as long as the power source voltage is applied current leaks and energy is consumed unintentionally becomes prominent.

In the years before 2000 the switching current having the characteristic that energy is consumed when the CMOS circuit is actually driven occupied the large portion of the entire power consumption. However it is forecasted that after the year 2000 along with the progress of microfabrication technologies the ratio of energy consumption by leakage current will become dominant exponentially.

Therefore the trend goes to the phase not to realize a digital LSI of the same processing capacity or more than that of the digital LSI by making the power source voltage low and making the operation frequency high but to realize a digital LSI by not setting the power source voltage as low as possible that is by preventing the decline of the threshold value voltage and driving similar plural processing mechanisms in parallel.

For example it is not to realize a high speed processor but to realize a mixed loading chip of plural processors and ASIC Application Specific Integrated Circuit that can operate in parallel.

The above consideration helps prevention of the exponential increase of the leakage current and easily realizes the compact and thin and light weight structure of digital LSI that is regarded as the value of semiconductors by microfabrication technologies.

Further when the compact and thin and light weight structure of digital LSI is realized products are differentiated with the same chip area as that of the digital LSI and by adding further processing functions therefore loading more plural processors and ASIC that can perform parallel processing than the mixed loading chip that is integration is performed consequently.

However in integration the number of transistors showing the CMOS circuit scale per unit chip area increases the LSI gets to have a large load capacity and the power consumption by switching current increases. It is forecasted that around the year 2010 the number of processors and ASIC loaded per one chip will be several ten to one hundred and the power source voltage will become saturated while become low on the contrary the consumption current as the sum of the switching current and the leakage current will be increasing in proportion to the number of processors and ASIC loaded per one chip.

There are occurring two main problems to be solved in the low voltage and large current age in the future arising from microfabrication and integration of digital LSI. One is the heat design power problem to occur with the digital LSI itself becoming a heat generation source and the other is the electromagnetic noise countermeasure problem to occur with the digital LSI itself becoming an electromagnetic noise generation source.

The thermal design power problem is the problem in designing the package of digital LSI by use of heat calculation equation. Whether the digital LSI is driving or not consumed power is converted into heat in accordance to the amount of current consumed and increases the temperature of digital LSI itself.

In the chip temperature there exists a temperature range to guarantee proper operation and when the temperature range is exceeded digital LSI sees malfunction and in the worst case the CMOS circuit is broken and operations cannot be made. In the personal computer and the like a cooling fan is arranged at the vicinity of LSI and thereby chip temperature increase is prevented.

However the cooling fan causes noise therefore it is not desired to package the cooling fan to digital household electric appliances. Further there is a case where a route to dissipate heat such as a heat sink or the like is arranged in package thereby the chip temperature increase is prevented.

In the future when microfabrication and integration are applied to digital LSI the consumption current will increase and the chip temperature will increase and there is a fear that the chip temperature may exceed the range of the temperature to guarantee proper operation.

Further the electromagnetic noise countermeasure issue is the problem concerning the system design of entire semiconductor integrated circuit device from digital LSI to a board on which the digital LSI is loaded. The electromagnetic noise is the total value of the value of DC component voltage of consumption current occurring by resistance components of entire power source wiring circuit including digital LSI and battery loaded on the board and the value of AC component voltage change of consumption current occurring by inductance components formed in the entire power source wiring circuit.

The value of the DC component voltage corresponds to the product IR of the resistance value R of the entire power source wiring circuit and the value I of consumption current. Meanwhile the value of the change in AC component voltage change corresponds to the product L dI dt of the inductance value L of the entire power source wiring circuit and the change ratio dI dt of consumption current per unit time.

In the electromagnetic noise there exists an allowable operation voltage margin and the operation voltage margin is the voltage equivalent to approximately 5 of the power source voltage.

However along with fine configuration the power source voltage is saturated but low and the operation voltage margin also becomes small. In general it is necessary to make the electromagnetic noise limited in the range of the operation voltage margin.

If the power source noise exceeds the operation voltage margin some phenomena occur like the power source voltage and the grounding potential those are normally constant fluctuate largely and the Power Integrity is deteriorated.

And at the same time the Signal Integrity among circuits becomes deteriorated LSI sees malfunction and in the worst case by occurrence of unnecessary radiation that is unnecessary electromagnetic wave EMI Electromagnetic Interface exceeds allowable values leading to an environmental issue.

In the future when microfabrication and integration are applied to digital LSI the consumption current and the time change ratio of the consumption current will easily increase and there is a fear that the electromagnetic noise may exceed the range of the operation voltage margin that will become smaller.

Accordingly in order to manufacture digital LSI while maintaining its compact and thin and light weight structure and multi functions by fine configuration and integration it is necessary to provide some feature and design to digital LSI so as to make the chip temperature where consumption current is going to increase in future becomes the main factor within the range of the operation guarantee temperature and make the power source noise which comes to the main factor limited in the range of the operation voltage margin power budget value at which the power supply is available under the maximum power of the semiconductor integrated circuit device is preset and application specifications can be satisfied within the range of the power budget value.

In general as technologies to make the consumption current small there are two technologies. One is power gating technology wherein power shutout to shut out power source voltage and action block shutout to shut out operation clock and the like are arranged to plural processors and ASIC loaded on digital LSI and the other is power control technology wherein power source voltage or operation frequency is controlled for the processors and ASIC.

The present inventors had examinations on a power consumption control device according to the prior art disclosed in Japanese Patent Laid Open No. H8 152945 Patent Document 1 hereinafter with the digital household electric appliances as objectives before the present application. The Patent Document 1 is a patent concerning a power consumption control device wherein the power control technology is employed and application specifications are satisfied within the power budget value. Further in the Patent Document 1 the use of the power gating technology is included. Before extracting problems the Patent Document 1 is explained.

Function blocks request for necessary power according to the present load condition. An information collection unit adds and collects required power from the respective function blocks. A supply power distribution determination unit when the total of added and collected power is within supplyable power value instructs a power distribution unit and outputs power requirement to the respective function blocks and when the total of power exceeds the supplyable power value it determines a power distribution method according to a predetermined method and instructs the power distribution unit and distributes and outputs supplyable power to the respective function blocks according to the power distribution method.

In the power consumption control technology by a power consumption control device of such a structure there are the following problems to be solved.

First as the first problem for example when the function block is a processor that can flexibly change processing contents different from ASIC where the power value can be fixed the required power is different per processing content that is per task therefore the number of combinations of power distribution is large and they become complicated therefore it is difficult to package a power distribution candidate table unit and it poses a problem.

Further a power consumption control device has the power distribution candidate table unit selection unit and distribution unit thereon even when desired plural function blocks work it sets the power distribution unit with appropriate power distribution thereby it can perform the power supply control within the power budget value.

However as the second problem for example when the function block to which the power distribution unit supplies low power source voltage and low operation frequency that is supplies low power in the course of process and satisfies a specified process to complete it since the priority and the contents of the power distribution method are not clear there is a fear that it cannot supply high power to the power distribution unit and high speed processing cannot ever be recovered.

Further when the total required power exceeds the power budget value in the course of process for example in the case where the total required power is made low to a certain function block according to a priority by use of the power gating technology since the process of the function block is stopped by the power consumption control unit if the power consumption control unit lets the function block be uncontrolled operation cannot be made later and there occurs a fear that the dead line of application specifications cannot be satisfied.

Accordingly it is necessary to set time for the function block that is in stop state according to the priority and release the stop state to supply power and the like.

The third problem is that the power consumption of the power consumption control unit is added to the total required power.

When the digital LSI is realized by one digital LSI it is necessary to make the total required power including the power consumption control unit within the power budget value.

Further the fourth problem is to limit the maximum power value of the digital LSI within the allowable power of power source IC.

When the power consumption control unit fails rapid sampling of large total required power by simultaneous driving of many function blocks that is when timing of comparison with the power budget value is lost the allowable power of power source IC is exceeded and sufficient power cannot be supplied to the respective function blocks and the process is broken and nonconformity occurs.

Accordingly it is necessary to estimate power margin within allowable power precisely and limit the maximum power.

In the case where the digital LSI is realized by one semiconductor integrated circuit device it is ideal to arrange a power source voltage distribution unit per function block however in order to prevent the chip area of digital LSI from becoming large the power source voltage distribution unit is often allotted and packaged to a set of relative function blocks.

Therefore if it is known that all the function blocks belonging to the set are in idle state shutdown of power source voltage can be made collectively for the function blocks belonging to the set and low power consumption can be realized.

The sixth problem is that even when plural function blocks are loaded it is necessary to set power in other function blocks than the power consumption control unit.

When the function block is regarded as a processor or a controller normally it is possible to change the power source voltage value and settings of operation frequency of the power distribution unit from software that operates the function block for example before the function block completes a specified process and gets in idle state by setting of the software the function block itself can get in stop state and therefore low power consumption can be realized.

However in the power consumption control unit 401 in Patent Document 1 power setting can be made only by the power consumption control unit therefore it is necessary to arrange a mechanism to set power from the function block.

The object of the present invention is to provide a technology for performing execution scheduling of function blocks so as to control the total required power of a single or plural function blocks within a supplyable power budget value and thereby realizing stable operations with low power consumption.

A semiconductor integrated circuit device comprises a single or plural function blocks a power consumption control unit that controls total required power of function blocks and determines the supply power of the respective function blocks an operation clock distribution unit that supplies operation clock per function block and the power consumption control unit a power source voltage distribution unit that supplies power source voltage per function block and the power consumption control unit a power conversion unit that collects power consumption component signals in function blocks and the power consumption control unit and converts them into total required power a volatile semiconductor memory such as RAM that the function blocks and the power consumption control unit can read and write a nonvolatile semiconductor memory such as ROM that the function blocks and the power consumption control unit can read and a timer and these are connected by buses and data are sent and received among them.

Identifiers are provided to all the function blocks and on local memory area corresponding to RAM area that the function blocks and the power consumption control unit can read and write a list is arranged to store the identifiers and the priority of task allotted to task operating on the function blocks power mode value to show either high power mode at which the function blocks operate with high power source voltage and high speed operation clock or low power mode at which the function blocks operate with low power source voltage and low speed operation clock or stop mode at which the function blocks get in stop state and a single or plural function block corresponding link lists function block control link list for controlling schedule of the task provided with a list which stores a power mode time indicating a duration of the low power mode or the stop mode as a parameter and linkable to the list power control link list for controlling function blocks in action currently at high power mode suspending link list for controlling function blocks in stop currently at stop mode and low power control link list for controlling function blocks in action currently at low power mode that are linkable with the list are prepared.

When a function block is used into the function block corresponding link list corresponding to the identifier of the function block the list to which the priority of task operating on the function block and the identifier and the power mode value showing high power mode and power mode time is inserted and linked in the order of the high priority and at the same time to the power control link list head lists of all the function block corresponding link lists are linked in the order of low priority.

If the total required power does not exceed the power budget value equivalent to the value obtained by subtracting the margin voltage from the allowable voltage of power source IC the setting of the power distribution unit is fixed.

On the contrary when there is no adverse effect on application specifications even if the total required power exceeds the power budget value and the power supply is stopped to the time control unit that controls the timer the power mode value showing stop mode and the power mode time are set to the head list of the power control link list the power mode value and the power mode time are stored from the power control link list the head list is excluded the operation clock and the power source voltage supplied to the function block corresponding to the identifier stored in the excluded head list are shut down by the power distribution unit and the function block is made into stop mode and the head list excluded is linked to the suspending link list in the order of high priority.

In the same manner when there is any adverse effect on application specifications even when it exceeds that and the power supply is stopped to the time control unit the power mode value showing low power mode and the power mode time are set to the head list of the power control link list the power mode value and the power mode time are stored from the power control link list the head list is excluded the operation clock and the power source voltage supplied to the function block corresponding to the identifier stored in the excluded head list are lowered by the power distribution unit and the function block is made into low power mode and the head list excluded is connected to the low power link list in the order of high priority.

Further when the use of a function block is completed the operation clock and the power source voltage supplied to the function block corresponding to the identifier stored in the head list of the suspending link list are raised by the power distribution unit and the head list is excluded and they are inserted again into the power control link list in the order of low priority and at the same time the operation clock and the power source voltage supplied to the function block corresponding to the identifier stored in the head list of the low power link list are raised by the power distribution unit and the head list is excluded and they are inserted again into the power control link list in the order of low priority and then the head list of the completed function block corresponding link list is deleted.

When the power mode value output from the time control unit after the power mode time set in the time control unit shows the stop mode the shutout of the operation clock and the power source voltage of the power distribution unit corresponding to the identifier stored in the head list of the suspending link list are released and the head list is excluded from the suspending link list and is inserted again into the power control link list.

When the power mode value shows the low power mode the operation clock and the power source voltage of the power distribution unit corresponding to the identifier stored in the head list of the low power link list are raised and the head list is excluded from the low power link list and is inserted again into the power control link list.

As described above among the proposed means by arranging linear link lists including the function block corresponding link list the power control link list the suspending link list and the low power link list and the like on local memory even for addition and deletion of scalable function block those were impossible in the table where the number of function blocks and power distribution are fixed such as power distribution candidate table and even when a task is added and deleted scalably by an operating system hereinafter OS by processor in the function block it is possible to perform packaging and operation flexibly and easily thereby the first problem can be solved.

Further among the proposed means by controlling the list storing the priority of the task allotted to the identifier and the information processing device mode values showing high power mode at which the function blocks operate with high power source voltage and high speed operation clock or low power mode at which the function blocks operate with low power source voltage low speed operation clock or stop mode at which the function blocks get in stop state and mode time indicating the duration of the low power mode of stop mode as parameters by the function block corresponding link list the power control link list the suspending link list and the low power link list even when the function block gets in the stop state or the low power state high power can be supplied to the power distribution unit after the mode time and accordingly the second problem can be solved.

Furthermore among the proposed means by structuring a semiconductor integrated circuit device comprising a single or plural function blocks the power consumption control unit the operation clock distribution unit the power source voltage distribution unit the power conversion unit the volatile semiconductor memory and the nonvolatile semiconductor memory and connecting them by buses and making data receiving and sending available it is possible to arrange a structure for setting its own power from the function block and the power consumption control unit and a structure for adding the power consumption of the power consumption control unit to the total required power and accordingly the third problem and the sixth problem can be solved.

Moreover the power consumption control unit compares the total required power with the power budget value as the value obtained by subtracting the power margin value from the allowable power of power source of the power source IC for example thereby controls the total required power at the allowable power or below. By making it the power budget value it is possible to make the total required power within the allowable power precisely and accordingly the fourth problem can be solved.

Finally in the case where the power source voltage distribution unit is allotted to a set of relative function blocks it is judged whether the list is linked to the function block corresponding link list corresponding to the identifier of all the function blocks of the set or not thereby it is possible to shut down the power source voltage by the power source voltage distribution unit corresponding to all the identifiers and accordingly the fifth problem can be solved.

The above and other objects and novel characteristics of the present invention will be apparent from the description of this specification and the accompanying drawings.

The typical ones of the inventions disclosed in this application will be briefly described as follows.

It is possible to perform packaging and operation flexibly and easily for scalable addition and deletion of function blocks loaded on a semiconductor integrated circuit device thereby achieving low power consumption effects and stable operations.

Hereinafter embodiments of the present invention will be described in detail with reference to the accompanying drawings. Note that components having the same function are denoted by the same reference symbols throughout the drawings for describing the embodiment and the repetitive description thereof will be omitted.

A semiconductor integrated circuit device includes a single or plural function blocks a clock pulse generation unit an operation clock distribution unit a power source unit a power source voltage distribution unit a power conversion unit a power consumption control unit an I O unit a ROM nonvolatile semiconductor memory a RAM volatile semiconductor memory a timer and buses .

The function blocks the operation clock distribution unit the power source voltage distribution unit the power conversion unit the power consumption control unit the I O unit the ROM the RAM and the timer are connected via the buses .

The function block is equivalent to an exclusive circuit of ASIC accelerator and the like and a general purpose circuit performing command control data processing and the like programmably according to software stored in processor DSP FPU and ROM RAM such as FPGA and the like. The respective function block has an interrupt receiving unit .

The bus is structured of a command control line for executing a command issued by the function block and a data transmission line via which the function block performs reading and writing by the ROM the RAM meanwhile for easy explanation in the present specification further a single or plural interrupt receiving lines and interrupt sending lines are added to the structure.

Further the function block has a power sensor that measures a power consumption structural element signal . The power sensor sequentially transfers the power consumption structural element signal to the power conversion unit . The power sensor is equivalent to for example a performance counter that measures the number of switching times of CMOS circuit a temperature sensor that measures heat amount a power monitor that measures consumption current and voltage.

The power conversion unit is structured of a power conversion unit and an adder and a total required power storage register .

The power conversion unit converts the power consumption structural element signal into a function required power value. The adder sequentially stores the total required power obtained by totaling all the function required power value into the total required power storage register .

The operation clock distribution unit is structured of a PLL Phase Locked Loop circuit to respond to all the function blocks and the power consumption control unit a divider an operation clock shutdown unit and an operation frequency state control register .

The operation clock distribution unit gradually multiplies the pulse generated by the clock pulse generator by a PLL and converts the result into the operation clock by the divider to output it to the respective function blocks .

The operation frequency state control register shuts down the operation clock to a specified function block according to setting. Further the register changes the PLL and the divider according to the bit pattern of the operation frequency state control register and supplies a desired operation frequency to the function block .

The power source unit is provided as a power source IC that converts for example battery voltage into power source voltage and supplies the power source voltage to the function block and the power consumption control unit . Further as a power source circuit system in addition to the power source unit a power source switch is packaged to the function block .

The power source voltage distribution unit has a power source switch register that sets the power source switch and by setting the bit pattern of the power source switch register sends a power source switch control signal that turns ON or OFF the power source switch of a specified function block and supplies or shuts down the power source voltage .

The power consumption control unit is structured of a command decoding unit an interrupt receiving unit an interrupt generator a time control unit a list registration unit a list release unit a power budget value acquisition unit an event processing unit and a power sensor . Further to the power consumption control unit a bus and a timer are connected.

Although it is not described because of simplified figure the timer is of the same kind as the function block . The timer converts the operation clock input from the operation clock distribution unit into a timer event .

The interrupt receiving unit notifies that there has been a timer interrupt in the timer event to the time control unit .

The time control unit adds 1 to a system clock memory at every input of the timer event and counts the number of timer interrupt times.

Further the time control unit sets a specified cycle time from the function block to a countdown memory A and subtracts one from the countdown memory Aat every timer event . When the countdown memory becomes zero the unit generates a cycle event and starts the event processing unit and resets the cycle time automatically to the countdown memory A and repeats the cycle event

Furthermore the time control unit sets a specified alarm time from the function block to the countdown memory B and subtracts one from the countdown memory Bat every timer event . When the countdown memory becomes zero the unit generates an alarm event and starts the event processing unit .

The event processing unit is structured of a total required power value acquisition unit a power budget value register a subtractor a comparator a power normal processing unit a power abnormal processing unit and a power shutdown processing unit .

When the event processing unit starts the command decoding unit acquires the total required power via the bus from the total required power storage register of the power conversion unit to the total required power value acquisition unit and stores it to the total required power value acquisition unit .

Next the event processing unit inputs the subtraction result obtained by subtracting the total required power stored in the total required power value acquisition unit from the power budget value stored in the power budget value register by the subtractor into the comparator .

The comparator judges whether the subtraction result is zero or more. If the subtraction result is zero or more execution is shifted to the power normal processing unit and if it is minus execution is shifted to the power abnormal processing unit .

Finally after execution of the power normal processing unit and the power abnormal processing unit execution is shifted to the power shutdown processing unit .

The power consumption control unit shifts execution to the command decoding unit when the interrupt receiving unit receives interrupt from the function block .

The command decoding unit shift execution to one of the list registration unit the list release unit the power budget value acquisition unit and the time control unit according to kinds of interrupt elements.

The list registration unit and the list release unit just after process give a start event to the event processing unit .

Further in the present specification the relation between master and slave among the function blocks is defined as that the master function block gives a command to the slave function block and the slave function block generates an interrupt to the master function block after completion of the specified process of the slave function block and the master function block receives the interrupt.

And the definition of a task is a thread or process controlled by an OS operating on the master function block and the slave function block. That is thread process and slave function block unit becomes a task unit. However when the OS is loaded on the slave function block the slave function block is not the unit but the thread or process operating on the slave function block becomes the task unit.

Accordingly the function block A in is the master and the function block Bis the slave. Further the relation between the function block A and the power consumption control unit becomes a master or a slave to each other.

The power consumption control unit may be packaged in the exclusive circuit or the general purpose circuit but hereinafter explanation is made on assumption of the use of the general purpose circuit that is processor.

The software to operate on the function block A is structured of OS A function block A software function block B control software power setting software function block communication software and application software and the software to operate on the power consumption control unit is structured of OS X power setting software function block communication software and power control application software .

The application software is structured of a thread controlled by the OS A and calls out the system call A of the OS A the function block A application programming interface hereinafter referred to as API of the function block A software the function block B control API of the function block B control software the power setting API of the power setting software and the function block communication API of the function block communication software and realizes application specifications.

The power control application software is structured of a thread controlled by the OS X and calls out from the power control thread system call X of the OS X power setting API and function block communication API and thereby realizes power control application specifications.

The thread and the power control thread call out system call A system call X supplied by the OS A and OS X and thereby realize thread control time control sync async communications and other functions.

They also call out the function block A API supplied by the function block A software and thereby perform specified processes by the function block A

Further they also call out the function block B API supplied by the function block B software and thereby perform specified processes by the function block B

In the same manner they call out the power setting API supplied by the power setting software and thereby set the power to the function block that is set the operation clock shutdown supply of power source voltage and operation frequency.

In the same manner they call out the function block communication API supplied by the function block communication software and thereby realize the function to transfer data with the function block .

Meanwhile the power setting software the function block communication software and the power control thread are stored in a specified program memory as a part of the ROM .

Further the power setting software the function block communication software and the power control thread perform specified processes by use of the specified working memory as one area of the RAM that can be read and written by the power consumption control unit .

The specified working memory is used for data processing. Other software is mapped to the ROM other than the specified program memory and for data processing the RAM areas other than the specified working memory is used.

The specified working memory is structured of a function block communication structural body a list pool a single or plural function block guard for the number of function blocks a power control guard a suspending guard and a low power guard .

The function block communication structural body is a memory block to store a command identifier memory and a single or plural communication parameter memory .

The list pool is a set of lists to be supplied to the link list. And the list is a dynamic memory block to store parameters including a task control pointer memory a power control pointer memory a task priority memory a function block identifier memory a power mode value memory and a power mode time memory and the like.

The function block guard the power control guard the suspending guard and the low power guard are of the same memory format as that of the list but are static memory blocks not supplied from the list pool .

Further the function block guard the power control guard the suspending guard and the low power guard using the list respectively control the function block link list the power control link list the suspending link list and the low power link list.

The function block link list performs the task control of the function block . To the task control pointer memory of the function block guard the address of the head list is stored and at the same time the address of the function block guard is stored into the task control pointer memory of the tail list.

Between the head list and the tail list the list is connected to the task control pointer memory in the order of high priority so that the task priority of the head list should be at the highest priority and the task priority of the tail list should be at the lowest priority. Further when the lists of the same task priority are connected they are connected in the order of FIFO First In First Out .

The power control link list controls the total required power. To the power control pointer memory of the power control guard the address of the head list is stored and at the same time the address of the power control guard is stored into the power control pointer memory of the tail list.

Between the head list and the tail list the list is connected by use of the power control pointer memory in the order of low priority so that the task priority of the head list should be at the lowest priority and the task priority of the tail list should be at the highest priority. Further when the lists of the same task priority are connected they are connected in the order of FIFO.

The suspending link list controls of shutdown and supply of operation clock in the power clock distribution unit . To the power control pointer memory of the suspending guard the address of the head list is stored and at the same time the address of the power control guard is stored into the power control pointer memory of the tail list.

Between the head list and the tail list the list is connected by use of the power control pointer memory in the order of high priority so that the task priority of the head list should be at the highest priority and the task priority of the tail list should be at the lowest priority. Further when the lists of the same task priority are connected they are connected in the order of FIFO.

The low power processing link list controls the operation frequency in the operation clock distribution unit . To the power control pointer memory of the low power guard the address of the head list is stored and at the same time the address of the power control guard is stored into the power control pointer memory of the tail list.

Between the head list and the tail list the list is connected by use of the power control pointer memory in the order of high priority so that the task priority memory of the head list should be at the highest priority and the task priority of the tail list should be at the lowest priority. Further when the lists of the same task priority are connected they are connected in the order of FIFO.

Meanwhile the programming language specification to be used is supposed to be ANSI C however other programming language may be employed. The type of API is function type.

Before explanations it is supposed that the power consumption control unit is realized by a processor and is structured of the power control thread the OS X the power setting software and the function block communication software . That is the command decoding unit the interrupt receiving unit and the interrupt generator of the power consumption control unit use processor and the time control unit uses the time control unit of the OS X

As the power setting API a power setting API that accesses the operation frequency state control register of the operation clock distribution unit and sets the operation frequency a power setting API that accesses to the same and sets the shutdown and supply of the operation clock a power setting API that accesses the power source switch register of the power source distribution unit and sets the shutdown and supply of the power source voltage a power setting API that accesses the total required power storage register of the power conversion unit and loads the total required power value to the power consumption control unit and the like are arranged.

Further as the function block communication API a function block communication API that transmits to the power consumption control unit that the thread has been generated a function block communication API that transmits to the power consumption control unit that the slave function block has been operated a function block communication API that transmits to the power consumption control unit that the thread is deleted from now a function block communication API that transmits to the power consumption control unit that the action of the slave function block has completed a function block communication API that sets the power budget value from the master function block a function block communication API that sets the cycle time of the cycle event to the event processing unit from the master function block and the like are arranged.

The function block communication API sets as arguments the task priority of the thread that a programmer or the OS A sets the function block identifier of the function block A the communication mode value for setting whether the communication between function blocks is sync or async the power mode value for setting the high power mode the middle power mode or the low power mode of the function block and the power mode time showing the holding time of the power mode value.

In the first process step S to the command identifier memory of the function block communication structural body a command identifier corresponding to own command is stored to the communication parameter memory A the task priority is stored and to the communication parameter memory B a function block identifier is stored to the communication parameter memory C the communication mode value is stored to the communication parameter memory D the power mode value is stored and to the communication parameter memory E the power mode time is stored respectively.

In the second process step S an interrupt is made from the function block A to the power consumption control unit .

Next it is judged whether the communication mode is sync or async and if it is sync the procedure goes to the third process step S .

In the third process step S by use of the power setting API the action of the function block A as the master function block is stopped.

The function block communication API also sets as arguments in the same manner the task priority of the thread that a programmer sets the function block identifier of the function block B the communication mode value for setting whether the communication between function blocks is sync or async the power mode value for setting the high power mode the middle power mode or the low power mode of the function block and the power mode time showing the holding time of the power mode value and the first process S the second process S and the third process S are performed in the same manner.

However in the third process step S it is the function block B as the slave function block that stops the action by use of the power setting API .

The function block communication API sets the function block identifier of the function block A as an argument.

In the fourth process step S to the command identifier memory of the function block communication structural body a command identifier corresponding to own command is stored and to the communication parameter memory A the function block identifier is stored respectively and the second process step S is performed.

In the same manner in the function block communication API too the function block identifier of the function block B is set as an argument and after the fourth process step S the second process step S is performed.

In the fifth process step S to the command identifier memory of the function block communication structural body a command identifier corresponding to own command is stored and to the communication parameter memory A the power budget value is stored respectively and the second process step S is performed.

In the sixth process step S to the command identifier memory of the function block communication structural body a command identifier corresponding to own command is stored and to the communication parameter memory A the power budget value is stored respectively and the second process step S is performed.

When an interrupt is received by the interrupt receiving unit of the power consumption control unit the function block communication software accesses the function block communication structural body via the command decoding unit as the seventh process step S .

Next it reads the command identifier from the command identifier memory of the function block communication structural body and selects the process corresponding to a desired function block communication API from the eighth process step S through the thirteenth process step S .

That is if the command identifier shows the function block communication API the procedure goes to the eighth process step S if it shows the function block communication API the procedure goes to the ninth process step S if it shows the function block communication API the procedure goes to the tenth process step S if it shows the function block communication API the procedure goes to the eleventh process step S if it shows the function block communication API the procedure goes to the twelfth process step S and if it shows the function block communication API the procedure goes to the thirteenth process step S .

First the list A is secured from the list pool and the value stored in the communication parameter memory. A of the function block communication structural body is stored into the task priority memory of the list A and the value stored in the communication parameter memory B is stored into the function block identifier and the value stored in the communication parameter memory D is stored into the power mode value memory and the value stored in the communication parameter memory E is stored into the power mode time memory .

And to the function block link list controlled by the function block guard B corresponding to the value of the function block identifier memory by use of the task control pointer memory the list is inserted in the order of priority and in the order of FIFO when the task priorities are same.

For example when the list B is connected to the function block guard B if the list A is higher than the task priority of the list B as the head list it is inserted after the function block guard B on the contrary if it is lower and in the case of the same task priority it is inserted and linked after the list B as the tail list.

In the eighth process step S after the list A is inserted into the function block link list and the list A is inserted into the power control link list controlled by the power control guard by use of the power control pointer memory in order of lower priority and in the order of FIFO when the task priorities are same.

After the list A is inserted into the function block link list and the power control link list the start event is made to the event processing unit and the eighth process S is completed.

Further the ninth process step S is the same list registration process as the eighth process step S .

First the task control pointer memory of the list C of the head of the function block link list controlled by the function block guard C corresponding to the function block identifier as the value of the communication parameter memory A of the function block communication structural body is removed.

Next the power control pointer memory of the list C corresponding to the value stored in the function block identifier memory of the removed list C is removed from the power control link list and the list C is returned to the list pool .

In the tenth process step S next when there exists the head list in the suspending link list controlled by the suspending guard and the low power link list controlled by the low power guard that is when the list D is liked to the suspending guard or the list E is linked to the low power guard the task control pointer memory of the list Dis removed from the suspending link list. In the same manner from the low power link list the task control pointer memory of the list E is removed.

Finally the power setting API and further the power setting API are called out and the function block corresponding to the function block identifier memory of the removed list D and list E is set by the operation clock distribution unit to the high power mode that is the maximum operation frequency.

The power budget value as the value of the communication parameter memory A of the function block communication structural body is stored into the power budget value register .

In the thirteenth process step S the cycle time as the value of the communication parameter memory A of the function block communication structural body is set by use of the system call X of the time control function of the OS X

The event process step S is realized by the power control thread . That is the start of the event process S corresponds to the start of the power control thread .

The power control thread first calls out the power setting API corresponding to the total required power value acquisition unit and loads the total required power value.

Next the total required power value is subtracted from the power budget value stored in the power budget value register if the result is positive or zero execution is shifted to the power normal processing unit and if it is negative execution is shifted to the power abnormal processing unit .

The power normal processing unit loads the communication mode value as the value of the communication parameter memory C of the function block communication structural body and the function block identifier as the value of the communication parameter memory B

If the communication mode value is set as sync an interrupt is made to the function block corresponding to the function block identifier by the interrupt generation unit .

The power abnormal processing unit first removes the head list F from the power control pointer memory of the power control link list.

Then it set the power mode time as the value of the power mode time memory time memory of the list F as the alarm time by the system call X to the alarm function of the OS X

Further if the power mode value memory of the removed list F is in the stop mode after inserting into the suspending link list in the order of high task priority it calls out the power setting API and shuts down the operation clock to the function block corresponding to the value of the function block identifier memory of the inserted list F

When the power mode value memory is in the low power mode after inserting it into the low power link list and linked in the order of high task priority it calls out the power setting API and makes low the operation frequency of the function clock corresponding to the function block corresponding to the function block identifier memory of the inserted list F

Further after lapse of the alarm time by the alarm event the head list linked directly to the suspending guard and the low power guard is removed from the power control pointer memory .

And the power setting API and further the power setting API are called out and the function block corresponding to the function block identifier memory of the removed list is set by the operation clock distribution unit to the high power mode that is turned to the maximum operation frequency.

It is supposed that the function block A the function block C and the function block D share the same power source switch .

First it is detected whether the each of the function block link list A the function block link list C and the function block link list D is empty or not that is whether the head address of the own function block guard is stored in the task control pointer memory of the function block guard .

If all of the function block link list A the function block link list C and the function block link list D are empty the power source switch register of the power source voltage distribution unit is set so as to perform low power consumption and the power source voltage is shut down by the power source .

Of course if an arbitrary function block link list is empty the operation clock is shut down by the operation clock distribution unit .

The present invention includes as shown in the power setting software the function block communication software and the power control thread thereby can perform the power control of the same information processing device as the preferred embodiment in . That is when any arbitrary function block has the power control thread the function block functions also as the power consumption control unit .

In the foregoing the invention made by the inventors of the present invention has been concretely described based on the embodiments. However it is needless to say that the present invention is not limited to the foregoing embodiments and various modifications and alterations can be made within the scope of the present invention.

The present invention is suitable for the technology for performing the power control in a semiconductor integrated circuit device and achieving low power consumption of the semiconductor integrated circuit device through its stable actions.

