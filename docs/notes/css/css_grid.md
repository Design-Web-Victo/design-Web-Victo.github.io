# CSS Grid

La disposition par grille CSS (CSS Grid layout) est comme son nom l'indique une méthode de disposition basée sur un système de grille à deux dimensions. On peut le voir comme une feuille Excel avec des lignes et des colonnes. C'est une grosse différence entre cette méthode et Flexbox, qui a plutôt une disposition unidirectionnelle. Par contre les deux systèmes fonctionnent très bien ensemble. Il n'est pas rare de voir une disposition générale d'une page avec **grid** et l'alignement des sections avec **Flexbox**. 

Tout comme avec Flexbox, on va travailler avec un conteneur de base parent (**Grid container**) et ses items enfants (**Grid items**).

## Exemple simple de disposition

HTML

``````html
<!DOCTYPE html>

<html>

    <head>
        <meta charset="utf-8">

        <title>Exemple simple de disposition</title>
        <link rel="stylesheet" href="styles/exemple_simple.css">
    </head>

    <body>

        <div class="grid_container">
            <div class="grid_items">Item 1</div>
            <div class="grid_items">Item 2</div>
            <div class="grid_items">Item 3</div>
            <div class="grid_items">Item 4</div>
            <div class="grid_items">Item 5</div>
            <div class="grid_items">Item 6</div>
        </div>

    </body>

</html>
``````

CSS 

``````css
.grid_container {
    /* Détermine une disposition grid */
    display: grid;
    /* On détermine une disposition sur trois colonnes, la
     * première et dernière avec une dimension de 150 pixels. 
     * La colonne du milieu s'adaptera à l'espace disponible
     */
    grid-template-columns: 150px 1fr 150px;
    /* On détermine deux lignes de 150 pixels chacune */
    grid-template-rows: 150px 150px;
    /* Il y aura une espace en les enfants de 10 pixels */
    grid-gap: 10px;

}

.grid_items {
    /* J'utilise ici flexbox sur les items pour
     * gérer l'alignement du contenu 
     */
    display: flex;
    justify-content: center;
    align-items: center;
    /* un peu de style pour embellir le tout */
    background-color: lightcoral;
    border-radius: 5px;
    font-size: 2em;
    color: #fff;
}
``````

Résultat

![css-grid01](../../assets/images/css-grid01.png)

## Propriétés du Grid Container

### display

Comme avec Flexbox, on doit déterminer le méthode de disposition qu'on veut utiliser pour le container avec la propriété **display**. Avec Css Grid on attribue la valeur **grid** à cette propriété.

``````css
.container {
	display: grid;
}
``````

### grid-template-columns

Détermine le nombre et les dimensions des colonnes de la grille par une liste de valeur. Chaque valeur représentent à la fois un colonne et sa dimension.

``````css
.container {
    /* La grille aura deux colonnes, la première
     * de 100 pixels et la seconde de 200 pixels
     */
	grid-template-columns: 100px 200px; 
}
``````

Si toutes les colonnes ont la même dimension, on peut utiliser **repeat()**

``````css
.container {
    /* Ici la grille aura 10 colonnes de 100 pixels */
	grid-template-columns: repeat(10, 100px);
}
``````

On peut aussi utiliser l'unité de mesure **fr** qui représente une fraction de l'espace disponible. 

``````css
.container {
    /* Ici la grille aura 10 colonnes de largeur égale. 
     * La largeur sera redimensionnée selon l'espace disponible
     * Par exemple si le conteneur à une largeur de 1000px, chaque colonne sera de 100px
     */
	grid-template-columns: repeat(10, 1fr);
}

.container_large {
    /* Ici la grille aura 3 colonnes dont celle du milieu 
     * sera 2 fois plus grande que la première et la dernière
     */
    grid-template-columns: 1fr 2fr 1fr
}
``````

### grid-template-rows

Détermine le nombre et les dimensions des lignes de la grille par une liste de valeur. Chaque valeur représentent à la fois une ligne et sa dimension. Les valeurs possible sont exactement les mêmes que pour **grid-template-columns**.

### grid-template-area

Il est aussi possible de construire une représentation visuelle de la disposition voulue avec la propriété **grid-template-area**. On doit définir un mot-clé pour chaque "cellule" de notre grille et ensuite associer chaque item composant la grille à un mot-clé avec la propriété **grid-area**.

HTML

``````html
<!DOCTYPE html>

<html>

    <head>
        <meta charset="utf-8">

        <title>Exemple simple de disposition</title>
        <link rel="stylesheet" href="styles/exemple_simple.css">
    </head>

    <body>

        <div class="grid_container">
            <div class="grid_items item1">Item 1</div>
            <div class="grid_items item2">Item 2</div>
            <div class="grid_items item3">Item 3</div>
            <div class="grid_items item4">Item 4</div>
            <div class="grid_items item5">Item 5</div>
            <div class="grid_items item6">Item 6</div>
        </div>

    </body>

</html>
``````
CSS
``````css
.grid_container {
	display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(3, 150px);
    grid-gap: 10px;
    /* On détermine un mot-clé qu'on peut répéter en respectant une 
     * disposition rectangulaire. Le . sert à laisser la case vide.
     */
    grid-template-areas: 
        "item1 item2 item3 item4"
        "item1 item5 item5 ."
        "item1 . item6 item6";
}

.grid_items {
    /* J'utilise ici flexbox sur les items pour
     * gérer l'alignement du contenu 
     */
    display: flex;
    justify-content: center;
    align-items: center;
    /* un peu de style pour embellir le tout */
    background-color: lightcoral;
    border-radius: 5px;
    font-size: 2em;
    color: #fff;
}

.item1 {
    /* On relie le mot-clé avec l'item par la propriété grid-area */
    grid-area: item1;
}
.item2 {
    grid-area: item2;
}
.item3 {
    grid-area: item3;
}
.item4 {
    grid-area: item4;
}
.item5 {
    grid-area: item5;
}
.item6 {
    grid-area: item6;
}

``````

Résultat

![css-grid02](../../assets/images/css-grid02.png)

## Propriété des Grid items

### grid-column-start, grid-column-end, grid-column

Permet de déterminer à partir de quelle colonne l'item commence et à quelle colonne il se termine. Pour déterminer le numéro de ligne, il faut s'imaginer notre grille qui commence par une ligne avant la première cellule, comme dans l'image suivante : 

![css-grid03](../../assets/images/css-grid03.png)

Donc si on veut que le premier item soit disposé dans les colonnes 1 et 2 de la première ligne, on aurait les valeurs suivantes : 

``````css
.item1 {
	grid-column-start: 1;
    grid-column-end: 3;
}
``````

On peut faire la même chose sur une seule ligne avec la propriété grid-column où la valeur est égale à la colonne du début et de la fin séparé par le symbole /

``````css
.item1 {
	grid-column: 1 / 3;
}
``````

On peut aussi utilisé comme valeur de fin -1, ce qui veut dire que la colonne de fin sera la toute dernière, peut-importe le nombre et si on en ajoute en cours de route.

``````css
.item1 {
	grid-column: 1 / -1;
}
``````

### grid-row-start, grid-row-end, grid-row

C'est la même propriété que pour le grid-column, mais au niveau des lignes.

## Tutoriel sous forme de jeux

- [Grid Garden](https://codepip.com/games/grid-garden/){:target="_blank"}

## Tutoriel en vidéo

<iframe width="560" height="315" src="https://www.youtube.com/embed/Jarz_GZG7-I?si=-aJHd5CPmWrlq9TX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen class="center"></iframe>

## Pour aller plus loin 

- [A Complete Guide to Grid ](https://css-tricks.com/snippets/css/complete-guide-grid/){:target="_blank"}
- [MDN - Grilles CSS](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_grid_layout){target=_blank}
- [Plein d'exemple de disposition avec Grid](https://gridbyexample.com/examples/){target=_blank}

