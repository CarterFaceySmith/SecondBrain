
C++ programs must be compiled before running, [[Compilation]] creates an exe. If changes are made the file must be recompiled before the next run.

Notes:
- C++ supports some implicit typecasting

## Key Concepts

- **[[Object-Oriented Programming]]**
- **Standard Template Library (STL)**:
    - **Containers:** Data structures like vectors, lists, maps, sets, queues, and stacks that provide storage and manipulation capabilities for collections of objects.
    - **Algorithms:** Predefined functions for common operations such as sorting, searching, modifying, and iterating over elements of containers.
    - **Iterators:** Objects used to traverse and access elements of containers in a generic and consistent manner, facilitating algorithmic operations on container elements.
- **Templates**: Generic programming feature that allows writing functions, classes, and data structures that operate on any data type, promoting code reuse and flexibility.
- **Memory Management:**
    - **Dynamic Memory Allocation:** Allocating memory at runtime using operators `new` and `delete` to manage dynamic data structures and objects.
    - **[[Smart Pointers]]:** Automatic memory management objects (`unique_ptr`, `shared_ptr`, `weak_ptr`) that prevent memory leaks and resource leaks by encapsulating dynamic memory allocation and deallocation.
- **[[Concurrency]]:** Support for multithreading and parallelism using features like [[Threads]], [[Mutex]]es, condition variables, [[Atomic Operations]], and parallel [[Algorithms]], enabling efficient utilisation of modern multicore processors.
#### Typedefs

You can define new types using 'typedef' eg.
`typedef int Integer; //creates a new int type called Integer that can be used in place of int`