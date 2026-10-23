# Les objets en JavaScript

Un objet est une structure de données qui permet de regrouper plusieurs informations, qui peuvent être de type différentes, liées à un même sujet. 

Prenons l'exemple d'un livre dont je veux stocker le titre, l'auteur, l'année de parution de l'édition et son code ISBN : 

| Propriété | Valeur |
|---|---|
| Titre | Le meilleur des mondes |
| Auteur | Aldous Huxley |
| Parution | 2017 |
| ISBN | 9782266283038 |

```javascript title="Exemple objet livre"
const livre = {
    titre: "Le meilleur des mondes",
    auteur: "Aldous Huxley",
    parution: 2017,
    isbn: 9782266283038
}
```

## Créer un objet

- On utilise les accolades pour créer un objet.
- Les données sont conservées sous des propriétés constituées d'un nom et d'une valeur séparés par un deux-points ` : `.
- Les propriétés sont séparées entre elles par une virgule.

## Accéder aux propriétés

On peut accéder aux propriétés de deux façons: 

- **Notation avec un point**: On indique le nom de l'objet suivi d'un point et le nom de la propriété.
- **Notation avec crochet** : On indique entre crochet le nom de la propriété.

```javascript
const livre = {
    titre: "Le meilleur des mondes",
    auteur: "Aldous Huxley",
    parution: 2017,
    isbn: 9782266283038
}
// Notation avec un point
console.log(livre.titre);
// Notation avec crochet 
console.log(livre["titre"]);
```

