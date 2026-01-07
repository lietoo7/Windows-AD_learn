# Fiche Technique 3 : Comptes utilisateurs, profils et permissions

Cette section traite de la gestion de l'identité des utilisateurs sur une machine locale et de la manière dont leurs données et privilèges sont structurés.

## 1. Types de comptes : Administrateur vs Utilisateur standard

Windows distingue principalement deux types de comptes pour garantir la sécurité du système :

* **Utilisateur Standard :** * Peut utiliser la plupart des logiciels et modifier les paramètres qui n'affectent que son propre profil.
* Ne peut pas installer de logiciels impactant le système global ni modifier les fichiers système ou les paramètres de sécurité.


* **Administrateur :** * Possède un contrôle total sur l'ordinateur.
* Peut installer des applications, modifier le registre, gérer les autres comptes et accéder à tous les fichiers de la machine.


* **Système (SYSTEM) :** Un compte invisible encore plus puissant que l'administrateur, utilisé par Windows lui-même pour gérer les processus de bas niveau.

## 2. Création, Modification et Suppression

La gestion des comptes peut s'effectuer via l'application **Paramètres** ou la console **netplwiz** (plus avancée).

* **Création :** Lors de la création, Windows demande s'il s'agit d'un compte local ou d'un compte Microsoft (lié au cloud).
* **Modification :** Permet de changer le mot de passe, de modifier le type de compte (passer de Standard à Administrateur) ou de changer l'image de profil.
* **Suppression :** Lors de la suppression, Windows propose de conserver ou de supprimer les fichiers personnels de l'utilisateur (documents, bureau, etc.).

## 3. Profils Utilisateurs (C:\Users)

Lorsqu'un utilisateur se connecte pour la première fois, Windows crée un **Profil**.

* **Emplacement :** `C:\Users\[NomUtilisateur]`.
* **Structure du profil :** Contient les dossiers personnels (Documents, Images, Téléchargements) et le dossier caché `AppData` qui stocke les paramètres spécifiques aux applications.
* **NTUSER.DAT :** Un fichier caché crucial dans chaque profil. Il contient les paramètres de registre spécifiques à l'utilisateur (HKEY_CURRENT_USER). Si ce fichier est supprimé ou corrompu, le profil ne pourra pas se charger correctement.

## 4. Permissions sur les profils

Par défaut, Windows applique une isolation stricte :

* Un utilisateur standard ne peut pas ouvrir le dossier d'un autre utilisateur.
* Seul un Administrateur peut forcer l'accès au profil d'un tiers après avoir accepté un avertissement de sécurité.
 
