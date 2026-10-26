# Electricity Forecasting

Projet de construction d’une application locale de prévision de consommation électrique avec un pipeline de données.

## Données et modèle prévus

Le dataset prévu est **ElectricityLoadDiagrams20112014**. Les données historiques seront rejouées pour simuler un flux.

Le premier modèle prévu est un **LSTM univarié sur le compteur MT_001**, utilisant une fenêtre de 96 mesures espacées de 15 minutes pour prévoir la mesure suivante, à un horizon de 15 minutes.

## Architecture envisagée

Un producteur Python rejouera les données historiques vers Kafka. Spark Structured Streaming traitera les événements, puis PostgreSQL stockera les données. Un service dédié assurera la prédiction, FastAPI exposera les données et les prévisions, et Streamlit fournira l’interface. Docker Compose permettra de lancer les services localement. L’entraînement hors ligne sera séparé de la prédiction dans l’application.

Technologies envisagées : **Python, TensorFlow/Keras, Kafka, Spark Structured Streaming, PostgreSQL, FastAPI, Streamlit et Docker Compose**.

## État actuel

Le projet est en cours d’initialisation. Aucune fonctionnalité n’est implémentée ; le modèle et l’architecture décrits ci-dessus sont prévus.
