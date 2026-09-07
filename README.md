# App Market Segmentation: Google Play vs. Apple App Store

**Live Tableau Dashboard:** [Insert Tableau Public Link Here]

This project analyzes and segments the mobile application market by integrating datasets from the Google Play Store and Apple App Store. Using machine learning (K-Means Clustering), the project categorizes apps based on user engagement, pricing, and ratings to uncover market trends and developer opportunities.

## 🚀 Project Overview

The mobile app market is highly saturated. To understand what drives app success across different ecosystems, this project processes raw store data, unifies the schemas, and applies clustering algorithms to group applications into distinct market segments.

**Key Outcomes:**
*   Unified disparate datasets from two major app stores into a single, clean schema.
*   Engineered and standardized features (e.g., converting mixed string sizes to uniform Megabytes, cleaning currency symbols).
*   Segmented the market into 5 distinct clusters using K-Means to identify app profiles (e.g., highly-reviewed free apps vs. premium niche apps).
*   Visualized market distribution and segments using Tableau.

## 🛠 Tech Stack

*   **Language:** Python
*   **Data Manipulation:** Pandas, NumPy
*   **Machine Learning:** Scikit-Learn (K-Means, StandardScaler)
*   **Visualization:** Tableau
*   **Environment:** Jupyter Notebook

## 📁 Repository Structure

```text
├── data/
│   ├── raw/                 # Original Kaggle/Store CSV files
│   └── processed/           # combined_apps_with_clusters.csv
├── notebooks/
│   └── main.ipynb           # Data cleaning, EDA, and Clustering pipeline
├── dashboards/
│   └── visualization.twb            # Tableau workbook
├── visualizations/
│   ├── Market Distribution.png
│   └── Market Segmen.png
└── README.md

```

## 🧠 Methodology

1. **Data Cleaning:**
* Filtered out invalid Google Play Store ratings (capped at 5.0 max).
* Stripped non-numeric characters (`+`, `,`, `$`) from `Installs` and `Price` columns to cast them as numeric.
* Wrote a custom parsing function to standardize the `Size` column, converting 'M' (Megabytes) and 'k' (Kilobytes) into a uniform `Size_MB` float.
* Standardized Apple App Store bytes into Megabytes.


2. **Data Integration:**
* Aligned columns across both datasets (App, Platform, Category, Rating, Reviews, Size_MB, Price) and concatenated them into a master DataFrame.


3. **Feature Scaling & Clustering:**
* Extracted key performance indicators: `Rating`, `Reviews`, and `Price`.
* Applied `StandardScaler` to normalize the variance across features with vastly different ranges.
* Trained a `KMeans` model (`n_clusters=5`) to assign a `Cluster_ID` to every application.



## 📈 Visualizations

The clustering results and market distributions were exported to Tableau for interactive analysis.

* **Market Segmen.png:** Illustrates the distribution of the 5 clusters across price points and review volumes.
* **Market Distribution.png:** Compares the density of app categories between iOS and Android.

## ⚙️ How to Run

1. Clone this repository.
2. Install the required libraries:
```bash
pip install pandas numpy scikit-learn jupyter

```


3. Open `notebooks/main.ipynb` to execute the data pipeline.
4. The script will output `combined_apps_with_clusters.csv` to your directory.

```

```
