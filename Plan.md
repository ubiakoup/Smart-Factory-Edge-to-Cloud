# Smart Factory — Edge to Cloud

## Présentation

Cette formation a pour objectif de faire découvrir les principes de l’Industrie 4.0 à travers la mise en œuvre d’une architecture IIoT moderne allant de la couche OT jusqu’au Cloud.

Les participants construiront progressivement une plateforme industrielle capable de :

* collecter des données industrielles via OPC-UA ;
* transporter les données avec MQTT ;
* traiter et visualiser les données au niveau Edge ;
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

### TP01 — Mise en place de l’environnement

* Vagrant
* Infrastructure de laboratoire
* Machines virtuelles OT, Edge et Ansible

### TP02 — Simulation OT avec OPC-UA

* Simulation d’un PLC industriel
* Serveur OPC-UA
* Structure des données OPC-UA
* Visualisation avec UaExpert

---

## Jour 2 — Edge Computing & Monitoring Local

### TP03 — Déploiement de la plateforme Edge avec Docker Compose

Déploiement automatisé des services :

* MQTT Broker
* OPC-UA Data Collector
* Node-RED
* InfluxDB
* Grafana

### TP04 — Collecte et traitement des données industrielles

* OPC-UA Client
* MQTT
* Node-RED
* Traitement des flux temps réel

### TP05 — Stockage et visualisation des données

* InfluxDB
* Dashboards Grafana
* Monitoring industriel temps réel

---

## Jour 3 — Cloud Integration

### TP06 — Intégration Edge-to-Cloud avec AWS IoT Core

* MQTT Bridge
* AWS IoT Core
* Communication sécurisée Edge → Cloud

### TP07 — Stockage des données avec Amazon S3

* AWS IoT Rules
* Archivage des données industrielles
* Data Lake industriel

### TP08 — Traitement événementiel et notifications

* AWS Lambda
* Amazon SNS
* Notifications temps réel
* Cas d’usage de supervision industrielle

---

# Architecture cible

```text
PLC → OPC-UA → MQTT → Node-RED → InfluxDB → Grafana
                                      │
                                      ▼
                               AWS IoT Core
                                      │
                     ┌────────────────┴───────────────┐
                     ▼                                ▼
                   S3                           Lambda → SNS
```

---

# Technologies

* OPC-UA
* MQTT
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
