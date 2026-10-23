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

## Modifier, ajouter et supprimer des propriétés

On modifie la valeur d'une propriété de la même façon qu'on le fait avec une variable: 

```javascript title="Modifier une propriété"
livre.parution = 2018;
```

Si on fait référence à une propriété qui n'existe pas, elle sera ajoutée:
```javascript title="Ajouter une propriété"
livre.note = 8;
```

Pour supprimer une propriété on utilise l'opérateur `delete`
```javascript title="Supprimer une propriété"
delete livre.note;
```

## Objets impriqués

Il est possible d'imbriquer un objet dans un objet. 

```javascript
const etudiant = {
    nom: "Alex",
    age: 19,
    adresse: {
        ville: "Victoriaville",
        codePostal: "G6P 1A1"
    }
};
```

Dans cet exemple, si on veut accéder à la valeur de la propriété ville on doit enchaîner les propriétés:
```javascript
console.log(etudiant.adresse.ville);
```

## Parcourir les propriétés d'un objet

On peut parcourir les propriétés d'un objet avec une boucle `for...in`

```javascript
const jeu = {
    titre: "Minecraft",
    prix: 39.99,
    genre: "Sandbox"
};

for (const propriete in jeu) {
    console.log(propriete);
}

// Affichera :
// titre
// prix
// genre
```

Pour afficher les valeurs de chaque propriété, on peut utiliser la notation par crochet:

```javascript
for (const propriete in jeu) {
    console.log(jeu[propriete]);
}
```

## Tableaux d'objets

Il est très courant d'avoir des objets dans un tableau.

```javascript
const jeux = [
    {
        titre: "Minecraft",
        genre: "Sandbox",
        prix: 39.99
    },
    {
        titre: "Stardew Valley",
        genre: "Simulation",
        prix: 17.99
    },
    {
        titre: "Hades",
        genre: "Action",
        prix: 32.99
    }
];
```

Pour accéder aux valeurs, on utilise les mêmes techniques que pour les tableaux et les objets.

```javascript
console.log(jeux[0].titre);
// Afficher "Minecraft"
```