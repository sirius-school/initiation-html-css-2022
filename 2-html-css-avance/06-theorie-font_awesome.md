<!-- omit in toc -->
# Font Awesome

Voici un petit tuto sur comment utiliser Font Awesome dans vos projets.

Font Awesome est une police de caractère composé de plus de 7800 icônes. Il y en a des gratuites et des payantes.

De plus l'intérêt est de pouvoir utiliser vos icônes comme une simple police de caractère, toutes les propriétés applicable à du texte le sont aussi sur vos icônes (color, font-size,...)

<!-- omit in toc -->
## Table des matières

- [Mise en place](#mise-en-place)
- [Utilisation](#utilisation)
  - [HTML](#html)
  - [Pseudo-element (avancé)](#pseudo-element-avancé)

## Mise en place

On va importer notre font dans notre fichier `.css`ou `.scss` (sass).

```css
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css');
```

On peut vérifier sur [CDNJS](https://cdnjs.com/libraries/font-awesome) si il y a une nouvelle version disponible.

On pourrait également incorporer le lien vers la police dans nos fichiers `html` mais il faudrait le faire pour chaque page pour ne pas risquer de perdre nos icônes sur certaines pages.

C'est tout ce que l'on a besoin de faire en amont!

[:arrow_up: Revenir au top](#table-des-matières)

## Utilisation

### HTML

Il est possible d'utiliser directement une balise HTML pour afficher son icône. Pour cela, rendez-vous dans [la section Icons du site de Font Awesome](https://fontawesome.com/icons) et choisissez votre icône gratuite. Vous pouvez également éffectuer une recherche.

Une fois votre icône sélectionné cliquez sur la balise `<i>`en haut de l'aperçu de l'icône. Cela copie la balise complète qui est maintenant prête à être intégrée dans votre fichier HTML.

![fa-icon](img/06/fa-icon.gif)

Cette pratique n'est pas la meilleure, car la balise `<i>`est une ancienne balise HTML qui servait à mettre du texte en italique. Elle est voué à disparaître dans une future version de HTML, du coup toutes vos icônes pourrait ne plus fonctionner du jour au lendemain. Vous pouvez donc remplacer cette balise par une balise `<span>`.

[:arrow_up: Revenir au top](#table-des-matières)

### Pseudo-element (avancé)

Une autre méthode est l'utilisation du CSS et des pseudo-element. Voici la marche à suivre:

1. Créez une classe `icon`et placez-y le code nécessaire à l'affichage de votre icône.
2. Créez une classe nommé selon votre icône et appliquez le pseudo-sélecteur `::before`.
3. Dans la propriété `content`de votre `before`placez l'unicode que vous trouvez également au dessus de l'aperçu de l'icône. :exclamation: N'oubliez pas le "backslash" ( \\ ) devant le code en question!
4. Placez une propriété `font-family`et la valeur `Font Awesome 5 Free` ou `Font Awesome 5 brands` si il s'agit d'icône de marques (Facxeboo, Twitter,...).

Voici un exemple de code fonctionnel:

```css
.icon {
  display: grid;
  place-items: center;
  font-family: "Font Awesome 5 Free"; 
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  font-style: normal;
  font-variant: normal;
  font-weight: 900; 
}

.brand{
  font-family: "Font Awesome 5 Brands";
}

.facebook::before {
  content: '\f39e';
  font-size: 1.5em;
}
```

```html
<div class="icon brand facebook"></div>
```

[:arrow_up: Revenir au top](#table-des-matières)

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)
