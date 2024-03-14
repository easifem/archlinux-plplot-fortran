# PlPlot with Fortran bindings on ArchLinux.

PlPlot is a cross-platform software package for creating scientific plots. 
This repository contains the plplot build for Fortran on archlinux.

You can read more about the plplot [here](https://plplot.sourceforge.net/). Also, see some [examples](https://plplot.sourceforge.net/examples.php)

## The problem:

The AUR repository on https://aur.archlinux.org/packages/plplot does not build PlPlot with fortran bindings. This is because the PKGBUILD file set `ENABLE_fortran` to false. 

## Temporary solution
This repository is the temporary solution to the above problem. In this repository, `ENABLE_fortran` is set to `true`. 
This repository is mainly for resolving the external dependencies of EASIFEM.

