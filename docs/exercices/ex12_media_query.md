# Exercice 12 - Media Query

L'objectif de cet exercice est d'ajuster la disposition d'un site selon 3 cas.

## Initialisation du projet

- [x] Téléchargez le projet de départ et copiez le dans votre répertoire de cours : [ex12_mediaquery_depart.zip](../../ressources/ex12_mediaquery_depart.zip){target=_blank}.

## Page 1

Faites la mise en forme suivante sur le ficher **page1.html** (Quand il est question de zone de texte, on inclus le titre et les paragraphes): 

- [x] La zone de texte doit avoir une ==largeur maximal== de 900 pixels et elle doit être centrée horizontalement.
- [x] Ajoutez un ==padding== à gauche et à droite de la zone de texte de 2 rem.
- [x] Les titres h2 doivent être de couleur grise et souligné en orange.
- [x] Le texte doit être d'alignement justifié et disposé sur 2 colonnes à l'aide de la propriété `column-count`.

<figure markdown>
  ![ex12_p1a](../../images/ex12_p1a.png){.center .shadow}
  <figcaption>Le résultat doit ressembler à cette image </figcaption>
</figure>

- [x] Maintenant quand la largeur de l'écran est inférieur à 750 pixels, le texte doit être affiché sur une colonne.
- [x] Enlevez aussi la ligne de surlignement orange aux sous-titres.

<figure markdown>
  ![ex12_p1b](../../images/ex12_p1b.png){.center .shadow}
  <figcaption>Le résultat doit ressembler à cette image </figcaption>
</figure>

## Page 2

Faites la mise en forme suivante sur le ficher **page2.html** quand la largeur de l'écran est ==inférieur ou égale à 800 pixels==.

- [x] La section "À propos de moi" disparait.
- [x] Il n'y a pas de changement à l'entête ni au pied de page.
- [x] La barre de menu est remplacé par un menu de type "hamburger". 

!!! Note 

    Un menu **hamburger** est composé d'un icone représentant 3 traits horizontals. Quand on clique sur l'icône, la zone de menu apparait à l'écran. Il y a des méthodes pour le faire uniquement en css et html, je vous laisse ==rechercher et expérimenter== votre solution.

Quand on imprime la page, appliquez les changements suivants: 

- [x] L'entête de la page et le menu disparaissent.
- [x] La section "À propos de moi" se déplace à la fin du document.
- [x] On va donc avoir les deux articles suivis de la section "À propos".

!!! Astuce

    Pour visualiser le résultat en mode impression, imprimez la page à l'aide de votre navigateur. Il vous donnera un aperçu avant de lancer l'impression.

Voici un aperçu de chacun des états de la page

<figure markdown>
  ![ex12_p2a](../../images/ex12_p2a.png){.center .shadow}
  <figcaption>Largeur supérieur à 800 pixels</figcaption>
</figure>

<figure markdown>
  ![ex12_p2b](../../images/ex12_p2b.png){.center .shadow}
  <figcaption>Largeur inférieur à 800 pixels avec le menu hamburger</figcaption>
</figure>

<figure markdown>
  ![ex12_p2c](../../images/ex12_p2c.png){.center .shadow}
  <figcaption>Impression</figcaption>
</figure>


