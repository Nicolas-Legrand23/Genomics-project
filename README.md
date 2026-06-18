# NAFLD Transcriptomic Analysis (GSE135251)

This project analyzes bulk RNA-seq data from the GEO dataset **GSE135251**, covering the full spectrum of NAFLD: Control, NAFL, NASH (F0–F4).  
The goal is to identify transcriptomic signatures associated with:

1. **Metabolic dysregulation** (NAFL vs Control)  
2. **Early fibrotic activation** (NASH F2 vs NASH F0–F1)

The analysis is performed entirely in **R** using **DESeq2**, **clusterProfiler**, and standard RNA-seq workflows.

---

## 📁 Repository Structure
```
project/
│
├── Project.Rmd          # Full analysis pipeline
├── Project.html         # Rendered HTML report
├── README.md            # Project documentation
├── figures/             # Exported plots (optional)
└── .gitignore           # Excludes raw GEO files
```

Raw GEO files (`GSE135251/raw/`) are **not included** due to size.  
They can be downloaded automatically by running the R Markdown file.

---

## 🔬 Main Contrasts Analyzed

### 1. NAFL vs Control  
**Biological theme:** Metabolic reprogramming  
- 1102 upregulated genes  
- 1838 downregulated genes  
- Enriched pathways:  
  - Lipid metabolic regulation  
  - Cholesterol biosynthesis  
  - Sterol/secondary alcohol biosynthesis  

### 2. NASH F2 vs NASH F0–F1  
**Biological theme:** Early immune activation  
- 27 upregulated genes  
- 2 downregulated genes  
- Enriched pathways:  
  - Antimicrobial response  
  - Chemotaxis  
  - Humoral immune response  

---

## 📊 Summary Table

| Contrast | Up DEGs | Down DEGs | Main Theme | Key Pathways |
|---------|----------|------------|-------------|----------------|
| NAFL vs Control | 1102 | 1838 | Metabolic reprogramming | Lipid metabolism, cholesterol biosynthesis |
| NASH F2 vs F0–F1 | 27 | 2 | Immune activation | Antimicrobial response, chemotaxis |

---

## 🚀 How to Run the Analysis

1. Open `Project.Rmd` in RStudio  
2. Install required packages (DESeq2, GEOquery, tidyverse, clusterProfiler, etc.)  
3. Knit to HTML  

All raw data will be downloaded automatically.

---

## 📚 Citation

If you use this dataset, please cite the original GEO study:  
**GSE135251 — Sci Transl Med (2020)**.

---

## 👤 Author

**Nicolas Legrand**  
Master 2 Bioinformatics — EFREI Paris  
2026
