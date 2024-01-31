**Definition:** Smart pointers are objects in [[C++]] that manage dynamically allocated [[Memory]] automatically, providing a safer and more convenient alternative to raw pointers.

**Types:**
    - **`unique_ptr`:** Represents exclusive ownership of a dynamically allocated object. It ensures that only one `unique_ptr` instance can point to the object at a time, and it automatically deallocates the memory when the `unique_ptr` goes out of scope.
    - **`shared_ptr`:** Enables shared ownership of a dynamically allocated object among multiple `shared_ptr` instances. It maintains a reference count to track the number of shared owners, and it deallocates the memory when the last `shared_ptr` reference is released.
    - **`weak_ptr`:** Provides a non-owning, weak reference to an object managed by a `shared_ptr`. It allows observing the object's state without affecting its reference count, helping prevent circular references and potential memory leaks.

**RAII (Resource Acquisition Is Initialisation):** Smart pointers adhere to the RAII principle, where resource management is tied to object lifetime. Memory deallocation occurs automatically when the smart pointer object goes out of scope, ensuring timely cleanup and preventing memory leaks.

**Advantages:** Smart pointers help prevent common memory management pitfalls such as memory leaks, dangling pointers, and double deletions by providing automatic memory cleanup, ownership semantics, and resource tracking.

**Usage:** Prefer smart pointers over raw [[Pointer]]s in modern C++ code to enhance code safety, readability, and maintainability, while minimising the risk of memory-related errors and bugs.