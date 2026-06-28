# NAFLD Transcriptomic Analysis (GSE135251)

This project performs a full bulk RNA‑seq analysis of the GEO dataset **GSE135251**, which profiles liver biopsies across the complete NAFLD spectrum:

- Control  
- NAFL (simple steatosis)  
- NASH F0–F4 (fibrosis stages)

The goal is to characterize transcriptomic changes associated with NAFLD progression, from early metabolic dysregulation to advanced fibrotic remodeling.  
The analysis is implemented entirely in **R** using a clean, reproducible R Markdown pipeline.

---

## 📁 Repository Structure
```
project/
│
├── Project.Rmd      # Full analysis pipeline (download → DESeq2 → GO → plots)
├── Project.html     # Rendered HTML report with automatic interpretations
└── README.md        # Project documentation
```

Raw GEO files are **not included** in the repository.  
They are automatically downloaded when knitting the R Markdown file.

---

## 🧬 Analysis Overview

The pipeline performs:

1. Automatic download of raw featureCounts files  
2. Construction of a clean count matrix  
3. Metadata extraction and alignment  
4. DESeq2 differential expression across 5 contrasts  
5. VST transformation  
6. Visualization suite for each contrast:
   - Volcano plot  
   - PCA with variance interpretation  
   - Heatmap of strongly polarized genes  
   - GO enrichment (Biological Process)  
7. Automatic textual interpretation after each plot  
8. Summary table and barplot of DEGs  

The report is fully annotated and designed for interpretability.

---

## 🔬 Contrasts Analyzed

All contrasts are computed as:


Below is a summary of the **actual results produced by the pipeline**.

---

## 📊 Summary of Differential Expression Results

| Contrast | Up DEGs | Down DEGs | Interpretation |
|---------|----------|------------|----------------|
| **NAFL vs Control** | 1102 | 1838 | Strong metabolic + immune remodeling |
| **F0F1 vs Control** | 923 | 1711 | Early NASH signature, moderate immune activation |
| **F2 vs Control** | 1383 | 1836 | Clear fibrotic transition, strong transcriptional shift |
| **F3 vs Control** | 1281 | 1454 | Advanced fibrosis, strong ECM remodeling |
| **F4 vs Control** | 1756 | 1346 | Cirrhosis-like profile, strong immune/fibrotic activation |

These values come directly from the DESeq2 pipeline.

---

## 🧠 Interpretation Highlights

The updated pipeline prints **interpretation blocks directly after each plot**, making the HTML report narrative and easy to read.

### 🔥 Volcano Plots  
- All contrasts show **hundreds to thousands** of DEGs  
- Most contrasts are dominated by **downregulation**, except F4 (upregulation dominates)

### 🔥 PCA  
- PC1 explains **14–19%** of variance  
- PC2 explains **9–11%**  
- Interpretation logic:
  - **PC1 < 10%** → weak structure  
  - **10–20%** → moderate structure (your case)  
  - **>20%** → strong separation  

All contrasts show **moderate separation**, consistent with biological heterogeneity in human biopsies.

### 🔥 Heatmaps  
- All contrasts show **strong polarized signatures**  
- Clear up/down blocks indicate coherent transcriptional programs  

### 🔥 GO Enrichment  
Across contrasts, enriched processes include:

- Lipid metabolism (NAFL)  
- Immune activation (F0F1 → F4)  
- Extracellular matrix organization (fibrosis stages)  
- Chemotaxis / inflammatory response  

These match known NAFLD biology.

---

## 🚀 How to Run the Analysis

1. Open `Project.Rmd` in RStudio  
2. Install required packages:  
   - DESeq2  
   - GEOquery  
   - tidyverse  
   - clusterProfiler  
   - enrichplot  
   - pheatmap  
3. Knit to HTML  

The pipeline automatically:

- downloads raw data  
- builds the count matrix  
- runs DESeq2  
- generates all plots  
- prints interpretations after each visualization  

---

## 📚 Dataset Citation

If you use this dataset, please cite:

**GSE135251 — Sci Transl Med (2020)**  
"Transcriptomic profiling of NAFLD progression in human liver biopsies."

---

## 👤 Author

**Nicolas Legrand**  
Master 2 Bioinformatics — EFREI Paris  
2026

