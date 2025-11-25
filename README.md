# Project Overview<br>
Stratton & Fils Private Banking Group has undertaken this analytics initiative to better understand the behavioral and demographic diversity within the existing customer base. Using unsupervised machine learning techniques—specifically PCA for dimensionality reduction and K-Means for clustering—we segmented customers across geographical, demographic, behavioral, and psychographic attributes. The objective is to identify which customer groups are most likely to adopt Stratton’s newly developed digital banking platform, created in partnership with our fintech innovation partner,with these segmentation insights guiding targeted digital onboarding initiatives, more precise marketing campaigns, and a differentiated engagement plan tailored to each customer segment’s readiness for digital financial services.

# Methods and Workflow
⚠️ Note: The analysis is based on the real banking dataset modeled after authentic banking attributes to illustrate customer segmentation for digital adoption, which cannot be shared publicly due to confidentiality reasons. All techniques and insights mirror real-world banking analytics workflows.

## 1. Data Preparation
The dataset consists of 10750 records with 28 attributes, categorized into demographic, geographical, behavioral, and psychographic groups.

<p align="center">
  <img src="images/Supplementary variables.png" width="500">
  <br>
  <em>Supplementary variables: Explain cluster differences in age, income, location</em>
</p>

<p align="center">
  <img src="images/Active variables.png" width="500">
  <br>
  <em>Active variables: Capture customers' behavioral differences</em>
</p>


## 2. Exploratory KMeans
* Chose the pptimal cluster number 7 from elbow method and silhouette score plot.
* Raw KMeans with cluster number 7 produces a silhouette score of ~0.60.

<p align="center">
  <img src="images/raw_kmeans.png" width="500">
  <br>
  <em>The lower the inertia, the better.<br>
      The higher the silhouette score, the better.</em>
</p>
  

## 3. Refined KMeans on PCA-transformed attributes
### Summary 
- Extracted 4 principal components from 17 active variables (behavioral + psychographic) to reduce dimensionality and uncover latent drivers.
- Applied KMeans on both raw data and PCA-transformed data to assess segmentation stability.
- Cluster stability validated by comparing label distributions and overlaps between raw vs. PCA-based cluster assignments.
- Final model uses PCA-derived cluster labels, supported by a significantly improved silhouette score (~0.81) after mitigating multicollinearity present in the raw dataset.

### PCA Loading Matrix

<p align="center">
  <img src="images/PCA loadings.png" width="800">
  <br>
  <em>Loadings for PC1 to PC4 showing dominant behavioral and psychographic drivers across components.</em>
</p>

### Interpretation of Principal Components

#### **PC1 — Digital Engagement & Tech-Savviness & High Risk Preference**  
These are customers active in online activities and use of mobile/digital banking, with high risk tolerance indicated by crypto/NFT involvement.

#### **PC2 — Proactive Bank Interaction & Market Investments & Consumer Spending**  
These are customers exhibiting high stock/NASDAQ investment activity (mid–high risk tolerance) combined with strong consumer spending patterns (credit card and grocery spending).

#### **PC3 — Traditional Banking Preference & Moderate Spending**  
These are customers with high ATM and branch usage and low digital adoption, indicating a preference for in-person banking.

#### **PC4 — Mid-Corp Fund Investment Focus & Low Borrowing & Light Banking Interaction**  
These are customers with strong preference for mid-corporate investment products (USAXSFund), low interaction activity (few branch visits, light app usage) and low overall spending and borrowing patterns

### 2D PCA scatter plot

<p align="center">
  <img src="images/2D PCA Scatter plot with KMeans clusters .png" width="500">
  <br>
  <em>PCA1 as x-axis and PCA2 as y-axis</em>
</p>

### Interpretation
- Clusters 2 and 6 demonstrate strong digital affinity, tech openness and high risk tolerance
- Cluster 0 exhibits huge spending and investment potential along with high bank engagement
- Cluster 4 
 

# Cluster interpretation
## Summary 
- Profile each cluster using means of attribute.
- Visualize clusters based on top 10 attirbutes in terms of weighted PCA loading.
- Used supplementary variables (geographical + demographic) to add socio-demographic context.




