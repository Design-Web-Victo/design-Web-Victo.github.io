# Les événements

Les événements surviennent à tout moment quand les usagers consultent et intérragissent avec nos page web. Ils réprésentent une action qui est survenue et pour laquelle on peut réagir et exécuter du code. Un exemple d'événement qu'on utilise régulièrement est le clique d'un usager sur un bouton.

## Comment interragir avec les événements?

Pour lancer du code selon un événement précis, on va utiliser ce qu'on appelle un *handler*. Le *handler* va ==écouter== l'événement qu'on lui demande d'observer et exécuter du code (généralement une fonction) à chaque fois que l'événement va intervenir. Prenons un exemple simple où je veux afficher un message avec la fonction `alert()` quand je clique sur un bouton.

Voici le code HTML
```html title="index.html" linenums="1" hl_lines="8 11"
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Test événement</title>
    <script defer src="js/script.js"></script>
</head>
<body>
    <button id="bouton-alert" data-text="Allo">Cliquez-moi</button> 
</body>
</html>
```

### Depuis la page HTML

On peut ajouter un attribut à une balise HTML pour l'événement à écouter avec le nom de l'événement et la fonction JavaScript à exécuter.

Dans mon exemple je vais ajouter à la balise button l'attribut `onClick` suivit du nom de la fonction à lancer.

```html title="index.html" linenums="10" hl_lines="2"
<body>
    <button id="bouton-alert" data-text="Allo" onClick='nomFonction()'>Cliquez-moi</button> 
</body>
```

### addEventListener

Tous les objets qui peuvent lancer un événement on une fonction qui se nomme `addEventListener()` et qu'on va utiliser pour écouter les événements. La syntaxe est la suivante 

```javascript
objet.addEventListener('nomEvenement', fonction);
```
La fonction prend en paramêtre le nom de l'événement à écouter et la fonction qu'on veut exécuter. Habituellement l'objet sera une constante qui contient l'élément HTML qui lance l'événement. Le nom de la fonction doit être indiqué ==sans les parenthèses==.

Avec l'exemple plus haut je vais, dans mon script, commencer par assigner mon élément à une constante. Ensuite j'ajoute un *handler* à la constante avec la fonction `addEventListener` pour l'événement **click**. Finalement je crée la fonction qui va être exécutée quand on cliquera sur le bouton. 

```javascript title="script.js" linenums="1"
const monBouton = document.getElementById("bouton-alert");

monBouton.addEventListener("click", afficherAlerte);

function afficherAlerte() {
    alert("Vous avez cliqué sur le bouton !");
}
```
!!! attention

    la fonction `addEventListener` prend uniquement une fonction comme deuxième paramètre. On ne pourrais pas simplement y ajouter le code à exécuter. On peut cependant créer une fonction anonyme fléchée uniquement pour l'occasion.

Le même exemple avec une fonction anonyme

```javascript
const monBouton = document.getElementById("bouton-alert");

monBouton.addEventListener("click", () => {
    alert("Vous avez cliqué sur le bouton !");
});
```

## removeEventListener

Parfois on veut pouvoir enlever un écouteur d'événement qu'on aurait ajouté à un élément. On peut utiliser la méthode `removeEventListener()` comme ceci : 

```js title="" hl_lines="2"
const monBouton = document.getElementById("bouton-alert");
// Ajoute un event listener
monBouton.addEventListener("click", afficherAlerte);

// Supprimer un event listener
// On doit spécifier le même type d'événement (ici 'click') et la même fonction
monBouton.removeEventListener('click', afficherAlerte);
```

## L'objet événement

Quand on lance une fonction depuis `addEventListener`, un objet "événement" est passé par défaut en paramètre de la fonction. Pour le récupérer il suffit d'ajouter un paramètre supplémentaire à la fonction. Habituellement le paramètre sera nommé **e** ou **event**. Cet objet contient plein d'information sur l'événement, entre autre l'élément qui l'a déclenché. En reprenant l'exemple plus haut, on peut par exemple accéder aux attributs du bouton avec la propriété target de l'objet événement et par exemple changer le texte du bouton : 

```javascript title="script.js" linenums="1" hl_lines="6"
const monBouton = document.getElementById("bouton-alert");

monBouton.addEventListener("click", afficherAlerte);

function afficherAlerte(e) {
    e.target.innerHTML = "Vous venez de cliquer sur le bouton !";
}
```


## Annuler le comportement par défaut de l'événement

Chaque événement a un comportement par défaut, comme par exemple quand on soumet un formulaire. On peut annuler ce comportement avec l'objet événement et la fonction `preventDefault()`

```javascript title="script.js" linenums="1" hl_lines="6"
const formulaire = document.getElementById("formulaire-inscription");

formulaire.addEventListener("submit", valideFormulaire);

function valideFormulaire(e) {
    e.preventDefault();
    // ...
}
```

## Sources

- [https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events){target=_blank}