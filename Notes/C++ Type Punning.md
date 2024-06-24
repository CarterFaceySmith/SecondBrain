Simply put, this is reinterpreting some data as a different type without allocating new [[Memory]].

```cpp
int main (){
	int a = 50;
	double value = *(double*)&a; 
}
```

The above code assigns `a` to an integer value of 50, then declares a double `value` variable which is assigned as a integer [[Pointer]] to the memory address of `a` (`&a`) cast to a double pointer `(double*)`, this is then dereferenced by the prepended asterisk to get the `double` value at that address.

This is pretty bad though because you have essentially looked four bytes past your integer and used that as the size of a double is 8 bytes vs an integers 4, it won't have written to that memory but it was read from and uninitialised.

A better example is something like the following:

```cpp
struct Entity{
	int x; y;
}
int main(){
	Entity e = {5,8};
	int* position = (int*)&e;
	int y = e.y; /* Alternative */
	int y = *(int*)((char*)&e + 4); /* Insane, don't do this really */
	
	std::cout << position[0] << ", " << position[1] << std::endl;
}
```

*Even better*:

```cpp
struct Entity{
	int x; y;
	int* GetPositions(){
		return &x;
	}
}
int main(){
	Entity e = {5,8};
	int* position = e.GetPositions();
	position[0] = 2; /* No copy memory interpretation */
	
	int y = e.y; /* Alternative */
	int y = *(int*)((char*)&e + 4); /* Insane, don't do this really */
	
	std::cout << position[0] << ", " << position[1] << std::endl;
}
```


See also:
- [[C++]]
- [Type Pruning in C++](https://www.youtube.com/watch?v=8egZ_5GA9Bc&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb&index=66)