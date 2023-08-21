# Operating Systems

There's not really a universally accepted definition of what an OS does, it mainly revolves around programs an OS ships with and the [[Kernel]] (program running at all times on the OS).

OS is a resource allocator and control program at its core. This is all performed by the [[Kernel]].

### System Startup/Boot 
1. PC is turned on
2. BIOS initialises hardware
3. BIOS calls code stored in MBR (Master Boot Record, a special memory section) at the start of disk 0
4. MBR loads code from the bootsector of the active partition
5. Bootsector loads and runs the bootloader from its filesystem

### Interrupt Driven
OS are typically 'interrupt driven', via hardware or software (exceptions/[[TRAPs]]), these interrupts signal for action by the OS.

### Mate, how the fuck does an interrupt work?
Let's say you're a nice little OS doing your everyday routine, you suddenly get an interrupt from something, what happens?

1. Firstly, if the CPU is currently processing an instruction the address is saved and state of the CPU is preserved by storing registers and the program counter, this is so it can resume and not fuck whatever it was doing.
2. Then, or if the CPU was idle, control is transferred to the interrupt service routine through the 'interrupt vector', this contains the addresses of all the service routines, like the big boss of service routines and their manager so to speak.

### Storage Structure
Ya got ya main memory, and ya secondary memory. Main is for large storage media that the CPU accesses directly, your RAM. Secondary storage is extension memory, shit like HDD and SSDs you've added, nonvolatile and large capacity.