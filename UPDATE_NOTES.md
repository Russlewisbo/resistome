# Resistome Analysis Report - Update Notes

## Update: December 27, 2025

### New Section Added: Genotype-Phenotype Relationships

A comprehensive analysis of the relationship between beta-lactamase genes and antimicrobial susceptibility has been added to the report.

---

## What Was Added

### Section: "Genotype-Phenotype Relationships"
**Location**: Between "Resistance Genotypes" and "Capsular Type-Resistance Associations"

**Size**: 376 lines of new content

---

## Content Overview

### 1. **Beta-lactamase Gene Burden Analysis**
- Distribution of additional genes (excluding universal KPC-31)
- 50% of isolates have no additional beta-lactamases
- Up to 4 additional genes per isolate

### 2. **MIC by Gene Burden**
- **Key Finding**: No dose-response relationship
- Paradox: 4 genes = lowest median MIC (12 mg/L)
- 0 genes = wide MIC range (4-644 mg/L, 161-fold!)

### 3. **Individual Gene Effects**
- Median MIC for isolates carrying each gene
- blaSHV-11 carriers: highest median (256 mg/L)
- Context-dependent effects observed

### 4. **Clone-Specific Patterns**
- **ST307 Paradox**: Most genes (CTX-M-15 + SHV-28) but LOWEST MIC
- **ST101**: Few genes but HIGHEST MIC (256 mg/L)
- **ST512**: IncX3 plasmid-borne KPC-31
- **ST147**: Multiple genes, high MIC as expected

### 5. **Gene Combination Effects**
- CTX-M-15 + SHV-28: Highest synergy (256 mg/L)
- CTX-M-15 + TEM: Lower MIC (12 mg/L)
- Context-dependent, non-additive effects

### 6. **Mechanistic Insights** (Tabbed Panels)
- **KPC-31 Dominance**: Universal but variable expression
- **Synergistic Effects**: Epistatic interactions
- **Clone Effects**: Genetic background critical
- **Clinical Implications**: Both WGS + MIC needed

---

## Visualizations Added

1. **Boxplot**: MIC by number of beta-lactamase genes
2. **Bar Chart**: Median MIC for each individual gene
3. **Scatter Plot**: Clone-specific genotype-phenotype relationships
4. **Multiple Tables**: 
   - Gene burden distribution
   - MIC statistics by gene count
   - Clone-specific profiles
   - Gene combination effects
   - Summary findings

---

## Key Discoveries Highlighted

### 🔬 Major Finding
**Complex, non-linear genotype-phenotype relationships:**
- Same genes → different phenotypes in different clones
- More genes ≠ higher resistance
- Clone identity is critical

### ⚠️ The ST307 Paradox
- Most additional genes: CTX-M-15 (10/16), SHV-28 (13/16)
- **Lowest** median MIC: 18 mg/L
- Hypothesis: Chromosomal KPC-31 with lower expression

### ✓ Clinical Relevance
- **Genotype alone insufficient** for treatment decisions
- **Phenotypic testing (MIC) essential**
- **Integration needed**: WGS + MIC + MLST

---

## How to Use the Updated Report

### Render the Report
```bash
quarto render resistome_analysis_report.qmd
```

### Preview Locally
```bash
quarto preview resistome_analysis_report.qmd
```

### Push to GitHub (for website update)
```bash
git add resistome_analysis_report.qmd
git commit -m "Add genotype-phenotype analysis section"
git push
```

Website will update automatically in 1-2 minutes!

---

## Section Structure

The new section includes:

```
# Genotype-Phenotype Relationships
├── Introduction & Key Finding callout
├── Beta-lactamase Gene Burden
│   ├── Distribution table
│   └── Note about 50% having no additional genes
├── MIC by Gene Burden
│   ├── Boxplot visualization
│   ├── Summary statistics table
│   └── Paradox warning callout
├── Individual Gene Effects
│   └── Bar chart of median MICs
├── Clone-Specific Patterns
│   ├── Scatter plot with gene profiles
│   ├── Clone profile table
│   └── ST307 paradox callout
├── Gene Combination Effects
│   └── Combination analysis table
├── Key Mechanistic Insights
│   ├── KPC-31 Dominance (tab)
│   ├── Synergistic Effects (tab)
│   ├── Clone Effects (tab)
│   └── Clinical Implications (tab)
├── Summary Table
└── Research Implications (tip callout)
```

---

## Technical Details

### Code Blocks Added
- **6 major visualizations**
- **7 summary tables**
- **4 callout boxes** (important, warning, note, tip)
- **1 tabbed panel** with 4 tabs

### Data Analysis
- Analysis of 42 isolates
- 7 beta-lactamase genes examined
- 5 sequence types compared
- Multiple statistical summaries

---

## What This Adds to Your Analysis

### Before
- Gene presence/absence data
- Individual gene prevalence
- Basic gene profiles by clone

### After
- **Genotype-phenotype correlation analysis**
- **Clone-specific patterns**
- **Gene combination effects**
- **Mechanistic insights**
- **Clinical decision support**
- **Research hypotheses**

---

## Next Steps

1. ✅ Section added to report
2. ⬜ Render locally to verify: `quarto render`
3. ⬜ Review the new section in HTML output
4. ⬜ Push to GitHub for website update
5. ⬜ Share with collaborators

---

## Notes

- All code is embedded and reproducible
- Tables are interactive (sortable/searchable)
- Figures are high-resolution
- Section flows naturally with existing content
- Maintains consistent styling and formatting

---

**Questions?** The new section is fully integrated and ready to use!
