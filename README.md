# Clustering Analysis Of Gas Turbine Operational Patterns

This project involves the use of clustering analysis to identify operational patterns in gas turbine performance. Two machine learning clustering algorithms, k-Means and Hierarchical clustering, are trained on a dataset to find patterns representing the operational characteristics of gas turbines.

## Table of Contents
- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [Data Exploration and Preparation](#data-exploration-and-preparation)
- [Model Design and Implementation](#model-design-and-implementation)
- [Result Analysis and Discussion](#result-analysis-and-discussion)
- [Ethical, Legal, and Professional Considerations](#ethical-legal-and-professional-considerations)
- [Conclusion](#conclusion)
- [References](#references)

## Introduction

With the increasing use of gas turbines in power production, it is essential to understand their operational patterns to reduce environmental impact and maximize efficiency. This study utilizes clustering analysis to identify innate operating patterns in gas turbines using a dataset comprising various sensor measurements.

## Dataset Overview

The dataset includes variables such as ambient temperature (AT), pressure (AP), humidity (AH), air filter difference pressure (AFDP), gas turbine exhaust pressure (GTEP), turbine inlet temperature (TIT), turbine after temperature (TAT), compressor discharge pressure (CDP), turbine energy yield (TEY), carbon monoxide (CO), and nitrogen oxides (NOx). The dataset consists of 7628 rows of data, aggregated over one hour.

## Data Exploration and Preparation

1. **Initial Exploration**:
    - Viewed the top five and bottom rows using `head()` and `tail()` functions.
    - Summarized data types and checked for missing values with `info()` and `isnull().sum()` functions.
    - Displayed statistical summaries using `describe()`.

2. **Pairplot Visualization**:
    - Created a matrix of pairplots using Seaborn to visualize variable relationships.
    - Identified positive and negative correlations between variables, e.g., GTEP and CO are positively correlated, while GTEP and TAT are negatively correlated.

3. **Missing Value Check**:
    - Verified no missing values using `isnull().sum()`.

4. **Data Preprocessing**:
    - Standardized the features using `StandardScaler` to eliminate mean and scale variance to one.

## Model Design and Implementation

1. **k-Means Clustering**:
    - Used the elbow method to determine the optimal number of clusters.
    - Applied k-Means clustering with the optimal number of clusters.
    - Reduced dimensionality using Principal Component Analysis (PCA) to retain important information.

2. **Hierarchical Clustering**:
    - Utilized a dendrogram to determine the optimal number of clusters.
    - Applied hierarchical clustering with the optimal number of clusters.

## Result Analysis and Discussion

- **Cluster Visualization**:
    - Identified three clusters:
        - **Cluster 1 (blue)**: Normal operation of the gas turbine.
        - **Cluster 2 (red)**: Suboptimal operating conditions.
        - **Cluster 3 (green)**: Unusual sensor measurements indicating system failure or malfunction.

- **Evaluation Metrics**:
    - Used `silhouette_score` and `davies_bouldin_score` to evaluate the models.
    - Achieved silhouette scores of 0.44 for k-Means and 0.40 for Hierarchical clustering.
    - Achieved Davies-Bouldin scores of 0.90 for k-Means and 0.98 for Hierarchical clustering.

## Ethical, Legal, and Professional Considerations

- The dataset is licensed under the Creative Commons Attribution 4.0 International license, allowing use for research purposes with appropriate credit.

## Conclusion

This research utilized k-Means and Hierarchical clustering algorithms to analyze gas turbine performance and identify operational patterns. The models identified three distinct clusters representing optimal, suboptimal, and abnormal operating conditions. Evaluation metrics indicated well-separated and distinct clusters, providing insights into the operational efficiency and sustainability of gas turbines.

## References
- Chen, C., Luo, J., & Parker, K. (1998). Image segmentation via adaptive K-mean clustering and knowledge-based morphological operations with biomedical applications. IEEE Transactions on Image Processing, 7(12), 1673-1683.
- Gas Turbine CO and NOx Emission Data Set. (2019). UCI Machine Learning Repository.
