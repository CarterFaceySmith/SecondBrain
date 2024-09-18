In [[C++]] this means the data type of a variable is determined at [[Compilation]] time, before program execution.

Therefore, a var can only be used with data of a specific type, and the [[Compiler]] ensures only valid operations are performed on that type.

If there is a mismatch, the [[Compiler]] will adjust the data type of the var to match another if feasible, via internal [[Typecasting]], and will raise an invalid type conversion error during [[Compilation]] if not.

```cpp
#include <iostream>

int main() {
    int num = 65;        // 'num' is statically typed as an integer
    double pi = 3.14159; // 'pi' is statically typed as a double
    char c = 'c';        // 'c' is statically typed as a char

    c = num;    // This asssigment would convert num's value to ASCII equivalent character
    num = pi; // This assignment would convert pi's value from double type to int type
    
    std::cout << "The value of num is: " << num << std::endl;
    std::cout << "The value of pi is: " << pi << std::endl;
    std::cout << "The value of c is: "<< c << std::endl;
    return 0;
}
```


See also:
 - [[Dynamic Typing]]