# TRAPs

Certain assembly ops require specialised knowledge or protections best left to the computer, we use TRAPs for this (service routines or system calls are other names)

These are low level operations predetermined and performed exclusively by the OS

Think of a TRAP as a diverting of the flow of the code, the code runs line by line then when it hits a TRAP it is diverted and performs a specific op by the system until complete then resumes the code

Mechanism:
1. Looks up starting address for TRAP
2. Transfer to service routine (TRAP)
3. Return to code once complete

