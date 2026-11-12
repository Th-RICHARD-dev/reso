# Reso

## Présentation

Reso est une application web de réseau social (micro-blogging) développée en PHP natif et MariaDB. Elle permet la gestion des comptes utilisateurs, la publication de contenus et le suivi d'abonnements entre membres.

Ce dépôt est un **fork individuel** issu d'un projet de groupe initial [reso](https://github.com/SachaBouk/reso). Il a été réorganisé et maintenu pour faire évoluer l'architecture technique, la sécurité et les fonctionnalités.

## Stack Technique

- **Backend** : PHP 8.x
- **Base de données** : MariaDB
- **Dépendances** : Composer (`vlucas/phpdotenv` pour l'isolation des identifiants)
- **Frontend** : HTML5, CSS3

## Fonctionnalités

- **Authentification** : Inscription, connexion sécurisée et gestion des sessions PHP (`$_SESSION`).
- **Publications** : Création, enregistrement et affichage dynamique des messages.
- **Fil d'actualité** : Flux global trié par ordre antéchronologique.
- **Profils & Réseau** : Consultation des profils publics et système d'abonnements/suivis (relations followers/following).

## Structure du Projet

```text
reso/
├── authentification/   # Scripts de login, register et logout
├── contacts/           # Profils utilisateurs et gestion du suivi (follow)
├── messages/           # Traitement de la création des posts
├── images/             # Ressources graphiques statiques
├── vendor/             # Autoload et dépendances Composer
├── .env                # Variables d'environnement (accès BDD)
├── composer.json       # Configuration du projet et paquets PHP
├── db.php              # Singleton / Connexion centralisée MariaDB
├── index.php           # Point d'entrée principal (Feed)
├── style.css           # Centralisation des règles de style
└── README.md           # Documentation technique
```

## Composants Principaux

- `index.php` : Point d'entrée et agrégateur du fil d'actualité principal.
- `db.php` : Initialisation de la connexion BDD via `mysqli` et chargement des variables d'environnement (`.env`).
- `authentification/` : Traitement des données d'accès, validation et persistance de session.
- `contacts/` : Gestion des requêtes de profils et des tables de liaison d'abonnements.
- `messages/` : Enregistrement et sanitisation des publications soumises.
- `style.css` : Feuille de style globale centralisant l'ensemble de l'UI.

## 📄 Licence

Ce projet est un projet personnel créer pas [Thomas Richard](https://github.com/Th-RICHARD-dev). Tous droits réservés.
