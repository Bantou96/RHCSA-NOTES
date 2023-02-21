### Définition des termes 
- Système d'exploitation : programme ou un ensemble de programmes permettant la gestion de l'ordinateur et des périphériques.
- Noyau : programme principal du système d'exploitation chargé en mémoire au démarrage du système.
- Logiciel : Ensemble de programmes (Code source + Code Objet) 
- Logiciel libre : entièrement libre d'accès, d'utilisation et de redistribution
- Logiciel open source : entièrement libre d'accès, d'utilisation, de modification et de redistribution. 
- FSF : Free Sotfware Fundation 
- Licence : contrat que le détenteur des droits sur un logiciel va proposer afin de concéder certains droits à ses licenciés.
- Organisme de gestion des licences : GPL (General Public Licence)
- Liberté sur une licence
  - Liberté 0 : Utiliser le logiciel quelque soit l'usage 
  - Liberté 1 : Etudier le fonctionnement du logiciel et l'adapter selon ses besoins
  - Liberté 2 : redistribution de copies du logiciel
  - Liberté 3 : Améliorer le logiciel et le diffuser au public
  
### Les distributions Linux
3 grandes familles :
- Debian : Ubuntu, Kali, Debian...
- Redhat : CentOS, Fedora, RHEL...
- Slackware : Suse, OpenSuse...

### Red Hat
• Une distribution Linux est un système d'exploitation installable, construit à partir d'un noyau
Linux et prenant en charge les bibliothèques et les programmes utilisateur.
• Red Hat participe à la prise en charge et à la contribution de code aux projets Open Source,
parraine et intègre le logiciel de projet dans des distributions communautaires, et le stabilise
pour le proposer comme produit pris en charge pour des entreprises.
• Red Hat Enterprise Linux est la distribution Open Source Linux commercialisée pour les
entreprises de Red Hat.
• Un abonnement Red Hat Developer gratuit permet d'obtenir des ressources et des informations
gratuites, dont une version 16 nœuds de Red Hat Enterprise Linux.

#### Le Shell
- Interpréteur de commandes interactif et personnalisable
- Deux types (GUI & CLI)
- CLI :  Command Line Interface
  - Bash : Shell de base (le plus répendu et recommandé pour les débutant)
  - C-shell : Shell adapté à la programmation avec le langage C 
  - Z-shell : Shell avec des fonctionnalités avancés comme l'autocomplétion
  
#### Le prompt
Il fournit les informations sur le système 
- Structure : 
```mame@pc:~$```
  - mame : nom d'utilisateur courant 
  - pc : nom de la machine
  - ~ : Répertoire de travail
  - $ : Caractère de terminaison
- Fichier d'initialisation du shell bash : /etc/profile

### Les types de commandes 
- Commandes internes au shell 
- Commandes externes (programmes binaires)
- Les alias (raccourcis de commandes)
- Syntaxe d'une commande : 
  - commande -options arg1 arg2

Exemple
``` 
wc -l /etc/passwd
```
ou sous forme combiner (command1 ; command2)
``` 
wc -l /etc/passwd ; wc -w /etc/passwd
```
