In the context of [[Linkers and Loaders]] the management and resolution of symbols from symbol tables is crucial, nothing works without this.

## Symbols Broadly

A symbol is a reference, each input module to a linker contains a table of these symbols that the module needs and uses, these can be:
1. Global symbols
	1. Defined and referenced in the module itself
	2. Referenced but not defined in the module itself (externals)
	3. Segment names, also usually considered to be global symbols defined at segment start
2. Non-global symbols, usually for debuggers and crash dump analysis
3. Line number information, tells the source language debuggers the communication between source lines and object file code

The [[Linkers]] read all of the symbol tables in the input module and get the useful info, often just what is needed to link, then builds the link-time symbol table and uses it to guide the linking process.

Note: Some formats have multiple symbol tables per file, like [[Executable and Linkable Format (ELF) Files]] which has one for debugging/relinking and one for [[Dynamic Linking]].

## Symbol Table Formats

Within the linker itself, the symbol table is often kept as an array of table entries using a [[Hashing]] function to location entries, or alternatively as an [[Arrays]] of [[Pointer]]s indexed by a hash function with all the entires that has together chained from each header.

So, to locate a symbol the linker computes a hash of the symbol name and uses that value modulo the number of buckets to select one of the hash buckets, then runs down the chain of symbols looking for the symbol.

### Module Tables

A linker of course needs to track input modules too, normally this is just done by storing a copy of the header in a table since most of the key info is in the file header.

This table also contains pointers to in-memory copies of the symbol table string table and relocation tables, along with any computed offsets of the text, data and bss segments in the output.

During first pass of the [[Two-pass Linking]] process, the linker reads in the symbol table from each file (generally copying into an in-memory buffer), if required by the format it will also put the symbol name string offsets into pointers to the in-memory version of the string too.

## Symbol Resolution

During the second pass of the [[Two-pass Linking]] process, the linker resolves symbol references as it creates the output file. 

> Real situations are more complex. For one thing, there are many ways that a symbol might be referred to, in a data pointer, in an instruction, or even synthesized from multiple instructions. For another, the output of the link- er is itself frequently relocatable. This means that if, say, a symbol is resolved to offset 426 in the data section, the output file has to contain a relocatable reference to data+426 where the symbol reference was. (*Linkers & Loaders*, John R. Levine)

The output file usually has it's own symbol table so the linker needs to make a new vector of indexes of the symbols to be used in the output file then map symbol numbers in outgoing relocation entries to those new indices.

### Weak And Strong Symbols

**Strong**: Must be resolved
**Weak**: *May* be resolved if there's a definition, but it's not an error if unresolved, primarily useful in connection with [[Object Code Libraries]]

[[Executable and Linkable Format (ELF) Files]] specifically adds another kind of weak symbol, a weak definition as well as a weak reference, defining a global symbol if no normal definition is available, if one is then the weak definition is ignored.
## [[Name Mangling]]








