Long Short-Term Memory (LSTM) networks are a type of [[Recurrent Neural Networks (RNN)]] designed to remember data over long periods of time. 

Unlike standard RNNs, which can struggle with learning long-term dependencies due to the vanishing gradient problem, LSTMs are designed to handle this like a champ.

More or less though these strictly improve the concept of [[Recurrent Neural Networks (RNN)]], and are therefore used for the same tasks like sequencing.

## How do they work?

An LSTM network is composed of LSTM cells, each of which includes a cell state and three gates: an input gate, a forget gate, and an output gate. The cell state acts like a conveyor belt, carrying information along the sequence. The gates control the flow of information into, out of, and within the cell.

- **Input Gate**: Decides what new information will be stored in the cell state.
	- $i_t = σ(θ_{xi}x_t + θ_{hi}h_{t−1} + b_i)$
	- New cell state from $tanh(−1, 1)$
- **Forget Gate**: Decides what information gets thrown away from the cell state.
	- $ft = σ(θ_{xf}x_t + θ_{hf}h_{t−1} + b_f )$. 
	- Sigmoid = output between 0 (forget) and 1 (keep)
- **Output Gate**: Decides what information the cell outputs based on its current state.
	- $o_t = σ(θ_{xo}x_t + θ_{ho}h_{t−1} + b_o)$
	- Multiplied with output from $tanh(−1, 1)$ in actual output

Cell update: $gt = tanh(θ_{xg}x_t + θ_{hg}h_{t−1} + b_g)$

LSTM solved the vanishing gradient problem because:
- $f_t$ are outputs of a sigmoid and therefore 1 for important information.  
- Activation functions act through a summation, therefore vanishing gradients are not propagated through the whole cell state.

Note: Input, states, and gates are not limited to 1st-order tensors. Gate functions can consist of FC and CNN layers.

![[Screenshot 2023-07-07 at 8.58.36 pm.png]]

## Why are they useful?

LSTMs are particularly useful for tasks that involve sequential data with long-term dependencies, like language translation, speech recognition, and time series prediction. 