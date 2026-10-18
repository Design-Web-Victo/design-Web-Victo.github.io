# Sélectionner un élément HTML en JS

On peut sélectionner un ou plusieurs élément HTML par différente fonction de l'objet **document**

Prenons pour exemple le html suivant
``````html
<div class="conteneur-horloge">
    <div id="affichage-date" class="boite"></div>
    <div id="affichage-heure" class="boite"></div>
</div>
``````

## getElementById()

Pour sélectionner un élément par son id on doit le passer en paramètre sous format texte ou avec une variable. La fonction retourne un HTLMElement (un objet qui "contient" l'élément HTML) sur lequel on peut ensuite travailler.

``````js
let affichageDate = document.getElementById('affichage-date');
``````

## getElementsByClassName()

Pour sélectionner un élément par sa classe on doit la passer en paramètre sous format texte ou avec une variable. La fonction retourne une collection d'éléments HTML (on peut le voir et l'utiliser comme ==un tableau==)

``````js
let listeBoites = document.getElementsByClassName('boite');

// Pour parcourir la collection on peut faire une boucle standard
for (let i = 0; i < listeBoites.length; i++) {
    console.log(listeBoites[i]);
}
// On peut aussi utiliser une boucle for simplifiée
for (let boite of listeBoites) {
    console.log(boite);
}
``````

## querySelector()
Retourne uniquement ==le premier résultat== correspondant à la requête sous la forme d'un HTMLElement. On peut utiliser les mêmes sélecteur qu'on a appris à utiliser en css.
``````js
/* Je sélectionne toutes les divs qui sont enfant de l'élément  
   avec la classe conteneur-horloge mais la fonction va me 
   retourner que le premier résultat */
let listeBoites = document.querySelector('.conteneur-horloge div');
``````

## querySelectorAll()
La même chose que pour querySelector mais retourne ==tous les éléments== correspondants sous forme de **NodeList** (un tableau)

``````js
/* Je sélectionne toutes les divs qui sont enfant de l'élément avec 
   la classe conteneur-horloge */
let listeBoites = document.querySelectorAll('.conteneur-horloge div');

// Je peux parcourir le résultat comme un tableau
for (let boite of listeBoites) {
    console.log(boite);
}
// mais aussi avec une boucle foreach
listeBoites.forEach(boite => {
    console.log(boite);
});
``````