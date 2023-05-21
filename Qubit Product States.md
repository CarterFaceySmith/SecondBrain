A kind of multi-qubit state, representing cases that could be written as as sequence of [[Qubits]] states. 

$|+0>$

Let's start with two general single-qubit product states.

![[Screen Shot 2022-10-30 at 1.45.42 pm.png]]

We're going to use $|ba>$ to refer to the product combined state of these two states, this can be written as follows:

$$|ba> = [b_0a_0,b_0a_1,b_1a_0,b_1a_1]$$
Note the normal notation is limited by Latex commands here and the $ba$ pairs are normally on seperate lines with the brackets around the whole matrix.

## That's great and all, but how do we use this?

The practicality of this stems from probability calculations, you see, if we want to find the probability of two unrelated things occuring we multiply their probabilities together.

With [[Quantum Mechanics]] we multiply their [[Probability Amplitudes]].

So the amplitude of state 00 is the amp. of qubit $a$ being 0 multiplied by the amplitude of qubit $b$ being 0.

![[Screen Shot 2022-10-30 at 1.57.05 pm.png]]

## Entangled states?

Let's get ready for some Jada Smith style [[Entanglement]].

Quantum computations generally start in a product state where all qubits are in the state |0>.

We can then apply single qubit gates to manipulate these single qubit states, rotating them, but they will remain in a product state.

To create entanglement we apply multi-qubit gates ([[Quantum Logic Gates]]), e.g cx (CNOT) or cz (performs a Z gate on the target qubit if the control qubit is 1) gates.

Note that the control qubit is the left qubit and the right qubit is the target: $|00>$

So we can do $qc.cx(1,0)$ to generate an entangled [[Quantum Circuits]] using Qiskit, where the two singular qubits are passed through a cx gate resulting in entanglement demonstrated below.

![[Screen Shot 2022-10-30 at 6.58.36 pm.png]]

