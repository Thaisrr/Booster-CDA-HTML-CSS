# Le HTML

- HyperText Markup Language -> hypertexte = lien
- Tim Berners Lee en 1991
- premier navigateur web : Netscape
- Yahoo
- Dans les années 2000 : web 2.0
  - Arrivée des réseaux sociaux
  - Iphone -> les pages web doivent être affichables sur téléphone

=> Aujourd'hui 70% des personnes utilisent internet sur leur téléphone
    -> Les sites doivent donc impérativement être responsive


## C'est quoi le HTML ?

- Un language de balisage ( comme : XML, SVG )
- Descriptif
- Language de base pour la création de pages web
=> Ce n'est pas un language de programmation !

Une balise :
```
<nom-balise>Contenu</nom-balise>
<balise-orpheline />
```

Aujourd'hui, on en est à la version 5 de HTML
<nom-balise>contenu <nom-balise>


## Les types de balises : 

- Balise de contenu ( texte, média, ect)
- Balise de structure ( peuvent contenir du texte, ou d'autres balises )

## Structure d'une page HTML : 

- Doctype : définit la version de HTML utilisée
- HTML : défini la page elle même
  - Head : contient des infos sur la page pour les passer au navigateur
  - Body : contenu de la page

## Les titre
    - 6 niveaux de titre
    - H1 : une seule fois par page, c'est le premier titre qui doit apparaître.
    - H2, H3, ... H6 : on les mets dans l'ordre.
    -> Pour le référencement et l'accessibilité


## Balises sémantiques : 

- Nav : encadre une liste de liens de navigations. peut être utilisé plusieurs fois dans la page.
- Header : entête d'une page, d'une section, d'un article... peut être utilisé plusieurs fois.
- Footer : pied de page / de section / d'article. Utilisable plusieurs fois.
- Section : encadre un bloc de code sur un même sujet / un même contexte. Utilisable plusieurs fois.
- Article : comme section, on peut utiliser l'un ou l'autre
- Aside : contenu secondaire ou complémentaire au contenu principal. S'utilise en dehors de main, et peut être utilisé plusieurs fois.
- Main : contenu principal de la page. Le contenu doit être unique. Ne s'utilise qu'une fois par page.

-> Les div (ou division) n'ont pas de valeur sémantique. Il faut les utiliser en dernier recours, 
pour encadrer du code à styliser / placer sur la page par exemple.