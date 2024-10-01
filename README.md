Amazon Books ETL
This project contains an ETL (Extract, Transform, Load) process implemented using Apache Airflow. It fetches book data from Amazon, cleans it, and stores it in a PostgreSQL database.

**Overview**
  The ETL process consists of the following tasks:
  1. _Extract_: Fetch book data from Amazon.
  2. _Transform_: Clean the data for consistency.
  3. _Load_: Store the cleaned data in a PostgreSQL database.

**Components**
  **Directed Acyclic Graph (DAG)**
  The DAG defines the workflow and consists of the following tasks:
  - _fetch_book_data:_ Extracts data from Amazon.
  - _create_table:_ Creates a table in PostgreSQL to store the book data.
  - _insert_book_data:_ Loads the extracted data into the PostgreSQL table.
  
  **Operators**
  - _PythonOperator_: Used to execute Python functions for fetching and inserting data.
  - _PostgresOperator_: Used to create the table in PostgreSQL.
  
  **Hooks**
  - _PostgresHook_: Allows connection to the PostgreSQL database.

  **Installation**
    1. Ensure you have Python 3.x installed.
    2. Install the required packages using pip:
      pip install apache-airflow requests pandas beautifulsoup4
    3. Set up your PostgreSQL database and create a connection with the ID _books_connection_
