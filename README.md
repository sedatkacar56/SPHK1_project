# Sphk1\_Project

## Author: Sedat Kacar

## Date: 2/25/25

### Description

This project involves single-cell RNA sequencing (scRNA-seq) analysis using the Seurat package in R. The analysis includes quality control, normalization, integration, clustering, and pathway enrichment for various conditions related to the Sphk1 project.

### Requirements

To run this project, you need the following:

- R (version 4.0 or later)
- The following R packages installed:
  - `Seurat`
  - `dplyr`
  - `ggplot2`
  - `gridExtra`
  - `tidyr`
  - `SingleR`
  - `celldex`
  - `Azimuth`
  - `clusterProfiler`
  - `org.Mm.eg.db`
  - `ReactomePA`
  - `gageData`
  - `pathview`
  - `KEGGREST`

### Data

- The dataset consists of 10X Genomics H5 files for different experimental conditions.
- Data is loaded using `Read10X_h5()`.
- Filtering criteria include:
  - Minimum 100 genes per cell
  - Maximum 5000 genes per cell
  - Mitochondrial gene percentage <10%
  - Minimum total RNA counts of 800 and maximum of 17000

### Analysis Workflow

1. **Quality Control & Filtering**

   - Calculate mitochondrial gene percentage.
   - Perform feature scatter plots and violin plots for QC.
   - Subset the data based on QC criteria.

2. **Normalization & Feature Selection**

   - Normalize data using `NormalizeData()`.
   - Identify variable features with `FindVariableFeatures()`.

3. **Integration of Multiple Datasets**

   - Use `FindIntegrationAnchors()` and `IntegrateData()` to integrate multiple conditions.

4. **Clustering & Dimensionality Reduction**

   - Perform PCA (`RunPCA`), UMAP (`RunUMAP`), and clustering (`FindNeighbors`, `FindClusters`).
   - Visualize clusters using `DimPlot()`.

5. **SCTransform Normalization**

   - Normalize with `SCTransform()` for more accurate integration.

6. **Cell Type Annotation**

   - Transfer cell type labels using `FindTransferAnchors()` and `TransferData()`.
   - Integrate external annotations (`SingleR`, `Azimuth`).

7. **Differential Expression Analysis**

   - Identify marker genes using `FindMarkers()`.
   - Generate DotPlots and FeaturePlots for visualization.

8. **Pathway & Functional Enrichment Analysis**

   - Perform KEGG pathway enrichment using `gage()` and `enrichKEGG()`.
   - Conduct Gene Ontology (GO) enrichment with `enrichGO()`.
   - Reactome pathway analysis with `ReactomePA()`.
   - Visualize results using bar plots, dot plots, and pathway maps from `pathview()`.

### Output

- **Plots & Figures:**
  - Quality control plots (FeatureScatter, VlnPlot)
  - UMAP/PCA visualizations for clustering
  - Dot plots & feature plots for gene expression
  - Bar plots for pathway enrichment
- **Data Files:**
  - Integrated Seurat objects for downstream analysis
  - CSV files containing differentially expressed genes
  - KEGG, GO, and Reactome enrichment results

### How to Run

1. Clone this repository.
2. Open R or RStudio.
3. Load the required libraries.
4. Run the scripts in sequence for data preprocessing, integration, clustering, and enrichment analysis.

### License

This project is open-source under the MIT License.

SEDAT KACAR

INDIANA UNIVERSITY - Pulmonary Division
