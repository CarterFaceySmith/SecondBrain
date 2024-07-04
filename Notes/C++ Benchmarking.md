How do you measure the performance of code you have just written? It's important you are able to compare to previous implementations or get a baseline performance metric in [[Optimisation]] critical code. 

There are many ways to do this based on the language, in this context we will use [[C++]].

First off, ***fucking make sure you're benchmarking in the 'release' mode of your codebase***, it's pretty pointless to benchmark code that isn't going to be finalised and shipped.

## [[Benchmarking]] implementations

### Timers and `chrono`

Use `chrono` to create a scope-based timer attached to some object to time execution of the code, simple as, but not very robust.

Example:
```cpp
class Timer {
	public {
		Time(){
			auto m_StartTimepoint = std::chrono::high_resolution_clock::now();
		}

		~Timer(){
			Stop();
		}

		void Stop(){
			auto endTimepoint = std::chrono::high_resolution_clock::now();
			auto start = std::chrono:;time_point_cast<std::chrono::microseconds>(m_StartTimepoint).time_since_epoch().count();
		}
	}
		private:
		std::chrono::time_point<std::chrono::high_resolution_clock> m_StatrtTimepoint;
};
```

### Visual benchmarking

We can use Google Chrome to read in profiling data via Chrome Tracing, the following code snippet details this, courtesy of TheCherno.

```cpp
/*
Usage: include this header file somewhere in your code (eg. precompiled header), and then use like:

Instrumentor::Get().BeginSession("Session Name");        // Begin session 
{
     InstrumentationTimer timer("Profiled Scope Name");   // Place code like this in scopes you'd like to include in profiling
     // Code
 }
Instrumentor::Get().EndSession();                        // End Session

You will probably want to macro-fy this, to switch on/off easily and use things like __FUNCSIG__ for the profile name.
*/

// Example profile:
// #define PROFILE_SCOPE(name) InstrumentationTimer timer##__LINE__(name)

#pragma once

#include <string>
#include <chrono>
#include <algorithm>
#include <fstream>
#include <thread>

struct ProfileResult
{
    std::string Name;
    long long Start, End;
    uint32_t ThreadID;
};

struct InstrumentationSession
{
    std::string Name;
};

class Instrumentor
{
private:
    InstrumentationSession* m_CurrentSession;
    std::ofstream m_OutputStream;
    int m_ProfileCount;
public:
    Instrumentor()
        : m_CurrentSession(nullptr), m_ProfileCount(0)
    {
    }

    void BeginSession(const std::string& name, const std::string& filepath = "results.json")
    {
        m_OutputStream.open(filepath);
        WriteHeader();
        m_CurrentSession = new InstrumentationSession{ name };
    }

    void EndSession()
    {
        WriteFooter();
        m_OutputStream.close();
        delete m_CurrentSession;
        m_CurrentSession = nullptr;
        m_ProfileCount = 0;
    }

    void WriteProfile(const ProfileResult& result)
    {
        if (m_ProfileCount++ > 0)
            m_OutputStream << ",";

        std::string name = result.Name;
        std::replace(name.begin(), name.end(), '"', '\'');

        m_OutputStream << "{";
        m_OutputStream << "\"cat\":\"function\",";
        m_OutputStream << "\"dur\":" << (result.End - result.Start) << ',';
        m_OutputStream << "\"name\":\"" << name << "\",";
        m_OutputStream << "\"ph\":\"X\",";
        m_OutputStream << "\"pid\":0,";
        m_OutputStream << "\"tid\":" << result.ThreadID << ",";
        m_OutputStream << "\"ts\":" << result.Start;
        m_OutputStream << "}";

        m_OutputStream.flush();
    }

    void WriteHeader()
    {
        m_OutputStream << "{\"otherData\": {},\"traceEvents\":[";
        m_OutputStream.flush();
    }

    void WriteFooter()
    {
        m_OutputStream << "]}";
        m_OutputStream.flush();
    }

    static Instrumentor& Get()
    {
        static Instrumentor instance;
        return instance;
    }
};

class InstrumentationTimer
{
public:
    InstrumentationTimer(const char* name)
        : m_Name(name), m_Stopped(false)
    {
        m_StartTimepoint = std::chrono::high_resolution_clock::now();
    }

    ~InstrumentationTimer()
    {
        if (!m_Stopped)
            Stop();
    }

    void Stop()
    {
        auto endTimepoint = std::chrono::high_resolution_clock::now();

        long long start = std::chrono::time_point_cast<std::chrono::microseconds>(m_StartTimepoint).time_since_epoch().count();
        long long end = std::chrono::time_point_cast<std::chrono::microseconds>(endTimepoint).time_since_epoch().count();

        uint32_t threadID = std::hash<std::thread::id>{}(std::this_thread::get_id());
        Instrumentor::Get().WriteProfile({ m_Name, start, end, threadID });

        m_Stopped = true;
    }
private:
    const char* m_Name;
    std::chrono::time_point<std::chrono::high_resolution_clock> m_StartTimepoint;
    bool m_Stopped;
};
```

## [Google Benchmarking Toolkit](https://github.com/google/benchmark)

An opensource repository of code benchmarking tools for C++, also integrates nicely with [[CMake]].

First things first, you gotta get the `benchmark` library set up. If you're using CMake, you can add it as a subdirectory in your project or install it system-wide if that's your vibe.

Time to get down to business. Write some benchmark functions that test the specific parts of your code you want to measure. Think of it like a mini stress test for your functions.

```cpp
#include <benchmark/benchmark.h>

static void MyBenchmarkFunction(benchmark::State& state) {
    // Setup code here

    for (auto _ : state) {
        // Code to benchmark here
    }

    // Teardown code here (optional)
}
BENCHMARK(MyBenchmarkFunction);
```

Compile your benchmarks and run them! Check out the results and see how your code performs. 

Now look for outliers, identify slow spots, and figure out where you can optimise.

#### Tips & Tricks

- **Warm-Up:** Ensure your benchmarks run long enough to warm up the CPU cache and get consistent results.
- **Avoid Optimisations:** Compilers are sneaky and might optimise away your benchmark code. Use `benchmark::DoNotOptimize` to prevent this.
- **Multiple Runs:** Run your benchmarks multiple times to account for variations in performance.


See also:
- [CppCon 2015: Chandler Carruth "Tuning C++: Benchmarks, and CPUs, and Compilers! Oh My!"](https://www.youtube.com/watch?v=nXaxk27zwlk)
- [BENCHMARKING in C++ (how to measure performance)](https://www.youtube.com/watch?v=YG4jexlSAjc&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb&index=76)
- [VISUAL BENCHMARKING in C++ (how to measure performance visually)](https://www.youtube.com/watch?v=xlAH4dbMVnU&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb&index=82)