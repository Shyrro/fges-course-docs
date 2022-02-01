---
title: Les bases
position: 3
category: Cours
---

## Directives

Une directive est un attribut html qu'on peut assigner aux éléments afin qu'ils réalisent une fonction précise. Dans cette section nous énuméreront les directives de base, mais sachez qu'il en existe d'autres et qu'on peut même en créer soi même.

Pour les plus curieux d'entre vous, vous pouvez trouver plus d'informations dans la documentation officielle de Vue en suivant les liens suivants: 
- https://v3.vuejs.org/api/directives.html#v-text
- https://v3.vuejs.org/guide/custom-directive.html#custom-directives. 

Pour les autres, dans le cadre de ce cours, vous n'aurez pas besoin de plus que les directives listées ici.

### v-model

Cette directive permet de lier une variable à un élément de manière **bi-directionnelle**. Celà veut dire que l'appellant et l'appellé peuvent tous deux agir sur cette variable afin de la modifier. 

Exemple : 

```html
<template>
    <input v-model="nom" />
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
    data: () => {
        return {
            nom: '',
        }
    }
})
</script>
```

Dans cet exemple, la variable <code>nom</code> sera modifiée si le présent composant la modifie, mais également lorsque l'utiliseur va modifier sa valeur dans l'input. A chaque fois que l'input va détecter un changement de la variable, il va la mettre à jour. 

Ainsi, il n'y a pas besoin de vérifier un événement spécifique sur l'input tel que <code>change</code> ou <code>blur</code> etc. pour réagir au changement de la variable.

### v-if

Cette directive permet de conditionner l'affichage d'un élément en fonction d'une condition.

Exemple :

```html {all|3,11|all}
<template>
  <input v-model="name">
  <span v-if="name === 'bob'"> {{ name }} </span>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data: () => {
    return {
      name: 'toto',
    }
  },
})
</script>
```

Dans cet exemple, nous avons un input qui prend en _v-model_ notre <code>name</code> qu'on a déclaré comme <code>data</code>. <br>
Juste à côté, un <code>\<span></code> qui est censé afficher la valeur de cette data. En revanche, comme nous avons ajouté la directive <code>v-if</code> sur l'élément, il n'affichera le nom que lorsque la condition dans le <code>v-if</code> est remplie. 

C'est à dire qu'il n'affichera le <code>\<span></code> uniquement lorsque la valeur du name sera égale à **bob**

### v-for

Cette directive permet d'itérer sur un tableau pour nous permettre d'afficher son contenu. 
Elle fonctionne de la même manière qu'une boucle normale telle que vous les connaissez, la différence est qu'elle s'applique directement sur le <code>template</code>.

Exemple : 

```html {all|3-5,15|all}
<template>
  <ul>
    <li v-for="legume in legumes" :key="legume.id"> 
      {{ legume.value }} 
    </li>
  </ul>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data: () => {
    return {
      legumes: [
        {
          id: 1,
          value: 'tomate',
        }, 
        {
          id: 2,
          value: 'oignon',
        }, 
        {
          id: 3,
          value: 'carotte',
        }]
    }
  }
});
</script>
```

Dans cet exemple, on itère sur un tableau de **légumes**. Chaque objet "légume" contient un <code>id</code> qui correspond à l'identifiant de l'objet ainsi qu'une valeur <code>value</code>.

Nous souhaitons itérer sur ce tableau, afin d'afficher une liste affichant le nom des légumes. 
On itère donc sur le tableau, en lui disant que pour chaque **légume** on veut afficher <code>legume.value</code>. 

On lui indique également quelle est la clé d'indexation dans <code>:key</code>, afin qu'il puisse mieux optimiser le rendu.

### v-on

La directive <code>v-on</code> permet de dire à un élément ce qu'il doit faire quand un événement est déclenché.

Prenons cet exemple : 

```html
<template>
  <button @click="counter++">Incrémenter</button>
  <span> {{ counter }} </span>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data: () => {
    return {
      counter: 0,
    }
  }
});
</script>
```

Dans cet exemple, nous voulons qu'à chaque fois que l'événement <code>click</code> est déclenché, nous incrémentons la data <code>counter</code>. 

Vous remarquerez que dans l'exemple j'écris <code>@click</code> alors qu'on parle de directive. C'est tout simplement que <code>@click</code> est l'écriture abrégée de <code>v-on:click</code> et que je vous conseille d'utiliser.

Pour plus d'informations sur cette directive, je vous conseille de lire la documentation officielle de Vue : https://v3.vuejs.org/api/directives.html#v-on .

### v-bind

La directive <code>v-bind</code> permet de lier une donnée du composant à un attribut d'un élément du template.
Par exemple, dans le code suivant, nous affectons la donnée <code>imgUrl</code> à notre élément <code>\<img></code>.

```html
<template>
  <img :src="imgUrl">
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data: () => {
    return {
      imgUrl: 'https://...',
    },
  },
})
</script>
```
Dans cet exemple, vous remarquez que vous ne voyez pas la directive `v-bind`, c'est normal, car <code>:src</code> est une manière raccourcie d'écrire <code>v-bind:src</code> et c'est la manière dont il faudra l'écrire de manière générale.

## Options

### computed

Une <code>computed</code>, est une valeur calculée. Dans le composant, elle est définie comme une fonction sans paramètre mais utilisée comme une <code>data</code>. 

Le but d'une <code>computed</code> et de garder un <code>template</code> déclaratif et plus lisible, tout en améliorant les performances. 

Si on prends l'exemple suivant : 

```html
<template>
  <input v-model="nom" placeholder="nom"/>
  <input v-model="prenom" placeholder="prenom"/>
  <p>{{ fullName }}</p>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      nom: '',
      prenom: ''
    }
  },
  computed: {
    fullName() {
      return `${this.nom} ${this.prenom}`; 
    }
  }
})
</script>

```

La valeur de la computed <code>fullName</code> sera recalculée à chaque fois que la valeur de la data <code>nom</code> ou <code>prenom</code> est modifiée. 
Elle ne sera donc pas recalculée à chaque fois si les valeurs restent inchangées. 

Tandis que si on décide ne pas utiliser de computed et de faire : 

```html
<template>
  <input v-model="nom" placeholder="nom"/>
  <input v-model="prenom" placeholder="prenom"/>
  <p>{{ nom + ' ' + prenom }}</p>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      nom: '',
      prenom: ''
    }
  },
})
</script>

```

La valeur correspondant au nom complet sera recalculée à chaque fois qu'un <code>rendu</code> de la page est effectué. 
Egalement, on voit que celà rends le code moins maintenable et nous avons en plus une opération dans le <code>template</code>, qui nous fait perdre le côté **déclaratif** de Vue.

### methods

Il n'y a pas grand chose à dire sur les méthodes. Vous savez déjà ce que c'est. La seule différence, est qu'ici, ce sont des méthodes **SPECIFIQUES** au composant. Elles ne pourront donc pas utilisées en dehors.

Exemple :

```html
<template>
  <button @click="increment">Incrémenter</button>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      counter: 0,
    }
  },
  methods: {
    increment() {
      this.counter++;
    }
  }
});
</script>
```

Dans cet exemple, nous déclarons une méthode qui permet d'incrémenter la valeur de notre compteur.

### watchers

Les watchers permettent de **surveiller** une variable et d'exécuter de la logique en conséquence. 

Prenons cet exemple : 

```js
import { defineComponent } from 'vue';

export default defineComponent({
  data: () => {
    firstName: 'Foo',
    lastName: 'Bar',
    fullName: 'Foo Bar',
  },
  watch: {
    firstName: function (newVal) {
      this.fullName = `${newVal} ${this.lastName}`;
    },
    lastName: function (newVal) {
      this.fullName = `${this.firstName} ${newVal}`;
    },
  }
})
```

Dans cet exemple, nous surveillons la data <code>firstName</code> ainsi que la data <code>lastName</code>. A chaque fois que celle ci change, nous récupérons la nouvelle valeur <code>newVal</code> afin de mettre à jour la data <code>fullName</code>.

Vous devez sans doute vous dire que dans ce cas, autant utiliser une <code>computed</code>, et vous aurez raison. Dans la plupart des cas, si vous pensez à utiliser un <code>watcher</code>, réfléchissez avant pour savoir si ce que vous voulez n'est pas possible en <code>computed</code>.


## Communication

### props

Les props, permettent à un composant parent de communiquer avec un composant enfant en lui passant des données. 
La donnée transmise, est, réactive. Si elle change au niveau du parent, le changement sera répercuté dans l'enfant. En revanche, elle n'est **PAS MODIFIABLE** depuis l'enfant.

Exemple : 

```html
<!-- ComposantEnfant.vue -->
<template>
  <span>{{ numero }}</span>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    numero: Number,
  },
});
</script>
```

Nous avons ci dessus, un composant, qui affiche un numéro. On voit ici, que le numéro est défini en tant que props, ce qui signifie que sa valeur sera mise à jour dynamiquement, en fonction de ce que le composant parent a passé.

De son côté, le composant parent, pour appeler ce composant de cette manière : 

```js
<ComposantEnfant numero="3" />
```

ou dans le cas ou il utilise une data :

```js
<ComposantEnfant :numero="maData" />
```

### events

Afin qu'un enfant puisse communiquer avec son parent, il faut qu'il communique avec lui grâce à des <code>events</code>. 
Ces events sont définissables par vous avec le nom que vous souhaitez et sont appelables de la même manière que tous les autres grâce à la directive <code>v-on</code>.

```vue
<!-- MonComposantEnfant.vue -->
<template>
  <button @click="sendDataToParent(donnee)">
    Alert parent
  </button>
</template>
<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data: () => {
    return {
      donnee: 'hello',
    },
  },
  emits: ['update-data'],
  methods: {
    sendDataToParent(data) {
      this.$emit('update-data', data);
    }
  }
});
</script>
```

Dans cet exemple, à chaque fois que dans ce composant, le bouton est cliqué, la méthode <code>sendDataToParent</code> est appelée. Cette méthode fait appel à la méthode <code>this.$emit</code> qui permet au composant, d'envoyer un événement au parent. Ici nous envoyons l'événement <code>update-data</code> au parent avec la data <code>donnee</code>.

Pour que le parent récupère cette donnée, il faut qu'il appelle le composant en précisant quoi faire lors de la réception de l'événement.

Exemple :

```vue
<template>
  <mon-composant-enfant @updateData="handleChildData"/>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  methods: {
    handleChildData(payload) {
      console.log(payload.donnee);
    }
  }
})
</script>
```