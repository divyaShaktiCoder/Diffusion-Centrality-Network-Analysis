Diffusion Centrality
<p align="center"> <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/NetworkX-Analysis-orange?style=flat-square"> <img src="https://img.shields.io/badge/NumPy-Matrix%20Operations-013243?style=flat-square&logo=numpy"> <img src="https://img.shields.io/badge/SciPy-Scientific%20Computing-8CAAE6?style=flat-square&logo=scipy"> <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat-square"> </p> <p align="center"> A simple implementation of <b>Diffusion Centrality</b> for identifying important nodes in complex networks. </p> 

Diffusion Centrality

Implementation and analysis of Diffusion Centrality on real-world network datasets using Python.

📌 About

Diffusion Centrality measures the importance of a node based on how effectively influence can spread through a network over multiple steps.

📊 Datasets

All datasets are already included in the datasets/ folder:
Karate Club
Dolphins
Football
Political Books
Reachability

📦 Installation

1. Open the notebook in Google Colab and run the cells in order.
2.Required libraries can be installed using:
   !pip install numpy networkx scipy matplotlib

📁 Project Structure
├── datasets/
│   ├── karate.edgelist
│   ├── dolphins.edgelist
│   ├── football.edgelist
│   ├── polbooks.edgelist
│   └── reachability.edgelist
│
├── src/
├── notebooks/
└── README.md

▶️ Run
Open diffusion_centrality_colab.ipynb in Google Colab.
Mount Google Drive if required.
Make sure the datasets are available.
Run all cells.

📈 Results
For each dataset, the project:

Calculates Diffusion Centrality
Displays the Top 5 nodes
Generates Top 10 node visualizations



