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