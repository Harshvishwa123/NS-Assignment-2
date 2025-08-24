# Network Science Assignment 2 - Winter 2025

## Overview
This assignment covers fundamental concepts in network science including small-world networks, scale-free networks, network robustness, and protein interaction networks. All implementations must be done in Python using Jupyter Notebooks.

## Assignment Structure

### Submission Requirements
- **Format**: Well-documented Jupyter Notebook for each question
- **Files per question**: Data files, Jupyter Notebook (.ipynb), PDF export of notebook
- **Naming convention**: `TeamNumber.zip`
- **Late penalty**: 3 points deduction for delayed submissions
- **Total points**: 10 (scaled)

## Questions Overview

### Question 1: Watts-Strogatz Small-World Network Model [20 points]
**Objective**: Implement and analyze the small-world network model

**Tasks**:
- Implement Watts-Strogatz algorithm
- Compute scaled clustering coefficient and scaled characteristic path length
- Plot results vs. rewiring probability
- Use suitably large values of n (nodes) and k (initial connections)
- Exact replication of reference plot expected

**Key Concepts**:
- Small-world phenomenon
- Clustering coefficient
- Characteristic path length
- Rewiring probability

### Question 2: Barabási-Albert Scale-Free Networks [10 points]
**Objective**: Implement and analyze preferential attachment networks

**Tasks**:
- Implement BA algorithm from scratch
- Vary initial network size and growth parameters
- Analyze 100+ network instances
- Compute:
  - Average clustering coefficient
  - Characteristic path length
  - Degree distribution

**Mathematical Foundation**:
```
P_i(k) ∝ k_i / Σ(k_j) for j=1 to n
```

### Question 3: Modified BA Algorithm [10 points]
**Objective**: Strengthen preferential attachment bias

**Tasks**:
- Modify BA algorithm: connection probability ∝ (degree)²
- Compare with standard BA networks
- Create higher-order variants
- Analyze topological differences

### Question 4: Network Robustness Analysis [20 points total]

#### 4(a): Random Node Deletion [5 points]
- Implement random node removal strategy
- Measure characteristic path length vs. fraction removed (f)
- Measure giant cluster size (S)
- Use NetworkX or igraph libraries

#### 4(b): Comparative Robustness [5 points]
- Compare random vs. scale-free networks
- Test both random and targeted deletion strategies
- Analyze network response patterns

#### 4(c): Real-World Network Analysis [5 points]
- Choose real-world scale-free network (500 < n < 5000 nodes)
- Apply robustness analysis
- Document network source and characteristics

#### 4(d): Analysis and Discussion [5 points]
- Compare results with Albert et al. (Nature, 2000)
- Discuss patterns in:
  - Characteristic path length response
  - Giant cluster size changes
  - Fragmentation behavior

### Question 5: Yeast Protein Interactome Analysis [15 points total]

#### 5(a): Network Construction and Visualization [5 points]
- Data source: Yeast Interactome Database (http://interactome.dfci.harvard.edu/S_cerevisiae/)
- Plot degree distribution
- Create C(k) × k plot
- Visualize using Cytoscape
- Highlight high-degree proteins

#### 5(b): Essential Protein Analysis [5 points]
- Identify key proteins by interaction count
- Plot fraction of essential proteins vs. degree k
- Use external databases for essentiality data

#### 5(c): Protein Network Robustness [5 points]
- Apply random and targeted deletion to YPI
- Compute robustness metrics (S and <s>)
- Reference: Jeong et al., Nature 411, 41-42 (2001)

## Implementation Guidelines

### Required Libraries
```python
import networkx as nx
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
from scipy import stats
import random
```

### Computational Considerations
- Tasks are computationally intensive - start early
- Use efficient algorithms and data structures
- Consider parallel processing for large-scale analyses
- Optimize memory usage for large networks

### Documentation Standards
- Clear markdown explanations for each step
- Well-commented code
- Mathematical formulations where applicable
- Interpretation of results
- Comparison with theoretical expectations

## File Structure
```
TeamNumber.zip
├── Question1/
│   ├── Q1_notebook.ipynb
│   ├── Q1_notebook.pdf
│   └── data/
├── Question2/
│   ├── Q2_notebook.ipynb
│   ├── Q2_notebook.pdf
│   └── data/
├── Question3/
│   ├── Q3_notebook.ipynb
│   ├── Q3_notebook.pdf
│   └── data/
├── Question4/
│   ├── Q4_notebook.ipynb
│   ├── Q4_notebook.pdf
│   └── data/
└── Question5/
    ├── Q5_notebook.ipynb
    ├── Q5_notebook.pdf
    └── data/
```

## Key Algorithms to Implement

### 1. Watts-Strogatz Algorithm
1. Start with regular ring lattice
2. For each edge, rewire with probability p
3. Compute clustering and path length metrics

### 2. Barabási-Albert Algorithm
1. Start with small complete graph
2. Add nodes one by one
3. Connect new node based on preferential attachment
4. Repeat until desired size

### 3. Network Robustness Analysis
1. Remove nodes (random or targeted)
2. Recalculate network properties
3. Track giant component evolution
4. Measure connectivity changes

## Evaluation Criteria
- **Correctness**: Proper algorithm implementation
- **Analysis**: Thorough statistical analysis
- **Visualization**: Clear, informative plots
- **Documentation**: Comprehensive explanations
- **Comparison**: Alignment with literature results

## Tips for Success
1. **Start early** - computational tasks take time
2. **Validate implementations** against known results
3. **Use appropriate network sizes** for statistical significance
4. **Document assumptions** and parameter choices
5. **Compare results** with published literature
6. **Optimize code** for better performance

## Reference Papers
- Watts & Strogatz (1998) - Small-world networks
- Albert et al. (2000) - Network robustness
- Jeong et al. (2001) - Protein network centrality

## Data Sources
- Yeast Interactome Database: http://interactome.dfci.harvard.edu/S_cerevisiae/
- Essential gene databases (SGD, OGEE, etc.)
- Real-world network repositories (SNAP, NetworkRepository, etc.)

---

**Note**: Ensure all code is reproducible and results are clearly presented with appropriate statistical measures and visualizations.
