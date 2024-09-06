Further: [[C++ Debugging]]

## Types of Debugger Messages

- **Error Messages:** Notify you about issues in the code that prevent the program from running or compiling correctly. These messages typically include information about the file and the line number where the error is detected, followed by a description of the issue.

Example:

```cpp
    test.cpp: In function 'int main()':
    test.cpp:6:5: error: 'cout' was not declared in this scope
         cout << "Hello World!";
         ^~~~
```

- **Warning Messages:** Inform you about potential issues or risky programming practices that may not necessarily cause errors but could lead to problems later on. Like error messages, warning messages usually include information about the file and line number where the issue is found, along with a description of the problem.

Example:
   
```cpp
    test.cpp: In function 'int main()':
    test.cpp:6:17: warning: comparison between signed and unsigned integer expressions [-Wsign-compare]
         if (a < size)
                  ^
```

- **Informational Messages:** Provide general information about the execution of the program, such as breakpoints, watchpoints, and variable values. These messages can also reveal the current state of the program, including the call [[Stack]] and the list of active [[Threads]].

Example (_assuming you are using GDB as debugger_):

```cpp
    (gdb) break main
    Breakpoint 1 at 0x40055f: file test.cpp, line 5.
    (gdb) run
    Starting program: /path/to/test
    Breakpoint 1, main () at test.cpp:5
    5       int a = 5;
    ```

## Code Examples

To make use of debugger messages, you need to employ a debugger, such as GDB or Visual Studio Debugger, and include specific flags during the compilation process.

Example using GDB:

```cpp
// test.cpp

#include <iostream>

int main() {
    int num1 = 10;
    int num2 = 0;
    int result = num1 / num2;

    std::cout << "Result: " << result << std::endl;

    return 0;
}
```

```bash
$ g++ -g -o test test.cpp  // Compile with -g flag to include debugging information
$ gdb ./test               // Run the GDB debugger
(gdb) run                  // Execute the program inside GDB
```

At this point, the debugger will show an error message triggered by the division by zero:

```
Program received signal SIGFPE, Arithmetic exception.
0x00005555555546fb in main () at test.cpp:7
7       int result = num1 / num2;
```