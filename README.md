# Amazon Vine Analysis

## Project Overview

The purpose of this project was to analyze reviews that were written through Amazon's paid Amazon Vine program. This program allows companies to pay a fee to Amazon and provide products to the Amazon Vine members who then are required to leave a review. This project will use a dataset of music reviews to analyze whether there is any bias toward favorable reviews from Vine members in the dataset. PySpark is used to extract and transform the data, and then to connect to an AWS RDS instance and load the data into a database in pgAdmin. PySpark is again used for the analysis of the positive reviews. 

## Resources

- Data Sources: [Amazon Vine Music Reviews](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Music_v1_00.tsv.gz)
- Software: PySpark 3.0.3, Google Colaboratory, Amazon AWS RDS, pgAdmin 4

## Results

To begin the analysis of positive reviews, a Vine dataframe is created to hold information related to star ratings and votes

![vineDF](https://github.com/mein0819/Amazon_Vine_Analysis/blob/main/readMeImages/vineTable.png)

The data is furthur grouped into reviews that had 20 or more total votes and which the percentage of helpful votes is 50% or higher

![helpful votes](https://github.com/mein0819/Amazon_Vine_Analysis/blob/main/readMeImages/helpfulVotesDF.png)

From this dataframe, the reviews are separated into two dataframes of paid and unpaid Vine reviews

![paid reviews](https://github.com/mein0819/Amazon_Vine_Analysis/blob/main/readMeImages/paidDF.png)

![unpaid reviews](https://github.com/mein0819/Amazon_Vine_Analysis/blob/main/readMeImages/unpaidDF.png)

The analysis for the paid Vine reviews shows the following:

![paid5star](https://github.com/mein0819/Amazon_Vine_Analysis/blob/main/readMeImages/paid5star.png)

- There were 7 total paid Vine reviews
- 0 reviews had a 5 star rating, so 0% of paid Vine music reviews were 5 stars

The analysis for the unpaid Vine reviews show the following: 

![unpaid5star](https://github.com/mein0819/Amazon_Vine_Analysis/blob/main/readMeImages/unpaid5star.png)

- There were 105,962 total unpaid Vine reviews
- 67,568 of those reviews were 5 star
- 63.77 of unpaid Vine music reviews were 5 stars

## Summary

Due to the small sample size of the paid Vine reviews it's hard to determine whether there is any positivity bias in the reviews. A 63% 5 star rate out of 105,962 unpaid reviews shows a tendency towards bias though. For futher analysis, widening the criteria for which reviews are included may help with the sample size issue, or else a different data set may need to be used all together to get a better picture of positivity bias between paid and unpaid reviewers to determine whether the Vine program is worth investing in. 

