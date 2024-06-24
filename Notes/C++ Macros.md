First off, during the [[Compiler]] pre-processing stage, when the `#define` statements are parsed, macros are parsed too, pure text replacing, same shit.

Example:
```cpp
#define CARTER std::cout("Hello, Carter.") /* This is terrible practice, never do it */
#define TIMEOUT_INTERVAL 10 /* This is a fine standard define statement */
```

But it gets weirder, remember we are just doing text replacement with these, so let's get funky and gross... don't do this: `#define OPEN_CURLY {`

A better use case for macros could be `#define LOG(x) std::cout << x << std::endl`

An even ***better*** use case would be defining debug only printout statements and logging:

```cpp
#if DEBUG == 1
#define LOG(x) std::cout << x << std::endl
#elif defined(RELEASE)
#define LOG(x) /* Replaces with nothing, as nothing is after the definition */
#endif
```

Note: `DEBUG` and `RELEASE` must be defined in your environment/compiler for this to work, or you can add `#define DEBUG 1` before the above code block.

Handy tip `#if 0` will zero out an entire encapsulated code block if you want, easier than commenting it all out normally.

Another example is logging [[Memory]] byte allocation and line number by replacing the `new` keyword with a custom that tracks the allocation and line it came from etc.

## Multi-line macros

Just use a backslash to escape the newline character in your `#define`.

```cpp
#define MAIN int main()\
{\
	std::cin.get();\
}

MAIN
```


See also:
- [[C++]]
- [[Metaprogramming]]
- [[Optimisation]]