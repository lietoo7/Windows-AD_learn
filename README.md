# Windows Fundamentals

Ce dépôt est un guide complet dédié aux fondamentaux du système d'exploitation Windows. Il couvre les concepts essentiels allant de la gestion du système de fichiers aux outils d'administration avancés.

## Sommaire

1. [Le système de fichiers]( )
2. [Dossiers Windows et System32]( )
3. [Comptes utilisateurs, profils et permissions]( )
4. [UAC (Contrôle de compte d'utilisateur)]( )
5. [Paramètres et Panneau de configuration]( )
6. [Gestionnaire des tâches]( )
7. [Gestion de l'ordinateur (compmgmt)]( )
8. [Informations système]( )
9. [Moniteur de ressources (resmon)]( )
10. [Invite de commandes (CMD)]( )
11. [Éditeur de registre]( )

---

## 1. Le système de fichiers

Étude de la manière dont Windows organise et sécurise les données sur le disque.

* **Permissions :** Introduction aux droits d'accès (Lecture, Écriture, Modification, Contrôle total).
* **HPFS, FAT16 et FAT32 :** Historique et limites des anciens systèmes de fichiers.
* **NTFS :** Caractéristiques principales (journalisation, compression, sécurité native).
* **ADS (Alternate Data Streams) :** Technique permettant de rattacher des données cachées à un fichier.

## 2. Dossiers Windows et System32

* **C:\Windows :** Répertoire principal de l'installation du système.
* **System32 :** Analyse du dossier critique contenant les bibliothèques (DLL) et les exécutables système.
* **Variables d'environnement :** Utilisation de %windir% pour accéder au dossier système quel que soit le nom du lecteur.

## 3. Comptes utilisateurs, profils et permissions

* **Types de comptes :** Différences entre l'Administrateur et l'Utilisateur standard.
* **Gestion des comptes :** Procédures de création, de modification et de suppression.
* **Profils :** Structure du dossier C:\Users et stockage des données spécifiques à l'utilisateur.

## 4. UAC (Contrôle de compte d'utilisateur)

* **Les bases :** Comprendre le rôle de l'UAC dans la prévention des modifications non autorisées.
* **Paramètres UAC :** Comment modifier les niveaux de notification pour équilibrer sécurité et confort.

## 5. Paramètres et Panneau de configuration

* **System Configuration :** Utilisation des outils de configuration de base.
* **Configuration avancée :** Accès aux propriétés système avancées (performances, protection du système).

## 6. Gestionnaire des tâches

Surveillance en temps réel des processus, de l'utilisation des ressources et de la gestion des applications au démarrage.

## 7. Gestion de l'ordinateur (compmgmt)

Présentation de la console centralisée regroupant le gestionnaire de disques, l'observateur d'événements et la gestion des dossiers partagés.

## 8. Informations système

* **msinfo32 :** Consultation détaillée des composants matériels et logiciels.
* **Variables d'environnement :** Configuration et rôle des variables système et utilisateur.

## 9. Moniteur de ressources (resmon)

Analyse approfondie de la consommation du processeur, de la mémoire, du disque et du réseau par processus.

## 10. Invite de commandes (CMD)

Utilisation des commandes essentielles pour l'administration, le diagnostic réseau et la gestion des fichiers.

## 11. Éditeur de registre

* **Clés de registre :** Comprendre la structure des ruches (HKEY_LOCAL_MACHINE, HKEY_CURRENT_USER).
* **Précautions :** Importance de la sauvegarde et risques liés à la modification du registre.

 
