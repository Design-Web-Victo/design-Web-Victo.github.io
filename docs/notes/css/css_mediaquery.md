# Media queries

Il est possible avec les requêtes média (media queries) de définir une séries de règles css différentes en fonction de l'appareil ou de son type d'affichage (la taille de l'écran par exemple).  On pourrait très bien avoir des règles pour les écrans d'ordinateur, pour l'impression et pour les cellulaires.

## Syntaxe dans une feuille de style

```css title="Syntaxe d'un media query"
@media not|only type_de_media and (caracteristique_media) {
  selecteur {
    propriété : valeur;
  }

  selecteur {
    propriété : valeur;
  }
}
```

### Type de media

Le type de média est **optionnel**, par défaut il prendra la valeur **all** qui correspond à tous les médias. 

| Valeur | description                                                  |
| ------ | ------------------------------------------------------------ |
| all    | Tous les types de média (valeur par défaut)                  |
| screen | Tous les appareils possédant un écran                        |
| print  | Pour l'impression, par exemple quand on fait un aperçu avant l'impression |
| speech | Pour les outils de synthèse vocale                           |

!!! Note

    La très grande majorité du temps, nous allons utiliser *screen* comme type de média
    ``````css
    @media screen and (max-width: 680px) {
      /* Mon code css */
    }
    ``````

### Opérateurs logiques

#### and

Permet de combiner plusieurs sous-requête en une seule. Pour que la requête soit évalué comme vrai, toutes les sous-requêtes doivent aussi être vrai.

```css
@media screen and (min-width: 320px) and (max-width: 768px) {
  ...
}
```

Dans cet exemple les règles seront utilisées sur tous les appareils possédant un écran dont la dimension de la zone d'affichage est située entre 320 et 768 pixels.

#### or

On peut aussi en séparant les sous-requêtes par une virgule, utiliser le **ou** logique. Dès qu'une sous-requête est vrai, la requête média sera vrai.

``````css
@media  screen and (min-height: 680px), screen and (orientation: portrait) { 
    ... 
}
``````

Dans cet exemple, les règles seront appliquées si la taille de la zone d'affichage est d'une hauteur supérieur à 680 pixels ou si l'écran est en mode portrait.

#### not

Permet d'inverser le résultat d'une requête. 

``````css
@media print and ( not(color) ) {
  ...
}
``````

Dans cet exemple, les règles seront appliquées si l'appareil est une imprimante et ne peut pas afficher de couleur.

### Caractéristique du média

On peut aussi ajouter dans la condition un ou des caractéristiques du média. Le plus souvent on va travailler avec la largeur de la zone d'affichage ou l'orientation du l'appareil.

Si on veut travailler avec la largeur de l'écran, on va utiliser la caractéristique **width** précédée de **min-** ou **max-** pour déterminer une borne inférieur ou supérieur.

Exemple, je veux appliquer une règle si la largeur de l'écran est inférieur ou égale à 680 pixels. Je vais indiquer que la largeur maximale doit être de 680 pixels. 

``````css
@media  screen and (max-width: 680px) {
  ...
}
``````

Avec les nouvelles spécifications css on peut maintenant utiliser les caractères >, < et = au lieu de **min-** et **max-**. Ça donne une requête qui est visuellement plus facile à comprendre. La même exemple plus haut réécrite de cette façon : 

``````css
@media  screen and (width <= 680px) {
  ...
}
``````

Il est aussi possible de cette façon de donner une plage sans utiliser l'opérateur **AND**. Par exemple je veux une règle qui s'applique quand la largeur de l'écran est entre 600 pixels et 1200 pixels

``````css
@media  screen and (600px <= width <= 1200px) {
  ...
}
``````
### Exemple

```css title="Exemple d'un media query"
/* Si la largeur de l'écran est inférieur ou égale à 680 pixels */
@media  screen and (width <= 680px) {
  /* Je veux modifier la taille de police des balises h1 */
  h1 {
    font-size: 2rem;
  }
  /* Je modifie la propriété flex-wrap de la classe conteneur */
  .conteneur {
    flex-wrap: wrap;
  }
}
```

## Utilisation des requêtes média

### Dans un fichier HTML

#### Avec la balise link

On peut ajouter l'attribut media à la balise link pour importer un fichier css seulement quand la requête est vrai.

```html
<html>
  <head>
    <!-- Va être importé si la taille de l'écran a une largeur supérieur à 600 pixels -->
    <link rel="stylesheet" href="extra-large.css" media="(min-width: 600px)" />
  </head>

</html>
```

### Dans un fichier CSS

L'utilisation dans un fichier css ce fait en englobant la ou les règles par la requête.

``````css
@media screen and (min-width: 320px) and (max-width: 768px) {
  p {
    background-color: yellow;
    color: blue;
  }
}
``````

#### Avec l'attribut media de la balise style

On peut aussi utiliser l'attribut media de la balise style.

``````css
<style>
  p {
    background-color: blue;
    color: white;
  }
</style>

<style media="all and (max-width: 500px)">
  p {
    background-color: yellow;
    color: blue;
  }
</style>
``````

Ici la couleur du texte des paragraphes changera selon la dimension de l'écran.

## Concepts important à garder en tête

### Ordre des médias queries

On a vu que le css appliquait les règles en cascade, l'une après l'autre. C'est aussi le cas avec les médias queries. Si vous en avez plusieurs, faites attention à l'ordre dans lesquelles vous les définissez. Voici un petit exemple où je change la couleur de fond de la page selon la largeur de l'écran. 

``````css
body {
    background-color: antiquewhite;
}

@media  screen and (width <= 600px) {
    body {
        background-color: pink;
    }
}

@media  screen and (width <= 1000px) {
    body {
        background-color:chartreuse;
    }
}
``````
La couleur ne deviendra jamais rose, car quand le premier média query est vrai, le deuxième le sera toujours aussi. La règle appliquée sera donc la dernière. Dans cet exemple on devrait inverser les deux médias queries.

!!! important

    Vos requêtes médias devraient toujours se retrouver à la fin de vos fichiers de style css.

### Évitez les répétitions

Dans le contenu d'un média query, ajoutez ==uniquement les règles qui seront modifiées==. Vous n'êtes pas obligé de répéter toutes les règles et ça évite une duplication du code et une porte ouverte pour de possibles erreurs.

``````css
h1 {
    color: blue;
    font-size: 5em;
}
@media  screen and (width <= 600px) {
    h1 {
        font-size: 2em;
    }
}
``````
Ici j'ai appliqué du style à mes balises h1, et quand la largeur de l'écran est inférieur ou égale à 600 pixels, je change la taille de la police. Étant donné que je ne veux pas aussi changer la couleur, je me suis pas obligé de répéter la règle ici, la couleur restera bleu.

## sources

* [https://css-tricks.com/a-complete-guide-to-css-media-queries/](https://css-tricks.com/a-complete-guide-to-css-media-queries/){target=_blank}
* [https://developer.mozilla.org/fr/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/fr/docs/Web/CSS/Media_Queries/Using_media_queries){target=_blank}
* [https://www.w3schools.com/css/css3_mediaqueries.asp](https://www.w3schools.com/css/css3_mediaqueries.asp){target=_blank}
* [https://www.w3schools.com/css/css3_mediaqueries_ex.asp](https://www.w3schools.com/css/css3_mediaqueries_ex.asp){target=_blank}

