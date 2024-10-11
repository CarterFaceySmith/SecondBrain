## Information

- Paper Title: Continuous synthesis of artificial speech sounds from human cortical surface recordings during silent speech production
- Author(s): Kevin Meng, Farhad Goodarzy, EuiYoung Kim, Ye Jin Park, June Sic Kim, Mark J Cook, Chun Kee Chung, David B Grayden
- Year: 2023
- Journal: Journal of Neural Engineering
- DOI: https://doi.org/10.1088/1741-2552/ace7f6

### Abstract

Objective. Brain–computer interfaces can restore various forms of communication in paralysed patients who have lost their ability to articulate intelligible speech. This study aimed to demonstrate the feasibility of closed-loop synthesis of artificial speech sounds from human cortical surface recordings during silent speech production. Approach. Ten participants with intractable epilepsy were temporarily implanted with intracranial electrode arrays over cortical surfaces. 

A decoding model that predicted audible outputs directly from patient-specific neural feature inputs was trained during overt word reading and immediately tested with overt, mimed and imagined word reading. Predicted outputs were later assessed objectively against corresponding voice recordings and subjectively through human perceptual judgments. 

Main results. Artificial speech sounds were successfully synthesized during overt and mimed utterances by two participants with some coverage of the precentral gyrus. About a third of these sounds were correctly identified by naïve listeners in two-alternative forced-choice tasks. A similar outcome could not be achieved during imagined utterances by any of the participants. 

However, neural feature contribution analyses suggested the presence of exploitable activation patterns during imagined speech in the postcentral gyrus and the superior temporal gyrus. In future work, a more comprehensive coverage of cortical surfaces, including posterior parts of the middle frontal gyrus and the inferior frontal gyrus, could improve synthesis performance during imagined speech. 

Significance. As the field of speech neuroprostheses is rapidly moving toward clinical trials, this study addressed important considerations about task instructions and brain coverage when conducting research on silent speech with non-target participants.

### Key Points

- Demonstrated feasibility of closed-loop synthesis of artificial speech sounds from human cortical surface recordings
- Successfully synthesized artificial speech sounds during overt and mimed utterances for two participants
- About a third of synthesized sounds were correctly identified by naïve listeners in two-alternative forced-choice tasks
- Imagined speech synthesis was unsuccessful, but showed potential in certain brain areas
- Highlighted the importance of brain coverage and task instructions in silent speech research

### Methodology

- 10 participants with intractable epilepsy implanted with intracranial electrode arrays
- Decoding model trained on overt word reading, tested on overt, mimed, and imagined word reading
- Used Linear Discriminant Analysis (LDA) classifiers for audio spectrogram prediction
- Used Multivariate Temporal Response Function (mTRF) for speech probability estimation
- Extracted neural features from high-gamma band (70-170 Hz) activity
- Evaluated synthesis performance using Dynamic Time Warping (DTW) correlation
- Conducted subjective evaluation through human perceptual judgments

### Results

- Artificial speech sounds successfully synthesized for 2 out of 10 participants during overt and mimed speech
- Synthesis was successful for participants with coverage of the precentral gyrus
- About 33% of synthesized sounds correctly identified in two-alternative forced-choice tasks
- No successful synthesis during imagined speech for any participant
- Neural feature contribution analysis showed potential in postcentral gyrus and superior temporal gyrus for imagined speech
- High-gamma band activity in precentral gyrus correlated with articulatory movements
- Superior temporal gyrus activations likely reflected perception of own voice

### Conclusions

- Demonstrated feasibility of closed-loop synthesis of artificial speech sounds from cortical recordings
- Highlighted the importance of electrode placement, particularly coverage of the precentral gyrus
- Identified potential areas for improvement in imagined speech synthesis
- Emphasized the need for comprehensive coverage of cortical surfaces in future research
- Addressed important considerations for conducting silent speech research with non-target participants

### Personal Notes

- The study's approach of training on overt speech and testing on silent speech is practical but may limit clinical translation for patients who have already lost speech ability
- The success in mimed speech synthesis is promising for potential applications in locked-in patients
- The inability to synthesize imagined speech highlights the complexity of decoding internal speech processes
- The study's use of both objective and subjective evaluation methods provides a comprehensive assessment of the synthesized speech
- The comparison between ECoG and SEEG datasets offers valuable insights into electrode placement strategies

### Quotations

> "About a third of these sounds were correctly identified by naïve listeners in two-alternative forced-choice tasks." (Abstract)

> "As the field of speech neuroprostheses is rapidly moving toward clinical trials, this study addressed important considerations about task instructions and brain coverage when conducting research on silent speech with non-target participants." (Abstract)

### References to Follow Up

- Moses D A et al 2021 Neuroprosthesis for decoding speech in a paralyzed person with anarthria New Engl. J. Med. 385 217–27
- Anumanchipalli G K, Chartier J and Chang E F 2019 Speech synthesis from neural decoding of spoken sentences Nature 568 493–8
- Crone N E, Sinai A and Korzeniewska A 2006 High-frequency gamma oscillations and human brain mapping with electrocorticography Prog. Brain Res. 159 275–95
- Indefrey P 2011 The spatial and temporal signatures of word production components: a critical update Front. Psychol. 2 255

## Literature Review Sections

- Brain-Computer Interfaces for Speech Restoration
  - Current state of speech neuroprostheses
  - Challenges in decoding speech from brain signals
  - Comparison of invasive and non-invasive approaches

- Silent Speech Decoding
  - Differences between overt, mimed, and imagined speech
  - Neural correlates of silent speech production
  - Challenges in decoding imagined speech

## Research Questions

- How can the decoding of imagined speech be improved to achieve similar performance to overt and mimed speech?
- What is the optimal electrode placement for capturing neural signals related to speech production across different speech modes?
- How does the choice of neural features and decoding algorithms affect the quality and intelligibility of synthesized speech?
- What are the long-term stability and adaptability considerations for speech BCIs in clinical applications?

## Gaps in the Literature

- Limited research on imagined speech decoding compared to overt and mimed speech
- Lack of standardized protocols for evaluating speech BCI performance across different studies
- Insufficient understanding of the neural mechanisms underlying imagined speech production
- Limited exploration of the effects of feedback on decoding performance in closed-loop systems

## Synthesis

This study advances the field of speech neuroprostheses by demonstrating the feasibility of closed-loop synthesis of artificial speech sounds from cortical surface recordings during silent speech production. 

The success in synthesizing speech during overt and mimed utterances, particularly from the precentral gyrus, provides valuable insights for future BCI designs. However, the challenges encountered in decoding imagined speech highlight the complexity of internal speech processes and the need for more targeted approaches in electrode placement and neural feature selection. 

The study's comprehensive methodology, combining both objective and subjective evaluations, offers a robust framework for assessing BCI performance in speech synthesis tasks. The comparison between ECoG and SEEG datasets further emphasizes the importance of brain coverage in capturing relevant neural signals for speech decoding.

## Ideas for Future Research

- Develop more sophisticated decoding algorithms specifically tailored for imagined speech, potentially incorporating deep learning approaches
- Investigate the use of multimodal data, combining ECoG with other imaging techniques (e.g., fMRI) to better localize speech-related neural activity
- Explore the potential of adaptive decoding models that can adjust to changes in neural signals over time
- Conduct longitudinal studies to assess the long-term stability and efficacy of speech BCIs in clinical populations
- Investigate the effects of neurofeedback training on improving user control and synthesis quality in closed-loop speech BCI systems