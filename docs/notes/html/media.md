# Intégration multimédia

## Insérer de l'audio avec la balise `<audio>`

Pour ajouter des fichiers audios à une page Web, utilisez la balise <audio>.

```html title="Syntaxe de base"
<audio src="musique.mp3" controls></audio>
```

**Attributs**

- `src` : chemin vers le fichier audio.
- `controls` : affiche les boutons de lecture, pause, volume, etc. Sans `controls`, l'interface pour contrôler le son sera invisible, on devra gérer son lancement en JavaScript.
- `autoplay` : Lance automatiquement la lecture. ==Ne pas utiliser==, maintenant la plupart des navigateurs bloquent cette fonctionalité.
- `loop` : Rejoue le fichier audio en boucle.

**Utilisation de plusieurs sources**

Pour assurer la compatibilité entre navigateurs, on peut fournir plusieurs formats audio : 

```html title="Exemple plusieurs sources"
<audio controls>
  <source src="musique.mp3" type="audio/mpeg">
  <source src="musique.ogg" type="audio/ogg">
  Votre navigateur ne supporte pas l'élément audio.
</audio>
```

## Insérer des vidéos avec la balise `<video>`

Elle permet d’intégrer des vidéos directement dans une page Web sans plugin externe (comme Flash auparavant). La balise fonctionne sensiblement comme la balise `<audio>`.

```html title="Syntaxe de base"
<video src="film.mp4" controls></video>
```

**Attributs**

- `src` : chemin vers le fichier vidéo.
- `controls` : affiche les boutons de lecture, pause, volume, etc. Sans `controls`, la vidéo sera invisible et l’utilisateur ne pourra pas la contrôler. On devra gérer son lancement en JavaScript.
- `autoplay` : Lance automatiquement la lecture. ==Ne pas utiliser==, maintenant la plupart des navigateurs bloquent cette fonctionalité.
- `loop` : Rejoue la vidéo en boucle.
- `poster` : Définit une image d’aperçu avant la lecture.
- `width` et `height` : Tout comme une image, on peut forcer une largeur et une hauteur à la vidéo.

**Utilisation de plusieurs sources**

Pour assurer la compatibilité entre navigateurs, on peut fournir plusieurs formats vidéo : 

```html title="Exemple plusieurs sources"
<video controls poster="./assets/images/aperçu.jpg" width="640" height="360">
    <source src="film.mp4" type="video/mp4">
    <source src="film.webm" type="video/webm">
    <source src="film.ogv" type="video/ogg">
    Votre navigateur ne supporte pas la balise vidéo.
</video>
```

- Le navigateur lit le premier format compatible en partant de la première ligne source.
- Si aucun format n'est compatible, il affichera le texte inscrit après les balises `<source>`



## Insérer du contenu avec `<iframe>`

La balise `<iframe>` est un élément HTML utilisé pour intégrer un autre document HTML dans la page web actuelle. Il s’agit d’une fenêtre qui affiche un autre site web ou un autre élément de contenu sans obliger le visiteur à quitter votre site. 

Les iframes sont utilisés à diverses fins telles que : 

- **Intégration multimédia** : Intégrez facilement des vidéos, de l'audio ou des animations provenant de plateformes telles que YouTube, etc. 
- **Inclure des cartes** : intégrez des cartes de services tels que Google Maps directement dans votre site. 
- **Chargement de formulaires et de widgets** : incorporez des formulaires ou des widgets provenant d'autres sources sans écrire de code complexe.

```html title="Exemple de syntaxe" hl_lines="2"
<iframe src="https://www.example.com" width="600" height="400" title="Exemple de page"></iframe>
```

**Attributs**

- `src` : Définit l’adresse du document à afficher.
- `width` et `height` : Définissent les dimensions de l’iframe (en pixels ou en %).
- `title` : Texte descriptif pour l’accessibilité (recommandé).

!!! Note

    Beaucoup de sites permettent de partager du contenu par un `<iframe>` qu'on peut copier et qui est souvent disponible dans les options de partage. 

### Intégration de vidéos Youtube

1. Trouvez la vidéo Youtube que vous voulez intégrer à votre site.
2. Cliquez sur le bouton **Partager** et ensuite **Intégrer**
3. Quelques options vous sont proposés et aussi le code `<iframe>` à utiliser
4. Copiez ce code dans votre page HTML.


## Sources

1. **`<audio>`**
    - [MDN - Audio](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/audio){target=_blank}
    - [Tutorial HTML - Audio](https://tutorialehtml.com/fr/html-audio/){target=_blank}
1. **`<video>`**
    - [W3Docs - Comment Insérer un Vidéo dans HTML](https://fr.w3docs.com/snippets/html/comment-inserer-un-video-dans-html.html){target=_blank}
    - [MDN - Vidéo](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/video){target=_blank}
2. **`<iframe>`**
    - [MDN - iframe](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/iframe){target=_blank}
    - [Geeks for Geeks - HTML Iframes](https://www.geeksforgeeks.org/html/html-iframes/){target=_blank}
    - [Comment intégrer du contenu à l’aide d’iFrames HTML](https://www.bluehost.com/fr/blog/quest-ce-quun-iframe-comment-integrer-du-contenu-a-laide-diframes-html/){target=_blank}
