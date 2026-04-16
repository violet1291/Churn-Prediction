# Churn-Prediction
Understand and predict customer churn for a subscription-based company.

**Executive Summary**
A quantitative and exploratory analysis was conducted to understand and predict customer churn, using Python (scikit-learn, pandas, numpy, matplotlib) and Excel (pivot tables). Through the K-means clustering technique, three key groups were identified—new, active, and at-risk customers—and visualized with the help of Principal Component Analysis (PCA). Subsequently, a logistic regression model was applied to measure the effect of each variable on churn probability. The results indicated that subscription tenure and recent severe support cases increase churn risk, while a high satisfaction index, support priority, platform usage, and perceived customer benefit reduce it. These findings provide a solid foundation for strategic decisions aimed at maximizing customer retention.

**Data Preparation and Cleaning**

First, a data cleansing process was carried out. Seven records with values outside the expected range (0 and 1) in the Churn variable were identified. Since there was no justification for a third state (state 4) and they represented less than 0.35% of the total, these records were removed to ensure an appropriate analysis. Additionally, three rows with missing values were eliminated to guarantee the proper functioning of the applied techniques.

Subsequently, numerical variables were standardized to homogenize their scales and prevent those with larger values from disproportionately influencing the clustering process.

**Exploratory Data Analysis**

Before applying the algorithms, an Exploratory Data Analysis (EDA) was conducted to identify patterns, relationships, and potential multicollinearity among variables. The analysis revealed that the variables with the highest positive correlation were Change in Customer Benefit and Change in Service Usage.

**Customer Segmentation (Clustering)**

For customer classification, the K-Means method was selected, an unsupervised learning algorithm suitable for unlabeled data. This method enables the identification of natural groups within the dataset based on similarities among observations.

A total of three clusters (k = 3) was established, determined using the Elbow Method, which identifies the optimal number of clusters.

The process followed the methodological stages of the algorithm:

- Random selection of the three initial centroids.
- Calculation of the Euclidean distance between each data point and the centroids.
- Assignment of each observation to the nearest centroid.
- Recalculation of the centroids for each cluster.
- Iteration of the previous steps until convergence and cluster stability were achieved.

The following groups were identified, with the characteristics described below.
_Table 1. Number of Customers Who Remain Subscribed or Churn_
<img width="849" height="100" alt="image" src="https://github.com/user-attachments/assets/0b0df236-06ce-44d7-a7b0-9b46521c1c00" />

Source: Author’s own elaboration.

_Table 2. Customer Groups by Average Characteristics_
<img width="753" height="257" alt="image" src="https://github.com/user-attachments/assets/195214ea-2df6-4024-9836-0ddaddbac1c4" />

Source: Author’s own elaboration.

**Dimensionality Reduction and Visualization**

To visualize the clusters within a single plane and evaluate their separation, Principal Component Analysis (PCA) was applied. This technique projected the original variables into a two-dimensional space while preserving the maximum possible variance of the data. As a result, a clear graphical representation of the achieved segmentation was obtained, validating the coherence between the groups and the variables that define them (see Figure 1).

**Churn Probability Analysis (Logistic Regression)**

Finally, to understand the effect of each variable on customer churn probability, a binary logistic regression model was applied. This model allowed for the estimation of coefficients (β) and odds ratios (e^β) for each predictor, identifying which factors increase or decrease the likelihood of churn (Table 3).

_Table 3. Logistic Regression Coefficients and Odds Ratios_
<img width="752" height="295" alt="image" src="https://github.com/user-attachments/assets/3a61f5b6-1c00-4b2a-b797-aea426511d38" />

Source: Author’s own elaboration.

**Figure 1. Customer Type Classification**
<img width="789" height="604" alt="image" src="https://github.com/user-attachments/assets/b1bed89c-b304-4205-808b-8a5768be1927" />

Source: Author’s own elaboration.

The results show a good overall fit, indicating that variables related to satisfaction, service usage, and perceived benefit decrease the probability of churn, while those associated with technical support and its variability tend to increase it. The model achieves high accuracy (95%); however, it fails to correctly identify class 1, reflecting a significant class imbalance and a bias toward the majority class (Churn = 0). This is consistent with the dataset composition, where approximately 4.37% of customers are in the churn state. To improve probability estimation, balancing the dataset between positive and negative churn cases is recommended.

**Table 4. Logistic Regression Classification Report**

<img width="858" height="156" alt="image" src="https://github.com/user-attachments/assets/7e277f50-6926-47c4-92db-2f99380fcf1b" />

Source: Author’s own elaboration.

**Methodological Synthesis**

In summary, the methodology combined unsupervised data mining techniques (clustering) with supervised predictive modeling (logistic regression). This approach enabled both the identification of homogeneous customer groups and the determination of factors influencing their retention or churn. The mixed-method strategy provided a comprehensive understanding of customer behavior and a solid foundation for designing targeted customer loyalty strategies for each segment. Balancing the dataset with respect to the Churn variable is recommended to achieve more accurate predictive model adjustments.

