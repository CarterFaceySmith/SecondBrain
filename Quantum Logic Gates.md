Good luck mate.

## NOT ($x$)
- Standard NOT gate, flips a qubit
- Rotates along the x-axis

## CNOT ($cx$)
- Controlled not, or the Pauli X-gate
- If control state qubit is 1 it will flip the target qubit (pos to neg or whatever), performs an $x$ gate on the target
- Another way of thinking about this is a rotation around the x-axis of the qubit
- This is a bit funky though, because we can have something called [[Phase Kickback]]
	- When there is a superposition on both the control and target qubits, some features of the target superposition can feed back into the control
	- So an alternative interpretation of the $cx$ gate is that it applys a $z$ to control if the target is in state $|->$ and does nothing if in state $|+>$

## Y
- Looks a lot like a CNOT/X gate but with an $i$ in place of the regular 1
- It's basically just a not gate with some $i$ multiple
- Rotates along the y-axis

## Z
- Standard Z gate simply rotates along the z-axis, the vertical

### H (Hadamard)
- This fucker is a quantum beast in nature, it's gonna be everywhere so get comfy
- Transforms a definite quantum state into a superposition of possible quantum states
	- I.e. Takes a defined state and turns it into [[Superposition]]
- Let's say you send a spin-up or spin-down electron through an $h$-gate, it becomes basically a coin standing on its side that will topple only when measured
- It can also be said to reverse the roles of z measurement and x measurement

### Z ($cz$)
- Acts on two qubits, the target and control
- If control state qubit is 1 it will perform a $z$ on the target
	- But wait a second, this is a bit funny, you see if either state is not 1 then technically nothing happens. 

## $R_z$ ($R\phi$)
- Parameterised, it accepts a parameter, like the Y gate
- Accepts $\phi$ and exhibits a rotation around the z-axis by $\phi$ radians

## I
- A variant of the $R_z$ gate above
- Does nothing in particular but can specify a 'none' operation when considering real hardware, from a software point it is more tenuous
- Its matrix is the identity matrix itself

## S
- A variant of the $R_z$ gate above
- Maps $X \to Y$, extending the basic H gate detailed above to make more complex [[Superposition]]
- In a [[Bloch Sphere]] sense it does a $\pi/2$ rotation around the Z axis

## $S^\dagger$ 
- In a [[Bloch Sphere]] sense it does a $-\pi/2$ rotation around the Z axis

## T
- A variant of the $R_z$ gate above
- In a [[Bloch Sphere]] sense it does a $\pi/4$ rotation around the Z axis

## $T^\dagger$ 
- In a [[Bloch Sphere]] sense it does a $-\pi/4$ rotation around the Z axis


See also:
- [[Opaque Quantum Gates]]
- [[Composite Quantum Gates]]
- [[Parameterised Quantum Circuits]] 