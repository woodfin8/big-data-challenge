# big-data-challenge

##Who Watches the Watchmen?
This assignment analyzes reviews from Amazon's [Vine Program](https://www.amazon.com/gp/vine/help?ie=UTF8). 

Review data sets are extracted from [S3](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt) and into a SparkSession. 
Using `PySpark`, the data is separated into 4 tables; customers, products, review_id_table and vine_table. 
These tables are written to a PostgreSQL Database hosted on Amazon RDS.

##Tech
* Python - version 3.7.3
* pgAdmin - version 4.13
* Spark - version 2.4.4
* Amazon S3
* Amazon RDS



