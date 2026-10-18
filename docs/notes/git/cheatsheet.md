# Aide-mémoire des commandes git

Voici un aide mémoire des commandes git que nous utilisons pour ce cours. La structure est inspiré de ce document : [Git Cheat Sheet - Github (French)](https://www.templateroller.com/template/2639556/git-cheat-sheet-github-french.html#doc_window){target=_blank}

## Configuration de git

**Nom de la branche par défaut**

Changer le nom de la branche créé par défaut avec la commande `git init`.

```
git config --global init.defaultBranch [nom de la branche]
```

Configurer le nom d'usager et le email dans un terminal

```
git config --global user.name "Prénom Nom"
```
```
git config --global user.email "courriel@exemple.com"
```

## Création de dépot

**Initialiser un dépot local git**

Essentiel pour pouvoir utiliser git sur un projet. À faire à la racine de votre répertoire de projet

```
git init
```

**Télécharger un projet distant**

Crée une copie local synchroniée d'un projet distant. La commande va créer un répertoire du nom du dépot. 

```
git clone [url]
```

**Lier un dépot local à un dépot distant**

```
git remote add origin [url]
```

---

## Effectuer des changements

**Vérifier le statut du dépot**

Donne des informations sur le dépot, la file d'attente et les modifications.

```
git status
```

**Ajouter un ou des fichiers dans la file d'attente**

Vous pouvez lister un à un les fichiers à ajouter ou bien utiliser un point pour ajouter tous les fichiers qui ont des modifications depuis le dernier commit.

```
# Ajout par nom de fichier
git add [nom_fichier]

# Ajout de tous les fichiers modifiés
git add .
```

**Créer une version du projet (commit)**

```
git commit -M "description du commit"
```

**Synchroniser le commit avec un dépôt distant**

La première fois:

```
git push -u origin main
```

Ensuite

```
git push
```

---




