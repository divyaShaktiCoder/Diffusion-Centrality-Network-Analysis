# Diffusion Centrality — Network Science

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/NetworkX-Network%20Analysis-orange" alt="NetworkX">
  <img src="https://img.shields.io/badge/NumPy-Scientific%20Computing-013243?logo=numpy" alt="NumPy">
  <img src="https://img.shields.io/badge/SciPy-Scientific%20Computing-8CAAE6?logo=scipy" alt="SciPy">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557c?logo=matplotlib" alt="Matplotlib">
  <img src="https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?logo=googlecolab" alt="Google Colab">
  <img src="https://img.shields.io/badge/Network%20Science-Research-purple" alt="Network Science">
</p>

<p align="center">
  <strong>Implementation and Experimental Analysis of Diffusion Centrality Across Multiple Network Datasets</strong>
</p>

---

## 📌 Table of Contents

- [About the Project](#-about-the-project)
- [Project Objectives](#-project-objectives)
- [What is Network Science?](#-what-is-network-science)
- [What is Centrality?](#-what-is-centrality)
- [What is Diffusion Centrality?](#-what-is-diffusion-centrality)
- [Why Diffusion Centrality?](#-why-diffusion-centrality)
- [Mathematical Foundation](#-mathematical-foundation)
- [Understanding the Formula](#-understanding-the-formula)
- [Role of q](#-role-of-q)
- [Role of T](#-role-of-t)
- [How the Algorithm Works](#-how-the-algorithm-works)
- [Step-by-Step Methodology](#-step-by-step-methodology)
- [Implementation](#-implementation)
- [Datasets](#-datasets)
- [Dataset Format](#-dataset-format)
- [Project Structure](#-project-structure)
- [Technologies Used](#-technologies-used)
- [Installation](#-installation)
- [Google Colab](#-google-colab)
- [Running the Project](#-running-the-project)
- [Code Explanation](#-code-explanation)
- [Output](#-output)
- [Results](#-results)
- [Comparison with Other Centrality Measures](#-comparison-with-other-centrality-measures)
- [Interpretation of Results](#-interpretation-of-results)
- [Computational Complexity](#-computational-complexity)
- [Advantages](#-advantages)
- [Limitations](#-limitations)
- [Future Improvements](#-future-improvements)
- [Reproducibility](#-reproducibility)
- [Research Background](#-research-background)
- [References](#-references)
- [Author](#-author)
- [Acknowledgements](#-acknowledgements)
- [License](#-license)

---

# 📌 About the Project

**Diffusion Centrality** is a network centrality measure that evaluates the importance of nodes based on their ability to influence or reach other nodes through repeated diffusion across a network.

Traditional centrality measures often focus on one particular aspect of a network:

- Degree Centrality focuses on direct connections.
- Closeness Centrality focuses on distance.
- Betweenness Centrality focuses on shortest paths.
- Eigenvector Centrality focuses on connections to important nodes.

Diffusion Centrality takes a different perspective.

Instead of looking only at direct connections, it considers how influence can propagate through the network over multiple steps.

For example:

```text
                 B
                / \
               /   \
              A     D
               \   /
                \ /
                 C
                 |
                 E

🎯 Project Objectives

The main objectives of this project are:

1.Understand the concept of Diffusion Centrality.
2.Study the mathematical formulation of Diffusion Centrality.
3.Represent real-world datasets as graphs.
4.Convert graphs into adjacency matrices.
5.Calculate the largest eigenvalue of the adjacency matrix.
6.Determine the diffusion parameter q.
7.Calculate diffusion over multiple periods.
8.Rank nodes according to their Diffusion Centrality scores.
9.Identify the top influential nodes.
10.Visualize the results.
11.Experiment with different network datasets.
12.Build a reproducible Python/Google Colab implementation.


📐 Mathematical Foundation

The Diffusion Centrality used in this project is:

$$ DC(q,T) = \left[ \sum_{l=1}^{T}(qA)^l \right]\mathbf{1} $$

Where:

Symbol	Meaning
A	Adjacency matrix
q	Diffusion/transmission parameter
T	Number of diffusion periods
l	Diffusion step
1	Vector containing ones
DC	Diffusion Centrality
