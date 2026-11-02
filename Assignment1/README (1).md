> **AI Assistance Declaration**: I used Claude (Anthropic) for README structure and drafting, script design planning, and review feedback on my code. Prompts used: see the AI Assistance Disclosure section at the bottom of this file and `Appendix.md`. I verified outputs using {methods, e.g. running the script, knitting the .Rmd, GitHub preview, comparison with a tidyverse README}. All final calculations are done by myself. I am responsible for the accuracy and originality of this work.

# Synthetic Retail Sales Summary

An R project that generates a synthetic retail sales dataset, summarizes total revenue by region, and exports the results as a CSV file and a bar chart.

## Overview

`sales_summary.R` generates 500 rows of synthetic retail sales data (dates in 2025), summarizes total revenue by region, and exports a CSV and a bar chart. The script is documented step by step in `sales_summary_doc.Rmd`.

- Reproducible: the random seed is fixed with `set.seed(123)`
- Self-checking: the script verifies its own results before finishing
- Synthetic data only: no real or personal data is used

## Project Structure

```text
markdown-buddy-habeeb/
├── README.md
├── Reflection.md
├── Appendix.md
├── LICENSE
├── sales_summary.R
├── sales_summary_doc.Rmd
└── output/
    ├── revenue_by_region.csv
    └── revenue_by_region.png
```

The `output/` folder is created by the script when it runs.

## Requirements

- R
- `dplyr` 1.0.0 or later (the script uses `summarise(.groups = ...)`)
- `ggplot2` (this also installs `scales`, which the chart uses for axis labels)
- To knit the `.Rmd`: `rmarkdown` and `knitr` (RStudio and Posit Cloud include both)

## Installation

Clone the repository and install the packages:

```bash
git clone https://github.com/<your-username>/markdown-buddy-habeeb.git
cd markdown-buddy-habeeb
```

```r
install.packages(c("dplyr", "ggplot2"))
```

## Example Usage

Run the script from the project root, because `output/` is a relative path.

From a terminal:

```bash
Rscript sales_summary.R
```

Or from an R session:

```r
source("sales_summary.R")
```

The script prints the regional revenue table to the console, writes both output files, and ends with `All checks passed.`

To build the documentation, open `sales_summary_doc.Rmd` in RStudio or Posit Cloud and click **Knit**.

## Outputs

| File | Description |
|------|-------------|
| `output/revenue_by_region.csv` | Total revenue per region, sorted descending and rounded to 2 decimals |
| `output/revenue_by_region.png` | Bar chart of revenue by region |

## Verification

The script runs its own checks at the end and prints `All checks passed.` if they succeed:

1. The data has exactly 500 rows.
2. Each region's total is recomputed independently in base R and matches the summary table.
3. Both output files exist.

## Reproducibility

The script uses `set.seed(123)`, so repeated runs give identical data and an identical CSV. To confirm, compare `tools::md5sum("output/revenue_by_region.csv")` across two runs.

## License

This project is released under the [MIT License](LICENSE).

## AI Assistance Disclosure

**Tool used:** Claude (Anthropic), October 2026.

**Main prompts:**

- {paste your seed prompt for the README outline}
- {paste your refinement prompt}
- {paste your critique/validation prompt}
- {paste your prompts for the script design plan and the script review}

The full prompts and key responses are in [`Appendix.md`](Appendix.md).

**Changes I made after reviewing the outputs:**

- Wrote `sales_summary.R` myself from an AI-suggested section layout
- Rounded the regional totals to 2 decimals
- Added comma formatting to the chart's y-axis
- Extended the cross-check to recompute every region's total, not only one
- Updated the README to match what the script actually does
- {add any edits you made after previewing on GitHub or knitting the .Rmd}
