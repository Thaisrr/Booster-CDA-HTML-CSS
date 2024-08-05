# Le CSS

## Cascading StyleSheets

- fichier en .css
- Styliser du HTML

S'utilise soit dans le HTML, dans une balise `style`, soit dans un fichier à part, importé dans HTML.
( Soit en ligne, directement dans la balise HTML, mais c'est moche !)

## Selecteurs

- Balise HTML -> on utilise simplement le nom de la balise
- Classe -> nom réutilisable qu'on donne à un ou plusieurs éléments pour le viser.
- ID -> nom unique qu'on donne à un élément.

La balise est la plus générale, ensuite c'est la classe, enfin, l'id.
Donc en terme de priorité le CSS s'applique d'abord sur les balises, puis réécrit le style pour les classes, 
et enfin, réécrit le style pour les ID.

Syntaxe du CSS :
```
selecteur {
    propriété : valeur
}

balise {}

.classe {}

#id {}

parent enfant {} // tous les enfants d'un parent

parent > enfant {} // tous les enfants direct d'un parent
```


## Les Couleurs : 

- nom de couleur prédéfinie ( https://fr.wikipedia.org/wiki/Couleur_du_Web )
- hexadecimal ( de #000000 à #ffffff );
- rgb : rougevert blue rgb(5, 100, 90,);
- hsl : hue saturation lightness hsl(360, 100%, 100%);
-> rgb, hsl et hexa peuvent prendre un 4eme paramètre pour l'opacité, en pourcentage (ou en hexa pour hexadecimal )
https://coolors.co/
https://colorhunt.co/palettes/popular
https://www.realtimecolors.com
https://zippystarter.com/tools/shadcn-ui-theme-generator


## Les Tailles
Valeurs variables
- pixel -> 1 pixel d'écran = un ou plusieurs
- em -> 1 fois la taille de la police du bloc ou on se trouve
- rem -> 1 fois la taille de la police globale
- % -> 100% = taille du bloc parent ou de la police parente
- vw -> Largeur de la fenêtre ( view width ): 100vw = toute la taille de la fenêtre
- vh -> Hauteur de la fenêtre ( view Height) : 100vh = toute la hauteur

Valeurs fixes
- cm
- points ( imprimerie )
- ...


## Autres Selecteurs

Selecteurs de base : balise, .class, #id

### Selecteur universel

```css
* {
    box-sizing: border-box;
}
```

### Selecteur de classe plus précis


```css
.class1.class2 {
    /* selectionne les éléments qui ont class1 ET class2 */
}
```

### Selecteur de descendant

Selectionne un enfant d'un élément
```css
.parent .enfant {
    /* ici, on stylise .enfant quand il est dans un .parent */
}
```

### Selecteur de descendant direct

Selectionne uniquement les enfants directs d'un parent
```css
.parent > .enfant {}
```

### Selecteur d'élément suivant

```css
.label + input {
    /* selectionne les input qui suivent un label */
}
```

### Selecteur d'élément suivant direct

Selectionne l'élément qui suit directement

```css
p ~ div {
    /* selectionne les div qui suivent directement un p */
}
```

## Les Pseudos Selecteurs

Permettent de modifier un élément en fonction de son etat

### Hover

Permet de donner un style spécifique à un élément quand la souris est dessus

```css
button:hover {
    
}
```

### focus

Lorsque l'utilisateur.trice est sur un élément cliquable ( input, button, lien, ...)

```css
input:focus {}
```

### active

Lorsqu'on clique sur un élément ( très bref )

```css
a:active {}
```

### visited

Lorsqu'un lien à déjà été visité

```css
a:visited {}
```

### link

Etat d'un lien par défaut ( quand il n'y a pas d'action dessus )

```css
a:link {}
```

Pour modifier un lien, il faut respecter un ordre dans les pseudo selecteurs : 
LoVe Hate
Link - Visited - Hover

## Les pseudo selecteur de position

Selectionne des éléments en fonction de leur position

### first-child
- Selectionne l'élément quand il est le premier enfant

```css
p:first-child {}
```

### first-of-type
Selectionne le premier enfant de son type, dans une liste d'éléments frères

```css
article:first-of-type {}
```

### last-child
Selectionne le dernier enfant d'une liste

```css
p:last-child {}
```

### last-of-type
Selectionne le dernier element de son type dans une liste de frères

```css
article:last-of-type {}
```

### nth-child
Selectionne un élément à une position spécifique

```css
p:nth-child(2) {}
```

On peut selectionner un élément sur deux, les pairs (even) et impairs (odd)

```css
p:nth-child(even) {}
```

### first-letter

Selectionne la première lettre d'un élément

```css
p:first-letter {}
```

### first-line

Selectionne la première ligne d'un élément

```css
p:first-line {}
```

## Le Display

C'est le comportement d'un élément par rapport aux éléments autour

### inline

Un élément inline se place en ligne, à côté d'un autre élément inline. 
Sa taille correspond à son contenu.
On ne peut ni modifier la hauteur, ni la largeur.

Par défaut : `a`, `span`, `strong`, `i`, `b`, `em`, ... -> balises de texte enrichies

### block

Les élements de type block se placent les uns en dessous des autres, le en haut à gauche possible.
Ils prennent toute la largeur disponible ( width : 100%).
Leur hauteur correspond au contenu.
On peut modifier la largeur et la hauteur.

Défaut : les balises de structure : `div`, `p`, `h1`, `h2`, `article`, `section`...

### inline-block

Les éléments se placent les uns à côtés des autres ( entre élément inline / inline-block ).
On peut modifier leur hauteur / largeur.

Par défaut : `img`, `input`, `button`, `textarea`

=> Astuce : pour centrer un élément de type inline, ou inline block, on utilise `text-align: center` sur le parent.

### none

En display none, l'élément est supprimé du document.


## La Position

Modifier la façon dont un élément se positionner par rapport à sa position initiale, ou par rapport aux autres éléments.

Par défaut, c'est la `position: static` qui est utilisée.

### Position relative

Modifie la position d'un élément par rapport à sa position initiale.
Pour les autres éléments, c'est comme si l'élément n'avait pas bougé.

### Position absolute

En position absolute, on place l'élément par rapport au parent le plus proche ayant une position relative.
( ou autre que static ). Si aucun parent n'est trouvé, alors elle se positionne par rapport au body.
Pour les autres éléments, l'élément en absolute sort du flux, il n'existe plus. 

### Position fixed

En position fixed, l'élément sort du flux.
Il se place par rapport à la fenêtre, et reste à sa place malgré le scroll.

### Position sticky

En position sticky, l'élément se positionne là où il doit être par défaut, 
Mais il va prendre une position au scroll de son parent.
Quand le disparait, l'élément disparait aussi

### z-index

Il permet de gérer la superposition des éléments, on indiquant leur position sur l'axe Z.
C'est l'élément avec un z-index plus élevé qui sera au dessus des autres.
On peut aller dans le négatif pour reculer un élément.


## Float

Un élément en float est retiré du flux normal du document pour se positionner soit à droite, soit à gauche.
Les autres éléments frères se positionneront autour du float.

## Les Flexboxes

Les flexboxes permettent de gérer la disposition des éléments par rapport à leur parent.
C'est le parent qui va gérer la façon dont les enfants vont se disposer.

Sur le conteneur ( le parent : )
```css
.parent {
    display: flex;
}
```

Ensuite, on gère l'alignement horizontal avec 
`justify-content` : flex-start (defaut) | center | flex-end | space-between | space-around | space-evenly

Et l'alignement vertical avec
`align-items` : flex-start | flex-end | stretch ( defaut ) | center | baseline

Par défaut, le parent va essayer de garder tous ses enfants sur une seule ligne, quitte à déborder/
On gère ce comportement avec `flex-wrap: wrap`

On peut gérer la direction des enfants ( row ou column ) avec `flex-direction`.
Attention, en column, justify-content sert à modifier l'axe Y, et align-items l'axe X !( ça s'inverse )

On peut jouer avec l'ordre des éléments en leur mettant la propriété `order`.
Par défaut, l'ordre d'un élément est à 0. On va mettre -1 pour mettre devant, ou 1 pour mettre à la fin.

On peut demander à un élément d'être plus grand que les autres avec `flex-grow`;

Pour apprendre les flex : https://flexboxfroggy.com/#fr