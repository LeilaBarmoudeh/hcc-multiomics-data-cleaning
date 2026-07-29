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
<img width="686" height="311" alt="Scr" src="https://github.com/user-attachments/assets/92326d4a-62a6-4b95-a561-2b615303c806" />

# After Cleaning
 Parsed and Standardized Format
<img width="596" height="92" alt="Scr" src="https://github.com/user-attachments/assets/1e7bc575-a483-494c-923f-ac0ca238b06a" />


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
  # Data Availability
Original patient-level datasets are not included due to privacy and data-sharing restrictions.
# Example of Python pipline
from src.clean_phosphoproteomics import clean_phospho
from src.clean_proteomics import clean_protein
from src.clean_rnaseq import clean_rnaseq
from src.harmonize_samples import harmonize_samples


def main():
    phospho = clean_phospho(
        "data/raw_examples/phosphoproteomics_raw_mock.csv"
    )

    protein = clean_protein(
        "data/raw_examples/proteomics_raw_mock.csv"
    )

    rnaseq = clean_rnaseq(
        "data/raw_examples/rnaseq_raw_mock.csv"
    )
 cleaned = harmonize_samples(phospho, protein, rnaseq)

    for name, df in cleaned.items():
        df.to_csv(
            f"data/processed_examples/{name}_cleaned.csv",
            index=False
        )


if __name__ == "__main__":
    main()


if __name__ == "__main__":
    main()
