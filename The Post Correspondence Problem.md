# The Post Correspondence Problem

## Definition

Given two sequences of $n$ strings on some alphabet $\Sigma$, e.g.
$$A = w_1, w_2, \dots w_n$$
$$B = v_1, v_2, \dots v_n$$
We can say their exists a post correspondence solution (PC-solution) for pair ($A,B$) if there is a nonempty sequence of integers $i, j, \dots k$ such that:

$$w_iw_j \dots w_k = v_iv_j \dots v_k$$
The Post-correspondence problem is to devise some [[Algorithms]] that tells us for any ($A,B$), whether or not a PC-solution exists.

In general, there is no algorithm for deciding this question under all circumstances, rendering it undecidable.

## Modified Post-correspondence problem

The modified PC-problem is defined the same way as the initial PC-problem, with one exception, in this version the first elements of sequences $A$ and $B$ play a special role, as an MPC solution **must** start with $w_1$ on the left side and $v_1$ on the right side.

Note: If an MPC solution exists, then there is also a PC solution, but the inverse is not true.

This problem is also undecidable.

### Main Difference Between MPCP and PCP?

An instance of MPCP is a set of tiles (just like an instance of PCP), with the additional constraint that a specific tile is denoted as an initial tile that must be used as the first tile in the matching.

See also:
- [[Undecidable Problems]]
- [[Turing Machines]]
- [https://courses.engr.illinois.edu/cs373/sp2009/lectures/lect_26.pdf](https://courses.engr.illinois.edu/cs373/sp2009/lectures/lect_26.pdf)
- 