# Task 8: Clustering with K-Means (Mall Customer Segmentation)

### Objective
The primary goal was to perform **Unsupervised Learning** using the K-Means algorithm to discover hidden customer segments based on spending habits and income, focusing on the mandatory steps of **Normalization** and finding the **Optimal K**.

### Dataset & Preprocessing
* **Dataset:** Mall Customer Segmentation Dataset.
* **Encoding:** The categorical feature 'Gender' was converted to numerical using **One-Hot Encoding** (creating the binary column 'Gender\_Male').
* **Feature Selection:** Four features were used for clustering: Annual Income, Spending Score, Age, and the encoded Gender.
* **Feature Scaling (Mandatory):** All predictor features were scaled using **`StandardScaler`**. K-Means is a **distance-based algorithm**, and scaling is essential to ensure all features contribute equally to the distance calculation.

---

### Methodology: Finding the Optimal K

#### 1. Elbow Method
An iterative approach was implemented to find the optimal number of clusters ($K$) by plotting the **Inertia** (Within-Cluster Sum of Squares, or WCSS) against the $K$ values.

* **Observation:** The visual inflection point (or "elbow") in the inertia plot was identified as $K=2$. 

[Image of the Elbow Method graph]


#### 2. Final Clustering Results

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Optimal K Selected** | **2** | The $K$ value chosen based on the Elbow Method's suggestion. |
| **Silhouette Score** | **0.2762** | **Weak Clustering.** This score (between 0.0 and 1.0) is low, indicating that the clusters are **not highly separated** and many data points are close to the decision boundary. |

---

### Analysis and Conceptual Insights

#### 1. Cluster Quality
* The low **Silhouette Score (0.2762)** suggests that $K=2$ is a weak separation. This is likely because clustering based on the four selected features (Income, Spending, Age, Gender) does not capture the true, more nuanced customer segments. This result indicates that **Feature Engineering** or using a different clustering algorithm (like DBSCAN) may be needed for better separation.

#### 2. K-Means Mechanics
* **K-Means Process:** The model successfully partitioned the data by iteratively assigning points to the nearest **centroid** (based on Euclidean distance) and recalculating the centroid's mean position until convergence. 

[Image of K-Means Clustering steps]

* **Unsupervised Learning:** This task successfully demonstrated unsupervised learning—discovering groups in unlabeled data—which is vital for business intelligence like customer segmentation.
