Code that can execute without modification regardless of its absolute address.

Essential for shared [[Object Code Libraries]], allows the OS to load them at any address.

It's not a specific code but more-so a *characteristic* of code, a way to write it.

>For the most part, PIC is pretty easy to create. 
>
>[[Relative Jumps]] are often used by [[Hardware]] architecture, so that jump instructions within the routines need no [[Relocation]]. References to local data on the [[Stack]] use based addressing relative to a base register, which doesn’t need any [[Relocation]], either. 
>
>The only challenges are calls to routines not in the shared library, and references to global data. 

