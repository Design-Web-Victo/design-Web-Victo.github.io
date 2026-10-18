# Syntaxe du langage JavaScript

## Terminer une ligne de code

Chaque ligne de code doit se terminer par un point-virgule ( ; )! En fait ce n'est pas entièrement vrai. JavaScript est un langage assez permissif, et on peut ne pas en ajouter la plupart du temps sans créer d'erreurs.

``````js
// Ici les deux messages vont s'afficher même s'il n'y a pas de point-virgule
alert('Bonjour')
alert('tout le monde')
``````

Par contre, c'est une bonne pratique de toujours en ajouter, et ==je veux que vous le fassiez toujours==.

### Commentaires

Pour ajouter un commentaire sur une ligne, on utilise //. Pour les blocs de commentaires, on va plutôt utiliser `/* */`

``````js
// Commentaire sur une ligne
alert('Coucou!!');
/*
	Commentaire sur
	plusieurs lignes
*/
console.log('Hola');
``````

## Variables

### Déclaration et assignation

En JavaScript les variables n'ont pas de type. Pour déclarer une variable, il suffit d'utiliser le mot **let** ou **var** suivi du nom de la variable.

- **var** : Variable ayant une porté global et accessible à l'extérieur du bloc d'instruction où elle est déclarée
- **let** : Variable dont la porté est celle de son bloc d'instruction.

Pour aller plus loin : [https://laconsole.dev/blog/differences-let-var-const-js/](https://laconsole.dev/blog/differences-let-var-const-js/){target=_blank}

!!! Astuce

    Je vous conseille de toujours utiliser **let** pour déclarer une variable. Si vous voulez accéder à votre variable de manière plus globale, déclarez la au début de votre fichier de script à l'extérieur des fonctions.

```js

function test() {
	var variableVar = true;
	let variableLet = true;

	// Les deux variables sont accessible ici
}

// Seulement variableVar est accessible ici
```

Ensuite pour assigner une valeur à notre variable on va utiliser le symbole = suivi de la valeur. On peut aussi faire les deux étapes sur la même ligne.

``````js
// Déclaration d'une variable
let message;
// Assignation de la variable
message = 'Bonjour tout le monde';
// La même chose sur une ligne
let message = 'Bonjour tout le monde';

alert (message);
``````

Attention, **déclarer** une variable plus d'une fois avec let va provoquer une erreur.

``````js
let message = 'Bonjour';
let message = 'Au revoir'; // On va avoir une erreur de syntaxe ici
``````

Les variables n'ayant pas de type, on peut passer plusieurs types de valeurs à une même variable. Par contre ==ce n'est pas une bonne pratique== et on devrait l'éviter.

``````js
let message = 'Allo';
alert(message) // Va afficher Allo
message = 5;
alert(message * 2) // Va afficher 10;
``````

### Constantes

Une constante est une variable dont la valeur ne peut être changé après son assignation. On utilise le mot **const** pour la déclarer.

``````js
const COULEUR_ORANGE = '#ffaa00';

COULEUR_ORANGE = '#ffffff'; // Va provoquer une erreur
``````

### Bien nommer ses variables

Un nom de variable peut être composé de lettre, chiffre et des caractères $ et _. Le premier caractère ne doit pas être un chiffre. Si le nom de la variable comporte plus d'un mot, on va utiliser la notation [camelCase](https://fr.wikipedia.org/wiki/Camel_case){target=_blank} : on supprime les espaces, le premier mot en minuscule mais les suivants commenceront par une lettre majuscule. Attention, le nom de variable est aussi sensible à la case.

`````js
// Exemple de nom en camelCase
let nomEnCamelCase = 'Hallo!';
// Les deux variables sont différentes
let message = 'Message 1';
let messAge = 'Message 2';
`````

Pour les constantes, la norme veux qu'on mettre le nom entièrement en majuscule avec les différents mots séparés par un _ quand la valeur est "hardcodé" (attribué dans le code lors de la déclaration). Sinon on utilise le camelCase comme avec les variables.

``````js
// La valeur est ici hardcodé
const COULEUR_ORANGE = '#ffaa00';
// On assigne la constant avec le résultat de la fonction calculAge()
const monAge = calculAge(dateDeNaissance);
``````

En règle générale on doit éviter les noms de variable trop courts ou non significatifs.

``````js
// Le nom ne veut rien dire
let a = 'Mon titre';
// C'est beaucoup plus significatif avec ce nom
let texteTitre = 'Mon titre'
``````

## Concaténer du texte ou des variables

En JavaScript, on peut aussi mélanger du texte et des variables dans une même phrase. On peut le faire facilement avec l'opérateur +

```js
let prenom = "Mathieu";
let message = "Bonjour " + prenom + " !";
console.log(message); // Bonjour Mathieu !
```

JavaScript ne met pas d’espace automatiquement, vous devez les ajouter vous-même aux besoins
```js
let prenom = "Mathieu";
let message = "Bonjour" + prenom + "!";
console.log(message); // BonjourMathieu!
```

On peut concaténer plusieurs variables ensembles
```js
let prenom = "Mathieu";
let langage = "JavaScript";
let message = "Je m'appelle " + prenom + " et j'aime le " + JavaScript;
console.log(message); // Je m'appelle Mathieu et j'aime le JavaScript
```

### Attention aux types de données

Si vous concaténez un nombre avec du texte, JavaScript le transforme automatiquement en texte :
```js
let age = 45;
let message = "J'ai " + age + " ans";
console.log(message); // J'ai 45 ans
```

Si on additionne deux nombres, on doit s'assurer qu'ils ne sont pas exprimé comme du texte (entre guillement) : 
```js
console.log(10 + 5);    // 15
console.log("10" + 5);  // "105"  ← concaténation, pas addition
```

### Une version plus pratique de concaténer
Depuis la version ES6, JavaScript permet une façon plus simple et plus lisible de concaténer. On utilise des backticks (accent grave) et des interpolations ${variable}. C'est beaucoup plus facile à lire et à écrire

```js
let prenom = "Mathieu";
let age = 45;
console.log(`Bonjour, je m'appelle ${prenom} et j'ai ${age} ans.`);
```

## Exercices

- Dans le répertoire **js** votre projet **exercices_js**, ajoutez et liez le un fichier **syntaxe.js**. 
- Commentez les liens vers les autres fichiers de script des exercices précédents.
- Réalisez les exercices suivants dans un fichier JS

**Exercice 1 : Déclarer une variable**

- Déclare une variable prenom et donne-lui ton prénom.
- Affiche sa valeur avec console.log.

**Exercice 2 : Changer une valeur**

- Déclare une variable ville avec la valeur "Montréal".
- Modifie ensuite la valeur pour "Victoriaville".
- Affiche le résultat avant et après le changement.

**Exercice 3 : Types de valeurs**

- Déclare une variable age (nombre), une variable nom (texte) et une variable estConnecte (booléen).
- Affiche les trois valeurs à l'aide d'un seul [console.table()](https://www.w3schools.com/jsref/met_console_table.asp){target=_blank}
- En vous aidant du lien plus haut, utilisez un objet pour afficher les valeurs de vos variable (2e exemple)

**Exercice 4 : Utiliser une constante**

- Déclare une constante PI avec la valeur 3.1416.
- Essaie ensuite de changer sa valeur et observe l’erreur à la console.
- Au lieu de changer sa valeur, efface la dernière ligne et crée à la place une variable nommée circonference.
- Assigne cette variable avec la circonférence d'un cercle de 4cm de rayon.
- Utilise la constante PI pour ton calcul (petit rappel la formule est 2πr)
- Affiche le résultat à la console.
```js
console.log("La circonférence d'un cercle ayant un rayon de 4cm est : ", circonference);
```

**Exercice 5 : Concaténation**

- Déclare les variables nomEleve, prenomEleve et ageEleve sur la même ligne et assigne leur des valeurs.
- Affiche à la console la phrase `Je m'appelle [prenom] [nom] et j'ai [age] ans` en utilisant le symbole + pour concaténer.
- Affiche le même texte mais en utilisant des backticks.

- [x] Quand vous aurez terminé l'exercice, créez un commit nommé "Exercices syntaxe" et envoyez-le sur GitHub (git push)

