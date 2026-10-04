# Diffusion Centrality: Network Analysis

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![NetworkX](https://img.shields.io/badge/NetworkX-Network%20Analysis-orange.svg)](https://networkx.org/)
[![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-blue.svg)](https://numpy.org/)
[![SciPy](https://img.shields.io/badge/SciPy-Scientific%20Computing-green.svg)](https://scipy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-red.svg)](https://matplotlib.org/)


![GitHub stars](https://img.shields.io/github/stars/divyaShaktiCoder/Diffusion-Centrality-Network-Analysis?style=for-the-badge&logo=github) ![GitHub forks](https://img.shields.io/github/forks/divyaShaktiCoder/Diffusion-Centrality-Network-Analysis?style=for-the-badge&logo=github) ![GitHub issues](https://img.shields.io/github/issues/divyaShaktiCoder/Diffusion-Centrality-Network-Analysis?style=for-the-badge&logo=github) ![Last commit](https://img.shields.io/github/last-commit/divyaShaktiCoder/Diffusion-Centrality-Network-Analysis?style=for-the-badge&logo=github)


# Diffusion Centrality

---

## 🔍 Overview

**Diffusion Centrality** measures how effectively influence can spread from a node through a network over multiple steps.

This project implements Diffusion Centrality **from scratch** using graph datasets and evaluates it on **five real-world network datasets**.

### Formula

```math
DC(q,T)=\left[\sum_{l=1}^{T}(qA)^l\right]\mathbf{1}
```

**Parameters used:**

```text
T = 3
q = 1 / λ₁
```

where `A` is the adjacency matrix and `λ₁` is the largest eigenvalue of `A`.

---

## 📊 Datasets

| Dataset            | Network Type              |
| ------------------ | ------------------------- |
| 🥋 Karate Club     | Social Network            |
| 🐬 Dolphins        | Social Network            |
| 🏈 Football        | Sports Network            |
| 📚 Political Books | Book Network              |
| 🔗 Reachability    | Directed Weighted Network |

All datasets are included in the **`datasets/`** folder.

Each dataset is stored as an **edge list**, where each row represents a connection between two nodes.

Example:

```text
1 2
1 3
2 4
3 4
```

For the weighted dataset:

```text
1 2 0.75
1 3 0.42
2 4 0.91
```

---

## 🧩 Dataset Preparation

The datasets are used directly from the `.edgelist` files.

The process is:

```text
Raw Edge List
      ↓
Read Dataset
      ↓
Create NetworkX Graph
      ↓
Handle Directed / Undirected Graph
      ↓
Handle Weighted / Unweighted Edges
      ↓
Create Adjacency Matrix
      ↓
Apply Diffusion Centrality
```

### Graph Construction

For **unweighted datasets**, every edge represents a connection:

```text
A[i][j] = 1
```

For the **weighted reachability dataset**, the edge value represents the connection strength:

```text
A[i][j] = weight
```

The graph is then converted into an adjacency matrix `A`.

---

## 🧠 Diffusion Centrality From Scratch

The centrality calculation is implemented without using a pre-built Diffusion Centrality function.

### Step 1 — Create Adjacency Matrix

For a graph:

```text
1 ─── 2
│     │
└── 3 ┘
```

the adjacency matrix represents which nodes are connected.

```text
A =
[0 1 1]
[1 0 1]
[1 1 0]
```

### Step 2 — Find Largest Eigenvalue

The largest eigenvalue of the adjacency matrix is calculated:

```text
λ₁ = largest eigenvalue of A
```

Then:

```text
q = 1 / λ₁
```

This scaling factor controls the diffusion process.

### Step 3 — Simulate Diffusion

For `T = 3`:

```text
(qA)
(qA)²
(qA)³
```

The final calculation is:

```math
DC = (qA)1 + (qA)^2 1 + (qA)^3 1
```

where `1` is a vector of ones.

### Step 4 — Calculate Node Scores

The resulting values represent the Diffusion Centrality score of each node.

A higher score means that the node can potentially influence or reach more nodes through the network.

### Step 5 — Rank Nodes

Finally, nodes are sorted according to their Diffusion Centrality scores.

```text
Rank    Node    Score
1       ...     ...
2       ...     ...
3       ...     ...
```

---

## ⚙️ How It Works

```text
Dataset
   ↓
Create Graph
   ↓
Adjacency Matrix
   ↓
Find λ₁
   ↓
Calculate q
   ↓
Calculate (qA), (qA)², (qA)³
   ↓
Calculate Centrality Scores
   ↓
Rank Nodes
   ↓
Visualize Results
```

---

## ☁️ Google Drive & Colab Setup

The project is run using **Google Colab** and the project folder is stored in Google Drive.

### 1. Upload the Project Folder

Upload the complete project folder to:

```text
Google Drive
└── MyDrive
    └── Dataset-NetworkScience/
```

The folder should contain the datasets and project files.

### 2. Mount Google Drive

Run this cell in Google Colab:

```python
from google.colab import drive

drive.mount('/content/drive')
```

After running it, authorize Google Drive access.

### 3. Copy the Project to Colab

Copy the project folder from Google Drive:

```python
!cp -r /content/drive/MyDrive/Dataset-NetworkScience .
```

### 4. Open the Project Folder

```python
%cd Dataset-NetworkScience
```

Now the project files can be accessed directly from the Colab environment.

### 5. Check the Files

```python
!ls
```

You should see the project files and folders.

For example:

```text
README.md
datasets
src
notebooks
results
```

---

## 📦 Installation

Install the required Python libraries in Google Colab:

```python
!pip install numpy networkx scipy matplotlib
```

---

## 📁 Project Structure

```text
Dataset-NetworkScience/
│
├── datasets/                  # Network datasets
│   ├── karate.edgelist
│   ├── dolphins.edgelist
│   ├── football.edgelist
│   ├── polbooks.edgelist
│   └── reachability.edgelist
│
├── src/                       # Diffusion Centrality implementation
│   └── diffusion_centrality.py
│
├── notebooks/                 # Google Colab notebook
│   └── diffusion_centrality_colab.ipynb
│
├── results/                   # Generated results
│   └── figures/
│
└── README.md
```

---

## ▶️ Run

1. Upload `Dataset-NetworkScience` to Google Drive.
2. Open the notebook in **Google Colab**.
3. Mount Google Drive.
4. Copy the project folder to Colab.
5. Move into the project directory.
6. Install the required libraries.
7. Run the notebook cells in order.
8. View the ranked nodes and generated visualizations.

---

## 📈 Results

For each network, the program:

* Calculates Diffusion Centrality
* Finds the **Top 5 influential nodes**
* Generates a **Top 10 visualization**

Example:

```text
Top 5 Nodes
────────────
Rank  Node  Score
1     ...   ...
2     ...   ...
3     ...   ...
4     ...   ...
5     ...   ...
```

Generated visualizations are stored in:

```text
results/figures/
```

---

## 📚 Reference

Banerjee, A., Chandrasekhar, A. G., Duflo, E., & Jackson, M. O. (2013).

**The Diffusion of Microfinance.**
*Science, 341(6144).*

---

## 👨‍💻 Author

**Divya Shakti**
Department of Computer Science
University of Delhi

---

<p align="center">
  ⭐ If you found this project useful, consider starring the repository.
</p>
