The Kernel is a center of [[Operating Systems]] and provides basic services to all other parts of the OS. Makes up the main layer between OS and hardware, and mainly assists with memory management, file systems, device control and networking.

Commonly includes:
- An interrupt handler
	- Carries out all requests or completed input/output operations that compete for the kernel's services
- A scheduler
	- Determine which programs share the kernel's processing time and in what order
- A supervisor
	- Gives use of the computer to each process when scheduled
- Might include:
	- Manager for OS address spaces in memory
