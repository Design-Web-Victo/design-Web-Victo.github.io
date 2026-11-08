# Mise en forme du formulaire

On peut modifier apparence de notre formulaire et la plupart de ses éléments avec des règles css. Tout ce qui touche le texte et les polices de caractères est utilisable. On aussi facilement modifier l'apparence des "boites" des éléments avec les propriétés associées comme padding, marging, border, etc.

Voici quelques ressources pour vous guider : 

- [https://developer.mozilla.org/fr/docs/Learn/Forms/Styling_web_forms](https://developer.mozilla.org/fr/docs/Learn/Forms/Styling_web_forms)
- [https://www.w3schools.com/css/css_form.asp](https://www.w3schools.com/css/css_form.asp)
- [https://blog.logrocket.com/how-to-style-forms-with-css-a-beginners-guide/](https://blog.logrocket.com/how-to-style-forms-with-css-a-beginners-guide/)

## Pseudo-classe

On peut aussi utiliser des pseudo-classes pour modifier l'apparence des éléments du formulaire selon leur état. Les plus pertinentes sont les suivantes : 

### :focus

Applicable quand l'élément est sélectionné. Peut nous permettre par exemple de donner un effet "de surlignement" de l'élément que l'usager est en train de remplir.

``````css
/* Je veux que pour tout mes éléments input la couleur de fond devienne rose quand on le sélectionne */
input:focus {
    background-color: pink;
}
``````

!!! Note

    Si je veux supprimer le surlignement par défaut de l'élément quand il a le focus, je peux utiliser la proptiété css `outline: none;`

    ```css linenums="1" hl_lines="6"
    input:focus {
        outline: none;
    }
    ```

### :required

Applicable uniquement quand l'élément à l'attribut **required**. Peut être utile si on veut avoir une mise en forme différente pour les éléments obligatoires.

**Html**

``````html
<input type='text' id='cle-activation' name='cle_activation' required>
``````

**Css**

``````css
input:required{
	background-color: rgb(255, 153, 0);
}
``````

!!! Attention

    Quand on utilise une liste de choix (la balise `select`), une valeur vide (`value=""`) est considéré comme si on n'envoie aucune valeur et va déclencher l'événement.

### :invalid

Applicable quand l'usager à saisie une valeur invalide, comme par exemple une adresse courriel non conforme dans un élément input de type courriel.

**Html**

``````html
<input type="email" name="courriel_usager" id="courriel_usager">
``````

**Css**

``````css
/* Quand l'usager va entrer une valeur pour le input courriel_usaager, la bordure sera rouge si le courriel est invalide. */
#courriel_usager:invalid {
    border: 2px solid #ff0000;
}
``````

