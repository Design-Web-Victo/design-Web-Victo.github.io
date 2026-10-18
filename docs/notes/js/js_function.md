# Les fonctions en Javascript

## Déclarer une fonction

Pour déclarer une fonction, un utilise la commande **function** suivi du nom de la fonction. Ensuite on peut accepter des paramètres dont on va indiquer le nom entre parenthèse. Les paramètres n'ont pas besoin d'avoir de type de données. On peut aussi retourner une valeur avec la commande **return**. Dès que la fonction rencontre une commande **return**, le traitement s'arrête et la valeur est retournée.

``````js
function maFonction(param1, param2) {
	// ...
	return resultat;
}
``````

## Assigner une fonction à une variable

On peut aussi stocker la fonction dans une variable. Dans ce cas la syntaxe reste la même mais on n'est pas tenu d'indiquer de nom de fonction.

```javascript linenums="1"
const maFonction = function (param1, param2) {
	// ...
	return resultat;
}
```

!!! danger "Attention"

	Si vous assignez une fonction à une variable, celle-ci doit être déclaré **avant** son appel, sinon vous aurez une erreur.

## Lancer une fonction

Pour lancer une fonction on utilise le nom de la fonction avec entre parenthèses les paramètres. S'il n'y a aucun paramètre on doit quand même utiliser des parenthèses vides. Quand la fonction retourne un résultat on peut récupérer directement le résultat dans une variable. On peut aussi se servir de la fonction directement dans une condition, comme par exemple si elle retourne une valeur booléenne.

```javascript title="script.js" linenums="1"
function test() {
	return true;
}

// Lance la fonction test
test();
// Récupère la valeur de retour de la fonction test
let valeurTest = test();
// Utilise la valeur de retour de la fonction test dans une condition
if (test()) {
	// ...
}
```

## Fonction de *callback*

En JavaScript il est très fréquent qu'une fonction demande en paramètre une deuxième fonction. On appelle ce type de fonction une fonction de *callback*. Un exemple qu'on voit fréquemment est la fonction `addEventListener` qui prend en paramètre le type d'événement à écouter et la fonction a exécuter quand l'événement est détecté. On va se servir de cette fonction pour illustrer la syntaxe. 

On peut utiliser le nom d'une fonction déclaré dans le script
```javascript linenums="1"
const monBouton = document.getElementById('btn');

function message() {
    console.log("Bonjour");
}

monBouton.addEventListener('click', message);
```

!!! Danger

	Vous remarquerez que j'ai appelé la fonction message sans paramètre ni parenthèse. En effet on doit uniquement donner le nom de la fonction sinon elle sera exécuté immédiatement au chargement du script.

On peut aussi déclarer la fonction directement dans le paramètre. On va privilégier ce cas quand la fonction n'aura pas a être exécutée ailleur dans le code. On peut même omettre le nom de la fonction. On va appeler ce type de fonction une fonction anonyme.

```javascript title="script.js" linenums="1" hl_lines="6"
monBouton.addEventListener('click', function () {
	console.log("Bonjour");
});
```

## Fonction fléchée (arrow function)

Il y a une autre syntaxe plus concise d'écrire une fonction, la fonction fléché. Avec cette syntaxe on doit assigner la fonction à une variable ou l'utliser comme fonction de *callback*. 

Le principe est simple: 

- On enlève la commande **function**
- On peut oublier le nom de la fonction s'il n'est pas utilisé.
- Les parenthères des paramètres sont obligatoire, même s'il n'y en a pas.
- Après les parenthèses on va utiliser le symbôle `=>` 
- Des accolades contiendront le code de la fonction.

```javascript title="script.js" linenums="1" hl_lines="6"
const message = () => {
	return "Bonjour!";
}

const somme = (nombre1, nombre2) => {
	return nombre1 + nombre2;
}

monBouton.addEventListener('click', () => {
	console.log(somme(2,2));
});
```

## Exercices

- Dans le répertoire **js** votre projet **exercices_js**, ajoutez et liez le un fichier **syntaxe.js**. 
- Commentez les liens vers les autres fichiers de script des exercices précédents.
- Réalisez les exercices suivants dans un fichier JS
- Vous devez documenter toutes les fonctions que vous allez créer : [Documenter les fonctions](http://localhost:8000/notes/js/js_qualite_code/#documenter-les-fonctions){target=_blank}

### Exercice 1

- Déclarer une fonction **log** qui va prendre en paramètre un texte et qui l'affichera à la console.
- Lancez cette fonction au chargement de la page HTML avec le texte de votre choix en paramètre.

### Exercice 2

- Créez une fonction **saison** qui prend en paramètre le nom d'un mois et qui retourne la saison correspondante.
- Réutilisez le code que vous avez fait à la question #7 des exercices sur les conditions.
- Sur une même ligne, affichez à la console la saison correspondante au mois d'octobre en utilisant votre fonction. (Vous pourriez aussi réutiliser la fonction **message**)

### Exercice 3

- Créez une fonction fléchée assigné à une variable **estMajeur** qui prend en paramètre un age et retourne `true` si l'age est supérieur ou égale à 18 ou sinon `false`.
- Ensuite utilisez la fonction dans une structure `if` qui affichera à la console "Vous pouvez entrer" si l'age est majeur.

### Exercice 4

- Dans la page **index.html**, ajoutez un bouton avec le texte "Salutation"
- Dans le fichier **syntaxe.js**, créez une fonction qui va demander avec `prompt()` le prénom et ensuite le nom de l'usager.
- Ensuite avec `alert()` affichez à l'écran le message `Bonjour [prénom] [nom]`.
- Quand on clique sur le bouton, lancez votre fonction.

!!! note

	Dans votre balise bouton, utilisez l'attribut `onClick` : `<button onclick="nomFonction()">`

- [x] Quand vous aurez terminé l'exercice, créez un commit nommé "Exercices fonctions" et envoyez-le sur GitHub (git push)

## Sources 

- [https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Functions](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Functions){target=_blank}
- [https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Functions/Arrow_functions](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Functions/Arrow_functions){target=_blank}