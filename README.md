# Instacart-Customer-Behavior-Analysis

## Project Overview

#### Purpose
Reason I chose this dataset stemmed from firstly my constant interest in retail data and secondly my curiosity to find out distinctive shopping behaviors by different customer segments.

#### Data Source & Preprocessing
- source: https://www.kaggle.com/competitions/instacart-market-basket-analysis  
- Data: originally 15 columns, 3,500K rows, but I only used 300K rows due to the Tableau Public's processing capacity 
- Key Columns: order_id, user_id, aisle, number of order, number of product within an order, order_day_of_week, reordered..

#### Business Question
- How to segment the customers who made purchases?
- What's the shopping behavior that each segment shows differently
- What products are most frequently basketed? - market basket analysis
 
## Methodology
#### Customer Segmentation
- I applied PCA with 6 components to the crosstab counting purchase number of each aisle by user. I chose aisle among product and deparment due to its middle granularity (134 columns)
- Then I selected 2 components (PCA1 and PCA4) which seemed to compose the most distinctiv clusters.
- Using K-means Clustering with 4 clusters, I was able to divide customer segments by their purchase items.

#### Market Basket Analysis
- I generated aisle pairs for each order, merged the cluster group data, and calculated the frequency for each aisle pair and customer group combination

#### Visualization
- Lastly, I created a dashboard that contains a comprehensive shopping behavior analysis of customers with a filter of clutering segment.


## Tableau Dashboard

![image](https://github.com/Hayoung-Zoe-Kim/Instacart_Customer_Behavior_Analysis/blob/main/dashboard1.png)
![image](https://github.com/Hayoung-Zoe-Kim/Instacart_Customer_Behavior_Analysis/blob/main/dashboard2.png)

https://public.tableau.com/app/profile/hayoung7844/viz/CustomerShoppingBehaviorbySegments/Story1?publish=yes

## Analysis & Insights
| Cluster                          | Avg Basket Size | Avg Number of Orders | Avg Number of Distinct Products Purchased | Avg Reorder Rate | Avg Purchase Interval |
|----------------------------------|-----------------|----------------------|-------------------------------------------|------------------|-----------------------|
| 0 - Health-Conscious Shoppers    | 15.89           | 1.319                | 17.85                                    | 65.34%           | 10.31                 |
| 1 - Balanced Basket Shoppers     | 8.29            | 1.097                | 8.685                                    | 57.41%           | 11.36                 |
| 2 - Niche Market - Baby Care     | 21.97           | 1.358                | 25.10                                    | 61.76%           | 9.654                 |
| 3 - Veggie Lovers                | 14.17           | 1.197                | 15.44                                    | 53.60%           | 11.22                 |


### Cluster & Market Basket Analysis Summary

**Cluster 0: The Health-Conscious Shoppers**
- This group, making up 17.35% of total purchasers, favors fresh produce and dairy, with a pronounced preference for fruits and yogurt.
- They present the highest reorder rate at 65.34%, often repurchasing milk and snack bars, indicative of a consistent shopping routine, typically every 10.31 days.
- **Top Pairings:** Strong affinity for fruit, with 'fresh fruits' paired with 'yogurt' and 'packaged vegetables fruits' being the most frequent combinations.This cluster's preference for healthy snacks and dairy aligns with their identity as health-conscious shoppers. The frequent combination of fruits and yogurt could indicate a trend towards healthy breakfast or snack choices.

**Cluster 1: The Balanced Basket Shoppers**
- As the largest segment (70.03% of purchasers), this cluster engages in a varied selection of fresh produce. Their average basket size is modest (8.685), which could signal selective shopping or budget awareness.
- Their relatively lower reorder rate suggests a combination of habitual and impromptu purchasing patterns.
- **Top Pairings**: Diverse pairings with 'fresh fruits' and 'fresh vegetables' leading, indicating a balanced diet.The variation in pairings supports their profile as balanced shoppers, likely to have a mix of routine and exploratory shopping patterns.

**Cluster 2: The Niche Market - Baby Care Focused**
- Although small (1.37% of purchasers), this segment is distinguished by a significant purchase of baby food, hinting at a customer base of infant caretakers.
- They have the most substantial average basket size, presumably due to bulk purchases in the baby care category.
- **Top Pairings:** 'Baby food formula' has a high frequency, but fresh produce also features prominently, showing that these shoppers are purchasing for more than just baby needs. Their unique shopping needs are further emphasized by the frequency of baby food purchases, yet they maintain a balanced diet indicated by purchases of fresh produce.

**Cluster 3: The Veggie Lovers**
- Accounting for 11.21% of purchasers, this cluster exhibits the highest spending on vegetables, suggesting a focus on health-conscious or vegetarian diets.
- **Top Pairings:** Dominated by vegetable pairings, which aligns with their profile as veggie lovers. The cluster's strong preference for vegetables is evident, which might suggest that they are more likely to be cooking at home.


### Comparative Insights
**Clustering**
- **Average Basket Size:** Cluster 2's larger basket size likely reflects the necessity to stock up on baby products, in contrast to Cluster 1's selective shopping behavior.
- **Average Number of Orders:** Cluster 1 has fewer orders on average, which might signify a group with less frequent shopping activity. However, across all clusters, the average is close to 1, implying the dataset may primarily consist of single-order cases per user.
- **Distinct Product Purchases:** Cluster 2’s diverse product assortment possibly mirrors the comprehensive needs within the baby care spectrum.
- **Reorder Rate:** Clusters 0 and 2 have higher reorder rates, suggesting regular buying habits, which may be attributed to essential daily goods and baby care items.
- **Purchase Interval:** The shorter purchase intervals in Cluster 2 could be a reflection of the frequent necessity to replenish baby care supplies.
Time of Purchase: While afternoon shopping on Mondays and Sundays is common across all clusters, Cluster 2 uniquely shows a significant morning shopping presence (9-11 AM), likely aligned with the routines of parents.

**Market Basket Analysis**
- **Healthy Eating:** Clusters 0 and 3 are more likely to pair fresh produce with other healthy options like yogurt, which may indicate a trend towards health-conscious eating.
- **Family-Oriented Shopping:** Cluster 2 pairs baby food with other household groceries, suggesting shopping behavior that caters to all family members.
- **Routine vs. Spontaneity:** The high reorder rates in Cluster 0 suggest a routine in their shopping habits, while the lower rates in Cluster 1 might indicate more spontaneous purchasing.
- **Potential Targeting Strategies:** Retailers can target Clusters 0 and 3 with health-oriented promotions, while Cluster 2 might be more responsive to baby-care related deals.


## ⭐️ How to apply to Business Strategies
**1. Personalized Promotions**

For Cluster 0, introduce loyalty rewards on fruits and yogurt, and for Cluster 3, offer vegetable bundle deals with complementary health products.

**2. Targeted Product Placement**

For Cluster 2, strategically place baby essentials for easy access and expedite shopping with a 'Family Shopping' lane.

**3. Cross-Selling Opportunities**

Suggest complementary items like granola with yogurt for Clusters 0 and 3 during checkout for effective cross-selling.

**4. Store Layout Optimization**

Reorganize the store to cluster top-purchased produce for Clusters 0 and 3, streamlining their shopping experience.

**5. Demand Forecasting and Inventory Management**

Analyze purchase pair frequencies across all clusters to inform inventory management and reduce stockouts.

**6. Time-Based Marketing**

Offer morning specials on baby products for early shoppers in Cluster 2 to capture the peak shopping times.
