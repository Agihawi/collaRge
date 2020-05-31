#' A function to randomise colours in an image
#'
#' This function allows you to randomise RGB values in an imager image
#' @param pretty_image Set the pretty_image to an imager file that you want
#' @return Return a colourised image
#' @keywords pretty image random colours
#' @import imager graphics stats
#' @export
#' @examples
#' library(imager)
#' parrots.cp <- load.example("parrots")
#' randomise_colours(parrots.cp)
randomise_colours <- function(pretty_image) {
  #define number and subsample of R,G,B to use
  subsample_n <- floor(runif(n=1, min=1, max=2.9))
  to_use <- sample(c('R', 'G', 'B'), size=subsample_n, replace=FALSE)

  if ('R' %in% to_use) {
    R(pretty_image) <- runif(n=1, min=0, max=1)
  }
  if ('G' %in% to_use) {
    G(pretty_image) <- runif(n=1, min=0, max=1)
  }
  if ('B' %in% to_use) {
    B(pretty_image) <- runif(n=1, min=0, max=1)
  }
  return(pretty_image)
}

#' A function to create a collage of randomly colourised image
#'
#' This function allows you to produce a collage of an image with random colourings and save to file
#' @param pretty_image Define a pretty image using imager package
#' @param plot_image if TRUE the image will be plotted to the console. Default=FALSE
#' @param filename_to_save Where should the image be saved? ie ./image.jpeg. default=NULL
#' @return  Return a beautiful collage
#' @keywords pretty image random colours collage
#' @export
#' @examples
#' library(imager)
#' parrots.cp <- load.example("parrots")
#' create_collage(parrots.cp, plot_image=TRUE, filename_to_save = '~/Desktop/jungle.jpeg')
create_collage <- function(pretty_image, plot_image=FALSE, filename_to_save=NULL){
  #randomise colours 4 times
  pretty_image1 <- randomise_colours(pretty_image)
  pretty_image2 <- randomise_colours(pretty_image)
  pretty_image3 <- randomise_colours(pretty_image)
  pretty_image4 <- randomise_colours(pretty_image)

  #prepare top rows
  top_row <- imappend(list(pretty_image1, pretty_image2), "x"  )
  bottom_row <- imappend(list(pretty_image3, pretty_image4), "x")

  new_image <- imappend(list(top_row, bottom_row), "y")

  #plot also if requested by function
  if (plot_image == TRUE) {
    plot(new_image)
  }

  #save file if requested
  if (!is.null(filename_to_save)) {
    imager::save.image(new_image, filename_to_save)
  }

  return(new_image)
}


#create_collage(parrots.cp, plot_image=TRUE, filename_to_save = '~/Desktop/jungle.jpeg')
