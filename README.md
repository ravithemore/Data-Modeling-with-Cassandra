# Data Modeling with Cassandra

This project focuses on applying data modeling techniques with Cassandra and building an ETL (Extract, Transform, Load) pipeline using Python. The objective is to create a data model tailored to the specific queries we want to perform on our dataset. 

## Project Overview

In this project, we aim to build a data model around the following queries:

1. Get details of a song that was heard on the music app history during a particular session.
2. Get songs played by a user during a particular session on the music app.
3. Get all users from the music app history who listened to a particular song.

## Requirements

To run this project, you need:
- Python (version >= 3.6)
- Apache Cassandra
- Cassandra Python driver (cassandra-driver)

## Dataset

The dataset used for this project contains the music app history, which includes information such as user sessions, songs played, and other relevant details.

## Data Modeling

### Entity-Relationship Diagram (ERD)

To design our data model, we first create an Entity-Relationship Diagram (ERD) based on the queries we want to support. This helps us understand the relationships between different entities in our dataset.

### Tables Creation

We create tables in Cassandra to store our data efficiently based on our ERD. Each table is designed to support specific queries, ensuring optimal performance.

## ETL Pipeline

The ETL pipeline is responsible for extracting data from the source, transforming it into a format suitable for our data model, and loading it into Cassandra tables.

## Project Structure

- `data/`: Contains the dataset used in the project.
- `src/`: Contains Python scripts for data modeling and ETL.
  - `create_tables.py`: Script to create tables in Cassandra.
  - `etl.py`: ETL pipeline implementation.
- `README.md`: Documentation for the project.

## Running the Project

1. Clone the repository: `git clone https://github.com/your_username/data-modeling-cassandra.git`
2. Navigate to the project directory: `cd data-modeling-cassandra`
3. Install dependencies: `pip install -r requirements.txt`
4. Start Apache Cassandra.
5. Run `create_tables.py` to create tables in Cassandra.
6. Run `etl.py` to execute the ETL pipeline and populate the tables.
7. You can now run queries to retrieve desired information from the Cassandra tables.

## Example Queries

Here are some example queries you can run against the created tables:

1. Get details of a song played during a particular session:
```sql
SELECT * FROM songs_by_session WHERE session_id = <session_id> AND item_in_session = <item_in_session>;
