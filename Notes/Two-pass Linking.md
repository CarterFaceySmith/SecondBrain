[[Linkers]] take in a set of input object files, libraries and perhaps command files, and from these make an output object file and maybe other misc. files like a load map.

The input files for these contain:
1. *Segments*: chunks of code to be placed in the output file
2. *At least one symbol table*

When the linker runs it:
1. Scans the input files to find the segment sizes and collect definitions/references of all symbols
2. Creates a segment table listing all segments defined
3. Creates a symbol table with all the symbols imported or exported

Using what is gained from this first pass, it assigns numeric locations to symbols, determines sizes and locations of segments in the output address space and figures out where to place them in the output file.

On second pass it uses this info to control the actual linking, it goes through and reads then relocates the object code, changing numeric addresses to symbol references and adjusting memory addresses to reflect relocated segment addresses.

It then writes this relocated code to the output file, after header information, then writes the symbol table information.

## Relinkable Objects

This is where the output file of one linker run can be used as the input for a subsequent linker run. The output file is required to have a symbol table like the one in an input file for this to work, alongside necessary input information, of course.

## On Single Pass Linkers

Some linkers appear to work in one pass, this is done by buffering some of the contents of the input in memory during linking, then reading the material later. It is an implementation trick and does not change the nature of two-pass linking.

See also:
- [[C++ Header Files]]

