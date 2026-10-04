# Diffusion Centrality

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/NetworkX-Analysis-orange?style=flat-square">
  <img src="https://img.shields.io/badge/NumPy-Matrix%20Operations-013243?style=flat-square&logo=numpy">
  <img src="https://img.shields.io/badge/SciPy-Scientific%20Computing-8CAAE6?style=flat-square&logo=scipy">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat-square">
</p>

<p align="center">
  <b>Network analysis using Diffusion Centrality</b>
</p>

<p align="center">
  A simple Python implementation for identifying influential nodes in complex networks through multi-step diffusion.
</p>

---

## 🔍 Overview

**Diffusion Centrality** measures how effectively influence can spread from a node through a network over multiple steps.

This project implements Diffusion Centrality and tests it on **five real-world network datasets**.

### Formula

$$
DC(q,T)=\left[\sum_{l=1}^{T}(qA)^l\right]\mathbf{1}
$$

**Parameters used:**

```text
T = 3
q = 1 / λ₁
```

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
Diffusion for T = 3
   ↓
Calculate Centrality Scores
   ↓
Rank Nodes
   ↓
Visualize Results
```

---

## 🛠️ Technologies

`Python` · `NetworkX` · `NumPy` · `SciPy` · `Matplotlib` · `Google Colab`

---

## 📦 Installation

This project is designed to run in **Google Colab**.

Open:

```text
notebooks/diffusion_centrality_colab.ipynb
```

Install the required libraries:

```python
!pip install numpy networkx scipy matplotlib
```

---

## 📁 Project Structure

```text
├── datasets/                  # Network datasets
│   ├── karate.edgelist
│   ├── dolphins.edgelist
│   ├── football.edgelist
│   ├── polbooks.edgelist
│   └── reachability.edgelist
│
├── src/                       # Python implementation
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

1. Open the notebook in **Google Colab**.
2. Make sure the `datasets/` folder is available.
3. Install the required libraries.
4. Run the notebook cells in order.

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
