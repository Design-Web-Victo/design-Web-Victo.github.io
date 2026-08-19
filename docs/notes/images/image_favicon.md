# Les favicons

Un favicon (abréviation de "*favorite icon*") est une petite icône qui s’affiche dans l’onglet du navigateur, à côté du titre de la page. Il aide à identifier rapidement un site parmi plusieurs onglets ouverts.

## Quel est le format de fichier à utiliser?

Tout d'abord vous devez trouvez l'icône à utiliser.

- Le format classique est **.ico**, mais vous pouvez aussi utiliser des images au format **.png**, **.jpg** ou **.svg**.
- L'icône doit avoir une taille carré et être d'une dimension allant de 8x8 à 64x64 pixels. Une taille de 32x32 pixels est le standart actuel pour l'icône d'un onglet de navigateur.
- Traditionnellement le fichier est nommé `favicon.ico` et est situé à la racine du site web

## Intégration dans la page html

Dans la balise `<head>` nous allons ajouter le favicon à l'aide d'une balise `<link>`.

```html title="Exemple" hl_lines="6"
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demo classe</title>

    <link rel="icon" type="image/x-icon" href="./favicon.ico">
</head>
```
**Attributs**

- `rel="icon"` : Indique que le fichier est un icône.
- `type="image/x-icon"` : Indique le type du fichier. Dans cet exemple le fichier est de type ico. Pour un fichier png on utiliserait `type="image/png"`.
- `href="./favicon.ico"` : Le chemin relatif vers le fichier.

## Générateur de favicon

Pour vous permettre de créer facilement une icône de favicon: 

- [https://www.favicon.cc/](https://www.favicon.cc/){target=_blank}
- [https://favicon.io/](https://favicon.io/){target=_blank}
- [https://realfavicongenerator.net/](https://realfavicongenerator.net/){target=_blank}

## Source 

- [Formats de fichier acceptés et compatibilité](https://en.wikipedia.org/wiki/Favicon#Image_file_format_support){target=_blank}
- [Mettre un favicon en HTML : comment procéder ?](https://www.ionos.fr/digitalguide/sites-internet/web-design/comment-mettre-un-favicon-en-html/){target=_blank}
- [Qu’est-ce qu’un Favicon? Un Guide Complet](https://elementor.com/blog/fr/quest-ce-quun-faviconun-guide-complet-pour-creer-optimiser-la-petite-icone-de-votre-site-web/){target=_blank}
