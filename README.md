# GNCIPL-Internship-Project-Week-4

Stock Movement Clusters

The goal of this project is to use unsupervised learning to group stocks with similar price movement patterns. By identifying these "clusters," we can gain insights into market trends and make more informed decisions about portfolio diversification.

1. Data Collection & Preparation
Data Source: Historical stock price data was collected from Yahoo Finance using the yfinance library. We selected a list of 50 well-known stocks across various sectors.

Preprocessing:

Data Cleaning: We handled missing values by forward-filling them to ensure a continuous time series for each stock.

Feature Engineering & Normalization: To compare the shape of the price movements rather than their absolute values, we normalized each stock's price series. This was achieved using StandardScaler from scikit-learn, which transforms the data to have a mean of 0 and a standard deviation of 1.

2. Exploratory Data Analysis (EDA)
Summary Statistics: We generated summary statistics to understand the basic properties of the data, such as the mean, standard deviation, and quartiles of the normalized price movements.

Visual Inspection: We plotted the normalized price series for a few sample stocks to visually confirm that their movements were comparable and to get a sense of the volatility in the data.

3. Model Building & Tuning
Dimensionality Reduction: The time series data had a high number of features (one for each trading day). We used PCA (Principal Component Analysis) to reduce this to a smaller number of components that captured 95% of the total variance. This simplifies the data and speeds up the clustering process without losing significant information.

Clustering: We chose K-Means as our clustering algorithm due to its efficiency and interpretability. To determine the optimal number of clusters (k), we used the Elbow Method. We plotted the Within-Cluster Sum of Squares (WCSS) for a range of k values and identified the "elbow" where the rate of decrease significantly slowed.

4. Results & Visualization
Final Clusters: Based on the Elbow Method, we determined the optimal number of clusters was k=4. We trained the K-Means model on the PCA-transformed data to assign each stock to one of these four clusters.

Cluster Visualization: We visualized the clusters by plotting the stocks on a 2D scatter plot using the first two principal components.  Each cluster was color-coded to highlight the groupings.

