## What is GNU gprof?

GNU gprof is the granddaddy of profiling tools, part of the [[GNU]] Binutils package. It's a sampling-based [[Profiler]] that provides both flat profile and call graph information for your [[C++]] programs.

## How gprof Works

1. **Instrumentation**: When you compile with `-pg`, the [[Compiler]] adds code to your program to collect timing information.
2. **Sampling**: While running, the program periodically samples the program counter.
3. **Data Collection**: The program writes profiling data to a file named `gmon.out`.
4. **Analysis**: gprof reads `gmon.out` and your executable to produce a human-readable report.

## Setting Up gprof

1. Compile your program with profiling enabled:
   ```bash
   g++ -pg -o myprogram myprogram.cpp
   ```

2. Run your program normally:
   ```bash
   ./myprogram
   ```

3. Analyse the results:
   ```bash
   gprof myprogram gmon.out > analysis.txt
   ```

## Understanding gprof Output

gprof produces two main types of output:

### 1. Flat Profile

This shows how much time your program spent in each function:

```
Flat profile:

Each sample counts as 0.01 seconds.
  %   cumulative   self              self     total
 time   seconds   seconds    calls  ms/call  ms/call  name
 33.34      0.02     0.02     7208     0.00     0.00  open
 16.67      0.03     0.01      244     0.04     0.12  offtime
 16.67      0.04     0.01        8     1.25     1.25  memccpy
 16.67      0.05     0.01        7     1.43     1.43  write
 16.67      0.06     0.01                             mcount
  0.00      0.06     0.00      236     0.00     0.00  tzset
  0.00      0.06     0.00      192     0.00     0.00  tolower
```

### 2. Call Graph

This shows the calling relationships between functions:

```
Call graph:

granularity: each sample hit covers 4 byte(s) for 20.00% of 0.05 seconds

index % time    self  children    called     name
                0.00    0.05       1/1           main [2]
[1]    100.0    0.00    0.05       1         report [1]
                0.00    0.03       1/1           format_header [3]
                0.00    0.01       1/1           print_header [9]
```

## Practical Example

Let's profile a simple program with a performance issue:

```cpp
#include <vector>
#include <algorithm>
#include <cstdlib>

void inefficientSearch(std::vector<int>& vec, int target) {
    for (int i = 0; i < 1000000; ++i) {
        std::find(vec.begin(), vec.end(), target);
    }
}

int main() {
    std::vector<int> data(10000);
    for (int& n : data) n = std::rand() % 10000;
    
    inefficientSearch(data, -1);
    return 0;
}
```

Compile and run:
```bash
g++ -pg -o search search.cpp
./search
gprof search gmon.out > analysis.txt
```

In the output, you'll likely see that `std::find` is taking up a significant portion of the execution time. This would suggest that we should consider using a more efficient data structure or [[Algorithms]] for our search operation.

## Pros of gprof

1. **Simplicity**: Easy to use with minimal setup.
2. **Low Overhead**: Relatively small impact on program execution time.
3. **Standard Tool**: Widely available and well-documented.

## Cons of gprof

1. **Limited Detail**: Doesn't provide line-level profiling.
2. **No Thread Support**: Struggles with multi-threaded applications.
3. **Time Accuracy**: Can be less accurate for very short functions.

## Best Practices

1. **Compile with Optimisations**: Use `-O2` along with `-pg` for more realistic results.
2. **Run with Representative Data**: Ensure your test run exercises the typical use cases.
3. **Focus on Hot Spots**: Pay attention to functions that consume the most time.
4. **Consider Call Counts**: A function might be slow because it's called frequently, not because it's inefficient.