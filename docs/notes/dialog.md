# Afficher une fenêtre modale

Une fenêtre **modale** bloque l'interaction avec le reste de la page tant qu'elle est ouverte. Il y a plusieurs méthodes différentes, on va voir comment afficher une fenêtre avec l'élément HTML `<dialog>`.

## Structure de base

```html
<button id="btnOuvrir">Ouvrir la modale</button>

<dialog id="maModale">
  <h2>Titre de la modale</h2>
  <p>Voici le contenu de la fenêtre modale.</p>
  <button id="btnFermer">Fermer</button>
</dialog>
```

Par défaut, un `<dialog>` est **caché**. Il n'apparaît que lorsqu'on l'ouvre avec JavaScript (ou avec l'attribut `open`, qui l'affiche sans le rendre modal).

## Ouvrir et fermer avec JavaScript

```javascript
const modale = document.getElementById('maModale');

document.getElementById('btnOuvrir').addEventListener('click', () => {
  modale.showModal();   // ouvre en mode modal
});

document.getElementById('btnFermer').addEventListener('click', () => {
  modale.close();       // ferme la modale
});
```

<!-- ### Les méthodes à connaître

| Méthode / propriété | Rôle |
| --- | --- |
| `showModal()` | Ouvre la boîte en mode modal (fond bloqué, `::backdrop` affiché) |
| `show()` | Ouvre la boîte sans la rendre modale (le reste de la page reste utilisable) |
| `close(valeur)` | Ferme la boîte; la valeur optionnelle est stockée dans `returnValue` |
| `open` | Propriété booléenne : `true` si la boîte est ouverte |
| `returnValue` | Chaîne de caractères indiquant comment la boîte a été fermée | -->


### L'effet de la méthode `showModal()`

Quand on lance la méthode `showModal()` le navigateur va automatiquement:

- afficher l'élément `<dialog>` centré, au-dessus du reste de la page;
- rendre inaccessible le contenu derrière la modale (clics et clavier);
- fermer la modale quand on appuie sur la touche **Échap**;
- rendre disponible le pseudo-élément `::backdrop` pour styliser l'arrière-plan.

## Styliser la modale

```css
dialog {
  border: none;
  border-radius: 8px;
  padding: 1.5rem;
  max-width: 400px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

/* L'arrière-plan assombri derrière la modale */
dialog::backdrop {
  background: rgba(0, 0, 0, 0.5);
}
```
!!! danger "Attention"

    Ne changez pas la propriété `display` (`display: flex` ou `display: grid`) pour la mise en forme de votre fenêtre car elle restera visible en tout temps (petit bug).
    Si vous voulez l'utilisez ajouter l'attribut `[open]` à votre sélecteur.

    ```css title="Exemple" hl_lines="1"
    dialog[open] {
        display: flex;
        flex-direction: column;
    }
    ```

## Variante : fermer avec un formulaire

Un formulaire dont la méthode est `dialog` **ne soumet rien au serveur** : il ferme simplement la boîte qui le contient. La valeur du bouton cliqué est stockée dans `returnValue`.

```html hl_lines="6 7"
<button id="ouvrir">Supprimer</button>

<dialog id="confirmation">
  <form method="dialog">
    <p>Voulez-vous vraiment continuer ?</p>
    <button value="non">Non</button>
    <button value="oui">Oui</button>
  </form>
</dialog>
```

```javascript
const dlg = document.getElementById('confirmation');

document.getElementById('ouvrir').addEventListener('click', () => {
  dlg.showModal();
});

dlg.addEventListener('close', () => {
  console.log('Réponse :', dlg.returnValue); // "oui" ou "non"

  if (dlg.returnValue === 'oui') {
    // exécuter l'action confirmée
  }
});
```

### Comment ça fonctionne

1. L'utilisateur clique sur un bouton du formulaire.
2. Le navigateur ferme la boîte (pas de rechargement de la page).
3. La `value` du bouton cliqué devient `dialog.returnValue`.
4. L'événement `close` est déclenché : c'est là qu'on lit la réponse.

### Avec des champs de saisie

Le formulaire peut aussi contenir des champs. La validation HTML (`required`, `type="email"`, etc.) s'applique avant la fermeture, mais les données ne sont pas envoyées automatiquement : on les lit nous-mêmes dans le gestionnaire de l'événement `close`.

```html
<dialog id="saisie">
  <form method="dialog">
    <label>Votre nom : <input type="text" name="nom" id="nom" required></label>
    <button value="annuler" formnovalidate>Annuler</button>
    <button value="ok">Valider</button>
  </form>
</dialog>
```

```javascript
const saisie = document.getElementById('saisie');

saisie.addEventListener('close', () => {
  if (saisie.returnValue === 'ok') {
    const nom = saisie.querySelector('#nom').value;
    console.log('Nom saisi :', nom);
  }
});
```

L'attribut `formnovalidate` sur le bouton « Annuler » permet de fermer la boîte sans exiger que le champ soit rempli.


## Références

- Pour en savoir plus : [Élément HTML `<dialog>` : l'élément de boîte de dialogue](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/dialog){target=_blank}
