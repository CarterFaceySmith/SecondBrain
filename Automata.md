# Automata

### What's an Automaton mate? AKA Finite State Machines

An *abstraction* of a computer, basically a model or representation of some sort of a computer and its functions.

##### Ya mumma's standard Automaton functions:
- Can read input
- Can produce output
- May have temporary storage of some sort
- Has a control unit that is in a internal state at any given time, these iternal states could be any number of things/variations and change in a defined manner

##### Deterministic and nondeterministic:
A deterministic automaton has each move be uniquely determined by the current state  and machine configuration. It's *predictable*.

A nondeterministic automaton has several possible moves at any one point, it's a wily bugger. Only a set of the possible actions can be predicted.

See more: [[Nondeterminism]]

### Why should you give a fuck about this?

Automata are the basis of most computational functions at some of the lowest levels imaginable, for example, a 'binary adder' that takes two bit strings and produces their sum as output is crucial to computing. This is a great example of something commonly represented by an automata.

Think of automata like lego pieces that have very defined specific functions, inputs and outputs, by piecing these pieces together carefully and crafting an elegant system, we can make any program we desire. The scale can be microscopic as is the case in the 'binary adder' above, or massive.

If you can figure out a language L = { all legal C++ programs that will not go into infinite loops on any input} then it'd be possible to write so called *uber-compilers* that do semantic error checking as well as the syntactic error checking they currently do.

Note: Could you also do this by deliberately making a limited new language with set ways of writing things so what is to be expected can easily be figured out and predicted?


### Mathematical definition 
$$
M =\ <Q, \Sigma, \delta, q_0, F>
$$
#### Deterministic
Q = the possible states, normally written as Q0, Q1... (finite)
$\Sigma$ = the alphabet of the machine (input alphabet)
$\delta$  = Q x Sigma $\to$ Q
$Q_0$ = the machine starting state
F = Final states (AKA accept states), a subset of all possible states

#### Non-deterministic 
Q = the possible states, normally written as $Q_0, Q_1\dots$
$\Sigma$ = the alphabet of the machine
$\delta$ = Q x $\Sigma$ $\to$ $2^Q$ (non-deterministic [[Transition Function]])
$Q_0$ = the machine starting state
F = Final states (AKA accept states), a subset of all possible states

**Note**:
	Something rather *groovy* is combining automata, ie making one of the states of a 'mother' automata the final states of a 'child' automata.  
	For example you want an automata that only accepts strings accepted by two sub-automata so you make path states that match the accept states of the sub-automata. 
	See page 165 of Foundations of Computation for an example.

## Converting Between DFA and NFA

1. Start with $\lambda$ closure for each state in the NFA
2. Generate transition table
3. Initial state of DFA is the $\lambda$ closure of the initial state of the NFA
4. Construct DFA and keep adding states until all transitions are to existing states

JFLAP also can convert these for you in a pinch.

See week 6 lecture notes for additional information.


See also:
- [[Formal Languages and Grammar]]
- [[Computer Science Fundamentals]]
- https://www.youtube.com/watch?v=zF3RjLpYMUE
- [[Pumping Lemma]]
- https://www.javatpoint.com/automata-conversion-from-nfa-to-dfa
- 
