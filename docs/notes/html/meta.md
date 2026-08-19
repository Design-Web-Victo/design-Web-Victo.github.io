# La balise meta

La balise <meta> en HTML sert à fournir des métadonnées (informations sur la page) qui ne sont pas directement visibles par l’utilisateur, mais qui sont utilisées par les navigateurs, les moteurs de recherche et les réseaux sociaux. Elle peut être utilisée à plusieurs reprises dans la page, c'est dans ses attribut que l'on va définir l'information à envoyer.

La balise doit être utilisé à l'intérieur de la balise `<head>`.

```html title="Exemple d'utilisation de la balise meta"
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Découvrez nos meilleures recettes de cuisine maison.">
  <meta name="author" content="Mathieu Fréchette">
  <meta name="robots" content="index, follow">

  <!-- Open Graph pour réseaux sociaux -->
  <meta property="og:title" content="Mes Recettes Maison">
  <meta property="og:description" content="Des recettes simples et délicieuses pour tous les jours.">
  <meta property="og:image" content="https://monsite.com/images/recette.jpg">
  <meta property="og:type" content="website">

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">

  <title>Mes Recettes Maison</title>
</head>
```

<!-- Pour plus de détail sur la propriété og, consultez la page [Optimiser le référencement](../hebergement/web_referencement.md) -->

## Balises `<meta>` courantes et leur usage

| Balise                                      | Rôle / Usage principal                                                       |
|---------------------------------------------|-------------------------------------------------------------------------------|
| `<meta charset="UTF-8">`                    | Définit l'encodage des caractères (UTF-8 est le standard recommandé).         |
| `<meta name="description" content="...">`   | Fournit une description pour le référencement (SEO).                         |
| `<meta name="keywords" content="mot1, mot2">` | (Obsolète, peu utilisé) Liste de mots-clés pour les moteurs de recherche.     |
| `<meta name="author" content="Nom">`        | Indique l’auteur du site ou de la page.                                      |
| `<meta name="viewport" content="width=device-width, initial-scale=1.0">` | Assure un bon rendu sur les plus petits écrans, les cellulaires par exemple.                                          |
| `<meta name="robots" content="index, follow">` | Contrôle l’indexation par les moteurs de recherche (ex. : `noindex, nofollow`). |
| `<meta http-equiv="refresh" content="5; url=page.html">` | Redirige ou actualise la page après un délai donné.                          |
| `<meta property="og:title" content="...">`  | Titre pour l’aperçu sur les réseaux sociaux (Open Graph – Facebook, LinkedIn). |
| `<meta property="og:description" content="...">` | Description pour les réseaux sociaux.                                        |
| `<meta property="og:image" content="image.jpg">` | Image d’aperçu pour les réseaux sociaux.                                    |
| `<meta name="twitter:card" content="summary_large_image">` | Type d’aperçu pour Twitter.                                                  |

