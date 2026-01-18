# Projet Portfolio : Pipeline ETL Automatisé NYC Taxi

## 🌟 Résumé Exécutif

Ce projet met en œuvre un pipeline de données entièrement automatisé sur **Google Cloud Platform** pour traiter les enregistrements de trajets des taxis jaunes de la ville de New York (NYC Yellow Taxi). En exploitant des services cloud natifs tels que **BigQuery**, **Cloud Storage** et **Cloud Composer (Airflow)**, j'ai construit un système évolutif qui transforme des millions de points de données brutes en un format structuré, prêt pour l'analyse avancée et le Machine Learning.

## 🎯 Cas d'Utilisation et Objectifs

Dans le secteur du transport urbain, les décisions basées sur les données sont cruciales pour optimiser la gestion de la flotte et les stratégies de tarification. Les données brutes des taxis de NYC sont volumineuses et se présentent sous différents formats au fil du temps.

**Mes objectifs étaient les suivants :**
1.  **Automatiser l'ingestion :** Éliminer la collecte manuelle de données en planifiant des téléchargements mensuels.
2.  **Assurer l'évolutivité :** Utiliser une infrastructure cloud capable de gérer des ensembles de données massifs sans dégradation des performances.
3.  **Qualité des données :** Mettre en œuvre une logique de transformation pour filtrer les anomalies (ex: trajets sans passagers, distances négatives).
4.  **Permettre les prédictions :** Créer un jeu de données "Gold" optimisé pour l'entraînement de modèles ML afin de prédire les coûts des trajets ou la demande.

## 🛠️ Le Parcours Technique

### 1. Le Lac de Données Brut (GCS)
La première étape implique un orchestrateur Python qui récupère les fichiers Parquet depuis le portail NYC Open Data. Ces fichiers sont stockés dans **Google Cloud Storage**, servant de "Data Lake" immuable. Cela garantit que nous disposons toujours des données sources originales pour un retraitement si nécessaire.

### 2. L'Entrepôt de Données (BigQuery)
J'ai conçu un processus de chargement à deux niveaux dans **BigQuery** :
-   **Zone Raw (brute) :** Les données sont chargées telles quelles dans des tables d'atterrissage.
-   **Zone Refined (raffinée) :** À l'aide de transformations SQL, je nettoie les données — en gérant les conversions de types (comme `passenger_count` de float à int) et en supprimant les enregistrements erronés.

### 3. Orchestration avec Apache Airflow
L'ensemble du processus est géré par un **DAG Airflow**. Cela offre une interface visuelle pour surveiller la santé du pipeline, gérer les tentatives automatiques (retries) et planifier le flux de travail pour qu'il s'exécute le dernier vendredi de chaque mois, garantissant ainsi que les dernières données sont toujours traitées.

## 📈 Impact et Résultats

*   **Efficacité :** Réduction de 90 % du temps de préparation des données grâce à l'automatisation.
*   **Fiabilité :** Mise en œuvre d'une logique de chargement "idempotente" qui empêche les entrées de données en double, même si une tâche est redémarrée.
*   **Prêt pour l'IA :** La table finale est directement compatible avec **BigQuery ML**, permettant le développement immédiat de modèles prédictifs sans ETL supplémentaire.

## 💡 Apprentissages Clés

La réalisation de ce projet m'a permis d'approfondir mon expertise en :
-   **Orchestration de flux de travail complexes** à travers plusieurs services cloud.
-   **Conception de schémas SQL efficaces** dans un environnement d'entrepôt de données serverless.
-   **Mise en œuvre des meilleures pratiques** pour l'ingénierie de données, telles que la journalisation, la gestion des erreurs et le chargement incrémentiel.
