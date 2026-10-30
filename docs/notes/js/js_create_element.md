# Créer, ajouter et supprimer un élément

On peut avec JavaScript créer, ajouter et supprimer des éléments html à notre page.

### Créer des éléments

On peut créer un élément en Javascript en utilisant la function **createElement()**.

``````js title="Syntaxe"
document.createElement("nodename")
// nodename réprésente le nom de la balise html
``````

``````js title="Exemple d'utilisation"
// Créer une nouvelle balise h1 et l'assigne dans la variable titre
let titre = document.createElement("h1");
``````

Une fois l'élément créé, on peut le modifier et le manipuler comme quand on récupére un élément avec `getElementbyId()` par exemple.

```javascript title="script.js" linenums="1" hl_lines="6"
// Création de l'élément h1
let titre = document.createElement("h1");
// Ajout du id "idTitre"
titre.id = "idTitre";
// Ajout de texte dans la balise
titre.innerText = "Le Titre";
// Ajout d'une classe "classTitre"
titre.classList.add("classTitre");
// Ajout d'un listener sur le click
titre.addEventListener("click", cliqueSurTitre);
```

### Ajouter des éléments

Les méthodes **append()** et **appendChild()** sont utilisés pour ajouter des éléments dans le DOM, on va voir la méthode **append()**. Cette méthode prend en paramètre un élément HTLM ou du texte. On peut utiliser **append()** avec l'objet **document** ou avec ==un autre élément==.

``````js
// Récupère l'élément avec le id containerExemple 
// (c'est un élément div pour l'exemple)
let monContainer = document.getElementById("containerExemple");
// Créer un élément h1
let titre = document.createElement("h1");
titre.innerText = "Le Titre";

// Ajouter l'élément créé dans le document, dans la page. La balise h1 
// sera ajouté à la suite des autres éléments à l'intérieur de la balise body.
document.body.append(titre);
// Ajouter l'élément créé dans l'élément monContainer. La balise h1 sera 
// ajouté à la suite des autres éléments à l'intérieur de l'élément avec le 
// id containerExemple.
monContainer.append(titre);
``````

### Créer des éléments imbriqués

Il est possible de créer plusieurs éléments et de les imbriqués l'un dans l'autre avant de les ajouter dans la page Web. Dans ce cas on va ajouter uniquement l'élément parent. Prenons par exemple une liste à puce qu'on voudrais créer entièrement à partir d'un tableau de string.

```js title="Création d'une liste à puces"
const tableauItems = ["item1", "item2", "item3"]
// Création de l'élément ul
const ul = document.createElement("ul");
// Pour chaque item du tableau, on va créer un item de liste à puces (li)
// et l'ajouter dans celle-ci
for (let i = 0; i < tableauItems.length; i++) {
    const li = document.createElement("li");
    li.innerText = tableauItems[i];
    ul.append(li);
}
// Finalement on ajoute l'élément ul qui contient déjà les 3 éléments li
document.body.append(ul);
```

### Supprimer des éléments

Pour supprimer un élément il suffit de le sélectionner et d'utiliser la méthode **remove()**

``````js
// Récupère l'élément avec le id containerExemple
let monContainer = document.getElementById("containerExemple");
// Supprime l'élément. Attention tous les éléments enfants qui étaient à l'intérieur de cet élément seront aussi supprimé.
monContainer.remove();
``````

Pour supprimer tous les éléments enfants d'un parent utilisez la méthode **replaceChildren()**
``````js
// Récupère l'élément avec le id containerExemple
let monContainer = document.getElementById("containerExemple");
// Supprime tous les enfants sans supprimer le parent.
monContainer.replaceChildren();
``````



