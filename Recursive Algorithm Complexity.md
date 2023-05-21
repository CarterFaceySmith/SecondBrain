# Recursive Algorithm Complexity

### Steps to analyse recursive algorithms, made simple for one neuron mfers

1. Identify input size of the initial problem, find total num. of subprobs. and identify input size of those subprobs.;
2. Write the recurrence relation for the time complexity;
	1. Define time complexity of larger problem in terms of input size;
	1. Define time complexity of subprobs. in terms of input size;
	1. Analyse worst-case time complexity of any additional operations; 
	1. Add the time complexities of the subprobs. and additional operations to get the overall time complexity func. (T(n));
	1. Define the time complexity of the base case, ie the smallest ver. of the subprob., this is a crucial step to be defined correctly as the recurrence depends on this.
3. Solve the recurrence relation to get the total time complexity.
	1. Normally done through one of two methods:
		1. Recursion Tree Method; or
			1. The fundamental approach.
		1. Master Theorum Method.
			1. Works best for divide and conquer recurrence.

### What's a recurrence relation mate

A recurrence relo. represents a sequence of terms that results from recursion. Ie. any term is defined in terms of its previous terms.

Normally we find T(n) if we have k num. of subproblems as follows:

T(n) = T(input size of subprob. 1) + T(input size of subprob. 2) + ... T(input size of subprob. k) + time complexity of additional operations other than recursive calls

We then solve this recurrence relation and calculate the overall time complexity in terms of [[Big-O Notation]].


See also:
- [[Algorithms]]
- [[Algorithmic Complexity]]
- https://www.enjoyalgorithms.com/blog/time-complexity-analysis-of-recursion-in-programming

