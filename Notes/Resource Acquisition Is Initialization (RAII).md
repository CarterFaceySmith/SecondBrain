A [[C++]] programming technique which binds the life cycle of a resource to the lifetime of an object, e.g. a constructor doing dynamic allocation and having its destructor free that allocation.

```cpp
struct Resource{
	Resource(){ /* Code */}
	~Resource(){/* Code */}
};

int main(){
	std::unique_ptr<Resource> r2(new Resource); /* Auto-freed when ptr out of scope */
}
```

Example with [[Mutex]] locks:

```cpp
void print_func(){
	my_mutex.lock();
	std::cout << "print from thread\n";
	my_mutex.unlock();
}

void better_print_func(){
	std::lock_guard<std::mutex> g(my_mutex);
	std::cout << "print from thread\n";
}

int main(){
	std::thread t1(print_func);
	std::thread t2(print_func);
	t1.join();
	t2.join();

	std::thread t3(better_print_func);
	std::thread t4(better_print_func);
	t3.join();
	t4.join();
}
```


See also:
- [[Pointer]]
- [[Smart Pointers]]