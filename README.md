# ⚓ Bataille Navale - PHP & MySQL (Architecture Nginx)

### 📋 Présentation du projet
[cite_start]Ce projet consiste en une reproduction du célèbre jeu de la **Bataille Navale**, développée entièrement en **PHP 8.2** avec une gestion de données via **MySQL**[cite: 30, 31]. [cite_start]L'objectif était de concevoir un système de jeu fonctionnel et robuste en se concentrant exclusivement sur la logique serveur (Back-end), sans l'utilisation de JavaScript[cite: 30].

> [cite_start]**Note :** Ce projet a été réalisé en binôme dans le cadre de ma formation au sein de l'école **CODA**[cite: 10, 30].

---

### 🛠️ Caractéristiques techniques
* [cite_start]**Serveur Web :** Nginx (configuré pour PHP-FPM).
* [cite_start]**Langage :** PHP 8.2.
* [cite_start]**Base de données :** MySQL / SQL[cite: 30, 31, 39].
* [cite_start]**Front-end :** HTML5 et CSS3 (Design responsive)[cite: 35].
* [cite_start]**Environnement :** Linux[cite: 43].

---

### 🎮 Fonctionnalités
* [cite_start]**Gestion du plateau :** Grille interactive générée dynamiquement via PHP[cite: 30].
* [cite_start]**Logique de jeu :** Système de tir avec vérification en temps réel (Touché, Coulé, À l'eau)[cite: 30].
* [cite_start]**Persistance des données :** Sauvegarde de l'état des navires et de l'historique des tirs dans MySQL[cite: 30, 31].
* **Zéro JavaScript :** Toute l'interactivité est gérée par des requêtes HTTP et des sessions PHP.

---

### 🚀 Installation et Configuration

#### 1. Cloner le repository
```llgit clone [https://github.com/ton-username/bataille-navale.git](https://github.com/ton-username/bataille-navale.git)```
```cd bataille-navale```

#### 2. Configuration de la base de données

Importez le schéma SQL fourni dans votre instance MySQL :

```CREATE DATABASE bataille_navale;```
```USE bataille_navale;```
-- Importez ici votre fichier .sql
```SOURCE database.sql;```

3. Configuration de Nginx

Pour faire fonctionner ce projet sous Nginx avec PHP 8.2, utilisez la configuration suivante:
Nginx

```server {```
    ```listen 80;```
    ```server_name localhost;```
    ```root /var/www/bataille-navale;```
    ```index index.php;```

    ```location / {```
       ``` try_files $uri $uri/ =404;```
   ``` }```

    ```location ~ \.php$ {```
        ```include snippets/fastcgi-php.conf;```
        ```fastcgi_pass unix:/var/run/php/php8.2-fpm.sock;```
    ```}```
```}```

👥 Collaboration (Travail en binôme)

Le développement en binôme a été une opportunité de mettre en pratique des méthodes de travail collaboratives:

    Répartition des tâches : Conception du Modèle Conceptuel de Données (MCD) et développement des algorithmes de tir.

    Gestion de version : Utilisation de Git et GitHub pour la fusion des fonctionnalités et le suivi des modifications.
