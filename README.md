# Kevmag – Gestion du magasin Complast

Application de gestion pour le magasin de meubles Complast (Bibwa, N'sele, Kinshasa).

## Fonctions
- **Caisse** : panier, client, mode de paiement (espèces, mobile money, banque, crédit). Chaque vente diminue le stock et reçoit un numéro de reçu.
- **Stock** : produits par catégorie (chambres, lits, matelas, mousses, tables, canapés, buffets…), prix, quantité, seuil d'alerte.
  Pour les mousses : densité, longueur, largeur et épaisseur (affichées dans le stock, la caisse et sur le reçu).
- **Import de produits** (dans Stock) : fichier Excel (.xlsx) ou CSV. Les colonnes sont reconnues (nom, catégorie, prix, stock, alerte, densité, longueur, largeur, épaisseur). Sans catégorie, Kevmag la devine d'après le nom (mousse, matelas, lit, armoire/wardrobe → Garde-robe, dressing table et chest → Dresser table, night stand → Nightstand, salon…) et lit les mesures des mousses dans le nom (« D25 190x140x20 »). Aperçu avant import, catégorie modifiable ; un produit déjà existant (même nom) est mis à jour. Un modèle de fichier est téléchargeable.
- **Gammes de matelas** : Elengi, Bonheur, Dream, Extra Dream, Orthopédique, Prestige, Super Dream, Bébé D14, Bébé D16. Choix dans le formulaire (devinée d'après le nom), colonne « Gamme » à l'import, sous-filtres et sous-groupes dans la liste des matelas.
- **Stock classé par catégorie** : liste regroupée par catégorie, avec des filtres (Tous, Mousse, Matelas…).
- **Reçus** : après chaque vente (bouton 🖨️ Reçu dans la Caisse) ou plus tard depuis le Rapport. Format ticket (imprimante 58/80 mm) ou page A4 / PDF. Nom, adresse, téléphone et message du magasin se règlent dans **Réglages**.
- **Rapport** : chiffre du jour et du mois, liste des ventes (annulables), produits à réapprovisionner.
- **Réglages** : devise ($ ou FC), sauvegarde et restauration des données.

## Utilisation
Ouvrir `index.html` dans un navigateur (téléphone ou ordinateur). Aucune installation nécessaire.

Les données sont enregistrées dans le navigateur de l'appareil : faire une sauvegarde régulière depuis **Réglages**.

## Installer sur iPhone (comme une application)
1. Ouvrir **https://kevconcept.github.io/Kevmag/** dans **Safari**.
2. Toucher le bouton **Partager** (carré avec une flèche vers le haut).
3. Choisir **Sur l'écran d'accueil**, puis **Ajouter**.

L'icône Kevmag apparaît sur l'écran d'accueil. L'application s'ouvre en plein écran et fonctionne aussi sans internet.

Attention : les données saisies dans Safari et celles de l'icône sont séparées. Utiliser toujours l'icône (ou restaurer une sauvegarde dedans).

Sur Android : ouvrir le site dans Chrome, menu ⋮ → **Installer l'application** (ou **Ajouter à l'écran d'accueil**).
