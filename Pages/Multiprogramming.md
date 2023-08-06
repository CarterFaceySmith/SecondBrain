Running multiple programs simultaenously.

We allocate more than one concurrent program and it's resources, allowing the CPU to be used by various users and I/O devices and therefore ensuring it always has something to execute (high utilisation).

Concurrent access to shared data has challenges though, such as 'Race Condition'.

## Race Condition

What is it?

It's when multiple processes access and manipulate the same data concurrently, meaning the outcome of execution depends solely on the order of access.


## Critical Selection Problem

Take a system of *n* processes {$p_0, p_1, \dots p_{n-1}$}. Where each might look like the following:

	do {
		entry section
			critical section
		exit section
			remainder section
		} while (true);

Each process has what we call a 'critical selection' code segment:
- Changes common vars, updates table, writing file, etc.
- **When one process is in the critical selection phase, no other process can be in their critical selection phase**

So my friend, the 'critical selection problem' detailed above is to design a protocol to *guarantee* that each process asks permission to do the following:
1. Enter critical section in entry section
2. Follow critical section with exit section
3. Follow exit section with remainder section

**_What??_**

Basically the processes need system permission to enter the next phase as they go along, and the system needs to deny them if there's a clash of any sort.

### What can we do about this?

- Mutual Exclusion (Prevents data corruption)
	- If there's a process in its critical section then no other processes can be executing in their critical sections

- Progress (Prevents deadlock)
	- If no process in critical section and some want to enter critical section, the selection of which will enter next cannot be postponed indefinitely

- Bounded Waiting (Prevents starvation)
	- A bound needs to exist on the number of times other processes are allowed to enter their critical sections after a process has already made a request to enter critical and it is yet to be granted


## Synchronization Hardware

On most modern computers we have special hardware instructions that allow for testing/modifying the content of a word or swapping the contents of two words *atomically*, one uninterruptible unit. We can use these to solve the critical section problem.

See the below mutual exlcusion implementation using a figurative test_and_set instruction:

	do {
		while (test_and_set(*lock*))
			; /* do nothing */
			/* critical section */
	
		lock = false;
	
			/* remainder section */
	} while(true);


## The *Mutex* Lock

[[Operating Systems]] designers built software tools to solve critical-section problems, one of which is the mutex (mutual exclusion) lock.

We use the mutex lock of course to protect critical regions, and therefore, possible race conditions.

See also: [[Deadlocks]]

### How does it work?

A mutex lock has a simple boolean val: available. This indicates exactly what it says, the lock availability.

If the lock is available, a call to acquire() (atomic acquisition instruction) succeeds and the boolean is switched.

A process **must** acquire the lock *before* entering a critical section, it then releases the lock when it exits the critical section.