# Amazon_Vine_Analysis

## Overview of the analysis: 

Our work on the SellBy project was so successful, we’ve been tasked with another, larger project. We are to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. SellBy pay a fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

<img src="https://user-images.githubusercontent.com/107224632/193185240-ebfef4a1-b3c8-4cc3-b851-e196f670c963.png" width=80% height=80%><br />
*Figure 1: Load Amazon Data into Spark DataFrame *<br />

<img src="https://user-images.githubusercontent.com/107224632/193185406-a8604de7-fcf9-48c3-81a0-5049e3ac19cd.png" width=80% height=80%><br />
*Figure 2: customers_df *<br />

<img src="https://user-images.githubusercontent.com/107224632/193185509-bb9754e2-0740-4b13-b790-ea6f0f05d168.png" width=80% height=80%><br />
*Figure 3: products_df *<br />

<img src="https://user-images.githubusercontent.com/107224632/193185615-18296757-1a37-4907-b88f-73a2320e0f0c.png" width=80% height=80%><br />
*Figure 4: review_id_df *<br />

<img src="https://user-images.githubusercontent.com/107224632/193185756-0cec6610-2fda-4f5d-8f29-a1517785989e.png" width=80% height=80%><br />
*Figure 5: vine_df *<br />

<img src="https://user-images.githubusercontent.com/107224632/193185866-4adc03c8-f618-4ba9-9a9d-c74a27825f86.png" width=80% height=80%><br />
*Figure 6: Connecting to the AWS RDS instance and write each DataFrame to its table *<br />

<img src="https://user-images.githubusercontent.com/107224632/193186440-35b51396-26d6-4d53-b771-e84805b99762.png" width=80% height=80%><br />
*Figure 7: products_table *<br />

<img src="https://user-images.githubusercontent.com/107224632/193186600-3f1761a0-2eaa-4e76-9e25-b74951c43c9d.png" width=80% height=80%><br />
*Figure 8: customers_table *<br />

<img src="https://user-images.githubusercontent.com/107224632/193186761-84c078e3-c0f1-4fcb-b2e5-3ad3ae1ef8f2.png" width=80% height=80%><br />
*Figure 9: review_id_table *<br />

<img src="https://user-images.githubusercontent.com/107224632/193186934-72ee3be4-00bb-4bb3-83ee-e29b3360c758.png" width=80% height=80%><br />
*Figure 10: vine_table *<br />

I chose to analyze the amazon_reviews_us_Sports data set. As shown in figures 1, I used PySpark to take the amazon_reviews_us_Sports dataset and import it to a dataframe. As shown in figures 2 through 6, I performed the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance. I used pgAdmin to create data tables using sql. From the AWS RDS instance, I loaded the transformed data into the pgAdmin tables. Figures 7 through 10 show each of the tables in pgAdmin filled with the transformed data. I then used PySparkto determine if there is any bias toward favorable reviews from Vine members in your dataset.

## Results:

### How many Vine reviews and non-Vine reviews were there?

<img src="https://user-images.githubusercontent.com/107224632/193182203-e11654d5-7866-4927-b1f6-8db61b0597e6.png" width=80% height=80%><br />
*Figure 11: total_ratings_df *<br />

 * There are a total of 334 Vine reviews <br />
 * There are a total of 61614 non-vine reviews <br />

### How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

  * There are a total of 139 5 star Vine reviews <br />
  * There are a total of 32665 5 star non-vine reviews <br />

### What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

  * The percentage of Vine reviews that were 5 stars is 41.62% (rounded) <br />
  * The percentage of non-Vine reviews that were 5 stars is 53.02% (rounded) <br />

## Summary: 
Based on our analysis of the amazon_reviews_us_Sports data set, we can comfortably say that there is not a positivity bias for reviews in the Vine program. As shown in figure 11, our percentage of 5 star reviews given by vine members is about than 12% lower than those given by non-vine reviews. This lower percentage doesn't fit the expected results for a positivity bias, which would expect vine reviews to have a higher 5 star percentage than the non-Vine reviewer. To better support our argument, we could evaluate the remaining ratings on the review scale. Evaluating the 1, 2, 3 and 4 star reviews between the Vine and non-Vine reviews in additon to evaluating different datasets would better support our initial observation that Vine reviews do not show positivity bias.
