# L'imbrication en CSS

L'imbrication (nesting en anglais) permet d'écrire un sélecteur css et ses règles à l'intérieur d'un autre sélecteur. 

L'avantage étant de regrouper ensemble des règles relatives à un même élément HMTL.

!!! note ""

    Libre à vous d'utiliser l'imbrication dans vos projets. Si ça complique votre compréhension ne l'utilisez pas.

```css title="Exemple avec css traditionnel"
.card {
    background-color: white;
}

.card h2 {
    color: blue;
}

.card p {
    font-size: 1rem;
}

.card a {
    color: red;
}
```

Dans cet exemple on veut appliquer des règles à la classe `card` ainsi qu'à toutes les balises enfants `h2`, `p` et `a`. Avec l'imbrication ça donnerait ceci

```css title="Avec imbrication"
.card {
    background-color: white;

    h2 {
        color: blue;
    }

    p {
        font-size: 1rem;
    }

    a {
        color: red;
    }
}
```

## Le symbole &

On peut remplacer le sélecteur parent par le symbole `&`. C'est très utiliser avec les pseudo-classes.

```css title="Symbole &" 
.button {
    background-color: blue;

    &:hover {
        background-color: darkblue;
    }
}
```

Attention à ne pas vous tromper quand vous utilisez le symbole `&`.

```css title="" hl_lines="2"
/* Une classe title qui est enfant d'une classe card */
.card {
    .title {
        color: red;
    }
}
/* Est équivalent à */
.card .title {
    color: red;
}

/* Un élément qui à les classes card et title */
.card {
    &.title {
        color: red;
    }
}
/* Est équivalent à */
.card.title {
    color: red;
}
```



## À retenir

- L'imbrication fonctionne toujours avec une relation de sélecteur parent et enfant.

```css title=""
parent {
    propriété: valeur;

    enfant {
        propriété: valeur;
    }
}
```

- Essayez de ne pas imbriquer trop profondément, un seul niveau suffit aisément.
- Le symbole `&` est très pratique pour ne pas répéter le sélecteur parent.
- Une bonne pratique est de regrouper les sélecteurs qui sont dépendant d'un même sélecteur parent ensemble. 

## Médiagraphie

- Maxime. (2026, February 15). *CSS nesting : Pourquoi et comment l’utiliser?* writecode.fr. [https://writecode.fr/tutoriel/le-nesting-avec-css-vanilla](https://writecode.fr/tutoriel/le-nesting-avec-css-vanilla){target=_blank}
- MozDevNet. (n.d.). *CSS nesting*. MDN Blog RSS. [https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Nesting](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Nesting){target=_blank} 