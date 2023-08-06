# Threads

A basic unit of CPU utilisation, comprised of an ID, program counter, register set and [[Stack]].

Threads can share with other threads belonging to the same process, allowing the process to perform more than one task at a time.

This is where the term "multithreading" comes from.

## Multithreading Models

How are threads supported?

1. User level
	- User threads are supported above the [[Kernel]] and are managed without [[Kernel]] support.
2. [[Kernel]] level
	- Kernel threads are supported and managed directly by the [[Operating Systems]]

### Thread types

#### User
Management done by user-level threads library, primary thread libraries are:
	- POSIX Pthreads
	- Windows threads
	- Java threads

#### Kernel
Supported by the [[Kernel]]
	- Windows
	- Solaris
	- Linux
	- Tru64 UNIX
	- Mac OS X

### Establishing a relationship between user and kernel threads

- Many-to-one
	- Maps many user-level threads to one kernel thread
	- Management done by thread library in user space so it's efficient
	- But, as only one thread can access the kernel at once, multiple are unable to run in parallel on [[Multicore Programming]] systems.

- One-to-one
	- Each user thread is mapped to a kernel thread
	- Allows for [[Parallelism]]
	- Drawback is that each user thread must also create a corresponding kernel thread

- Many-to-many
	- Multiplexes many user-level threads to a smaller or equal number of kernel threads

### Implicit threading

What do we do if an application requires hundreds of thousands of threads?

Transfer the creation and management if threading from application developers to compilers and run-time libraries. This is implicit threading.

#### Thread pool
What the fuck is a thread pool?

1. Create a number of threads at process, place them into a pool where they wait for work
2. When a server receives a request, it will awaken a thread in the pool if one is free or wait if not
3. Once the thread completes the request it returns to the pool

#### System calls

`exec()`: program specified in the param will replace entire process, including all threads
`fork()`: system call is used to create a seperate dujplicate process


See also:
- [[Computer Science Fundamentals]]
- [[Multicore Programming]]
- [[CPU Scheduling]]