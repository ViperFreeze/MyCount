# MyCount

Application web de suivi de budget personnel, en un seul fichier HTML, sans serveur ni dépendance à installer.

## Fonctionnalités

- **Mois** (accueil) : en gros, ce qui reste ce mois-ci (revenus + crédits − prélèvements − dépenses − ce qui est encore prévu pour vos objectifs), avec le détail déjà débité / à débiter / crédits, puis la saisie des dépenses avec un libellé (suggestions : Nourriture, Essence et vos libellés habituels) et leur historique.
- **Revenus par mois** : un montant habituel (Réglages) et, si besoin, un montant propre à un mois (prime, mois incomplet) via « Modifier » sur la ligne Revenus. Changer le montant habituel ne réécrit pas les mois passés.
- **Objectifs comptés dans ce qui reste** : la part pas encore dépensée de vos objectifs du mois (ex. 200 € sur 250 € de Courses) est déduite de « Il vous reste ». Une dépense dans un objectif ne change donc pas ce qui reste, seul un dépassement le fait baisser.
- **Double validation** : une dépense saisie est d'abord « en attente ». Elle est comptée tout de suite dans ce qui reste (en bleu sur la jauge), mais ne passe en « déjà débité » que quand vous touchez deux fois « Débité » (le 1er appui affiche « Confirmer ? »), une fois l'opération vraiment visible sur votre compte en banque. Le cadre « À valider » liste tout ce qui n'est pas encore passé, y compris les prélèvements du mois ; les opérations validées du mois y restent visibles (avec « Annuler »). Une case « Déjà débité » permet de saisir une opération déjà passée.
- **Crédits** : les rentrées d'argent ponctuelles (remboursement, virement reçu…) s'ajoutent aux revenus du mois, avec la même validation « Reçu ».
- **Objectifs de dépenses** (onglet Mois) : un plafond mensuel **par catégorie** (ex. 250 € pour Courses, prélèvements de la catégorie compris) ou **par libellé** (ex. 100 € pour l'Essence). Une barre montre ce qui reste ou le dépassement, et « Voir » filtre la liste. À la saisie, une dépense peut être rangée dans une catégorie ; la catégorie est reprise automatiquement quand on réutilise le même libellé.
- **Prélèvements** : les prélèvements mensuels rangés par catégorie, et la gestion des catégories.
- **Historique** : toutes les opérations, avec recherche et filtres, et un export CSV des 3 derniers mois (séparateur « ; », s'ouvre dans Excel ou Google Sheets).
- **Stats** : comparaison des dépenses sur les 6 derniers mois.
- **Épargne** : ce que vous avez de côté, votre objectif, et un prélèvement mensuel d'épargne (compté avec les autres prélèvements et déduit de ce qui reste ; celui du mois en cours s'ajoute à l'épargne une fois validé « Débité »). Les prévisions montrent, mois par mois, le montant atteint jusqu'à l'objectif.
- **Réglages** (comme MyHours) : revenus mensuels, thème clair/sombre/auto, sauvegarde automatique dans un Gist GitHub privé, export/import de fichier, copier-coller entre appareils (fusion sans doublons) et remise à zéro des dépenses.

Au premier lancement, l'appli démarre vide avec des catégories par défaut, à ajuster dans l'onglet Prélèvements.

## Utilisation

Ouvrir `index.html` dans un navigateur. Aucune installation n'est nécessaire.

## Installer sur l'écran d'accueil

L'app est installable (PWA) et fonctionne hors ligne une fois ouverte. Elle doit être servie en HTTPS, par exemple via GitHub Pages : `https://viperfreeze.github.io/MyCount/`.

- **iPhone (Safari)** : bouton Partager → « Sur l'écran d'accueil ».
- **Android (Chrome)** : menu ⋮ → « Installer l'application » ou « Ajouter à l'écran d'accueil ».

L'installation ne fonctionne pas depuis un fichier ouvert en local ni depuis l'aperçu claude.ai.

## Données

Toutes les données restent dans le stockage local (`localStorage`) du navigateur. Rien n'est envoyé à un serveur et aucune donnée personnelle n'est stockée dans ce dépôt. Les montants sont enregistrés en centimes pour éviter les erreurs d'arrondi.
