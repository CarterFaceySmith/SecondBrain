## Information

- Paper Title: Neural Dynamics and Seizure Correlations: Insights from Neural Mass Models in a Tetanus Toxin Rat Model of Epilepsy
- Author(s): Parvin Zarei Eskikand, Artemio Soto-Breceda, Mark J. Cook, Anthony N. Burkitt, David B. Grayden
- Year: 2024
- Journal: Not specified (appears to be a preprint or manuscript)
- DOI: Not provided

### Abstract

This study focuses on the use of a neural mass model to investigate potential relationships between functional connectivity and seizure frequency in epilepsy. We fitted a three-layer neural mass model of a cortical column to [[intracranial EEG (iEEG)]] data from a Tetanus Toxin rat model of [[Epilepsy]], which also included responses to periodic electrical stimulation. 

Our results show that some of the connectivity weights between different neural populations correlate significantly with the number of seizures each day, offering valuable insights into the dynamics of neural circuits during [[Epileptogenesis]]. We also simulated single-pulse electrical stimulation of the neuronal populations to observe their responses after the connectivity weights were optimised to fit background (non-seizure) EEG data. 

The recovery time, defined as the time from stimulation until the membrane potential returns to baseline, was measured as a representation of the critical slowing down phenomenon observed in nonlinear systems operating near a bifurcation boundary. The results revealed that recovery times in the responses of the computational model fitted to the EEG data were longer during 5 min periods preceding [[Seizure]]s compared to 1 hr before seizures in four out of six rats. 

Analysis of the iEEG recorded in response to electrical stimulation revealed results similar to the computational model in four out of six rats. This study supports the potential use of this computational model as a model-based biomarker for [[Seizure Prediction]] when direct electrical stimulation to the brain is not feasible.

### Key Points

- Developed a three-layer neural mass model of a cortical column
- Fitted model to iEEG data from a Tetanus Toxin rat model of epilepsy
- Investigated correlations between connectivity weights and daily seizure frequency
- Simulated single-pulse electrical stimulation to observe recovery times
- Compared model results with actual iEEG responses to electrical stimulation
- Proposed potential use of the model as a biomarker for seizure prediction

### Methodology

- Used a neural mass model of three cortical layers (2/3, 4, and 5)
- Each layer consisted of excitatory and inhibitory neuron populations
- Model included synaptic connections within and between layers
- Fitted model to iEEG data using Unscented Kalman Filter (UKF)
- Analysed correlations between model parameters and daily seizure counts
- Simulated single-pulse electrical stimulation in the model
- Compared recovery times 5 minutes before seizures vs 1 hour before seizures
- Analysed actual iEEG responses to electrical stimulation for comparison

### Results

- Some connectivity weights showed significant correlations with daily seizure frequency
- Excitatory-to-Excitatory, Inhibitory-to-Excitatory, and Inhibitory-to-Inhibitory connections mostly showed positive correlations with seizure frequency
- Excitatory-to-Inhibitory connections showed negative correlations with seizure frequency
- Recovery times in the model were longer 5 minutes before seizures compared to 1 hour before in 4 out of 6 rats
- Similar results were observed in actual iEEG responses to stimulation in 4 out of 6 rats
- The model accurately reproduced the original iEEG signals

### Conclusions

- The neural mass model provides insights into the relationship between neural dynamics and seizure activity
- Changes in connectivity strengths correlate with seizure frequency, suggesting potential mechanisms of epileptogenesis
- The critical slowing down phenomenon, observed in both the model and actual iEEG data, may serve as a biomarker for seizure prediction
- The computational model shows potential as a proxy measure for critical slowing down when direct brain stimulation is not feasible

### Personal Notes

- The use of a neural mass model to investigate epilepsy mechanisms is an innovative approach
- The correlation between connectivity weights and seizure frequency provides interesting insights into epileptogenesis
- The observation of critical slowing down in both the model and actual data is promising for seizure prediction
- The discrepancies in results between rats highlight the complexity of epilepsy and the need for further investigation
- The potential use of the model as a [[Biomarker]] without direct brain stimulation could be valuable for non-invasive applications

### Quotations

> "Our results show that some of the connectivity weights between different neural populations correlate significantly with the number of seizures each day, offering valuable insights into the dynamics of neural circuits during epileptogenesis." (Abstract)

> "This study supports the potential use of this computational model as a model-based biomarker for seizure prediction when direct electrical stimulation to the brain is not feasible." (Abstract)

### References to Follow Up

- Trevelyan, A. J., et al. (2006). Modular propagation of epileptiform activity: evidence for an inhibitory veto in neocortex.
- Maturana, M. I., et al. (2020). Critical slowing down as a biomarker for seizure susceptibility.
- Scheffer, M., et al. (2009). Early-warning signals for critical transitions.
- Dehghani, N., et al. (2016). Dynamic balance of excitation and inhibition in human and monkey neocortex.

## Literature Review Sections

- Neural Mass Models in Epilepsy Research
  - Applications of neural mass models to study epilepsy mechanisms
  - Advantages and limitations of using neural mass models for EEG analysis

- Critical Slowing Down in Epilepsy
  - Evidence for critical slowing down as a biomarker for seizure susceptibility
  - Computational and experimental approaches to studying critical slowing down

## Research Questions

- How do changes in specific connectivity weights contribute to the development and progression of epilepsy?
- Can the neural mass model be used to predict seizures in individual patients with sufficient accuracy for clinical use?
- How does the critical slowing down phenomenon relate to other known biomarkers of seizure susceptibility?
- What are the limitations of using neural mass models to study complex neurological disorders like epilepsy?

## Gaps in the Literature

- Limited understanding of the relationship between functional connectivity changes and seizure frequency in epilepsy
- Lack of non-invasive methods for assessing critical slowing down as a biomarker for seizure prediction
- Need for further validation of computational models as proxies for direct brain stimulation in epilepsy research
- Limited exploration of the variability in neural dynamics across different individuals with [[Epilepsy]]

## Synthesis

This study bridges the gap between computational modeling and experimental neuroscience in epilepsy research. By using a neural mass model to analyse iEEG data from a Tetanus Toxin rat model, the authors provide insights into the relationship between functional connectivity and seizure frequency. 

The observation of critical slowing down in both the model and actual data supports the potential use of this phenomenon as a biomarker for seizure prediction. The study also highlights the complexity of epilepsy, as evidenced by the variability in results across different rats. 

The approach of using a computational model as a proxy for direct brain stimulation opens up new possibilities for non-invasive epilepsy research and potential clinical applications.

## Ideas for Future Research

- Extend the neural mass model to include more detailed representations of neuronal subtypes and connectivity patterns
- Investigate the relationship between critical slowing down and other known biomarkers of seizure susceptibility
- Develop and validate the neural mass model for use in human epilepsy patients, comparing results with invasive EEG recordings
- Explore the use of machine learning techniques to improve the accuracy of seizure prediction based on model-derived biomarkers
- Investigate the effects of anti-epileptic drugs on the model parameters and their relationship to seizure frequency