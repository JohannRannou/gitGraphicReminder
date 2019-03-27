# Comment utiliser l'outil de versionnage **git** pour gérer ses jeux de données Zset


## Qu'est qu'un gestionnaire de version?

C'est un outil qui :

  * "enregistre" l'état d'un projet à un état donné
  * permet de revenir à un état donné précédant 
  * permet de comparer deux états 
  
Ça évite d'avoir des répertoires ou des fichiers qui s'appellent ``mon_calcul_v0.inp``, ``mon_calcul_v9.inp``, ``mon_calcul_19_03_2019.inp``,  ``mon_calcul_qui_marche_lundi_matin.inp``.
  
  

## Principe de base de git




## Usage de base pour des jeux de données Zset pour un usage individuel


### Initialiser un dépot git dans un répertoire

Si on veux "versionner" un répertoire, il sufit d'y rentrer et de taper :

```
git init
```


### Initier le versionnage de fichiers

Les fichiers sont par défaut non versionnés, il faut préciser à git qu'il faut les *tracker*.

```
git add calcul.inp
```
ou pour plusieurs fichiers
```
git add calcul.inp mesher.inp
```

Cette commande place les fichiers, dans leur état  courant, dans l'index


### Modifier l'état de fichiers dans l'index

C'est aussi la commande `add` qu'il faut utiliser, c'est pareil qu'avant
```
git add calcul.inp mesher.inp
```


### Commiter les fichiers de l'index

Commiter signifier "enregistrer un état". Par défaut, git commit tout ce qui est dans l'index.
Attention, l'état *working* d'un fichier peut être différent de l'état *indexé*.

Pour commiter :

```
git commit
```
Il faut alors donner un descriptif des modifications.
Il est important d'être précis pour pouvoir s'y retrouver longtemps après.
**Ne pas hésiter à faire plein de commit plutôt qu'un très gros.**
C'est plus facile dans ce cas de trouver un message pertinent.


Si on a la flemme d'indexer préalablement, on peut commiter tous les fichiers déjà *trackés* comme ceci :

```
git commit -a
```

### Avoir des informations sur l'état du dépot

Pour afficher  une liste détaillée des commits (date, identifiant, messages, lien avec le commit précédent)
```
git log
```

Pour savoir ce qui est dans l'index, ce qui n'est pas dans l'index, ce qui n'est pas versionner :

```
git status
```


### Visualiser les différences avec une version précédente


différence entre l'état courant (*working*) avec l'index
```
git diff
```

différence entre l'état courant (*working*) avec le dernier commit
```
git diff HEAD
```


différence entre deux commits
```
git diff 
```
