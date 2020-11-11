# Overview of Amazon Customer Rating Analysis
The purpose of this analysis is to work with and perform an ETL process on big data and store it with Amazon Web Services (AWS). The dataset used in this analysis is from a Amazon Customer Review database that contains two types of customer feedback: paid and unpaid reviews. This dataset includes information about various watches from an Amazon program called Vine that was responsible for conducting the paid reviews. 

In the analysis, we clean up the data, transform and filter it with dataframes and then store it in pgAdmin SQL tables in a server connected to AWS. Once it is cleaned, analysis is conducted to determine whether there is any bias in the reviews of the Vine program, compared to unpaid customer reviews.

The tools used in this analysis are: Python with PySpark in Google Colab (used to transform and clean the dataset), pgAdmin with SQL tables, and AWS servers.

# Results
1. How many Vine reviews and non-Vine reviews were there?
Once the dataset was cleaned (filtered for total votes over 20, and whether helpful votes/total votes is >= 50%), there were 8,409 total reviews. There were 47 total paid Vine reviews and 8,362 unpaid reviews.

2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
There are only 15 five star Vine reviews. There are 4,332 five star unpaid reviews.

3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
31.9% of Vine reviews were five stars. 51.8% of non-Vine reviews were five stars.

# Summary
In conclusion, there are a few different points to call out about the Vine paid reviews vs. unpaid reviews.

* There are only 47 total reviews for the paid program, compared to 8,362 unpaid reviews. This means that there is a lot more valuable insight to gather from the unpaid reviews since the dataset is much larger.
* There is negative bias for the paid reviews, as the % to total of 5 star reviews was only 31.9% compared to unpaid at 51.8%. This means that the customers rating the product might have been more critical because they were being paid for their insight. Those who left unpaid reviews were responding more accurately because there was no outside influence on their opinions or reviews.
* In order to support this conclusion, I would also look at other ratings in the reviews. Perhaps the paid Vine reviewers rated more things with a 4 instead of 5 compared to unpaid reviews (and had a higher percentage of 4 star ratings). This could be because they didn't want to always provide 100% satisfaction with the product since they were being paid and wanted to appear that they were being critical of the product.

# Storage in AWS
Since the dataset in this analysis is so large, it is important to store it on a cloud based server. This data is uploaded to the AWS using pgAdmin. Below are screenshots of the dataset stored in various SQL tables in pgAdmin.


![Dashboard](https://github.com/Gerry84/Amazon_Vine_Analysis/blob/main/images/customers_table.PNG)
![Dashboard](https://github.com/Gerry84/Amazon_Vine_Analysis/blob/main/images/products_table.PNG)
![Dashboard](https://github.com/Gerry84/Amazon_Vine_Analysis/blob/main/images/review_id_table.PNG)
![Dashboard](https://github.com/Gerry84/Amazon_Vine_Analysis/blob/main/images/vine_table.PNG)
