MixSIARgui
=============

`MixSIARgui` creates a graphical user interface (GUI) for the [MixSIAR](https://github.com/brianstock/MixSIAR) package. The GTK-based R packages that the MixSIAR GUI depends on are no longer supported on CRAN, so for `MixSIAR` to remain on CRAN it was necessary to split the GUI off into its own package, which will remain on GitHub. 

MixSIAR ([paper](https://peerj.com/articles/5096/), [R package](https://github.com/brianstock/MixSIAR)) is a framework to run Bayesian mixing models to analyze biological tracer data (i.e. stable isotopes, fatty acids), which estimate the proportions of source (prey) contributions to a mixture (consumer). MixSIAR is not one model, but a framework that allows a user to create a mixing model based on their data structure and research questions, via options for fixed/random effects, source data types, priors, and error terms. MixSIAR represents a collaborative coding project between the investigators behind MixSIR, SIAR, and IsoSource: Brice Semmens, Brian Stock, Eric Ward, Andrew Parnell, Donald Phillips, and Andrew Jackson.

## Basic use

```
library(MixSIARgui)
mixsiar_gui()
```

![MixSIAR GUI.](https://github.com/brianstock/MixSIAR/blob/master/Manual/mixsiar_gui_shot.png)

<img src="https://github.com/brianstock/MixSIAR/blob/master/Manual/mixsiar_gui_shot.png" width="100" height="150">

There is an extensive user manual included in the package install. To find the directory location on your computer:
```
find.package("MixSIAR")
```

The manual is also available from the GitHub site [here](https://github.com/brianstock/MixSIAR/blob/master/inst/mixsiar_manual_small.pdf).

## Installation

The GUI requires GTK+ to be installed, and the instructions are platform-specific ([Windows](#Windows), [Mac](#Mac), [Linux](#Linux)). Installation is a breeze on Linux, alright on Windows, and difficult on Mac.

#### Windows

1. Download and install/update [R].
2. Download and install [JAGS].
3. Open R. 
4. Install GTK+ dependent packages:

    ```
    install.packages(c("gWidgets", "RGtk2", "gWidgetsRGtk2", "devtools"))
    ```

5. Load `RGtk2`. You will be prompted to install GTK+. **Follow the automatic prompts and do not interrupt the GTK+ installation!**:

```
library(RGtk2)
```

6. Restart R and run:

```
devtools::install_github("brianstock/MixSIARgui", dependencies=T) # installs MixSIAR as dependency
```

7. Load MixSIAR and run GUI:

```
library(MixSIARgui) # also loads MixSIAR
mixsiar_gui()
```

#### Mac

1. Download and install/update [R].
2. Download and install [JAGS].
3. Open R. 
4. Install GTK+ dependent R packages:
```
install.packages(c("gWidgets", "RGtk2", "gWidgetsRGtk2", "devtools"))
```
5. Close R.
6. Download and install the newest [GTK+ framework].
7. Install the latest X11 application, [xQuartz].
8. Open R and run:
```
devtools::install_github("brianstock/MixSIARgui", dependencies=T) # installs MixSIAR as dependency
```
9. Load MixSIAR and run GUI:
```
library(MixSIARgui) # also loads MixSIAR
mixsiar_gui()
```

If the above steps do not work, try information in the links below. The goal is to install and load `RGtk2` without problems.

https://github.com/davidcsterratt/retistruct/issues/4
http://marcoghislanzoni.com/blog/2014/08/29/solved-installing-rattle-r-3-1-mac-os-x-10-9/
https://gist.github.com/sebkopf/9405675
https://yihui.org/en/2018/01/install-rgtk2-macos/
https://gist.github.com/zhiyzuo/a489ffdcc5da87f28f8589a55aa206dd

#### Linux

1. Download and install/update [R].
2. Download and install [JAGS]. From the terminal: `sudo apt-get install jags r-cran-rjags`.
3. Download and install [GTK+ framework]. From the terminal: `sudo apt-get install libgtk2.0-dev`.
4. Check if GTK+ is installed correctly. Open R, install and load the `RGtk2` package with:

```
install.packages("RGtk2","devtools")
library(RGtk2)
```

5. Install `MixSIAR` and `MixSIARgui`:

```
devtools::install_github("brianstock/MixSIARgui", dependencies=T) # installs MixSIAR as dependency
```

6. Load MixSIAR and run GUI:
```
library(MixSIARgui) # also loads MixSIAR
mixsiar_gui()
```

### Feedback

This software has been improved by the questions, suggestions, and bug reports of the user community. If you have a comment, please use the [Issues](https://github.com/brianstock/MixSIAR/issues) page.

### Citing MixSIAR:

If you use MixSIAR results in publications, please cite the MixSIAR manual as (similar to how you cite R):

> Stock BC and Semmens BX. 2016. MixSIAR GUI User Manual. Version 3.1. https://github.com/brianstock/MixSIAR. doi:10.5281/zenodo.1209993.

The MixSIAR model framework is described in:

> Stock BC, Jackson AL, Ward EJ, Parnell AC, Phillips DL, Semmens BX. 2018. Analyzing mixing systems using a new generation of Bayesian tracer mixing models. PeerJ 6:e5096 https://doi.org/10.7717/peerj.5096

[pandoc]:https://github.com/jgm/pandoc/releases/
[GTK+ framework]:http://r.research.att.com/#other
[xQuartz]:http://xquartz.macosforge.org/landing/
[R Studio]:https://www.rstudio.com/products/rstudio/download/
[R]:https://cran.r-project.org/bin/
[JAGS]:http://mcmc-jags.sourceforge.net/
[Issues]:https://github.com/brianstock/MixSIAR/issues
[SIAR Facebook group]:https://www.facebook.com/pages/SIAR-Stable-Isotope-Analysis-in-R/148501811896914

