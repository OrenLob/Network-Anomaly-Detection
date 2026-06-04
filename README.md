# Network-Anomaly-Detection
Unsupervised machine learning project detecting network cyber-attacks using PCA, K-Means, Isolation Forest, and LOF.
# Network Anomaly Detection & Unsupervised Learning 🛡️

## Project Overview
This project applies advanced unsupervised machine learning techniques to real-world network traffic data (CICIDS2017) to detect cyber-attacks without prior labeling. The goal is to explore data geometry, uncover hidden structures, and critically evaluate the performance of various clustering and anomaly detection algorithms.

## Methodology 🛠️
The pipeline includes the following steps:
1. **Exploratory Data Analysis (EDA):** Handling heavy-tailed distributions and multicollinearity in a 51-dimensional feature space.
2. **Dimensionality Reduction:** Using **PCA** (retaining >90% variance with 15 components) and **t-SNE** for local structure visualization.
3. **Clustering Analysis:** Comparing centroid-based (**K-Means**), density-based (**DBSCAN**), and **Hierarchical Clustering**. We also performed feature-space clustering to identify redundant network metrics.
4. **Anomaly Detection:** Evaluating classical statistical methods against machine learning approaches:
   * **Z-Score**
   * **Isolation Forest**
   * **Local Outlier Factor (LOF)**

## Key Insights 💡
* **The Context of Anomalies:** Classical methods like Z-Score fail catastrophically on skewed network data because they lack local environmental context, resulting in massive false positives. In contrast, LOF successfully finds true local anomalies by analyzing neighborhood density.
* **Global vs. Local Outliers:** Isolation Forest is highly effective at finding extreme, global attacks on the periphery of the data, while LOF excels at finding stealthy attacks hiding near dense clusters of normal traffic.
* **Curse of Dimensionality:** Distance-based metrics degrade in 51 dimensions. PCA successfully mitigated this, improving computational efficiency and visualization quality.


## Dataset 📊
Due to GitHub's file size limits, the `cicids2017_cleaned.csv` dataset (~700MB) is not included in this repository. 

You can download the exact cleaned dataset used in this project directly from Kaggle:
👉 [CICIDS2017 Cleaned and Preprocessed Dataset](https://www.kaggle.com/datasets/ericanacletoribeiro/cicids2017-cleaned-and-preprocessed)

**Note to run the code:** Simply download the CSV file from the link above and place it in the root directory of this project before running the scripts.
