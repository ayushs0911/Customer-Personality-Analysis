## Problem Statemet 
Customer Personality Analysis is a detailed analysis of a company’s ideal customers. It helps a business to better understand its customers and makes it easier for them to modify products according to the specific needs, behaviors and concerns of different types of customers.

Customer personality analysis helps a business to modify its product based on its target customers from different types of customer segments. For example, instead of spending money to market a new product to every customer in the company’s database, a company can analyze which customer segment is most likely to buy the product and then market the product only on that particular segment.

```
!kaggle datasets download -d imakash3011/customer-personality-analysis
```

## Data Handling 
- Dropped Missing values 
- Converted `Dt_Customer` from `object` to `datetime` type 
- Created new attrbute `Customer_For` : Showing the days, the customer started shopping from store 

## Feature Engineering 
- `Age` : extracted it from `Year_Birth` column 
- `Spent`: total amount spent by customer by adding total money spend on all products 
- `Marital_Status` : reduced the categories of `Living_with` to `Partner` and `Single`
- `Children` : Total children in household 
- `Fanily Size`
- `Education` : Segmented Education levels into 3 levels : `UG`, `PG`, `Graduate`

## Outliers 
`Income` and `Age` has outliers. Removed them by setting upperlimit of both the attributes. 
```
Upper Limit: mean + (3 * standard deviation) = 0 + (3 * 1) = 3
Lower Limit: mean - (3 * standard deviation) = 0 - (3 * 1) = -3
```

## Data Preprocessing 
- `LabelEncoder()` 
- `StandardScaler()`
- Dimensionality Reduction using `PCA`


## No. of clusters using Elbow method
<img width="400" alt="Screenshot 2023-05-18 at 1 47 50 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/073af7a3-946a-492a-978d-6798e6ef10b3"><br>

## Algorithm
```
AC = AgglomerativeClustering(n_clusters = 4)

ypred = AC.fit_predict(PCA_ds)
PCA_ds["Clusters"] = ypred

#adding the clusters fearure to the orignal dataframe
data["Clusters"] = ypred
```

## Plot of Clusters
<img width="400" alt="Screenshot 2023-05-18 at 1 49 00 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/bd44bd71-d0e2-4f63-8000-a932ae78041e">

## Clusters based on Various Attributes 
<img width="240" alt="Screenshot 2023-05-18 at 1 51 00 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/f131e363-f258-4dfe-a163-993801cf8e95">
<img width="240" alt="Screenshot 2023-05-18 at 1 51 16 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/a975e9c1-9a45-4b68-bfa4-6b0e26f68b79">
<img width="240" alt="Screenshot 2023-05-18 at 1 51 31 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/1c182600-928b-49f4-9305-879e5b7ee9d1">
<img width="240" alt="Screenshot 2023-05-18 at 1 51 44 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/9be8a198-eebb-4e4d-bb71-25e99fa7371c">
<img width="240" alt="Screenshot 2023-05-18 at 1 51 58 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/93d29d9b-1852-42fd-9bee-176ba0f2f2c9">
<img width="240" alt="Screenshot 2023-05-18 at 1 52 12 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/274a6813-f7b7-4b3f-959b-ed9c85d34069">
<img width="240" alt="Screenshot 2023-05-18 at 1 52 25 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/92d37da4-91fe-4da9-9a69-7d4aa87d64e3">
<img width="240" alt="Screenshot 2023-05-18 at 1 52 36 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/dc5fc46c-f08c-492f-aee8-47aa5f73ff38">

## Distrbution of clusters on Campaigns and Deals 
<img width="400" alt="Screenshot 2023-05-18 at 1 54 18 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/c635176e-a4df-4f66-a070-36ec8e2ea4e4">
<img width="400" alt="Screenshot 2023-05-18 at 1 54 39 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/a5eb0662-cc20-438a-8284-36725b67208e">

## Purchasing Styles 
<img width="240" alt="Screenshot 2023-05-18 at 1 55 12 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/e65fad83-eece-4f98-b3e3-f6f466c32374">
<img width="240" alt="Screenshot 2023-05-18 at 1 55 25 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/5ee37ac2-ac83-4ff4-893a-bc7cb3b4b80d">
<img width="240" alt="Screenshot 2023-05-18 at 1 55 38 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/38a19362-f22d-4d68-b7d0-5809a38123de">
<img width="240" alt="Screenshot 2023-05-18 at 1 55 52 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/9db25716-25c5-4689-8e74-2458503fc4ed">

## Profiling
<img width="240" alt="Screenshot 2023-05-18 at 1 56 27 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/e2d55012-6f67-4de4-8655-be4f6e5e92c4">
<img width="240" alt="Screenshot 2023-05-18 at 1 56 39 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/38f0fdf7-dea7-4a46-b9bd-4a59f15b27cc">
<img width="240" alt="Screenshot 2023-05-18 at 1 56 52 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/cf322d73-f068-4bc4-9143-46a377e801aa">
<img width="240" alt="Screenshot 2023-05-18 at 1 57 05 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/4808452d-c891-43b4-a939-dd51259b84e4">
<img width="240" alt="Screenshot 2023-05-18 at 1 57 18 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/869fd383-39a6-4018-9a78-fef4cc9bda06">
<img width="240" alt="Screenshot 2023-05-18 at 1 57 31 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/c39ac38f-4590-42ff-9a69-8394929d20eb">
<img width="240" alt="Screenshot 2023-05-18 at 1 57 46 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/bcddf61d-355d-4d05-a2bc-9cbe5cfc3125">
<img width="240" alt="Screenshot 2023-05-18 at 1 57 59 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/f24bbb10-393c-4f5c-bfbc-1f1a472de443">
<img width="240" alt="Screenshot 2023-05-18 at 1 58 12 PM" src="https://github.com/ayushs0911/Customer-Personality-Analysis/assets/122048067/6b661f2f-d9b1-4fc5-8894-38b62ccbcca8">

# Conclusion 
### Cluster Number : 0
- they are definitely a parent
- at the max have 4 members in the family and atleast 2
- single parents are subset of this group
- most have teenager at home
- relatively older.
### Cluster Number : 1
- not parents
- at max only 2 members in family
- Slight majority of couples over single people
- span all ages
- a high income group
### Cluster Number : 2
- Majority of these are parents
- at max are 3 members in family
- majority have one kid
- relatively younger
### Cluster Numver : 3
- Definitely a parent
- upto 5 members in family and least 2
- majority of them have teenager at home
- relatively older
- a lower income group


