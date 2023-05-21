A type of [[Deep Learning]] [[Machine Learning]] model.

Used commonly for [[Natural Language Processing (NLP)]] tasks.

The main idea behind transformer models is that they use a self-attention mechanism to weigh the importance of different words in a sequence. This means that the model can pay more attention to the words that are most relevant to the task at hand, rather than treating all words equally. The self-attention mechanism also allows the model to process sequences of variable lengths, which is important for NLP tasks where the length of the input can vary.

Transformer models consist of an encoder and a decoder. The encoder processes the input sequence and produces a hidden representation, which is then used by the decoder to generate the output sequence. During training, the model learns to predict the correct output sequence based on the input sequence and a set of target output sequences.

The self-attention mechanism works by computing a set of attention scores between all pairs of words in the input sequence. Each attention score represents the importance of one word in the input sequence relative to all the other words. These attention scores are used to compute a weighted sum of the input words, which produces a new representation of the input that is more focused on the most relevant words.


See also:
- https://www.youtube.com/watch?v=4Bdc55j80l8



