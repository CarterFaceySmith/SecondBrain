So you've got your [[Quantum Logic Gates]], what can you do with them?

A quantum circuit is a routine of quantum operations on quantum data, like [[Qubits]], and concurrent [[Classical Information]]. It is made of, naturally, quantum gates, measures and resets. 

A set of quantum gates is said to be universal ([[Universality]]) if any unitary transformation of the quantum data can be efficiently approximated arbitrarily well as a sequence of gates in the set. Any quantum program can be represented by a sequence of quantum circuits and non-concurrent classical computation.


![Quantum Teleportation Labeled](https://qiskit.org/textbook/ch-algorithms/images/teleportation_labelled.svg)

The above quantum circuit uses three qubits and two classical bits. There are four main components in this quantum circuit, implementing the [[Quantum Teleportation]] [[Algorithms]].

## Pieces of Infinity - The Parts of the Circuit

### Initialisation and Reset
- Start the computation with a well-defined quantum state
- Achieved through initialisation and reset operations:
	- Resets can be performed by a combo of single-qubit gates and concurrent real-time classical computation that will monitor whether we've created the desired state through measurements

### Applying [[Quantum Logic Gates]]
- We then apply a sequence of quantum gates to manipulate the [[Qubits]] as required for whatever we're doing

### Measurements
- We then measure two of the three qubits (in this case), a classical computer interprets the measurements of each qubit as classical outcomes and stores them in the two classical bits
- So basically: measure -> interpret to classical -> store in classical bits

### Classically Conditioned Quantum Gates
- Finally, we apply single-qubit $Z$ and $X$ quantum gates on the third qubit, these gates are conditioned on the results of the measurements that are stored in the previously mentioned classical bits.

## Another Example: VQE

![Variational Quantum Eigensolver Labeled](https://qiskit.org/textbook/ch-algorithms/images/vqe-labeled.png)

Here we can see an example that implements the [[Variational Quantum Eigensolver]] [[Algorithms]].

## An Interesting Note

You might wonder why the classical parts are necessary, after all a quantum computer can do anything a classical computer can in theory right? 

It's the fragility of it though, quantum states are prone to it, that's why for example the information from the quantum circuit is encoded and transmitted classically at the end, it's stable.

See also:
- [[Quantum Logic Gates]]
- [[Parameterised Quantum Circuits]]