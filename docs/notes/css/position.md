# La propriété position

En CSS, la propriété **`position`** permet de définir la manière dont un élément HTML est positionné dans la page. Elle influence la disposition, le chevauchement et la superposition des éléments.

## 1. Les valeurs principales de position

### static

Valeur par défaut

- L’élément suit le flux normal du document.
- Les propriétés `top`, `right`, `bottom`, `left` **n’ont aucun effet**.

```css
p {
  position: static;
}
```

### relative

L’élément reste dans le flux normal, mais peut être déplacé par rapport à sa position initiale.

- Les propriétés `top`, `left`, `right`, `bottom` déplacent l’élément sans affecter les autres.

```css
div {
  position: relative;
  top: 10px;
  left: 20px;
}
```

<!-- 👉 Utile comme **contenant de référence** pour des éléments positionnés en `absolute`. -->


### absolute

L’élément est retiré du flux normal.

- Il est positionné par rapport à son premier **ancêtre positionné** (c’est-à-dire un parent avec une valeur `position` différent de `static`).
- Les autres éléments se comportent comme si l’élément n’existait pas.

```css
.box {
  position: absolute;
  top: 50px;
  right: 10px;
}
```

!!! note "" 
  
    Très utilisé pour les menus, bulles d’information, légendes sur images.


### fixed

Semblable à `absolute`, mais l’élément est fixé **par rapport à la fenêtre du navigateur** (viewport).

- Il reste visible même lors du défilement.

```css
nav {
  position: fixed;
  top: 0;
  left: 0;
}
```

!!! note "" 
  
    Exemple courant : une barre de navigation fixe en haut de page.


### sticky

Combinaison entre `relative` et `fixed`.

- L’élément suit le flux normal jusqu’à ce qu’un seuil soit atteint (ex. `top: 0;`), puis il devient fixe.
- Dépend du **contenant parent**.

```css
header {
  position: sticky;
  top: 0;
}
```

!!! note "" 
    Exemple courant : un en-tête qui reste collé en haut lors du défilement.

## 2. Les propriétés de décalage

- `top`, `right`, `bottom`, `left` servent à définir la position exacte de l’élément selon son contexte.
- Elles n’agissent **que si la valeur de `position` est différent de `static`**.

Exemple :

```css
img {
  position: absolute;
  top: 100px;
  left: 50px;
}
```

## 3. La superposition avec `z-index`

- La propriété `z-index` définit l’ordre d’empilement (superposition) des éléments positionnés.
- Plus la valeur est grande, plus l’élément est au-dessus.

```css
.card {
  position: absolute;
  z-index: 10;
}
```

## 4. Résumé des différences

| Valeur     | Flux normal respecté ?  | Exemples d’usage                      |
| ---------- | ----------------------- | --------------------------------------|
| `static`   | ✅ Oui                  | Texte, blocs par défaut               |
| `relative` | ✅ Oui                  | Ajustement fin, ancre pour `absolute` |
| `absolute` | ❌ Non                  | Boîtes flottantes, overlays           |
| `fixed`    | ❌ Non                  | Menus fixes, boutons flottants        |
| `sticky`   | ✅ Oui (partiellement)  | En-têtes, colonnes collantes          |

---

## Mediagraphie

- MozDevNet. (n.d.-a). *Propriété CSS position*. CSS | MDN. [https://developer.mozilla.org/fr/docs/Web/CSS/Reference/Properties/position](https://developer.mozilla.org/fr/docs/Web/CSS/Reference/Properties/position){target=_blank} 

<section class="niveau-ia-production">
    <div class="colonne-image">
        <img src="../../images/ia/AIA_768x1024.png" width="64">    
    </div>
    
    <div class="colonne-description">
        <span class="ia-titre accent">Aidé de l'intelligence artificielle</span>

        <p>J’ai utilisé l’outil d’intelligence artificielle 
            <span class="accent">ChatGPT, GPT-5.6 Luna</span> 
            afin de 
            <span class="accent">résumer les valeurs de la propriété position</span>. 
        </p>
        <p>Plus précisément, j’ai demandé à l’outil d’accomplir les tâches suivantes : </p>
        <ul>
            <li>Créer un tableau en markdown</li>
            <li>Y résumer les différentes valeurs de position et les comparer entre elles</li>
        </ul>
    </div>
</section>