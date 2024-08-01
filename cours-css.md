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