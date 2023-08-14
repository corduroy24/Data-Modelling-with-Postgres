# Purpose
<!-- Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goals. -->
Sparkify's anaylytics team would like to analyze the data they'vce been collecting on and songs and user activity. They are particular interested in understanding what songs users are listening to. Currently, the data required to perform such an analysis comprises of JSON logs in a directory. They would like for an easier approach towards analyzing the data. One that can be sustained or built upon over the years.

# run scripts
<!-- How to run the Python scripts -->
Open a terminal and run the following 
- python create_tables.py
- python etl.py

# Files
<!-- An explanation of the files in the repository -->
***create_tables.py:*** drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
***etl.py:*** reads and processes files from song_data and log_data and loads them into your tables. You can fill this out based on your work in the ETL notebook.
***sql_queries.ipynb:*** contains all your sql queries, and is imported into the last three files above.
***etl.ipynb:*** reads and processes a single file from the song data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables
***test.ipynb:*** displays the first few rows of each table to let you check your database
***data:*** The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID.

# Justification: Database schema and ETL pipeline
<!-- State and justify your database schema design and ETL pipeline. -->
Given that Sparkify does not require advanced quieries, the star schema is most suitable. The analytical team can also take advantage of the denormalized structured and fast aggregations as their database continues to grow.Logically, the fact table with the records in the log data asscoiated with song plays. 4 dimension tables users, songs, artists and timestamps) can be leveraged to answer business questions. 

An ETL pipeline is utilized to transfer data from files in two local directories into these tables in Postgres using Python and SQL.