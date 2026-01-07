# Fiche Technique 4 : User Account Control (UAC)

L'UAC est une fonctionnalité de sécurité fondamentale introduite pour empêcher des logiciels potentiellement malveillants de modifier le système sans le consentement de l'utilisateur.

## 1. Les bases de l'UAC

Le principe de l'UAC est de faire fonctionner tous les utilisateurs (même les administrateurs) avec des privilèges standards le plus souvent possible.

* **Le jeton d'accès :** Lorsqu'un administrateur se connecte, il possède deux jetons : un jeton d'utilisateur standard et un jeton d'administrateur. Les actions quotidiennes utilisent le jeton standard.
* **Le déclenchement :** Lorsqu'une action nécessite des privilèges élevés (installation d'un pilote, modification de fichiers système), Windows demande une confirmation.
* **Le Bureau sécurisé :** Lorsque la fenêtre UAC apparaît, l'arrière-plan s'assombrit. C'est le "Bureau sécurisé" qui empêche d'autres applications d'interagir avec la boîte de dialogue ou de simuler un clic à votre place.

## 2. Les niveaux de notification

Il existe quatre niveaux de réglage pour l'UAC, accessibles via le panneau de configuration ou en tapant `UserAccountControlSettings` dans le menu démarrer.

* **Toujours m'avertir :** Le niveau le plus strict. Recommandé si vous installez souvent de nouveaux logiciels ou visitez des sites peu familiers.
* **M'avertir uniquement quand des applications tentent d'apporter des modifications (Par défaut) :** Windows ne demande pas de confirmation lorsque vous modifiez vous-même les paramètres Windows, mais le fait pour les programmes tiers.
* **M'avertir uniquement quand des applications tentent d'apporter des modifications (ne pas estomper le bureau) :** Identique au précédent, mais sans le Bureau sécurisé (moins sûr).
* **Ne jamais m'avertir :** Désactive l'UAC. **Fortement déconseillé**, car cela permet à n'importe quel logiciel d'obtenir des droits administratifs en silence.

## 3. Comportement selon le type de compte

* **Compte Administrateur :** Une simple boîte de dialogue demande de cliquer sur "Oui".
* **Compte Standard :** Windows demande de saisir le mot de passe d'un compte administrateur pour continuer.
 
