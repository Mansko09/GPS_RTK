# GPS_RTK
Projet d'électronique réalisé en groupe par Léo GLORIA, Justine XIANG et Mantoulaye MBENGUE
Par construction, le GPS n'est pas assez précis pour la navigation autonome (~5m). 
Mais il existe un moyen d'améliorer grandement sa précision (~5cm), en comparant les résultats obtenus entre un GPS mobile et un autre fixe, situé dans la même zone géographique
 
Que sont les systèmes RTK? (Real Time Kinematic)
En pratique, les systèmes RTK utilisent un récepteur fixe (station de base dont la position est connue précisément) et un certain nombre de récepteurs mobiles. La station de base compare la position calculée à partir du signal GPS et la position réelle, puis réémet les corrections à apporter vers les récepteurs mobiles

Nous avons les objectifs suivants:
- Tester la précision d'un GPS seul
- Tester la précision d'un GPS en mode RTK 
- Effectuer les calculs RTK en mode sans écran
- Remonter les informations obtenus dans une IHM

Nous avons à disposition un NEO-7M-0-000 avec sa datasheet: https://www.snapeda.com/parts/NEO-7M-0-000/U-Blox%20America/datasheet/ 
