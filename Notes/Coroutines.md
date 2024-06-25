>A coroutine is a function that can suspend execution to be resumed later. Coroutines are stackless: they suspend execution by returning to the caller, and the data that is required to resume execution is stored separately from the stack. This allows for sequential code that executes asynchronously (e.g. to handle non-blocking I/O without explicit callbacks), and also supports algorithms on lazy-computed infinite sequences and other uses.


See also:
- [[C++]]
- [[Functions]]
- [[Asynchronous Programming]]
- [Coroutines - cppreference](https://en.cppreference.com/w/cpp/language/coroutines)