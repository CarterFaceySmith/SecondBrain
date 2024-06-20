A type of abstract data structure, behaves akin to a real-world stack of physical objects.

A stack is 'last-in-first-out', the element inserted last is accessed first.

Insertion is called 'push' and removal is called 'pop'.

Can be implemented using a [[Arrays]], [[Pointer]], or [[Linked-Lists]].

#### Basic Operations
- `push()`
- `pop()`
- `peek()`: see the top elem of the stack without removing
- `isFull()`
- `isEmpty()`

## Why does the Stack exist?
Given an example of a recursive [[Functions]] call, how would you remember the return memory address after each call to eventually return to the main function? 

Let's say at the beginning of that function it's address is pushed to a stacked and as the loop continues once it has no further calls to make it executes a pop on the stack for the number of times the function was called, eventually you are back in main.

See also:
- [[Data Structures]]
- [why stack exists](https://www.youtube.com/watch?v=hKXNr8oAkk8&pp=ygUQd2h5IHN0YWNrIGV4aXN0cw%3D%3D)
- [What is a stack and how does it work? - 6502 part 5](https://www.youtube.com/watch?v=xBjQVxVxOxc&pp=ygUkd2hhdCBpcyBhIHN0YWNrIGFuZCBob3cgZG9lcyBpdCB3b3Jr)