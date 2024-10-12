## Information

- Paper Title: Intrinsic Biologically Plausible Adversarial Robustness
- Author(s): Matilde Tristany Farinha, Thomas Ortner, Giorgia Dellaferrera, Benjamin Grewe, Angeliki Pantazi
- Year: 2024
- Journal: arXiv preprint
- DOI: Not provided (arXiv preprint)

### Abstract

Artificial Neural Networks (ANNs) trained with Backpropagation (BP) excel in different daily tasks but have a dangerous vulnerability: inputs with small targeted perturbations, also known as adversarial samples, can drastically disrupt their performance. 

Adversarial training, a technique in which the training dataset is augmented with exemplary adversarial samples, is proven to mitigate this problem but comes at a high computational cost. In contrast to ANNs, humans are not susceptible to misclassifying these same adversarial samples. Thus, one can postulate that biologically-plausible trained ANNs might be more robust against adversarial attacks. 

In this work, we chose the biologically-plausible learning algorithm Present the Error to Perturb the Input To modulate Activity (PEPITA) as a case study and investigated this question through a comparative analysis with BP-trained ANNs on various computer vision tasks. 

We observe that PEPITA has a higher intrinsic adversarial robustness and, when adversarially trained, also has a more favourable natural-vs-adversarial performance trade-off. In particular, for the same natural accuracies on the MNIST task, PEPITA's adversarial accuracies decrease on average only by 0.26% while BP's decrease by 8.05%.

### Key Points

- ANNs trained with backpropagation are vulnerable to adversarial attacks
- Biologically-plausible learning algorithms like PEPITA may offer better adversarial robustness
- PEPITA shows higher intrinsic adversarial robustness compared to BP
- PEPITA has a more favourable natural-vs-adversarial performance trade-off when adversarially trained
- PEPITA benefits more from fast adversarial training than BP

### Methodology

- Compared PEPITA and BP on computer vision tasks (MNIST, Fashion-MNIST, CIFAR-10, CIFAR-100)
- Used single fully connected hidden layer with 1024 ReLU neurons and softmax output layer
- Employed MSE loss, momentum SGD optimizer, and early stopping
- Tested with FGSM and PGD adversarial attacks
- Evaluated natural and adversarial performance for both algorithms
- Investigated intrinsic robustness, adversarial training, and fast adversarial training

### Results

- PEPITA shows higher intrinsic adversarial robustness than BP
- For MNIST, PEPITA's adversarial accuracy decreases by 0.26% on average, while BP's decreases by 8.05%
- PEPITA maintains better adversarial performance when trained with weak adversarial samples (FGSM) and tested with strong attacks (PGD)
- PEPITA offers a better trade-off between natural and adversarial performance
- PEPITA benefits more from fast adversarial training than BP

### Conclusions

- Biologically-inspired learning algorithms like PEPITA can lead to ANNs that are more robust against adversarial attacks than BP
- PEPITA's alternative feedback pathway may contribute to its increased adversarial robustness
- The study opens doors for developing safer and more trustworthy AI systems inspired by biologically-plausible learning algorithms

### Personal Notes

- The use of biologically-inspired algorithms for improving adversarial robustness is an interesting approach
- The trade-off between natural and adversarial performance is a crucial consideration in practical applications
- Future work exploring other biologically-plausible algorithms and theoretical understanding of their robustness could be valuable
- The study's limitation to specific adversarial attacks (FGSM and PGD) suggests room for further investigation with other attack methods

### Quotations

> "Unlike BP, PEPITA-trained models can be intrinsically robust against adversarial attacks. That is, naturally trained (i.e., only using natural samples) PEPITA models can be adversarial robust without the computationally heavy burden of adversarial training."

> "We propose that alternative feedback pathways in these algorithms enhance the adversarial robustness of the trained models."

### References to Follow Up

- Dellaferrera, G. and Kreiman, G. (2022). Error-driven input modulation: Solving the credit assignment problem without a backward pass. Proceedings of the 39th International Conference on Machine Learning.
- Madry, A., Makelov, A., Schmidt, L., Tsipras, D., and Vladu, A. (2019). Towards Deep Learning Models Resistant to Adversarial Attacks. arXiv:1706.06083.
- Goodfellow, I., Shlens, J., and Szegedy, C. (2015). Explaining and harnessing adversarial examples. International Conference on Learning Representations.

## Literature Review Sections

- Adversarial Attacks and Defenses in Deep Learning
  - Types of adversarial attacks (FGSM, PGD, etc.)
  - Adversarial training techniques and their limitations

- Biologically-Plausible Learning Algorithms
  - Comparison of various biologically-inspired learning methods
  - Advantages and challenges of biologically-plausible approaches

## Research Questions

- How do other biologically-plausible learning algorithms perform in terms of adversarial robustness?
- What specific properties of PEPITA's alternative feedback pathway contribute to its improved robustness?
- How does PEPITA's performance scale with deeper network architectures and more complex datasets?
- Can insights from PEPITA be used to improve the adversarial robustness of traditional backpropagation-based models?

## Gaps in the Literature

- Limited exploration of adversarial robustness across a wide range of biologically-plausible learning algorithms
- Lack of theoretical understanding of the relationship between alternative feedback pathways and adversarial robustness
- Insufficient investigation of PEPITA's performance on more complex network architectures and datasets
- Limited exploration of PEPITA's robustness against a broader range of adversarial attack methods

## Synthesis

This study bridges the gap between biologically-inspired learning algorithms and adversarial robustness in artificial neural networks. By demonstrating that PEPITA, a biologically-plausible learning algorithm, exhibits superior adversarial robustness compared to traditional backpropagation, the research opens new avenues for developing more secure and reliable AI systems. 

The findings suggest that alternative feedback pathways, a common feature in biologically-inspired algorithms, may play a crucial role in enhancing adversarial robustness. This work not only contributes to the field of adversarial machine learning but also strengthens the case for further exploration of biologically-inspired approaches in AI development.

## Ideas for Future Research

- Investigate the adversarial robustness of other biologically-plausible learning algorithms (e.g., Feedback Alignment, Target Propagation)
- Develop a theoretical framework to explain the link between alternative feedback pathways and adversarial robustness
- Explore PEPITA's performance on more complex network architectures (e.g., convolutional neural networks) and larger datasets
- Investigate PEPITA's robustness against a wider range of adversarial attacks, including black-box and adaptive attacks
- Combine insights from PEPITA with existing adversarial defence techniques to create hybrid, more robust models
- Study the impact of different parameter initialisation schemes and network depths on PEPITA's adversarial robustness