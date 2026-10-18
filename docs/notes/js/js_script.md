# Ajouter un script à une page Web

Développé initialement pour ajouter un peu de dynamisme aux pages web, JavaScript est devenu aujourd'hui un incontournable du développement web. Il peut être utilisé à la fois du côté client (depuis un navigateur) ou bien du côté serveur. C'est un langage de script qui n'a pas besoin d'être compilé, il est exécuté directement par le navigateur. Les scripts (nom donné aux "programmes" JavaScript) peuvent être écrits directement dans un fichier HTML ou dans un fichier portant l'extension js.

Tout comme les règles CSS, on peut ajouter un script directement dans un fichier HMTL ou relier un fichier qui contient le script au fichier HTML.

## Dans un fichier HTML

- Utilsez la balise `script`.
- Elle peut être utilisée à l'intérieur de la balise `head` et `body`.
- Utilisez qu'une balise `script` par fichier html pour une meilleure lisibilitée.

``` html
<script type="text/JavaScript">
    alert('Hello, world!');
</script>
```

!!! note

    Idéalement, on va réserver l'ajout de script directement dans un fichier html à des utilisations simples et brèves. La plupart du temps les scripts **sont contenus dans des fichiers externes**.

## Dans un fichier externe

- Le fichier portera l'extension **js**
- Nous allons conserver les fichiers js dans un répertoire situé à la racine du projet et nommé js.
- Il faut le relier au fichier html comme on le fait avec nos fichiers css
- On utilise la balise `script` mais en lui fournissant le chemin relatif vers le fichier

``` html
<script defer src="mes_scripts.js"></script>

<!-- Pour ajouter plus d'un fichier, on répète avec les autres fichiers -->
<script defer src="deuxieme_script.js"></script>
```

!!! Note

    La maintenance et la clarté du code est une raison d'extraire les scripts dans des fichiers externes. Mais l'avantage majeur est que le navigateur va télécharger les fichiers en cache. Ensuite si une autre page html fait référence à un des fichiers téléchargés, il sera lu depuis le cache et non pas téléchargé à nouveau, ce qui réduit le trafic et permet à la page de s'afficher plus rapidement.

### Utilisation de l'attribut defer et async de la balise script

Par défaut, quand on charge un script depuis un fichier externe, il ==sera exécuté immédiatement==. Ça peut poser un problème si notre script interagit avec des éléments du DOM car ceux-ci peuvent ne pas être encore "chargés" (accessibles) lors de exécution du script. Pour palier à ce problème on peut soit charger nos scripts à la toute fin de notre fichier HTML ou bien utiliser l'attribut _defer_ ou _async_ de la balise **script**.

- **defer** sera utilisé quand on veut manipuler des éléments de la page et être sûr qu'ils sont chargés. Le script ne bloquera pas l'affichage de la page et sera exécuté une fois celle-ci chargé en entier.
- **async** sera utilisé pour un script qui est totalement indépendant de la page html. L'exécution ne bloquera pas l'affichage de la page et sera lancé une fois le script terminé.

**Exemple**

``` html
<script defer src="mes_scripts.js"></script>
<script async src="mon_script_async.js"></script>
```

Source : [https://JavaScript.info/script-async-defer](https://JavaScript.info/script-async-defer){target=_blank}

## Exercices

Testons l'ajout de script avec un petit exercice simple.

- Sur GitHub créez un dépôt nommé **exercices_js** (Lors de la création cochez "**Add a README file**").
- Clonez le dépôt dans le répertoire du cours. (Vous allez réutiliser ce projet pour d'autres exercices)
- Créez un fichier nommé **index.html** et ajoutez-y les balises de base d'une page html.
- Ajoutez à l'aide de la balise **script** le code JavaScript pour faire afficher votre message.

Maintenant on va refaire la même chose mais depuis un fichier externe.

- Toujours dans le projet **exercices_js**, créez un nouveau sous-répertoire nommé **js**.
- Dans ce sous-répertoire, créez un fichier nommé **helloworld.js**.
- Ajouter le code dans ce nouveau fichier. (Uniquement la ligne `alert('Mon message depuis un script')`, pas la balise **script**).
- Faites référence à ce fichier en utilisant la balise **script** dans votre fichier html.
- Rechargez la page pour voir le résultat.

Vous devriez avoir comme résultat deux messages qui s'affichent à l'écran, un depuis le fichier html et un autre depuis le fichier js externe.

!!! note ""

    Ajoutez `defer` en attribut à la balise script qui fait référence à votre fichier JavaScript.

    - Est-ce que vous voyez une différence?
    - Pouvez-vous expliquer ce comportement?

On va afficher un troisième message, mais cette fois dans la console du navigateur avec la fonction **console.log()**.

- Ouvrez la console en faisant un clique droit dans la page, ensuite inspecter dans le menu contextuel et l'onglet console.
- Ajoutez un message de votre chois dans le fichier **helloworld.js**.
- Rechargez la page pour voir le résultat.

``` js
console.log("Message à la console");
```

- [x] Quand vous aurez terminé l'exercice, créez un commit nommé "Ajout d'un script" et envoyez-le sur GitHub (git push)

!!! Note 

    Chaque navigateur nous donne accès à une console qui affiche différents messages (d'avertissements, d'erreurs, etc.). 
    Les messages affichés dans la console ne sont pas vus par l'utilisateur qui consulte la page web. Il faut ouvrir la 
    console pour les visualiser. La console est un outil très utilisé pour suivre vos scripts et les "débugger". 
    
    Plus de détail : [La méthode console.log()](https://developer.mozilla.org/fr/docs/Web/API/console/log_static){target=_blank}
