
# ANCIEN PROJET: GPS_RTK
Projet d'électronique réalisé en groupe par Léo GLORIA, Justine XIANG et Mantoulaye MBENGUE
Par construction, le GPS n'est pas assez précis pour la navigation autonome (~5m). 
Mais il existe un moyen d'améliorer grandement sa précision (~5cm), en comparant les résultats obtenus entre un GPS mobile et un autre fixe, situé dans la même zone géographique

Nous avons à disposition un NEO-7M-0-000 avec sa datasheet: https://www.snapeda.com/parts/NEO-7M-0-000/U-Blox%20America/datasheet/ 

Nous avons les objectifs suivants:
- Tester la précision d'un GPS seul
- Tester la précision d'un GPS en mode RTK 
- Effectuer les calculs RTK en mode sans écran
- Remonter les informations obtenus dans une IHM

Avant cela, nous allons étudier le GPS RTK:

 Qu'est-ce que le système GPS?
Un GPS est composé de satellites et d’un récepteur.
Chaque satellite est à une distance d’environ 20 km de la terre. Ils sont environ une trentaine qui tournent autour de la terre (pas dans le même sens), de telle sorte qu’à tout moment où l’on souhaite déterminer une position, on a à disposition entre 5 et 10 satellites.
Le récepteur GPS est un boîtier (ce qu’on achète dans le commerce) composé d’une antenne (permet d’avoir une bonne qualité du signal), de composants électroniques (ajoutent du bruit) et d’une batterie (autonomie).


 Fonctionnement du GPS:
- déterminer la distance L entre le satellite et le récepteur:
Tous les satellites sont équipés d’une horloge atomique très précise
Chaque satellite envoie un signal (un pulse) au boitier GPS contenant des informations sur le nom du satellite, la position du satellite dans l’espace, sur le temps d’envoi du signal tdépart .
Le récepteur enregistre le temps tarrivé où le signal est reçu.
On a L=(tarrivé-tdépart)*c,  avec c la célérité de la lumière (les ondes radio se déplacent à la vitesse de la lumière)
- Localiser le récepteur:
On connaît la distance avec les trois satellites: L1,L2 et L3
Prenons l’exemple de vouloir localiser une personne:
La technique utilisée par le GPS est la triangulation 3D: on a besoin de trois satellites.
En effet, dans le monde tridimensionnel un premier satellite sait que la personne se situe sur une sphère de rayon  (distance satellite-personne).
Avec l’utilisation d’un deuxième satellite, la position se réduit à un cercle (intersection de deux sphères). 
Enfin, l’intersection avec un troisième satellite nous permet de réduire les possibilités de positions à 2.
En utilisant la surface de la terre, on élimine la solution improbable (qui se situerait dans l’espace).

 Limites du GPS:
Le récepteur GPS doit capter les signaux provenant de satellites, il aura donc des problèmes pour les capter lorsque le récepteur ne voit pas le ciel: Bâtiments, forêts, et montagnes 
 
 Que sont les systèmes RTK? 
Définition RTK: Real Time Kinematic: une technique précise de positionnement par satellite qui permet d’obtenir des résultats avec une précision au centimètre près, ce qui en fait un outil efficace pour les géomètres, dans le monde entier.

En pratique, les systèmes RTK utilisent un récepteur fixe (station de base dont la position est connue précisément) et un certain nombre de récepteurs mobiles. La station de base compare la position calculée à partir du signal GPS et la position réelle, puis réémet les corrections à apporter vers les récepteurs mobiles


Etude du GPS  NEO-7M-0-000 
Logiciels: Ublox et RTK lib 

## NOUVEAU PROJET: Module pour écran de retour pour l'Amphi Watteau

En quoi consiste notre projet?
créer un boîtier avec 4 boutons, qui permettra selon le bouton sur lequel on appuiera et une caméra, d'afficher sur un mini écran un zoom du tableau à craies ou du cours projeté. Ce boîtier permettra aux étudiants PMR (dont les places sont au fond de l'amphithéâtre) de mieux voir le cours projeté ou écrit. Pour ce faire: nous devons configurer les 4 boutons grâce à une carte STM32; relier cette carte au réseau, à la caméra (grâce à un câble HDMI) et à une matrice 8x8 (qui sera connectée à l'écran).


  Etapes du projet:

1. Définition des besoins et spécifications : Identification des différentes configurations du tableau à craies à afficher, le type d'écran à utiliser, les interactions utilisateur avec les boutons.

2. Programmation de la carte Nucleo H7A3 : Utilisation d'IDE pour écrire le 
code qui contrôlera les interactions avec les boutons, la capture d'image à partir de la caméra et l'affichage des différentes configurations sur l'écran. 

3. Programmation des boutons poussoirs: https://forum.digikey.com/t/controlling-neopixels-with-stm32/20527

4. Assemblage des composants : Une fois que le programme pour allumer les LEDs est vérifié, on procède à l'assemblage des composants, y compris la caméra, l'écran et les boutons, conformément au schéma et au design prévus. On vérifie le soudage de chaque composant et les connexions.

5. Conception du boîtier sur Onshape et impression 3D

6. Test et débogage : tests approfondis pour s'assurer que le boîtier fonctionne comme prévu.






