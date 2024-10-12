## Information

- Paper Title: GMap: An Open-source Efficient Compiler for Mapping any Network onto any Neuromophic Chip
- Author(s): Jimmy Weber, Chenxi Wu, Melika Payvand
- Year: 2023
- Conference: [[International Conference on Neuromorphic Systems]] (ICONS '23)
- DOI: https://doi.org/10.1145/3589737.3605997

### Abstract

Neuromorphic computing has emerged as a promising solution to the power and memory requirements of embedded systems. However, mapping pre-trained neural networks onto diverse neuromorphic hardware architectures presents significant challenges. 

In this paper, we introduce GMap, a versatile, easy-to-use, and open-source python library designed for mapping neural networks onto any arbitrary hardware architecture. GMap adapts the simulated annealing approach, offering a probabilistic, meta-heuristic optimisation for approximating the global optimum mapping. 

The algorithm takes architectural parameters of the hardware and network connectivity as input and provides a mapping solution as output. T

he library allows users to either map a pre-trained network onto a pre-existing chip or define custom hardware with respect to its constraints. GMap contributes to the neuromorphic field by enabling efficient deployment of neural networks on various hardware platforms and facilitating further research and collaboration in the neuromorphic community.

### Key Points

- GMap is an open-source Python library for mapping neural networks to arbitrary neuromorphic hardware
- Uses simulated annealing for optimisation of network mapping
- Supports pre-existing chips and custom hardware definitions
- Aims to address challenges in mapping networks to diverse neuromorphic architectures
- Provides a solution for efficient deployment of neural networks on various hardware platforms

### Methodology

- Adapts simulated annealing approach for mapping optimisation
- Takes hardware architectural parameters and network connectivity as input
- Provides mapping solution as output
- Allows mapping to pre-existing chips or custom hardware with specific constraints
- Uses a function to calculate violated constraints when mapping to custom hardware
- Employs a probabilistic, meta-heuristic optimisation to approximate global optimum
- Transitions from wide exploration to focused, greedy search in promising regions

### Results

- GMap provides sub-optimal solutions due to its heuristic nature
- Solution quality improves with increased number of search steps
- Computational complexity is O(steps * N), where N is the number of neurons
- Performance assessed using hand-crafted networks with known optimal mappings
- Demonstrates effectiveness in finding suitable mapping solutions
- Shows improvement in solution quality with increasing number of steps

### Conclusions

- GMap addresses challenges of mapping networks to diverse neuromorphic hardware
- Contributes to efficient deployment of neural networks on various platforms
- Offers flexibility for mapping to different hardware architectures
- Open-source tool designed for collaboration and improvement by the community
- Available on GitHub under EIS-Hub/GMap-compiler

### Personal Notes

- The approach of using simulated annealing for network mapping is interesting and seems effective
- The flexibility to define custom hardware constraints could be very useful for researchers
- It would be interesting to see how this compares to other mapping approaches in terms of efficiency and accuracy
- The open-source nature of the tool could lead to rapid improvements and adaptations by the community

### Quotations

> "GMap employs a sophisticated method to find a configuration that minimizes the number of violated constraints. In cases where the configuration does not violate any constraints of the hardware, the network is considered mappable onto the chip."

> "By making GMap available on GitHub, it is hoped that collaboration and contributions from the community will lead to further improvements and extensions, supporting the continued advancement of neuromorphic computing."

### References to Follow Up

- Moradi, S., et al. (2017). A scalable multicore architecture with heterogeneous memory structures for dynamic neuromorphic asynchronous processors (dynaps). IEEE transactions on biomedical circuits and systems, 12(1):106–122.
- Van Laarhoven, P. J. M., et al. (1987). Simulated annealing. Springer.
- Das, A., et al. (2018). Mapping of local and global synapses on spiking neuromorphic hardware. In 2018 Design, Automation & Test in Europe Conference & Exhibition (DATE), pages 1217–1222. IEEE.

## Literature Review Sections

- Neuromorphic Hardware Mapping Challenges
  - Limitations of current hardware-specific mapping solutions
  - Approaches to generalised mapping techniques

- Simulated Annealing in Optimisation Problems
  - Applications in network mapping and graph problems
  - Advantages and limitations for neuromorphic hardware mapping

## Research Questions

- How does GMap's performance compare to hardware-specific mapping solutions in terms of efficiency and accuracy?
- What are the limitations of the simulated annealing approach for very large networks or complex hardware architectures?
- How can the algorithm be further optimised to improve mapping quality or reduce computational complexity?
- What additional features or constraints might be useful to include in future versions of GMap?

## Gaps in the Literature

- Limited comparison with other generalised mapping techniques for neuromorphic hardware
- Lack of detailed analysis on the impact of different hardware constraints on mapping efficiency
- Insufficient exploration of the trade-offs between mapping quality and computation time for large-scale networks

## Synthesis

GMap represents a significant step towards addressing the challenges of mapping neural networks to diverse neuromorphic hardware architectures. By providing a flexible, open-source solution, it enables researchers and engineers to efficiently deploy networks on various platforms, potentially accelerating the development and adoption of neuromorphic computing for edge applications. 

The use of simulated annealing offers a balance between exploration and exploitation in the search for optimal mappings, though the sub-optimal nature of the solutions may necessitate further refinement for certain applications. 

The tool's ability to accommodate both pre-existing chips and custom hardware definitions makes it particularly valuable for the research community, allowing for experimentation with novel architectures and constraints.

## Ideas for Future Research

- Investigate hybrid optimisation approaches combining simulated annealing with other techniques to improve mapping quality
- Develop automated constraint generation tools to facilitate the definition of custom hardware architectures
- Explore the integration of GMap with neuromorphic simulation environments for end-to-end network design and deployment
- Investigate the application of GMap to other domains requiring graph mapping onto constrained hardware architectures
- Conduct a comprehensive benchmarking study comparing GMap to other mapping solutions across various network and hardware configurations