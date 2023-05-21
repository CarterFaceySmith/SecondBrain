# Big-O Notation

Used to measure the time complexity ([[Asymptotic Complexity]]) of a function, normally an algorithm but not necessarily limited.

#### Let's get hypothetical with it baby
You are a slave to the corporate dystopia we find ourselves in today and your big boss man requests a 10 petabyte file be transferred to him as fast as possible. Due to constraints with electronic file trasnfer speeds capping out it would literally be faster to get on a plane with the physical drive and hand it over after a journey.

In this scenario the electronic file transfer can be represented as O(s) with s being the size of the file, and the aeroplane transfer can be represented as O(1) as it is always the same length of time to transfer regardless of file size smaller or larger.

You can see that for a small file, it's likely that electronic transfer (linear time complexity) is faster, but as the file size (s) grows there will come a point where it intersects with and then becomes slower than the aeroplane (constant time complexity).

#### Notations
1. O(n): UPPERBOUND, if the algo is O(g(n)), the running time of the algo as n gets larger is at most proportional to g(n);
	1. MEASURES THE WORST CASE TIME COMPLEXITY
2. Θ(n), ASYMPTOTICALLY TIGHT UPPER AND LOWER BOUND, if the algo is Θ(g(n)), the running time of the algo as n gets larger is proportional to g(n);
	1. MEASURES BOTH THE BEST AND WORST CASE TIME COMPLEXITY
3. Ω(n), LOWER BOUND, if the algo is Ω(g(n)), the running time of the algo as n gets larger is at least proportional to g(n)
	1. MEASURES THE BEST CASE TIME COMPLEXITY

#### Tips and Tricks
- Drop the constants in any measure of time complexity, 2n is the same as n.
- Drop the nondominant terms in any measure of time complexity, O(n^3 + n) simply becomes O(n^3).
- When you see a problem where the number of elems in the problem space gets halved each time, its likely to be a O(log n) runtime complexity.
- When to add vs when to multiply:
	- If your algorithm is in the form "do this, then, when you're all done, do that" then you add the runtimes.
	- If your algorithm is in the form "do this for each time you do that" then you multiply the runtimes.

#### Other common notations
1. Constant = O(1)
2. Logarithmic = O(log n)
3. Linear = O(n)
4. n log n = O(n log n)
5. Quadratic = O(n^2)
6. Cubic = O(n^3)
7. Polynomial = n^O(1)
8. Exponential = 2^O(n)


See also:
- [[Asymptotic Complexity]]
- 