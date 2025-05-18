## Information

- Paper Title: Predicting Antiseizure Medication Outcomes in Early Diagnosed Epilepsy: A Multimodal Framework Using EEG, MRI, and Clinical Data
- Author(s): Duong Nhu, Jiahe Liu, Richard Shek-kwan Chang, Daniel Thom, Zhibin Chen, Mohamad Nazem-Zadeh, Alison Anderson, Sarah Barnard, Jacqueline French, Patrick Kwan, and Zongyuan Ge
- Year: 2025
- Journal: medRxiv (preprint)
- DOI: https://doi.org/10.1101/2025.03.12.25323644

### Abstract

The paper presents a multimodal deep learning framework for predicting antiseizure medication (ASM) outcomes in patients with newly diagnosed epilepsy. The proposed approach integrates electroencephalography (EEG), magnetic resonance imaging (MRI), clinical factors, and molecular drug features to enhance prediction accuracy. 

The framework includes EEG Q-Net, a pre-trained quantisation model that captures fine-grained temporal EEG patterns, and MRI embeddings from BiomedCLIP. For ASMs, the researchers employed pre-trained models to generate embeddings for SMILES (Simplified Molecular Input Line Entry System) notations, capturing chemical similarities and interactions. 

The multimodal fusion model achieved an AUC of 0.75, demonstrating superior performance compared to the best unimodal model (0.71), highlighting the benefits of multimodal integration for personalised epilepsy management.

### Key Points

- Proposed multimodal framework integrates EEG, MRI, clinical data, and molecular drug features
- Developed EEG Q-Net for capturing temporal patterns in EEG signals
- Used BiomedCLIP for extracting features from MRI scans
- Employed pre-trained models for generating SMILES embeddings of ASMs
- Multimodal approach outperformed individual modalities for ASM outcome prediction
- System designed to be easily translatable to clinical practice using routinely collected data

### Methodology

- Dataset combined patients from Human Epilepsy Project (HEP1) and Alfred Health Hospital in Australia
- Developed EEG Q-Net framework with quantisation representation, masking, and context learning using Structured State Space models (S4)
- Extracted SMILES notations for ASMs from Drugbank
- Tested two SMILES embedding approaches: MoLER (graph-based) and Molecular Transformer Embeddings (MTE)
- Employed BiomedCLIP, a vision-language foundation model, to extract features from MRI scans
- Compared single-view (axial) vs multi-view (axial, coronal, sagittal) MRI approaches
- Used multilayer perceptron (MLP) fusion architecture to combine modality-specific embeddings
- Optimised AUC directly using compositional AUC loss with Primal-Dual Stochastic Compositional Adaptive optimiser

### Results

- Multimodal approach achieved best performance with AUC of 0.75 (SD: 0.07)
- Clinical factors with SMILES embeddings achieved AUC of 0.71 for both MoLER and MTE
- SMILES embeddings outperformed ASM one-hot encoding (AUC: 0.68)
- EEG embeddings achieved AUC of 0.64
- MRI multi-view embeddings achieved AUC of 0.69
- Combination of EEG embeddings with clinical factors improved AUC to 0.74
- While EEG and MRI models had lower AUCs than clinical-factor models, the best EEG models had higher precision

### Conclusions

- Integration of multiple data modalities enhances ASM outcome prediction compared to unimodal approaches
- SMILES embeddings provide a more effective representation of drugs than one-hot encoding
- Multi-view MRI approach captures more comprehensive structural information than single-view
- The framework can be adapted for ASM selection by using prediction probabilities to guide treatment decisions
- Multimodal approach lays foundation for personalised epilepsy management using routinely collected clinical data

### Personal Notes

- The use of pre-trained models for each modality is a clever approach to handle the complexity of multimodal medical data
- SMILES embeddings represent an important advancement over traditional one-hot encoding for representing drug structures
- The integration of molecular drug features could potentially allow the model to generalise to new ASMs
- The focus on routinely collected clinical data makes this approach practically translatable to clinical settings
- Multiple MRI views are essential for capturing the full extent of structural anomalies in epilepsy

### Quotations

> "Our findings underscore the benefits of multimodal integration for personalised epilepsy management, as our fusion model achieved an AUC of 0.75, an improvement over the best unimodal model (0.71)."

> "Uncontrolled seizures can cause substantial health, psychosocial, and economic impacts to patients, including increased hospitalisation, comorbidities, premature mortality, and decreased quality of life."

### References to Follow Up

- BiomedCLIP [25] - A vision-language foundation model trained on medical images
- MoLER [14] - Graph-based model for molecular embedding
- Molecular Transformer Embeddings (MTE) [15] - End-to-end transformer encoder for SMILES embedding
- Structured State Space models (S4) [9] - Method for quantising signals through bilinear transformation

## Literature Review Sections

- Current ASM outcome prediction approaches
    - Limitations of clinical factor-based models
    - Integration of genetic information
    - Potential of neuroimaging biomarkers
- Deep learning approaches for EEG and MRI analysis
    - Quantisation methods for EEG signal processing
    - Foundation models for medical image analysis
    - Multimodal fusion strategies

## Research Questions

- How can multimodal deep learning improve personalised epilepsy treatment?
- What is the relative contribution of each modality to prediction accuracy?
- Can pre-trained embeddings for molecular drug structures enhance generalisability?
- How effective are foundation models in extracting features from medical imaging data?

## Gaps in the Literature

- Limited use of raw EEG and MRI data in ASM outcome prediction
- One-hot encoding inadequately captures drug relationships
- Need for cost-effective alternatives to genome sequencing
- Lack of comprehensive multimodal approaches in epilepsy management

## Synthesis

The integration of multimodal data through specialised deep learning architectures represents a significant advancement in epilepsy treatment personalisation. By leveraging routinely collected clinical, neurophysiological, and neuroimaging data, the proposed framework offers a practical approach to ASM selection that could potentially reduce the trial-and-error period often experienced by patients. The use of pre-trained models for feature extraction from complex data types demonstrates the value of transfer learning in medical applications with limited training data.

## Ideas for Future Research

- Specialised 3D MRI models to better capture structural abnormalities
- Methods for handling missing modalities in clinical practice
- Refined co-embedding techniques to optimise multimodal data fusion
- Prospective clinical validation of the prediction framework
- Extension to multi-drug therapy prediction for refractory epilepsy
- Integration of longitudinal data to capture disease progression


See also:

- [[Brain-Computer Interface (BCI)]]
- [[Computational Neuroscience]]
- [[Machine Learning]]