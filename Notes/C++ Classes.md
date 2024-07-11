A type of [[Abstract Data Type (ADT) in C++]], and a core aspect of [[Object-Oriented Programming]], similar to [[C++ Structures]] except with private data structures by default upon initialisation, generally used for more complex tasking.

Example:
```cpp
class Person {
	std::string name_; // Private
	unsigned int age_;

public:
	unsigned age() const { return age_; } // Getter function - immutable therefore const
}
```


See also:
- [[C++]]