---
layout: post
title:  Uncertainty propagation just got easier
date: 2018-10-23 15:02:00+0100
description: New tools to easily propagate uncertainties for marine CO<sub>2</sub> system
---

Have you ever wanted to include the uncertainties along with your
calculated marine CO<sub>2</sub> system variables? Although a basic
requirement for good science, the only way forward has been to code it
yourself.  Fortunately, it just got a lot easier.

Marine scientists who study the ocean CO<sub>2</sub> system often use
two of its measured or modeled variables to calculate the others,
doing so with available public software packages. For instance, ocean
pH is often calculated, not measured or modeled directly. But what
about the uncertainties associated with those calculations?
Unfortunately, they are seldom reported because none of the packages
have provided an uncertainty propagation feature.

The few groups that have reported uncertainties have rolled their own,
relying on different approaches, specifying different input
uncertainties, and often assuming globally uniform sensitivities of
calculated variables to input variables.

To allow such uncertainty propagation to become routine, the
[OA-ICC](https://www.iaea.org/services/oa-icc) funded an effort to
code a consistent set of tools in several public packages.
Uncertainty propagation add-ons are now available for four of these
packages: [CO2SYS-Excel](https://github.com/jamesorr/CO2SYS-Excel),
[CO2SYS-MATLAB](https://github.com/jamesorr/CO2SYS-MATLAB),
[seacarb](http://CRAN.R-project.org/package=seacarb), and
[mocsy](https://github.com/jamesorr/mocsy).  Clicking on those links
will lead you directly to the archive where each package can be
downloaded, on CRAN for seacarb and on GitHub for the other 3
packages.

The interface for the CO2SYS-Excel add-on is provided in the same file
as the standard package but as an additional (fourth) Excel sheet,
where input uncertainties (standard uncertainties) are entered and
where calculated uncertainties (combined standard uncertainties) are
displayed (after clicking the red START button on Sheet 3). For the
add-ons to the other three packages, each is provided as a new routine
called `errors` with a suffix that depends on the computer language of
each package (`.m`, `.R`, and `.f90`). Its arguments are just like those for
the preexisting routine in each package that computes carbonate
chemistry variables (`CO2SYS.m`, `carb.R`, and `vars.f90`,
respectively) except that there is also a new line of arguments for
the input uncertainties.  Besides the typical documentation
for each package, the new archives for CO2SYS-MATLAB, seacarb, and
mocsy also contain a `notebooks` directory, which itself contains `jupyter` notebook files with extensive examples.  Once in that directory, just click on
a notebook file to visualize its contents as HTML. Even better,
download them and and run them interactively in your browser as `jupyter`
notebooks.

A new publication detailing this effort, the tools, and interpretation
of results is now available (Orr et al., 2018).


REFERENCE

Orr, J. C., Epitalon, J.-M., Dickson, A. G., and Gattuso, J.-P. Routine uncertainty propagation for the marine carbon dioxide system, *Mar. Chem.,* in press, [doi:10.1016/j.marchem.2018.10.006](https://doi.org/10.1016/j.marchem.2018.10.006), 2018. 
