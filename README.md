## Project Overview: Netflix Data Pipeline with MongoDB & PyMongo
This project demonstrates how to design a simple data engineering pipeline using only Python, MongoDB, and PyMongo. 
The goal is to support the Data Science and Product teams of a global streaming platform by answering key business questions about content performance and user behavior.

The data originates from a cleaned Netflix dataset (netflix_cleaned.csv), which is first loaded into MongoDB (netflixDB.titles collection). 
From there, a series of aggregation pipelines is applied to extract insights such as popular genres, country-level trends, monthly content uploads, ratings distribution, and duplicate titles. Finally, results are automated and exported for further use in analysis or dashboards.
## Steps and queries used to build the data pipeline are;
1. Data Ingestion

Imported the dataset netflix_cleaned.csv into MongoDB (netflixDB database, titles collection).

Verified schema consistency (fields like title, listed_in, country, date_added, release_year, rating, type).

2. Query Design & Transformation
Designed MongoDB aggregation pipelines for each business task:

Genres with more than 100 shows → Unwound listed_in field and grouped by genre.

Top 5 countries by movie releases after 2015 → Filtered type = Movie, then grouped by country.

Monthly upload trend → Extracted year and month from date_added and counted uploads.

Most common rating per content type → Grouped by (type, rating) to find dominant ratings.

Duplicate titles → Grouped by title and identified duplicates.

3. Automation with PyMongo

Completed each aggregation pipeline in Python scripts using PyMongo.

Converted MongoDB query results into pandas DataFrames.

Exported results into CSV files so they can be consumed by Product Managers or Data Scientists.
