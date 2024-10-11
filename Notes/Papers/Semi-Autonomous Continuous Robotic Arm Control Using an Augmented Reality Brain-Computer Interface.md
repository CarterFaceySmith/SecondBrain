## Information

- Paper Title: Semi-Autonomous Continuous Robotic Arm Control Using an Augmented Reality Brain-Computer Interface
- Author(s): Kirill Kokorin, Syeda R Zehra, Jing Mu, Peter Yoo, David B Grayden, and Sam E John
- Year: 2024
- Journal: TechRxiv (preprint)
- DOI: https://doi.org/10.36227/techrxiv.171638984.48965766/v1

### Abstract

Noninvasive augmented-reality (AR) brain-computer interfaces (BCIs) that use steady-state visually evoked potentials (SSVEPs) typically adopt a fully autonomous goal-selection framework to control a robot, where automation is used to compensate for the low information transfer rate of the BCI. 

This scheme improves task performance but users may prefer direct control (DC) of robot motion. To provide users with a balance of autonomous assistance and manual control, we developed a shared control (SC) system for continuous control of robot translation using an SSVEP AR-BCI, which we tested in a 3D reaching task. 

The SC system used the BCI input and robot sensor data to continuously predict which object the user wanted to reach, generated an assistance signal, and regulated the level of assistance based on prediction confidence. Eighteen healthy participants took part in our study and each completed 24 reaching trials using DC and SC. Compared to DC, SC significantly improved mean task success rate, normalised reaching trajectory length, and participant workload measured with the NASA Task Load Index. 

Therefore, users of SC can control the robot effectively, while experiencing increased agency. Our system can personalise assistive technology by providing users with the ability to select their preferred level of autonomous assistance.

### Key Points

- Developed a shared control (SC) system for continuous control of robot translation using an SSVEP AR-BCI
- SC system predicts user's intended object and provides assistance based on confidence
- SC significantly improved task success rate, trajectory efficiency, and reduced workload compared to direct control (DC)
- System allows users to balance autonomous assistance and manual control

### Methodology

- 18 healthy participants completed 24 reaching trials each using DC and SC
- Used HoloLens 2 for AR display of SSVEP stimuli
- EEG recorded using g.USBamp amplifier with 9 electrodes
- Canonical Correlation Analysis (CCA) used for SSVEP decoding
- Shared control system used angular policy for prediction and confidence-based assistance
- The CCA decoding used the following correlation calculation: $$\rho_j = \max_{W_Z,W_Y} \frac{E[W_Z^T Z_k Y_j^T W_Y]}{\sqrt{E[W_Z^T Z_k Z_k^T W_Z]E[W_Y^T Y_j Y_j^T W_Y]}}$$ where $Z_k \in \mathbb{R}^{9\times256}$ is the filtered EEG data and $Y_j \in \mathbb{R}^{4\times256}$ is the template for each target frequency.
- The shared control command was generated using: $$u = \alpha u_a + (1 - \alpha)u_b$$ where $u_a$ is the autonomous assistance command, $u_b$ is the BCI output, and $\alpha \in [0, 0.7]$ is the assistance level.

### Results

- SC significantly improved mean task success rate (p<0.0001, $\mu=36.1\%$, 95% CI [25.3%, 46.9%])
- SC significantly reduced normalised reaching trajectory length (p<0.0001, $\mu=-26.8\%$, 95% CI [-36.0%,-17.7%])
- SC significantly reduced participant workload (p<0.02, $\mu=-11.6$, 95% CI [-21.1,-2.0])
- Mean balanced accuracy across participants: 66.1% [56.2%, 75.0%]
- Mean information transfer rate: 49.5 bits/min [32.8 bits/min, 66.2 bits/min]
- The information transfer rate (ITR) was calculated using: $$B_p = \frac{60}{t}\left(\log_2 J + A_p \log_2 A_p + (1-A_p) \log_2 \frac{1-A_p}{J-1}\right)$$ where $J=5$ is the number of directions/frequencies, $t=1$ s is the online decoding window length, and $A_p$ is the balanced accuracy for each participant.

### Conclusions

- SC system provides effective continuous control of robotic arm using AR-BCI
- Users can experience increased agency while maintaining high task performance
- System can personalise assistive technology by allowing users to select preferred level of autonomous assistance
- SC framework can potentially be adapted to other interfaces and applications in assistive technology

### Personal Notes

- The use of AR for SSVEP stimuli presentation is innovative and addresses the issue of gaze diversion
- The shared control approach seems promising for balancing user agency and task performance
- The angular policy for prediction, given by: $$\gamma_i = \arccos (\hat{r}_{PG_i} \cdot u_b)$$ where $\gamma_i$ is the angle between the user input $u_b$ and the unit vector $\hat{r}_{PG_i}$ to each object, provides an intuitive way to infer user intent
- It would be interesting to see how this system performs with individuals who have motor impairments
- The discussion on fatigue reduction through SC is important for practical BCI applications

### Quotations

> "Our SC system provided robust improvements in performance in different environments created by randomising object layouts and end-effector starting positions across participants." (Page 8)

> "As BCI-controlled robots become commercial products, users should be provided with a suite of functionality that allows them to choose the most appropriate level of automation for their internal context (e.g., fatigue) and external context (e.g., task difficulty)" (Page 8)

### References to Follow Up

- Chen, X., et al. (2020). Combination of augmented reality based brain-computer interface and computer vision for high-level control of a robotic arm.
- Dragan, A. D., & Srinivasa, S. S. (2013). A policy-blending formalism for shared control.
- Si-Mohammed, H., et al. (2018). Towards BCI-based interfaces for augmented reality: feasibility, design and evaluation.

## Literature Review Sections

- AR-based SSVEP BCIs
    - Several studies have explored using AR for SSVEP stimuli presentation
    - Generally comparable performance to screen-based systems
    - Potential advantages in reducing gaze diversion and increasing user immersion
- Shared Control in BCIs
    - Various approaches to combining user input with autonomous assistance
    - Trend towards providing users with more agency while maintaining task performance
    - Challenges in balancing user control and system assistance

## Research Questions

- How does the performance of the AR-BCI system compare when used by individuals with motor impairments?
- What is the optimal balance between user control and autonomous assistance for different tasks and user preferences?
- How can the shared control system be adapted for other types of BCIs or input modalities?

## Gaps in the Literature

- Long-term studies on the usability and effectiveness of AR-BCIs in real-world settings
- Comparative studies between different shared control approaches across various BCI paradigms
- Investigation of fatigue reduction strategies in continuous control BCIs

## Synthesis

The integration of augmented reality with SSVEP-based BCIs represents a promising direction for improving the usability of BCI-controlled assistive devices. By presenting stimuli in the user's field of view, these systems can potentially reduce the cognitive load associated with traditional screen-based interfaces. 

The shared control approach developed in this study addresses a critical challenge in BCI research: balancing user agency with task performance. By dynamically adjusting the level of assistance based on prediction confidence, the system aims to provide a more natural and effective control experience.

## Ideas for Future Research

- Develop adaptive shared control algorithms that learn user preferences over time
- Investigate the use of multimodal inputs (e.g., combining SSVEP with eye-tracking or EMG) in the shared control framework
- Explore the application of this shared control approach to other assistive technologies, such as wheelchair control or prosthetic limbs
- Conduct longitudinal studies to assess the long-term effects of using AR-BCIs on user performance, fatigue, and satisfaction