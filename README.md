# Pathway-GNN: Interpretable Single-Cell Clustering via Pathway-Aware Graph Learning

This repository contains the implementation, datasets, results and additional materials for the paper:

**Pathway-GNN: Interpretable Single-Cell Clustering via Pathway-Aware Graph Learning**  
_Preveena K V, Manu Madhavan, Prashanth Suravjhalla (2025)_

The framework integrates curated biological pathway knowledge into single-cell representation learning by constructing pathway-specific bipartite gene–cell graphs, followed by graph neural network (GNN) based embedding, attention-driven pathway attribution, and self-supervised contrastive training.

---

## Key Features
- Pathway-specific bipartite graph construction from scRNA-seq data
- GCN / GraphSAGE based pathway embedding
- Attention mechanism to learn pathway importance per cell
- Contrastive learning for label-free clustering
- Supports clustering evaluation (Silhouette, ARI, NMI, AMI)
- Works for both healthy and disease tissue datasets


## Repository Structure

Pathway-GNN/
│
├── notebooks/
│ └── pathway_gnn_pipeline.ipynb # End-to-end Colab notebook
│
├── results/
│ ├── UMAP_visualizations/ # Cell embedding visualizations
│ ├── Pathway_attention_heatmaps/ # Cluster-specific pathway attributions
│ └── Confusion_matrices/ # Cluster ↔ cell-type correspondence
│
├── supplementary/
│ ├── Additional document/
│
└── README.md

## 🧰 Dependencies

| Package | Version |
|--------|---------|
| Python | ≥ 3.12 |
| PyTorch | ≥ 2.8 |
| PyTorch Geometric | ≥ 2.6 |
| Scanpy | ≥ 1.11 |
| NetworkX | ≥ 2.7 |
| scikit-learn | ≥ 1.6 |

Install required packages:
pip install torch torch-geometric scanpy networkx umap-learn scikit-learn

## Running the Pipeline
Google Colab
Open the notebook directly:
notebooks/pathway_gnn_pipeline.ipynb

Upload the following inputs:

Expression matrix (.csv with genes × cells and metadata columns)
Pathway gene sets (.gmt format)

Then run all cells. Output includes:

Final cell embeddings
KMeans / Leiden clustering
Pathway attribution heatmaps
UMAP visualizations

## Data Availability
The single-cell RNA-seq datasets used in this study are publicly available through the NCBI Gene Expression Omnibus (GEO).  
Pancreatic datasets were obtained from GEO under accession number **GSE84133**.  
Choroid datasets were obtained from GEO under accession number **GSE183320**.  
