# Examen 1 - Révision B

## Directives

À l'aide de tout ce que vous avez appris jusqu'à maintenant, vous devez reproduire la maquette suivante (voir plus bas pour les spécifications): 

![Gabarit](../../images/examen01_revb_01.png){.center .shadow}

## 1. Initialisation

- Téléchargez le projet de départ: [examen1_revision_b.zip](../../ressources/examen1_revision_b.zip)

## 2. Mise en page générale

- Créez un conteneur qui contiendra la totalité de votre page.
- Ce conteneur doit avoir une largeur de 700 pixels et doit être centré à la page.
- Ne définissez pas de hauteur à ce conteneur.
- Dans votre fichier css, déclarez des variables pour les couleurs des 6 partis

| Parti                              | Couleur  |
| ---------------------------------- | -------- |
| Parti libéral du Québec (PLQ)      | \#f08080 |
| Parti québécois (PQ)               | \#004C9D |
| Québec solidaire (QS)              | \#FF8040 |
| Parti conservateur du Québec (PCQ) | \#1db9e0 |
| Coalition avenir Québec (CAQ)      | \#1e90ff |
| Climat Québec (CQ)                 | \#13876c |



## 3. Entête

- L'entête comporte un titre **h1** (Élection Québec 2022) et un sous-titre **h2** (Arthabaska) qui sont tous les deux centrés.
- Il y a une marge dans le bas de 50 pixels.
- Créez un *web font* avec la police **gilroy-extrabold-webfont.woff2** qui se retrouve dans les fichiers fournis.
- Appliquez cette police à toute l'entête.
- Le titre doit avoir une taille de 4em et le sous-titre 2.5em

## 4. Section des candidats

- Créer une **div** pour chacun des candidats.
- Cette division aura une **marge** de 50 pixels gauche - droite et de 0 pixels haut - bas.
- Ajoutez aussi un **padding** de 30 pixels gauche - droite et de 15 pixels haut - bas.
- Il y a une bordure noire de 1 pixels et le curseur est un *pointer* (une main).
- Les éléments sont centrés verticalement à l'intérieur de la **div**.
- Le nom du candidat et son parti sont alignés à gauche et l'icone à droite.
- Appliquez une marge en haut de 10 pixels et en bas de 5 pixels au nom du candidat.
- L'icone de cercle vide est un icone de font awesome.

| Icone        | classe font awesome               |
| ------------ | --------------------------------- |
| Cercle vide  | fa-regular fa-circle fa-2xl       |
| Cercle coché | fa-regular fa-circle-check fa-2xl |

Vous pouvez utiliser mon lien si vous avez de la difficulté à vous connecter à Font Awesome

``````html
<script src="https://kit.fontawesome.com/80e9d74121.js" crossorigin="anonymous"></script>
``````



### 4.1 Quand on survole la division d'un candidat

- Changez la couleur de fond pour la couleur du parti du candidat.
- Faites une translation de 20 pixels sur l'axes des x.
- Changez l'icone du cercle vide pour celui du cercle coché. (On masque l'un et afficher l'autre)
- Utilisez les variables css déclarées plus haut pour la couleur de fond.
- L'animation doit avoir une transition uniquement sur la propriété transform et être d'un durée de 400ms.

![Gabarit](../../images/examen01_revb_02.png){.center .shadow}

!!! Astuce

    On peut appliquer un changement sur un élément enfant quand on survol sont parent. Par exemple j'ai une div et à l'intérieur un titre h1

    ``````html
    <div>
      <h1>Exemple</h1>
    </div>
    ``````

    En css je pourrais modifier la couleur du texte h1 quand je survol la div en faisant ceci

    ``````
    div:hover h1 {
      color: red
    }
    ``````

## 5. Pied de page

- Ajoutez un bouton centré après la liste des candidats avec le texte "Je vote".
- Stylisez le bouton à votre gout.
- Sur la dernière ligne, ajoutez le texte "@ Prénom Nom" aligné à gauche et l'image **logo_election_quebec.png** alignée à droite. L'image se retrouve dans les fichiers que je vous fournis.
- L'image à une hauteur fixe de 24 pixels. 
- Ajoutez un lien sur l'image vers l'url https://www.electionsquebec.qc.ca/

Ouf c'est terminé, n'oubliez pas de faire d'inclure tous les fichiers dans la remise.

## Grille de correction

| éléments                                                     | pondération |
| ------------------------------------------------------------ | ----------: |
| **1. Mise en page générale**                                 |     **/10** |
| Les spécifications du conteneur sont respectées              |           5 |
| Des variables ont été crées pour les couleurs des partis     |           5 |
| **2. Entête**                                                |     **/20** |
| Les spécifications de l'entête sont respectées               |           5 |
| Une web font a été créé                                      |          10 |
| La police de caractère et la taille de la police ont été modifié comme demandé |        5     |
| **3. Section des candidats**                                 |     **/55** |
| Les spécifications de la "div" sont respectées               |          10 |
| Le nom du candidat et son parti ainsi que l'icône sont bien alignés |          10 |
| Utilisation des icônes de Font Awesome                       |           5 |
| Modification de la division lors du survol avec la souris    |          20 |
| Modification de l'icône lors du survol de la division        |          10 |
| **4. Pied de page**                                          |     **/10** |
| Le bouton est centré                                         |           2 |
| Le bouton a été stylisé                                      |           2 |
| Le texte est aligné à gauche et l'image à droite             |           2 |
| L'image à une hauteur de 24 pixels                           |           2 |
| Un lien est ajouté à l'image                                 |           2 |
| **5. Qualité du code**                                       |     **/5** |
| Le code est exempt d'erreur                                  |           5 |
| **Total**                                                    |    **/100** |

