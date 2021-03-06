# IMEX_SfloW2D

IMEX_SfloW2D is a FORTRAN90 code designed to model shallow water granular flows over digital elevation models (DEMs) of natural terrain, with the friction forces described by the Voellmy-Salm rheology. The system is described by an hyperbolic system of partial differential equations with relaxation and source terms. It is possible to select a simpler rheology in order to mimic the system of equations described in Kurganov and Petrova, 2007.

One of the reasons we wrote such a software is the possibility to have an open source code that can be freely downloaded by the users, which can simply use it without any intervention on the code or they can modify and widen their own version. IMEX_SfloW2D is written in Fortran90, which has the advantage to have a simple syntax and to be well known into the scientific community.

The model is discretized in time with an explicit-implicit Runge-Kutta method where the hyperbolic part is solved explicitly and the other terms (friction) are treated implicitly to allow for larger time steps and to enforce the stopping condition. The finite volume solver for the hyperbolic part of the system is based on the Kurganov and Petrova 2007 semi-discrete central scheme and it is not tied on the specific eigen-structure of the model. The implicit part is solved with a Newton-Raphson method where the elements of the Jacobian of the nonlinear system are evaluated numerically with a complex step derivative technique. This automatic procedure allows for easy changes of the friction term.

The code can deal with different scenarios, but its first aim is to treat gravitational flows over topographies described as digital elevation models (DEMs) in the ESRI ascii format. The output files can be handled very well with gnuplot, in particular with the package it is provided a small script that create a video from the output data saved at different times. Moreover it is possible to save the solution as as ESRI ascii files, suitable for GIS softwares.

### Installation

To compile:

./configure

make

make install



The executable is copied in the bin folder.

To test the code copy the executable from the bin folder to the examples folder and:

./IMEX_SfloW2D

The code also need a DEM file in esri ascii format, named topography_dem.asc

### Webpage

https://demichie.github.io/IMEX_SfloW2D/


### Documentation

A wiki page describing the model is available at:

[https://github.com/demichie/IMEX_SfloW2D/wiki](https://github.com/demichie/IMEX_SfloW2D/wiki) 

Doxygen generated documentation of the code can be found at:

[http://demichie.github.io/IMEX_SfloW2D/html/](http://demichie.github.io/IMEX_SfloW2D/html/) 


### Authors

Mattia de' Michieli Vitturi, Giacomo Lari

### Acknowledgments

The development of IMEX-SfloW2D has been partially funded by Istituto Nazionale di Geofisica e Vulcanologia and Italian DPC (INGV - DPC B2 2016 Ob. 4 - Subtask D1).
