# Container Queries

Le  World Wide Web Consortium (W3C) est responsable d'établir les standards du Web, qui sont par la suite intégrés dans les navigateurs. 
En décembre 2021, le W3C a ajouté dans ses spécifications une fonctionnalité longtemps demandée des intégrateurs Web, le **Container queries**. 
Jusqu'à présent, les media queries permettaient de changer l'affichage selon la taille de l'écran seulement. Avec les **Container Queries**, il est désormais possible d'ajuster le style d'un élément **en fonction des propriétés de son conteneur, généralement sa taille.**

## Le principe

![css_container_queries](../../assets/images/css-containerqueries.png)

Source : [https://web.dev/cq-stable/](https://web.dev/cq-stable/){target=_blank}

## Utilisation des Container Queries


L'utilisation des Container Queries se déroule en 2 étapes:

1. Identification du conteneur parent
2. Interrogation des propriétés du conteneur


### 1. Identification du conteneur parent

Cette étape consiste à préciser dans le CSS qu'un élément dans la page aura un impact sur le style d'un autre élément qui est son enfant (imbriqué).
Cela se fait en créant un "contexte de confinement" (containment context). 

En des mots plus simples, il faut déclarer dans le CSS qu'on a un élément qui influencera le style d'un sous-élément. 
Cela s'effectue en utilisant la propriété **container-type** en lui donnant l'une des 3 valeurs possibles:

* **size** : La condition se basera les dimensions en ligne et en bloc du conteneur. Applique le confinement de la disposition, du style et de la taille au conteneur. *Utilité principale : pour changer le style d'un élément en fonction de la hauteur et la largeur du contenu de son conteneur*
* **inline-size** : La condition portera sur les dimensions en ligne du conteneur. Applique la disposition, le style et le confinement de taille en ligne à l'élément. *Utilité principale : pour changer le style d'un élément en fonction de la largeur du conteneur* 
* **normal** : la condition ne portera pas sur la dimension du conteneur, seulement sur les styles. *Contexte principal d'utilisation : pour définir un conteneur sans interroger ses dimensions.* 


``````html
<div id="conteneur">
  <article class="carte">
    Contenu de la carte ...
  </article>
  <article class="carte">
    Contenu de la carte ...
  </article>
</div>
``````

``````css hl_lines="2"
#conteneur {
  container-type: inline-size;
}
``````

#### Nommer le conteneur

On peut aussi nommer le conteneur parent pour faciliter la compréhension de ceux-ci dans le CSS et choisir lequel interroger lorsque les conditons s'appliquent avec la propriété **container-name** : 

```css hl_lines="3"
#conteneur {
  container-type: inline-size;
  container-name: liste-cartes;
}
```

Il existe aussi la propriété **container** qui nous permet de définir le nom et le type sur la même ligne 

```css hl_lines="2"
#conteneur {
  container: liste-cartes / inline-size;
}
```

Pour en savoir plus : [https://developer.mozilla.org/en-US/docs/Web/CSS/container-name](https://developer.mozilla.org/en-US/docs/Web/CSS/container-name){target=_blank}

### 2. Interrogation des propriétés du conteneur

Cette étape consiste à préciser les conditions qui redéfinieront le style d'un élément. Cette partie ressemble beaucoup aux Media Queries sauf que nous allons utiliser `@container` au lieu de `@media`

``````css
@container (width < 700px) {
  .carte h2 {
    font-size: 0.9em;
  }
}
``````

Pour ciblé notre container query uniquement sur un conteneur qu'on a nommé, on ajoutera le nom à la suite de `@container`

```css title="" hl_lines="1"
@container liste-cartes (width < 700px) {
  .carte h2 {
    font-size: 0.9em;
  }
}
```


#### Exemple 

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="oNJGeQw" data-editable="true" data-user="carinecroteau" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/carinecroteau/pen/oNJGeQw">
  Container - Exemple 1</a> by carinecroteau (<a href="https://codepen.io/carinecroteau">@carinecroteau</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Le contenu des 2 premières cartes (celles présentes dans le conteneur ayant la propriété *container-type: inline-size;*) changera de taille lorsque la largeur du conteneur sera inférieure à la taille spécifiée. 


#### Opérateurs logiques

Les opérateurs sont les mêmes que pour les Media Queries (**and**, **or** et **not**). 

``````css
@container (width > 400px) and (height > 400px) {
  /* Mon code css */
}

@container (width > 400px) or (height > 400px) {
  /* Mon code css */
}

@container not (width < 400px) {
  /* Mon code css */
}

``````

## Unités de mesure propres aux Container Queries

Des unités de mesure ont été ajoutées et peuvent être utilisées lorsque des Containers Queries sont définies dans le CSS : 

* cqw : 1% de la largeur du conteneur
* cqh : 1% de la hauteur du conteneur
* cqi : 1% de la dimension inline du conteneur
* cqb : 1% de la dimension block du conteneur
* cqmin : la plus petite valeur entre cqi et cqb
* cqmax : la plus grande valeur entre cqi et cqb

## Aller plus loin

Envie d'en apprendre davantage? Voici d'autres informations sur les Container Queries : 

* Bien que cette fonctionnalité ne soit pas encore entièrement supportée dans les navigateurs, une nouveauté en lien avec les Container Queries a été ajoutée récemment à la spécification CSS : les **Style Container Queries**.  Le principe permettra de cibler un conteneur selon la valeur d'une de ses propriétés. [https://developer.chrome.com/blog/style-queries/](https://developer.chrome.com/blog/style-queries/){target=_blank}.  
Pour voir un exemple en action : 
[https://developer.chrome.com/blog/style-queries/#weather-cards](https://developer.chrome.com/blog/style-queries/#weather-cards){target=_blank} 
  



## Sources

* [https://www.alsacreations.com/article/lire/1915-Les-Container-Queries-en-CSS.html](https://www.alsacreations.com/article/lire/1915-Les-Container-Queries-en-CSS.html){target=_blank}
* [https://web.dev/cq-stable/](https://web.dev/cq-stable/){target=_blank}
* [https://www.oddbird.net/2021/04/05/containerqueries/](https://www.oddbird.net/2021/04/05/containerqueries/){target=_blank}
* [https://developer.mozilla.org/fr/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/fr/docs/Web/CSS/Media_Queries/Using_media_queries){target=_blank}
* [https://caniuse.com/css-container-queries](https://caniuse.com/css-container-queries){target=_blank}
* [https://developer.mozilla.org/en-US/docs/Web/CSS/container-name](https://developer.mozilla.org/en-US/docs/Web/CSS/container-name){target=_blank}
* [https://developer.chrome.com/blog/style-queries/](https://developer.chrome.com/blog/style-queries/){target=_blank}
* [https://developer.chrome.com/blog/style-queries/#weather-cards](https://developer.chrome.com/blog/style-queries/#weather-cards){target=_blank}

