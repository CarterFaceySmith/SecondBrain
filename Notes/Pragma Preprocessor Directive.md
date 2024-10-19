```cpp
#pragma once

// your code here
```

`#pragma once` serves the same purpose as [[C++ Header Guards]], to avoid a header file from being included multiple times. With traditional header guards, the developer is responsible for guarding the header (by using preprocessor directives `#ifndef`, `#define`, and `#endif`). With `#pragma once`, we’re requesting that the compiler guard the header. How exactly it does this is an implementation-specific detail.

There is one known case where `#pragma once` will typically fail. If a header file is copied so that it exists in multiple places on the file system, if somehow both copies of the header get included, header guards will successfully de-dupe the identical headers, but `#pragma once` won’t (because the [[Compiler]] won’t realise they are actually identical content).

For most projects, `#pragma once` works fine, and many developers now prefer it because it is easier and less error-prone. Many IDEs will also auto-include `#pragma once` at the top of a new header file generated through the IDE.

Because `#pragma once` is not defined by the [[C++]] standard, it is possible that some compilers may not implement it. 