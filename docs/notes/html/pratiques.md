# Bonnes pratiques du langage

Un fichier HTML peut vite rapidement un fouillis total si vous ne porter pas attention à votre manière d'écrire. Voici quelques normes simples à suivre qui vous éviteront de vous y perdre.

## Utiliser l'indentation

Un indentation est une tabulation ou un espace de 4 caractères qu'on insère devant une balise HTML. 

- Dès que vous ouvrez une balise, chaque enfant aura une indentation supplémentaire.
- La fermeture d'une balise doit toujours être alignée avec son ouverture

```html title="Exemple avec une mauvaise indentation"
<div><ul>
<li>Item 1</li><li>Item 2</li><li>Item 3</li>
    </ul>
            </div>
```

```html title="Exemple avec indentation correcte"
<div>
    <ul>
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
    </ul>
</div>
```

Les deux exemples fonctionnent et donne le même résultat, mais il est beaucoup plus facile de lire le second et de visualiser son résultat.

## Tout en minuscule

Le nom et les attributs d'une balise devraient toujours être en minuscule. Ça ne changera rien au rendu mais ça améliore la lisibilité.

```html title="À ne pas faire"
<div>
    <Div>
        <DIV>
        </div>
    </DIV>
</Div>
```

## Éviter les lignes interminables

Dans la programmation en générale on essaie d'écrire des lignes de code qui ne dépasse pas les 80 caractères. Ce que je vous conseille est de vous assurer que la ligne que vous écrivez entre dans la largeur de votre écran. 

- Si vous devez défiler horiontalement pour la voir en entier elle est trop longue.
- Une solution est de faire un saut de ligne entre les attributs d'une balise trop longue.
- Vous pouvez aussi écrire le contenu d'une balise sur une autre ligne
- Rappelez-vous que les saut de ligne dans votre code ne sont pas interprétés par le navigateur
- Les paragraphes de texte sont une exception, vous pouvez les laisser sur une ligne si c'est plus simple.

```html title="Exemples"
<!-- Au lieu d'écrire ceci -->
<input type='number' id='numero_refence' name='numero_refence' min="100001" max="199999" value="100001">
<!-- Vous pouvez faire ça -->
<input type='number' 
    id='numero_refence' 
    name='numero_refence' 
    min="100001" 
    max="199999" 
    value="100001">

<!-- Un long paragraphe -->
<p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Expedita nulla ullam odio inventore, reiciendis necessitatibus! Esse vero totam inventore dicta quis laborum delectus quisquam corrupti dolores laboriosam quidem, aliquam, repudiandae nisi. Iste voluptas ratione placeat labore illo corrupti nulla cum minima magnam deleniti doloremque, eum mollitia saepe nihil harum quidem?</p>
<!-- Pourrait aussi s'écrire de cette façon -->
<p>
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. 
    Expedita nulla ullam odio inventore, reiciendis necessitatibus! 
    Esse vero totam inventore dicta quis laborum delectus quisquam 
    corrupti dolores laboriosam quidem, aliquam, repudiandae nisi. 
    Iste voluptas ratione placeat labore illo corrupti nulla cum minima 
    magnam deleniti doloremque, eum mollitia saepe nihil harum quidem?
</p>
```

