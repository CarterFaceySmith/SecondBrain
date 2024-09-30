A program in execution, noting a program is a passive entity, whereas the process is the active variant of the same.

Can be thought of as the totality of a program:
- Execution state and registers at a given moment, the frame
- Instruction set
- Currently open file list
- IO

It's a *context*. They then go into a process queue which the [[Operating Systems]] manages via a process control block (PCB).

You can think of this by way of the following generic struct:

```rust
pub struct PCB{
	pid: u16,
	state: ProcessStateEnum,
	program_counter: u16,
	general_purpose_registers: [u8; 4],
	instruction_register: u8,
	flags: [u1; 3],
}
```

The OS also tracks each memory block in the address space of a process, normally the PCB also contains memory limits information to help this.

Here is a more detailed example from the [Linux kernel](https://github.com/torvalds/linux/blob/master/include/linux/sched.h).


See also:
- [The fundamental unit of work in modern computer systems](https://www.youtube.com/watch?v=LDhoD4IVElk)
- 

