---
title: Prérequis
position: 2
category: Configuration
---

Cette section vous permet de configurer votre poste afin de pouvoir développer sans soucis en cours.
Vous y trouverez le liens à télécharger, ainsi que le prérequis nécessaires si vous ne les avez pas déjà.

## Runtime

Il vous faut avoir `nodejs` dans une version qui est minimum >=14.

<img src="http://www.alekos.fr/wp-content/uploads/2016/06/nodejs.jpg">

Lien pour télécharger : https://nodejs.org/


## IDE

Il vous faudras également un IDE pour pouvoir développer. Il faut que votre IDE soit compatible avec les différents frameworks Javascript récents. 

Pour ma part, je vous conseille VSCode. Vous pouvez choisir autre chose, mais gardez en tête que si c'est un IDE que je ne connais pas, je ne pourrais pas toujours vous aider.

Pour ceux qui ont fait le choix de VSCode, je vous demander d'installer les extensions suivantes ( Vous pouvez cliquer dessus pour aller sur la page de téléchargement ): 

- <a href="https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode" target="_blank">Prettier</a>
- <a href="https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar" target="_blank">Volar</a>
- <a href="https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint" target="_blank">ESLint</a>
- <a href="https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare" target="_blank">LiveShare</a> (cette extension vous permet de partager en live votre code avec moi)

Pour ceux qui souhaitent avoir des thèmes plus agréables et qui ne savent pas ou chercher, je vous conseille les thèmes Material suivants, pour les couleurs et icônes.

- <a href="https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme" target="_blank">Material Theme</a>
- <a href="https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme" target="_blank">Material Icon Theme</a>

## Git

<img src="https://miro.medium.com/max/800/1*Jl2VDHVzFBDdXggRprziUg.png">

Pour que je puisse améliorer constamment le contenu des cours, j'aurai besoin de vos repos git que je regarderai souvent.

Vous pouvez choisir ce que vous voulez entre <a href="https://github.com" target="_blank">Github</a>, <a href="https://gitlab.com" target="_blank">Gitlab</a> ou <a href="https://bitbucket.org" target="_blank">Bitbucket</a>.

Une fois votre Git créé, vous pouvez le mettre dans la section du Discord `gits`.

## Application Vue

Pour suivre ce cours, vous allez devoir savoir comment créer une application Vue.

Il y'a plusieurs manières possibles de le faire. De notre côté, nous allons utiliser <a href="https://vitejs.dev/" target="_blank">Vite</a> pour créer nos applications.

Si vous voulez créer un application nommée `mon-application`, vous pouvez executer la commande suivante : 

```bash
npm init vite@latest mon-application -- --template vue
```

Celà va vous créer le dossier `mon-application`.

Pour lancer votre application, allez dans le dossier avec la commande :

```bash
cd mon-application
```

Commencez par installer les dépendances avec la commande : 

```bash
npm install
```

Une fois installées, vous pourrez ensuite lancer votre application en lancant la commande: 

```bash
npm run dev
```