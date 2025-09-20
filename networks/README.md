# Brain Network Dynamics Analysis

This repository contains the final project for the **Networks** course; one of the courses that involved some programming at the **African Institute for Mathematical Sciences (AIMS), South Africa**. The project investigates the dynamic changes in human brain functional networks as a result of motor skill learning.

The analysis is documented in the Jupyter Notebook (`Brain Network Dynamics Analysis.ipynb`) and summarized in the final report (`Brain Network Dynamics Analysis.pdf`).

## Abstract

This study analyzes fMRI datasets of the human brain before (Day 1) and after (Day 3) participants learned a complex finger-tapping task. The analysis reveals a significant reorganization of the brain's functional network. Initially, the network is densely interconnected and globally integrated. After three days of practice, as the task becomes automatic, the network evolves to become sparser, more modular, and more efficient.

**Key Findings:**
- **Increased Efficiency:** The brain network prunes redundant connections, reducing the total number of edges from 2,500 to 1,540.
- **Enhanced Modularity:** The network on Day 3 shows a higher degree of modularity, indicating the formation of distinct, specialized subnetworks that handle tasks more automatically.
- **Hub Reorganization:** The roles of key "hub" regions shift significantly. Initially prominent hubs in motor control areas become less central, while new integrative regions emerge to coordinate automated performance.
- **Optimized Structure:** The analysis confirms that the brain's network evolves from a densely interconnected system to a more refined and efficient "small-world" architecture, optimized for the learned skill.

## Repository Structure

```
.
├── data/
│   ├── Brain1.csv       # Adjacency list for the brain network on Day 1 (early learning)
│   └── Brain3.csv       # Adjacency list for the brain network on Day 3 (after practice)
├── plot/Pictures/
│   └── ...              # Images and plots generated during the analysis
├── Brain Network Dynamics Analysis.ipynb  # Jupyter Notebook with the complete Python code
└── Brain Network Dynamics Analysis.pdf    # The final project report
```

## Dataset

The datasets (`Brain1.csv` and `Brain3.csv`) represent the functional brain networks of 20 participants. The data was originally published by Mantzaris et al. (2013).

- **Nodes:** 112 anatomically defined brain regions.
- **Edges:** Undirected edges denote significant functional connections (high coherence in low-frequency activity).
- **Brain1 (Day 1):** The network during early learning (112 nodes, 2,500 edges).
- **Brain3 (Day 3):** The network after practice and skill mastery (112 nodes, 1,540 edges).

## Methodology

The analysis was conducted in Python, primarily using the `networkx` library for graph analysis and `matplotlib` for visualization. The core methodological steps include:

1.  **Network Construction:** Loading the adjacency lists from the `.csv` files and constructing graph objects for the Day 1 and Day 3 networks.
2.  **Community Detection:** Applying **spectral partitioning** to divide each network into two communities to investigate its modular structure.
3.  **Modularity and Small-World Analysis:** Quantifying the evolution of the network's structure by measuring the proportion of intra-community vs. inter-community edges and counting network motifs (triangles and 4-cycles).
4.  **Comparison with Random Networks:** Comparing the brain networks' clustering coefficients and motif counts to equivalent **Erdős–Rényi random graphs** to confirm that their structure is non-random and highly organized.
5.  **Centrality Analysis:** Identifying the changing roles of key brain regions by calculating three centrality measures:
    -   **Degree Centrality:** To find the most connected "hub" nodes.
    -   **Closeness Centrality:** To find nodes that can communicate most efficiently across the network.
    -   **Betweenness Centrality:** To identify critical "bridge" nodes that connect different communities.

## Getting Started

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/peter-adepoju/AIMS-Programming-Courses.git
    cd AIMS-Programming-Courses/networks
    ```

2.  Install the required Python libraries:
    ```bash
    pip install numpy pandas networkx matplotlib scipy
    ```

### Usage

1.  Launch Jupyter Notebook or JupyterLab from your terminal:
    ```bash
    jupyter notebook
    ```
2.  Open the `Brain Network Dynamics Analysis.ipynb` file.
3.  Run the cells sequentially to reproduce the data loading, analysis, and visualizations.

## Authors

This project was a collaborative effort by a group of four students for the Networks course at AIMS South Africa.

- **Peter Oluwafemi Adepoju** ([@Peter Adepoju](https://github.com/peter-adepoju))
- Isaiah Anuoluwapo Aremu ([Isaiah Aremu](https://www.linkedin.com/in/isaiah-anuoluwapo-aremu-1a7301305))
- Morongwa Ralefeta([Morongwa Ralefeta](https://www.linkedin.com/in/morongwa-ralefeta-85b27021b))
- Anjoreoluwa Boluwajoko ([Anjoreoluwa Boluwajoko](https://www.linkedin.com/in/anjoreoluwa-boluwajoko-0050b9160))

## References

- Bassett, D.S. et al. (2011) ‘Dynamic reconfiguration of human brain networks during learning’, *Proceedings of the National Academy of Sciences of the United States of America*, 108(18), pp. 7641–7646.
- Bassett, D.S. and Bullmore, E. (2006) ‘Small-world brain networks’, *The Neuroscientist*, 12(6), pp. 512–523.
- Dayan, E. and Cohen, L.G. (2011) ‘Neuroplasticity subserving motor skill learning’, *Neuron*, 72(3), pp. 443–454.
- Mantzaris, A.V. et al. (2013) ‘Dynamic network centrality summarizes learning in the human brain’, *Journal of complex networks*, 1(1), pp. 83–92.
- Rubinov, M. and Sporns, O. (2010) ‘Complex network measures of brain connectivity: uses and interpretations’, *NeuroImage*, 52(3), pp. 1059–1069.
- Sporns, O. and Kötter, R. (2004) ‘Motifs in brain networks’, *PLoS biology*, 2(11), p. e369.

## License

This project is open-source and available under the [MIT License](LICENSE).
