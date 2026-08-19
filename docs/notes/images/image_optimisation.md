# Optimiser les images d'un site Web

Voici plusieurs trucs pratiques pour optimiser les images d’un site Web et améliorer la performance, le référencement et l’accessibilité.


## 1. **Choisir le bon format**

Utiliser le format d'images qui est adapté à votre besoin. Voici un petit rappel des formats principaux avec leurs usages courants : 

* **JPEG** : Photos, paysages, .
* **PNG** : Logos, images avec transparence.
* **WebP** : Idéal pour la majorité des usages (photos et transparence).
* **SVG** : Logos et éléments vectoriels (scalable, léger).

Pour plus de détail : [Les types d'images pour le web](./image_type.md)

## 2. **Redimensionner à la bonne taille**

* Fournis des images **aux dimensions réelles d’affichage**.
* Ne charge pas une image de **4000 px** si elle s’affiche en **800 px**.


## 3. **Utiliser `srcset` quand c'est pertinent**

Fournir plusieurs résolutions d'une même image permet de ne charger que la résolution adapté à l'écran.

```html
<img 
  src="img/photo-1200.jpg"
  srcset="
    img/photo-600.jpg 600w, 
    img/photo-900.jpg 900w, 
    img/photo-1200.jpg 1200w
    "
  alt="Paysage urbain avec gratte-ciels">
```

## 4. **Activer le chargement différé (lazy loading)**

Ajoutez l'attribut `loading="lazy"` pour n'afficher les images que lorsqu'elle sont visible à l'écran:

```html
<img src="img/gallery.jpg" alt="Exposition d’art" loading="lazy">
```

Permet de réduire le temps de chargement initial de la page.


## 5. **Utiliser des noms précis**

- Nom du fichier descriptif : `chaise-bois-chene.jpg` plutôt que `IMG_1234.jpg`.
- Attribut `alt` précis pour l’accessibilité et le référencement :

```html
<img src="chaise-bois-chene.jpg" alt="Chaise en bois de chêne avec assise rembourrée">
```

## 6. **Préférer SVG pour les logos et icônes**

- Léger, vectoriel, net sur tous les écrans.
- Peut être coloré ou animé via CSS/JS.

