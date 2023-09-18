Most [[Compilation]] systems have a *compiler driver*, it automatically invokes the phases of the compiler as needed.

## A Practical Example Using Two C Files

- C preprocessor on file A, creating preprocessed A
- C compiler on preprocessed A, creating assembler file A
- Assembler on assembler file A, creating object file A
- C preproccesor on file B, creating preprocessed B
- C compiler on preprocessed B, creating assembler file B
- Assembler on assembler file B, creating object file B
- Linker on object files A and B, and system C library

I.e. the driver compiles each source file to assembler then object code, links the object code together including needed routines from the system C library ([[Object Code Libraries]]).

Remember though that in actuality they often compare the creation dates of source and object files, and only recompile source files that have changed.


See also:
- [[Linkers and Loaders]]