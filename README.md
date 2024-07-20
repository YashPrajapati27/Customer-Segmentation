# Customer Segmentation Project

## Project Overview
This project aims to utilize machine learning techniques to segment customers based on their purchasing behavior, age, gender, annual income, etc. By dividing customers into distinct segments, we aim to gain insights into their preferences, needs, and behaviors. This information can inform targeted marketing strategies, personalized recommendations, and product/service offerings.

## Source Data
The dataset used in this project is the **Online Retail Dataset** from the UCI Machine Learning Library. The dataset consists of 8 columns and 5000 rows. Below is the data dictionary:

- **InvoiceNo**: Invoice number uniquely assigned to each transaction.
- **StockCode**: Product (item) code.
- **Description**: Product (item) name.
- **Quantity**: The quantities of each product (item) per transaction.
- **InvoiceDate**: The day and time when each transaction was generated.
- **UnitPrice**: Product price per unit in sterling.
- **CustomerID**: Customer number uniquely assigned to each customer.
- **Country**: The name of the country where each customer resides.

## Data Preprocessing
1. **Handling Missing Data**: Removed rows with null `CustomerID` as there is no way to retrieve these numbers.
2. **Removing Negative Values**: Removed records where `UnitPrice` < 0 and `Quantity` < 0, as these could represent cancelled or returned orders.
3. **Country Restriction**: Restricted the data to only `United Kingdom` customers as more than 90% of the customers are from the UK.

## Customer Segments
The K-Means clustering algorithm was used for customer segmentation. The Davies-Bouldin Score was used to evaluate the clustering performance. The smaller the Davies-Bouldin Score, the more optimal the cluster. The evaluation results are as follows:

- **3 Clusters**: Davies Bouldin Score - 1.0202
- **4 Clusters**: Davies Bouldin Score - 0.9815
- **5 Clusters**: Davies Bouldin Score - 0.9976

The optimum cluster was found to be 4, with the lowest Davies-Bouldin Score.

### Interpretation of the Clusters
1. **Loyal Customers (Cluster 0)**: A small segment (4%) with infrequent recent purchases but a history of high purchase frequency and value. They might require targeted campaigns to re-engage them.
2. **Almost Lost (Cluster 1)**: The largest segment (43%) with recent purchases but low purchase frequency and value. They require strategies to incentivize more frequent and higher-value purchases.
3. **Lost Cheap Customers (Cluster 2)**: A significant segment (35%) with infrequent and low-value purchases in the distant past. They might be less profitable to target.
4. **Best Customers (Cluster 3)**: A sizable segment (18%) with the most recent, frequent, and high-value purchases. They deserve continued focus and loyalty programs.

## Conclusion
The customer segmentation using K-Means clustering helped in identifying four distinct customer segments. These insights can be used to tailor marketing strategies, enhance customer engagement, and improve business outcomes.
