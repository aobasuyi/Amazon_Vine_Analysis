# Amazon_Vine_Analysis

## Overview of the analysis
The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. A client about to release a large catalogue of products will be assisted in analyzing Amazon reviews written by members of the paid Amazon Vine program to determine if there were bias toward favorable reviews from Vine members. <br />

The technical deliverables required to complete the Amazon Vine analysis include: <br />

1. Perform ETL on Amazon Product Reviews.
2. Determine Bias of Vine Reviews.


## Resources
- Data Source: This analysis was performed using the  [Health_Personal_Care](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Health_Personal_Care_v1_00.tsv.gz) dataset.
-  Codes: [Amazon Review ETL](https://github.com/aobasuyi/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb) and [Vine Review Analysis](https://github.com/aobasuyi/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb)
- Data Tools:  Google Colaboratory notebook
- Software: Apache Spark 3.0.3, Python 3.7, Visual Studio Code 1.50.0 


## Results: 

#### Deliverable 1: Perform ETL on Amazon Product Reviews:

- Using your knowledge of the cloud ETL process, create an AWS RDS database with tables in pgAdmin. Pick a dataset from the Amazon Review datasets and extract the dataset into a DataFrame. Transform the DataFrame into four separate DataFrames that match the table schema in pgAdmin. Then upload the transformed data into the appropriate tables and run queries in pgAdmin to confirm that the data has been uploaded.

#### a). The extracted dataset was transformed into four DataFrames as shown:

**The customers DataFrame:** <br />
<br /> ![Image](Dataframe_images/customer_df.png) <br />

**The products DataFrame:** <br />
<br /> ![Image](Dataframe_images/products_df.png) <br />

**The review_id DataFrame:** <br />
<br /> ![Image](Dataframe_images/review_id_df.png) <br />

**The vine DataFrame:** <br />
<br /> ![Image](Dataframe_images/vine_df.png) <br />

#### b). All four DataFrames were loaded into their respective tables in pgAdmin. The results were then queried to check that the tables have been populated are shown:

**The customers table (pgAdmin):** <br />

| Customers table  | Query Result |
| ------------- | ------------- |
| ![customers_table](Images/customers_table.png)  | ![customer_table_query](Images/customers_table_message.png) |

**The products_table (pgAdmin):** <br />

| Customers table  | Query Result |
| ------------- | ------------- |
| ![products_table](Images/products_table.png)  | ![products_table_query](Images/product_table_message.png) |

**The review_id_table:** <br />

| Customers table  | Query Result |
| ------------- | ------------- |
| ![customers_table](Images/review_id_table.png)  | ![customer_table_query](Images/review_id_table_message.png) |


**The vine_table:** <br />

| Customers table  | Query Result |
| ------------- | ------------- |
| ![customers_table](Images/vine_table.png)  | ![customer_table_query](Images/vine_table_message.png) |


### Deliverable 2: Determine Bias of Vine Reviews:

- Determine the number of Vine and non-Vine reviews: <br />
    - The number of helpful Vine reviews : **497**
    - The number of helpful non-Vine reviews : **120863**

- Determine how many Vine reviews and non-Vine reviews were *5 stars*:<br />
    - The number of helpful *5-star* Vine reviews : **220**
    - The number of helpful *5-star* non-Vine reviews: **74470**

- Determine what percentage of Vine reviews and non-Vine reviews were *5 stars*:<br />
    - The percentage of helpful Vine reviews that were *5 stars*: 44.27%
    - The percentage of helpful non_Vine reviews that were *5 stars*: 61.62%

## Summary: 
- The results of the analysis from this dataset show that Non-Amazon Vine members were more likely to give a Health Personal Care product a *5 star* rating compared to an Amazon Vine member. There seems to be no positivity bias in the paid reviews compared to unpaid Vine reviews.

- An additional analysis carried out with the dataset to support this statement (refer to [Vine Review Analysis](https://github.com/aobasuyi/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb)) shows that.
    - The percentage of total Vine reviews for votes greater or equal to 20 that were 5 stars: **43.56%**
    - The percentage of total non_Vine reviews for votes greater or equal to 20 that were 5 stars: **57.24%**
