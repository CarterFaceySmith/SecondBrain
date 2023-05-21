# Smart Pointers in [[C++]]

A wrapper that wraps around a [[Pointer]] to an object on the heap, keeps track of object access, references to it, can delete the object and manages its memory.

#### Two types (so far)

Need to "#include <memory>" at the top of the file to access smart pointers.
	
- unique_ptr: a smart ptr where there may only be ONE reference to the object, cannot be copied
- shared_ptr: a smart ptr where there may be multiple references to the object
	
C++ does recommend using smart pointers as standard, and it's a good call, but they can have issues with circular references and leaking memory, plus not every other OOP language supports smart pointers.
	
