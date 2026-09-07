# Anglais One

Carnet de vocabulaire anglais qu'on remplit et révise à plusieurs — sans que personne ait besoin d'un compte.

## Mettre l'appli en ligne (une seule fois)

L'appli (`index.html`) est prête, mais GitHub doit être autorisé à la publier :

1. Sur GitHub, va dans **Settings** (Paramètres) du repo `benjimdrr/benjamin`
2. Dans le menu de gauche, clique **Pages**
3. Sous **Source**, choisis **Deploy from a branch**
4. Branche : **`claude/anglais-one-shared-sync-9yc74y`** (ou `main` une fois cette branche fusionnée), dossier **`/ (root)`**
5. **Save**

Après une ou deux minutes, l'appli est en ligne à cette adresse :

**👉 https://benjimdrr.github.io/benjamin/**

## Utiliser l'appli

Envoie ce lien à tes amis — **aucun compte requis**, ni Claude, ni GitHub, ni rien. Tout le monde qui l'ouvre voit la même liste de mots, en temps réel :
- ajouter un mot (avec plusieurs traductions possibles),
- modifier ou supprimer un mot,
- réviser avec le quiz (anglais → français, français → anglais, ou mélange),
- suivre un classement commun des scores de quiz,
- voir combien d'amis ont la page ouverte en ce moment.

Les mots et les scores sont sauvegardés sur une base de données partagée (Firebase, gratuite), pas dans le navigateur : rien ne se perd, pas besoin de recommencer à chaque visite.

## Détails techniques

- `index.html` : le code source complet (une seule page HTML/CSS/JS), à héberger tel quel (GitHub Pages ou n'importe quel hébergeur statique).
- Stockage partagé : **Firebase Realtime Database** (projet `anglais-b8c25`), en accès libre (lecture/écriture ouvertes sur les chemins `words` et `scores`) — comme un Google Doc dont le lien est partagé, il n'y a pas de mot de passe.
- Si Firebase est injoignable (réseau bloqué), l'appli bascule sur un mode solo local (`localStorage`) pour ne pas planter, avec un message qui l'indique.
