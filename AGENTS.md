# KPC-31 Resistome Project — Memory File

## Project Summary
Analysis of 42 KPC-31-carbapenemase-producing *Klebsiella pneumoniae* (n=33, 78.6%) and *Escherichia coli* (n=9, 21.4%) clinical isolates. Combines whole-genome sequencing (resistome, MLST, plasmid typing) with phenotypic antimicrobial susceptibility testing (MIC, 26 antibiotics).

## Primary Data File
- **File:** `Progetto 1 (KPC-31) versione 2.xlsx`
- **Sheet:** `Foglio1`
- **Loading:** `read_excel(file_path, sheet = "Foglio1", skip = 0)`
- **Structure:** Row 1 = some headers, Row 2 = antibiotic/gene names, Rows 3–44 = data
- **Columns:**
  - 1–6: ID, SPECIES, CLINICAL_SOURCE, ST, Wzi, KL
  - 7: CAZ-AVI MIC
  - 8–34: Other antibiotic MICs (names from row 2)
  - 35–48: Beta-lactamase genes (see below)
  - 49–112: Other resistance genes (aminoglycosides, quinolones, sulfonamides, etc.)
  - 113–134: Plasmid incompatibility groups
- **Total columns:** 155

## Data Loading Pattern
```r
file_path <- "Progetto 1 (KPC-31) versione 2.xlsx"
resistome_full <- read_excel(file_path, sheet = "Foglio1", skip = 0)
row2 <- as.character(resistome_full[2, ])
final_data <- resistome_full[3:nrow(resistome_full), ]
colnames(final_data)[1:6] <- c("ID", "SPECIES", "CLINICAL_SOURCE", "ST", "Wzi", "KL")
colnames(final_data)[7] <- "CAZ-AVI"
# Antibiotic names from row2[8:34]
# Beta-lactamase gene names set manually (cols 35–48)
# Column names sanitised: hyphens and spaces → underscores
```

## Beta-lactamase Gene Column Names (cols 35–48, after sanitising)
`BlaCTXM-15`, `bla_TEM-1`, `blaTEM-1A`, `blaTEM-1B`, `blaSHV-1`, `blaSHV-11`, `blaSHV-28`, `BlaSHV-106`, `BlaSHV-158`, `blaKPC`, `BlaKPC-31`, `blaOXA-1`, `bla_OXA-9`, `bla_OXA-18`

**Important:** After `gsub("-","_",...)` sanitisation the names become e.g. `bla_TEM_1`, `BlaCTXM_15` etc. Use sanitised names when subsetting `analysis_data`.

## Key Known Column Name Issue (fixed)
- `bla TEM_1` (with space) was a bug — correct sanitised name is `bla_TEM_1`

## MIC Extraction Helper
```r
extract_mic_numeric <- function(x) {
  sapply(x, function(val) {
    if (is.na(val) || val == "") return(NA_real_)
    as.numeric(gsub("[^0-9.]+", "", as.character(val)))
  })
}
```

## Key Findings
- **100%** of isolates carry *blaKPC-31*
- **Sequence types:** ST307 (n=16, 50%), ST101 (n=7, 21.9%), ST512 (n=5, 15.6%), ST147 (n=2), ST131 (n=2, *E. coli*)
- **CAZ-AVI resistance (MIC >16):** 35.7% overall; ST101, ST512, ST147 = 100%; ST307 = heterogeneous (median 18 mg/L)
- **ST307 paradox:** highest β-lactamase gene burden but lowest median MIC — possible chromosomal KPC-31 integration
- **ST101:** sparse resistome but carries *armA* (pan-aminoglycoside resistance)
- **ST512:** 100% IncX3 plasmid association
- **ST147:** highest gene count per isolate (up to 15), carries *fosA*
- **45%** of isolates carry no additional β-lactamase genes beyond *blaKPC-31*
- **IncF** plasmids detected across 4 STs — active HGT signal

## Project File Structure
```
resistome/
├── Progetto 1 (KPC-31) versione 2.xlsx   # Primary data
├── _quarto.yml                            # Site config (navbar updated Apr 2026)
├── styles.css
├── index.qmd                              # Homepage
├── resistome_analysis_report.qmd          # Comprehensive resistance analysis
├── resistome_genotype_phenotype_final.qmd # Genotype-phenotype correlations
├── manuscript.qmd                         # Scientific manuscript draft (NEW)
├── references.bib                         # BibTeX references for manuscript (NEW)
├── about.qmd
├── AGENTS.md                              # This memory file
└── docs/                                  # Rendered site (GitHub Pages)
    ├── index.html
    ├── manuscript.html
    ├── resistome_analysis_report.html
    ├── resistome_genotype_phenotype_final.html
    └── ...
```

## Quarto Site
- **Framework:** Quarto website, rendered to `docs/`
- **Deployment:** GitHub Pages from `docs/` on `main` branch
- **Repo:** https://github.com/Russlewisbo/resistome
- **Navbar:** Home | Full Report | Beta-lactamase analysis | Manuscript | About | [GitHub icon]
- **Render command:** `quarto render` (from project root)
- **Render single file:** `quarto render manuscript.qmd --to html`

## Manuscript (manuscript.qmd)
- **Title:** "Genomic and phenotypic characterization of KPC-31-producing *Klebsiella pneumoniae* and *Escherichia coli*: convergence of high-risk clones and complex genotype-phenotype relationships"
- **Sections:** Abstract, Introduction, Results (with live R table), Discussion, References
- **Methods:** To be written by co-author
- **References:** 15 citations in `references.bib`
- **Format:** HTML only (kableExtra incompatible with docx)
- **Status:** Draft — author review pending

## Known Bugs Fixed (April 2026)
1. `resistome_genotype_phenotype_final.qmd` chunk `tem-mer-analysis`: column `"bla TEM_1"` (space) → `"bla_TEM_1"` (underscore)
2. Same file: Wilcoxon test wrapped in `tryCatch()` — one group had too few observations
3. Same file: `tbl-tem-mer-summary` — `data.frame()` crash on NA values; replaced with safe helper functions
4. `manuscript.qmd`: removed `docx` format target (incompatible with kableExtra HTML output)

## R Environment
- R 4.5.1, Positron 2026.04.0
- Key packages: `tidyverse`, `readxl`, `ggplot2`, `knitr`, `kableExtra`
EOF 2>&1
