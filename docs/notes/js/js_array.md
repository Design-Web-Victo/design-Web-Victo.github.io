# Les tableaux

Un tableau est une structure de données qui permet de stocker plusieurs valeurs dans une seule variable.
Chaque valeur a une position appelée index qui commence à 0.

## Déclaration

Il existe deux syntaxes pour céer un tableau vide, la deuxième étant la plus utilisée : 

```js
let tableauNew = new Array();
let tableauCrochet = [];
```

Il n'est pas nécessaire de déterminer la taille du tableau lors de sa déclaration. Tout comme les variables on peut déclarer le tableau et ensuite lui assigner des valeurs sur la même ligne. 

```js
let fruits = ["Pomme", "Orange", "Poire"];
```

## Les éléments du tableau

On peut ajouter n'importe quel type de données dans un tableau, mais je vous conseille de toujours vous en tenir à un type par tableau.

```js
let tableauString = ["un", "deux", "trois"];
let tableauInteger = [1, 2, 3];
let tableauObjet = [
    {nom: "Fréchette", prenom: "Mathieu"},
    {nom: "Taleb", prenom: "Frédérik"},
    {nom: "Mercier", prenom: "François"},
];
```

**Accéder à un élément du tableau**

On va utiliser l'index de l'élément pour le récupérer : 

```js
console.log(fruits[2]); // Poire
```

Si l’indice n’existe pas, JavaScript retourne `undefined`;

**Modifier la valeur d'un élément**

On peut modifier un élément comme on le ferais avec une variable

```js
fruits[2] = "Banane";
```

**Ajouter un élément dans le tableau**

Ajouter ==à la fin== du tableau avec `array.push()`: 

```js
fruits.push("Kiwi");
fruits.push("Fraise", "Bleuet"); // On peut ajouter plus d'un élément à la fois
```

Ajouter au début avec `array.unshift()`:

```js
fruits.unshift("Framboise"); // On pourrait aussi en ajouter plus d'un
```

**Supprimer un élément du tableau**

Supprimer le dernier élément avec `array.pop()`: 
```js
fruits.pop();
```

Supprimer le premier élément avec `array.shift()`: 
```js
fruits.shift();
```

**Récupérer le nombre d'éléments d'un tableau**

```js
let professeurs = ["Mathieu", "Frédérick" ,"François", "Simon"];
console.log(professeurs.length); // 4
// On peut se servir de length pour récupérer le dernier élément sans
// connaître son index
console.log(professeurs[professeurs.length - 1]); // Simon
```

## Parcourir un tableau

Avec une boucle `for`:

```js
let fruits = ["Pomme", "Orange", "Poire"];

for (let i = 0; i < fruits.length; i++) {
    // Affiche chaque item du tableau à la console
    console.log(fruits[i]);
}
```

Avec une boucle `for..of`:
```js
let fruits = ["Pomme", "Orange", "Poire"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

Avec `array.forEach()`:
```js
let fruits = ["Pomme", "Orange", "Poire"];

fruits.forEach((fruit) => {
    console.log(fruit);
});
```

Dans cet exemple `fruit` est une variable accessible uniquement dans la boucle et qui représente l'élément de l'itération (c'est la même chose que de faire `fruits[i]` avec une boucle `for`). 

## Opération sur les tableaux

Voici quelques opérations plus avancés sur les tableaux. Elles utilisent tous une fonction de callback comme paramètre.

**`array.find()`**

Pour trouver ==le premier élément== du tableau correspondant à une condition.

```js
let ages = [18, 21, 43, 25, 20];

let resultat = ages.find((age) => { return age > 40 });

console.log(resultat); // 43
```

**`array.filter()`**

Retourne un nouveau tableau contenant tous les éléments du tableau d'origine qui remplissent une condition.

```js
let professeurs = ["Mathieu", "Frédérick" ,"François", "Simon"];

const nouveauTableau = professeurs.filter((prof) => { 
    return prof.length >= 8;
});
console.log(nouveauTableau); // ["Frédérick", "François"]
```

**`array.map()`**

Retourne un nouveau tableau en modifiant tous les éléments du tableau d'origine selon la fonction fournie.

```js
let nombres = [1, 2, 3, 4];

let nombresDouble = nombres.map((nombre) => {
  return nombre * 2;
});

console.log(nombresDouble); // [2, 4, 6, 8]
```

## Exercices

- Dans le répertoire **js** votre projet **exercices_js**, ajoutez et liez le un fichier **array.js**. 
- Commentez les liens vers les autres fichiers de script des exercices précédents.
- Réalisez les exercices suivants dans un fichier JS

**Exercice #1 - Parcourir un tableau**

- Déclarez un tableau `noms` contenant 5 prénoms.
- Ajoutez un prénoms au début et à la fin du tableau.
- Affichez chaque prénom dans la console à l’aide :
    1. d'une boucle `for`
    2. d'une boucle `for..of`
    3. d'une boucle `array.forEach()`

**Exercice #2 - Filtrer un tableau**

- Créez un tableau `notes` contenant les valeurs suivantes : `[85, 42, 67, 90, 58, 73]`
- Utilisez la méthode `.filter()` pour créer un nouveau tableau `notesReussies` qui contient seulement les notes supérieures ou égales à 60.
- Affichez le résultat dans la console.
- Affichez le dernier élément du tableau `notesReussies` en utilisant `length`.

**Exercice #3 - Transformer un tableau**

- Crée un tableau `prix` contenant les valeurs suivantes (en dollars) : `[10, 25, 30, 5, 15]`
- Utilise `.map()` pour créer un nouveau tableau `prixTaxes` qui contient le prix avec une taxe de 15% ajoutée.
- Affiche les deux tableaux (`prix` et `prixTaxes`).

**Exercice 4 - Combiner filter() et map()**

- Crée un tableau `nombres` contenant : `[2, 5, 8, 11, 14, 17]`
- Utilise `.filter()` pour garder seulement les nombres pairs.
- Puis, applique `.map()` pour multiplier ces nombres par 3.
- Affiche le tableau final qui devrait être `[6, 24, 42]`.

**Exercice 5 - Tableau d'objets**

Selon le tableau d'objets suivant : 
```js
let produits = [
  { nom: "Chocolat", prix: 3 },
  { nom: "Chips", prix: 2 },
  { nom: "Café", prix: 8 },
  { nom: "Pain", prix: 4 }
];
```

- Utilise `.filter()` pour créer un tableau `produitsAbordables` contenant seulement les produits dont le prix est inférieur à 5.
- Utilise `.map()` sur `produitsAbordables` pour créer un nouveau tableau qui contient seulement les noms des produits.
- Affiche le résultat final. Utilisez `console.table()` pour afficher le contenu de `produitsAbordables` et `console.log()` pour le 2e tableau. 

!!! Astuce

    Pour accéder aux propriétés d'un objet: 
    ```js
    // Depuis le tableau
    console.log(`Le prix du ${produits[0].nom} est de ${produits[0].prix} dollars`);
    // Dans une boucle
    produits.forEach(produit => {
        console.log(produit.prix);
    });
    ```

- [x] Quand vous aurez terminé l'exercice, créez un commit nommé "Exercices tableaux" et envoyez-le sur GitHub (git push)


## Pour aller plus loin

Vous pouvez faire l'[exercice 13](../../exercices/ex13_js_array.md) pour continuer à expérimenter avec les tableaux.


## Références

- [Le Tutoriel JavaScript Moderne - Arrays](https://fr.javascript.info/array){target=_blank}
- [MDN - Array](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array){target=_blank}