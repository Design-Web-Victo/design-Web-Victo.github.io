# Exercice 14 - Gestion d'un catalogue de livres

## Initialisation et remise

- Créez un dépôt nommé **dw_ex14_object** sur Github
- Clonez le dépôt sur votre portable et réalisez l'exercice
- Vous devez créer un fichier JavaScript qui contiendra le script et le relier à une page html.
- Une fois terminé, créez une version de votre exercice (add, commit) et poussez le (push) sur Github.
- Remettez le devoir Teams avec l'url vers votre dépot.

## Énoncé

- Copiez le tableau suivant dans votre fichier de script.
- Réalisez ensuite les étapes suivantes.

```javascript title="Tableau de livres"
const livres = [
    { titre: "1984", auteur: "George Orwell", annee: 1949, disponible: true },
    { titre: "Le Seigneur des anneaux", auteur: "J.R.R. Tolkien", annee: 1954, disponible: false },
    { titre: "Dune", auteur: "Frank Herbert", annee: 1965, disponible: true },
    { titre: "Fahrenheit 451", auteur: "Ray Bradbury", annee: 1953, disponible: true },
    { titre: "Le messie de Dune", auteur: "Frank Herbert", annee: 1969, disponible: true },
];
```

!!! astuce

    Si vous avez besoin d'aide avec les objets : [Le Tutoriel JavaScript Moderne - Objets](https://fr.javascript.info/object){target=_blank}

### Partie 1 – Lecture et affichage

- Affichez dans la console le titre du premier livre du tableau.
- Affichez le nombre total de livres dans la collection.
- Utilisez `console.table()` pour afficher le tableau de livres
- Maintenant créez une boucle qui affiche le titre et l’auteur de chaque livre.

### Partie 2 – Manipulation des données

- Ajoutez un nouveau livre à la fin du tableau :
    - `{ titre: "Neuromancien", auteur: "William Gibson", annee: 1984, disponible: false }`
- Changez la disponibilité du livre "Le Seigneur des anneaux" à true. Vous devez parcourir le tableau de livres pour le retrouver et changer la propriété `disponible`.
- Supprimez le livre "Fahrenheit 451" du tableau. Comme le livre n'est pas au début ni à la fin du tableau, vous ne pouvez utiliser les méthodes `.pop()` et `.shift()`. Commencez par retrouver son index avec [`.findIndex()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex){target=_blank}. Ensuite, si vous avez un résultat, utilisez la méthode [`.splice()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array/splice){target=_blank}

### Partie 3 – Recherche et filtrage

- Créez un nouveau tableau contenant uniquement les livres disponibles.
- Affichez le titre des livres disponibles publiés avant 1960.
- Cherchez s’il existe des livres de l’auteur "Frank Herbert" et affichez un message approprié :
    - "Livres trouvés : Dune, Le messie de Dune"
    - ou "Aucun livre de Frank Herbert trouvé."

### Partie 4 – Fonction d'affichage du catalogue

- Écrivez une fonction afficherCatalogue(livres) qui :
    - Trie les livres par année de publication avec la méthode `.sort()`.
    - Utilisez la méthode `.map()` pour créer un nouveau tableau.
    - Chaque item de ce tableau sera uniquement un string formaté comme ceci : `=> titre (auteur) - [Disponible/Non disponible]`
    - Affiche le tableau comme ceci :

    ```text
    === Catalogue des livres ===
    => 1984 (George Orwell, 1949) - Disponible
    => Le Seigneur des anneaux (J.R.R. Tolkien, 1954) - Disponible
    => Dune (Frank Herbert, 1965) - Disponible
    => Le messie de Dune (Frank Herbert, 1969) - Disponible
    => Neuromancien (William Gibson, 1984) - Non disponible
    ```

- Lancez ensuite la fonction pour afficher le résultat

!!! astuce

    Pour lancer une fonction, vous n'avez qu'à inscrire son nom et ajouter les paramêtres s'il y en a

    ```js
    nomFonction(); // Fonction sans paramêtres
    nomFonction(params); // Fonction avec paramêtres
    ```

### Partie 5 – Lancer une recherche depuis un bouton

- Créez une fonction `rechercherLivre()` qui va permettre de rechercher les livres d'un auteur. (Vous pouvez copier le code que vous avez créé à la partie 3)
- L'usager devra entrer le nom de l'auteur. Pour ce faire utilisez la fonction [`prompt()`](https://www.w3schools.com/jsref/met_win_prompt.asp){target=_blank} comme ceci: 

```js
let auteurRecherche = prompt("Entrez le nom de l'auteur");
```

- Ensuite affichez le résultat de la recherche avec la fonction [`alert()`](https://www.w3schools.com/jsref/met_win_alert.asp){target=_blank}
- Finalement ajoutez un bouton dans votre page html avec l'attribut `onclick="rechercherLivre()"`

```html 
<button onclick="rechercherLivre()">Rechercher</button>
```

- Testez votre fonction en cliquant sur le bouton.