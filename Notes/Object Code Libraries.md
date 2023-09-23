A set of object code files which can be used in code by importing the library.

After [[Linkers]] process all of the regular input files, they run through imports that remain undefined and then grab those from imported or referenced libraries.

## Library Formats

Simplest is just sequences of [[Object Files]] modules.

[[UNIX]] [[Linkers]] libraries use an archive format, libraries consist of an archive header followed by alternating file headers and object files.

Normally a variation of the following, using only text characters in the archive headers and starting with the 'magic' eight character string `!<arch>\n`, each archive member is preceded by a 50 byte header containing:
- Name of member
- Modification data as a decimal number of seconds since beginning of 1970
- User and group IDs as decimal numbers
- [[UNIX]] file mode as an octal number
- Size of file in bytes as a decimal number (File is padded with a newline char is number is odd)
- Two char reverse quote and newline to make header a line of text

```
File header:
!<arch>\n
Member header:
char name[16]; /* member name */
char modtime[12]; /* modification time */
char uid[6]; /* user ID */
char gid[6]; /* group ID */
char mode[8]; /* octal file mode */
char size[10]; /* member size */
char eol[2]; /* reverese quote, newline */
```

## Creating Libraries

Each archive format has its own technique for creating libraries. Generally this shit depends on how much support the [[Operating Systems]] provides for the archive format.

[[UNIX]] systems contained a pair of programs called `lorder` and `tsort` to help
create archives. `Lorder` took as its input a set of object files (not libraries),
and produced a dependency list of what files referred to symbols in what
other files. `Tsort` did a topological sort on the output of `lorder`, producing a sorted list of files so each symbol is defined after all the references to it, allowing a single sequential pass over the files to resolve all undefined references.

## Searching Libraries

Generally during the first pass of the [[Two-pass Linking]] process after all individual files have been read.



