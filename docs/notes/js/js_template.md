# Gabarit de fichier Javascript

Pour vous aider à structurer vos fichier JavaScript, voici un gabarit de départ que vous pouvez utiliser.

```javascript title="script.js" linenums="1"
// ====================================================
// =  Déclaration des variables globales              =
// ====================================================



// ====================================================
// =  Déclaration des événements                      =
// ====================================================



// ====================================================
// =  Code qui sera exécuté au chargement de la page  =
// ====================================================



// ====================================================
// =  Déclaration des fonctions                       =
// ====================================================
```

## Déclaration des variables globales

Au tout début on déclare les variables qui seront utilisées globalement dans le script. On va retrouver par exemple les éléments du DOM avec lesquels ont va interragir.

```javascript title="script.js" linenums="1"
const boutonSoumettre = document.getElementById('bouton');
```

## Déclaration des événements

Dans cette section on va faire la déclaration des évènements qui seront déclenchées lors d'interractions avec certains éléments du DOM.

```javascript title="script.js" linenums="1"
boutonSoumettre.addEventListener('clic', AfficherMessage);
```

## Code qui sera exécuté au chargement de la page

Le code des deux sections précédentes sera exécuté automatiquement au chargement de la page. Si on veut en ajouter on va le faire dans cette section

```javascript title="script.js" linenums="1"
console.log("Le script est chargé");
```

## Déclaration des fonctions

Finalement on va écrire ici les fonctions qui seront utilisées dans notre script.

```javascript title="script.js" linenums="1"
function AfficherMessage() {
    console.log("Hello world!");
}
```

L'exemple complet 

```javascript title="script.js" linenums="1"
// ====================================================
// =  Déclaration des variables globales              =
// ====================================================
const boutonSoumettre = document.getElementById('bouton');


// ====================================================
// =  Déclaration des événements                      =
// ====================================================
boutonSoumettre.addEventListener('clic', AfficherMessage);


// ====================================================
// =  Code qui sera exécuté au chargement de la page  =
// ====================================================
console.log("Le script est chargé");


// ====================================================
// =  Déclaration des fonctions                       =
// ====================================================

/**
 * Afficher un message à la console
 */
function AfficherMessage() {
    console.log("Hello world!");
}
```