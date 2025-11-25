🔍 Project Overview<br>
Stratton & Fils Private Banking Group has undertaken this analytics initiative to better understand the behavioral and demographic diversity within the existing customer base. Using unsupervised machine learning techniques—specifically PCA for dimensionality reduction and K-Means for clustering—we segmented customers across geographical, demographic, behavioral, and psychographic attributes. The objective is to identify which customer groups are most likely to adopt Stratton’s newly developed digital banking platform, created in partnership with our fintech innovation partner,with these segmentation insights guiding targeted digital onboarding initiatives, more precise marketing campaigns, and a differentiated engagement plan tailored to each customer segment’s readiness for digital financial services.

🧮 Methods and Workflow<br>
⚠️ Note: The analysis is based on the real banking dataset modeled after authentic banking attributes to illustrate customer segmentation for digital adoption, which cannot be shared publicly due to confidentiality reasons. All techniques and insights mirror real-world banking analytics workflows.

1. Data Preparation<br>
The dataset consists of 10750 records with 28 attributes, categorized into demographic, geographical, behavioral, and psychographic groups.

<insert graph> here

2. Exploratory KMeans
* Optimal cluster number 7 chosen from elbow method and silhouette score plot.
* Raw KMeans with cluster number 7 produces a silhouette score of ~0.60. 

3. Refined KMeans on PCA-transformed attributes
* 4 principle components extracted from 17 active variables (behavioral + psychographic attributes) to uncover latent features
🧭 PC1 — Digital Engagement + Tech-Savviness + High Risk Preference
Themes
Heavy digital banking usage/High online activity/High-risk crypto/NFT investments/Tech-forward, innovation-adopting customers

Interpretation
PC1 loads strongly on InternetTrafficVolume, TimeOnlineBanking, AppLogins, SocialMediaInter, and especially Bitcoins and NFTs.
This combination represents customers who:
Are heavy online and mobile users
Adopt new financial technologies early (crypto/NFTs)
Show higher risk tolerance and digital financial literacy

🧭 PC2 — Proactive Bank Interaction + Market Investments + Consumer Spending

Themes:

Active relationship with the bank

Engaged in stock/market investments

Higher discretionary spending

Interpretation:
PC2 has high positive loadings on NASDAQInvest, StockVolume, and CreditCardSpending, as well as GrocerySpending.
This indicates customers who:

Invest actively in market assets (mid–high risk tolerance)

Spend consistently across categories

Maintain regular interactions with the bank

👉 PC2 represents a “Financially Active, Higher-Spending Investors” dimension.

#### 🧭 PC3 — Traditional Banking Users + Moderate Spending + Limited Digital Touchpoints

Themes:

Reliance on branch/ATM

Lower digital adoption

Moderate investment and spending behavior

Interpretation:
PC3 shows high loadings on ATMVisits, ServiceFees, and BranchVisits, with noticeable negative relationships for digital variables.
These customers:

Prefer traditional, in-person banking channels

Use less online and mobile banking

Maintain moderate account activity and investment amounts

👉 PC3 captures a “Traditional Banking Preference / Low Digital Adoption” behavioral axis.

#### 🧭 PC4 — Mid-Corp Fund Investment Focus + Low Borrowing + Light Banking Interaction

Themes:

Strong preference for mid-corporate investment products

Low engagement across other services

Light user of borrowing/credit-related activities

Interpretation:
PC4 loads strongly on USAXSFundInvest (bank-owned medium-size corporate funds), with relatively low contributions from lending or digital engagement variables.
These customers:

Prefer stable, mid-corporate investment instruments

Show low interaction intensity (few branch visits, light app usage)

Have low overall spending and borrowing patterns

👉 PC4 reflects a “Mid-Corporate Fund Investors / Low-Interaction Customers” profile.


* Cluster stability tested by examining the distribution of cluster labels and the overlaps in labels derived from raw vs PCA-transformed data.
* Settled with the PCA cluster label since the silhouette score significantly improved to ~0.81 as the issue of multicollinearity inherent in the raw data is removed. 

4. Cluster interpretation
* Profile each cluster using means of attribute.
* Visualize clusters based on top 10 attirbutes in terms of weighted PCA loading.
* 11 Supplementary variables (geographical + demographic) used to add socio-demographic context.




