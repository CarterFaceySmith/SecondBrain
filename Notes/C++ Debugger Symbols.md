Additional info embedded within a compiled program's [[Computer Binary]] code, helps debuggers understand the structure, source code and variables at a particular point in an execution process.

Two types:
1. Internal: Reside within the compiled binary itself, note that using these increases the size of the binary itself which might not be good in a prod environment
2. External: Kept in separate files from the binary code with file extensions like `.pdb` in Windows or `dSYM` in macOS.

## Generating Debugger Symbols

Using the `g++` [[Compiler]]:

**Internal Debugging Symbols (g++)**

To create a debug build with internal debugging symbols, use the `-g` flag:

```
g++ -g -o my_program my_program.cpp
```

This command compiles `my_program.cpp` into an executable named `my_program` with internal debugging symbols.

**External Debugging Symbols (g++)**

In case you want to generate a separate file containing debugging symbols, you can use the `-gsplit-dwarf` flag:

```
g++ -g -gsplit-dwarf -o my_program my_program.cpp
```

This command compiles `my_program.cpp` into an executable named `my_program` and generates a separate file named `my_program.dwo` containing the debugging symbols.

When sharing your compiled binary to end-users, you can remove the debugging symbols using the `strip` command:

```
strip --strip-debug my_program
```

This command removes internal debug symbols, resulting in a smaller binary size while keeping the `.dwo` file for debugging purposes when needed.


See also:
- [[C++]]
- [[C++ Debugging]]