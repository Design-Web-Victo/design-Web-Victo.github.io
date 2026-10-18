# Les conditions en JavaScript

Les conditions permettent d’exécuter du code seulement si une situation est vraie.

## Structure du if

**if**

```js title="Structure de base"
if (condition) {
  // instructions exécutées si la condition est vraie
}
```

```js title="Exemple"
let age = 18;

if (age >= 18) {
  console.log("Tu es majeur.");
}
```

**if ... else**

```js
let age = 15;

if (age >= 18) {
  console.log("Tu es majeur.");
} else {
  console.log("Tu es mineur.");
}
```

**if ... else if ... else**

```js
let temperature = 30;

if (temperature < 0) {
  console.log("Il gèle !");
} else if (temperature < 20) {
  console.log("Il fait frais.");
} else {
  console.log("Il fait chaud !");
}
```

## Les opérateurs de comparaison
| Opérateur | Signification                  | Exemple     | Résultat |
| --------- | ------------------------------ | ----------- | -------- |
| `==`      | égal à (valeur)                | `5 == "5"`  | ✅ vrai   |
| `===`     | égal à (valeur **et** type)    | `5 === "5"` | ❌ faux   |
| `!=`      | différent de (valeur)          | `5 != 3`    | ✅ vrai   |
| `!==`     | différent (valeur **et** type) | `5 !== "5"` | ✅ vrai   |
| `>`       | supérieur à                    | `7 > 3`     | ✅ vrai   |
| `<`       | inférieur à                    | `4 < 2`     | ❌ faux   |
| `>=`      | supérieur ou égal à            | `8 >= 8`    | ✅ vrai   |
| `<=`      | inférieur ou égal à            | `2 <= 5`    | ✅ vrai   |

!!! astuce

    Utilisez toujours `===` plutôt que `==` pour éviter les confusions de type.

## Les opérateurs logiques

| Opérateur | Signification| Exemple | Résultat|
| --------- | ------------ | ------- | ------- |
| `&&`      | ET (toutes les conditions doivent être vraies) | `(age >= 18 && age < 65)` | vrai si les deux sont vraies |
| `||` | OU (au moins une est vraie) | `(jour == "samedi" || jour == "dimanche")` | vrai si un des deux est vrai |
| `!`       | NON (inverse la condition)                     | `!(age >= 18)`            | vrai si l’âge est **inférieur à 18** |


```js title="Exemple"
let jour = "dimanche";

if (jour === "samedi" || jour === "dimanche") {
  console.log("C’est le week-end !");
} else {
  console.log("C’est la semaine.");
}
```

## Le if ternaire

L’opérateur ternaire est une façon courte d’écrire une condition if...else sur une seule ligne.

Il est très utile quand tu veux affecter une valeur ou afficher un message simple selon une condition.

```js title="Syntaxe"
condition ? valeur_si_vrai : valeur_si_faux
```

`?` signifie : “alors”
`:` signifie : “sinon”



### Exemple
```js title="Version if ... else"
let age = 20;
let message;

if (age >= 18) {
  message = "Majeur";
} else {
  message = "Mineur";
}

console.log(message);
```

```js title="Version avec le if ternaire"
let age = 20;
let message = (age >= 18) ? "Majeur" : "Mineur";
console.log(message);
```

**Quand utiliser le ternaire ?**

- [x] Quand la condition est simple
- [x] Quand tu veux affecter une valeur à une variable
- [x] Quand tu veux afficher un message court

**À éviter pour :**
 
- [ ] Les conditions complexes
- [ ] Les cas où plusieurs instructions doivent être exécutées

## L'instruction switch

L’instruction switch permet de tester plusieurs valeurs possibles d’une même variable.
C’est une alternative au if...else if...else quand on compare une même variable à plusieurs cas.

```js title="Syntaxe de base"
switch (variable) {
  case valeur1:
    // instructions exécutées si variable == valeur1
    break;

  case valeur2:
    // instructions exécutées si variable == valeur2
    break;

  default:
    // instructions exécutées si aucune valeur ne correspond
}
```

```js title="Exemple simple"
let jour = "mardi";

switch (jour) {
  case "lundi":
    console.log("Début de la semaine !");
    break;
  case "mardi":
    console.log("Deuxième jour de la semaine.");
    break;
  case "mercredi":
    console.log("Milieu de semaine !");
    break;
  default:
    console.log("Jour inconnu.");
}
```

### Importance de l'instruction break

Sans `break`, JavaScript continue d’exécuter les instructions des cas suivants, même si la condition n’est plus vraie.

```js title="Exemple sans break"
let fruit = "pomme";

switch (fruit) {
  case "pomme":
    console.log("C’est une pomme.");
  case "banane":
    console.log("C’est une banane.");
  default:
    console.log("Fruit inconnu.");
}
```

``` title="Résultat"
C’est une pomme.
C’est une banane.
Fruit inconnu.
```

Par contre on pourra vouloir utiliser la même instruction pour plusieurs conditions: 
```js title="Exemple de plusieurs conditions" hl_lines="4-5"
let jour = "samedi";

switch (jour) {
  case "samedi":
  case "dimanche":
    console.log("C’est le week-end !");
    break;
  default:
    console.log("C’est un jour de semaine.");
}
```

### À retenir

- `switch` compare une valeur exacte à plusieurs cas possibles.
- Chaque case doit se terminer par un break.
- Le default est facultatif, mais recommandé.
- C’est plus lisible qu’une longue série de if...else if.

## Exercices

- Dans le répertoire **js** votre projet **exercices_js**, ajoutez et liez le un fichier **condition.js**. 
- Commentez les liens vers les autres fichiers de script des exercices précédents.
- Réalisez les exercices suivants dans un fichier JS

**Exercice 1 : Majeur ou mineur**

!!! note "Tester si une valeur est un nombre entier"

    La fonctione `Number.isInteger()` prend en paramète une variable et retourne vrai si la valeur de la variable est un Integer.
    Vous pouvez l'utiliser directement dans une condition ou récupérer le résultat dans une variable.

    ```js title=""
    // Directement dans la condition du si
    if (Number.isInteger(age)) { 
      ... 
    }
    // En récupérant le résultat pour plus tard
    let isAgeValide = Number.isInteger(age);
    ```


- Créez une variable **age** et attribuez lui une valeur.
- Testez en premier si la valeur est un Integer et qu'elle est plus grande que 0, sinon affichez à la console le message "Age invalide"
- Affichez à la console "Tu es majeur." si age est plus grand ou égale à 18, sinon affiche "Tu es mineur."

**Exercice 2 : Pair ou impair**

- Utilisez un if ternaire pour cet exercice.
- Crée une variable nombre et assigniez lui une valeur entière.
- À l'aide de l'opérateur modulo (%) affiche
    - "Le nombre (nombre) est pair." si nombre % 2 === 0
    - Sinon "Le nombre (nombre) est impair."

**Exercice 3 : Note d’examen**

- Créez une variable note.
- Utilisez une structure `if...else if...else` pour afficher
    - "Excellent" si note >= 90
    - "Très bien" si note >= 75
    - "Bien" si note >= 60
    - "Échec" sinon.

**Exercice 4 : Température**

- Créez une variable temperature.
- Utilisez une structure `if...else if...else` pour afficher
    - "Il gèle" si temperature < 0
    - "Il fait frais" si temperature est entre 0 et 15 inclusivement.
    - "Température agréable" si temperature est entre 16 et 25 inclusivement.
    - "Il fait chaud!" sinon.

**Exercice 5 : Accès utilisateur**

- Créez deux variables :
    - connecte (true ou false)
    - role ("admin" ou "user")
- Affichez : 
    - "Bienvenue administrateur" si l’utilisateur est connecté et son rôle est "admin"
    - "Bienvenue utilisateur" si connecté et rôle "user"
    - "Bienvenue rôle inconnu" si role contient un autre valeur.
    - "Accès refusé" si non connecté.

**Exercice 6 : Menu d'options**

- À l'aide d'une structure switch
- Créez une variable choix.
- Affichez le résultat suivant selon la valeur de choix: 
    - 1 = "Nouvelle partie"
    - 2 = "Charger une partie"
    - 3 = "Quitter"
    - autre valeur = "Option invalide"

**Exercice 7 : Mois de l'année**

- À l'aide d'une structure switch
- Créez une variable mois (par exemple "janvier", "février", etc.).
- Affichez : 
    - décembre, janvier, février = "Hiver"
    - mars, avril, mai = "Printemps"
    - juin, juillet, août = "Été"
    - septembre, octobre, novembre = "Automne"
- Regroupez les conditions `case` qui sont similaire ensemble.
- Assurez-vous que ça fonctionne peu importe la case de mois (majuscule ou minuscule).

!!! Astuce ""

    Essayez d'intégrer la méthode [toLowerCase()](https://www.w3schools.com/jsref/jsref_toLowerCase.asp){target=_blank} à votre condition.

- [x] Quand vous aurez terminé l'exercice, créez un commit nommé "Exercices conditions" et envoyez-le sur GitHub (git push)