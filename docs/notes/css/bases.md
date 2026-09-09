# CSS

Le CSS (Cascading Style Sheet ou en français feuilles de style en cascade) est un langage utilisé principalement pour faire la mise en forme de pages HTML. Ses capacités ont évolué depuis son lancement et on peut aujourd'hui s'en servir à d'autre fin, par exemple animer des éléments de nos pages (ce qui était réservé au Javascript auparavant).

## Syntaxe

Une règle CSS consiste en un sélecteur et un bloc de déclaration formé d'une série de déclarations "propriété : valeur". Le bloc de déclaration début par une accolade {=={==} et est suivi par une série de déclarations séparées par un point-virgule. Elle se termine par la fermeture de l'accolade. 

Prenons l'exemple suivant 

```css
h1 {
	color: red;
    font-size: 5em;
}
```
Le sélecteur ici est la balise h1, donc la règle sera appliquée à toutes les balises h1 du fichier HTML. Ensuite dans le bloc de déclaration, la première ligne applique la valeur **red** à la propriété **color**, le texte dans les balises h1 sera de couleur rouge. Finalement la deuxième ligne indique d'augmenter la taille de la police à 5em, une valeur relative qui indique de l'augmenter de 5 fois la taille courante. (Nous verrons les unités de mesure CSS plus loin)

Quand le css est inclus en attribut directement dans la balise, on dit *inline*, la syntaxe est un peu différente. on indique seulement les paires propriétés-valeur sans spécifier de sélecteur et sans les accolades. L'attribut à utiliser est **style**.

La même règle que plus haut, mais directement ajouté dans la balise

```css
< h1 style="color:red;font-size:5em;" >
```

On peut ajouter des commentaires en encadrant notre texte par les symboles `/*` et `*/`

```css
/* Un commentaire sur une ligne */

/* Un commentaire sur 
plusieurs lignes */

h1 {
	color: red; /* Un commentaire à la fin d'une ligne */
}
```



## Comment et où l'inclure dans nos pages

Il existe trois méthodes pour ajouter des règles css à un fichier HTLM : 

- Par une fichier externe
- Avec la balise style
- Directement dans une balise HTML avec l'attribut style

### Feuille de style externe

Les règles sont inscrites dans un fichier portant l'extension **css**. C'est la méthode la plus commune et efficace d'inclure du css dans les pages web. Le fichier css peut être relié à plus d'un fichier html, ce qui facilite l'uniformité d'un site internet et évite beaucoup de répétition.

fichier **style.css**

```css
h1 {
	color: red;
    font-size: 5em;
}
```

On lie le ou les fichiers css au fichier HTML avec la balise **link** qu'on ajoute dans la balise **head**. L'attribut **href** donnera le chemin vers le fichier css et l'attribut **rel** indiquera vers quel type de ressource un fais le lien, ici stylesheet pour feuille de style.

```css hl_lines="7"
<head>
	<meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Mon portfolio</title>
    /* Le lien se fait ici */
    <link rel="stylesheet" href="styles.css"> 
</head>
```
Dans cette exemple, on lie le fichier styles.css à notre fichier HTML.

### Feuille de style interne

On peut aussi ajouter les règles directement dans le fichier HTML en utilisant la balise **style**. Pour plus de clarté et de lisibilité je vous suggère d'ajouter votre code à l'intérieur de la balise **head** mais on peut aussi l'ajouter n'importe où dans la page. 
```css
<head>
	<meta charset="utf-8">
    <title>Mon portfolio</title>
    /* Les règles css sont ajoutées ici */
	<style>
        h1 {
			color: red;
            font-size: 5em;
        }
	</style>
</head>
```

### Styles en ligne

La dernière méthode consiste à inclure les règles directement dans une balise html en utilisant l'attribut style. Cette méthode n'est à utiliser qu'en **dernier recours**, quand il n'y a vraiment pas d'autres alternatives. Le code est beaucoup plus difficile à maintenir et à uniformiser quand les règles sont déclarées de cette façon.

```css
<h1 style="color:red;font-size:5em">
```

## Les sélecteurs CSS

Un sélecteur est une expression qui cible une entité HTML sur laquelle on va appliquer des règles CSS. Comme nous l'avons vu dans la section syntaxe, le sélecteur est la première information défini quand on défini notre série de règles.

```css
	.hautPage { /* Le sélecteur est ici la classe hautPage */
		color: purple;
	}
```
Dans cet exemple, toutes les balises qui ont en attribut la classe "hautPage" seront affectées par la règle. 

On peut regrouper plusieurs sélecteurs qui partage les mêmes règles en les séparant par une virgule.

```css
h1, h2, .titre {
	font-size: 2em;
}
```
Dans cet exemple, toutes les balises h1, h2 ainsi que celle ayant en attribut la classe titre seront ciblées. **Attention**, si un des sélecteurs regroupés est invalide, la règle ne sera pas appliqué. *Ce qui veux dire que même les autres sélecteurs valides seront ignorés*. 

### Type de sélecteur

Il existe plusieurs type de sélecteurs qu'on peut classer en différents groupes. 

- Les sélecteurs de balise, de classe et d'id sont les plus communs et les plus simple à utiliser. 
- Les sélecteurs d'attribut qui nous permet de cibler un attribut précis dans une balise. 
- Les pseudo-classes et pseudo-éléments qui ciblent des éléments dans un état donné.
- On peut aussi combiner des sélecteurs pour préciser encore plus notre sélection.

Quelques exemples

```css
/* Sélecteur de balise */
h1 { ... }

/* Sélecteur de classe */
.titre { ... }

/* Sélecteur d'id */
#hautPage { ... }

/* Sélectionne toutes les balises img qui ont l'attribut alt */
img[alt] { ... }

/* Sélectionne toutes les balises input dont l'attribut type est égale à "text" */
input[type="text"] { ... }

/* La règle sera appliquée sur les balises img quand on les survole */
img:hover { ... }

/* La règle sera appliquée sur la première ligne de texte des balises p */
p::first-line { ... }

/* La règle sera appliquée sur la première lettre du texte des balises p */
p::first-letter { ... }

/* Sélectionne toutes les balises p dont le parent immédiat est une balise div */
div > p { ... }

/* Sélectionne toutes les balises p qui sont les déscentants d'une balise div */
div p { ... }
```

Pour plus de détails et d'exemples : 

- [https://www.w3schools.com/cssref/css_selectors.asp](https://www.w3schools.com/cssref/css_selectors.asp){target=_blank}
- [https://developer.mozilla.org/fr/docs/Learn/CSS/Building_blocks/Selectors#reference_table_of_selectors](https://developer.mozilla.org/fr/docs/Learn/CSS/Building_blocks/Selectors#reference_table_of_selectors){target=_blank}

## Ordre de priorité des règles

Quand plusieurs règles css ciblent le même élément HTML, et qu'en plus elles utilisent la même propriété CSS il y a un conflit. La résolution de ce conflit se fera selon la priorité des règles utilisées.

  Commençons par un exemple : 

```html
<!DOCTYPE html>

<html>

  <head>
    <meta charset="utf-8">
    <title>Le titre de ma page</title>

    <style>
        body {
            font-size: 14px;
        }
        p {
            font-size: 16px;
        }
        .titre {
            font-size  : 20px;
        }
    </style>

  </head>

  <body>
        <span class="titre">Priorité des règles CSS</span>
        <div>
            <p style="font-size: 12px;">De quel taille sera ma police??</p>
            <p>Et ici?</p>
            Et là?
        </div>
  </body>
</html>
```

La propriété font-size est utilisé dans 3 règles qui entre en conflit, notamment avec l'élément p. Êtes-vous capable de déterminé en lisant le code de qu'elle taille sera la police de chacun des paragraphes et du texte qui suit dans l'élément div?

Les priorités de résolution du conflit peuvent être résumé comme ceci : 

1. Utilisation du mot-clé !important après la priorité CSS
2. La spécificité du sélecteur CSS

### Le mot-clé !important

Une règle se terminant par le mot-clé !important aura toujours la plus haute priorité. S'il y a un conflit avec de multiples `!important`, alors on va utiliser ensuite la spécificité pour déterminer la priorité.

```html
<style>
	div {
		font-size: 16px !important;
		}
	.textePlusGros {
		font-size: 18px;
	}
</style>

<div class="textePlusGros">
	Voici mon texte.
</div>
```
Dans l'exemple suivant, en temps normal la règle avec le sélecteur `.textePlusGros` aurait préséance mais c'est la règle avec le sélecteur div qui sera appliquée à cause de l'utilisation de `!important`.

L'utilisation du mot-clé `!important` devrait être éviter le plus possible, c'est un mauvaise pratique. Ça "brise" les principes de base du CSS et rend le débogage plus difficile. 

### La spécificité du sélecteur CSS

Plus le sélecteur est précis, plus la priorité sera élevée. En partant de la priorité la moins élevée : 

| Sélecteur                                        | Exemple                       |
| ------------------------------------------------ | ----------------------------- |
| *                                                | *                             |
| Balise                                           | H1                            |
| Classe                                           | .maClasse                     |
| Id                                               | #monId                        |
| Directement dans un balise avec l'attribut style | p style="font-size: 12px;"    |

En réalité le calcul est beaucoup plus complexe mais on peut facilement s'en tenir à ce tableau.

