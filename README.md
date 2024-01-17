## Research Summary: Analysing Road Crashes in Greater Melbourne using Machine Learning

### **1. Methodology**
#### **1.1 Study Area and Data Sources**
- **Region**: Greater Melbourne.
- **Features**: Environmental, road, socio-economic, and demographic attributes.
- **Machine Learning Models Used**: Random Forest and Geographically Weighted Regression.
- **Datasets**:
  - Crash records from VicRoads (2015-2020).
  - Melbourne road network and Points of Interest (OpenStreetMap).
  - Satellite-derived metrics: LST, NDBI, NDVI.
  - 2020 census data.

![image](https://github.com/chrisxj33/Capstone-Research/assets/53899548/97ccec76-043b-46e4-a836-03ea2e7a7ead)

#### **1.2 Multi-Technique Machine Learning Approach**
- **Random Forest**: 
  - Captured complex, non-linear relationships.
  - Managed numerous features and handled collinearity.
  - Interpretability enhanced using SHAP values.
- **Generalised Linear Regression (GLR)**:
  - Preliminary feature selection step.
  - Selected statistically significant values (p-value < 0.01).
- **Geographically Weighted Regression (GWR)**:
  - Accounted for spatial autocorrelation of road crashes.
  - Provided localised parameter estimates for varied impact across regions.

#### **1.3 Hexagonalisation (H3 Geospatial Indexing)**
- Developed by Uber Technologies.
- Multi-resolution analysis capturing patterns at various spatial scales.
- Addressed Modifiable Areal Unit Problem (MAUP).
- Compared hexagonal units with traditional administrative boundaries for spatial consistency.

#### **1.4 Data Pre-Processing**
- Data cleaning to address null values and irrelevant data.
- Derived features, e.g., road curvature (from OSM road network) and slope (using the Victorian DEM).
- Aggregated datasets into hexagonal grids using H3 Python library.
- Used Random Forest model with 'crash count' as the target variable.
- Visualized feature importance scores and summarized SHAP values.
- Addressed potential multi-collinearity using a VIF threshold of 10.

#### **1.5 Features for GWR Model**
- **Resolution 7 Features**: Other Road Length, Total Nodes, Male Population (%), Childless Population (%), Avg. Vegetation Index, Avg. Land Surface Temperature, Avg. Built-Up Index, Total Bridges, Total Tunnels, English Speaking Population (%), Sum Tourism POIs, Sum Leisure POIs.
- **Resolution 8 Features**: Avg. Vegetation Index, Avg. Land Surface Temperature, Avg. Built-Up Index, Total Bridges, Total Tunnels, Residential Road Length, Link Road Length, Total Roundabouts, Avg. Roads at Intersections, Avg. Speed Limit, Avg. Road Curvature.

### **Tools and Software**
- **Python Libraries**: H3, SHAP, Pandas, Geopandas, scikit-learn.
- **Spatial Software**: ArcGIS Pro, QGIS.
- **Statistical Software**: R.
