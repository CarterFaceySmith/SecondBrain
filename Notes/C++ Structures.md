A type of [[Abstract Data Type (ADT) in C++]], and a core aspect of [[Object-Oriented Programming]], similar to [[C++ Classes]] except with public data structures by default upon initialisation.

Example:
```cpp
struct Person_t {
	std::string name; // Public
	unsigned int age;

private:
	unsigned int socialSecurityNum_;
};
```

## Why Use a Struct Instead of [[C++ Classes]]?

Generally speaking, structs are used for basic stuff, they should be data containers that carry public data and have very few basic member [[Functions]].

Classes are generally used for more complex tasking and carry private data which can be interfaced with through their public member functions.


See also:
- [[Data Structures]]
- [[C++]]