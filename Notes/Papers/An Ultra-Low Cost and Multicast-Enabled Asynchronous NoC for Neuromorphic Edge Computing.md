## Information

- Paper Title: An Ultra-Low Cost and Multicast-Enabled Asynchronous NoC for Neuromorphic Edge Computing
- Author(s): Zhe Su, Simone Ramini, Demetra Coffen Marcolin, Alessandro Veronesi, Milos Krstic, Giacomo Indiveri, Davide Bertozzi, Steven M. Nowick
- Year: 2024
- Journal: IEEE Journal on Emerging and Selected Topics in Circuits and Systems
- DOI: 10.1109/JETCAS.2024.3433427

### Abstract

Biological brains are increasingly taken as a guide toward more efficient forms of computing. The latest frontier considers the use of spiking neural-network-based neuromorphic processors for near-sensor data processing, in order to fit the tight power and resource budgets of edge computing devices. 

However, a prevailing focus on brain-inspired computing and storage primitives in the design of neuromorphic systems is currently bringing a fundamental bottleneck to the forefront: chip-scale communications. While communication architectures (typically, a network-on-chip) are generally inspired by, or even borrowed from, general purpose computing, neuromorphic communications exhibit unique characteristics: they consist of the event-driven routing of small amounts of information to a large number of destinations within tight area and power budgets. 

This article aims at an inflection point in network-on-chip design for brain-inspired communications, revolving around the combination of cost-effective and robust asynchronous design, architecture specialisation for short messaging and lightweight hardware support for tree-based multicast. When validated with functional spiking neural network traffic, the proposed NoC delivers energy savings ranging from 42% to 71% over a state-of-the-art NoC used in a real multi-core neuromorphic processor for edge computing applications.

### Key Points

- Introduces an ultra-low cost and multicast-enabled asynchronous Network-on-Chip (NoC) for neuromorphic edge computing
- Focuses on efficient event-driven routing of small information packets to multiple destinations
- Combines cost-effective asynchronous design with architecture specialization for short messaging
- Provides lightweight hardware support for tree-based multicast
- Achieves 42% to 71% energy savings compared to state-of-the-art NoCs in neuromorphic processors

### Methodology

- Developed a bundled-data asynchronous design style for the NoC
- Used Mousetrap pipeline for high-performance asynchronous data transmission
- Implemented a novel switch architecture with input port modules (IPMs) and output port modules (OPMs)
- Designed specialized components for routing, arbitration, and multicast support
- Utilized a timing optimization flow for handling relative timing constraints
- Compared the proposed NoC with state-of-the-art asynchronous and synchronous designs
- Validated the NoC using functional spiking neural network traffic

### Results

- Achieved 67% less energy-per-bit and 52% lower packet latency compared to baseline unicast designs
- Demonstrated 37.8% area savings and 26% energy-per-bit reduction for multicast operations
- Showed superior energy efficiency across various payload sizes (28 to 504 bits)
- Outperformed state-of-the-art neuromorphic NoCs in spiking neural network experiments, with energy savings of 42% to 71%
- Exhibited 52% better area efficiency and 69% lower energy-per-bit compared to an optimized synchronous NoC

### Conclusions

- The proposed NoC architecture provides a significant advancement in interconnection networks for neuromorphic edge computing
- Specialization for short messaging and lightweight multicast support offers substantial efficiency improvements
- The asynchronous design approach delivers major cost benefits while maintaining robust operation
- The NoC can be used standalone or as a dedicated network plane for short messages in platforms with diverse traffic patterns

### Personal Notes

- The focus on single-flit packets for neuromorphic communication is an interesting approach to optimise for the specific needs of these systems
- The detailed handling of timing constraints and robustness issues in asynchronous design is particularly noteworthy
- The comparison with both asynchronous and synchronous state-of-the-art designs provides a comprehensive evaluation of the proposed architecture
- The validation using real neuromorphic workloads adds credibility to the practical applicability of the design

### Quotations

> "This paper targets a major innovation in interconnection networks for on-chip communication in neuromorphic edge computing platforms, which relies on two fundamental pillars:" (Page 410)

> "By coherently and systematically developing the implications of these principles, the paper comes up with an ultra-low cost NoC architecture for the efficient delivery of spike messages, with built-in and lightweight support for the parallel tree-based multicast of single-flit packets." (Page 410)

### References to Follow Up

- S. Moradi et al., "A scalable multicore architecture with heterogeneous memory structures for dynamic neuromorphic asynchronous processors (DYNAPs)," IEEE Trans. Biomed. Circuits Syst., vol. 12, no. 1, pp. 106–122, Feb. 2018.
- D. Bertozzi et al., "Cost-effective and flexible asynchronous interconnect technology for GALS systems," IEEE Micro, vol. 41, no. 1, pp. 69–81, Jan. 2021.
- M. Singh and S. M. Nowick, "MOUSETRAP: High-speed transition-signaling asynchronous pipelines," IEEE Trans. Very Large Scale Integr. (VLSI) Syst., vol. 15, no. 6, pp. 684–698, Jun. 2007.

## Literature Review Sections

- Asynchronous NoC Design for Neuromorphic Systems
  - Comparison of different asynchronous design styles and their trade-offs
  - Challenges in implementing efficient multicast support in asynchronous NoCs

- Energy Efficiency in Neuromorphic Edge Computing
  - Techniques for reducing power consumption in on-chip communication
  - Impact of communication architectures on overall system energy efficiency

## Research Questions

- How can the proposed NoC architecture be scaled for larger neuromorphic systems beyond edge computing?
- What are the potential trade-offs between energy efficiency and performance when further optimising for ultra-low power operation?
- How does the proposed NoC perform under varying workloads and network topologies typical in neuromorphic computing?
- Can the principles of this design be extended to other domains requiring efficient, event-driven communication?

## Gaps in the Literature

- Limited exploration of NoC architectures specifically optimised for spiking neural network communication patterns
- Lack of comprehensive studies on the long-term reliability and variability of asynchronous NoCs in neuromorphic systems
- Insufficient investigation of the impact of different multicast addressing schemes on NoC efficiency in large-scale neuromorphic platforms

## Synthesis

This paper presents a significant advancement in NoC design for neuromorphic edge computing by addressing the unique communication requirements of spiking neural networks. 

By specialising the architecture for short, event-driven messages and providing efficient multicast support, the authors have demonstrated substantial improvements in energy efficiency and area utilisation compared to both general-purpose and existing neuromorphic NoCs. 

The asynchronous design approach, while challenging to implement, offers advantages in terms of power consumption and adaptability to varying workloads. The comprehensive validation using real neuromorphic workloads provides strong evidence for the practical applicability of the proposed design in edge computing scenarios.

## Ideas for Future Research

- Investigate adaptive NoC architectures that can dynamically adjust to changing communication patterns in learning neuromorphic systems
- Explore the integration of this NoC design with emerging memory technologies to further optimise the memory-compute interface in neuromorphic processors
- Develop automated design space exploration tools for optimising NoC parameters based on specific neuromorphic workloads and constraints
- Study the scalability of the proposed architecture for very large-scale neuromorphic systems, potentially incorporating hierarchical or heterogeneous NoC designs
- Investigate the potential of using machine learning techniques to optimise the NoC routing and multicast strategies based on observed traffic patterns in neuromorphic applications