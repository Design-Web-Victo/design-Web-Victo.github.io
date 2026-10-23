# Exercice 17 - Liste de tâches

## Initialisation

- Dans cet exercice nous allons coder les fonctionnalités d'une liste de tâches.
- La portion HTML et CSS est déjà fait, vous n'avez qu'à télécharger le projet de départ dans le devoir Teams.
- Une fois le dépôt récupéré vous devriez avoir une page qui ressemble à ceci.

![ex16_01](../../images/ex16_01.png)

## Fonctionnalités à programmer

**Ajout de tâches**

- Quand on appuie sur la touche "Entrée" ou si l'on clique sur le bouton "+", on ajoute le texte saisie dans la section "Tâches à faire". 
- S'il n'y a pas de texte on ajoute rien. 
- Dans la section "Tâche à faire" il y a une balise **ul** vide (une liste à puce). Le texte ajouté ==sera dans une balise **li**== à l'intérieur de la balise **ul**. 
- Vous devez ==ajouter la classe "tache"== au nouvel item.
- Ajoutez aussi un événement pour déclencher une action quand on clique sur un item de la liste (l'événement est décrit plus bas)

**Section des tâches complétées**

- Quand on clique sur une tâche de la liste des tâches à faire, on le déplace dans la liste des tâches complétées. 
- On lui ==ajoute la classe "fait"==. 
- Pour déplacer la tache d'une liste à l'autre, on n'a qu'à récupérer l'élément dans une variable et ensuite de l'ajouter dans la bonne liste.
- Si vous utilisez cette méthode pour déplacer l'item, n'oubliez pas d'enlever l'événement clique sur l'item.
- Quand on clique sur l'icône de la poubelle, on doit supprimer toutes les tâches de la liste des tâches complétées.

## Remise de l'exercice

- [x] Une fois l'exercice terminé, compressez votre répertoire et rendez le dans le devoir Teams


<figure markdown>
  ![ex19_02](../../images/ex16_02.png){.center .shadow}
  <figcaption>Exemple du résultat final</figcaption>
</figure>


## Pour aller plus loin (optionnel)

- Enregistrez la liste des tâches à faire et des tâches complétées dans le stockage local
- Réaffichez-les lors du chargement de la page. 
- Référez-vous au notes de cours sur le [stockage local](../notes/js/js_local_storage.md). 

!!! Astuce

    Une bonne stratégie serait de créer un tableau pour les valeurs de chaque liste et d'ensuite les enregistrer dans le stockage dès qu'il y a un changement dans les listes. Au chargement de la page chargez les valeurs et recréez les items.
