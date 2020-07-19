# Data-Modeling-with-Postgres
Project 1: Data Modeling with Postgres for Udacity 


# The goal 
of this project is to build a PostgreSQL database utilizing the data on users activity and songs metadata. Building the database helps us do complex analytics regarding users activity as well as song play analysis.

# Data
The songs' metadata sourse is a subset of the Million Song Dataset (https://labrosa.ee.columbia.edu/millionsong/). Also, the users' activities is a simulated data using eventsim. The data resides in two main directories:

Songs metadata: collection of JSON files that describes the songs such as title, artist name, year, etc.
Logs data: collection of JSON files where each file covers the users activities over a given day.


# HOW TO
The source code is available in three separate Python scripts. Below is a brief description of the main files:

sql_queries.py has all the queries needed to both create/drop tables for the database as well as a SQL query to get song_id and artist_id from other tables since they are not provided in logs dataset.


create_tables.py creates the database, establish the connection and creates/drops all the tables required using sql_queries module.


etl.py build the pipeline that extracts the data from JSON files, does some transformation (such as adding different time attributes from timestamp) and then insert all the data into the corresponding tables.


Therefore, we first run create_tables.py then etl.py to create the database, create tables, and then insert the data using the ETL pipeline.



# Examples
```
%load_ext sql
%sql postgresql://student:student@127.0.0.1/sparkifydb
%%sql
SELECT COUNT(*) from songplays;
```
