---
title: API
description: ""
position: 2
category: Twitter Clone
---

Vous retrouverez dans cette section liées à l'utilisation de l'API pour réaliser votre clone de Twitter.<br/>
L'API est accessible depuis l'URL suivante <code>https://fges-twitter-clone.herokuapp.com/</code>.

Chacun de vous va se voir attribuer une clé afin de se connecter à cette API. <br>
Vous serez identifié avec votre nom et prénom et toutes les actions que vous ferez à partir de cette API utiliseront cette identité pour réaliser les différentes actions demandées.

## Utiliser la clé API

Afin d'utiliser votre clé API, vous devrez la passer en tant que <code>header</code> de votre requête en utilisant le header : <code>x-fges-user-key</code>.

Exemple avec <code>axios</code>: <br>

```js
axios.get("https://fges-twitter-clone.herokuapp.com/", {
  headers: {
    "x-fges-user-key": "Your API key",
  },
});
```

## Définitions API

Cette section contient la définition des différents appels <b>REST</b> .

### <code>/allTweets</code>

<code><b>Method: GET </b></code>

Cette méthode renvoie tous les tweets de tous les utilisateurs.

La réponse API contient un tableau de tweets, chacun défini selon la structure de données suivante :

<code><b>Tweet</b></code>

- <code>_id</code>(<code>string</code>)
  - Id du tweet
- <code>owner</code>(<code>string</code>)
  - L'id de l'utilisateur qui a posté le tweet
- <code>parent</code>(<code>string</code>)
  - L'id du tweet parent. Si ce champ est vide, ça veut dire que ce Tweet est un tweet racine.
- <code>children</code>(<code>Tweet[]</code>)
  - Un tableau de tweets enfants. La structure des tweets enfants ressemble à celle du parent. A la seule différence que les tweet enfants n'ont pas d'enfants eux même. Seuls les tweets racine ont des enfants.

Exemple de réponse :

```json
[
  {
    "_id": "617d4d7865657a04174e5a0a",
    "owner": "617d4ca565657a04174e5a09",
    "message": "Hello World",
    "parent": "",
    "children": [
      {
        "_id": "617d68a765657a04174e5a0d",
        "owner": "617d4ca565657a04174e5a09",
        "message": "Hola que tal"
      },
      {
        "_id": "617d68e065657a04174e5a0e",
        "owner": "617d4ca565657a04174e5a09",
        "message": "Encore moi"
      }
    ]
  },
  {
    "_id": "617db5ee1312efcc30368b16",
    "owner": "617d4ca565657a04174e5a09",
    "message": "Second tweet",
    "parent": "",
    "children": []
  }
]
```

### <code>/tweet/:id</code>

<code><b>Method: GET </b></code>

Cette route permet de récupérer un Tweet spécifique grâce à son id. <br>
L'id doit être passé dans la route de l'appel.

Exemple avec axios: 

```js
axios.get('/tweet/monIdDeTweet');
```

Pour retouver la définition d'un tweet, référez-vous à la section <nuxt-link to="/fr/twitterApi#codealltweetscode">/allTweets</nuxt-link> .