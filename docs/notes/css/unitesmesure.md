# Unités de mesure

Dans une page Web, de nombreux éléments cohabitent ensemble : du texte, des sections, des images, des couleurs, etc.   

Pour assurer une disposition intéressante, il faut apprendre à définir les dimensions de ces éléments. Pour ce faire, il faut choisir une propriété, une valeur et une unité de mesure. 

Il existe plusieurs types d'unités et chacune répond à un besoin très précis. En début de formation, nous sommes conscients qu'il peut être difficile de choisir la bonne unité, et c'est pour cette raison que nous accampagnons dans cet apprentissage.  

Voici les grands principes pour faire un choix judicieux. 

## Type d'unités

 * Unités absolues : elles sont utilisées pour définir une taille fixe, qui ne varie pas en fonction des autres éléments de la page. 
 * Unités relatives au texte: elles sont utilisées pour définir la taille d'un élément en fonction de la taille d'un élément textuel.
 * Unités relatives au viewport : elles sont utilisées pour permettre aux éléments de s'adapter à la taille de la fenêtre du navigateur (viewport).
 * Unités en pourcentage : elles sont utilisées lorsqu'on l'on désire adapter le contenu à la taille de son élément parent. 

### Unités absolues

Les valeurs des unités doivent être entières.

* **px** : Pixels, l'unité absolue la plus utilisée 
* **in** : Pouces
* **cm** : Centimètres
* **mm** : Millimetres
* **pc** : Picas
* **pt** : Points

```css title="Exemple"
.bouton {
    top: 10px;
    left: 20px;
}
```

### Unités relatives au texte

Les valeurs des unités peuvent être décimales

* **em** : Relatif à la taille de la police du parent immédiat
* **rem** : Relatif à la taille de la police de l'élément `HTML`, donc de la taille de la page.

```css title="Exemple"
.titre {
    padding: 0.5rem;
}
```

### Unités relatives au viewport

* **vh** : Hauteur de la zone d'affichage
* **vw** : Largeur de la zone d'affichage

```css title="Exemple"
.boite {
    height: 100vh;
}
```

### Unités en pourcentage

* %

```css title="Exemple"
.boite {
    width: 100%
}
```


## Sources:   
* [https://www.w3.org/Style/Examples/007/units.fr.html](https://www.w3.org/Style/Examples/007/units.fr.html){target=_blank}
* [https://developer.mozilla.org/fr/docs/Learn/CSS/Building_blocks/Values_and_units](https://developer.mozilla.org/fr/docs/Learn/CSS/Building_blocks/Values_and_units){target=_blank}
* [https://graphiste.com/blog/unites-mesure-css/](https://developer.mozilla.org/fr/docs/Learn/CSS/Building_blocks/Values_and_units){target=_blank}
* [https://www.codeur.com/tuto/css/unite-de-mesure-taille-px-em-rem/](https://www.codeur.com/tuto/css/unite-de-mesure-taille-px-em-rem/){target=_blank}
