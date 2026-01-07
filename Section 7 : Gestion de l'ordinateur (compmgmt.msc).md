# Fiche Technique 7 : Gestion de l'ordinateur

La console **Gestion de l'ordinateur** est une interface MMC (Microsoft Management Console) qui regroupe plusieurs outils d'administration en une seule fenêtre. Elle est accessible via un clic droit sur le bouton Démarrer ou en tapant `compmgmt.msc`.

## 1. Outils système

Cette partie permet de surveiller l'état de santé et les événements du système.

* **Observateur d'événements :** Le journal de bord de Windows. Il enregistre tout : erreurs matérielles, tentatives de connexion échouées, mises à jour réussies. C'est le premier endroit où regarder en cas de panne (BSOD).
* **Dossiers partagés :** Permet de voir quels dossiers de votre machine sont accessibles sur le réseau, qui y est connecté actuellement et quels fichiers sont ouverts à distance.
* **Utilisateurs et groupes locaux :** Un outil puissant pour gérer les comptes (création, réinitialisation de mot de passe) et surtout pour gérer les **Groupes** (ex: ajouter un utilisateur au groupe "Administrateurs" ou "Utilisateurs du Bureau à distance").

## 2. Stockage (Gestion des disques)

C'est l'un des composants les plus utilisés de cette console.

* **Initialisation :** Préparer un nouveau disque dur pour Windows.
* **Partitionnement :** Réduire un volume pour en créer un nouveau, ou étendre une partition existante.
* **Formatage :** Choisir le système de fichiers (NTFS, exFAT) et effacer les données.
* **Lettres de lecteur :** Modifier la lettre attribuée à un disque (ex: changer D: en E:).

## 3. Services et applications

* **Services :** Permet de gérer les programmes qui tournent en arrière-plan sans interface utilisateur. On peut configurer leur mode de démarrage :
* **Automatique :** Se lance au démarrage de Windows.
* **Manuel :** Se lance uniquement si une application en a besoin.
* **Désactivé :** Le service ne peut pas être lancé, ce qui peut renforcer la sécurité ou économiser des ressources.


* **Contrôle WMI :** Outil avancé pour configurer les propriétés de l'infrastructure de gestion Windows.

## 4. Gestionnaire de périphériques

Bien qu'accessible séparément, il est intégré ici pour :

* Mettre à jour les pilotes (drivers).
* Identifier les composants non reconnus (marqués d'un point d'exclamation jaune).
* Désactiver un composant matériel défectueux.
 
