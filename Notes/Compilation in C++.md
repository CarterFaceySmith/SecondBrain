# Compilation in [[C++]]

Edit -> Compile -> Execute cycle

### Let's run through the behind the scenes of this

1. First off your **pre-processor** comes along and runs through all the # statements at the top of your file, eg include, define, ifndef, endif, etc.
2. Then your **compiler** translates all the raw code and turns it into assembly instructions.
3. Your **assembler** comes in and partially compiles an individual cpp file into an object file, which is a machine code file (1s and 0s) that is missing its links to vars, funcs, methods that the code requires to actually run, in their place it contains a *'symbol table'* for all the missing links.
4. Finally, your **linker** connects all the missing links between the object files by matching the symbols in each of the symbol tables of the object files, after which it becomes a full executable.

### Why is this handy to know?

Well bud, you can do a partial compilation to only spend time compiling the part of a file or project that you've changed, to do this you use the -c flag in gcc, look it up online idgaf. 

You don't need to spend the time and resources recompiling the entire project, you can simply compile the change.

You can also make libraries using this method, a library is typically an object file that is then linked into an individual project using a linker per above.  Uses the linker flag -l, look it up.


See also:
- [[Makefiles]]

