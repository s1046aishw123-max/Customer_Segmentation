# 🛍️ Mall Customer Segmentation Using K-Means Clustering

## 📌 Project Overview

This project focuses on segmenting mall customers based on their **annual income and spending score** using the K-Means clustering algorithm. The goal is to identify distinct customer groups and understand their spending behavior to support targeted marketing strategies and customer engagement.

The project uses Python for data analysis, Scikit-learn for clustering, and Matplotlib and Seaborn for data visualization.

## 🎯 Objectives

- Explore and understand customer demographic data.
- Analyze the relationship between annual income and spending score.
- Apply the K-Means clustering algorithm to group customers.
- Use the Elbow Method to help determine the optimal number of clusters.
- Visualize customer segments and cluster centroids.
- Identify opportunities for targeted marketing and customer engagement.

## 📂 Dataset

The project uses the **Mall Customers dataset**, stored as `Mall_Customers.csv`.

The dataset includes customer information such as:

- Customer ID
- Gender
- Age
- Annual Income (k$)
- Spending Score (1–100)

**Features used for clustering:**
- Annual Income (k$)
- Spending Score (1–100)

These two features are used to group customers according to income and spending behavior.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Data analysis and model implementation |
| Pandas | Data loading and manipulation |
| NumPy | Numerical operations |
| Scikit-learn | K-Means clustering |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Jupyter Notebook / Google Colab | Development environment |

## 🔄 Project Workflow

### 1. Data Loading and Exploration

- Loaded the dataset using Pandas.
- Examined sample records using `df.head()`.
- Inspected column types and dataset structure using `df.info()`.
- Checked missing values using `df.isnull().sum()`.

### 2. Feature Selection

Selected Annual Income and Spending Score as the input features for clustering.

```python
X = df.iloc[:, [3, 4]].values
```

These features help distinguish customers with different spending patterns and income levels.

### 3. Finding the Optimal Number of Clusters

Applied the **Elbow Method** to evaluate different cluster counts from 1 to 10.

- Trained K-Means models with different numbers of clusters.
- Calculated Within-Cluster Sum of Squares (WCSS).
- Plotted the WCSS values against the number of clusters.
- Used the elbow plot to guide the selection of five clusters.

### 4. Building the K-Means Model

Configured the K-Means algorithm with five clusters and the `k-means++` initialization method.

```python
from sklearn.cluster import KMeans

kmeans = KMeans(
    n_clusters=5,
    init="k-means++",
    random_state=0
)

y = kmeans.fit_predict(X)
```

The model assigns each customer to a cluster based on the selected features.

### 5. Visualizing Customer Segments

Created a scatter plot to visualize the five customer clusters using different colors.

The visualization includes:
- Annual Income on the X-axis
- Spending Score on the Y-axis
- Color-coded customer clusters
- Cluster centroids representing the centers of the groups

This makes it easier to compare customer groups and identify differences in spending behavior.

## 📊 Results and Customer Segments

The K-Means model is configured to identify five customer segments. These segments can be interpreted based on their relative income and spending scores.

| Customer Segment | General Interpretation | Potential Strategy |
|---|---|---|
| Cluster 1 | Lower income and lower spending | Budget-friendly promotions |
| Cluster 2 | Lower income and higher spending | Affordable offers and loyalty incentives |
| Cluster 3 | Moderate income and moderate spending | Personalized product recommendations |
| Cluster 4 | Higher income and lower spending | Targeted engagement campaigns |
| Cluster 5 | Higher income and higher spending | Premium offers and loyalty programs |

*These descriptions are illustrative interpretations of common customer segments, not verified labels for the notebook's cluster IDs. Actual segment assignments should be interpreted from the generated scatter plot and cluster centroids.*

## 📈 Visualizations

### Elbow Method

The Elbow Method plot helps assess how WCSS changes as the number of clusters increases. The notebook uses five clusters for the final model.

### Customer Segmentation Plot

The scatter plot displays customers according to annual income and spending score, with different colors representing the predicted clusters.


![Elbow Method](images/elbow_method.png)

![Customer Segmentation](images/customer_segments.png)

## 🚀 How to Run the Project

### Prerequisites

- Python 3.x
- Jupyter Notebook or Google Colab
- The `Mall_Customers.csv` dataset

### Step 1: Clone the Repository

```bash
git clone https://github.com/s1046aishw123-max/Customer_Segmentation.git
```

### Step 2: Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Step 3: Add the Dataset

Place `Mall_Customers.csv` in the project directory.

Update the dataset path in the notebook if necessary:

```python
import pandas as pd

df = pd.read_csv("Mall_Customers.csv")
```

### Step 4: Run the Notebook

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open the customer segmentation notebook and execute the cells in order to explore the data, generate the Elbow Method plot, train the clustering model, and visualize the customer segments.

## 📁 Repository Structure

```text
mall-customer-segmentation/
│
├── Mall_Customers.csv
├── customersegment.ipynb
├── images/
│   ├── elbow_method.png
│   └── customer_segments.png
└── README.md
```


## 💡 Business Applications

Customer segmentation can help businesses:

- Develop targeted marketing campaigns.
- Personalize promotions based on spending behavior.
- Identify potential high-value customers.
- Improve customer engagement and retention.
- Allocate marketing resources more effectively.

## 🧠 Skills Demonstrated

- Python programming
- Data exploration and preprocessing
- Feature selection
- Unsupervised machine learning
- K-Means clustering
- Elbow Method
- Data visualization
- Customer segmentation and business interpretation

*This project demonstrates the application of unsupervised machine learning to customer segmentation, helping transform customer data into insights that can inform marketing and engagement strategies.*
