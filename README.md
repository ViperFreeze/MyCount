# MyCount

Application web de suivi de budget personnel, en un seul fichier HTML, sans serveur ni dépendance à installer.

## Fonctionnalités

- **Budgets** : un budget mensuel par catégorie, avec le reste à dépenser et une jauge de rythme sur le mois.
- **Dépenses** : saisie rapide, historique par mois, gestion des catégories.
- **Stats** : comparaison des dépenses sur les 6 derniers mois.
- **Épargne** : objectifs d'épargne avec échéance et versement mensuel suggéré, dépôts et retraits, et simulateur (versement, durée, taux, dont Livret A) avec date d'atteinte prévue pour chaque objectif.
- **Synchronisation** entre appareils par copier-coller d'une sauvegarde JSON, fusionnée sans doublons.

Au premier lancement, l'appli démarre vide avec des catégories par défaut, à ajuster dans Budgets.

## Utilisation

Ouvrir `index.html` dans un navigateur. Aucune installation n'est nécessaire.

## Installer sur l'écran d'accueil

L'app est installable (PWA) et fonctionne hors ligne une fois ouverte. Elle doit être servie en HTTPS, par exemple via GitHub Pages : `https://viperfreeze.github.io/MyCount/`.

- **iPhone (Safari)** : bouton Partager → « Sur l'écran d'accueil ».
- **Android (Chrome)** : menu ⋮ → « Installer l'application » ou « Ajouter à l'écran d'accueil ».

L'installation ne fonctionne pas depuis un fichier ouvert en local ni depuis l'aperçu claude.ai.

## Données

Toutes les données restent dans le stockage local (`localStorage`) du navigateur. Rien n'est envoyé à un serveur et aucune donnée personnelle n'est stockée dans ce dépôt. Les montants sont enregistrés en centimes pour éviter les erreurs d'arrondi.
