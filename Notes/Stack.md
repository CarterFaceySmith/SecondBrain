## The Stack as a [[Data Structures]] concept

A type of abstract data structure, behaves akin to a real-world stack of physical objects.

A stack is 'last-in-first-out', the element inserted last is accessed first.

Insertion is called 'push' and removal is called 'pop'.

Can be implemented using a [[Arrays]], [[Pointer]], or [[Linked-Lists]].

### Basic Operations

- `push()`
- `pop()`
- `peek()`: see the top elem of the stack without removing
- `isFull()`
- `isEmpty()`

## The Stack as a memory concept

The stack can also refer to a space of contiguous memory in the context of [[C++]] specifically, where it is used by the [[Compiler]] to allocate and deallocate [[Memory]] space for variables at compile time automatically.

When the scope of whatever you allocate on the stack ends, everything that was allocated therein is freed automatically, the stack pointer moves to the position it was at before you entered the scope.

### What happens when a variable is declared?

When a variable is declared in code, for example a 4 byte integer, at compile time it is allocated memory in the stack, to do so the stack [[Pointer]] (i.e. the pointer to the top of the stack) moves that number of bytes further along.

### Why does the Stack exist?

Given an example of a recursive [[Functions]] call, how would you remember the return memory address after each call to eventually get back to the main function? 

Let's say at the beginning of that function its address is pushed to a stack, the loop continues and once it has no further calls to make it executes a pop on the stack for the number of times the function was called, eventually you are back in main.

See also:
- [[Data Structures]]
- [why stack exists](https://www.youtube.com/watch?v=hKXNr8oAkk8&pp=ygUQd2h5IHN0YWNrIGV4aXN0cw%3D%3D)
- [What is a stack and how does it work? - 6502 part 5](https://www.youtube.com/watch?v=xBjQVxVxOxc&pp=ygUkd2hhdCBpcyBhIHN0YWNrIGFuZCBob3cgZG9lcyBpdCB3b3Jr)