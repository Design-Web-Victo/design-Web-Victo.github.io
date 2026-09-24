# Exercice 11 - Animation CSS

Votre équipe doit ajouter des animations dans la page internet d'un client. Il a vu trois animations sur le site d'un concurent et veut absolument que vous les intégriez dans son site. Comme vous êtes le petit nouveau de la boite, les autres développeurs vous donnent le choix de l'animation à développer. Mais commme vous devez encore faire vos preuves, l'équipe vous demande de faire un prototype de l'animation pour qu'ensuite on puisse l'intègrer dans le site.

## Consigne

- Faites votre choix parmi les trois types d'animation désirés
    1. Carte avec animation au survol
    2. Animation sur la bordure
    3. Animation au défilement de la page
- Consultez les ressources mise à votre disposition et décider de votre animation.
- Créez ensuite un prototype de l'animation selon les contraintes définies par le chargé de projet.
- Essayez le plus possible ==d'utiliser des sélecteurs de classe et d'id== pour une meilleure intégration dans le site du client.

!!! note

    - Assurez-vous de bien comprendre ce que vous faites et de ne pas juste copier-coller le code.
    - Aidez-vous de copilot, demandez lui des explications.
    - Un prototype est un petit projet simple qui démontre la faisabilité de la demande.

## Initialisation et remise

- Créez un nouveau projet nommé **dw_ex11_animation**
- Une fois terminé, créez compressez votre travail et remettez le dans un devoir Teams.

## Intégrité académique

Étant donné que vous allez grandement vous inspirer de code déjà créé, vous devez dans cette exercice ==citer vos sources==.

- Dans la balise `<head>` de votre page, ajouter dans une balise `<meta name="source">` le lien vers la ressource que vous avez utilisé (si vous avez plusieurs sources, ajoutez une balise <meta>` par source) : 

```html title="Exemple"
<meta name="source" content="Projet inspiré de https://scroll-driven-animations.style/demos/image-reveal/css/">
```

- Si vous emprunté seulement une section de code, citez la source en commentaire comme indiqué ici : [https://techinfo.profinfo.ca/code-emprunte/](https://techinfo.profinfo.ca/code-emprunte/){target=_blank}


## 1. Carte avec animation au survol

Votre client aimerait beaucoup présenter son équipe avec des cartes animées comme celle-ci : 

<p class="codepen" data-height="300" data-default-tab="result" data-slug-hash="MWpeqby" data-pen-title="Responsive Card Hover Effect" data-user="_niikhil" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/_niikhil/pen/MWpeqby">
  Responsive Card Hover Effect</a> by Nikhil (<a href="https://codepen.io/_niikhil">@_niikhil</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://public.codepenassets.com/embed/index.js"></script>

### Ressources

- [Responsive Card Hover Effect](https://codepen.io/_niikhil/pen/MWpeqby){target=_blank}

### Contraintes (critères de réalisation)

- [ ] Les cartes ont une dimensions de 300 X 300 pixels.
- [ ] Vous devez aussi créer un conteneur qui va contenir les cartes. 
- [ ] On peut ajouter un nombre x de cartes et les cartes supplémentaires qui n'entre pas dans le conteneur seront disposé sur une nouvelle ligne.
- [ ] Le client veut que la section avec le nom de la personne apparaisse sous l'image et que l'image soit déplacé vers le haut uniquement.
- [ ] Il aimerait aussi que vous ajoutiez sous le poste de la personne une ligne avec deux icônes centrés horizontalement: un icône vers le profile LinkedIn et un autre pour le courriel de la personne.
- [ ] Utilisez l'icône officiel de LinkedIn et un icône représentatif d'un courriel. Les icônes doivent être des fichiers images situés dans votre prototype.
- [ ] Ces icônes doivent diriger l'utilisateur vers l'url # pour LinkedIn et mailto:# pour le courriel.
- [ ] Dans le code démo, on utilise le mot-clé `@media`. Les développeurs vous mettent au défi de comprendre sont utilisation.
- [ ] Dans votre prototype, insérez une balise `<details>` avec en `<summary>` la question "À quoi sert le mot-clé @media" et ajoutez ==dans vos mots== la réponse dans la section détail.



## 2. Animation sur un bouton

Sur le site du client il y a une section où il présente ses produits avec une image et un lien pour en savoir plus. Il aimerait qu'ont ajoute une animation pour que chaque produit ressemble à ceci: 

<p class="codepen" data-height="300" data-default-tab="result" data-slug-hash="oBxKPx" data-pen-title="Draw borders from center!" data-user="flatking" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/flatking/pen/oBxKPx">
  Draw borders from center!</a> by Ben Sheppard (<a href="https://codepen.io/flatking">@flatking</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>


### Ressources

- [Draw border from center!](https://codepen.io/flatking/pen/oBxKPx){target=_blank}

### Contraintes (critères de réalisation)

- [ ] Remplacez l'image qui ne fonctionne pas dans la démonstration par une image de votre choix. Utilisez la propriété `background-size: cover;` pour qu'elle remplisse bien le cadre.
- [ ] Changer le texte du bouton pour "**Produit #1**" et quand on survole le bouton pour "**En savoir plus**"
- [ ] La couleur du bouton au survol doit avoir une transparence de 75%.
- [ ] Le temps d'animation au survol du bouton doit être de 500 millisecondes.
- [ ] Dans le code démo, on utilise `:before` et `:after`. Les développeurs vous mettent au défi de comprendre sont utilisation.
- [ ] Dans votre prototype, insérez une balise `<details>` avec en `<summary>` la question "À quoi sert les pseudo-classes before et after" et ajoutez ==dans vos mots== la réponse dans la section détail.


## 3. Animation au défilement de la page

Notre client veut ajouter dans une page l'historique de sa compagnie. Il aimerait que le texte soit agrémenté d'images et ajouter une animation sur les images.

!!! Danger "Attention"

    Les propriétés pour réaliser une animation au défilement uniquement en css ne sont pas encore disponible sur Firefox ([CanIUse](https://caniuse.com/?search=animation-timeline%3A%20scroll()){target=_blank}). Assurez-vous d'utiliser les navigateurs Edge ou Chrome.

### Ressources

- [Image qui apparait au défilement](https://scroll-driven-animations.style/demos/image-reveal/css/){target=_blank}

### Contraintes (critères de réalisation)

- [ ] Votre prototype doit comporter assez de texte pour permettre de voir l'animation sur les images. (Utilisez du [Lorem Ipsum](https://www.lipsum.com/){target=_blank})
- [ ] La section de texte avec les images doit avoir une largeur maximale de 800 pixels et être centrée sur dans la page
- [ ] L'alignement du texte doit être justifié
- [ ] Vous devez inclure 3 images différentes à votre prototype. Les images doivent occuper toute la largeur de la section de texte mais ne pas la déborder.
- [ ] L'animation sur les images est la même pour les trois. L'image doit apparaître de la gauche et ce positionner à l'endroit voulu dans le texte.
- [ ] Les images doivent aussi commmencer à une opacité de 0 et "apparaître" jusqu'à avoir une opacité de 100%.
- [ ] Utilisez une balise `<figure>` pour l'image et citez votre source dans une balise `<figcaption>`
- [ ] Dans le code démo, on utilise la propriété css `animation-timeline`. Les développeurs vous mettent au défi de comprendre sont utilisation.
- [ ] Dans votre prototype, insérez une balise `<details>` avec en `<summary>` la question "À quoi sert la propriété css animation-timeline?" et ajoutez ==dans vos mots== la réponse dans la section détail.

## Pour aller plus loin

C'est totalement optionnel mais voici des liens vers d'autres ressources que j'avais retenues pour cet exercice.

### Carte avec animation au survol

- [https://codepen.io/veronicadev/pen/WJyOwG](https://codepen.io/veronicadev/pen/WJyOwG){target=_blank}
- [https://codepen.io/yancy/pen/gBLLxz](https://codepen.io/yancy/pen/gBLLxz){target=_blank}
- [https://codepen.io/l-e-e/pen/MWoMpJp](https://codepen.io/l-e-e/pen/MWoMpJp){target=_blank}
- [https://codepen.io/hexagoncircle/full/XWbWKwL](https://codepen.io/hexagoncircle/full/XWbWKwL){target=_blank}

### Animation sur la bordure (aussi pour les boutons)

- [https://www.sliderrevolution.com/resources/css-border-animation/](https://www.sliderrevolution.com/resources/css-border-animation/){target=_blank}
- [https://www.youtube.com/watch?v=-VOUK-xFAyk](https://www.youtube.com/watch?v=-VOUK-xFAyk){target=_blank}
- [https://www.bram.us/2021/01/29/animating-a-css-gradient-border/](https://www.bram.us/2021/01/29/animating-a-css-gradient-border/){target=_blank}

### Animation au défilement

**Théorie**

- [CSS Tricks - Unleash the Power of Scroll-Driven Animations](https://css-tricks.com/unleash-the-power-of-scroll-driven-animations/){target=_blank}
- [Incredible scroll-based animations with CSS-only](https://www.youtube.com/watch?v=UmzFk68Bwdk){target=_blank}

**Démonstrations**

- [Barre de progression de lecture](https://scroll-driven-animations.style/demos/progress-bar/css/){target=_blank}
- [Image plein écran qui devient une entête fixe](https://scroll-driven-animations.style/demos/cover-to-fixed-header/css/){target=_blank}
- [Carte qui s'empile](https://scroll-driven-animations.style/demos/stacking-cards/css/){target=_blank}

