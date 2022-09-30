# Amazon_Vine_Analysis

## Overview of the analysis: 

Our work on the SellBy project was so successful, we’ve been tasked with another, larger project. We are to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. SellBy pay a fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

As shown in figures 1 ... I chose to analyze the amazon_reviews_us_Sports data set. I used PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance. I used pgAdmin to create data tables using sql. From the AWS RDS instance, I loaded the transformed data into the pgAdmin tables. I then used PySparkto determine if there is any bias toward favorable reviews from Vine members in your dataset.

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

## Summary: 
Based on our analysis of the amazon_reviews_us_Sports data set, we can comfortably say that there is not a positivity bias for reviews in the Vine program. As shown in figure 1, our percentage of 5 star reviews given by vine members is about than 12% lower than those given by non-vine reviews. This lower percentage doesn't fit the expected results for a positivity bias, which would expect vine reviews to have a higher 5 star percentage than the non-Vine reviewer. To better support our argument, we could evaluate the remaining ratings on the review scale. Evaluating the 1, 2, 3 and 4 star reviews between the Vine and non-Vine reviews in additon to evaluating different datasets would better support our initial observation that Vine reviews do not show positivity bias.
