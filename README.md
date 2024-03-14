# PlPlot with Fortran bindings on ArchLinux.

PlPlot is a cross-platform software package for creating scientific plots. 
This repository contains the plplot build for Fortran on archlinux.

The AUR repository on https://aur.archlinux.org/packages/plplot does not build PlPlot with fortran bindings. This is because the PKGBUILD file set `ENABLE_fortran` to false. In this repository, `ENABLE_fortran` is set to `true`. This repository is mainly for resolving the external dependencies of EASIFEM.

