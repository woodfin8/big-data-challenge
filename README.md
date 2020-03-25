# big-data-challenge

[!toy_review](Level-1/toy_total_help_ratio.PNG)

## Reviewing the Reviewers
This assignment analyzes two review data-sets from Amazon's [Vine Program](https://www.amazon.com/gp/vine/help?ie=UTF8). 

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


