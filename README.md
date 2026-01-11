# 🚕 Projet Data Engineering – Pipeline ETL Automatisé NYC Taxi (GCP)

## 📌 Présentation du projet

Ce projet met en œuvre un **pipeline ETL automatisé et scalable** sur **Google Cloud Platform (GCP)** pour traiter les données publiques des **taxis jaunes de New York (NYC Yellow Taxi)**.

L’objectif est de transformer des **données brutes volumineuses** en **données fiables, structurées et prêtes pour l’analyse, la BI et le Machine Learning**, en s’appuyant sur une **architecture moderne de type Modern Data Stack**.

---

## 🎯 Objectifs du projet

- ✅ Automatiser l’ingestion de données mensuelles
- ✅ Mettre en place une architecture cloud scalable
- ✅ Garantir la qualité et la fiabilité des données
- ✅ Structurer les données pour l’analytics et le Machine Learning
- ✅ Orchestrer l’ensemble du pipeline avec Apache Airflow

---

## 🏗️ Architecture du pipeline ETL

<p align="center">
  <img src="assets/architecture_etl_nyc_taxi.png" alt="Architecture Pipeline ETL NYC Taxi sur GCP" width="90%">
</p>

---

## 🔍 Lecture détaillée de l’architecture

### 1️⃣ Sources de données
- Données publiques issues de **NYC Open Data**
- Fichiers au format **Parquet**
- Données mises à jour mensuellement

---

### 2️⃣ Ingestion & Data Lake (Google Cloud Storage)
- Téléchargement automatisé des fichiers via **Python**
- Stockage dans **Google Cloud Storage**
- Zone **RAW / brute** servant de Data Lake immuable
- Possibilité de retraiter l’historique à tout moment

---

### 3️⃣ Orchestration – Apache Airflow (Cloud Composer)
- Orchestration complète du pipeline ETL
- Planification automatique mensuelle
- Gestion :
  - des dépendances
  - des erreurs
  - des retries
  - du monitoring
- Visualisation et supervision via l’UI Airflow

---

### 4️⃣ Entrepôt de données – Google BigQuery
- Chargement des données brutes dans des tables **RAW**
- Transformations SQL vers des tables **REFINED / GOLD**
- Nettoyage des données :
  - suppression des trajets invalides
  - contrôle des valeurs aberrantes
  - conversions de types
- Optimisation pour les requêtes analytiques

---

### 5️⃣ Analyse & valorisation des données
- Requêtes SQL analytiques dans BigQuery
- Données prêtes pour :
  - 📊 Business Intelligence
  - 📈 Reporting
  - 🤖 Machine Learning (BigQuery ML)
- Exploitation possible via des outils BI (Looker, Power BI…)

---

## 🛠️ Stack technique utilisée

### ☁️ Cloud & Data Platform
- Google Cloud Platform (GCP)
- Google Cloud Storage
- BigQuery
- Cloud Composer (Apache Airflow)

### ⚙️ Data Engineering
- Python
- SQL
- ETL / ELT
- Orchestration Airflow

### 📊 Analytics & BI
- BigQuery SQL
- Modélisation analytique
- Préparation de datasets pour BI & ML

---

## 📈 Résultats & impact

- 🚀 Automatisation complète du pipeline ETL
- ⏱️ Réduction significative du temps de préparation des données
- ✅ Données fiables et prêtes à l’analyse
- 📊 Architecture alignée avec les standards Modern Data Stack
- 🤖 Dataset directement exploitable pour le Machine Learning

---

## 💡 Apprentissages clés

Ce projet m’a permis de renforcer mes compétences en :

- Architecture data cloud
- Orchestration de pipelines complexes
- Modélisation analytique dans BigQuery
- Bonnes pratiques Data Engineering (idempotence, monitoring, qualité)
- Approche data-driven orientée business

---

## 🚀 Pistes d’amélioration

- 🔍 Ajout de contrôles qualité avancés (Great Expectations)
- 📊 Connexion à un outil BI (Looker studio)
- 🔁 Mise en place d’un CI/CD pour les DAGs Airflow
- 🤖 Implémentation de modèles prédictifs avec BigQuery ML

---

## 👤 Auteur

**Nicodème**  
📍 Paris, France  
📧 nicodememoulonga@gmail.com  
🔗 GitHub : https://github.com/kyser131997

---

⭐ **N’hésitez pas à mettre une étoile au projet si vous le trouvez pertinent !**
