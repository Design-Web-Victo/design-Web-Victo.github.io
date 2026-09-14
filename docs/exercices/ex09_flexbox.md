# Exercice 09 - Page avec Flexbox

## Mise en place de l'exercice

- Dans cet exercice vous devez reproduire la disposition de ce site : [https://www.wimpdecaf.com/](https://www.wimpdecaf.com/){target=_blank}. Lisez bien les indications plus bas, ce n'est pas tout le site qui est à reproduire.
- Clonez le projet de départ avec le lien Github Classroom que votre enseignant vous fournira.
- Vous avez déjà un fichier html avec un début de structure et un fichier css avec des variables à utiliser.
- J'ai divisé l'exercice en deux parties, je vous conseille de les réaliser une à la suite.

## Valeur par défaut de la page

- Conservez les valeurs qui sont déjà présentes dans le fichier CSS
- La police par défaut de la page est [Roboto Regular](https://fonts.google.com/specimen/Roboto){target=_blank}, téléchargez la sur Google Font et insérez la dans votre page à l'aide d'une *Web Font*;
- La couleur du texte est dans la variable `--couleur-texte`

## Partie 1 - L'entête de la page

<figure markdown>
  ![Entête](../assets/images/ex09_entete.png){.center .shadow}
  <figcaption>Aperçu de l'entête</figcaption>
</figure>

- L'entête est un élément `<header>` et elle à une hauteur fixe défini par la variable `--hauteur-entete`
- Utilisez la variable `--color-bg` pour la couleur de fond de l'entête.
- Utilisez la variable `--border-radius` pour régler les coins arrondis.
- Les éléments de l'entête doivent tous être centrés verticalement.
- Divisez votre entête en trois section : 
  - L'image de logo à gauche
  - Une section `<nav>` au centre
  - 2 icônes à droite.
- Utilisez **Flexbox** pour bien disposer les trois sections (Utilisez les propriétés qui vous semblent les plus appropriées)

<figure markdown>
  ![Division Flexbox de l'entête](../assets/images/ex09_entete_flexbox.png){.center .shadow}
  <figcaption>Division Flexbox de l'entête</figcaption>
</figure>

### L'image de logo

- L'images **Logo.svg** est disponible dans le répertoire `./assets/images/`
- Elle doit avoir une hauteur de 50px.

### Le menu

- Pour la section menu, utilisez une liste à puce pour les 4 items (*Decaf Menu*, *The Blog*, *Why Decaf* et *FAQs*)
- Ensuite à l'aide de Flexbox que vous appliquerez sur la balise `<ul>` alignez les items et enlevez la puce avec une règle CSS.
- Les 4 items sont des liens hypertextes qui pour l'instant ont l'url **#**.
- Utilisez le SVG de flèche présent dans le fichier **index.html** pour la flèche à droite de *Decaf Menu*. Elle fait aussi partie du lien hypertexte.
- Créez une classe CSS qui aura l'unique rôle de mettre le texte en caractère gras. 
- Appliquez cette classe au premier item du menu.

### Les icônes

- Les deux icônes sont des SVG qui sont déjè en commentaire dans le fichier **index.html**.
- Tout comme les items du menu, ce sont des liens hypertextes avec l'url **#**.
- Assurez vous qu'ils soient centrés verticalement et espacés convenablement entre eux.

## Partie 2 - La section principale

<figure markdown>
  ![Section principale](../assets/images/ex09_main.png){.center .shadow}
  <figcaption>Aperçu de la section principale</figcaption>
</figure>

- Cette section à une hauteur de 80 Viewport Heigth
- Elle est divisé en deux plus petites section, la vidéo et l'autre avec du texte.
- Utilisez Flexbox pour aligner ces deux sections côtes-à-côtes.
- La vidéo à une largeur de 35 Viewport Width et la section texte occupe tout l'espace restante.
- Utilisez les variables `--border-radius` et `--color-bg`.

### La vidéo

- La vidéo `background_video.mp4` est disponible dans le répertoire `./assets/videos/`
- Utilisez la balise `<video>` avec les attributs `loop`, `muted` et `autoplay``.
- Elle doit occuper l'entièreté de sa section.

### Le texte

- Tous les éléments de cette section sont centrés horizontalement et verticalement.

#### Le titre "Rethink Decaf"

- Utilisez la police `ObviouslyVariable` déjà définie dans le fichier css.
- Pour formatez le texte, j'ai utilisé les propriétés suivantes: `font-size`, `font-weight`, `font-stretch` et `line-height`. Expérimentez pour essayer de reproduire sensiblement le même résultat.

#### La note d'évaluation

- Les 5 étoiles sont un même SVG disponible dans le fichier **index.html**
- La taille de la police est de `1.25rem`

#### Le bouton

- La couleur de fond est `--color-bouton` et pour le texte utilisez `--color-bg`.
- Utilisez une balise `<button>` ou une balise `<a>` pour simuler le bouton.
- Le curseur de la souris devient une main quand on est sur le bouton.

<figure markdown>
  ![Résultat final](../assets/images/ex09_final.png){.center .shadow}
  <figcaption>Résultat final</figcaption>
</figure>
