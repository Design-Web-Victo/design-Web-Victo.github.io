# Bootstrap

Bootstrap est un *framework* CSS axé sur les composants. Il nous permet de rapidement créer un site *responsive* sans avoir trop de connaissance en css. On peut en effet arrivé à un résultat très décent sans écrire une seule ligne de css. Son utilisation se fait par des classes qu'on ajoute à nos élément. Je vous conseille fortement d'installer l'extension [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) pour ajouté à VSCode une complétion automatique des classes. Ce qui est génial avec cette extension c'est qu'elle fonctionne même avec nos propres fichiers css.

## Installation

Il y a plusieurs façon d'ajouter Bootstrap à nos projet, on va voir comment l'installer via le téléchargement des fichiers ou par CDN.

### Téléchargement des fichiers de styles

Téléchargez les fichiers "compilés" sur le site officiel de bootstrap : [https://getbootstrap.com/docs/5.2/getting-started/download/](https://getbootstrap.com/docs/5.2/getting-started/download/)

Copiez ensuite ces fichiers dans votre projet, préférablement dans un dossier css. Pour l'instant vous pouvez uniquement copier le fichier bootstrap.css. Vous devez ensuite faire une référence vers ce fichier avec la balise link dans le fichier html où vous voulez utiliser Bootstrap : 

``````html
<link rel="stylesheet" href="css/bootstrap.css">
``````

### Utilisation via CDN

Encore depuis le site officiel de Bootstrap, allez récupérer les urls de la section "Include via CDN" directement depuis la page accueil. Pour l'instant vous pouvez seulement utiliser le lien pour le css. Ajouter ensuite se lien dans la section head de votre fichier html.

``````html
<!-- CSS only -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-iYQeCzEYFbKjA/T2uDLTpkwGzCiq6soy8tYaI1GyVh/UjpbCx/TYkiZhlZB6+fzT" crossorigin="anonymous">

``````

Note : J'ai mis le liens plus haut qu'à titre d'exemple, il est toujours préférable d'aller chercher le liens le plus à jour.

### Avantages et inconvénients

En téléchargeant les fichiers css, on accélère l'utilisation de Bootstrap sur notre site mais on "alourdi" légèrement sa taille en terme d'espace disque. Un utilisant un CDN on télécharge les fichiers depuis un serveur distant, ça peut ralentir un peu l'affichage et on est dépendant de ce serveur. D'un autre côté on s'assure d'avoir une version la plus à jour et ça nous évite d'avoir à maintenir des fichiers supplémentaires pour notre site.

Un chose à faire attention, Bootstrap "reset" certaines propriétés des éléments html, comme par exemple la marge de la balise **body** qui est changé à 0px au lieu de 8px. Il est toujours préférable d'ajouter les liens vers Bootstrap <u>AVANT</u> les autres fichiers css. 

## Utilisation

Comme on disait plus haut, l'utilisation de Bootstrap se fait à l'aide de classes prédéfinis qu'on ajoute à l'élément qu'on veut "stylisé". Prenons par exemple les deux boutons suivants :

![bootstrap](../../assets/images/bootstrap.png) 

Le rendu est similaire à part pour la couleur. Voici le code html et css que j'ai utilisé pour les créés : 

**HTLM**

``````html
<button class="bouton-css">Bouton CSS</button>  
<button class="btn btn-primary btn-lg">Bouton bootstrap</button>          
``````

**CSS**

``````css
.bouton-css {
    border: none;
    border-radius: 0.5em;
    padding: 0.5em 1.5em;
    font-size: 1.2em;
    background-color: darkslateblue;
    color: white;
    cursor: pointer;
}

.bouton-css:hover {
    background-color: rgb(104, 92, 186);
    box-shadow: 0px 0px 5px gray;
}
``````

Comme vous pouvez le voir, aucune règle css n'a été requise pour créer mon bouton Bootstrap. C'est avec les trois classes ajoutées qu'il a été créé. (btn indique que c'est un bouton, btn-primary pour la couleur bleu et btn-lg pour avoir un plus gros bouton). Merveilleux non? On ne le vois pas dans ma capture d'écran mais il y a aussi un effet quand on survol le bouton. 

C'est une des forces de Bootstrap. En ajoutant quelques classes à un élément on peut rapidement le transformer en quelque chose de plus stylisé. Ça nous assure aussi une certaine conformité dans notre site: les composantes auront tous le même style. On a par contre moins de contrôle sur nos éléments. Si on a des modifications à faire c'est un peu plus compliqué. 

Alors si on veux rapidement créer un site qui "parait" bien sans trop se compliquer la vie avec le css, Bootstrap est une bonne solution. Si on commence à modifier un par un nos élément pour modifier le style que l'on veut donner à notre site on devrait peut-être revenir à du css "pure".

##  Les "breakpoints"

Bootstrap a été développé avec comme objectif de nous donner une méthode facile de créer des sites "responsive". Les breakpoints sont des valeurs prédéfinies qui représentent des largeurs en pixels. Vous vous rappeler quand on faisait des media query, on utilisait des dimensions en pixels avec min-width. C'est un peu le même principe avec les breakpoints. On peux souvent les ajouter à une classe bootstrap pour la rafiner.

**Liste des breakpoints**

![bootstrap02](../../assets/images/bootstrap02.png)

## Les conteneurs (container)

Un peu comme on l'a vu avec flexbox et grid, les conteneurs sont l'élément de base à utiliser quand on fait de la disposition avec Bootstrap. Il y a trois différent type de conteneur, représenté par les classes suivantes : 

- .container, sa largeur sera fixe et va dépendre de la dimension de l'écran.
- .container-fluid, sa largeur sera toujours de 100%
- .container-{breakpoint}, sa largeur sera de 100% tant que la dimension de l'écran ne dépassera pas la valeur du breakpoint. 

``````html
<div class="container-lg">
	...
</div>
``````

Vous pouvez voir un exemple en action ici : [https://getbootstrap.com/docs/5.2/examples/grid/#containers](https://getbootstrap.com/docs/5.2/examples/grid/#containers)

## Le système de grille

On peut utiliser avec Bootstrap utilise un système de conteneur, ligne et colonne pour faire la disposition de nos éléments. En plus, c'est flexbox :astonished: qui est utilisé "en dessous de la couverture". Pas de panique vous allez voir l'utilisation est quand même assez simple. On va utiliser des éléments div auxquelles ont va donner les classes appropriées. On commence par créer une div "conteneur", ensuite on crée une autre div qui va être la première ligne. Dans cette div on va créer le nombre de div égale au nombre de colonne voulue. La beauté de la chose est qu'on n'est pas obligé d'avoir le même nombre de colonne par ligne, chaque ligne est indépendante des autres.

Dans cette exemple je crée une ligne de 2 colonne et un autre de 3. Les deux lignes auront la même dimension en largeur, les cases de chaque ligne vont s'ajuster en conséquence.

``````html
<div class="container text-center">
  <div class="row">
    <div class="col">
      1 of 2
    </div>
    <div class="col">
      2 of 2
    </div>
  </div>
  <div class="row">
    <div class="col">
      1 of 3
    </div>
    <div class="col">
      2 of 3
    </div>
    <div class="col">
      3 of 3
    </div>
  </div>
</div>
``````

![bootstrap04](../../assets/images/bootstrap04.png)

Par défaut les colonnes se partageront équitablement l'espace disponible. On peut aussi définir des dimensions pour certaine ou toutes les colonnes. Chaque ligne est divisé en 12 parties égales. On peut attribuer à une colonne une valeur de 1 à 12 déterminant ainsi la proportion de l'espace que cette colonne va prendre, une valeur de 6 équivaut à 50% de la dimension totale par exemple. Si la somme de ces valeurs dépassent 12, les colonnes excédentaire vont déborder sur une  autre ligne.

``````html
<div class="container text-center">
	<div class="row">
        <div class="col-8">1 of 2</div>
        <div class="col-6">2 of 2</div>
	</div>
	<div class="row">
        <div class="col">1 of 3</div>
        <div class="col">2 of 3</div>
        <div class="col">3 of 3</div>
	</div>
</div>
``````

![bootstrap03](../../assets/images/bootstrap03.png)

On peut aussi spécifier un breakpoint à la classe ainsi qu'une valeur pour modifier les colonnes selon la dimension de l'écran.

``````html
<div class="container text-center">
    <div class="row">
        <div class="col col-md-4">1 of 2</div>
        <div class="col col-md-8">2 of 2</div>
    </div>
    <div class="row">
        <div class="col col-md-12">1 of 3</div>
        <div class="col col-md-6">2 of 3</div>
        <div class="col col-md-6">3 of 3</div>
    </div>
</div>
``````

ici tant que la dimension de l'écran ne dépassera pas 768px (le breakpoint md) les colonnes seront égales entre elles. Ensuite les proportions seront celle après le breakpoint.

![bootstrap05](../../assets/images/bootstrap05.png)

![bootstrap06](../../assets/images/bootstrap06.png)

Une dernière chose, j'ai dis plus tôt que le système de grille utilisait Flexbox. On peut donc se servir de ce qu'on a appris et l'appliquer ici à l'aide de classes Bootstrap.

``````html
<div class="container text-center">
    <div class="row">
    	<div class="col-4">Ligne 1</div>
    </div>
    <div class="row">
    	<div class="col-7">Ligne 2</div>
    </div>
    <div class="row">
        <div class="col-2">1 of 3</div>
        <div class="col-2">2 of 3</div>
        <div class="col-2">3 of 3</div>
    </div>
</div>
``````

![bootstrap08](../../assets/images/bootstrap08.png)

``````html
<div class="container text-center">
        <div class="row justify-content-center">
            <div class="col-4">Ligne 1</div>
        </div>
        <div class="row justify-content-end">
            <div class="col-7">Ligne 2</div>
        </div>
        <div class="row justify-content-between">
            <div class="col-2">1 of 3</div>
            <div class="col-2">2 of 3</div>
            <div class="col-2">3 of 3</div>
        </div>
    </div>
``````

![bootstrap07](../../assets/images/bootstrap07.png)

Voilà la base du système de grille de Bootstrap, pour aller plus loin consultez la documentation officielle ici : [https://getbootstrap.com/docs/5.2/layout/grid/](https://getbootstrap.com/docs/5.2/layout/grid/)



## Sources et références

- [https://getbootstrap.com/](https://getbootstrap.com/)