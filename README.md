# data_warehouse

 ***Credits***
Udacity Data Engineer Nanodegree Program

## Rubric
## 1. Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goals.
## 2. State and justify your database schema design and ETL pipeline.

-----------


## Rubric

Table Creation

- [x] ***Table creation script runs without errors.***: The script, create_tables.py, runs in the terminal without errors. The script successfully connects to the Sparkify database, drops any tables if they exist, and creates the tables.

- [x] ***Staging tables are properly defined***: CREATE statements in sql_queries.py specify all columns for both the songs and logs staging tables with the right data types and conditions.

- [x] ***Fact and dimensional tables for a star schema are properly defined.***: CREATE statements in sql_queries.py specify all columns for each of the five tables with the right data types and conditions.
Data Modeling

ETL

- [x] ***ETL script runs without errors.***: The script, etl.py, runs in the terminal without errors. The script connects to the Sparkify redshift database, loads log_data and song_data into staging tables, and transforms them into the five tables.

- [x] ***ETL script properly processes transformations in Python***: INSERT statements are correctly written for each table and handles duplicate records where appropriate. Both staging tables are used to insert data into the songplays table.

Code Quality

- [x] ***The project shows proper use of documentation.***: The README file includes a summary of the project, how to run the Python scripts, and an explanation of the files in the repository. Comments are used effectively and each function has a docstring.

- [x] ***The project code is clean and modular***: Scripts have an intuitive, easy-to-follow structure with code separated into logical functions. Naming for variables and functions follows the PEP8 style guidelines.

## 1. Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goals.

Service logs are proposed to be stored in a db, so to access them easily: it is propose to store them in a "warehouse", a redshift cluster.

## 2. State and justify your database schema design and ETL pipeline.

<img src="http://yuml.me/diagram/plain/class/[songplays|songplay_id;start_time;user_id;level;song_id;artist_id;session_id;location;user_agent]-[Users {bg:orange}| user_id; first_name;last_name;gender;level], [songplays]-[songs {bg:orange}|song_id;title;artist_id;year;duration] , [songplays]-[artists {bg:orange}|artist_id;name;location;latitude;longitude], [songplays]-[time {bg:orange}|start_time;hour;day;week;month;year;weekday]">
