
```cpp
Derived* derived = new Derived(); // Derived class

Base* base = derived; // New base instance is assigned to the derived class

AnotherClass* ac = dynamic_cast<AnotherClass*>(base); 
/* Does a null check on the class cast before conversion */

std::cin.get();
```

## How does the compiler know that the class is what it is?

C++ stores stores runtime type information (RTTI) about all of our types, this is what allows this functionality, but adds overhead.


See also:
- [[C++]]
- [Dynamic Casting in C++ - TheCherno](https://www.youtube.com/watch?v=CiHfz6pTolQ&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb&index=73)