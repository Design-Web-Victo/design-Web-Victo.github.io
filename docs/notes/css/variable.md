# Les variables CSS

On peut maintenant utiliser des variables nativement en css, aussi appelé *css custom properties*.

## Déclaration et utilisation

On va déclarer la variable comme on le fait avec n'importe quel propriété en css en utilisant deux tirets (--) suivie du nom de la variable.

``````css
--nom-variable: valeur-variable;
``````

ensuite on utiliser la fonction **var()** pour utiliser la valeur de la variable.

``````css
propriété-css : var(--nom-variable);
``````

Dans cet exemple la variable `--couleur-texte` contient une valeur de couleur. On utilise ensuite la variable pour modifier la couleur du texte des balises h1. 

``````css linenums="1"
:root {
    --couleur-texte: #6495ed;
}

h1 {
    color: var(--couleur-texte);
}
``````

!!! note

    **:root** représente l'élément "racine" de notre page, le plus haut niveau de visibilité pour notre variable. En effet l'endroit où est déclaré la variable importe sur ça visibilité. C'est les même règles qui s'appliquant pour la priorité des propriétés css.

``````css linenums="1"
body {
    color: var(--couleur-texte);
}

h1 {
    --couleur-texte: #dc143c;
    color: var(--couleur-texte);
}
``````

Dans cet exemple, je veux utiliser la variable **--couleur-texte** comme couleur de texte à tous les éléments de body, mais la variable est déclaré pour les balises h1, elle ne sera utilisable que dans les balises h1 (et ses enfants s'il y en a). 

On peut avec la fonction var() utiliser une valeur par défaut pour résoudre le problème rencontré ici, sinon la couleur du texte restera celle par défaut.

``````css linenums="1"
body {
    /* Si la variable n'est pas trouvé le texte sera rouge */
    color: var(--couleur-texte, red); 
}
``````
### Thème de couleur

Les variables CSS sont souvent utilisé pour créer facilement des thèmes de couleur. Dans cet exemple, on défini un style de base pour un bouton en utilisant des variables avec valeur par défaut. Ensuite on crée des classes pour facilement ajuster le style du bouton au besoin

<p class="codepen" data-height="500" data-default-tab="html,result" data-slug-hash="abPYvYL" data-editable="true" data-user="frechettemathieu" style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/frechettemathieu/pen/abPYvYL">
  Untitled</a> by Mathieu Fréchette (<a href="https://codepen.io/frechettemathieu">@frechettemathieu</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### Dans une animation

On peut utiliser aussi utiliser les variables dans les animations et les media queries

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="jzPRRL" data-editable="true" data-user="hamzaiqbal" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/hamzaiqbal/pen/jzPRRL">
  CSS Vars : Animations</a> by Hamza Iqbal (<a href="https://codepen.io/hamzaiqbal">@hamzaiqbal</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Source : [https://codepen.io/hamzaiqbal/pen/jzPRRL](https://codepen.io/hamzaiqbal/pen/jzPRRL){target=_blank}


## Ce qu'on ne peut pas faire

### Inscrire en texte le chemin d'accès à un fichier

Quand on veut mettre le chemin vers un fichier dans une variable, on doit utiliser la fonction url() avec en paramètre la destination comme valeur.

``````css linenums="1"
:root {
	--image-fond-invalide: 'img/mon_image.png';
	--image-fond-valide: url('img/mon_image.png');
}

body {
	background: url(var(--image-fond-invalide)); /* Commande invalide */
	background: var(--image-fond-valide); /* Commande valide */
}

``````

### Unité numérique

On ne peut pas définir un nombre comme unité et ensuite lui accolé le type d'unité

``````css
h1 {
	/* Invalide */
    --taille-police: 2;
	font-size: var(--taille-police)em;
}

h1 {
	/* Valide */
    --taille-police: 2em;
	font-size: var(--taille-police);
}
``````

On pourrait contourner le problème avec la fonction **calc()** qui nous permet d'effectuer un calcul et d'utiliser le résultat en valeur : 

``````css
h1 {
    --taille-police: 2;
	font-size: calc(var(--taille-police) * 1em);
}
``````

### Comme nom de sélecteur ou un nom de propriété

On ne peut pas mettre le nom d'un sélecteur ou d'une propriété dans une variable et ensuite l'utiliser

``````css linenums="1" hl_lines="7"
:root {
	--mes-titres: h1;
	--taille-police: font-size;
}

/* Invalide */
var(--mes-titres) {
	color: red;
}

/* Invalide */
h1 {
	var(--taille-police): 2em;
}
``````

### Dans les critères d'une media queries

On ne peut pas utiliser une variable dans la requête d'une media query.

``````css linenums="1" hl_lines="7"
:root
{
    --taille-ecran: 768px;
}
 
/* Non valide */
@media (min-width: var(--taille-ecran))
{
    ...
}
``````

### Ne pas assigner de valeur

Quand on initialise une variable, ==on doit absolument lui assigner une valeur==.