## Proyecto 2: Gene Expression Quality Control — GSE2034

Analysis of a real breast cancer gene expression dataset from NCBI GEO.

**Dataset:** GSE2034 — 286 breast cancer patients, 22,283 genes measured  
**Source:** NCBI Gene Expression Omnibus (used in 500+ published papers)

### What this project does
- Downloads GSE2034 directly from GEO using GEOparse
- Applies log2 transformation to normalize expression values
- Detects outlier samples using ±2 standard deviation threshold
- Filters low-variability genes (removes bottom 25% by std)
- Generates QC visualizations following bioinformatics paper standards

### Key results
- 286 samples — no outliers detected (high quality dataset)
- 22,283 genes → 16,712 after QC filtering
- Expression range after log2: 2.14 — 14.93

### Technologies
Python · GEOparse · Pandas · NumPy · Matplotlib · Seaborn · SciPy

---

## Proyecto 3: Differential Expression Analysis — GSE2034

Identified genes associated with bone relapse in breast cancer
using 286 primary tumor samples from NCBI GEO.

**Dataset:** GSE2034 — same cohort as Project 2, now analyzed for
bone relapse prediction using primary tumor gene expression.

**Biological context:** RNA was extracted from primary breast tumors
at surgery — before any relapse occurred. The genes found were already
altered at diagnosis, making them potential early predictive markers.

### What this project does
- Separates 286 patients into bone relapse (n=69) vs no relapse (n=217)
- Runs t-test for each of the 16,712 filtered genes
- Applies Benjamini-Hochberg FDR correction to control false positives
- Filters DEGs with FDR < 0.05 and |log2FC| > 1
- Generates volcano plot and heatmap of top 30 DEGs

### Key results
- 35 differentially expressed genes identified
- 28 downregulated in bone relapse — putative tumor suppressors silenced
- 7 upregulated — candidate progression markers
- Most significant gene: 214777_at (FDR = 0.005)

### Visualizations
- `volcano_plot.png` — significance vs fold change for all 16,712 genes
- `heatmap_DEGs.png` — expression signature of top 30 DEGs across 286 patients

### Technologies
Python · Pandas · SciPy · Statsmodels · Matplotlib · Seaborn

### Next step
ML model to predict bone relapse using the 35 DEGs as features
