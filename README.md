Real-Time Data Ingestion Pipeline with Apache Airflow, PostgreSQL, and API Integration


Overview:

This project implements a real-time data ingestion pipeline using Apache Airflow. The pipeline extracts user data from an API, processes it into a structured format, and loads it into a PostgreSQL database. Additionally, data is extracted from an API and integrated into the same database. The entire process is orchestrated using Airflow, and DBWeaver is used for database visualization.

Architecture:


API Data Source: An external REST API providing user and data in JSON format.

Apache Airflow: Used for orchestrating the data extraction, transformation, and loading (ETL) processes.

PostgreSQL: Serves as the database to store the processed user and weather data.

DBWeaver: A database management tool used to visualize and interact with PostgreSQL.

Docker: Used to containerize the Airflow environment and ensure seamless deployment.

Workflow:

Extract User Data:

The SimpleHttpOperator in Airflow fetches user data from the API endpoint.

The response is parsed and stored as an XCom variable.

Extract Weather Data:

Another SimpleHttpOperator fetches weather data from an external API.

The response is also stored as an XCom variable.

Process Data:

The extracted JSON data is transformed into a structured format using Pandas.

The data is normalized and converted into CSV format.

Store Data:

A PostgresHook is used to load the processed CSV data into a PostgreSQL database.

The COPY SQL command inserts the data efficiently.
