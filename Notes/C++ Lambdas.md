An unnamed function defined inline.

Use it whenever you would have a function [[Pointer]], i.e. when you're passing a function to a function.

Example:
```cpp
void ForEach(const std::vector<int> &values, void(*func)(int)){
	for(int value : values)
		func(value);
}

int main(){
	std::vector<int> values = {1,2,3,4,5};
	ForEach(values, [/*params here*/](int value) {std::cout << "Value: " << value << std::endl;});
	std::cin.get();
}
```

Can also assign the lambda to `auto` and just pass that variable in if you wanna keep using it.

Remember scopes, the lambda function can still only access functions within it or passed in via the capture group (the square brackets in the above example).
- `[&]`: [[Pass-by-reference]]
- `[=]`: [[Pass-by-value]]


See also:
- [[C++]]
- [[Functions]]
- [Lambda expressions - cppreference](https://en.cppreference.com/w/cpp/language/lambda)