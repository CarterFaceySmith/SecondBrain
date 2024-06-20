The so-called "brain" of the computer.

## Basic Flow

[[RAM]] sends data at some memory address to Control Unit through BUS into some register, the Control Unit deciphers it and is processed per whatever instruction or data it is via the ALU.

## Components
- **Control Unit**: Receives orders from RAM as instructions and breaks it down for other components
- **ALU (Arithmetic Logic Unit)**: Performs mathematical operations, takes two inputs and outputs one answer or a flag if doing COMPAREs.
	- Flags can be EQUAL, A is Larger, or both flags off meaning B is Larger
- **Register**: Acts like RAM within CPU, stores numbers temporarily, when the Control Unit turns on the set wire the Register will save whatever number is on its input wires.
	- When the enable wire is turned on, register outputs whatever is saved inside, this is output to the CPU Bus.
- **Bus**: A group of wires that connect multiple components in a computer.

## Instruction Sets
- `LOAD` a number from RAM into the CPU
- `ADD` two number together
- `STORE` a number from the CPU back out to [[RAM]]
- `COMPARE` one number with another
- `JUMP IF` *Condition* to another address in [[RAM]]
- `JUMP` to another address in RAM
- `OUT`put to a device such as a monitor
- `IN`put from a device such as a keyboard

## CPU Instruction Set Architecture
- [[x86 Architecture]]
- [[ARM Architecture]]
- [[RISC-V Architecture]]

See also:
- [[Operating Systems]]
- [[Computer Science Fundamentals]]
- [[Hardware]]
- [How a CPU Works](https://www.youtube.com/watch?v=cNN_tTXABUA&pp=ygUPaG93IGEgY3B1IHdvcmtz)