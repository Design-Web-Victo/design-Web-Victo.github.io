# GitHub

Il est tout à fait possible d'utiliser uniquement Git pour faire une gestion locale des versions de ses projets de développement. Cependant, il peut être intéressant de partager son code sur une plateforme collaborative. Il existe plusieurs plateformes intégrant Git, les 2 plus connues étant GitHub (utilisée principalement pour le partage de projets publics) et Bitbucket (utilisée principalement pour la collaboration de projets privés). Dans le cadre du cours, nous utiliserons GitHub. 

## Différences entre Git et GitHub

- Git est un outil permettant aux développeurs de gérer le cycle de vie de leurs projets.
- GitHub est une plateforme web intégrant les fonctionnalités Git permettant de collaborer sur des projets de développement.

## Publier un projet sur la plateforme GitHub

La première étape consiste à se créer un dépôt sur GitHub. Le nom du dépôt est à votre discrétion, mais doit être différent des autres dépôts qui sont associés à votre utilisateur ou une organisation. (**Attention**, si vous créez un dépot pour héberger un site web, vous devez suivre la nomenclature décrite dans les notes de cours portant sur [GitHub Pages](./git_githubpages.md))

Pour créer un nouveau dépôt, allez sur GitHub et cliquez sur l'onglet Repositories.  Cliquez ensuite sur le bouton  **New** qui se situe en haut à droite. 

![github_create_repo](../../assets/images/git_githubpages_01.png)

Ensuite vous avez deux choix, selon de que votre projet soit déjà initialisé ou non par git. 

### 1. Commencer un projet à partir d'un dépôt

Si vous n'avez pas commencé le développement de votre projet, le plus simple est de cloner le dépôt que vous venez de créer. Vous devez débuter par récupérer l'url de votre dépôt.  Sur la page GitHub du dépôt cliquez sur le bouton "Code" en haut à droite et copiez l'url affiché.

![github_clone](../../assets/images/git_githubpages_02.png)

Allez ensuite dans le répertoire de votre projet et ouvrez une console Git Bash en cliquant avec le bouton droit de la souris et en sélectionnant **git bash here** dans le menu. Dans la console, clonez maintenant le dépôt avec la commande git clone suivi de l'url que vous avez récupéré.

```bash
git clone https://github.com/utilisateur/nom-du-depot
```

### 2. Lier un projet existant

Si votre projet est déjà commencé et qu'un dépôt Git est déjà créé en local (sur votre portable), vous pouvez l'associer avec le dépôt créé sur GitHub, sinon vous devez commencer par initialiser un [dépot](./git_basics.md#initialiser-un-depot). Allez dans le répertoire de votre projet et ouvrez une console Git Bash en cliquant avec le bouton droit de la souris et en sélectionnez **git bash here** dans le menu. Dans la console, entrez la commande suivante en remplaçant l'url par celui du dépôt sur GitHub : 

```bash
git remote add origin https://github.com/utilisateur/nom-du-depot
```

## Soumettre le projet local sur un dépôt GitHub
Une fois le lien établi entre votre projet local et le dépôt GitHub, continuez d'utiliser les [commandes principales}(\notes_de_cours\git_basics/#resume-des-commandes-principales) pour gérer les versions de votre projet. Pour déployer votre projet local en ligne, utilisez la commande suivante : 

```bash
git push
```