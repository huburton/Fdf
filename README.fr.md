# FdF — cartes d'altitude en fil de fer

*[English version](README.md)*

Lit une grille d'altitudes et la dessine en paysage filaire isométrique, en C avec la MiniLibX (une petite
bibliothèque graphique pour X11). Projet de l'école 19 (réseau 42).

![La carte mars.fdf rendue en fil de fer isométrique](docs/mars.webp)

## Ce qu'il fait

- Il lit les cartes `.fdf` (une altitude par point) et vérifie les lignes mal formées ou de longueurs inégales.
- Il projette chaque point en isométrie, puis met la carte à l'échelle et la centre dans la fenêtre.
- Il trace les segments entre voisins avec l'algorithme de Bresenham, directement dans le tampon de l'image.
- Les grosses cartes (`julia.fdf` et `elem-fract.fdf`, fournies, font 2,8 Mo chacune) sont lues par blocs
  dans un tampon qui s'agrandit, avant l'analyse.
- `Échap` ou la croix de la fenêtre quitte en libérant tout.

## Compilation et lancement

Il faut `make`, un compilateur C et les paquets de développement X11 (`libx11-dev libxext-dev libbsd-dev`
sous Debian/Ubuntu). La MiniLibX et ma libft sont incluses dans `resources/`.

```bash
make
./fdf resources/maps/mars.fdf
```

Une vingtaine de cartes de test sont dans `resources/maps/` (`42.fdf`, `pyramide.fdf`, `julia.fdf`…).
