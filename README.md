# Compte commun

Petite page web pour répartir les charges communes d’un couple selon la logique du « reste à vivre égal » : chacun finit le mois avec le même montant, une fois sa part versée sur le compte commun.

## Ce que fait la page

- Calcule la part de chacun à virer sur le compte commun à partir des deux salaires.
- Additionne la liste des charges fixes, avec une marge pour les dépenses variables.
- Permet de modifier, ajouter ou supprimer une charge.
- Génère un lien de partage pour copier sa configuration sur un autre appareil.

## Le calcul

Avec :

- `A` : salaire de la première personne
- `B` : salaire de la seconde personne
- `C` : total des charges fixes
- `M` : marge pour les dépenses variables
- `T = C + M` : montant cible du compte commun

Alors :

- Part de la première personne = `(T + A − B) / 2`
- Part de la seconde personne = `T − part de la première`

Le reste à vivre est identique pour les deux : `(A + B − T) / 2`.

## Utilisation

1. Ouvrir [cette page](https://lucsapin.github.io/charges-ll/) et saisir les charges manuellement ou via un import.
2. Chaque mois, saisir les deux salaires.
3. Lire les montants à virer sur le compte commun.

Dans le champ d’une charge, on peut écrire une somme, par exemple `21+7,90`.

## Partager la configuration entre deux téléphones

La page est publique et vide : aucune donnée personnelle n’est dans le dépôt.

1. Sur le premier téléphone, ouvrir **Partager ou importer la configuration** et appuyer sur **Créer le lien de partage**.
2. Envoyer le lien par message.
3. Sur le second téléphone, ouvrir le lien et appuyer sur **Importer**.

Si la page est installée sur l’écran d’accueil, le lien s’ouvre dans Safari et non dans l’application installée. Dans ce cas, copier le lien, ouvrir l’application, déplier **Partager ou importer la configuration**, coller le lien dans le champ prévu et appuyer sur **Importer**.

Le lien contient les charges et la marge, pas les salaires. Tout ce qui suit le `#` dans une adresse reste dans le navigateur et n’est jamais envoyé à GitHub.

## Installation

Il n’y a rien à installer : tout tient dans un seul fichier `index.html`, sans serveur.

### Publier avec GitHub Pages

1. Déposer `index.html` à la racine du dépôt.
2. Dans **Settings → Pages**, choisir la branche principale et le dossier racine.
3. Ouvrir l’adresse fournie par GitHub.

### Ajouter à l’écran d’accueil d’un iPhone

1. Ouvrir l’adresse dans Safari.
2. Appuyer sur **Partager**, puis sur **Sur l’écran d’accueil**.

## Données

Les salaires, la marge et la liste des charges sont enregistrés dans le `localStorage` du navigateur, donc uniquement sur l’appareil utilisé. Rien n’est envoyé à un serveur.

- Chaque téléphone garde ses propres réglages : une charge modifiée sur l’un n’apparaît pas sur l’autre tant qu’un nouveau lien n’a pas été partagé.
- Vider les données du navigateur efface les réglages. Le lien de partage permet de les restaurer.

## Limites

- Pas de synchronisation automatique entre appareils.
- Pas d’historique des mois précédents.
- Les montants sont en euros.
