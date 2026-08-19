# Balises de texte

Différentes balises html sont dédiées à la structure du texte et à sa mise en forme. Parcontre pour la mise en forme essayez de privilégier les styles css quand c'est possible.

## 1. Titres et structure

Ces balises définissent la hiérarchie et l’organisation du contenu.

| Balise        | Usage principal                                              |
|---------------|--------------------------------------------------------------|
| `<h1>` à `<h6>` | Titres et sous-titres, du plus important (`<h1>`) au moins important (`<h6>`). |

```html
<h1>Mon titre principal</h1>
<h2>Titre de section 1</h2>
<h3>Sous-titre</h3>
<h2>Titre de section 2</h2>
```

!!! Astuce

    Utiliser un seul `<h1>` par page, puis `<h2>`, `<h3>`, etc. pour structurer.

---

## 2. Paragraphes et sauts de ligne

| Balise | Usage principal                  | Exemple                         |
|--------|----------------------------------|---------------------------------|
| `<p>`  | Crée un paragraphe de texte.     | `<p>Ceci est un paragraphe.</p>` |
| `<br>` | Saut de ligne forcé (à éviter). | `Bonjour<br>Comment ça va ?` |
| `<hr>` | Saut de ligne avec ligne de séparation. | `Fin d'un texte<hr>Début d'une nouvelle section` |

!!! Astuce

    Au lieu de la balise `<br>` utilisez le css pour régler l'espacement entre les éléments

---

## 3. Texte en emphase et en importance

| Balise      | Usage principal                                                             | Exemple                                       |
|-------------|-----------------------------------------------------------------------------|-----------------------------------------------|
| `<strong>`  | Texte important (souvent en gras et interprété comme important par les lecteurs d’écran). | `<strong>Attention</strong> : ceci est crucial.` |
| `<em>`      | Texte en emphase (souvent en italique).                                     | `<em>Ce mot est souligné par l'intonation.</em>` |
| `<b>`       | Gras sans signification sémantique (visuel seulement).                      | `<b>Texte gras</b>` |
| `<i>`       | Italique sans signification sémantique (visuel seulement).                  | `<i>Texte en italique</i>` |
| `<mark>`    | Met en surbrillance du texte important ou à réviser.                        | `Ceci est <mark>important</mark>.` |

!!! Note

    Les balises `<b>` et `<i>` ne sont plus vraiment utilisées. Le css permet de faire la même chose en mieux.

---

## 4. Citations et références

| Balise        | Usage principal                                     | Exemple                                            |
|---------------|-----------------------------------------------------|----------------------------------------------------|
| `<blockquote>`| Citation longue avec retrait.                       | `<blockquote>Le web sémantique est l'avenir.</blockquote>` |
| `<q>`         | Citation courte en ligne (génère des guillemets).   | `<q>Le savoir, c'est le pouvoir.</q>`              |
| `<cite>`      | Indique une source ou référence (souvent en italique). | `<cite>Albert Einstein</cite>`                   |
| `<abbr>`      | Abréviation avec info-bulle.                        | `<abbr title="HyperText Markup Language">HTML</abbr>` |


```html title="Exemple de citation"
<blockquote>
  "La simplicité est la sophistication suprême."
  <cite>— Léonard de Vinci</cite>
</blockquote>
```

---

## 5. Autres balises utiles pour le texte

| Balise     | Usage principal                          | Exemple                          |
|------------|------------------------------------------|----------------------------------|
| `<code>`   | Représente du code informatique en ligne. | `<code>print("Hello")</code>`   |
| `<pre>`    | Conserve la mise en forme du texte (espaces, retours). | `<pre>Ligne 1\nLigne 2</pre>` |
| `<sup>`    | Exposant.                               | `x<sup>2</sup>`                  |
| `<sub>`    | Indice.                                 | `H<sub>2</sub>O`                 |
| `<small>`  | Texte moins important ou notes de bas de page. | `<small>Mentions légales</small>` |
| `<del>`    | Texte supprimé.                        | `<del>Ancienne version</del>`    |
| `<ins>`    | Texte ajouté.                          | `<ins>Nouvelle version</ins>`    |

