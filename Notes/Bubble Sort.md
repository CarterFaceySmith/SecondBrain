A simple sorting algorithm, comparison-based, each adjacent pair is compared and swapped if not in order.

Not too efficient, it has an average and worst-case [[Asymptotic Complexity]] of $O(n^2)$ where $n$ represents the total number of items.

## C++ Pseudo Bubble Sort Implementation
```C++
for (int i = 0; i < len(arr); i++) {
	for (int j = 0; j < len(arr)-1-i; j++) {
		if (arr[j] > arr[j+1]) {
			int temp = arr[j];
			arr[j] = arr[j+1];
			arr[j+1]=temp;
		}
	}
}
```


See also:
- [[Algorithms]]
