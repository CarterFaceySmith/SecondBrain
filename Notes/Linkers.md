For a basic overview, see [[Linkers and Loaders]].

Linkers are generally kept as simple as possible to speed up program startup.
## [[Two-pass Linking]]

## [[Relocation]] 

## Linker Command Languages

A command language controls the linking process, this normally includes a list of object files and libraries to link at minimum.

### Common Techniques of Input

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

### **[[Position-Independent Code (PIC)]]**

## An Example of a Linker File for an [[Executable and Linkable Format (ELF) Files]] Executable

```
ENTRY(_start)  

SECTIONS {     
	. = 0x100000;  /* Set the starting address of the executable */      
	
	.text : {         
		*(.text)   /* Include all text sections (code) */     
	}      
	
	.data : {         
		*(.data)   /* Include all data sections */     
	}      
		
	.bss : {         
		*(.bss)    /* Include all uninitialized data sections */     
	}      

	/* Define other sections as needed */ }`
```

In this example:
- `ENTRY(_start)` specifies the entry point of the executable, usually a symbol representing the program's starting address.
- `SECTIONS` block encapsulates section definitions.
- `. = 0x100000` sets the starting address for the executable (0x100000 in this case).
- `.text`, `.data`, and `.bss` are section names. The `*` character is a wildcard that includes all sections of the specified type.
- The sections specified in each block are included in the output in the order they are defined.

## Linking in [[Embedded Systems]]

### Addressing Space Quirks

Embedded systems have small address spaces with weird layouts, a linker for an embedded system needs a way to specify the layout of the linked program in extreme detail, assigning kinds of code/data and even routines and variables to specific addresses.

### Non-uniform Memory

References to on-chip memory are faster than off-chip, so in systems with both kinds it is critical for high importance routines to go in fast memory.

You may be able to squeeze all time-critical code into fast mem. at link time, but could also copy code or data from slow to fast as needed so routines can share fast mem. at different times.

**Note**:
> For this trick, it’s very useful to be able to tell a linker "put this code at location XXXX but link it as though it’s at location YYYY", so the code will be correct when it’s copied from XXXX in slow memory to YYYY in fast memory at runtime.

