# Héberger un site sur GitHub Pages

GitHub Pages est un service d'hébergement offert gratuitement par Github et qui utilise les fichiers HTML, CSS et Javascript d'un dépôt pour ensuite les publier comme un site internet standart.

## Créer un dépôt sur GitHub

La première étape consiste à se créer un dépôt sur GitHub. Le nom du dépôt doit **obligatoirement** avoir la structure suivante : **username.github.io** où username est votre nom d'usager sur GitHub. 

Pour créer un nouveau dépôt, allez sur GitHub et cliquez sur l'onglet Repositories.  Cliquez ensuite sur le bouton  **New** qui se situe en haut à droite. Attention de bien vérifier l'orthographe car à la moindre erreur le site ne sera pas affiché. 

![github_create_repo](../../assets/images/git_githubpages_01.png)

Le nom du repository (dépôt) serait dans mon exemple {==FrechetteMathieu.github.io==}, vous n'avez pas à modifier les autres paramètres. Assurez-vous par contre que le dépôt est public, les dépôts privé ne pourront pas être "transformés" en page web.

Ensuite vous avez deux choix, selon de que votre projet soit déjà initialisé ou non par git. 

## Deux choix pour lier votre site à Github

### 1. Commencer un site à partir de zéro

Si vous n'avez pas commencé le développement de votre site le plus simple est de cloner le dépôt que vous venez de créer. Vous devez débuter par récupérer l'url de votre dépôt.  Sur la page GitHub du dépôt cliquez sur le bouton "Code" en haut à droite et copiez l'url affiché.

![github_clone](../../assets/images/git_githubpages_02.png)

Allez ensuite dans le répertoire de votre projet et ouvrez une console Git Bash en cliquant avec le bouton droit de la souris et en sélectionnant **git bash here** dans le menu. Dans la console, clonez maintenant le dépôt avec la commande git clone suivi de l'url que vous avez récupéré.

```bash
git clone https://github.com/username/username.github.io
```

### 2. Lier un projet existant

Si votre projet est déjà commencé et qu'un dépôt Git est déjà créé en local (sur votre portable), vous pouvez l'associer avec le dépôt créé sur GitHub, sinon vous devez commencer par initialiser un [dépot](./git_basics.md#initialiser-un-depot). Allez dans le répertoire de votre projet et ouvrez une console Git Bash en cliquant avec le bouton droit de la souris et en sélectionnez **git bash here** dans le menu. Dans la console, entrez la commande suivante en remplaçant l'url par celui du dépôt sur GitHub : 

```bash
git remote add origin https://github.com/username/username.github.io
```

Pour valider que le liaison fonctionne, vous pouvez utiliser la commande 

```bash
git remote -v
```
Si tout a fonctionné vous allez voir à l'écran l'url du dépôt GitHub

![git_remote](../../assets/images/git_githubpages_03.png)

Vérifiez ensuite que la branche de votre projet local correspond à la branche par défaut du dépôt Github. 

``````bash
git branch --show-current
``````

Vous indiquera le nom de la branche dans laquelle vous êtes. Si elle est différente renommez là pour avoir le même nom que sur Github avec la commande suivante

``````bash
git branch -m nom_de_la_nouvelle_branche
``````

Un fois assuré que les noms des branches correspondent, il vous restera à pousser votre site sur le dépôt Github. Faites un commit des changements et de vos fichiers

``````bash
# ajoute tous les fichiers dans la file d'attente
git add .
# effectue le commit
git commit -m "Premiere mise en ligne"
# Copie les fichiers vers le dépôt Github
# main est égale au nom de la branche sur votre portable
git push -u origin main
``````

Si vous avez une erreur avec la dernière commande git push, essayer de forcer le push avec la commande suivante 

``````bash
git push -F origin nom_de_la_branche_local
``````

## Accéder à mon site

Pour accéder à la version en ligne de votre site, vous n'avez qu'a utiliser l'url `https://LeNomDuDépôt`. Dans l'exemple plus haut l'url serait donc `https://designweb-a2021.github.io/`



