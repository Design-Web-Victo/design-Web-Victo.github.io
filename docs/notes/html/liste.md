# Les listes en HTML

Les listes permettent de présenter plusieurs éléments de façon structurée. En HTML, on distingue principalement **les listes à puces** et **les listes numérotées**.

## Liste à puces

Une liste à puces est utilisée lorsque **l'ordre des éléments n'a pas d'importance**.

On utilise la balise `<ul>` (*unordered list*).

Chaque élément de la liste est placé dans une balise `<li>` (*list item*).

```html title="Exemple"
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

Résultat :

<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>

!!! tip "À retenir"

    `<ul>` contient la liste et chaque élément est placé dans `<li>`.


## Liste numérotée

Une liste numérotée est utilisée lorsque **l'ordre des éléments est important**.

On utilise la balise `<ol>` (*ordered list*).

```html title="Exemple"
<ol>
    <li>Ouvrir Visual Studio Code</li>
    <li>Créer un fichier HTML</li>
    <li>Écrire le code</li>
    <li>Ouvrir la page dans un navigateur</li>
</ol>
```

Résultat :

1. Ouvrir Visual Studio Code
2. Créer un fichier HTML
3. Écrire le code
4. Ouvrir la page dans un navigateur


## Listes imbriquées

Une liste peut contenir une autre liste.

```html
<ul>
    <li>Développement web</li>
    <li>
        <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
        </ul>
    </li>
    <li>Programmation 1</li>
</ul>
```

Résultat :

<ul>
    <li>Développement web</li>
    <li>
        <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
        </ul>
    </li>
    <li>Programmation 1</li>
</ul>

Les listes imbriquées sont utiles pour représenter une **hiérarchie** ou des **sous-catégories**.


## Points importants à retenir

* `<ul>` crée une **liste à puces**.
* `<ol>` crée une **liste numérotée**.
* `<li>` représente **un élément de liste**.
* Une liste peut contenir une autre liste.

## Exemple complet

```html
<h2>Étapes pour créer une page web</h2>

<ol>
    <li>Créer le fichier HTML</li>
    <li>Ajouter le contenu</li>
    <li>Créer la feuille CSS</li>
    <li>Ajouter les styles</li>
</ol>

<h2>Langages utilisés</h2>

<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```
