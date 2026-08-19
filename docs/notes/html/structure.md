# Structure HTML5 d'une page web

Les fichiers qui composeront les pages de notre site web porteront l'extension html. Le fichier principale de votre site internet doit toujours porter le nom de `index.html`

Le code qui suit représente la structure de base d'une page web

```html
<!DOCTYPE html>
<html lang="fr">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Le titre de ma page</title>
  </head>
  <body>
    <p>Un paragraphe qui sera afficher à l'utilisateur</p>
  </body>
</html>
```

!!! astuce
    
    C'est une bonne idée de créer un extrait de code de la structure de base d'une page html, ça nous permet de ne pas avoir à tout réécrire à chaque fois. On peut également grâce à Emmet utiliser le raccourci ! qui nous donne aussi une structure de départ

Voyons plus en détail chacune de ces balises

**!DOCTYPE html**

Historiquement, cette balise servait à indiquer au navigateur quelle règles il devait utiliser pour bien afficher la page. On continue de l'inclure pour des questions de rétrocompatibilité. Cette balise ne doit pas être "fermée".

**html**

La page dans son ensemble. Toutes les autres balises html doivent se retrouver à l'intérieur de celle-ci. L'attribut `lang` sert à indiquer la langue utilisée dans la page.

**head**

On va ajouter ici tout ce qu'on inclure dans la page web mais qui ne sera pas visible par l'utilisateur. 

- Des mots-clé pour le référencement
- Des liens vers les fichiers css, javascript et autres librairies utilisées.

**meta**

La balise meta peut avoir de multiples utilisations selon les attributs qu'on lui donne. Elle est entre autre utilisé pour le référencement de nos site.


**title**

Pour définir le titre de la page, qui sera afficher dans l'onglet du navigateur.

**body**

C'est ici qu'on va placer le contenu de la page qui sera afficher par le navigateur et visible par l'utilisateur.
