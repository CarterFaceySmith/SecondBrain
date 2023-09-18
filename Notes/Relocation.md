One of the elements of [[Linkers and Loaders]].

## A Practical Example from *Linkers & Loaders* (J.R. Levine)

"Consider this snippet of x86 code that moves the contents of variable `a` to variable `b` using the eax register.
```
mov a,%eax
mov %eax,b
```

If `a` is defined in the same file at location 1234 hex and `b` is imported from
somewhere else, the generated object code will be:
```
A1 34 12 00 00 mov a,%eax
A3 00 00 00 00 mov %eax,b
```

Each instruction contains a one-byte operation code followed by a four-
byte address. The first instruction has a reference to 1234 (byte reversed,
since the x86 uses a right to left byte order) and the second a reference to
zero since the location of `b` is unknown.

Now assume that the linker links this code so that the section in which `a` is
located is relocated by hex 10000 bytes, and `b` turns out to be at hex 9A12.

The linker modifies the code to be:
```
A1 34 12 01 00 mov a,%eax
A3 12 9A 00 00 mov %eax,b
```

That is, it adds 10000 to the address in the first instruction so now it refers
to `a`’s relocated address which is 11234, and it patches in the address for
`b`. These adjustments affect instructions, but any pointers in the data part
of an object file have to be adjusted as well."

