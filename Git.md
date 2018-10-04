# Commandes Git:

[Basics](#basics)
[Merge](#merge)
[Branches](#branches)
[Examples](#examples)
[Pull](#pull)


## Basics

`git clone ADRESSE_DU_DEPOT nom_du_dossier_destination(optionel)`
Permet de copier un depot git distant en local


`git status`
Permet de verifier l'etat des fichiers vis a vis du dernier commit local


`git add NOM_DU_FICHIER`
Permet d'ajouter/tracker l'etat d'un fichier pour l'ajouter au prochain commit 
Un fichier supprimé doit aussi etre "add"


`git commit -m "MESSAGE_DU_COMMIT"`
Permet de creer une "snapshot" du projet et y associer un nom
>option -a : ajouter l'etat de tous les fichiers DEJA trackés (modifiés, deplacés, supprimés)


`git push ADRESSE_DU_DEPOT BRANCHE_A_POUSSER`
Permet de pousser la branche projet "en ligne"
>option: -u | --set-upstream pour créer la branche sur le depot distant



Dans le fichier .gitconfig a la racine de votre session (`~/.gitconfig`) doit contenir:
```
[pull]
	rebase = true
```



`git pull`
Permet de recuperer les donnees du depot distant:

1)Il n'y a pas de conflits ou git sait les gérer, un merge est effectué automatiquement.

2)Il y a des conflits:
	-Régler les conflits dans chaque fichier (via `git status`)
	-Poursuivre le rebase: `git rebase --continue`
	-Ne pas oublier de pousser les nouveaux commits


set des alias dans .gitconfig (`~/.gitconfig`)
```
[alias]
  aa = add --all
  cm = commit -m
```




## Merge

1)`git checkout BRANCH_NAME` 

Se positionner sur la branche que l'on veut merge

2) `git pull origin BRANCH_NAME`

Récuperer les datas de la branche depuis le depot distant

3)`git checkout master`

Se positionner sur la branche vers laquelle on veut merge BRANCH_NAME

4)`git merge BRANCH_NAME`
Faire le merge


##### Plusieurs cas sont possible pour le `git merge` :

```Already up-to-date.```

-Il n'y a eu aucun changement a effectuer

-Il n'y a rien d'autre a faire



```
Mise à jour 05677c9..2ed28c1
Fast-forward
 FICHIER | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
 ```

-Le merge a fusionné le travail en ajoutant les fichier/datas de BRANCH_NAME sur la branche courante (master)

-Il n'y a rien d'autre a faire



```
Fusion automatique de FICHIER
CONFLIT (contenu) : Conflit de fusion dans FICHIER
La fusion automatique a échoué ; réglez les conflits et validez le résultat.
```

Le merge n'a pas été effectué, git nous positionne automatiquement sur une "branche temporaire", il faut régler manuellement les conflits (le fichier qui s'appelle FICHIER dans l'exemple)

-Faire un `git status` pour vérifier les fichiers a modifier pour résoudre les conflits, message:

```
Sur la branche master
Votre branche est à jour avec 'origin/master'.
Vous avez des chemins non fusionnés.
  (réglez les conflits puis lancez "git commit")

Chemins non fusionnés :
  (utilisez "git add <fichier>..." pour marquer comme résolu)

	modifié des deux côtés :  FICHIER

aucune modification n'a été ajoutée à la validation (utilisez "git add" ou "git commit -a")
```

-Apporter les modifs aux fichiers nécessaire

-`git add FICHIER` puis `git commit -m "MERGE BRANCH_NAME to MASTER"`

ou `git commit -am "MERGE BRANCH_NAME to MASTER"` message:

```[master 2e66a41] Merge complete```

-Le merge a fonctionné, et git nous re-positionne sur la branche Master

-Il n'y a plus rien a faire


## Branches

Connaitre la branche actuelle du dossier local:
`git branch` 

```
  master
* tester

```
L'etoile (ainsi que la couleur selon la coloration de votre shell), indique sur quelle branche nous sommes positionnés.

Créer une nouvelle branche:
`git branch NOUVELLE_BRANCHE`

Se positionner sur une branche:
`git checkout BRANCHE_CIBLE`


On ***préfèrera*** créer ET se positionner directement sur la nouvelle branche:
`git checkout -b NOUVELLE_BRANCHE`


## Pull

Cas 1:

On est sur la branche master

`git pull` ou `git pull origin master`


Plusieurs cas sont possible:

```Already up-to-date.```

-Il n'y a eu aucun changement a effectuer

-Il n'y a rien d'autre a faire

PENDING

## Examples


PENDING
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEwMDQ0MjE1Myw3MzA5OTgxMTZdfQ==
-->