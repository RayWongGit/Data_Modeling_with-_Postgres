# Project: Data Modeling with Postgres
## Introduction
Sparkify is a startup who have just launched a new music streaming app. They wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. 

The analytics team is particularly interested in understanding what songs users are listening to. However, currently they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like us to create a Postgres database with tables designed to optimize queries on song play analysis. Our task in this project is to create a database schema and ETL pipeline for this analysis. 

## Dataset

There are two dataset we will use in this project.

- **Song Dataset**: Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. 
- **Log Dataset**: This consists of log files in JSON format and contains activity logs from a music streaming app based on specified configurations.The log files are partitioned by year and month. 

## Schema Design

Using the song and log datasets, we'll create a star schema optimized for queries on song play analysis. This will include the following tables: 

### Fact Table

**1. songplays** - records in log data associated with song plays i.e. records with page NextSong

- songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
**2. users** - users in the app

- user_id, first_name, last_name, gender, level

**3. songs** - songs in music database

- song_id, title, artist_id, year, duration

**4. artists** - artists in music database

- artist_id, name, location, latitude, longitude

**5. time** - timestamps of records in songplays broken down into specific units

- start_time, hour, day, week, month, year, weekday

## Project Steps
Below are steps we will follow to complete the project:

### Create Tables
First we create a python file named 'sql_queries.py' to write sql statements.

Queries statements including: drop table statement, create table statement, insert value statement as well as select statement.

Then we run create_tables.py to execute the sql statements to create your database and tables.

### Build ETL Processes
In the etl.ipynb notebook, we will develop ETL processes for each table with first couple rows.

### Build ETL Pipeline
Based on the exploration above, we will process the entire datasets 