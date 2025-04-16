# Neotis-GTEx-v1
Analysis of v10 of publicly available GTEx data with 20-29 vs oldest

Neotis Bioinformatics Analysis Pipeline

A collection of Python scripts for comprehensive analysis of GTEx aging data, transposable element (TE) density, functional analysis, and report generation.

Table of Contents

Installation

Usage

Scripts Overview

Workflow

Contributing

License

Installation

Clone the repository:

git clone https://github.com/yourusername/neotis-pipeline.git
cd neotis-pipeline

(Optional) Create and activate a virtual environment:

python3 -m venv venv
source venv/bin/activate

Install required Python packages:

pip install -r requirements.txt

Requirements include: numpy, pandas, scipy, matplotlib, seaborn, statsmodels, pydeseq2, requests, tqdm, plus optional: scanpy, anndata, leidenalg.

Usage

Each script can be run from the command line. Use -h or --help to list available options.

python "Gtex data preperation - 1.py" [--force_reload]
python "Diffrential expression analysis - 2.py" --design "~condition"
python "Functional analysis - Diffrential analysis.py"
python "Functional analysis - GO term analysis.py"
python "Download and calculate TE - 5.py"
python "TE differential enrichment.py"
python "Visualisations - DE heatmaps.py"
python "Visualisations - GO terms.py"
python "Report generation.py" --base-dir ./Neotis

Scripts Overview

1. GTEx Data Preparation (Gtex data preperation - 1.py)

Description: Load and preprocess GTEx v10 RNA-seq data and metadata; checkpoint support.

Key Features: dependency check, GCT parsing, gene info cleaning.

2. Differential Expression Analysis (Diffrential expression analysis - 2.py)

Description: Perform differential expression between age groups in GTEx tissues using PyDESeq2.

Key Features: MA/volcano plots, top-gene heatmaps, B-statistic calculation.

3. Advanced Functional Analysis (Functional analysis - Diffrential analysis.py)

Description: Generate SQL-ready outputs, top-100 gene matrices, similarity analyses, transmembrane subset processing.

Key Features: BioMart integration, hypergeometric tests, age-specific matrices.

4. GO Enrichment Analysis (Functional analysis - GO term analysis.py)

Description: Execute GO enrichment per tissue and grouped tissues (BP, CC, MF categories).

Key Features: Tissue grouping, multiple comparison correction, output TSV/CSV.

5. TE Density Calculation (Download and calculate TE - 5.py)

Description: Download Ensembl and UCSC annotations; compute TE density across chromosomes; visualize distributions.

Key Features: Parallel processing, retry logic, chromosome-based parsing.

6. TE Differential Enrichment (TE differential enrichment.py)

Description: Compare TE-enriched regions with DE gene sets; perform permutation and Fisher’s tests.

Key Features: TSS assignment, binning, enrichment classification, overlap statistics.

7. DE Heatmaps and Volcano Plots (Visualisations - DE heatmaps.py)

Description: Create comprehensive heatmaps and volcano plots for general, upregulated, and transmembrane genes; tissue similarity matrices.

Key Features: Custom colormaps, labeled volcano, large-scale figure generation.

8. GO Term Visualisation (Visualisations - GO terms.py)

Description: Generate bar plots and dot plots of top GO terms for common and tissue-specific analyses.

Key Features: Network graphs, heatmaps, category-wise plotting.

9. HTML Report Generation (Report generation.py)

Description: Compile visualizations and analyses into an interactive HTML report.

Key Features: Dynamic tabs, embedded images, data tables, GTEx contrasts.

Workflow

A typical analysis pipeline might follow:

Data prep: Gtex data preperation - 1.py

DE analysis: Diffrential expression analysis - 2.py

Functional & SQL outputs: Functional analysis - Diffrential analysis.py

GO enrichment: Functional analysis - GO term analysis.py

TE analysis: Download and calculate TE - 5.py → TE differential enrichment.py

Visualisations: Visualisations - DE heatmaps.py → Visualisations - GO terms.py

Report: Report generation.py

