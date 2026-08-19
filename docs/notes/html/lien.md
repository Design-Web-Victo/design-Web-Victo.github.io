# Lien hypertexte


La balise **`<a>`** en HTML (appelée **balise d’ancrage ou lien hypertexte**) sert principalement à créer des **liens cliquables**, mais elle a beaucoup plus de possibilités qu’on ne le pense. Voici un tour complet :

---

## 1. **Créer un lien hypertexte (usage de base)**

La forme la plus courante :

```html
<a href="https://www.exemple.com">Visiter le site</a>
```

* **`href`** : l’URL ou l’adresse vers laquelle le lien pointe.

---

## 2. **Liens internes (ancre dans la même page)**

Permet de naviguer à une section spécifique :

```html
<a href="#section2">Aller à la section 2</a>

<h2 id="section2">Section 2</h2>
```

* Utilise **`id`** comme repère.

---

## 3. **Liens vers des fichiers téléchargeables**

Pour permettre le téléchargement direct :

```html
<a href="document.pdf" download>Télécharger le PDF</a>
```

* L’attribut **`download`** force le téléchargement.

---

## 4. **Lancer un e-mail ou un appel**

### Envoyer un e-mail :

```html
<a href="mailto:exemple@mail.com">Envoyer un e-mail</a>
```

### Lancer un appel téléphonique (sur mobile) :

```html
<a href="tel:+14185551234">Appeler maintenant</a>
```

---

## 5. **Ouvrir un lien dans un nouvel onglet ou une nouvelle fenêtre**

```html
<a href="https://www.exemple.com" target="_blank" rel="noopener noreferrer">
  Ouvrir dans un nouvel onglet
</a>
```

* **`target="_blank"`** : ouvre dans un nouvel onglet/fenêtre.
* **`rel="noopener noreferrer"`** : recommandé pour la sécurité et la confidentialité.

??? info "Précision sur l'attribut rel"

    L'attribut rel="noopener noreferrer" dans une balise `<a>` est utilisé pour des raisons de sécurité et de confidentialité lorsqu'un lien ouvre une nouvelle page dans un nouvel onglet ou une nouvelle fenêtre (avec target="_blank").

    Fonctionnement des deux valeurs :
    
      1. **noopener** :
        - Empêche la nouvelle page ouverte d'accéder à l'objet window.opener de la page d'origine.
        - Cela protège la page d'origine contre des attaques potentielles, comme le tabnabbing, où la nouvelle page pourrait rediriger la page d'origine vers un site malveillant.
      2. **noreferrer** :
        - Empêche le navigateur d'envoyer l'en-tête HTTP Referer à la nouvelle page.
        - Cela signifie que la nouvelle page ne saura pas d'où provient le trafic (pas d'URL de la page d'origine).

    Pour plus de détails sur l'attribut rel : [https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Attributes/rel](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Attributes/rel){target=_blank}

---

## 6. **Transformer n’importe quel élément en lien**

```html
<a href="https://www.exemple.com">
  <img src="image.jpg" alt="Image cliquable">
</a>
```

* Les balises `<a>` peuvent contenir du texte, des images, des icônes, voire des blocs complets (depuis HTML5).

---

## 7. **Créer un lien vide ou cliquable sans navigation**

* Avec `#` :

```html
<a href="#">Lien sans destination</a>
```

Utilez pour des menus ou des scripts JS. On peut aussi s'en servir pour simuler un retour au début de la page.


---

## 8. **Accessibilité et bonnes pratiques**

* **Texte de lien explicite** : éviter les "Cliquez ici". Préférez :

  ```html
  <a href="/contact">Contactez-nous</a>
  ```

* **Utiliser `title` (avec modération)** :

  ```html
  <a href="/info" title="Plus d'informations sur ce sujet">Plus d'infos</a>
  ```

  Utile pour ajouter de l'information supplémentaire, mais pas indispensable.



