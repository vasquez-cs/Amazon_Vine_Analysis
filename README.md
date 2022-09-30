# Amazon_Vine_Analysis

## Overview of the analysis: 

Our work on the SellBy project was so successful, we’ve been tasked with another, larger project. We are to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. SellBy pay a fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

I chose to analyze the amazon_reviews_us_Sports data set. I used PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance. I used pgAdmin to create data tables using sql. From the AWS RDS instance, I loaded the transformed data into the pgAdmin tables. I then used PySparkto determine if there is any bias toward favorable reviews from Vine members in your dataset.

## Results:

### How many Vine reviews and non-Vine reviews were there?
<img src="https://user-images.githubusercontent.com/107224632/193182203-e11654d5-7866-4927-b1f6-8db61b0597e6.png" width=80% height=80%><br />
*Figure 1: total_ratings_df *<br />

 *There are a total of 334 Vine reviews
 *There are a total of 61614 non-vine reviews

### How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

  *There are a total of 139 5 star Vine reviews and 
  *There are a total of 32665 5 star non-vine reviews

### What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

  *The percentage of Vine reviews that were 5 stars is 41.62% (rounded)
  *The percentage of non-Vine reviews that were 5 stars is 53.02% (rounded)

## Summary: In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
