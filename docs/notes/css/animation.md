# Animation CSS

Il est possible de rendre nos sites web un peu plus attrayant en ajoutant de l'animation en css. On va utiliser deux propriétés qui travaille main dans la main : la **transition** et la **transformation**.

## La transition

La transition s'occupe de créer une animation fluide durant la transformation. Sans transition, les effets de la transformation seraient immédiat.  On utilise souvent la transition et la transformation conjointement, mais elle peut aussi être utilisé seule. Par exemple on veut changer la couleur d'un bouton quand on le survole avec la souris (:hover). Appliquer une transition va rendre le changement de couleur plus fluide, en effectuant un dégradé d'une couleur vers l'autre.

On peut appliquer les propriétés suivantes à la transition : 

- transition-property {==(requise)==}
- transition-duration {==(requise)==}
- transition-timing
- transition-delay

!!! Astuce

    Il existe aussi une propriété "raccourci" qui englobe ces 4 propriétés, **transition**.

    ```css
    .bouton {
        transition: [property] [duration] [timing-function] [delay];
    }
    ```

### Transition-property

Permet de spécifier sur quelle propriété css la transition va être appliqué. On peut utilser la valeur **all** pour appliquer la transition sur toutes les propriétés.

``````css
.bouton {
    /* On applique la transition sur toutes les propriétés */
	transition-property: all;
    /* Ici elle sera appliqué uniquement sur le changement de couleur de fond */
	transition-property: background-color;
}
``````

Si on veut appliquer la transition ==sur une ou plusieurs propriétés mais pas toutes==, on va utiliser la commande raccourci **transition** en séparant chaque propriété par une virgule

``````css
transition: propriete1 300ms, propriete2 300ms;
``````

### Transition-duration

On défini avec transition-duration la durée de la transition. Elle peut être exprimé en millisecondes ou en secondes.

``````css
.bouton {
	transition-duration: 700ms;
}
``````

### Transition-timing-function

Permet de définir la vitesse de la transition par rapport à sa durée. Par défaut la valeur est **ease**:  la transition débute tranquillement, accélère et ralenti vers la fin. Il y a plusieurs valeurs possible, je vous laisse les explorer. Mais à moins de besoin précis, habituellement on peut laisser la valeur par défaut.

``````css
.bouton {
    /* La transition va aller en s'accélérant */
	transition-timing-function: ease-in; 
}
``````

Pour plus d'information sur la propriété : [https://developer.mozilla.org/fr/docs/Web/CSS/transition-timing-function](https://developer.mozilla.org/fr/docs/Web/CSS/transition-timing-function){target=_blank}

### Transition-delay

Permet de retarder le début de la transition. La valeur peut être exprimé en millisecondes ou en secondes.

``````css
.bouton {
	/* La transition va commencer après 1 seconde */
	transition-delay: 1s;
}
``````



## La transformation

On peut transformer nos éléments facilement avec la propriété css **transform**. Les quatres transformations possibles sont la rotation, le déplacement, la déformation et l'agrandissement/diminution, respectivement `rotate`, `translate`, `skew` et `scale`.

### Rotate

Effectue une rotation de l'élément en spécifiant une valeur en degré. La valeur peut être positive pour une rotation dans le sens horaire ou négative pour un sens anti-horaire.

``````css
.bouton:hover {
    /* Effectue un tour sur lui-même dans le sens horaire */
	transform: rotate(360deg);
    /* Effectue un tour sur lui-même dans le sens anti-horaire */
	transform: rotate(-360deg);
}
``````

### Translate

Déplace l'élément selon une valeur sur l'axe des x et l'axe des y. Une valeur positive à x déplace l'élément vers la droite et vers la gauche pour une valeur négative. Une valeur négative à l'axe des y déplace l'élément vers le haut et vers le bas pour une valeur positive. On peut utiliser les propriétés suivantes pour effectuer la translation. 

- translateX(valeurX)
- translateY(valeurY)
- translate(valeurX, ValeurY) 

La valeur peut être exprimé en pixels ou bien en poucentage. Quand elle est en pourcentage, elle représente le poucentage de la taille de l'élément. Par exemple si mon bouton à une largeur de 600 pixels et que je lui donne 50% comme valeur de x, le bouton sera déplacé de 300 pixels vers la droite sur l'axe des x.

``````css
.bouton:hover {
    /* Le bouton sera déplacé de 400 pixels vers la droite */
    transform: translateX(400px);
    /* Le bouton sera déplacé de 1 fois et demi sa hauteur vers le haut */
    transform: translateY(-150%);
    /* Le résultat sera le même que les deux lignes précédentes */
	transform: translate(400px, -150%);
}
``````

### Scale

On peut avec scale aggrandir ou diminuer un élément. La valeur est un poucentage exprimé par un nombre décimal positif, 1 étant la taille actuelle de l'élément. Donc les valeurs de 0 à 0.99 diminueront l'élément alors que les valeurs supérieures à 1 l'augmenteront. On peut utiliser les propriétés suivantes : 

- scaleX(valeurX)
- scaleY(valeurY)
- scale(valeurXY)
- scale(valeurX, valeurY)

``````css
.bouton:hover {
	/* Élargis de 2x horizontalement */
	transform: scaleX(2);
	/* Élargis de 2x verticalement */
	transform: scaleY(2);
	/* Élargis de 2x horizontalement et verticalement */
	transform: scale(2);
	/* Élargis de 2x horizontalement et verticalement */
	transform: scale(2,2);
}
``````

### Skew

La propriété skew sert à incliner l'élément selon l'axe des x et des y. Tout comme rotate et translate, une valeur négatif déplace à gauche pour les x ou en haut pour les y, alors qu'une valeur positive inclinera à droite pour les x et en bas pour les y. On peut utiliser les propriétés suivantes :

- skewX(valeurX)
- skewY(valeurY)
- skew(valeurX, valeurY)

``````css
.bouton:hover {
	/* Incline de 25 degrées vers la gauche */
	transform: skewX(-25deg);
	/* Incline de 25 degrées vers le bas */
	transform: skewY(25deg);
	/* Incline de 25 degrées vers la droite */
	transform: skew(25deg,0);
}
``````

### Transform-origin

Par défaut, la transformation de l'élément s'effectue à partir du centre de celui-ci. On peut modifier ce comportement avec la propriété `transform-origin`. On donne deux valeurs à la propriété, la position de l'origine sur l'axe des x et sur l'axe des y. On peut exprimé les valeurs en pourcentage, qui représente la dimension de l'élément (0% correspond à l'extrème gauche alors que 100% la droite de l'élément). On peut aussi utiliser les mots-clés left, right, top, bottom, center. Sinon les autres unités de mesure CSS sont acceptés. Cette propriété doit être définie au même niveau que la transition.

``````css
.bouton {
	transform-origin: left bottom;
	/* Cette ligne est égale à la précédente*/
	transform-origin: 0% 100%;
    transition: all 1s; 
}
``````

## Des animations plus évoluées avec @keyframes

Avec la commande `@keyframe` ont peut aller beaucoup plus loin qu'avec `transform`. `@keyframe` nous permet en effet de séparer notre animation en plusieurs étapes.

La première étape est de définir l'animation en soit avec `@keyframe`. Ensuite on va ajouter les "étapes" de notre animation, les tranformations à faire. Celle-ci son composé d'une ou plusieurs rêgles css. Pour chaque étape on doit aussi définir un pourcentage qui indique à qu'elle moment durant l'animation l'étape s'enclenche. (La durée de l'animation sera déclaré plus loin) La syntaxe est la suivante : 

``````css
@keyframes nom_animation {
    0% {
        /* Règle de l'étape 1 */
    }
    50% {
        /* Règle de l'étape 2 */
    }
    100% {
        /* Règle de l'étape 3 */
    }
}
``````

Voici un exemple qui va modifier la couleur de fond, en partant du cyan on va jusqu'à mi-chemin aller vers le jaune pour ensuite glisser vers le orange.

``````css
@keyframes color_change {
    0% {
        background-color: cyan;
    }
    50% {
        background-color: yellow;
    }
    100% {
        background-color: orange;
    }
}
``````

Ensuite on va "lancer" notre animation en l'associant à un sélecteur css. L'animation sera déclenchée automatiquement au chargement de la page, à moins d'utiliser le sélecteur :hover qui se fera lors du survol de la souris sur l'élément. La propriété à utiliser est **animation**, un "raccourci" qui englobe 8 autres propriétées : 

- animation-delay
- animation-direction
- animation-duration
- animation-fill-mode
- animation-iteration-count
- animation-name
- animation-play-state
- animation-timing-function

On n'est pas obligé de définir une valeur pour toutes ces propriétés, elles en ont tous une par défaut. 

Pour plus de détail sur ces propriétés : [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation){target=_blank}

Au minimum on va définir le nom de l'animation, sa durée et le nombre répétition : 

``````css
html {
    animation: nom_animation durée nombre_repetition;
}
``````

Le nom de l'animation est celui défini dans le `@keyframe`, la durée est défini en secondes (s) ou en millisecondes (ms). Enfin la répétition est un nombre qui peut être fractionnaire. On peut aussi utiliser **infinite** pour répéter l'animation à l'infini. 

## Pour aller plus loin avec les animations 

- [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations){target=_blank}
- [https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes){target=_blank}
- [https://css-tricks.com/snippets/css/keyframe-animation-syntax/](https://css-tricks.com/snippets/css/keyframe-animation-syntax/){target=_blank}

