---
title: Routing
description: ""
position: 2
category: "Cours"
---

## Qu'est-ce que c'est ?

Le routing sert à configurer votre app de manière à lier vos composants à des "**routes**".
Une **route** correspond à quelques détails près à votre URL, c'est ce qui permet à votre navigateur de savoir vers où il doit aller.

Etant donné qu'on est en mode SPA ( Single Page Application ), on ne redirige plus vers des fichiers **html** comme on pouvait le faire avant, mais vers des composants.

Le <code>Router</code> va donc nous permettre de connecter des **routes** à des **composants**.<br/>
Ainsi, votre url "https://monsite/toto" pourra par exemple vous rediriger vers votre composant <code>Toto.vue</code>.

## Utilisation du Router

### Installation

Afin d'utiliser le Router de Vue, il faut d'abord installer le package <code>vue-router</code>. <br/>
Executez donc la commande suivante pour l'installer :

```bash
npm i vue-router
```

### Configuration

#### Fichier de routing

Afin de pouvoir configurer votre router, on va d'abord créer un fichier qui contiendra la configuration nécessaire pour que celui-ci fonctionne comme vous le souhaitez.

Commençons par créer un fichier <code>routing.js</code> :

```js
import { createRouter, createWebHistory } from "vue-router";
// Ici, on importe les composants qu'on veut configurer
// Dans ce cas, ce sera Accueil et Details
import Accueil from "./Accueil.vue";
import Details from "./Details.vue";

// Nous créons d'abord nos Routes
const routes = [
  // En n'indiquant rien d'autre que '/' dans path
  // Nous disons à Vue que c'est la page racine
  // Donc, la racine de votre application
  // Affichera le composant "Home.vue"
  {
    path: "/",
    component: Home,
  },
  // Ici, nous disons que pour la route "/details"
  // Nous afficherons le composant "Details.vue"
  {
    path: "/details",
    component: Details,
  },
];

// On crée notre router à partir des routes configurées
export default createRouter({
  // Afin que votre Router puisse fonctionner correctement
  // Nous avons besoin de lui créer un système d'historique
  history: createWebHistory(),
  // Nous ajoutons les routes fraîchement configurées
  routes,
});
```

### Ajout à l'app

Bon, c'est bien, vous avez configuré et créé votre router, mais si vous ne l'utilisez pas, il est inutile.

Il faut donc l'ajouter à votre application. Pour celà, allons dans notre <code>main.js</code> :

```js
import { createApp } from 'vue';
import App from './App.vue';
// On importe notre router du fichier qu'on a créé avant
import router from './routing';

const app = createApp(App);

// On utilise notre router grâce à la méthode 'use'
app.use(router);

app.mount('#app');
```

### Utilisation

Maintenant que votre <code>Router</code> est configuré, il faut dire à notre application ou l'appeler. 

Nous allons donc découvrir deux composants principaux, qui permettront d'intéragir avec le router : 

- <code>RouterView</code>
- <code>RouterLink</code>

#### RouterView

Le composant <code>RouterView</code>, permet d'afficher un composant configuré dans notre router, si on fait

```html
    <RouterView />
```
dans un composant, ça va, dans un premier temps, afficher le composant lié à la route actuelle. Si nous somme sur 'http://localhost/' il va afficher le composant <code>Home</code>, car on est à la racine. 
Si on est sur <code>/details</code> il va afficher le composant <code>Details</code>.
De plus, à chaque fois qu'un changement de route est effectué, il va automatiquement remplacer le composant affiché, par le composant lié à la route à laquelle vous avez navigué.

Pour l'instant, on se limitera à cette utilisation là. Pour les plus curieux d'entre vous qui seraient intéressés par des utilisations plus poussées, je vous invite à aller consulter la doc de VueRouter : https://router.vuejs.org/ .

#### RouterLink

Le <code>RouterLink</code> est le composant qu'on va utiliser pour naviguer entre nos **Routes**. 
Il faut le voir comme un élément <code>\<a>\</a></code> mais qui gère uniquement les routes de votre app.

Exemple : 

```html
<RouterLink to="/details"></RouterLink>
```
Va créer un lien, qui lorsque vous cliquez dessus, va vous emmener sur la Route <code>/details</code> de votre application.
