A wrapper around a [[Pointer]] to an object on the [[Heap]], keeps track of object access, references to it, can dynamically allocate and deallocate [[Memory]].

Need to `#include <memory>` at the top of the file to access smart pointers.

## Types

- **`unique_ptr`:** Represents exclusive ownership of a dynamically allocated object. It ensures that only one `unique_ptr` instance can point to the object at a time, and it automatically deallocates the memory when the `unique_ptr` goes out of scope.

- **`shared_ptr`:** Enables shared ownership of a dynamically allocated object among multiple `shared_ptr` instances. It maintains a reference count to track the number of shared owners, and it deallocates the memory when the last `shared_ptr` reference is released.

- **`weak_ptr`:** Provides a non-owning, weak reference to an object managed by a `shared_ptr`. It allows observing the object's state without affecting its reference count, helping prevent circular references and potential memory leaks.

C++ does recommend using smart pointers as standard, and it's a good call, but they can have issues with circular references and leaking memory, plus not every other [[Object-Oriented Programming]] language supports smart pointers.

[[Resource Acquisition Is Initialization (RAII)]]: Smart pointers adhere to the RAII principle, where resource management is tied to object lifetime. Memory deallocation occurs automatically when the smart pointer object goes out of scope.