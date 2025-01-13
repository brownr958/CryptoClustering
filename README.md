# CryptoClustering

This repository contains the solution to the CryptoClustering assignment. The project applies the K-means clustering algorithm and Principal Component Analysis (PCA) to classify cryptocurrencies based on their price fluctuations across various timeframes.

---

## **Table of Contents**
- [Overview](#overview)
- [Files](#files)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Steps and Methodology](#steps-and-methodology)
- [Key Insights](#key-insights)

---s

## **Overview**
The goal of this project is to analyze price changes in cryptocurrencies over different timeframes (24 hours, 7 days, 30 days, 60 days, 200 days, and 1 year) to identify patterns and cluster them using the K-means algorithm. The analysis also includes dimensionality reduction using PCA to optimize clustering performance and improve interpretability.

---

## **Files**
- `Crypto_Clustering.ipynb`: Jupyter Notebook containing the full implementation of the assignment.
- `crypto_market_data.csv`: Dataset used for clustering.
- `README.md`: Overview and documentation of the project.

---

## **Technologies Used**
- Python 3.8+
- Jupyter Notebook
- Libraries: 
  - `pandas`
  - `matplotlib`
  - `hvplot`
  - `scikit-learn`

---

## **Installation**

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/CryptoClustering.git
   ```

2. Navigate to the project directory:
   ```bash
   cd CryptoClustering
   ```

3. Create a virtual environment (optional but recommended):
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows, use `env\Scripts\activate`
   ```

4. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

5. Launch the Jupyter Notebook:
   ```bash
   jupyter notebook Crypto_Clustering.ipynb
   ```

---

## **Steps and Methodology**

### **1. Data Preparation**
- Load the dataset (`crypto_market_data.csv`) into a Pandas DataFrame.
- Normalize the data using `StandardScaler` to ensure all features are on a similar scale.

### **2. Finding the Optimal k**
- Use the elbow method to find the best value for `k` by computing the inertia for `k` values ranging from 1 to 11.
- Visualize the results in an elbow curve and determine the optimal `k`.

### **3. K-means Clustering with Original Data**
- Cluster the cryptocurrencies using the optimal `k` value.
- Add cluster assignments to the DataFrame and visualize clusters using a scatter plot of `price_change_percentage_24h` vs. `price_change_percentage_7d`.

### **4. Dimensionality Reduction with PCA**
- Apply PCA to reduce the dataset to three principal components while retaining as much information as possible.
- Calculate the explained variance to evaluate the effectiveness of dimensionality reduction.

### **5. Clustering with PCA Data**
- Perform K-means clustering on the PCA-transformed data.
- Visualize the clusters in a scatter plot using the first two principal components (`PC1` and `PC2`).

### **6. Feature Importance Analysis**
- Calculate the weights of each feature for each principal component.
- Identify features with the strongest positive and negative influence on each component.

---

## **Key Insights**
1. **Optimal k Value**: The elbow method determines the best value for `k` for clustering both the original and PCA data.
2. **Dimensionality Reduction**: PCA reduces the dataset to three components while retaining most of the variance, improving clustering performance.
3. **Feature Contributions**: Feature weights highlight the most influential variables for each principal component, aiding interpretability.
4. **Cluster Visualization**: Scatter plots provide clear visualizations of the cryptocurrency clusters based on both original and PCA data.

---

## **Contributing**
Feel free to fork this repository and create pull requests for improvements or additional features.

---

## **License**
This project is licensed under the MIT License.