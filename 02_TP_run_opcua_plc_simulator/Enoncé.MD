# TP 2 — Simulation OT avec OPC-UA (dans la stack Vagrant)

## Objectifs pédagogiques

À la fin de ce TP, vous serez capable de :

- Se connecter à une machine virtuelle via SSH  
- Naviguer dans un environnement Linux  
- Créer et utiliser un environnement virtuel Python  
- Installer des dépendances avec un fichier requirements.txt  
- Comprendre le rôle d’un serveur OPC-UA  
- Lancer un simulateur de PLC  

---

## Contexte

Dans notre architecture IIoT, la couche OT (Operational Technology) représente les machines physiques (capteurs, automates, PLC).

Dans notre cas, nous utilisons Vagrant pour créer nos différents environnements:

- un serveur Ansible  nommé iot-ansible
- un serveur OPC UA / PLC (simulation)  nommé iot-opcua-plc-simulator
- un serveur Edge  nommé iot-edge

Dans ce TP, nous allons travailler sur le serveur iot-opcua-plc-simulator pour simuler notre couche OT.

---

## Informations réseau

Serveur OPC UA / PLC :

IP : 192.168.56.11

---

## Accès à la machine OPC UA

### Méthode 1 — Terminal (recommandé)

```bash
cd iot_stack_ubuntu22
vagrant ssh iot-opcua-plc-simulator
````

### Méthode 2 — SSH direct (MobaXterm / Terminal)

```bash
ssh vagrant@192.168.56.11
```

Clé privée à utiliser :

.vagrant/machines/iot-opcua-plc-simulator/virtualbox/private_key

---

## Accès au projet

```bash
cd /home/vagrant/projects
ls
```

---

## Étapes

### 1. Vérifier Python

```bash
python3 --version
```

### 2. Vérifier pip
```bash
sudo apt install python3.10-venv
```

```bash
python3 -m pip --version
```

### 3. Créer un environnement virtuel

```bash
python3 -m venv venv
```

### 4. Activer l’environnement virtuel

```bash
source venv/bin/activate
```

### 5. Créer le fichier requirements.txt

```bash
nano requirements.txt
```

Contenu du fichier :

```txt
opcua
cryptography
```

### 6. Installer les dépendances

```bash
python3 -m pip install --upgrade pip
python3 -m pip install -r requirements.txt
```

### 7. Vérifier les installations

```bash
python3 -m pip list
```

### 8. Lancer le simulateur OPC-UA

```bash
python3 opcua_plc_simulation.py
```

---
## Résultat attendu

* Connexion SSH fonctionnelle
* Environnement Python opérationnel
* Dépendances installées
* Serveur OPC-UA lancé

---
## Exercice 1

### Pourquoi utilise-t-on un environnement virtuel ?
---
## Exercice 2

### Quel est le rôle de la bibliothèque OPC-UA ?
---
## Exercice 3

### Que représente le simulateur PLC ?
---
## Exercice 4

### Pourquoi simuler un environnement OT ?
---



## Bonnes pratiques

* Toujours utiliser un environnement virtuel
* Ne jamais installer les dépendances globalement
* Utiliser python3 -m pip
* Travailler dans /home/vagrant/projects

---

## En cas d’erreur

```bash
rm -rf venv
```

Puis recommencer les étapes.

---

Vous venez de simuler un environnement OT industriel.

```
```
