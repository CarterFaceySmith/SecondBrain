# Turing Machines

## Basic Concept

Let's say you take an [[Automata]] (finite state) and add a ticker tape to it that is infinite in both directions, you keep the input as a string and the output as a yes or no.

This string is processed as dictated by the machine, with the memory being the *current machine state* and the tape. The output is then based on the last state reached (the halt state).

You have a start cell, the machine then reads the cell, can alter or not alter the contents depending on the cell contents read, then can move left (commonly L) or right (commonly R) by one cell.

A turing machine, is a bit cooked, because with it you can effectively perform any calculation any other programmable computer can as long as you're willing to spend enough time on the machine, this is Church-Turing hypothesis.

Note: Due to this, a multi tape turing machine or any variant is effectively no less capable than a single tape turing machine.

*Another fucking note*: You can have a turing machine be an input to a turing machine, but again, it can be represented by a single tape machine.

A *universal turing machine* is a turing machine that can simulate another on some input. E.g. you feed in an turing machine encoded turing machine into another which decodes it and simulates it.

## Mathematical Definition

A Turing Machine is a 4-tuple: $(Q,\Lambda,q_0,\delta)$

1. Q is a finite set of states incl. the halt state 'h'
2. $\Lambda$ is an alphabet which includes the blank symbol '#'
3. $q_0 \in Q$ is the start state
4. $\delta$ is the transition function
	- An example is if it was $\delta(q, \sigma) = (r, d, r)$ 
		- This means that when the turing machine in in state q, and reads the symbol $\sigma$, it writes the symbol r, and moves one cell in the direction d, then enters state r.

## Turing-acceptable

You've got an alphabet $\Sigma$ that doesnt contain # and a language L over it. L is turing-acceptable if:

There's a turing machine:
$$M=(Q, \Lambda, q_0, \delta)$$
	- Such that:
		- $\Sigma \subseteq \Lambda$
		- And for each $w \in \Sigma*$, when M is run with input w it halts if and only if $w \in L$  


## The Limit of Algorithmic Computation

### Computability and Decidability

#### Turing-computable

A.K.A Computability

Let's say you've got $\Sigma$ and $\Gamma$ which are *alphabets* that don't contain #, and that f is a function from $\Sigma*$ to $\Gamma*$. 

We say f is *turing-computable* if there's a turing machine:
$$M=(Q, \Lambda, q_0, \delta)$$
Such that, $\Sigma \subseteq \Lambda$ and $\Gamma \subseteq \Lambda$ and for each string $w \in \Sigma*$, when M isrun with input w it halts with output f(w). 

We then say M *computes* the function f.

#### Turing-decidable

Alright big man, let's go.

You've got an alphabet $\Sigma$ that doesnt contain # and a language L over it. L is turing-decidable if:
- There's a turing machine:
$$M=(Q, \Lambda, q_0, \delta)$$
	- Such that:
		- $\Sigma \subseteq \Lambda, (0, 1) \subseteq \Lambda$
		- And for each $w \in \Sigma*$, when M is run with input w it halts with output $\chi L(w)$ 
			- What the fuck does this mean? It means it halts with ouput 0 or 1 and the output is 0 if w isnt in L and 1 if it is. We then say M *decides* the language L.

## [[The Halting Problem]]


See also:
- [[Automata]]
- [[Computer Science Fundamentals]]