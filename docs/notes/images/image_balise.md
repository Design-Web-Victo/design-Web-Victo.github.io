# Différentes balises pour intégrer des images

Plusieurs balise HTML permettent d'insérer des images dans une page web. Gardez à l'esprit que peut importe la balise utilisée elle ne sert qu'à ajouter l'image dans la page. Le positionnement et la dimension seront réglés par le css.

## `<img>`

C'est la balise la plus couramment utilisée.

**Syntaxe de base**

```hmtl title="Syntaxe de base"
<img src="chemin/vers/image.jpg" alt="Description de l'image">
```

**Attributs de la balise `<img>`**

- `src` (requis) : chemin vers le fichier image (==toujours utiliser [un chemin relatif](../html/relative_path.md){trget=_blank}==)
- `alt` (requis) : texte alternatif affiché si l'image ne charge pas et lu par les lecteurs d'écran.
- `width` et `height` : définissent la largeur et la hauteur en pixels. Attention, si les deux valeurs sont données, l'image ne conservera pas ses proportions originales. Donc à moins d'être sûr vous pouvez utiliser qu'un des deux attributs. On peut exprimer la valeur en px ou seulement numériquement (300px ou 300).
```html
<img src="./photo.jpg" alt="Une photo" width="300">
```
- `title` : affiche une info-bulle au survol
```html
<img src="logo.png" alt="Logo de l'entreprise" title="Notre logo officiel">
```
- `loading="lazy"` : charge l'image seulement quand elle devient visible dans la fenêtre. Permet d'accélérer le chargement de la page.

??? info "L'attribut loading"

    L’attribut loading="lazy" sur la balise <img> permet de différer le chargement de l’image jusqu’à ce qu’elle soit proche d’apparaître dans la fenêtre de visualisation (viewport) de l’utilisateur.

    **Avantages :**

    - Améliore la performance de la page (chargement plus rapide).
    - Réduit la consommation de données, surtout sur mobile.
    - Utile pour les pages avec beaucoup d’images ou des images en bas de page.

    **Fonctionnement :**

    - Le navigateur ne télécharge l’image que lorsque l’utilisateur fait défiler la page et que l’image est sur le point d’être visible.
    - Cela aide à optimiser l’expérience utilisateur, surtout sur les sites avec beaucoup de contenu visuel.
    - Ne pas l'utiliser sur des images critiques pour le contenu principal de votre site, comme un logo en entête.

- `srcset` : Permet de spécifier plusieurs versions d'une même image (dimension variable) optimisées pour différentes résolutions ou tailles d'écran. On va spécifier un nom de fichier suivi d'une taille en pixels et d'un w qui exprime la taille maximal de l'écran pour utiliser cette image. Pour ajouter des images, on doit les séparer par des virgules.
```html
<img
  src="images/mountains-small.jpg"
  alt="Montagnes"
  srcset="
    images/mountains-small.jpg 400w,
    images/mountains-medium.jpg 800w,
    images/mountains-large.jpg 1200w
    "
>
```
Dans cette exemple, on donne trois images avec des tailles différentes. Si le navigateur à une largeur d'affichage de 1000 pixels, l'image affichée sera `mountains-large.jpg` car c'est elle qui à la largeur supérieur la plus proche. On doit quand-même toujours renseigner l'attribut `src` quand on utilise `srcset`. Elle sert de valeur par défaut si le navigateur ne supporte pas `srcset` ou si les fichiers listés dans srcset ne correspondent pas aux conditions. Pour plus de détail : [srcset: Optimiser le chargement des images en html](https://laconsole.dev/blog/attribut-srcset-optimiser-chargement-images-html#des-images-responsive-avec-lattribut-srcset){target=_blank}


--- 

```html title="Exemple complet"
<img src="./images/montagne.webp" 
       alt="Paysage de montagne enneigée" 
       width="600" 
       loading="lazy">
```

L'image `montagne.webp` situé dans le répertoire images sera d'une largeur de 600 pixels et le navigateur la chargera uniquement quand elle sera visible à l'écran. Le texte alternatif est `Paysage de montagne enneigée`. 

## `<figure>` et `<figcation>`

`<figure>` est une balise sémantique qui sert à regrouper une image à une légende (avec la balise `<figcaption`). Tout comme les autres balises sémantique, c'est une bonne pratique pour améliorer le référencement et l'accessibilité.

La légende n'est pas obligatoire, on peut utiliser `<figure>` seule avec la balise `<img>`.

```html title="Exemple d'utilisation"
<figure>
  <img src="montagne.jpg" alt="Montagne enneigée">
  <figcaption>Vue panoramique des Alpes en hiver.</figcaption>
</figure>
```

## `<picture>`

La balise `<picture>` en HTML est utilisée pour offrir des images adaptatives (responsive) en fonction de différents critères comme la taille de l'écran. Elle permet de spécifier plusieurs sources d'images et de laisser le navigateur choisir la plus appropriée. Le navigateur évalue les conditions de la première balise `<source>`. Si elles sont remplis, c'est cette image qui sera utilisé, sinon on passe à la ligne suivante. Si aucune conditions ne peut être satisfaites, l'image de la balise `<img>` sera utilisée.

**Fonctionnement de la balise `<picture>`**

Structure de base :

- La balise `<picture>` contient une ou plusieurs balises <source> suivies d'une balise <img>.
- Les balises `<source>` définissent des images alternatives avec des attributs comme media (requêtes CSS) ou type (format d'image).
- La balise `<img>` agit comme une image de secours (fallback) si aucune des sources ne correspond.

Attributs de la balise `<source>`:

- media : Permet de spécifier une condition (comme une largeur d'écran) pour utiliser une image particulière.
- type : Permet de spécifier le format de l'image (par exemple, image/webp).
- srcset : Définit une ou plusieurs sources d'images avec des résolutions différentes.

```html title="Exemple d'utilisation"
<picture>
    <source srcset="image-large.webp" media="(min-width: 800px)" type="image/webp">
    <source srcset="image-large.jpg" media="(min-width: 800px)">
    <source srcset="image-small.webp" type="image/webp">
    <img src="image-small.jpg" alt="Description de l'image">
</picture>
```

Explication de l'exemple :

- Si l'écran a une largeur minimale de 800px et que le navigateur supporte le format WebP, l'image image-large.webp sera utilisée.
- Si l'écran a une largeur minimale de 800px mais que le format WebP n'est pas supporté, image-large.jpg sera utilisée.
- Si aucune des conditions précédentes n'est remplie, le navigateur utilisera image-small.webp (si WebP est supporté) ou image-small.jpg comme solution de secours.

!!! success "Avantages"

    - Permet d'optimiser les performances en chargeant des images adaptées à l'appareil.
    - Améliore l'expérience utilisateur en affichant des images de meilleure qualité sur des écrans haute densité.
    - Offre une compatibilité avec différents formats d'image (comme avec le format WebP).

!!! failure "Désavantages"

    - Peut être plus compliqué à utiliser qu'un combinaison de la balise `<img>` et de règles CSS.
    - Le code devient plus difficile à maintenir si on a plusieurs `<picture>` dans notre site.