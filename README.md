# AEDE 8895 AI Demo

This repository contains materials for demonstrating AI-assisted workflows in research, including a Quarto presentation and an Ohio property tax analysis project.

## Project Structure

```
.
├── ai-workflow-talk.qmd        # Quarto presentation source
├── ai-workflow-talk.html       # Rendered presentation
├── custom.scss                 # OSU-branded theme
├── code/
│   └── ohio_tax_analysis.R     # Main analysis script
├── data/
│   └── raw/
│       └── 2024-sd-rates.xlsx  # School district millage rates
├── output/
│   ├── ohio_school_districts_floor_map.png
│   ├── greene_county_tax_comparison.png
│   └── top_counties_at_floor.png
└── newsletter-data/            # Reference materials
    └── ohio-property-tax-analysis/
```

---

## Ohio Property Tax Analysis

Analysis of how Ohio's 2024 property tax reforms (HB 186) affect school districts differently based on their millage rates relative to the 20-mill floor.

### Data Sources

| Data | Source | File |
|------|--------|------|
| School district millage rates | Ohio Dept. of Education, Tax Year 2024 | `data/raw/2024-sd-rates.xlsx` |
| Geographic boundaries | U.S. Census Bureau TIGER/Line (2023) | Downloaded via `tigris` package |
| Property tax examples | Greene County Auditor | Hardcoded in script |

### Requirements

R packages:
- `tidyverse`
- `sf`
- `readxl`
- `scales`
- `tigris`
- `viridis`

Install all dependencies:
```r
install.packages(c("tidyverse", "sf", "readxl", "scales", "tigris", "viridis"))
```

### Reproducing the Analysis

From the project root directory:

```r
source("code/ohio_tax_analysis.R")
```

The script will:
1. Read school district millage data from `data/raw/`
2. Download Ohio school district boundaries from Census TIGER/Line
3. Merge datasets using numeric keys (93.6% match rate)
4. Generate three visualizations in `output/`:
   - `ohio_school_districts_floor_map.png` - Statewide map of districts by floor status
   - `greene_county_tax_comparison.png` - Property tax comparison for two homes
   - `top_counties_at_floor.png` - Bar chart of top 10 counties by floor districts

### Key Findings

- **356 districts (62%)** are at the 20-mill floor
- **217 districts (38%)** are above the floor
- Rural/exurban districts are predominantly at the floor; urban/suburban districts are above

### Policy Context

- **HB 920 (1976)**: Protected homeowners from automatic tax increases during reappraisals—but only for districts above the 20-mill floor
- **HB 186 (2024)**: Extended protections to floor districts, but eliminated automatic revenue growth they previously received

---

## Quarto Presentation

### Rendering

```bash
quarto render ai-workflow-talk.qmd
```

### Presenting

- Arrow keys or spacebar to advance
- `S` for speaker notes
- `F` for fullscreen
- `O` for slide overview

### Theme Colors

OSU colors in `custom.scss`:
- Scarlet: `#BB0000`
- Gray: `#666666`
