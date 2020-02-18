# TP2 - Compte-Rendu

## Exercice 1 - Variables d’environnement

1. Dans la variable *PATH*
\> `printenv PATH`
`/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:[...]`

2. \>`printenv`
`[...]`
`HOME=/home/vebervi`
`[...]`
Il semble donc que ce soit la variable d'environnement *HOME* qui permette à la commande `cd` sans argument de nous ramener dans notre répertoire personnel.

3. - `LANG=fr_FR.UTF-8` - C'est la langue et l'encodage
	- `PWD=/home/` - C'est le dossier courant, elle change donc à chaque fois que l'on se déplace
	- `OLDPWD=/` - C'est donc le dossier où l'on était avant que l'on se trouve là où l'on est... C'est le dossier "précédent" de *PWD*. C'est cette variable qui est utilisée dans la commande `cd -` pour retourner au dossier où l'on était précedemment.
	- `SHELL=/bin/bash` - C'est là où se trouve l'interpréteur de commande, ici *bash*. Par ailleurs, on retrouve ce chemin au début des scripts bash.
	- `_=/usr/bin/printenv` - C'est le dernière paramètre de la dernière commande exécutée : 
	\> `touch 1.txt 2.txt 3.txt`
	\> `echo $_`
	`3.txt`

4. \> `MY_VAR="tp2ex1"`
\> `echo $MY_VAR`
`tp2ex1`

5. \> `bash`
\> `echo $MY_VAR`
*rien*
`bash` ouvre un autre shell, d'où le fait que notre variable locale (donc uniquement connue du Shell précédent) n'existe plus.

6. \> `export MY_VAR="tp2ex1"`
\> `echo $MY_VAR`
`tp2ex1`
\> `bash`
\> `echo $MY_VAR`
`tp2ex1`
Notre variable existe encore car elle a bien été déclarée comme une variable d'environnement et donc accessible peu importe le shell dans lequel on se trouve.

7. \> `export NOMS="DREVET VEBER`
\> `echo $NOMS`
`DREVET VEBER`

8. \> `echo "Bonjour à vous deux, $NOMS !`
`Bonjour à vous deux, DREVET VEBER !`

9. `unset` supprime la variable, elle n'existe plus. Affecter une chaîne vide à une variable crée quand même une variable, mais vide. Afficher une variable supprimée n'affichera rien tandis qu'afficher une variable vide donnera un retour à la ligne.

10. \> `echo '$HOME'" = $HOME"`
`$HOME = /home/vebervi`

## Programmation Bash

Pour rajouter noter dossier *script* à la variable *PATH*, on va rajouter `PATH=$PATH:~/script` à la fin du fichier *.bashrc* puis on exécute la commande `source .bashrc` afin que la modification soit prise en compte.

### Exercice 2 - Contrôle de mot de passe

##### DREVET Yoann
##### VEBER Vincent