---
title: API
description: ""
position: 3
category: "Cours"
---

## Qu'est-ce qu'une API?

Une API, de manière simplifiée, est une interface qui permet d'intéragir avec une application distante.

<img src="https://celitech.com/wp-content/uploads/2021/02/API-schema-915x515.png">

Dans notre cas, nous utiliserons une API principalement pour intéragir avec les données d'une base de données distante afin de permettre à notre application front-end de les utiliser.

## API REST

Dans notre, nous allons principalement parler des API de type <code>REST</code>.

Les API de type REST, permettent d'intéragir avec le serveur distant grâce à des verbes spécifiques, qui définissent l'action réalisée par l'API.

Les principaux verbes qui vont nous intéresser :

- GET : Pour **récupérer** des ressources
- POST : Pour **créer** des ressources
- PUT : Pour **mettre à jour** des ressources
- DELETE : Pour **supprimer** des ressources

## Utilisation avec Vue

Dans notre cas, nous allons utiliser le package <code>axios</code> pour intéragir avec l'API.
C'est le package officiel recommandé pour Vue. Il y a plusieurs autres manières d'appeler des API, mais si vous n'êtes pas expert, je vous conseille de vous limiter à <code>axios</code> dans le cadre de ce cours.

Commencez donc d'abord, par installer <code>axios</code> avec la commande suivante :

```bash
npm i axios
```

Ensuite, là ou vous voudrez l'utiliser, il vous suffira de l'importer et l'utiliser dans votre script :

```js
import axios from "axios";

// EXEMPLE DE GET
axios
  .get("https://monapi")
  .then((result) => {
    // Gérer le cas de succès
  })
  .catch((error) => {
    // Gérer le cas d'erreur
  });
```
