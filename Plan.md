# Smart Factory — Edge to Cloud

## Présentation

Cette formation a pour objectif de faire découvrir les principes de l’Industrie 4.0 à travers la mise en œuvre d’une architecture IIoT moderne allant de la couche OT jusqu’au Cloud.

Les participants construiront progressivement une plateforme industrielle capable de :

* collecter des données industrielles via OPC-UA ;
* transporter les données avec MQTT ;
* traiter les données au niveau Edge ;
* stocker et visualiser les données industrielles ;
* intégrer les données dans le Cloud AWS ;
* mettre en œuvre des mécanismes de stockage, de traitement et de notification.

---

# Objectifs pédagogiques

À l'issue de cette formation, les participants seront capables de :

* Comprendre l’Industrie 4.0 et le rôle de l’intégration IT/OT ;
* Comprendre l’architecture d’une plateforme IIoT moderne (OT, Edge et Cloud) ;
* Comprendre les protocoles industriels OPC UA et MQTT ;
* Mettre en place une chaîne de collecte, traitement et visualisation des données industrielles ;
* Utiliser Node-RED pour l’intégration et l’orchestration des flux de données ;
* Déployer des services avec Docker et Docker Compose ;
* Mettre en place une intégration Edge-to-Cloud avec AWS IoT Core ;
* Stocker, traiter et notifier les événements industriels dans le Cloud AWS.

---

# Programme

## Jour 1 — Fondations IIoT & Couche OT

### TP00 — Découverte de l’architecture Smart Factory

* Architecture Edge-to-Cloud
* Intégration IT/OT
* Flux de données industriels
* Technologies utilisées

### TP01 — Mise en place de l’environnement

* Vagrant
* Infrastructure de laboratoire
* Machines virtuelles OT, Edge et Ansible
* Réseau et dossiers synchronisés

### TP02 — Simulation OT avec OPC-UA

* Simulation d’un PLC industriel
* Architecture OPC-UA
* Structure des données industrielles
* NodeIds et Address Space
* Visualisation avec UaExpert

---

## Jour 2 — Edge Computing & Monitoring Local

### TP03 — Déploiement du microservice MQTT Broker (Mosquitto)

* Architecture Publish / Subscribe
* Topics MQTT
* Déploiement du broker MQTT avec Docker
* Validation des échanges MQTT

### TP04 — Développement et déploiement du Data Collector

* OPC-UA Client
* Collecte des données industrielles
* Publication MQTT
* Dockerfile
* Construction de l’image Docker
* Déploiement du microservice

### TP05 — Déploiement du microservice Node-RED

* Traitement des flux MQTT
* Découverte de Node-RED
* Création des premiers flows industriels

### TP06 — Déploiement du microservice InfluxDB

* Base de données Time-Series
* Buckets et organisation des données
* Stockage des données industrielles

### TP07 — Déploiement du microservice Grafana

* Connexion à InfluxDB
* Création des dashboards
* Monitoring industriel temps réel

### TP08 — Intégration Node-RED & InfluxDB

* Transformation des données
* Injection des données dans InfluxDB
* Validation du pipeline Edge

### TP09 — Alerting & Monitoring industriel

* Alarmes Grafana
* Détection d’anomalies
* Notifications de supervision

### TP10 — Automatisation de la plateforme avec Docker Compose

* Infrastructure as Code
* Docker Compose
* Déploiement automatisé de la plateforme Edge complète

---

## Jour 3 — Cloud Integration

### TP11 — Intégration Edge-to-Cloud avec AWS IoT Core & Amazon S3

* MQTT Bridge
* AWS IoT Core
* AWS IoT Rules
* Stockage des données dans Amazon S3
* Data Lake industriel

### TP12 — Traitement événementiel avec AWS Lambda & Amazon SNS

* Déclenchement automatique avec Lambda
* Notifications industrielles avec SNS
* Cas d’usage de supervision
* Validation de l’architecture Edge-to-Cloud

---

# Architecture cible

```text
PLC → OPC-UA → MQTT → Data Collector → Node-RED → InfluxDB → Grafana
                                                        │
                                                        ▼
                                                 AWS IoT Core
                                                        │
                            ┌───────────────────────────┴──────────────────────────┐
                            ▼                                                      ▼
                        Amazon S3                                           AWS Lambda
                                                                                  │
                                                                                  ▼
                                                                            Amazon SNS
```

---

# Technologies

* OPC-UA
* MQTT
* Mosquitto
* Node-RED
* Docker
* Docker Compose
* InfluxDB
* Grafana
* AWS IoT Core
* AWS Lambda
* Amazon S3
* Amazon SNS

---

# Public visé

* Ingénieurs IT / OT
* DevOps Engineers
* Cloud Engineers
* Automaticiens
* Intégrateurs industriels
* Étudiants souhaitant découvrir l’Industrie 4.0
