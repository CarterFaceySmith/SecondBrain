# CPU Scheduling 

Because all programs have some time waiting for IO, there are wasted system cycles and power.

A scheduler allows us to have one process using the CPU while the other waits for IO.

## Process Execution

![[Pasted image 20220809140459.png]]

## The Scheduler

It's the job of the scheduler to select another process from the ready queue to run next. 

The storage structure for the ready queue and the algorithm used to select the next process are not necessarily a FIFO queue. There are several alternatives to choose from, as well as numerous adjustable parameters for each algorithm. 

## Review: Context Switching

When the CPU switches to another process it needs ti save the old process state and load the saved state of the new process.

## Schedulers Expanded

### Short-term Scheduler
- CPU Scheduler
- selects which process should be executed next and allocates CPU

### Long-term Scheduler
- Job Scheduler
- Selects which processes should be brought into the ready queue

### Medium-term Scheduler
- Can be added if degree of multiple programming needs to decrease
- I.e. Removes processes from memory, stores them on disk and brings them back in to continue execution when warranted

## Preemptive vs. Non-preemptive

### Preemptive
Scheduler can forcibly remove processes from a CPU when it decides to allocate that CPU to another process.

### Non-preemptive
The scheduler is unable to force processes off the CPU.

## Alright, alright, alright. This is a lot but how does the Scheduler even decide this shit?

On a criteria son.

The main prioritisation is to keep the CPU as busy (utilised) as possible. Then it looks to throughput, the number of processes that complete their execution per time unit.

After this it goes as follows:
- Turnaround time: amount of time to execute the process
	- waiting time + CPU burst
- Waiting time: amount of time a process has been waiting in the ready queue
- Response time: amount of time it takes from when a request was submitted until the first response is produced, not output

## [[Scheduling Algorithms]]

## [[Ready Queues and Multilevel Queues]]

See also:
- https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/5_CPU_Scheduling.html