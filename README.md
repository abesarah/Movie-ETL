# Movie-ETL
![ ](/Resources/movie_reels.jpg?raw=true=250x250)

### Purpose:
Created an automated pipeline that takes in new data (Wikipedia data, Kaggle metadata, and the MovieLens rating data), performs the appropriate transformations, and loads the data into existing tables in a PostgreSQL database.  

### Technologies Used: 
-	Python
    - Pandas
    - SQLAlchemy
-	PostgreSQL

### [Deliverable 1](/ETL_function_test.ipynb): 
-	An ETL function is written to read in the three data files. 
-	The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed in the file. 
-	The function converts the Kaggle metadata file to a Pandas DataFrame. 
-	The function converts the MovieLens ratings data file to a Pandas DataFrame.

### [Deliverable 2](/ETL_clean_wiki_movies.ipynb): 
-	The TV shows are filtered out, and the wiki_movies_df DataFrame is created. 
-	A try-except block is used to catch errors while extracting the IMDb IDs with a regular expression and dropping duplicate IDs. 
-	The extraction and transformation of the Wikipedia data in the ETL function does the following:
-	A list comprehension is used to keep columns with non-null values. 
-	The non-null box office data is converted to string values using the lambda and join functions. 
-	A regular expression is used to match the six elements of "form_one" of the box office data. 
-	A regular expression is used to match the three elements of "form_two" of the box office data. 
-	The following columns are cleaned in the Wikipedia DataFrame: 
    - The box office column
    - The budget column
    - The release date column
    - The running time column
-	The cleaned Wikipedia data is converted to a Pandas DataFrame.
### [Deliverable 3](/ETL_clean_kaggle_data.ipynb): 
-	The extraction and transformation of the Kaggle metadata using the ETL function does the following:
-	The Kaggle metadata is cleaned. 
-	The Wikipedia and Kaggle DataFrames are merged. 
-	The following is performed on the merged Wikipedia and Kaggle DataFrames.
    - Unnecessary columns are dropped.
    - A function is used to fill in the missing Kaggle data.
    - The movies_df DataFrame is filtered to keep specific columns.
    - The movies_df DataFrame columns are renamed.
-	The extraction and transformation of the MovieLens ratings data using the ETL function does the following:
-	The ratings counts are cleaned. 
-	The movies_df DataFrame is merged with the cleaned ratings DataFrame. 
-	The empty values in the movies_with_ratings_df DataFrame are filled with “0”. 
-	The movies_with_ratings_df and the movies_df DataFrames are displayed. 
### [Deliverable 4](ETL_create_database.ipynb): 
-	The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png.
-	The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png. 
-	The elapsed time to add the data to the database is displayed.

	

