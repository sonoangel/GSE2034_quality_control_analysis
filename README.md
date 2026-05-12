# Breast Cancer Bone Relapse — Bioinformatics Analysis

Complete bioinformatics analysis of gene expression data from 286
breast cancer patients to identify molecular predictors of bone relapse.

**Dataset:** GSE2034 — Wang et al. 2005, The Lancet  
**Source:** NCBI Gene Expression Omnibus  
**Tools:** Python · Pandas · SciPy · scikit-learn · Matplotlib · Seaborn

---

## Project Structure

### 📊 Project 1 — Quality Control
`GSE2034_quality_control.ipynb`
- Downloads GSE2034 from NCBI GEO
- log2 normalization of 22,283 genes
- Outlier detection and low-variability gene filtering
- **Result:** 16,712 informative genes, 0 outlier samples

### 🧬 Project 2 — Differential Expression Analysis  
`GSE2034_differential_expression.ipynb`
- t-test across 16,712 genes + Benjamini-Hochberg FDR correction
- Volcano plot and heatmap of top 30 DEGs
- **Result:** 35 DEGs (7 up, 28 down in bone relapse)

### 🔵 Project 3 — PCA and Clustering
`GSE2034_PCA_clustering.ipynb`
- PCA reducing 16,712 dimensions to 2 components
- K-means clustering with optimal K selection
- **Result:** 3 molecular subgroups with different relapse rates
  - Cluster 1 (n=115): **38.3% relapse — HIGH RISK**
  - Cluster 2 (n=57):  **8.8% relapse — LOW RISK**
  - Cluster 3 (n=114): **17.5% relapse — INTERMEDIATE**

### 🔬 Project 4 — Complete Integrated Analysis
`GSE2034_complete_analysis.ipynb`
- End-to-end pipeline: QC → DEG → PCA → Clustering
- Single reproducible notebook with all analyses

---

## Key Visualizations

| Analysis | File |
|----------|------|
| QC distribution | qc_distribucion.png |
| Volcano plot | volcano_plot.png |
| DEG heatmap | heatmap_DEGs.png |
| PCA patients | pca_pacientes.png |
| Molecular clusters | clustering_final.png |

---

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn statsmodels
jupyter notebook
```

Download GSE2034_series_matrix.txt.gz from:
https://ftp.ncbi.nlm.nih.gov/geo/series/GSE2nnn/GSE2034/matrix/

---

*Biological Engineer specializing in Bioinformatics + AI*
