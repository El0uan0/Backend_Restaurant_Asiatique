# Borne de Commande - Backend API

Ce dépôt contient le code source de l'API REST (Backend) pour le projet de borne de commande de restauration asiatique.
Il est développé en Java avec le framework Javalin.

## Auteurs (Groupe)
- Icham OULALI
- Pierre Michel NDENGUE BOUNOUNOU
- Ouday GDIRI
- Elouan QUENTEL

## Prérequis
- Java 17 (JDK)
- Maven 3.x
- Docker & Docker Compose (pour la base de données)

## Installation et Lancement

### 1. Cloner le projet
```bash
git clone <URL_DU_REPO_BACKEND>
cd Backend_Restaurant_Asiatique
```

### 2. Lancer la base de données (Docker)
Le projet utilise MySQL. Vous pouvez lancer la base de données via Docker :
```bash
docker-compose up -d mysqldb
```
*Note : Le script d'initialisation se trouve dans `src/main/resources/init.sql`.*

### 3. Compiler et lancer le serveur
Utilisez Maven pour démarrer l'API :
```bash
mvn clean install
mvn exec:java -Dexec.mainClass="org.example.Main"
```
Une fois lancé, le serveur sera accessible sur `http://localhost:7000`.

## Endpoints
- `GET /api/categories` : Liste toutes les catégories.
- `GET /api/products` : Liste tous les produits (peut être filtré par `?category=ID`).
- `POST /api/orders` : Crée une nouvelle commande.
- `GET /api/orders/{id}` : Récupère les détails d'une commande.

## Architecture
- **Framework Web** : Javalin
- **SGBD** : MySQL 8.0 (Dockerisé)
- **Outil de Build** : Maven

## Modélisation
L'archive de la modélisation Modelio (`ABCD_design.zip`) se trouve à la racine de ce dépôt (conformément à REQ-LIV-003).