# Chicago Traffic Crashes – Data Mining Project (Group 7)

Se mined Chicago crash data (crashes, people, vehicles) to understand patterns, form clusters, and build a predictive model. 
## Collaborators

| Name            | GitHub Profile                                             |
|-----------------|------------------------------------------------------------|
| Giuliano Difranco | [@GiulianoWasHere](https://github.com/GiulianoWasHere)   |
| Marco Lavorini   | [@lavo2](https://github.com/lavo2)                        |



## Data Sources (Chicago Open Data)
* Crashes: https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if
* People: https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d
* Vehicles: https://data.cityofchicago.org/Transportation/Traffic-Crashes-Vehicles/68nd-jvt3
Derived incident/profile CSVs are created during Task 1 and saved under `dataset/` along with cleaned versions (so notebooks can run offline).

## Project Tree
```
.
├── README.md
├── requirements.txt
├── crash_map.html
├── crash_map_bin.html
├── dataset/
│   ├── crashes.csv
│   ├── people.csv
│   └── vehicles.csv
├── DM_Group7_TASK1/
│   ├── 1.1_Understanding.ipynb
│   ├── 1.2-distribution.ipynb
│   └── 1.3-profile_DU.ipynb
├── DM_Group7_TASK2/
│   ├── Outliers-removal.ipynb
│   ├── Kmeans++.ipynb
│   ├── Kmeans_Elbow.ipynb
│   ├── Kmeans_hierarchical_K3.ipynb
│   ├── Kmeans_hierarchical_K6.ipynb
│   └── DBSCAN.ipynb
├── DM_Group7_TASK3/
│   └── 3-prediction.ipynb
├── DM_Report_Group7.pdf
└── Project DM 2024-25 - Crahses.pdf
```

## Task 1 – Understand & Prepare
Notebooks: `1.1_Understanding`, `1.2-distribution`, `1.3-profile_DU`.
We look at columns, missing values, types, merge the main tables, remove unusable rows, examine core distributions (time, weather, location, severity) and engineer incident profile features. Result: cleaned + profiled CSVs used later.

## Task 2 – Clustering
Notebooks: outlier handling + K-Means (plus + elbow), hierarchical (k=3 vs k=6), DBSCAN. We test different notions of similarity: centroid-based, hierarchical structure, and density. We compare inertia/silhouette and interpret clusters (e.g., time-of-day, weather, severity mixes).

## Task 3 – Prediction
Notebook: `3-prediction`. We build a supervised model for crash severity / injury outcome. Steps: split data, handle imbalance, train baseline vs stronger models (see notebook), evaluate with accuracy plus recall/precision/F1 (and ROC where relevant). Output: performance tables and plots.

## Map Visualization
`crash_map.html` (and the binary variant) is an interactive map layering crash density/severity. Open it directly in a browser; it’s generated from cleaned data.

## Environment
Python 3.10+. Install deps:
```
pip install -r requirements.txt
```
Run notebooks in order (Task 1 → 2 → 3). Paths assume repository root as working directory.

## Report
`DM_Report_Group7.pdf` is our written summary; the project brief PDF is the original assignment.