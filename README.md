# EmmanuelAbete_3_19012022

MES CHOIX TECHNIQUES
____________________

L’avantage que j'ai eu à utiliser CSS Grid plutot que Flexbox à certains moments, c'est que sur certains points, j'avais des réglages moins complexes à effectuer dans le choix des propriétés CSS. Selon certaines circonstances, CSS Grid m'a semblé avantageux soit pour la mise en page intégrale, soit pour une partie de mise en page.

Dans le dossier "sass", j'ai créé le fichier "base.scss" pour y mettre tout ce qui concerne la configuration, notamment les "fonts". (Chemin de destination :  EmmanuelAbete_3_19012022/sass/base.scss)

J'ai mis le bouton "Explorer nos restaurants" dans un fichier "explorer.scss" à l'intérieur du dossier "layout" que j'ai créé. (Chemin de destination :  EmmanuelAbete_3_19012022/sass/layout/explorer.scss)

J'ai créé un fichier "mixins.scss" dans le dossier "utils". (Chemin de destination :  EmmanuelAbete_3_19012022/sass/utils/mixins.scss)
Dans le fichier "mixins.scss", j'ai placé les propriétés CSS correspondant au dégradé de couleur pour le bouton "Explorer nos restaurants" et pour le remplissage des coeurs au passage de la souris.

J'ai mis la liste des @use dans le fichier "style.scss". 
________________________________________________________

ANIMATION : Coeurs

Pour insérer les coeurs, tout d'abord, je suis allé dans la documentation de "Font Awesome". 
J'ai cliqué sur "CSS Pseudo-elements". Dans cette rubrique, j'ai copié les propriétés CSS correspondant à la balise <style> et je les ai collées dans un élément "::before" que j'ai créé. 

Ensuite, toujours dans la rubrique "CSS Pseudo-elements" de "Font Awesome", j'ai copié les propriétés CSS correspondant à la class ".login::before", et je les ai collées. J'ai fait quelques modifications pour que ça colle avec ce qui était demandé.

Ensuite, dans la propriété "content" que j'ai copiée, j'ai remplacé l'unicode "f007" par l'unicode "f004" correspondant au coeur provenant de "Font Awesome".
  
C'est en jouant sur le font-weight que j'ai pu créer le changement de forme du coeur au passage de la souris.

Les propriétés CSS du coeur, localisées dans l'élément "::before", je les ai refactorisées dans le fichier "mixins.scss".
  
Ensuite, j'ai créé l'élément "::after". J'y ai inclus les propriétés CSS que j'avais refactorisées dans mes "mixins", notamment le dégradé de couleurs. 
Pour que le coeur soit rempli au passage de la souris, j'ai changé le font-weight en 900.

Ensuite, j'ai configuré le ":hover" de la class .card__description de telle manière que l'élément "::after" ait une opacité de 1. 
  
Pour que le remplissage du coeur grossisse au passage de la souris, j'ai rajouté la propriété "transform" avec une valeur translateY de (-50%) et un scale de 1.1. 
________________________________________________________
  
ANIMATION : Carrés verts qui apparaissent
  
Dans le dossier "utils", j'ai créé un fichier "animations.scss". 
  
Dans ce fichier, j'ai créé une règle @keyframes que j'ai nommé "quarterspin" avec les propriétés CSS que vous pourrez voir. Et j'ai importé le "quarterspin" dans le ":hover" de "i". 

J'ai utilisé la propriété "white-space" avec la valeur "nowrap"  pour forcer le texte à rester sur une seule ligne.
  
Pour que la partie du texte située à l'extérieur ne soit pas visible lorsque je réduis le responsive, j'ai utilisé la propriété "overflow" avec la valeur "hidden".
  
Pour afficher les trois petits points qui indiquent que le texte est rogné, j'ai utilisé la propriété "text-overflow" avec la valeur "ellipsis".
  
Pour que le check des carrés verts gardent la même taille lorsque je réduis le responsive, j'ai appliqué la propriété "flex-shrink" avec une valeur de 0.
________________________________________________________
  
ANIMATION : Menus qui apparaissent progressivement
  
J'ai utilisé la pseudo-classe "nth-child(#{$i}) {animation-delay: 100ms *$i}".

Ca veut dire que le premier enfant de la class ".menus__category" a une animation-delay de 100ms, le deuxième enfant de la class ".menus__category" a une animation-delay de 200ms, le troisième enfant de la class ".menus__category" a une animation-delay de 300ms.
________________________________________________________
  
ANIMATION : Loader
  
J'ai créé cette animation à l'aide d'un pseudo-élément, en pur CSS.

J'ai expérimenté un "display: grid" sur la class .loader, et ça a bien fonctionné. 
Le problème c'est que si maintenant j'applique à la place du "display: grid" un "display: flex", le loader se positionnera par erreur à gauche au lieu de se positionner au centre. 
    
Pour que l'élément en arrière-plan du loader reste à sa dernière place, j'ai utilisé la propriété "animation". En y appliquant la valeur "forwards", l'élément en arrière-plan conserve sa dernière position avant l'animation.
________________________________________________________
