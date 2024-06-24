A bit like a class type, similar to a struct, except it can only occupy the memory of one member at a time, it's all the same [[Memory]].

Closely linked to [[C++ Type Punning]].

Means we can have multiple ways of referring to the same thing, e.g. different types.

```cpp
union{
	float a;
	int b;
}
```

If you assign `b` to be 2, and ten print `a` you will see the float representation of 2.

```cpp
struct Vector4{
	union{
		struct{
			float x, y, z, w;
		};
		struct{
			Vector2 a, b;
		};
	};
};
```

The above is valid code and all struct members of the `Vector4` struct occupy the same memory space and can be accessed/modified as per `Vector4Name.x`.


See also:
- [[C++]]
- [[Data Structures]]