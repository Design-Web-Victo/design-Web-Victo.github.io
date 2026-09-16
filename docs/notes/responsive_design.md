# Créer des sites web adaptatif

Un site adaptatif (ou responsive web design) est une page web conçue pour s’afficher correctement et offrir une expérience optimale **sur différents appareils** (ordinateurs, tablettes, téléphones intelligents). L’objectif est que le contenu reste lisible, accessible et agréable **peu importe la taille ou l’orientation de l’écran**.

## Pourquoi concevoir un site adaptatif?

En 2025, environ 60% des visites proviennent de téléhones mobiles, contre 38% pour les ordinateurs et 2% pour les tablettes[^1]. Prendre en compte les différent supports possibles pour consulter un site internet est devenu un incontournable aujourd'hui.

Au début de l'ère du mobile, il n'était pas rare qu'on développe un site pour la consultation sur ordinateur et un second site qui était destiné au visionnement sur mobile. On devait donc faire le travail en double et ça complexifiait la maintenance et la mise à jour des deux sites. Avec la conception adaptative, on économise temps et argent.

## Quels sont les avantages?

1. Une architecture adaptative
2. Une navigation ergonomique
3. Des contenus multi-écrans : Le contenu créé pour le site est adapté à l'écran, pas besoin de faire plusieurs versions
4. Des visuels qui s'adaptent (Taille des images)
5. Économies de temps et d'argent

## La conception adaptative

### mobile first vs responsive design

Il existe deux manières d'aborder la création d'un site adaptatif: Le **mobile d’abord** (ou mobile first) et le **responsive design** (design réactif).

**Le « mobile d’abord » consiste à créer un site internet adaptatif en partant de l’interface mobile**, puis à l’adapter aux tablettes et aux ordinateurs. À favoriser si la cible est essentiellement la consultation sur mobile.

**Le « responsive design » permet de créer un site internet adaptatif en partant de l’interface ordinateur** et est la technique la plus courante utilisée. 

### Essayez de concevoir au moins 3 versions de votre site

- **Petite :** moins de 600px, format pour la plupart des smartphones
- **Moyenne :** 600px – 900px, format pour la plupart des tablettes, les gros téléphones, et les petits ordinateurs
- **Large :** plus de 900px, format pour la plupart des ordinateurs

C'est devenu simple à faire avec l'aide de [media queries](./css/mediaquery.md).

### Quelques points à prendre en compte

**L’expérience utilisateur est essentielle**: un design adaptatif doit faire bien plus que d’adapter un site à une taille d’écran. Il doit également prendre en compte l’expérience utilisateur, la manière dont ces derniers interagissent avec le site, et le contenu qu’ils regardent vraiment.

!!! Attention 

    Faites attention aux éléments cliquable (icônes et boutons). Selon Apple : **la taille minimale confortable pour les éléments UI cliquables est de 44 x 44 px**.

**L’engagement des utilisateurs** : 
	- Conservez un design simple et de rester sobre (KISS). 
	- Concevez votre site en fonction de votre contenu et de l’expérience que vous voulez créer. Si le but est de faire en sorte que les gens cliquent un maximum sur le bouton “contactez-nous”, faites en sorte que ce bouton saute aux yeux.

**La navigation** : Modifier les modes de navigation pour des interfaces mobiles (menu "hamburger", menu déroulant, onglets).
**Les images flexibles** : Le code doit permettre aux images de changer d’échelle (en pourcentage) en fonction de la largeur du navigateur.

### Aide-mémoire

- [x] Utiliser des unités de mesures relatives (pourcentage, rem, em, vh, vw) quand c'est possible.
- [x] Optimiser les images pour différents terminaux et différentes vitesses de connexion (*lazy loading*).
- [x] Modifier le style des liens et boutons pour être mieux adapté au tactile
- [x] Redimensionner dynamiquement les polices pour mieux fonctionner sur différentes résolutions d'écrans
- [x] Modifier les modes de navigation pour des interfaces mobiles
- [x] Charger le contenu en fonction de la résolution de l'écran (media query)

## Ressources

- [Les bases de la conception de sites web adaptatifs](https://99designs.fr/blog/design-web-digital/lconception-sites-web-adaptatifs/){target=_blank}
- [Site adaptatif : 6 avantages du responsive design](https://www.combustible.ca/2016/08/10-elements-essentiels-dun-bon-site-web-adaptatif-pour-les-pme/){target=_blank}
- [Recommandations pour créer un Site Web Adaptatif](https://www.infoq.com/fr/news/2014/06/responsive-website-design/){target=_blank}

[^1]: [Mobile Device Website Traffic Statistics (2025 Trends)](https://www.tekrevol.com/blogs/mobile-device-website-traffic-statistics/){target=_blank}