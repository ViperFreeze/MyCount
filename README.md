# MyCount

Application web de suivi de budget personnel, en un seul fichier HTML, sans serveur ni dépendance à installer.

## Fonctionnalités

- **Budget plaisir** (accueil) : en gros, ce qu'il vous reste pour vous faire plaisir ce mois-ci, calculé à partir de votre salaire : salaire + crédits reçus − prélèvements (épargne comprise) − objectifs de dépenses = budget plaisir du mois. Chaque dépense hors objectifs (ou au-delà d'un objectif) le fait baisser. Une jauge montre la part déjà dépensée avec le repère du jour, et le montant possible par jour jusqu'à la fin du mois. Le solde en banque, facultatif, s'affiche en petit comme contrôle (fin de mois estimée).
- **Revenus par mois** : un montant habituel (Réglages) et, si besoin, un montant propre à un mois (prime, mois incomplet) via « Modifier » sur la ligne Revenus. Changer le montant habituel ne réécrit pas les mois passés.
- **Objectifs retirés du budget plaisir** : le plafond de chaque objectif (ex. 250 € de Courses) est réservé d'avance. Une dépense dans un objectif ne change donc pas le budget plaisir, seul un dépassement le fait baisser.
- **Notifications de la banque** : MacroDroid (Android) dépose chaque notification BoursoBank dans le Gist de sauvegarde (un fichier `notif-<heure>-<n>.txt`). MyCount les lit à l'ouverture puis chaque minute : paiements carte, virements envoyés et prélèvements sont ajoutés tout seuls, sans validation. Une même dépense annoncée deux fois n'est comptée qu'une fois, et un prélèvement déjà prévu est simplement marqué « passé ». Les notifications lues sont retirées du Gist.
- **À ranger** : les dépenses venues des notifications se rangent d'un appui (catégorie ou objectif par libellé, ex. Essence) ; les suivantes chez le même commerçant sont rangées toutes seules. Un prélèvement inconnu peut être ajouté aux prélèvements mensuels. Les notifications non reconnues (ex. alerte de crédit sans montant) s'ajoutent en dépense ou crédit, ou s'ignorent.
- **Saisie à la main** : repliée sous la liste des opérations (« + Ajouter une opération à la main »), pour le liquide ou une notification manquée.
- **Crédits** : les rentrées d'argent ponctuelles (remboursement, virement reçu…) s'ajoutent aux revenus du mois.
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
