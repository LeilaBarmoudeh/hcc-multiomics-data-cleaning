# hcc-multiomics-data-cleaning
Python pipeline for cleaning and harmonizing HCC phosphoproteomics, proteomics, and RNA-seq matrices with matched tumor/normal samples.

This repository contains a reproducible Python workflow for cleaning and harmonizing hepatocellular carcinoma (HCC) multi-omics datasets.
The project integrates:
- Phosphoproteomics (phosphosite abundance)
- Proteomics (protein abundance)
- Transcriptomics (RNA-seq expression)
- Matched tumor/normal samples
The pipeline transforms raw omics matrices into standardized and analysis-ready datasets suitable for downstream statistical and machine-learning workflows.
# Example of Raw Data
Raw phosphoproteomics matrices contained compound feature identifiers and wide-format sample matrices.
# Before Cleaning
idx                                      111      114
ENSG00000003056.8|ENSP00000000412.3|S267|DDQLGEESEERDDHL|1
# After Cleaning
# Parsed and Standardized Format
gene_id         protein_id      site    sample_111_T
ENSG00000003056 ENSP00000000412 S267    23.95
Challenges before cleaning:
- Compound feature annotations
- Numeric sample labels
- Missing values
- Non-standardized metadata
- Multi-layer sample alignment
Improvements:
- Structured metadata columns
- Harmonized sample identifiers
- Analysis-ready matrices
- Explicit tumor/normal labels
# Tools
Python via Jupyter
# Packages in Python
- pandas
- numpy
- matplotlib
- seaborn
- scipy
