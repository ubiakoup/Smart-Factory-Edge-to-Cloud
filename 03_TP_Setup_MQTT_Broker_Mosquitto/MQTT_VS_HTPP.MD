
#  MQTT vs HTTP — Guide clair (Application Layer - OSI)

---

## 1. Contexte : où se situent MQTT et HTTP ?

MQTT et HTTP sont deux protocoles de la **couche applicative (Layer 7)** du modèle OSI.

Ils reposent sur la même base réseau :

* **Layer 4 (Transport)** → TCP (communication fiable)
* **Layer 3 (Réseau)** → IP (routage des données)

👉 Donc :

```
Application → Transport → Réseau
MQTT / HTTP → TCP → IP
```

✔️ Même infrastructure réseau
❗ Mais logique de communication différente

---

##  2. Différence fondamentale de communication

###  HTTP → Request / Response

* Le client envoie une requête
* Le serveur répond
* Communication **synchrone**

👉 Exemple :

```
Client → GET /data
Serveur → JSON
```

❗ Nécessite souvent des requêtes répétées (polling)

---

###  MQTT → Publish / Subscribe

* Les clients publient des messages sur un **broker**
* Les abonnés reçoivent automatiquement les données
* Communication **asynchrone**

👉 Exemple :

```
Capteur → publish température
Broker → distribue aux abonnés
```

✔️ Découplé
✔️ Temps réel
✔️ Scalable

---

##  3. Comparaison rapide

| Critère       | MQTT                | HTTP               |
| ------------- | ------------------- | ------------------ |
| Modèle        | Publish / Subscribe | Request / Response |
| Communication | Asynchrone          | Synchrone          |
| Connexion     | Persistante         | Souvent courte     |
| Overhead      | Très faible         | Élevé              |

---

##  4. Structure d’un message : Header vs Payload

###  Définition

Un message réseau est composé de :

* **Header (en-tête)** → informations de contrôle
* **Payload (contenu)** → la donnée utile

---

###  Analogie simple

📦 Colis :

* **Header** = étiquette (adresse, instructions)
* **Payload** = contenu de la boîte

---

## 🌐 5. Exemple avec HTTP

```
POST /api/data HTTP/1.1
Host: example.com
Content-Type: application/json
Content-Length: 120
```

👉 Headers HTTP :

* verbeux
* textuels
* riches en métadonnées

✔️ Très flexible
❗ Mais lourd

---

## 6. Exemple avec MQTT

MQTT contient aussi des headers, mais :

* très **compacts**
* en **binaire**
* souvent **quelques bytes seulement**

👉 Informations typiques :

* type de message (publish, subscribe)
* longueur du message

✔️ Minimaliste → performant

---

## ⚡ 7. Pourquoi MQTT est plus léger ?

### MQTT

* Headers très petits (**~2 bytes minimum**)
* Protocole **binaire compact**
* Connexion **persistante**
* Communication **event-driven**

✅ Résultat :

* faible bande passante
* faible CPU
* faible consommation énergétique

---

### HTTP

* Headers **textuels et verbeux**
* Beaucoup de métadonnées (cookies, user-agent…)
* Requêtes fréquentes nécessaires

❗ Résultat :

* plus de trafic
* plus de latence
* plus de CPU

---

##  8. Focus important : le payload MQTT

👉 MQTT transporte simplement :

* un **topic** (canal de communication)
* un **payload** (suite de bytes)

---

###  Format du payload

MQTT **ne définit pas le format** des données.

✔️ Le payload peut être :

* JSON ✅ (le plus courant)
* binaire (Protobuf, CBOR…)
* texte
* image, etc.

---

### 📊 Exemple réel MQTT

**Topic**

```
factory/machine1/temperature
```

**Payload (JSON)**

```json
{
  "timestamp": "2026-03-26T10:15:00Z",
  "value": 22.5,
  "unit": "°C"
}
```

---

## 9. Pourquoi JSON est souvent utilisé ?

✔️ Avantages :

* lisible par humain
* facile à debug
* compatible avec tous les langages
* parfait pour Node-RED / Grafana / APIs

❗ Limites :

* plus lourd que binaire
* parsing plus coûteux

---

## 10. Fiabilité des échanges

### MQTT

* QoS 0 → au plus une fois
* QoS 1 → au moins une fois
* QoS 2 → exactement une fois

✔️ Fiabilité configurable

---

### HTTP

* Basé sur TCP
* Retry à gérer côté application

---

## 11. Cas d’usage

### MQTT

* IoT / IIoT
* capteurs industriels
* communication temps réel
* réseaux instables

---

### HTTP

* API REST
* applications web
* interfaces utilisateur
* intégration IT

---

##  12. Conclusion

> MQTT est un protocole léger, optimisé pour les communications IoT grâce à un modèle publish/subscribe, un overhead minimal et une connexion persistante.
> HTTP est un protocole universel, plus verbeux, basé sur un modèle requête/réponse, adapté aux applications web et aux APIs.

---

## À retenir

* Même base : **TCP/IP**
* MQTT → **léger, asynchrone, temps réel**
* HTTP → **standard, synchrone, web**
* MQTT transporte des **bytes**, souvent en **JSON**
