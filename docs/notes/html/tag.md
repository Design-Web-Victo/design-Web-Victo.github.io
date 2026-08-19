# Les balises HTML

## Syntaxe

Le langage HTML utilise des balises pour indiquer au navigateur de quelle façon afficher le contenu de la page. C'est l'élément de base de notre page web, les blocs légo qu'on utilise pour construire notre site. Une balise débute toujours par le caractère **<** suivi du nom de la balise. On peut ensuite ajouter des attributs à chaque balise, certain général et d'autre plus spécifique. 

Voici un exemple de syntaxe d'une balise avec des attributs : 

```html
<input type="text" id="nom" name="nom" value="Mathieu">
```

La balise se terminera par le caractère **>**.  Tout le contenu qui suivra sera affecté par cette balise. Pour chaque ouverture de balise, on doit ajouter un autre balise de fermeture. Pour ce faire on utilise le même mot clé mais précédé du caractère **/**.  Ex: 

```html
<h1>Le titre de ma page</h1>
```
Dans cette exemple le texte 'Le titre de la page' sera afficher comme un titre de niveau 1 parce qu'il est englober dans la balise **h1**.


Certaine balise n'ont pas besoin de fermeture, comme par exemple la balise **img** pour afficher une image : 
```html
<img src="avatar.jpg" alt="Une superbe photo de moi"> 
```

**Syntaxe sur plusieurs lignes**

On peut écrire une balise sur plusieurs lignes. C'est une syntaxe qu'on rencontre souvent quand une balise comporte plusieurs attributs. La norme veut qu'on utilise une indentation sur les lignes suivantes.

```html title="Syntaxe sur plusieurs lignes"
<img src="./images/montagne.webp" 
    alt="Paysage de montagne enneigée" 
    width="600" 
    loading="lazy">
```

## Les attributs

Un attribut est composé de son nom suivie du caratère = et de la valeur sous format texte (la valeur sera entouré par des apostrophes ou des guillemets). Dans l'exemple plus haut avec la balise img l'attribut **src** a la valeur `"avatar.jpg"`.

Chaque balise vient avec sa liste d'attributs. N'ayez crainte vous n'avez pas à les apprendres par coeur, c'est souvent les mêmes qu'on utilise et sinon une petite recherche google et c'est réglé. Les deux attributs qu'on va utiliser le plus, et qui sont communes à toutes les balises, sont **id** et **class**.

### id

```html
<div id="conteneur-principal"> ... </div>
```

L'attribut **id** sert à donner un identificateur unique à une balise. La valeur doit être une chaine de caractères (sans espace) ==unique== au document. Pour plus de précaution la valeur devrait être unique à tout votre site. On va surtout utiliser cet attribut en JavaScript et en CSS.

### class

```html
<h2 class="titre entete">Titre de section</h2>
```

L'attribut **class** permet de regrouper plusieurs balises ensemble. Au contraire de l'attribut **id**, la valeur peut être répété dans plusieurs balises et on peut même utiliser plus d'une valeur en séparant les mots par des espaces. Dans l'exemple plus haut, la balise h2 à la classe **titre** et **entete**. On va beaucoup utiliser **class** pour le CSS.

### Les attributs data

Une chose vraiment utile avec les attributs est qu'on peut en ajouter des personnalisés. Il suffit d'utiliser le préfix **data-** suivi du nom de l'attribut que l'on veut ajouter dans la balise de l'élément html.

HTML

``````html
<div data-key="65" class="note">
	...
</div>
``````

Ici on a ajouté un attribut data-key avec la valeur 65 à la balise **div**. L'intérêt est de stocker de l'information directement dans la balise qu'on peut ensuite récupérer en JavaScript.

