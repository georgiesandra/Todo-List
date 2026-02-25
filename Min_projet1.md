#Conception architecturale d'une application de gestion de taches
##1. Introduction

Notre projet consiste a concevoir une application de gestion de taches nommée Taskflow qui permettra à utilisateur d'organiser et de suivre ses taches quotidiennes.L'utilisateur pourra etre capable de créer , supprimer, ajouter, modifier , filtrer, rechercher, se connecter tout en gerant les priorités, les statuts et les notifications de ses différentes taches.


## 2.Objectifs

-Appliquer le principe d'architecture en couche
-Définir les API REST sécurisée
-Gérer Interface Responsive
-Gestion de la base de données
-Gestion de l'authentification de la sécuritée


## 3.Besoin fonctionnels
  
  ### Authentification 
-Création d'un compte pour accèder à l'application
-Connection pour accèder à mes taches
-Déconnexion sécurisée
-Protection des routes

 ### Gestion des taches
-création d'une taches pour organiser mon travail
-Vision global des taches sur mon espace
-Signaler une taches quand t'elle est deja terminer
-Modification d'une taches existante
-Suppresion d'une tache
-Définir les prioritée des taches
-Changer la prioritée des taches
-Mettre à jour les statut (dire si une tache a été terminée ou pas)
-je veux filtrer mes tâches par statut
-je veux rechercher une tâche par mot-clé
-je veux me déconnecter en toute sécurité
-Gestion des rappels et des notifications



## 4.Besoin non-fonctionnels

-Gestion de la performance et la réactivité
-Gestion de la disponibilité
-Gestion de la confidentialité
-Gestion de usuabilité
-Gestion de la scalabilité
-Gestion de la sécurité 
-Gestion de la fluidité des données



## 5.Contrainte techniques

-Avoir une architecture 3 tiers
-Respecter un modelèle client/Serveur
-Avoir un diagramme architectural
-Sécurité des sessions
-Coherence des données 
-La perfomance du système
-Accéssibilité au navigateur
-Versioning
-Gestion de l'architecture Client-Serveur 


## 6.Choix de la Stack techniques

Stack Python:
-Front-end: React.js
-Back-end: Node.js
-Base de données: MongoDB
-Authentification: JWT
-Communication:API REST
-Versioning: Git

## 7.Diagramme architectural 

Les différentes couches de notre diagramme:

-Front-end: Composants React modulaires, pages(login,dashboard,tasks), gestion de l'état global, communication HTTP avec l'API.

-Back-end: Configuration, Controleurs, services(logique métier), middleware(authentification,validation), gestions des erreurs, models, routes

-Base de données: Modèlisation de données, repositories, base de données relationnelle
   

## 8.Responsabilités de chaque composants

POur le frontend

-Affichage et rendu de l'interface utilisateur
-Gestion des interactions utilisateur (clics, saisies, navigation)
-Validation côté client (première ligne de défense)
-Gestion de l'état local de l'application
-Communication avec le back-end via des requêtes HTTP
-Optimisation des performances côté client

POur le backend


-Traitement de la logique métier complexe
-Authentification et autorisation des utilisateurs
-Validation rigoureuse des données (sécurité)
-Gestion des sessions et des tokens
-Communication avec la base de données
-Exposition d'APIs pour le front-end
-Gestion des erreurs et logging

Pour la base de données


-Stockage permanent des données
-Gestion des transactions (ACID)
-Maintien de l'intégrité référentielle
-Optimisation des requêtes et indexation
-Gestion de la concurrence d'accès
-Sauvegarde et récupération des données


## 9. Modélisation des données

Table: Users

|Champ     |Type        |Description             |
|------------------------------------------------|
|Id        |INT         |Identifiant Unique      |
|Email     |VARCHAR     |Email Unique            |
|Password_hash    |VARCHAR    |Mot de passe haché|
|Create_at    |DATE     |Date de création        |

Table: Tasks

|Champ        |Type        |Description                  |
|--------------------------------------------            |
|Id           |INT         |Identifiant Unique           |
|User_id      |INT (FK)    |Réference à l'utilisateur    |
|Title        |VARCHAR     |Titre de la tache            |
|Description  |TEXT        |Description                  |
|Priority     |Enum        |Low/medium/high              |
|Status       |Boolean     |Terminé ou non               |
|CReated_at    |DATE        |Date de création automatique |

## 10. Endpoints de l'API

|CRUD    | Méthode   | URL     | Action              |
|----------------------------------------------------|
|-       | POST      | /auth/register| Créer un compte|
|-       | POST      | /auth/login   | Se connecter
|-       | POST      | /auth/logout  | Se déconnecter
|CReate  | POST      | /tasks        | Créer une tache
|Read    | GET       | /tasks        | Lire toutes les taches
|Read    | GET       | /tasks/:id    | Lire une tache
|Read    | GET       | /tasks?status=| Filtrer par statut
|Read    | GET       | /tasks?search=| Rechercher par mot-clé
|Update  | PUT       | /tasks/:id    | Modifier une tache
|Delete  |DELETE     | /tasks/:id    | Supprimer une tache


## 11. Flux des données

L’utilisateur interagit avec l’interface | v
Le front-end envoie une requête HTTP | v L’API traite la requête | v
Les données sont enregistrées ou récupérées | v
Une réponse JSON est retournée | v
L’interface est mise à jour


## 12. Structure du projet

Voici un schéma logique démonstractif :

|--README.md
|--taskflow/
    |--backend/
        |--config/
        |--controllers/
        |--middleware/
        |--models/
        |--routes/
    |--frontend/
        |--src/
            |--components/
            |--pages/
            |--services/

Explication


- frontend/ : contient l’interface utilisateur développée avec React.

- components/ : regroupe les composants réutilisables.

- services/ : contient la gestion des appels API.

- pages/ : structure les différentes vues de l’application.

- backend/ : contient la logique serveur.

- controllers/ : gèrent le traitement des requêtes.

- models/ : représentent la structure des données.

- routes/ : définissent les endpoints REST.

- config/ : contient la configuration de la base de données.


## 13. Conclusion

Ce projet nous permettra de concevoir, de developper et de maintenir des applications complétes front-end / back-end , sécuritées, performance et l'évolution en s'appuyant sur une architure cohérente.





