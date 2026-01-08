# Fiche Technique 1 : Le Système de Fichiers

Cette section détaille la manière dont Windows gère le stockage, l'organisation et la sécurité des données sur les supports physiques.

## 1. Les Permissions (NTFS)

Les permissions NTFS (New Technology File System) déterminent le niveau d'accès des utilisateurs aux fichiers et dossiers.

### **Permissions de base :**
* **Lecture :** Afficher le contenu du fichier ou du dossier.
* **Écriture :** Modifier le contenu ou créer de nouveaux fichiers.
* **Lecture et exécution :** Lancer des programmes (.exe, .bat) et lire le contenu.
* **Modification :** Lire, écrire et supprimer des fichiers/dossiers.
* **Contrôle total :** Tous les droits, y compris le changement des permissions pour autrui.
* **Héritage :** Par défaut, un sous-dossier hérite des permissions de son dossier parent.

## 2. Historique : HPFS, FAT16 et FAT32

Avant la généralisation du NTFS, d'autres systèmes étaient utilisés :

* **HPFS (High Performance File System) :** Créé pour l'OS/2, il a influencé Windows mais est aujourd'hui obsolète pour le grand public.
* **FAT16 :** Utilisé par MS-DOS. Limité à des partitions de 2 Go.
* **FAT32 :** * Ancien standard (Windows 95/98).
* **Limite majeure :** Ne peut pas stocker un fichier individuel de plus de 4 Go.
* Pas de gestion native des permissions de sécurité.



## 3. NTFS (New Technology File System)

Le système de fichiers moderne de Windows (depuis Windows NT). Ses avantages incluent :

* **Fiabilité :** Utilise la "journalisation" pour récupérer les données en cas de crash.
* **Sécurité :** Supporte les permissions granulaires par utilisateur.
* **Compression :** Possibilité de compresser des fichiers nativement pour gagner de l'espace.
* **Quotas :** Permet de limiter l'espace disque utilisé par chaque utilisateur.

## 4. ADS (Alternate Data Streams)

L'ADS est une fonctionnalité spécifique au NTFS souvent méconnue.

* **Définition :** Permet d'attacher des métadonnées ou des fichiers entiers à un fichier principal sans changer sa taille apparente dans l'explorateur.
* **Cas d'usage légitime :** Utilisé par Windows pour marquer un fichier comme "provenant d'Internet" (Zone.Identifier).
* **Risque de sécurité :** Des logiciels malveillants peuvent utiliser l'ADS pour cacher du code malveillant derrière un fichier texte ou image anodin.
* **Commande pour visualiser :** `dir /R` dans l'invite de commandes permet de voir les flux cachés.

