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

A node may influence its immediate neighbors first:

Node
 ↓
1-hop neighbors

The influence can then continue:

Node
 ↓
1-hop neighbors
 ↓
2-hop neighbors
 ↓
3-hop neighbors

Diffusion Centrality combines these repeated diffusion effects into a single centrality score.

🎯 Project Objectives

The main objectives of this project are:

Understand the concept of Diffusion Centrality.
Study the mathematical formulation of Diffusion Centrality.
Represent real-world datasets as graphs.
Convert graphs into adjacency matrices.
Calculate the largest eigenvalue of the adjacency matrix.
Determine the diffusion parameter q.
Calculate diffusion over multiple periods.
Rank nodes according to their Diffusion Centrality scores.
Identify the top influential nodes.
Visualize the results.
Experiment with different network datasets.
Build a reproducible Python/Google Colab implementation.
🌐 What is Network Science?

Network Science is the study of complex systems represented as networks.

A network consists mainly of:

Nodes + Edges
Nodes

Nodes represent entities.

Examples:

Person
Organization
Book
Team
Website
Computer
Airport
Edges

Edges represent relationships between nodes.

Examples:

Friendship
Communication
Collaboration
Competition
Citation
Connection
Information Flow

A simple network can be represented as:

A -------- B
|          |
|          |
C -------- D

Here:

A, B, C, D are nodes.
The lines represent edges.
⭐ What is Centrality?

Centrality measures help determine which nodes are important in a network.

Different centrality measures define "importance" differently.

For example:

Degree Centrality

Asks:

How many direct connections does this node have?

Betweenness Centrality

Asks:

How often does this node lie on shortest paths between other nodes?

Closeness Centrality

Asks:

How close is this node to the rest of the network?

Eigenvector Centrality

Asks:

Is this node connected to other important nodes?

Diffusion Centrality

Asks:

How effectively can influence from this node spread through the network over multiple steps?

🔥 What is Diffusion Centrality?

Diffusion Centrality measures the potential influence of a node by considering the repeated spread of information, influence, resources, or other quantities through a network.

The key idea is:

Direct Influence
       +
Indirect Influence
       +
Repeated Diffusion
       ↓
Diffusion Centrality

Therefore, Diffusion Centrality considers more than just immediate neighbors.

💡 Simple Example

Suppose we have:

A ---- B ---- C ---- D

If we look only at direct connections:

A → B
B → A,C
C → B,D
D → C

Node B and C have two direct connections.

However, diffusion allows influence to travel further:

A → B → C → D

So the importance of a node depends not only on the number of immediate connections but also on the network structure through which influence spreads.

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
🔢 Formula for T = 3

This project uses:

$$ T=3 $$

Therefore:

$$ DC = (qA)^1\mathbf{1} + (qA)^2\mathbf{1} + (qA)^3\mathbf{1} $$

Or:

DC =
1-step diffusion
+
2-step diffusion
+
3-step diffusion
🧮 Understanding the Formula
Step 1 — Adjacency Matrix

Suppose the graph is:

A ----- B
 \     /
   \ /
    C

Its adjacency matrix can be represented as:

$$ A = \begin{bmatrix} 0 & 1 & 1\\ 1 & 0 & 1\\ 1 & 1 & 0 \end{bmatrix} $$

The matrix describes the connections between nodes.

Step 2 — Matrix Power

The first power:

$$ A^1 $$

represents direct connections.

The second power:

$$ A^2 $$

captures paths involving two steps.

The third power:

$$ A^3 $$

captures paths involving three steps.

Therefore:

A¹ → 1-step paths
A² → 2-step paths
A³ → 3-step paths
Step 3 — Include q

The diffusion parameter scales the adjacency matrix:

$$ qA $$

Then the diffusion process becomes:

$$ (qA)^1 $$ $$ (qA)^2 $$ $$ (qA)^3 $$
Step 4 — Add Contributions

The contributions from all diffusion periods are added:

$$ (qA)^1+(qA)^2+(qA)^3 $$
Step 5 — Multiply by Ones Vector

Finally:

$$ DC = [(qA)^1+(qA)^2+(qA)^3]\mathbf{1} $$

This produces one score for every node.

🔢 Role of q

The parameter q controls the strength of diffusion.

This project calculates:

$$ q=\frac{1}{\lambda_1} $$

where:

$$ \lambda_1 $$

is the largest eigenvalue of the adjacency matrix.

The purpose of this scaling is to keep the diffusion process controlled.

In the implementation:

q = 1.0 / lam1
🔢 Role of T

T represents the number of diffusion periods.

The project uses:

T = 3

Therefore the algorithm considers:

1 step
2 steps
3 steps

Changing T changes how far the diffusion process is allowed to propagate.

For example:

T = 1 → only first-step diffusion
T = 2 → first + second step
T = 3 → first + second + third step
T = 5 → first through fifth step
🔄 How the Algorithm Works

The complete process is:

             Dataset
                │
                ▼
           Network Graph
                │
                ▼
       Adjacency Matrix A
                │
                ▼
      Largest Eigenvalue λ₁
                │
                ▼
          q = 1 / λ₁
                │
                ▼
       Calculate (qA)¹
                │
                ▼
       Calculate (qA)²
                │
                ▼
       Calculate (qA)³
                │
                ▼
       Add all contributions
                │
                ▼
      Diffusion Centrality
                │
                ▼
         Rank the nodes
                │
                ▼
        Top 5 / Top 10
                │
                ▼
          Visualization
🧪 Step-by-Step Methodology
Step 1 — Load Dataset

The project reads graph data from edge-list files.

Example:

1 2
1 3
2 3
3 4
Step 2 — Create Graph

NetworkX is used to create the graph.

G = nx.read_edgelist(...)

For directed networks:

nx.DiGraph

is used.

Step 3 — Convert Graph to Matrix
A = nx.to_numpy_array(G)

This produces the adjacency matrix.

Step 4 — Find Largest Eigenvalue

The largest eigenvalue is calculated.

For large symmetric matrices, the project can use:

eigsh()

For smaller or directed networks:

np.linalg.eigvals()

is used.

Step 5 — Calculate q
q = 1.0 / lam1
Step 6 — Perform Diffusion

For each diffusion period:

power = power @ qA

Then:

result += power @ np.ones(n)
Step 7 — Rank Nodes

The scores are sorted from highest to lowest.

ranked = sorted(
    dc.items(),
    key=lambda kv: kv[1],
    reverse=True
)
Step 8 — Display Top 5

The five highest-scoring nodes are printed.

Step 9 — Visualize Top 10

The ten highest-scoring nodes are displayed in a horizontal bar chart.

🧑‍💻 Implementation

The main function used in this project is:

def diffusion_centrality(
    G,
    node=None,
    q=None,
    T=3,
    normalized=False
):

The graph is converted into an adjacency matrix:

A = nx.to_numpy_array(G)

The number of nodes is:

n = A.shape[0]

If negative edge weights exist, their magnitude is used:

if (A < 0).any():
    A = np.abs(A)

The largest eigenvalue is then calculated.

For large symmetric graphs:

lam1 = eigsh(
    A,
    k=1,
    which="LM",
    return_eigenvectors=False
)[0]

Otherwise:

lam1 = np.max(
    np.abs(np.linalg.eigvals(A))
)

The diffusion parameter is:

q = 1.0 / lam1

The diffusion matrix is:

qA = q * A

The diffusion powers are accumulated:

power = np.eye(n)
result = np.zeros(n)

for _ in range(T):

    power = power @ qA

    result += power @ np.ones(n)

Finally, the result is returned as a dictionary:

return dict(zip(G.nodes(), result))
📊 Datasets

This project contains multiple network datasets for experimentation.

1. Karate Club

The Karate Club network represents social relationships between members of a karate club.

Domain    : Social Network
Weighted  : No
Directed  : No

It is a small and widely used network for testing graph algorithms.

2. Dolphins

The Dolphins network represents social relationships between dolphins.

Domain    : Animal Social Network
Weighted  : No
Directed  : No

It provides a real-world example of a social network.

3. Football

The Football network represents relationships between college football teams.

Domain    : Sports Network
Weighted  : No
Directed  : No

This dataset is useful for studying network structure and communities.

4. Political Books

The Political Books network represents relationships among political books.

Domain    : Books / Political Network
Weighted  : No
Directed  : No

It demonstrates how network centrality can be applied to information and book networks.

5. Reachability

The Reachability dataset represents a directed weighted network.

Domain    : Reachability Network
Weighted  : Yes
Directed  : Yes

This dataset allows the diffusion process to be studied in a directed and weighted environment.

📋 Dataset Summary
Dataset	Domain	Weighted	Directed
Karate	Social	❌	❌
Dolphins	Animal Social	❌	❌
Football	Sports	❌	❌
Polbooks	Books / Political	❌	❌
Reachability	Reachability	✅	✅
📄 Dataset Files

The project uses edge-list files:

karate.edgelist
dolphins.edgelist
football.edgelist
polbooks.edgelist
reachability.edgelist
📝 Dataset Format
Unweighted Dataset

Example:

1 2
1 3
2 3
2 4
3 4

Each line represents:

source_node target_node
Weighted Dataset

The weighted reachability dataset follows:

source_node target_node weight

Example:

A B 0.5
A C 1.0
B D 0.8

The third value represents the edge weight.

📁 Project Structure

A recommended GitHub repository structure is:

diffusion-centrality-network-analysis/
│
├── README.md
│
├── LICENSE
│
├── requirements.txt
│
├── .gitignore
│
├── notebooks/
│   └── diffusion_centrality_colab.ipynb
│
├── src/
│   └── diffusion_centrality.py
│
├── datasets/
│   ├── karate.edgelist
│   ├── dolphins.edgelist
│   ├── football.edgelist
│   ├── polbooks.edgelist
│   ├── reachability.edgelist
│   └── README.md
│
├── results/
│   ├── figures/
│   │   ├── karate_top10.png
│   │   ├── dolphins_top10.png
│   │   ├── football_top10.png
│   │   ├── polbooks_top10.png
│   │   └── reachability_top10.png
│   │
│   └── tables/
│       ├── karate_top5.csv
│       ├── dolphins_top5.csv
│       ├── football_top5.csv
│       ├── polbooks_top5.csv
│       └── reachability_top5.csv
│
├── images/
│   ├── diffusion-centrality.png
│   ├── methodology.png
│   └── network-example.png
│
└── docs/
    ├── report.pdf
    └── presentation.pdf
🛠 Technologies Used
Python

Primary programming language.

NetworkX

Used for:

Graph creation
Graph loading
Network representation
Graph analysis
NumPy

Used for:

Adjacency matrices
Matrix operations
Numerical calculations
Eigenvalue computation
SciPy

Used for efficient eigenvalue computation.

Matplotlib

Used for visualization and result charts.

Google Colab

Used for interactive execution and experimentation.

📦 Installation

Clone the repository:

git clone https://github.com/YOUR-USERNAME/diffusion-centrality-network-analysis.git

Move into the project:

cd diffusion-centrality-network-analysis

Install the dependencies:

pip install -r requirements.txt
📋 requirements.txt

The requirements.txt file should contain:

numpy
networkx
scipy
matplotlib

You can also install them directly:

pip install numpy networkx scipy matplotlib
☁️ Google Colab

The project can be executed directly in Google Colab.

The notebook is located at:

notebooks/diffusion_centrality_colab.ipynb

The Colab workflow is:

Google Drive
     ↓
Project Dataset
     ↓
Google Colab
     ↓
Load Graph
     ↓
Calculate Diffusion Centrality
     ↓
Rank Nodes
     ↓
Generate Charts
▶️ Running the Project
Method 1 — Python

Run:

python src/diffusion_centrality.py
Method 2 — Google Colab

Open:

notebooks/diffusion_centrality_colab.ipynb

Run the notebook cells from top to bottom.

The notebook:

Mounts Google Drive.
Copies the project.
Loads the datasets.
Creates graph objects.
Calculates Diffusion Centrality.
Prints top nodes.
Generates charts.
Saves the generated figures.
💻 Google Colab Setup

The notebook starts by mounting Google Drive:

from google.colab import drive

drive.mount('/content/drive')

The project can then be copied:

!cp -r /content/drive/MyDrive/Dataset-NetworkScience .

The project directory is opened:

%cd Dataset-NetworkScience
📊 Output

For every dataset, the program prints information similar to:

============================================================
  DATASET: karate
============================================================
  Nodes : ...
  Edges : ...
  T     : 3

  Top 5 Nodes by Diffusion Centrality
  ------------------------------------------
  Rank  Node                Score
  ------------------------------------------
  1     ...                 ...
  2     ...                 ...
  3     ...                 ...
  4     ...                 ...
  5     ...                 ...
  ------------------------------------------

  ✓ Chart saved: figures_simple/karate_top10.png

The exact node rankings depend on the dataset and graph structure.

📈 Results

The project generates Top-10 Diffusion Centrality charts.

The general visualization looks like:

Node A |████████████████████| 10.245
Node B |██████████████████  |  9.821
Node C |████████████████    |  8.902
Node D |██████████████      |  7.841
Node E |████████████        |  7.125

The longer the bar, the higher the Diffusion Centrality score.

🏆 Top Node Interpretation

The node with the highest Diffusion Centrality is ranked first.

For example:

Rank 1 → Node A
Rank 2 → Node B
Rank 3 → Node C

This means that, under the selected diffusion parameters and network structure, Node A has the highest calculated diffusion influence among the analyzed nodes.

🔬 Comparison with Other Centrality Measures
Centrality	Main Question
Degree	How many direct connections does a node have?
Closeness	How close is a node to the rest of the network?
Betweenness	How often is a node on shortest paths?
Eigenvector	Is the node connected to important nodes?
PageRank	How important are incoming connections?
Diffusion	How effectively can influence spread through the network?
🔵 Degree Centrality

Degree Centrality focuses on immediate connections.

        B
        |
A ----- C ----- D
        |
        E

Node C has many direct connections.

Therefore, its Degree Centrality is high.

However, Degree Centrality does not directly model repeated diffusion.

🟢 Closeness Centrality

Closeness Centrality focuses on the shortest-path distance from a node to other nodes.

A node that can reach other nodes using shorter paths receives higher closeness.

🟠 Betweenness Centrality

Betweenness Centrality focuses on nodes that act as bridges.

A --- B --- C
        |
        D

If many shortest paths pass through B, then B can have high Betweenness Centrality.

🟣 Eigenvector Centrality

Eigenvector Centrality considers the importance of neighboring nodes.

A node connected to highly important nodes can itself receive a high score.

🔴 Diffusion Centrality

Diffusion Centrality considers repeated diffusion:

             Node
               │
               ▼
          1-step spread
               │
               ▼
          2-step spread
               │
               ▼
          3-step spread
               │
               ▼
       Total diffusion influence
📌 Key Difference

A simple way to remember the measures:

Degree       → Direct connections

Closeness    → Distance

Betweenness  → Bridges

Eigenvector  → Important neighbors

Diffusion    → Repeated influence spreading
📊 Interpretation of Results

A high Diffusion Centrality score does not simply mean:

"This node has the most edges."

Instead, it indicates that the node has a strong position for spreading influence through the network according to the chosen diffusion model.

A node can receive a high score because:

It has many neighbors.
Its neighbors are well connected.
It can reach many nodes.
There are many possible paths through the network.
Its influence can propagate effectively over multiple steps.
⚙️ Computational Complexity

The implementation converts the graph into a dense adjacency matrix.

For a graph with n nodes:

A → n × n matrix

Dense matrix operations can become expensive for large networks.

Repeated matrix multiplication is performed for every diffusion step:

(qA)¹
(qA)²
...
(qA)ᵀ

Therefore, computational cost increases with:

Number of nodes
Number of edges
Number of diffusion periods T
Matrix density

For large networks, sparse matrix techniques can significantly improve performance.

⚡ Eigenvalue Optimization

For large symmetric networks, the project uses:

from scipy.sparse.linalg import eigsh

Instead of calculating all eigenvalues, it can calculate the required dominant eigenvalue efficiently.

For smaller or directed networks, the implementation uses:

np.linalg.eigvals(A)
✅ Advantages

Diffusion Centrality has several useful properties.

1. Considers Multiple Steps

It does not only consider direct neighbors.

2. Models Influence

It is useful for studying spreading processes.

3. Flexible

The diffusion period T can be changed.

4. Applicable to Different Networks

It can be applied to:

Social networks
Communication networks
Information networks
Collaboration networks
Sports networks
Biological networks
5. Combines Local and Global Information

The score can capture both direct and indirect network relationships.

⚠️ Limitations
1. Dense Matrix Representation

The current implementation uses:

nx.to_numpy_array(G)

This creates a dense matrix.

Very large graphs can therefore require significant memory.

2. Matrix Multiplication Cost

Repeated matrix multiplication becomes expensive for large networks.

3. Choice of T

The value of T affects the results.

For example:

T = 1

and:

T = 10

can produce different node rankings.

4. Choice of q

The diffusion parameter also influences the diffusion process.

This implementation uses:

$$ q=\frac{1}{\lambda_1} $$
5. Dataset Differences

Different datasets represent different real-world systems.

Therefore, comparing raw scores between completely different datasets should be done carefully.

The ranking within each network is generally more meaningful than comparing absolute scores across unrelated networks.

🚀 Future Improvements

Several improvements can be added in future versions.

1. Sparse Matrix Implementation

Use SciPy sparse matrices instead of dense NumPy matrices.

2. Large Network Support

Optimize the algorithm for networks containing millions of nodes or edges.

3. GPU Acceleration

Use GPU-based matrix operations for very large networks.

4. Interactive Visualization

Add interactive network visualization using tools such as:

Plotly
PyVis
Gephi
5. Centrality Comparison

Compare:

Degree
Closeness
Betweenness
Eigenvector
PageRank
Diffusion Centrality
6. Parameter Analysis

Experiment with:

T = 1
T = 2
T = 3
T = 5
T = 10

and different values of q.

7. Ranking Stability

Study whether the same nodes remain influential when T changes.

Example:

T = 1  → Ranking A
T = 3  → Ranking B
T = 5  → Ranking C
T = 10 → Ranking D

This can be used to analyze ranking stability.

🧪 Suggested Future Experiment

One useful experiment is:

        Diffusion Period
              │
       ┌──────┼──────┐
       ↓      ↓      ↓
      T=1    T=3    T=10
       │      │      │
       └──────┼──────┘
              ↓
       Compare Rankings
              ↓
       Ranking Stability

This can help determine whether the most influential nodes remain consistent as diffusion continues for longer periods.

🔁 Reproducibility

The project is designed so that the experiments can be reproduced.

Basic process:

git clone https://github.com/YOUR-USERNAME/diffusion-centrality-network-analysis.git

cd diffusion-centrality-network-analysis

pip install -r requirements.txt

python src/diffusion_centrality.py

Alternatively, the Google Colab notebook can be executed directly.

🗂️ Recommended GitHub Workflow

The recommended development workflow is:

1. Create GitHub Repository
          ↓
2. Add README.md
          ↓
3. Add requirements.txt
          ↓
4. Add Python source code
          ↓
5. Add Colab notebook
          ↓
6. Add datasets
          ↓
7. Run experiments
          ↓
8. Save results
          ↓
9. Add charts
          ↓
10. Push to GitHub
🔐 Dataset and Copyright Notice

The datasets used in this project may originate from external academic or research sources.

Before publishing the datasets publicly, verify:

Original dataset source
Dataset license
Redistribution permissions
Citation requirements

Dataset-specific information should be documented where applicable.

The code in this repository is intended for educational and research purposes.

📚 Research Background

This project is based on research in network science, social networks, and information diffusion.

Diffusion-based centrality measures are particularly useful when the underlying process involves the spread of information, behavior, resources, or influence through network connections.

The theoretical foundation is related to work by:

Banerjee, Chandrasekhar, Duflo, and Jackson (2013).

The research examines diffusion through social networks in the context of microfinance and information transmission.

📖 Reference

Banerjee, A., Chandrasekhar, A. G., Duflo, E., & Jackson, M. O. (2013).

The Diffusion of Microfinance.

Science, 341(6144), 1236498.

DOI:

10.1126/science.1236498
🧠 Key Takeaway

The central idea of this project is:

A node is not important only because
it has many direct connections.

It can also be important because
influence originating from it can
spread effectively through the network.

In short:

             NETWORK
                │
                ▼
        DIRECT CONNECTIONS
                │
                ▼
       INDIRECT CONNECTIONS
                │
                ▼
        REPEATED DIFFUSION
                │
                ▼
       DIFFUSION CENTRALITY
                │
                ▼
         NODE IMPORTANCE
🎓 Academic Contribution

This project demonstrates the application of concepts from:

Graph Theory
     +
Linear Algebra
     +
Matrix Algebra
     +
Eigenvalue Computation
     +
Network Science
     +
Information Diffusion
     +
Data Visualization

It provides both a theoretical and computational understanding of Diffusion Centrality.

👨‍💻 Author
Divya Shakti

Department of Computer Science
University of Delhi

Project

Diffusion Centrality — Network Science

This project was developed as an academic implementation and experimental study of network diffusion and node influence.

🙏 Acknowledgements

This project uses open-source Python libraries:

NetworkX
NumPy
SciPy
Matplotlib

The theoretical foundation is based on academic research in network science and information diffusion.

📜 License

This project is intended for educational and research purposes.

If you choose an open-source license for the code, you can use an MIT License and include the corresponding LICENSE file in the repository.

⭐ Support

If you find this project useful for learning Network Science, Graph Theory, or Diffusion Centrality, consider giving the repository a ⭐.

<p align="center">

<strong>Network → Diffusion → Influence → Centrality → Analysis</strong>

</p> <p align="center">

Made with Python • NetworkX • NumPy • SciPy • Matplotlib • Google Colab

</p>
