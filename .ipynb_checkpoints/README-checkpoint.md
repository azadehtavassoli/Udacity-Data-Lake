# Data Lake
Project Data Warehouse done by Azadeh Tavassol as part of the Udactiy Data Engineer Nanodegree.

## Project Summary

The aim is to build an ETL pipline to extract songs and logs data from even S3 bucket in first step, and using Spark and PySpark transform and load the data into a set of tables in form of parquet file on another S3 bucket.

Due to the larg scale of song files, a small protion of it is porvided on the local machin for development and testing. After finalizing the local etl python script, the codes are moved to an EMR notebook on the AWS platform, overwhich the actual process of ETL is performed. The EMR notebook is also included in the project files.


## Used input data
The input data contains two S3 buckets:

* Song data: s3://udacity-dend/song_data
* Log data: s3://udacity-dend/log_data

The song dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are filepaths to two files in this dataset.

* song_data/A/B/C/TRABCEI128F424C983.json
* song_data/A/A/B/TRAABJL12903CDCF1A.json

## ETL pipeline
The ETL pipeline (see etl.py) loads the S3 data sources into Spark dataframes, aggregrates and transforms the data into the described schema and writes the data back to S3 in the parquet format.

## Instructions

* **dl.cfg:**
Create an AWS IAM role .dl.cfg is contain AWS keys.

* **etly.py:**
This script once executed retrieves the song and log data in the s3 bucket, transforms the data into fact and dimensional tables then loads the table data back into s3 as parquet files.

* **Sparkify.ipynb:**
The EMR notebook to run the ETL process over AWS platform