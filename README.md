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

### Next step
Wednesday: differential expression analysis — which genes distinguish
metastatic from non-metastatic tumors?
