# Project Overview
Stratton & Fils Private Banking Group has undertaken this analytics initiative to better understand the behavioral and demographic diversity within the existing customer base. Using unsupervised machine learning techniques, specifically PCA for dimensionality reduction and K-Means for clustering, our objective is to identify which customer groups are most likely to adopt Stratton’s newly developed digital banking platform, created in partnership with our fintech innovation partner. <br>
We have successfully identified **3750 out of 10750** customers as our target group for the first wave of digital banking rollout, who display strong digital affinity, medium to high risk tolerance and huge spending potential.

# Methods and Workflow
⚠️ Note: The analysis is based on the real banking dataset modeled after authentic banking attributes to illustrate customer segmentation for digital adoption, which cannot be shared publicly due to confidentiality reasons. However, all techniques and insights mirror real-world banking analytics workflows.

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
These are customers with high ATM and branch usage and low digital adoption, indicating a preference for traditional in-person banking.

#### **PC4 — Mid-Corp Fund Investment Focus & Low Borrowing & Light Banking Interaction**  
These are customers with strong preference for mid-corporate investment products (USAXSFund), low interaction activity (few branch visits, light app usage) and low overall spending and borrowing patterns

### 2D PCA scatter plot: Segmentation Across Dominant Behavioral Dimensions

<p align="center">
  <img src="images/2D PCA Scatter plot with KMeans clusters .png" width="500">
  <br>
  <em>The horizontal axis (PC1) captures digital engagement, tech-savviness, and risk tolerance.<br>
      The vertical axis (PC2) reflects proactive bank interaction, market investments, and consumer spending.</em>
</p>

### Key observations
#### Clusters **2**, **6**, and **0** should be prioritized for the **first wave of digital banking rollout and marketing campaigns**
- Clusters 2 and 6 sit at the far right of PC1, indicating strong digital affinity, tech openness and high risk tolerance.
- Cluster 0 occupies the upper-left region with the highest PC2 scores, exhibiting huge spending and investment potential and strong engagement with Stratton's services
#### Other clusters represent secondary targets or segments requiring different onboarding approaches
- Clusters positioned between these extremes show moderate digital readiness and traditional banking reliance (clusters 4 and 5) or light engagement with the bank (clusters 1 and 3).


# Cluster interpretation and Recommendations
## Target Segments
- Primary Targets: Clusters 2, 6, 0 (high digital readiness OR high value).
- Secondary Targets: mid-range clusters showing partial openness to digital tools.
- Low Readiness Segments: traditional clusters requiring guided onboarding & education.
- Investment-Focused Segments: tailor features around portfolio tracking & advisory services.

### Cluster profiling (standardized) based on top 10 behavioral/psychographic attributes
[🔗 Interactive Dashboard – Active Variables](https://krishuang-1116.github.io/DigitalBankingSegmentationProject/cluster_profiles_active_vars.html) 

### Cluster profiling (standardized) based on geographical/demographic attributes 
[🔗 Interactive Dashboard – Supplementary Variables](https://krishuang-1116.github.io/DigitalBankingSegmentationProject/cluster_profiles_supplementary_vars.html))


