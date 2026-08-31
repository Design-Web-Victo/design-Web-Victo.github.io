# Les chemins relatifs

Le chemin relatif en HTML est une manière d’indiquer où se trouve un fichier (image, page, script, etc.) ==par rapport à la position du fichier HTML== qui l’appelle. C’est l’inverse d’un chemin absolu, qui indique l’adresse complète (ex: c:/users/moi/cegep/designweb/projet1/image.png).

!!! attention

    Utilisez toujours les chemins relatifs pour les ressources de votre site.

## Pourquoi utiliser un chemin relatif?

- Facilite la gestion des fichiers quand on déplace le projet (par exemple d’un ordinateur à un serveur en ligne).
- Plus flexible : pas besoin de changer les liens si l'hébergeur change.

## Comment écrire un chemin relatif?

Il faut garder à l'esprit que le chemin est relatif au fichier dans lequel on l'inscrit.

Si on est dans le même répertoire que le fichier, on peut uniquement entrer le nom du fichier. Par soucis de compatibilité, j'utilise toujours les caractères `./` devant le nom du fichier. Le point indique qu'on se dirige dans le dossier en cours.

```html
<img src="./image.jpg" alt="Image dans le même dossier que la page html">
```

**Dans un dossier enfant**

Dans ce cas on n'a qu'à indiquer le nom des dossiers séparés par le caractère `/`

```html
<img src="../images/image.jpg" alt="Image dans le dossier enfants images">
```

**Dans un dossier parent**

Les caractères `..` indique qu'on remonte d'un répertoire. Donc si le fichier est un répertoire plus "haut" que le fichier en cours : 

```html
<img src="../image.jpg" alt="Image dans le dossier parent">
```

On peut remonter de plus d'un niveau.
```html
<img src="../../image.jpg" alt="Image dans le dossier parent d'un parent">
```

**Dans un dossier frère**

On va utiliser une combinaison des caractères `..` et des noms de répertoire pour se diriger vers la destination.

Dans cet exemple je suis dans le fichier page.html et je veux afficher l'image logo.png

```css title="" hl_lines="3"
/projet/
 ├── html/
 │    └── page.html
 └── images/
      └── logo.png
```

```html
<img src="../images/logo.png" alt="Logo du site">
```

!!! note

    Les chemins relatifs fonctionnent de la même façon en CSS et en JavaScript.





