Alright, let's break down Kadane's algorithm in simple terms. It's a method used to find the maximum subarray sum within an [[Arrays]] of numbers. Here's how it works:

1. Start by scanning through the array from left to right.
2. Keep track of two values: the maximum subarray sum seen so far and the current subarray sum.
3. As you move along the array:
    - Add the next element to the current subarray sum.
    - If the current element is greater than the current subarray sum, start a new subarray from that element.
4. Whenever you find a new maximum subarray sum, update the record.
5. Keep doing this until you've scanned through the entire array.
6. At the end, you'll have the maximum subarray sum.

That's Kadane's algorithm in a nutshell. It's like searching for the biggest prize within the array, one step at a time.


See also:
- [[Dynamic Programming]]