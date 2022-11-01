# big-data-challenge: Amazon product reviews

This repository contains two scripts performing the ETL process and uploading DataFrames to an RDS instance.

[Video Games dataset script](level-1/amazon_reviews_videogames.ipynb)

[Books dataset script](level-1/amazon_reviews_books.ipynb)

The following [schema](level-1/schema.sql) was used to create the tables in the RDS database. 

The two datasets used to create the DataFrames are linked below:

 1. [Video Games](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz)

 2. [Books](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Books_v1_02.tsv.gz)

Each script carries out the following:

 * Creates a SparkSession and connection to Postgres

 * Loads in the datasets from S3 into a DataFrame

 * Drops null and duplicate rows

 * Formats the DataFrame columns to match the schema formats

 * Creates multiple DataFrames for each table in the database

 * Writes the DataFrames to the tables in an RDS instance.

There is an additional script that uses PySpark to analyse whether Vine reviews can be seen as trustworthy reviews. The above Video Games dataset was used for this analysis. 

[Vine reviews analysis](level-2/vine_reviews_analysis.ipynb)