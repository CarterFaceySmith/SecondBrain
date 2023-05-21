A [[Quantum Algorithms]] that demonstrated advantages over classical computers.

## Concept
There is a function returning the bitwise product of the input with a hidden string of bits 𝑠. Its length is 𝑛.

$$𝑓(𝑥)=𝑠⋅𝑥(mod2)$$

To find the hidden string, we would need to call the function 𝑓 for 𝑛 times. 

However, using a quantum computer, we can solve this problem with 100% confidence after **only one call** to the function. 

The quantum Bernstein-Vazirani algorithm to find the hidden bit string is very simple:

1. Initialize the inputs qubits to the state |0⟩⊗𝑛, and output qubit to |−⟩-   .
2. Apply Hadamard gates to the input register
3. Query the oracle
4. Apply Hadamard gates to the input register
5. Measure