## Information

- Paper Title: Encoding seizures with partial synchronisation: A spiking neural network for biosignal monitoring on a mixed signal neuromorphic processor
- Author(s): Jim Bartels, Olympia Gallou, Hiroyuki Ito, Matthew Cook, Johannes Sarnthein, Giacomo Indiveri, and Saptarshi Ghosh
- Year: 2024
- Journal: bioRxiv
- DOI: https://doi.org/10.1101/2024.05.22.595225

### Abstract

Long-term monitoring of biomedical signals is crucial for modern clinical treatment of neurological disorders such as epilepsy. This paper presents a novel spiking neural network (SNN) architecture, co-designed and implemented with a mixed-signal neuromorphic chip, for monitoring epileptic seizures. 

The hardware-aware SNN captures the phenomenon of partial synchronisation within brain activity during seizures. The network is validated on a full-custom mixed-signal neuromorphic hardware using real-time analog signals converted from an Electroencephalographic (EEG) seizure data-set, and encoded as streams of events by an asynchronous delta modulation (ADM) circuit. 

The researchers demonstrate the ability of the hardware SNN to extract local synchronisation patterns from the event streams and show that such patterns can facilitate seizure detection using a simple linear classifier.

### Key Points

- Developed a novel SNN architecture for encoding partial synchronisation in seizures
- Implemented on DYNAP-SE2 mixed-signal neuromorphic chip
- Used Asynchronous Delta Modulation (ADM) to convert EEG signals to event streams
- SNN consists of a "translation" layer and a "non-local non-global" (NLNG) encoding layer
- Demonstrated ability to extract local synchronisation patterns during seizures
- Achieved comparable classification accuracy to original input data using a linear SVM

### Methodology

- Used SWEC-ETHZ iEEG Database for EEG seizure data
- Converted digital EEG data to analog signals using DAC setup
- Processed signals through Analog Front End (AFE) and ADM on DYNAP-SE2 chip
- Implemented two-layer SNN on DYNAP-SE2:
  1. Translation layer with Recurrent Excitatory (R-E), Recurrent Inhibitory (R-I), and Feed-Forward Inhibitory (FF-I) neurons
  2. NLNG encoding layer with specific connectivity structure
- Analysed synchronisation patterns using kernelised spike trains and Manhattan norm calculations
- Used linear Support Vector Machine (SVM) for seizure classification

### Results

- ADM successfully encoded EEG signals into event streams
- Translation layer performed firing-rate based filtering
- NLNG layer encoded correlation between input channels by firing rate
- Observed emergence of partially synchronised clusters during seizure periods
- Achieved classification accuracy between 81.4–91.8% using NLNG layer features
- Performance comparable to classification using original AFE input (83.1–92.9% accuracy)

### Conclusions

- Presented a real-time event-based seizure monitoring system using neuromorphic hardware
- Successfully encoded seizures during ictal periods using inherent dynamical properties of SNN
- Created first human EEG seizure dataset encoded into events using real-time delta-modulator
- Provided foundation for design of always-on embedded low-power neural network computing systems for biomedical signal processing

### Personal Notes

- The use of neuromorphic hardware for seizure detection is an innovative approach that could lead to more efficient, long-term monitoring solutions
- The partial synchronisation encoding method is particularly interesting and may provide new insights into seizure dynamics
- Further research on optimising the NLNG layer and developing on-chip classification methods could improve the system's performance and applicability

### Quotations

> "Rather than following the classical Machine learning (ML) approach of training artificial neural networks (ANNs) with large data-sets, our proposed SNN that is at the same time biologically inspired and (as a consequence) compatible with neuromorphic hardware, amplifies and extracts the intrinsic partial synchronization (i.e., "Chimera") patterns that are present (but not prominent) in the input signals." (Page number not provided)

> "The main contribution of the work described in this article is the development of a foundational network dynamics-based approach for biomedical signal monitoring using mixed-signal neuronal circuits." (Page number not provided)

### References to Follow Up

- Breakspear, M. (2017). Dynamic models of large-scale brain activity. Nature Neuroscience
- Chicca, E., et al. (2014). Neuromorphic electronic circuits for building autonomous cognitive systems. Proceedings of the IEEE
- Richter, O., et al. (2024). DYNAP-SE2: a scalable multi-core dynamic neuromorphic asynchronous spiking neural network processor. Neuromorphic Computing and Engineering

## Literature Review Sections

- Neuromorphic Computing for Biosignal Processing
  - Advantages of neuromorphic approaches for low-power, always-on monitoring
  - Comparison of different neuromorphic hardware platforms for biomedical applications

- Seizure Detection and Classification Methods
  - Traditional machine learning approaches vs. neuromorphic solutions
  - Role of synchronisation patterns in seizure characterisation and detection

## Research Questions

- How does the performance of this neuromorphic system compare to state-of-the-art digital seizure detection methods in terms of accuracy, power consumption, and long-term stability?
- Can the NLNG layer be optimised to improve seizure detection accuracy while maintaining its low-power characteristics?
- Is it possible to develop an on-chip classification method that eliminates the need for offline SVM processing?
- How well does this system generalise to different types of seizures and across a larger patient population?

## Gaps in the Literature

- Limited exploration of long-term stability and performance of the neuromorphic system in real-world conditions
- Lack of direct comparison with other seizure detection methods on the same dataset
- Insufficient investigation of the system's ability to differentiate between different types of seizures
- Limited discussion on the potential for this approach to be applied to other neurological disorders or biosignal processing tasks

## Synthesis

This paper presents a novel approach to seizure detection using neuromorphic hardware, bridging the gap between neuroscience, biomedical engineering, and computer science. By leveraging the inherent dynamics of analog neurons and encoding partial synchronisation patterns, the system offers a promising alternative to traditional digital signal processing methods. 

The use of event-based processing and asynchronous delta modulation aligns well with the nature of neural signals, potentially allowing for more efficient and biologically relevant analysis. While the current implementation shows comparable performance to simple classifiers using the original input data, there is significant potential for improvement through optimisation of the NLNG layer and development of on-chip classification methods.

## Ideas for Future Research

- Develop an on-chip classification method to create a fully integrated neuromorphic seizure detection system
- Investigate the use of multiple NLNG layers or more complex connectivity structures to improve seizure detection accuracy
- Explore the application of this neuromorphic approach to other neurological disorders, such as Parkinson's disease or sleep disorders
- Conduct long-term studies in clinical settings to assess the system's performance and stability over extended periods
- Investigate the potential for this system to provide early warning of impending seizures by analysing pre-ictal synchronisation patterns