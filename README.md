 # Data Modeling with Postgres
 
 
 
 
 ### Scope
 
 Data Modeling with Postgres is a project designed for Sparkify  with the goal to streamline their data models and simplify the querying into the database. The project aims to create an ETL pipeline using the JSON logs to save into the Postgres database inorder to make it east for querying and performing analysis on song plays.
 
 ### Prerequsites
 
 - Postgres
 - Python 3+
 - Anaconda / Jupyter Notebook
 
 
 ### How to Execute
 
 1. Run create_tables.py
 2. Run etl.py
 3. Test and Validate the script using test.ipynb Jupyter Notebook
 
 
 
 
 ### Database Design & Schema
 
 In order to simplify and increase query execution we'd have to develope a database on a star schema. We'd have a Fact table *songplays* and  dimension <br/>
 tables *users*, *artists*, *songs*, *time*. 
 
 Songplays
 
 Column | DataType | Constraint
 --- | --- | ---
 songplay_id | Serial | NOT NULL , PRIMARY
 start_time | VARCHAR | NOT NULL
 user_id | INT | NOT NULL
 level | VARCHAR
 song_id | VARCHAR
 artist_id | VARCHAR
 session_id | INT
 location | VARCHAR
 user_agent | VARCHAR
 
 
 Dimesion Tables:
 
 users
 
  Column | DataType | Constraint
 --- | --- | ---
 user_id | INT | NOT NULL, PRIMARY
 first_name | VARCHAR
 last_name | VARCHAR
 gender | VARCHAR
 duration | VARCHAR
 
 
 Songs
 
  Column | DataType | Constraint 
 --- | --- | ---
 song_id | VARCHAR | NOT NULL, PRIMARY
 title | VARCHAR
 artist_id | VARCHAR | NOT NULL
 year | INT
 duration | FLOAT
 
 Artists
 
  Column | DataType | Constraint
 --- | --- | ---
 artist_id | VARCHAR | NOT NULL, PRIMARY
 name | VARCHAR
 location | VARCHAR
 latitude | FLOAT
 longitude | FLOAT
 
 Time
 
  Column | DataType | Constraint
 --- | --- | ---
 start_time | TIMESTAMP | NOT NULL, PRIMARY
 hour | INT
 day | INT
 week | INT
 month | INT
 year | INT
 weekday | INT
 
 
 As we can see from the tables, we can get most of the data we need for analysis using the songplays table and if we need further data we can retrieve 
 it using minimum number of joins.
 

 
 
 
 
 
 