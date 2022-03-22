---
title: Projet
position: 5
category: Travaux
---

Dans le cadre de votre projet, je vous propose plusieurs API à utiliser pour construire votre site autour. <br>Vous pouvez évidemment utiliser d'autres API ou des APIs que vous auriez fait vous même, la seule condition est que je puisse éxecuter **facilement** app.<br><br>
Le but du projet est de vous faire utiliser toutes les notions vues en cours.
Vous avez également une grille de notation pour vous aider à mieux vous organiser.

Le projet se fera par groupe de 2 et vous avez la liberté de faire votre site comme
vous le souhaitez, vous ne serez pas noté sur sa conception mais sur l’utilisation
correcte des concepts vues en cours.

Chaque groupe de projet devra donner sur Discord dans la section <code>#gits-projets</code>, le git de son projet ainsi que les noms des personnes du groupe.

Les gits de vos projets peuvent être en privé contrairement aux gits de cours. <br>
⚠️ **Pensez à me rajouter en tant que contributeur** ⚠️

## Liste d'APIs

### Rick & Morty 

<img src="https://intrld.com/wp-content/uploads/2019/01/rickmorty.png.webp" />

Créer un site permettant de parcourir les personnages de la série, en affichant des
liens vers les épisodes (en fonction de ce que l’api renvoie pour chaque épisode ) et
un détail de la localisation de chaque personnage. <br> <br>
Le but est de pouvoir rechercher, filtrer par personnage, par épisode etc.<br>
Evidemment, si l’API vous donne des idées, n’hésitez pas à les exploiter et vous
amuser. 😉 <br> <br>
La documentation de l’API est disponible via le lien suivant :

https://rickandmortyapi.com/documentation/#rest

### Pokédex

<img src="http://static.hitek.fr/img/actualite/2016/12/23/w_pokemon-by-purpleblades-d661egz.jpg">

Créer un pokédex en utilisant l’API suivante : https://pokeapi.co/ . <br>
Vous pouvez vous inspirer du site : https://www.pokemon.com/fr/pokedex .

### Studio Ghibli

<img src="https://webzine.one/wp-content/uploads/studio-gihbli-960x384.jpg">

Vous pouvez vous baser sur cette API pour répértorier les films de studio ghibli ainsi
que leurs personnages. <br>
Ceci dit cette API ne contient pas d’images, gardez celà en tête si vous pensiez
afficher les images des films. <br><br>
Lien de l’API : https://ghibliapi.herokuapp.com/


## Barème

| Maitrise des bases de Vue             | 5pts  |
|---------------------------------------|-------|
| - Rendu déclaratif des variables              |
| - Liaison de données                          |
| - Utilisation intelligente des composants     |
| - Communication entre composants              |
| - Bonne utilisation des options d'un composant |
| - Utilisation intelligente des directives     |
| - Modification intelligente de la css         |

| Maitrise du router                    | 5pts  |
|---------------------------------------|-------|
| - Configuration du router             |       |
| - Navigation à l'aide de routes entre composants |       |
| - Passage de paramètres/props/query intelligent entre les routes|
| - Utilisation de sous routes ( Si besoin ) |

| Maitrises des appels RESTfull via axios| 3pts  |
|---------------------------------------|-------|
| - Appel d'API REST                           |
| - Gestion des succès et erreurs       |
| - Formattage des données reçues |

| Maitrise du store                     | 5pts  |
|---------------------------------------|-------|
| - Utilisation de getters                      |
| - Utilisation des mutations                   |
| - Réutilisation des données du store entre les composants |

| Propreté du code (commentaires, indentation...) + présence d’un README explicatif| 2pts  |
|---------------------------------------|-------|

## Recommandations

Dans cette section, je vous conseille quelques librairies UI pour vous économiser du temps dans votre projet. 

Voici les librairies compatibles Vue 3 que je vous conseille : 

### NaiveUI

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--e52ZPnB1--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pgv7cugpx4pkcpypduvc.png">

Naive UI est librairie offrant des composants légers avec des utilitaires ready to use correspondant à la plupart des cas que vous allez rencontrer. 

Lien de la documentation : https://www.naiveui.com/en-US/os-theme;

### PrimeVue

<img src="https://i1.wp.com/www.primefaces.org/wp-content/uploads/2021/05/hashnode-vue-3.5.02x.jpg?resize=1060%2C557&ssl=1">

Prime Vue est une librairie complète qui vous offre différents thèmes intégrés utilisables pour votre application ainsi que des composants très complets. 

Documentation : https://www.primefaces.org/primevue/#/setup

### VantUI

<img src="https://92ui.net/wp-content/uploads/2021/03/bc0ff793e533afaf9f3abc0f82c8da1d.jpg" />

VantUI est une librairie dont les composants sont adaptés à l'utilisation mobile.

Documentation : https://vant-contrib.gitee.io/vant/#/en-US/home


Il existe évidemment, une infinité d'autres librairies, ceux ci ne sont que des recommandations de librairies que je pense adaptées à l'usage de vos projets.


<style>
tbody > tr {
    border:none!important;
    line-height: 0.5em;
}

thead > tr > th:nth-child(2) {
    text-align: right;
}
</style>