How do you measure the performance of code you have just written? It's important you are able to compare to previous implementations or get a baseline performance metric in [[Optimisation]] critical code. 

There are many ways to do this based on the language, in this context we will use [[C++]].

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
