# Examen 1 - Révision C

## Directives

À l'aide de tout ce que vous avez appris jusqu'à maintenant, vous devez reproduire la maquette suivante (voir plus bas pour les spécifications): 

![Gabarit](../../images/examen01_revc_01.png){.center .shadow}

## 1. Structure du projet

- Créez un dossier nommé **Examen1_NomPrenom** dans lequelle vous allez créer un fichier index.html. Ajoutez ensuite un sous-dossier pour vos feuilles de styles, un pour les images et un pour les polices de caractères.
- Téléchargez les fichiers requis pour cet exercice: [Fichiers fournis](../../ressources/examen1_revision_c.zip).
- Copiez les fichiers dans les bons répertoires.
- Créez un fichier de styles CSS.

## 2. Utilisation de variables CSS

- Toutes les couleurs que vous allez utiliser doivent être assigné à des variables CSS.  Voici les couleurs que j'ai utilisé dans la maquette

| Description                                            | couleur            |
| ------------------------------------------------------ | ------------------ |
| Bordure rouge                                          | \#ca2417           |
| Bordure grise (autour des caractéristique de la bière) | \#d5d5d5           |
| Couleur du texte de description                        | \#6f706f           |
| Nom de la bière en gros, dans le bas de la page        | hsla(0,0%,100%,.4) |

## 3. Utilisation de Web Font

- Il y a deux fichiers de polices dans les fichiers fournis, **Oswald-Regular.ttf** et **Faustina-Regular.ttf**. Créez un webfont pour chacun d'eux. 

## 4. Disposition générale

- Toute la page doit être contenu dans une division centrée.
- Appliqué la police Oswald à tout le document.
- L'image de fond est incluse dans les fichiers fournies.

## 5. Section image

- La section image occupe 40% en largeur de la division principale.
- Assurez-vous que l'image ne déborde pas de son conteneur.

## 6. Section description

- La section description occupe 60% en largeur de la division principale.
- Utilisez la police ==faustina== pour la catégorie de bière ("Classiques"), le slogan ("Une sacré bonne bière!") et le texte de description.

  ``````html
  <p class="description-biere">À l’origine, ce type d’ale anglaise fut conçu pour résister aux longs voyages de ravitaillement entre l’Angleterre et les troupes cantonnées aux Indes. Subtile en caramel et en malt fin, elle se démarque au nez par la présence prédominante du houblon. En bouche, elle est sèche et franche. Son amertume est longue et laisse des notes de malt et de caramel. Idéale avec les produits de la mer et les fromages corsés.</p>
  ``````

- Pour la grosseur de la police des différents texte, je vous laisse juger par vous-même. Tant que les proportions s'apparentent à l'image de la maquette c'est parfait.
- C'est peu visible sur l'image mais il y a une bordure grise autour de la section des caractéristiques (pourcentage d'alcool, ibu, etc...)
- Dans cette section, chaque caractéristique est centré horizontalement et alignée dans le bas verticalement.
- L'image du verre est disponible dans les fichiers fournis.
- Le texte "DENSITÉ" et la phrase de la disponibilité utilise la police faustina.
- Utilisez Grid, Flexbox ou un mélange des deux pour faire la disposition des différentes sections.

## 7. Media Query

- Faites en sorte que quand la résolution de l'écran est inférieur à 870 pixels : 
    - Le nom de la bière dans le bas de la page disparaisse.
    - La section description soit en premier et prenne toute la place
    - L'image de la bière soit sous la section description

![Media Query](../../images/examen01_revc_02.png){.center .shadow}

  

## Grille de correction

| éléments                                                     | pondération |
| ------------------------------------------------------------ | ----------: |
| **1. Structure du projet**                                   |      **/5** |
| La structure est respecté avec les sous-dossiers             |           5 |
| **2. Utilisation de variables CSS**                          |      **/5** |
| Toutes les couleurs utilisées sont assignées à des variables |           5 |
| **3. Utilisation de Web Font**                               |     **/10** |
| Un web font a été créé pour les deux polices de caractères   |          10 |
| **4. Disposition générale**                                  |     **/15** |
| La division principale est centrée                           |           5 |
| La police de caractère Oswald est appliquée à toute la page  |           5 |
| Un image de fond a été utilisé                               |           5 |
| **5. Section image**                                         |     **/15** |
| Les spécifications ont été respectées                        |          15 |
| **6. Section detail**                                        |     **/30** |
| Les spécifications ont été respectées                        |          10 |
| La disposition est fidèle à la maquette et a été fait avec grid et/ou flexbox |          20 |
| **7. Media Query**                                           |     **/20** |
| Le nom de la bière en bas de page est masqué                 |           5 |
| La section description est affichée en premier et l'image ensuite. |          15 |
| **Total**                                                    |    **/100** |