#### Complétion
Utiliser la touche TAB. 
```
exemple :
cd + TAB
```
#### Historique
- Utiliser les touches haut et bas pour naviguer
- Afficher toute l'historique 
```
history 
```
- Vider l'historique
```
history -c
```
- Rappeler une commande de l'historique
```
!number (ex: !20)
!string (ex: !date)
!! (rappeler la derniere commande de l'historique)
```
#### Recherche
- Faire la combinaison de touche : ```ctrl + r + mot_clé```
- Quitter la recherche : ```ctrl + g```
#### Déplacement
- Début de commande : ```ctrl + a```
- Fin de commande : ```ctrl + e```
- Se deplacer vers la gauche mot par mot : ```ctrl + LeftArrow```
- Se deplacer vers la droite mot par mot : ```ctrl + RightArrow``
#### Suppression
- Supprimer tout depuis le curseur jusqu'à la fin de la commande : ```ctrl + k```
- Supprimer tout avant le curseur : ```crtl + u``` 
#### Modifier la casse
- Transformer en majuscule : ```ESC + u``` 
- Transformer en miniscule: ```ESC + l``` 
#### Rappeler l'argument de la derniere commande
Utiliser les combinaisons de touches : ```ESC + .``` ou ```Alt + .```

#### Ecrire une commande sur plusieurs lignes
```
head -n 3 \
/usr/share/dict/words \
/usr/share/dict/linux.words
```
