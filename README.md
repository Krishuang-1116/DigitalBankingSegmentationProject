🔍 Project Overview<br>
This project applies unsupervised machine learning techniques (PCA and K-Means) to cluster the existing customer base of Stratton & Fils Private Banking Group (referred to as Stratton) based on geographical, demographic, behavioral, and psychographic attributes. The goal is to identify Stratton's customer segments most likely to adopt a new digital banking solution that Stratton developed in partnership with a fintech startup, with these segmentation insights guiding future marketing strategies and digital onboarding efforts.

🧮 Methods and Workflow<br>
⚠️ Note: The analysis is based on the real banking dataset modeled after authentic banking attributes to illustrate customer segmentation for digital adoption, which cannot be shared publicly due to confidentiality reasons. All techniques and insights mirror real-world banking analytics workflows.

1. Data Preparation<br>
The dataset consists of 10750 records with 28 attributes. 
* Cleaning, scaling, and standardizing numeric features.
* Categorizing 28 attributes into demographic, geographical, behavioral, and psychographic groups.

2. Exploratory KMeans
* Optimal cluster number 7 chosen from elbow method and silhouette score plot.
* Raw KMeans with cluster number 7 produces a silhouette score of ~0.60. 

3. Refined KMeans on PCA-transformed attributes
* 4 principle components extracted from 17 active variables (behavioral + psychographic attributes) to uncover latent features
* Cluster stability tested by examining the distribution of cluster labels and the overlaps in labels derived from raw vs PCA-transformed data.
* Settled with the PCA cluster label since the silhouette score significantly improved to ~0.81 as the issue of multicollinearity inherent in the raw data is removed. 

4. Cluster interpretation
* Profile each cluster using means of attribute.
* Visualize clusters based on top 10 attirbutes in terms of weighted PCA loading.
* 11 Supplementary variables (geographical + demographic) used to add socio-demographic context.




