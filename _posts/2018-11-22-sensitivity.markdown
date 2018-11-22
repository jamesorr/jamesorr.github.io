---
layout: post
title:  Easy & accurate sensitivities for marine CO<sub>2</sub> system
date: 2018-10-23 15:02:00+0100
description: New tools to help deconvolve controls of marine CO<sub>2</sub> variables
---

Marine scientists often assess the causes of variations
in CO2 system variables are by applying a
Taylor series decomposition, but results don't always add up. For
example, with $$pCO2 = f(DIC, Alk, T, S)$$, we often rely on a
first-order Taylor-series decomposition to quantify the
contributions the total change in pCO2 

$$
\Delta pCO2 = \frac{\partial pCO2}{\partial DIC} \Delta DIC
            + \frac{\partial pCO2}{\partial Alk} \Delta Alk
	    + \frac{\partial pCO2}{\partial T} \Delta T
	    + \frac{\partial pCO2}{\partial S} \Delta S
$$

That equation sums the contributions from the simultaneous changes
($$\Delta$$) in the 4 input variables, where each is multiplied by a
partial derivative (sensitivity) giving it the same units as the total
change.  

Results may not add up (the right side may not equal the left) though
if the $$\Delta$$s are inaccurate, e.g., if some of them are measured
imprecisely, or if they are too large and the system is
nonlinear. Furthermore, the sensitivities must be accurate, an issue
that has been often overlooked. Because there is a delicate balance
between terms in some regions, even minor imprecisions in the
sensitivities of say 10% can lead to the wrong
conclusions. Fortunately, those performing such analysis can now avoid
approximated sensitivities by relying instead on recent routines that
compute the sensitivities accurately.

Highly accurate sensitivities are provided by the new routines that
were released along with the publication describing the
[OA-ICC](https://www.iaea.org/services/oa-icc)-funded effort to
provide uncertainty propagation add ons in several public software packages
that compute CO2 system variables(Orr et al., 2018). These packages include
[CO2SYS-MATLAB](https://github.com/jamesorr/CO2SYS-MATLAB),
[seacarb](http://CRAN.R-project.org/package=seacarb), and
[mocsy](https://github.com/jamesorr/mocsy). Clicking on those links
will lead you directly to the archive where each package can be
downloaded, on CRAN for seacarb and on GitHub for the other 2
packages.

Each package includes a new routine called `derivnum` with a suffix that
depends on the computer language of each package (`.m`, `.R`, and
`.f90`). Input arguments are just like those for the preexisting routine
in each package that computes carbonate chemistry variables
(`CO2SYS.m`, `carb.R`, and `vars.f90`, respectively) except that there
is also one new argument added to the beginning of the list to specify
the variable with respect to which derivatives will be taken.

Besides the typical documentation for each package, the new archives
for CO2SYS-MATLAB, seacarb, and mocsy also contain a `notebooks`
directory, which itself contains `jupyter` notebook files with
extensive examples.  Once in that directory, just click on the
appropriately naled notebook file to visualize its contents as
HTML. Even better, if you download a package, those notebook files
will be available locally; you may run them interactively in your
browser as `jupyter` notebooks.

More details about these routines are available in Orr et al. (2018).


REFERENCES

Kwiatkowski, L., and Orr, J. C. (2018) Diverging seasonal extremes for
ocean acidification during the twenty-first century, Nature Climate
Change 8, 2, 141–145,
[doi:10.1038/s41558-017-0054-0](https://www.nature.com/articles/s41558-017-0054-0).

Orr, J. C., Epitalon, J.-M., Dickson, A. G., and Gattuso, J.-P. (2018) Routine uncertainty propagation for the marine carbon dioxide system, *Mar. Chem. 207,* 84-107, [doi:9.1016/j.marchem.2018.10.006](https://doi.org/10.1016/j.marchem.2018.10.006). 
