# Pointer

a director to something, ie a file pointer can point to the prev file

remember used in [[Linked-Lists]] to direct prev and next

can be null, ie at the end of a list the null pointer point to nothing next (in [[C++]] this is nullptr)

### Layers of Abstraction

Simply means the amount of layers you have to go through for a pointer to get to your end goal, eg.
```c++
x = 1
ptr = &x //pointer to the address of x
ppter = &ptr //the pointer to the address of ptr
```

So to get a new pointer to retrieve val of x you have two layers to get through, therefore layers of abstraction, so you would say ***ptr = &pptr


### The triple-ref technique (Triple reference pointers)

how it's written in C: p**

what it is: a pointer to a pointer to a thing, commonly referenced as tracer. allows you to know where you have come from in a heap, ie the prev. node in memory and it's contents


### Key info and specific terminology

pointers can be reassigned

int* ptr = a pointer named ptr which points to a var whose datatype is integer (int can be any datatype)
you can read the above syntax as 'integer pointer named p'

*p = whatever the pointer p is pointing to's value (the value pointed to by...)
- Eg. *p = 12 changes the value of whatever p is pointing to to 12

&p = the memory value at p (access the address in memory of p)

** p = whatever the value of the data the pointer p is pointing to is, you can change values stored using this, ie you can go through the pointer and say fuck that change the data stored there to whatever

when working with pointers it can be useful to draw out a diagram to better see the flow of pointers-to-pointers etc

the above can be used to reassign data values and manipulate them overall


### How are pointers regularly used in programming though?
- referring to new memory reserved during program runtime
- refer and share large data structures without having to make copies of the data structures and clog the program up
- specify relationships among data, eg linked lists, graphs, trees, etc.

