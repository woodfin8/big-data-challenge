# big-data-challenge

![toy](/Level-1/images/toy_total_help_avg.png)

## Reviewing the Reviewers
This study analyzes two review data-sets from Amazon's [Vine Program](https://www.amazon.com/gp/vine/help?ie=UTF8). One set of video game reviews and one of toy reviews. 

Review data sets are extracted from [S3](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt) and into a SparkSession. 
Using `PySpark`, the data is separated into 4 tables; customers, products, review_id_table and vine_table. 
These tables are written to a PostgreSQL Database hosted on Amazon RDS.

Vine program reviews and non-vine reviews are compared to gauge the effectiveness of the Vine program. Are Vine reviews more helpful, are they more trustworthy and how many Vine reviewers are potentially un-reliable?

## Tech
* Python - version 3.7.3
* pgAdmin - version 4.13
* Spark - version 2.4.4
* Amazon S3
* Amazon RDS

### Python Dependencies
* Pandas - version0.25.3
* PySpark - version 2.4.4
* Matplotlib - version 3.1.1
* Findspark - version 1.3.0

## Instructions
* Install above Python dependencies
* Create SQL tables using the schema in the SQL_schema folder
* Enter your Amazon RDS url in the 'jdbc_url' variable
* Create a config.py file with your RDS password saved under the 'pword' variable
* Run big_data_games.ipynb and big_data_toys.ipynb to import the data, create tables, load to RDS and run analysis

## Findings
The below findings only consider Amazon reviews which received votes. Reviews that received no votes were filtered out of the data-set.

### Review Distribution

Vine reviewers gave mostly 4 and 5 star reviews in similar proportions. For video games 74.7% of vine reviews gave 4 or 5 stars (37.4% and 37.3% respectively). For toys 74.8% of vine reviews gave 4 or 5 stars (35.9% and 38.9% respectively). Both datasets had very few 1 star vine reviews; 2% of video game vine reviews received one star, 1.7% for toy vine reviews.

For non-vine reviews ,5 star ratings were by far the most common; 47.7% for video games and 53.5% for toys. 1 star ratings were also more common in non-vine reviews; 16.8% for video games and 13.7% for toys.

### Average Number of Helpful Votes

In video games, non-vine reviews received more helpful votes on average than vine reviews for star ratings 1-4. Vine out-perfored modestly in 5 star reviews which received an average of 4.4 vs non-vine's 4.0.

Vine toy reviews did better earning more helpful votes on average than non-vine's across all star ratings. Margin ranged from 1.2 votes better for 5 star reviews to 2.6 votes better for 1 star reviews.

### Helpful Vote Ratio

For another measure of review quality, I looked at the ratio of helpful votes to total votes received by the review. Vine reviews didn't out-perform on this measure. Toy vine reviews under-performed vs their non-vine counterparts in 4 and 5 star ratings (the most common ratings given by vine reviews). Video game 4 and 5 star vine reviews only slightly out-performed non-vine's (4-6%)

### Reviewer Quality

How good are the top reviewers? I filtered for vine and non-vine customers who wrote at least 10 reviews and looked for low-quality reviewers, i.e. reviwers whose helpful vote to total vote ratio was below 50%.

Vine reviewers did only slightly better than their non-vine review counterparts. For video games. 18.1% of vine reviewers were low-quality vs 28.6% of non-vine reviewers. For toys, 4.1% of vine reviewers were low quality vs 7.2% for non-vine

## Conclusions

Based on the video game and toy review data sets, the vine program only creates modestly better reviews. For the video game data set, vine under-perform on average number of helpful votes. Vine reviews for both video games and toys also award 4 or 5 stars ~75% of the time. This suggests vine reviewers are being sent above average products or that they are grading on a favorable curve. 

## Charts

![game_disto](/Level-1/images/game_total_disto.png)

