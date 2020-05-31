# collaRge - A simple R package made for the bioinformatics programming challenges

A quick example:

```
library(devtools)
install_github("Agihawi/collaRge/collaRge")
library(collaRge)
library(imager)
parrots.cp <- load.example("parrots")
collage <- create_collage(parrots.cp, plot_image=FALSE)
plot(collage)
```

