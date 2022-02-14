# Movies-ETL

## Overview of Extract Transform & Load (ETL) Movies Database Project

The goal of this project was to create an automated data pipeline that extracts various data from multiple sources (Wikipedia data in .json extracted format, movie data from Kaggle.com, and an aggregated movie ratings .csv spreadsheet), clean and amalgamate them into usable, joined datasets, then load them into an SQL database (PostgresSQL) using comprehensive ETL data pipeline functions and SQLAlchemy engines to connect the data from our Jupyter Notebook to our PostgresSQL database server.

We extracted data by reading the appropriate .csv and .json files into our project. We transformed the data by assessing data quality, cleaning rows, formatting data types, and performing necessary joins and drops. We loaded our cleaned data using SQLAlchemy and a polished data pipeline function to import our data cleanly into our SQL database and chunk-wise for data that exceeded PostgresSQL's maximum loading size.

## Results

We've completed this process and separated each step into 4 project files

### 1
#### ETL_function_test.ipynb
Data is discovered and extracted from the appropriate sources (Kaggle.com, wikipedia-movies.json source)
NON_JSON Data is transferred into our Jupyter notebook project and converted into Pandas DataFrames.
JSON Data is loaded using json.load() function, then converted into a Pandas DataFrame.

### 2
#### ETL_clean_wiki_movies.ipynb
Created clean_movie() function to revise and combine alternative languages data (sparse, scattered, inconsistent data) into one alt_titles column.
Revised and changed column names using an embedded change_column_name_function().
Defined a extract_transform_load() function to comprehensively handle the transformation process of wikipedia and kaggle data; this function includes:
- Python list comprehensions
- Lambda functions
- Apply() and map() methods
- RegEx (Regular Expressions) & RegEx-incorporated functions

### 3
#### ETL_clean_kaggle_data.ipynb
Included extraneous ratings.csv data
Cleaned, Filtered, and Merged ratings.csv data to previously cleaned and structured movies dataframe:
- Revised data types with .astype() function, Pandas' pd.to_numeric() function, & logical operators on Boolean data types
- Used .dropna() function, .fillna() function, .drop() function, and .rename() function to filter and change unwanted columns/column names
- Merged DataFrames using pd.merge().

### 4
#### ETL_create_database.ipynb
Used SQLAlchemy to import engine and connect our data to our PostgresSQL database using the create_engine() method and the .to_sql() method
Initiated and completed entire ETL process with a single function call [our function was named extract_transform_load()]