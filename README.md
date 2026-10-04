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
Diffusion Centrality

A simple Python implementation of Diffusion Centrality for network datasets.

The program:

📊 Calculates Diffusion Centrality for every node

🏆 Shows the Top 5 nodes

📈 Creates a Top 10 bar chart

💾 Saves charts as PNG images

🌐 Supports both weighted and directed networks

☁️ Runs easily in Google Colab

📌 Formula

The Diffusion Centrality used in this project is:

DC = [(qA)¹ + (qA)² + ... + (qA)ᵀ] × 1

Where:

A = adjacency matrix

q = inverse of the largest eigenvalue of A

T = number of diffusion steps

DC = Diffusion Centrality score

This project uses:

T = 3

📂 Datasets

The program can process these datasets:

Dataset	Type
🥋 Karate	Undirected
🐬 Dolphins	Undirected
🏈 Football	Undirected
📚 PolBooks	Undirected
🔗 Reachability	Weighted + Directed

Dataset files should be placed in the project folder.

🚀 How to Run
1. Open Google Colab

Upload/open the Python file:

diffusion_centrality_simple.py

2. Mount Google Drive

The notebook automatically mounts Google Drive and copies the project:

from google.colab import drive
drive.mount('/content/drive')


Make sure your project folder is available at:

MyDrive/Dataset-NetworkScience

3. Run the program

The program will:

Load each dataset

Calculate Diffusion Centrality

Print the Top 5 nodes

Create a Top 10 bar chart

Save the chart in:

figures_simple/

📊 Example Output
============================================================
  DATASET: karate
============================================================
  Nodes : 34
  Edges : 78
  T     : 3

  Top 5 Nodes by Diffusion Centrality
  ------------------------------------------
  Rank  Node                Score
  ------------------------------------------
  1     ...
  2     ...
  3     ...
  4     ...
  5     ...
  ------------------------------------------

  ✓ Chart saved: figures_simple/karate_top10.png

🖼️ Generated Charts

A separate chart is created for each dataset:

figures_simple/
├── karate_top10.png
├── dolphins_top10.png
├── football_top10.png
├── polbooks_top10.png
└── reachability_top10.png


Each chart shows the 10 nodes with the highest Diffusion Centrality.

🛠️ Requirements

Install the required Python packages with:

pip install numpy networkx matplotlib scipy


Google Colab already provides most of these packages.

📦 Main Libraries

NumPy — numerical calculations

NetworkX — network and graph analysis

SciPy — largest eigenvalue calculation

Matplotlib — visualization

📁 Project Structure
Dataset-NetworkScience/
│
├── diffusion_centrality_simple.py
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

🎯 Purpose

The goal of this project is to provide a simple and easy-to-understand implementation of Diffusion Centrality for studying the importance of nodes in different networks.

Higher Diffusion Centrality means that a node can potentially reach or influence more of the network through multiple steps.

👨‍💻 Technologies

Python · NetworkX · NumPy · SciPy · Matplotlib · Google Colab

⭐ Result

The project provides both:

Numerical results → Top 5 important nodes

Visual results → Top 10 Diffusion Centrality bar charts

This makes it easy to compare important nodes across different network datasets.
