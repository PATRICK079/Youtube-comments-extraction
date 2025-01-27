# Introduction 

This project is an automated end-to-end ETL pipeline, scheduled to run daily. It fetches comments from a YouTube channel and loads the data into a AWS postgres database.

# Business Statement 


Company XYZ, an entertainment business, is concerned about customer retention and aims to better understand audience feedback. To address this, they have tasked me with developing an automated ETL pipeline that extracts comments from one of their recently posted YouTube videos and stores them in a database. The pipeline will be deployed into production and scheduled to run daily, ensuring new comments are fetched regularly. The ultimate goal is to use these collected comments to build a sentiment analysis model, providing valuable insights into customer satisfaction and identifying actionable strategies to enhance their overall experience




Overview
========

Welcome to Astronomer! This project was generated after you ran 'astro dev init' using the Astronomer CLI. This readme describes the contents of the project, as well as how to run Apache Airflow on your local machine.

Project Contents
================

The Astro project for managing YouTube comments contains the following files and folders:

dags: This folder holds the Python files for your Airflow DAGs. By default, it includes one example DAG:

- etl.py: This DAG demonstrates a simple ETL pipeline that extracts comments from a specified YouTube video using the YouTube Data API and loads them into a PostgreSQL database. The DAG utilizes the TaskFlow API to define tasks in Python and employs dynamic task mapping to process comments efficiently. This serves as the foundation for automating the daily comment extraction process.
- Dockerfile: Contains a versioned Astro Runtime Docker image that enhances the Airflow experience. You can modify this file to execute additional commands or apply runtime overrides as needed.

- include: A folder for additional files you may need for your project. It is empty by default.

- packages.txt: Use this file to install any OS-level packages required for your project. It is empty by default.

- requirements.txt: Add Python packages required for your project here. It is empty by default.

 plugins: Add custom or community plugins for your project to this folder. It is empty by default.

- airflow_settings.yaml: A local-only file for specifying Airflow Connections, Variables, and Pools instead of entering them manually in the Airflow UI during development.
  
- Docker compose: for the connection of airflow and postgres 

Deploy Your Project Locally
===========================

1. Start Airflow locally: Run astro dev start to start Airflow on your machine. This command spins up four Docker containers for different Airflow components:

Postgres: Airflow's Metadata Database
Webserver: Renders the Airflow UI
Scheduler: Monitors and triggers tasks
Triggerer: Handles deferred task execution
Verify Docker containers: Run docker ps to ensure all four containers are created successfully.

Note: By default, astro dev start exposes the Airflow Webserver on port 8080 and Postgres on port 5432. If these ports are already in use, stop the conflicting Docker containers or modify the ports.

Access the Airflow UI: Open http://localhost:8080/ in your browser and log in with admin for both the username and password.

Access the Postgres database: Connect to the database at localhost:5432/postgres for managing the extracted YouTube comments.

