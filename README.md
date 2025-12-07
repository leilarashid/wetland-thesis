\# Wetland Classification Research



Thesis research developing methods to predict wetland types (Marsh, Swamp, Fen, Bog) and hydrogeochemical characteristics using remote sensing and field data.



\*\*Author\*\*: Leila Rashid  

\*\*Supervisors\*\*: Murray Richardson, Koreen Millard  

\*\*Institution\*\*: Carleton University



---



\## Project Overview



This repository contains the complete analytical workflow for understanding ecohydrological signals in wetlands and predicting their water chemistry and hydrology using:

\- UAV-derived multispectral imagery and point clouds

\- Satellite remote sensing indices (NDVI harmonics, Tasseled Cap Wetness)

\- Field measurements of water chemistry and hydrology

\- Topographic derivatives from DEM data



---



\## Repository Structure

```

wetland-thesis/

├── variable-reduction/

│   └── shapley.ipynb          # SHAP-based variable selection workflow

├── ordination-analysis/

│   └── RDA\_workflow.ipynb     # Redundancy Analysis (RDA) or Principal Component analysis ordination

├── uav-processing/

│   └── veg-struct-extract.ipynb  # UAV vegetation structure extraction

├── docs/                       # Documentation and meeting notes etc

└── README.md                   # This file

```



---



\## Workflow Description



\### 1. UAV Processing (`uav-processing/`)

Extracts vegetation structure metrics from LiDAR point clouds:

\- Height statistics (mean, median, max, percentiles)

\- Canopy cover at multiple heights

\- Stem density

\- Stratified by vegetation layers



\*\*Input\*\*: UAV point clouds  

\*\*Output\*\*: Site-level vegetation structure metrics



---



\### 2. Variable Reduction (`variable-reduction/`)

Uses SHAP (Shapley Additive exPlanations) with Random Forest to reduce multicollinearity:

\- Applies cumulative SHAP importance thresholds (80-90%)

\- Processes variable groups separately:

&nbsp; - Satellite indices (NDVI harmonics, TCW, SWI)

&nbsp; - Topographic derivatives (multiple resolutions)

&nbsp; - UAV vegetation structure

&nbsp; - Multispectral indices (stricter thresholds)

&nbsp; - Chemistry and hydrology





\*\*Input\*\*: Full wetland dataset with all predictors  

\*\*Output\*\*: Reduced variable set for ordination analysis



---



\### 3. Ordination Analysis (`ordination-analysis/`)

Redundancy Analysis (RDA) to explore relationships between vegetation predictors and hydrogeochemistry:

\- Uses vegetation/remote sensing as predictors (X)

\- Hydrogeochemistry as response (Y)

\- Implements proper handling of censored chemistry data (U-score transformations)



\*\*Current results\*\*:

\- \*\*RDA1\*\*: Hydrogeochemical gradient (mineral-rich fens/marshes ↔ mineral-poor bogs)

\- \*\*RDA2\*\*: Vegetation structure gradient (treed systems ↔ open graminoid systems)

\- \*\*RDA3\*\*: Additional perspectives on system variation



\*\*Input\*\*: Reduced variable dataset from SHAP analysis  

\*\*Output\*\*: Publication-quality ordination plots and interpretation











