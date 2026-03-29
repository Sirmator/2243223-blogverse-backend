# BlogVerse Backend

API backend NestJS pour la plateforme de blogging BlogVerse. Ce backend gère l'authentification des utilisateurs, la gestion des articles et les services de profil utilisateur.

## Prérequis

Avant d'exécuter le projet, assurez-vous d'avoir installé les éléments suivants :

- **Node.js** (v18 ou supérieure)
- **npm** (v9 ou supérieure)
- **MySQL** (v5.7 ou supérieure) - Doit être en cours d'exécution et accessible

## Installation

1. **Installer les dépendances :**
   ```bash
   npm install
   ```

2. **Configurer les variables d'environnement :**
   - Copiez le fichier `.env.example` vers `.env` :
     ```bash
     cp .env.example .env
     ```
   - Mettez à jour le fichier `.env` avec votre configuration :
     ```
     PORT=3001
     DB_HOST=localhost
     DB_USERNAME=blog_user
     DB_PASSWORD=secret
     DB_PORT=3306
     DB_NAME=blog_app
     DATABASE_URL=localhost:3306
     ```

3. **Créer la base de données MySQL :**
   - Assurez-vous que votre serveur MySQL est en cours d'exécution
   - Créez un utilisateur de base de données avec les identifiants spécifiés dans votre fichier `.env`
   - Exécutez les migrations de base de données si nécessaire

## Exécution de l'Application

### Mode Développement
```bash
npm run start:dev
```
Exécute l'application en mode watch. Tous les changements dans les fichiers source relanceront automatiquement le serveur.

### Mode Production
D'abord, construisez le projet :
```bash
npm run build
```

Puis démarrez le serveur de production :
```bash
npm run start:prod
```

### Mode Débogage
```bash
npm run start:debug
```
Exécute l'application en mode débogage avec watch activé. Vous permet d'attacher un débogueur.

### Démarrage Standard
```bash
npm run start
```
Exécute l'application une seule fois sans mode watch.

## Autres Commandes Disponibles

- **Linting :**
  ```bash
  npm run lint
  ```
  Vérifie et corrige les problèmes de style de code en utilisant ESLint.

- **Formatage :**
  ```bash
  npm run format
  ```
  Formate le code en utilisant Prettier.

- **Tests :**
  ```bash
  npm run test          # Exécute les tests une seule fois
  npm run test:watch   # Exécute les tests en mode watch
  npm run test:cov     # Exécute les tests avec un rapport de couverture
  npm run test:e2e     # Exécute les tests de bout en bout
  ```

## Structure du Projet

```
src/
├── auth/              # Module d'authentification
├── guard/             # Gardes de routes
├── models/            # Modèles de données
├── post/              # Module de gestion des articles
├── user/              # Module de gestion des utilisateurs
├── utils/             # Fonctions utilitaires et configuration de la base de données
├── app.module.ts      # Module principal de l'application
├── app.service.ts     # Service principal de l'application
└── main.ts            # Point d'entrée de l'application
```

## Points d'Accès API

Le backend fournit les modules principaux suivants :

- **Auth** : Connexion et enregistrement des utilisateurs
- **User** : Gestion du profil utilisateur
- **Post** : Créer, lire et mettre à jour les articles de blog

## Dépannage

- **Erreur de connexion à la base de données** : Assurez-vous que MySQL est en cours d'exécution et que les identifiants dans `.env` sont corrects
- **Port déjà utilisé** : Modifiez le `PORT` dans votre fichier `.env`
- **Problèmes de dépendances** : Essayez de supprimer `node_modules` et exécutez `npm install` à nouveau
