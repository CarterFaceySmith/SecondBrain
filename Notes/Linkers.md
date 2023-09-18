For a basic overview, see [[Linkers and Loaders]].
## [[Two-pass Linking]]

## [[Relocation]] 

## Linker Command Languages

A command language controls the linking process, this normally includes a list of object files and libraries to link at minimum.

### Common Techniques

- Command line: A mixture of files names and switches can be passed into the linker via the command line when called, a file containing names/switches can be run through and input in sequence if the command line has a command length limit.
- Intermixing with object files: Alternating object files and linker commands in a single input file.
- Embedded in object files: Passing the options needed to link an object file within the file itself.
- Seperate configuration language: Some have a full language to control linking, e.g. GNU linker.

## Adherence to [[Application Binary Interface (ABI)]]

A Linker often does heavy lifting in ensuring compliance with an [[Operating Systems]] ABI, which is important so the program is able to run.

## Advanced Concepts
### Dynamic Linking
- A process where linking is postponed until run-time, and the linking is performed by the loader.
- Reduces memory usage, allows shared libraries, and facilitates easy updates.

### **Shared Libraries**
- Libraries that are loaded at run-time and can be shared by multiple programs.
- Reduces program size, allows updates without recompilation, and enforces a common codebase.

### **Position-Independent Code (PIC)**
- Code that can execute without modification regardless of its absolute address.
- Essential for shared libraries and allows the OS to load them at any address.