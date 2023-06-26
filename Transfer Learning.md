The main idea is to ***train a new classifier for a new problem, with an existing model***. 

- The problems we are trying to overcome:
	- Training a Deep Neural Network requires a **HUGE** amount of data.
	- Much data might not be available, or could be expensive.

- What are the basic guidelines for such thing?
	- The new problem must be similar to the one the current model already aims to solve. (i.e - taking an already trained model that recognises dogs, and make it also recognise cats).
	- Can we transfer knowledge from the previous problem to the new one?
	- Can we re-use parts of the already trained network?

The last bullet point is the key idea of this method. 

A good modern classifier is constructed from two parts - CNN and FC, where the first one is referred as a **Features Extractor** and the latter as **The Classifier**.

In order to use the existing knowledge:  
- We can drop the FC part, and replace it with a new fresh untrained one. 
- For the CNN part we might want to:
	- Freeze the CNN weights completely during the new training session.
	- Slow the learning rate of the CNN only, so it learns a bit more from the new data, but doesn’t make a significant impact, that might hurt the efficiency of the model.
	- Let it train as usual.