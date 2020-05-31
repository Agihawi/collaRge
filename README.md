# collaRge - A simple R package made for the bioinformatics programming challenges

### A quick example:

```
library(devtools)
install_github("Agihawi/collaRge/collaRge")
library(collaRge)
library(imager)
parrots.cp <- load.example("parrots")
collage <- create_collage(parrots.cp, plot_image=FALSE)
plot(collage)
```

### For a file on the internet, just provide the url!

If you don't like the look, just run the function again and colours will be randomly generated. just adjust your filename to wherever you want to save it.

```
sample_human <- load.image('https://github.com/Agihawi/collaRge/blob/master/tests/sample_human.png?raw=true')
human_collarge <- create_collage(sample_human, plot_image=TRUE, filename_to_save='tests/many_humans.png')
```

![](tests/many_humans.png)
