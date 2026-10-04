# Diffusion Centrality — Network Science

Implementation of **Diffusion Centrality** for analyzing the influence and importance of nodes in different networks.

## 📌 Overview

Diffusion Centrality measures how effectively influence can spread from a node through a network over multiple steps.

The formula used is:

\[
DC(q,T)=\left[\sum_{l=1}^{T}(qA)^l\right]\mathbf{1}
\]

where:

- `A` = Adjacency Matrix
- `q` = Diffusion parameter
- `T` = Number of diffusion steps

In this project:

```text
T = 3
q = 1 / λ₁
