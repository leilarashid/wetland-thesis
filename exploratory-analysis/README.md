\# Exploratory Analysis



\*\*Purpose:\*\* Understand data distributions, correlations, and outliers after u-score transformation and before SHAP variable reduction.



\*\*Input:\*\* `wetland\_alldata\_2025\_only\_uscore.csv` 



\*\*Outputs:\*\* 

\- Diagnostic plots saved to `figures/`



\*\*Workflow position:\*\*

1\. ← After: `chem-preprocessing/calculate\_uscores.ipynb`

2\. → Before: `variable-reduction/shapley.ipynb`



\## Running the analysis

```r

\# From RStudio or R console

source("exploratory\_stats.R")

```



\## Key findings to document

\- Which chemistry group (and other data groups) variables show best class separation?

\- Which variable groups are highly intercorrelated (SHAP inflation risk)?

\- Any problematic outliers requiring investigation?

\- Variance differences justifying z-score standardization?

