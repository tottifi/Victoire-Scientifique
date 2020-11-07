# Victoire-Scientifique

## Développement Scientifique dans le Monde depuis 1900

---

La Carte est disponible sous deux formats pour plus de facilité de lecture: _Carte.gif_ et _Carte.mp4_.

Pour utiliser les points personalisées de la carte (Les prix Nobels et les Spatioports) il est nécessaire d'ajouter le chemin vers le dossier _svg_ dans : Préférences -> Options -> Système -> SVG Paths.

---

Quant aux sources de données:
- _victoire\_scientifique.qgz_ contient le projet QGIS (En version 3.14, la méthode pour le temps utilisée est le Temporal Controller et non le Time Manager, mais cela est aisément reconfigurable)
- _osm\_world\_universities.geojson_ contient les points des universités du monde récupérés deuips OpenStreetMap

_Frames_ est un dossier contenant les frames utilisées pour générer la carte à l'aide de la commande suivante depuis Linux (Ensuite remodifiée à l'aide de https://ezgif.com):
```
ffmpeg -i victoire_scientifique%0004d.png -vf "split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" out.gif
```

_heatmap_ est un dossier contenant le fichier permettant de réutiliser la heatmap sur le projet (Par défaut ce sont des couches temporaires, il faut donc les générer).

_Legende_ est un dossier contenant notre légende géoréférencée. Cela est nécessaire car il n'est pas possible d'obtenir une mise en page pour une exportation en tant qu'animation.

_ne\_10m\_admin\_0\_countries_ contient les bordures des pays récupérées sur Natural Earth.

_nobel_ contient les données récupérée en ligne des prix nobels discerné dans les catégories suivantes: Chimie, Médecine, Physique et Turing (Informatique). Le dossier contient aussi un _Points\_Positions.gpkg_ que nous avons créé afin de réaliser une jointure entre les pays ayant obtenus les prix nobels et une position par points, ce qui nous a permis de générer la jointure _Jointure\_generee\_Pays\_Nobels.geojson_.

_spatioports_ contient des données entièrements réarrangées des positions des différents spatioports mondiaux venant de https://fr.wikipedia.org/wiki/Liste_des_bases_de_lancement. Seuls les spatioports ont été conservés, les bases de lancements de fusées sondes n'étant pas essentielles.

_svg_ contient les images personalisées utilisées dans la carte au format SVG.