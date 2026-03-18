# Fiche Technique 10 : Invite de commandes (CMD)

L'invite de commandes (`cmd.exe`) est l'interface textuelle historique de Windows. Elle permet d'exécuter des tâches administratives, d'automatiser des processus via des scripts (.bat) et d'accéder à des outils de diagnostic non disponibles dans l'interface graphique.

## 1. Principes de base

* **Mode Utilisateur vs Mode Administrateur :** Certaines commandes (comme la réparation système ou la modification du réseau) nécessitent d'être lancées en tant qu'administrateur pour fonctionner.
* **Navigation :**
* `cd` (Change Directory) : Pour se déplacer dans les dossiers.
* `dir` : Pour lister les fichiers et dossiers d'un répertoire.
* `cls` : Pour effacer l'écran.



## 2. Commandes de gestion du système et des fichiers

* **sfc /scannow :** (System File Checker) Vérifie l'intégrité des fichiers système et répare ceux qui sont corrompus.
* **chkdsk :** Analyse le disque dur à la recherche d'erreurs logiques ou de secteurs défectueux.
* **tasklist / taskkill :** Permet d'afficher les processus en cours et de forcer l'arrêt d'un programme via son nom ou son PID.
* **shutdown /s /t 0 :** Éteint l'ordinateur immédiatement.

## 3. Commandes réseau essentielles

L'invite de commandes est l'outil privilégié pour diagnostiquer les problèmes de connexion.

* **ipconfig :** Affiche la configuration IP de la machine (adresse locale, masque de sous-réseau, passerelle).
* **ping [adresse] :** Vérifie la connectivité avec une autre machine ou un site web.
* **tracert [adresse] :** Affiche le chemin parcouru par les paquets de données pour atteindre une destination.
* **netstat :** Affiche toutes les connexions réseau actives et les ports ouverts sur l'ordinateur.

## 4. Gestion des droits et réseaux locaux

* **net user :** Permet de lister, créer ou modifier les mots de passe des utilisateurs locaux.
* **net share :** Affiche et gère les partages de dossiers sur le réseau.

## 5. Astuces d'utilisation

* **Auto-complétion :** Appuyez sur la touche `Tab` pour compléter automatiquement le nom d'un fichier ou d'un dossier.
* **Historique :** Les flèches `Haut` et `Bas` permettent de naviguer dans les commandes précédemment tapées.
* **Redirection :** Utiliser `>` pour envoyer le résultat d'une commande dans un fichier texte (ex: `systeminfo > infos.txt`).
 
