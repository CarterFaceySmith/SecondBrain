>A virtual function (also known as virtual methods) is a member function that is declared within a base class and is re-defined (overridden) by a derived class. 
>
>When you refer to a derived class object using a [[Pointer]] or a reference to the base class, you can call a virtual function for that object and execute the derived class’s version of the method.

- Virtual [[Functions]] ensure that the correct function is called for an object, regardless of the type of reference (or pointer) used for the function call.
- They are mainly used to achieve [Runtime polymorphism](https://www.geeksforgeeks.org/polymorphism-in-c/).
- Functions are declared with a `virtual` keyword in a base class.
- The resolving of a function call is done at runtime.

## [[C++ Virtual Destructor]]


See also:
- [[C++]]
- [[Polymorphism]]