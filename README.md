# datalake_fasterize
Ce projet contient un pipeline ETL orchestré par Apache Airflow.
Le pipeline extrait des données depuis deux bases PostgreSQL, réalise des transformations, puis écrit les résultats sur un bucket AWS S3 au format Parquet partitionné par date.

datalake_fasterize/
├── airflow/                 # Dossier Airflow (config & dags)
│   └── dags/
│       └── users_orders_dag.py   # DAG Airflow
├── etl/
│   ├── __init__.py
│   └── etl.py               # Fonctions d'extraction, transformation, chargement
├── requirements.txt         # Dépendances Python
└── README.md

# Composants du projet 

Python 3.10

PostgreSQL accessible avec les accès dans etl/etl.py

AWS S3 avec clé d’accès et secret pour écrire dans un bucket

Apache Airflow 

Virtualenv pour isoler l’environnement

# Instalation du projet 

python -m venv env
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows

pip install --upgrade pip
pip install -r requirements.txt

# Configuration d’Airflow

Se place à la racine du projet, puis exécuter ces commandes:

- export AIRFLOW_HOME=$(pwd)/airflow   # Linux/macOS
- set AIRFLOW_HOME=%cd%\airflow  
- airflow db migrate 
- airflow standalone



