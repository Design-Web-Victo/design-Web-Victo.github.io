# Exercice 07 - La typographie

## Mise en place de l'exercice

- Dans cet exercice vous allez ajouter du style dans votre page sur un pays du monde (L'exercice 04). Il n'est pas nécessaire de faire une copie de votre projet, vous pouvez le modifier directement.
- Créez un dossier nommé **css** et dans ce dossier un fichier **style.css** où vous allez écrire votre code css.
- Reliez votre fichier css au fichier **index.html**

## Suppression de la liste numérotée

- Avant de commencer le travail supprimer la liste numérotée qui contient les 4 balises `<details>` de la section `<aside>`.
- Conserver les balises `<details>` ainsi que l'intégralité de leur contenu.

## Modification des polices

- Trouvez une police de caractère pour le titre `<h1>` (Le nom du pays).
- La police doit être téléchargée en fichier et ajoutée à votre projet dans le répertoire `assets/fonts/`.
- Créez un *Web Font* avec la propriété `@font-face` dans votre fichier css.
- Modifiez ensuite votre code pour que le titre h1 en haut de page utilise cette police.

---

- Trouvez maintenant une seconde police pour les sous-titre `<h2>` sur [Google Fonts](https://fonts.google.com/){target=_blank}
- Importez la police dans votre fichier css avec `@import`
- Ajoutez la classe `sous-titre` à toutes les balises `<h2>` de votre page (**En bref** et **Carte du pays**).
- Modifiez ensuite votre code pour que la classe `sous-titre` utilise cette police.

## Ajout d'un icône de Font Awesome

- Sur Font Awesome trouvez un icône de carte qui vous convient.
- Faites le nécessaire pour ajouter cet icône à l'intérieur de la balise `<h2>` du titre **Carte du pays**.

## Utilisation de variables

- Créez deux variables CSS qui contiendront un code de couleur.
- Utilisez la première variable pour modifier la couleur de tous les titres de la page (`<h1>` et `<h2>`).
- Utilisez la seconde couleur pour  modifier la couleur du deuxième titre `<h2>` uniquement. (**Carte du pays**).

## Styliser les `<details>`

- Ajouter du code CSS pour styliser à votre goût les balises `<details>` et leur contenu. (En conservant la couleur que vous avez appliqué au premier `<summary>`)
- Laissez aller votre côté artistique mais assurez-vous de comprendre les rêgles que vous ajoutez.
- Expérimentez en utilisant les propiétés `padding`, `marging` et `border`.

!!! help "Pour vous inspirer"

    Voici quelques articles intéressants qui pourraient vous aider 

    - [CSS-Tricks - Using & Styling the Details Element](https://css-tricks.com/using-styling-the-details-element/){target=_blank}
    - [Sitepoint - 20 Simple Ways to Style the HTML details Element](https://www.sitepoint.com/style-html-details-element/){target=_blank}
    - [LogRocket - Styling HTML &lt;details&gt; and &lt;summary&gt; with modern CSS](https://blog.logrocket.com/styling-html-modern-css/){target=_blank}