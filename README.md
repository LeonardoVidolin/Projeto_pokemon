# Projeto_pokemon
Pokemon Data Engineering Project

Project Overview
This project demonstrates the use of data engineering tools and techniques to extract, transform, and load (ETL) data from the PokeAPI, a popular API for accessing Pokemon data. The primary goal is to showcase proficiency in Python for coding, Apache Airflow for orchestration, and database management for data storage.

Table of Contents
- Project Overview
- Features
- Architecture
- Technologies Used
- Setup and Installation
- Usage
- Project Structure
- Contributing

Features
- Data Extraction: Extracts Pokemon data from the PokeAPI.
- Data Transformation: Cleans and transforms the data into a structured format.
- Data Loading: Loads the transformed data into a local database, simulating a data warehouse environment.
- Orchestration: Uses Apache Airflow to manage and schedule ETL workflows.

Architecture
- Extract: Fetches data from the PokeAPI.
- Transform: Processes the raw data to extract relevant fields and structure it.
- Load: Inserts the transformed data into a local SQL database.
- Orchestration: Airflow DAGs manage the scheduling and execution of the ETL processes.

Technologies Used
- Python: For scripting and data processing.
- Apache Airflow: For workflow orchestration.
- PokeAPI: The source of the Pokemon data.
- SQLite: Local database for storing the transformed data.
- Docker: Containerization for easy setup and deployment.

Setup and Installation
1) Clone the Repository:

git clone https://github.com/yourusername/pokemon-data-engineering.git
cd pokemon-data-engineering

2) Set Up Virtual Environment:

python3 -m venv venv
source venv/bin/activate


3) Install Dependencies:

pip install -r requirements.txt

4) Start Docker Containers:

Ensure you have Docker installed and running. Then, start the Airflow and database containers:
docker-compose up -d

5) Initialize Airflow:

docker-compose run airflow-webserver airflow db init
docker-compose run airflow-webserver airflow users create --username admin --password admin --firstname admin --lastname admin --role Admin --email admin@example.com

Usage
1) Access Airflow UI:
Open your browser and go to http://localhost:8080 to access the Airflow web interface. Log in with the credentials you created during setup.

2) Trigger the ETL Pipeline:
In the Airflow UI, you will find the DAG named pokemon_etl. Trigger this DAG to start the ETL process.

3) Verify Data Load:
Connect to the SQLite database to verify that the Pokemon data has been loaded correctly.
sqlite3 pokemon.db


Project Structure

pokemon-data-engineering/
├── dags/
│   └── pokemon_etl_dag.py
├── scripts/
│   ├── extract.py
│   ├── transform.py
│   └── load.py
├── config/
│   └── airflow.cfg
├── docker-compose.yml
├── requirements.txt
├── README.md
└── .env.example
- dags/: Contains Airflow DAG definitions.
- scripts/: Contains the Python scripts for extraction, transformation, and loading.
- config/: Configuration files for Airflow.
- docker-compose.yml: Docker Compose file to set up Airflow and the database.
- requirements.txt: List of Python dependencies.
- .env.example: Example environment file.

Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.