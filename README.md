# Kevmag – Gestion du magasin Complast

Application de gestion pour le magasin de meubles Complast (Bibwa, N'sele, Kinshasa).

## Fonctions
- **Caisse** : panier, client, mode de paiement (espèces, mobile money, banque, crédit). Chaque vente diminue le stock et reçoit un numéro de reçu.
- **Remises à la caisse** : 3 % sur tous les articles, 0 % sur les mousses et les matelas Elengi, 10 % sur les matelas Orthopédique (modifiable dans Réglages) ; appliquées au panier, aux acomptes et aux échanges, détaillées sur les reçus.
- **Prix en $ et en FC** : chaque prix d’article est affiché dans les deux devises au taux du jour (stock, caisse, panier, échanges, recherche, aperçu d’import) ; dans le formulaire, le prix peut être saisi en $ ou en FC (l’autre est calculé).
- **Vente en dollars ou en francs congolais** : à la caisse, choix de la devise de la vente et du taux du jour ; total affiché dans les deux devises ; reçu (A4, ticket, WhatsApp) dans la devise payée avec l'équivalent ; Rapport : encaissé en $ et en FC.
- **Stock** : produits par catégorie (chambres, lits, matelas, mousses, tables, canapés, buffets, TV stands…), prix, quantité, seuil d'alerte.
  Pour les mousses : densité, longueur, largeur et épaisseur (affichées dans le stock, la caisse et sur le reçu).
- **Import de produits** (dans Stock) : fichier Excel (.xlsx) ou CSV. Les colonnes sont reconnues (nom, catégorie, prix, stock, alerte, densité, longueur, largeur, épaisseur). Sans catégorie, Kevmag la devine d'après le nom (mousse, matelas, lit, armoire/wardrobe → Garde-robe, dressing table et chest → Dresser table, night stand → Nightstand, salon…) et lit les mesures des mousses dans le nom (« D25 190x140x20 »). Aperçu avant import, catégorie modifiable ; un produit déjà existant (même nom) est mis à jour, mais seulement pour les colonnes remplies dans le fichier (une liste de prix ne change pas le stock). Un modèle de fichier est téléchargeable.
- **Gammes de matelas** : Elengi, Bonheur, Dream, Extra Dream, Orthopédique, Prestige, Super Dream, Bébé D14, Bébé D16. Choix dans le formulaire (devinée d'après le nom), colonne « Gamme » à l'import, sous-filtres et sous-groupes dans la liste des matelas ; dans chaque gamme, les matelas sont triés par taille (longueur, largeur, puis épaisseur).
- **Tarifs** (💲, menu latéral, bouton du Stock ou Réglages) : prix de **tous les articles** au même endroit, saisis en FC ou en $ (taux des tarifs 2 350 ; le prix en FC reste exact). Filtres par catégorie et gamme/densité, recherche, filtre « ⚠️ Sans prix » ; prix modifiable directement dans la liste ; grille par gamme pour les matelas (colonnes = largeur, lignes = épaisseur).
  - **Grille des mousses** (dans Tarifs → Mousse) : prix en FC par cm d’épaisseur pour D12 / D16 / D20 × largeurs 90 / 120 / 140 / 180, modifiable ; bouton « Appliquer » (toutes ou une densité) ; prix automatique des nouvelles mousses.
- **Mousses** : sous-filtres par densité (D12, D16, D20, Déchet / divers) avec le nombre d’articles et de pièces ; groupées par densité puis triées par taille (longueur, largeur, épaisseur).
- **Import d'une photo (JPG/PNG) de liste de prix** : Kevmag lit le texte de la photo (Tesseract.js, internet nécessaire), retrouve les tailles et les prix, devine la catégorie et la gamme (« MATELA BONHEUR 900 »), et relie chaque ligne au produit existant de même taille. Les prix sont modifiables dans l'aperçu ; ceux non lus sont en orange, à compléter. Le stock n'est pas modifié.
- **Stock classé par catégorie** : liste regroupée par catégorie, avec des filtres (Tous, Mousse, Matelas…).
- **Reçus** (facture A4 par défaut : logo, mentions légales RCCM/Id. Nat./N° Impôt, encadrés Reçu et Client, tableau, total, montant en lettres, cachet et signature ; ou ticket 58/80 mm) : après chaque vente (bouton 🖨️ Reçu dans la Caisse) ou plus tard depuis le Rapport. Format ticket (imprimante 58/80 mm) ou page A4 / PDF. Nom, adresse, téléphone et message du magasin se règlent dans **Réglages**.
- **WhatsApp** : bouton « Envoyer sur WhatsApp » sur le reçu (vers le numéro du client s'il est saisi) et « Envoyer le rapport du jour sur WhatsApp » dans Rapport (vers le numéro WhatsApp du gérant, réglé dans Réglages → Reçus). WhatsApp s'ouvre avec le message prêt ; il reste à appuyer sur Envoyer.
- **Vente sans stock (à livrer)** : un article vendu au-delà du stock est noté « −N vendus · à livrer » (stock négatif, filtre ⚠️ À livrer, mention sur le reçu et WhatsApp) ; à l’arrivage (entrée ou transfert reçu) les pièces déjà vendues sont déduites automatiquement et signalées.
- **Transferts entre magasins** (🚚) : envoi vers un autre magasin (stock diminue) ou réception d’un autre magasin (stock augmente), plusieurs articles par transfert, magasins mémorisés, bon de transfert A4 (expéditeur / transporteur / réceptionnaire) et WhatsApp, historique filtrable, annulation qui remet le stock ; Rapport : pièces envoyées / reçues du jour.
- **Entrées d’articles** (📥) : provenance « usine » (bon de réception BRU) ou « autre magasin » (enregistrée aussi comme transfert reçu TRR), plusieurs articles par entrée, bon A4 et WhatsApp, historique filtrable, annulation ; bouton ＋ du stock = entrée usine rapide ; Rapport : reçu de l’usine / transferts.
- **Acomptes** (onglet ⏳) : réservation d'articles payée en plusieurs fois. Création depuis la Caisse (articles retirés du stock), versements en $ ou FC, barre de progression, reçu d'acompte A4 et envoi WhatsApp, « Livrer » quand tout est payé (devient une vente), « Annuler » remet en stock et indique le montant à rembourser. Rapport : acomptes reçus du jour.
- **Échanges** (sans remboursement) : retrouver l'achat (n° de reçu, client, téléphone), choisir les articles rapportés et les nouveaux ; échange accepté à prix égal ou supérieur (le client paie la différence en $ ou FC), refusé si le nouvel article est moins cher. Stock mis à jour, bon d'échange A4 et WhatsApp, différence comptée dans le chiffre du jour. Accès : tuile « Échange » de l'Accueil, bouton de la Caisse, menu latéral.
- **État du stock sur WhatsApp** : boutons « WhatsApp (PDF) » et « WhatsApp (Excel) » dans Rapport → État du stock ; le fichier est créé (jsPDF / SheetJS) puis partagé via le menu de partage du téléphone (choisir WhatsApp) ; sinon il est téléchargé et WhatsApp s’ouvre.
- **Rapport** : chiffre du jour et du mois, liste des ventes (annulables), produits à réapprovisionner.
- **Arrière-plan « Ciel »** : ciel réaliste en WebGL (nuages volumétriques en bruit fractal, éclairés par le soleil, en perspective, poussés par le vent), couleurs interpolées selon l’heure (aube, jour, soir, nuit étoilée avec lune) ; version simplifiée si WebGL est indisponible ; Réglages → Apparence → Arrière-plan (Produits / Ciel / Aucun).
- **Animation en arrière-plan** : les photos des produits Complast (dossier `fond/`) défilent doucement derrière l’application (fondu + zoom lent), désactivable dans Réglages → Apparence.
- **Apparence** : thème « iOS 26 · Liquid Glass » par défaut (verre translucide, barre d’onglets flottante, grands titres, clair/sombre selon l’iPhone) ou « Nuit étoilée », au choix dans Réglages.
- **Réglages** : devise ($ ou FC), sauvegarde et restauration des données.

## Utilisation
Ouvrir `index.html` dans un navigateur (téléphone ou ordinateur). Aucune installation nécessaire.

Les données sont enregistrées dans le navigateur de l'appareil : faire une sauvegarde régulière depuis **Réglages**.

## Synchronisation entre appareils (Firebase)
Réglages → ☁️ Synchronisation. Un projet Firebase gratuit (Authentication e-mail/mot de passe + Firestore) partage produits, ventes, acomptes, échanges et réglages entre tous les appareils connectés au même compte, en direct et hors ligne (file d'attente Firestore).
- Chaque élément est un document Firestore (`produits`, `ventes`, `acomptes`, `echanges`, `config/magasin`), avec un champ `maj` (horodatage serveur) ; les suppressions sont « douces » (`supprime: true`).
- Les changements locaux sont détectés par empreinte et envoyés par lots ; le stock est envoyé en incrément (`+/- différence`) pour rester juste quand plusieurs appareils vendent en même temps.
- Chaque appareil n'écoute que les documents modifiés depuis sa dernière synchro (peu de lectures).
- Le guide d'installation et les règles Firestore (limitées à l'e-mail du magasin) sont dans l'application.

## Installer sur iPhone (comme une application)
1. Ouvrir **https://kevconcept.github.io/Kevmag/** dans **Safari**.
2. Toucher le bouton **Partager** (carré avec une flèche vers le haut).
3. Choisir **Sur l'écran d'accueil**, puis **Ajouter**.

L'icône Kevmag apparaît sur l'écran d'accueil. L'application s'ouvre en plein écran et fonctionne aussi sans internet.

Attention : les données saisies dans Safari et celles de l'icône sont séparées. Utiliser toujours l'icône (ou restaurer une sauvegarde dedans).

Sur Android : ouvrir le site dans Chrome, menu ⋮ → **Installer l'application** (ou **Ajouter à l'écran d'accueil**).
