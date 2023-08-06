# Dynamic Memory Allocation

DMA allows you to set an array size *DYNAMICALLY, WOW*! Basically, the array size can be set at program runtime instead of compile time, which is good when the prog. doesn't know about the number of iterables in advance. 

Ie when the user inputs items to be stored and we dont know how many theyll input but need to iterate through them all to print them after, or some other circumstance mate idk im not a cop theres a shit tonne of ways to use this concept.

### But Carter, how?!

Typically for the scenario above we set a pointer to the size of the array (in C++ at least), and when we loop through we then set the end condi to be when i=pointer.

Note: When reassigning a pointer, remember to use the delete keyword to delete what that pointer is currently pointing to before reassigning. Otherwise the initally referenced data will be stuck out in the ether unreferencable and therefore creating programmatic garbage on the [[Heap]].

### Stack vs. [[Heap]]

Stack = special mem area, stores temp vars created by funcs, in this space vars are declared stored and init during runtime, auto erased after computing task is completed, contiguous block

[[Heap]] = mem area, stores global vars, supports [[Dynamic Memory Allocation]], not managed automatically, free-floating region of memory, random order

### Managing memory ([[C++]])

To delete object we use a deconstructor/destructor, using the ~ symbol followed by the name of the class.

See also:
- [[Pointer]]
- [[C++]]
- [[Memory]]
