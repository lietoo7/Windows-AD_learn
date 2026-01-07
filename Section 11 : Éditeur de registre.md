# Fiche Technique 11 : Éditeur de registre

L'Éditeur de registre (`regedit.exe`) est une base de données hiérarchique qui stocke toutes les configurations du système d'exploitation, des composants matériels et des applications logicielles. C'est le "cerveau" de Windows.

## 1. Structure du Registre (Les Ruches)

Le registre est organisé en cinq dossiers principaux appelés "Ruches" (Hives), chacun ayant un rôle spécifique :

* **HKEY_CLASSES_ROOT (HKCR) :** Gère les associations de fichiers (par exemple, quel logiciel ouvre un .pdf) et les objets COM/OLE.
* **HKEY_CURRENT_USER (HKCU) :** Contient la configuration de l'utilisateur actuellement connecté (fond d'écran, thèmes, paramètres de logiciels).
* **HKEY_LOCAL_MACHINE (HKLM) :** La ruche la plus importante. Elle stocke les paramètres globaux de la machine (configuration Windows, pilotes, sécurité), valables pour tous les utilisateurs.
* **HKEY_USERS (HKU) :** Contient les profils de tous les utilisateurs chargés sur la machine.
* **HKEY_CURRENT_CONFIG (HKCC) :** Stocke des informations sur le profil matériel utilisé au démarrage.

## 2. Clés et Valeurs

Le registre fonctionne comme un système de fichiers :

* **Clés :** Elles ressemblent à des dossiers.
* **Sous-clés :** Dossiers contenus dans d'autres dossiers.
* **Valeurs :** Ce sont les données réelles stockées. Il existe plusieurs types :
* **REG_SZ :** Une chaîne de caractères (texte).
* **REG_DWORD :** Un nombre entier (souvent 0 pour désactiver, 1 pour activer).
* **REG_BINARY :** Données binaires brutes.



## 3. Pourquoi modifier le registre ?

La modification du registre permet de personnaliser Windows au-delà de ce que propose l'interface graphique standard, par exemple :

* Désactiver des fonctionnalités système (ex: Cortana ou la télémétrie).
* Modifier le comportement de l'explorateur de fichiers.
* Réparer des erreurs logicielles complexes en supprimant des clés résiduelles.

## 4. Précautions de sécurité

La modification du registre comporte des risques. Une erreur peut empêcher le système de démarrer.

* **Sauvegarde :** Avant toute modification, il est impératif d'exporter la clé concernée (Fichier > Exporter) pour pouvoir la restaurer en cas de problème.
* **Points de restauration :** Créer un point de restauration système est une sécurité supplémentaire.
* **Précision :** Ne jamais supprimer ou modifier une valeur dont vous ne connaissez pas l'utilité exacte.
 
