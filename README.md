### Analysis of UK Road Traffic Accidents (2016-2020)

#### Data Overview
The dataset under analysis consists of road traffic accidents in the UK from 2016 to 2020. Various attributes such as location coordinates (longitude, latitude), temporal data (time, year), and other accident-specific details are included.

#### Data Cleaning and Preparation
Initially, the dataset is examined for data types, null values, and duplicates:
- Missing values are identified and removed.
- Duplicate records are dropped.
- Unnecessary columns (`lsoa_of_accident_location`, `accident_index`, `accident_reference`, `date`, `accident_year`) are excluded to streamline the dataset.

The `time` column is transformed to extract the hour of the day, which is a more meaningful feature for analysis. Categorical columns are encoded using `LabelEncoder` to prepare for clustering.

#### Exploratory Data Analysis (EDA)
Several visualizations are created to understand the data distribution and trends over time:
1. **Line Plots**: Display the temporal trends of attributes like `longitude`, `location_northing_osgr`, `location_easting_osgr`, and `accident_year`. This helps identify any significant changes or patterns across the years.
2. **Scatter Plots**: Illustrate the relationships between different pairs of attributes (e.g., `longitude` vs. `latitude`, `location_northing_osgr` vs. `longitude`). These plots reveal the geographical distribution and clustering tendencies in the data.
3. **Histograms**: Show the frequency distribution of attributes, highlighting the central tendencies and spread of values for `longitude`, `location_northing_osgr`, `location_easting_osgr`, and `accident_year`.

#### Clustering Analysis
**KMeans Clustering**:
- **Elbow Method**: The elbow method is used to determine the optimal number of clusters by plotting distortions (inertia) for different cluster counts. The plot suggests that 2 or 3 clusters are optimal.
- **Clustering Execution**: KMeans is applied with 2 and 3 clusters, and the results are visualized:
  - **2-Cluster Visualization**: Scatter plot of `latitude` vs. `longitude` shows two distinct clusters.
  - **3-Cluster Visualization**: Similar scatter plot with three clusters, along with a 3D scatter plot (`latitude`, `longitude`, and `time`), offering deeper insight into the clustering structure.

**DBSCAN Clustering**:
- Density-Based Spatial Clustering of Applications with Noise (DBSCAN) is performed to identify clusters of varying densities and outliers.
- A scatter plot of `latitude` vs. `longitude` with color-coded clusters is generated, providing a visual representation of how accidents are distributed spatially and the density-based clusters formed.

#### Key Insights
1. **Temporal Patterns**: Line plots indicate how accident-related variables have evolved over the years, potentially reflecting changes in road safety measures or traffic patterns.
2. **Geographical Distribution**: Scatter plots and histograms reveal the spread and concentration of accidents across different regions, aiding in identifying high-risk areas.
3. **Cluster Analysis**: KMeans and DBSCAN clustering highlight underlying patterns in the data. The elbow method suggests 2 or 3 clusters as optimal, and the subsequent visualizations help in understanding these groupings. DBSCAN's density-based approach further identifies areas with high accident density and outliers, providing a nuanced view of accident hotspots.

#### Conclusion
The analysis of the UK road traffic accidents dataset from 2016 to 2020 reveals significant temporal and geographical patterns. Clustering analysis offers valuable insights into the data structure, helping to identify high-risk areas and patterns in accident occurrences. This comprehensive exploration can inform future road safety policies and targeted interventions to reduce traffic accidents.
### Dataset link:
https://www.kaggle.com/datasets/benjaminfox/uk-road-traffic-data-2016-2020
