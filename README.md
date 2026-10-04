Diffusion Centrality
<p align="center"> <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/NetworkX-Analysis-orange?style=flat-square"> <img src="https://img.shields.io/badge/NumPy-Matrix%20Operations-013243?style=flat-square&logo=numpy"> <img src="https://img.shields.io/badge/SciPy-Scientific%20Computing-8CAAE6?style=flat-square&logo=scipy"> <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat-square"> </p> <p align="center"> A simple implementation of <b>Diffusion Centrality</b> for identifying important nodes in complex networks. </p> <p align="center"> <a href="#overview">Overview</a> • <a href="#method">Method</a> • <a href="#datasets">Datasets</a> • <a href="#results">Results</a> • <a href="#usage">Usage</a> </p>
Overview

Diffusion Centrality measures the importance of a node by considering how influence can spread through a network over multiple steps.

This project calculates Diffusion Centrality for several network datasets, ranks the nodes, and generates visualizations of the 10 most central nodes.

Pipeline
Network
   │
   ▼
Adjacency Matrix
   │
   ▼
Largest Eigenvalue
   │
   ▼
Diffusion Parameter q
   │
   ▼
Diffusion Centrality
   │
   ├──────────────► Top 5 Nodes
   │
   └──────────────► Top 10 Visualization

Method

The implementation follows:

𝐷
𝐶
=
∑
𝑙
=
1
𝑇
(
𝑞
𝐴
)
𝑙
1

where:

$A$ is the adjacency matrix

$q$ is the inverse of the largest eigenvalue of $A$

$T$ is the number of diffusion steps

$\mathbf{1}$ is an all-ones vector

For this project:

T = 3


The largest eigenvalue is calculated automatically for each network.

Datasets
Dataset	Nodes	Network
Karate	34	Undirected
Dolphins	—	Undirected
Football	—	Undirected
PolBooks	—	Undirected
Reachability	—	Weighted / Directed

The datasets are stored as .edgelist files and loaded automatically by the program.

Results

The program produces two types of results:

Ranking

Top 5 Nodes
───────────────
1. Node   Score
2. Node   Score
3. Node   Score
4. Node   Score
5. Node   Score


Visualization

Each dataset produces a horizontal bar chart containing the Top 10 nodes ranked by Diffusion Centrality.

Karate
<p align="center"> <img src="figures_simple/karate_top10.png" width="750"> </p>
Dolphins
<p align="center"> <img src="figures_simple/dolphins_top10.png" width="750"> </p>
Football
<p align="center"> <img src="figures_simple/football_top10.png" width="750"> </p>
PolBooks
<p align="center"> <img src="figures_simple/polbooks_top10.png" width="750"> </p>
Reachability
<p align="center"> <img src="figures_simple/reachability_top10.png" width="750"> </p>
Usage
Google Colab

The project is designed to run directly in Google Colab.

Place the project in:

Google Drive
└── MyDrive
    └── Dataset-NetworkScience


Then run:

diffusion_centrality_simple.py


The script automatically:

Mounts Google Drive

Loads the datasets

Calculates Diffusion Centrality

Prints the Top 5 nodes

Generates Top 10 charts

Saves the charts in figures_simple/

Installation

For local execution:

pip install numpy networkx scipy matplotlib


Then run:

python diffusion_centrality_simple.py

Project Structure
Dataset-NetworkScience/
│
├── diffusion_centrality_simple.py
│
├── karate.edgelist
├── dolphins.edgelist
├── football.edgelist
├── polbooks.edgelist
├── reachability.edgelist
│
└── figures_simple/
    ├── karate_top10.png
    ├── dolphins_top10.png
    ├── football_top10.png
    ├── polbooks_top10.png
    └── reachability_top10.png

Requirements
Python 3.x
NumPy
NetworkX
SciPy
Matplotlib

Why Diffusion Centrality?

Unlike measures based only on immediate connections, Diffusion Centrality considers paths across multiple steps.

This makes it useful for studying networks where influence, information, or interaction can propagate beyond a node's direct neighbors.

Output

For each dataset:

Dataset
   │
   ├── Network statistics
   │
   ├── Top 5 nodes
   │
   └── Top 10 Diffusion Centrality chart


Charts are saved automatically as:

figures_simple/<dataset>_top10.png

<p align="center"> <sub>Network Analysis • Diffusion Centrality • Python</sub> </p>
