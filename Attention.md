A [[Deep Learning]] concept wherein only local nodes connect to the output node, not all given nodes in the previous layer. This is done via weighting each input to augment their importance to the output node.

Used in [[Transformer]]s and many other models if needed.

## The Architecture

### High-level Concept

- A decoder processes the information given:
	- Previous decoder hidden state
	- Previous output
	- Attention

### Multi-head Attention

Given a query $Q$, we need to basically find the most similar key $K$ and the value $V$ that corresponds to that key.

$$Attention(Q,K,V)=softmax(\frac{QK^T}{\sqrt{d_k}})V$$
We are multiplying our query by keys then normalising by it's respective dimension $d_k$ here.

Note $QK^T$ is simply the dot product between $QK^1,QK^2\dots QK^T$.

So multi-head attention is the ability to select multiple things at once and determine what is important.

## Attention vs. Convolution Example

![[Screenshot 2023-07-07 at 9.11.12 pm.png]]