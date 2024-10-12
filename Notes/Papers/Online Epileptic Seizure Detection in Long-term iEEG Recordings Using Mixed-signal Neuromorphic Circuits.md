## Information

- Paper Title: Online Epileptic Seizure Detection in Long-term iEEG Recordings Using Mixed-signal Neuromorphic Circuits
- Author(s): Olympia Gallou, Jim Bartels, Saptarshi Ghosh, Kaspar Schindler, Johannes Sarnthein, Giacomo Indiveri
- Year: 2024
- Journal: [[medRxiv]]
- DOI: https://doi.org/10.1101/2024.06.13.24308876

### Abstract

This paper presents a mixed-signal hardware implementation of a biologically realistic [[Spiking Neural Network (SNN)]] for always-on monitoring with online [[Seizure]] detection. The system was validated using wideband [[Electroencephalography (EEG)]]signal recordings with over 122 continuous hours of data, without pre-filtering. 

The network was tested with a cohort of 5 patients and a total of 22 seizures including generalised and focal onsets. The system effectively captures spatiotemporal features based on synchronised multichannel intracranial EEG activity, achieving 100% sensitivity across all patients and near zero false alarms. 

Notably, inference across patients required only calibrating the parameters of the network's output layer on a single recorded seizure from the patient.

### Key Points

- Developed a mixed-signal hardware SNN for online seizure detection
- Used adaptive Asynchronous Delta Modulator (ADM) for signal encoding
- Implemented on DYNAP-SE neuromorphic processor
- Tested on long-term iEEG recordings from 5 patients with 22 seizures
- Achieved 100% sensitivity and near-zero false alarm rate
- Required minimal calibration (single seizure) for each patient

### Methodology

- Used SWEC-ETHZ iEEG database for long-term recordings
- Implemented adaptive ADM for signal encoding
- Designed SNN architecture with two layers:
  1. Hidden layer with excitatory and inhibitory neuron ensembles
  2. Output layer with inhibitory cluster and readout neuron
- Configured SNN on DYNAP-SE neuromorphic processor
- Analysed synchronisation using correlation matrices and coincidence index
- Evaluated performance using sensitivity, false alarm rate, and detection delay

### Results

- Achieved 100% sensitivity across all patients
- Near-zero false alarm rate (0.07/hour on average)
- Mean detection delay of 18.8 seconds
- Estimated average power consumption of 12.48 μW
- Demonstrated effective capture of synchronisation features during seizures

### Conclusions

- Demonstrated feasibility of long-term reliable seizure monitoring on a resource-constrained neuromorphic chip
- Addressed challenges of high false alarm rates and power consumption
- Paved the way for closed-loop neuromodulation System-on-Chip (SoC)
- Future work aims to reduce detection delay and develop dedicated ultra-low power ASIC

### Personal Notes

- The use of adaptive ADM for signal encoding is a clever approach to handle long-term recordings with varying signal amplitudes
- The SNN architecture's ability to capture synchronisation features is impressive and biologically plausible
- The low power consumption and high sensitivity make this approach promising for implantable devices
- Further research on reducing detection delay could significantly improve the system's clinical utility

### Quotations

> "Event-based neuromorphic devices have emerged as promising candidates for enabling energy-efficient biosignal monitoring and computation at the edge" (Page 2)

> "Our proposed solution effectively addressed two common challenges: high FAR and power consumption." (Page 4)

### References to Follow Up

- Sharifshazileh, M., et al. (2021). An electronic neuromorphic system for real-time detection of high frequency oscillations (HFOs) in intracranial EEG. Nature Communications
- Moradi, S., et al. (2018). A scalable multicore architecture with heterogeneous memory structures for dynamic neuromorphic asynchronous processors (DYNAPs). IEEE Transactions on Biomedical Circuits and Systems
- Donati, E., & Indiveri, G. (2023). Neuromorphic bioelectronic medicine for nervous system interfaces: From neural computational primitives to medical applications. Progress in Biomedical Engineering

## Literature Review Sections

- Neuromorphic Computing for Biosignal Processing
  - Advantages of event-based processing for long-term monitoring
  - Comparison of different neuromorphic hardware platforms for EEG analysis

- Seizure Detection Algorithms and Devices
  - Traditional machine learning approaches vs. neuromorphic solutions
  - Performance metrics and challenges in long-term seizure monitoring

## Research Questions

- How does the performance of this neuromorphic system compare to state-of-the-art digital seizure detection methods in clinical settings?
- Can the detection delay be reduced while maintaining high sensitivity and low false alarm rates?
- How well does the system generalise to different types of seizures and patients not included in the initial cohort?
- Is it possible to incorporate online learning mechanisms to improve performance over time?

## Gaps in the Literature

- Limited exploration of the system's performance on different types of seizures (e.g., absence seizures)
- Lack of direct comparison with other commercial seizure detection devices
- Insufficient investigation of the system's long-term stability and performance drift
- Limited discussion on the potential for this approach to be applied to non-invasive EEG recordings

## Synthesis

This paper presents a significant advancement in the field of neuromorphic computing for biosignal processing, specifically in the context of epileptic seizure detection. By leveraging the inherent characteristics of mixed-signal neuromorphic hardware, the researchers have developed a system that addresses two major challenges in long-term seizure monitoring: high false alarm rates and power consumption. 

The use of adaptive encoding and a carefully designed SNN architecture allows for efficient processing of long-term iEEG recordings, achieving perfect sensitivity and near-zero false alarms across multiple patients. 

This approach demonstrates the potential of neuromorphic systems to enable always-on, low-power monitoring solutions that could significantly improve the quality of life for epilepsy patients.

## Ideas for Future Research

- Investigate the incorporation of online learning mechanisms to adapt the SNN to patient-specific seizure patterns over time
- Explore the application of this neuromorphic approach to non-invasive EEG recordings for broader clinical use
- Develop a fully integrated system-on-chip combining the adaptive ADM, SNN, and potential stimulation circuitry for closed-loop neuromodulation
- Conduct long-term clinical trials to assess the system's performance and stability over extended periods (months to years)
- Investigate the potential of this approach for detecting or predicting other neurological events beyond epileptic seizures