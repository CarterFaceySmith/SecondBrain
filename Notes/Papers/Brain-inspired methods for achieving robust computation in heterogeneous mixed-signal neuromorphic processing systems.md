## Information

- Paper Title: Brain-inspired methods for achieving robust computation in heterogeneous mixed-signal neuromorphic processing systems
- Author(s): Dmitrii Zendrikov, Sergio Solinas, Giacomo Indiveri
- Year: 2023
- Journal: [[Neuromorphic Computing and Engineering Journal]]
- DOI: https://doi.org/10.1088/2634-4386/ace64c

### Abstract

Neuromorphic processing systems implementing spiking neural networks with mixed signal analog/digital electronic circuits and/or memristive devices represent a promising technology for edge computing applications that require low power, low latency, and that cannot connect to the cloud for off-line processing, either due to lack of connectivity or for privacy concerns. 

However, these circuits are typically noisy and imprecise, because they are affected by device-to-device variability, and operate with extremely small currents. So achieving reliable computation and high accuracy following this approach is still an open challenge that has hampered progress on the one hand and limited widespread adoption of this technology on the other. By construction, these hardware processing systems have many constraints that are biologically plausible, such as heterogeneity and non-negativity of parameters. More and more evidence is showing that applying such constraints to artificial neural networks, including those used in artificial intelligence, promotes robustness in learning and improves their reliability. 

Here we delve even more into neuroscience and present network-level brain-inspired strategies that further improve reliability and robustness in these neuromorphic systems: we quantify, with chip measurements, to what extent population averaging is effective in reducing variability in neural responses, we demonstrate experimentally how the neural coding strategies of cortical models allow silicon neurons to produce reliable signal representations, and show how to robustly implement essential computational primitives, such as selective amplification, signal restoration, working memory, and relational networks, exploiting such strategies. 

We argue that these strategies can be instrumental for guiding the design of robust and reliable ultra-low power electronic neural processing systems implemented using noisy and imprecise computing substrates such as subthreshold neuromorphic circuits and emerging memory technologies.

### Key Points

- Neuromorphic systems face challenges due to device variability and noise in mixed-signal circuits
- Brain-inspired strategies can improve robustness and reliability in these systems
- Population averaging effectively reduces variability in neural responses
- Cortical model-inspired neural coding strategies produce reliable signal representations
- Robust implementation of computational primitives like selective amplification and working memory
- Strategies can guide design of ultra-low power neural processing systems using imprecise substrates

### Methodology

- Used DYNAP-SE multi-core neuromorphic processor for experiments
- Measured device mismatch effects in neuron and synapse circuits
- Implemented population coding and soft Winner-Take-All (sWTA) networks
- Tested strategies for averaging across space and time
- Evaluated recurrent excitation and inhibition in neural clusters
- Implemented relational networks using coupled sWTA networks
- Measured and analysed chip performance using various neural coding strategies

### Results

- Population averaging reduced variability in neural responses, following 1/√N scaling
- Combining longer integration times with small clusters achieved 8-bit equivalent precision
- Recurrent excitation and inhibition improved signal representation and reduced correlations
- sWTA networks demonstrated selective amplification, signal restoration, and working memory
- Relational networks successfully implemented using coupled sWTA networks
- Brain-inspired strategies improved robustness and reliability in neuromorphic systems

### Conclusions

- Brain-inspired computational strategies effectively mitigate device variability and noise
- Population coding and sWTA networks offer robust signal representation and processing
- These strategies provide additional benefits like speed, coding efficiency, and power savings
- The approach allows flexible trade-offs between precision, area, and power consumption
- Brain-inspired methods can guide the design of reliable ultra-low power neuromorphic systems

### Personal Notes

- The use of population coding to mitigate device variability is particularly interesting
- The trade-off between cluster size, integration time, and precision offers flexible design options
- The implementation of working memory and relational networks demonstrates the potential for complex computations
- The approach seems promising for edge computing applications with strict power and latency requirements
- Further exploration of on-chip learning and plasticity mechanisms could enhance adaptability

### Quotations

> "By construction, these hardware processing systems have many constraints that are biologically plausible, such as heterogeneity and non-negativity of parameters." (Page 2)

> "We argue that these strategies can be instrumental for guiding the design of robust and reliable ultra-low power electronic neural processing systems implemented using noisy and imprecise computing substrates such as subthreshold neuromorphic circuits and emerging memory technologies." (Page 2)

### References to Follow Up

- Mead C 1990 Neuromorphic electronic systems Proc. IEEE 78 1629–36
- Douglas R J and Martin K A 2007 Recurrent neuronal circuits in the neocortex Curr. Biol. 17 R496–500
- Indiveri G and Sandamirskaya Y 2019 The importance of space and time for signal processing in neuromorphic agents IEEE Signal Process. Mag. 36 16–28

## Literature Review Sections

- Neuromorphic Computing for Edge Applications
  - Advantages and challenges of mixed-signal neuromorphic systems
  - Comparison with traditional digital computing approaches

- Biologically Inspired Computational Strategies
  - Population coding and averaging in neural systems
  - Excitatory-Inhibitory balance and its computational benefits

## Research Questions

- How do the proposed brain-inspired strategies scale with increasing network size and complexity?
- What are the limitations of these approaches for different types of computational tasks?
- How can on-chip learning and plasticity mechanisms be integrated with these strategies to enhance adaptability?
- What are the trade-offs between energy efficiency, computational capability, and robustness in these neuromorphic systems?

## Gaps in the Literature

- Limited exploration of the interaction between brain-inspired strategies and emerging memory technologies
- Lack of comprehensive comparison with state-of-the-art digital neuromorphic systems across various benchmarks
- Insufficient investigation of the applicability of these strategies to more complex cognitive tasks
- Limited discussion on the integration of these approaches with conventional machine learning frameworks

## Synthesis

This paper presents a compelling case for using brain-inspired computational strategies to address the challenges of variability and noise in mixed-signal neuromorphic systems. By leveraging population coding, excitatory-inhibitory balance, and soft Winner-Take-All networks, the authors demonstrate how robust and reliable computation can be achieved using imprecise and noisy hardware substrates. 

The approach offers a promising path forward for ultra-low power edge computing applications, potentially enabling complex neural processing in resource-constrained environments. 

The flexibility of the approach, allowing trade-offs between precision, area, and power consumption, makes it particularly attractive for a wide range of applications. However, further research is needed to fully explore the scalability of these methods and their integration with emerging memory technologies and learning mechanisms.

## Ideas for Future Research

- Investigate the integration of the proposed strategies with memristive devices for synaptic plasticity
- Explore the use of these brain-inspired methods in multi-modal sensor fusion for edge computing
- Develop benchmarks specifically designed to evaluate the robustness and efficiency of neuromorphic systems
- Study the applicability of these strategies to neuromorphic systems implemented with different process technologies
- Investigate the potential of combining these approaches with conventional deep learning methods for hybrid systems