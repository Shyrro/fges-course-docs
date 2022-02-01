---
title: TP1
position: 4
category: Travaux
---

## Exercice 1

Créer un composant, permettant d’afficher une valeur en km, m, cm et mm.

- En utilisant des computed
- En utilisant des watchers

## Exercice 2

Créer un formulaire d’inscription qui prend :

- nom
- prénom
- date de naissance
- adresse mail

Au clic sur le bouton d’inscription, cacher le formulaire et afficher **“Félicitations, vous êtes inscrits”**.

## Exercice 3

Ajouter des validations sur le formulaire de l’exercice précédent pour empêcher le clic sur le bouton d’inscription si les données saisies sont invalides ( soit vides, soit pas au bon format ).

## Exercice 4

Créer un composant <code>Carrousel</code>, qui permet de faire défiler des images en prenant en props une liste d’images.

Il est constitué d’un bouton à gauche qui permet de défiler les images vers la gauche, d’une image au milieu et d’un bouton à droit permettant le défilement à droite.

## Exercice 5

Créer une TodoList.

- Un composant pour chaque élément de la liste
- Un composant pour la liste
- Un composant qui regroupe les deux composants précédents ainsi que des boutons pour ajouter des éléments à la liste.

Chaque élément de la liste contient un bouton permettant de supprimer un élément de la liste.


## Exercice 6

Créer un formulaire d’inscription avec plusieurs étapes:

- **Etape 1 :** Données personnelles ( nom, prenom, age, sexe etc)
- **Etape 2 :** Adresse postale, rue etc
- **Etape 3 :** Acceptation des conditions générales

Le formulaire doit avoir une barre de progression indiquant l’étape. Chaque étape contient un formulaire avec les données correspondantes ainsi qu’un bouton “suivant” qui est grisé tant que le formulaire n’est pas valide.<br>
Au clic sur suivant, on passe à la prochaine étape du formulaire et la barre de progression doit être mise à jour. <br><br>
L’image ci dessous donne un exemple de ce qui est attendu :

<img src="/progress.png" />

