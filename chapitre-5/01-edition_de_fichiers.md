### les outils 
- gedit
- vim 
- nano
- emacs

### Vim
les modes 

- ESC : mode normal
- i : mode insertion
- : --> mode commande 
- v : mode visuel (permet de selectionner par caractere)
- ctrl + v : mode visual block (permet de selectionner par colonne)
- Shift + V : mode visual line (permet de selectionner ligne par ligne)

les commandes utiles en mode normal ESC

- o : ouvre une nouvelle ligne et nous met directement en mode insert
- A : insertion en fin de ligne
- u : équivalent du ctrl + z
- yy : copier
- p : coller (on peut specifier le nombre de fois qu'on voudrait coller ex : 10p)
- dd : supprimer ou couper une ligne 
- x : effacer le caractère 
- dw : effacer un mot
- cw : changer un mot (efface le mot et nous met en mode insertion)
- d$ : effacer depuis le curseur 
- / : rechercher un mot
- ZZ : quitter et enregistrer

Les commandes utiles en mode commande (:)

- q! : quitter sans enregistrer
- wq! : enregistrer et quitter 
- w file_path : enregistrer vers un fichier specifique 

Editer le fichier : ```~/.vimrc```
- numeroter les lignes dans vim 
```
set number
```
- definir le taquet de tabulation par defaut (2 espaces) lors de la modification de fichiers YAML par exemple dans le fichier ~/.vimrc
```
autocmd FileType yaml setlocal ts=2
set number 
```
