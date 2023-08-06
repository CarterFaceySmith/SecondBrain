Alright so it's not *quite* [[Probability]] as we currently understand it to be, in the classical sense that is, [[Quantum Computing]] has probability amplitudes.

So what the fuck is this?

Let's look, so classical probablity has each potential outcome to something represented by a 'probability amplitude', and the magnitude of that amplitude tells us how likely that outcome is to occur.

*QUANTUM* probability amplitudes have one more special boy property: *phase* baby.

## Phase, what?

Think of phase as an angle, so like conventional probability has a magnitude, amplitudes have a direction too, this is represented by a complex number.

![](https://learn.qiskit.org/content/intro/images/what-is/amp-vs-prob.svg)

Pretty odd, even weirder is that if you add two of these amplitudes together they can actually cancel each other out just like positives and negatives do, this is called [[Interference]], a key element of [[Quantum Mechanics]].

Note that we square the magnitudes of our amplitudes to get probabilities.

## How are these represented?

Enter state [[Vectors]].

Remember that for *n* qubits there are $2^n$ possible outcomes, which we can store in lists of length $2^n$ called vectors, simple stuff. Now, since they describe the state of our qubits what would we call them? You guessed it, state vectors.

![[Screen Shot 2022-10-29 at 10.47.18 pm.png]]

These obey the rules of [[Matrix Multiplication]], addition, etc. 


See also:
- [[Quantum Operations]]
