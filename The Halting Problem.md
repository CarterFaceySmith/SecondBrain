# The Halting Problem

What is it?

Simple. 

Given a [[Turing Machines]] $M$ and input $w$, does $M$, when started in state $q_0w$, perform a computation that eventually halts?

The domain of this problem is the set of all Turing machines and all $w$, we are looking for one machine that will prove whether or not the computation of $M$ applied to $w$ will halt.

The halting problem is undecidable.

## Reducing One Undecidable Problem to Another

We say that Problem $A$ is **reduced** to a problem $B$ if the decidability of $A$ follows from the decidability of $B$. So, if we know that $A$ is undecidable, we can conclude $B$ is too.


See also:
- [[Turing Machines]]
- [[Proofs]]
- https://www.cs.odu.edu/~toida/nerzic/390teched/computability/unsolv-1.html
- [[Undecidable Problems]]