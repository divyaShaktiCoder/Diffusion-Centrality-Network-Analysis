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
🌐 Diffusion Centrality
Simple Network Analysis with Python
<p align="center"> <b>Measure node importance through network diffusion.</b><br> Analyze multiple real-world networks and visualize the most influential nodes. </p> <p align="center">







</p>
✨ What is this?

Diffusion Centrality measures how important a node is based on how effectively information, influence, or connections can spread through a network.

This project provides a simple Python implementation that calculates Diffusion Centrality and identifies the most important nodes in different networks.

The program automatically:

📥 Loads network datasets
→ 🧮 Calculates Diffusion Centrality
→ 🏆 Finds the Top 5 nodes
→ 📊 Creates a Top 10 visualization
→ 💾 Saves the results as PNG images

🧠 How it works

The implementation uses:

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

Where:

Symbol	Meaning
A	Adjacency matrix
q	Inverse of the largest eigenvalue
T	Number of diffusion steps
DC	Diffusion Centrality
⚙️ Current setting
T = 3


The algorithm considers paths up to 3 diffusion steps through the network.

📊 Networks

This project analyzes 5 different network datasets:

🗂️ Dataset	🔗 Network Type
🥋 Karate	Undirected
🐬 Dolphins	Undirected
🏈 Football	Undirected
📚 PolBooks	Undirected
🌐 Reachability	Weighted + Directed
🚀 Getting Started
1️⃣ Open Google Colab

Upload:

diffusion_centrality_simple.py

2️⃣ Add the project to Google Drive

The expected location is:

MyDrive/
└── Dataset-NetworkScience/


The program automatically mounts Google Drive and copies the project into Colab.

3️⃣ Run the program

That's it.

The program processes all available datasets automatically.

🏆 Output

For every dataset, the program displays:

Top 5 Nodes
DATASET: karate

Nodes : 34
Edges : 78
T     : 3

Top 5 Nodes by Diffusion Centrality

Rank   Node          Score
--------------------------------
1      ...           ...
2      ...           ...
3      ...           ...
4      ...           ...
5      ...           ...


It also creates a Top 10 bar chart.

📈 Visual Results

Place the generated charts inside:

figures_simple/


Then they can be displayed directly in GitHub.

🥋 Karate

🐬 Dolphins

🏈 Football

📚 PolBooks

🌐 Reachability

📁 Project Structure
Dataset-NetworkScience/
│
├── 📄 diffusion_centrality_simple.py
│
├── 📊 karate.edgelist
├── 📊 dolphins.edgelist
├── 📊 football.edgelist
├── 📊 polbooks.edgelist
├── 📊 reachability.edgelist
│
└── 📁 figures_simple/
    ├── 🖼️ karate_top10.png
    ├── 🖼️ dolphins_top10.png
    ├── 🖼️ football_top10.png
    ├── 🖼️ polbooks_top10.png
    └── 🖼️ reachability_top10.png

🛠️ Built With
Technology	Purpose
🐍 Python	Main programming language
🔗 NetworkX	Network analysis
🔢 NumPy	Matrix calculations
⚡ SciPy	Eigenvalue calculation
📊 Matplotlib	Data visualization
☁️ Google Colab	Execution environment
📦 Installation

If running locally:

pip install numpy networkx matplotlib scipy


Or simply run the project in Google Colab.

🎯 Project Goal

The main goal is to provide a clear and easy-to-understand implementation of Diffusion Centrality.

Instead of only producing numerical values, this project also provides visualizations that make it easier to identify and compare the most important nodes.

💡 Why Diffusion Centrality?

Traditional centrality measures often focus on immediate connections.

Diffusion Centrality considers multiple steps of network diffusion.

In simple terms:

        Node
         │
    ┌────┴────┐
    ▼         ▼
 Neighbor   Neighbor
    │         │
    ▼         ▼
  Next      Next
  Layer     Layer


This allows the method to capture the broader reach of a node within a network.

📌 Key Features

✅ Simple implementation

✅ Multiple network datasets

✅ Directed network support

✅ Weighted network support

✅ Automatic eigenvalue calculation

✅ Top 5 node ranking

✅ Top 10 visualization

✅ PNG output

✅ Google Colab compatible

⭐ Summary

Input

Network Dataset
      ↓


Processing

Adjacency Matrix
      ↓
Largest Eigenvalue
      ↓
Calculate q
      ↓
Diffusion Centrality
      ↓


Output

🏆 Top 5 Nodes
      +
📊 Top 10 Chart

<p align="center"> <b>🌐 Diffusion Centrality</b><br> Network Analysis • Node Importance • Data Visualization </p>
