## Information

- Paper Title: Neural activity shaping in visual prostheses with deep learning
- Author(s): Domingos Castro, David B Grayden, Hamish Meffin, and Martin Spencer
- Year: 2024
- Journal: [[Journal of Neural Engineering]]
- DOI: https://doi.org/10.1088/1741-2552/ad6186

### Abstract

Objective. The visual perception provided by retinal prostheses is limited by the overlapping current spread of adjacent electrodes. This reduces the spatial resolution attainable with unipolar stimulation. Conversely, simultaneous multipolar stimulation guided by the measured neural responses—neural activity shaping (NAS)—can attenuate excessive spread of excitation allowing for more precise control over the pattern of neural activation. 

However, defining effective multipolar stimulus patterns is a challenging task. Previous attempts focused on analytical solutions based on an assumed linear nonlinear model of retinal response; an analytical model inversion (AMI) approach. Here, we propose a model-free solution for NAS, using artificial neural networks (ANNs) that could be trained with data acquired from the implant. 

Approach. Our method consists of two ANNs trained sequentially. The measurement predictor network (MPN) is trained on data from the implant and is used to predict how the retina responds to multipolar stimulation. The stimulus generator network is trained on a large dataset of natural images and uses the trained MPN to determine efficient multipolar stimulus patterns by learning its inverse model. We validate our method in silico using a realistic model of retinal response to multipolar stimulation. 

Main results. We show that our ANN-based NAS approach produces sharper retinal activations than the conventional unipolar stimulation strategy. As a theoretical bench-mark of optimal NAS results, we implemented AMI stimulation by inverting the model used to simulate the retina. Our ANN strategy produced equivalent results to AMI, while not being restricted to any specific type of retina model and being three orders of magnitude more computationally efficient. 

Significance. Our novel protocol provides a method for efficient and personalized retinal stimulation, which may improve the visual experience and quality of life of retinal prosthesis users.

### Key Points

- Developed an ANN-based approach for neural activity shaping (NAS) in visual prostheses
- The method uses two sequentially trained networks: Measurement Predictor Network (MPN) and Stimulus Generator Network (SGN)
- ANN-based NAS produces sharper retinal activations than conventional unipolar stimulation
- ANN approach matches the accuracy of Analytical Model Inversion (AMI) but is more computationally efficient
- The method is model-free and can be personalised for individual implant users

### Methodology

- Developed two artificial neural networks:
  1. Measurement Predictor Network (MPN): Predicts retinal response to multipolar stimulation
  2. Stimulus Generator Network (SGN): Generates efficient multipolar stimulus patterns
- MPN training:
  - Used simulated data from 10,000 random multipolar stimuli
  - Network architecture: Fully connected ANN with input layer (64 neurons), two hidden layers (128 neurons each), and output layer (64 neurons)
  - Activation function: ReLU for hidden and output layers
- SGN training:
  - Used CIFAR 100 dataset (60,000 32x32 images)
  - Network architecture: Three hidden layers (128 neurons each) with ReLU activation, output layer with hyperbolic tangent activation
  - L2 regularisation applied to output layer
- Simulated retinal model:
  - 10,000 retinal cells and 64 electrodes
  - Linear-nonlinear (LNL) model of retinal response
  - Electrical Receptive Fields (ERFs) modelled as 2D ellipsoidal Gaussians
- Tested under different spread regimes and noise conditions

### Results

- MPN accurately predicted retinal responses to multipolar stimulation
  - Root Mean Square Error (RMSE) typically below 0.06 [a.u.]
- SGN produced effective stimulation patterns
  - Best performance with L2 regularisation lambda of $10^{-3}$
- ANN-based method matched accuracy of AMI approach
  - Mean RMSE differences: 0.005, -0.002, and -0.006 [a.u.] for noise levels of 0, 0.5, and 1 σ, respectively
- ANN method significantly more computationally efficient
  - Inference time for 10,000 images: 23.4 ± 3.7 ms (ANN) vs 69.6 ± 2.0 s (AMI)

### Conclusions

- ANN-based NAS approach produces sharper retinal activations than conventional unipolar stimulation
- Method matches accuracy of AMI while being model-free and computationally efficient
- Approach can be personalised for individual implant users
- Potential to improve visual experience and quality of life for retinal prosthesis users

### Personal Notes

- The use of deep learning for NAS is innovative and addresses limitations of previous analytical approaches
- The model-free nature of the ANN approach makes it more flexible and adaptable to different retinal responses
- The computational efficiency of the ANN method is a significant advantage for real-time applications in implantable devices
- The study's use of a simulated environment allows for thorough testing, but validation in real retinal implants will be crucial
- The method's ability to adapt to different spread regimes and noise conditions is promising for clinical applications

### Quotations

> "Our ANN strategy produced equivalent results to AMI, while not being restricted to any specific type of retina model and being three orders of magnitude more computationally efficient." (Abstract)

> "As general function approximators, ANNs should be capable of handling these irregularities, even if it requires larger networks and more intensive training." (Discussion)

### References to Follow Up

- Maturana M I et al 2016 PLoS Comput. Biol. 12 e1004849
- Spencer M J et al 2019 J. Neural Eng. 16 026008
- Beyeler M et al 2019 Sci. Rep. 9 9199
- Granley J et al 2022 Hybrid Neural Autoencoders for Stimulus Encoding in Visual and Other Sensory Neuroprostheses

## Literature Review Sections

- Neural Activity Shaping (NAS) in Visual Prostheses
  - Previous approaches focused on analytical solutions based on linear-nonlinear models
  - NAS can attenuate excessive spread of excitation and improve spatial resolution
  - Challenges in defining effective multipolar stimulus patterns

- Deep Learning in Visual Prostheses
  - Recent studies have used encoder-decoder frameworks for stimulus pattern generation
  - Previous work focused on accounting for phosphene distortions in epiretinal implants
  - Current study uses deep learning for NAS to solve blurring problem due to overlapping phosphenes

## Research Questions

- How does the performance of the ANN-based NAS approach compare to other methods in real retinal implants?
- Can the ANN method adapt to more complex, non-linear retinal responses that may not be captured by the LNL model?
- How can the ANN approach be optimised to exploit both sides of the non-linearity in the Transfer Function of retinal cells?
- What is the impact of different error metrics (e.g., Structural Image Index) on the performance of the ANN method?

## Gaps in the Literature

- Validation of the ANN-based NAS approach in real retinal implants and with human subjects
- Investigation of the method's performance with more complex retinal response models
- Exploration of online retraining strategies to adapt to long-term changes in retinal response
- Studies on the impact of different MEA configurations and electrode densities on the ANN method's performance

## Synthesis

The development of efficient and personalised stimulation strategies for visual prostheses is crucial for improving the quality of visual perception for implant users. The ANN-based NAS approach presented in this study addresses limitations of previous methods by providing a model-free, computationally efficient solution that can adapt to individual retinal responses. By combining the flexibility of deep learning with the concept of neural activity shaping, this method has the potential to significantly enhance the spatial resolution of retinal prostheses, particularly in high-density electrode arrays where current overlap is a major challenge.

## Ideas for Future Research

- Conduct in vivo studies to validate the ANN-based NAS approach in real retinal implants
- Investigate the performance of the method with more complex retinal response models that incorporate temporal dynamics and cell-type specificity
- Develop online retraining strategies to adapt the ANN models to long-term changes in retinal response
- Explore the use of alternative error metrics, such as Structural Image Index, in the loss function of the ANNs
- Investigate the potential of the ANN-based NAS approach for other types of neural prostheses, such as cochlear implants or cortical visual prostheses